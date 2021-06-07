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
ms.openlocfilehash: aefb414deb68376ea45e792f21a929fac7cf3969
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379652"
---
# <a name="introducing-the-new-microsoft-edge"></a>Az új Microsoft Edge

![Az örökölt embléma Microsoft Edge új embléma Microsoft Edge animációja](images/new-edge.gif)

Az új Microsoft Edge a [Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) nyílt forráskódú projektet, amely jobb kompatibilitást biztosít az ügyfelek számára, és csökkenti a webfejlesztők számára a web töredezettségét.

A [Windows Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójával az új Microsoft Edge első alkalommal érhető el a HoloLens 2 ügyfelei számára! Ossza meg csapatával a visszajelzéseket és a hibákat az új alkalmazás Visszajelzés küldése Microsoft Edge vagy a [Visszajelzési központ.](hololens-feedback.md) 

> [!IMPORTANT]
> Ez az Microsoft Edge automatikusan lecseréli az örökölt Microsoft Edge, amelyet az új kiadások már nem támogatnak. [](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/)

![Új Microsoft Edge képernyőkép](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>Az új alkalmazás Microsoft Edge

Az új Microsoft Edge ![új Microsoft Edge ikon](images/new_edge_logo.png) A (kék és zöld örlő ikon jelöli) a rendszer a Start menü a webes hivatkozás aktiválásakor automatikusan elindul.

> [!NOTE]
> Amikor először indítja el az új Microsoft Edge HoloLens 2-ben, a beállítások és az adatok importálva lesznek az örökölt Microsoft Edge.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Szabályzatbeállítások konfigurálása az új Microsoft Edge

Az új Microsoft Edge böngésző-szabályzatok sokkal szélesebb készletét kínálják a rendszergazdáknak a HoloLens 2-ben, mint ami korábban a régi Microsoft Edge.

Az új szabályzatbeállítások kezelésével kapcsolatos további információkért íme néhány hasznos forrás Microsoft Edge:

- [Az Microsoft Edge-szabályzatbeállítások konfigurálása a Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge régi verziója szabályzatleképezés Microsoft Edge beállítása](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [A Google Chrome Microsoft Edge szabályzatleképezéshez](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Teljes [Microsoft Edge Enterprise dokumentációja](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Az új operációs rendszer által támogatott böngésző-szabályzatok Microsoft Edge a csapatunk nem tudja garantálni, hogy minden új szabályzat működik a HoloLens 2-ben. Azonban a HoloLens 2-ben korábban támogatott minden korábbi Microsoft Edge Microsoft Edge szabályzat megfelelőjeként teszteltük és megerősítettük, hogy az új megfelelője a vártnak megfelelően működik. A [Microsoft Edge régi verziója](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) Microsoft Edge-szabályzatleképezéssel kapcsolatos további Microsoft Edge a HoloLens 2-ben használt régi Microsoft Edge-szabályzatok új megfelelőjét találja.
>
> Legalább két új szabályzat Microsoft Edge, amelyekről tudjuk, hogy *nem* fognak működni a HoloLens 2-ben:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Mire számítsunk a HoloLens 2-Microsoft Edge újdonságaiból?

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

**A böngészővel kapcsolatos legfontosabb problémák:**
- A holografikus billentyűzet nagyító előnézete le van tiltva az új Microsoft Edge. Reméljük, hogy egy későbbi frissítésben újra elérhető lesz a funkció, amint a nagyítás megfelelően működik.
- Előfordulhat, hogy a hang lejátszása nem a megfelelő böngészőablakból történik, ha egy másik böngészőablak van megnyitva és aktív. A probléma megoldásához zárja be a másik aktív ablakot, amely nem hanganyagot kellene lejátszani.
- Ha a "Kövessen" módban egy böngészőablakból játszik le hangot, a "Követés" mód letiltása esetén a hang továbbra is lejátszásra kerül. A probléma megoldásához leállíthatja a hanglejátszást, mielőtt letiltja a "Kövessen" módot, vagy bezárhatja az ablakot az X gombbal.
- Az aktív ablakokkal Microsoft Edge előfordulhat, hogy más 2D-s alkalmazásablakok váratlanul inaktívvá válnak. Ezeket az ablakokat újraaktiválhatja, ha újra kapcsolatba lép velük.

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider-csatornák

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

## <a name="using-wdac-to-block-new-microsoft-edge"></a>A WDAC használata az új Microsoft Edge

Ahhoz, hogy a rendszergazdák a [WDAC-szabályzatukat](windows-defender-application-control-wdac.md) frissítve blokkolják az új Microsoft Edge alkalmazást, a következőket kell hozzáadnia a szabályzathoz.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Végpontok kezelése az új Microsoft Edge

Egyes környezetek esetében figyelembe kell venni a hálózati korlátozásokat. Az új Edge zökkenőmentes felhasználói élményének biztosítása érdekében engedélyezze [ezeket a Microsoft-végpontokat.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

További információ a [HoloLens jelenleg elérhető végpontjairól.](hololens-offline.md)

## <a name="install-web-apps"></a>Webalkalmazások telepítése
 > [!Note]
> A [Windows Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójától az Office-webalkalmazás már nem lesz előre telepítve. 

Az új Edge használatával webalkalmazásokat telepíthet a Microsoft Store mellett. Telepítheti például a Microsoft Office a SharePointban vagy a OneDrive-ban tárolt fájlok megtekintéséhez és szerkesztéséhez. Az Office-webalkalmazás telepítéséhez keresse fel az Elérhető alkalmazás vagy az Office telepítése gombot a https://www.office.com címsorban.   A **megerősítéshez válassza** a Telepítés lehetőséget.
> [!IMPORTANT]
> Az Office webalkalmazás funkciói csak akkor érhetők el, ha a HoloLens 2 aktív internetkapcsolattal rendelkezik.

## <a name="webxr-and-360-viewer"></a>WebXR és 360 Viewer


Az új Microsoft Edge támogatja a WebXR-t, amely a modern webes élmények létrehozásának új szabványa (a WebVR helyett). Számos modern webes élményt a VR szem előtt tartva terveztek (a nézetet egy virtuális környezetre cserélik), de ezeket a élményt a HoloLens 2 is támogatja. A WebXR szabvány kibővített és vegyes valóságú, magával ragadó webes élményt tesz lehetővé, amelyek a fizikai környezetet használják. Mivel a fejlesztők több időt töltenek a WebXR-sel, arra számítunk, hogy a HoloLens 2 ügyfeleinek új, kibővített és vegyes valóságú élmények várhatók!

A 360 Viewer bővítmény a WebXR-re épül, és automatikusan együtt telepíthető az új Microsoft Edge HoloLens 2-ben. Ez a webes bővítmény lehetővé teszi, hogy elmerüljön a 360 fokos videókban. A YouTube a 360 videó közül kínálja a legnagyobb választékot, ezért javasoljuk, hogy ott kezdje.

### <a name="how-to-use-webxr"></a>A WebXR használata

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

### <a name="how-to-use-360-viewer"></a>A 360 Viewer használata

1. Egy 360 fokos videóra navigálhat a YouTube-on.
1. A videókeretben válassza a vegyes valóságú headset gombot:

    ![Gomb a 360 Viewer aktiválásához](images/enter-360-viewer.jpg)

1. Amikor először próbálja elindítani a 360 Viewert egy adott tartományon, a böngésző beleegyezést kér a modern nézetbe való belépéshez. Válassza az **Allow (Engedélyezése) lehetőséget.**
1. [Légi koppintással](hololens2-basic-usage.md#select-using-air-tap) hozzuk fel a lejátszásvezérlőket. Használjon [kézi sugarakat](hololens2-basic-usage.md#select-using-air-tap) és légi koppintásokat a lejátszáshoz/szüneteltetéshez, a továbbítás/visszaugrás, a feliratok be- és kikapcsolása vagy a felhasználói élmény leállítása érdekében (ami kilép a modern nézetből). A lejátszásvezérlők néhány másodperc inaktivitás után eltűnnek.

### <a name="top-webxr-and-360-viewer-known-issues"></a>A WebXR és a 360 Viewer legfontosabb ismert problémái
- A WebXR-élmény összetettségétől függően a képkocka- és képkocka-méret csökkenhet vagy megakhat.
- A WebXR-hez a kézzel készített kéz támogatása alapértelmezés szerint nincs engedélyezve. A fejlesztők a "WebXR Hand Input" edge://flags engedélyezhetik a támogatást.
- Előfordulhat, hogy a YouTube-on kívül 360 videó nem a várt módon működik.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Visszajelzés küldése a WebXR-ről és a 360 Viewerről

Ossza meg csapatával a visszajelzéseket és a hibákat az új rendszer Visszajelzés küldése Microsoft Edge. 
