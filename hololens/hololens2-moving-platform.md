---
title: HoloLens 2. áthelyezési platform mód
description: A HoloLens használata mozgó platformokon
keywords: moving platforms, dynamic motion, hololens, moving platform mode
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 8/10/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 81b3231827fce9a2ae2d5e3105800685fedb917b
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427947"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Mozgó platform mód alacsony dinamikus mozgású mozgó platformokon

Az **Insider 20348.1411-es** buildjében bétaverziós támogatást biztosítunk a 2. HoloLens mozgó platformokon való nyomon követéshez. A build telepítése és a Platformáttelepítési mód engedélyezése után a 2. HoloLens-t korábban elérhetetlen környezetekben is használhatja, például nagy méretű teherszállítókban és nagy méretű hatalmasakban. Jelenleg a funkció célja ezeknek az adott mozgó platformoknak a engedélyezése. Bár semmi sem akadályozza meg abban, hogy más környezetekben is megpróbálja használni a funkciót, a funkció célja, hogy először támogatást nyújtsunk ezekhez a környezetekhez.

> [!NOTE]
> Ez a funkció jelenleg csak az [insiders Windows érhető el.](hololens-insider.md)

![Példa a platform áthelyezésre.](./images/mpm-compare.gif)

Ez a cikk a következővel foglalkozik:

