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
ms.date: 06/17/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 1c0beed39fa6b4642a581da6baac44c732642e74d8b2c41ebca1b6d3f24b127d
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663487"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2. kiadási megjegyzések

Annak érdekében, hogy hatékony felhasználói élményben legyen része a HoloLens, továbbra is kiadjuk a funkciókat, a hibákat és a biztonsági frissítéseket. Ezen az oldalon láthatja az egyes HoloLens újdonságokat. A 2. HoloLens frissítésének legújabb verziójához [](hololens-update-hololens.md#check-for-updates-and-manually-update) manuálisan is frissíthet, vagy a Teljes flash frissítéssel (FFU) frissítheti az eszközt az [Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device)segítségével. A [letöltés](https://aka.ms/hololens2download) naprakész, és a legújabb általánosan elérhető buildet biztosítja.

> [!NOTE]
> A Windows 11-es bejelentése a számítógép verziójával Windows. 2021 májusában elindítottunk egy jelentős operációsrendszer-frissítést HoloLens 2. kiadásra, és az őszre vonatkozó ügyfél-visszajelzések alapján dolgozunk egy hamarosan megjelenő kiadáson. [](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067)

> [!IMPORTANT]
> A [21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)buildben már megoldott ismert hiba miatt, amely a Remote Assist-felhasználókat érinti, időlegesen szüneteltette a Windows Holographic 21H1-es verziójának frissítéseit. Emellett módosítottuk az alapértelmezett Advanced Recovery Companion (ARC) buildet a [Windows Holographic 20H2 – 2021.](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)júniusi frissítésére. Az ARC-build folytatja a 21H1 build megcélzását.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holographic, 21H1-es verzió – 2021. júliusi frissítés
- Build 20348.1010

A frissítés fejlesztései és javításai:

- Eszközportál továbbfejlesztett módszerekkel értesíti az ügyfelet, Fájlkezelő problémákba ütközik a zárolt fájlok megnyitásakor.
- A fájlok feltöltése, letöltése, átnevezése és törlése mostantól ki van javítva, ha https-t használ az összes támogatott böngészőben.
- Kijavítva a hiba, amely miatt Wi-Fi proxy nem menthető, amikor Wi-Fi tulajdonságok felhasználói felületét a **Gépház -> Network & Internet -> Status -> Properties** ről indították.
- Az eSIM-tanúsítványok operációsrendszer-frissítések közötti eltávolításával kapcsolatos probléma megoldása. Ez a javítás biztosítja, hogy az eSIM-tanúsítványok és a kapcsolódó összetevők el is törlődnek a 21H1-es kiadásra való frissítéskor.
- Kijavítottunk egy olyan problémát, amely hatással van az előre telepített alkalmazásokra az operációs rendszer alaphelyzetbe állításakor. 
- Az akkumulátor töltöttségi teljesítménye úgy van behangolva, hogy növelje a futásidőt, amikor nagyobb processzorterheléssel kell töltenie.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. júliusi frissítés
- Build 19041.1157

A frissítés fejlesztései és javításai:

- Eszközportál továbbfejlesztett módszerekkel értesíti az ügyfelet, Fájlkezelő problémákba ütközik a zárolt fájlok megnyitásakor. 
- A fájlok feltöltése, letöltése, átnevezése és törlése mostantól ki van javítva, ha https-t használ az összes támogatott böngészőben.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, 21H1-es verzió – 2021. júniusi frissítés
- Build 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive munkahelyi vagy iskolai kameratekercs feltöltése

A HoloLens 2 Gépház alkalmazáshoz egy új funkciót adtunk hozzá, amely lehetővé teszi az ügyfelek számára, hogy automatikusan feltöltsön vegyes valóságú fényképeket és videókat az eszköz Pictures > Camera Roll mappájába a megfelelő OneDrive for work or school mappába. Ez a funkció a 2. [HoloLens-es](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) OneDrive-alkalmazáson belül egy funkcióbeli rést kijavít, amely csak az ügyfél személyes Microsoft-fiók-fiókjába (és nem a munkahelyi vagy iskolai fiókjába) való automatikus kameratekintéses feltöltést támogatja.

**Működés**

- Látogasson **Gépház > System > Mixed Reality Camera webhelyre** a "Kamera feltöltése" engedélyezéséhez.
- Ennek a funkciónak  a Be állásba való beállításával az eszközön rögzített vegyes valóságú fényképek és videók automatikusan várólistára kerülnek a munkahelyi vagy iskolai OneDrive-fiók Pictures > Camera Roll mappájába való feltöltéshez.
    >[!NOTE]
    >A funkció engedélyezése előtt rögzített  fényképek és videók nem kerülnek a várakozási sorba a feltöltéshez, így manuálisan kell feltölteni őket.
- Az Gépház lapon megjelenő állapotüzenet megjeleníti a függőben lévő feltöltési fájlok számát (vagy elolvassa az "OneDrive naprakész" üzenetet, ha az összes függőben lévő fájl fel lett töltve).
- Ha aggódik a sávszélesség miatt, vagy bármilyen okból "szüneteltetni" szeretné  a feltöltést, a funkciót kikapcsolhatja. A funkció ideiglenes letiltása biztosítja, hogy a feltöltési üzenetsor tovább nő, miközben új fájlokat ad hozzá a Camera Roll mappához, de a fájlok feltöltése addig nem folytatódik, amíg újra nem engedélyezi a funkciót.
- Először a legújabb fájlok lesznek feltöltve (utolsó be, első ki).
- Ha a OneDrive problémát mutat (például a jelszó módosítása után), **megjelenik** a Javítás most gomb a Gépház lapon.
- Nincs maximális fájlméret, de vegye figyelembe, hogy a nagy fájlok feltöltése hosszabb időt fog igénybe venni (különösen akkor, ha a feltöltési sávszélesség korlátozott). Ha egy nagy méretű fájl feltöltése közben szünetelteti vagy kikapcsolja a feltöltést, a részleges feltöltés megmarad. Ha a feltöltés a szüneteltetéstől vagy a kikapcsolástól számított néhány órán belül újra engedélyezve van, a feltöltés onnan folytatódik, ahol azt kikapcsolták. Ha azonban a feltöltés több óra után újra engedélyezve van, a nagyméretű fájl feltöltése az elejétől újraindul.

**Ismert problémák és kikötések**

- Ez a beállítás nem rendelkezik beépített szabályozással az aktuális sávszélesség-használat alapján. Ha egy másik forgatókönyv esetében maximális sávszélességre van szüksége, kapcsolja ki manuálisan a beállítást. A feltöltés fel lesz függesztve, de a funkció továbbra is figyeli az újonnan hozzáadott fájlokat a Camera Roll (Kameratekerés) szolgáltatásban. Engedélyezze újra a feltöltést, ha készen áll a folytatásra.
- Ezt a funkciót engedélyezni kell az eszköz minden felhasználói fiókjához, és csak az eszközre éppen bejelentkezett felhasználó fájljait tudja aktívan feltölteni.
- Ha valós időben készít fényképeket vagy videókat, miközben a Gépház-oldalon figyeli a feltöltések számát, vegye figyelembe, hogy a függőben lévő fájlok száma nem változik, amíg az aktuális fájl feltöltése be nem fejeződik.
- A feltöltés szünetel, ha az eszköz elalszik vagy ki van kapcsolva. Annak érdekében, hogy a függőben lévő feltöltések befejeződtek, aktívan használja az eszközt, amíg a Gépház-oldal el nem olvassa a "OneDrive naprakész" adatokat, vagy módosítsa a **Power & alvó** beállításait.
### <a name="added-support-for-some-telemetry-policies"></a>Bizonyos telemetriai szabályzatok támogatása hozzáadva

A 2. HoloLens következő telemetriai szabályzatok támogatottak:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

A System\AllowTelemetry és a System\ConfigureTelemetryOptInSettingsUx együttes használatával teljes körűen szabályozható a telemetria és a viselkedés az Gépház alkalmazásban.

A frissítés fejlesztései és javításai:
- Javítja a nagyobb videósérüléseket színezéssel.
- Kijavít egy problémát, amely miatt előfordulhat, hogy a Power menüben csonkolt egy szöveg.
- Engedélyezi a RequirePrivateStoreOnly szabályzat támogatását.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. júniusi frissítés
- Build 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>Bizonyos telemetriai szabályzatok támogatása hozzáadva

A 2. HoloLens következő telemetriai szabályzatok támogatottak:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

A System\AllowTelemetry és a System\ConfigureTelemetryOptInSettingsUx együttes használatával teljes körűen szabályozható a telemetria és a viselkedés az Gépház alkalmazásban.

Javasoljuk, hogy próbálja ki a legújabb buildet, Windows Holographic 21H1-es verzióját.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. júniusi frissítés
- Build 18362.1116

A frissítés fejlesztései és javításai:
- Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb buildet, Windows Holographic 21H1-es verzióját.

>[!IMPORTANT]
> Ez a build a továbbiakban nem lesz szervizelt.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, 21H1-es verzió
- Build 20346.1002

Ez a frissítés két célcsoport számára tartalmaz funkciókat; a végfelhasználó által az eszközön bárki által használható funkciók, valamint a rendszergazdák által konfigurálható új eszközkezelési lehetőségek. Az alábbi táblázat az egyes célközönségek számára releváns funkciókat tartalmazza. Ha Ön rendszergazda, tekintse meg a rendszergazdai frissítési [ellenőrzőlistát.](#it-admin---update-checklist)
>[!IMPORTANT]
>A buildre való frissítéshez HoloLens 2 eszköznek jelenleg a 2021. februári frissítést (19041.1136-os build) vagy újabb verziónak kell futnia. Ha nem látja a funkciófrissítést, először frissítse az eszközt, és próbálkozzon újra.

>[!NOTE]
>Jelenleg Microsoft HoloLens 2. verzió a következő kiadások havi karbantartási frissítéseit (hiba- és biztonsági javításokat) támogatja:
>- Windows Holographic, 20H2-es verzió (Build 19041.1128+)
>- Windows Holographic, 2004-es verzió (Build 19041.1103+)
>- Windows Holographic, 1903-as verzió (18362-es vagy újabb build) 
>
> Az Windows Holographic 21H1 verziójának bevezetésével a **Holographic 1903 Windows** havi karbantartási frissítéseit Windows ki. Ez lehetővé teszi, hogy a legújabb kiadásokra összpontosítsunk, és továbbra is értékes fejlesztéseket biztosítsunk. 


| Szolgáltatás neve                                              | Rövid leírás                                                                      | Célközönség | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Új Microsoft Edge](#introducing-the-new-microsoft-edge)  | Az új, Chromium-alapú Microsoft Edge a 2. HoloLens érhető el. | Végfelhasználó | 
[WebXR és 360 Viewer](#webxr-and-360-viewer) | Próbálja ki a magával ragadó webes élményt és a 360 videólejátszást. | Végfelhasználó | 
[Új Gépház alkalmazás](#new-settings-app) | A régi Gépház az alkalmazást egy frissített verzió váltja fel új funkciókkal és beállításokkal. | Végfelhasználó |
[Színkorrektálás megjelenítése](#display-color-calibration) | Válasszon egy alternatív színprofilt a HoloLens 2-es megjelenítéshez. | Végfelhasználó |
[Alapértelmezett alkalmazásválasztó](#default-app-picker) | Válassza ki, hogy melyik alkalmazást indítsa el az egyes fájl- vagy hivatkozástípusokkal. | Végfelhasználó |
[Alkalmazásonkénti kötetvezérlés](#per-app-volume-control) | Az alkalmazásszintű kötet szabályozása a rendszerkötettől függetlenül. | Végfelhasználó |
[Webalkalmazások telepítése](#install-web-apps) | Telepítse a webalkalmazásokat HoloLens 2. Microsoft Office az új Microsoft Edge böngészővel. | Végfelhasználó |
[Pöccintéssel gépeléssel](#swipe-to-type) | Az ujjlenyomata hegyével "pöccintsen" szavakat a holografikus billentyűzeten. | Végfelhasználó |
[Power menu from Start](#power-menu-from-start) | A Start menüben indítsa újra és állítsa le HoloLens eszközt. | Végfelhasználó |
[Több felhasználó szerepel a Bejelentkezési képernyőn](#multiple-users-listed-on-sign-in-screen) | Több felhasználói fiók megjelenítése a Bejelentkezési képernyőn. | Végfelhasználó |
[USB-C külső mikrofon támogatása](#usb-c-external-microphone-support) | Használjon USB-C-mikrofonokat az alkalmazásokhoz és / vagy a Remote Assisthez. | Végfelhasználó |
[Látogatói automatikus bejelentkezés kioszkok számára](#visitor-auto-logon-for-kiosks) | Lehetővé teszi a látogatói fiókokra való automatikus bejelentkezést a kioszkmódokhoz. | Rendszergazdai |
[Új AUMID-k új alkalmazásokhoz Kioszk módban](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMID-ket az Gépház Edge-alkalmazásokhoz. | Rendszergazdai |
[Továbbfejlesztett kioszkmódú hibák kezelésével](#kiosk-mode-behavior-changes-for-handling-of-failures) | A kioszkmód az üres Start menü előtt keres globális hozzárendelt hozzáférést. | Rendszergazdai |
[Új BeállításokURI-k az Gépház láthatósága számára](#new-settings-uris-for-page-settings-visibility) | Több mint 20 új SettingsURI a Gépház/PageVisibilityList szabályzathoz. | Rendszergazdai |
[A Fallback Diagnostics konfigurálása](#configuring-fallback-diagnostics-via-settings-app) | Tartalék diagnosztikai viselkedés beállítása az Gépház alkalmazásban. | Rendszergazdai |
[Dolgok megosztása a közeli eszközökkel](#share-things-with-nearby-devices) | Fájlok vagy URL-címek megosztása HoloLens számítógépekre. | Mind |
[Új operációsrendszer-diagnosztikai nyomkövetések](#new-os-diagnostic-traces) | Új hibaelhárító a Gépház az operációs rendszer frissítéséhez. | Rendszergazdai |
[Kézbesítésoptimalizálás előzetes verzió](#delivery-optimization-preview) | Csökkentse a sávszélesség-használatot több különböző eszközről HoloLens esetén. | Rendszergazdai |

Tekintse meg a kapcsolódó kibocsátási megjegyzéseket:

- [Látogasson el a HoloLens Emulator archívumba](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365-útmutatók](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Az új Microsoft Edge

![Az örökölt embléma Microsoft Edge animációja az új Microsoft Edge emblémára](images/new-edge.gif)

Az új Microsoft Edge a nyílt forráskódú [Chromium,](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) hogy jobb kompatibilitást biztosítsunk az ügyfelek számára, és hogy a webfejlesztők kevesebb töredezettségben használják a webalkalmazásokat.

> [!IMPORTANT]
> Ez az Microsoft Edge automatikusan lecseréli az örökölt Microsoft Edge, [](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) amelyet az új kiadások már nem támogatnak.

![Új Microsoft Edge képernyőkép](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Az új alkalmazás Microsoft Edge

Az új Microsoft Edge ![új Microsoft Edge ikon](images/new_edge_logo.png) A (kék és zöld örlő ikon jelöli) a rendszer a webhivatkozás Start menü automatikusan elindul a webes hivatkozás aktiválásakor.

> [!NOTE]
> Amikor a 2. Microsoft Edge elindítja az új HoloLens, a beállítások és az adatok importálva lesznek az örökölt Microsoft Edge. Ha az új Microsoft Edge elindítása után továbbra is az örökölt Microsoft Edge-t használja, az új adatok nem lesznek szinkronizálva az örökölt Microsoft Edge az új Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Szabályzatbeállítások konfigurálása az új Microsoft Edge

Az új Microsoft Edge a 2. HoloLens böngésző-szabályzatok sokkal szélesebb skáláját kínálja a rendszergazdáknak, mint ami korábban az örökölt Microsoft Edge.

Az új szabályzatbeállítások kezelésével kapcsolatos további információkért íme néhány hasznos Microsoft Edge:

- [A Microsoft Edge beállításainak konfigurálása a Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Microsoft Edge régi verziója szabályzatleképezés Microsoft Edge beállítása](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [A Google Chrome Microsoft Edge szabályzatleképezéshez](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Teljes [Microsoft Edge Enterprise dokumentációja](/deployedge/)

> [!IMPORTANT]
> Az új szabályzatok által támogatott böngésző-szabályzatok Microsoft Edge miatt csapatunk nem tudja garantálni, hogy minden új szabályzat a 2. HoloLens működik. Azonban teszteltük és megerősítettük, mint az Microsoft Edge korábbi Microsoft Edge szabályzatok megfelelőinek megfelelő új HoloLens a vártnak megfelelően működnek. A [Microsoft Edge régi verziója](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) Microsoft Edge szabályzatleképezéssel kapcsolatos további Microsoft Edge-megfelelőjét a 2. HoloLens korábbi Microsoft Edge-szabályzatok mindegyikének megkereséséhez lásd: HoloLens szabályzatleképezés.
>
> Legalább két új szabályzat Microsoft Edge, amelyről tudjuk, hogy *a* 2. HoloLens nem fog működni:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Mire számítsunk a 2. Microsoft Edge új HoloLens után?

Mivel az új Microsoft Edge egy natív Win32-alkalmazás, amely egy új UWP-adapterréteggel rendelkezik, amely lehetővé teszi, hogy csak UWP-eszközökön, például az HoloLens 2-n fusson, előfordulhat, hogy egyes funkciók nem érhetők el azonnal. Az elkövetkező hónapokban új forgatókönyveket és funkciókat fogunk támogatni, ezért ebben a térben naprakész információkat is keres.

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
- Ha egy böngészőablakból ["Kövessen"](hololens2-basic-usage.md#follow-me-stop-following)módban játszik le hangot, a hang továbbra is lejátszásra kerül, ha letiltja a "Követés" módot. A probléma megoldásához leállíthatja a hanglejátszást a "Követés" mód letiltása előtt, vagy bezárhatja az **ablakot az X gombbal.**
- Az aktív alkalmazásablakok Microsoft Edge előfordulhat, hogy más 2D-s alkalmazásablakok váratlanul inaktívvá válnak. Ezeket az ablakokat újraaktiválhatja, ha újra kapcsolatba lép velük.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Belső csatornák

Az Microsoft Edge csapat három előzetes verziójú csatornát tesz elérhetővé az Edge Insider-közösség számára: Béta, Dev és Canary. Az előzetes verziójú csatorna telepítése nem távolítja el a Microsoft Edge kiadását a HoloLens 2-es verziójáról, és egyszerre több is telepíthető. 

Látogasson el [Microsoft Edge Insider kezdőlapjára,](https://www.microsoftedgeinsider.com) ha többet szeretne megtudni az Edge Insider közösségéről. A különböző Edge Insider-csatornákkal kapcsolatos további információkért és az első lépésekért látogasson el az [Edge Insider letöltési oldalára.](https://www.microsoftedgeinsider.com/download)

Az Insider-csatornák több módon is Microsoft Edge a 2 HoloLens való telepítéséhez:

**Közvetlen telepítés az eszközön (jelenleg csak a nem támogatott eszközök számára érhető el)**
  1. A 2. HoloLens oldalon keresse fel az [Edge Insider letöltési oldalát.](https://www.microsoftedgeinsider.com/download)
  1. Válassza **a Download for HoloLens 2 gombot** a telepíteni kívánt Edge Insider-csatornához.
  1. Indítsa el a letöltött .msix fájlt az Edge letöltési üzenetsorból vagy az eszköz "Letöltések" mappájában (a Fájlkezelő).
  1. [Elindul az](app-deploy-app-installer.md) alkalmazástelepítő.
  1. Kattintson a **Telepítés gombra.**
  1. A sikeres telepítés után a Microsoft Edge Beta, Dev vagy Canary külön bejegyzésként Minden alkalmazás **a** Start menü.

**Telepítés számítógéppel Windows Eszközportál [(a](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) fejlesztői módot engedélyezni kell a 2. HoloLens)**
  1. A számítógépen látogasson el az [Edge Insider letöltési oldalára.](https://www.microsoftedgeinsider.com/download)
  1. Kattintson a telepíteni kívánt Edge **Insider-csatorna** "Letöltés Windows 10" gombja melletti legördülő nyílra.
  1. Válassza **HoloLens 2. lehetőséget** a legördülő menüben.
  1. Mentse az .msix fájlt a számítógép "Letöltések" mappájába (vagy egy másik könnyen elérhető mappába).
  1. A [Windows Eszközportál](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) számítógépen a letöltött .msix fájl telepítéséhez használja a HoloLens 2.
  1. A sikeres telepítés után a Microsoft Edge Beta, Dev vagy Canary külön bejegyzésként Minden alkalmazás **a** Start menü.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>A WDAC használata az új Microsoft Edge

Ahhoz, hogy a rendszergazdák a [WDAC-szabályzatot](windows-defender-application-control-wdac.md) frissítve blokkolják az új Microsoft Edge alkalmazást, a következőket kell hozzáadnia a szabályzathoz.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Végpontok kezelése az új Microsoft Edge

Egyes környezetek esetében figyelembe kell venni a hálózati korlátozásokat. Az új Edge zökkenőmentes felhasználói élményének biztosítása érdekében engedélyezze [ezeket a Microsoft-végpontokat.](/deployedge/microsoft-edge-security-endpoints)

További információ a jelenleg elérhető [végpontjairól a HoloLens.](hololens-offline.md)

### <a name="install-web-apps"></a>Webalkalmazások telepítése
 > [!Note]
>A [Windows 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1)verziójától a Office-webalkalmazás már nem lesz előre telepítve.

Az új Edge használatával webalkalmazásokat telepíthet a Microsoft Store mellett. Telepítheti például a Microsoft Office webalkalmazást, hogy megtekintsen és szerkesszen egy vagy SharePoint OneDrive. A webalkalmazás Office a címsorban található Alkalmazás elérhető vagy Office https://www.office.com telepítése gombot.   A **megerősítéshez válassza** a Telepítés lehetőséget.

> [!IMPORTANT]
> Office webalkalmazás funkciói csak akkor érhetők el, ha a HoloLens 2.-es HoloLens rendelkezik aktív internetkapcsolattal.

### <a name="webxr-and-360-viewer"></a>WebXR és 360 Viewer

Az új Microsoft Edge támogatja a WebXR-t, amely a modern webes élmények létrehozásának új szabványa (a WebVR helyett). Számos modern webes élményt a VR szem előtt tartva terveztek (a látómezőt virtuális környezetre cserélik), de ezeket az élményeket a 2. HoloLens is támogatja. A WebXR szabvány kibővített és vegyes valóságú, a fizikai környezetet is használva magával ragadó webes élményt nyújt. Mivel a fejlesztők több időt töltenek a WebXR-sel, arra számítunk, hogy új, kibővített és vegyes valóságú élmények érkeznek majd, HoloLens 2 ügyfél kipróbálhatja!

A 360 Viewer bővítmény a WebXR-re épül, és automatikusan a 2. Microsoft Edge új HoloLens együtt telepíti. Ez a webes bővítmény lehetővé teszi, hogy 360 fokos videókban merüljön el. A YouTube a 360 videó legnagyobb választékát kínálja, ezért javasoljuk, hogy itt kezdje.

#### <a name="how-to-use-webxr"></a>A WebXR használata

1. WebXR-támogatással lépjen egy webhelyre.
1. Válassza az **Enter VR (VR beírása)** gombot a webhelyen. A gomb helye és vizuális megjelenítése webhelyenként eltérő lehet, de a következőre hasonlíthat:

    ![Példa a VR-gombra](images/75px-enter-vr.png)

1. Amikor először próbál webxr-felhasználói élményt indítani egy adott tartományban, a böngésző jóváhagyást kér a modern nézetbe való belépéshez, majd válassza az Allow (Engedélyezése) **lehetőséget.**
1. A [HoloLens 2 kézmozdulattal](hololens2-basic-usage.md#the-hand-tracking-frame) módosíthatja a felhasználói élményt.
1. Ha a felhasználói élményben nincs **Kilépés** gomb, a [Start](hololens2-basic-usage.md#start-gesture) kézmozdulattal térhet vissza.

**Ajánlott WebXR-minták**
- 360 Viewer (lásd a következő szakaszt)
- [XR-ök](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR-Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>A 360 Viewer használata

1. Lépjen egy 360 fokos videóra a YouTube-on.
1. A videókeretben válassza a mixed reality headset gombot:

    ![Gomb a 360 Viewer aktiválásához](images/enter-360-viewer.jpg)

1. Amikor először próbálja elindítani a 360 Viewert egy adott tartományon, a böngésző kérni fogja a beleegyezést a modern nézetbe való belépéshez. Válassza az **Allow (Engedélyezése) lehetőséget.**
1. [Légi koppintással](hololens2-basic-usage.md#select-using-air-tap) hozzuk fel a lejátszásvezérlőket. Használjon [kézi sugarakat](hololens2-basic-usage.md#select-using-air-tap) és légi koppintásokat a lejátszáshoz/szüneteltetéshez, az előre/visszaugráshoz, a feliratok be- és kikapcsol megjelenítéséhez vagy a élmény leállításhoz (ami kilép a modern nézetből). A lejátszásvezérlők néhány másodperc inaktivitás után eltűnnek.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>A WebXR és a 360 Viewer legfontosabb ismert problémái
- A WebXR-élmény összetettségétől függően a képkocka-eszkocka csökkenhet vagy megakhat.
- A WebXR-hez használt kézzel készített alkalmazások támogatása alapértelmezés szerint nincs engedélyezve. A fejlesztők a `edge://flags` "WebXR Hand Input" bekapcsolásával engedélyezhetik a támogatást.
- Előfordulhat, hogy a YouTube-on kívül 360 videó nem a várt módon működik.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Visszajelzés küldése a WebXR-ről és a 360 Viewerről

Ossza meg a visszajelzéseket és  a hibákat a csapatunkkal az új visszajelzés küldése funkció Microsoft Edge.

### <a name="new-settings-app"></a>Új Gépház alkalmazás

Ebben a kiadásban a Gépház új verzióját vezetjük be. Az új Gépház alkalmazás új funkciókat és kibővített beállításokat tartalmaz a HoloLens 2-hez a következő területeken: Hang, Power & sleep, Network & Internet, Alkalmazások, Fiókok, Könnyű kezelés stb.

> [!NOTE]
> Mivel az új Gépház alkalmazás különbözik az örökölt Gépház-alkalmazástól, a Gépház környezetben korábban elhelyezett összes Gépház frissítéskor el lesz távolítva.

![Új Gépház alkalmazás kezdőlapja](images/new-settings-app.png)

**Új funkciók és beállítások**
- Gépház keresés: keressen rá a beállításokra a Gépház a kezdőlapon kulcsszavak vagy a beállítás nevének használatával.
- System > Sound:
  - Bemeneti és kimeneti hangeszközök: egymástól függetlenül válassza ki a bemeneti és kimeneti hangeszközöket (például hanganyagot figyelhet Bluetooth hanganyagokkal, vagy USB-C mikrofont használhat a hangbemenethez).
    > [!NOTE]
    > Bluetooth 2. HoloLens nem támogatja a mikrofonokat.
  - Alkalmazáskötet: az egyes alkalmazások kötetét egymástól függetlenül módosíthatja. Lásd: [alkalmazásonkénti kötetvezérlés.](#per-app-volume-control)
- A > Power &: megadhatja, hogy az eszköz mikor legyen alvó üzemmódban egy bizonyos tétlenség után.
- Rendszer > akkumulátor: manuálisan engedélyezheti az takarékos üzemmód üzemmódot, vagy beállíthatja az akkumulátor töltöttségi küszöbértékét, amely takarékos üzemmód bekapcsolja automatikusan.
- USB> eszközök: alapértelmezés szerint letilthatja az USB-kapcsolatokat.
- Hálózati & internet:
  - Az USB-C Ethernet-adapterek mostantól a Hálózati adapterek & jelennek meg.
  - Elérhetőek az USB-C Ethernet-adapter beállításai, beleértve annak IP-címét is.
  - Mostantól a 2. HoloLens engedélyezheti a repülőgép üzemmódot.
- Alkalmazások: alaphelyzetbe állíthatja a fájl- és hivatkozástípusokhoz használt alapértelmezett alkalmazásokat. További információ: [Alapértelmezett alkalmazásválasztó.](#default-app-picker)
- Fiókok > felhasználók: az eszköztulajdonosok felhasználókat adhatnak hozzá, frissítheti az általános felhasználókat az eszköztulajdonosokra, visszaminősítheti az eszköztulajdonosokat normál felhasználókra, és eltávolíthat felhasználókat.
- Könnyű kezelés: szövegméret és néhány vizuális hatás módosítása.

**Ismert problémák**
- A korábban Gépház windows el lesz távolítva (lásd a fenti megjegyzést).
- A továbbiakban nem nevezheti át az eszközt a Gépház alkalmazással. A rendszergazdák az HoloLens 2 eszköznév-sablonhoz Windows [Autopilot](hololens2-autopilot.md) vagy az MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName csomópont használatával nevezheti át az eszközöket.
- Az Ethernet-oldalon mindig megjelenik egy virtuális Ethernet-eszköz ("UsbNcm").
- Előfordulhat, hogy az új Microsoft Edge akkumulátor-használata az UWP-adapterréteg által támogatott Win32 asztali alkalmazás természetéből adódóan nem pontos (hamarosan nem várható javítás).

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
    > Ha nem látja a halvány jeleneteket a környezetében, manuálisan módosíthatja a HoloLens 2 fényerejét az eszköz bal oldalán található fényerejét jelző gombokkal.
1. Válassza az 1–6. gombot, hogy azonnal kipróbálja az egyes színprofilokat, és keresse meg azt, amely a leginkább hasonlít a szemére (ez általában azt jelenti, hogy a jelenetnek leginkább megfelelő profil jelenik meg a legsemlegesebbnek, a szürkeárnyalatos mintázattal és a vékony tonének pedig az elvárt módon kell megjelennie.)

    ![Színjelenet megjelenítése](images/color-cal-ui.png)
    
1. Ha elégedett a kiválasztott profillal, válassza a **Mentés & Kilépés gombot**
1. Ha nem szeretne módosításokat tenni, válassza a Mégse & **Kilépés** gombot, és a módosítások visszaállnak

> [!TIP]
> A megjelenítési színbeállítás használata során az alábbi tippeket kell szem előtt tartania:
> - A megjelenítési színek színkorrektálását bármikor újra Gépház, amikor csak szeretné
> - Ha az eszközön bárki korábban már használta a színprofilok beállítását, a legutóbbi módosítás dátuma és időpontja megjelenik a Gépház oldalon
> - A megjelenítési színek színkorrektálásának újrafuttatásakor a korábban mentett színprofil ki lesz emelve, és a 0. profil nem jelenik meg (mivel a 0. profil a megjelenítés eredeti színprofilját jelöli)
> - Ha vissza szeretne állítani a megjelenítés eredeti színprofiljára, ezt a Gépház oldalon (lásd a színprofil [alaphelyzetbe](#how-to-reset-color-profile)állítását)

##### <a name="how-to-reset-color-profile"></a>Színprofil alaphelyzetbe állítása 

Ha nem elégedett a 2. HoloLens egyéni színprofillal, visszaállíthatja az eszköz eredeti színprofilját:
1. Indítsa el **a Gépház** alkalmazást, és **navigáljon a System > (Rendszer- és >) lapra.**
1. A **Színkorrektálás megjelenítése alatt** válassza a Visszaállítás alapértelmezett **színprofilra gombot.**
1. Amikor megnyílik a  párbeszédpanel, válassza az Újraindítás lehetőséget, ha készen áll a 2. HoloLens újraindítására, és alkalmazza a módosításokat.

#### <a name="top-display-color-calibration-known-issues"></a>A legjobb megjelenítési színekkel kapcsolatos ismert problémák

- A Gépház lapon az állapotsring, amely a színprofil legutóbbi módosulásának időpontját jelzi, elavult, amíg újra be nem Gépház.
    - Áthidaló megoldás: Válasszon ki egy Gépház, majd válassza újra a Tanúsítvány lapot.

#### <a name="default-app-picker"></a>Alapértelmezett alkalmazásválasztó

Amikor aktivál egy hivatkozást, vagy egynél több telepített alkalmazást tartalmazó fájltípust nyit meg, egy új ablak nyílik meg, amely felszólítja, hogy válassza ki, melyik telepített alkalmazás kezelje a fájl- vagy hivatkozástípust. Ebben az ablakban azt is kiválaszthatja, hogy a kiválasztott alkalmazás kezelje-e az "Egyszer" vagy "Mindig" típusú fájlt vagy hivatkozástípust.

Ha az "Always" (Mindig) lehetőséget választja, de később módosítani szeretné, hogy melyik alkalmazás kezeljen egy adott fájlt vagy hivatkozástípust, visszaállíthatja a mentett alapértelmezett beállításokat a **Gépház > alkalmazásokban.** Görgessen az oldal aljára, és válassza a Clear (Ürítés) gombot a "Default apps for file types" (Alapértelmezett alkalmazások fájltípusokhoz) és/vagy "Default apps for link types" (Alapértelmezett alkalmazások hivatkozástípusokhoz) alatt.  Az asztali számítógépek hasonló beállításától eltérően az egyes alapértelmezett fájltípusokat nem lehet alaphelyzetbe állítani.

#### <a name="per-app-volume-control"></a>Alkalmazásonkénti kötetvezérlés

Ebben a Windows buildben a felhasználók manuálisan módosíthatja az egyes alkalmazások kötetszintjeiket. Így a felhasználók jobban azokra az alkalmazásokra koncentrálnak, amelyekre szükségük van, vagy jobban hallanak több alkalmazás használata esetén. Ilyen lehet például, ha le kell kapcsolni egy alkalmazás mennyiségét, miközben egy másik személy távsegítségért egy másik személy segítségét hívja egy másikban.

Egy adott alkalmazás kötetének beállításhoz lépjen a **Gépház** System Sound elemre, majd a Speciális hangbeállítások alatt válassza az Alkalmazáskötet és az  ->    ->   **eszközbeállítások lehetőséget.**<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Pöccintéssel gépeléssel

Egyes ügyfelek gyorsabban "gépelnek" a virtuális billentyűzeten a begépelni kívánt szó alakjának megformálása által, és ezt a funkciót a holografikus billentyűzet előzetes verziójaként használjuk. Pöccintsen egyszerre egy szót úgy, hogy a holografikus billentyűzet síkján végiglépteti az ujjlenyomata hegyét, elforgatja a szó alakját, majd a billentyűzet síkján megrekedi az ujjlenyomata hegyét. Pöccintéssel anélkül pöccinthet a szavak után, hogy le kellene nyomni a szóközt, ha a szavak között eltávolítja az ujját a billentyűzetről. A funkció akkor működik, ha pöccintéssel követi az ujját a billentyűzeten.

Vegye figyelembe, hogy ez a funkció a holografikus billentyűzet természetéből adódóan nem mindig tud az ujjlenyomatával szembeni ellenállást használni és elsajátítani (ellentétben a mobiltelefonos kijelzővel). 

### <a name="power-menu-from-start"></a>Power menu from Start

Egy új menü, amely lehetővé teszi, hogy a felhasználó kijelentkeztetje, leállítsa és újraindítsa az eszközt. A rendszerfrissítések HoloLens kezdőképernyő jelzi, hogy mikor érhető el a rendszerfrissítés.

#### <a name="how-to-use"></a>Használat

1. Nyissa meg HoloLens kezdőképernyő a [Start kézmozdulattal,](hololens2-basic-usage.md#start-gesture) vagy mondja ki a "Go to Start" (Ugrás az indításhoz) gombra.

2. Figyelje meg a felhasználói profil képe melletti három pont ikont (...):<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Válassza ki a felhasználói profil képét a saját kezűleg vagy a "Power" hangparancs használatával.

4. Megjelenik egy menü, amely az eszköz kijelentkeztet, újraindítható vagy leállítható beállításait tartalmaz:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Válassza ki a menüelemet a regisztrációhoz, az újraindításhoz vagy a HoloLens. Előfordulhat, hogy a Kijelentkezás lehetőség nem érhető el, ha az eszköz egyetlen [Microsoft-fiókhoz (MSA)](hololens-identity.md)vagy helyi fiókhoz van beállítva.

6. A Start kézmozdulattal zárja be a menüt úgy, hogy bárhová Start menü, vagy bezárja a menüt.

#### <a name="update-indicator"></a>Frissítésjelző

Amikor elérhetővé válik egy frissítés, a három pont ikon kigyűjt, jelezve, hogy az újraindítás telepíti a frissítést. A menü beállításai is megváltoznak, hogy tükrözzék a frissítés jelenlétét.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Több felhasználó szerepel a Bejelentkezési képernyőn

Korábban a Bejelentkezés képernyőn csak a legutóbb bejelentkezett felhasználó, valamint az "Egyéb felhasználó" belépési pont jelent meg. Ügyfeleink visszajelzést kaptak arról, hogy ez nem elegendő, ha több felhasználó jelentkezett be az eszközre. Így is újra kellett beírniuk a felhasználónevüket stb.

Az ebben a Windows buildben  bemutatott Más felhasználó lehetőség kiválasztásakor, amely a PIN-kód beviteli mezőtől jobbra található, a Bejelentkezés képernyőn több felhasználó jelenik meg, akik korábban bejelentkeztek az eszközre. Így a felhasználók kiválaszthatják a felhasználói profiljukat, majd a saját hitelesítő Windows Hello bejelentkeznek. A Fiók hozzáadása gombbal új felhasználó is hozzáadható az eszközhöz az Egyéb felhasználók **lapon.**

Az Egyéb felhasználók menü Egyéb felhasználók gombja megjeleníti az eszközre legutóbb bejelentkezett felhasználót. Válassza ezt a gombot a felhasználó bejelentkezési képernyőjére való visszatéréshez.

![Bejelentkezési képernyő alapértelmezése](./images/multiusers1.jpg)

<br>

![Bejelentkezési képernyő – egyéb felhasználók](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C külső mikrofon támogatása

> [!IMPORTANT]
> Az USB-mikrofon csatlakoztatása nem lesz automatikusan beállítva **bemeneti eszközként.** Az USB-C-kábeleket csatlakoztatva a felhasználók azt fogják látni, hogy a hanganyag automatikusan a mikrofonhoz lesz átirányítva, de az HoloLens operációs rendszer a belső mikrofontömböt a többi bemeneti eszköz fölé rangsorítja. **USB-C mikrofon használata érdekében kövesse az alábbi lépéseket.**

A felhasználók a Hangbeállítások panelen választhatnak USB-C-hez csatlakoztatott külső **mikrofonokat.** Az USB-C-mikrofonok hívásra, felvételre stb. használhatók.

Nyissa meg **a Gépház** alkalmazást, és válassza a **System**  >  **Sound lehetőséget.**

![Hang Gépház](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Ha külső mikrofonokat használ a **Remote Assist** segítségével, a felhasználóknak a "Hangeszközök kezelése" hivatkozásra kell kattintanunk.
>
> Ezután a legördülő menüben állítsa a  külső mikrofont Alapértelmezett vagy **Kommunikációs alapértelmezettre.** Az **Alapértelmezett beállítás** azt jelenti, hogy a külső mikrofon mindenhol használatban lesz.
>
> A **Kommunikáció alapértelmezett beállítása** azt jelenti, hogy a külső mikrofon a Remote Assist és más kommunikációs alkalmazásokban lesz használva, de a HoloLens mic tömb továbbra is használható más feladatokhoz.

![Hangeszközök kezelése](images/usbc-mic-2.png)

<br>

![Mikrofon alapértelmezett beállítása](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Mi a helyzet a Bluetooth támogatással?

Sajnos Bluetooth a mikrofonok jelenleg nem támogatottak a 2. HoloLens esetén.

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C mikrofonok hibaelhárítása

Vegye figyelembe, hogy egyes USB-C-mikrofonok helytelenül, mikrofonként és *beszélőként is* jelentik magukat. Ez a mikrofonnal, és nem a HoloLens. Ha ezen mikrofonok valamelyikét csatlakoztatja HoloLens, előfordulhat, hogy a hang elveszett. Szerencsére van egy egyszerű javítás.  

A **Gépház** System Soundban explicit módon állítsa be a beépített beszélők  ->    ->   **(Analog Feature Audio Driver)** alapértelmezett eszközként való **beállítását.** HoloLens akkor is meg kell jegyezni ezt a beállítást, ha a mikrofont eltávolítják, majd később újracsatlakoztatják.

![USB-C-mikrofonok hibaelhárítása](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Látogatói automatikus bejelentkezés kioszkok számára

Ez az új funkció lehetővé teszi a Látogatói fiókokba való automatikus bejelentkezést a kioszkmódokhoz.

Nem AAD-konfiguráció esetén egy eszköz konfigurálása látogatói automatikus bejelentkezéshez:

1. Hozzon létre egy kiépítési csomagot, amely:
    1. Úgy **konfigurálja a Runtime-beállításokat/AssignedAccess-t,** hogy engedélyezze a látogatói fiókokat.
    1. Ha szükséges, regisztrálja az eszközt az MDM-be (Futásidejű **beállítások/Munkahely/Regisztrációk),** hogy később kezelhető legyen.
    1. Ne hozzon létre helyi fiókot
1. [Alkalmazza a kiépítési csomagot.](hololens-provisioning.md)

Az AAD-konfigurációk esetén a felhasználók a maihoz hasonló eredményt érhetnek el a módosítás nélkül. A kioszkmódhoz konfigurált AAD-hez beléptethet egy látogatói fiókot egyetlen gombkoppintással a bejelentkezési képernyőről. Miután bejelentkezett a látogatói fiókba, az eszköz mindaddig nem kéri újra a bejelentkezést, amíg a Látogatót kifejezetten ki nem jelentkezik a Start menüből, vagy újra nem indítják az eszközt.

A látogatói automatikus bejelentkezés egyéni [OMA-URI-szabályzat segítségével](/mem/intune/configuration/custom-settings-windows-10) kezelhető:

- URI-érték: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Szabályzat  | Description   | Konfigurációk  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Lehetővé teszi a látogató számára a kioszkba való automatikus bejelentkezést   | 1 (Igen), 0 (Nem, alapértelmezés.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Az új Gépház Edge-alkalmazások használata kioszkmódban

Amikor alkalmazásokat ad hozzá [a kioszkhoz,](hololens-kiosk.md)a rendszergazda gyakran hozzáadja az alkalmazást a kioszkhoz, de az alkalmazásfelhasználói modell azonosítóját (AUMID) használja. Mivel az Gépház-alkalmazást és az Microsoft Edge-alkalmazást is új alkalmazásnak tekintjük, és eltérnek az ezen alkalmazásokhoz AUMID-t használni képes régebbi alkalmazásoktól, frissíteni kell az új AUMID-t.

Amikor úgy módosít egy kioszkot, hogy az tartalmazza az új alkalmazásokat, javasoljuk, hogy adja hozzá az új AUMID-t, és hagyja meg a régit. Ez egyszerű átállást fog létrehozni, amikor a felhasználók frissítik az operációs rendszert, és nem kell új szabályzatokat kapniuk ahhoz, hogy a kioszkot a kívánt rendeltetésszerűen használják.

| Alkalmazás                    | AUMID (AUMID)                                                  |
|------------------------|--------------------------------------------------------|
| Régi Gépház alkalmazás       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Új Gépház alkalmazás       | BAEAEF15-9CAF-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Régi Microsoft Edge alkalmazás | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Új Microsoft Edge alkalmazás | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>A kioszkmód viselkedésének változásai a hibák kezelésével

A régebbi buildek esetén, ha egy eszköz kioszkkonfigurációval rendelkezik, amely a globális hozzáférés és az AAD-csoporttaghoz rendelt hozzáférés kombinációja is, akkor az AAD-csoporttagság meghatározása sikertelen volt, a felhasználó a["start](hololens-kiosk.md#kiosk-mode-behavior-changes-for-handling-of-failures)menüben semmi sem jelenik meg" jelenik meg.

A jelen Windows kiadástól kezdve a kioszkmód vissza fog állni a globális kioszkkonfigurációhoz (ha van ilyen), ha az AAD-csoport kioszkmódja során hibák lépnek fel.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Új Gépház URI-k az Gépház láthatósághoz

A [Windows Holographic 20H2-es](hololens-release-notes.md#windows-holographic-version-20h2) verziójában hozzáadtunk egy [Gépház/PageVisibilityList szabályzatot,](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) amely korlátozza a Gépház alkalmazásban látható oldalakat. A PageVisibilityList egy olyan szabályzat, amely lehetővé teszi a rendszergazdák számára, hogy megakadályozzák a System Gépház alkalmazás adott lapjainak láthatóságát vagy akadálymentességét, vagy a megadottak kivételével minden oldal esetén ezt teszik meg.

Ha felkeresi [a Page Gépház Visibility](settings-uri-list.md)oldalt, útmutatást talál a CSP használatára és a korábbi kiadásokban elérhető URI-k listájára.

Bővítjük az elérhető URI-k listáját Gépház rendszergazdák által felügyelhető URI-k listáját. Ezen URI-k némelyike az új alkalmazás újonnan elérhető Gépház van. Ha a Gépház/PageVisibilityList szabályzatot használja, tekintse át az alábbi listát, és szükség szerint módosítsa az engedélyezett vagy letiltott oldalakat.

> [!NOTE]
> **Elavult: ms-settings:network-proxy**
>
> Ezekben az újabb buildekben az egyik beállítási oldal elavult. A régi **Hálózati &-proxy** lap már nem érhető el  >   globális beállításként. Az új kapcsolatonkénti proxybeállítások a Network & Internet Wi-Fi Properties (Internetes Wi-Fi-tulajdonságok) vagy   >  Network & Internet Ethernet Properties (Internetes **Ethernet&** tulajdonságai alatt  >     >    >  **találhatók.**

<br>

| Beállítások lap                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Alkalmazások > Alkalmazások & funkciók                               | `ms-settings:appsfeatures`                         |
| Alkalmazások > Alkalmazások & speciális > funkciókkal          | `ms-settings:appsfeatures-app`                     |
| Offline > alkalmazások                                  | `ms-settings:maps`                                 |
| Offline > alkalmazások és > Térképek letöltése                  | `ms-settings:maps-downloadmaps`                    |
| Egérrel > eszközök                                      | `ms-settings:mouse`                                |
| USB> eszközök                                        | `ms-settings:usb`                                  |
| Hálózati & internetes > repülőgép üzemmódban                   | `ms-settings:network-airplanemode`                 |
| Adatvédelmi > általános                                    | `ms-settings:privacy-general`                      |
| Adatvédelem > ink & személyre szabás beírásával             | `ms-settings:privacy-speechtyping`                 |
| Adatvédelmi > Motion                                     | `ms-settings:privacy-motion`                       |
| Adatvédelem > képernyőfelvételek szegélyek                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Adatvédelmi > képernyőképek és alkalmazások                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Rendszer > akkumulátor                                     | `ms-settings:batterysaver`                         |
| Rendszer > akkumulátor                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| System > Sound > App volume and device preferences (Alkalmazáskötet és eszközbeállítások) | `ms-settings:apps-volume`                          |
| System > Sound > Hangeszközök kezelése              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Idő & Language > dátum és & ideje                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| A & biztonsági > visszaállítás & frissítése               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Frissített URI-k

Korábban a következő két URI nem adná meg a felhasználót közvetlenül a megadott oldalakra, csak blokkolta volna a fő frissítésoldalt. A következő elemek úgy frissültek, hogy közvetlenül a saját oldalukra irányulnak:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Tartalék diagnosztika konfigurálása Gépház alkalmazáson keresztül

A Gépház alkalmazásban a felhasználó konfigurálhatja a [Fallback Diagnostics viselkedését.](hololens-diagnostic-logs.md) A beállítás Gépház alkalmazás **Adatvédelmi**  ->  **hibaelhárítás lapjára** navigálva konfigurálhatja ezt a beállítást.

> [!NOTE]
> Ha az eszközhöz MDM-szabályzat van konfigurálva, a felhasználó nem tudja felülbírálni ezt a viselkedést.  

### <a name="share-things-with-nearby-devices"></a>Dolgok megosztása a közeli eszközökkel

Megoszthatja a dolgokat a Windows 10 eszközökkel, beleértve a számítógépeket és a 2 HoloLens eszközöket is. Kipróbálhatja a megosztott Gépház- és URL-címek megosztásához egy HoloLens  ->    ->   számítógép között. További részletekért olvassa el, hogyan oszthat meg dolgokat a közeli eszközökkel a [Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

Ez a szolgáltatás a [Connectivity/AllowConnectedDevices használatával kezelhető.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Új operációsrendszer-diagnosztikai nyomkövetések

A Gépház alkalmazás korábbi hibaelhárítói mellett egy új hibaelhárítót is hozzáadtunk az új Gépház operációsrendszer-frissítésekhez. Lépjen az **Update Security Gépház** troubleshoot Windows Update (Biztonsági  ->  **frissítések &amp;**  >    >  **Windows) lapra,** és válassza az **Indítás lehetőséget.** Ez lehetővé teszi a nyomkövetések gyűjtését az operációsrendszer-frissítésekkel kapcsolatos probléma reprodukálása során, hogy az it-it és a támogatással kapcsolatos hibaelhárítást támaszon ki.

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
- Windows Holographic for Business a HTTP-letöltési módokat és a Microsoft-végpontról [Csatlakoztatott gyorsítótár támogatja;](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) A társközi letöltési módok és csoport-hozzárendelések jelenleg nem támogatottak HoloLens eszközök esetében.
- HoloLens nem támogatja az üzembe helyezést vagy a kézbesítés optimalizálását Windows Server Update Services végpontok esetén.
- A hibaelhárításhoz vagy diagnosztikára van szükség a Csatlakoztatott gyorsítótár-kiszolgálón, vagy nyomkövetést kell gyűjteni a HoloLens-on HoloLens-n Gépház Update & Security Troubleshooting Windows Update (Frissítés &  >  **biztonsági**  >   **hibaelhárítása)**  >   **Windows keresztül.**

### <a name="it-admin---update-checklist"></a>Rendszergazda – Frissítési ellenőrzőlista

Ez az ellenőrzőlista segít az ebben a funkciófrissítésben hozzáadott új elemekről, amelyek hatással lehetnek az aktuális eszközkezelési konfigurációkra vagy az új szolgáltatásokra, amelyek használatba lesznek adva.

#### <a name="updates-to-kiosk-mode"></a>A Kioszkmód frissítései

✔️ Új [**AUMID-k új alkalmazásokhoz Kioszk módban:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Ha korábban az Gépház alkalmazást vagy a Microsoft Edge-alkalmazást egy kioszkban használtuk, ezeket az alkalmazásokat más alkalmazásazonosítót használó új alkalmazásokra cseréljük. Javasoljuk, hogy olvassa el alább az Új [AUMID-k új alkalmazásokhoz kioszkmódban való](#use-the-new-settings-and-edge-apps-in-kiosk-modes) beállítását. Ezzel biztosíthatja, hogy továbbra is a Gépház alkalmazás legyen a Kioszkban, vagy tartalmazza az új Microsoft Edge alkalmazást. Ezeket a módosításokat most már végre lehet helyezni, és az összes eszközön üzembe lehet helyezni, így zökkenőmentesebb a frissítéskor való váltás.

✔️ [**látogatói automatikus bejelentkezés kioszkok számára:**](#visitor-auto-logon-for-kiosks) 

A látogatók mostantól automatikusan bejelentkeztetnek egy kioszkba. Ez a viselkedés alapértelmezés szerint be van kapcsolva, de kezelhető és letiltható.

✔️ [**továbbfejlesztett kioszkmódú hibák kezelésével:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Ha a bejelentkezett AAD-felhasználó AAD-csoporttagságának meghatározása nem sikerült, a rendszer a start menü globális kioszkkonfigurációját használja (ha van), ellenkező esetben a felhasználó üres Start menüt kap. Bár az üres Start menü nem közvetlenül beállítható konfiguráció, ez az új kezelés lehet valami, amely tájékoztatja a támogatási részleget arról, hogy kioszkokat használ-e, mivel ez a konfigurációkra is vonatkozhat, vagy előfordulhat, hogy új módosításokat szeretne végezni a hozzárendelt hozzáférési konfigurációkon.

#### <a name="updates-to-page-settings-visibility"></a>Oldaloldal-Gépház frissítései

✔️ [**lap Gépház URI-k Gépház URI-k**](#new-settings-uris-for-page-settings-visibility)

Ha jelenleg a Page [Gépház láthatóságát](settings-uri-list.md) használja, akkor lehetséges, hogy módosításokat szeretne végezni a meglévő URI-kban, amelyek engedélyezettek vagy blokkolva vannak.

#### <a name="updates-for-your-wdac-policy"></a>A WDAC-szabályzat frissítései
✔️ Ha korábban blokkolja a Microsoft Edge WDAC-n keresztül, frissítenie kell a WDAC-szabályzatot. Tekintse át az alábbiakat, és használja a megadott mintakódot.
#### <a name="enable-new-endpoints-for-edge"></a>Új végpontok engedélyezése az Edge-hez
✔️ Ha olyan infrastruktúrával rendelkezik, amely magában foglalja a hálózati végpontok, például a proxy vagy a tűzfal konfigurálását, engedélyezze ezeket az új végpontokat az új Microsoft Edge számára.

#### <a name="newly-configurable-items"></a>Újonnan konfigurálható elemek

✔️ Tartalék [diagnosztika konfigurálása:](#configuring-fallback-diagnostics-via-settings-app)Beállíthatja, hogy a rendszer gyűjtse-e a tartalék diagnosztikát, és ki.

✔️ Dolgok megosztása a közeli[eszközökkel:](#share-things-with-nearby-devices)Letilthatja az új közeli megosztási funkciót.

✔️ [configuring policy settings for the new Microsoft Edge:](#configuring-policy-settings-for-the-new-microsoft-edge)Review the newly configurations available for Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Új diagnosztikai eszköz

✔️[új operációsrendszer-diagnosztikai nyomkövetések:](#new-os-diagnostic-traces)Az operációs rendszer frissítésével kapcsolatos naplók gyűjtése.

### <a name="improvements-and-fixes-in-the-update"></a>A frissítés fejlesztései és javításai:

- [Az offline diagnosztika](hololens-diagnostic-logs.md#offline-diagnostics) a sorozatszámmal és az operációs rendszer verziójával kapcsolatos további eszközadatokat is tartalmaz.
- Kijavítja az üzletági alkalmazások futásidejű kiépítési csomagokkal történő üzembe helyezéssel kapcsolatos problémát.
- Kijavítja az üzletági alkalmazások telepítési állapotjelentési szolgáltatásával kapcsolatos problémát.
- Kijavít egy problémát, amely az új alkalmazáscsomagok eszköz-visszaállítások közötti megőrzésével kapcsolatban áll fenn.
- Kijavít egy problémát, amely miatt helytelen szimbólumok írhatóak be az Edge-be a japán ügyfelek számára.
- Javítja az operációs rendszer frissítéseinek rugalmasságát az előre telepített alkalmazások, például az Edge körül. 
- A frissítés megbízhatóságát kijavítja, amely hatással van a Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. májusi frissítés
- Build 19041.1146

A frissítés fejlesztései és javításai:
- Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb buildet, Windows Holographic 21H1-es verzióját.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. májusi frissítés
- Build 18362.1110

A frissítés fejlesztései és javításai:
- Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. **Ez a build a továbbiakban nem kap havi szolgáltatásfrissítéseket.** Javasoljuk, hogy próbálja ki a legújabb buildet, Windows Holographic 21H1-es verzióját.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. áprilisi frissítés
- Build 19041.1144

A frissítés fejlesztései és javításai:

- Kijavítja az üzletági alkalmazások telepítési állapotjelentési szolgáltatásával kapcsolatos problémát.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. áprilisi frissítés
- Build 18362.1108

A frissítés fejlesztései és javításai:

- Elhárít egy problémát, Gépház az alkalmazás összeomlik egy helyi fiók jelszavának módosításakor.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. márciusi frissítés
- Build 19041.1140

A frissítés fejlesztései és javításai:

- Azok az ügyfelek, akik az AdvancedPhotoCapture vagy a LowLagPhotoCapture használatával készítettek fényképeket HoloLens 2-es ről, a fénykép rögzítése után legfeljebb 3 másodperccel lekérik a kamerát.
- A Eszközportál szolgáltatás memóriavesztésének kijavítása. A probléma megnövekedett memóriahasználatot okozott a szolgáltatásban, amely miatt más alkalmazások nem foglalták le a memóriát.
- Kijavítottunk egy hibát, amely miatt a szakaszos bevezetésben regisztrált felhasználók nem tudnak bejelentkezni az eszközre.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. márciusi frissítés
- Build 18362.1102

A frissítés fejlesztései és javításai:

- A Eszközportál szolgáltatás memóriavesztésének kijavítása. A probléma megnövekedett memóriahasználatot okozott a szolgáltatásban, amely miatt más alkalmazások nem foglalták le a memóriát.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. februári frissítés
- Build 19041.1136

A frissítés fejlesztései és javításai:

- Kijavítja a kezdeti eszközbeállítással és az alkalmazásfrissítések áruházbeli tárolással kapcsolatban ható problémát.
- Elhárítja a későbbi kiadások frissítésével és járatokkal HoloLens problémát.
- Eltávolítva a nem használt, előre telepített tanúsítványokat az eSIM gyökértárolóból a HoloLens eszközökről.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. februári frissítés
- Build 18362.1098

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb buildeket a Windows Holographic 2004-es verziójához.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. januári frissítés
- Build 19041.1134

A frissítés fejlesztései és javításai:

- Jobb teljesítmény indítás, folytatás és felhasználóváltás során, ha sok felhasználó van az eszközön.
- Arm32-támogatás hozzáadva a [Kutatási módhoz.](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. januári frissítés
- Build 18362.1091

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb buildeket a Windows Holographic 2004-es verziójához.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, 20H2-es verzió – 2020. decemberi frissítés
- Build 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Alkalmazások telepítése a 2. HoloLens a Alkalmazástelepítő

Új **funkcióval (Alkalmazástelepítő)** bővítjük az alkalmazásokat, így zökkenőmentesen telepíthet alkalmazásokat a HoloLens 2 eszközön. A funkció alapértelmezés szerint be lesz kapcsolva a nem **engedélyezett eszközökön.** A vállalatok fennakadásainak elkerülése érdekében az alkalmazástelepítő jelenleg nem lesz elérhető **a felügyelt** eszközökhöz.  

Az eszközök akkor minősülnek "felügyeltnek", ha **az** alábbiak bármelyike igaz:
- Regisztrált [MDM](hololens-enroll-mdm.md)
- Kiépítési [csomaggal konfigurálva](hololens-provisioning.md)
- A [felhasználói identitás](hololens-identity.md) az Azure AD

Most már anélkül telepítheti az alkalmazásokat, hogy engedélyeznie kellene a Fejlesztői módot, vagy engedélyeznie kellene a Eszközportál.  Egyszerűen töltse le (USB-n vagy peremhálózaton keresztül) az Appx-csomagot az eszközre, és navigáljon a Fájlkezelő Appx-csomaghoz, hogy a rendszer a telepítést elindító kérést adja vissza.  Másik [lehetőségként kezdeményezzen telepítést egy weblapról.](/windows/msix/app-installer/installing-windows10-apps-web)  Az Microsoft Store-ból telepített vagy az MDM LOB App Deployment funkcióját használó alkalmazásokhoz hasonló módon az [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) alkalmazásoknak [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) digitálisan alá kell írniuk az aláírási eszközzel, és az HoloLens-eszköznek megbízhatónak kell lennie az aláíráshoz használt tanúsítványban az alkalmazás üzembe helyezése előtt.

**Alkalmazástelepítési utasítások.**

1.  Győződjön meg arról, hogy az eszköz nem minősül felügyeltnek
1.  Győződjön meg arról, HoloLens 2. eszköz be van kapcsolva és csatlakoztatva van a számítógéphez
1.  Győződjön meg arról, hogy be van jelentkezve a HoloLens 2-es eszközre
1.  A számítógépen navigáljon az egyéni alkalmazáshoz, és másolja a yourapp.appxbundle et a yourdevicename\Internal Storage\Downloads mappába.   A fájl másolása után leválaszthatja az eszközt
1.  A 2. HoloLens nyissa meg a Start menüt, válassza a Minden alkalmazás elemet, és indítsa el Fájlkezelő alkalmazást.
1.  Lépjen a Letöltések mappára. Előfordulhat, hogy az alkalmazás bal oldali panelén először az Ez az eszköz lehetőséget kell választania, majd a Letöltések lapra kell navigálnia.
1.  Válassza ki a yourapp.appxbundle fájlt.
1.  A Alkalmazástelepítő meg fog indulni. Az alkalmazás telepítéséhez kattintson a Telepítés gombra.
A telepített alkalmazás a telepítés befejezésekor automatikusan elindul.

A folyamat teszteléséhez [mintaalkalmazásokat Windows univerzális GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) talál.

Olvassa el az alkalmazások [2. HoloLens-re való telepítésének](app-deploy-app-installer.md)teljes folyamatát a Alkalmazástelepítő.  

![MRTK-példák telepítése Alkalmazástelepítő](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>A frissítés fejlesztései és javításai:

- A kézkövetés mostantól számos olyan új esetben fenntartja a nyomkövetést, ahol a korábbi kéz elveszett volna.  Egyes új esetekben csak a pozíció frissül a felhasználó valódi kezében, míg a többit egy korábbi helyzet alapján következtetjük ki.  Ez a változás segít javítani a követési konzisztenciát az olyan mozgások során, mint a dobás, a dobás, a dobás és a klónozás.  Abban az esetben is segít, ha a kéz egy felület közelében van, vagy egy objektumot tart lenyomva.  A kézdiánlék [](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) kikövetkeztetve az egy közös pontossági érték "Hozzávetőleges" értékre lesz állítva a "High" (Magas) helyett.
- Kijavítottunk egy hibát, amely miatt az Azure AD-fiókok PIN-kódját alaphelyzetbe állítva a következő hibaüzenet jelenik meg: "Hiba történt.
- A felhasználóknak sokkal kevesebb indítás utáni OOBE-összeomlást kell látniuk az ET, az Iris gépi alkalmazásból, az új felhasználó vagy az értesítési bejelentések indításakor.
- A felhasználóknak megfelelő időzónának kell lennie az OOBE-val.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, 1903– 2020. decemberi frissítés
- Build 18362.1088

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb Windows Holographic verziót, a 20H2 – 2020. decemberi frissítést és a buildben hozzáadott új Alkalmazástelepítő funkciót.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, 20H2-es verzió
- Build 19041.1128

Windows A holografikus 20H2-es verzió már elérhető, és nagyszerű új funkciókat kínál 2 HoloLens és informatikai szakember számára. Az automatikus szempozíciótól a tanúsítványkezelőn át a Gépház a továbbfejlesztett kioszkmódú funkciókon át az AutoPilot új beállítási képességein át. Ez az új frissítés lehetővé teszi, hogy az it-csapatok részletesebben szabályozni tudjanak a HoloLens konfigurálását és felügyeletét, és még zökkenőmentesebb holografikus élményt kínálnak a felhasználóknak. 

Ez a legújabb kiadás a 2004-es verzió havi frissítése, de ezúttal új funkciókkal is rendelkezik. A fő buildszám változatlan marad, és a Windows Update a 2004-es verzió (19041-es build) havi kiadását jelzi. A Build Number (Buildszám) lap Gépház > About (Információ) képernyőn meggyőződhet arról, hogy a legújabb elérhető 19041.1128-as vagy további buildet nézi. A legújabb kiadásra való frissítéshez nyissa meg a Gépház alkalmazást, nyissa meg az Update & Security (Biztonsági frissítések frissítése) gombra, és koppintson a Frissítések keresése gombra. További információ a frissítések kezeléséhez HoloLens [kezeléséhez: Manage HoloLens updates](hololens-updates.md).

### <a name="whats-new-in-windows-holographic-version-20h2"></a>A Holographic Windows 20H2-es verziójának újdonságai  

| Szolgáltatás                                              | Leírás                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Automatikus szempozíció támogatása](hololens-release-notes.md#auto-eye-position-support) | Aktívan számítja ki a szempozíciókat anélkül, hogy a felhasználók szemkövetésen átesnek.   |
| [Tanúsítványkezelő](hololens-release-notes.md#certificate-manager)   | Lehetővé teszi, hogy az új, egyszerűbb metódusok tanúsítványokat telepítsenek és távolítsanak el Gépház alkalmazásból.     |
| [Automatikus indítású kiépítés USB-ről](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | A csomagok USB-meghajtókon történő kiépítésekor a rendszer automatikusan kéri a kiépítési oldalt az OOBE-ban.                                                         |
| [Kiépítési csomagok automatikus megerősítése az OOBE-ban](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | A kiépítési csomagokat a rendszer automatikusan alkalmazza az OOBE során a kiépítési oldalról.                                                         |
| [Automatikus kiépítés felhasználói felület használata nélkül](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Az automatikus kiépítési automatikus indítás és az automatikus megerősítés kombinálása. |
| [Az Autopilot használata Wi-Fi kapcsolattal](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Használjon Autopilotot Wi-Fi Ethernet-adapter nélkül. |
| [TenantLockdown CSP és Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | A bérlő regisztrálása és a szabályzat alkalmazása után az eszköz csak akkor regisztrálható a bérlőben, amikor alaphelyzetbe áll vagy újra flash(nek) állítva van. |
| [Globális hozzáférés hozzárendelve](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Új konfigurációs módszer több alkalmazásos kioszkmódhoz, amely a teljes kioszkot rendszerszinten alkalmazza, így mindenkire alkalmazható.                  |
| [Alkalmazás automatikus indítása többalkalmazásos kioszkban](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Beállítja, hogy az alkalmazás automatikusan elinduljon, amikor többalkalmazásos kioszkmódba jelentkezik be.                                                        |
| [A kioszkmód viselkedésének változásai a hibák kezelésével](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | A kioszkmód meghibásodása már korlátozó tartalékot is lehetővé tesz.                                                                                                |
| [HoloLens Politikák](hololens-release-notes.md#hololens-policies)                                    | Új szabályzatok a HoloLens.     |
| [Azure AD-csoporttagság gyorsítótárazése offline kioszkhoz](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Az új szabályzat lehetővé teszi a felhasználók számára, hogy csoporttagság-gyorsítótárat használjanak a kioszkmód offline használatára a beállított számú napig.                                        |
| [Új eszközkorlátozási szabályzatok a 2. HoloLens számára](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Az újonnan engedélyezett eszközkezelési szabályzatok a 2. HoloLens engedélyezve.                                                                                |
| [Új energiagazdálkodási szabályzatok a 2. HoloLens számára](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Újonnan támogatott szabályzatok az időtúllépési beállításokhoz.  |
| [Szabályzatok frissítése](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Újonnan engedélyezett szabályzatok, amelyek lehetővé teszik a frissítések vezérlését.           |
| [Engedélyezve Gépház 2. HoloLens lap láthatósága](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Szabályzat az alkalmazásban látható oldalak Gépház meg.             |
| [Kutatási mód](hololens-release-notes.md#research-mode) | Kutatási mód használata a 2. HoloLens esetén. |
| [Rögzítés hosszának megnövelve](hololens-release-notes.md#recording-length-increased) | Az MRC-felvételeket a továbbiakban nem 5 percre korlátozták. |
| [A frissítés fejlesztései és javításai](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | További javítások a frissítésben.   |

### <a name="auto-eye-position-support"></a>Automatikus szempozíció támogatása

A 2 HoloLens szempozíciók lehetővé teszik a pontos hologram-pozíciót, a kényelmes megtekintést és a jobb megjelenítési minőséget. A szempozíciók kiszámítása belsőleg, a szemkövetési számítás részeként történt. Ehhez azonban minden felhasználónak szemkövetést kell követnie, még akkor is, ha a felhasználói élményhez nincs szükség szemre való betekintő adatokra.

**Az automatikus szempozíció (Auto Eye Position, AEP)** lehetővé teszi, hogy ezek a forgatókönyvek interakció nélküli módon számítsák ki a felhasználó szempozícióit. Az Auto Eye Position automatikusan elindul a háttérben, attól kezdve, hogy a felhasználó bekapcsolja az eszközt. Ha a felhasználó még nem rendelkezik előzetes szemkövetési rendszerrel, az Auto Eye Position 20–30 másodperces feldolgozási idő után elkezdi a felhasználó szempozícióját a kijelző rendszer számára. A felhasználói adatok nem maradnak meg az eszközön, ezért ez a folyamat meg lesz ismételve, ha a felhasználó kikapcsolja és újra berakja az eszközt, vagy ha az eszköz újraindul vagy felébreszti az alvó állapotból.

Az Auto Eye Position funkcióval a rendszer viselkedése megváltozik, ha egy nem skálázott felhasználó helyezi el az eszközt. Ebben a kontextusban a nem minősített felhasználó olyanra hivatkozik, aki korábban még nem ment keresztül az eszközön a szemkövetési folyamaton.

| Aktív alkalmazás | Korábbi viselkedés | Viselkedés a holografikus Windows 20H2-es verziójának frissítésével |
|:-------------------|:-----------------|:-----------------------------------|
| Nem tekintetre képes alkalmazás vagy Holographic Shell |Megjelenik a szemkövetési párbeszédpanel. | Nem jelenik meg kérdés. |
| Tekintetre képes alkalmazás | Megjelenik a szemkövetési párbeszédpanel. | A szemkövetési üzenet csak akkor jelenik meg, ha az alkalmazás hozzáfér a tekintetfolyamhoz. |

Ha a felhasználó egy nem tekintetet használó alkalmazásról a tekinteti adatokhoz hozzáférő alkalmazásra tér át, megjelenik a figyelmeztetés. 

Minden más rendszerviselkedés hasonló lesz ahhoz, amikor az aktuális felhasználó nem rendelkezik aktív szemkövetési követéssel. Az egy szándékból indítható indítási kézmozdulat például nem lesz engedélyezve. A kezdeti beállításhoz nem változik az Out-Of-Box-Experience.

A szemre vonatkozó tekinteti adatokat vagy a rendkívül pontos hologrampozíciót igénylő élmények esetén azt javasoljuk, hogy a nem skálázott felhasználók a szemkövetési görbét futtassanak. Elérhető a szemkövetési parancssorból vagy a start menüből a Gépház alkalmazás elindításával, majd a System > > Eye > Run eye illetve a **elemet** választva.

Ezek az információk később más, a-nak [megfelelő adatokat is tartalmaznak.](hololens-calibration.md#auto-eye-position-support) 

### <a name="certificate-manager"></a>Tanúsítványkezelő

- Továbbfejlesztett naplózási, diagnosztikai és érvényesítési eszközök az eszközbiztonság és -megfelelőség érdekében az új Tanúsítványkezelővel. Ez a képesség lehetővé teszi a tanúsítványok kereskedelmi környezetekben való nagy léptékű üzembe helyezését, hibaelhárítását és érvényesítését.

A Windows Holographic 20H2 verzióban egy tanúsítványkezelőt ad hozzá a HoloLens 2 Gépház alkalmazáshoz. Az Update Gépház > Security & certificates (Biztonsági tanúsítványok **frissítése) > meg.** Ez a funkció egyszerű és felhasználóbarát módja a tanúsítványok megtekintésének, telepítésének és eltávolításának az eszközön. Az új Tanúsítványkezelővel a rendszergazdák és a felhasználók továbbfejlesztett naplózási, diagnosztikai és érvényesítési eszközökkel gondoskodnak az eszközök biztonságának és megfelelőségének biztosításáról. 

-   **Naplózás:** A tanúsítvány megfelelő telepítésének ellenőrzése vagy annak ellenőrzése, hogy a tanúsítvány megfelelően lett-e eltávolítva. 
-   **Diagnosztika:** Ha problémák merülnek fel, a megfelelő tanúsítványoknak az eszközön való létezik-e a hitelesítése időt takarít meg, és segít a hibaelhárításban. 
-   **Érvényesítés:** Annak ellenőrzése, hogy a tanúsítvány a kívánt célt szolgálja-e és működik-e, jelentős időt takaríthat meg, különösen kereskedelmi környezetekben, mielőtt nagyobb léptékben helyez üzembe tanúsítványokat.

Ha gyorsan meg kell találnia egy adott tanúsítványt a listában, lehetőség van név, tároló vagy lejárati dátum szerint rendezni. A felhasználók közvetlenül is kereshetnek tanúsítványt. Az egyes tanúsítványtulajdonságok megtekintéséhez jelölje ki a tanúsítványt, majd kattintson az **Információ elemre.** 

A tanúsítványtelepítés jelenleg a .cer és a .crt fájlokat támogatja. Az eszköztulajdonosok a helyi gépen és az aktuális felhasználónál telepíthet tanúsítványokat;  minden más felhasználó csak az Aktuális felhasználóra telepíthető. A felhasználók csak a közvetlenül telepített tanúsítványokat távolítják el a Gépház felhasználói felületről. Ha egy tanúsítvány más módon lett telepítve, ugyanezen mechanizmussal kell eltávolítani.

#### <a name="to-install-a-certificate"></a>Tanúsítvány telepítése: 

1.  Csatlakozás 2 HoloLens számítógépre.
1.  Helyezze a telepíteni kívánt tanúsítványfájlt a 2. HoloLens helyére.
1.  Lépjen a **Gépház App > Update & Security > Certificates**(Tanúsítványok frissítése) lapra, és válassza a Tanúsítvány telepítése lehetőséget.
1.  Kattintson **a Fájl importálása** elemre, és keresse meg a helyet, ahol a tanúsítványt mentette.
1.  Válassza **a Store Location (Áruház helye) lehetőséget.**
1.  Válassza **a Tanúsítványtároló lehetőséget.**
1.  Kattintson az **Install** (Telepítés) gombra.

A tanúsítványnak most már telepítve kell lennie az eszközön.

#### <a name="to-remove-a-certificate"></a>Tanúsítvány eltávolítása: 
1. Lépjen a **Gépház App > Update and Security > Certificates (Tanúsítványok frissítése és >) lapra.**
1. Keresse meg a tanúsítványt név alapján a keresőmezőben.
1. Válassza ki a tanúsítványt.
1. Kattintson az **Eltávolítás gombra.**
1. Ha  a rendszer megerősítést kér, válassza az Igen lehetőséget.

![Tanúsítványmegjelenítő a Gépház alkalmazásban](images/certificate-viewer-device.jpg)

![Kép arról, hogyan használható a tanúsítvány felhasználói felülete egy tanúsítvány telepítéséhez](images/certificate-device-install.jpg)

Ezek az információk később, egy új Tanúsítványkezelő [lapon találhatók.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>Automatikus indítású kiépítés USB-ről

- Automatizált folyamatok, amelyek kevesebb felhasználói beavatkozást lehetővé teszik, ha a kiépítési csomagokkal rendelkező USB-meghajtókat az OOBE során használják.

A kiadás előtt a felhasználóknak manuálisan kellett elindítaniuk a kiépítési képernyőt az OOBE során a kiépítéshez egy gombkombináció használatával. A felhasználók mostantól kihagyhatja a gombkombinációt egy USB-tároló meghajtón található kiépítési csomag használatával. 

1. Csatlakoztassa az USB-meghajtót a kiépítési csomaghoz az OOBE első kezelhető pillanatában
1. Amikor az eszköz készen áll a kiépítésre, az automatikusan megnyitja a kiépítési lapot. 

Megjegyzés: Ha egy USB-meghajtó be van csatlakoztatva az eszköz indítása közben, az OOBE számba veszi a meglévő USB-tárolóeszközt, és figyel a további csatlakoztatott usb-meghajtókra is.

A kiépítési csomagok OOBE során való alkalmazásával kapcsolatos további információkért látogasson el a HoloLens [dokumentációjában.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Az [USB-ről történő](hololens-provisioning.md#auto-launch-provisioning-from-usb) automatikus indítással kapcsolatos további információkat a kiépítési dokumentációban HoloLens találhat.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Kiépítési csomagok automatikus megerősítése az OOBE-ban
- Ha megjelenik a Kiépítési csomag lap, automatikusan alkalmazza az összes felsorolt csomagot, így kevesebb felhasználói beavatkozást lehetővé tevő automatizált folyamat jelenik meg.

Amikor megjelenik a kiépítés főképernyője, az OOBE 10 másodpercig számol, mielőtt automatikusan elkezdi alkalmazni az összes kiépítési csomagot. A felhasználók a [várt](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) csomagok ellenőrzése után 10 másodpercen belül is megerősítheti vagy megszakíthatja a műveletet.

### <a name="automatic-provisioning-without-using-ui"></a>Automatikus kiépítés felhasználói felület használata nélkül
- Kombinált automatikus folyamatok a kiépítés kevesebb eszköz-interakciója érdekében. 

Az USB-eszközökről történő kiépítés automatikus indításának és a kiépítési csomagok automatikus megerősítésének kombinálásával a felhasználók HoloLens 2 eszközt automatikusan kiépíthet az eszköz felhasználói felületének használata nélkül, vagy akár be is használhatja az eszközt. Több eszköz esetében továbbra is használhatja ugyanazt az USB-meghajtót és kiépítési csomagot. Ez akkor hasznos, ha egyszerre több eszközt telepít ugyanazon a területen. 

1. [Hozzon létre egy kiépítési csomagot](hololens-provisioning.md) [Windows Configuration Designer használatával.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Másolja a csomagot egy USB-tároló meghajtójára.
1. [Flash-HoloLens 2-esről](hololens-insider.md#ffu-download-and-flash-directions) [19041.1361-es](https://aka.ms/hololens2previewdownload)vagy újabb buildre. 
1. Ha [az Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) befejezte az eszköz flash (flash) funkcióját, csatlakoztassa az USB-C-kábelt. 
1. Csatlakoztassa az USB-meghajtót az eszközhöz.
1. Amikor a HoloLens 2. eszköz OOBE rendszerindításkor automatikusan észleli a kiépítési csomagot az USB-meghajtón, és elindítja a kiépítési lapot.
1. 10 másodperc elteltével az eszköz automatikusan alkalmazza a kiépítési csomagot. 

Az eszköz konfigurálása megtörtént, és megjelenik a [Sikeres kiépítés képernyő.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### <a name="using-autopilot-with-wi-fi-connection"></a>Az Autopilot használata Wi-Fi kapcsolattal
- Az Ethernet-hez szükséges USB-C adapterek már nem szükségesek a hardverkövetelmények csökkentéséhez azáltal, hogy az Autopilot Wi-Fi csatlakoztatott eszközökön.

Mostantól az OOBE során, miután a 2. HoloLens Wi-Fi-vel csatlakozott, az OOBE egy Autopilot-profilt keres az eszközhöz. Ha talál ilyen igénylést, a program az AAD-beléptetési és -regisztrációs folyamat hátralévő részében ezt fogja végrehajtani. Ez azt jelenti, hogy az Ethernet USB-C vagy Wi-Fi és USB-C adapter között való használata már nem követelmény, de továbbra is működni fognak, ha az OOBE elején meg vannak téve. További információ a 2 eszközre [HoloLens Autopilotról.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP és Autopilot
- Úgy tartja meg a szervezet bérlői eszközeit, hogy az eszköz alaphelyzetbe állításán vagy perjelén keresztül is zárolja őket a bérlőhöz. A további biztonság érdekében a fiók létrehozását a kiépítésen keresztül nem teszi elérhetőre. 

HoloLens 2 eszköz már támogatja a TenantLockdown CSP-t [Windows Holographic 20H2 verziójától.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown (Bérlői zárolás)](/windows/client-management/mdm/tenantlockdown-csp) A CSP lehetővé HoloLens, hogy a 2., csak autopilotot használó MDM-regisztrációhoz legyen kötve. Miután a TenantLockdown CSP RequireNetworkInOOBE csomópontja true (igaz) vagy false (kezdetben beállított) értékre van állítva HoloLens 2-es verzióban, ez az érték megmarad az eszközön az újra flash() vagy operációsrendszer-frissítések stb. ellenére is. 

Ha HoloLens 2. HoloLens TenantLockdown CSP-k RequireNetworkInOOBE csomópontja true (igaz) értékre van állítva, az OOBE határozatlan ideig vár az Autopilot-profil sikeres letöltésére és alkalmazásra a hálózati kapcsolat után. 

Miután a TenantLockdown CSP-k RequireNetworkInOOBE csomópontja igazra van állítva HoloLens 2. HoloLens OOBE-ban a következő műveletek nem engedélyezettek: 
- Helyi felhasználó létrehozása futásidejű kiépítéssel 
- Azure AD-beléptetés végrehajtása futásidejű üzembe építéssel 
- Annak kiválasztása, hogy ki az eszköz a tulajdonában az OOBE felhasználói élményben 

#### <a name="how-to-set-this-using-intune"></a>Hogyan állíthatja be ezt az Intune-nal? 
1. Hozzon létre egy egyéni OMA URI eszközkonfigurációs profilt, és adja meg a true értéket a RequireNetworkInOOBE csomóponthoz az alább látható módon.
Az OMA-URI értékének ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE kell lennie

   > [!div class="mx-imgBorder"]
   > ![Tennant zárolásának beállítása OMA-URI-n keresztül](images/hololens-tenant-lockdown.png)

1. Hozzon létre egy csoportot, és rendelje hozzá az eszközkonfigurációs profilt. 

1. A HoloLens az előző lépésben létrehozott csoport 2. eszköztagját, és indítsa el a szinkronizálást.  

Ellenőrizze az Intune-portálon, hogy az eszközkonfiguráció alkalmazása sikeres volt-e. Miután ez az eszközkonfiguráció sikeresen alkalmazva lett HoloLens 2. eszközön, a TenantLockdown hatása aktív lesz.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>A TenantLockdown RequireNetworkInOOBE szolgáltatásának a 2. HoloLens az Intune használatával való kizárása 
1. Távolítsa el HoloLens 2. adatokat arról az eszközcsoportról, amelyhez korábban hozzárendelték a fent létrehozott eszközkonfigurációt. 

1. Hozzon létre egy egyéni OMA URI-alapú eszközkonfigurációs profilt, és adja meg a false (hamis) értéket a RequireNetworkInOOBE mezőben, ahogy az alább látható. Az OMA-URI értékének ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE kell lennie

   > [!div class="mx-imgBorder"]
   > ![Képernyőkép a RequireNetworkInOOBE hamisra állításával az Intune OMA URI-ján keresztül](images/hololens-tenant-lockdown-false.png)

1. Hozzon létre egy csoportot, és rendelje hozzá az eszközkonfigurációs profilt az eszközcsoporthoz. 

1. A HoloLens az előző lépésben létrehozott csoport 2. eszköztagját, és aktiválja a szinkronizálást.

Ellenőrizze az Intune-portálon, hogy az eszközkonfiguráció alkalmazása sikeres volt-e. Miután ez az eszközkonfiguráció sikeresen alkalmazva lett HoloLens 2. eszközön, a TenantLockdown hatásai inaktívak lesznek. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Mi történne az OOBE során, ha az Autopilot-profil nincs hozzárendelve egy HoloLens a TenantLockdown true (igaz) beállítása után? 
Az OOBE határozatlan ideig vár az Autopilot-profil letöltésére, és megjelenik a következő párbeszédpanel. A TenantLockdown hatásainak eltávolításához az eszközt először az eredeti bérlővel kell regisztrálni az AutoPilot használatával, és a RequireNetworkInOOBE-t az előző lépésben leírtak szerint meg kell szüntetni a TenantLockdown CSP által bevezetett korlátozások eltávolítása előtt. 

![Az eszköz nézetében megtekintheti, hogy mikor van kikényszeríteni a szabályzatot az eszközön.](images/hololens-autopilot-lockdown.png)

Ezek az információk most az Autopilot többi része mellett találhatók a [Tenantlockdown CSP és az AutoPilot alatt.](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)

### <a name="global-assigned-access--kiosk-mode"></a>Globális hozzárendelt hozzáférés – Kioszkmód
- Csökkentett identitáskezelés a kioszkmódban azáltal, hogy engedélyezi az új kioszkmódot, amely rendszerszinten alkalmazza a kioszkmódot.

Ez az új funkció lehetővé teszi, hogy a rendszergazda egy HoloLens 2-es eszközt konfiguráljon több alkalmazás kioszkmódhoz, amely rendszerszinten alkalmazható, nem rendelkezik affinitással semmilyen identitással a rendszeren, és mindenkire érvényes, aki bejelentkezik az eszközre. Az új funkcióról részletesen a globálisan hozzárendelt [HoloLens kioszkban olvashat.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Alkalmazás automatikus indítása többalkalmazásos kioszkmódban 
- Az automatikus alkalmazásindítás célzott felülete, amely tovább növeli a Kioszk módhoz választott felhasználói felület és alkalmazásválasztások számának növelése érdekében.

Csak a többalkalmazásos kioszkmódra vonatkozik, és csak 1 alkalmazás jelölhető ki automatikus indításra a hozzárendelt hozzáférés konfigurációjának alábbi kiemelt attribútumával. 

Az alkalmazás automatikusan elindul, amikor a felhasználó bejelentkezik. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>A kioszkmód viselkedésének változásai a hibák kezelésével
- Biztonságosabb kioszkmód a kioszkmódban elérhető alkalmazások kiküszöbölésével. 

Korábban a kioszkmód alkalmazása során felmerülő hibák HoloLens a Start menüben az összes alkalmazás megjelenik. A Windows Holographic 20H2-es verziójában a hibák esetén nem jelennek meg alkalmazások a Start menüben az alábbiak szerint: 

![Kép a kioszkmódról, ha meghibásodik.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Politikák
- Eszközkezelési lehetőségek kifejezetten HoloLens eszközkezeléshez létrehozott eszközök számára. 

Új vegyes valóságú szabályzatok 2 HoloLens a Holographic 20H2 Windows verziójában. Az új szabályozható beállítások közé tartozik a fényerejének beállítása, a kötet beállítása, a hangfelvételek letiltása vegyes valóságú rögzítések esetén, a diagnosztikai adatok gyűjtésének beállítása és az AAD-csoporttagság gyorsítótára.  

| Új HoloLens szabályzat                                | Leírás                                                                               | Jegyzetek                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | A fényerő gombok letilthatók, így a gomb megnyomása nem módosítja a fényerejét.       | 1 Igen, 0 Nem (alapértelmezett)                                                |
| MixedReality\VolumeButtonDisabled                  | Lehetővé teszi a hangerőszabályzó gombok letiltását, hogy a billentyű lenyomása ne változtassa meg a hangerőt.               | 1 Igen, 0 Nem (alapértelmezett)                                                |
| MixedReality\MicrophoneDisabled                    | Letiltja a mikrofont, így a 2. HoloLens hangrögzítése nem lehetséges.                      | 1 Igen, 0 Nem (alapértelmezett)                                                |
| MixedReality\FallbackDiagnostics                   | A diagnosztikai naplók gyűjtésének viselkedését szabályozza.                               | 0 Letiltva, 1 Engedélyezve az eszköztulajdonosok számára, 2 Engedélyezve mindenki számára (alapértelmezett) |
| MixedReality\HeadTrackingMode                      | Jövőbeli használatra fenntartva.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Azt szabályozza, hogy a rendszer hány napig használja az Azure AD-csoporttagság gyorsítótárát az Azure AD-csoportokat megcélzó kioszkhoz. | Lásd alább.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Azure AD-csoporttagság gyorsítótárazése offline kioszkhoz
- Offline kioszkok használata AAD-csoportokkal akár 60 napig.

Ez a szabályzat szabályozza, hogy hány napig használható az Azure AD-csoporttagság gyorsítótára az Azure AD-csoportokat célzó hozzárendelt hozzáférési konfigurációkhoz a bejelentkezett felhasználók számára. Ha ez a házirend-érték csak 0-snál nagyobb értékre van állítva, akkor a rendszer a gyorsítótárat használja, ellenkező esetben nem.  

Név: AADGroupMembershipCacheValidityInDays URI érték: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Minimum – 0 nap  
Maximum – 60 nap 

A szabályzat megfelelő használatának lépései: 
1. Hozzon létre egy eszközkonfigurációs profilt az Azure AD-csoportokat megcélzó kioszkeszközhöz, és rendelje hozzá HoloLens eszközhöz. 
1. Hozzon létre egy egyéni OMA URI-alapú eszközkonfigurációt, amely a kívánt számú napra állítja be ezt a szabályzatértéket (> 0), és rendelje hozzá HoloLens eszközhöz. 
    1. Az URI értéket a következő OMA-URI szövegmezőben kell megadni: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Az érték az engedélyezett minimális és maximális érték között lehet.
1. Regisztrálja HoloLens eszközöket, és ellenőrizze, hogy mindkét konfiguráció alkalmazva lesz-e az eszközre. 
1. Az Azure AD 1-es felhasználónak be kell jelentkeznie, ha elérhető az internet, amint a felhasználó bejelentkezik, és az Azure AD-csoporttagság sikeres megerősítést nyer, létrejön a gyorsítótár. 
1. Az 1. Azure AD-felhasználó mostantól offline állapotba HoloLens, és kioszkmódhoz használhatja, ha a szabályzat értéke X számú napot tesz lehetővé. 
1. A 4. és az 5. lépés megismételhető bármely más Azure AD-felhasználó N felhasználója számára. Itt az a lényeg, hogy minden Azure AD-felhasználónak be kell jelentkeznie az eszközre az internet használatával, hogy legalább egyszer megállapítsuk, hogy tagja-e annak az Azure AD-csoportnak, amelyhez kioszkkonfiguráció van megcélzva. 
 
> [!NOTE]
> Amíg egy Azure AD-felhasználó esetében végre nem hajtotta a 4. lépést, a "leválasztott" környezetekben hiba lép fel. 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Új eszközkorlátozási szabályzatok a 2. HoloLens számára
- Lehetővé teszi a felhasználók számára bizonyos eszközkezelési szabályzatok kezelését, például a kiépítési csomagok hozzáadásának vagy eltávolításának blokkolását.

Újonnan engedélyezett szabályzatok, amelyek több felügyeleti lehetőséget 2 HoloLens lehetővé. 
- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone (Időzóna konfigurálása)](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

Az AllowAddProvisioningPackage és az AllowRemoveProvisioningPackage két új- és hozzá van adva a [gyakori eszközkorlátozásainkhoz.](hololens-common-device-restrictions.md)

> [!NOTE]
> A [RemoteLock](/windows/client-management/mdm/remotelock-csp)esetében a HoloLens csak a ./Vendor/MSFT/RemoteLock/Lock konfigurációt támogatja. A PIN-kódokkal (például alaphelyzetbe állítással és helyreállítással) kapcsolatos konfigurációk nem támogatottak.

### <a name="new-power-policies-for-hololens-2"></a>Új energiagazdálkodási szabályzatok a 2. HoloLens számára
- További lehetőségek az alvó HoloLens vagy zárolásra energiagazdálkodási szabályzatokkal. 

Ezek az újonnan hozzáadott szabályzatok lehetővé teszik a rendszergazdák számára az energiagazdálkodási állapotban, például az üresjárati időtúllépés szabályozását. Az egyes szabályzatokkal kapcsolatos további információkért kattintson a szabályzatra mutató hivatkozásra.

|     Szabályzatdokumentáció hivatkozása                |     Jegyzetek                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Példaérték az Windows Configuration Designerben való használatra, például`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Példaérték az Windows Configuration Designerben való használatra, például`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Példaérték a Windows Configuration Designerben, például 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Példaérték a Windows Configuration Designerben, például 100                                                                          |
|     [StandbyTimeoutOnBattery (StandbyTimeoutOnBattery)](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Példaérték az Windows Configuration Designerben való használatra, például`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Példaérték az Windows Configuration Designerben való használatra, például`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

A DisplayOffTimeoutOnBattery és a DisplayOffTimeoutPluggedIn két új- és hozzá van adva a [gyakori eszközkorlátozásainkhoz.](hololens-common-device-restrictions.md)

> [!NOTE]
> A 2. HoloLens érdekében győződjön meg arról, hogy a DisplayOffTimeoutOnBattery és a StandbyTimeoutOnBattery értékei is azonosak. Ugyanez vonatkozik a DisplayOffTimeoutPluggedIn és a StandbyTimeoutPluggedIn állapotra. A modern készenléti üzemmóddal kapcsolatos további információkért tekintse meg a Kijelző, alvó és [hibernált](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) inaktív időzítők.

### <a name="newly-enabled-update-policies-for-hololens"></a>Újonnan engedélyezett frissítési szabályzatok HoloLens
- További lehetőségek a frissítések telepítésére vagy a Frissítések szüneteltetése gomb letiltására a frissítések biztosításához.

Ezek a frissítési szabályzatok mostantól engedélyezve vannak HoloLens 2 eszközön:
-   [Frissítés/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

A frissítési szabályzatokkal és az eszközök HoloLens való használatával kapcsolatos részletes információkat itt olvashatja: Manage HoloLens updates (Frissítések [kezelése).](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Engedélyezve Gépház 2. HoloLens lap láthatósága
- Nagyobb felhasználói felületi vezérlés a Gépház alkalmazásban, ami összekeverhető, hogy csak korlátozott számú oldalt mutasson.

Most már engedélyeztünk egy olyan szabályzatot, amely lehetővé teszi a rendszergazdák számára, hogy megakadályozzák a System Gépház-alkalmazás adott lapjainak láthatóvá vagy hozzáférhetővé tétele, vagy hogy ezt a megadott oldalak kivételével minden oldalon meg tudjanak tenni. Ha meg szeretne ismerkedni a funkció teljes testreszabásának mikéntjére, kattintson az alábbi hivatkozásra.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Ha meg szeretne ismerkedni a 2. HoloLens testreszabható oldalbeállításokkal, látogasson el a Gépház [URI-k oldalára.](settings-uri-list.md) 
 
![Képernyőkép a módosított aktív órákról az Gépház alkalmazásban](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Kutatási mód
Kutatási módban a 2. HoloLens a számítógépes látáskutatás eszköze lesz. A korábbi kiadásokhoz képest a Research Mode for HoloLens 2 a következő előnyökkel jár:
-   A HoloLens (1. generációs) kutatási módban elérhető érzékelők mellett mostantól IMU-érzékelői hozzáférést is biztosítunk, beleértve a gyorsulásmérőt, a groscope-t és a kilométermérőt.
-   HoloLens 2. lépés olyan új képességeket biztosít, amelyek a Kutatási móddal együtt használhatók. Pontosabban a kézkövetési és a szemkövetési API-khoz való hozzáférés, amelyek a kísérletek gazdagabb készletét biztosítják.

A kutatók mostantól lehetővé teszik, hogy a HoloLens eszközükön engedélyezzék a research mode (kutatási mód) számára az összes külső, nyers képérzékelő adatfolyamhoz való hozzáférést. A Research Mode for HoloLens 2 a gyorsulásmérő, a groscope és a kilométeróra-mérők eléréséhez is hozzáférést biztosít. A felhasználók adatainak védelme érdekében a nyers szemkövetéses kameraképek nem érhetők el a Research Mode(Kutatási mód) funkción keresztül, a szem-tekintet iránya azonban a meglévő API-kon keresztül érhető el.

További technikai részletekért tekintse meg a [kutatási mód](/windows/mixed-reality/research-mode) dokumentációját.

### <a name="recording-length-increased"></a>Rögzítés hosszának megnövelve
Az ügyfelek visszajelzései miatt növeljük a vegyes valóságú [rögzítések hosszát.](holographic-photos-and-videos.md) A vegyes valóságú rögzítések alapértelmezés szerint nem lesznek 5 percre korlátozva, hanem a maximális rögzítési hosszt számítják ki a rendelkezésre álló lemezterület alapján. Az eszköz a teljes lemezterület 80%-ának megfelelő szabad lemezterület alapján megbecsüli a videófelvétel maximális időtartamát.

> [!NOTE]
> A HoloLens a videófelvétel alapértelmezett hosszát (5 perc) használja, ha a következők valamelyike bekövetkezik:
> - A becsült maximális rögzítési időtartam kisebb, mint az alapértelmezett 5 perc.
> - A rendelkezésre álló lemezterület kevesebb, mint a teljes lemezterület 20%-a.

A teljes követelményeket a holografikus fényképek és [videók dokumentációjában találja.](holographic-photos-and-videos.md#maximum-recording-length) 

### <a name="improvements-and-fixes-in-the-update"></a>A frissítés fejlesztései és javításai:
- Az OOBE több képernyője már sötét módban van.
- További információ: A tartalomnak a legújabb online adatvédelmi nyilatkozatra kell mutasson.
- Elhárítottunk egy problémát, amely miatt a felhasználók nem létesíthették ki a VPN-profilokat a kiépítési csomagokon keresztül.
- Ki van javítva a VPN-kapcsolat proxykonfigurációs problémája.
- Szabályzat frissítve az USB-függvények Enumerálásának letiltásához az MDM for NCM for AllowUsbConnection esetén.
- Elhárítottunk egy problémát, amely miatt egy HoloLens-eszköz nem jelent meg a Fájlkezelő-ban a Media Transfer Protocol (MTP) protokollon keresztül, amikor az eszköz egyalkalmazásos [kioszkként van beállítva.](hololens-kiosk.md) Vegye figyelembe, hogy az MTP (és általában az USB-kapcsolat) továbbra is letiltható az [AllowUSBConnection szabályzattal.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Kijavítottunk egy hibát, amely miatt a Start menü ikonjai megfelelően voltak skálázva Kioszk módban.
- Kijavítottunk egy hibát, amely az Azure AD-csoportokat megcélzó kioszkmódban való HTTP-gyorsítótárazás miatt történt.
- Ki lett javítva az a hiba, amely miatt a felhasználók nem tudtak a Párosítás gombot használni a fejlesztői mód kiépítési csomagokkal való engedélyezése után, kivéve, ha letiltották és újra engedélyezték a Fejlesztői módot.

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

- Elhárít egy problémát, amely Visual Studio megakadályozta az alkalmazások hibakeresését, ha a SupportsMultipleInstances="true" szó jelen van az appxmanifestben.
- Ez a kiadás tartalmazza az NCSI-proxyészlelési javítást, amely a hálózati proxyn keresztüli sikertelen internetes észlelést oldja meg. Az NCSI az internetkapcsolat észleléséhez használhat gépproxyt és profilonkénti proxyt. A későbbi kiadásban az NCSI támogatni fogja a felhasználónkénti proxyt.
- A legtöbb Windows Mixed Reality az előrefelé vezető vektor párhuzamos a talajjal, amikor a felhasználó feje semleges pozícióban van. A 2. HoloLens korábbi verziói azonban úgy igazítják a vektort, hogy az inkább a kijelzőpanelekre legyen rávetülve, amely az ideális tájoláshoz képest néhány fokkal lefelé van dőlve. A 2. HoloLens újabb verziói javították ezt a szemantikai konzisztencia biztosítása érdekében az űrlaptényezők között.
- Továbbfejlesztett kézkövetési robusztusság, amely adott forgatókönyvekben kevesebb nyomkövetési veszteségeket eredményez.
- Ez a kiadás egy javítást tartalmaz a hang-időbélyegző minőségének javításához, amely hozzájárult a videórögzítési problémákhoz.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. szeptemberi frissítés
- Build 18362.1079

A frissítés fejlesztései és javításai:

- A legtöbb Windows Mixed Reality az előrefelé vezető vektor párhuzamos a talajjal, amikor a felhasználó feje semleges pozícióban van. A 2. HoloLens korábbi verziói azonban úgy igazítják a vektort, hogy az inkább a kijelzőpanelekre legyen rávetülve, amely az ideális tájoláshoz képest néhány fokkal lefelé van dőlve. A 2. HoloLens újabb verziói javították ezt a szemantikai konzisztencia biztosítása érdekében az űrlaptényezők között.
- Továbbfejlesztett kézkövetési robusztusság, amely adott forgatókönyvekben kevesebb nyomkövetési veszteségeket eredményez.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, 2004-es verzió – 2020. augusztusi frissítés
- Build 19041.1113

A frissítés fejlesztései és javításai:

- Gépház alkalmazás a továbbiakban nem fogja követni a felhasználót az Írisz-regisztráció vagy a Szemkövetési élmények igénylésében.
- Kijavítottunk egy hibát, amely miatt a kiépítési csomag OOBE során való alkalmazása, amely átnevezi az eszközt, és más műveleteket hajt végre (például egy hálózathoz csatlakozik) az átnevezés miatt nem hajt végre más műveleteket az eszköz újraindítása után.
- Módosított színséma a kezdeti eszközbeállítási folyamatokhoz a vizualizáció minőségének javítása érdekében.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. augusztusi frissítés
- Build 18362.1074

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb buildeket a Windows Holographic 2004-es verziójához.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, 2004-es verzió – 2020. júliusi frissítés
- Build 19041.1109

A frissítés fejlesztései és javításai:

- A fejlesztők mostantól dönthetnek úgy, hogy engedélyezik vagy letiltják a Eszközportál biztonságos kapcsolatot igényelnek.
- Javult az alkalmazások operációsrendszer-frissítések utáni indításának megbízhatósága.
- A beérkezett üzenetek alapértelmezett fényerejét 100%-ra módosítottuk.
- A 2. Windows Eszközportál HTTPS-továbbítással kapcsolatos HoloLens probléma megoldása.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. júliusi frissítés
- Build 18362.1071

A frissítés fejlesztései és javításai:

- Kijavítottunk egy problémát, amely miatt a hologramok eltűnhetnek a Unity-alkalmazásokban a követés elvesztésekor vagy visszaszerzésekor.
- Kijavítottunk egy problémát, amely miatt az HoloLens alkalmazások visszamentek a rendszerhéjba, miközben a HoloLens Emulator egyes eszközökön hardvergyorsítással használják.
- A 2. Windows Eszközportál https-továbbításával kapcsolatos HoloLens probléma megoldása.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, 2004-es verzió – 2020. júniusi frissítés
- Build 19041.1106

A frissítés fejlesztései és javításai:

- Az egyéni MRC-rögzítők mostantól új alapértelmezett értékekkel rendelkeznek bizonyos tulajdonságokhoz, ha nincsenek megadva.
  - On the *MRC Video Effect*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Modern headset))
  - Az *MRC audiohatáson:*
    - LoopbackGain (az aktuális "App Audio Gain" érték Vegyes valóság rögzítése oldalon a Windows Eszközportál)
    - MicrophoneGain (az aktuális "Mic Audio Gain" érték a Vegyes valóság rögzítése oldalán Windows Eszközportál)
- Kijavítottunk egy hibát, amely javította a hangminőséget a vegyes valóságú rögzítési forgatókönyvekben. Pontosabban, ennek a javításnak meg kell szüntetnie a rögzítés hangkisértődései, amikor megjelenik a **Start** menü.
- Továbbfejlesztett hologramstabilitás a rögzített videókban.
- Megoldottuk azt a problémát, amely miatt a vegyes valóságú rögzítés nem tudott videót rögzíteni, miután az eszköz több napig készenléti állapotban volt.
- A HolographicSpace.UserPresence API általában le van tiltva a Unity-alkalmazások esetében. Ez a viselkedés elkerüli azt a problémát, amely miatt egyes alkalmazások szünetelnek a vizor tükrözése esetén, még akkor is, ha a "futtatás a háttérben" beállítás engedélyezve van. Az API most már engedélyezve van a Unity 2018.4.18-as és újabb, valamint 2019.3.4-es és újabb verzióihoz.
- Ha egy Eszközportál kapcsolaton keresztül fér hozzá a Wi-Fi, előfordulhat, hogy egy webböngésző érvénytelen tanúsítvány miatt megakadályozza a hozzáférést. Előfordulhat, hogy a böngésző hibát jelez( például "ERR_SSL_PROTOCOL_ERROR", még akkor is, ha az eszköz tanúsítványa korábban megbízható volt. Ebben az esetben nem tud továbbhaladni a Eszközportál, mivel nincs lehetőség a biztonsági figyelmeztetések figyelmen kívül hagyása. Ez a frissítés megoldotta a problémát. Ha az eszköztanúsítványt korábban letöltötték, és a böngésző biztonsági figyelmeztetései el lett távolítva a számítógépen, és SSL-hiba történik, az új tanúsítványt le kell tölteni, és megbízhatónak kell lennie a böngésző biztonsági figyelmeztetései esetén.
- Lehetővé tette olyan futásidejű kiépítési csomag létrehozása, amely MSIX-csomagok használatával képes alkalmazásokat telepíteni.
- Hozzá van adva egy beállítás **a Gépház** System Hologramok, amely lehetővé teszi a felhasználók számára, hogy az eszköz leállított Mixed Reality minden hologramot automatikusan  >    >   eltávolítsanak a Mixed Reality eszközről.
- Kijavítottunk egy hibát, amely HoloLens, amelyek a képpontformátumukat feketére változtatták a HoloLens emulátorban.
- Kijavítottunk egy hibát, amely összeomlást okozott az Iris-bejelentkezés során.
- Kijavítottunk egy hibát, amely a már meglévő alkalmazások ismételt áruházi letöltésével kapcsolatos.
- Kijavítottunk egy hibát, amely meggátolja, hogy a modern alkalmazások Microsoft Edge meg többször.
- Kijavítottuk a Hibát, amely a Photos alkalmazás indításkor, az 1903-as kiadásból való frissítés után jelent meg.
- Jobb teljesítmény és megbízhatóság.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. júniusi frissítés
- Build 18362.1064

A frissítés fejlesztései és javításai:

- Az egyéni MRC-rögzítők új alapértelmezett értékekkel rendelkeznek bizonyos tulajdonságokhoz, ha nincsenek megadva.
  - Az *MRC videóhatáson:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Modern headset))
  - Az *MRC audiohatáson:*
    - LoopbackGain (az aktuális "App Audio Gain" érték Vegyes valóság rögzítése oldalon a Windows Eszközportál)
    - MicrophoneGain (az aktuális "Mic Audio Gain" érték a Vegyes valóság rögzítése oldalán Windows Eszközportál)
- A HolographicSpace.UserPresence API általában le van tiltva a Unity-alkalmazások esetében. Ez a viselkedés elkerüli azt a problémát, amely miatt egyes alkalmazások szünetelnek a vizor tükrözése esetén, még akkor is, ha a háttérben való futtatás engedélyezve van. Az API most már engedélyezve van a Unity 2018.4.18-as és újabb, valamint 2019.3.4-es és újabb verzióihoz.
- Kijavítottunk egy hibát, amely HoloLens, amelyek a képpontformátumukat feketére változtatták a HoloLens Emulator.
- Kijavítottuk a Photos alkalmazás első indításkor való indításával kapcsolatos hibát az 1903-as kiadásból való frissítés után.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, 2004-es verzió  
- Build – 19041.1103

Az HoloLens 2020. májusi fő szoftverfrissítése, a *Windows Holographic 2004-es* verziója számos izgalmas új képességet tartalmaz, például az Windows Autopilot támogatását, az alkalmazás sötét módját, az USB Ethernet-támogatást az 5G/LTE-elérési pontokhoz stb. A legújabb kiadásra való frissítéshez nyissa meg a Gépház alkalmazást, nyissa meg az Update & Security (Biztonsági frissítések frissítése) lehetőséget, és válassza a Check for Updates (Frissítések    **keresése)** ****   gombot. 

|             Szolgáltatás                              |          Leírás                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Új eszközök előzetes konfigurálása és zökkenőmentes beállítása éles környezetben az AutoPilot Windows használatával                 |
|       FIDO 2-támogatás                             |          A FIDO2 biztonsági kulcsok támogatása a megosztott eszközök gyors és biztonságos hitelesítésének engedélyezéséhez            |
|       Továbbfejlesztett kiépítés                      |          Zökkenőmentesen alkalmazhat kiépítési csomagot egy USB-meghajtóról a HoloLens                              |
|       Alkalmazástelepítés állapota                 |          Ellenőrizze a telepítési állapotot a Gépház alkalmazás MDM-en keresztüli lekért HoloLens 2. alkalmazásba               |
|       Konfigurációszolgáltatók (CSP-k)   |          Új konfigurációs szolgáltatók hozzáadva a rendszergazdai vezérlési képességek javítása érdekében                 |
|       USB 5G/LTE-támogatás                       |          A bővített USB Ethernet-képesség lehetővé teszi az 5G/LTE támogatását                                    |
|       Sötét alkalmazás mód                              |          Sötét alkalmazás mód érhető el a sötét és világos módokat támogató alkalmazásokhoz, ami javítja a megtekintési élményt        |
|       Hangparancsok                             |          További rendszerhangparancsok támogatása a HoloLens vezérléséhez                           |
|       A kézkövetés fejlesztései                 |          A kézkövetés fejlesztései pontosabb gombokat és 2D-s belós interakciókat eredményeznek                        |
|       Minőségi fejlesztések és javítások                 |          Különböző rendszerteljesítményi és megbízhatósági fejlesztések a platformon                            |

### <a name="support-for-windows-autopilot"></a>Az Autopilot Windows támogatása

Windows Az Autopilot for HoloLens 2 lehetővé teszi, hogy az eszköz értékesítési csatornája előre regisztrálja HoloLens Intune-bérlőjébe. Amikor az eszközök megérkeznek, készen állnak a bérlőn megosztott eszközökként való önálló üzembe helyezésre. Az öntelepítés előnyeinek kihasznál érdekében az eszköznek a telepítés első képernyőjén csatlakoznia kell egy hálózathoz egy USB-C-to-Ethernet kapcsolattal.

Miután a felhasználó elindítja az AutoPilot önkiszolgáló üzembe helyezési folyamatát, a folyamat a következő lépéseket teszi:

1. Az eszköz csatlakozása a Azure Active Directory (Azure AD) szolgáltatáshoz.
1. Az Azure AD használatával regisztrálja az eszközt a Microsoft Intune (vagy egy másik MDM-szolgáltatásban).
1. Töltse le az eszközre vonatkozó szabályzatokat, tanúsítványokat és hálózati profilokat.
1. Az eszköz kiépítése.
1. A bejelentkezési képernyőt mutatja be a felhasználónak.

További információ: [Windows Autopilot for HoloLens 2 kiértékelési útmutató.](hololens2-autopilot.md)

*Lépjen kapcsolatba a fiókkezelővel az AutoPilot előzetes verzióhoz való csatlakozáshoz. Az Autopilot-kompatibilis eszközök hamarosan megkezdik a szállítást.*

### <a name="fido2-security-key-support"></a>FIDO2 biztonsági kulcs támogatása

Egyes felhasználók egy HoloLens munkahelyi vagy iskolai környezetben osztják meg az eszköz eszközét. Ezért fontos, hogy a felhasználók könnyedén, hosszú felhasználónév és jelszó beírása nélkül is használhasson. A Fast Identity Online (FIDO) lehetővé teszi, hogy a szervezetben (Azure AD-bérlőn) bárki zökkenőmentesen jelentkezzen be HoloLens felhasználónév vagy jelszó megadása nélkül.

A FIDO2 biztonsági kulcsok egy "unphishable" szabványalapú, jelszó nélküli hitelesítési módszer, amely bármilyen tényezőben elérhető. A FIDO a jelszó nélküli hitelesítés nyílt szabványa. Lehetővé teszi a felhasználók és a szervezetek számára, hogy felhasználónév vagy jelszó nélkül jelentkezzenek be az erőforrásaikba. Ehelyett egy külső biztonsági kulcsot vagy egy eszközbe épített platformkulcsot használnak.

Első lépések: [Jelszó nélküli biztonsági kulcsos bejelentkezés engedélyezése.](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Továbbfejlesztett MDM-regisztráció kiépítési csomagon keresztül

A kiépítési csomagok segítségével konfigurációs HoloLens állíthatja be a konfigurációt, és nem HoloLens a rendszer. Korábban a kiépítési csomagokat át kellett másolni a HoloLens memóriába. Mostantól USB-meghajtón is használhatók, így azok könnyebben újra felhasználhatók több HoloLens eszközön, és az eszközöket párhuzamosan is kiépítheti. A kiépítési csomagok mostantól támogatják az eszközkezelésben való regisztráláshoz szükséges mezőket is, így a kiépítés után nincs szükség manuális telepítésre.

A kipróbálhoz:

1. Töltse le a Windows Configuration Designer legújabb verzióját Windows gépére.
1. Válassza **a Provision HoloLens Devices Provision** HoloLens  >  **2 devices (Eszközök HoloLens kiépítése) lehetőséget.**
2. Készítse el a konfigurációs profilt. Ezután másolja az összes létrehozott fájlt egy USB-C tárolóeszközre.
3. Csatlakoztassa az USB-C eszközt bármely, frissen flash HoloLens. Ezután nyomja le **a hangerőt a** kiépítési csomag  +   alkalmazáshoz.

### <a name="line-of-business-application-install-status"></a>Üzletági alkalmazások telepítési állapota

Az üzletági alkalmazások MDM-alkalmazástelepítése és -kezelése kritikus fontosságú a HoloLens. A rendszergazdáknak és a felhasználóknak meg kell tekinteniük az alkalmazástelepítés állapotát a naplózás és a diagnosztika érdekében. Ebben a kiadásban további részleteket adtunk hozzá **a Gépház** Hozzáférés munkahelyi vagy iskolai fiókhoz lapon Kattintson a  >    >    >  **fiók adatai**  >  **elemre.**

### <a name="additional-csps-and-policies"></a>További CSP-k és szabályzatok

A [konfigurációszolgáltató (CSP)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) az eszköz konfigurációs beállításainak olvasására, beállítására, módosítására vagy törlésére való felület. Ebben a kiadásban további szabályzatok támogatását adjuk hozzá, hogy növeljük a rendszergazdák felügyeletét a telepített HoloLens felett. A hálózati szolgáltatás által támogatott CSP-k [HoloLens: NetworkQoSPolicy CSP.](/windows/client-management/mdm/networkqospolicy-csp)

A kiadás újdonsága:

**Házirendek csp-e** 

A Szabályzatkonfiguráció szolgáltató lehetővé teszi, hogy a vállalat házirendeket konfigurálja Windows eszközökön. Ebben a kiadásban új szabályzatokat adtunk hozzá a HoloLens, amelyek itt vannak felsorolva. További információ: A 2. HoloLens által támogatott [szabályzat-CSP-k.](/windows/client-management/mdm/policies-supported-by-hololens2)  

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

Támogatás lett hozzáadva bizonyos mobilos szélessávú eszközök, például az 5G/LTE-telefonok és Wi-Fi elérési pontok engedélyezéséhez, amikor USB-kapcsolaton keresztül csatlakoznak HoloLens 2. porthoz. Ezek az eszközök mostantól egy másik Ethernet-kapcsolatként **jelennek** meg a hálózati beállítások között. (A külső illesztőt igénylő mobil szélessávú eszközök nem támogatottak.) Ez a funkció nagy sávszélességű kapcsolatokat tesz lehetővé, Wi-Fi nem érhető el, Wi-Fi a Wi-Fi nem elég nagy teljesítményű. További információ a támogatott USB-eszközökről: [Csatlakozás-Bluetooth USB-C-eszközök csatlakoztatása.](hololens-connect-devices.md)  

### <a name="hand-tracking-improvements"></a>A kézkövetés fejlesztései

Ez a kiadás számos kézkövetési fejlesztést tartalmaz:

- **A pontozás stabilitása:** A rendszer most már nem rekedt meg az indexaláék eltolása ellen, amikor a torkok eltoltják. Ez a módosítás javítja a pontosságot a gombok leküldésekor, a begépelésekor, a tartalom görgetésekor és így tovább. 
- **Kevesebb véletlen légi koppintás:** Továbbfejlesztettük a légi koppintás kézmozdulatának észlelését. Számos gyakori forgatókönyvben kevesebb véletlen aktiválás történik, például amikor az oldalára ugrunk.
- **A felhasználói kapcsoló megbízhatósága:** A rendszer mostantól gyorsabb és megbízhatóbb a kézméret frissítésében, amikor megoszt egy eszközt.
- **Kisebb kézlopás:** Továbbfejlesztettük az olyan esetek kezelését, amelyekben kétnél több kéz látható az érzékelőkkel. Ha többen dolgoznak együtt, sokkal kisebb az esélye annak, hogy a nyomon követéses kéz a felhasználótól a jelenetben található valaki más kézhez "ugrik".
- **Rendszer megbízhatósága:** Kijavítottunk egy hibát, amely miatt a kézkövetés leállt, amikor az eszköz nagy terhelés alatt áll.

### <a name="dark-mode"></a>Sötét mód

Számos Windows már támogatja a sötét és a világos módot is. HoloLens 2 felhasználó választhatja ki az alapértelmezett módot a mindkettőt támogató alkalmazásokhoz. A frissítés után az alapértelmezett alkalmazásmód "sötét", de ezt a beállítást egyszerűen módosíthatja: Lépjen a Gépház a Rendszer színei Válassza ki az alapértelmezett  >    >    >  **alkalmazásmódot.** 

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

![Csempés sötét módú ablakok](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Rendszerhangparancsok

Mostantól az eszközön található bármely alkalmazáshoz használhat hangparancsokat. További információ: [Use your voice to operate HoloLens](hololens-cortana.md). Lásd még [a 2. HoloLens támogatott nyelveket.](hololens2-language-support.md)  

### <a name="cortana-updates"></a>Cortana frissítések

A frissített alkalmazás integrálható a Microsoft 365, így több mindent el tud edni az eszközein (jelenleg csak US-English érhető el). A HoloLens 2-es Cortana már nem támogat bizonyos eszközspecifikus parancsokat, például a kötet beállítását vagy az újraindítást. Ezeket a beállításokat mostantól támogatják az új rendszerhangparancsok. Az új alkalmazásról Cortana blogunkban talál [további információt.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>Minőségi fejlesztések és javítások

Fejlesztések és javítások a frissítésben is:  
- Bevezettünk egy aktív megjelenítési megjelenítési rendszert. Ez a funkció javítja a hologramok stabilitását és igazítását. Most már a helyén maradnak, ha a fejét oldalról oldalra mozgatja.
- Kijavítottunk egy hibát, Wi-Fi a HoloLens időnként megszakadt a streamelés. Ha egy alkalmazás azt jelzi, hogy kis késésű streamelésre van szüksége, implementálja a javítást a [SetSocketMediaStreamingMode függvény hívásával.](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)
- Kijavítottunk egy lefagyó eszközt, amely a streamelés közben történt kutatási módban.
- Kijavítottunk egy hibát, amely miatt bizonyos esetekben a megfelelő felhasználó nem jelenik meg a bejelentkezési képernyőn a munkamenet befejezésekor.
- Kijavítottunk egy hibát, amely miatt a felhasználók nem tudtak MDM-naplókat exportálni a **Gépház.**
- Kijavítottunk egy problémát, amely miatt a szemkövetés pontossága a telepítés után a vártnál alacsonyabb lehet.
- Kijavítottunk egy problémát, amely miatt a szemkövetési alrendszer bizonyos körülmények között nem tudta inicializálni vagy végrehajtani a beszigorizálást.
- Kijavítottunk egy problémát, amely miatt a rendszer a már beállított felhasználót kéri a szemredúsztástól.
- Kijavítottunk egy hibát, amely miatt a illesztő összeomlott a szemkontraszt során.
- Kijavítottunk egy hibát, amely miatt a bekapcsológomb ismételt lenyomása 60 másodperces rendszer-időtúllépést és rendszerhéj-összeomlást okozhatott.
- Nagyobb stabilitás a mélységi pufferek számára.
- Hozzáadtunk egy **Megosztás gombot** a Visszajelzési központ hogy a felhasználók könnyebben megosztanának visszajelzéseket.
- Kijavítottunk egy hibát, amely miatt a RoboRaid wan nincs megfelelően telepítve.

### <a name="known-issues"></a>Ismert problémák

- A zh-CN rendszernyelvvel kapcsolatos probléma megakadályozza, hogy a hangparancsok vegyes valóságot rögzítsenek vagy megjelenítsen egy eszköz IP-címét.
- A probléma megoldásához el kell indítania a Cortana alkalmazást, miután elindítja az eszközt a "Hey Cortana" hangaktiválás használatához. Ha egy 18362-es buildről frissített, előfordulhat, hogy a Cortana-alkalmazás előző verziójához egy második alkalmazáscsempét is lát, amely már nem működik a **Start menüben.**

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. májusi frissítés 
- Build 18362.1061

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat, mivel a csapat a Windows Holographic 2004. májusi frissítésén dolgozott a korábban leírtak szerint.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. áprilisi frissítés
- Build 18362.1059

**Sötét mód a támogatott alkalmazásokhoz** 

Számos Windows a sötét és a világos módot is támogatja. HoloLens 2 ügyfél választhatja ki az alapértelmezett módot a mindkét színsémát támogató alkalmazásokhoz. Az ügyfelek visszajelzései alapján az alapértelmezett alkalmazásmódot "sötétre" állítva bármikor módosíthatja ezt a beállítást: Lépjen az **Gépház > System > Colors** oldalra, és keresse meg az "Alapértelmezett alkalmazásmód kiválasztása" **lehetőséget.**

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
- Az Unreal-fejlesztők mostantól a 3D View (3D Eszközportál oldalon tesztelik és hibakeresést végezni az alkalmazásukon.
- Továbbfejlesztett hologramstabilitás vegyes valóságban a *HolographicDepthReprojectionMethod DepthReprojection algoritmus* használata esetén.
- Ki van javítva a "WinRT IStreamSocketListener API-osztály nincs regisztrálva" hiba a 32 bites ARM-alkalmazásokban.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. márciusi frissítés 
- Build 18362.1056

A frissítés fejlesztései és javításai:

- Továbbfejlesztett hologramstabilitás vegyes valóságban a *HolographicDepthReprojectionMethod AutoPlanar* algoritmus használata esetén.
- Gondoskodott róla, hogy a mélységi MF-mintához csatolt koordinátarendszer konzisztens legyen a nyilvános dokumentációval.
- Hatékonyabb fejlesztői hatékonyság, mert lehetővé teszi az ügyfelek számára, hogy nagy mennyiségű szöveget illessnek be az eszközportálon keresztül.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. februári frissítés 
- Build 18362.1053

A frissítés fejlesztései és javításai:

- Ideiglenesen letiltotta a HolographicSpace.UserPresence API-t a Unity-alkalmazásokhoz. Ez a módosítás elkerüli azt a problémát, amely miatt egyes alkalmazások szünetelnek a vizor tükrözése esetén, még akkor is, ha a "futtatás a háttérben" beállítás engedélyezve van.
- Kijavítottunk egy kézi követés által okozott véletlenszerű HUP-összeomlást, amelyben a felhasználó felhasználói felületi lefagyást észlelt, majd néhány másodperc elteltével visszatért a rendszerhéjba.
- Továbbfejlesztett kézkövetés, hogy amikor az indexavacsával omol, az ujjlenyomat felső része kevésbé valószínű, hogy váratlanul megreked.
- Javult a fejkövetés, a térbeli leképezés és más futásidők megbízhatósága.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. januári frissítés 
- Build 18362.1043
 
A frissítés fejlesztései és javításai:

- Nagyobb stabilitás az exkluzív alkalmazások számára a HoloLens 2 emulátor használata során.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, 1903-as verzió – 2019. decemberi frissítés 
- Build 18362.1042

A frissítés fejlesztései és javításai:

- Bevezettük az utolsó fázisú reprodukálás (LSR) javításokat. Továbbfejlesztett vizuális renderelés a hologramok számára, hogy stabilabbnak és stabilabbnak jelenjenek meg, és pontosabban számolják el azok mélységét. Ez a jelenség a frissítés után észrevehetőbb lesz, ha az alkalmazások nem megfelelően állítják be a hologramok mélységét.
- Ki van javítva az exkluzív alkalmazások stabilitása és az kizárólagos alkalmazások közötti navigáció.
- Megoldottunk egy problémát, amely miatt a vegyes valóságú rögzítés nem tudott videót rögzíteni, miután az eszköz több napig készenléti állapotban volt.
- Továbbfejlesztett hologram-stabilitás.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, 1903-as verzió – 2019. novemberi frissítés 
- Build 18362.1039

A frissítés fejlesztései és javításai:

- Ki van javítva a **Hangparancsok** kiválasztása funkció az en-CA és az en-AU kezdeti beállítása során.
- Javult az objektumok vizuális minősége a Unity és az Mixed Reality Toolkit (MRTK) legújabb verzióiban.
- Kijavítottuk az indításkor szüneteltetett állapotban elakadt holografikus alkalmazások problémáinak megoldását, Start menü a rendszer megnyitotta és bezárta.
- Az OpenXR-futásidejű megfelelőség javításai és fejlesztései HoloLens 2. és az emulátor számára.
