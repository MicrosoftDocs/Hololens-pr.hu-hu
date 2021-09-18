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
ms.openlocfilehash: bdfdcda8cc890691f6112e7798d402ca9e7f4c6d
ms.sourcegitcommit: 6c8406bbcc79c1f624736cc68e1aaeab70436902
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/17/2021
ms.locfileid: "127904310"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Belső előzetes verzió a Microsoft HoloLens

Üdvözöljük az Insider előzetes verziójának legújabb buildjeiben HoloLens! Az első lépésekhez egyszerűen [hozzá](hololens-insider.md#start-receiving-insider-builds) lehet kezdeni, és értékes visszajelzést adni az operációs rendszer következő jelentős frissítésével kapcsolatban a HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Belső kibocsátási megjegyzések

Izgatottan várjuk, hogy ismét új funkciókat Windows Insidersbe. Az új buildek a fejlesztői és bétaverziós csatornákra lesznek felkísértve a legújabb frissítéseket. Ezt az oldalt folyamatosan frissítjük, ahogy további funkciókkal és frissítésekkel egészül ki a Windows Insider buildje. Legyen izgatott, és készen áll arra, hogy ezeket a frissítéseket a valóságba keverje.

Ez a továbbfejlesztett hibaelhárítási és eszközjelentésekkel, a kioszkmód egyes javított hibáival, a tanúsítványmegjelenítővel, a bővített kezelhetőségi felülettel és a magasabb frissítési megbízhatósággal kapcsolatos. Ennek a funkciófrissítésnek egy új funkciója hamarosan HoloLens a moving Platform Mode (Mozgóplatform mód). Tekintse meg a 2. HoloLens nagyszerű funkcióit!

| Szolgáltatás                 | Leírás                | Felhasználó vagy forgatókönyv | Build bevezetve |
|-------------------------|----------------------------|--------------|------------------|
| [Platform mód mozgatás](#moving-platform-mode) | Bevezeti a moving Platform Mode bétaverziót, amely a konfiguráláskor HoloLens 2. használatát teszi lehetővé alacsony dinamikus mozgást tapasztaló nagy méretű állatokon. | Mind | 20348.1411 |
| [PFX-fájl támogatása a Tanúsítványkezelőben](#pfx-file-support-for-certificate-manager) | PFX-tanúsítványok hozzáadása Gépház felhasználói felületen | Végfelhasználó | 20348.1405 |
| [Speciális diagnosztikai jelentés megtekintése a Gépház a HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | MDM diagnosztikai naplók megtekintése az eszközön | Hibaelhárítás | 20348.1405 |
| [Offline diagnosztikai értesítések](#offline-diagnostics-notifications) | Visszajelzés a naplógyűjtéssel kapcsolatban | Hibaelhárítás | 20348.1405 |
| [Az alacsony tárterületű naplógyűjtés fejlesztései](#low-storage-log-collection-improvements) | A naplógyűjtési forgatókönyvek fejlesztései alacsony tárolási helyzetekben. | Hibaelhárítás | 20348.1412 |
| [CSP-módosítások a jelentéskészítési HoloLens részleteihez](#csp-changes-for-reporting-hololens-details) | Új CSP-k az adatok lekérdezéséhez | It-rendszergazdák    | 20348.1403                 |
| [CSP által vezérelt automatikus bejelentkezési szabályzat](#auto-login-policy-controlled-by-csp) | Fiók automatikus bejelentkezéshez használatos | It-rendszergazdák | 20348.1405 |
| [Továbbfejlesztett frissítés-újraindítás észlelése és értesítések](#improved-update-restart-detection-and-notifications) | Új engedélyezett szabályzatok és felhasználói felület a frissítésekhez. | It-rendszergazdák | 20348.1405 |
| [Intelligens újrapróbálkozás alkalmazásfrissítésekkor](#smart-retry-for-app-updates) | Lehetővé teszi a rendszergazdák számára az alkalmazások frissítésére ütemezett újraküldetni a frissítéseket. | It-rendszergazdák | 20348.1405 |
| [Csak privát áruházbeli alkalmazások használata Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Az áruházbeli alkalmazás konfigurálása úgy, hogy csak a szervezettől származó alkalmazásokat mutassa | Rendszergazdai | 20348.1408 |
| [WDAC- és LOB-alkalmazások használata](#use-wdac-and-lob-apps) | Lehetővé teszi, hogy a rendszergazdák saját alkalmazásokat használjanak, és továbbra is a WDAC használatával tiltsák le a többi alkalmazást. | It-rendszergazdák | 20348.1405 |
| [Javítások és fejlesztések](#fixes-and-improvements) | Javítások és fejlesztések a HoloLens. | Mind | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>Rendszergazdai belső szolgáltatás ellenőrzőlistája

✔️ Ha egyetlen Azure AD-fiókot szeretne beállítani az automatikus bejelentkezéshez, konfigurálja ezt az új [CSP-t.](#auto-login-policy-controlled-by-csp) <br>
✔️ Ha úgy szeretné konfigurálni az alkalmazásokat, hogy a frissítés sikertelen frissítése után automatikusan kísérelje meg a frissítést, állítsa be ezt az új [CSP-t intelligens újrapróbálkozáshoz.](#smart-retry-for-app-updates) <br>
✔️ Ha jobban szeretné szabályozni az operációs rendszer frissítéseit, tekintse meg az újonnan engedélyezett frissítési [szabályzatokat.](#improved-update-restart-detection-and-notifications) <br>
✔️ Ha a vállalati alkalmazásokat az Microsoft Store-n keresztül szeretné elérhetővé tenni a vállalati áruházban, de csak a szervezet alkalmazásait [](#use-only-private-store-apps-for-microsoft-store)szeretné engedélyezni, nem a teljes áruházat, állítsa be ezt a szabályzatot. <br>
✔️ Ha szeretné tudni a szabad tárterületet, az SSID-t vagy a HoloLens-eszközök BSSID-ját, tekintse meg ezeket a jelentéskészítési [CSP-ket.](#csp-changes-for-reporting-hololens-details) <br>
✔️ Ha a WDAC használatával szeretné letiltani az alkalmazások vagy folyamatok indítását, de saját alkalmazásokat kell használnia, mostantól engedélyezheti a LOB-t a [WDAC-szabályzatban.](#use-wdac-and-lob-apps)

### <a name="moving-platform-mode"></a>Platform mód mozgatás

Az **Insider 20348.1411-es** buildjében bétaverziós támogatást biztosítunk a 2. HoloLens mozgó platformokon való nyomon követéshez. A build telepítése és a Mozgóplatform mód engedélyezése után használhatja a HoloLens 2-es HoloLens korábban nem elérhető környezetekben, például nagy méretű teherszállítókban és nagy méretű állatokban. Jelenleg a funkció célja ezeknek az adott mozgó platformoknak a engedélyezése. Bár semmi sem akadályozza meg abban, hogy más környezetekben is megpróbálja használni a funkciót, a funkció célja, hogy először támogatást nyújtsunk ezekhez a környezetekhez.

Ha többet szeretne megtudni a támogatott funkciókról és az új funkció engedélyezéséről, látogasson el a [mozgóplatform oldalára.](hololens2-moving-platform.md)

#### <a name="overview-to-try-out-moving-platform-mode"></a>A platform üzemmód áthelyezésének kipróbált módja – áttekintés

1. [Fejlesztői mód és eszközportál engedélyezése.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. [Platform üzemmód áthelyezésének engedélyezése az Eszközportálon keresztül.](hololens2-moving-platform.md#enabling-moving-platform-mode)
1. Vigye az eszközt a nagyméretű mozgó platformra, és figyelje meg, mennyire stabilak a hologramok.

### <a name="pfx-file-support-for-certificate-manager"></a>PFX-fájl támogatása a Tanúsítványkezelőben

Az Insider Windows 20348.1405-ös buildben vezettük be. Mostantól támogatott a Tanúsítványkezelő a .pfx-tanúsítványok használatára. [](certificate-manager.md) Amikor a felhasználók Gépház Frissítés & biztonsági tanúsítványokhoz, és kiválasztják a Tanúsítvány telepítése lehetőséget, a felhasználói felület mostantól támogatja  >    >   **a** .pfx tanúsítványfájlt.
A felhasználók titkos kulccsal .pfx-tanúsítványt importálnak a felhasználói tárolóba vagy a számítógép tárolóba.

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>PFX-fájlok tanúsítványkezelőben való kipróbálása – áttekintés

1. Készítse elő a PFX-fájlt.
1. Másolja a fájlt az eszközre EGY USB-C-kábelen keresztül.
1. Nyissa meg Gépház alkalmazást, navigáljon a [Tanúsítványkezelőhöz,](certificate-manager.md) és alkalmazza a tanúsítványt.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Speciális diagnosztikai jelentés megtekintése a Gépház a HoloLens

A felügyelt eszközök esetében a viselkedés hibaelhárítása során fontos lépés annak ellenőrzése, hogy a várt házirend-konfiguráció van-e alkalmazva. Korábban az új funkció esetében ezt az információt az MDM-en keresztül vagy az eszköz közelében kellett megtekinteni az MDM-en keresztül, miután exportálta az **Gépház** Accounts Access munkahelyi vagy iskolai alkalmazással összegyűjtött diagnosztikai naplókat, és válassza a Felügyeleti naplók exportálása és megtekintése egy közeli számítógépen  ->    >  lehetőséget. 

Az MDM-diagnosztika mostantól megtekinthető az eszközön az Edge böngésző használatával. Ha könnyebben meg szeretne tekinteni egy MDM diagnosztikai jelentést, lépjen a Hozzáférés munkahelyi vagy iskolai alkalmazáshoz lapra, és válassza a Speciális diagnosztikai **jelentés megtekintése lehetőséget.** Ez létrehozza és megnyitja a jelentést egy új Edge-ablakban.

![Tekintse meg a speciális diagnosztikai jelentést Gépház alkalmazásban.](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>A speciális diagnosztikai jelentés kipróbálásának áttekintése

1. Nyissa meg a Beállítások alkalmazást.
1. Lépjen a Fiókok lapra, és kattintson a Felügyeleti naplók **exportálása hivatkozásra.**
1. Tekintse meg az eszköz konfigurációjának speciális információit.

### <a name="offline-diagnostics-notifications"></a>Offline diagnosztikai értesítések

Ez egy offline diagnosztika nevű meglévő [szolgáltatás frissítése.](hololens-diagnostic-logs.md#offline-diagnostics) Korábban nem volt egyértelmű jelzés a felhasználók számára a diagnosztikai gyűjtés aktiválására vagy befejezésére.
Most, hogy hozzáadta Windows Insider-buildeket, kétféle visszajelzési mód létezik az Offline Diagnosticshoz. Az első a bejelentések értesítései, amelyek a gyűjtemény indításakor és befejezésekor is megjelennek. Ezek akkor jelennek meg, ha a felhasználó bejelentkezett, és rendelkezik vizualizációval.

![Bejelentés a naplók gyűjtéséhez.](./images/logcollection1.jpg)

![Bejelentés a naplógyűjtés befejezésekor.](./images/logcollection2.jpg)

Mivel a felhasználók gyakran használják tartalék naplógyűjtési mechanizmusként az Offline diagnosztikát, amikor nem férnek hozzá a kijelzőkhez, nem tudnak bejelentkezni vagy még mindig az OOBE-ban vannak, a naplók gyűjtésekor hangjel is megjelenik. A bejelentési értesítés mellett ez a hang is megjelenik.

Ez az új funkció az eszköz frissítésekekor lesz engedélyezve, és nem szükséges engedélyezni vagy kezelni. Ha az új visszajelzés nem jelenik meg vagy nem hallható, az Offline diagnosztika továbbra is létrejön.

Reméljük, hogy a visszajelzések újabb kiegészítésével könnyebb diagnosztikai adatokat gyűjteni, és gyorsabban elhárítani a problémákat.

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>A diagnosztikai értesítések kipróbálásának áttekintése

1. Az eszköz zárolásának feloldása és elhasználódása.
1. Az Offline **diagnosztikagyűjtéshez** nyomja le a Power and Volume **down** (Be- és lenyomás) [gombkombinációt.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Megtekintheti a bejelentési értesítéseket, és hangjeleket hallhat arról, hogy az eszköz mikor indul el és fejezi be a naplók gyűjtését.

### <a name="low-storage-log-collection-improvements"></a>Az alacsony tárterületű naplógyűjtés fejlesztései

Az olyan forgatókönyvekben, ahol az eszköz a diagnosztikai naplók gyűjtésekor  kevés a lemezterület, létrejön egyStorageDiagnostics.zipnevű jelentés. Az alacsony tárterület küszöbértékét a rendszer Windows [határozza meg.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>A kevés tárterületet eredményező fejlesztések kipróbálásának áttekintése

1. Töltse ki az eszköz tárhelyét.
1. Az Offline **diagnosztikagyűjtéshez** nyomja le a Power and Volume **down** (Be- és lenyomás) [gombkombinációt.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Figyelje meg, hogy egy új fájl található a naplók gyűjteményében, amely a naplók dokumentumok mappájában HoloLens.

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-módosítások a jelentéskészítési HoloLens részleteihez

- A Windows 20348.1403-as buildben vezettük be

Az alábbi CSP-k új módszereket kínálnak a jelentések jelentésére a HoloLens eszközeiről.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP – Ingyenes Storage

A DevDetail CSP mostantól a szabad tárterületet is jelenti HoloLens eszközön. Ennek nagyjából meg kell egyeznie az alkalmazás Gépház lapján látható Storage értékkel. Az alábbiakban az ezt az információt tartalmazó csomópont található.

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
> - Egyes események, például a fő operációsrendszer-frissítések miatt előfordulhat, hogy a megadott felhasználónak újra be kell jelentkeznie az eszközre az automatikus bejelentkezés folytatásához.
> - Az automatikus bejelentkezés csak MSA- és AAD-felhasználók számára támogatott.

#### <a name="overview-to-try-auto-logon-csp"></a>Az automatikus bejelentkezés CSP-jének kipróbálás áttekintése

1. Konfigurálja az új CSP-t egy kívánt [felhasználóhoz egy egyéni házirend használatával:](/mem/intune/configuration/custom-settings-windows-10)`./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. Alkalmazza a CSP-t az eszközre a [kiépítési csomag vagy](hololens-provisioning.md) [az MDM segítségével.](hololens-mdm-configure.md)
1. Jelentkezzen be a megadott fiókba.
1. Indítsa újra az eszközt, és figyelje meg, hogy a felhasználó automatikusan be van jelentkezve.

### <a name="improved-update-restart-detection-and-notifications"></a>Továbbfejlesztett frissítés-újraindítás észlelése és értesítések

Az aktív órák és a telepítési idő házirendek között elkerülhető, hogy a HoloLens újraindítsa az eszközöket, amikor használatban vannak. Ha azonban nem történik újraindítás a szükséges frissítések telepítésének befejezéséhez, az is késleltetné a frissítések telepítését. Most olyan szabályzatokat adtunk hozzá, amelyek lehetővé teszik az it-ita számára a határidők és a szükséges újraindítások kényszerítése, valamint a frissítések időbeni telepítésének befejezését. A felhasználók értesítést kaphatnak az újraindítás kezdeményezése előtt, és az it-szabályzatnak megfelelően késleltetni tudják az újraindítást.

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
1. Figyelje meg, hogy a felhasználó értesítést kap a frissítésről, és hogy újra kell indítania az \* eszközt.

\* Az eredmények a frissítési szabályzatok alapján változhatnak.

### <a name="smart-retry-for-app-updates"></a>Intelligens újrapróbálkozás alkalmazásfrissítésekkor

A HoloLens egy új szabályzat, amely lehetővé teszi a rendszergazdák számára, hogy ismétlődő vagy egyszeri dátumot állítsanak be az olyan alkalmazások újraindításához, amelyek frissítése az alkalmazás használatban való használata miatt meghiúsult, és lehetővé teszi a frissítés alkalmazását. Ezek több különböző eseményindító, például ütemezett időpont vagy bejelentkezés alapján is beállíthatók. További információ az [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)szabályzatnézet használatával kapcsolatban.

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Az alkalmazásfrissítések intelligens újrapróbálkozási próbálkozásának áttekintése

1. Konfigurálja az új intelligens újrapróbálkozási funkciót.
1. Olyan eszközön, amely még nem kapta meg az alkalmazást, és megfelelően van konfigurálva, jelentkezzen be egy online környezetbe.
1. Az eszköz kikapcsolásával vagy leválasztásával ne tudja letölteni az alkalmazást.
1. A letöltés újrapróbálkozása során az eszköz bekapcsolt állapotban legyen, és kapcsolódva legyen az internethez.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Csak privát áruházbeli alkalmazások használata Microsoft Store

A RequirePrivateStoreOnly szabályzat engedélyezve van a HoloLens. Ez a szabályzat lehetővé Microsoft Store, hogy az alkalmazás úgy legyen konfigurálva, hogy csak a szervezet számára konfigurált privát tárolót mutassa. A hozzáférés korlátozása csak az Ön által elérhetővé tett alkalmazásokra.

További információ az [ApplicationManagement/RequirePrivateStoreOnly -ről.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

#### <a name="overview-to-try-only-private-store-apps"></a>A privát áruházbeli alkalmazások kipróbálásának áttekintése

1. Konfigurálja az új szabályzatot az eszközökhöz [az MDM-en keresztül.](hololens-mdm-configure.md)
1. Jelentkezzen be egy olyan eszközre, amely a szabályzatot használja.
1. Nyissa meg Microsoft Store alkalmazást, és figyelje meg, hogy csak a szervezet alkalmazásait láthatja.

### <a name="use-wdac-and-lob-apps"></a>WDAC- és LOB-alkalmazások használata

Mostantól a WDAC használatával letilthatja az alkalmazások vagy folyamatok indítását, és továbbra is használhatja a saját, nagyságú alkalmazásait. mostantól engedélyezheti őket a WDAC-szabályzatban. A szabályzat használata magában foglalja egy további kódsor futtatását a PowerShellben a WDAC-szabályzat létrehozásakor. [Tekintse át az itt található lépéseket.](/mem/intune/configuration/custom-profile-hololens)

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>Saját alkalmazások WDAC használatával való letiltásának áttekintése

1. Gyűjtse össze az LOB-alkalmazás AUMID-it és a blokkolni kívánt alkalmazásokat.
1. [Hozzon létre egy új WDAC-szabályzatot](/mem/intune/configuration/custom-profile-hololens) az új lépéseket követve.
1. [Telepítse a szabályzatot az MDM használatával](hololens-mdm-configure.md) az eszközére.
1. Jelentkezzen be az eszközre, és figyelje meg, hogy elindíthatja az alkalmazást, és letilthat másokat.

### <a name="fixes-and-improvements"></a>Javítások és fejlesztések

- Kijavítottunk egy ismert hibát, Eszközportál amikor nem volt rákérdezés [a zárolt fájlok letöltésére.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- A [fájlfeltöltési és -letöltési időkor](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)Eszközportál hiba kijavítva.
- A megfelelőségi tulajdonságok jelentésével kapcsolatos problémák megoldása HoloLens eszközökről; Előfordulhat, hogy újraindításra van szükség ahhoz, hogy a megfelelő jelentéskészítés aktiválódjon az Insider-buildek esetén.  
- Engedélyezve van [egy hozzárendelt](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) hozzáférési API, így az alkalmazások mostantól megállapíthatják, hogy egy HoloLens fut-e kioszkmódban a HoloLens.
- Frissítettük a Remote Assist beépített verzióját, amely friss flashre van telepítve.
- A 2D-alkalmazások gamepad-feldolgozása le lett tiltva az Insider-buildek esetében. Az eltávolítással az alkalmazások mostantól szabadon használhatja közvetlenül a Gamepad API-kat, és hozzáférhetnek a vezérlők teljes készletéhez, és bármit megtesznek, amit csak szeretne. A fejlesztőknek a Gamepad API-kat kell használniuk a Gamepad bemenetének használhatja. Példa a [Gamepad osztályra (Windows. Gaming.Input) – Windows UWP-alkalmazások.](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)
- Kijavítottunk egy hibát, amely miatt az első felhasználói bejelentkezés után az OOBE leállt olyan esetekben, amikor AAD-csoportalapú kioszkkonfigurációkat használtak.
- Javítva lett a frissítési értesítések és párbeszédpanelek megjelenítésével kapcsolatos probléma az eszköz újraindításához.

## <a name="start-receiving-insider-builds"></a>Insider-buildek fogadásának kezdete

> [!NOTE]
> Ha a közelmúltban nem frissített, indítsa újra az eszközt az állapot frissítéséhez, és szerezze be a legújabb buildet.
>
> - Az "Eszköz újraindítása" hangparancs jól működik.
> - Az újraindítási gombot a következő Gépház/Windows Insider Program.
>
> Előfordulhat, hogy egy hiba történt a háttérben, amely miatt előfordulhatott, hogy ezzel vissza fog menni a útjára.

A 2. HoloLens eszközön válassza az Update Gépház Security &  >  **lehetőséget Windows Insider Program** és válassza az  >   Első **lépések lehetőséget.** Csatolja a regisztrációhoz használt fiókot Windows Insiderben.

> [!NOTE]
> Ahhoz, hogy regisztrálja az eszközt az Insider-buildekbe, engedélyeznie kell a nem kötelező telemetriát. Ha még nem tette meg, nyissa meg a Gépház alkalmazást, és válassza az **Adatvédelmi** diagnosztika &, majd válassza a Választható diagnosztikai  ->   **adatok lehetőséget.**

Windows belső csatorna most a Csatornákra van átköltözve. A **Gyors** kör lesz a **Fejlesztői** csatorna, a **Lassú** kör lesz a **Béta csatorna,** a kiadási **előnézeti** kör pedig a kiadási előzetes csatorna **lesz.** A leképezés így néz ki:

![Windows A belső csatornák magyarázata.](images/WindowsInsiderChannels.png)

További információ: [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (A belső csatornák Windows blogok).
Ezután válassza az **Aktív fejlesztés** a Windows lehetőséget, válassza ki,  hogy dev **channel-t** vagy Béta csatorna-buildeket szeretne kapni, és tekintse át a program feltételeit.
A **befejezéshez válassza > Újraindítás most** lehetőséget. Miután az eszköz újraindult, a Gépház > **Update & Security > Frissítések** keresése lapra ásva leküldheti a legújabb buildet.

### <a name="update-error-0x80070490-work-around"></a>Hiba 0x80070490 hiba a hiba körül

Ha frissítési hibát 0x80070490 a fejlesztői vagy bétaverziós csatornán való frissítéskor, próbálkozzon a következő rövid távú munkával. Ez magában foglalja a belső csatorna áthelyezését, a frissítés be- és áthelyezését, majd az Insider-csatorna vissza mozgatát.

#### <a name="stage-one---release-preview"></a>Első fázis – Előzetes verzió

1. Gépház a Biztonsági & frissítése, majd Windows Insider Program a Kiadási előzetes **csatorna lehetőséget.**

2. Gépház, Update & Security, Windows Update, **Frissítések keresése.** A frissítés után folytassa a második fázisra.

#### <a name="stage-two---dev-channel"></a>Második fázis – Fejlesztői csatorna

1. Gépház Update & Security (Biztonsági frissítés) Windows Insider Program válassza a **Dev Channel (Fejlesztői csatorna) lehetőséget.**

2. Gépház, Update & Security, Windows Update, **Frissítések keresése.**

## <a name="ffu-download-and-flash-directions"></a>FFU letöltési és flash utasítások

Az aláírt ffu repülőjárattal való teszteléshez először fel kell oldania az eszköz zárolását, mielőtt a repülőjárat aláírt ffu-ját felrakná.

1. Pc-n:
    1. Töltse le a ffu-t a számítógépére a [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) ről.

    1. Telepítse az ARC-t (Speciális helyreállítási társ) a következő Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. On HoloLens - Flight Unlock: Open **Gépház**  >  **Update & Security**  >  **Windows Insider Program** majd regisztráljon, indítsa újra az eszközt.

1. Flash FFU – Most már az ARC használatával is flashlheti a repülőjárat aláírt FFU-ját.

### <a name="provide-feedback-and-report-issues"></a>Visszajelzés küldése és problémák jelentése

A [visszajelzések Visszajelzési központ és a](hololens-feedback.md) jelentésekkel kapcsolatos problémák HoloLens a saját alkalmazásában. A Visszajelzési központ biztosítja, hogy minden szükséges diagnosztikai információ bekerül a hibakeresésbe és a probléma megoldásához.  A kínai és a japán nyelvű HoloLens ugyanúgy kell jelenteni.

> [!NOTE]
> Mindenképpen fogadja el azt a kérdést, amely rákérdez, hogy szeretné Visszajelzési központ szeretné-e elérni a Dokumentumok mappát (válassza az **Igen** lehetőséget, amikor a rendszer kéri).

## <a name="note-for-developers"></a>Megjegyzés fejlesztőknek

Nyugodtan fejleszthet alkalmazásokat belső fejlesztésű belső HoloLens.  Az első [lépésekhez tekintse](https://developer.microsoft.com/windows/mixed-reality/development) HoloLens fejlesztői dokumentációját. Ugyanezek az utasítások az insider buildek HoloLens.  Használhatja a Unity ugyanazon buildeket és Visual Studio, mint a fejlesztéshez HoloLens használ.

## <a name="stop-receiving-insider-builds"></a>Insider-buildek fogadásának leállítása

Ha már nem szeretné megkapni az Windows Holographic Insider-buildjét, kikapcsolhatja, ha az HoloLens éles [](hololens-recovery.md) buildet futtat, vagy az Advanced Recovery Companion használatával helyreállíthatja az eszközt az Windows Holographic nem insider verziójára.

> [!CAUTION]
> Megjelenik egy ismert probléma, amely miatt az Insider Preview-ból való regisztrációt manuálisan újratelepítő felhasználók kék képernyőt tapasztalnak. Ezt követően manuálisan kell helyreállítania az eszközt. Ha szeretné részletesen ismerni, hogy ez hatással lenne-e a problémára, tekintse meg az ismert [problémát.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Annak ellenőrzése, hogy a HoloLens futtat-e éles buildet:

1. Keresse meg **Gépház > System > About (Rendszer) >,** és keresse meg a build számát.

1. [Az éles buildszámok kibocsátási megjegyzései.](hololens-release-notes.md)

Az Insider-buildek lemondása:

1. Éles buildet HoloLens futtató környezetben válassza a **Gépház > Update & Security > Windows Insider Program** lehetőséget, és válassza a Stop Insider builds (Belső buildek leállítása) **lehetőséget.**

1. Az eszköz lemondáshoz kövesse az utasításokat.
