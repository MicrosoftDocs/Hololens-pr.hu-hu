---
title: Lap Gépház láthatósága
description: Maradjon naprakész a PageVisibilityList által támogatott URI-k listájával és a vegyes valóságú eszközökön HoloLens útmutatóval.
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
ms.openlocfilehash: 454d79e8b719feb73d5a39280794dcd76f134952
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639233"
---
# <a name="page-settings-visibility"></a>Lap Gépház láthatósága

A HoloLens egyik felügyelhető szolgáltatása a [Gépház/PageVisibilityList szabályzat](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) használatával korlátozza az alkalmazáson belül Gépház oldalakat. A PageVisibilityList egy olyan szabályzat, amely lehetővé teszi a rendszergazdák számára, hogy megakadályozzák a System Gépház alkalmazás adott lapjainak láthatóságát vagy akadálymentességét, vagy a megadottak kivételével minden oldal esetén ezt teszik meg.

> [!NOTE]
> Ez a funkció csak a [Holographic Windows 20H2-es](hololens-release-notes.md#windows-holographic-version-20h2) vagy újabb verziójában használható 2 HoloLens eszközök esetén. Győződjön meg arról, hogy a használni kívánt eszközök frissítve vannak.


## <a name="examples"></a>Példák
A lapokat a közzétett URI-k rövid verziója azonosítja, amely az "ms-settings:" előtaggal csökkentett URI.

Az alábbi példa egy olyan szabályzatot mutat be, amely csak az about és a Bluetooth-lapokhoz biztosít hozzáférést, amelyek URI-ja "network-wifi" és "bluetooth" (bluetooth) lehet:
- `showonly:network-wifi;network-proxy;bluetooth`

Az alábbi példa egy olyan szabályzatot mutat be, amely elrejti az operációs rendszer alaphelyzetbe állítása oldalt:
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>A szabályzat telepítése az Intune-on keresztül

Az Intune a következő konfigurációs értékeket fogja tartalmazni:

- **Név:** A profil rendszergazda által előnyben részesített megjelenítendő neve.
- **OMA-URI:** A beállítási oldal teljes URI-ját, beleértve a [hatókörét is.](/windows/client-management/mdm/policy-configuration-service-provider) Az ezen az oldalon található példák a hatókört `./Device` használják.
- **Érték:** Egy sztringérték, amely azt jelzi, hogy csak a megadott oldalakat kell-e elrejtenie vagy *csak* meg kell mutatnia. Lehetséges értékek: `hide:<pagename>` és `showonly:<pagename>` . 
 
Több oldal is meg lehet adni pontosvesszővel elválasztva, és a gyakori oldalak listája alább található.

1. Hozzon létre **egy egyéni szabályzatot.**
1. Az **OMA-URI beállításakor** adja meg a teljes hatókörű URI-t. Például: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Az adat kiválasztásakor válassza a Sztring **lehetőséget**
1. Az Érték **megadásakor** használja a fenti útmutatást. Például: **`showonly:network-wifi;network-proxy;bluetooth`** vagy **`hide:reset`** 
> [!IMPORTANT]
> Ügyeljen arra, hogy az egyéni eszközkonfigurációt olyan csoporthoz rendelje, amelybe az eszköznek szánták. Ha ezt a lépést nem végzi el, a rendszer lekedi a szabályzatot, de nem alkalmazza.

Az [Intune-HoloLens](hololens-mdm-configure.md) és az eszközkonfigurációkról további információt az MDM-konfigurációk konfigurálása és konfigurálása oldalon található.


## <a name="deploying-this-policy-via-a-provisioning-package"></a>A szabályzat üzembe helyezése kiépítési csomagon keresztül

A Configuration Designerben a következő konfigurációs értékeket Windows meg:

**Érték:** Egy sztringérték, amely azt jelzi, hogy csak a megadott oldalakat kell-e elrejtenie vagy *csak* meg kell mutatnia. Lehetséges értékek: `hide:<pagename>` és `showonly:<pagename>` . Több oldal is meg lehet adni pontosvesszővel elválasztva, és a gyakori oldalak listája alább található.


1. Amikor a konfigurációtervezőben létrehozza a csomagot Windows a **Szabályzatok lapra > Gépház > PageVisibilityList**
1. Adja meg a sztringet: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exportálja a kiépítési csomagot.
1. Alkalmazza a csomagot az eszközre.
A kiépítési csomagok létrehozásáról és alkalmazásról további részleteket a HoloLens [oldalon talál.](hololens-provisioning.md)


A választott módszertől függetlenül az eszköznek meg kell kapnia a módosításokat, és a felhasználók számára az alábbi Gépház alkalmazás.

![Képernyőkép a módosított aktív órákról az Gépház alkalmazásban](images/hololens-page-visibility-list.jpg)

Ha úgy Gépház, hogy az alkalmazásoldalakon saját oldalakat mutasson vagy rejtsen el, nézze meg a Gépház elérhető URI-HoloLens.

## <a name="settings-uris"></a>Gépház Uri

HoloLens eszközök és Windows 10 eszközök különböző oldalakat tartalmaznak a Gépház alkalmazásban. Ezen az oldalon csak a meglévő beállításokat fogja HoloLens.

### <a name="accounts"></a>Fiókok
| Beállítások lap           | URI                                            |
|-------------------------|------------------------------------------------|
| Hozzáférés munkahelyi vagy iskolai rendszerhez | `workplace`                         |
| Íriszregisztrálás       | `signinoptions-launchirisenrollment` |
| Bejelentkezési lehetőségek         | ` signinoptions `                   |

### <a name="apps"></a>Alkalmazások
| Beállítások lap | URI                          |
|---------------|------------------------------|
| Alkalmazások & <sup>funkciók 2</sup>     | `appsfeatures` <br> |
| Alkalmazások & funkciókkal > <sup>2.</sup> speciális beállítások     | `appsfeatures-app` <br> |
| Az & offline > <sup>2 Térképek funkciói</sup>     | `maps-maps` <br> |
| Az & offline > alkalmazások Térképek > Maps <sup>2 letöltése</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>Eszközök
| Beállítások lap | URI                          |
|---------------|------------------------------|
| Bluetooth     | `bluetooth` <br> `connecteddevices` |
| <sup>2. egér</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>Adatvédelem
| Beállítások lap            | URI                                             |
|--------------------------|-------------------------------------------------|
| Fiókadatok             | `privacy-accountinfo`              |
| Alkalmazásdiagnosztika        | `privacy-appdiagnostics`              |
| Háttérben futó alkalmazások        | `privacy-backgroundapps`              |
| Naptár                 | `privacy-calendar`                    |
| Híváselőzmények             | `privacy-callhistory`                 |
| Kamera                   | `privacy-webcam`                      |
| Kapcsolattartók                 | `privacy-contacts`                    |
| Diagnosztikai & visszajelzés | `privacy-feedback`                    |
| Dokumentumok                | `privacy-documents`                   |
| E-mail                    | `privacy-email`                       |
| Fájlrendszer              | `privacy-broadfilesystemaccess`       |
| <sup>2. általános</sup>             | `privacy-general`       |
| Ink & gépelés személyre <sup>szabás 2</sup>             | `privacy-speechtyping`       |
| Hely                 | `privacy-location`                    |
| Üzenetkezelés                | `privacy-messaging`                   |
| Mikrofon               | `privacy-microphone`                  |
| <sup>2. mozgás</sup>               | `privacy-motion`                  |
| Értesítések            | `privacy-notifications`               |
| Egyéb eszközök            | `privacy-customdevices`               |
| Képek                 | `privacy-pictures`                    |
| Rádiók                   | `privacy-radios`                      |
| Képernyőkép a <sup>szegélyek 2-ről</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| Képernyőképek és alkalmazások <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| Speech                   | `privacy-speech`                      |
| Feladatok                    | `privacy-tasks`                       |
| Felhasználói mozgások           | `privacy-backgroundspatialperception` |
| Videók                   | `privacy-videos`                      |
| Hangaktiválás       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>Hálózat és internet
| Beállítások lap | URI                              |
|---------------|----------------------------------|
| <sup>2.</sup> repülőgép üzemmód | `network-airplanemode`        |
| Proxy | `network-proxy`        |
| VPN   | `network-vpn`          |
| Wi-Fi  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>Rendszer
| Beállítások lap      | URI                                |
|--------------------|------------------------------------|
| <sup>2. akkumulátor</sup>           | `batterysaver`<br>|
| <sup>2. akkumulátor</sup>           | `batterysaver-settings`<br>|
| Színek             | `colors`<br>`personalization-colors` |
| Hologramok <sup>2.</sup>  |  `holograms`  |
| <sup>2. hiba</sup> |  `calibration` |
| Értesítési & műveletek  | `notifications`          |
| Megosztott élmények | `crossdevice` 
| <sup>2. hang</sup>           | `sound`<br>|
| Hang > alkalmazáskötet és eszköz preferencia <sup>2</sup>           | `apps-volume`<br>|
| Hang > Hangeszközök kezelése <sup>2</sup>           | `sound-devices`<br>|
| Tárolás            | `storagesense`           |
| Storage > Sense <sup>2</sup> Storage konfigurálása           | `storagepolicies`<br>|

### <a name="time--language"></a>Time & Language
| Beállítások lap | URI                                           |
|---------------|-----------------------------------------------|
| Dátum & <sup>2</sup> | `dateandtime`                  |
| <sup>2. billentyűzet</sup> | `keyboard`                  |
| <sup>2. nyelv</sup> | `language`                  |
| <sup>2. nyelv</sup> | `regionlanguage-languageoptions`                  |
| Nyelv      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| Region        | `regionformatting`                  |

### <a name="update--security"></a>Biztonsági & frissítése
| Beállítások lap                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Speciális beállítások                    | `windowsupdate-options`         |
| Visszaállítás & <sup>2</sup>      | `reset`         |
| Windows Insider Program               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows Update                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows Frissítés – Frissítések keresése | `windowsupdate-action`          |


- <sup>1</sup> – Az Windows Holographic 21H1-es verziójánál korábbi verziók esetén a következő  két URI valójában nem a Speciális beállítások vagy Beállítások **oldalra** lép; csak a Frissítés oldalon található fő Windows vagy fognak jelenni.
  -  windowsupdate-options
  -  windowsupdate-restartoptions

- <sup>2</sup> – Elérhető Windows Holographic 21H1 vagy újabb verzióban.


Az URI-k teljes Windows 10 Gépház tekintse meg az indítási beállítások [dokumentációját.](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)
