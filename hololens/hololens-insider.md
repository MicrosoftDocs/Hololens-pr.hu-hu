---
title: Belső előzetes verzió a Microsoft HoloLens
description: Megismerheti az Insider-buildek első lépéseit, és értékes visszajelzést adhat a következő jelentős operációsrendszer-frissítésünkről a HoloLens.
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
ms.openlocfilehash: 86a763adb233b45242182d069a56692aeddc2e59
ms.sourcegitcommit: 5cb3230e02e703584e50358cb0f0b5f33a51b169
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2021
ms.locfileid: "121858582"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Belső előzetes verzió a Microsoft HoloLens

Üdvözöljük az Insider előzetes verziójának legújabb buildjeiben HoloLens! Az első lépések [egyszerűek,](hololens-insider.md#start-receiving-insider-builds) és értékes visszajelzést biztosítanak az operációs rendszer következő jelentős frissítésével kapcsolatban a HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Belső kibocsátási megjegyzések

Izgatottan várjuk, hogy ismét új funkciókat Windows Insidersbe. Az új buildek a fejlesztői és bétaverziós csatornákra lesznek felkísértve a legújabb frissítéseket. Ezt az oldalt folyamatosan frissítjük, ahogy további funkciókat és frissítéseket adunk hozzá a Windows Insider buildjeinkhez. Legyen izgatott, és készen áll arra, hogy ezeket a frissítéseket a valóságba keverje.

| Szolgáltatás                 | Leírás                | Felhasználó vagy forgatókönyv | Build bevezetve |
|-------------------------|----------------------------|--------------|------------------|
| [CSP-módosítások a jelentéskészítési HoloLens részleteihez](#csp-changes-for-reporting-hololens-details) | Új CSP-k az adatok lekérdezéséhez | It-rendszergazdák    | 20348.1403                 |
| [CSP által vezérelt automatikus bejelentkezési szabályzat](#auto-login-policy-controlled-by-csp) | Fiók automatikus bejelentkezése | It-rendszergazdák | 20348.1405 |
| [Továbbfejlesztett frissítés-újraindítás észlelése és értesítések](#improved-update-restart-detection-and-notifications) | Új, engedélyezett frissítésekre vonatkozó- és felhasználói felületi (UX). | It-rendszergazdák | 20348.1405 |
| [PFX-fájltámogatás a Tanúsítványkezelőhöz](#pfx-file-support-for-certificate-manager) | PFX-tanúsítványok hozzáadása Gépház felhasználói felületen | Végfelhasználó | 20348.1405 |
| [Intelligens újrapróbálkozás alkalmazásfrissítésekkor](#smart-retry-for-app-updates) | Lehetővé teszi a rendszergazdák számára az alkalmazások frissítésére ütemezett újrakikerált alkalmazások frissítését. | It-rendszergazdák | 20348.1405 |
| [Speciális diagnosztikai jelentés megtekintése a Gépház a HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | MDM diagnosztikai naplók megtekintése az eszközön | Hibaelhárítás | 20348.1405 |
| [Offline diagnosztikai értesítések](#offline-diagnostics-notifications) | Visszajelzés a naplógyűjtéssel kapcsolatban | Hibaelhárítás | 20348.1405 |
| [Csak privát áruházbeli alkalmazások használata Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Az áruházbeli alkalmazás konfigurálása úgy, hogy csak a szervezettől származó alkalmazásokat mutassa | Rendszergazdai | 20348.1408 |
| [Az alacsony tárterületű naplógyűjtés fejlesztései](#low-storage-log-collection-improvements) | A naplógyűjtési forgatókönyvek fejlesztései alacsony tárolási helyzetekben. | Rendszergazdai | 20348.1412 |
| [Platform mód mozgatás](#moving-platform-mode) | Bevezeti a moving Platform Mode bétaverziót, amely a konfigurálás után HoloLens 2. használatát teszi lehetővé alacsony dinamikus mozgást tapasztaló nagy méretű állatokon. | Mind | 20348.1411 |
| [Javítások és fejlesztések](#fixes-and-improvements) | Javítások és fejlesztések a HoloLens. | Mind | 20348.1411 |

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-módosítások a jelentéskészítési HoloLens részleteihez

- A Windows 20348.1403-as buildben vezettük be

Az alábbi CSP-k új módszereket kínálnak a jelentések jelentésére a HoloLens eszközökről.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP – Ingyenes Storage

A DevDetail CSP mostantól a szabad tárterületet is jelenti HoloLens eszközön. Ennek nagyjából egyeznie kell az alkalmazás Gépház lapján látható Storage értékkel. Az alábbiakban az ezt az információt tartalmazó csomópont található.

- ./DevDetail/Ext/Microsoft/FreeStorage (csak GET művelet)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP – SSID és BSSID

A DeviceStatus CSP mostantól egy olyan hálózat SSID és BSSID Wi-Fi, amelyhez HoloLens csatlakozik. A következő csomópontok tartalmazzák ezt az információt.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID

Példa syncml blobra (MDM-szállítóknak) a NetworkIdentifiers lekérdezéséhez

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

### <a name="auto-login-policy-controlled-by-csp"></a>CSP által vezérelt automatikus bejelentkezési szabályzat

Ez az új AutoLogonUser szabályzat szabályozza, hogy a rendszer automatikusan bejelentkeztet-e egy felhasználót. Egyes ügyfelek olyan eszközöket is beállítanának, amelyek egy identitáshoz kötődnek, de nem szeretnék, ha bármilyen bejelentkezési élményre lenne lehetőség. Imagine eszköz felvétele és azonnali használata a remote assist használatával. Vagy az is előnyös, ha gyorsan el tudja terjeszteni a HoloLens, és lehetővé teszi a végfelhasználók számára a bejelentkezés gyorsítását.

Ha a szabályzat nem üres értékre van állítva, megadja az automatikus bejelentkezési felhasználó e-mail-címét. Az automatikus bejelentkezés engedélyezéséhez a megadott felhasználónak legalább egyszer be kell jelentkeznie az eszközre.

Az új szabályzat sztringértékének `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` OMA-URI-ját

- Az azonos e-mail-címmel rendelkező felhasználónál engedélyezve lesz az automatikus bejelentkezés.

Egy olyan eszközön, ahol ez a szabályzat konfigurálva van, a szabályzatban megadott felhasználónak legalább egyszer be kell jelentkeznie. Az eszköz az első bejelentkezést követő újraindítása után automatikusan bejelentkezik a megadott felhasználóra. Csak egyetlen automatikus bejelentkezési felhasználó támogatott. Ha engedélyezve van, az automatikusan bejelentkezett felhasználó nem fog tudni manuálisan kijelentkezni. Ha egy másik felhasználóval jelentkezik be, először le kell tiltani a szabályzatot.

> [!NOTE]
>
> - Egyes események, például a fő operációsrendszer-frissítések miatt előfordulhat, hogy a megadott felhasználónak újra be kell jelentkeznie az eszközre az automatikus bejelentkezés folytatásához.
> - Az automatikus bejelentkezés csak MSA- és AAD-felhasználók számára támogatott.

### <a name="improved-update-restart-detection-and-notifications"></a>Továbbfejlesztett frissítés-újraindítás észlelése és értesítések

Az aktív órák és a telepítési idő házirendek között lehetőség van arra, hogy ne kelljen újraindítani HoloLens eszközöket, amikor használatban vannak. Ha azonban nem történik újraindítás a szükséges frissítések telepítésének befejezéséhez, az is késleltetné a frissítések telepítését. Most olyan szabályzatokat adtunk hozzá, amelyek lehetővé teszik az it-ita számára a határidők és a szükséges újraindítások kényszerítése, valamint a frissítések időbeni telepítésének befejezését. A felhasználók értesítést kaphatnak az újraindítás kezdeményezése előtt, és az it-szabályzatnak megfelelően késleltetni tudják az újraindítást.

A következő frissítési szabályzatok bővültek:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="pfx-file-support-for-certificate-manager"></a>PFX-fájl támogatása a Tanúsítványkezelőben

Az Insider Windows 20348.1405-ös buildben vezettük be. Mostantól támogatott a Tanúsítványkezelő a .pfx-tanúsítványok használatára. [](certificate-manager.md) Amikor a felhasználók Gépház Frissítés & biztonsági tanúsítványokhoz, és kiválasztják a Tanúsítvány telepítése lehetőséget, a felhasználói felület mostantól támogatja  >    >   **a** .pfx tanúsítványfájlt.
A felhasználók titkos kulccsal .pfx-tanúsítványt importálnak a felhasználói tárolóba vagy a számítógép tárolóba.

### <a name="smart-retry-for-app-updates"></a>Intelligens újrapróbálkozás az alkalmazásfrissítések során

A HoloLens egy új szabályzat, amely lehetővé teszi a rendszergazdák számára, hogy ismétlődő vagy egyszeri időpontot állítsanak be azon alkalmazások újraindításához, amelyek frissítése az alkalmazás használatban való használata miatt meghiúsult, és amely lehetővé teszi a frissítés alkalmazását. Ezek több különböző eseményindító, például ütemezett időpont vagy bejelentkezés alapján is beállíthatók. A szabályzat használatával kapcsolatos további információkért tekintse meg az [ApplicationManagement/ScheduleForceRestartForUpdateFailures et.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Speciális diagnosztikai jelentés megtekintése a Gépház a HoloLens

A felügyelt eszközök esetében a viselkedés hibaelhárítása során fontos lépés annak ellenőrzése, hogy a várt házirend-konfiguráció van-e alkalmazva. Korábban ezt az új funkciót az MDM-en keresztül vagy az eszköz közelében kellett volna, miután exportálta az Gépház Accounts Access (Hozzáférés munkahelyi vagy iskolai) fiókokkal szolgáltatáson keresztül összegyűjtött MDM **diagnosztikai** naplókat, és válassza a Felügyeleti naplók exportálása és megtekintése egy közeli számítógépen  ->    >  lehetőséget. 

Az MDM-diagnosztika mostantól megtekinthető az eszközön az Edge böngésző használatával. Ha könnyebben meg szeretne tekinteni egy MDM diagnosztikai jelentést, lépjen a Hozzáférés munkahelyi vagy iskolai alkalmazáshoz lapra, és válassza a Speciális diagnosztikai **jelentés megtekintése lehetőséget.** Ez létrehozza és megnyitja a jelentést egy új Edge-ablakban.

![Tekintse meg a speciális diagnosztikai jelentést Gépház alkalmazásban.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Offline diagnosztikai értesítések

Ez egy offline diagnosztika nevű meglévő [szolgáltatás frissítése.](hololens-diagnostic-logs.md#offline-diagnostics) Korábban nem volt egyértelmű jelzés a felhasználók számára a diagnosztikai gyűjtés aktiválására vagy befejezésére.
Az Insider Windows mostantól kétféle visszajelzési mód létezik az offline diagnosztikához. Az első a bejelentések értesítései, amelyek a gyűjtemény indításakor és befejezésekor is megjelennek. Ezek akkor jelennek meg, ha a felhasználó bejelentkezett, és rendelkezik vizualizációval.

![Bejelentés a naplók gyűjtéséhez.](./images/logcollection1.jpg)

![Bejelentés a naplógyűjtés befejezésekor.](./images/logcollection2.jpg)

Mivel a felhasználók gyakran használják tartalék naplógyűjtési mechanizmusként az Offline diagnosztikát, amikor nem férnek hozzá a kijelzőkhez, nem tudnak bejelentkezni vagy még mindig az OOBE-ban vannak, a naplók gyűjtésekor hangjel is megjelenik. A bejelentési értesítés mellett ez a hang is megjelenik.

Ez az új funkció az eszköz frissítésekekor lesz engedélyezve, és nem szükséges engedélyezni vagy kezelni. Ha az új visszajelzés nem jelenik meg vagy nem hallható, az Offline diagnosztika továbbra is létrejön.

Reméljük, hogy a visszajelzések újabb kiegészítésével könnyebb diagnosztikai adatokat gyűjteni, és gyorsabban elhárítani a problémákat.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Csak privát áruházbeli alkalmazások használata Microsoft Store

A RequirePrivateStoreOnly szabályzat engedélyezve van a HoloLens. Ez a szabályzat lehetővé Microsoft Store, hogy az alkalmazás csak a szervezet számára konfigurált privát tárolót mutassa. A hozzáférés korlátozása csak az Ön által elérhetővé tett alkalmazásokra.

További információ az [ApplicationManagement/RequirePrivateStoreOnly-ről](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="low-storage-log-collection-improvements"></a>Az alacsony tárterületű naplógyűjtés fejlesztései

Az olyan forgatókönyvekben, ahol az eszköz a diagnosztikai naplók gyűjtésekor  kevés a lemezterület, létrejön egyStorageDiagnostics.zipnevű jelentés. Az alacsony tárterület küszöbértékét a rendszer Windows [határozza meg.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

### <a name="moving-platform-mode"></a>Platform mód mozgatás

Az **Insider 20348.1411-es** buildjében bétaverziós támogatást biztosítunk az alacsony dinamikus mozgású mozgó platformok nyomon követéséhez a 2. HoloLens esetében. A build telepítése és a Platformáttelepítési mód engedélyezése után használhatja a HoloLens 2-es HoloLens korábban nem elérhető környezetekben, például nagy méretű teherszállítókban és nagy méretű állatokban. Jelenleg a funkció célja ezeknek az adott mozgó platformoknak a engedélyezése. Bár semmi sem akadályozza meg abban, hogy más környezetekben is megpróbálja használni a funkciót, a funkció elsősorban ezen környezetek támogatásának hozzáadására összpontosít.

Ha többet szeretne megtudni a támogatott funkciókról és az új funkció bekapcsolásról, látogasson el [a mozgóplatform oldalára.](hololens2-moving-platform.md)

### <a name="fixes-and-improvements"></a>Javítások és fejlesztések

- Kijavítottunk egy ismert hibát, Eszközportál amikor nem volt [rákérdezés zárolt fájlok letöltésére.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Kijavítottunk egy ismert hibát, amely Eszközportál és letöltés [időkorrekta miatt ki volt javítva.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- A megfelelőségi tulajdonságok jelentésével kapcsolatos problémák elhárítása HoloLens eszközökről; Előfordulhat, hogy újraindításra van szükség ahhoz, hogy a megfelelő jelentéskészítés aktiválódjon az Insider-buildek esetén.  
- Engedélyezve van [egy Hozzárendelt](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) hozzáférés API, így az alkalmazások megállapíthatják, hogy egy HoloLens fut-e kioszkmódban a felhasználói fiókba bejelentkezett HoloLens.
- Frissítettük a Remote Assist új flashre telepített beépített verzióját.

## <a name="start-receiving-insider-builds"></a>Insider-buildek fogadásának kezdete

> [!NOTE]
> Ha a közelmúltban nem frissített, indítsa újra az eszközt az állapot frissítéséhez, és szerezze be a legújabb buildet.
>
> - Az "Eszköz újraindítása" hangparancs jól működik.
> - Az újraindítási gombot is választhatja a Gépház/Windows Insider Program.
>
> Előfordulhat, hogy egy hiba történt a háttéren, amely miatt ön is találkozhatott, így újra jó úton haladhat.

A 2. HoloLens eszközön válassza az **Update** Gépház Security &  >  **Windows Insider Program** get  >   started (Első **lépések) lehetőséget.** Csatolja a regisztrációhoz használt fiókot Windows Insiderben.

Windows belső csatorna most már a Csatornákra van átköltözve. A **Gyors** kör lesz a **Fejlesztői** csatorna, a **Lassú** kör lesz a **Béta csatorna,** a Kiadási **előnézeti** kör pedig a Kiadás **előnézete csatorna** lesz. A leképezés így néz ki:

![Windows Belső csatornák magyarázata](images/WindowsInsiderChannels.png)

További információ: [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (A belső csatornák Windows blogok).
Ezután válassza az **Active development of Windows (Aktív** fejlesztés a Windows) lehetőséget, válassza ki, hogy szeretné-e fogadni a Dev **Channelt** vagy Béta csatorna **buildeket,** és tekintse át a program feltételeit.
A **befejezéshez válassza > Újraindítás most lehetőséget.** Miután az eszköz újraindult, Gépház > **Update & Security > Frissítések** keresése a legújabb build lehozáshoz lapra.

### <a name="update-error-0x80070490-work-around"></a>Hiba 0x80070490 hiba

Ha frissítési hibát 0x80070490 a Dev vagy a Beta csatornán való frissítéskor, próbálkozzon a következő rövid távú munkával. Ez magában foglalja a belső csatorna áthelyezését, a frissítés be- és áthelyezését, majd az Insider-csatorna vissza mozgatát.

#### <a name="stage-one---release-preview"></a>Első fázis – Előzetes kiadás

1. Gépház a Biztonsági & frissítése, majd Windows Insider Program a Kiadási előzetes **csatorna lehetőséget.**

2. Gépház, Update & Security, Windows Update, Check **for updates**. A frissítés után folytassa a második fázisra.

#### <a name="stage-two---dev-channel"></a>Második fázis – Fejlesztői csatorna

1. Gépház Update & Security (Biztonsági frissítés) Windows Insider Program válassza a **Dev Channel (Fejlesztői csatorna) lehetőséget.**

2. Gépház, Update & Security, Windows Update, Check **for updates**.

## <a name="ffu-download-and-flash-directions"></a>FFU letöltési és flash utasítások

A flight signed ffu (FFU) teszteléséhez először fel kell oldania az eszköz zárolását, mielőtt felrakná a repülőjárat aláírt ffu-ját.

1. Pc-n:
    1. Töltse le a ffu-t a számítógépére a [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) ről.

    1. Telepítse az ARC-t (Advanced Recovery Companion) a Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. On HoloLens - Flight Unlock: Open **Gépház** Update & Security Windows Insider Program majd  >    >   regisztráljon, indítsa újra az eszközt.

1. Flash FFU – Most már az ARC használatával is meg flashlheti a repülőjárat aláírt FFU-ját.

### <a name="provide-feedback-and-report-issues"></a>Visszajelzés küldése és problémák jelentése

A [visszajelzések Visszajelzési központ és a](hololens-feedback.md) jelentésekkel kapcsolatos problémák HoloLens a saját alkalmazásában. A Visszajelzési központ biztosítja, hogy minden szükséges diagnosztikai információ bekerül a hibakeresésbe és a probléma megoldásában a mérnökeinknek.  A kínai és a japán nyelvű HoloLens ugyanúgy kell jelenteni.

> [!NOTE]
> Mindenképpen fogadja el azt a kérdést, amely rákérdez, hogy szeretné Visszajelzési központ szeretné-e elérni a Dokumentumok mappát (válassza az **Igen** lehetőséget, amikor a rendszer kéri).

## <a name="note-for-developers"></a>Megjegyzés fejlesztőknek

Nyugodtan kipróbálhatja az alkalmazások fejlesztését belső fejlesztésű belső HoloLens.  Az első [lépésekhez tekintse](https://developer.microsoft.com/windows/mixed-reality/development) HoloLens fejlesztői dokumentációját. Ugyanezek az utasítások az Insider-buildekkel is HoloLens.  Használhatja a Unity ugyanazon buildeket, Visual Studio a fejlesztéshez már HoloLens is.

## <a name="stop-receiving-insider-builds"></a>Insider-buildek fogadásának leállítása

Ha már nem szeretné megkapni az Windows Holographic Insider-buildjét, kikapcsolhatja, ha az HoloLens éles buildet futtat, vagy az Advanced Recovery Companion segítségével helyreállíthatja az eszközt az Windows Holographic nem insider verziójára. [](hololens-recovery.md)

> [!CAUTION]
> Megjelenik egy ismert probléma, amely miatt az Insider Preview buildre való regisztrációt manuálisan újratelepítő felhasználók kék képernyőt tapasztalnak. Ezt követően manuálisan kell helyreállítania az eszközt. Ha szeretne többet tudni arról, hogy ez hatással lenne-e az Ön számára, tekintse meg az ismert [problémát.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Annak ellenőrzése, hogy a HoloLens futtat-e éles buildet:

1. Keresse meg **Gépház > System > About (Rendszer >) et,** és keresse meg a build számát.

1. [Az éles buildszámokat a kibocsátási megjegyzésekben láthatja.](hololens-release-notes.md)

Az Insider-buildek lemondása:

1. Éles buildet HoloLens futtató környezetben válassza a Gépház > **Update & Security > Windows Insider Program** lehetőséget, és válassza a Stop Insider builds (Belső buildek leállítása) **lehetőséget.**

1. Az eszköz lemondáshoz kövesse az utasításokat.
