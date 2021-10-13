---
title: Belső előzetes verzió a Microsoft HoloLens
description: Ismerje meg, hogyan kezdheti meg az Insider-buildek működését, és hogyan adhat értékes visszajelzést a következő jelentős operációsrendszer-frissítésről a HoloLens.
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
ms.date: 10/12/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 080eb5949bc80d1ce922d57f099c375668f5633f
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924362"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Belső előzetes verzió a Microsoft HoloLens

Üdvözöljük az Insider előzetes verziójának legújabb, HoloLens! Az első lépések [egyszerűek,](hololens-insider.md#start-receiving-insider-builds) és értékes visszajelzést adhatunk a következő jelentős operációsrendszer-frissítésről a HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Belső kibocsátási megjegyzések

Izgatottan várjuk, hogy a legutóbbi Insider-funkciók nyilvánosak! Ha ezekről szeretne olvasni, tekintse meg a kibocsátási megjegyzések [oldalát](hololens-release-notes.md)

## <a name="start-receiving-insider-builds"></a>Insider-buildek fogadásának kezdete

> [!NOTE]
> Ha a közelmúltban nem frissítette az eszközt, indítsa újra az eszközt, hogy frissítse az állapotot, és szerezze be a legújabb buildet.
>
> - Az "Eszköz újraindítása" hangparancs jól működik.
> - Az újraindítási gombot a következő Gépház/Windows Insider Program.
>
> Előfordulhat, hogy egy hiba történt a háttérben, amely miatt ön is találkozhatott, így újra a útjára fog menni.

A 2. HoloLens eszközön válassza az Update Gépház Security &  >  **lehetőséget Windows Insider Program** és válassza az  >   Első **lépések lehetőséget.** Csatolja a regisztrációhoz használt fiókot Windows Insiderben.

> [!NOTE]
> Ahhoz, hogy regisztrálja az eszközt az Insider-buildekbe, engedélyeznie kell a nem kötelező telemetriát. Ha még nem tette meg, nyissa meg a Gépház alkalmazást, és válassza a **Privacy**  ->  **Diagnostics & visszajelzést,** majd válassza a Választható diagnosztikai **adatok lehetőséget.**

Windows belső csatorna most a Csatornákra van átköltözve. A **Gyors** kör lesz a **fejlesztői** csatorna, a **Lassú** kör lesz a **Béta csatorna,** a kiadási **előnézeti** kör pedig a kiadási előzetes csatorna **lesz.** A leképezés így néz ki:

![Windows A belső csatornák magyarázata.](images/WindowsInsiderChannels.png)

További információ: [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (A belső csatornák Windows blogok).
Ezután válassza az **Active development of Windows**(Aktív fejlesztés a Windows) lehetőséget, válassza ki, hogy szeretné-e megkapni a Dev **Channelt** vagy **Béta csatorna** buildeket, és tekintse át a program feltételeit.
A **befejezéshez > Újraindítás most lehetőséget.** Miután az eszköz újraindult, a **Gépház > update & Security > Frissítések** keresése lapra ásás a legújabb build lekért verziójára.

### <a name="update-error-0x80070490-work-around"></a>Hiba 0x80070490 hiba a hibakódok között

Ha frissítési hibát 0x80070490 a dev vagy bétaverziós csatornán való frissítéskor, próbálkozzon a következő rövid távú munkával. Ez magában foglalja a belső csatorna áthelyezését, a frissítés be- és vissza mozgatát.

#### <a name="stage-one---release-preview"></a>Első fázis – Előzetes verzió

1. Gépház update & Security (Biztonsági frissítés) Windows Insider Program válassza a Release Preview Channel (Előzetes **verziójú csatorna) lehetőséget.**

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

A [visszajelzések Visszajelzési központ és a](hololens-feedback.md) jelentésekkel kapcsolatos problémák HoloLens a saját alkalmazásában. A Visszajelzési központ biztosítja, hogy minden szükséges diagnosztikai információ megtalálható, hogy a mérnökök gyorsan hibakeresést és megoldást tudjanak biztosítani a problémára.  A kínai és a japán nyelvű HoloLens ugyanúgy kell jelenteni.

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

1. Éles buildet HoloLens futtató Gépház > az **Update & Security > Windows Insider Program,** és válassza a **Stop Insider builds**(Belső buildek leállítása) lehetőséget.

1. Az eszköz lemondáshoz kövesse az utasításokat.
