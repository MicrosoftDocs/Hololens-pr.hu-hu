---
title: A HoloLens 2 kibocsátási megjegyzései
description: Maradjon naprakész az új HoloLens 2-kiadások frissítéseit.
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
ms.openlocfilehash: 16aec0e60fde40f0a2bffefa871a7a3774b1eb2e
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924536"
---
# <a name="hololens-2-release-notes"></a>A HoloLens 2 kibocsátási megjegyzései

Annak érdekében, hogy a HoloLens-eszközök használata hatékony legyen, továbbra is kiadunk funkciókat, hibákat és biztonsági frissítéseket. Ezen az oldalon láthatja a HoloLens minden hónapban megjelenő újdonságát. A HoloLens 2 legújabb frissítésének [](hololens-update-hololens.md#check-for-updates-and-manually-update) lefutására ellenőrizheti a frissítéseket, és manuálisan frissítheti, vagy lekértheti a teljes flash frissítést (FFU), hogy az Advanced Recovery Companion (Speciális helyreállítás-kísérő) funkcióval flashlje az [eszközt.](hololens-recovery.md#clean-reflash-the-device) A [letöltés](https://aka.ms/hololens2download) naprakész, és a legújabb általánosan elérhető buildet biztosítja.

> [!NOTE]
> A legutóbbi Windows 11-bejelentés a Windows PC-s verziójára összpontosított. 2021 májusában elindítottunk egy jelentős operációsrendszer-frissítést [a](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) HoloLens 2-höz, és az őszre vonatkozó ügyfél-visszajelzések alapján dolgozunk egy hamarosan megjelenő kiadáson.

> [!IMPORTANT]
> A [21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)build egyik ismert problémája miatt, amely a Remote Assist-felhasználókat érinti, jelenleg a Windows Holographic 21H1-es verziójának frissítéseit szüneteltetjük. Módosítottuk az alapértelmezett Advanced Recovery Companion buildet is [a Windows Holographic 20H2 – 2021.](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)júniusi frissítésére, amely a legújabb 20H2-es kiadás.
>
> Bár a probléma hatásának csökkentése érdekében csökkentjük a 21H1 rendelkezésre állását, tisztában vagyunk vele, hogy egyes ügyfelek továbbra is a 21H1-re szeretnék frissíteni. A 21H1-re frissíteni kívánó ügyfelek számára két különböző útvonal érhető el:
>
> - [Regisztrálja az eszköz(öke)t Windows](hololens-insider.md#start-receiving-insider-builds) Insiders-eszközként, és válassza a **Béta csatorna** lehetőséget, amely lehetővé teszi, hogy az eszközök a 21H1-es verzióra frissítsenek, és megbízható buildekkel legyenek felépítve.
> - [Töltse le a legfrissebb FFU-t a számítógépre,](https://aka.ms/hololens2download) majd az Advanced Recovery Companion (Speciális helyreállítás-kísérő) segítségével [flash()](hololens-recovery.md#clean-reflash-the-device)segítségével flash() eszközzel.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, 21H1-es verzió – 2021. júniusi frissítés
- Build 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive munkahelyi vagy iskolai kameratekercs feltöltése

Új funkciót adtunk hozzá a HoloLens 2 Beállítások alkalmazáshoz, amely lehetővé teszi az ügyfelek számára, hogy automatikusan feltöltsön vegyes valóságú fényképeket és videókat az eszköz Pictures > Camera Roll mappájában a megfelelő OneDrive munkahelyi vagy iskolai mappába. Ez Microsoft-fiók a funkció a HoloLens 2 [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) alkalmazásában található szolgáltatásbeli hézagokat elég kijavítani, amely csak az ügyfél személyes tárhelyére (és a munkahelyi vagy iskolai fiókjukba) való automatikus kameratekercs-feltöltést támogatja.

**Működés**

- A **"Kamera feltöltése> funkció** engedélyezéséhez látogasson el > System > Mixed Reality Camera (Kamera feltöltése) lapra.
- Ennek a funkciónak  a Be állásba való beállításával az eszközön rögzített vegyes valóságú fényképek és videók automatikusan várólistára kerülnek a OneDrive munkahelyi vagy iskolai fiókjának Pictures > Camera Roll mappájába való feltöltéshez.
    >[!NOTE]
    >A funkció engedélyezése előtt rögzített  fényképek és videók nem kerülnek a várakozási sorba a feltöltéshez, így manuálisan kell feltölteni őket.
- A Beállítások lapon megjelenő állapotüzenet megjeleníti a függőben lévő fájlok számát (vagy elolvassa a "OneDrive naprakész" állapotot, ha az összes függőben lévő fájl fel lett töltve).
- Ha aggódik a sávszélesség miatt, vagy bármilyen okból "szüneteltetni" szeretné  a feltöltést, a funkciót kikapcsolhatja. A funkció ideiglenes letiltása biztosítja, hogy a feltöltési üzenetsor tovább nő, miközben új fájlokat ad hozzá a Camera Roll mappához, de a fájlok feltöltése addig nem folytatódik, amíg újra nem engedélyezi a funkciót.
- A rendszer először a legújabb fájlokat tölti fel (utolsóként, elsőként ki).
- Ha a OneDrive-fiókjában problémák vannak (például a jelszó módosítása után), megjelenik a Javítás **most** gomb a Beállítások lapon.
- Nincs maximális fájlméret, de vegye figyelembe, hogy a nagy fájlok feltöltése hosszabb időt fog igénybe venni (különösen akkor, ha a feltöltési sávszélesség korlátozott). Ha egy nagy méretű fájl feltöltése közben szünetelteti vagy kikapcsolja a feltöltést, a részleges feltöltés megmarad. Ha a feltöltés a szüneteltetéstől vagy a kikapcsolástól számított néhány órán belül újra engedélyezve van, a feltöltés onnan folytatódik, ahonnan a feltöltést kikapcsolták. Ha azonban a feltöltés több óra után újra engedélyezve van, a nagy méretű fájl feltöltése az elejétől újraindul.

**Ismert problémák és kikötések**

- Ez a beállítás nem rendelkezik beépített szabályozással az aktuális sávszélesség-használat alapján. Ha a sávszélességet maximalizálni kell egy másik forgatókönyvhöz, kapcsolja ki manuálisan a beállítást. A feltöltés fel lesz függesztve, de a funkció továbbra is figyeli a Camera Roll újonnan hozzáadott fájljait. Engedélyezze újra a feltöltést, ha készen áll a folytatásra.
- Ezt a funkciót engedélyezni kell az eszközön lévő összes felhasználói fiókhoz, és csak az eszközre jelenleg bejelentkezett felhasználó fájljait tudja aktívan feltölteni.
- Ha valós időben készít fényképeket vagy videókat, miközben a Beállítások lapon figyeli a feltöltések számát, vegye figyelembe, hogy a függőben lévő fájlok száma nem változik, amíg az aktuális fájl feltöltése be nem fejeződik.
- A feltöltés szünetel, ha az eszköz elalszik vagy ki van kapcsolva. Annak érdekében, hogy a függőben lévő feltöltések befejeződtek, aktívan használja az eszközt, amíg a Beállítások lap el nem olvassa a "OneDrive naprakész" adatokat, vagy módosítsa a **Power & beállításait.**
### <a name="added-support-for-some-telemetry-policies"></a>Bizonyos telemetriai szabályzatok támogatása hozzáadva

A HoloLens 2 mostantól a következő telemetriai szabályzatokat támogatja:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete (Letiltás letiltása)
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

A System\AllowTelemetry és a System\ConfigureTelemetryOptInSettingsUx együttes használatával teljes körűen vezérelni kell a Telemetriát és a viselkedést a Beállítások alkalmazásban.

A frissítés fejlesztései és javításai:
- Javítja a nagyobb videósérüléseket színezéssel.
- Kijavít egy problémát, amely miatt előfordulhat, hogy a Power menüben csonkolt egy szöveg.
- Engedélyezi a RequirePrivateStoreOnly szabályzat támogatását.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. júniusi frissítés
- Build 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>Bizonyos telemetriai szabályzatok támogatása hozzáadva

A HoloLens 2 mostantól a következő telemetriai szabályzatokat támogatja:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete (Letiltás letiltása)
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

A System\AllowTelemetry és a System\ConfigureTelemetryOptInSettingsUx együttes használatával teljes körűen vezérelni kell a Telemetriát és a viselkedést a Beállítások alkalmazásban.

Javasoljuk, hogy próbálja ki a legújabb buildet, a Windows Holographic 21H1-es verzióját.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. júniusi frissítés
- Build 18362.1116

A frissítés fejlesztései és javításai:
- Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb buildet, a Windows Holographic 21H1-es verzióját.

>[!IMPORTANT]
> Ez a build a továbbiakban nem lesz szervizelt.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, 21H1-es verzió
- Build 20346.1002

Ez a frissítés két célcsoport funkcióit tartalmazza; a végfelhasználó által az eszközön bárki által használható funkciók, valamint a rendszergazdák által konfigurálható új eszközkezelési lehetőségek. Az alábbi táblázat az egyes célközönségek számára releváns funkciókat tartalmazza. Ha Ön rendszergazda, tekintse meg a rendszergazdai [frissítési ellenőrzőlistát.](#it-admin---update-checklist)
>[!IMPORTANT]
>A build frissítéséhez a HoloLens 2-eszközöknek jelenleg a 2021. februári frissítést (19041.1136-os build) vagy újabb verziókat kell futniuk. Ha nem látja a funkciófrissítést, először frissítse az eszközt, és próbálkozzon újra.

>[!NOTE]
>Napjainkban Microsoft HoloLens 2. verzió támogatja a havi karbantartási frissítéseket (hiba- és biztonsági javításokat) a következő kiadásokhoz:
>- Windows Holographic, 20H2-es verzió (Build 19041.1128+)
>- Windows Holographic, 2004-es verzió (Build 19041.1103+)
>- Windows Holographic, 1903-as verzió (Build 18362+) 
>
> A Windows Holographic 21H1 verziójának bevezetésével a **Windows Holographic 1903-as** verziójának havi karbantartási frissítéseit is bevezetjük. Ez lehetővé teszi, hogy a legújabb kiadásokra összpontosítsunk, és továbbra is értékes fejlesztéseket biztosítsunk. 


| Szolgáltatás neve                                              | Rövid leírás                                                                      | Célközönség | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Új Microsoft Edge](#introducing-the-new-microsoft-edge)  | Az új, Chromium-alapú Microsoft Edge már elérhető a HoloLens 2-hez. | Végfelhasználó | 
[WebXR és 360 Viewer](#webxr-and-360-viewer) | Próbálja ki a modern webes élményt és a 360 videólejátszást. | Végfelhasználó | 
[Új beállítások alkalmazás](#new-settings-app) | Az örökölt Settings alkalmazást egy frissített verzió váltja fel új funkciókkal és beállításokkal. | Végfelhasználó |
[Színkorrektálás megjelenítése](#display-color-calibration) | Válasszon egy alternatív színprofilt a HoloLens 2-megjelenítéshez. | Végfelhasználó |
[Alapértelmezett alkalmazásválasztó](#default-app-picker) | Válassza ki, hogy melyik alkalmazást indítsa el az egyes fájl- vagy hivatkozástípusokkal. | Végfelhasználó |
[Alkalmazásonkénti kötetvezérlés](#per-app-volume-control) | Az alkalmazásszintű kötet szabályozása a rendszerkötettől függetlenül. | Végfelhasználó |
[Webalkalmazások telepítése](#install-web-apps) | Az új böngészővel telepíthet webalkalmazásokat a HoloLens 2 Microsoft Office, Microsoft Edge telepíthet. | Végfelhasználó |
[Pöccintéssel gépeléssel](#swipe-to-type) | Az ujjlenyomata hegyével "pöccintsen" szavakat a holografikus billentyűzeten. | Végfelhasználó |
[Power menu from Start](#power-menu-from-start) | A Start menüben indítsa újra és állítsa le a HoloLens-eszközt. | Végfelhasználó |
[Több felhasználó szerepel a Bejelentkezési képernyőn](#multiple-users-listed-on-sign-in-screen) | Több felhasználói fiók megjelenítése a Bejelentkezési képernyőn. | Végfelhasználó |
[USB-C külső mikrofon támogatása](#usb-c-external-microphone-support) | Használjon USB-C-mikrofonokat az alkalmazásokhoz és / vagy a Remote Assisthez. | Végfelhasználó |
[Látogatói automatikus bejelentkezés kioszkok számára](#visitor-auto-logon-for-kiosks) | Lehetővé teszi a látogatói fiókokra való automatikus bejelentkezést a kioszkmódokhoz. | Rendszergazdai |
[Új AUMID-k új alkalmazásokhoz Kioszk módban](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | Az új Beállítások és Edge-alkalmazások AUMID-i. | Rendszergazdai |
[Továbbfejlesztett kioszkmódú hibák kezelésével](#kiosk-mode-behavior-changes-for-handling-of-failures) | A kioszkmód az üres Start menü előtt keres globális hozzárendelt hozzáférést. | Rendszergazdai |
[Új beállításokURI-k az oldalbeállítások láthatósága számára](#new-settings-uris-for-page-settings-visibility) | Több mint 20 új SettingsURIs for Settings/PageVisibilityList policy. | Rendszergazdai |
[A Fallback Diagnostics konfigurálása](#configuring-fallback-diagnostics-via-settings-app) | Tartalék diagnosztikai viselkedés beállítása a Beállítások alkalmazásban. | Rendszergazdai |
[Dolgok megosztása a közeli eszközökkel](#share-things-with-nearby-devices) | Fájlok vagy URL-címek megosztása Egy HoloLensből egy számítógépre. | Mind |
[Új operációsrendszer-diagnosztikai nyomkövetések](#new-os-diagnostic-traces) | Új hibaelhárító az operációsrendszer-frissítések beállításaiban. | Rendszergazdai |
[Kézbesítésoptimalizálás előzetes verzió](#delivery-optimization-preview) | Csökkentse a sávszélesség-használatot több HoloLens-eszközről történő letöltések esetén. | Rendszergazdai |

Tekintse meg a kapcsolódó kibocsátási megjegyzéseket:

- [Látogasson el a HoloLens Emulator archívumba](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365-útmutatók](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Az új Microsoft Edge

![Az örökölt embléma Microsoft Edge új embléma Microsoft Edge animációja](images/new-edge.gif)

Az új Microsoft Edge a [Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) nyílt forráskódú projektet, amely jobb kompatibilitást biztosít az ügyfelek számára, és csökkenti a webfejlesztők számára a web töredezettségét.

> [!IMPORTANT]
> Ez az Microsoft Edge automatikusan lecseréli az örökölt Microsoft Edge, amelyet az új kiadások már nem támogatnak. [](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/)

![Új Microsoft Edge képernyőkép](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Az új alkalmazás Microsoft Edge

Az új Microsoft Edge ![új Microsoft Edge ikon](images/new_edge_logo.png) A (kék és zöld örlő ikon jelöli) a rendszer a Start menü a webes hivatkozás aktiválásakor automatikusan elindul.

> [!NOTE]
> Amikor először indítja el az új Microsoft Edge HoloLens 2-ben, a beállítások és az adatok importálva lesznek az örökölt Microsoft Edge. Ha az új Microsoft Edge elindítása után továbbra is az örökölt Microsoft Edge-t használja, az új adatok nem lesznek szinkronizálva az örökölt Microsoft Edge az új Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Szabályzatbeállítások konfigurálása az új Microsoft Edge

Az új Microsoft Edge böngésző-szabályzatok sokkal szélesebb készletét kínálják a rendszergazdáknak a HoloLens 2-ben, mint ami korábban a régi Microsoft Edge.

Az új szabályzatbeállítások kezelésével kapcsolatos további információkért íme néhány hasznos forrás Microsoft Edge:

- [Az Microsoft Edge-szabályzatbeállítások konfigurálása a Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge régi verziója szabályzatleképezés Microsoft Edge beállítása](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [A Google Chrome Microsoft Edge szabályzatleképezéshez](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Teljes [Microsoft Edge Enterprise dokumentációja](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Az új operációs rendszer által támogatott böngésző-szabályzatok Microsoft Edge a csapatunk nem tudja garantálni, hogy minden új szabályzat működik a HoloLens 2-ben. Azonban a HoloLens 2-ben korábban támogatott minden korábbi Microsoft Edge Microsoft Edge szabályzat megfelelőjeként teszteltük és megerősítettük, hogy az új megfelelője a vártnak megfelelően működik. A [Microsoft Edge régi verziója](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) Microsoft Edge-szabályzatleképezéssel kapcsolatos további Microsoft Edge a HoloLens 2-ben használt régi Microsoft Edge-szabályzatok új megfelelőjét találja.
>
> Legalább két új szabályzat Microsoft Edge, amelyről tudjuk, hogy *nem* fognak működni a HoloLens 2-ben:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Mire számítsunk a HoloLens 2-Microsoft Edge újdonságaiból?

Mivel az új Microsoft Edge egy natív Win32-alkalmazás, amely egy új UWP-adapterréteggel rendelkezik, amely lehetővé teszi, hogy csak UWP-eszközökön, például a HoloLens 2-n fusson, előfordulhat, hogy egyes funkciók nem érhetők el azonnal. Az elkövetkező hónapokban új forgatókönyveket és funkciókat fogunk támogatni, ezért ebben a térben naprakész információkat is keres.

**Várható forgatókönyvek és funkciók:**
- Első futtatás, bejelentkezés a profilba és szinkronizálás
- A webhelyeknek a várt módon kell renderelve és viselkedniük
- A legtöbb böngészőfunkciónak (kedvencek, előzmények stb.) a várt módon kell működnie
- Sötét mód
- Webalkalmazások telepítése az eszközre
- Bővítmények telepítése (ha olyan bővítményeket használ, amelyek nem működnek megfelelően a HoloLens 2-ben)
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

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider-csatornák

Az Microsoft Edge csapat három előzetes csatornát tesz elérhetővé az Edge Insider-közösség számára: Béta, Dev és Canary. Az előzetes verziójú csatornák telepítése nem távolítja el a Microsoft Edge kiadott verzióját a HoloLens 2-re, és egyszerre több is telepíthető. 

A [Microsoft Edge Insider kezdőlapján](https://www.microsoftedgeinsider.com) további információt talál az Edge Insider-közösségről. A különböző Edge Insider-csatornákkal kapcsolatos további információkért és az első lépésekért látogasson el az [Edge Insider letöltési oldalára.](https://www.microsoftedgeinsider.com/download)

Az Insider-csatornák a HoloLens 2 Microsoft Edge re való telepítésének több módja is van:

**Közvetlen telepítés az eszközön (jelenleg csak a nem támogatott eszközök számára érhető el)**
  1. A HoloLens 2-ben látogasson el az [Edge Insider letöltési oldalára.](https://www.microsoftedgeinsider.com/download)
  1. Válassza **a Download for HoloLens 2 (Letöltés HoloLens** 2-hez) gombot a telepíteni kívánt Edge Insider-csatornához.
  1. Indítsa el a letöltött .msix fájlt az Edge letöltési üzenetsorból vagy az eszköz "Letöltések" mappájába (a Fájlkezelő).
  1. [Elindul az](app-deploy-app-installer.md) alkalmazástelepítő.
  1. Kattintson a **Telepítés gombra.**
  1. A sikeres telepítés után a Microsoft Edge Beta, Dev vagy Canary külön bejegyzésként Minden alkalmazás a Start menü. 

**Telepítés pc-n Windows eszközportál [(a](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) fejlesztői módot engedélyezni kell a HoloLens 2-n)**
  1. A számítógépen látogasson el az [Edge Insider letöltési oldalára.](https://www.microsoftedgeinsider.com/download)
  1. Válassza a telepíteni kívánt Edge **Insider-csatorna** "Letöltés Windows 10" gombja melletti legördülő nyilat.
  1. A legördülő menüben válassza a **HoloLens 2** lehetőséget.
  1. Mentse az .msix fájlt a számítógép "Letöltések" mappájába (vagy egy másik könnyen elérhető mappába).
  1. A [Windows eszközportál](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) .msix-fájl a HoloLens 2-re való telepítéséhez használja az Windows eszközportál számítógépen.
  1. A sikeres telepítés után a Microsoft Edge Beta, Dev vagy Canary külön bejegyzésként Minden alkalmazás a Start menü. 

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>A WDAC használata az új Microsoft Edge

Ahhoz, hogy a rendszergazdák a [WDAC-szabályzatukat](windows-defender-application-control-wdac.md) frissítve blokkolják az új Microsoft Edge alkalmazást, a következőket kell hozzáadnia a szabályzathoz.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Végpontok kezelése az új Microsoft Edge

Egyes környezetek esetében figyelembe kell venni a hálózati korlátozásokat. Az új Edge zökkenőmentes felhasználói élményének biztosítása érdekében engedélyezze [ezeket a Microsoft-végpontokat.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

További információ a [HoloLens jelenleg elérhető végpontjairól.](hololens-offline.md)

### <a name="install-web-apps"></a>Webalkalmazások telepítése
 > [!Note]
>A [Windows Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójától az Office-webalkalmazás már nem lesz előre telepítve.

Az új Edge használatával webalkalmazásokat telepíthet a Microsoft Store mellett. Telepítheti például a Microsoft Office a SharePointban vagy a OneDrive-ban tárolt fájlok megtekintéséhez és szerkesztéséhez. Az Office-webalkalmazás telepítéséhez keresse fel az Elérhető alkalmazás vagy az Office telepítése gombot a https://www.office.com címsorban.   A **megerősítéshez válassza** a Telepítés lehetőséget.

> [!IMPORTANT]
> Az Office webalkalmazás funkciói csak akkor érhetők el, ha a HoloLens 2 aktív internetkapcsolattal rendelkezik.

### <a name="webxr-and-360-viewer"></a>WebXR és 360 Viewer

Az új Microsoft Edge tartalmazza a WebXR támogatását, amely a modern webes élmények létrehozásának új szabványa (a WebVR helyett). Számos modern webes élményt a VR szem előtt tartva terveztek (a nézetet egy virtuális környezetre cserélik), de ezeket a élményt a HoloLens 2 is támogatja. A WebXR szabvány kibővített és vegyes valóságú, magával ragadó webes élményt tesz lehetővé, amelyek a fizikai környezetet használják. Mivel a fejlesztők több időt töltenek a WebXR-sel, arra számítunk, hogy a HoloLens 2 ügyfeleinek új, kibővített és vegyes valóságú élmények várhatók!

A 360 Viewer bővítmény a WebXR-re épül, és automatikusan együtt telepíthető az új Microsoft Edge HoloLens 2-ben. Ez a webes bővítmény lehetővé teszi, hogy 360 fokos videókban merüljön el. A YouTube a 360 videó közül kínálja a legnagyobb választékot, ezért javasoljuk, hogy ott kezdje.

#### <a name="how-to-use-webxr"></a>A WebXR használata

1. WebXR-támogatással lépjen egy webhelyre.
1. Válassza az **Enter VR (VR beírása)** gombot a webhelyen. A gomb helye és vizuális megjelenítése webhelyenként eltérő lehet, de a következőre hasonlíthat:

    ![Példa VR-gomb beírása](images/75px-enter-vr.png)

1. Amikor először próbál webxr-élményt elindítani egy adott tartományon, a böngésző jóváhagyást kér a modern nézetbe való belépéshez, és válassza az **Allow (Engedélyezése) lehetőséget.**
1. A [HoloLens 2 kézmozdulatokkal módosíthatja](hololens2-basic-usage.md#the-hand-tracking-frame) a felhasználói élményt.
1. Ha a felhasználói élmény  nem rendelkezik Kilépés gombbal, a Start kézmozdulattal [térhet](hololens2-basic-usage.md#start-gesture) vissza a kezdőlapra.

**Ajánlott WebXR-minták**
- 360 Viewer (lásd a következő szakaszt)
- [XR-ök](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>A 360 Viewer használata

1. Lépjen egy 360 fokos videóra a YouTube-on.
1. A videókeretben válassza a vegyes valóságú headset gombot:

    ![A 360 Viewer aktiválása gomb](images/enter-360-viewer.jpg)

1. Amikor először próbálja elindítani a 360 Viewert egy adott tartományon, a böngésző beleegyezést kér a modern nézetbe való belépéshez. Válassza az **Allow (Engedélyezése) lehetőséget.**
1. [Légi koppintással](hololens2-basic-usage.md#select-using-air-tap) hozzuk fel a lejátszásvezérlőket. Használjon [kézi sugarakat](hololens2-basic-usage.md#select-using-air-tap) és légi koppintásokat a lejátszáshoz/szüneteltetéshez, a továbbítás/visszaugrás, a feliratok be- és kikapcsolása vagy a felhasználói élmény leállítása érdekében (ami kilép a modern nézetből). A lejátszásvezérlők néhány másodperc inaktivitás után eltűnnek.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>A WebXR és a 360 Viewer legfontosabb ismert problémái
- A WebXR-élmény összetettségétől függően a képkocka- és képkocka-méret csökkenhet vagy megakhat.
- A WebXR-hez a kézzel készített kéz támogatása alapértelmezés szerint nincs engedélyezve. A fejlesztők a `edge://flags` "WebXR Hand Input" bekapcsolásával engedélyezhetik a támogatást.
- Előfordulhat, hogy a YouTube-on kívül 360 videó nem a várt módon működik.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Visszajelzés küldése a WebXR-ről és a 360 Viewerről

Ossza meg csapatával a visszajelzéseket és a hibákat az új rendszer Visszajelzés küldése Microsoft Edge. 

### <a name="new-settings-app"></a>Új beállítások alkalmazás

Ebben a kiadásban a Settings alkalmazás új verzióját mutatjuk be. Az új Beállítások alkalmazás új funkciókat és kibővített beállításokat tartalmaz a HoloLens 2-hez a következő területeken: Hang, Power & sleep, Network & Internet, Alkalmazások, Fiókok, Könnyű kezelés stb.

> [!NOTE]
> Mivel az új Beállítások alkalmazás különbözik az örökölt Beállítások alkalmazástól, a környezetben korábban elhelyezett beállítások ablakai frissítéskor el lesznek távolítva.

![Új beállítások alkalmazás kezdőlapja](images/new-settings-app.png)

**Új funkciók és beállítások**
- Beállítások keresése: kulcsszavak vagy a beállítás nevének használatával keressen rá a beállításokra a Beállítások kezdőlapján.
- System > Sound:
  - Bemeneti és kimeneti hangeszközök: egymástól függetlenül válassza ki a bemeneti és kimeneti hangeszközöket (például Bluetooth-kábelen keresztüli hanglejátszást vagy USB-C mikrofont használjon a hangbemenethez).
    > [!NOTE]
    > A HoloLens 2 nem támogatja a Bluetooth-mikrofonokat.
  - Alkalmazáskötet: az egyes alkalmazások kötetének egymástól független beállítása. Lásd: [alkalmazáskötet-vezérlőnként.](#per-app-volume-control)
- A > Power &: megadhatja, hogy az eszköz mikor alvó üzemmódba ússzanak egy bizonyos tétlenség után.
- Rendszer > Akkumulátor: manuálisan engedélyezze az takarékos üzemmód üzemmódot, vagy állítson be egy akkumulátor-küszöbértéket, amely takarékos üzemmód bekapcsolja automatikusan.
- USB> eszközök: alapértelmezés szerint letilthatja az USB-kapcsolatokat.
- Hálózati & internet:
  - Az USB-C Ethernet-adapterek mostantól megjelennek a Hálózati adapterek & interneten.
  - Az USB-C Ethernet-adapter beállításai már elérhetők, beleértve annak IP-címét is.
  - Mostantól engedélyezheti a repülőgépes üzemmódot a HoloLens 2-ben.
- Alkalmazások: alaphelyzetbe állíthatja a fájl- és hivatkozástípusokhoz használt alapértelmezett alkalmazásokat. További információ: [Alapértelmezett alkalmazásválasztó.](#default-app-picker)
- Fiókok > felhasználók: az eszköztulajdonosok felhasználókat adhatnak hozzá, frissítheti az általános felhasználókat az eszköztulajdonosokra, visszaminősítheti az eszköztulajdonosokat normál felhasználókra, és eltávolíthat felhasználókat.
- Könnyű kezelés: szövegméret és néhány vizuális hatás módosítása.

**Ismert problémák**
- A korábban elhelyezett Beállítások ablakokat a rendszer eltávolítja (lásd a fenti megjegyzést).
- A Továbbiakban nem nevezheti át az eszközt a Beállítások alkalmazással. A rendszergazdák a [Windows Autopilot for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) eszköznévsablon vagy az MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName csomópont használatával nevezheti át az eszközöket.
- Az Ethernet-oldalon mindig megjelenik egy virtuális Ethernet-eszköz ("UsbNcm").
- Az új hálózati adapterek Microsoft Edge nem biztos, hogy pontosak, mivel az UWP-adapterréteg által támogatott Win32 asztali alkalmazás (hamarosan nem várható javítás).

#### <a name="display-color-calibration"></a>Színkorrektálás megjelenítése



Ezzel az új beállítással alternatív színprofilt választhat a HoloLens 2-megjelenítéshez. Ez segíthet a színek pontosabb megjelenítésében, különösen alacsonyabb megjelenítési fényerejénél. A színkorrektálás megjelenítése a Beállítások alkalmazásban, a Rendszerbeállítások lapon > található.

> [!NOTE]
> Mivel ez a beállítás új színprofilt ment a megjelenítési belső vezérlőprogramba, ez egy eszközönkénti beállítás (és nem az egyes felhasználói fiókok egyedi beállítása).

##### <a name="how-to-use-display-color-calibration"></a>A megjelenítési színek színezésének használata

1. Indítsa el **a Beállítások** alkalmazást, és lépjen a System > **És elemre.**
1. A **Színkorrektálás megjelenítése alatt** válassza a Megjelenítés **színkorrektálás gombját.**
1. Elindul a színekkel való megjelenítés élménye, és arra bátorítja, hogy győződjön meg arról, hogy a vizor a megfelelő helyen van.
1. Az utasítási párbeszédpanelek megnyitása után a kijelző automatikusan 30%-os fényerejére halványul.
    > [!TIP]
    > Ha nem látja a halvány jeleneteket a környezetében, manuálisan módosíthatja a HoloLens 2 fényerejét az eszköz bal oldalán található világítási gombokkal.
1. Válassza az 1–6. gombot, hogy azonnal kipróbálja az egyes színprofilokat, és keresse meg azt, amely a leginkább hasonlít a szemére (ez általában azt jelenti, hogy a profil, amely segít a jelenetnek a legsemlegesebbnek megjelenni, a szürke skálázási mintával és a hajszínszínekkel a vártnak megfelelően jelenik meg.)

    ![Színjelenet megjelenítése](images/color-cal-ui.png)
    
1. Ha elégedett a kiválasztott profillal, válassza a **Save & Exit (Kilépés)** gombot
1. Ha nem szeretne módosításokat tenni, válassza a Mégse & **Kilépés** gombot, és a módosítások vissza lesznek állva

> [!TIP]
> Íme néhány hasznos tipp, amely a megjelenítési színek színbeállításának használata során hasznos lehet:
> - Ha szeretné, újra futtathatja a beállítások megjelenítési színbeállítását
> - Ha az eszközről valaki korábban már használta a beállítást a színprofilok módosításához, a legutóbbi módosítás dátuma és időpontja megjelenik a Beállítások lapon.
> - Amikor újra futtatja a megjelenítési színek színkiszínezését, a korábban mentett színprofil ki lesz emelve, és a 0. profil nem jelenik meg (mivel a 0. profil a megjelenítés eredeti színprofilját jelöli)
> - Ha vissza szeretne állítani a megjelenítés eredeti színprofiljára, ezt a Beállítások lapon használhatja (lásd a színprofil alaphelyzetbe [állítását)](#how-to-reset-color-profile)

##### <a name="how-to-reset-color-profile"></a>Színprofil alaphelyzetbe állítása 

Ha nem elégedett a HoloLens 2-ben mentett egyéni színprofillal, visszaállíthatja az eszköz eredeti színprofilját:
1. Indítsa el **a Beállítások** alkalmazást, és lépjen a System > **És elemre.**
1. A **Színkorrektálás megjelenítése alatt** válassza a Visszaállítás alapértelmezett **színprofilra gombot.**
1. Amikor megnyílik a párbeszédpanel, válassza **az** Újraindítás lehetőséget, ha készen áll a HoloLens 2 újraindítására és a módosítások alkalmazására.

#### <a name="top-display-color-calibration-known-issues"></a>A legjobb megjelenítési színekkel kapcsolatos ismert problémák

- A Beállítások lapon az állapotsring, amely a színprofil legutóbbi módosításának időpontját jelzi, elavult lesz, amíg újra be nem tölti a Beállítások lapot.
    - Áthidaló megoldás: Válasszon ki egy másik Beállítások lapot, majd válassza újra a Hibabeesés lapot.

#### <a name="default-app-picker"></a>Alapértelmezett alkalmazásválasztó

Amikor aktivál egy hivatkozást, vagy egynél több telepített alkalmazást tartalmazó fájltípust nyit meg, egy új ablak nyílik meg, amely arra kéri, hogy válassza ki, melyik telepített alkalmazás kezelje a fájl- vagy hivatkozástípust. Ebben az ablakban azt is kiválaszthatja, hogy a kiválasztott alkalmazás kezelje-e az "Egyszer" vagy "Mindig" hivatkozástípust.

Ha az "Always" (Mindig) lehetőséget választja, de később módosítani szeretné, hogy melyik alkalmazás kezeljen egy adott fájlt vagy hivatkozástípust, visszaállíthatja a mentett alapértelmezett beállításokat a **Beállítások > Alkalmazások lapon.** Görgessen az oldal aljára, és válassza a Clear (Ürítés) gombot az "Alapértelmezett alkalmazások fájltípusokhoz" és/vagy "Default apps for link types" (Alapértelmezett alkalmazások hivatkozástípusokhoz) alatt.  Az asztali számítógépek hasonló beállításával ellentétben az egyes fájltípusokat nem lehet alaphelyzetbe állítani.

#### <a name="per-app-volume-control"></a>Alkalmazásonkénti kötetvezérlés

Ebben a Windows-buildben a felhasználók manuálisan módosíthatjják az egyes alkalmazások kötetszintjeiket. Így a felhasználók jobban azokra az alkalmazásokra koncentrálnak, amelyekre szükségük van, vagy jobban hallanak több alkalmazás használata esetén. Például le kell kapcsolni egy alkalmazás mennyiségét, miközben egy másik személyt hív meg távsegítségért egy másikban.

Egy adott alkalmazás kötetének beállításhoz lépjen a **Beállítások** Rendszerhang elemre, majd a Speciális hangbeállítások alatt válassza az  ->    ->  Alkalmazáskötet és **az eszközbeállítások lehetőséget.**<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Pöccintés a begépelhez

Egyes ügyfelek gyorsabban "gépelnek" a virtuális billentyűzeten a begépelni kívánt szó alakjának megformálása által, és ezt a funkciót a holografikus billentyűzethez megtekintjük. Pöccintsen egyszerre egy szót úgy, hogy a holografikus billentyűzet síkján végiglépteti az ujjlenyomata hegyét, megpöccinti a szó alakját, majd a billentyűzetsíkról megfedi az ujjlenyomata hegyét. Pöccintéssel nyomon követő szavakat pöccinthet anélkül, hogy le kellene nyomni a szóközt úgy, hogy a szavak között eltávolítja az ujját a billentyűzetről. A funkció akkor működik, ha pöccintés nyomát látja az ujjlenyomata billentyűzeten való mozgása után.

Vegye figyelembe, hogy ez a funkció a holografikus billentyűzet természetéből adódóan nem mindig tud az ujjlenyomatával szemben ellenállást használni (ellentétben a mobiltelefonos kijelzővel). 

### <a name="power-menu-from-start"></a>A Power menü a Start menüből

Új menü, amely lehetővé teszi, hogy a felhasználó kijelentkeztetje, leállítsa és újraindítsa az eszközt. A HoloLens-kezdőképernyő jelzi, hogy mikor érhető el a rendszerfrissítés.

#### <a name="how-to-use"></a>Használat

1. Nyissa meg a HoloLens-kezdőképernyő [a Start](hololens2-basic-usage.md#start-gesture) kézmozdulattal, vagy mondja ki a "Go to Start" (Ugrás az indításhoz) gombra.

2. Figyelje meg a felhasználói profil képe melletti három pont ikont (...):<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Válassza ki a felhasználói profil képét a saját kezűleg vagy a "Power" hangparancs használatával.

4. Megjelenik egy menü, amely az eszköz kijelentkeztet, újraindítható vagy leállítható beállításait tartalmaz:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Válassza ki a menüelemet a HoloLens kijelentkeztetésével, újraindításával vagy leállítával. Előfordulhat, hogy a Kijelentkezás lehetőség nem érhető el, ha az eszköz egyetlen [Microsoft-fiókhoz (MSA)](hololens-identity.md)vagy helyi fiókhoz van beállítva.

6. Zárja be a menüt bárhol másra, vagy zárja be Start menü start kézmozdulattal.

#### <a name="update-indicator"></a>Frissítésjelző

Amikor egy frissítés elérhetővé válik, a három pont ikon kigyűjt, jelezve, hogy az újraindítás telepíti a frissítést. A menü beállításai is megváltoznak, hogy tükrözzék a frissítés jelenlétét.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Több felhasználó szerepel a Bejelentkezési képernyőn

Korábban a Bejelentkezés képernyőn csak a legutóbb bejelentkezett felhasználó, valamint az "Egyéb felhasználó" belépési pont jelent meg. Ügyfeleink visszajelzést kaptak arról, hogy ez nem elegendő, ha több felhasználó is bejelentkezett az eszközre. Továbbra is újra kellett beírniuk a felhasználónevüket stb.

Az ebben a Windows-buildben bemutatott Egyéb felhasználó lehetőség kiválasztásakor, amely a PIN-kód beviteli mezőtől jobbra található, a Bejelentkezés képernyőn több olyan felhasználó is megjelenik, akik korábban bejelentkeztek az eszközre.  Ez lehetővé teszi, hogy a felhasználók kiválasztják a felhasználói profiljukat, majd a saját Windows Hello jelentkezzenek be. A Fiók hozzáadása gombbal új felhasználó is hozzáadható az eszközhöz az Egyéb felhasználók **lapon.**

Az Egyéb felhasználók menüBen az Egyéb felhasználók gomb megjeleníti az eszközre legutóbb bejelentkezett felhasználót. Válassza ezt a gombot a felhasználó bejelentkezési képernyőjére való visszatéréshez.

![Bejelentkezési képernyő – alapértelmezés](./images/multiusers1.jpg)

<br>

![Bejelentkezési képernyő – egyéb felhasználók](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C külső mikrofon támogatása

> [!IMPORTANT]
> Az USB-mikrofon csatlakoztatása nem lesz automatikusan beállítva **bemeneti eszközként.** USB-C-kábelek csatlakoztatása esetén a felhasználók megfigyelhetik, hogy a mikrofon hanganyaga automatikusan a mikrofonhoz lesz irányítva, de a HoloLens operációs rendszer a belső mikrofontömböt a többi bemeneti eszköz fölé rangsorítja. **USB-C mikrofon használata érdekében kövesse az alábbi lépéseket.**

A felhasználók a Hangbeállítások panelen  választhatnak USB-C-hez csatlakoztatott külső mikrofonokat. Az USB-C-mikrofonok hívásra, felvételre stb. használhatók.

Nyissa meg **a Beállítások** alkalmazást, és válassza a **Rendszerhang**  >  **lehetőséget.**

![Hangbeállítások](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Ha külső mikrofonokat használ a **Remote Assist** segítségével, a felhasználóknak a "Hangeszközök kezelése" hivatkozásra kell kattintanunk.
>
> Ezután a legördülő menüben állítsa a  külső mikrofont Alapértelmezett vagy **Kommunikációs alapértelmezettre.** Az **Alapértelmezett beállítás** azt jelenti, hogy a külső mikrofon mindenhol használatban lesz.
>
> A **Kommunikáció alapértelmezett beállítása** azt jelenti, hogy a külső mikrofon a Remote Assistben és más kommunikációs alkalmazásokban lesz használva, de a HoloLens mic tömb továbbra is használható más feladatokhoz.

![Hangeszközök kezelése](images/usbc-mic-2.png)

<br>

![Mikrofon alapértelmezett beállítása](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Mi a helyzet a Bluetooth-mikrofonok támogatásával?

Sajnos a Bluetooth-mikrofonok jelenleg még nem támogatottak a HoloLens 2-ben.

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C-mikrofonok hibaelhárítása

Vegye figyelembe, hogy egyes USB-C-mikrofonok helytelenül jelentik magukat mikrofonként és *beszélőként* is. Ez a mikrofonnal, és nem a HoloLens-sel van probléma. Ha ezen mikrofonok valamelyikét a HoloLenshez csatlakoztatja, a hang elveszhet. Szerencsére van egy egyszerű javítás.  

A **Settings** System Sound  ->  **(Beállítások rendszerhangja)** lapon explicit módon állítsa be a beépített beszélők  ->   **(Analog Feature Audio Driver)** alapértelmezett eszközként való **beállítását.** A HoloLensnek akkor is meg kell jegyeznie ezt a beállítást, ha a mikrofont eltávolítják, majd később újracsatlakoztatják.

![USB-C-mikrofonok hibaelhárítása](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Látogatói automatikus bejelentkezés kioszkok számára

Ez az új funkció lehetővé teszi a Látogatói fiókokba való automatikus bejelentkezést kioszkmódokhoz.

Nem AAD-konfiguráció esetén egy eszköz konfigurálása látogatói automatikus bejelentkezéshez:

1. Hozzon létre egy kiépítési csomagot, amely:
    1. Úgy **konfigurálja a Runtime-beállításokat/AssignedAccess-t,** hogy engedélyezze a látogatói fiókokat.
    1. Ha szükséges, regisztrálja az eszközt az MDM-be (Futásidejű **beállítások/Munkahely/Regisztrációk),** hogy később kezelhető legyen.
    1. Ne hozzon létre helyi fiókot
1. [Alkalmazza a kiépítési csomagot.](hololens-provisioning.md)

Az AAD-konfigurációk esetén a felhasználók a maihoz hasonló eredményt érhetnek el a módosítás nélkül. A kioszkmódhoz konfigurált AAD-hez beléptethet egy látogatói fiókot egyetlen gombkoppintással a bejelentkezési képernyőről. Miután bejelentkezett a látogatói fiókba, az eszköz nem kéri újra a bejelentkezést, amíg a Látogató kijelentkezik a Start menüből, vagy újra nem indítják az eszközt.

A látogatói automatikus bejelentkezés egyéni [OMA-URI szabályzat segítségével](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) kezelhető:

- URI-érték: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Szabályzat  | Leírás   | Konfigurációk  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Lehetővé teszi a látogatónak a kioszkba való automatikus bejelentkezést   | 1 (Igen), 0 (Nem, alapértelmezés.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Az új Settings és Edge alkalmazások használata kioszkmódban

Amikor alkalmazásokat ad hozzá [a kioszkhoz,](hololens-kiosk.md)a rendszergazda gyakran hozzáadja az alkalmazást a kioszkhoz, de az alkalmazásfelhasználói modell azonosítóját (AUMID) használja. Mivel a Beállítások alkalmazást és az Microsoft Edge-alkalmazást is új alkalmazásnak tekintjük, és eltérnek a régebbi alkalmazásoktól, az alkalmazásokhoz AUMID-t használni képes kioszkokat frissíteni kell az új AUMID használatának megfelelően.

Amikor úgy módosít egy kioszkot, hogy az tartalmazza az új alkalmazásokat, javasoljuk, hogy adja hozzá az új AUMID-t, és hagyja meg a régit. Ez egyszerű átállást fog létrehozni, amikor a felhasználók frissítik az operációs rendszert, és nem kell új szabályzatokat kapniuk a kioszk megfelelő használatának érdekében.

| Alkalmazás                    | AUMID (AUMID)                                                  |
|------------------------|--------------------------------------------------------|
| Régi beállítások alkalmazás       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Új beállítások alkalmazás       | BAEAEF15-9CAF-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Régi Microsoft Edge alkalmazás | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Új Microsoft Edge alkalmazás | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>A kioszkmód viselkedésének változásai a hibák kezelésével

A régebbi buildek esetén, ha egy eszköz kioszkkonfigurációval rendelkezik, amely a globális hozzáférés és az AAD-csoporttagok hozzárendelt hozzáférésének kombinációja, akkor az AAD-csoporttagság meghatározása sikertelen volt, a felhasználó a["start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)menüben semmi sem jelenik meg" jelenik meg.

Ebben a Windows-kiadásban a kioszkmód vissza fog állni a globális kioszkkonfigurációhoz (ha van ilyen), ha az AAD-csoport kioszkmódja során hibák lépnek fel.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Új beállítási URI-k az oldalbeállítások láthatósága számára

A [Windows Holographic 20H2-es](hololens-release-notes.md#windows-holographic-version-20h2) verziójában hozzáadtunk egy [Settings/PageVisibilityList szabályzatot,](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) amely korlátozza a Beállítások alkalmazásban látható oldalakat. A PageVisibilityList egy olyan szabályzat, amely lehetővé teszi a rendszergazdák számára, hogy megakadályozzák a Rendszerbeállítások alkalmazás adott lapjainak láthatóságát vagy akadálymentességét, vagy hogy ezt a megadottak kivételével minden oldalon megtedzék.

Ha felkeresi [az Oldalbeállítások láthatósága](settings-uri-list.md)oldalt, útmutatást talál a CSP használatára és a korábbi kiadásokban elérhető URI-k listájára.

Kibővítjük az elérhető Beállítás URI-k listáját, amelyeket a rendszergazdák kezelnek. Ezen URI-k némelyike az új Beállítások alkalmazás újonnan elérhető területeihez használható. Ha Settings/PageVisibilityList szabályzatot használ, tekintse át az alábbi listát, és szükség szerint módosítsa az engedélyezett vagy letiltott oldalakat.

> [!NOTE]
> **Elavult: ms-settings:network-proxy**
>
> Ezekben az újabb buildekben az egyik beállítási oldal elavult. A régi **Hálózati & internetproxy** lap már nem  >   érhető el globális beállításként. Az új kapcsolatonkénti proxybeállítások az Internet  >  **Wi-Fi&** tulajdonságai vagy az Internet  >   **Ethernet&** tulajdonságai alatt  >    >  **találhatók.**

<br>

| Beállítások lap                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Alkalmazások > Alkalmazások & funkciói                               | `ms-settings:appsfeatures`                         |
| Alkalmazások > Alkalmazások & funkciók > speciális beállítások          | `ms-settings:appsfeatures-app`                     |
| Offline > alkalmazások                                  | `ms-settings:maps`                                 |
| Offline > alkalmazások és > térképek letöltése                  | `ms-settings:maps-downloadmaps`                    |
| Egérrel > eszközök                                      | `ms-settings:mouse`                                |
| USB> eszközök                                        | `ms-settings:usb`                                  |
| Hálózati & internetes > repülőgép üzemmódban                   | `ms-settings:network-airplanemode`                 |
| Adatvédelmi > általános                                    | `ms-settings:privacy-general`                      |
| Adatvédelmi > Ink & gépelés személyre szabása             | `ms-settings:privacy-speechtyping`                 |
| Adatvédelmi > Motion                                     | `ms-settings:privacy-motion`                       |
| Adatvédelmi > Képernyőkép a szegélyekről                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Adatvédelmi > képernyőképek és alkalmazások                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| System > Battery                                     | `ms-settings:batterysaver`                         |
| System > Battery                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| System > Sound > Alkalmazáskötet és eszközbeállítások | `ms-settings:apps-volume`                          |
| System > Sound > Hangeszközök kezelése              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Tárterületsegéd         | `ms-settings:storagepolicies`                      |
| A & nyelv és > dátum & ideje                        | `ms-settings:dateandtime`                          |
| Time & Language > Billentyűzet                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| A & biztonsági > visszaállítás & frissítése               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Frissített URI-k

Korábban a következő két URI nem adná meg a felhasználót közvetlenül a jelzett oldalakra, csak blokkolta volna a fő frissítésoldalt. A következő elemek úgy frissültek, hogy közvetlenül a saját oldalukra irányulnak:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>A Tartalék diagnosztika konfigurálása a Beállítások alkalmazással

Most a Beállítások alkalmazásban a felhasználó konfigurálhatja a [Fallback Diagnostics viselkedését.](hololens-diagnostic-logs.md) A Beállítás alkalmazás Adatvédelmi hibaelhárítás  ->  **lapjára navigálva** konfigurálhatja ezt a beállítást.

> [!NOTE]
> Ha az eszközhöz MDM-szabályzat van konfigurálva, a felhasználó nem tudja felülbírálni ezt a viselkedést.  

### <a name="share-things-with-nearby-devices"></a>Dolgok megosztása a közeli eszközökkel

Megoszthatja a dolgokat a Windows 10 eszközökkel, beleértve a számítógépeket és más HoloLens 2-eszközöket is. Kipróbálhatja a Beállítások rendszer által **megosztott** élmények között, és megoszthat fájlokat vagy URL-címeket  ->    ->   a HoloLensből a számítógépekre. További részletekért olvassa el, hogyan oszthat meg dolgokat a közeli eszközökkel a [Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

Ez a szolgáltatás a [Connectivity/AllowConnectedDevices használatával kezelhető.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Új operációsrendszer-diagnosztikai nyomkövetések

A Beállítások alkalmazás korábbi hibaelhárítói mellett egy új hibaelhárítót is hozzáadtunk az új Operációsrendszer-frissítések beállítások alkalmazásához. Lépjen a **Beállítások Frissítése**  ->  **biztonsági &amp; hibaelhárítása**  >    >  **lapra, Windows Update** válassza az Indítás **lehetőséget.** Ez lehetővé teszi a nyomkövetések gyűjtését az operációsrendszer-frissítésekkel kapcsolatos probléma reprodukálása során, hogy az it-it és a támogatási szolgálattal kapcsolatos hibaelhárítást javítsa.

### <a name="delivery-optimization-preview"></a>Kézbesítésoptimalizálás előzetes verzió

Ezzel a HoloLens-frissítéssel a Windows Holographic for Business lehetővé teszi a kézbesítésoptimalizálási beállításokat, hogy csökkentse a sávszélesség-használatot több HoloLens-eszközről történő letöltések esetén. A funkció teljesebb leírása és az ajánlott hálózati konfiguráció itt érhető el: Kézbesítésoptimalizálás [a Windows 10 frissítéséhez.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

Az alábbi beállítások a felügyeleti felület részeként vannak engedélyezve, [és az Intune-ból konfigurálhatóak:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Az előzetes verzióval kapcsolatos néhány figyelmeztetés:

- A HoloLens támogatása ebben az előzetes verzióban csak az operációs rendszer frissítéseit támogatja.
- Windows Holographic for Business a HTTP letöltési módokat és a Microsoft-végpontról [való Csatlakoztatott gyorsítótár letöltéseket támogatja;](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) A holoLens-eszközök jelenleg nem támogatják a társközi letöltési módokat és csoport-hozzárendeléseket.
- A HoloLens nem támogatja a végpontok üzembe helyezését Windows Server Update Services optimalizálását.
- A hibaelhárításhoz diagnosztikára van szükség a Csatlakoztatott gyorsítótár-kiszolgálón, vagy nyomkövetést kell gyűjteni a HoloLensen a HoloLensen a Settings  >  **Update & Security**  >   **Troubleshooting**  >   **Windows Update**.

### <a name="it-admin---update-checklist"></a>Rendszergazda – Frissítési ellenőrzőlista

Ez az ellenőrzőlista segít az ebben a funkciófrissítésben hozzáadott új elemekről, amelyek hatással lehetnek az aktuális eszközkezelési konfigurációkra, vagy olyan új funkciókra, amelyek használatba lesznek adva.

#### <a name="updates-to-kiosk-mode"></a>A kioszkmód frissítései

✔️ Új [**AUMID-k új alkalmazásokhoz kioszkmódban:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Ha korábban a Beállítások alkalmazást vagy egy Microsoft Edge alkalmazást használt kioszkban, ezeket az alkalmazásokat új alkalmazásokra cseréljük, amelyek más alkalmazásazonosítót használnak. Javasoljuk, hogy olvassa el alább az [Új AUMID-k új alkalmazásokhoz Kioszk módban cikkeket.](#use-the-new-settings-and-edge-apps-in-kiosk-modes) Ezzel biztosíthatja, hogy továbbra is a Beállítások alkalmazás legyen a kioszkban, vagy tartalmazza az új Microsoft Edge alkalmazást. Ezeket a módosításokat már most is végre lehet tenni, és az összes eszközön üzembe lehet helyezni, és zökkenőmentesebb frissítésváltást lehetővé tenni.

✔️ Látogató [**automatikus bejelentkezése kioszkok számára:**](#visitor-auto-logon-for-kiosks) 

A látogatók mostantól automatikusan bejelentkeztetheti őket egy kioszkba. Ez a viselkedés alapértelmezés szerint be van kapcsolva, de kezelhető és letiltható.

✔️ [**továbbfejlesztett kioszkmódú sikertelen kezelés:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Ha a bejelentkezett AAD-felhasználó AAD-csoporttagságának meghatározása nem sikerült, akkor a rendszer a globális kioszkkonfigurációt használja a Start menüben (ha van), ellenkező esetben a felhasználó üres Start menüt kap. Bár az üres Start menü nem közvetlenül beállítható konfiguráció, ez az új kezelés segíthet tájékoztatni a támogatási részleget a kioszkok használata esetén, mivel ez a konfigurációkra is vonatkozhat, vagy új módosításokat kell végeznie a hozzárendelt hozzáférési konfigurációkon.

#### <a name="updates-to-page-settings-visibility"></a>Az oldalbeállítások láthatóságának frissítései

✔️ új [**beállítási URI-k az Oldalbeállítások láthatósága beállításhoz**](#new-settings-uris-for-page-settings-visibility)

Ha jelenleg az [Oldalbeállítások](settings-uri-list.md) láthatósága beállítást használja, akkor előfordulhat, hogy módosítani szeretné a meglévő URI-eket, amelyek engedélyezettek vagy le vannak tiltva.

#### <a name="updates-for-your-wdac-policy"></a>A WDAC-szabályzat frissítései
✔️ Ha korábban a WDAC Microsoft Edge blokkolta a forgalmat, frissítenie kell a WDAC-szabályzatot. Tekintse át az alábbiakat, és használja a megadott mintakódot.
#### <a name="enable-new-endpoints-for-edge"></a>Új végpontok engedélyezése az Edge-hez
✔️ Ha olyan infrastruktúrával rendelkezik, amely magában foglalja a hálózati végpontok, például a proxy vagy a tűzfal konfigurálását, engedélyezze ezeket az új végpontokat az új Microsoft Edge számára.

#### <a name="newly-configurable-items"></a>Újonnan konfigurálható elemek

✔️ Configure [Fallback Diagnostics](#configuring-fallback-diagnostics-via-settings-app)(Tartalék diagnosztika konfigurálása): Beállíthatja, hogy a rendszer gyűjtse-e a tartalék diagnosztikát, és ki gyűjtheti be.

✔️ Megosztás[a közeli eszközökkel:](#share-things-with-nearby-devices)Letilthatja az új közeli megosztási funkciót.

✔️ [configuring policy settings for the new Microsoft Edge:](#configuring-policy-settings-for-the-new-microsoft-edge)Review the newly configurations available for Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Új diagnosztikai eszköz

✔️[Új operációsrendszer-diagnosztikai nyomkövetés:](#new-os-diagnostic-traces)Az operációs rendszer frissítésével kapcsolatos naplók gyűjtése.

### <a name="improvements-and-fixes-in-the-update"></a>A frissítés fejlesztései és javításai:

- [Az offline diagnosztika](hololens-diagnostic-logs.md#offline-diagnostics) a sorozatszámmal és az operációs rendszer verziójával kapcsolatos további eszközadatokat is tartalmaz.
- Kijavítja az üzletági alkalmazások futásidejű kiépítési csomagokon keresztüli üzembe helyezéssel kapcsolatos problémákat.
- Kijavítja az üzletági alkalmazások telepítési állapotjelentési szolgáltatásával kapcsolatos problémát.
- Kijavít egy problémát, amely az új alkalmazáscsomagok eszköz-visszaállítások közötti megőrzésével kapcsolatban áll fenn.
- Kijavít egy problémát, amely miatt helytelen szimbólumok írhatóak be az Edge-be japán ügyfelek számára.
- Javítja az operációs rendszer frissítéseinek rugalmasságát az előre telepített alkalmazások, például az Edge körül. 
- A frissítés megbízhatóságát kijavítja, amely hatással van a Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. májusi frissítés
- Build 19041.1146

A frissítés fejlesztései és javításai:
- Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb buildet, a Windows Holographic 21H1-es verzióját.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. májusi frissítés
- Build 18362.1110

A frissítés fejlesztései és javításai:
- Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. **Ez a build többé nem kap havi szolgáltatásfrissítéseket.** Javasoljuk, hogy próbálja ki a legújabb buildet, a Windows Holographic 21H1-es verzióját.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. áprilisi frissítés
- Build 19041.1144

A frissítés fejlesztései és javításai:

- Kijavítja az üzletági alkalmazások telepítési állapotjelentési szolgáltatásával kapcsolatos problémát.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. áprilisi frissítés
- Build 18362.1108

A frissítés fejlesztései és javításai:

- Kijavít egy problémát, amely miatt a Beállítások alkalmazás összeomlik, amikor megpróbálja módosítani egy helyi fiók jelszavát.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. márciusi frissítés
- Build 19041.1140

A frissítés fejlesztései és javításai:

- Az AdvancedPhotoCapture vagy a LowLagPhotoCapture használatával a HoloLens 2 használatával készített fényképeket használó ügyfelek mostantól a fénykép rögzítése után legfeljebb 3 másodperccel lekérik a kamera testét.
- Javítva a Eszközportál szolgáltatás memóriavesztése, amely a szolgáltatás megnövekedett memóriahasználatát okozta, amely miatt más alkalmazások nem foglalták le a memóriát.
- Kijavítottunk egy hibát, amely miatt a szakaszos bevezetésben regisztrált felhasználók nem tudnak bejelentkezni az eszközre.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. márciusi frissítés
- Build 18362.1102

A frissítés fejlesztései és javításai:

- Javítva a Eszközportál szolgáltatás memóriavesztése, amely a szolgáltatás megnövekedett memóriahasználatát okozta, amely miatt más alkalmazások nem foglalták le a memóriát.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. februári frissítés
- Build 19041.1136

A frissítés fejlesztései és javításai:

- Kijavít egy problémát az eszköz kezdeti beállításához és az alkalmazásfrissítések tárolására.
- A későbbi HoloLens-kiadások frissítésével és járatokkal kapcsolatban problémát old meg.
- El lett távolítva a nem használt előre telepített tanúsítványok az eSIM-gyökértárolóból a HoloLens-eszközökről.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. februári frissítés
- Build 18362.1098

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a Windows Holographic 2004-es verziójához elérhető legújabb buildeket.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, 20H2-es verzió – 2021. januári frissítés
- Build 19041.1134

A frissítés fejlesztései és javításai:

- Jobb teljesítmény indítás, folytatás és felhasználóváltás során, ha sok felhasználó van az eszközön.
- Arm32-támogatás hozzáadva a [Kutatási módhoz.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, 1903-as verzió – 2021. januári frissítés
- Build 18362.1091

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a Windows Holographic 2004-es verziójához elérhető legújabb buildeket.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, 20H2-es verzió – 2020. decemberi frissítés
- Build 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Alkalmazások telepítése a HoloLens 2-re a Alkalmazástelepítő

Egy új **funkcióval (Alkalmazástelepítő)** bővítjük az alkalmazások zökkenőmentes telepítését a HoloLens 2-eszközökön. Ez a funkció alapértelmezés szerint be lesz kapcsolva a nem **engedélyezett eszközökön.** A vállalatok kimaradásának elkerülése érdekében az alkalmazástelepítő jelenleg nem lesz elérhető **a felügyelt** eszközökhöz.  

Az eszközök akkor minősülnek  "felügyeltnek", ha az alábbiak bármelyike igaz:
- MDM [regisztrálva](hololens-enroll-mdm.md)
- Kiépítési [csomaggal konfigurálva](hololens-provisioning.md)
- A felhasználói [identitás](hololens-identity.md) az Azure AD

Most már anélkül telepíthet alkalmazásokat, hogy engedélyeznie kellene a fejlesztői módot, vagy engedélyeznie kellene a Eszközportál.  Egyszerűen töltse le (USB-n vagy peremhálózaton keresztül) az Appx-csomagot az eszközre, és navigáljon az Appx-csomaghoz a Fájlkezelő, hogy a rendszer a telepítést elindító kérést kapjon.  Másik lehetőségként [kezdeményezzen telepítést a weblapról.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Az Microsoft Store-ból telepített alkalmazásokhoz vagy az MDM LOB App Deployment funkcióját használó alkalmazásokhoz hasonló [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) módon az [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) alkalmazásoknak digitálisan alá kell írniuk az aláírási eszközzel, és az aláíráshoz használt tanúsítványnak megbízhatónak kell lennie a HoloLens-eszközben az alkalmazás üzembe helyezése előtt.

**Alkalmazástelepítési utasítások.**

1.  Győződjön meg arról, hogy az eszköz nem minősül felügyeltnek
1.  Győződjön meg arról, hogy a HoloLens 2-eszköz be van kapcsolva és csatlakoztatva van a számítógéphez
1.  Győződjön meg arról, hogy be van jelentkezve a HoloLens 2-eszközre
1.  A számítógépen navigáljon az egyéni alkalmazáshoz, és másolja a yourapp.appxbundle et a yourdevicename\Internal Storage\Downloads mappába.   A fájl másolása után leválaszthatja az eszközt
1.  A HoloLens 2-eszközön nyissa meg a Start menüt, válassza a Minden alkalmazás elemet, és indítsa el Fájlkezelő alkalmazást.
1.  Lépjen a Letöltések mappára. Előfordulhat, hogy az alkalmazás bal oldali panelén először az Ez az eszköz lehetőséget kell választania, majd a Letöltések lapra kell navigálnia.
1.  Válassza ki a yourapp.appxbundle fájlt.
1.  A Alkalmazástelepítő meg fog indulni. Az alkalmazás telepítéséhez kattintson a Telepítés gombra.
A telepített alkalmazás a telepítés befejezésekor automatikusan elindul.

A folyamat teszteléséhez mintaalkalmazásokat találhat az univerzális [Windows-minták GitHubon.](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)

Olvassa el az alkalmazások [HoloLens 2-re](app-deploy-app-installer.md)való telepítésének teljes folyamatát a Alkalmazástelepítő.  

![MRTK-példák telepítése Alkalmazástelepítő](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>A frissítés fejlesztései és javításai:

- A kézkövetés mostantól számos olyan új esetben fenntartja a nyomkövetést, amikor a kéz korábban elveszett volna.  Az új esetek némelyikében csak a jobb pozíció frissül a felhasználó valódi kezében, a másik pedig egy korábbi helyzet alapján van kikövetkeztetve.  Ez a változás segít javítani a követési konzisztenciát az olyan mozgások során, mint a dobás, a dobás, a dobás és a klónozás.  Abban az esetben is segít, ha a kéz egy felülethez közel van, vagy egy objektumot tart lenyomva.  A kézredúsítő [](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) kikövetkeztetve az egy közös pontossági érték a "Közelítő" értékre lesz állítva a "High" (Magas) helyett.
- Kijavítottunk egy hibát, amely miatt az Azure AD-fiókok PIN-kódját alaphelyzetbe állítva a következő hibaüzenet jelenik meg: "Hiba történt.
- A felhasználóknak sokkal kevesebb indítás utáni OOBE-összeomlást kell látniuk az ET, az Iris gépi alkalmazásból, az új felhasználó vagy az értesítési bejelentések indításakor.
- A felhasználóknak megfelelő időzónának kell lennie az OOBE-val.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. decemberi frissítés
- Build 18362.1088

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a legújabb Windows Holographic 20H2 – 2020. decemberi frissítést és a buildben hozzáadott új Alkalmazástelepítő funkciót.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, 20H2-es verzió
- Build 19041.1128

A Windows Holographic 20H2-es verziója már elérhető, és nagyszerű új funkciókat kínál a HoloLens 2-felhasználók és informatikai szakemberek számára. Az automatikus szempozíciótól a Beállításokban a Tanúsítványkezelőn át a kioszkmód továbbfejlesztett funkcióin át az AutoPilot új beállítási képességein át. Ez az új frissítés lehetővé teszi az it-csapatok számára, hogy részletesebben irányítják a HoloLens-eszközök konfigurálását és felügyeletét, és még zökkenőmentesebb holografikus élményt kínálnak a felhasználóknak. 

Ez a legújabb kiadás a 2004-es verzió havi frissítése, de ezúttal új funkciókkal is rendelkezik. A fő buildszám változatlan marad, és Windows Update a 2004-es verzió (19041-es build) havi kiadását jelzi. A Build Number (Buildszám) lap Settings (Beállítások) > About (Információk) képernyőjén meggyőződhet arról, hogy a legújabb elérhető build 19041.1128+-as verzióját használja. A legújabb kiadásra való frissítéshez nyissa meg a Beállítások alkalmazást, nyissa meg az Update & Security (Biztonsági frissítések frissítése) menüt, és koppintson a Check for Updates (Frissítések keresése) elemre. A HoloLens-frissítések kezelésére vonatkozó további információkért látogasson el erre [az oldalra.](https://docs.microsoft.com/hololens/hololens-updates)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>A Windows Holographic 20H2-es verziójának újdonságai  

| Szolgáltatás                                              | Leírás                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Automatikus szempozíció támogatása](hololens-release-notes.md#auto-eye-position-support) | Aktívan számítja ki a szempozíciókat anélkül, hogy a felhasználók szemkövetésen keresztülmennek.   |
| [Tanúsítványkezelő](hololens-release-notes.md#certificate-manager)   | Lehetővé teszi, hogy az új egyszerűbb módszerek tanúsítványokat telepítsenek és távolítsanak el a Beállítások alkalmazásból.     |
| [Automatikus indítású kiépítés USB-ről](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Az USB-meghajtókon található kiépítési csomagok automatikusan kérik a kiépítési oldalt az OOBE-ban.                                                         |
| [Kiépítési csomagok automatikus megerősítése az OOBE-ban](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | A kiépítési csomagokat a rendszer automatikusan alkalmazza az OOBE során a kiépítési oldalról.                                                         |
| [Automatikus kiépítés felhasználói felület használata nélkül](hololens-release-notes.md#automatic-provisioning-without-using-ui) | A kiépítési automatikus indítás és az automatikus megerősítés kombinálása. |
| [Az Autopilot használata Wi-Fi kapcsolattal](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Az Autopilot eszközről Wi-Fi Ethernet-adapter nélkül használható. |
| [Tenantlockdown CSP és Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | A bérlői regisztráció és a szabályzat alkalmazása után az eszköz csak akkor regisztrálható ebben a bérlőben, ha alaphelyzetbe állítja vagy újra flashre állítja az eszközt. |
| [Globális hozzárendelt hozzáférés](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Új konfigurációs módszer több alkalmazásos kioszkmódhoz, amely a teljes kioszkot rendszerszinten alkalmazza, így mindenkire alkalmazható.                  |
| [Alkalmazás automatikus indítása többalkalmazásos kioszkban](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Beállítja, hogy egy alkalmazás automatikusan elinduljon, amikor többalkalmazásos kioszkmódba jelentkezik be.                                                        |
| [A kioszkmód viselkedésének változásai a hibák kezelésével](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | A kioszkmód meghibásodása már korlátozó tartalékot is lehetővé tesz.                                                                                                |
| [HoloLens-szabályzatok](hololens-release-notes.md#hololens-policies)                                    | Új szabályzatok a HoloLenshez.     |
| [Azure AD-csoporttagság gyorsítótárazése offline kioszkhoz](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Az új szabályzat lehetővé teszi a felhasználók számára, hogy csoporttagság-gyorsítótárat használjanak a kioszkmód offline használatára adott számú napig.                                        |
| [Új eszközkorlátozási szabályzatok a HoloLens 2-höz](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Az újonnan engedélyezett eszközkezelési szabályzatok engedélyezve vannak a HoloLens 2-ben.                                                                                |
| [Új energiagazdálkodási szabályzatok a HoloLens 2-hez](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Újonnan támogatott szabályzatok az időtúllépési beállításokhoz.  |
| [Szabályzatok frissítése](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Újonnan engedélyezett szabályzatok, amelyek lehetővé teszik a frissítések vezérlését.           |
| [A Beállítások oldal láthatósága engedélyezve a HoloLens 2-ben](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Szabályzat a Beállítások alkalmazásban látható oldalak választására.             |
| [Kutatási mód](hololens-release-notes.md#research-mode) | Kutatási mód használata a HoloLens 2-ben. |
| [Rögzítés hosszának megnövelve](hololens-release-notes.md#recording-length-increased) | Az MRC-felvételeket a továbbiakban nem 5 percre korlátozták. |
| [A frissítés fejlesztései és javításai](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | További javítások a frissítésben.   |

### <a name="auto-eye-position-support"></a>Auto Eye Position Support

A HoloLens 2 szempozíciói lehetővé teszik a pontos hologrampozíciót, a kényelmes megtekintést és a jobb megjelenítési minőséget. A szempozíciók kiszámítása belsőleg, a szemkövetési számítások részeként történt. Ehhez azonban minden felhasználónak szemkövetést kell követnie, még akkor is, ha a felhasználói élményhez nem szükséges szembetekintő adat.

**Az automatikus szempozíció (Auto Eye Position, AEP)** lehetővé teszi, hogy ezek a forgatókönyvek interakció nélküli módon számítsák ki a felhasználó szempozícióit. Az automatikus szempozíció automatikusan elindul a háttérben attól a pillanattól kezdve, hogy a felhasználó bekapcsolja az eszközt. Ha a felhasználó nem rendelkezik előzetes szemkövetési rendszerrel, az Auto Eye Position 20–30 másodperces feldolgozási idő után elkezdi a felhasználó szempozícióját a kijelzőrendszernek. A felhasználói adatok nem maradnak meg az eszközön, ezért ez a folyamat meg lesz ismételve, ha a felhasználó kikapcsolja és visszateszi az eszközt, vagy ha az eszköz újraindul vagy felébreszti az alvó állapotból.

Az Auto Eye Position funkcióval a rendszer viselkedése megváltozik, ha egy nem skálázható felhasználó helyezi el az eszközt. Ebben a kontextusban a nem számbavesített felhasználó olyanra utal, aki még nem ment át az eszközön korábban a szemkövetési folyamaton.

| Aktív alkalmazás | Korábbi viselkedés | Viselkedés a Windows Holographic 20H2 Update-től |
|:-------------------|:-----------------|:-----------------------------------|
| Nem tekintett alkalmazás vagy Holographic Shell |Megjelenik a szemkövetési párbeszédpanel. | Nem jelenik meg kérdés. |
| Tekintetre képes alkalmazás | Megjelenik a szemkövetési párbeszédpanel. | A szemkövetési üzenet csak akkor jelenik meg, ha az alkalmazás hozzáfér a tekintetfolyamhoz. |

Ha a felhasználó egy nem tekintetet használó alkalmazásról a tekinteti adatokhoz hozzáférő alkalmazásra tér át, megjelenik a figyelmeztetés. 

Minden más rendszerviselkedés hasonló lesz ahhoz, amikor az aktuális felhasználó nem rendelkezik aktív szemkövetési követéssel. Az egy szándékból indítható indítási kézmozdulat például nem lesz engedélyezve. A kezdeti beállításhoz nem változik az Out-Of-Box-Experience.

A szemre vonatkozó tekinteti adatokat vagy a rendkívül pontos hologrampozíciót igénylő élmények esetén azt javasoljuk, hogy a nem skálázott felhasználók a szemkövetési görbét futtassanak. Elérhető a szemkövetési parancssorból vagy a Beállítások alkalmazás start menüből való elindításával, majd a **System > > Eye > Run eye és a elemet** választva.

Ezek az információk később más, a-nak [megfelelő adatokat is tartalmaznak.](hololens-calibration.md#auto-eye-position-support) 

### <a name="certificate-manager"></a>Tanúsítványkezelő

- Továbbfejlesztett naplózási, diagnosztikai és érvényesítési eszközök az eszközbiztonság és -megfelelőség érdekében az új Tanúsítványkezelővel. Ez a képesség lehetővé teszi a tanúsítványok kereskedelmi környezetekben való nagy léptékű üzembe helyezését, hibaelhárítását és érvényesítését.

A Windows Holographic 20H2-es verziójában tanúsítványkezelőt ad hozzá a HoloLens 2 Beállítások alkalmazáshoz. A Biztonsági **tanúsítványok > frissítése & lapra > meg.** Ez a funkció egyszerű és felhasználóbarát módja a tanúsítványok megtekintésének, telepítésének és eltávolításának az eszközön. Az új Tanúsítványkezelővel a rendszergazdák és a felhasználók továbbfejlesztett naplózási, diagnosztikai és érvényesítési eszközökkel gondoskodnak az eszközök biztonságának és megfelelőségének biztosításáról. 

-   **Naplózás:** A tanúsítvány megfelelő telepítésének ellenőrzése vagy annak ellenőrzése, hogy a tanúsítvány megfelelően lett-e eltávolítva. 
-   **Diagnosztika:** Ha problémák merülnek fel, a megfelelő tanúsítványoknak az eszközön való létezik-e a hitelesítése időt takarít meg, és segít a hibaelhárításban. 
-   **Érvényesítés:** Ha ellenőrzi, hogy a tanúsítvány a kívánt célt szolgálja-e és működik-e, jelentős időt takaríthat meg, különösen kereskedelmi környezetekben, mielőtt nagyobb léptékben helyez üzembe tanúsítványokat.

Ha gyorsan meg kell találnia egy adott tanúsítványt a listában, lehetőség van név, tároló vagy lejárati dátum szerint rendezni. A felhasználók közvetlenül is kereshetnek tanúsítványt. Az egyes tanúsítványtulajdonságok megtekintéséhez jelölje ki a tanúsítványt, majd kattintson az **Információ elemre.** 

A tanúsítványtelepítés jelenleg a .cer és a .crt fájlokat támogatja. Az eszköztulajdonosok a helyi gépen és az aktuális felhasználónál telepíthet tanúsítványokat;  minden más felhasználó csak az Aktuális felhasználóra telepíthető. A felhasználók csak a beállítások felhasználói felületről távolítják el a közvetlenül telepített tanúsítványokat. Ha egy tanúsítvány más módon lett telepítve, ugyanezen mechanizmussal kell eltávolítani.

#### <a name="to-install-a-certificate"></a>Tanúsítvány telepítése: 

1.  Csatlakoztassa a HoloLens 2-t egy számítógéphez.
1.  Helyezze el a telepíteni kívánt tanúsítványfájlt a HoloLens 2-es helyén.
1.  Lépjen a **Settings App > Update & Security > Certificates**(Tanúsítványok frissítése) lapra, és válassza a Tanúsítvány telepítése lehetőséget.
1.  Kattintson **a Fájl importálása** elemre, és keresse meg a helyet, ahol a tanúsítványt mentette.
1.  Válassza **a Store Location (Áruház helye) lehetőséget.**
1.  Válassza **a Tanúsítványtároló lehetőséget.**
1.  Kattintson az **Install** (Telepítés) gombra.

A tanúsítványnak most már telepítve kell lennie az eszközön.

#### <a name="to-remove-a-certificate"></a>Tanúsítvány eltávolítása: 
1. Lépjen a Settings App > Update and Security > Certificates (Tanúsítványok **>) elemre.**
1. Keresse meg a tanúsítványt név alapján a keresőmezőben.
1. Válassza ki a tanúsítványt.
1. Kattintson az **Eltávolítás gombra.**
1. Ha  a rendszer megerősítést kér, válassza az Igen lehetőséget.

![Tanúsítványmegjelenítő a Beállítások alkalmazásban](images/certificate-viewer-device.jpg)

![Kép arról, hogyan használható a tanúsítvány felhasználói felülete egy tanúsítvány telepítéséhez](images/certificate-device-install.jpg)

Ezek az információk később, egy új Tanúsítványkezelő [lapon találhatók.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>Automatikus indítású kiépítés USB-ről

- Automatizált folyamatok, amelyek kevesebb felhasználói beavatkozást lehetővé teszik, ha a kiépítési csomagokkal rendelkező USB-meghajtókat az OOBE során használják.

A kiadás előtt a felhasználóknak manuálisan kellett elindítaniuk a kiépítési képernyőt az OOBE során a kiépítéshez egy gombkombináció használatával. A felhasználók mostantól kihagyhatja a gombkombinációt egy USB-tároló meghajtón található kiépítési csomag használatával. 

1. Csatlakoztassa az USB-meghajtót a kiépítési csomaghoz az OOBE első kezelhető pillanatában
1. Amikor az eszköz készen áll a kiépítésre, az automatikusan megnyitja a kiépítési lapot. 

Megjegyzés: Ha egy USB-meghajtó be van csatlakoztatva az eszköz indulása közben, az OOBE számba veszi a meglévő USB-tárolóeszközt, és figyel a további csatlakoztatott eszközökre is.

A kiépítési csomagok OOBE során való alkalmazásával kapcsolatos további információkért keresse fel a [HoloLens kiépítési dokumentációját.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

További információt [az USB-ről](hololens-provisioning.md#auto-launch-provisioning-from-usb) történő automatikus indításról a HoloLens kiépítési dokumentációjában találhat.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Kiépítési csomagok automatikus megerősítése az OOBE-ban
- Ha megjelenik a Kiépítési csomag lap, automatikusan alkalmazza az összes felsorolt csomagot, így kevesebb felhasználói beavatkozást lehetővé tevő automatizált folyamat jelenik meg.

Amikor megjelenik a kiépítés főképernyője, az OOBE 10 másodpercig számol, mielőtt automatikusan elkezdi alkalmazni az összes kiépítési csomagot. A felhasználók a [várt csomagok](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) ellenőrzése után ebben a 10 másodpercben is megerősítheti vagy megszakíthatja a műveletet.

### <a name="automatic-provisioning-without-using-ui"></a>Automatikus kiépítés felhasználói felület használata nélkül
- Kombinált automatikus folyamatok a kiépítés kevesebb eszköz-interakciója érdekében. 

Az USB-eszközökről történő kiépítés automatikus indításának és a kiépítési csomagok automatikus megerősítésének kombinálásával a felhasználók az eszköz felhasználói felületének használata nélkül, vagy akár az eszköz beemelése nélkül is kiépítik a HoloLens 2-eszközöket. Több eszköz esetében továbbra is használhatja ugyanazt az USB-meghajtót és kiépítési csomagot. Ez akkor hasznos, ha egyszerre több eszközt telepít ugyanazon a területen. 

1. [Hozzon létre egy kiépítési csomagot a](hololens-provisioning.md) [Windows Configuration Designer használatával.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Másolja a csomagot egy USB-tároló meghajtójára.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build](https://aka.ms/hololens2previewdownload). 
1. Ha [az Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) befejezte az eszköz flash (flash) funkcióját, csatlakoztassa az USB-C-kábelt. 
1. Csatlakoztassa az USB-meghajtót az eszközhöz.
1. Amikor a HoloLens 2 eszköz OOBE-ban indul, automatikusan észleli a kiépítési csomagot az USB-meghajtón, és elindítja a kiépítési oldalt.
1. 10 másodperc elteltével az eszköz automatikusan alkalmazza a kiépítési csomagot. 

Az eszköz most már konfigurálva van, és megjelenik a [Sikeres kiépítés képernyő.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### <a name="using-autopilot-with-wi-fi-connection"></a>Az Autopilot használata Wi-Fi kapcsolattal
- Az Ethernet-hez szükséges USB-C adapterek már nem szükségesek a hardverkövetelmények csökkentéséhez azáltal, hogy az Autopilot Wi-Fi csatlakoztatott eszközökön.

Mostantól az OOBE során, miután csatlakoztatta a HoloLens 2-t a Wi-Fi-hez, az OOBE egy Autopilot-profilt keres az eszközhöz. Ha talál ilyen igénylést, a program az AAD-beléptetési és -regisztrációs folyamat hátralévő részében ezt fogja végrehajtani. Ez azt jelenti, hogy az Ethernet USB-C vagy Wi-Fi és USB-C adapter között való használata már nem követelmény, de továbbra is működni fognak, ha az OOBE elején meg vannak téve. További információ a [HoloLens 2-eszközökhöz használható Autopilotról.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP és Autopilot
- Úgy tartja meg a szervezet bérlői eszközeit, hogy az eszköz alaphelyzetbe állításán vagy perjelén keresztül is zárolja őket a bérlőhöz. A további biztonság érdekében a fiók létrehozását a kiépítéssel nem lehet. 

A HoloLens 2 rendszerű eszközök mostantól támogatják a TenantLockdown CSP-t [a Windows Holographic 20H2 verziójától.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown (Bérlői zárolás)](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) A CSP lehetővé teszi, hogy a HoloLens 2 kizárólag autopilot használatával MDM-regisztrációhoz legyen kötve. Miután a TenantLockdown CSP RequireNetworkInOOBE csomópontja true (igaz) vagy false (kezdetben beállított) értékre van állítva a HoloLens 2-ben, ez az érték megmarad az eszközön annak ellenére, hogy újra flashz, operációsrendszer-frissítések stb. 

Ha a TenantLockdown CSP-k RequireNetworkInOOBE csomópontja true (igaz) értékre van állítva a HoloLens 2-ben, az OOBE határozatlan ideig vár az Autopilot-profil sikeres letöltésére és alkalmazására a hálózati kapcsolat után. 

Ha a TenantLockdown CSP-k RequireNetworkInOOBE csomópontja true (igaz) értékre van állítva a HoloLens 2-ben, az OOBE nem engedélyezett a következő műveletek esetében: 
- Helyi felhasználó létrehozása futásidejű kiépítéssel 
- Azure AD-beléptetés végrehajtása futásidejű üzembe építéssel 
- Annak kiválasztása, hogy ki az eszköz a tulajdonában az OOBE felhasználói élményben 

#### <a name="how-to-set-this-using-intune"></a>Hogyan állíthatja be ezt az Intune-nal? 
1. Hozzon létre egy egyéni OMA URI eszközkonfigurációs profilt, és adja meg a true értéket a RequireNetworkInOOBE csomóponthoz az alább látható módon.
Az OMA-URI értékének ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE kell lennie

   > [!div class="mx-imgBorder"]
   > ![Tennant zárolásának beállítása OMA-URI-n keresztül](images/hololens-tenant-lockdown.png)

1. Hozzon létre egy csoportot, és rendelje hozzá az eszközkonfigurációs profilt. 

1. Tegye a HoloLens 2 eszközt az előző lépésben létrehozott csoport tagjaként, és aktiválja a szinkronizálást.  

Ellenőrizze az Intune-portálon, hogy az eszközkonfiguráció alkalmazása sikeres volt-e. Miután ez az eszközkonfiguráció sikeresen alkalmazva lett a HoloLens 2-eszközön, a TenantLockdown hatása aktív lesz.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>TenantLockdown RequireNetworkInOOBE in HoloLens 2-ben, az Intune használatával való mellőzésével 
1. Távolítsa el a HoloLens 2-t abból az eszközcsoportból, amelyhez korábban hozzárendelték a fent létrehozott eszközkonfigurációt. 

1. Hozzon létre egy egyéni OMA URI-alapú eszközkonfigurációs profilt, és adja meg a false (hamis) értéket a RequireNetworkInOOBE mezőben, ahogy az alább látható. Az OMA-URI értékének ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE kell lennie

   > [!div class="mx-imgBorder"]
   > ![Képernyőkép a RequireNetworkInOOBE hamisra állításával az Intune OMA URI-ján keresztül](images/hololens-tenant-lockdown-false.png)

1. Hozzon létre egy csoportot, és rendelje hozzá az eszközkonfigurációs profilt. 

1. Tegye a HoloLens 2 eszközt az előző lépésben létrehozott csoport tagjaként, és aktiválja a szinkronizálást.

Ellenőrizze az Intune-portálon, hogy az eszközkonfiguráció alkalmazása sikeres volt-e. Miután ez az eszközkonfiguráció sikeresen alkalmazva lett a HoloLens 2-eszközön, a TenantLockdown hatásai inaktívak lesznek. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Mi történne az OOBE során, ha az Autopilot-profil nincs hozzárendelve a HoloLenshez, miután a TenantLockdown igazra lett állítva? 
Az OOBE határozatlan ideig vár az Autopilot-profil letöltésére, és megjelenik a következő párbeszédpanel. A TenantLockdown hatásainak eltávolításához az eszközt először az eredeti bérlővel kell regisztrálni az AutoPilot használatával, és a RequireNetworkInOOBE-t az előző lépésben leírtak szerint meg kell szüntetni a TenantLockdown CSP által bevezetett korlátozások eltávolítása előtt. 

![Eszközönkénti nézet: a szabályzat kikényszerítenie kell az eszközön.](images/hololens-autopilot-lockdown.png)

Ezek az információk most már az Autopilot többi része mellett találhatók a [Tenantlockdown CSP és az Autopilot alatt.](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)

### <a name="global-assigned-access--kiosk-mode"></a>Globális hozzárendelt hozzáférés – Kioszkmód
- Csökkentett identitáskezelés a kioszkmódhoz, azáltal, hogy engedélyezi a kioszkmódot a rendszer szintjén alkalmazva az új kioszkmódot.

Ez az új funkció lehetővé teszi, hogy a rendszergazda egy HoloLens 2-eszközt több alkalmazás kioszkmódhoz konfiguráljon, amely rendszerszinten alkalmazható, nem rendelkezik affinitással semmilyen identitással a rendszeren, és mindenkire érvényes, aki bejelentkezik az eszközre. Az új funkcióról részletesen a HoloLens globálisan hozzárendelt hozzáférési [kioszkban olvashat.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Alkalmazás automatikus indítása többalkalmazásos kioszkmódban 
- Összpontosított élmény az automatikus alkalmazásindítással, tovább növelve a Kioszk módhoz kiválasztott felhasználói felület és alkalmazásválasztások számának növelése.

Csak a többalkalmazásos kioszkmódra vonatkozik, és csak 1 alkalmazás jelölhető ki automatikus indításra a hozzárendelt hozzáférés konfigurációjának alábbi kiemelt attribútumával. 

Az alkalmazás automatikusan elindul, amikor a felhasználó bejelentkezik. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>A kioszkmód viselkedésének változásai a hibák kezelésével
- Biztonságosabb kioszkmód az elérhető alkalmazások kioszkmódban való meghibásodásának kiküszöbölésével. 

Korábban a kioszkmód alkalmazása során felmerülő hibákról a HoloLens az összes alkalmazást a Start menüben használta. A Windows Holographic 20H2-es verziójában hibák esetén a Start menüben nem jelennek meg alkalmazások az alábbiak szerint: 

![Kép a kioszkmódról, ha az sikertelen.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens-szabályzatok
- Eszközkezelési lehetőségek kifejezetten az eszközkezeléshez létrehozott HoloLenshez. 

Új vegyes valóságú szabályzatok voltak létrehozva a HoloLens 2 rendszerű eszközökhöz a Windows Holographic 20H2-es verziójában. Új szabályozható beállítások: a fényerejének beállítása, a kötet beállítása, a hangfelvételek letiltása vegyes valóságban, a diagnosztika gyűjtésének beállítása és az AAD-csoporttagság gyorsítótára.  

| Új HoloLens-szabályzat                                | Leírás                                                                               | Jegyzetek                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Engedélyezi a fényerejét gombra kattintva letiltható, így a gomb lenyomása nem módosítja a fényerejét.       | 1 Igen, 0 Nem (alapértelmezett)                                                |
| MixedReality\VolumeButtonDisabled                  | A hangerőszabályzó gombok letilthatók, így a billentyű lenyomása nem módosítja a hangerőt.               | 1 Igen, 0 Nem (alapértelmezett)                                                |
| MixedReality\MicrophoneDisabled                    | Letiltja a mikrofont, így nem készít hanganyagot a HoloLens 2-ben.                      | 1 Igen, 0 Nem (alapértelmezett)                                                |
| MixedReality\FallbackDiagnostics                   | A diagnosztikai naplók gyűjtésének viselkedését szabályozza.                               | 0 Letiltva, 1 Engedélyezve az eszköztulajdonosok számára, 2 Engedélyezve az összes számára (alapértelmezett) |
| MixedReality\HeadTrackingMode                      | Jövőbeli használatra fenntartva.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Azt szabályozza, hogy a rendszer hány napig használja az Azure AD-csoporttagság gyorsítótárát az Azure AD-csoportokat megcélzó kioszkok számára. | Lásd alább.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Azure AD-csoporttagság gyorsítótárazése offline kioszkhoz
- Offline kioszkok használata AAD-csoportokkal akár 60 napig.

Ez a szabályzat azt szabályozza, hogy hány napig használható az Azure AD-csoporttagság gyorsítótára a bejelentkezett felhasználók Azure AD-csoportjait célzó hozzárendelt hozzáférés-konfigurációkhoz. Ha ez a szabályzatérték csak 0-snál nagyobb értékre van állítva, akkor a rendszer másként nem használja a gyorsítótárat.  

Név: AADGroupMembershipCacheValidityInDays URI érték: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Perc – 0 nap  
Maximum – 60 nap 

A szabályzat megfelelő használatának lépései: 
1. Hozzon létre egy eszközkonfigurációs profilt az Azure AD-csoportokat megcélzó kioszkhoz, és rendelje hozzá HoloLens-eszköz(ök)hez. 
1. Hozzon létre egy egyéni OMA URI-alapú eszközkonfigurációt, amely a kívánt számú napra (> 0) állítja be ezt a szabályzatértéket, és hozzárendeli a HoloLens-eszköz(ök)hez. 
    1. Az URI értéket az OMA-URI szövegmezőben a következőként kell megadni: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Az érték minimális/maximálisan megengedett lehet.
1. HoloLens-eszközök regisztrálása és annak ellenőrzése, hogy mindkét konfiguráció alkalmazva lesz-e az eszközre. 
1. Az Azure AD 1 felhasználó bejelentkeztethetővé válik, ha elérhető az internet, és a felhasználói bejelentkezés és az Azure AD-csoporttagság sikeres megerősítés után létrejön a gyorsítótár. 
1. Az 1. Azure AD-felhasználó mostantól offline állapotba tudja vinni a HoloLenst, és kioszkmódhoz használhatja, ha a szabályzat értéke X számú napot tesz lehetővé. 
1. A 4. és az 5. lépés megismételhető bármely más Azure AD-felhasználó N felhasználója számára. Itt az a legfontosabb, hogy minden Azure AD-felhasználónak be kell jelentkeznie az eszközre az internet használatával, hogy legalább egyszer megállapítsuk, hogy tagja-e annak az Azure AD-csoportnak, amelyhez a kioszkkonfigurációt megcélozták. 
 
> [!NOTE]
> Amíg egy Azure AD-felhasználó esetében végre nem hajtotta a 4. lépést, a "leválasztott" környezetekben hiba lép fel. 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Új eszközkorlátozási szabályzatok a HoloLens 2-höz
- Lehetővé teszi, hogy a felhasználók meghatározott eszközkezelési szabályzatokat kezeljenek, például letiltják a kiépítési csomagok hozzáadását vagy eltávolítását.

Újonnan engedélyezett szabályzatok, amelyek lehetővé teszik a HoloLens 2-eszközök további felügyeleti lehetőségeit. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone (Időzóna konfigurálása)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Az AllowAddProvisioningPackage és az AllowRemoveProvisioningPackage két új- és hozzá van adva a közös [eszközkorlátozásainkhoz.](hololens-common-device-restrictions.md)

> [!NOTE]
> A [RemoteLock esetében](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)a HoloLens csak a ./Vendor/MSFT/RemoteLock/Lock konfigurációt támogatja. A PIN-kódokkal (például alaphelyzetbe állítással és helyreállítással) kapcsolatos konfigurációk nem támogatottak.

### <a name="new-power-policies-for-hololens-2"></a>Új energiagazdálkodási szabályzatok a HoloLens 2-hez
- További lehetőségek arra, hogy a HoloLens mikor alszanak vagy zárolnak energiagazdálkodási szabályzatokkal. 

Ezek az újonnan hozzáadott szabályzatok lehetővé teszik a rendszergazdák számára az energiagazdálkodási állapotban, például az üresjárati időtúllépés szabályozását. Az egyes szabályzatokkal kapcsolatos további információkért kattintson a szabályzatra mutató hivatkozásra.

|     Szabályzatdokumentáció hivatkozása                |     Jegyzetek                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Példaérték a Windows Configuration Designerben való használatra, például:  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Példaérték a Windows Configuration Designerben való használatra, például:  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Példaérték a Windows Configuration Designerben való használatra, például 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Példaérték a Windows Configuration Designerben való használatra, például 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Példaérték a Windows Configuration Designerben való használatra, például:   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Példaérték a Windows Configuration Designerben való használatra, például:  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Ez a két új, DisplayOffTimeoutOnBattery és DisplayOffTimeoutPluggedIn új- és hozzá van adva a gyakori [eszközkorlátozásainkhoz.](hololens-common-device-restrictions.md)

> [!NOTE]
> A HoloLens 2 egységes felhasználói élménye érdekében győződjön meg arról, hogy a DisplayOffTimeoutOnBattery és a StandbyTimeoutOnBattery értékei is azonosak. Ugyanez vonatkozik a DisplayOffTimeoutPluggedIn és a StandbyTimeoutPluggedIn állapotra. A modern készenléti üzemmóddal kapcsolatos további részletekért tekintse meg a Kijelző, alvó és [hibernált](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) inaktív időzítők.

### <a name="newly-enabled-update-policies-for-hololens"></a>Újonnan engedélyezett frissítési szabályzatok a HoloLenshez
- További lehetőségek a Frissítések telepítésekor vagy a Frissítések felfüggesztése gomb letiltásával a frissítések biztosításához.

Ezek a frissítési szabályzatok mostantól engedélyezve vannak a HoloLens 2-eszközökön:
-   [Frissítés/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Frissítés/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Frissítés/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

A frissítési szabályzatokkal és azok HoloLens-eszközökön való használatával kapcsolatos részletes információkat itt olvashatja: [HoloLens-frissítések kezelése.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>A Beállítások oldal láthatósága engedélyezve a HoloLens 2-ben
- Nagyobb felhasználói felületi vezérlés a Beállítások alkalmazásban, amely nem mindig mutat néhány oldalt.

Ezzel engedélyeztünk egy olyan szabályzatot, amely lehetővé teszi a rendszergazdák számára, hogy megakadályozzák a Rendszerbeállítások alkalmazás adott lapjainak láthatóvá vagy hozzáférhetővé tételeit, vagy hogy ezt a megadott oldalak kivételével minden oldalon megtenzék. A funkció teljes testreszabásához kattintson az alábbi hivatkozásra.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Ha meg szeretne ismerkedni a HoloLens 2-ben testreszabható oldalbeállításokkal, látogasson el a [Beállítási URI-k oldalunkra.](settings-uri-list.md) 
 
![Képernyőkép a Beállítások alkalmazásban módosított aktív órákról](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Kutatási mód
Kutatási módban a HoloLens 2 a számítógépes látáskutatás eszköze lesz. A korábbi kiadásokhoz képest a HoloLens 2 kutatási módja a következő előnyökkel jár:
-   A HoloLens (1. generációs) kutatási módban elérhetővé vált érzékelők mellett mostantól IMU-érzékelői hozzáférést is biztosítunk, beleértve a gyorsulásmérőt, a groscope-t és a kilométermérőt.
-   A HoloLens 2 olyan új képességeket biztosít, amelyek a Kutatási móddal együtt használhatók. Pontosabban a kézkövetési és a szemkövetési API-khoz való hozzáférés, amelyek a kísérletek gazdagabb készletét biztosítják.

A kutatók mostantól lehetővé teszik a Research Mode (Kutatási mód) engedélyezését a HoloLens-eszközeiken a külső elérésű nyers képérzékelők streamjéhez való hozzáféréshez. A HoloLens 2 research mode (Kutatási mód a HoloLens 2-hez) az gyorsulásmérő, a groscope és a mérőmérő mérőóra-mérőkhez is hozzáférést biztosít. A felhasználók adatainak védelme érdekében a nyers szemkövetéses kameraképek nem érhetők el a Research Mode(Kutatási mód) szolgáltatáson keresztül, de a szem-tekintet iránya a meglévő API-kon keresztül érhető el.

További technikai részletekért tekintse meg a [kutatási mód](https://docs.microsoft.com/windows/mixed-reality/research-mode) dokumentációját.

### <a name="recording-length-increased"></a>Rögzítés hosszának megnövelve
Az ügyfelek visszajelzései miatt növeljük a vegyes valóságú [rögzítések hosszát.](holographic-photos-and-videos.md) A vegyes valóságú rögzítések alapértelmezés szerint nem lesznek 5 percre korlátozva, hanem a maximális rögzítési hosszt számítják ki a rendelkezésre álló lemezterület alapján. Az eszköz a teljes lemezterület 80%-ának megfelelő szabad lemezterület alapján megbecsüli a videófelvétel maximális időtartamát.

> [!NOTE]
> A HoloLens az alapértelmezett videofelvételi hosszt használja (5 perc), ha a következők valamelyike bekövetkezik:
> - A becsült maximális rögzítési időtartam kisebb, mint az alapértelmezett 5 perc.
> - A rendelkezésre álló lemezterület kevesebb, mint a teljes lemezterület 20%-a.

A teljes követelményeket a holografikus fényképek és [videók dokumentációjában találja.](holographic-photos-and-videos.md#maximum-recording-length) 

### <a name="improvements-and-fixes-in-the-update"></a>A frissítés fejlesztései és javításai:
- Az OOBE több képernyője már sötét módban van.
- További információ: A tartalomnak a legújabb online adatvédelmi nyilatkozatra kell mutasson.
- Elhárítottunk egy problémát, amely miatt a felhasználók nem létesíthették ki a VPN-profilokat a kiépítési csomagokon keresztül.
- Ki van javítva a VPN-kapcsolat proxykonfigurációs problémája.
- Szabályzat frissítve az USB-függvények Enumerálásának letiltásához az MDM for NCM for AllowUsbConnection esetén.
- Elhárítottunk egy problémát, amely miatt egy HoloLens-eszköz nem jelent meg az Fájlkezelő-ban a Media Transfer Protocol (MTP) protokollon keresztül, amikor az eszköz egyalkalmazásos [kioszkként van beállítva.](hololens-kiosk.md) Vegye figyelembe, hogy az MTP (és általában az USB-kapcsolat) továbbra is letiltható az [AllowUSBConnection szabályzattal.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Kijavítottunk egy hibát, amely miatt a Start menü ikonjai megfelelően voltak skálázva Kioszk módban.
- Kijavítottunk egy hibát, amely az Azure AD-csoportokat célzó kioszkmódot zavaró HTTP-gyorsítótárazás miatt történt.
- Ki lett javítva az a hiba, amely miatt a felhasználók nem tudtak a Párosítás gombot használni a fejlesztői módnak a kiépítési csomagokkal való engedélyezése után, kivéve, ha letiltották és újra engedélyezték a Fejlesztői módot.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. novemberi frissítés
- Build 18362.1085

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a Windows Holographic 20H2-es verziójának legújabb funkció kiadását.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, 2004-es és 2020. októberi frissítés
- Build 19041.1124
 
A frissítés fejlesztései és javításai:

- Eltávolítottunk egy felesleges ellenőrzést, amely futásidejű rendszerhibát okozott.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. októberi frissítés
- Build 18362.1081

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a Windows Holographic 2004-es verziójához elérhető legújabb buildeket.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, 2004-es és 2020. szeptemberi frissítés
- Build 19041.1117

A frissítés fejlesztései és javításai:

- Elhárít egy problémát, amely Visual Studio megakadályozta az alkalmazás hibakeresését, ha a SupportsMultipleInstances="true" szó jelen van az appxmanifestben.
- Ez a kiadás tartalmazza az NCSI-proxyészlelési javítást, amely a hálózati proxyn keresztüli sikertelen internetes észlelést oldja meg. Az NCSI számítógépproxyt és profilonkénti proxyt használhat az internetkapcsolat észleléséhez. A későbbi kiadásban az NCSI támogatni fogja a felhasználónkénti proxyt.
- A legtöbb Windows Mixed Reality az előrefelé vezető vektor párhuzamos a talajjal, amikor a felhasználó fejének semleges pozícióban van. A HoloLens 2 korábbi verziói azonban úgy igazítják a vektort, hogy az inkább a kijelzőpanelekre legyen igazított, amely az ideális tájoláshoz képest néhány fokkal lefelé van döntésre va. A HoloLens 2 újabb verziói javították ezt, hogy szemantikai konzisztenciát biztosítsanak az űrlaptényezők között.
- Továbbfejlesztett kézkövetési robusztusság, amely adott forgatókönyvekben kevesebb nyomkövetési veszteségeket eredményez.
- Ez a kiadás egy javítást tartalmaz a hang-időbélyegző minőségének javításához, amely hozzájárult a videórögzítési problémákhoz.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, 1903-as és 2020. szeptemberi frissítés
- Build 18362.1079

A frissítés fejlesztései és javításai:

- A legtöbb Windows Mixed Reality az előrefelé vezető vektor párhuzamos a talajjal, amikor a felhasználó fejének semleges pozícióban van. A HoloLens 2 korábbi verziói azonban úgy igazítják a vektort, hogy az inkább a kijelzőpanelekre legyen igazított, amely az ideális tájoláshoz képest néhány fokkal lefelé van döntésre va. A HoloLens 2 újabb verziói javították ezt, hogy szemantikai konzisztenciát biztosítsanak az űrlaptényezők között.
- Továbbfejlesztett kézkövetési robusztusság, amely adott forgatókönyvekben kevesebb nyomkövetési veszteségeket eredményez.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, 2004-es verzió – 2020. augusztusi frissítés
- Build 19041.1113

A frissítés fejlesztései és javításai:

- A Beállítási alkalmazás a továbbiakban nem követi a felhasználót az Írisz-regisztráció vagy a Szemkövetési csoport használata során.
- Kijavítottunk egy hibát, amely miatt a kiépítési csomag OOBE során való alkalmazása, amely átnevezi az eszközt, és más műveleteket hajt végre (például egy hálózathoz csatlakozik) az átnevezés miatt nem hajt végre más műveleteket az eszköz újraindítása után.
- Módosított színséma a kezdeti eszközbeállítási folyamatokhoz a vizualizáció minőségének javítása érdekében.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. augusztusi frissítés
- Build 18362.1074

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat. Javasoljuk, hogy próbálja ki a Windows Holographic 2004-es verziójához elérhető legújabb buildeket.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, 2004-es verzió – 2020. júliusi frissítés
- Build 19041.1109

A frissítés fejlesztései és javításai:

- A fejlesztők mostantól dönthetnek úgy, hogy engedélyezik vagy letiltják a Eszközportál biztonságos kapcsolatot igényelnek.
- Javult az alkalmazások operációsrendszer-frissítések utáni indításának megbízhatósága.
- A beérkezett üzenetek alapértelmezett fényerejét 100%-ra módosítottuk.
- A HoloLens 2-es Windows eszközportál HTTPS-továbbítással kapcsolatos probléma elhárítása.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. júliusi frissítés
- Build 18362.1071

A frissítés fejlesztései és javításai:

- Kijavítottunk egy problémát, amely miatt a hologramok eltűnhetnek a Unity-alkalmazásokban a követés elvesztésekor vagy visszaszerzésekor.
- Kijavítottunk egy hibát, amely miatt az exkluzív HoloLens-alkalmazások visszamentek a rendszerhéjba, miközben a HoloLens Emulatort hardvergyorsítással használt bizonyos eszközökön.
- A HoloLens 2-Windows eszközportál HTTPS-továbbítással kapcsolatos probléma elhárítása.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, 2004-es verzió – 2020. júniusi frissítés
- Build 19041.1106

A frissítés fejlesztései és javításai:

- Az egyéni MRC-rögzítők mostantól új alapértelmezett értékekkel rendelkeznek bizonyos tulajdonságokhoz, ha nincsenek megadva.
  - On the *MRC Video Effect*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Modern headset))
  - Az *MRC audiohatáson:*
    - LoopbackGain (az aktuális "App Audio Gain" érték a Vegyes valóság rögzítése oldalán a Windows eszközportál)
    - MicrophoneGain (az aktuális "Mic Audio Gain" érték a Vegyes valóság rögzítése lapján Windows eszközportál)
- Kijavítottunk egy hibát, amely javítja a hangminőséget a vegyes valóságú rögzítési forgatókönyvekben. Pontosabban, ennek a javításnak meg kell szüntetnie a felvétel hangberekeszét a **Start menü** megjelenítésekor.
- Továbbfejlesztett hologram-stabilitás a rögzített videókban.
- Megoldottuk azt a problémát, amely miatt a vegyes valóságú rögzítés nem tudott videót rögzíteni, miután az eszköz több napig készenléti állapotban maradt.
- A HolographicSpace.UserPresence API általában le van tiltva Unity-alkalmazások esetében. Ez a viselkedés elkerüli azt a problémát, amely miatt egyes alkalmazások szünetelnek a vizor tükrözése esetén, még akkor is, ha a "futtatás a háttérben" beállítás engedélyezve van. Az API mostantól engedélyezve van a Unity 2018.4.18-as és újabb, valamint 2019.3.4-es és újabb verzióihoz.
- Ha egy Eszközportál kapcsolaton keresztül fér hozzá a Wi-Fi, előfordulhat, hogy egy webböngésző érvénytelen tanúsítvány miatt megakadályozza a hozzáférést. Előfordulhat, hogy a böngésző hibát jelez( például "ERR_SSL_PROTOCOL_ERROR", még akkor is, ha az eszköz tanúsítványa korábban megbízható volt. Ebben az esetben nem haladhat előre a Eszközportál, mivel nincs lehetőség a biztonsági figyelmeztetések figyelmen kívül hagyása. Ez a frissítés megoldotta a problémát. Ha az eszköztanúsítványt korábban letöltötték, és a böngésző biztonsági figyelmeztetései el lett távolítva a számítógépen, és SSL-hiba történik, az új tanúsítványt le kell tölteni, és megbízhatónak kell lennie a böngésző biztonsági figyelmeztetései esetén.
- Lehetővé tette olyan futásidejű kiépítési csomag létrehozása, amely MSIX-csomagok használatával képes alkalmazásokat telepíteni.
- Hozzá van adva egy beállítás a Beállítási rendszer  >    >  **hologramjaiban,** amely lehetővé teszi a felhasználók számára, hogy automatikusan eltávolítsák az összes hologramot Mixed Reality eszköz leállított eszközéről.
- Kijavítottunk egy hibát, amely miatt a HoloLens-alkalmazások úgy módosítják a képpontformátumukat, hogy feketén rendereljenek a HoloLens emulátorban.
- Kijavítottunk egy hibát, amely összeomlást okozott az Írisz bejelentkezése során.
- Kijavítottunk egy hibát, amely a már meglévő alkalmazások ismételt áruházi letöltésével kapcsolatos.
- Kijavítottunk egy hibát, amely meggátolja, hogy a modern alkalmazások Microsoft Edge meg többször.
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
    - LoopbackGain (az aktuális "App Audio Gain" érték a Vegyes valóság rögzítése oldalán Windows eszközportál)
    - MicrophoneGain (az aktuális "Mic Audio Gain" érték a Vegyes valóság rögzítése oldalán Windows eszközportál)
- A HolographicSpace.UserPresence API általában le van tiltva a Unity-alkalmazások esetében. Ez a viselkedés elkerüli azt a problémát, amely miatt egyes alkalmazások szünetelnek a vizor felfelé tükrözése esetén, még akkor is, ha a háttérben való futtatás engedélyezve van. Az API most már engedélyezve van a Unity 2018.4.18-as és újabb, valamint 2019.3.4-es és újabb verzióihoz.
- Kijavítottunk egy hibát, amely miatt a HoloLens-alkalmazások a képpontformátumukat feketére változtatták a HoloLens Emulatorban.
- Ki van javítva a Photos alkalmazás 1903-as kiadásból való frissítés utáni első indításkor való indításával kapcsolatos hiba.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, 2004-es verzió  
- Build – 19041.1103

A HoloLens 2, *a Windows Holographic 2004 2020.* májusi fő szoftverfrissítése számos izgalmas új funkciót tartalmaz, többek között az Windows Autopilot támogatását, az alkalmazás sötét módját, az USB Ethernet-támogatást az 5G/LTE-elérési pontokhoz. A legújabb kiadásra való frissítéshez nyissa meg a **Beállítások** alkalmazást, nyissa meg az Update & Security (Biztonsági frissítések frissítése) lehetőséget, és válassza a   Check for Updates  **(Frissítések keresése)** ****   gombot. 

|             Szolgáltatás                              |          Leírás                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Új eszközök előzetes konfigurálása és zökkenőmentes beállítása éles környezetben a Windows AutoPilot használatával                 |
|       FIDO 2-támogatás                             |          A FIDO2 biztonsági kulcsok támogatása a megosztott eszközök gyors és biztonságos hitelesítésének engedélyezéséhez            |
|       Továbbfejlesztett kiépítés                      |          Kiépítési csomag zökkenőmentes alkalmazása USB-meghajtóról a HoloLensre                              |
|       Alkalmazástelepítés állapota                 |          Ellenőrizze a telepítés állapotát a Settings (Beállítások) alkalmazásban a HoloLens 2-be MDM-en keresztül lekért alkalmazások esetében               |
|       Konfigurációszolgáltatók (CSP-k)   |          Új konfigurációs szolgáltatók hozzáadva a rendszergazdai vezérlési képességek javítása érdekében                 |
|       USB 5G/LTE-támogatás                       |          A bővített USB Ethernet-képesség lehetővé teszi az 5G/LTE támogatását                                    |
|       Sötét alkalmazás mód                              |          Sötét alkalmazás mód érhető el a sötét és világos módokat támogató alkalmazásokhoz, ami javítja a megtekintési élményt        |
|       Hangparancsok                             |          További rendszerhangparancsok támogatása a HoloLens kéz nélküli vezérléséhez                           |
|       A kézkövetés fejlesztései                 |          A kézkövetés fejlesztései pontosabb gombokat és 2D-s belós interakciókat eredményeznek                        |
|       Minőségi fejlesztések és javítások                 |          Különböző rendszerteljesítményi és megbízhatósági fejlesztések a platformon                            |

### <a name="support-for-windows-autopilot"></a>Támogatás a Windows Autopilot

Windows Autopilot HoloLens 2-höz való regisztrálása lehetővé teszi, hogy az eszköz értékesítési csatornája előzetesen regisztrálja a HoloLenst az Intune-bérlőben. Amikor az eszközök megérkeznek, készen állnak a bérlőn megosztott eszközökként való önálló üzembe helyezésre. Az önálló üzembe helyezés előnyeinek kihasználásához az eszköznek a beállítás első képernyőjén csatlakoznia kell egy hálózathoz egy USB-C-to-Ethernet kapcsolattal.

Miután a felhasználó elindítja az Autopilot önkiszolgáló üzembe helyezési folyamatát, a folyamat a következő lépéseket teszi:

1. Az eszköz csatlakozása a Azure Active Directory (Azure AD) szolgáltatáshoz.
1. Az Azure AD használatával regisztrálja az eszközt a Microsoft Intune (vagy egy másik MDM-szolgáltatásban).
1. Töltse le az eszközre vonatkozó szabályzatokat, tanúsítványokat és hálózati profilokat.
1. Az eszköz kiépítése.
1. A bejelentkezési képernyőt mutatja be a felhasználónak.

További információkért olvassa el [Windows Autopilot HoloLens 2-hez útmutatót.](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Lépjen kapcsolatba a fiókkezelővel az AutoPilot előzetes verzióhoz való csatlakozáshoz. Az Autopilot-kompatibilis eszközök hamarosan megkezdik a szállítást.*

### <a name="fido2-security-key-support"></a>FIDO2 biztonsági kulcs támogatása

Egyes felhasználók egy HoloLens-eszközt osztnak meg másokkal munkahelyi vagy iskolai környezetben. Ezért fontos, hogy a felhasználók könnyedén, hosszú felhasználónév és jelszó beírása nélkül is használhasson. A Fast Identity Online (FIDO) lehetővé teszi, hogy a szervezetben (Azure AD-bérlőben) bárki zökkenőmentesen jelentkezzen be a HoloLensbe felhasználónév vagy jelszó megadása nélkül.

A FIDO2 biztonsági kulcsok egy "unphishable" szabványalapú, jelszó nélküli hitelesítési módszer, amely bármilyen tényezőben elérhető. A FIDO a jelszó nélküli hitelesítés nyílt szabványa. Lehetővé teszi a felhasználók és a szervezetek számára, hogy felhasználónév vagy jelszó nélkül jelentkezzenek be az erőforrásaikba. Ehelyett egy külső biztonsági kulcsot vagy egy eszközbe épített platformkulcsot használnak.

Első lépések: [Jelszó nélküli biztonsági kulcsos bejelentkezés engedélyezése.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Továbbfejlesztett MDM-regisztráció kiépítési csomagon keresztül

A kiépítési csomagok segítségével konfigurációs fájlon keresztül állíthatja be a HoloLens-konfigurációt, nem pedig a HoloLens-t. Korábban a kiépítési csomagokat a HoloLens belső memóriájába kellett másolni. Mostantól USB-meghajtón is lehet őket használni, így könnyebben újra felhasználhatók több HoloLens-eszközön, és párhuzamosan is kiépítheti az eszközöket. A kiépítési csomagok mostantól támogatják az eszközkezelésben való regisztráláshoz szükséges mezőket is, így a kiépítés után nincs szükség manuális telepítésre.

A kipróbálhoz:

1. Töltse le a Windows Configuration Designer legújabb verzióját a Windows Áruházból a számítógépre.
1. Válassza **a HoloLens-eszközök** kiépítése  >  **HoloLens 2-eszközök kiépítése lehetőséget.**
2. Készítse el a konfigurációs profilt. Ezután másolja az összes létrehozott fájlt egy USB-C tárolóeszközre.
3. Csatlakoztassa az USB-C eszközt bármely frissen flash elemekkel rendelkező HoloLenshez. Ezután nyomja le **a hangerőt a** kiépítési csomag  +   alkalmazáshoz.

### <a name="line-of-business-application-install-status"></a>Üzletági alkalmazások telepítési állapota

Az üzletági alkalmazások MDM-alkalmazások üzembe helyezése és kezelése kritikus fontosságú a HoloLenshez. A rendszergazdáknak és a felhasználóknak meg kell tekinteniük az alkalmazástelepítés állapotát a naplózás és a diagnosztika érdekében. Ebben a kiadásban további részletekkel bővült a **Settings** Accounts Access work or school (Beállítások fiókok elérése munkahelyi vagy iskolai fiókhoz) lapon  >    >    >  **Kattintson a fiók adatai**  >  **elemre.**

### <a name="additional-csps-and-policies"></a>További CSP-k és szabályzatok

A [konfigurációszolgáltató (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) az eszköz konfigurációs beállításainak olvasására, beállítására, módosítására vagy törlésére való felület. Ebben a kiadásban további szabályzatok támogatásával növeljük a rendszergazdák felügyeletét az üzembe helyezett HoloLens-eszközök felett. A HoloLens által támogatott CSP-k listájáért lásd: [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

A kiadás újdonsága:

**Szabályzat csP-ja** 

A Szabályzatkonfiguráció szolgáltató lehetővé teszi, hogy a vállalat házirendeket konfigurálja Windows-eszközökön. Ebben a kiadásban új szabályzatokat adtunk hozzá a HoloLenshez, amelyek itt vannak felsorolva. További információ: [A HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)által támogatott szabályzat-CSP-k.  

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

A NetworkQoSPolicy konfigurációs szolgáltató hálózati szolgáltatásminőségi (QoS) szabályzatokat hoz létre. A QoS-házirend egyező feltételek alapján hajt végre műveleteket a hálózati forgalomon. További információ: [NetworkQoSPolicy CSP.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Bővített USB Ethernet-támogatás az 5G/LTE-alapú, internetre csatlakoztatott eszközökhöz

Támogatás lett hozzáadva bizonyos, a HoloLens 2-hez USB-n keresztül csatlakozó mobileszközök, például 5G/LTE-telefonok és Wi-Fi-elérési pontok engedélyezéséhez. Ezek az eszközök mostantól egy másik Ethernet-kapcsolatként **jelennek** meg a hálózati beállítások között. (A külső illesztőt igénylő mobil broadband eszközök nem támogatottak.) Ez a funkció nagy sávszélességű kapcsolatokat tesz lehetővé, Wi-Fi nem érhető el, Wi-Fi a Wi-Fi nem elég nagy teljesítményű. További információ a támogatott USB-eszközökről: [Connect to Bluetooth and USB-C devices (Csatlakozás Bluetooth- és USB-C-eszközökhöz).](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### <a name="hand-tracking-improvements"></a>A kézkövetés fejlesztései

Ez a kiadás számos kézkövetési fejlesztést tartalmaz:

- **A stabilitás rámutatása:** A rendszer most ellenáll az indexavad megakadása ellen, amikor a torkok eltolást érnek el. Ez a módosítás javítja a gombok leküldésének, begépelése, görgetése tartalmának pontosságát, és még sok más is! 
- **Kevesebb véletlen légi koppintás:** Továbbfejlesztettük a légikoppintásos kézmozdulat észlelését. Számos gyakori forgatókönyvben kevesebb véletlen aktiválás történt, például amikor a két kéz az oldalára kerül.
- **A felhasználói kapcsoló megbízhatósága:** A rendszer mostantól gyorsabb és megbízhatóbb az eszköz megosztásakor a kézméret frissítésében.
- **Kisebb kézlopás:** Továbbfejlesztettük az olyan esetek kezelését, amelyekben kétnél több kéz látható az érzékelőkkel. Ha többen dolgoznak szorosan együtt, sokkal kisebb az esélye annak, hogy a nyomon követt kéz "elugrik" a felhasználótól a jelenetben található valaki más kézjéhez.
- **Rendszer megbízhatósága:** Kijavítottunk egy hibát, amely miatt a kézkövetés leállt, amikor az eszköz nagy terhelés alatt áll.

### <a name="dark-mode"></a>Sötét mód

Számos Windows-alkalmazás már a sötét és a világos módot is támogatja. A HoloLens 2 felhasználói kiválaszthatják az alapértelmezett módot a mindkettőt támogató alkalmazásokhoz. A frissítés után az alapértelmezett alkalmazásmód "sötét", de ezt a beállítást könnyen megváltoztathatja: Lépjen a Beállítások Rendszer színei Válassza ki az alapértelmezett  >    >    >  **alkalmazásmódot.** 

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

Mostantól az eszközön található bármely alkalmazáshoz használhat hangparancsokat. További információ: Use your voice to operate HoloLens (A hang használata [a HoloLens működtetéséhez).](https://docs.microsoft.com/hololens/hololens-cortana) Lásd [még: A HoloLens 2 támogatott nyelvei.](https://docs.microsoft.com/hololens/hololens2-language-support)  

### <a name="cortana-updates"></a>Cortana-frissítések

A frissített alkalmazás integrálható a Microsoft 365, hogy jobban el tudja látni az eszközeit (jelenleg csak US-English érhető el). A HoloLens 2-ben a Cortana már nem támogat bizonyos eszközspecifikus parancsokat, például a kötetek beállítását vagy az újraindítást. Ezeket a beállításokat már támogatják az új rendszerhangparancsok. Az új Cortana alkalmazásról a blogunkban talál [további információt.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>Minőségi fejlesztések és javítások

Fejlesztések és javítások a frissítésben is:  
- Bevezettünk egy aktív kijelző-megjelenítő rendszert. Ez a funkció javítja a hologramok stabilitását és igazítását. Mostantól a helyén maradnak, ha a fejet oldalról oldalra mozgatja.
- Kijavítottunk egy hibát, Wi-Fi a HoloLensbe streamelés rendszeresen megszakadt. Ha egy alkalmazás azt jelzi, hogy kis késésű streamelésre van szüksége, implementálja a javítást a [SetSocketMediaStreamingMode függvény hívásával.](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)
- Kijavítottunk egy lefagyó eszközt, amely a streamelés során, kutatási módban történt.
- Kijavítottunk egy hibát, amely miatt bizonyos esetekben a megfelelő felhasználó nem jelenik meg a bejelentkezési képernyőn a munkamenet befejezésekor.
- Kijavítottunk egy hibát, amely miatt a felhasználók nem tudtak MDM-naplókat exportálni a **Settings (Beállítások) segítségével.**
- Kijavítottunk egy hibát, amely miatt a szemkövetés azonnal, a beépített beállítás után a vártnál alacsonyabb lehet.
- Kijavítottunk egy problémát, amely miatt a szemkövetési alrendszer bizonyos körülmények között nem tudott inicializálni vagy végrehajtani a beépítést.
- Kijavítottunk egy problémát, amely miatt a rendszer a már beállított felhasználót kéri.
- Kijavítottunk egy problémát, amely miatt a illesztő összeomlott a szemkontraszt során.
- Kijavítottunk egy hibát, amely miatt az ismételt bekapcsológombnyomások 60 másodperces rendszer-időtúllépést és rendszerhéj-összeomlást okozhatnak.
- Nagyobb stabilitás a mélységi pufferek számára.
- Hozzáadtunk egy **Megosztás gombot** a Visszajelzési központ, hogy a felhasználók könnyebben megosztanának visszajelzéseket.
- Kijavítottunk egy hibát, amely miatt a RoboRaid wan nincs megfelelően telepítve.

### <a name="known-issues"></a>Ismert problémák

- A zh-CN rendszernyelvvel kapcsolatos probléma megakadályozza, hogy a hangparancsok vegyes valóságú rögzítést készítsenek, vagy megjelenítsék az eszköz IP-címét.
- A probléma megoldásához el kell indítania a Cortana alkalmazást, miután elindítja az eszközt a "Cortana" hangaktiválás használatához. Ha frissített egy 18362-es buildről, akkor előfordulhat, hogy a Cortana-alkalmazás előző verziójának egy második alkalmazáscsempe is látható, amely már nem működik a **Start menüben.**

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. májusi frissítés 
- Build 18362.1061

Ez a havi minőségi frissítés nem tartalmaz jelentős változásokat, mivel a csapat a Windows Holographic 2004 májusi frissítésén dolgozott a korábban leírtak szerint.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. áprilisi frissítés
- Build 18362.1059

**Sötét mód a támogatott alkalmazásokhoz** 

Számos Windows-alkalmazás támogatja a sötét és a világos módot is. A HoloLens 2 ügyfelei mostantól kiválaszthatják az alapértelmezett módot a mindkét színsémát támogató alkalmazásokhoz. Az ügyfelek visszajelzései alapján az alapértelmezett alkalmazásmódot "sötétre" állítva bármikor módosíthatja ezt a beállítást: Lépjen a Settings > System > Colors (Beállítások > **System > Colors)** elemre, és keresse meg a **"Choose your default app mode"** (Az alapértelmezett alkalmazásmód kiválasztása) lehetőséget.

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
- A hologram stabilitásának javítása vegyes valóságban a *HolographicDepthReprojectionMethod DepthReprojection algoritmus* használata esetén.
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
- Továbbfejlesztett kézkövetés, hogy amikor az indexavacsával koppint, annak az ujjlenyomatnak a felső része kevésbé lesz nagy valószínűséggel megördülve.
- Javult a fejkövetés, a térbeli leképezés és más futásidők megbízhatósága.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, 1903-as verzió – 2020. januári frissítés 
- Build 18362.1043
 
A frissítés fejlesztései és javításai:

- Továbbfejlesztett stabilitás az exkluzív alkalmazásokhoz a HoloLens 2 emulátor használata során.

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
- Ki lett javítva az indításkor szüneteltetett állapotban elakadó holografikus alkalmazások problémáinak megoldása, amíg a Start menü meg nem nyitották, majd be nem zárták.
- Az OpenXR-futásidejű megfelelőség javításai és fejlesztései a HoloLens 2-hez és az emulátorhoz.
