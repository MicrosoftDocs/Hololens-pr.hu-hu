---
title: Windows Defender Alkalmazásvezérlés (WDAC)
description: Az Alkalmazásvezérlés Windows Defender áttekintése, és annak használata vegyes valóságú HoloLens kezelésére.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5c3b55273346f330580b07e5294e7e8e65ea12d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032926"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Alkalmazásvezérlés – WDAC

## <a name="overview"></a>Áttekintés

A WDAC segítségével konfigurálhatja a HoloLens, hogy blokkolja az alkalmazások indítását. Ez eltér a Kioszk módtól, ahol a felhasználói felület elrejti az alkalmazásokat, de továbbra is elindíthatóak. A WDAC-val láthatja az alkalmazásokat, de nem indíthatóak el.

> [!NOTE]
> Amikor a végfelhasználók olyan alkalmazást próbálnak meg elindítani, amelyet a WDAC blokkol HoloLens, nem kap értesítést arról, hogy nem tudják elindítani az alkalmazást.

Egy eszközhöz több WDAC-szabályzat is hozzárendelhető. Ha több WDAC-házirend van beállítva egy rendszeren, a legszigorúbb házirendek lépnek életbe. 

Az alábbi útmutató segítségével a felhasználók megtudhatják, hogyan engedélyezheti vagy tilthatja le az alkalmazásokat [Windows PowerShell WDAC](/mem/intune/configuration/custom-profile-hololens)és HoloLens 2 eszközön a Microsoft Intune.

Amikor a felhasználók a saját számítógépükre telepített Windows 10 rá az első példalépéssel, előfordulhat, hogy néhány kísérletet kell tenniük az eredmények szűkítésére.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Ha nem tudja a csomag teljes nevét, előfordulhat, hogy néhányszor futtatnia kell a Get-AppxPackage -name \* YourBestGuess \* nevét, hogy megtalálja. A név után futtassa a következőt: "$package 1 = Get-AppxPackage -name Actual.PackageName"

Ha például a következő kódot futtatja Microsoft Edge több eredményt ad vissza, de ebből a listából megállapíthatja, hogy a teljes név, amire szüksége van, a Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Csomag családneveket a HoloLens

A fent hivatkozott útmutatóban manuálisan szerkesztheti a newPolicy.xml és szabályokat adhat hozzá olyan alkalmazásokhoz, amelyek csak a HoloLens a csomagjuk családnevekkel. Előfordulhat, hogy olyan alkalmazásokat használ, amelyek nem az asztali számítógépen vannak, és ezeket hozzá szeretné adni a szabályzathoz.

Az alábbi lista a 2 eszköz In-Box használt és HoloLens alkalmazások listáját tartalmazza.

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
| Fotók                     | Microsoft. Windows. Photos_8wekyb3d8bbwe             |
| Beállítások                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Tippek                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 – A Alkalmazástelepítő blokkolás csak a Alkalmazástelepítő alkalmazást blokkolja, más forrásokból, például a Microsoft Store vagy az MDM-megoldásból telepített alkalmazásokat nem.

### <a name="how-to-find-a-package-family-name"></a>Csomag családnevének megkeresés

Ha egy alkalmazás nem szerepel a listán, a felhasználó használhatja a Eszközportál-t, amely egy olyan HoloLens 2-hez csatlakozik, amely le szeretné tiltani az alkalmazást, a PackageRelativeID meghatározásához, és onnan a PackageFamilyName paramétert kapják meg.

1. Telepítse az alkalmazást a HoloLens 2-es eszközön. 
1. Nyissa meg Gépház -> Updates & Security -> For developers (Biztonsági beállítások fejlesztőknek) gombra, engedélyezze a Fejlesztői módot, majd **az** **Eszközportál gombra.** 
    1. További részletekért olvassa el az eszközportál beállítását és [használatát itt.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Miután Eszközportál, lépjen a **Nézetek,** majd az Alkalmazások **lapra.** 
1. Az Installed Apps (Telepített alkalmazások) panelen válassza ki a telepített alkalmazást a legördülő menüben. 
1. Keresse meg a PackageRelativeID azonosítót. 
1. Másolja az alkalmazás karaktereit az előtt, hogy ezek a karakterek `!` a PackageFamilyName névre fognak esni.

