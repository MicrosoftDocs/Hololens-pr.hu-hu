---
title: Belső előzetes verzió a Microsoft HoloLens
description: Megismerheti az Insider-buildek első lépéseit, és értékes visszajelzést adhat az operációs rendszer következő jelentős frissítésével kapcsolatban a HoloLens.
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
ms.date: 08/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 80346fd74c9b38ed557d815ed138b1da5702609e
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859017"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Belső előzetes verzió a Microsoft HoloLens

Üdvözöljük az Insider előzetes verziójának legújabb, HoloLens! Az első lépések [egyszerűek,](hololens-insider.md#start-receiving-insider-builds) és értékes visszajelzést adhatunk a következő jelentős operációsrendszer-frissítésünkről a HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Belső kibocsátási megjegyzések

Izgatottan várjuk, hogy ismét új funkciókat Windows Insidersbe. Az új buildek a fejlesztői és a bétaverziós csatornákon lesznek elérhetőek a legújabb frissítésekért. Ezt az oldalt folyamatosan frissítjük, ahogy további funkciókat és frissítéseket adunk hozzá a Windows Insider buildjeinkhez. Legyen izgatott, és készen áll arra, hogy ezeket a frissítéseket a valóságba keverje.

Ez a továbbfejlesztett hibaelhárításról és eszközjelentésről, a kioszkmód egyes rögzített hibáiról, a tanúsítványmegjelenítőről, a kibővített kezelhetőségi felületről és a nagyobb frissítési megbízhatóságról szól. Ennek a funkciófrissítésnek egy új funkciója hamarosan HoloLens a Mozgóplatform mód. Tekintse meg a 2. HoloLens nagyszerű funkcióit!

| Szolgáltatás                 | Leírás                | Felhasználó vagy forgatókönyv | Build bevezetve |
|-------------------------|----------------------------|--------------|------------------|
| [Mozgóplatformos mód](#moving-platform-mode) | Bevezeti a mozgóplatformos mód bétaverzióját, amely a konfigurálás után HoloLens 2 használatát teszi lehetővé alacsony dinamikus mozgást tapasztaló nagy méretű étkek esetében. | Mind | 20348.1411 |
| [PFX-fájltámogatás a Tanúsítványkezelőhöz](#pfx-file-support-for-certificate-manager) | PFX-tanúsítványok hozzáadása a felhasználói Gépház keresztül | Végfelhasználó | 20348.1405 |
| [Speciális diagnosztikai jelentés megtekintése a Gépház a HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | MDM diagnosztikai naplók megtekintése az eszközön | Hibaelhárítás | 20348.1405 |
| [Offline diagnosztikai értesítések](#offline-diagnostics-notifications) | Visszajelzés a naplógyűjtéssel kapcsolatban | Hibaelhárítás | 20348.1405 |
| [Az alacsony tárterületű naplógyűjtés fejlesztései](#low-storage-log-collection-improvements) | A naplógyűjtési forgatókönyvek fejlesztései alacsony tárolási helyzetekben. | Hibaelhárítás | 20348.1412 |
| [CSP-módosítások a jelentéskészítési HoloLens részleteihez](#csp-changes-for-reporting-hololens-details) | Új CSP-k a számára az adatok lekérdezéséhez | It-rendszergazdák    | 20348.1403                 |
| [CSP által vezérelt automatikus bejelentkezési szabályzat](#auto-login-policy-controlled-by-csp) | A fiók automatikus bejelentkezéshez használatos | It-rendszergazdák | 20348.1405 |
| [Továbbfejlesztett frissítés-újraindításészlelés és értesítések](#improved-update-restart-detection-and-notifications) | Új engedélyezett szabályzatok és felhasználói felület a frissítésekhez. | It-rendszergazdák | 20348.1405 |
| [Intelligens újrapróbálkozás az alkalmazásfrissítések során](#smart-retry-for-app-updates) | Lehetővé teszi, hogy a rendszergazdák ütemezett újraterveket frissítsenek az alkalmazásokon. | It-rendszergazdák | 20348.1405 |
| [Csak privát áruházbeli alkalmazások használata Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Áruházbeli alkalmazás konfigurálása úgy, hogy csak a szervezettől származó alkalmazásokat mutassa | Rendszergazdai | 20348.1408 |
| [WDAC- és LOB-alkalmazások használata](#use-wdac-and-lob-apps) | Lehetővé teszi, hogy a rendszergazdák saját alkalmazásokat használjanak, és továbbra is a WDAC használatával blokkolják a többi alkalmazást. | It-rendszergazdák | 20348.1405 |
| [Javítások és fejlesztések](#fixes-and-improvements) | Javítások és fejlesztések a HoloLens. | Mind | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>Rendszergazdai belső szolgáltatás ellenőrzőlistája

✔️ Ha egyetlen Azure AD-fiókot szeretne beállítani az automatikus bejelentkezéshez, konfigurálja ezt az új [CSP-t.](#auto-login-policy-controlled-by-csp) <br>
✔️ Ha úgy szeretné konfigurálni az alkalmazásokat, hogy a frissítés sikertelen frissítése után automatikusan kísérelje meg a frissítést, állítsa be ezt az új CSP-t az intelligens [újrapróbálkozáshoz.](#smart-retry-for-app-updates) <br>
✔️ Ha jobban szeretné szabályozni az operációs rendszer frissítéseit, tekintse meg az újonnan engedélyezett frissítési [szabályzatokat.](#improved-update-restart-detection-and-notifications) <br>
✔️ Ha a vállalati alkalmazásokat az Microsoft Store-n keresztül szeretné elérhetővé tenni a vállalati áruházban, de csak a szervezet alkalmazásait szeretné engedélyezni, nem a teljes áruházat, állítsa be ezt a [szabályzatot.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ Ha szeretné tudni a tárterületet, az SSID-t vagy a BSSID-t a HoloLens-eszközein, tekintse meg ezeket a jelentéskészítési [CSP-ket.](#csp-changes-for-reporting-hololens-details) <br>
✔️ Ha a WDAC használatával szeretné letiltani az alkalmazások vagy folyamatok indítását, de saját használatra kész alkalmazásokat is használnia kell, mostantól engedélyezheti a LOB-t a [WDAC-szabályzatban.](#use-wdac-and-lob-apps)

### <a name="moving-platform-mode"></a>Mozgóplatformos mód

Az **Insider 20348.1411-es** buildjében bétaverzióval bővült a 2. verzióban elérhető alacsony dinamikus mozgását indító platformok HoloLens támogatása. A build telepítése és a Mozgóplatform mód engedélyezése után a 2. HoloLens-t korábban elérhetetlen környezetekben használhatja, például nagy méretű teherszállítókban és nagy méretű állatokban. A funkció jelenleg csak az adott mozgó platformok engedélyezését célozza meg. Bár semmi sem akadályozza meg a funkció más környezetekben való használatát, a funkció elsősorban ezen környezetek támogatásának hozzáadására összpontosít.

Ha többet szeretne megtudni a támogatott funkciókról és az új funkció engedélyezéséről, látogasson el a [mozgóplatformra.](hololens2-moving-platform.md)

### <a name="pfx-file-support-for-certificate-manager"></a>PFX-fájltámogatás a Tanúsítványkezelőhöz

Az Insider Windows 20348.1405-ös buildje. Mostantól támogatott a Tanúsítványkezelő a .pfx-tanúsítványok használatára. [](certificate-manager.md) Amikor a felhasználók a **Gépház** Update & Security Certificates (Biztonsági tanúsítványok frissítése) lapra navigálnak, és kiválasztják a Tanúsítvány telepítése lehetőséget, a felhasználói felület mostantól támogatja  >    >   **a** .pfx tanúsítványfájlt.
A felhasználók .pfx-tanúsítványt importálnak titkos kulccsal a felhasználói tárolóba vagy számítógéptárolóba.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Speciális diagnosztikai jelentés megtekintése a Gépház a HoloLens

A felügyelt eszközök viselkedésének hibaelhárítása során fontos lépés annak ellenőrzése, hogy a rendszer a várt szabályzatkonfigurációt alkalmazza-e. Korábban ezt az információt az MDM-en keresztül vagy az eszköz közelében kellett megtekinteni, miután exportálta az **Gépház Accounts** Access munkahelyi vagy iskolai fiókokkal gyűjtött diagnosztikai naplóit, majd válassza a Felügyeleti naplók exportálása és megtekintése egy közeli számítógépen  ->    >  lehetőséget. 

Az MDM-diagnosztika mostantól megtekinthető az eszközön az Edge böngésző használatával. Ha könnyebben meg szeretne tekinteni egy MDM diagnosztikai jelentést, lépjen a Hozzáférés munkahelyi vagy iskolai alkalmazáshoz lapra, és válassza a **Speciális diagnosztikai jelentés megtekintése lehetőséget.** Ez létrehozza és megnyitja a jelentést egy új Edge-ablakban.

![Speciális diagnosztikai jelentés megtekintése az Gépház alkalmazásban.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Offline diagnosztikai értesítések

Ez egy offline diagnosztika nevű meglévő [szolgáltatás frissítése.](hololens-diagnostic-logs.md#offline-diagnostics) Korábban nem volt egyértelmű jelzés a felhasználók számára a diagnosztikai gyűjtés aktiválására vagy befejezésére.
Az Insider Windows buildek két módon adhatják hozzá a visszajelzéseket az offline diagnosztikához. Az első a bejelentések értesítései, amelyek a gyűjtemény indításakor és befejezésekor is megjelennek. Ezek akkor jelennek meg, ha a felhasználó bejelentkezett, és rendelkezik vizualizációval.

![Bejelentés a naplók gyűjtéséhez.](./images/logcollection1.jpg)

![Bejelentés a naplógyűjtés befejezésekor.](./images/logcollection2.jpg)

Mivel a felhasználók gyakran használják az offline diagnosztikát tartalék naplógyűjtési mechanizmusként, amikor nem férnek hozzá a kijelzőkhez, nem tudnak bejelentkezni, vagy még mindig az OOBE-ban vannak, a naplók gyűjtésekor hangszavak is le fognak játszani. A bejelentési értesítés mellett ez a hang is megjelenik.

Ez az új funkció az eszköz frissítésekekor lesz engedélyezve, és nem szükséges engedélyezni vagy kezelni. Ha az új visszajelzés nem jelenik meg vagy nem hallható, az Offline diagnosztika továbbra is létrejön.

Reméljük, hogy a visszajelzések újabb kiegészítésével könnyebb diagnosztikai adatokat gyűjteni, és gyorsabban elhárítani a problémákat.

### <a name="low-storage-log-collection-improvements"></a>Az alacsony tárterületű naplógyűjtés fejlesztései

Az olyan forgatókönyvekben, ahol az eszköz a diagnosztikai naplók gyűjtésekor  kevés a lemezterület, létrejön egyStorageDiagnostics.zipnevű jelentés. Az alacsony tárterület küszöbértékét a rendszer Windows [határozza meg.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-módosítások a jelentéskészítési HoloLens részleteihez

- A Windows 20348.1403-as buildben vezettük be

Az alábbi CSP-k új módokon jelenthetők meg a különböző eszközökről HoloLens jelentésekhez.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP – Ingyenes Storage

A DevDetail CSP mostantól a szabad tárterületet is jelenti HoloLens eszközön. Ennek nagyjából egyeznie kell az alkalmazás Gépház lapján látható Storage értékkel. Az alábbiakban az ezt az információt tartalmazó csomópont található.

- ./DevDetail/Ext/Microsoft/FreeStorage (csak GET művelet)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP – SSID és BSSID

A DeviceStatus CSP mostantól azon hálózati SSID és BSSID Wi-Fi is jelenti, amelyhez a HoloLens csatlakozik. A következő csomópontok tartalmazzák ezt az információt.

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
> - Egyes események, például a fő operációsrendszer-frissítések esetében előfordulhat, hogy a megadott felhasználónak újra be kell jelentkeznie az eszközre az automatikus bejelentkezés folytatásához.
> - Az automatikus bejelentkezés csak MSA- és AAD-felhasználók számára támogatott.

### <a name="improved-update-restart-detection-and-notifications"></a>Továbbfejlesztett frissítés-újraindítás észlelése és értesítések

Az aktív órák és a telepítési idő házirendek között lehetőség van arra, hogy ne kelljen újraindítani HoloLens eszközöket, amikor használatban vannak. Ha azonban nem történik újraindítás a szükséges frissítés telepítésének befejezéséhez, az is késleltetné a frissítések telepítését. Most olyan szabályzatokat adtunk hozzá, amelyek lehetővé teszik az it-ita számára a határidők és a szükséges újraindítások kényszerítése, valamint a frissítések telepítésének időbeni befejezését. A felhasználók értesítést kaphatnak az újraindítás kezdeményezése előtt, és az it-szabályzatnak megfelelően késleltetni tudják az újraindítást.

A következő frissítési szabályzatok hozzáadása:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="smart-retry-for-app-updates"></a>Intelligens újrapróbálkozás az alkalmazásfrissítések során

A HoloLens egy új szabályzat, amely lehetővé teszi a rendszergazdák számára, hogy ismétlődő vagy egyszeri időpontot állítsanak be az olyan alkalmazások újraindításához, amelyek frissítése az alkalmazás használatban való használata miatt meghiúsult, és lehetővé teszi a frissítés alkalmazását. Ezek több különböző eseményindító, például ütemezett időpont vagy bejelentkezés alapján is beállíthatók. További információ az [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)szabályzatnézet használatával kapcsolatban.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Csak privát áruházbeli alkalmazások használata Microsoft Store

A RequirePrivateStoreOnly szabályzat engedélyezve van a HoloLens. Ez a szabályzat lehetővé Microsoft Store, hogy az alkalmazás csak a szervezet számára konfigurált privát tárolót mutassa. A hozzáférés korlátozása csak az Ön által elérhetővé tett alkalmazásokra.

További információ az [ApplicationManagement/RequirePrivateStoreOnly-ről](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="use-wdac-and-lob-apps"></a>WDAC- és LOB-alkalmazások használata

Mostantól a WDAC használatával letilthatja az alkalmazások vagy folyamatok indítását, és továbbra is használhatja a saját öntudatos alkalmazásait. mostantól engedélyezheti őket a WDAC-szabályzatban. A szabályzat használata magában foglalja egy további kódsor futtatását a PowerShellben a WDAC-szabályzat létrehozásakor. [Tekintse át az itt található lépéseket.](/mem/intune/configuration/custom-profile-hololens)

### <a name="fixes-and-improvements"></a>Javítások és fejlesztések

- Kijavítottunk egy ismert hibát, Eszközportál amikor nem volt [rákérdezés zárolt fájlok letöltésére.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Ki van [javítva a fájlfeltöltéssel és Eszközportál időkorreklozásokkal kapcsolatban a fájlfeltöltési és -letöltési időkorreklok ismert problémája.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- A megfelelőségi tulajdonságok jelentésével kapcsolatos problémák elhárítása HoloLens eszközökről; Előfordulhat, hogy újraindításra van szükség ahhoz, hogy a megfelelő jelentéskészítés aktiválódjon az Insider-buildek esetén.  
- Engedélyezve van [egy Hozzárendelt](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) hozzáférés API, így az alkalmazások megállapíthatják, hogy egy HoloLens fut-e kioszkmódban a HoloLens.
- Frissítettük a Remote Assist új flashre telepített beépített verzióját.

## <a name="start-receiving-insider-builds"></a>Insider-buildek fogadásának kezdete

> [!NOTE]
> Ha a közelmúltban nem frissített, indítsa újra az eszközt az állapot frissítéséhez, és szerezze be a legújabb buildet.
>
> - Az "Eszköz újraindítása" hangparancs jól működik.
> - Az újraindítási gombot is választhatja a Gépház/Windows Insider Program.
>
> Előfordulhat, hogy egy hiba történt a háttéren, amely miatt előfordulhatott, hogy újra a útjára fog menni.

A 2. HoloLens eszközön válassza az **Update** Gépház Security &  >  **lehetőséget Windows Insider Program** és válassza az  >   Első **lépések lehetőséget.** Csatolja a regisztrációhoz használt fiókot Windows Insiderben.

Windows belsős már áttért a Csatornákra. A **Gyors** kör lesz a **Fejlesztői** csatorna, a **Lassú** kör lesz a **Béta csatorna,** a Kiadási **előnézeti** kör pedig a Kiadás **előnézete csatorna** lesz. A leképezés így néz ki:

![Windows Belső csatornák magyarázata](images/WindowsInsiderChannels.png)

További információ: [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (A belső csatornák Windows blogok).
Ezután válassza az **Active development of Windows (Aktív** fejlesztés a Windows) lehetőséget, válassza ki, hogy szeretné-e fogadni a Dev **Channelt** vagy Béta csatorna **buildeket,** és tekintse át a program feltételeit.
A **befejezéshez válassza > Újraindítás most** lehetőséget. Az eszköz újraindítása után az Update Gépház > Security & **> Frissítések** keresése a legújabb buildhez lapra.

### <a name="update-error-0x80070490-work-around"></a>Hiba 0x80070490 hiba

Ha frissítési hibát 0x80070490 a Dev vagy a Beta csatornán való frissítéskor, próbálkozzon a következő rövid távú munkával. Ez magában foglalja a belső csatorna áthelyezését, a frissítés be- és áthelyezését, majd az Insider-csatorna vissza mozgatát.

#### <a name="stage-one---release-preview"></a>Első fázis – Előzetes kiadás

1. Gépház Update & Security (Biztonsági frissítés) Windows Insider Program válassza a Release Preview Channel (Előzetes **verziójú csatorna) lehetőséget.**

2. Gépház, Update & Security, Windows Update, **Check for updates**. A frissítés után folytassa a második fázisra.

#### <a name="stage-two---dev-channel"></a>Második fázis – Fejlesztői csatorna

1. Gépház Update & Security (Biztonsági frissítés) Windows Insider Program válassza a **Dev Channel (Fejlesztői csatorna) lehetőséget.**

2. Gépház, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>FFU letöltési és flash utasítások

Az aláírt ffu repülőjárattal való teszteléshez először fel kell oldania az eszköz zárolását, mielőtt felrakná a repülőjárat aláírt ffu-ját.

1. Pc-n:
    1. Töltse le a ffu-t a számítógépére a [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) ről.

    1. Telepítse az ARC-t (Speciális helyreállítási társ) a következő Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. On HoloLens - Flight Unlock: Open **Gépház**  >  **Update & Security**  >  **Windows Insider Program** majd regisztráljon, indítsa újra az eszközt.

1. Flash FFU – Most már az ARC használatával is flash(flash) lehet a repülőjárat aláírt FFU-ját.

### <a name="provide-feedback-and-report-issues"></a>Visszajelzés küldése és problémák jelentése

A [visszajelzések Visszajelzési központ és](hololens-feedback.md) a jelentésekkel kapcsolatos problémák HoloLens a saját alkalmazásában. A Visszajelzési központ biztosítja, hogy minden szükséges diagnosztikai információ megtalálható, hogy a mérnökök gyorsan hibakeresést és megoldást tudjanak biztosítani a problémára.  A kínai és a japán nyelvű HoloLens ugyanúgy kell jelenteni.

> [!NOTE]
> Mindenképpen fogadja el azt a kérdést, amely rákérdez, hogy szeretné Visszajelzési központ szeretné-e elérni a Dokumentumok mappát (válassza az **Igen** lehetőséget, amikor a rendszer kéri).

## <a name="note-for-developers"></a>Megjegyzés fejlesztőknek

Nyugodtan fejleszthet alkalmazásokat belső fejlesztésű belső HoloLens.  Az első [lépésekhez HoloLens tekintse meg az](https://developer.microsoft.com/windows/mixed-reality/development) HoloLens fejlesztői dokumentációját. Ugyanezek az utasítások az insider buildekkel is HoloLens.  Használhatja a Unity ugyanazon buildeket és Visual Studio, mint a fejlesztéshez HoloLens használ.

## <a name="stop-receiving-insider-builds"></a>Insider-buildek fogadásának leállítása

Ha már nem szeretné megkapni az Windows Holographic Insider-buildjét, kikapcsolhatja, ha az HoloLens éles buildet futtat, vagy az Advanced Recovery Companion használatával helyreállíthatja az eszközt az Windows Holographic nem insider verziójára. [](hololens-recovery.md)

> [!CAUTION]
> Megjelenik egy ismert probléma, amely miatt az Insider Preview buildből a friss előzetes build manuális újratelepítése után leiratkozó felhasználók kék képernyőt tapasztalnak. Ezt követően manuálisan kell helyreállítania az eszközt. Ha szeretné részletesen ismerni, hogy ez hatással lenne-e a problémára, tekintse meg ezt az ismert [problémát.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Annak ellenőrzése, hogy a HoloLens futtat-e éles buildet:

1. Keresse meg **Gépház > System > About (Rendszer >) et,** és keresse meg a build számát.

1. [Az éles buildszámok kibocsátási megjegyzései.](hololens-release-notes.md)

Az Insider-buildek lemondása:

1. Éles buildet HoloLens futtató Gépház > az **Update & Security > Windows Insider Program** oldalon válassza a **Stop Insider builds (Belső** buildek leállítása) lehetőséget.

1. Az eszköz lemondáshoz kövesse az utasításokat.
