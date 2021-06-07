---
title: Windows Defender alkalmazásvezérlés – WDAC
description: Az alkalmazásvezérlés Windows Defender áttekintése, és annak használata a HoloLens vegyes valóságú eszközeinek kezeléséhez.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378085"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender alkalmazásvezérlés – WDAC

A WDAC lehetővé teszi, hogy a rendszergazda úgy konfigurálja az eszközeit, hogy letiltsa az alkalmazások elindítását az eszközökön. Ez eltér az eszközkorlátozási módszerektől, például a Kioszk módtól, ahol a felhasználó egy olyan felhasználói felületet kap, amely elrejti az eszközön található alkalmazásokat, de továbbra is elindítható. Bár a WDAC van megvalósítva, az alkalmazások továbbra is láthatók a Minden alkalmazás listában, de a WDAC megakadályozza, hogy az eszköz felhasználója elindítsa ezeket az alkalmazásokat és folyamatokat.

Egy eszközhöz több WDAC-szabályzat is hozzárendelhető. Ha több WDAC-házirend van beállítva egy rendszeren, a legszigorúbb házirendek lépnek életbe. 

> [!NOTE]
> Amikor a végfelhasználók olyan alkalmazást próbálnak meg elindítani, amelyet a WDAC blokkol, a HoloLensen nem kapnak értesítést arról, hogy nem tudják elindítani az alkalmazást.

Az alábbi útmutatóból megtudhatja, hogyan engedélyezheti vagy tilthatja le a [HoloLens 2-eszközökön](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)található alkalmazásokat a WDAC és a Windows PowerShell használatával a Microsoft Intune.

Amikor a felhasználók az első példalépéssel rákeresnek a Windows 10 számítógépre telepített alkalmazásokra, előfordulhat, hogy néhány kísérletet kell tenniük az eredmények szűkítésére.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Ha nem tudja a csomag teljes nevét, előfordulhat, hogy néhányszor futtatnia kell a Get-AppxPackage -name \* YourBestGuess \* nevét. Ha már megvan a név, futtassa a következőt: "$package 1 = Get-AppxPackage -name Actual.PackageName"

Ha például a következőt futtatja Microsoft Edge több eredményt ad vissza, de ebből a listából megállapíthatja, hogy a szükséges teljes név a Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Csomag családnevei HoloLens-alkalmazásokhoz

A fent hivatkozott útmutatóban manuálisan szerkesztheti a newPolicy.xml és szabályokat adhat hozzá a csak a HoloLensen telepített alkalmazásokhoz a csomag családnevekkel. Előfordulhat, hogy olyan alkalmazásokat használ, amelyek nem az asztali számítógépen vannak, és a szabályzathoz kíván hozzáadni.

Az alábbi lista a HoloLens 2-eszközökre In-Box és alkalmazásokat sorolja fel.

| Alkalmazásnév                   | Csomag családneve                                |
|----------------------------|----------------------------------------------------|
| 3D-megjelenítő                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Alkalmazástelepítő              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Naptár                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Kamera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365-útmutatók        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Visszajelzési központ               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Fájlkezelő              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Filmek & TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Fotók                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| Beállítások                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Tippek                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 – A Alkalmazástelepítő blokkolás csak az Alkalmazástelepítő alkalmazást blokkolja, más forrásokból, például a Microsoft Store vagy az MDM-megoldásból telepített alkalmazásokat nem.

### <a name="how-to-find-a-package-family-name"></a>Csomag családnevének megkeresés

Ha egy alkalmazás nem szerepel a listán, akkor a felhasználó használhatja a Eszközportál-t, amely egy olyan HoloLens 2-hez csatlakozik, amely le szeretné tiltani az alkalmazást a PackageRelativeID meghatározásához, és onnan a PackageFamilyName paramétert fogja kapni.

1. Telepítse az alkalmazást a HoloLens 2-eszközön. 
1. Nyissa meg a Settings -> Updates & Security -> For developers (Biztonság –>, majd engedélyezze a **Fejlesztői** módot, majd az **Eszközportál lehetőséget.** 
    1. További részletekért olvassa el az eszközportál beállítását és [használatát itt.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Ha Eszközportál, lépjen a **Nézetek,** majd az **Alkalmazások lapra.** 
1. Az Installed Apps (Telepített alkalmazások) panelen válassza ki a telepített alkalmazást a legördülő menüből. 
1. Keresse meg a PackageRelativeID azonosítót. 
1. Másolja az alkalmazás karaktereit a ! karakter előtt. Ezek a karakterek lesznek a PackageFamilyName karakterei.


