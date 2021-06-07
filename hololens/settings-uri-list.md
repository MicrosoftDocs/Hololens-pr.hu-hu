---
title: Oldalbeállítások láthatósága
description: Maradjon naprakész a PageVisibilityList által támogatott URI-k listájával és a HoloLens vegyes valóságú eszközökön elérhető útmutatóval.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, hozzárendelt hozzáférés, kioszk, beállítások oldal
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5779ffa1de1700b4fcd17fc17b8ae3a82a45c22
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379573"
---
# <a name="page-settings-visibility"></a>Oldalbeállítások láthatósága

A HoloLens-eszközök egyik felügyelhető szolgáltatása a [Settings/PageVisibilityList szabályzat](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) használatával korlátozza a Beállítások alkalmazásban látható oldalakat. A PageVisibilityList egy olyan szabályzat, amely lehetővé teszi a rendszergazdák számára, hogy megakadályozzák a Rendszerbeállítások alkalmazás adott lapjainak láthatóságát vagy akadálymentességét, vagy hogy ezt a megadott oldalak kivételével az összes oldalon meg tudjanak jelenni.

> [!NOTE]
> Ez a funkció csak a [Windows Holographic 20H2-es](hololens-release-notes.md#windows-holographic-version-20h2) vagy újabb verziójában használható a HoloLens 2-es eszközökön. Győződjön meg arról, hogy a használni kívánt eszközök frissítve vannak.

Az alábbi példa egy olyan szabályzatot mutat be, amely csak az About és a Bluetooth-oldalakhoz biztosít hozzáférést, amelyek URI-ja "ms-settings:network-wifi" és "ms-settings:bluetooth" lehet:
- `showonly:network-wifi;network-proxy;bluetooth`

Ennek beállítása kiépítési csomaggal:

1. Amikor a Windows Configuration Designerben létrehozza a csomagot, lépjen a Házirendek és > **beállítások > Lap láthatóságaLista elemre.**
1. Adja meg a sztringet: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exportálja a kiépítési csomagot.
1. Alkalmazza a csomagot az eszközre.
A kiépítési csomagok létrehozására és alkalmazására vonatkozó részletes információkért látogasson el erre [az oldalra.](hololens-provisioning.md)

Ezt az Intune-on keresztül, az OMA-URI használatával lehet tenni:

1. Hozzon létre **egy egyéni szabályzatot.**
1. Az OMA-URI beállításakor használja a következő sztringet: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Az adat kiválasztásakor válassza a Sztring **lehetőséget**
1. Az érték beírásakor használja a következőt: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Ügyeljen arra, hogy az egyéni eszközkonfigurációt olyan csoporthoz rendelje, amelybe az eszköznek szánták.

További információ az Intune-csoportokról és az eszközkonfigurációkról: [HoloLens MDM-konfiguráció.](hololens-mdm-configure.md)

Az eszköznek a választott módszertől függetlenül meg kell kapnia a módosításokat, és a felhasználók számára a következő Beállítások alkalmazás fog jelennek meg.

![Képernyőkép a Beállítások alkalmazásban módosított aktív órákról](images/hololens-page-visibility-list.jpg)

Ha a Beállítások alkalmazásoldalait úgy konfigurálja, hogy saját oldalakat mutassanak vagy rejtsen el, nézze meg a HoloLensben elérhető Beállítás URI-ket.

## <a name="settings-uris"></a>Beállítási URI-k

A HoloLens- és Windows 10-eszközök különböző oldalakat tartalmaznak a Beállítások alkalmazásban. Ezen az oldalon csak a HoloLensben meglévő beállításokat találja meg.

### <a name="accounts"></a>Fiókok
| Beállítások lap           | URI                                            |
|-------------------------|------------------------------------------------|
| Hozzáférés munkahelyi vagy iskolai rendszerhez | `ms-settings:workplace`                         |
| Íriszregisztrálás       | `ms-settings:signinoptions-launchirisenrollment` |
| Bejelentkezési lehetőségek         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>Alkalmazások
| Beállítások lap | URI                          |
|---------------|------------------------------|
| Alkalmazások &<sup>funkciók 2</sup>     | `ms-settings:appsfeatures` <br> |
| Alkalmazások & funkciókkal > <sup>2.</sup> speciális beállításokkal     | `ms-settings::appsfeatures-app` <br> |
| Az offline & <sup>2</sup> > alkalmazások     | `ms-settings:maps-maps` <br> |
| Az offline térképek & elérhető > alkalmazások > Maps <sup>2 letöltése</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>Eszközök
| Beállítások lap | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <sup>2. egér</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>Adatvédelem
| Beállítások lap            | URI                                             |
|--------------------------|-------------------------------------------------|
| Fiókadatok             | `ms-settings:privacy-accountinfo`              |
| Alkalmazásdiagnosztika        | `ms-settings:privacy-appdiagnostics`              |
| Háttérben futó alkalmazások        | `ms-settings:privacy-backgroundapps`              |
| Naptár                 | `ms-settings:privacy-calendar`                    |
| Híváselőzmények             | `ms-settings:privacy-callhistory`                 |
| Kamera                   | `ms-settings:privacy-webcam`                      |
| Kapcsolattartók                 | `ms-settings:privacy-contacts`                    |
| Diagnosztikai és & visszajelzés | `ms-settings:privacy-feedback`                    |
| Dokumentumok                | `ms-settings:privacy-documents`                   |
| E-mail                    | `ms-settings:privacy-email`                       |
| Fájlrendszer              | `ms-settings:privacy-broadfilesystemaccess`       |
| <sup>2. általános</sup>             | `ms-settings:privacy-general`       |
| Ink & személyre szabás <sup>begépelése 2</sup>             | `ms-settings:privacy-speechtyping`       |
| Hely                 | `ms-settings:privacy-location`                    |
| Üzenetkezelés                | `ms-settings:privacy-messaging`                   |
| Mikrofon               | `ms-settings:privacy-microphone`                  |
| <sup>2. mozgás</sup>               | `ms-settings:privacy-motion`                  |
| Értesítések            | `ms-settings:privacy-notifications`               |
| Egyéb eszközök            | `ms-settings:privacy-customdevices`               |
| Képek                 | `ms-settings:privacy-pictures`                    |
| Rádiók                   | `ms-settings:privacy-radios`                      |
| Képernyőkép a <sup>szegélyek 2-ről</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| Képernyőképek és alkalmazások <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| Speech                   | `ms-settings:privacy-speech`                      |
| Feladatok                    | `ms-settings:privacy-tasks`                       |
| Felhasználói mozgások           | `ms-settings:privacy-backgroundspatialperception` |
| Videók                   | `ms-settings:privacy-videos`                      |
| Hangaktiválás       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>Hálózat és internet
| Beállítások lap | URI                              |
|---------------|----------------------------------|
| <sup>2.</sup> repülőgép üzemmód | `ms-settings:network-airplanemode`        |
| Proxy | `ms-settings:network-proxy`        |
| VPN   | `ms-settings:network-vpn`          |
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>Rendszer
| Beállítások lap      | URI                                |
|--------------------|------------------------------------|
| <sup>2. akkumulátor</sup>           | `ms-settings:batterysaver`<br>|
| <sup>2. akkumulátor</sup>           | `ms-settings:batterysaver-settings`<br>|
| Színek             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Hologramok <sup>2</sup>  |  `ms-settings:holograms`  |
| <sup>2. hiba</sup> |  `ms-settings:calibration` |
| Értesítési & műveletek  | `ms-settings:notifications`          |
| Megosztott élmények | `ms-settings:crossdevice` 
| <sup>2. hang</sup>           | `ms-settings:sound`<br>|
| Hang > alkalmazáskötet és eszköz preferencia <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| Hang > Hangeszközök kezelése <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| Tárolás            | `ms-settings:storagesense`           |
| Storage > Configue Tárterületsegéd <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>Time & Language
| Beállítások lap | URI                                           |
|---------------|-----------------------------------------------|
| Dátum & <sup>2</sup> | `ms-settings:dateandtime`                  |
| <sup>2. billentyűzet</sup> | `ms-settings:keyboard`                  |
| <sup>2. nyelv</sup> | `ms-settings:language`                  |
| <sup>2. nyelv</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| Nyelv      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| Region        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>Biztonsági & frissítése
| Beállítások lap                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Speciális beállítások                    | `ms-settings:windowsupdate-options`         |
| Visszaállítás & <sup>2</sup>      | `ms-settings:reset`         |
| Windows Insider Program               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update – Frissítések keresése | `ms-settings:windowsupdate-action`          |


>  <sup>1</sup> A Windows Holographic előtti, 21H1-es verziónál korábbi verziók esetén  a következő két URI valójában nem a Speciális beállítások vagy Beállítások **oldalra** lép; csak a főoldalt blokkolják vagy Windows Update meg.
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions
 
> <sup>2</sup> – Windows Holographic 21H1 vagy újabb rendszeren érhető el.


A beállítások URI Windows 10 teljes listáját az indítási beállítások [dokumentációjában](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) találhatja meg.
