---
title: Az új Microsoft Edge
description: Tudnivalók az új Edge-alkalmazásról
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, edge, internet, böngésző
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 8ef73733b9fa4f422335977be860371b9570d549
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189698"
---
# <a name="introducing-the-new-microsoft-edge"></a>Az új Microsoft Edge

![Az örökölt embléma Microsoft Edge új embléma Microsoft Edge animációja.](images/new-edge.gif)

Az új Microsoft Edge a nyílt forráskódú [Chromium,](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) hogy jobb kompatibilitást biztosítsunk az ügyfelek számára, és hogy a webfejlesztők számára kevésbé töredezettebb legyen a web.

A [Windows Holographic 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1)verziójával az új Microsoft Edge első alkalommal HoloLens 2 ügyfél számára! Ossza meg a visszajelzéseket és  a hibákat a csapatunkkal az új szolgáltatás Visszajelzés küldése funkcióját Microsoft Edge vagy a [Visszajelzési központ.](hololens-feedback.md)

> [!IMPORTANT]
> Ez az Microsoft Edge automatikusan lecseréli az örökölt Microsoft Edge, amely már nem [támogatott az](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) új kiadásokban.

![Új Microsoft Edge képernyőkép.](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>Az új alkalmazás Microsoft Edge

Az új Microsoft Edge ![új Microsoft Edge ikon.](images/new_edge_logo.png) A (kék és zöld örlő ikon jelöli) a rendszer a Start menü és automatikusan elindul, amikor aktivál egy webes hivatkozást.

> [!NOTE]
> Amikor először indítja el az új Microsoft Edge a 2. HoloLens, a beállítások és az adatok importálva lesznek az örökölt Microsoft Edge.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Szabályzatbeállítások konfigurálása az új Microsoft Edge

Az új Microsoft Edge a 2. HoloLens böngésző-szabályzatok sokkal szélesebb készletét kínálják a rendszergazdáknak, mint ami korábban az örökölt Microsoft Edge.

Az új szabályzatbeállítások kezelésével kapcsolatos további információkért íme néhány hasznos forrás Microsoft Edge:

- [A Microsoft Edge beállításainak konfigurálása a Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Microsoft Edge régi verziója szabályzatleképezés Microsoft Edge beállítása](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [A Google Chrome Microsoft Edge szabályzatleképezéshez](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Az [Microsoft Edge Enterprise teljes dokumentációja](/deployedge/)

> [!IMPORTANT]
> Az új szabályzatok által támogatott böngésző-szabályzatok mennyisége miatt Microsoft Edge csapatunk nem tudja garantálni, hogy minden új szabályzat a 2. HoloLens működik. Azonban teszteltük és megerősítettük, mint az új Microsoft Edge a 2. HoloLens által korábban támogatott minden korábbi Microsoft Edge szabályzatnak megfelelőt. A [Microsoft Edge régi verziója](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) Microsoft Edge szabályzatleképezéssel kapcsolatos további Microsoft Edge a 2. Microsoft Edge-ben használt korábbi Microsoft Edge-szabályzatok új megfelelőjét HoloLens találja.
>
> Legalább két új szabályzat Microsoft Edge, amelyekről tudjuk, hogy *a* 2. HoloLens nem fognak működni:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Mire számíthatunk a 2. Microsoft Edge új HoloLens után?

Mivel az új Microsoft Edge egy natív Win32-alkalmazás, amely egy új UWP-adapterréteggel rendelkezik, amely lehetővé teszi, hogy csak UWP-eszközökön, például a HoloLens 2-n fusson, előfordulhat, hogy egyes funkciók nem érhetők el azonnal. Az elkövetkező hónapokban új forgatókönyveket és funkciókat fogunk támogatni, ezért tekintse át ezt a helyet naprakész információkért.

**A várható forgatókönyvek és funkciók:**
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
- Tartalom visszaállítása a megfelelő ablakba a környezetben elhelyezett több ablakban való böngészéskor

**Nem várt forgatókönyvek és funkciók:**
- Térbeli hang több ablakból egyidejű hangstreamekkel
- "Lásd, mondja ki"
- Nyomtatás

**A böngészővel kapcsolatos legfontosabb problémák:**
- A holografikus billentyűzet nagyító előnézete le van tiltva az új Microsoft Edge. Reméljük, hogy egy későbbi frissítésben újra elérhető lesz a funkció, amint a nagyítás megfelelően működik.
- Előfordulhat, hogy a hang lejátszása nem a megfelelő böngészőablakból történik, ha egy másik böngészőablak van megnyitva és aktív. A probléma megoldásához zárja be a másik aktív ablakot, amely nem hanganyagot kellene lejátszani.
- Ha egy böngészőablakból "Kövessen" módban játszik le hangot, a "Követés" mód letiltása esetén a hang továbbra is lejátszásra kerül. A probléma megoldásához leállíthatja a hanglejátszást a "Követés" mód letiltása előtt, vagy bezárhatja az ablakot az X gombbal.
- Az aktív alkalmazásablakok Microsoft Edge előfordulhat, hogy más 2D-s alkalmazásablakok váratlanul inaktívvá válnak. Ezeket az ablakokat újraaktiválhatja, ha újra kapcsolatba lép velük.

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Belső csatornák

Az Microsoft Edge csapat három előzetes verziójú csatornát tesz elérhetővé az Edge Insider-közösség számára: Béta, Dev és Canary. Az előzetes verziójú csatorna telepítésével nem távolítja el a Microsoft Edge kiadott verzióját a HoloLens 2., és egyszerre több is telepíthető. 

Látogasson el [Microsoft Edge Insider kezdőlapjára,](https://www.microsoftedgeinsider.com) ha többet szeretne megtudni az Edge Insider közösségéről. A különböző Edge Insider-csatornákkal kapcsolatos további információkért és az első lépésekért látogasson el az [Edge Insider letöltési oldalára.](https://www.microsoftedgeinsider.com/download)

Az Insider-csatornák 2 Microsoft Edge re való telepítésére több módszer is HoloLens áll rendelkezésre:

**Közvetlen telepítés az eszközön (jelenleg csak a nem támogatott eszközök számára érhető el)**
  1. A 2. HoloLens oldalon keresse fel az [Edge Insider letöltési oldalát.](https://www.microsoftedgeinsider.com/download)
  1. Válassza **a Download for HoloLens 2 gombot** a telepíteni kívánt Edge Insider-csatornához.
  1. Indítsa el a letöltött .msix fájlt az Edge letöltési üzenetsorból vagy az eszköz "Letöltések" mappájában (a Fájlkezelő).
  1. [Elindul az](app-deploy-app-installer.md) alkalmazástelepítő.
  1. Kattintson a **Telepítés gombra.**
  1. A sikeres telepítés után a Microsoft Edge Beta, Dev vagy Canary külön bejegyzésként Minden alkalmazás **a** Start menü.

**Telepítés számítógéppel Windows Eszközportál [(a](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) fejlesztői módnak engedélyezve kell lennie a HoloLens 2. számítógépen)**
  1. A számítógépen látogasson el az [Edge Insider letöltési oldalára.](https://www.microsoftedgeinsider.com/download)
  1. Kattintson a telepíteni kívánt Edge **Insider-csatorna** "Letöltés Windows 10" gombja melletti legördülő nyílra.
  1. Válassza **HoloLens 2. lehetőséget** a legördülő menüben.
  1. Mentse az .msix fájlt a számítógép "Letöltések" mappájába (vagy egy másik könnyen elérhető mappába).
  1. A [Windows Eszközportál](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) .msix-fájl a 2. HoloLens való telepítéséhez használja HoloLens számítógépen.
  1. A sikeres telepítés után a Microsoft Edge Beta, Dev vagy Canary külön bejegyzésként Minden alkalmazás **a** Start menü.

## <a name="using-wdac-to-block-new-microsoft-edge"></a>A WDAC használata az új Microsoft Edge

Ahhoz, hogy a rendszergazdák a [WDAC-szabályzatukat](windows-defender-application-control-wdac.md) frissítve blokkolják az új Microsoft Edge alkalmazást, a következőket kell hozzáadnia a szabályzathoz.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Végpontok kezelése az új Microsoft Edge

Egyes környezetek esetében figyelembe kell venni a hálózati korlátozásokat. Az új Edge zökkenőmentes felhasználói élményének biztosítása érdekében engedélyezze [ezeket a Microsoft-végpontokat.](/deployedge/microsoft-edge-security-endpoints)

További információ a jelenleg elérhető [végpontjairól a HoloLens.](hololens-offline.md)

## <a name="install-web-apps"></a>Webalkalmazások telepítése
 > [!Note]
> A [Windows 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1)verziójától a Office már nem lesz előre telepítve. 

Az új Edge használatával webalkalmazásokat telepíthet az Microsoft Store mellett. Például telepítheti a Microsoft Office webalkalmazást, hogy megtekintse és szerkessze a SharePoint vagy OneDrive. A webalkalmazás Office a címsorban található Alkalmazás elérhető vagy Office https://www.office.com telepítése gombot.   A **megerősítéshez válassza** a Telepítés lehetőséget.
> [!IMPORTANT]
> Office webalkalmazás funkciói csak akkor érhetők el, ha a 2. HoloLens-es HoloLens rendelkezik aktív internetkapcsolattal.

## <a name="webxr-and-360-viewer"></a>WebXR és 360 Viewer


Az új Microsoft Edge támogatja a WebXR-t, amely a modern webes élmények létrehozásának új szabványa (a WebVR helyett). Számos modern webes élményt a VR szem előtt tartva terveztek (ezek a 2. verzióval helyettesítik a látómezőt egy virtuális környezettel), de ezeket az élményeket a 2. HoloLens is támogatja. A WebXR szabvány kibővített és vegyes valóságú, a fizikai környezetet is használva magával ragadó webes élményt nyújt. Mivel a fejlesztők több időt töltenek a WebXR-sel, arra számítunk, hogy új, kibővített és vegyes valóságú élmények érkeznek majd, HoloLens 2 ügyfél kipróbálhatja!

A 360 Viewer bővítmény a WebXR-re épül, és automatikusan telepítve van a 2. Microsoft Edge új HoloLens mellett. Ez a webes bővítmény lehetővé teszi, hogy 360 fokos videókban merüljön el. A YouTube a 360 videó legnagyobb választékát kínálja, ezért javasoljuk, hogy itt kezdje.

### <a name="how-to-use-webxr"></a>A WebXR használata

1. WebXR-támogatással lépjen egy webhelyre.
1. Válassza az **Enter VR (VR beírása)** gombot a webhelyen. A gomb helye és vizuális megjelenítése webhelyenként eltérő lehet, de a következőre hasonlíthat:

    ![Példa a VR-gombra.](images/75px-enter-vr.png)

1. Amikor első alkalommal próbál webxr-élményt elindítani egy adott tartományon, a böngésző jóváhagyást kér a modern nézetbe való belépéshez, és kiválasztja az **Allow (Engedélyezése) lehetőséget.**
1. A [HoloLens 2 kézmozdulattal módosíthatja](hololens2-basic-usage.md#the-hand-tracking-frame) a felhasználói élményt.
1. Ha a felhasználói élmény  nem rendelkezik Kilépés gombbal, a Start kézmozdulattal [térhet](hololens2-basic-usage.md#start-gesture) vissza a kezdőlapra.

**Ajánlott WebXR-minták**
- 360 Viewer (lásd a következő szakaszt)
- [XR-ök](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR-Paint](https://threejs.org/examples/webxr_vr_paint.html)

### <a name="how-to-use-360-viewer"></a>A 360 Viewer használata

1. Lépjen egy 360 fokos videóra a YouTube-on.
1. A videókeretben válassza a vegyes valóságú headset gombot:

    ![A 360 Viewer aktiválásához kattintson a gombra.](images/enter-360-viewer.jpg)

1. Amikor először próbálja elindítani a 360 Viewert egy adott tartományon, a böngésző beleegyezést kér a modern nézetbe való belépéshez. Válassza az **Allow (Engedélyezése) lehetőséget.**
1. [Légi koppintással](hololens2-basic-usage.md#select-using-air-tap) hozzuk fel a lejátszásvezérlőket. Használjon [kézi sugarakat](hololens2-basic-usage.md#select-using-air-tap) és légi koppintásokat a lejátszáshoz/szüneteltetéshez, a továbbítás/visszaugrás, a feliratok be- és kikapcsolása vagy a felhasználói élmény leállítása (ami kilép a modern nézetből). A lejátszásvezérlők néhány másodperc inaktivitás után eltűnnek.

### <a name="top-webxr-and-360-viewer-known-issues"></a>A WebXR és a 360 Viewer legfontosabb ismert problémái
- A WebXR-élmény összetettségétől függően a képkocka- és képkocka-méret csökkenhet vagy megakhat.
- A WebXR-hez a kézzel készített kéz támogatása alapértelmezés szerint nincs engedélyezve. A fejlesztők a "WebXR Hand Input edge://flags bekapcsolásával engedélyezhetik a támogatást.
- Előfordulhat, hogy a YouTube-on kívül 360 videó nem a várt módon működik.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Visszajelzés küldése a WebXR-ről és a 360 Viewerről

Kérjük, ossza meg a visszajelzéseket és a hibákat a csapatunkkal a **Visszajelzés** küldése funkcióval az új Microsoft Edge.
