---
title: Belső előzetes verzió a Microsoft HoloLens
description: Megismerheti az Insider-buildek első lépéseit, és értékes visszajelzést adhat a következő jelentős operációsrendszer-frissítésünkről a HoloLens.
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
ms.date: 10/19/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 382c979138068ab1d9682ee4e84831accc9e4553
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351655"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Belső előzetes verzió a Microsoft HoloLens

Üdvözöljük az Insider előzetes verziójának legújabb buildjeiben HoloLens! Az első lépések [egyszerűek,](hololens-insider.md#start-receiving-insider-builds) és értékes visszajelzést biztosítanak a következő jelentős operációsrendszer-frissítésünkről a HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Belső kibocsátási megjegyzések

Újdonságok és újdonságok a HoloLens? Tekintse meg a hamarosan elérhető új HoloLens!

### <a name="colorblind-mode"></a>Colorblind mód

Az Insider 20348.1463-as buildje hozzáadva

A Colorblind mód hasznos egy nagyszerű funkció, amely HoloLens teszi elérhetőbbé. Az új colorblind mód a Színszűrők Gépház a Gépház  ->  **Könnyű kezelés**  ->  **található.** Számos új szűrő érhető el. Az alábbi vizualizáció néhány elérhető szűrőt mutat be.

| Ki | Szürkeárnyalatos | Tritanopia |
|-----|-----------|------------|
| ![Színszűrő kikapcsolva](images/colorblind-off.png)   | ![Szürkeárnyalatos színszűrő](images/colorblind-greyscale.png)         | ![Színszűrő tritanlógus](images/colorblind-tritanopia.png)          |

### <a name="fixes-and-improvements"></a>Javítások és fejlesztések

- Ki lett javítva egy ismert hiba, amely miatt az eszköz minden alkalommal, [amikor az energiagazdálkodás 18%-ra csökkent,](hololens-troubleshooting.md#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)az eszköz hirtelen automatikusan leáll.
- A platform üzemmód áthelyezésének fejlesztései a lefelé irány észlelésekor.
- Ki van javítva a frissítési párbeszédpanelekkel kapcsolatban megjelenő hiba.
- Frissítve lett a Microsoft Edge verziója.
- Ki lett javítva az a hiba, amely miatt a választható diagnosztikai adatok váltógombja nem őrzött meg a kiválasztott beállítást a telemetriabeállítások oldalán az újraindítás után.
- Kijavítva és hiba, amely miatt a rendszer nem ismerte fel a QR-kódokat, amikor az eszközhöz képest 45 fokos szögben elforgatták őket.

## <a name="start-receiving-insider-builds"></a>Insider-buildek fogadásának kezdete

> [!NOTE]
> Ha a közelmúltban nem frissített, indítsa újra az eszközt az állapot frissítéséhez, és szerezze be a legújabb buildet.
>
> - Az "Eszköz újraindítása" hangparancs jól működik.
> - Az újraindítási gombot is választhatja a Gépház/Windows Insider Program.
>
> Előfordulhat, hogy egy hiba történt a háttéren, amely miatt előfordulhatott, hogy újra a útjára fog menni.

A 2. HoloLens eszközön válassza az **Update** Gépház Security &  >  **lehetőséget Windows Insider Program** és válassza az  >   Első **lépések lehetőséget.** Csatolja a regisztrációhoz használt fiókot Windows Insiderben.

> [!NOTE]
> Ahhoz, hogy regisztrálja az eszközt az Insider-buildekbe, engedélyeznie kell a nem kötelező telemetriát. Ha még nem tette meg, nyissa meg a Gépház alkalmazást, válassza a **Privacy**  ->  **Diagnostics & visszajelzést,** majd válassza a Választható diagnosztikai **adatok lehetőséget.**

Windows belső csatorna most már a Csatornákra van átköltözve. A **Gyors** kör lesz a **Fejlesztői** csatorna, a **Lassú** kör lesz a **Béta csatorna,** a Kiadási **előnézeti** kör pedig a Kiadás **előnézete csatorna** lesz. A leképezés így néz ki:

![Windows Belső csatornák magyarázata.](images/WindowsInsiderChannels.png)

További információ: [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (A belső csatornák Windows blogok).
Ezután válassza az **Active development of Windows (Aktív** fejlesztés a Windows) lehetőséget, válassza ki, hogy **szeretné-e** fogadni a **Dev Channelt** vagy Béta csatorna buildeket, és tekintse át a program feltételeit.
A **befejezéshez válassza > Újraindítás most** lehetőséget. Az eszköz újraindítása után az Update Gépház > Security & **> Frissítések** keresése a legújabb buildhez lapra.

### <a name="update-error-0x80070490-work-around"></a>Hiba 0x80070490 hiba

Ha frissítési hibát 0x80070490 a Dev vagy a Beta csatornán való frissítéskor, próbálkozzon a következő rövid távú munkával. Ez magában foglalja a belső csatorna áthelyezését, a frissítés be- és áthelyezését, majd az Insider-csatorna vissza mozgatát.

#### <a name="stage-one---release-preview"></a>Első fázis – Előzetes kiadás

1. Gépház a Frissítés & lehetőséget, Windows Insider Program válassza a **Kiadási** előzetes csatorna lehetőséget.

2. Gépház, Update & Security, Windows Update, **Check for updates**. A frissítés után folytassa a második fázisra.

#### <a name="stage-two---dev-channel"></a>Második fázis – Fejlesztői csatorna

1. Gépház Update & Security (Biztonsági frissítés) Windows Insider Program válassza a **Dev Channel (Fejlesztői csatorna) lehetőséget.**

2. Gépház, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>FFU letöltési és flash utasítások

Az aláírt ffu repülőjárattal való teszteléshez először fel kell oldania az eszköz zárolását, mielőtt felrakná a repülőjárat aláírt ffu-ját.

1. Pc-n:
    1. Töltse le a ffu-t a számítógépére a [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) ről.

    1. Telepítse az ARC-t (Advanced Recovery Companion) a [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) Microsoft Store: .

1. On HoloLens - Flight Unlock: **Open Gépház** Update & Security Windows Insider Program majd  >    >   regisztráljon, indítsa újra az eszközt.

1. Flash FFU – Most már az ARC használatával is ki flashlheti a repülőjárat aláírt FFU-ját.

### <a name="provide-feedback-and-report-issues"></a>Visszajelzés küldése és problémák jelentése

A [visszajelzések Visszajelzési központ és a](hololens-feedback.md) jelentésekkel kapcsolatos problémák HoloLens a saját alkalmazásában. A Visszajelzési központ biztosítja, hogy minden szükséges diagnosztikai információ bekerül a hibakeresésbe és a probléma megoldásában a mérnökeinknek.  A kínai és a japán nyelvű HoloLens ugyanúgy kell jelenteni.

> [!NOTE]
> Mindenképpen fogadja el azt a kérdést, amely megkérdezi, hogy szeretné-e Visszajelzési központ a Dokumentumok mappa eléréséhez (válassza az **Igen** lehetőséget, amikor a rendszer erre kéri).

## <a name="note-for-developers"></a>Megjegyzés fejlesztőknek

Nyugodtan kipróbálhatja az alkalmazások fejlesztését belső fejlesztésű belső HoloLens.  Az első [lépésekhez tekintse](https://developer.microsoft.com/windows/mixed-reality/development) HoloLens fejlesztői dokumentációját. Ugyanezek az utasítások az Insider-buildekkel is HoloLens.  Használhatja a Unity ugyanazon buildeket, Visual Studio a fejlesztéshez már HoloLens is.

## <a name="stop-receiving-insider-builds"></a>Insider-buildek fogadásának leállítása

Ha már nem szeretné megkapni az Windows Holographic Insider-buildjét, kikapcsolhatja, ha az HoloLens éles [](hololens-recovery.md) buildet futtat, vagy az Advanced Recovery Companion segítségével helyreállíthatja az eszközt az Windows Holographic nem insider verziójára.

> [!CAUTION]
> Megjelenik egy ismert probléma, amely miatt az Insider Preview buildre való regisztrációt manuálisan újratelepítő felhasználók kék képernyőt tapasztalnak. Ezt követően manuálisan kell helyreállítania az eszközt. Ha szeretne többet tudni arról, hogy ez hatással lenne-e az Ön számára, tekintse meg ezt az ismert [problémát.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Annak ellenőrzése, hogy a HoloLens futtat-e éles buildet:

1. Keresse meg **Gépház > System > About (Rendszer**> about ) et, és keresse meg a build számát.

1. [Tekintse meg az éles buildszámok kibocsátási megjegyzéseit.](hololens-release-notes.md)

Az Insider-buildek lemondása:

1. Éles buildet HoloLens futtató Gépház > az **Update & Security > Windows Insider Program**, és válassza a **Stop Insider builds**(Belső buildek leállítása) lehetőséget.

1. Az eszköz lemondáshoz kövesse az utasításokat.
