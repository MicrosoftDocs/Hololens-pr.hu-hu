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
ms.openlocfilehash: 2c0e6e285b2eb86342450e8f05876e0cc3bccfe8
ms.sourcegitcommit: 5cb3230e02e703584e50358cb0f0b5f33a51b169
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2021
ms.locfileid: "121858595"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Mozgó platform mód alacsony dinamikus mozgású mozgó platformokon

Az **Insider 20348.1411-es** buildjében bétaverziós támogatást biztosítunk a 2. HoloLens mozgást indító platformok nyomon követéséhez. A build telepítése és a Mozgóplatform mód engedélyezése után használhatja a HoloLens 2-es HoloLens korábban elérhetetlen környezetekben, például nagy méretű teherszállítókban és nagy méretű állatokban. Jelenleg a funkció célja ezeknek az adott mozgó platformoknak a engedélyezése. Bár semmi sem akadályozza meg abban, hogy más környezetekben is megpróbálja használni a funkciót, a funkció elsősorban ezen környezetek támogatásának hozzáadására összpontosít.

> [!NOTE]
> Ez a funkció jelenleg csak az insiders Windows [érhető el.](hololens-insider.md)

Ez a cikk a következővel foglalkozik:

1. [Miért van szükség a platform áthelyezésre?](#why-moving-platform-mode-is-necessary)
1. [A platform üzemmód áthelyezésének engedélyezése](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Miért van szükség a platform üzemmód áthelyezésének módjára?

HoloLens kell tudnia követni a fej pozícióját [6](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) szabadsági fokban (X, Y, Z fordítás és dobás, dobás, yaw rotáció) a stabil hologramok megjelenítése érdekében. Ehhez a HoloLens két hasonló információt követ nyomon két különböző forrásból:

1. Látható fénykamerák – nyomon követik a környezetet, például azt a fizikai helyiséget, amelyben a HoloLens
1. Inertial Measurement Unit (IMU), – egy gyorsulásmérőből, groscope-ból és kilométermérőből áll, amely nyomon követi a fejlelést és a tájolást a Földhez viszonyítva

A két forrásból származó információk összetettek, így alacsony késéssel és nagy gyakorisággal követheti a fej pozícióját, hogy zökkenőmentes hologramokat renderelhessenek.

Ez a megközelítés azonban egy kritikus feltételezésen alapul; a környezet (amelyet a kamerák követnek) a Földhöz viszonyítva marad (amelyhez képest az IMU méréseket tud végezni). Ha ez nem így van, például a víz egy vízparton, a két forrásból származó információk ütköznek egymással, és a követő elveszhet. Ez az ütközés helytelen pozícióinformációkat hoz létre, és a elvesztését vagy akár a elvesztését is nyomon követi.

A Platform mód áthelyezésének megoldása. Ha engedélyezi a mozgóplatformos módot, az arra utal, hogy a követőnk nem támaszkodhat az érzékelő bemeneteire, hogy mindig teljesen megegyezhetünk egymással. Ehelyett nagyobb mértékben kell a vizualizációkövetésre hagyatkoznunk, és gyorsan azonosítanunk a nem megbízható inertiális mozgási adatokat, és ennek megfelelően szűrnünk kell őket, mielőtt&#39;az IMU-bemenetet.

## <a name="supported-environments-and-known-limitations"></a>Támogatott környezetek és ismert korlátozások

Bár a Platform mód áthelyezését úgy alakították ki, hogy intelligensen kezelje az inertial és a vizuális adatütközéseket, jelenleg arra terjed ki, hogy a nagy méretű, alacsony dinamikus mozgást tapasztaló állatokra terjed ki. Ez azt jelenti, hogy bizonyos korlátozások és nem támogatott forgatókönyvek is vannak.

### <a name="known-limitations"></a>Ismert korlátozások

- A platform üzemmód áthelyezésének (MPM) egyetlen támogatott környezete a nagy méretű, alacsony dinamikus mozgást tapasztaló hüggvény. Ez azt jelenti, hogy számos  gyakori környezet/helyzet még nem támogatott a nagy gyakoriságú mozgás, valamint a magas gyorsulás és [gyorsulás](https://en.wikipedia.org/wiki/Jerk_(physics))miatt. Például: síkok, szerelvények, autók, kerékpárok, busz, kis méretű vízi járművek, liftek stb.
- Hologramok az MPM engedélyezése esetén a rendszer kissé áttenné a munkát, különösen akkor, ha önagyú vízen van.
- Semmi sem akadályozza meg, hogy a felhasználók nem támogatott környezetekben kísérelje meg az MPM használatát, azonban a nem kívánt mellékhatásokat tapasztalhatnak, ha az eszköz képes nyomon követni a nem támogatott térben. Az MPM-et használó felhasználók például azt&#39;, hogy liftben is használhatók az emeletek módosítása közben, míg ez korábban lehetetlen volt. Sajnos, bár az MPM lehetővé teszi az eszköz nyomon követését, jelenleg nem kezeli a térképkezelést. Így a felhasználók azt fogják látni, hogy ha egy liftben cseréli az emeletet, az összezavarja az alsó és felső szinteket, és negatív hatással lesz a térképminőségre.

## <a name="prerequisites"></a>Előfeltételek

A platformmód áthelyezésének bétaverziós támogatása csak néhány előfeltételt igényel:

1. Telepítse a 20348.1411-es vagy újabb buildet a legújabb [Insiders build ARC-on](hololens-insider.md#ffu-download-and-flash-directions) keresztüli flash() frissítésével, vagy regisztrálja és frissítse [az eszközt.](hololens-insider.md#start-receiving-insider-builds)
   - Megjegyzés: Ez a build jelenleg csak az [Insider Dev Channelben érhető el.](hololens-insider.md#start-receiving-insider-builds)
2. Fejlesztői [mód és Eszközportál](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>A platform áthelyezési módjának engedélyezése

Az áthelyezési platform mód engedélyezéséhez először engedélyezze [a Eszközportál.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

1. Válassza ki **a System** (Rendszer) elemet a bal oldali menüben
2. Válassza a **Moving Platform Mode (Platform üzemmód mozgatja)** oldalt, és jelölje be **a Moving Platform Mode (Platform üzemmód mozgatja)** jelölőnégyzetet.

![Első kép](.\images\moving-platform-1.png) ![Második kép](.\images\moving-platform-2.png)

3. Ha a rendszer figyelmeztetést kér, kattintson az **OK gombra.**

![Harmadik kép](.\images\moving-platform-3.png)

4. Indítsa újra az eszközt, amely a jobb felső Eszközportál **Power** menüben vagy a következő hangparancs kiadásával indítható újra az eszközön, és válassza az &quot; Igen &quot; &quot; &quot; lehetőséget.

![Negyedik kép](.\images\moving-platform-4.png)

Ha nem látja a Mozgóplatform mód lehetőséget a Eszközportál, az valószínűleg azt jelenti, hogy még nem a megfelelő buildet használja. Lásd az [Előfeltételek szakaszt.](#prerequisites)