1. [Miért van szükség a platform áthelyezésre?](#why-moving-platform-mode-is-necessary)
1. [A platform üzemmód áthelyezésének engedélyezése](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Miért van szükség a platform üzemmód áthelyezésének módjára?

HoloLens kell tudnia követni a fej pozícióját [6](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) szabadsági fokban (X, Y, Z, fordítás és dobás, dobás, yaw rotáció) a stabil hologramok megjelenítése érdekében. Ehhez a HoloLens két hasonló információt követ nyomon két különböző forrásból:

1. Látható fénykamerák – nyomon követik a környezetet, például azt a fizikai helyiséget, amelyben a HoloLens
1. Inertial Measurement Unit (IMU), – egy gyorsulásmérőből, groscope-ból és kilométermérőből áll, amely nyomon követi a fejlelést és a tájolást a Földhez viszonyítva

A két forrásból származó információk összetettek, így alacsony késéssel és nagy gyakorisággal követheti a fej pozícióját, hogy zökkenőmentes hologramokat renderelhessenek.

Ez a megközelítés azonban egy kritikus feltételezésen alapul; a környezet (amelyet a kamerák követnek) a Földhöz viszonyítva marad (amelyhez képest az IMU méréseket tud végezni). Ha ez nem így van, például a víz egy vízparton, a két forrásból származó információk ütköznek egymással, és a követő elveszhet. Ez az ütközés helytelen pozícióinformációkat hoz létre, és a elvesztését vagy akár a veszteség nyomon követését is okozhatja.

A Platform mód áthelyezésének megoldása. Ha engedélyezi a mozgóplatformos módot, az arra utal, hogy a követőnk nem támaszkodhat az érzékelő bemeneteire, hogy mindig teljesen megegyezhetünk egymással. Ehelyett nagyobb mértékben kell a vizualizációkövetésre hagyatkoznunk, és gyorsan azonosítanunk a nem megbízható inertiális mozgási adatokat, és ennek megfelelően szűrnünk kell őket, mielőtt használhatjuk az IMU-bemenetet.

## <a name="supported-environments-and-known-limitations"></a>Támogatott környezetek és ismert korlátozások

Bár a Platform mód áthelyezését úgy alakították ki, hogy intelligensen kezelje az inertial és a vizuális adatütközéseket, jelenleg arra terjed ki, hogy a nagy méretű, alacsony dinamikus mozgást tapasztaló állatokra terjed ki. Ez azt jelenti, hogy bizonyos korlátozások és nem támogatott forgatókönyvek is vannak.

### <a name="known-limitations"></a>Ismert korlátozások

- A platform üzemmód áthelyezésének (MPM) egyetlen támogatott környezete a nagy méretű, alacsony dinamikus mozgást tapasztaló hüggvény. Ez azt jelenti, hogy számos  gyakori környezet/helyzet még nem támogatott a nagy gyakoriságú mozgás, valamint a magas gyorsulás és [a](https://en.wikipedia.org/wiki/Jerk_(physics))gyorsulás miatt. Például: síkok, szerelvények, autók, kerékpárok, busz, kis méretű vízi járművek, liftek stb.
- Hologramok az MPM engedélyezésekor kismértékben is előfordulhat, különösen akkor, ha önagyú vízen van.
- Semmi sem akadályozza meg, hogy a felhasználók nem támogatott környezetekben kísérelje meg az MPM használatát, azonban a nem kívánt mellékhatásokat tapasztalhatnak, ha az eszköz képes nyomon követni a nem támogatott térben. Az MPM esetén például a felhasználók azt találhatják, hogy liftben is használhatók az emeletek módosítása közben, míg ez korábban nem volt lehetséges. Sajnos, bár az MPM lehetővé teszi az eszköz nyomon követését, jelenleg nem kezeli a térképkezelést. A felhasználók azt fogják látni, hogy ha egy liftben cseréli az emeletet, az összezavarja az alsó és felső emeletet, és negatívan befolyásolja a térkép minőségét.

## <a name="prerequisites"></a>Előfeltételek

A platformmód áthelyezésének bétaverziós támogatása csak néhány előfeltételt igényel:

1. Telepítse a 20348.1411-es vagy újabb buildet a legújabb [Insiders build ARC-on](hololens-insider.md#ffu-download-and-flash-directions) keresztüli flash() frissítésével, vagy regisztrálja és frissítse [az eszközt.](hololens-insider.md#start-receiving-insider-builds)

   > [!NOTE]
   > Ez a build jelenleg csak az [Insider Dev Channelben érhető el.](hololens-insider.md#start-receiving-insider-builds)

2. Fejlesztői [mód és Eszközportál](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>A platform üzemmód áthelyezésének engedélyezése

A Mozgóplatform mód engedélyezéséhez először engedélyezze [a Eszközportál.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

1. Válassza ki **a System** (Rendszer) elemet a bal oldali menüben

   ![Első kép.](.\images\mpm-01.png)

2. Válassza a **Moving Platform Mode (Platform üzemmód mozgatja)** oldalt, és jelölje be **a Moving Platform Mode (Platform üzemmód mozgatja)** jelölőnégyzetet.

    ![Második kép.](.\images\mpm-02.png)

3. Ha a rendszer figyelmeztetést kér, kattintson az **OK gombra.**

   ![Harmadik kép.](.\images\mpm-03.png)

4. Indítsa újra az eszközt, amelyet a jobb felső Eszközportál **Power** menüben, vagy a következő hangparancs kiadásával lehet újraindítani az eszközt, és válassza az &quot; Igen &quot; &quot; &quot; lehetőséget.

   ![Negyedik kép.](.\images\mpm-04.png)

Ha nem látja a Mozgóplatform mód lehetőséget a Eszközportál, az valószínűleg azt jelenti, hogy még nem a megfelelő buildet használja. Lásd az [Előfeltételek szakaszt.](#prerequisites)

## <a name="reporting-issues"></a>Jelentéskészítési problémák

Ahogy korábban említettük, ez a funkció egy bétaverziós funkció, amely csak fejlesztői módban érhető el, ami azt jelenti, hogy problémákba ütközhet. Ha ez történik, hogy megvizsgáljuk és javítsuk a terméket, kérjük,

1. Jelentse a problémát [Visszajelzési központ](hololens-feedback.md) **Hologram pontossága,** stabilitása és megbízhatósága kategóriában, és foglalja bele a következőket:
    1. A probléma leírása, beleértve a várt viselkedést és a tapasztalt viselkedést
    1. A Mixed Reality [videófelvétele](holographic-photos-and-videos.md#capture-a-mixed-reality-video)
2.  Nyisson meg egy támogatási esetet a címen, és ossza meg Visszajelzési központ URL-címét, hogy felvezessük a kérdést, ha a következő kérdések [https://aka.ms/hlsupport](https://aka.ms/hlsupport) merültek fel