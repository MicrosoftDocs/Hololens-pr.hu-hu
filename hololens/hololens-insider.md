---
title: Belső előzetes verzió a Microsoft HoloLens
description: Ismerje meg az Insider-buildek első lépéseit, és adjon értékes visszajelzést a következő jelentős operációsrendszer-frissítésünkről a HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 09/14/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 68485fd0ad7f050748a412da3d57eb8f59e9a685
ms.sourcegitcommit: d09556a101663ef5dfff865d4753e64a41032b78
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2021
ms.locfileid: "128346744"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Belső előzetes verzió a Microsoft HoloLens

Üdvözöljük az Insider előzetes verziójának legújabb buildjeiben HoloLens! Egyszerűen elkezdheti a [rendszert,](hololens-insider.md#start-receiving-insider-builds) és értékes visszajelzést adhat a következő jelentős operációsrendszer-frissítésünkről a HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Belső kibocsátási megjegyzések

Izgatottan várjuk, hogy új funkciókat Windows Insidersbe. Az új buildek a fejlesztői és bétaverziós csatornákra lesznek felkísértve a legújabb frissítéseket. Ezt az oldalt folyamatosan frissítjük, ahogy további funkciókat és frissítéseket adunk hozzá a Windows Insider buildjeinkhez. Legyen izgatott, és készen áll arra, hogy ezeket a frissítéseket a valóságba keverje.

Ez a továbbfejlesztett hibaelhárítási és eszközjelentésekkel, a kioszkmódban és a tanúsítványmegjelenítővel kapcsolatos javított hibákról, a bővített kezelhetőségi felületről és a magasabb frissítési megbízhatóságról szól. Ennek a funkciófrissítésnek egy új funkciója hamarosan HoloLens a mozgóplatformos mód. Tekintse meg a 2. HoloLens nagyszerű funkcióit!

| Szolgáltatás                 | Leírás                | Felhasználó vagy forgatókönyv | Build bevezetve |
|-------------------------|----------------------------|--------------|------------------|
| [Platform mód mozgatás](#moving-platform-mode) | Bevezeti a moving Platform Mode bétaverziót, amely a konfigurálás után HoloLens 2. használatát teszi lehetővé alacsony dinamikus mozgást tapasztaló nagy méretű állatokon. | Mind | 20348.1411 |
| [PFX-fájltámogatás a Tanúsítványkezelőhöz](#pfx-file-support-for-certificate-manager) | PFX-tanúsítványok hozzáadása Gépház felhasználói felületen | Végfelhasználó | 20348.1405 |
| [Speciális diagnosztikai jelentés megtekintése a Gépház a HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | MDM diagnosztikai naplók megtekintése az eszközön | Hibaelhárítás | 20348.1405 |
| [Offline diagnosztikai értesítések](#offline-diagnostics-notifications) | Visszajelzés a naplógyűjtéssel kapcsolatban | Hibaelhárítás | 20348.1405 |
| [Az alacsony tárterületű naplógyűjtés fejlesztései](#low-storage-log-collection-improvements) | A naplógyűjtési forgatókönyvek fejlesztései alacsony tárolási helyzetekben. | Hibaelhárítás | 20348.1412 |
| [CSP-módosítások a jelentéskészítési HoloLens részleteihez](#csp-changes-for-reporting-hololens-details) | Új CSP-k az adatok lekérdezéséhez | It-rendszergazdák    | 20348.1403                 |
| [CSP által vezérelt automatikus bejelentkezési szabályzat](#auto-login-policy-controlled-by-csp) | Fiók automatikus bejelentkezéshez használatos | It-rendszergazdák | 20348.1405 |
| [Továbbfejlesztett frissítés-újraindítás észlelése és értesítések](#improved-update-restart-detection-and-notifications) | Új engedélyezett szabályzatok és felhasználói felület a frissítésekhez. | It-rendszergazdák | 20348.1405 |
| [Intelligens újrapróbálkozás az alkalmazásfrissítések során](#smart-retry-for-app-updates) | Lehetővé teszi a rendszergazdák számára az alkalmazások frissítésére ütemezett újraküldetni a frissítéseket. | It-rendszergazdák | 20348.1405 |
| [Csak privát áruházbeli alkalmazások használata Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Az áruházbeli alkalmazás konfigurálása úgy, hogy csak a szervezettől származó alkalmazásokat mutassa | Rendszergazdai | 20348.1408 |
| [WDAC- és LOB-alkalmazások használata](#use-wdac-and-lob-apps) | Lehetővé teszi a rendszergazdák számára, hogy saját alkalmazásokat használjanak, és továbbra is a WDAC használatával tiltsák le a többi alkalmazást. | It-rendszergazdák | 20348.1405 |
| [Javítások és fejlesztések](#fixes-and-improvements) | Javítások és fejlesztések a HoloLens. | Mind | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>Rendszergazdai belső szolgáltatás ellenőrzőlistája

✔️ Ha egyetlen Azure AD-fiókot szeretne beállítani az automatikus bejelentkezéshez, konfigurálja ezt az új [CSP-t.](#auto-login-policy-controlled-by-csp) <br>
✔️ Ha úgy szeretné konfigurálni az alkalmazásokat, hogy a frissítés sikertelen frissítése után automatikusan kísérelje meg a frissítést, állítsa be ezt az új CSP-t intelligens [újrapróbálkozáshoz.](#smart-retry-for-app-updates) <br>
✔️ Ha jobban szeretné szabályozni az operációs rendszer frissítéseit, tekintse meg az újonnan engedélyezett frissítési [szabályzatokat.](#improved-update-restart-detection-and-notifications) <br>
✔️ Ha a vállalati alkalmazásokat az Microsoft Store-n keresztül szeretné elérhetővé tenni a vállalati áruházban, de csak a szervezet alkalmazásait szeretné [engedélyezni,](#use-only-private-store-apps-for-microsoft-store)nem a teljes áruházat, állítsa be ezt a szabályzatot. <br>
✔️ Ha szeretné tudni a szabad tárterületet, az SSID-t vagy a BSSID-t a HoloLens-eszközein, tekintse meg ezeket a jelentéskészítési [CSP-ket.](#csp-changes-for-reporting-hololens-details) <br>
✔️ Ha a WDAC használatával szeretné letiltani az alkalmazások vagy folyamatok indítását, de saját használatra kész alkalmazásokat is használnia kell, mostantól engedélyezheti a LOB-t a [WDAC-szabályzatban.](#use-wdac-and-lob-apps)

### <a name="moving-platform-mode"></a>Platform üzemmód mozgatás

Az **Insider 20348.1411-es** buildjében bétaverziós támogatást biztosítunk az alacsony dinamikus mozgású mozgó platformok nyomon követéséhez a 2. HoloLens esetében. A build telepítése és a Platformáttelepítési mód engedélyezése után használhatja a HoloLens 2-es HoloLens korábban nem elérhető környezetekben, például nagy méretű teherszállítókban és nagy méretű állatokban. Jelenleg a funkció célja ezeknek az adott mozgó platformoknak a engedélyezése. Bár semmi sem akadályozza meg abban, hogy más környezetekben is megpróbálja használni a funkciót, a funkció elsősorban ezen környezetek támogatásának hozzáadására összpontosít.

Ha többet szeretne megtudni a támogatott funkciókról és az új funkció engedélyezéséről, látogasson el a [mozgóplatform oldalára.](hololens2-moving-platform.md)

#### <a name="overview-to-try-out-moving-platform-mode"></a>A platform üzemmód áthelyezésének kipróbált módja – áttekintés

1. [Fejlesztői mód és eszközportál engedélyezése.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. [Platformmód áthelyezésének engedélyezése az Eszközportálon keresztül.](hololens2-moving-platform.md#enabling-moving-platform-mode)
1. Vigye az eszközt a nagyméretű mozgó platformra, és figyelje meg, mennyire stabilak a hologramok.

### <a name="pfx-file-support-for-certificate-manager"></a>PFX-fájltámogatás a Tanúsítványkezelőhöz

Az Insider Windows 20348.1405-ös buildben vezettük be. Mostantól támogatott a Tanúsítványkezelő a .pfx-tanúsítványok használatára. [](certificate-manager.md) Amikor a felhasználók az **Update Gépház** security certificates (Biztonsági tanúsítványok frissítése) & a Install a certificate (Tanúsítvány telepítése) gombra, a felhasználói felület mostantól támogatja  >    >   **a** .pfx tanúsítványfájlt.
A felhasználók titkos kulccsal .pfx-tanúsítványt importálnak a felhasználói tárolóba vagy a számítógép tárolóba.

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>PFX-fájlok tanúsítványkezelőben való kipróbálása – áttekintés

1. Készítse elő a PFX-fájlt.
1. Másolja a fájlt az eszközre EGY USB-C-kábelen keresztül.
1. Nyissa meg Gépház alkalmazást, keresse meg a [Tanúsítványkezelőt,](certificate-manager.md) és alkalmazza a tanúsítványt.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Speciális diagnosztikai jelentés megtekintése a Gépház a HoloLens

A felügyelt eszközök esetében a viselkedés hibaelhárítása során fontos lépés annak ellenőrzése, hogy a várt házirend-konfiguráció van-e alkalmazva. Az új funkció esetében korábban az MDM-en keresztül vagy az eszköz közelében, az MDM-en keresztül, az **Gépház** Accounts Access munkahelyi vagy iskolai fiókkal összegyűjtött diagnosztikai naplók exportálása után kellett megtekinteni ezt az információt, majd a Felügyeleti naplók exportálása és megtekintése egy közeli számítógépen lehetőség  ->    >  **kiválasztásával.** 

Az MDM-diagnosztika mostantól megtekinthető az eszközön az Edge böngésző használatával. Ha könnyebben meg szeretne tekinteni egy MDM diagnosztikai jelentést, lépjen a Hozzáférés munkahelyi vagy iskolai alkalmazáshoz lapra, és válassza a Speciális diagnosztikai **jelentés megtekintése lehetőséget.** Ez létrehozza és megnyitja a jelentést egy új Edge-ablakban.

![Tekintse meg a speciális diagnosztikai jelentést Gépház alkalmazásban.](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>A speciális diagnosztikai jelentés kipróbálásának áttekintése

1. Nyissa meg a Beállítások alkalmazást.
1. Lépjen a Fiókok lapra, és kattintson a Felügyeleti naplók **exportálása hivatkozásra.**
1. Tekintse meg az eszköz konfigurációjának speciális információit.

### <a name="offline-diagnostics-notifications"></a>Offline diagnosztikai értesítések

Ez egy offline diagnosztika nevű meglévő [szolgáltatás frissítése.](hololens-diagnostic-logs.md#offline-diagnostics) Korábban nem volt egyértelmű jelzés a felhasználók számára a diagnosztikai gyűjtés aktiválására vagy befejezésére.
Az Insider Windows buildek két módon adhatják hozzá a visszajelzéseket az offline diagnosztikához. Az első a bejelentések értesítései, amelyek a gyűjtés indításakor és befejezésekor is megjelennek. Ezek akkor jelennek meg, ha a felhasználó bejelentkezett, és rendelkezik vizualizációval.

![Bejelentés a naplók gyűjtéséhez.](./images/logcollection1.jpg)

![Bejelentés a naplógyűjtés befejezésekor.](./images/logcollection2.jpg)

Mivel a felhasználók gyakran használják az Offline diagnosztikát tartalék naplógyűjtési mechanizmusként, amikor nem férnek hozzá a kijelzőkhez, nem tudnak bejelentkezni vagy még mindig az OOBE-ban vannak, a naplók gyűjtésekor hangszavak is le fognak játszani. A bejelentési értesítés mellett ez a hang is megjelenik.

Ez az új funkció az eszköz frissítésekekor lesz engedélyezve, és nem szükséges engedélyezni vagy kezelni. Ha az új visszajelzés nem jelenik meg vagy nem hallható, az offline diagnosztika továbbra is létrejön.

Reméljük, hogy a visszajelzések újabb kiegészítésével könnyebb diagnosztikai adatokat gyűjteni, és gyorsabban elhárítani a problémákat.

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>A diagnosztikai értesítések kipróbálásának áttekintése

1. Az eszköz zárolásának feloldása és elhasználódása.
1. Az Offline **diagnosztikagyűjtéshez** nyomja le a Power and Volume **down** (Energiaellátás és kötet lenyomás) [gombot.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Tekintse meg a bejelentési értesítéseket, és hallgassa meg a hangjeleket, amikor az eszköz elindul és befejezi a naplók gyűjtését.

### <a name="low-storage-log-collection-improvements"></a>Az alacsony tárterületű naplógyűjtés fejlesztései

Olyan forgatókönyvekben, ahol úgy tűnik, hogy az eszköznek kevés a  lemezterülete a diagnosztikai naplók gyűjtésekor, a rendszer létrehoz egyStorageDiagnostics.zipnevű jelentést. Az alacsony tárterület küszöbértékét a rendszer Windows [határozza meg.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>Az alacsony tárolási szint fejlesztésének kipróbálás – áttekintés

1. Töltse ki az eszköz tárhelyét.
1. Az Offline **diagnosztikagyűjtéshez** nyomja le a Power and Volume **down** (Energiaellátás és kötet lenyomás) [gombot.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Figyelje meg, hogy egy új fájl található a naplók gyűjteményében, amely a naplók dokumentumok mappájában HoloLens.

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-módosítások a jelentéskészítési HoloLens részleteihez

- A Windows Insider 20348.1403-as buildje

Az alábbi CSP-k új módokon jelenthetők meg a HoloLens eszközeiről.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP – Ingyenes Storage

A DevDetail CSP mostantól a szabad tárterületet is jelenti HoloLens eszközön. Ennek nagyjából egyeznie kell az alkalmazás Gépház lapján látható Storage értékkel. Az alábbiakban az ezt az információt tartalmazó csomópont található.

- ./DevDetail/Ext/Microsoft/FreeStorage (csak GET művelet)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP – SSID és BSSID

A DeviceStatus CSP mostantól azon hálózati SSID és BSSID Wi-Fi is jelenti, amelyhez HoloLens van csatlakoztatva. Az alábbiakban az adott csomópontok tartalmazzák ezt az információt.

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

Ez az új AutoLogonUser szabályzat szabályozza, hogy a rendszer automatikusan bejelentkeztet-e egy felhasználót. Egyes ügyfelek identitáshoz kötött eszközöket szeretne beállítani, de nem szeretnék a bejelentkezési élményt. Imagine egy eszköz azonnali felvétele és a remote assist használata. Vagy az is előnyös, ha gyorsan el tudja terjeszteni a HoloLens, és lehetővé teszi a végfelhasználók számára a bejelentkezés gyorsítását.

Ha a szabályzat nem üres értékre van állítva, az automatikus bejelentkezési felhasználó e-mail-címét adja meg. Az automatikus bejelentkezés engedélyezéséhez a megadott felhasználónak legalább egyszer be kell jelentkeznie az eszközre.

Az új szabályzat sztringértékének `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` OMA-URI-ját

- Az azonos e-mail-címmel rendelkező felhasználónál engedélyezve lesz az automatikus bejelentkezés.

Egy olyan eszközön, ahol ez a szabályzat konfigurálva van, a szabályzatban megadott felhasználónak legalább egyszer be kell jelentkeznie. Az első bejelentkezést követően az eszköz további újraindításai automatikusan bejelentkeztetik a megadott felhasználót. Csak egyetlen automatikus bejelentkezési felhasználó támogatott. Ha engedélyezve van, az automatikusan bejelentkezett felhasználó nem fog tudni manuálisan kijelentkezni. Egy másik felhasználóként való bejelentkezéshez először le kell tiltani a szabályzatot.

> [!NOTE]
>
> - Egyes események, például a fő operációsrendszer-frissítések esetén előfordulhat, hogy a megadott felhasználónak újra be kell jelentkeznie az eszközre az automatikus bejelentkezés folytatásához.
> - Az automatikus bejelentkezés csak MSA- és AAD-felhasználók számára támogatott.

#### <a name="overview-to-try-auto-logon-csp"></a>Az automatikus bejelentkezés CSP-jének kipróbálás – áttekintés

1. Konfigurálja az új CSP-t egy kívánt [felhasználóhoz egy egyéni házirend használatával:](/mem/intune/configuration/custom-settings-windows-10)`./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. Alkalmazza a CSP-t az eszközre a [kiépítési csomag vagy](hololens-provisioning.md) [az MDM segítségével.](hololens-mdm-configure.md)
1. Jelentkezzen be a megadott fiókba.
1. Indítsa újra az eszközt, és figyelje meg, hogy a felhasználó automatikusan bejelentkezik.

### <a name="improved-update-restart-detection-and-notifications"></a>Továbbfejlesztett frissítés-újraindításészlelés és értesítések

Az aktív órák és a telepítési idő házirendek között lehetőség van elkerülni a HoloLens újraindítását, amikor használatban vannak. Ha azonban nem történik újraindítás a szükséges frissítések telepítésének befejezéséhez, az késleltetné a frissítések telepítését. Most olyan szabályzatokat adtunk hozzá, amelyek lehetővé teszik az it-ita számára a határidők és a szükséges újraindítások kényszerítése, valamint a frissítések időben való telepítésének befejezését. A felhasználókat az újraindítás megkezdése előtt értesíteni lehet, és az it-szabályzatnak megfelelően késleltetni tudják az újraindítást.

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

#### <a name="overview-to-try-new-update-notifications"></a>Az új frissítési értesítések kipróbálásának áttekintése

1. Konfigurálja az új frissítési CSP-k valamelyikét a [kiépítési](hololens-provisioning.md) csomag vagy az [MDM](hololens-mdm-configure.md) segítségével (lásd a fenti hivatkozáslistát, és válasszon egyet).
1. Használja az eszközt az ütemezett időpontban.
1. Figyelje meg, hogy a felhasználó értesítést kap a frissítésről, és hogy újra kell indítani az \* eszközt.

\* Az eredmények a használt frissítési szabályzatok alapján változhatnak.

### <a name="smart-retry-for-app-updates"></a>Intelligens újrapróbálkozás az alkalmazásfrissítések során

A HoloLens egy új szabályzat, amely lehetővé teszi a rendszergazdák számára, hogy ismétlődő vagy egyszeri dátumot állítsanak be azon alkalmazások újraindításához, amelyek frissítése nem sikerült, mert az alkalmazás használatban van, és lehetővé teszi a frissítés alkalmazását. Ezek több különböző eseményindító, például ütemezett időpont vagy bejelentkezés alapján is beállíthatók. További információ az [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)szabályzatnézet használatával kapcsolatban.

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Az intelligens újrapróbálkozás alkalmazásfrissítések kipróbálási áttekintése

1. Konfigurálja az új intelligens újrapróbálkozási funkciót.
1. Olyan eszközön, amely még nem kapta meg az alkalmazást, és megfelelően van konfigurálva, jelentkezzen be egy online környezetbe.
1. Kapcsolja ki vagy válassza le az alkalmazást, hogy az eszköz ne tudja letölteni az alkalmazást.
1. A letöltés újrapróbálkozása során az eszköz bekapcsolt állapotban legyen, és kapcsolódva legyen az internethez.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Csak privát áruházbeli alkalmazások használata Microsoft Store

A RequirePrivateStoreOnly szabályzat engedélyezve van a HoloLens. Ez a szabályzat lehetővé Microsoft Store, hogy az alkalmazás úgy legyen konfigurálva, hogy csak a szervezet számára konfigurált privát tárolót mutassa a [Microsoft Store Vállalatoknak.](/microsoft-store/microsoft-store-for-business-overview) A hozzáférés korlátozása csak az Ön által elérhetővé tett alkalmazásokra.

További információ az [ApplicationManagement/RequirePrivateStoreOnly -ről.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

#### <a name="overview-to-try-only-private-store-apps"></a>A privát áruházbeli alkalmazások kipróbálásának áttekintése

1. Konfigurálja az új szabályzatot az eszközökhöz [az MDM-en keresztül.](hololens-mdm-configure.md)
1. Jelentkezzen be egy olyan eszközre, amely a szabályzatot használja.
1. Nyissa meg Microsoft Store alkalmazást, és figyelje meg, hogy csak a szervezet alkalmazásait látja.

### <a name="use-wdac-and-lob-apps"></a>WDAC- és LOB-alkalmazások használata

Mostantól a WDAC használatával letilthatja az alkalmazások vagy folyamatok indítását, és továbbra is használhatja a saját, nagyságú alkalmazásait. mostantól engedélyezheti őket a WDAC-szabályzatban. A szabályzat használata magában foglalja egy további kódsor futtatását a PowerShellben a WDAC-szabályzat létrehozásakor. [Tekintse át az itt található lépéseket.](/mem/intune/configuration/custom-profile-hololens)

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>Saját alkalmazások WDAC használatával való letiltásának áttekintése

1. Gyűjtse össze az LOB-alkalmazás AUMID-it és a blokkolni kívánt alkalmazásokat.
1. [Hozzon létre egy új WDAC-szabályzatot](/mem/intune/configuration/custom-profile-hololens) az új lépéseket követve.
1. [Telepítse a szabályzatot az MDM használatával](hololens-mdm-configure.md) az eszközére.
1. Jelentkezzen be az eszközre, és figyelje meg, hogy elindíthatja az alkalmazást, és letilthat másokat.

### <a name="fixes-and-improvements"></a>Javítások és fejlesztések

#### <a name="for-developers"></a>Fejlesztőknek

- Kijavítottunk egy ismert hibát, Eszközportál amikor nem volt rá szükség [a zárolt fájlok letöltésére.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Ki van [javítva a fájlfeltöltési és -Eszközportál időkorreklú frissítések ismert problémája.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- A 2D-alkalmazások gamepad-feldolgozása le lett tiltva az Insider-buildek esetében. Az eltávolítással az alkalmazások mostantól közvetlenül is használhatjak a Gamepad API-kat, és hozzáférhetnek a vezérlők teljes készletéhez, és a fejlesztés során még többre van képes. A fejlesztőknek a Gamepad API-kat kell használniuk a Gamepad bemenetének használhatja. Példa a [Gamepad osztályra (Windows. Gaming.Input) – Windows UWP-alkalmazások.](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)
- Engedélyezte a [Hozzárendelt](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) hozzáférés API-t, így az alkalmazások mostantól megállapíthatják, hogy egy HoloLens fut-e kioszkmódban a felhasználói fiókba bejelentkezett HoloLens.

#### <a name="for-enterprise"></a>Nagyvállalati

- A megfelelőségi tulajdonságok jelentésével kapcsolatos problémák elhárítása HoloLens eszközökről; Előfordulhat, hogy újraindításra van szükség ahhoz, hogy a megfelelő jelentéskészítés aktiválódjon az Insider-buildek esetén.  
- Frissítettük a Remote Assist beépített verzióját, amely friss flashre van telepítve.
- Kijavítottunk egy hibát, amely miatt az első felhasználói bejelentkezés után az OOBE leállt olyan esetekben, amikor AAD-csoportalapú kioszkkonfigurációkat használtak.
- Javítva lett a frissítési értesítések és párbeszédpanelek megjelenítésével kapcsolatos probléma az eszköz újraindításához.
- Kijavítottunk egy hibát, amely miatt az eszköz újraindítása után az Xbox-vezérlőket és Bluetooth LE-perifériákat újra párosítani kellett a csatlakozáshoz.

## <a name="start-receiving-insider-builds"></a>Insider-buildek fogadásának kezdete

> [!NOTE]
> Ha a közelmúltban nem frissített, indítsa újra az eszközt az állapot frissítéséhez, és szerezze be a legújabb buildet.
>
> - Az "Eszköz újraindítása" hangparancs jól működik.
> - Az újraindítási gombot a következő Gépház/Windows Insider Program.
>
> Előfordulhat, hogy egy hiba történt a háttérben, amely miatt előfordulhatott, hogy ezzel vissza fog menni a útjára.

A 2. HoloLens eszközön válassza az **Update** Gépház Security &  >  **lehetőséget Windows Insider Program** és válassza az  >   Első **lépések lehetőséget.** Csatolja a regisztrációhoz használt fiókot Windows Insiderben.

> [!NOTE]
> Ahhoz, hogy regisztrálja az eszközt az Insider-buildekbe, engedélyeznie kell a nem kötelező telemetriát. Ha még nem tette meg, nyissa meg a Gépház alkalmazást, és válassza a **Privacy**  ->  **Diagnostics & visszajelzést,** majd válassza a Választható diagnosztikai **adatok lehetőséget.**

Windows belső csatorna most a Csatornákra van átköltözve. A **Gyors** kör lesz a **fejlesztői** csatorna, a **Lassú** kör lesz a **Béta csatorna,** a kiadási **előnézeti** kör pedig a kiadási **előnézeti csatorna lesz.** A leképezés így néz ki:

![Windows A belső csatornák magyarázata.](images/WindowsInsiderChannels.png)

További információ: [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (A belső csatornák Windows blogok).
Ezután válassza az **Active development of Windows**(A fejlesztői csatornák aktív fejlesztése) lehetőséget, válassza ki, hogy dev **channel-t** vagy Béta csatorna **buildeket** szeretne kapni, és tekintse át a program feltételeit.
A **befejezéshez válassza > Újraindítás most** lehetőséget. Miután az eszköz újraindult, a Gépház > **Update & Security** > Frissítések keresése ás a legújabb buildhez lapra.

### <a name="update-error-0x80070490-work-around"></a>Hiba 0x80070490 hiba a hibakódok között

Ha frissítési hibát 0x80070490 fejlesztői vagy bétaverziós csatornán való frissítéskor, próbálkozzon a következő rövid távú munkával. Ez magában foglalja a belső csatorna áthelyezését, a frissítés be- és áthelyezését, majd az Insider-csatorna vissza mozgatát.

#### <a name="stage-one---release-preview"></a>Első fázis – Előzetes verzió

1. Gépház Update & Security (Biztonsági frissítés) Windows Insider Program válassza a Release Preview Channel (Előzetes **verziójú csatorna) lehetőséget.**

2. Gépház, Update & Security, Windows Update, Frissítések **keresése.** A frissítés után folytassa a második fázisra.

#### <a name="stage-two---dev-channel"></a>Második fázis – Fejlesztői csatorna

1. Gépház Update & Security (Biztonsági frissítés) Windows Insider Program válassza a **Dev Channel (Fejlesztői csatorna) lehetőséget.**

2. Gépház, Update & Security, Windows Update, Frissítések **keresése.**

## <a name="ffu-download-and-flash-directions"></a>FFU letöltési és flash utasítások

Az aláírt ffu repülőjárattal való teszteléshez először fel kell oldania az eszköz zárolását, mielőtt a repülőjárat aláírt ffu-ját felrakná.

1. Pc-n:
    1. Töltse le a ffu-t a számítógépére a [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) ről.

    1. Telepítse az ARC-t (Speciális helyreállítási társ) a következő Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. On HoloLens - Flight Unlock: Open **Gépház**  >  **Update & Security**  >  **Windows Insider Program** majd regisztráljon, indítsa újra az eszközt.

1. Flash FFU – Most már az ARC használatával is flashlheti a repülőjárat aláírt FFU-ját.

### <a name="provide-feedback-and-report-issues"></a>Visszajelzés küldése és problémák jelentése

A [visszajelzések Visszajelzési központ és](hololens-feedback.md) a jelentésekkel kapcsolatos problémák HoloLens a saját alkalmazásában. A Visszajelzési központ biztosítja, hogy minden szükséges diagnosztikai információ bekerül a hibakeresésbe és a probléma megoldásához.  A kínai és a japán nyelvű HoloLens ugyanúgy kell jelenteni.

> [!NOTE]
> Mindenképpen fogadja el azt a kérdést, amely megkérdezi, hogy szeretné Visszajelzési központ szeretné-e elérni a Dokumentumok mappát (válassza az **Igen** lehetőséget, amikor a rendszer kéri).

## <a name="note-for-developers"></a>Megjegyzés fejlesztőknek

Nyugodtan fejleszthet alkalmazásokat belső fejlesztésű belső HoloLens.  Az első [lépésekhez tekintse](https://developer.microsoft.com/windows/mixed-reality/development) HoloLens fejlesztői dokumentációját. Ugyanezek az utasítások a kód insider buildje HoloLens.  Használhatja a Unity ugyanazon buildeket és Visual Studio, mint a fejlesztéshez HoloLens használ.

## <a name="stop-receiving-insider-builds"></a>Insider-buildek fogadásának leállítása

Ha már nem szeretné megkapni az Windows Holographic Insider-buildjét, kikapcsolhatja, ha az HoloLens éles [](hololens-recovery.md) buildet futtat, vagy az Advanced Recovery Companion használatával helyreállíthatja az eszközt az Windows Holographic nem insider verziójára.

> [!CAUTION]
> Megjelenik egy ismert probléma, amely miatt az Insider Preview-ból való regisztrációt manuálisan újratelepítő felhasználók kék képernyőt tapasztalnak. Ezt követően manuálisan kell helyreállítania az eszközt. Ha szeretné részletesen ismerni, hogy ez hatással lenne-e a problémára, tekintse meg az ismert [problémát.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Annak ellenőrzése, hogy a HoloLens futtat-e éles buildet:

1. Keresse meg **Gépház > System > About (Rendszer) >,** és keresse meg a buildszámot.

1. [Az éles buildszámok kibocsátási megjegyzései.](hololens-release-notes.md)

Az Insider-buildek lemondása:

1. Egy éles HoloLens buildet futtató környezetben válassza a Gépház > Frissítése & **Security > Windows Insider Program** lehetőséget, és válassza a Stop Insider builds (Belső buildek leállítása) **lehetőséget.**

1. Az eszköz lemondáshoz kövesse az utasításokat.
