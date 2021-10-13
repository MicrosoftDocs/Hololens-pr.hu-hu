---
title: HoloLens 2. áthelyezési platform mód
description: Az HoloLens használata mozgó platformokon
keywords: moving platforms, dynamic motion, hololens, moving platform mode
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 10/12/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 7c636cd97e31c74d4976e71ec3f41ac5afe5bdcc
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924425"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Mozgóplatform-mód alacsony dinamikus mozgású mozgó platformokon

A [Windows Holographic 21H2](hololens-release-notes.md#windows-holographic-version-21h2) verziójában bétaverziós támogatást biztosítunk a 2. HoloLens mozgást indító alacsony dinamikus platformok nyomon követéséhez. A build telepítése és a Mozgóplatform mód engedélyezése után a 2. HoloLens-t korábban nem elérhető környezetekben, például nagy méretű teherszállítókban és nagy méretű állatokban is használhatja. A funkció jelenleg csak az adott mozgó platformok engedélyezését célozza meg. Bár semmi sem akadályozza meg a funkció más környezetekben való használatát, a funkció elsősorban ezen környezetek támogatásának hozzáadására összpontosít.

![Példa platform áthelyezésre.](./images/mpm-compare.gif)

Ez a cikk a következővel foglalkozik:

1. [Miért szükséges a platformátköltözés?](#why-moving-platform-mode-is-necessary)
1. [A platformátköltözetlen mód engedélyezése](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Miért van szükség a platformmód áthelyezésre?

HoloLens [6](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) szabadsági fok (X, Y, Z, fordítás és dobás, dobás, dobás, yaw-rotáció) követésére van szükség a fej pozíciójának nyomon követéséhez a stabil hologramok megjelenítése érdekében. Ehhez a HoloLens két hasonló információt követ két különböző forrásból:

1. **Látható fénykamerák.** Ezek a kamerák nyomon követik a környezetet, például azt a fizikai helyiséget, amelyben a HoloLens
1. **Inertial Measurement Unit (IMU).** Az IMU egy gyorsulásmérőből, groscope-ból és kilométermérőből áll, amely nyomon követi a fejlelést és a tájolást a Földhöz viszonyítva

A két forrásból származó információk összetettek, így alacsony késéssel és elég gyakorisággal követik nyomon a fej pozícióját a zökkenőmentes hologramok renderelése érdekében.

Ez a megközelítés azonban egy kritikus feltételezésen alapul; A környezet (amelyet a kamerák követnek) a Földhöz viszonyítva marad (amelyen az IMU méréseket tud végezni). Ha ez nem így van, például egy víz alatt található étken, a két forrásból származó információk ütközhet egymással, és a követő elveszhet. Ez az ütközés helytelen pozícióinformációkat hoz létre, és a elvesztését vagy akár a veszteség nyomon követését is okozhatja.

A Platform mód áthelyezésének megoldása. Ha engedélyezi a mozgóplatformos módot, az arra utal, hogy a követőnk nem támaszkodhat az érzékelő bemeneteire, hogy mindig teljesen megegyeznek egymással. Ehelyett nagyobb mértékben kell a vizualizációkövetésre hagyatkoznunk, és gyorsan azonosítani a nem összefüggő inertiális mozgásadatokat, és ennek megfelelően szűrnünk kell őket, mielőtt használhatjuk az IMU-bemenetet.

## <a name="supported-environments-and-known-limitations"></a>Támogatott környezetek és ismert korlátozások

Bár a Platform mód áthelyezését úgy alakították ki, hogy intelligensen kezelje az inertial és a vizuális adatütközéseket, jelenleg a nagy, alacsony dinamikus mozgást tapasztaló, kátyúkra terjed ki. Ez azt jelenti, hogy vannak bizonyos korlátozások és nem támogatott forgatókönyvek.

### <a name="known-limitations"></a>Ismert korlátozások

- A Platform üzemmód (MPM) áthelyezésének egyetlen támogatott környezete a nagy méretű, alacsony dinamikus mozgást tapasztaló vízió. Ez azt jelenti, hogy számos  gyakori környezet/helyzet még nem támogatott a nagy gyakoriságú mozgás, valamint a magas gyorsulás és [gyorsulás](https://en.wikipedia.org/wiki/Jerk_(physics))miatt. Például: síkok, szerelvények, autók, kerékpárok, busz, kis méretű vízi járművek, liftek stb.
- Hologramok AZ MPM engedélyezésekor előfordulhat, különösen akkor, ha apy vízen van.
- Semmi sem akadályozza meg, hogy a felhasználók nem támogatott környezetekben próbáljanak MPM-et használni, azonban a nem kívánt mellékhatásokat tapasztalhatnak, ha az eszköz képes a nyomkövetést a nem támogatott térben tartani. Az MPM-ekkel például a felhasználók azt találhatják, hogy liftben is használhatók az emeletek módosítása közben, míg ez korábban nem volt lehetséges. Sajnos, bár az MPM lehetővé teszi az eszköz számára a követés fenntartását, jelenleg nem kezeli a térképkezelést. A felhasználók azt fogják látni, hogy a liftek padlózatának módosítása miatt az eszköz összekeveri az alsó és felső szinteket, és negatívan befolyásolja a térkép minőségét.

## <a name="prerequisites"></a>Előfeltételek

A platformmód áthelyezésének bétaverziós támogatása csak néhány előfeltételt igényel:

1. Telepítse [Windows Holographic 21H2-es](hololens-release-notes.md#windows-holographic-version-21h2) vagy újabb verzióját a [](https://aka.ms/hololens2download) legújabb build ARC-on keresztüli [frissítésével vagy flash-el történő frissítésével.](hololens-recovery.md#clean-reflash-the-device)

2. Fejlesztői [mód és Eszközportál](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>A platformátköltözetlen mód engedélyezése

Az Áthelyezési platform mód engedélyezéséhez először engedélyezze [a Eszközportál.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

1. Válassza ki **a Rendszer-elemet** a bal oldali menüben

   ![Első kép.](.\images\mpm-01.png)

2. Válassza a **Moving Platform Mode (Platform üzemmód mozgatja)** oldalt, és jelölje be **a Moving Platform Mode (Platform üzemmód mozgatja)** jelölőnégyzetet

    ![Második kép.](.\images\mpm-02.png)

3. Amikor a rendszer figyelmeztetést kér, kattintson az **OK gombra.**

   ![Harmadik kép.](.\images\mpm-03.png)

4. Indítsa újra az eszközt, amely a jobb felső Eszközportál **Power** menüben vagy a következő hangparancs kiadásával indítható újra az eszköz, és válassza az &quot; Igen &quot; &quot; &quot; lehetőséget.

   ![Negyedik kép.](.\images\mpm-04.png)

Ha nem látja a Platformátköltözés mód lehetőséget a Eszközportál, az valószínűleg azt jelenti, hogy még nem a megfelelő buildet használja. Lásd az [Előfeltételek szakaszt.](#prerequisites)

## <a name="reporting-issues"></a>Jelentéskészítési problémák

Ahogy korábban említettük, ez a funkció egy bétaverziós funkció, amely csak fejlesztői módban érhető el, ami azt jelenti, hogy problémákba ütközhet. Ha ez történik, megvizsgálhatja és fejlesztheti a terméket:

1. Jelentse a problémát [Visszajelzési központ](hololens-feedback.md) **Hologram pontossága,** stabilitása és megbízhatósága kategóriában, és foglalja bele a következőket:
    1. A probléma leírása, beleértve a várt viselkedést és a tapasztalt viselkedést
    1. A Mixed Reality [videófelvétele](holographic-photos-and-videos.md#capture-a-mixed-reality-video)
2.  Nyisson meg egy támogatási esetet a címen, és ossza meg Visszajelzési központ URL-címet, hogy felvezessük a kérdést, ha a következő kérdések [https://aka.ms/hlsupport](https://aka.ms/hlsupport) merültek fel