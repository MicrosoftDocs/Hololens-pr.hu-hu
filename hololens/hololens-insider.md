---
title: Belső előzetes verzió a Microsoft HoloLens
description: Ismerje meg az Insider-buildek első lépéseit, és adjon értékes visszajelzést a HoloLens következő jelentős operációsrendszer-frissítésével kapcsolatban.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977224"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Belső előzetes verzió a Microsoft HoloLens

Üdvözöljük a HoloLens legújabb Insider Preview buildjeiben! Egyszerűen elkezdheti [](hololens-insider.md#start-receiving-insider-builds) a rendszert, és értékes visszajelzést adhat a HoloLens következő jelentős operációsrendszer-frissítésével kapcsolatban.

## <a name="windows-insider-release-notes"></a>Windows Insider kibocsátási megjegyzések

Izgatottan várjuk, hogy ismét új funkciókkal kezdhetjük el a Windows Insiderst. Az új buildek a fejlesztői és bétaverziós csatornákra lesznek felkísértve a legújabb frissítéseket. Ezt az oldalt folyamatosan frissítjük, ahogy további funkciókat és frissítéseket adunk hozzá a Windows Insider buildhez. Legyen izgatott, és készen áll arra, hogy ezeket a frissítéseket a valóságba keverje.

| Szolgáltatás                 | Leírás                | Célfelhasználók | Build bevezetve |
|-------------------------|----------------------------|--------------|------------------|
| CSP-módosítások a HoloLensben | Új CSP-k az adatok lekérdezéséhez | It-rendszergazdák    | 20348.1403                 |

### <a name="csp-changes-on-hololens"></a>CSP-módosítások a HoloLensben

- A 20348 Windows Insider.1403-as buildben bevezetett

#### <a name="devdetail-csp"></a>DevDetail CSP

A DevDetail CSP mostantól a HoloLens-eszközön található szabad tárterületet is jelenti. Ennek nagyjából meg kell egyeznie a Beállítások alkalmazás Tárterület lapján látható értékkel. Az alábbiakban az ezt az információt tartalmazó csomópont található.

- ./DevDetail/Ext/Microsoft/FreeStorage (csak GET művelet)

#### <a name="devicestatus-csp"></a>DeviceStatus CSP

A DeviceStatus CSP mostantól arról az SSID-ről és BSSID-ről is jelentést készít, amelyhez a HoloLens aktívan csatlakozik. A következő csomópontok tartalmazzák ezt az információt.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-cím* Wi-Fi /SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID

Példa syncml blobra (MDM-szállítók számára) a NetworkIdentifiers lekérdezéséhez

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a>Javítások és fejlesztések:

- Kijavítottunk egy ismert hibát, Eszközportál amikor nem volt [rákérdezés zárolt fájlok letöltésére.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Kijavítottunk egy ismert hibát, amely Eszközportál és letöltés időkorrekta [miatt ki volt javítva.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

## <a name="start-receiving-insider-builds"></a>Insider-buildek fogadásának kezdete
> [!NOTE]
> Ha a közelmúltban nem frissített, indítsa újra az eszközt az állapot frissítéséhez, és szerezze be a legújabb buildet.
> - Az "Eszköz újraindítása" hangparancs jól működik. 
> - Az Újraindítás gombot a Beállítások/beállítások Windows Insider Program.
>
> Előfordulhat, hogy egy hiba történt a háttéren, amely miatt ön is találkozhatott, így újra a útjára fog menni.

HoloLens 2-eszközön válassza a Settings Update & Security Windows Insider Program ( Első lépések)  >    >   **lehetőséget.** Csatolja a regisztrációhoz használt fiókot Windows Insider.
A Windows Insider most már a Csatornákra költözik. A **Gyors** kör lesz a **Fejlesztői** csatorna, a **Lassú** kör lesz a **Béta csatorna,** a Kiadási **előnézeti** kör pedig a Kiadás **előnézete csatorna** lesz. A leképezés a következő: Windows Insider magyarázata További információ: Introducing Windows Insider Channels on Windows Blogs (A Windows blogok Windows Insider ![ ](images/WindowsInsiderChannels.png) [csatornái).](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)
Ezután válassza a **Windows** aktív fejlesztése lehetőséget, válassza ki, hogy szeretné-e fogadni a **Dev Channelt** vagy Béta csatorna **buildeket,** és tekintse át a program feltételeit.
A **befejezéshez válassza > Újraindítás most** lehetőséget. Az eszköz újraindítása után a Settings (Beállítások) > **Update & Security > Check for updates** to get the latest build (Frissítések keresése a legújabb buildhez) lapon.
### <a name="update-error-0x80070490-work-around"></a>Hiba 0x80070490 hiba a hiba körül
Ha frissítési hibát 0x80070490 a Dev vagy a Beta csatornán való frissítéskor, próbálkozzon a következő rövid távú munkával. Ez magában foglalja a belső csatorna áthelyezését, a frissítés be- és áthelyezését, majd az Insider-csatorna vissza mozgatát.
#### <a name="stage-one---release-preview"></a>Első fázis – Előzetes kiadás
1.  Beállítások, Biztonsági & frissítése, majd Windows Insider Program a Kiadási előzetes **csatorna lehetőséget.**
2.  Beállítások, Biztonsági & frissítése, Windows Update, **Frissítések keresése.** A frissítés után folytassa a második fázisra.
#### <a name="stage-two---dev-channel"></a>Második fázis – Fejlesztői csatorna
1. Beállítások, Biztonsági & frissítése, Windows Insider Program válassza a **Dev Channel lehetőséget.**
2. Beállítások, Biztonsági & frissítése, Windows Update, **Frissítések keresése.**
## <a name="ffu-download-and-flash-directions"></a>FFU letöltési és flash utasítások
Az aláírt ffu repülőjárattal való teszteléshez először fel kell oldania az eszköz zárolását, mielőtt felrakná a repülőjárat aláírt ffu-ját.
1. Pc-n:
    1. Töltse le a ffu-t a számítógépére a [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) ről.
    
    1. Telepítse az ARC-t (Advanced Recovery Companion) a Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. A HoloLens – Flight Unlock: Open  >  **Settings Update & Security**  >  **Windows Insider Program** majd regisztráljon, indítsa újra az eszközt.
1. Flash FFU – Most már az ARC használatával is meg flashlheti a repülőjárat aláírt FFU-ját.
### <a name="provide-feedback-and-report-issues"></a>Visszajelzés küldése és problémák jelentése
A HoloLensen Visszajelzési központ [alkalmazással](hololens-feedback.md) visszajelzést küldhet, és jelentést küldhet a problémákról. A Visszajelzési központ biztosítja, hogy minden szükséges diagnosztikai információ bekerül a hibakeresésbe és a probléma megoldásához.  A HoloLens kínai és japán verziójával kapcsolatos problémákat ugyanúgy kell jelenteni.
> [!NOTE]
> Mindenképpen fogadja el azt a kérdést, amely megkérdezi, hogy szeretné Visszajelzési központ szeretné-e elérni a Dokumentumok mappát (válassza az **Igen** lehetőséget, amikor a rendszer kéri).
## <a name="note-for-developers"></a>Megjegyzés fejlesztőknek
Nyugodtan kipróbálhatja alkalmazásait a HoloLens Insider buildjére építve.  Az első lépésekhez tekintse meg a [HoloLens fejlesztői](https://developer.microsoft.com/windows/mixed-reality/development) dokumentációját. Ugyanezek az utasítások működnek a HoloLens Insider-buildjén is.  Használhatja a Unity ugyanazon buildjéhez és Visual Studio, mint a HoloLens-fejlesztéshez.
## <a name="stop-receiving-insider-builds"></a>Insider-buildek fogadásának leállítása
Ha már nem szeretné megkapni a Windows Holographic Insider-buildjét, kikapcsolhatja, ha a HoloLens éles buildet futtat, vagy az Advanced Recovery Companion segítségével helyreállíthatja az eszközt a Windows Holographic nem insider verziójára. [](hololens-recovery.md)
> [!CAUTION]
> Megjelenik egy ismert probléma, amely miatt az Insider Preview buildre való regisztrációt manuálisan újratelepítő felhasználók kék képernyőt tapasztalnak. Ezt követően manuálisan kell helyreállítania az eszközt. Ha szeretne többet tudni arról, hogy ez hatással lenne-e az Ön számára, tekintse meg ezt az ismert [problémát.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
Annak ellenőrzése, hogy a HoloLens éles buildet futtat-e:
1. A Settings **(Beállítások) > System > About (A** rendszerről) lapon keresse meg a build számát.
1. [Tekintse meg az éles buildszámok kibocsátási megjegyzéseit.](hololens-release-notes.md)
Az Insider-buildek lemondása:
1. Éles buildet futtató HoloLensen válassza a Beállítások > **Update & Security > Windows Insider Program** lehetőséget, és válassza a Stop **Insider builds** lehetőséget.
1. Az eszköz lemondáshoz kövesse az utasításokat.
