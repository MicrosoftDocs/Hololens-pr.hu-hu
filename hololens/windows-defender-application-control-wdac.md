---
title: Windows Defender Alkalmazásvezérlés (WDAC)
description: Az alkalmazásvezérlés Windows Defender és használatának áttekintése vegyes valóságú HoloLens kezeléséhez.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/21/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: efdc57b5e045c1669587ffc46dbe2132b6de6600
ms.sourcegitcommit: 52ed453cace3851fbec0cfcc228fa2a79f1a2fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/22/2021
ms.locfileid: "128075385"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Alkalmazásvezérlés – WDAC

## <a name="overview"></a>Áttekintés

A WDAC segítségével konfigurálhatja a HoloLens, hogy letiltsa az alkalmazások indítását. Ez eltér a Kioszk módtól, ahol a felhasználói felület elrejti az alkalmazásokat, de továbbra is elindíthatóak. A WDAC-val láthatja az alkalmazásokat, de nem indíthatóak el.

> [!NOTE]
> Amikor a végfelhasználók olyan alkalmazást próbálnak meg elindítani a HoloLens-on, amelyet a WDAC blokkol, nem kap értesítést arról, hogy nem tudják elindítani az alkalmazást.

Egy eszközhöz több WDAC-szabályzat is hozzárendelhető. Ha több WDAC-házirend van beállítva egy rendszeren, a legszigorúbb házirendek lépnek életbe.

Az alábbi útmutatóból megtudhatja, hogyan engedélyezheti vagy tilthatja le az alkalmazásokat [a WDAC](/mem/intune/configuration/custom-profile-hololens)és a Windows PowerShell használatával HoloLens 2 eszközön a Microsoft Intune.

Amikor a felhasználók az első példalépéssel rákeresnek a Windows 10 számítógépre telepített alkalmazásokra, előfordulhat, hogy néhány kísérletet kell tenniük az eredmények szűkítésére.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
```

Ha nem tudja a csomag teljes nevét, előfordulhat, hogy néhányszor futtatnia kell a Get-AppxPackage -name \* YourBestGuess \* nevet. Ha már megvan a név, futtassa a következőt: "$package 1 = Get-AppxPackage -name Actual.PackageName"

Ha például a következő kódot futtatja Microsoft Edge több eredményt ad vissza, de ebből a listából megállapíthatja, hogy a szükséges teljes név a Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
```

## <a name="package-family-names-for-apps-on-hololens"></a>Csomag családneveket a HoloLens

A fent hivatkozott útmutatóban manuálisan szerkesztheti az alkalmazásokatnewPolicy.xml és szabályokat adhat hozzá a csak a HoloLens telepített alkalmazásokhoz a csomag családnevekkel. Előfordulhat, hogy olyan alkalmazásokat használ, amelyek nem az asztali számítógépen vannak, és hozzá szeretné adni a szabályzathoz.

Az alábbi lista a 2 In-Box használt és HoloLens alkalmazások listáját tartalmazza.

| Alkalmazásnév                   | Csomag családneve                                |
|----------------------------|----------------------------------------------------|
| 3D-megjelenítő                  | `Microsoft.Microsoft3DViewer_8wekyb3d8bbwe`          |
| Alkalmazástelepítő              | `Microsoft.DesktopAppInstaller_8wekyb3d8bbwe`<sup>1</sup>         |
| Naptár                   | `microsoft.windowscommunicationsapps_8wekyb3d8bbwe`  |
| Kamera                     | `HoloCamera_cw5n1h2txyewy`                          |
| Cortana                    | `Microsoft.549981C3F5F10_8wekyb3d8bbwe`              |
| Dynamics 365-útmutatók        | `Microsoft.Dynamics365.Guides_8wekyb3d8bbwe`         |
| Dynamics 365 Remote Assist | `Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe`      |
| Visszajelzési központ               | `Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe`         |
| Fájlkezelő              | `c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy` |
| Mail                       | `microsoft.windowscommunicationsapps_8wekyb3d8bbwe`  |
| Microsoft Store            | `Microsoft.WindowsStore_8wekyb3d8bbwe`               |
| Filmek & TV                | `Microsoft.ZuneVideo_8wekyb3d8bbwe`                  |
| OneDrive                   | `microsoft.microsoftskydrive_8wekyb3d8bbwe`          |
| Fotók                     | `Microsoft.Windows.Photos_8wekyb3d8bbwe`             |
| Beállítások                   | `HolographicSystemSettings_cw5n1h2txyewy`            |
| Tippek                       | `Microsoft.HoloLensTips_8wekyb3d8bbwe`               |

- 1 – A Alkalmazástelepítő blokkolás csak az Alkalmazástelepítő alkalmazást blokkolja, a más forrásokból, például a Microsoft Store vagy az MDM-megoldásból telepített alkalmazásokat nem.

### <a name="using-wdac-to-block-new-microsoft-edge"></a>A WDAC használata az új Microsoft Edge

Ahhoz, hogy a rendszergazdák a [WDAC-szabályzatukat](windows-defender-application-control-wdac.md) [frissítve](hololens-new-edge.md)blokkolják az új Microsoft Edge alkalmazást, a következőket kell hozzáadnia a szabályzathoz.

```xml
<Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" />
```

### <a name="how-to-find-a-package-family-name"></a>Csomag családnevének megkeresés

Ha egy alkalmazás nem szerepel a listán, akkor a felhasználó használhatja a Eszközportál-t, amely egy olyan HoloLens 2-es porthoz csatlakozik, amely le szeretné tiltani az alkalmazást, hogy meghatározza a PackageRelativeID azonosítót, és onnan szerezze be a PackageFamilyName paramétert.

1. Telepítse az alkalmazást a HoloLens 2-es eszközön.

1. Nyissa meg Gépház -> Updates & Security -> For developers (Biztonsági beállítások fejlesztőknek) gombra, engedélyezze a Fejlesztői módot, majd **az** **Eszközportál gombra.**

   További részletekért és utasításokért lásd az eszközportál beállítását és [használatát itt.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

1. Miután Eszközportál, lépjen a **Nézetek,** majd az Alkalmazások **lapra.**

1. Az Installed Apps (Telepített alkalmazások) panelen válassza ki a telepített alkalmazást a legördülő menüből.

1. Keresse meg a PackageRelativeID azonosítót.

1. Másolja az alkalmazás karaktereit az előtt, hogy ezek a karakterek `!` a PackageFamilyName nevet fogják tartalmazni.
