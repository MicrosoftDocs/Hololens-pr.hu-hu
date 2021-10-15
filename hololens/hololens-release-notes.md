---
title: HoloLens 2. kiadási megjegyzések
description: Maradjon naprakész az új, 2. HoloLens frissítésekkel.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/12/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 3f5e5f3e38c24805935fc69dfacd5eac93ddd017
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034280"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2. kiadási megjegyzések

Annak érdekében, hogy hatékony felhasználói élményben legyen része a HoloLens, továbbra is kiadjuk a funkciókat, a hibákat és a biztonsági frissítéseket. Ezen az oldalon láthatja az egyes HoloLens újdonságokat. A 2. HoloLens legújabb frissítéséhez ellenőrizheti [](hololens-update-hololens.md#check-for-updates-and-manually-update) a frissítéseket, és manuálisan frissíthet, vagy a Teljes flash frissítéssel (FFU) frissítheti az eszközt az [Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device)segítségével. A [letöltés](https://aka.ms/hololens2download) naprakész, és a legújabb általánosan elérhető buildet biztosítja.

> [!NOTE]
> A Windows 11-es bejelentése a legújabb PC-s verzióra Windows. 2021 októberében elindítottunk egy jelentős [operációsrendszer-frissítést HoloLens 2.](#windows-holographic-version-21h2)kiadásra, és az ügyfelek visszajelzései alapján dolgozunk a jövőbeli kiadásokon.

## <a name="windows-holographic-version-21h2"></a>Windows Holographic, 21H2-es verzió

- Build 20348.1432

Windows A Holographic 21H2-es verziója már elérhető, és nagyszerű új funkciókat kínál 2 HoloLens és informatikai szakember számára. Ez a továbbfejlesztett hibaelhárítási és eszközjelentésekkel, a kioszkmód egyes javított hibáival, a tanúsítványmegjelenítővel, a bővített kezelhetőségi felülettel és a magasabb frissítési megbízhatósággal kapcsolatos. Ennek a funkciófrissítésnek egy új funkciója hamarosan HoloLens a moving Platform Mode (Mozgóplatform mód). Tekintse meg a 2. HoloLens nagyszerű funkcióit!

Ez a legújabb kiadás a 21H1-es verzió havi frissítése, de ezúttal új funkciókat is tartalmazunk, ezért a fő buildszám változatlan marad, és az Windows Update a 21H1-es verzió (20348-as build) havi kiadását jelzi. HoloLens 2 beállítás továbbra is 21H1-et jelenít meg annak ellenére, hogy erre a kiadásra 21H2-ként hivatkozunk. Annak ellenőrzéséhez, hogy megkapta-e a 21H2-t, ellenőrizze, hogy a verziószám 20348.1432-es vagy újabb. A Build Number (Buildszám) megjelenik a Gépház > About (Információ) képernyőn, és ellenőrizze, hogy a legújabb elérhető buildet (20348.1432-es vagy további) verzióval dolgozik-e.

A legújabb kiadásra való frissítéshez nyissa meg a Gépház alkalmazást, nyissa meg az Update & Security (Biztonsági frissítések frissítése) gombra, és koppintson a Check for Updates (Frissítések keresése) gombra. A frissítésfrissítések kezeléséhez HoloLens a Manage HoloLens updates (Új frissítések [kezelése) HoloLens.](hololens-updates.md)

| Szolgáltatás                 | Leírás                | Felhasználó vagy forgatókönyv |
|-------------------------|----------------------------|--------------|
| [Platform mód mozgatás](#moving-platform-mode) | Bevezeti a Mozgóplatform mód bétaverzióját, amely a konfiguráláskor HoloLens 2 használatát teszi lehetővé alacsony dinamikus mozgást tapasztaló nagy méretű állatokon. | Mind |
| [PFX-fájl támogatása a Tanúsítványkezelőben](#pfx-file-support-for-certificate-manager) | PFX-tanúsítványok hozzáadása Gépház felhasználói felületen | Végfelhasználó |
| [Speciális diagnosztikai jelentés megtekintése a Gépház a HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | MDM diagnosztikai naplók megtekintése az eszközön | Hibaelhárítás |
| [Offline diagnosztikai értesítések](#offline-diagnostics-notifications) | Visszajelzés a naplógyűjtéssel kapcsolatban | Hibaelhárítás |
| [Az alacsony tárterületű naplógyűjtés fejlesztései](#low-storage-log-collection-improvements) | A naplógyűjtési forgatókönyvek fejlesztései alacsony tárolási helyzetekben. | Hibaelhárítás |
| [CSP-módosítások a jelentéskészítési HoloLens részleteihez](#csp-changes-for-reporting-hololens-details) | Új CSP-k az adatok lekérdezéséhez | It-rendszergazdák    |
| [CSP által vezérelt automatikus bejelentkezési szabályzat](#auto-login-policy-controlled-by-csp) | Fiók automatikus bejelentkezéshez használatos | It-rendszergazdák |
| [Továbbfejlesztett frissítés-újraindítás észlelése és értesítések](#improved-update-restart-detection-and-notifications) | Új engedélyezett szabályzatok és felhasználói felület a frissítésekhez. | It-rendszergazdák |
| [Intelligens újrapróbálkozás az alkalmazásfrissítések során](#smart-retry-for-app-updates) | Lehetővé teszi a rendszergazdák számára az alkalmazások frissítésére ütemezett újraküldetni a frissítéseket. | It-rendszergazdák |
| [Csak privát áruházbeli alkalmazások használata Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Az áruházbeli alkalmazás konfigurálása úgy, hogy csak a szervezettől származó alkalmazásokat mutassa | Rendszergazdai |
| [WDAC- és LOB-alkalmazások használata](#use-wdac-and-lob-apps) | Lehetővé teszi, hogy a rendszergazdák saját alkalmazásokat használjanak, és továbbra is a WDAC használatával tiltsák le a többi alkalmazást. | It-rendszergazdák |
| [Javítások és fejlesztések](#fixes-and-improvements) | Javítások és fejlesztések a HoloLens. | Mind |

### <a name="it-admin-feature-checklist"></a>Rendszergazdai funkciók ellenőrzőlistája

✔️ Ha egyetlen Azure AD-fiókot szeretne beállítani az automatikus bejelentkezéshez, konfigurálja ezt az új [CSP-t.](#auto-login-policy-controlled-by-csp) <br>
✔️ Ha úgy szeretné konfigurálni az alkalmazásokat, hogy a frissítés sikertelen frissítése után automatikusan kísérelje meg a frissítést, állítsa be ezt az új [CSP-t intelligens újrapróbálkozáshoz.](#smart-retry-for-app-updates) <br>
✔️ Ha jobban szeretné szabályozni az operációs rendszer frissítéseit, tekintse meg az újonnan engedélyezett frissítési [szabályzatokat.](#improved-update-restart-detection-and-notifications) <br>
✔️ Ha a vállalati alkalmazásokat az Microsoft Store-n keresztül szeretné elérhetővé tenni a vállalati áruházban, de csak a szervezet alkalmazásait szeretné engedélyezni, nem a teljes áruházat, állítsa be ezt a [szabályzatot.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ Ha szeretné tudni a szabad tárterületet, az SSID-t vagy a HoloLens-eszközök BSSID-ját, tekintse meg ezeket a jelentéskészítési [CSP-ket.](#csp-changes-for-reporting-hololens-details) <br>
✔️ Ha a WDAC használatával szeretné letiltani az alkalmazások vagy folyamatok indítását, de saját használatra kész alkalmazásokat is használnia kell, mostantól engedélyezheti a LOB-t a [WDAC-szabályzatban.](#use-wdac-and-lob-apps)

### <a name="moving-platform-mode"></a>Platform mód mozgatás

A Windows [Holographic 21H2-es](hololens-release-notes.md#windows-holographic-version-21h2) verziójától a 2. verzióban bétaverziós támogatást biztosítunk a alacsony dinamikus mozgású mozgó platformok HoloLens követéséhez. A build telepítése és a Mozgóplatform mód engedélyezése után használhatja a HoloLens 2-es HoloLens korábban nem elérhető környezetekben, például nagy méretű teherszállítókban és nagy méretű állatokban. Jelenleg a funkció célja ezeknek az adott mozgó platformoknak a engedélyezése. Bár semmi sem akadályozza meg abban, hogy más környezetekben is megpróbálja használni a funkciót, a funkció célja, hogy először támogatást nyújtsunk ezekhez a környezetekhez.

A támogatott funkciókról és az új funkció engedélyezéséről a [mozgóplatform oldalán olvashat bővebben.](hololens2-moving-platform.md)

#### <a name="overview-to-try-out-moving-platform-mode"></a>A platform üzemmód áthelyezésének kipróbált módja – áttekintés

1. [Fejlesztői mód és eszközportál engedélyezése.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. [Platform üzemmód áthelyezésének engedélyezése az Eszközportálon keresztül.](hololens2-moving-platform.md#enabling-moving-platform-mode)
1. Vigye az eszközt a nagyméretű mozgó platformra, és figyelje meg, mennyire stabilak a hologramok.

### <a name="pfx-file-support-for-certificate-manager"></a>PFX-fájl támogatása a Tanúsítványkezelőben

Az Insider Windows 20348.1405-ös buildben vezettük be. Mostantól támogatott a Tanúsítványkezelő a .pfx-tanúsítványok használatára. [](certificate-manager.md) Amikor a felhasználók a **Biztonsági tanúsítványok frissítése Gépház** lapra &, és kiválasztják a Tanúsítvány telepítése lehetőséget, a felhasználói felület mostantól támogatja  >    >   **a** .pfx tanúsítványfájlt.
A felhasználók titkos kulccsal .pfx-tanúsítványt importálnak a felhasználói tárolóba vagy a számítógép tárolóba.

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>PFX-fájlok tanúsítványkezelőben való kipróbálása – áttekintés

1. Készítse elő a PFX-fájlt.
1. Másolja a fájlt az eszközre EGY USB-C-kábelen keresztül.
1. Nyissa meg Gépház alkalmazást, keresse meg a [Tanúsítványkezelőt,](certificate-manager.md) és alkalmazza a tanúsítványt.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Speciális diagnosztikai jelentés megtekintése a Gépház a HoloLens

A felügyelt eszközök esetében a viselkedés hibaelhárítása során fontos lépés annak ellenőrzése, hogy a várt házirend-konfiguráció van-e alkalmazva. Korábban ezt az új funkciót az MDM-en keresztül vagy az eszköz közelében kellett volna, az **Gépház** Accounts Access munkahelyi vagy iskolai fiókkal összegyűjtött diagnosztikai naplók exportálása után, majd a Felügyeleti naplók exportálása és megtekintése egy közeli számítógépen lehetőség  ->    >  kiválasztásával. 

Az MDM-diagnosztika mostantól megtekinthető az eszközön az Edge böngésző használatával. Ha könnyebben meg szeretne tekinteni egy MDM diagnosztikai jelentést, lépjen a Hozzáférés munkahelyi vagy iskolai alkalmazáshoz lapra, és válassza a **Speciális diagnosztikai jelentés megtekintése lehetőséget.** Ez létrehozza és megnyitja a jelentést egy új Edge-ablakban.

![Tekintse meg a speciális diagnosztikai jelentést Gépház alkalmazásban.](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>A speciális diagnosztikai jelentés kipróbálásának áttekintése

1. Nyissa meg a Beállítások alkalmazást.
1. Lépjen a Fiókok lapra, és kattintson a Felügyeleti naplók **exportálása hivatkozásra.**
1. Tekintse meg az eszköz konfigurációjának speciális információit.

### <a name="offline-diagnostics-notifications"></a>Offline diagnosztikai értesítések

Ez egy offline diagnosztika nevű meglévő [szolgáltatás frissítése.](hololens-diagnostic-logs.md#offline-diagnostics) Korábban nem volt egyértelmű jelzés a felhasználók számára, hogy aktiválták a diagnosztikai gyűjtést, vagy hogy befejeződött.
A [Holographic Windows 21H2](hololens-release-notes.md#windows-holographic-version-21h2)verzióban hozzáadva két visszajelzési mód létezik az offline diagnosztika esetén. Az első a bejelentések értesítései, amelyek a gyűjtemény indításakor és befejezésekor is megjelennek. Ezek akkor jelennek meg, ha a felhasználó bejelentkezett, és rendelkezik vizualizációval.

![Bejelentés a naplók gyűjtéséhez.](./images/logcollection1.jpg)

![Bejelentés a naplógyűjtés befejezésekor.](./images/logcollection2.jpg)

Mivel a felhasználók gyakran használják tartalék naplógyűjtési mechanizmusként az Offline diagnosztikát, amikor nem férnek hozzá a kijelzőkhez, nem tudnak bejelentkezni vagy még mindig az OOBE-ban vannak, a naplók gyűjtésekor hangjel is megjelenik. A bejelentési értesítés mellett ez a hang is megjelenik.

Ez az új funkció az eszköz frissítésekekor lesz engedélyezve, és nem szükséges engedélyezni vagy kezelni. Ha az új visszajelzés nem jelenik meg vagy nem hallható, az Offline diagnosztika továbbra is létrejön.

Reméljük, hogy a visszajelzések újabb kiegészítésével könnyebb diagnosztikai adatokat gyűjteni, és gyorsabban elhárítani a problémákat.

Ezek az információk később, a diagnosztikai [naplók oldalán megtekinthetők.](hololens-diagnostic-logs.md#offline-diagnostics)

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>A diagnosztikai értesítések kipróbálásának áttekintése

1. Az eszköz zárolásának feloldása és elhasználódása.
1. Az Offline **diagnosztikagyűjtéshez** nyomja le a Power and Volume **down** (Be- és lenyomás) [gombkombinációt.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Megtekintheti a bejelentési értesítéseket, és hangjeleket hallhat arról, hogy az eszköz mikor indul el és fejezi be a naplók gyűjtését.

### <a name="low-storage-log-collection-improvements"></a>Az alacsony tárterületű naplógyűjtés fejlesztései

Olyan forgatókönyvekben, amelyekben úgy tűnik, hogy az eszköznek kevés a lemezterülete a diagnosztikai naplók **gyűjtésekor,** a rendszer létrehoz egyStorageDiagnostics.zipnevű jelentést. Az alacsony tárterület küszöbértékét a rendszer Windows [határozza meg.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

Ezek az információk később, a diagnosztikai [naplók oldalán megtekinthetők.](hololens-diagnostic-logs.md#offline-diagnostics)

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>A kevés tárterületet eredményező fejlesztések kipróbálásának áttekintése

1. Töltse ki az eszköz tárhelyét.
1. Az Offline **diagnosztikagyűjtéshez** nyomja le a Power and Volume **down** (Be- és lenyomás) [gombkombinációt.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Figyelje meg, hogy egy új fájl található a naplók gyűjteményében, amely a naplók dokumentumok mappájában HoloLens.

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-módosítások a jelentéskészítési HoloLens részleteihez

Az alábbi CSP-k új módszereket kínálnak a jelentések jelentésére a HoloLens eszközökről.

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

Egy olyan eszközön, ahol ez a szabályzat konfigurálva van, a szabályzatban megadott felhasználónak legalább egyszer be kell jelentkeznie. Az eszköz az első bejelentkezést követő újraindítása után automatikusan bejelentkezik a megadott felhasználóra. Csak egyetlen automatikus bejelentkezési felhasználó támogatott. Ha engedélyezve van, az automatikusan bejelentkezett felhasználó nem fog tudni manuálisan kijelentkezni. Egy másik felhasználóként való bejelentkezéshez először le kell tiltani a szabályzatot.

> [!NOTE]
>
> - Egyes események, például a fő operációsrendszer-frissítések esetében előfordulhat, hogy a megadott felhasználónak újra be kell jelentkeznie az eszközre az automatikus bejelentkezés folytatásához.
> - Az automatikus bejelentkezés csak msa és felhasználói AAD támogatott.

#### <a name="overview-to-try-auto-logon-csp"></a>Az automatikus bejelentkezés csp-jének kipróbálás áttekintése

1. Konfigurálja az új CSP-t egy kívánt [felhasználóhoz egy egyéni házirend használatával:](/mem/intune/configuration/custom-settings-windows-10)`./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. Alkalmazza a CSP-t az eszközre a [kiépítési csomag vagy](hololens-provisioning.md) [az MDM segítségével.](hololens-mdm-configure.md)
1. Jelentkezzen be a megadott fiókba.
1. Indítsa újra az eszközt, és figyelje meg, hogy a felhasználó automatikusan be van jelentkezve.

### <a name="improved-update-restart-detection-and-notifications"></a>Továbbfejlesztett frissítés-újraindítás észlelése és értesítések

Az aktív órák és a telepítési időre vonatkozó szabályzatok között elkerülhető a HoloLens újraindítása, amikor használatban vannak. Ha azonban nem történik újraindítás a szükséges frissítés telepítésének befejezéséhez, az is késleltetné a frissítések telepítését. Most olyan szabályzatokat adtunk hozzá, amelyek lehetővé teszik az it-ita számára a határidők és a szükséges újraindítások kényszerítése, valamint a frissítések időbeni telepítésének befejezését. A felhasználók értesítést kaphatnak az újraindítás kezdeményezése előtt, és az it-szabályzatnak megfelelően késleltetni tudják az újraindítást.

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

#### <a name="overview-to-try-new-update-notifications"></a>Új frissítési értesítések kipróbálásának áttekintése

1. Konfigurálja az új frissítési CSP-k valamelyikét a [kiépítési](hololens-provisioning.md) csomag vagy az [MDM](hololens-mdm-configure.md) segítségével (lásd a fenti hivatkozáslistát, és válasszon egyet).
1. Az eszközt az ütemezett időpontban használja.
1. Figyelje meg, hogy a felhasználó értesítést kap a frissítésről, és szükség van az eszköz \* újraindítására.

\* Az eredmények a frissítési szabályzatok alapján változhatnak.

### <a name="smart-retry-for-app-updates"></a>Intelligens újrapróbálkozás az alkalmazásfrissítések során

A HoloLens egy új szabályzat, amely lehetővé teszi a rendszergazdák számára, hogy ismétlődő vagy egyszeri időpontot állítsanak be az olyan alkalmazások újraindításához, amelyek frissítése az alkalmazás használatban való használata miatt meghiúsult, és amely lehetővé teszi a frissítés alkalmazását. Ezek több különböző eseményindító, például ütemezett időpont vagy bejelentkezés alapján is beállíthatók. A szabályzat használatával kapcsolatos további információkért tekintse meg az [ApplicationManagement/ScheduleForceRestartForUpdateFailures et.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

Ezek az információk később, az alkalmazástelepítési áruház [üzleti oldalának oldalán találhatók.](app-deploy-store-business.md)

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Az alkalmazásfrissítések intelligens újrapróbálkozási próbálkozásának áttekintése

1. Konfigurálja az új intelligens újrapróbálkozási funkciót.
1. Olyan eszközön, amely még nem kapta meg az alkalmazást, és megfelelően van konfigurálva, jelentkezzen be egy online környezetbe.
1. Az eszköz kikapcsolásával vagy leválasztásával ne tudja letölteni az alkalmazást.
1. A letöltés újrapróbálkozása során az eszköz bekapcsolt állapotban legyen, és kapcsolódva legyen az internethez.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Csak privát áruházbeli alkalmazások használata Microsoft Store

A RequirePrivateStoreOnly szabályzat engedélyezve van a HoloLens. Ez a szabályzat lehetővé Microsoft Store, hogy az alkalmazás úgy legyen konfigurálva, hogy csak a szervezet számára konfigurált privát tárolót mutassa a [Microsoft Store Vállalatoknak.](/microsoft-store/microsoft-store-for-business-overview) A hozzáférés korlátozása csak az Ön által elérhetővé tett alkalmazásokra.

További információ az [ApplicationManagement/RequirePrivateStoreOnly-ről](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

Ezek az információk később, az alkalmazástelepítési áruház [üzleti oldalának oldalán találhatók.](app-deploy-store-business.md)

#### <a name="overview-to-try-only-private-store-apps"></a>A privát áruházbeli alkalmazások kipróbálásának áttekintése

1. Konfigurálja az új szabályzatot az eszközökhöz [az MDM-en keresztül.](hololens-mdm-configure.md)
1. Jelentkezzen be egy olyan eszközre, amely a szabályzatot használja.
1. Nyissa meg Microsoft Store alkalmazást, és figyelje meg, hogy csak a szervezet alkalmazásait láthatja.

### <a name="use-wdac-and-lob-apps"></a>WDAC- és LOB-alkalmazások használata

Mostantól a WDAC használatával letilthatja az alkalmazások vagy folyamatok indítását, és továbbra is használhatja a saját öntudatos alkalmazásait. mostantól engedélyezheti őket a WDAC-szabályzatban. A szabályzat használata magában foglalja egy további kódsor futtatását a PowerShellben a WDAC-szabályzat létrehozásakor. [Tekintse át az itt található lépéseket.](/mem/intune/configuration/custom-profile-hololens)

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>Saját alkalmazások WDAC használatával való letiltásának áttekintése

1. Gyűjtse össze az LOB-alkalmazás AUMID-it és a blokkolni kívánt alkalmazásokat.
1. [Hozzon létre egy új WDAC-szabályzatot](/mem/intune/configuration/custom-profile-hololens) az új lépéseket követve.
1. [Telepítse a szabályzatot az MDM használatával](hololens-mdm-configure.md) az eszközére.
1. Jelentkezzen be az eszközre, és figyelje meg, hogy elindíthatja az alkalmazást, és letilthat másokat.

### <a name="fixes-and-improvements"></a>Javítások és fejlesztések

#### <a name="for-developers"></a>Fejlesztőknek

- Kijavítottunk egy ismert hibát, Eszközportál amikor nem volt rákérdezés [a zárolt fájlok letöltésére.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Ki van [javítva a fájlfeltöltési és -Eszközportál időkorreklú időkorrekta egy ismert problémája.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- A 2D-alkalmazások gamepad-feldolgozása le lett tiltva az Insider-buildek esetében. Az eltávolítással az alkalmazások mostantól közvetlenül is használhatjak a Gamepad API-kat, és hozzáférhetnek a vezérlők teljes készletéhez, és a fejlesztés során még többre van képes. A fejlesztőknek a Gamepad API-kat kell használniuk a Gamepad bemenetének használhatja. Példa a [Gamepad osztályra (Windows. Gaming.Input) – Windows UWP-alkalmazások.](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)
- Engedélyezte a [Hozzárendelt hozzáférés](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) API-t, így az alkalmazások mostantól megállapíthatják, hogy egy HoloLens fut-e kioszkmódban a felhasználói fiókba bejelentkezett HoloLens.

#### <a name="for-enterprise"></a>Nagyvállalati

- A megfelelőségi tulajdonságok jelentésével kapcsolatos problémák megoldása HoloLens eszközökről; Előfordulhat, hogy újraindításra van szükség ahhoz, hogy a megfelelő jelentéskészítés aktiválódjon az Insider-buildek esetén.  
- Frissítettük a Remote Assist beépített verzióját, amely friss flashre van telepítve.
- Kijavítottunk egy hibát, amely miatt az első felhasználói bejelentkezés után az OOBE leállt olyan forgatókönyvekben, AAD csoportalapú kioszkkonfigurációkat használtak.
- Javítva lett a frissítési értesítések és párbeszédpanelek megjelenítésével kapcsolatos probléma az eszköz újraindításához.
- Kijavítottunk egy hibát, amely miatt az eszköz újraindítása után az Xbox-vezérlőket és Bluetooth LE-perifériákat újra párosítani kellett a csatlakozáshoz.
- Kijavítottuk a videókódolóval kapcsolatban azt a hibát, amely a kimenő videó rövid lefagyását okozhatta egy Remote Assist-hívás során. Wi-Fi illesztő- és belsővezérlőprogram-módosításokat a "töredék és a forge" biztonsági rések Wi-Fi érdekében.
- Wi-Fi illesztő- és belsővezérlőprogram-módosításokat a "töredék és a forge" biztonsági rések Wi-Fi érdekében.
- A platformátköltöztatási mód (MPM) használata esetén a "Down" rövid idő alatt a tömegátlag alapján lesz megbecsülve. Ez az érték váltja fel a valódi tömegvonzást a Mozgóplatform módban.
- 3DoF módban vagy követés elvesztése esetén a hologramok időszakos rövidítésének kijavítva.
- Kijavít egy problémát, amely hatással van a régebbi kiadások 21H1/21H2 kiadásának frissítésére.

## <a name="windows-holographic-version-20h2---october-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. októberi frissítés

- Build 19041.1168

A frissítés fejlesztései és javításai:

- Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb buildet, Windows Holographic 21H2-es verzióját.

## <a name="windows-holographic-version-21h1---september-2021-update"></a>Windows Holographic, 21H1-es verzió – 2021. szeptemberi frissítés

- Build 20348.1018

A frissítés fejlesztései és javításai:

- A probléma megoldásához szükséges javítások, amelyek miatt a rendszeridő váratlanul ugrik.

## <a name="windows-holographic-version-20h2---september-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. szeptemberi frissítés

- Build 19041.1165

A frissítés fejlesztései és javításai:

- A probléma megoldásához szükséges javítások, amelyek miatt a rendszeridő váratlanul ugrik.

## <a name="windows-holographic-version-21h1---august-2021-update"></a>Windows Holographic, 21H1-es verzió – 2021. augusztusi frissítés

- Build 20348.1014

A frissítés fejlesztései és javításai:

- Kijavítottunk egy hibát, amely miatt az Xbox-vezérlők nem működnek a vezérlőt támogató modern alkalmazásokban.
- Továbbfejlesztett diagnosztika az eszközfrissítési hibákhoz.

## <a name="windows-holographic-version-20h2---august-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. augusztusi frissítés

- Build 19041.1161

A frissítés fejlesztései és javításai:

- Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb buildet, Windows Holographic 21H1-es verzióját.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holographic, 21H1-es verzió – 2021. júliusi frissítés

- Build 20348.1010

A frissítés fejlesztései és javításai:

- Eszközportál továbbfejlesztett módszerekkel értesíti az ügyfelet, ha Fájlkezelő problémákba ütközik a zárolt fájlok megnyitásakor.
- A fájlfeltöltés, -letöltés, -átnevezés és -törlés mostantól ki van javítva, ha https-t használ minden támogatott böngészőben.
- Kijavítva a Wi-Fi hiba, amely miatt Wi-Fi proxy nem menthető, amikor Wi-Fi tulajdonságok felhasználói felülete a Gépház > Network & Internet > Status (Állapot) > **tulajdonságokból** indul.
- Elhárítottuk az eSIM-tanúsítványok operációsrendszer-frissítések közötti eltávolításával kapcsolatos problémát. Ez a javítás biztosítja, hogy a 21H1-es kiadásra való frissítéskor a rendszer eltávolítsa az eSIM-tanúsítványokat és a kapcsolódó összetevőket.
- Kijavítottunk egy problémát, amely hatással van az előre telepített alkalmazásokra az operációs rendszer alaphelyzetbe állításakor.
- Az akkumulátor töltöttségi teljesítménye úgy van behangolva, hogy növelje a futásidőt, ha nagyobb processzorterhelést használ. Ha 2 HoloLens tölt fel, és a rendszer azt észleli, hogy az eszköz melegen fut, a belső akkumulátor lassabban töltődik fel a hő csökkentése érdekében. A pozitív eredmény az, hogy az eszköz termikus problémák miatt kisebb valószínűséggel áll le, ennek pedig az a hatása, hogy az eszköz hosszabb ideig fut. Ha az eszköz fut, a díj nem változik.

> [!IMPORTANT]
> A [21H1-es](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)buildben egy már megoldott ismert probléma miatt, amely a Remote Assist-felhasználókat érinti, időlegesen szüneteltette a Windows Holographic 21H1-es verziójának frissítéseit. Emellett módosítottuk az alapértelmezett Advanced Recovery Companion (ARC) buildet a [Windows Holographic 20H2 – 2021.](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)júniusi frissítésére. Az ARC-build folytatja a 21H1 build megcélzását.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. júliusi frissítés

- Build 19041.1157

A frissítés fejlesztései és javításai:

- Eszközportál továbbfejlesztett módszerekkel értesíti az ügyfelet, ha Fájlkezelő problémákba ütközik a zárolt fájlok megnyitásakor.
- A fájlfeltöltés, -letöltés, -átnevezés és -törlés mostantól ki van javítva, ha https-t használ minden támogatott böngészőben.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, 21H1-es verzió – 2021. júniusi frissítés

- Build 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive munkahelyi vagy iskolai kameratekercs feltöltése

A HoloLens 2 Gépház-alkalmazás új funkciójával az ügyfelek automatikusan feltölthetnek vegyes valóságot tartalmazó fényképeket és videókat az eszköz Pictures > Camera Roll mappájába a megfelelő OneDrive for work vagy school mappába. Ez a funkció a [2. HoloLens-es](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) OneDrive-alkalmazás funkcióbeli hézagát teszi lehetővé, amely csak az ügyfél személyes Microsoft-fiók-fiókjába (és nem a munkahelyi vagy iskolai fiókjába) való automatikus kameratekercs-feltöltést támogatja.

**Működés**

- Látogasson **Gépház > System > Mixed Reality Camera webhelyre** a "Kamera feltöltése" engedélyezéséhez.
- Ennek a funkciónak  a Be állásba való beállításával az eszközön rögzített vegyes valóságú fényképek és videók automatikusan várólistára kerülnek, hogy feltölthetőek a OneDrive munkahelyi vagy iskolai fiókjának Pictures > Camera Roll mappájába.
    >[!NOTE]
    >A funkció engedélyezése előtt rögzített  fényképek és videók nem kerülnek a várakozási sorba a feltöltéshez, így manuálisan kell feltölteni őket.
- A Gépház lapon megjelenő állapotüzenet megjeleníti a függőben lévő fájlok számát (vagy olvassa el a "OneDrive naprakész" üzenetet, ha az összes függőben lévő fájl fel lett töltve).
- Ha a sávszélesség miatt aggódik, vagy bármilyen okból "szüneteltetni" szeretné  a feltöltést, a funkciót kikapcsolhatja. A funkció ideiglenes letiltása biztosítja, hogy a feltöltési várólista tovább nő, miközben új fájlokat ad hozzá a Camera Roll mappához, de a fájlok feltöltése addig nem folytatódik, amíg újra nem engedélyezi a funkciót.
- A rendszer először a legújabb fájlokat tölti fel (utolsóként, elsőként ki).
- Ha a OneDrive problémái vannak (például a jelszó módosítása után), megjelenik **a** Javítás most gomb a Gépház lapon.
- Nincs maximális fájlméret, de vegye figyelembe, hogy a nagy fájlok feltöltése hosszabb időt fog igénybe venni (különösen akkor, ha a feltöltési sávszélesség korlátozott). Ha egy nagy méretű fájl feltöltése közben szünetelteti vagy kikapcsolja a feltöltést, a részleges feltöltés megmarad. Ha a feltöltés a szüneteltetéstől vagy a kikapcsolástól számított néhány órán belül újra engedélyezve van, a feltöltés onnan folytatódik, ahonnan a feltöltést kikapcsolták. Ha azonban a feltöltés több óra után újra engedélyezve van, a nagy méretű fájl feltöltése az elejétől újraindul.

**Ismert problémák és kikötések**

- Ez a beállítás nem rendelkezik beépített szabályozással az aktuális sávszélesség-használat alapján. Ha a sávszélességet maximalizálni kell egy másik forgatókönyvhöz, kapcsolja ki manuálisan a beállítást. A feltöltés fel lesz függesztve, de a funkció továbbra is figyeli a Camera Roll újonnan hozzáadott fájljait. Engedélyezze újra a feltöltést, ha készen áll a folytatásra.
- Ezt a funkciót engedélyezni kell az eszközön lévő összes felhasználói fiókhoz, és csak az eszközre jelenleg bejelentkezett felhasználó fájljait tudja aktívan feltölteni.
- Ha valós időben készít fényképeket vagy videókat, miközben a Gépház-oldalon figyeli a feltöltések számát, vegye figyelembe, hogy a függőben lévő fájlok száma nem változik, amíg az aktuális fájl feltöltése be nem fejeződött.
- A feltöltés szünetel, ha az eszköz elalszik vagy ki van kapcsolva. Annak érdekében, hogy a függőben lévő feltöltések befejeződtek, aktívan használja az eszközt, amíg a Gépház-oldal el nem olvassa a "OneDrive naprakész" részt, vagy módosítsa a **Power & beállításait.**

### <a name="added-support-for-some-telemetry-policies"></a>Bizonyos telemetriai szabályzatok támogatása hozzáadva

A 2. HoloLens következő telemetriai szabályzatok támogatottak:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete (Letiltás letiltása)
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

A System\AllowTelemetry és a System\ConfigureTelemetryOptInSettingsUx együttes használatával teljes körűen vezérelni kell a telemetriát és a viselkedést az Gépház alkalmazásban.

A frissítés fejlesztései és javításai:

- Javítja a nagyobb videósérüléseket színezéssel.
- Kijavít egy problémát, amely miatt előfordulhat, hogy a Power menüben csonkolt egy szöveg.
- Engedélyezi a RequirePrivateStoreOnly szabályzat támogatását.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. júniusi frissítés

- Build 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>Bizonyos telemetriai szabályzatok támogatása hozzáadva

A 2. HoloLens következő telemetriai szabályzatok támogatottak:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete (Letiltás letiltása)
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

A System\AllowTelemetry és a System\ConfigureTelemetryOptInSettingsUx együttes használatával teljes körűen vezérelni kell a telemetriát és a viselkedést az Gépház alkalmazásban.

Javasoljuk, hogy próbálja ki a legújabb buildet, Windows Holographic 21H1-es verzióját.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. júniusi frissítés

- Build 18362.1116

A frissítés fejlesztései és javításai:

- Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb buildet, Windows Holographic 21H1-es verzióját.

>[!IMPORTANT]
> Ez a build a továbbiakban nem lesz szervizelt.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, 21H1-es verzió

- Build 20346.1002

Ez a frissítés két célcsoport funkcióit tartalmazza; a végfelhasználó által az eszközön bárki által használható funkciók, valamint a rendszergazdák által konfigurálható új eszközkezelési lehetőségek. Az alábbi táblázat az egyes célközönségek számára releváns funkciókat tartalmazza. Ha Ön rendszergazda, tekintse meg a rendszergazdai frissítési [ellenőrzőlistát.](#it-admin---update-checklist)
>[!IMPORTANT]
>A build frissítéséhez HoloLens 2 eszköznek jelenleg a 2021. februári frissítést (19041.1136-os build) vagy újabb verziónak kell futnia. Ha nem látja a funkciófrissítést, először frissítse az eszközt, és próbálkozzon újra.

>[!NOTE]
>Jelenleg a Microsoft HoloLens 2. verzió támogatja a havi karbantartási frissítéseket (hiba- és biztonsági javításokat) a következő kiadásokhoz:
>
>- Windows Holographic, 20H2-es verzió (Build 19041.1128+)
>- Windows Holographic, 2004-es verzió (Build 19041.1103+)
>- Windows Holographic, 1903-as verzió (18362-es vagy újabb build)
>
> A Holographic Windows 21H1 verziójának bevezetésével a **Holographic 1903 Windows** havi karbantartási frissítéseit Windows bevezetjük. Ez lehetővé teszi, hogy a legújabb kiadásokra összpontosítsunk, és továbbra is értékes fejlesztéseket biztosítsunk.

| Szolgáltatás neve                                              | Rövid leírás                                                                      | Célközönség |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Új Microsoft Edge](#introducing-the-new-microsoft-edge)  | Az új, Chromium-alapú Microsoft Edge a 2. HoloLens érhető el. | Végfelhasználó |
[WebXR és 360 Viewer](#webxr-and-360-viewer) | Próbálja ki a modern webes élményt és a 360 videólejátszást. | Végfelhasználó |
[Új Gépház alkalmazás](#new-settings-app) | A régi Gépház az alkalmazást egy frissített verzió váltja fel új funkciókkal és beállításokkal. | Végfelhasználó |
[Színkorrektálás megjelenítése](#display-color-calibration) | Válasszon egy alternatív színprofilt a HoloLens 2-es megjelenítéshez. | Végfelhasználó |
[Alapértelmezett alkalmazásválasztó](#default-app-picker) | Válassza ki, hogy melyik alkalmazást indítsa el az egyes fájl- vagy hivatkozástípusokkal. | Végfelhasználó |
[Alkalmazásonkénti kötetvezérlés](#per-app-volume-control) | Az alkalmazásszintű kötet szabályozása a rendszerkötettől függetlenül. | Végfelhasználó |
[Webalkalmazások telepítése](#install-web-apps) | Telepítse a webalkalmazásokat HoloLens 2. Microsoft Office, az új Microsoft Edge böngészővel. | Végfelhasználó |
[Pöccintéssel gépeléssel](#swipe-to-type) | Az ujjlenyomata hegyével "pöccintsen" szavakat a holografikus billentyűzeten. | Végfelhasználó |
[Power menu from Start](#power-menu-from-start) | A Start menüben indítsa újra és állítsa le HoloLens eszközt. | Végfelhasználó |
[Több felhasználó szerepel a Bejelentkezési képernyőn](#multiple-users-listed-on-sign-in-screen) | Több felhasználói fiók megjelenítése a Bejelentkezési képernyőn. | Végfelhasználó |
[USB-C külső mikrofon támogatása](#usb-c-external-microphone-support) | Használjon USB-C-mikrofonokat az alkalmazásokhoz és / vagy a Remote Assisthez. | Végfelhasználó |
[Látogatói automatikus bejelentkezés kioszkok számára](#visitor-auto-logon-for-kiosks) | Lehetővé teszi a látogatói fiókokra való automatikus bejelentkezést a kioszkmódokhoz. | Rendszergazdai |
[Új AUMID-k új alkalmazásokhoz Kioszk módban](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMID-ket Gépház Edge-alkalmazásokhoz. | Rendszergazdai |
[Továbbfejlesztett kioszkmódú hibák kezelésével](#kiosk-mode-behavior-changes-for-handling-of-failures) | A kioszkmód az üres Start menü előtt keres globális hozzárendelt hozzáférést. | Rendszergazdai |
[Új BeállításokURI-k az Gépház láthatósága számára](#new-settings-uris-for-page-settings-visibility) | Több mint 20 új SettingsURIs a Gépház/PageVisibilityList szabályzathoz. | Rendszergazdai |
[A Fallback Diagnostics konfigurálása](#configuring-fallback-diagnostics-via-settings-app) | Tartalék diagnosztikai viselkedés beállítása az Gépház alkalmazásban. | Rendszergazdai |
[Dolgok megosztása a közeli eszközökkel](#share-things-with-nearby-devices) | Fájlok vagy URL-címek megosztása egy HoloLens számítógépről. | Mind |
[Új operációsrendszer-diagnosztikai nyomkövetések](#new-os-diagnostic-traces) | Új hibaelhárító a Gépház az operációs rendszer frissítéséhez. | Rendszergazdai |
[Kézbesítésoptimalizálás előzetes verzió](#delivery-optimization-preview) | Csökkentse a sávszélesség-használatot több különböző eszközről HoloLens esetén. | Rendszergazdai |

Tekintse meg a kapcsolódó kibocsátási megjegyzéseket:

- [Látogasson el a HoloLens Emulator archívumba](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365-útmutatók](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Az új Microsoft Edge

![Az örökölt embléma Microsoft Edge új embléma Microsoft Edge animációja.](images/new-edge.gif)

Az új Microsoft Edge nyílt forráskódú [projektet Chromium,](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) hogy jobb kompatibilitást biztosítsunk az ügyfelek számára, és hogy a webfejlesztők kevesebb töredezettségben használják a webalkalmazásokat.

> [!IMPORTANT]
> Ez az Microsoft Edge automatikusan lecseréli az örökölt Microsoft Edge, [](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) amelyet az új kiadások már nem támogatnak.

![Új Microsoft Edge képernyőkép.](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Az új alkalmazás Microsoft Edge

Az új Microsoft Edge ![új Microsoft Edge ikon.](images/new_edge_logo.png) A (kék és zöld örlő ikon jelöli) a rendszer a Start menü a webes hivatkozás aktiválásakor automatikusan elindul.

> [!NOTE]
> Amikor a 2. Microsoft Edge elindítja az új HoloLens, a beállítások és az adatok importálva lesznek az örökölt Microsoft Edge. Ha az új Microsoft Edge elindítása után továbbra is az örökölt Microsoft Edge-t használja, az új adatok nem lesznek szinkronizálva az örökölt Microsoft Edge az új Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Szabályzatbeállítások konfigurálása az új Microsoft Edge

Az új Microsoft Edge a 2. HoloLens böngésző-szabályzatok sokkal szélesebb készletét kínálja a rendszergazdáknak, mint ami korábban az örökölt Microsoft Edge.

Az új szabályzatbeállítások kezelésével kapcsolatos további információkért íme néhány hasznos Microsoft Edge:

- [A Microsoft Edge beállításainak konfigurálása a Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Microsoft Edge régi verziója szabályzatleképezés Microsoft Edge beállítása](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [A Google Chrome Microsoft Edge szabályzatleképezéshez](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Teljes [Microsoft Edge Enterprise dokumentációja](/deployedge/)

> [!IMPORTANT]
> Az új szabályzatok által támogatott böngésző-szabályzatok Microsoft Edge miatt csapatunk nem tudja garantálni, hogy minden új szabályzat a 2. HoloLens működik. Azonban teszteltük és megerősítettük, mint az Microsoft Edge korábbi Microsoft Edge szabályzatok megfelelőinek megfelelő új HoloLens a vártnak megfelelően működnek. A [Microsoft Edge régi verziója](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) Microsoft Edge szabályzatleképezéssel kapcsolatos további Microsoft Edge a 2. alkalommal használt régi Microsoft Edge-szabályzatok új megfelelőjét HoloLens találja.
>
> Legalább két új szabályzat Microsoft Edge, amelyről tudjuk, hogy *a* 2. HoloLens nem fog működni:
>
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Mire számítsunk a 2. Microsoft Edge új HoloLens után?

Mivel az új Microsoft Edge egy natív Win32-alkalmazás, amely egy új UWP-adapterréteggel rendelkezik, amely lehetővé teszi, hogy csak UWP-eszközökön, például a HoloLens 2-n fusson, előfordulhat, hogy egyes funkciók nem érhetők el azonnal. A következő hónapokban új forgatókönyveket és funkciókat fogunk támogatni, ezért ebben a térben naprakész információkat is keres.

**Várható forgatókönyvek és funkciók:**

- Első futtatás, bejelentkezés a profilba és szinkronizálás
- A webhelyeknek a várt módon kell renderelve és viselkedniük
- A legtöbb böngészőfunkciónak (kedvencek, előzmények stb.) a várt módon kell működnie
- Sötét mód
- Webalkalmazások telepítése az eszközre
- Bővítmények telepítése (ha olyan bővítményeket használ, amelyek nem működnek megfelelően a 2. HoloLens)
- PDF megtekintése és megjelölése
- Térbeli hang egyetlen böngészőablakból
- A böngésző automatikus és manuális frissítése
- PDF mentése a Nyomtatás menüből (a "Mentés PDF-be" beállítással)
- WebXR és 360 Viewer bővítmény
- Tartalom visszaállítása a megfelelő ablakra, ha több, a környezetben elhelyezett ablakban böngész

**Nem várt forgatókönyvek és funkciók:**

- Térbeli hang több ablakból egyidejű hangstreamekkel
- "Lásd, mondja ki"
- Nyomtatás

**A böngészővel kapcsolatos legfontosabb ismert problémák:**

- A holografikus billentyűzet nagyító előnézete le van tiltva az új Microsoft Edge. Reméljük, hogy egy későbbi frissítésben újra elérhető lesz a funkció, amint a nagyítás megfelelően működik.
- Előfordulhat, hogy a hang lejátszása nem a megfelelő böngészőablakból történik, ha egy másik böngészőablak van megnyitva és aktív. A probléma megoldásához zárja be a másik aktív ablakot, amely nem hanganyagot kellene lejátszani.
- Ha ["Kövessen"](hololens2-basic-usage.md#follow-me-stop-following)módban egy böngészőablakból játszik le hangot, a "Követés" mód letiltása esetén a hang továbbra is lejátszásra kerül. A probléma megoldásához leállíthatja a hanglejátszást, mielőtt letiltja a "Kövessen" módot, vagy bezárhatja az **ablakot az X gombbal.**
- Az aktív ablakokkal Microsoft Edge előfordulhat, hogy más 2D-s alkalmazásablakok váratlanul inaktívvá válnak. Ezeket az ablakokat újraaktiválhatja, ha újra kapcsolatba lép velük.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Belső csatornák

A Microsoft Edge csapat három előzetes csatornát tesz elérhetővé az Edge Insider-közösség számára: Béta, Dev és Canary. Az előzetes verziójú csatorna telepítésével nem távolítja el a Microsoft Edge kiadott verzióját a HoloLens 2., és egyszerre több is telepíthető.

A [Microsoft Edge Insider kezdőlapján](https://www.microsoftedgeinsider.com) további információt talál az Edge Insider-közösségről. A különböző Edge Insider-csatornákkal kapcsolatos további információkért és az első lépésekért látogasson el az [Edge Insider letöltési oldalára.](https://www.microsoftedgeinsider.com/download)

Az Insider-csatornák több módon is Microsoft Edge a 2 HoloLens való telepítéséhez:

**Közvetlen telepítés az eszközön (jelenleg csak a nem támogatott eszközök számára érhető el)**

  1. A 2 HoloLens oldalon keresse fel az [Edge Insider letöltési oldalát.](https://www.microsoftedgeinsider.com/download)
  1. Válassza **a Download for HoloLens 2 gombot** a telepíteni kívánt Edge Insider-csatornához.
  1. Indítsa el a letöltött .msix fájlt az Edge letöltési üzenetsorból vagy az eszköz "Letöltések" mappájába (a Fájlkezelő).
  1. [Elindul az](app-deploy-app-installer.md) alkalmazástelepítő.
  1. Kattintson a **Telepítés gombra.**
  1. A sikeres telepítés után a Microsoft Edge Beta, a Dev vagy a Canary külön bejegyzésként Minden alkalmazás **a** Start menü.

**Telepítés számítógéppel Windows Eszközportál [(ehhez](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) engedélyezni kell a fejlesztői módot a 2. HoloLens)**

  1. A számítógépen látogasson el az [Edge Insider letöltési oldalára.](https://www.microsoftedgeinsider.com/download)
  1. Válassza a telepíteni kívánt Edge **Insider-csatorna** "Letöltés Windows 10" gombja melletti legördülő nyilat.
  1. Válassza **HoloLens 2.** lehetőséget a legördülő menüben.
  1. Mentse az .msix fájlt a számítógép "Letöltések" mappájába (vagy egy másik könnyen elérhető mappába).
  1. A [Windows Eszközportál](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) számítógépen való használatával telepítse a letöltött .msix fájlt a 2. HoloLens számítógépen.
  1. A sikeres telepítés után a Microsoft Edge Beta, a Dev vagy a Canary külön bejegyzésként Minden alkalmazás **a** Start menü.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>A WDAC használata az új Microsoft Edge

Ahhoz, hogy a rendszergazdák a [WDAC-szabályzatukat](windows-defender-application-control-wdac.md) frissítve blokkolják az új Microsoft Edge alkalmazást, a következőket kell hozzáadnia a szabályzathoz.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Végpontok kezelése az új Microsoft Edge

Egyes környezetek esetében figyelembe kell venni a hálózati korlátozásokat. Az új Edge zökkenőmentes felhasználói élményének biztosítása érdekében engedélyezze [ezeket a Microsoft-végpontokat.](/deployedge/microsoft-edge-security-endpoints)

További információ a jelenleg elérhető [végpontjairól a HoloLens.](hololens-offline.md)

### <a name="install-web-apps"></a>Webalkalmazások telepítése

 > [!Note]
>A [holografikus Windows 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1)verziójától a Office webalkalmazás már nem lesz előre telepítve.

Az új Edge használatával webalkalmazásokat telepíthet a Microsoft Store mellett. Például telepítheti a Microsoft Office webalkalmazást, hogy megtekintse és szerkessze a SharePoint vagy OneDrive. A webalkalmazás Office a címsorban található Alkalmazás elérhető vagy Office https://www.office.com telepítése gombot.   A **megerősítéshez válassza** a Telepítés lehetőséget.

> [!IMPORTANT]
> Office webalkalmazás funkció csak akkor érhető el, ha a HoloLens 2-es HoloLens rendelkezik aktív internetkapcsolattal.

### <a name="webxr-and-360-viewer"></a>WebXR és 360 Viewer

Az új Microsoft Edge támogatja a WebXR-t, amely a modern webes élmények létrehozásának új szabványa (a WebVR helyett). Számos magával ragadó webes élményt a VR szem előtt tartva terveztek (a látómezőt egy virtuális környezetre cserélik), de ezeket az élményeket a 2. HoloLens is támogatja. A WebXR szabvány kibővített és vegyes valóságú, magával ragadó webes élményt tesz lehetővé, amelyek a fizikai környezetet használják. Mivel a fejlesztők több időt töltenek a WebXR-sel, arra számítunk, hogy új, kibővített és vegyes valóságú élmények érkeznek majd, HoloLens 2 ügyfél kipróbálhatja!

A 360 Viewer bővítmény a WebXR-re épül, és automatikusan a 2. Microsoft Edge új HoloLens együtt telepíthető. Ez a webes bővítmény lehetővé teszi, hogy 360 fokos videókban merüljön el. A YouTube a 360 videó közül kínálja a legnagyobb választékot, ezért javasoljuk, hogy itt kezdje.

#### <a name="how-to-use-webxr"></a>A WebXR használata

1. WebXR-támogatással lépjen egy webhelyre.
1. Válassza az **Enter VR (VR beírása)** gombot a webhelyen. A gomb helye és vizuális megjelenítése webhelyenként eltérő lehet, de a következőre hasonlíthat:

    ![Példa a VR-gombra.](images/75px-enter-vr.png)

1. Amikor első alkalommal próbál webxr-élményt elindítani egy adott tartományon, a böngésző jóváhagyást kér a modern nézetbe való belépéshez, és kiválasztja az **Allow (Engedélyezése) lehetőséget.**
1. A [HoloLens 2 kézmozdulattal](hololens2-basic-usage.md#the-hand-tracking-frame) módosíthatja a felhasználói élményt.
1. Ha a felhasználói élmény  nem rendelkezik Kilépés gombbal, a Start kézmozdulattal [térhet](hololens2-basic-usage.md#start-gesture) vissza a kezdőlapra.

**Ajánlott WebXR-minták**

- 360 Viewer (lásd a következő szakaszt)
- [XR-ök](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR-Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>A 360 Viewer használata

1. Lépjen egy 360 fokos videóra a YouTube-on.
1. A videókeretben válassza a vegyes valóságú headset gombot:

    ![A 360 Viewer aktiválásához kattintson a gombra.](images/enter-360-viewer.jpg)

1. Amikor először próbálja elindítani a 360 Viewert egy adott tartományon, a böngésző beleegyezést kér a modern nézetbe való belépéshez. Válassza az **Allow (Engedélyezése) lehetőséget.**
1. [Légi koppintással](hololens2-basic-usage.md#select-using-air-tap) hozzuk fel a lejátszásvezérlőket. Használjon [kézi sugarakat](hololens2-basic-usage.md#select-using-air-tap) és légi koppintásokat a lejátszáshoz/szüneteltetéshez, a továbbítás/visszaugrás, a feliratok be- és kikapcsolása vagy a felhasználói élmény leállítása (ami kilép a modern nézetből). A lejátszásvezérlők néhány másodperc inaktivitás után eltűnnek.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>A WebXR és a 360 Viewer legfontosabb ismert problémái

- A WebXR-élmény összetettségétől függően a képkocka- és képkocka-méret csökkenhet vagy megakhat.
- A WebXR-hez a kézzel készített kéz támogatása alapértelmezés szerint nincs engedélyezve. A fejlesztők a `edge://flags` "WebXR Hand Input" bekapcsolásával engedélyezhetik a támogatást.
- Előfordulhat, hogy a YouTube-on kívül 360 videó nem a várt módon működik.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Visszajelzés küldése a WebXR-ről és a 360 Viewerről

Ossza meg a visszajelzéseket és  a hibákat a csapatunkkal az új rendszer Visszajelzés küldése Microsoft Edge.

### <a name="new-settings-app"></a>Új Gépház alkalmazás

Ebben a kiadásban a Gépház új verzióját vezetjük be. Az új Gépház-alkalmazás új funkciókat és kibővített beállításokat tartalmaz a HoloLens 2-hez a következő területeken: Hang, Power &-alvó, Network & Internet, Alkalmazások, Fiókok, Könnyű kezelés stb.

> [!NOTE]
> Mivel az új Gépház alkalmazás különbözik az örökölt Gépház-alkalmazástól, a Gépház környezetben korábban elhelyezett összes Gépház törlődik frissítéskor.

![Új Gépház alkalmazás kezdőlapja.](images/new-settings-app.png)

**Új funkciók és beállítások**

- Gépház keresés: a beállításokat a kezdőlapon Gépház kulcsszavak vagy a beállítás nevének használatával keresheti meg.
- System > Sound:
  - Hangbemeneti és -kimeneti eszközök: egymástól függetlenül válassza ki a bemeneti és kimeneti hangeszközöket (például egy hanganyagot Bluetooth hanganyagon keresztül, vagy használjon USB-C mikrofont a hangbemenethez).
    > [!NOTE]
    > Bluetooth mikrofonokat a 2. HoloLens támogatja.
  - Alkalmazáskötet: az egyes alkalmazások kötetének egymástól független beállítása. Lásd: [alkalmazáskötet-vezérlőnként.](#per-app-volume-control)
- A > Power &: válassza ki, hogy az eszköz mikor alvó üzemmódba ússzanak egy bizonyos tétlenség után.
- Akkumulátor >: manuálisan engedélyezze az takarékos üzemmód üzemmódot, vagy állítson be egy akkumulátor-küszöbértéket, amely takarékos üzemmód bekapcsolja az akkumulátort.
- USB> eszközök: alapértelmezés szerint letilthatja az USB-kapcsolatokat.
- Hálózati & internet:
  - Az USB-C Ethernet-adapterek mostantól megjelennek a Hálózati adapterek & interneten.
  - Az USB-C Ethernet-adapter beállításai már elérhetők, beleértve annak IP-címét is.
  - Mostantól a 2. HoloLens engedélyezheti a repülőgép üzemmódot.
- Alkalmazások: alaphelyzetbe állíthatja a fájl- és hivatkozástípusokhoz használt alapértelmezett alkalmazásokat. További információ: [Alapértelmezett alkalmazásválasztó.](#default-app-picker)
- Fiókok > felhasználók: az eszköztulajdonosok felhasználókat adhatnak hozzá, frissítheti az általános felhasználókat az eszköztulajdonosokra, visszaminősítheti az eszköztulajdonosokat normál felhasználókra, és eltávolíthat felhasználókat.
- Könnyű kezelés: szövegméret és néhány vizuális hatás módosítása.

**Ismert problémák**

- A korábban Gépház el lesznek távolítva (lásd a fenti megjegyzést).
- Többé nem nevezheti át az eszközt a Gépház alkalmazással. A rendszergazdák az [Windows Autopilot for HoloLens 2](hololens2-autopilot.md) eszköznév-sablon vagy az MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName csomópont használatával nevezheti át az eszközöket.
- Az Ethernet-oldalon mindig megjelenik egy virtuális Ethernet-eszköz ("UsbNcm").
- Előfordulhat, hogy az új Microsoft Edge akkumulátor-használata nem lesz pontos, mivel az UWP-adapterréteg által támogatott Win32 asztali alkalmazás (hamarosan nem várható javítás).

#### <a name="display-color-calibration"></a>Színkorrektálás megjelenítése

Ezzel az új beállítással alternatív színprofilt választhat a HoloLens 2-es megjelenítéshez. Ez segíthet a színek pontosabb megjelenítésében, különösen alacsonyabb megjelenítési fényerejénél. A színkorrektálás megjelenítése a Gépház a Rendszer és > lapon található.

> [!NOTE]
> Mivel ez a beállítás egy új színprofilt ment a megjelenítési belső vezérlőprogramba, ez egy eszközönkénti beállítás (és nem egyedi az egyes felhasználói fiókok számára).

##### <a name="how-to-use-display-color-calibration"></a>A kijelző színkorrektálásának használata

1. Indítsa el **a Gépház** alkalmazást, és **navigáljon a System > (Rendszer- és >) lapra.**
1. A **Színkorrektálás megjelenítése alatt** válassza a Megjelenítés **színkorrektálásának futtatása** gombot.
1. Elindul a színekkel való megjelenítés élménye, és arra bátorítja, hogy a vizor a megfelelő helyen legyen.
1. Az utasítási párbeszédpanelek megnyitása után a kijelző automatikusan 30%-os fényerejére halványul.
    > [!TIP]
    > Ha nem látja a halvány jeleneteket a környezetében, manuálisan módosíthatja HoloLens 2-es fényerejét az eszköz bal oldalán található fényerejét jelző gombokkal.
1. Válassza az 1–6. gombot, hogy azonnal kipróbálja az egyes színprofilokat, és keresse meg azt, amely a leginkább hasonlít a szemére (ez általában azt jelenti, hogy a jelenetnek leginkább megfelelő profil jelenik meg a legsemlegesebbnek, a szürkeárnyalatos mintázattal és a vékony tonének pedig a várt módon kell megjelennie.)

    ![Színjelenet megjelenítése.](images/color-cal-ui.png)

1. Ha elégedett a kiválasztott profillal, válassza a **Mentés & Kilépés gombot**
1. Ha nem szeretne módosításokat tenni, válassza a Mégse & **Kilépés** gombot, és a módosítások visszaállnak

> [!TIP]
> A megjelenítési színbeállítás használata során az alábbi tippeket kell szem előtt tartania:
>
> - A megjelenítési színek színkorrektálását bármikor újra Gépház, amikor csak szeretné
> - Ha az eszközön bárki korábban már használta a színprofilok beállítását, a legutóbbi módosítás dátuma/időpontja megjelenik a Gépház oldalon
> - A megjelenítési színek színkorrektálásának újrafuttatásakor a korábban mentett színprofil ki lesz emelve, és a 0. profil nem jelenik meg (mivel a 0. profil a megjelenítés eredeti színprofilját jelöli)
> - Ha vissza szeretne állítani a megjelenítés eredeti színprofiljára, ezt a Gépház oldalon (lásd: a színprofil [alaphelyzetbe állítása)](#how-to-reset-color-profile)

##### <a name="how-to-reset-color-profile"></a>Színprofil alaphelyzetbe állítása

Ha nem elégedett a 2. HoloLens egyéni színprofillal, visszaállíthatja az eszköz eredeti színprofilját:

1. Indítsa el **a Gépház** alkalmazást, és **navigáljon a System > (Rendszer- és >) lapra.**
1. A **Színkorrektálás megjelenítése alatt** válassza a Visszaállítás alapértelmezett **színprofilra gombot.**
1. Amikor megnyílik a  párbeszédpanel, válassza az Újraindítás lehetőséget, ha készen áll a 2. HoloLens újraindítására, és alkalmazza a módosításokat.

#### <a name="top-display-color-calibration-known-issues"></a>A legjobb megjelenítési színekkel kapcsolatos ismert problémák

- A Gépház az állapotsring, amely a színprofil legutóbbi módosulásának időpontját jelzi, elavult, amíg újra be nem Gépház.
    - Megkerülő megoldás: Válasszon ki egy Gépház, majd válassza újra a Hiba lapot.

#### <a name="default-app-picker"></a>Alapértelmezett alkalmazásválasztó

Amikor aktivál egy hivatkozást, vagy egynél több telepített alkalmazást tartalmazó fájltípust nyit meg, egy új ablak nyílik meg, amely felszólítja, hogy válassza ki, melyik telepített alkalmazás kezelje a fájl- vagy hivatkozástípust. Ebben az ablakban azt is kiválaszthatja, hogy a kiválasztott alkalmazás kezelje-e az "Egyszer" vagy "Mindig" típusú fájlt vagy hivatkozástípust.

Ha az "Always" (Mindig) lehetőséget választja, de később módosítani szeretné, hogy melyik alkalmazás kezeljen egy adott fájlt vagy hivatkozástípust, visszaállíthatja a mentett alapértelmezett beállításokat a **Gépház > alkalmazásokban.** Görgessen az oldal aljára, és válassza a Clear (Ürítés) gombot a "Default apps for file types" (Alapértelmezett alkalmazások fájltípusokhoz) és/vagy "Default apps for link types" (Alapértelmezett alkalmazások hivatkozástípusokhoz) alatt.  Az asztali számítógépek hasonló beállításától eltérően az egyes alapértelmezett fájltípusokat nem lehet alaphelyzetbe állítani.

#### <a name="per-app-volume-control"></a>Alkalmazásonkénti kötetvezérlés

Ebben a Windows buildben a felhasználók manuálisan módosíthatja az egyes alkalmazások kötetszintjeiket. Így a felhasználók jobban azokra az alkalmazásokra koncentrálnak, amelyekre szükségük van, vagy jobban hallanak több alkalmazás használata esetén. Ilyen lehet például, ha le kell kapcsolni egy alkalmazás mennyiségét, miközben egy másik személy távsegítségért egy másik személy segítségét hívja egy másikban.

Egy adott alkalmazás kötetének beállításhoz lépjen a **Gépház** System Sound elemre, majd a Speciális hangbeállítások alatt válassza az Alkalmazáskötet és az  >    >   **eszközbeállítások lehetőséget.**<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Pöccintéssel gépeléssel

Egyes ügyfelek gyorsabban "gépelnek" a virtuális billentyűzeten a begépelni kívánt szó alakjának megformálása által, és ezt a funkciót a holografikus billentyűzet előzetes verziójaként használjuk. Pöccintsen egyszerre egy szót úgy, hogy a holografikus billentyűzet síkján végiglépteti az ujjlenyomata hegyét, elforgatja a szó alakját, majd a billentyűzetsíkról megfedi az ujjlenyomata hegyét. Pöccintéssel anélkül pöccinthet a szavak után, hogy le kellene nyomni a szóközt, ha a szavak között eltávolítja az ujját a billentyűzetről. A funkció akkor működik, ha pöccintéssel követi az ujját a billentyűzeten.

Vegye figyelembe, hogy ez a funkció a holografikus billentyűzet természetéből adódóan nem mindig tud az ujjlenyomatával szembeni ellenállást használni és elsajátítani (ellentétben a mobiltelefonos kijelzővel). 

### <a name="power-menu-from-start"></a>Power menu from Start

Új menü, amely lehetővé teszi, hogy a felhasználó kijelentkeztetje, leállítsa és újraindítsa az eszközt. A rendszerfrissítés HoloLens kezdőképernyő mutatója.

#### <a name="how-to-use"></a>Használat

1. Nyissa meg HoloLens kezdőképernyő a [Start kézmozdulattal,](hololens2-basic-usage.md#start-gesture) vagy mondja ki a "Go to Start" (Ugrás az indításhoz) gombra.

2. Figyelje meg a felhasználói profil képe melletti három pont ikont (...):<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Válassza ki a felhasználói profil képét a saját kezűleg vagy a "Power" hangparancs használatával.

4. Megjelenik egy menü, amely az eszköz kijelentkeztető, újraindítható vagy leállítható beállításait is tartalmaz:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Válassza ki a menüelemet a regisztrációhoz, az újraindításhoz vagy a HoloLens. Előfordulhat, hogy a Kijelentkezás lehetőség nem érhető el, ha az eszköz egyetlen [Microsoft-fiókhoz (MSA)](hololens-identity.md)vagy helyi fiókhoz van beállítva.

6. Zárja be a menüt máshová való érintéssel, Start menü a Start kézmozdulattal.

#### <a name="update-indicator"></a>Frissítésjelző

Amikor elérhetővé válik egy frissítés, a három pont ikon kigyűjt, jelezve, hogy az újraindítás telepíti a frissítést. A menü beállításai is megváltoznak, hogy tükrözzék a frissítés jelenlétét.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Több felhasználó szerepel a Bejelentkezési képernyőn

Korábban a Bejelentkezés képernyőn csak a legutóbb bejelentkezett felhasználó, valamint az "Egyéb felhasználó" belépési pont jelent meg. Ügyfeleink visszajelzést kaptak arról, hogy ez nem elegendő, ha több felhasználó jelentkezett be az eszközre. Így is újra kellett beírniuk a felhasználónevüket stb.

Az ebben a Windows buildben  bemutatott Más felhasználó lehetőség kiválasztásakor, amely a PIN-kód beviteli mezőtől jobbra található, a Bejelentkezés képernyőn több felhasználó jelenik meg, akik korábban bejelentkeztek az eszközre. Így a felhasználók kiválaszthatják a felhasználói profiljukat, majd a saját hitelesítő Windows Hello bejelentkeznek. A Fiók hozzáadása gombbal új felhasználó is hozzáadható az eszközhöz az Egyéb felhasználók **lapon.**

Az Egyéb felhasználók menü Egyéb felhasználók gombja megjeleníti az eszközre legutóbb bejelentkezett felhasználót. Válassza ezt a gombot a felhasználó bejelentkezési képernyőjére való visszatéréshez.

![A bejelentkezési képernyő alapértelmezés szerint.](./images/multiusers1.jpg)

<br>

![Bejelentkezési képernyő – más felhasználók.](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C külső mikrofon támogatása

> [!IMPORTANT]
> Az USB-mikrofon csatlakoztatása nem lesz automatikusan beállítva **bemeneti eszközként.** Az USB-C-kábeleket csatlakoztatva a felhasználók azt fogják látni, hogy a hanganyag automatikusan a mikrofonhoz lesz átirányítva, de a HoloLens operációs rendszer a belső mikrofontömböt a többi bemeneti eszköz fölé rangsorítja. **USB-C mikrofon használata érdekében kövesse az alábbi lépéseket.**

A felhasználók a Hangbeállítások panelen választhatnak USB-C-hez csatlakoztatott külső **mikrofonokat.** Az USB-C-mikrofonok hívásra, felvételre stb. használhatók.

Nyissa meg **a Gépház** alkalmazást, és válassza a **System**  >  **Sound lehetőséget.**

![Hang Gépház.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Ha külső mikrofonokat használ a **Remote Assist** segítségével, a felhasználóknak a "Hangeszközök kezelése" hivatkozásra kell kattintanunk.
>
> Ezután a legördülő menüben állítsa a  külső mikrofont Alapértelmezett vagy **Kommunikációs alapértelmezettre.** Az **Alapértelmezett beállítás** azt jelenti, hogy a külső mikrofon mindenhol használatban lesz.
>
> A **Kommunikáció alapértelmezett beállítása** azt jelenti, hogy a külső mikrofon a Remote Assist és más kommunikációs alkalmazásokban lesz használva, de a HoloLens mic tömb továbbra is használható más feladatokhoz.

![Hangeszközök kezelése.](images/usbc-mic-2.png)

<br>

![Mikrofon alapértelmezett beállítása.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Mi a helyzet a Bluetooth támogatással?

Sajnos Bluetooth a mikrofonok jelenleg nem támogatottak a 2. HoloLens esetén.

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C mikrofonok hibaelhárítása

Vegye figyelembe, hogy egyes USB-C-mikrofonok helytelenül, mikrofonként és *beszélőként is* jelentik magukat. Ez a mikrofonnal, és nem a HoloLens. Ha ezen mikrofonok valamelyikét csatlakoztatja HoloLens, előfordulhat, hogy a hang elveszett. Szerencsére van egy egyszerű javítás.  

A **Gépház** System Soundban explicit módon állítsa be a beépített beszélők  >    >   **(Analog Feature Audio Driver)** alapértelmezett eszközként való **beállítását.** HoloLens akkor is meg kell jegyezni ezt a beállítást, ha a mikrofont eltávolítják, majd később újracsatlakoztatják.

![USB-C mikrofonok hibaelhárítása.](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Látogatói automatikus bejelentkezés kioszkok számára

Ez az új funkció lehetővé teszi, hogy a látogatói fiókokba való automatikus bejelentkezés kioszkmódban is használható legyen.

A nem AAD konfigurálja az eszközt a látogatói automatikus bejelentkezéshez:

1. Hozzon létre egy kiépítési csomagot, amely:
    1. Úgy **konfigurálja a Futásidejű beállításokat/AssignedAccess-t,** hogy engedélyezze a látogatói fiókokat.
    1. Ha szükséges, regisztrálja az eszközt az MDM-be (Futásidejű **beállítások/Munkahely/Regisztrációk),** hogy később kezelhető legyen.
    1. Ne hozzon létre helyi fiókot
1. [Alkalmazza a kiépítési csomagot.](hololens-provisioning.md)

A AAD konfigurációja esetén a felhasználók a maihoz hasonlót érhetnek el a módosítás nélkül. AAD kioszkmódra konfigurált, beléptethet egy látogatói fiókot egyetlen gombkoppintással a bejelentkezési képernyőről. Miután bejelentkezett a látogatói fiókba, az eszköz nem kéri újra a bejelentkezést, amíg a Látogató kijelentkezik a Start menüből, vagy újra nem indítják az eszközt.

A látogatói automatikus bejelentkezés egyéni [OMA-URI szabályzat segítségével](/mem/intune/configuration/custom-settings-windows-10) kezelhető:

- URI-érték: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Szabályzat  | Description   | Konfigurációk  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Lehetővé teszi a látogatónak a kioszkba való automatikus bejelentkezést   | 1 (Igen), 0 (Nem, alapértelmezés.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Az új Gépház Edge-alkalmazások használata kioszkmódban

Amikor alkalmazásokat ad hozzá [a kioszkhoz,](hololens-kiosk.md)a rendszergazda gyakran hozzáadja az alkalmazást a kioszkhoz, de az alkalmazásfelhasználói modell azonosítóját (AUMID) használja. Mivel az Gépház-alkalmazást és az Microsoft Edge-alkalmazást is új alkalmazásnak tekintjük, és eltérnek a régebbi alkalmazásoktól, az alkalmazásokhoz AUMID-t használni képes kioszkokat frissíteni kell az új AUMID-hoz.

Ha úgy módosít egy kioszkot, hogy az tartalmazza az új alkalmazásokat, javasoljuk, hogy adja hozzá az új AUMID-t, és hagyja meg a régit. Ez egyszerű átállást fog létrehozni, amikor a felhasználók frissítik az operációs rendszert, és nem kell új szabályzatokat kapniuk a kioszk megfelelő használatának érdekében.

| Alkalmazás                    | AUMID (AUMID)                                                  |
|------------------------|--------------------------------------------------------|
| Régi Gépház alkalmazás       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Új Gépház alkalmazás       | BAEAEF15-9CAF-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Régi Microsoft Edge alkalmazás | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Új Microsoft Edge alkalmazás | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>A kioszkmód viselkedésének változásai a hibák kezelésével

A régebbi buildek esetén, ha egy eszköz kioszkkonfigurációval rendelkezik, amely AAD globális hozzáférés és AAD csoporttagok hozzárendelt hozzáférésének kombinációja, és AAD csoporttagság meghatározása sikertelen volt, a felhasználó a["Start](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)menüben semmi sem jelenik meg" jelenik meg.

A jelen Windows kiadástól kezdődően a teljes kioszkmód vissza fog állni a globális kioszkkonfigurációhoz (ha van ilyen) a csoportszintű kioszkmódban AAD hibák esetén.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Új Gépház URI-k a lap Gépház számára

A [Windows Holographic 20H2-es](hololens-release-notes.md#windows-holographic-version-20h2) verziójában hozzáadtunk egy [Gépház/PageVisibilityList szabályzatot,](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) amely korlátozza a Gépház alkalmazásban látható oldalakat. A PageVisibilityList egy olyan szabályzat, amely lehetővé teszi a rendszergazdák számára, hogy megakadályozzák a System Gépház alkalmazás adott lapjainak láthatóságát vagy akadálymentességét, vagy a megadottak kivételével minden oldal esetén ezt teszik.

Ha felkeresi [a Page Gépház Visibility](settings-uri-list.md)oldalt, útmutatást talál a CSP használatára és a korábbi kiadásokban elérhető URI-k listájára.

Bővítjük az elérhető URI-k Gépház listáját, amelyeket a rendszergazdák kezelnek. Ezen URI-k némelyike az új alkalmazás újonnan elérhető Gépház területeket. Ha a Gépház/PageVisibilityList szabályzatot használja, tekintse át az alábbi listát, és szükség szerint módosítsa az engedélyezett vagy letiltott oldalakat.

> [!NOTE]
> **Elavult: ms-settings:network-proxy**
>
> Ezekben az újabb buildekben az egyik beállítási oldal elavult. A régi **Hálózati & internetproxy** lap már nem érhető el  >   globális beállításként. Az új kapcsolatonkénti proxybeállítások az Internet  >  **Wi-Fi&** tulajdonságai vagy az Internet Ethernet& tulajdonságai alatt  >     >    >  **találhatók.**

<br>

| Beállítások lap                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Alkalmazások > Alkalmazások & funkciói                               | `ms-settings:appsfeatures`                         |
| Alkalmazások > Alkalmazások & funkciók és > speciális beállítások          | `ms-settings:appsfeatures-app`                     |
| Offline > alkalmazások                                  | `ms-settings:maps`                                 |
| Offline > alkalmazások és > térképek letöltése                  | `ms-settings:maps-downloadmaps`                    |
| Eszközök > egérrel                                      | `ms-settings:mouse`                                |
| USB> eszközök                                        | `ms-settings:usb`                                  |
| Hálózati & internetes > repülőgép üzemmódban                   | `ms-settings:network-airplanemode`                 |
| Adatvédelmi > általános                                    | `ms-settings:privacy-general`                      |
| Adatvédelem > ink & személyre szabás beírásával             | `ms-settings:privacy-speechtyping`                 |
| Adatvédelmi > Motion                                     | `ms-settings:privacy-motion`                       |
| Adatvédelmi > Képernyőkép a szegélyekről                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Adatvédelmi > képernyőképek és alkalmazások                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Rendszer > akkumulátor                                     | `ms-settings:batterysaver`                         |
| Rendszer > akkumulátor                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| System > Sound > App volume and device preferences (Alkalmazáskötet és eszközbeállítások) | `ms-settings:apps-volume`                          |
| System > Sound > Hangeszközök kezelése              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Idő & Language > dátum és & időpont                        | `ms-settings:dateandtime`                          |
| Time & Language > Billentyűzet                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| A & biztonsági > visszaállítás & frissítése               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Frissített URI-k

Korábban a következő két URI nem adná meg a felhasználót közvetlenül a megadott oldalakon, csak blokkolta volna a fő frissítésoldalt. A következő elemek úgy frissültek, hogy közvetlenül a saját oldalukra irányulnak:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Tartalék diagnosztika konfigurálása Gépház alkalmazáson keresztül

A Gépház alkalmazásban a felhasználó konfigurálhatja a [Fallback Diagnostics viselkedését.](hololens-diagnostic-logs.md) A beállítás Gépház alkalmazás Adatvédelmi hibaelhárítás lapjára  >   navigálva konfigurálhatja ezt a beállítást.

> [!NOTE]
> Ha az eszközhöz MDM-szabályzat van konfigurálva, a felhasználó nem tudja felülbírálni ezt a viselkedést.  

### <a name="share-things-with-nearby-devices"></a>Dolgok megosztása a közeli eszközökkel

Megoszthatja a dolgokat a Windows 10 eszközökkel, beleértve a számítógépeket és HoloLens 2 eszközt is. Kipróbálhatja a Gépház megosztott élményekben, hogy fájlokat vagy URL-címeket ossunk meg egy HoloLens  >    >   számítógéppel. További részletekért olvassa el, hogyan oszthat meg dolgokat a közeli eszközökkel a [Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

Ez a szolgáltatás a [Connectivity/AllowConnectedDevices használatával kezelhető.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Új operációsrendszer-diagnosztikai nyomkövetések

A Gépház alkalmazás korábbi hibaelhárítói mellett egy új hibaelhárítót is hozzáadtunk az új operációsrendszer-frissítésekhez Gépház alkalmazással. Lépjen az **Update** Security Gépház troubleshoot Windows Update (Frissítés  >  **&amp;**  >    >  **frissítése) lapra, és** válassza az Indítás **lehetőséget.** Ez lehetővé teszi a nyomkövetések gyűjtését az operációsrendszer-frissítésekkel kapcsolatos probléma reprodukálása során, hogy az it-it és a támogatással kapcsolatos hibaelhárítást támaszon ki.

### <a name="delivery-optimization-preview"></a>Kézbesítésoptimalizálás előzetes verzió

Ezzel a HoloLens frissítéssel a Windows Holographic for Business lehetővé teszi a kézbesítésoptimalizálási beállításokat, hogy csökkentse a sávszélesség-felhasználást több HoloLens eszközről való letöltések esetén. Ennek a funkciónak és az ajánlott hálózati konfigurációnak a teljes leírását itt érhetők el: Kézbesítésoptimalizálás [a Windows 10 frissítéséhez.](/windows/deployment/update/waas-delivery-optimization)

Az alábbi beállítások a felügyeleti felület részeként vannak engedélyezve, [és az Intune-ból konfigurálhatóak:](/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Az előzetes verzióval kapcsolatos néhány figyelmeztetés:

- HoloLens előzetes verzió csak az operációs rendszer frissítéseit támogatja.
- Windows Holographic for Business a HTTP-letöltési módokat és a Microsoft-végpontról [való Csatlakoztatott gyorsítótár letöltéseket támogatja;](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) A társközi letöltési módok és csoport-hozzárendelések jelenleg nem támogatottak HoloLens eszközök esetében.
- HoloLens nem támogatja az üzembe helyezést vagy a kézbesítés optimalizálását Windows Server Update Services végpontok esetén.
- A hibaelhárításhoz diagnosztikára van szükség a Csatlakoztatott gyorsítótár-kiszolgálón, vagy nyomkövetést kell gyűjteni a HoloLens-on HoloLens Gépház Update & Security Troubleshooting Windows Update (Frissítés Windows  >    >     >   **frissítésével) keresztül.**

### <a name="it-admin---update-checklist"></a>Rendszergazda – Frissítési ellenőrzőlista

Ez az ellenőrzőlista segít az ebben a funkciófrissítésben hozzáadott új elemekről, amelyek hatással lehetnek az aktuális eszközkezelési konfigurációkra, vagy olyan új funkciókra, amelyek használatba lesznek adva.

#### <a name="updates-to-kiosk-mode"></a>A Kioszkmód frissítései

✔️ Új [**AUMID-k új alkalmazásokhoz kioszkmódban:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Ha korábban az Gépház alkalmazást vagy egy Microsoft Edge-alkalmazást használt egy kioszkban, ezeket az alkalmazásokat más alkalmazásazonosítót használó új alkalmazásokra cseréljük. Javasoljuk, hogy olvassa el alább az [Új AUMID-k új alkalmazásokhoz Kioszk módban cikkeket.](#use-the-new-settings-and-edge-apps-in-kiosk-modes) Ezzel biztosíthatja, hogy továbbra is a teljes Gépház legyen a Kioszkban, vagy tartalmazza az új Microsoft Edge alkalmazást. Ezeket a módosításokat már most is végre lehet tenni, és az összes eszközön üzembe lehet helyezni, és zökkenőmentesebb frissítésváltást lehetővé tenni.

✔️ látogatói automatikus bejelentkezés [**kioszkok számára:**](#visitor-auto-logon-for-kiosks)

A látogatók mostantól automatikusan bejelentkeztetheti őket egy kioszkba. Ez a viselkedés alapértelmezés szerint be van kapcsolva, de kezelhető és letiltható.

✔️ [**kioszkmód továbbfejlesztett sikertelen leosztása:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Ha AAD bejelentkezett AAD felhasználó csoporttagságának meghatározása nem sikerült, akkor a rendszer a globális kioszkkonfigurációt használja a Start menüben (ha van), ellenkező esetben a felhasználó üres Start menüt kap. Bár az üres Start menü nem közvetlenül beállítható konfiguráció, ez az új kezelés segíthet tájékoztatni a támogatási osztályt arról, hogy kioszkokat használ-e, mivel ez a konfigurációkra is vonatkozhat, vagy lehet, hogy új módosításokat szeretne végezni a hozzárendelt hozzáférési konfigurációkon.

#### <a name="updates-to-page-settings-visibility"></a>Oldaloldal-Gépház frissítései

✔️ [**lap Gépház új URI-i Gépház láthatósága**](#new-settings-uris-for-page-settings-visibility)

Ha jelenleg oldaloldali Gépház [használ,](settings-uri-list.md) akkor előfordulhat, hogy módosításokat szeretne végezni a meglévő URI-kban, amelyek engedélyezettek vagy blokkolva vannak.

#### <a name="updates-for-your-wdac-policy"></a>A WDAC-szabályzat frissítései

✔️ Ha korábban a WDAC Microsoft Edge blokkolta a forgalmat, frissítenie kell a WDAC-szabályzatot. Tekintse át az alábbiakat, és használja a megadott mintakódot.

#### <a name="enable-new-endpoints-for-edge"></a>Új végpontok engedélyezése az Edge-hez

✔️ Ha olyan infrastruktúrával rendelkezik, amely magában foglalja a hálózati végpontok, például a proxy vagy a tűzfal konfigurálását, engedélyezze ezeket az új végpontokat az új Microsoft Edge számára.

#### <a name="newly-configurable-items"></a>Újonnan konfigurálható elemek

✔️ Configure [Fallback Diagnostics](#configuring-fallback-diagnostics-via-settings-app)(Tartalék diagnosztika konfigurálása): Beállíthatja, hogy a rendszer összegyűjtse-e a tartalék diagnosztikát, és ki gyűjtheti be.

✔️ Megosztás[a közeli eszközökkel:](#share-things-with-nearby-devices)Letilthatja az új közeli megosztási funkciót.

✔️ [Configuring policy settings for the new Microsoft Edge:](#configuring-policy-settings-for-the-new-microsoft-edge)Review the newly configurations available for Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Új diagnosztikai eszköz

✔️ Új[operációsrendszer-diagnosztikai nyomkövetés:](#new-os-diagnostic-traces)Az operációs rendszer frissítésével kapcsolatos naplók gyűjtése.

### <a name="improvements-and-fixes-in-the-update"></a>A frissítés fejlesztései és javításai:

- [Az offline diagnosztika](hololens-diagnostic-logs.md#offline-diagnostics) a sorozatszámmal és az operációs rendszer verziójával kapcsolatos további eszközinformációkat is tartalmaz.
- Kijavítja az üzletági alkalmazások futásidejű kiépítési csomagokon keresztüli üzembe helyezéssel kapcsolatos problémákat.
- Kijavítja az üzletági alkalmazások telepítési állapotjelentési szolgáltatásával kapcsolatos problémát.
- Kijavít egy problémát, amely az új alkalmazáscsomagok eszköz-visszaállítások közötti megőrzésével kapcsolatban áll fenn.
- Kijavít egy problémát, amely miatt helytelen szimbólumok írhatóak be az Edge-be japán ügyfelek számára.
- Javítja az operációs rendszer frissítéseinek rugalmasságát az előre telepített alkalmazások, például az Edge körül.
- A frissítés megbízhatóságát kijavítja, amely hatással van a Microsoft Edge.

## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. májusi frissítés

- Build 19041.1146

A frissítés fejlesztései és javításai:

- Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb buildet, Windows Holographic 21H1-es verzióját.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. májusi frissítés

- Build 18362.1110

A frissítés fejlesztései és javításai:

- Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. **Ez a build többé nem kap havi szolgáltatásfrissítéseket.** Javasoljuk, hogy próbálja ki a legújabb buildet, Windows Holographic 21H1-es verzióját.

## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. áprilisi frissítés

- Build 19041.1144

A frissítés fejlesztései és javításai:

- Kijavítja az üzletági alkalmazások telepítési állapotjelentési szolgáltatásával kapcsolatos problémát.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. áprilisi frissítés

- Build 18362.1108

A frissítés fejlesztései és javításai:

- Kijavít egy problémát, Gépház alkalmazás összeomlik, amikor megpróbálja módosítani egy helyi fiók jelszavát.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. márciusi frissítés

- Build 19041.1140

A frissítés fejlesztései és javításai:

- Azok az ügyfelek, akik az AdvancedPhotoCapture vagy a LowLagPhotoCapture használatával készítettek fényképeket HoloLens 2-es használatával, a fénykép rögzítése után legfeljebb 3 másodperccel lekérik a kamera képét.
- A Eszközportál szolgáltatás memóriavesztésének kijavítása. Ez a probléma megnövekedett memóriahasználatot okozott a szolgáltatásban, amely miatt más alkalmazások nem foglalták le a memóriát.
- Kijavítottunk egy hibát, amely miatt a szakaszos bevezetésben regisztrált felhasználók nem tudnak bejelentkezni az eszközre.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. márciusi frissítés

- Build 18362.1102

A frissítés fejlesztései és javításai:

- A Eszközportál szolgáltatás memóriavesztésének kijavítása. Ez a probléma megnövekedett memóriahasználatot okozott a szolgáltatásban, amely miatt más alkalmazások nem foglalták le a memóriát.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. februári frissítés

- Build 19041.1136

A frissítés fejlesztései és javításai:

- Kijavít egy problémát az eszköz kezdeti beállításához és az alkalmazásfrissítések tárolására.
- Elhárítja a későbbi kiadások frissítésével és járatokkal HoloLens problémát.
- Eltávolította a nem használt előre telepített tanúsítványokat az eSIM gyökértárolóból a HoloLens eszközökről.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. februári frissítés

- Build 18362.1098

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb buildeket a Windows Holographic 2004-es verziójához.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. januári frissítés

- Build 19041.1134

A frissítés fejlesztései és javításai:

- Jobb teljesítmény indítás, folytatás és felhasználóváltás során, ha sok felhasználó van az eszközön.
- Arm32-támogatás hozzáadva a [Research Mode-hez.](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. januári frissítés

- Build 18362.1091

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb buildeket a Windows Holographic 2004-es verziójához.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, 20H2-es verzió – 2020. decemberi frissítés

- Build 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Alkalmazások telepítése a 2. HoloLens a Alkalmazástelepítő

Egy új **funkcióval (Alkalmazástelepítő)** bővítjük az alkalmazások zökkenőmentesebb telepítését a HoloLens 2 eszközön. A szolgáltatás alapértelmezés szerint be lesz kapcsolva a nem nem **engedélyezett eszközökön.** A vállalatok kimaradásának elkerülése érdekében az alkalmazástelepítő jelenleg nem lesz elérhető **a felügyelt** eszközökhöz.  

Az eszközök akkor minősülnek  "felügyeltnek", ha az alábbiak bármelyike igaz:

- MDM [regisztrálva](hololens-enroll-mdm.md)
- Kiépítési [csomaggal konfigurálva](hololens-provisioning.md)
- A felhasználói [identitás](hololens-identity.md) az Azure AD

Most már anélkül telepítheti az alkalmazásokat, hogy engedélyeznie kellene a fejlesztői módot, vagy engedélyeznie kellene a Eszközportál.  Egyszerűen töltse le (USB-n vagy peremhálózaton keresztül) az Appx-csomagot az eszközre, és navigáljon az Appx-csomaghoz a Fájlkezelő, hogy a rendszer a telepítést elindító kérést kapjon.  Másik lehetőségként [kezdeményezzen telepítést a weblapról.](/windows/msix/app-installer/installing-windows10-apps-web)  Az Microsoft Store-ból telepített vagy az MDM LOB App Deployment funkcióját használó alkalmazásokhoz hasonló módon az [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) alkalmazásoknak [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) digitálisan alá kell írniuk az aláírási eszközzel, és az HoloLens-eszköznek megbízhatónak kell lennie az aláíráshoz használt tanúsítványban az alkalmazás üzembe helyezése előtt.

**Alkalmazástelepítési utasítások.**

1. Győződjön meg arról, hogy az eszköz nem minősül felügyeltnek
1. Győződjön meg arról, HoloLens 2. eszköz be van kapcsolva és csatlakoztatva van a számítógéphez
1. Győződjön meg arról, hogy be van jelentkezve a HoloLens 2-es eszközre
1. A számítógépen navigáljon az egyéni alkalmazáshoz, és másolja a yourapp.appxbundle et a yourdevicename\Internal Storage\Downloads mappába.   A fájl másolása után leválaszthatja az eszközt
1. A 2. HoloLens nyissa meg a Start menüt, válassza a Minden alkalmazás elemet, és indítsa el Fájlkezelő alkalmazást.
1. Lépjen a Letöltések mappára. Előfordulhat, hogy az alkalmazás bal oldali panelén először az Ez az eszköz lehetőséget kell választania, majd a Letöltések lapra kell navigálnia.
1. Válassza ki a yourapp.appxbundle fájlt.
1. A Alkalmazástelepítő meg fog indulni. Az alkalmazás telepítéséhez kattintson a Telepítés gombra.
A telepített alkalmazás a telepítés befejezésekor automatikusan elindul.

A folyamat teszteléséhez mintaalkalmazásokat [Windows univerzális GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) találhat.

Olvassa el az alkalmazások [2. HoloLens-re való telepítésének](app-deploy-app-installer.md)teljes folyamatát a Alkalmazástelepítő.  

![MRTK-példák telepítése Alkalmazástelepítő.](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>A frissítés fejlesztései és javításai:

- A kézkövetés mostantól számos olyan új esetben fenntartja a nyomkövetést, amikor a kéz korábban elveszett volna.  Az új esetek némelyikében csak a jobb pozíció frissül a felhasználó valódi kezében, a másik pedig egy korábbi helyzet alapján van kikövetkeztetve.  Ez a változás segít javítani a követési konzisztenciát az olyan mozgások során, mint a dobás, a dobás, a dobás és a klónozás.  Abban az esetben is segít, ha a kéz egy felülethez közel van, vagy egy objektumot tart lenyomva.  A kézredúsítő [](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) kikövetkeztetve az egy közös pontossági érték a "Közelítő" értékre lesz állítva a "High" (Magas) helyett.
- Kijavítottunk egy hibát, amely miatt az Azure AD-fiókok PIN-kódját alaphelyzetbe állítva a következő hibaüzenet jelenik meg: "Hiba történt.
- A felhasználóknak sokkal kevesebb indítás utáni OOBE-összeomlást kell látniuk az ET, az Iris gépi alkalmazásból, az új felhasználó vagy az értesítési bejelentések indításakor.
- A felhasználóknak megfelelő időzónának kell lennie az OOBE-val.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. decemberi frissítés

- Build 18362.1088

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb Windows Holographic 20H2 – 2020. decemberi frissítést és a buildben hozzáadott új Alkalmazástelepítő funkciót.

## <a name="windows-holographic-version-20h2"></a>Windows Holographic, 20H2-es verzió

- Build 19041.1128

Windows A Holographic 20H2 verzió már elérhető, és nagyszerű új funkciókat kínál 2 HoloLens és informatikai szakember számára. Az automatikus szempozíciótól a tanúsítványkezelőn át a Gépház a kioszkmód továbbfejlesztett funkcióin át az AutoPilot új beállítási képességein át. Ez az új frissítés lehetővé teszi, hogy az it-csapatok részletesebben szabályozni tudjanak a HoloLens konfigurálását és felügyeletét, és még zökkenőmentesebb holografikus élményt kínálnak a felhasználóknak.

Ez a legújabb kiadás a 2004-es verzió havi frissítése, de ezúttal új funkciókkal is rendelkezik. A fő buildszám változatlan marad, és Windows Update a 2004-es verzió (19041-es build) havi kiadását jelzi. A Build Number (Buildszám) megjelenik a Gépház > About (Információ) képernyőn, és ellenőrizze, hogy a legújabb elérhető build 19041.1128-as vagy további verzióval dolgozik-e. A legújabb kiadásra való frissítéshez nyissa meg a Gépház alkalmazást, nyissa meg az Update & Security (Biztonsági frissítések frissítése) gombra, és koppintson a Check for Updates (Frissítések keresése) gombra. Az új frissítések kezeléséhez HoloLens a Manage HoloLens updates (Új frissítések [kezelése) HoloLens meg.](hololens-updates.md)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>A Holographic 20H2 Windows újdonságai  

| Szolgáltatás                                              | Leírás                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Auto Eye Position Support](hololens-release-notes.md#auto-eye-position-support) | Aktívan számítja ki a szempozíciókat anélkül, hogy a felhasználók szemkövetésen keresztülmennek.   |
| [Tanúsítványkezelő](hololens-release-notes.md#certificate-manager)   | Lehetővé teszi, hogy az új, egyszerűbb módszerek tanúsítványokat telepítsenek és távolítsanak el Gépház alkalmazásból.     |
| [Automatikus indítású kiépítés USB-ről](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Az USB-meghajtókon található kiépítési csomagok automatikusan kérik a kiépítési oldalt az OOBE-ban.                                                         |
| [Kiépítési csomagok automatikus megerősítése az OOBE-ban](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | A kiépítési csomagokat a rendszer automatikusan alkalmazza az OOBE során a kiépítési oldalról.                                                         |
| [Automatikus kiépítés felhasználói felület használata nélkül](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Az automatikus kiépítési automatikus indítás és az automatikus megerősítés kombinálása. |
| [Az Autopilot használata Wi-Fi kapcsolattal](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Az Autopilot eszközről Wi-Fi Ethernet-adapter nélkül használható. |
| [TenantLockdown CSP és Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | A bérlő regisztrálása és a szabályzat alkalmazása után az eszköz csak akkor regisztrálható a bérlőben, amikor alaphelyzetbe áll vagy újra flash(ék) az eszközön. |
| [Globális hozzáférés hozzárendelve](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Új konfigurációs módszer több alkalmazásos kioszkmódhoz, amely rendszerszinten alkalmazza a kioszkot, így mindenkire alkalmazható.                  |
| [Alkalmazás automatikus indítása többalkalmazásos kioszkban](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Beállítja, hogy egy alkalmazás automatikusan elinduljon, amikor többalkalmazásos kioszkmódba jelentkezik be.                                                        |
| [A kioszkmód viselkedésének változásai a hibák kezelésével](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | A kioszkmód meghibásodása már korlátozó tartalékot is lehetővé tesz.                                                                                                |
| [HoloLens Politikák](hololens-release-notes.md#hololens-policies)                                    | Új szabályzatok a HoloLens.     |
| [Azure AD-csoporttagság gyorsítótárazése offline kioszkhoz](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Az új szabályzat lehetővé teszi a felhasználók számára, hogy csoporttagság-gyorsítótárat használjanak a kioszkmód offline használatára a beállított számú napig.                                        |
| [Új eszközkorlátozási szabályzatok a 2. HoloLens-](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Az újonnan engedélyezett eszközkezelési szabályzatok a 2. HoloLens engedélyezve.                                                                                |
| [Új energiagazdálkodási szabályzatok a 2. HoloLens számára](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Újonnan támogatott szabályzatok az időtúllépési beállításokhoz.  |
| [Szabályzatok frissítése](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Újonnan engedélyezett szabályzatok, amelyek lehetővé teszik a frissítések vezérlését.           |
| [Engedélyezve Gépház 2. HoloLens lap láthatósága](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Szabályzat az alkalmazásban látható oldalak Gépház meg.             |
| [Kutatási mód](hololens-release-notes.md#research-mode) | Kutatási mód használata a 2. HoloLens. |
| [Rögzítés hosszának megnövelve](hololens-release-notes.md#recording-length-increased) | Az MRC-felvételeket a továbbiakban nem 5 percre korlátozták. |
| [A frissítés fejlesztései és javításai](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | További javítások a frissítésben.   |

### <a name="auto-eye-position-support"></a>Automatikus szempozíció támogatása

A HoloLens 2-ben a szempozíciók lehetővé teszik a pontos hologram-pozíciót, a kényelmes megtekintést és a jobb megjelenítési minőséget. A szempozíciók kiszámítása belsőleg, a szemkövetési számítás részeként történt. Ehhez azonban minden felhasználónak szemkövetést kell követnie, még akkor is, ha a felhasználói élményhez nincs szükség szemre való betekintő adatokra.

**Az automatikus szempozíció (Auto Eye Position, AEP)** lehetővé teszi, hogy ezek a forgatókönyvek interakciómentes módon számítsák ki a felhasználó szempozícióit. Az Auto Eye Position automatikusan elkezd dolgozni a háttérben, attól kezdve, hogy a felhasználó bekapcsolja az eszközt. Ha a felhasználó még nem rendelkezik előzetes szemkövetési rendszerrel, az Auto Eye Position 20–30 másodperces feldolgozási idő után elkezdi a felhasználó szempozícióját a kijelző rendszer számára. A felhasználói adatok nem maradnak meg az eszközön, ezért ez a folyamat meg lesz ismételve, ha a felhasználó kikapcsolja és újra berakja az eszközt, vagy ha az eszköz újraindul vagy felébreszti az alvó állapotból.

Az Auto Eye Position funkcióval a rendszer viselkedése megváltozik, ha egy nem skálázott felhasználó az eszközt helyezi el. Ebben a kontextusban a nem minősített felhasználó olyanra hivatkozik, aki korábban még nem ment keresztül az eszközön a szemkövetési folyamaton.

| Aktív alkalmazás | Korábbi viselkedés | Viselkedés a holografikus Windows 20H2-es verziójának frissítésével |
|:-------------------|:-----------------|:-----------------------------------|
| Nem tekintetre képes alkalmazás vagy Holographic Shell |Megjelenik a szemkövetési párbeszédpanel. | Nem jelenik meg kérdés. |
| Tekintet-kompatibilis alkalmazás | Megjelenik a szemkövetési párbeszédpanel. | A szemkövetési üzenet csak akkor jelenik meg, ha az alkalmazás hozzáfér a szemstreamhez. |

Ha a felhasználó nem tekintetet használó alkalmazásról a tekinteti adatokhoz hozzáférő alkalmazásra tér át, megjelenik a figyelmeztetés.

A rendszer minden más viselkedése hasonló lesz ahhoz, amikor az aktuális felhasználó nem rendelkezik aktív szemkövetési követéssel. Az egy kézzel használható Indítás kézmozdulat például nem lesz engedélyezve. A kezdeti beállításhoz a kezdőélmény nem változik.

A szemre vonatkozó tekinteti adatokat vagy nagyon pontos hologrampozíciót igénylő élmények esetén javasoljuk, hogy a nem regisztrált felhasználók a szemkövetési görbét futtassanak. Elérhető a szemkövetési parancssorból, vagy úgy, hogy a start menüből elindítja a Gépház alkalmazást, majd a **System > > Eye > Run eye (Rendszer > 2016** 2016. 02. 00.) lehetőséget választva futtatja a run eye > elemet.

Ezek az információk később más, a-nak [megfelelő adatokat is tartalmaznak.](hololens-calibration.md#auto-eye-position-support)

### <a name="certificate-manager"></a>Tanúsítványkezelő

- Továbbfejlesztett naplózási, diagnosztikai és érvényesítési eszközök az eszközbiztonság és -megfelelőség érdekében az új Tanúsítványkezelővel. Ez a képesség lehetővé teszi a tanúsítványok kereskedelmi környezetekben való nagy léptékű üzembe helyezését, hibaelhárítását és érvényesítését.

A Windows Holographic 20H2 verzióban egy tanúsítványkezelőt ad hozzá a HoloLens 2 Gépház alkalmazáshoz. Az Update **Gépház > Security & és tanúsítványok > ugráshoz.** Ez a szolgáltatás egyszerű és felhasználóbarát módja a tanúsítványok megtekintésének, telepítésének és eltávolításának az eszközön. Az új Tanúsítványkezelővel a rendszergazdák és a felhasználók továbbfejlesztett naplózási, diagnosztikai és érvényesítési eszközökkel gondoskodnak az eszközök biztonságának és megfelelőségének biztosításáról.

- **Naplózás:** A tanúsítvány megfelelő telepítésének ellenőrzése vagy annak ellenőrzése, hogy a tanúsítvány megfelelően lett-e eltávolítva.
- **Diagnosztika:** Problémák esetén az eszköz megfelelő tanúsítványának létezik-e a hitelesítése időt takarít meg, és segít a hibaelhárításban.
- **Érvényesítés:** Annak ellenőrzése, hogy egy tanúsítvány a kívánt célt szolgálja-e és működik-e, jelentős időt takaríthat meg, különösen kereskedelmi környezetekben, mielőtt nagyobb léptékben helyez üzembe tanúsítványokat.

Ha gyorsan meg kell találnia egy adott tanúsítványt a listában, lehetőség van név, tároló vagy lejárati dátum szerint rendezni. A felhasználók közvetlenül is kereshetnek tanúsítványt. Az egyes tanúsítványtulajdonságok megtekintéséhez válassza ki a tanúsítványt, majd kattintson az **Információ elemre.**

A tanúsítványtelepítés jelenleg .cer és .crt fájlokat támogat. Az eszköztulajdonosok a helyi gépen és az aktuális felhasználón telepíthet tanúsítványokat;  minden más felhasználó csak az Aktuális felhasználóba telepíthető. A felhasználók csak a közvetlenül telepített tanúsítványokat távolítják el a Gépház felhasználói felületről. Ha egy tanúsítvány más módon lett telepítve, ugyanezt a mechanizmust kell eltávolítani.

#### <a name="steps-to-install-a-certificate"></a>Tanúsítvány telepítésének lépései

1. Csatlakozás 2. HoloLens számítógépére.
1. Helyezze a telepíteni kívánt tanúsítványfájlt a 2. HoloLens helyére.
1. Lépjen a Gépház App > Update & Security > Certificates (Tanúsítványok) **lapra,** és válassza a Tanúsítvány telepítése lehetőséget.
1. Kattintson **a Fájl importálása** elemre, és keresse meg a helyet, ahol a tanúsítványt mentette.
1. Válassza **a Store Location (Áruház helye) lehetőséget.**
1. Válassza **a Tanúsítványtároló lehetőséget.**
1. Kattintson az **Install** (Telepítés) gombra.

A tanúsítványnak most már telepítve kell lennie az eszközön.

#### <a name="steps-to-remove-a-certificate"></a>Tanúsítvány eltávolításának lépései

1. Lépjen a **Gépház App > Update and Security > Certificates (Tanúsítványok frissítése és >) lapra.**
1. Keresse meg a tanúsítványt név alapján a keresőmezőben.
1. Válassza ki a tanúsítványt.
1. Kattintson az **Eltávolítás gombra**
1. Ha a **rendszer** megerősítést kér, válassza az Igen lehetőséget.

![Tanúsítványmegjelenítő a Gépház alkalmazásban.](images/certificate-viewer-device.jpg)

![Kép arról, hogyan használható a Tanúsítvány felhasználói felülete egy tanúsítvány telepítésére.](images/certificate-device-install.jpg)

Ezek az információk később, egy új Tanúsítványkezelő [oldalon találhatók.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>Automatikus indítású kiépítés USB-ről

- Automatizált folyamatok, amelyek lehetővé teszik a kevesebb felhasználói beavatkozást, ha a kiépítési csomagokkal rendelkező USB-meghajtókat az OOBE során használják.

A kiadás előtt a felhasználóknak manuálisan kellett elindítaniuk a kiépítési képernyőt az OOBE során, hogy gombkombinációval kiépítsen. A felhasználók mostantól kihagyhatja a gombkombinációt egy USB-tároló meghajtón található kiépítési csomag használatával.

1. Csatlakoztassa az USB-meghajtót a kiépítési csomaghoz az OOBE első kezelhető pillanatában
1. Amikor az eszköz készen áll a kiépítésre, az automatikusan megnyitja a kiépítési oldalt.

Megjegyzés: Ha egy USB-meghajtó be van csatlakoztatva az eszköz indulása közben, az OOBE számba veszi a meglévő USB-tárolóeszközt, és figyelni fogja, hogy a további meghajtók be vannak-e csatlakoztatva.

A kiépítési csomagok OOBE során való alkalmazásával kapcsolatos további információkért látogasson el a HoloLens [dokumentációjában.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Az [USB-ről történő](hololens-provisioning.md#auto-launch-provisioning-from-usb) automatikus indítással kapcsolatos további információkat a kiépítési dokumentációban HoloLens találhat.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Kiépítési csomagok automatikus megerősítése az OOBE-ban

- A kevesebb felhasználói beavatkozást lehetővé tevő automatizált folyamat, amikor megjelenik a Kiépítési csomag lap, automatikusan alkalmazza az összes felsorolt csomagot.

Amikor megjelenik a kiépítés fő képernyője, az OOBE 10 másodpercet számol le, mielőtt automatikusan elkezdi alkalmazni az összes kiépítési csomagot. A felhasználók [a](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) várt csomagok ellenőrzése után 10 másodpercen belül is megerősítheti vagy megszakíthatja a műveletet.

### <a name="automatic-provisioning-without-using-ui"></a>Automatikus kiépítés felhasználói felület használata nélkül

- Kombinált automatikus folyamatok a kiépítéshez szükséges eszköz-interakciók csökkentése érdekében.

Az USB-eszközökről történő kiépítés automatikus indításának és a kiépítési csomagok automatikus megerősítésének kombinálásával a felhasználók HoloLens 2 eszközt automatikusan kiépíthet az eszköz felhasználói felületének használata nélkül, vagy akár be is használhatja az eszközt. Több eszköz esetében továbbra is használhatja ugyanazt az USB-meghajtót és kiépítési csomagot. Ez akkor hasznos, ha egyszerre több eszközt helyez üzembe ugyanazon a területen.

1. [Hozzon létre egy kiépítési csomagot](hololens-provisioning.md) [Windows Configuration Designer használatával.](https://www.microsoft.com/store/productId/9NBLGGH4TX22)
1. Másolja a csomagot egy USB-tároló meghajtójára.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build](https://aka.ms/hololens2previewdownload).
1. Ha [az Advanced Recovery Companion befejezte](https://www.microsoft.com/store/productId/9P74Z35SFRS8) az eszköz flash (flash) funkcióját, csatlakoztassa az USB-C-kábelt.
1. Csatlakoztassa az USB-meghajtót az eszközhöz.
1. Amikor a HoloLens 2 eszköz OOBE-ban indul, automatikusan észleli a kiépítési csomagot az USB-meghajtón, és elindítja a kiépítési lapot.
1. 10 másodperc elteltével az eszköz automatikusan alkalmazza a kiépítési csomagot.

Az eszköz most már konfigurálva van, és megjelenik a [Sikeres kiépítés képernyő.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### <a name="using-autopilot-with-wi-fi-connection"></a>Az Autopilot használata Wi-Fi kapcsolattal

- Az USB-C adapterek használata már nem szükséges az Ethernet-hez, ami csökkenti a hardveres igényeket azáltal, hogy az Autopilot Wi-Fi csatlakoztatott eszközökön.

Az OOBE során a 2. HoloLens Wi-Fi-vel való csatlakoztatása után az OOBE ellenőrzi, hogy van-e Autopilot-profil az eszközhöz. Ha talál ilyen igénylést, a folyamat többi része a AAD és a regisztrációs folyamat befejezésére lesz használva. Ez azt jelenti, hogy az ETHERNET és az USB-C Wi-Fi és az USB-C adapter között való használata már nem követelmény, de az OOBE kezdetekor továbbra is működni fognak. További információ a 2 eszközre [HoloLens Autopilotról.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>TenantLockdown CSP és Autopilot

- Úgy tartja a szervezet bérlőjében található eszközöket, hogy az eszköz alaphelyzetbe állításán vagy perjelen keresztül is zárolja őket a bérlőhöz. A további biztonság érdekében a fiók létrehozását a kiépítéssel nem lehet.

HoloLens 2 eszköz már támogatja a TenantLockdown CSP-t [Windows Holographic 20H2 verziójától.](hololens-release-notes.md#windows-holographic-version-20h2)

[TenantLockdown (Bérlői zárolás)](/windows/client-management/mdm/tenantlockdown-csp) A CSP lehetővé HoloLens, hogy a 2. pont csak az Autopilot használatával kötődik az MDM-regisztrációhoz. Ha a TenantLockdown CSP RequireNetworkInOOBE csomópontja true (igaz) vagy false (kezdetben beállított) értékre van állítva HoloLens 2-n, ez az érték megmarad az eszközön az újra flash (újra flash) vagy operációsrendszer-frissítések stb. ellenére.

Miután HoloLens 2. alkalommal a TenantLockdown CSP-k RequireNetworkInOOBE csomópontja true (igaz) értékre van állítva, az OOBE határozatlan ideig vár az Autopilot-profil sikeres letöltésére és alkalmazásra a hálózati kapcsolat után.

Miután a TenantLockdown CSP-k RequireNetworkInOOBE csomópontja true (igaz) értékre van állítva HoloLens 2. HoloLens OOBE esetében, a következő műveletek nem engedélyezettek az OOBE-ban:

- Helyi felhasználó létrehozása futásidejű kiépítéssel
- Azure AD-csatlakozás végrehajtása futásidejű üzembe építéssel
- Annak kiválasztása, hogy ki az eszköz a tulajdonában az OOBE-élményben

#### <a name="how-to-set-this-using-intune"></a>Hogyan állíthatja be ezt az Intune-nal?

1. Hozzon létre egy egyéni OMA URI eszközkonfigurációs profilt, és adja meg a true (igaz) értéket a RequireNetworkInOOBE csomóponthoz az alább látható módon.
Az OMA-URI értékének ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE kell lennie

   > [!div class="mx-imgBorder"]
   > ![Tennant-zárolás beállítása OMA-URI-n keresztül.](images/hololens-tenant-lockdown.png)

1. Hozzon létre egy csoportot, és rendelje hozzá az eszközkonfigurációs profilt az eszközcsoporthoz.

1. A HoloLens az előző lépésben létrehozott csoport 2. eszköztagját, és indítsa el a szinkronizálást.  

Ellenőrizze az Intune-portálon, hogy az eszközkonfiguráció alkalmazása sikeres volt-e. Miután ez az eszközkonfiguráció sikeresen alkalmazva lett HoloLens 2. eszközön, a TenantLockdown hatása aktív lesz.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Hogyan lehet a TenantLockdown RequireNetworkInOOBE szolgáltatását a 2. HoloLens az Intune használatával?

1. Távolítsa el HoloLens 2. adatokat arról az eszközcsoportról, amelyhez korábban hozzárendelték a fent létrehozott eszközkonfigurációt.

1. Hozzon létre egy egyéni OMA URI-alapú eszközkonfigurációs profilt, és az alább látható módon adja meg a false értéket a RequireNetworkInOOBE beállításhoz.
Az OMA-URI értékének ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE kell lennie

   > [!div class="mx-imgBorder"]
   > ![Képernyőkép a RequireNetworkInOOBE false (Hamis) beállításról OMA URI-n keresztül az Intune-ban.](images/hololens-tenant-lockdown-false.png)

1. Hozzon létre egy csoportot, és rendelje hozzá az eszközkonfigurációs profilt az eszközcsoporthoz.

1. A HoloLens az előző lépésben létrehozott csoport 2. eszköztagját, és indítsa el a szinkronizálást.

Ellenőrizze az Intune-portálon, hogy az eszközkonfiguráció alkalmazása sikeres volt-e. Miután ez az eszközkonfiguráció sikeresen alkalmazva lett HoloLens 2. eszközön, a TenantLockdown hatásai inaktívak lesznek.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Mi történne az OOBE során, ha az Autopilot-profil nincs hozzárendelve egy HoloLens miután a TenantLockdown true (igaz) értékre lett állítva?

Az OOBE határozatlan ideig vár az Autopilot-profil letöltésére, és megjelenik a következő párbeszédpanel. A TenantLockdown hatásainak eltávolításához az eszközt először az eredeti bérlővel kell regisztrálni az AutoPilot használatával, és a RequireNetworkInOOBE-t az előző lépésben leírtak szerint meg kell szüntetni a TenantLockdown CSP által bevezetett korlátozások eltávolítása előtt.

![Az eszköz nézetében megtekintheti, hogy mikor van kikényszeríteni a szabályzatot az eszközön.](images/hololens-autopilot-lockdown.png)

Ezek az információk most az Autopilot többi része mellett találhatók a [Tenantlockdown CSP és az AutoPilot alatt.](hololens2-autopilot.md#tenant-lockdown-csp-and-autopilot)

### <a name="global-assigned-access--kiosk-mode"></a>Globális hozzárendelt hozzáférés – Kioszkmód

- Csökkentett identitáskezelés a kioszkmódban azáltal, hogy engedélyezi az új kioszkmódot, amely rendszerszinten alkalmazza a kioszkmódot.

Ez az új funkció lehetővé teszi, hogy a rendszergazda egy HoloLens 2-es eszközt konfiguráljon több alkalmazás kioszkmódhoz, amely rendszerszinten alkalmazható, nem rendelkezik affinitással semmilyen identitással a rendszeren, és mindenkire érvényes, aki bejelentkezik az eszközre. Az új funkcióról részletesen a [kioszkmódban HoloLens olvashat.](hololens-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Alkalmazás automatikus indítása többalkalmazásos kioszkmódban

- Az automatikus alkalmazásindítás célzott felülete, amely tovább növeli a Kioszk módhoz választott felhasználói felület és alkalmazásválasztások számának növelése érdekében.

Csak a többalkalmazásos kioszkmódra vonatkozik, és csak 1 alkalmazás jelölhető ki automatikus indításra a hozzárendelt hozzáférés konfigurációjának alábbi kiemelt attribútumával.

Az alkalmazás automatikusan elindul, amikor a felhasználó bejelentkezik.

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>A kioszkmód viselkedésének változásai a hibák kezelésével

- Biztonságosabb kioszkmód a kioszkmódban rendelkezésre álló alkalmazások kiküszöbölésével.

Korábban a kioszkmód alkalmazásával HoloLens a Start menüben az összes alkalmazás megjelenik. A holografikus Windows 20H2-es verziójában hibák esetén a Start menüben nem jelennek meg alkalmazások az alábbiak szerint:

![Kép a kioszkmódról, ha meghibásodik.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Politikák

- Eszközkezelési lehetőségek kifejezetten HoloLens eszközkezeléshez létrehozott eszközök számára.

Új vegyes valóságú szabályzatok 2 HoloLens a Holographic 20H2 Windows verzióján. Az új szabályozható beállítások közé tartozik a fényerejének beállítása, a kötet beállítása, a hangfelvételek letiltása vegyes valóságú rögzítések esetén, a diagnosztikai adatok gyűjtésének beállítása, valamint AAD csoporttagság gyorsítótárának beállítása.  

| Új HoloLens szabályzat                                | Leírás                                                                               | Jegyzetek                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Lehetővé teszi a fényerő gombok letiltását, hogy a gomb megnyomása ne változtassa meg a fényerejét.       | 1 Igen, 0 Nem (alapértelmezett)                                                |
| MixedReality\VolumeButtonDisabled                  | Lehetővé teszi a hangerőszabályzó gombok letiltását, hogy a billentyű lenyomása ne változtassa meg a hangerőt.               | 1 Igen, 0 Nem (alapértelmezett)                                                |
| MixedReality\MicrophoneDisabled                    | Letiltja a mikrofont, így a 2. HoloLens hangrögzítése nem lehetséges.                      | 1 Igen, 0 Nem (alapértelmezett)                                                |
| MixedReality\FallbackDiagnostics                   | A diagnosztikai naplók gyűjtésének viselkedését szabályozza.                               | 0 Letiltva, 1 Engedélyezve az eszköztulajdonosok számára, 2 Engedélyezve mindenki számára (alapértelmezett) |
| MixedReality\HeadTrackingMode                      | Jövőbeli használatra fenntartva.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Azt szabályozza, hogy a rendszer hány napig használja az Azure AD-csoporttagság gyorsítótárát az Azure AD-csoportokat megcélzó kioszkhoz. | Lásd alább.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Azure AD-csoporttagság gyorsítótárazése offline kioszkhoz

- Offline kioszkok használata AAD legfeljebb 60 napig.

Ez a szabályzat szabályozza, hogy hány napig használható az Azure AD-csoporttagság gyorsítótára az Azure AD-csoportokat célzó hozzárendelt hozzáférési konfigurációkhoz a bejelentkezett felhasználók számára. Ha ez a házirend-érték csak 0-snál nagyobb értékre van állítva, akkor a rendszer más esetben nem használja a gyorsítótárat.  

Név: AADGroupMembershipCacheValidityInDays URI érték: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Minimum – 0 nap  
Maximum – 60 nap

A szabályzat megfelelő használatának lépései:

1. Hozzon létre egy eszközkonfigurációs profilt az Azure AD-csoportokat megcélzó kioszkeszközhöz, és rendelje hozzá HoloLens eszközhöz.
1. Hozzon létre egy egyéni OMA URI-alapú eszközkonfigurációt, amely a kívánt számú napra állítja be a szabályzat értékét (> 0), és rendelje hozzá HoloLens eszközhöz.
    1. Az URI értéket a következő OMA-URI szövegmezőben kell megadni: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Az érték az engedélyezett minimális és maximális érték között lehet.
1. Regisztrálja HoloLens eszközöket, és ellenőrizze, hogy mindkét konfiguráció alkalmazva lesz-e az eszközre.
1. Az Azure AD 1-es felhasználónak be kell jelentkeznie, ha elérhető az internet, amint a felhasználó bejelentkezik, és az Azure AD-csoporttagság sikeres megerősítést nyer, létrejön a gyorsítótár.
1. Az 1. Azure AD-felhasználó mostantól offline állapotba HoloLens, és kioszkmódhoz használhatja, ha a szabályzat értéke X számú napot tesz lehetővé.
1. A 4. és az 5. lépés megismételhető bármely más Azure AD-felhasználó N felhasználója számára. Itt az a lényeg, hogy minden Azure AD-felhasználónak be kell jelentkeznie az eszközre az internet használatával, hogy legalább egyszer megállapítsuk, hogy tagja-e annak az Azure AD-csoportnak, amelyhez kioszkkonfiguráció van megcélzva.

> [!NOTE]
> Amíg egy Azure AD-felhasználó esetében végre nem hajtotta a 4. lépést, a "leválasztott" környezetekben hiba lép fel.

### <a name="new-device-restriction-policies-for-hololens-2"></a>Új eszközkorlátozási szabályzatok a 2. HoloLens-

- Lehetővé teszi a felhasználók számára bizonyos eszközkezelési szabályzatok kezelését, például a kiépítési csomagok hozzáadásának vagy eltávolításának blokkolását.

Újonnan engedélyezett szabályzatok, amelyek több felügyeleti lehetőséget 2 HoloLens lehetővé.

- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage)
- [ConfigureTimeZone (Időzóna konfigurálása)](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

Az AllowAddProvisioningPackage és az AllowRemoveProvisioningPackage két új szabályzata hozzá lesz adva a [gyakori eszközkorlátozásainkhoz.](hololens-common-device-restrictions.md)

> [!NOTE]
> A [RemoteLock](/windows/client-management/mdm/remotelock-csp)esetében a HoloLens csak a ./Vendor/MSFT/RemoteLock/Lock konfigurációt támogatja. A PIN-kódokkal (például alaphelyzetbe állítással és helyreállítással) kapcsolatos konfigurációk nem támogatottak.

### <a name="new-power-policies-for-hololens-2"></a>Új energiagazdálkodási szabályzatok a 2. HoloLens számára

- További lehetőségek az alvó HoloLens vagy zárolásra energiagazdálkodási szabályzatokkal.

Ezek az újonnan hozzáadott szabályzatok lehetővé teszik a rendszergazdák számára az energiagazdálkodási állapotban, például az üresjárati időtúllépés szabályozását. Az egyes szabályzatokkal kapcsolatos további információkért kattintson a szabályzatra mutató hivatkozásra.

|     Szabályzatdokumentáció hivatkozása                |     Jegyzetek                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Példaérték a Windows Configuration Designerben, például:`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Példaérték a Windows Configuration Designerben, például:`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Példaérték a Windows Configuration Designerben, például 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Példaérték a Windows Configuration Designerben, például 100                                                                          |
|     [StandbyTimeoutOnBattery (StandbyTimeoutOnBattery)](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Példaérték a Windows Configuration Designerben, például:`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Példaérték a Windows Configuration Designerben, például:`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Ez a két új, DisplayOffTimeoutOnBattery és DisplayOffTimeoutPluggedIn szabályzat hozzáadódik a [gyakori eszközkorlátozásainkhoz.](hololens-common-device-restrictions.md)

> [!NOTE]
> A 2. HoloLens egységes felhasználói élmény érdekében győződjön meg arról, hogy a DisplayOffTimeoutOnBattery és a StandbyTimeoutOnBattery értékei is azonosak. Ugyanez vonatkozik a DisplayOffTimeoutPluggedIn és a StandbyTimeoutPluggedIn állapotra. A modern készenléti móddal kapcsolatos további információkért tekintse meg a Kijelző, alvó és [hibernált](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) üresjárati időzítők.

### <a name="newly-enabled-update-policies-for-hololens"></a>Újonnan engedélyezett frissítési szabályzatok HoloLens

- További lehetőségek a frissítések telepítésére vagy a Frissítések szüneteltetése gomb letiltására a frissítések biztosításához.

Ezek a frissítési szabályzatok mostantól engedélyezve vannak HoloLens 2 eszközön:

- [Frissítés/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
- [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
- [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

A frissítési szabályzatokkal és az eszközök HoloLens való használatával kapcsolatos részletes információkat itt olvashatja: Manage HoloLens updates (Frissítések [kezelése).](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Engedélyezve Gépház 2. HoloLens lap láthatósága

- Nagyobb felhasználói felületi vezérlés a Gépház alkalmazásban, ami összekeverhető, hogy csak korlátozott számú oldalt mutasson.

Most már engedélyeztünk egy olyan szabályzatot, amely lehetővé teszi a rendszergazdák számára, hogy megakadályozzák a System Gépház alkalmazás adott lapjainak láthatóvá vagy hozzáférhetővé tétele, vagy hogy ezt a megadott oldalak kivételével minden oldalon megtedzék. Ha meg szeretne ismerkedni a funkció teljes testreszabásának mikéntjére, kattintson az alábbi hivatkozásra.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Ha meg szeretne ismerkedni a 2. HoloLens testreszabható oldalbeállításokkal, látogasson el a Gépház [URI-k oldalára.](settings-uri-list.md)

![Képernyőkép a módosított aktív órákról az Gépház alkalmazásban.](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Kutatási mód

Kutatási módban a HoloLens 2. eszköze a számítógépes látáskutatásnak. A korábbi kiadásokhoz képest a research mode for HoloLens 2 a következő előnyökkel jár:

- A HoloLens (1. generációs) kutatási módban elérhetővé vált érzékelők mellett mostantól IMU-érzékelői hozzáférést is biztosítunk, beleértve a gyorsulásmérőt, a groscope-t és a kilométermérőt.
- HoloLens 2. lépés olyan új képességeket biztosít, amelyek a Kutatási móddal együtt használhatók. Pontosabban a kézkövetési és a szemkövetési API-khoz való hozzáférés, amelyek a kísérletek gazdagabb készletét biztosítják.

A kutatók mostantól lehetővé teszik, hogy a HoloLens eszközükön engedélyezzék a research mode (kutatási mód) számára az összes külső képérzékelő adatfolyamhoz való hozzáférést. A Research Mode for HoloLens 2 a gyorsulásmérő, a groscope és a kilométeróra-mérők eléréséhez is hozzáférést biztosít. A felhasználók adatainak védelme érdekében a nyers szemkövetéses kameraképek nem érhetők el a Research Mode(Kutatási mód) szolgáltatáson keresztül, de a szem-tekintet iránya a meglévő API-kon keresztül érhető el.

További technikai részletekért tekintse meg a [kutatási mód](/windows/mixed-reality/research-mode) dokumentációját.

### <a name="recording-length-increased"></a>Rögzítés hosszának megnövelve

Az ügyfelek visszajelzései miatt növeljük a vegyes valóságú [rögzítések hosszát.](holographic-photos-and-videos.md) A vegyes valóságú rögzítések alapértelmezés szerint nem lesznek 5 percre korlátozva, hanem a maximális rögzítési hosszt számítják ki a rendelkezésre álló lemezterület alapján. Az eszköz a teljes lemezterület 80%-ának megfelelő szabad lemezterület alapján megbecsüli a videófelvétel maximális időtartamát.

> [!NOTE]
> A HoloLens videófelvétel alapértelmezett hosszát (5 perc) használja, ha a következők valamelyike bekövetkezik:
>
> - A becsült maximális rögzítési időtartam kisebb, mint az alapértelmezett 5 perc.
> - A rendelkezésre álló lemezterület kevesebb, mint a teljes lemezterület 20%-a.

A teljes követelményeket a holografikus fényképek és [videók dokumentációjában találja.](holographic-photos-and-videos.md#maximum-recording-length)

### <a name="improvements-and-fixes-in-the-windows-holographic-version-20h2-update"></a>Fejlesztések és javítások a Windows Holographic 20H2-es verziójának frissítésében:

- Az OOBE több képernyője már sötét módban van.
- További információ: A tartalomnak a legújabb online adatvédelmi nyilatkozatra kell mutasson.
- Elhárítottunk egy problémát, amely miatt a felhasználók nem létesíthették ki a VPN-profilokat a kiépítési csomagokon keresztül.
- Ki van javítva a VPN-kapcsolat proxykonfigurációs problémája.
- Szabályzat frissítve az USB-függvények Enumerálásának letiltásához az MDM for NCM for AllowUsbConnection esetén.
- Elhárítottunk egy problémát, amely miatt egy HoloLens-eszköz nem jelent meg a Fájlkezelő Media Transfer Protocol (MTP) protokollon keresztül, amikor az eszköz egyalkalmazásos [kioszkként van beállítva.](hololens-kiosk.md) Vegye figyelembe, hogy az MTP (és általában az USB-kapcsolat) továbbra is letiltható az [AllowUSBConnection szabályzattal.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Kijavítottunk egy hibát, amely miatt a Start menü ikonjai megfelelően voltak skálázva Kioszk módban.
- Kijavítottunk egy hibát, amely az Azure AD-csoportokat célzó kioszkmódot zavaró HTTP-gyorsítótárazás miatt történt.
- Ki lett javítva az a hiba, amely miatt a felhasználók nem tudtak a Párosítás gombot használni a fejlesztői módnak a kiépítési csomagokkal való engedélyezése után, kivéve, ha letiltották és újra engedélyezték a Fejlesztői módot.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. novemberi frissítés

- Build 18362.1085

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb funkció kiadási buildet Windows Holographic 20H2-es verziójával.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, 2004-es verzió – 2020. októberi frissítés

- Build 19041.1124

A frissítés fejlesztései és javításai:

- Eltávolítottunk egy felesleges ellenőrzést, amely futásidejű rendszerhibát okozott.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. októberi frissítés

- Build 18362.1081

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb buildeket a Windows Holographic 2004-es verziójához.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, 2004-es verzió – 2020. szeptemberi frissítés

- Build 19041.1117

A frissítés fejlesztései és javításai:

- Elhárít egy problémát, amely Visual Studio megakadályozta az alkalmazások hibakeresését, amikor a SupportsMultipleInstances="true" szó jelen van az appxmanifestben.
- Ez a kiadás tartalmazza az NCSI-proxyészlelési javítást, amely a hálózati proxyn keresztüli sikertelen internetes észlelést oldja meg. Az NCSI használhat gépproxyt és profilonkénti proxyt az internetkapcsolat észleléséhez. Az NCSI a későbbi kiadásban támogatni fogja a felhasználónkénti proxyt.
- A legtöbb Windows Mixed Reality az előre irány vektor párhuzamos a talajjal, amikor a felhasználó feje semleges pozícióban van előretekintve. A 2. HoloLens korábbi verziói azonban úgy igazítják a vektort, hogy az inkább a kijelzőpanelekre legyen igazítva, amely az ideális tájoláshoz képest néhány fokkal lefelé van döntésre va. A 2. HoloLens újabb verziói javították ezt a szemantikai konzisztencia biztosítása érdekében az űrlaptényezők között.
- Továbbfejlesztett kézkövetési robusztusság, amely kevesebb nyomkövetési veszteségeket eredményez bizonyos helyzetekben.
- Ez a kiadás olyan javítást tartalmaz a hang-időbélyegző minőségének javításához, amely hozzájárult a videórögzítési problémákhoz.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. szeptemberi frissítés

- Build 18362.1079

A frissítés fejlesztései és javításai:

- A legtöbb Windows Mixed Reality az előre irány vektor párhuzamos a talajjal, amikor a felhasználó feje semleges pozícióban van előretekintve. A 2. HoloLens korábbi verziói azonban úgy igazítják a vektort, hogy az inkább a kijelzőpanelekre legyen igazítva, amely az ideális tájoláshoz képest néhány fokkal lefelé van döntésre va. A 2. HoloLens újabb verziói javították ezt a szemantikai konzisztencia biztosítása érdekében az űrlaptényezők között.
- Továbbfejlesztett kézkövetési robusztusság, amely kevesebb nyomkövetési veszteségeket eredményez bizonyos helyzetekben.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, 2004-es verzió – 2020. augusztusi frissítés

- Build 19041.1113

A frissítés fejlesztései és javításai:

- Gépház alkalmazás a továbbiakban nem fogja követni a felhasználót az Írisz-regisztráció vagy a Szemkövetési élmények igénylésében.
- Kijavítottunk egy hibát, amely miatt az eszközt átnevező és más műveleteket (például egy hálózathoz való csatlakozást) végző kiépítési csomag OOBE során való alkalmazása az átnevezés miatt nem tudja végrehajtani a többi műveletet az eszköz újraindítása után.
- Módosítottuk a kezdeti eszközbeállítási folyamatok színsémát a vizualizáció minőségének javítása érdekében.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. augusztusi frissítés

- Build 18362.1074

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb buildeket a Windows Holographic 2004-es verziójához.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, 2004-es verzió – 2020. júliusi frissítés

- Build 19041.1109

A frissítés fejlesztései és javításai:

- A fejlesztők mostantól dönthetnek úgy, hogy engedélyezik vagy letiltják, Eszközportál biztonságos kapcsolatot igényelnek.
- Javult a megbízhatóság az alkalmazások operációsrendszer-frissítések utáni indításához.
- A beérkezett üzenetek alapértelmezett fényerejét 100%-ra módosítottuk.
- Elhárítottunk egy, a 2. Windows Eszközportál-on HoloLens HTTPS-továbbítással kapcsolatos problémát.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. júliusi frissítés

- Build 18362.1071

A frissítés fejlesztései és javításai:

- Kijavítottunk egy problémát, amely miatt a hologramok eltűnhetnek a Unity-alkalmazásokban a követés elvesztésekor vagy visszaszerzésekor.
- Kijavítottunk egy problémát, amely miatt az HoloLens alkalmazások újra összeomlottak a rendszerhéjba, miközben a HoloLens Emulator egyes eszközökön hardvergyorsítással használják.
- A 2. Windows Eszközportál https-továbbításával kapcsolatos HoloLens probléma megoldása.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, 2004-es verzió – 2020. júniusi frissítés

- Build 19041.1106

A frissítés fejlesztései és javításai:

- Az egyéni MRC-rögzítők mostantól új alapértelmezett értékekkel rendelkeznek bizonyos tulajdonságokhoz, ha nincsenek megadva.
  - Az *MRC videóhatása:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Modern headset))
  - Az *MRC audiohatáson:*
    - LoopbackGain (az aktuális "App Audio Gain" érték a Vegyes valóság rögzítése lapján Windows Eszközportál)
    - MicrophoneGain (az aktuális "Mic Audio Gain" érték a Vegyes valóság rögzítése lapján Windows Eszközportál)
- Kijavítottunk egy hibát, amely javította a hangminőséget a vegyes valóságú rögzítési forgatókönyvekben. Pontosabban, ennek a javításnak meg kell szüntetnie a felvétel hanghiba-átvitelét a **Start menü** megjelenítésekor.
- Továbbfejlesztett hologramstabilitás a rögzített videókban.
- Megoldottuk azt a problémát, amely miatt a vegyes valóságú rögzítés nem tudott videót rögzíteni, miután az eszköz több napig készenléti állapotban volt.
- A HolographicSpace.UserPresence API általában le van tiltva a Unity-alkalmazások esetében. Ez a viselkedés elkerüli azt a problémát, amely miatt egyes alkalmazások szünetelnek a vizor tükrözése esetén, még akkor is, ha a "futtatás a háttérben" beállítás engedélyezve van. Az API most már engedélyezve van a Unity 2018.4.18-as és újabb, valamint 2019.3.4-es és újabb verzióihoz.
- Ha egy Eszközportál kapcsolaton keresztül fér hozzá a Wi-Fi, előfordulhat, hogy egy webböngésző érvénytelen tanúsítvány miatt megakadályozza a hozzáférést. Előfordulhat, hogy a böngésző hibát jelez( például "ERR_SSL_PROTOCOL_ERROR", még akkor is, ha az eszköz tanúsítványa korábban megbízható volt. Ebben az esetben nem tud továbbhaladni a Eszközportál, mivel nincs lehetőség a biztonsági figyelmeztetések figyelmen kívül hagyása. Ez a frissítés megoldotta a problémát. Ha az eszköztanúsítványt korábban letöltötték, és a böngésző biztonsági figyelmeztetései el lett távolítva a számítógépen, és SSL-hiba történik, az új tanúsítványt le kell tölteni, és megbízhatónak kell lennie a böngésző biztonsági figyelmeztetései esetén.
- Lehetővé tette olyan futásidejű kiépítési csomag létrehozása, amely MSIX-csomagok használatával képes alkalmazásokat telepíteni.
- Új beállítás hozzáadva a **Gépház** System Hologramok, amely lehetővé teszi a felhasználók számára, hogy az eszköz leállított Mixed Reality összes hologramot automatikusan  >    >   eltávolítsák a Mixed Reality eszközről.
- Kijavítottunk egy hibát, amely HoloLens, hogy a képpontformátumuk úgy változott, hogy feketét renderel a HoloLens emulátorban.
- Kijavítottunk egy hibát, amely összeomlást okozott az Írisz bejelentkezése során.
- Kijavítottunk egy hibát, amely a már meglévő alkalmazások ismételt áruházi letöltésével kapcsolatos.
- Kijavítottunk egy hibát, amely megakadályozza, hogy a modern alkalmazások Microsoft Edge meg többször.
- Kijavítottuk a Hibát, amely a Photos alkalmazás indításkor, az 1903-as kiadásból való frissítés után jelent meg.
- Jobb teljesítmény és megbízhatóság.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. júniusi frissítés

- Build 18362.1064

A frissítés fejlesztései és javításai:

- Az egyéni MRC-rögzítők új alapértelmezett értékekkel rendelkeznek bizonyos tulajdonságokhoz, ha nincsenek megadva.
  - Az *MRC videóhatása:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Modern headset))
  - Az *MRC audiohatáson:*
    - LoopbackGain (az aktuális "App Audio Gain" érték a Vegyes valóság rögzítése lapján Windows Eszközportál)
    - MicrophoneGain (az aktuális "Mic Audio Gain" érték a Vegyes valóság rögzítése lapján Windows Eszközportál)
- A HolographicSpace.UserPresence API általában le van tiltva a Unity-alkalmazások esetében. Ez a viselkedés elkerüli azt a problémát, amely miatt egyes alkalmazások szünetelnek a vizor tükrözése esetén, még akkor is, ha a háttérben való futtatás engedélyezve van. Az API most már engedélyezve van a Unity 2018.4.18-as és újabb, valamint 2019.3.4-es és újabb verzióihoz.
- Kijavítottunk egy hibát, amely miatt HoloLens, amelyek a képpontformátumukat feketére változtatták a HoloLens Emulator.
- Kijavítottuk a Photos alkalmazás első indításkor való indításával kapcsolatos hibát az 1903-as kiadásból való frissítés után.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, 2004-es verzió

- Build – 19041.1103

A HoloLens 2020. májusi fő szoftverfrissítése, a *Windows Holographic 2004-es* verziója számos izgalmas új képességet tartalmaz, többek között az Windows Autopilot, az alkalmazás sötét üzemmódja, az USB Ethernet-támogatás az 5G/LTE-elérési pontokhoz. A legújabb kiadásra való frissítéshez nyissa meg a **Gépház** alkalmazást, nyissa meg az Update & Security (Biztonsági frissítések frissítése) lehetőséget, és válassza a   Frissítések keresése  **** ****   gombot. 

|             Szolgáltatás                              |          Leírás                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Új eszközök előzetes konfigurálása és zökkenőmentes beállítása éles környezetben az AutoPilot Windows használatával                 |
|       FIDO 2-támogatás                             |          A FIDO2 biztonsági kulcsok támogatása a megosztott eszközök gyors és biztonságos hitelesítésének engedélyezéséhez            |
|       Továbbfejlesztett kiépítés                      |          Zökkenőmentesen alkalmazhat kiépítési csomagot egy USB-meghajtóról a HoloLens                              |
|       Alkalmazástelepítés állapota                 |          Ellenőrizze a telepítési állapotot az Gépház alkalmazás MDM-en keresztül a 2. HoloLens-be lekért alkalmazások esetében               |
|       Konfigurációszolgáltatók (CSP-k)   |          Új konfigurációs szolgáltatók hozzáadva a rendszergazdai vezérlési képességek javítása érdekében                 |
|       USB 5G/LTE-támogatás                       |          A bővített USB Ethernet-képesség lehetővé teszi az 5G/LTE támogatását                                    |
|       Sötét alkalmazás mód                              |          Sötét alkalmazásmód érhető el a sötét és világos módokat egyaránt támogató alkalmazásokhoz, ami javítja a megtekintési élményt        |
|       Hangparancsok                             |          További rendszerhangvezérlési parancsok támogatása a HoloLens vezérléséhez                           |
|       A kézkövetés fejlesztései                 |          A kézkövetés fejlesztései pontosabb gombokat és 2D-s belós interakciókat eredményeznek                        |
|       Minőségi fejlesztések és javítások                 |          Különböző rendszerteljesítmény- és megbízhatósági fejlesztések a platformon                            |

### <a name="support-for-windows-autopilot"></a>Az Autopilot Windows támogatása

Windows Az Autopilot for HoloLens 2 lehetővé teszi, hogy az eszköz értékesítési csatornája előre regisztrálja HoloLens az Intune-bérlőben. Amikor az eszközök megérkeznek, készen állnak a bérlőn megosztott eszközként való önálló üzembe helyezésre. Az önálló üzembe helyezés előnyeinek kihasznál érdekében az eszköznek a beállítás első képernyőjén csatlakoznia kell egy hálózathoz egy USB-C-to-Ethernet kapcsolattal.

Miután a felhasználó elindítja az Autopilot önkiszolgáló üzembe helyezési folyamatát, a folyamat a következő lépéseket teszi:

1. Az eszköz Azure Active Directory (Azure AD).
1. Az Azure AD használatával regisztrálja az eszközt a Microsoft Intune (vagy egy másik MDM-szolgáltatásban).
1. Töltse le az eszközre vonatkozó szabályzatokat, tanúsítványokat és hálózati profilokat.
1. Az eszköz kiépítése.
1. A bejelentkezési képernyőt mutatja be a felhasználónak.

További információ: [Windows Autopilot for HoloLens 2 kiértékelési útmutató.](hololens2-autopilot.md)

*Lépjen kapcsolatba a fiókkezelővel az AutoPilot előzetes verzióhoz való csatlakozáshoz. Az Autopilot-kompatibilis eszközök hamarosan megkezdik a szállítást.*

### <a name="fido2-security-key-support"></a>FIDO2 biztonsági kulcs támogatása

Egyes felhasználók munkahelyi HoloLens munkahelyi vagy iskolai környezetben osztják meg az eszköz eszközét. Ezért fontos, hogy a felhasználók könnyedén, hosszú felhasználónév és jelszó beírása nélkül is használhasson. A Fast Identity Online (FIDO) lehetővé teszi, hogy a szervezeten (Azure AD-bérlőn) bárki zökkenőmentesen jelentkezzen be HoloLens felhasználónév vagy jelszó megadása nélkül.

A FIDO2 biztonsági kulcsok egy "unphishable" szabványalapú, jelszó nélküli hitelesítési módszer, amely bármilyen tényezőben elérhető. A FIDO a jelszó nélküli hitelesítés nyílt szabványa. Lehetővé teszi a felhasználók és a szervezetek számára, hogy felhasználónév vagy jelszó nélkül jelentkezzenek be az erőforrásaikba. Ehelyett egy külső biztonsági kulcsot vagy egy eszközbe épített platformkulcsot használnak.

Első lépések: [Jelszó nélküli biztonsági kulcsos bejelentkezés engedélyezése.](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Továbbfejlesztett MDM-regisztráció a kiépítési csomagon keresztül

A kiépítési csomagok lehetővé HoloLens konfigurációs fájlon keresztül, és nem a HoloLens, hanem a konfigurációt. Korábban a kiépítési csomagokat át kellett másolni a HoloLens memóriába. Ezek mostantól USB-meghajtón is használhatók, így könnyebben újra felhasználhatók több HoloLens eszközön, és az eszközöket párhuzamosan is kiépítheti. A kiépítési csomagok mostantól támogatják az eszközkezelésbe való regisztrációhoz szükséges mezőt is, így a kiépítés után nincs szükség manuális beállításra.

A kipróbálhoz:

1. Töltse le a Windows Configuration Designer legújabb verzióját Windows a számítógépére.
1. Válassza **a Provision HoloLens Devices** Provision HoloLens  >  **2 devices (Eszközök kiépítése 2 eszközön) lehetőséget.**
1. Készítse el a konfigurációs profilt. Ezután másolja az összes létrehozott fájlt egy USB-C tárolóeszközre.
1. Csatlakoztassa az USB-C eszközt bármely, frissen flash HoloLens. Ezután nyomja le **a hangerőt**  +  **a bekapcsológombokkal** a kiépítési csomag alkalmazáshoz.

### <a name="line-of-business-application-install-status"></a>Az üzletági alkalmazások telepítési állapota

Az üzletági alkalmazások MDM-alkalmazástelepítése és -kezelése kritikus fontosságú a HoloLens. A rendszergazdáknak és a felhasználóknak meg kell tekinteniük az alkalmazás telepítési állapotát a naplózáshoz és a diagnosztikákhoz. Ebben a kiadásban további részleteket adtunk hozzá a **Gépház** hozzáférés munkahelyi vagy iskolai fiókhoz lapon Kattintson a  >    >    >  **fiók adatai**  >  **elemre.**

### <a name="additional-csps-and-policies"></a>További CSP-k és szabályzatok

A [konfigurációszolgáltató (CSP)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) az eszköz konfigurációs beállításainak olvasására, beállítására, módosítására vagy törlésére való felület. Ebben a kiadásban további szabályzatokat is támogatunk, hogy növeljük a rendszergazdák felügyeletét a telepített HoloLens felett. A csp-k által támogatott CSP-k listáját HoloLens [NetworkQoSPolicy CSP (HálózatQoSPolicy CSP)](/windows/client-management/mdm/networkqospolicy-csp).

A kiadás újdonsága:

**Házirendek csp-e** 

A Szabályzatkonfiguráció szolgáltató lehetővé teszi, hogy a vállalat házirendeket konfigurálja Windows eszközökön. Ebben a kiadásban új szabályzatokat adtunk hozzá a HoloLens, amelyek itt vannak felsorolva. További információ: [A 2. HoloLens által támogatott szabályzat-CSP-k.](/windows/client-management/mdm/policies-supported-by-hololens2)  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps
- LetAppsAccessGazeInput
- LetAppsAccessGazeInput_ForceAllowTheseApps
- LetAppsAccessGazeInput_ForceDenyTheseApps
- LetAppsAccessGazeInput_UserInControlOfTheseApps
- LetAppsAccessMicrophone_ForceAllowTheseApps
- LetAppsAccessMicrophone_ForceDenyTheseApps
- LetAppsAccessMicrophone_UserInControlOfTheseApps
- AllowWiFi

**NetworkQoSPolicy CSP**

A NetworkQoSPolicy konfigurációs szolgáltató hálózati szolgáltatásminőségi (QoS) házirendeket hoz létre. A QoS-házirend egyező feltételek alapján hajt végre műveleteket a hálózati forgalomon. További információ: [NetworkQoSPolicy CSP.](/windows/client-management/mdm/networkqospolicy-csp)

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Bővített USB Ethernet-támogatás 5G/LTE-alapú internetre csatlakoztatott eszközökhöz

Támogatás lett hozzáadva bizonyos mobilos szélessávú eszközök, például az 5G/LTE-telefonok és Wi-Fi elérési pontok engedélyezéséhez, amikor USB-kapcsolaton keresztül csatlakoznak HoloLens 2. porthoz. Ezek az eszközök mostantól egy másik Ethernet-kapcsolatként **jelennek** meg a hálózati beállítások között. (A külső illesztőt igénylő mobil szélessávú eszközök nem támogatottak.) Ez a funkció nagy sávszélességű kapcsolatokat tesz lehetővé, ha Wi-Fi nem érhető el, és Wi-Fi nem elég nagy teljesítményű. További információ a támogatott USB-eszközökről: Csatlakozás és [Bluetooth USB-C-eszközök.](hololens-connect-devices.md)  

### <a name="hand-tracking-improvements"></a>A kézkövetés fejlesztései

Ez a kiadás számos kézkövetési fejlesztést tartalmaz:

- **A pontozás stabilitása:** A rendszer most már nem állja meg az indexavat, amikor a torkok eltoltják. Ez a módosítás javítja a pontosságot a gombok leküldésekor, a begépelésekor, a tartalom görgetésekor és így tovább! 
- **Kevesebb véletlen légi koppintás:** Továbbfejlesztettük a légkoppintásos kézmozdulat észlelését. Számos gyakori forgatókönyvben kevesebb véletlen aktiválás történt, például amikor a két kéz az oldalára kerül.
- **A felhasználói kapcsoló megbízhatósága:** A rendszer mostantól gyorsabb és megbízhatóbb a kézméret frissítésében, amikor megoszt egy eszközt.
- **Kisebb kézlopás:** Továbbfejlesztettük az olyan esetek kezelését, amelyekben kétnél több kéz látható az érzékelőkkel. Ha többen dolgoznak együtt, sokkal kisebb az esélye annak, hogy a nyomon követéses kéz a felhasználótól a jelenetben található valaki más kézhez "ugrik".
- **Rendszer megbízhatósága:** Kijavítottunk egy hibát, amely miatt a kézkövetés leállt, amikor az eszköz nagy terhelés alatt áll.

### <a name="dark-mode"></a>Sötét mód

Számos Windows már támogatja a sötét és a világos módot is. HoloLens 2 felhasználó választhatja ki az alapértelmezett módot a mindkettőt támogató alkalmazásokhoz. A frissítés után az alapértelmezett alkalmazásmód "sötét", de ezt a beállítást egyszerűen módosíthatja: Lépjen a Gépház A rendszer színei Válassza ki az alapértelmezett  >    >    >  **alkalmazásmódot.**

Ezek a "in-box" alkalmazások támogatják a sötét módot:

- Beállítások
- Microsoft Store
- Mail
- Naptár
- Fájlkezelő
- Visszajelzési központ
- OneDrive
- Fotók
- 3D-megjelenítő
- Filmek & TV

![Sötét módú ablakok csempével.](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Rendszerhangparancsok

Mostantól az eszközön található bármely alkalmazáshoz használhat hangparancsokat. További információ: [Use your voice to operate HoloLens.](hololens-cortana.md) Lásd még [a 2. HoloLens támogatott nyelveket.](hololens2-language-support.md)  

### <a name="cortana-updates"></a>Cortana frissítések

A frissített alkalmazás integrálható a Microsoft 365, hogy jobban el tudja látni az eszközeit (jelenleg csak a US-English érhető el). A HoloLens 2. Cortana már nem támogat bizonyos eszközspecifikus parancsokat, például a kötetek beállítását vagy az újraindítást. Ezeket a beállításokat már támogatják az új rendszerhangparancsok. Az új alkalmazásról Cortana blogunkban talál [további információt.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>Minőségi fejlesztések és javítások

Fejlesztések és javítások a frissítésben is:  

- Bevezettünk egy aktív kijelző-megjelenítő rendszert. Ez a funkció javítja a hologramok stabilitását és igazítását. Mostantól a helyén maradnak, ha a fejet oldalról oldalra mozgatja.
- Kijavítottunk egy hibát, Wi-Fi a streamelés HoloLens időnként megszakadt. Ha egy alkalmazás azt jelzi, hogy kis késésű streamelésre van szüksége, implementálja a javítást a [SetSocketMediaStreamingMode függvény hívásával.](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)
- Kijavítottunk egy lefagyó eszközt, amely a streamelés során, kutatási módban történt.
- Kijavítottunk egy hibát, amely miatt bizonyos esetekben a megfelelő felhasználó nem jelenik meg a bejelentkezési képernyőn a munkamenet befejezésekor.
- Kijavítottunk egy hibát, amely miatt a felhasználók nem tudtak MDM-naplókat exportálni a **Gépház.**
- Kijavítottunk egy hibát, amely miatt a szemkövetés azonnal, a beépített beállítás után a vártnál alacsonyabb lehet.
- Kijavítottunk egy problémát, amely miatt a szemkövetési alrendszer bizonyos körülmények között nem tudott inicializálni vagy végrehajtani a beépítést.
- Kijavítottunk egy problémát, amely miatt a rendszer a már beállított felhasználót kéri a szemredúsztástól.
- Kijavítottunk egy problémát, amely miatt a illesztő összeomlott a szemkontraszt során.
- Kijavítottunk egy hibát, amely miatt az ismételt bekapcsológombnyomások 60 másodperces rendszer-időtúllépést és rendszerhéj-összeomlást okozhatnak.
- Nagyobb stabilitás a mélységi pufferek számára.
- Hozzáadtunk egy **Megosztás gombot** a Visszajelzési központ hogy a felhasználók könnyebben megosztanának visszajelzéseket.
- Kijavítottunk egy hibát, amely miatt a RoboRaid wan nincs megfelelően telepítve.

### <a name="known-issues"></a>Ismert problémák

- A zh-CN rendszernyelvvel kapcsolatos probléma megakadályozza, hogy a hangparancsok vegyes valóságot rögzítsenek vagy megjelenítsen egy eszköz IP-címét.
- A probléma megoldásához el kell indítania a Cortana alkalmazást, miután elindítja az eszközt a "Hey Cortana" hangaktiválás használatához. Ha frissített egy 18362-es buildről, akkor a Start menüben egy második alkalmazáscsempét is láthat a Cortana-alkalmazás előző **verziójához.**

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. májusi frissítés

- Build 18362.1061

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat, mivel a csapat a Windows Holographic 2004 májusi frissítésén dolgozott a korábban leírtak szerint.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. áprilisi frissítés

- Build 18362.1059

**Sötét mód a támogatott alkalmazásokhoz**

Számos Windows alkalmazás támogatja a sötét és a világos módot is. HoloLens 2 ügyfél választhatja ki az alapértelmezett módot a mindkét színsémát támogató alkalmazásokhoz. Az ügyfelek visszajelzései alapján az alapértelmezett alkalmazásmódot "sötétre" állítva bármikor módosíthatja ezt a beállítást: Lépjen a **Gépház > System > Colors** oldalra, és keresse meg az "Alapértelmezett alkalmazásmód kiválasztása" **lehetőséget.**

Ezek a "in-box" alkalmazások támogatják a sötét módot:

- Beállítások
- Microsoft Store
- Mail
- Naptár
- Fájlkezelő
- Visszajelzési központ
- OneDrive
- Fotók
- 3D-megjelenítő
- Filmek & TV

**Fejlesztések és javítások a frissítésben is:**

- Gondoskodott arról, hogy a rendszerhéj-átfedések vegyes valóságú rögzítésben is szerepelnek.
- Az Irreális fejlesztők mostantól a 3D View (3D-nézet) Eszközportál tesztelni és hibakeresést végezni az alkalmazásokban.
- Jobb hologramstabilitás a vegyes valóságban a *HolographicDepthReprojectionMethod DepthReprojection algoritmus* használata esetén.
- Ki van javítva a "WinRT IStreamSocketListener API-osztály nincs regisztrálva" hiba a 32 bites ARM-alkalmazásokban.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. márciusi frissítés

- Build 18362.1056

A frissítés fejlesztései és javításai:

- Jobb hologramstabilitás a vegyes valóságban a *HolographicDepthReprojectionMethod AutoPlanar* algoritmus használata esetén.
- Gondoskodott róla, hogy a mélységi MF-mintához csatolt koordinátarendszer konzisztens legyen a nyilvános dokumentációval.
- Hatékonyabb fejlesztői hatékonyság, mert lehetővé teszi az ügyfelek számára, hogy nagy mennyiségű szöveget illessnek be az eszközportálon keresztül.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. februári frissítés

- Build 18362.1053

A frissítés fejlesztései és javításai:

- Ideiglenesen letiltotta a HolographicSpace.UserPresence API-t Unity-alkalmazásokhoz. Ez a módosítás elkerüli azt a problémát, amely miatt egyes alkalmazások szünetelnek a vizor tükrözése esetén, még akkor is, ha a "futtatás a háttérben" beállítás engedélyezve van.
- Kijavítottunk egy kézi követés által okozott véletlenszerű HUP-összeomlást, amelyben a felhasználó felhasználói felületi lefagyást észlelt, majd néhány másodperc elteltével visszatért a rendszerhéjba.
- Továbbfejlesztett kézkövetés, hogy amikor az indexavacsával koppint, annak az ujjlenyomatnak a felső része kevésbé lesz valószínű, hogy váratlanul megreked.
- Javult a fejkövetés, a térbeli leképezés és más futásidők megbízhatósága.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. januári frissítés

- Build 18362.1043

A frissítés fejlesztései és javításai:

- Nagyobb stabilitás az exkluzív alkalmazások számára a HoloLens 2 emulátor használata során.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, 1903-as verzió – 2019. decemberi frissítés

- Build 18362.1042

A frissítés fejlesztései és javításai:

- Bevezettük az utolsó fázis reprodukálás (LSR) javításokat. A hologramok továbbfejlesztett vizuális renderelése stabilabbnak és pontosabbnak tűnik, és pontosabban számol a mélységüknek. Ez a jelenség a frissítés után észrevehetőbb lesz, ha az alkalmazások nem megfelelően állítják be a hologramok mélységét.
- Ki van javítva az exkluzív alkalmazások stabilitása és az exkluzív alkalmazások közötti navigáció.
- Megoldottuk azt a problémát, amely miatt a vegyes valóságú rögzítés nem tudott videót rögzíteni, miután az eszköz több napig készenléti állapotban volt.
- Továbbfejlesztett hologramstabilitás.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, 1903-as verzió – 2019. novemberi frissítés

- Build 18362.1039

A frissítés fejlesztései és javításai:

- Ki van javítva **a Hangparancsok** kiválasztása funkció az en-CA és az en-AU kezdeti beállítása során.
- Javult az objektumok vizuális minősége a unity és az Mixed Reality Toolkit (MRTK) legújabb verzióiban.
- Ki lett javítva az olyan problémák megoldása, amelyek miatt a holografikus alkalmazások indításkor szüneteltetett állapotban ragadtak, amíg a Start menü meg nem nyitották, majd be nem zárták.
- Az OpenXR-futásidejű megfelelőség javításai és fejlesztései HoloLens 2. és az emulátor számára.
