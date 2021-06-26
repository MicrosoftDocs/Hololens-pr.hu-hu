---
title: A HoloLens-kattintó használata
description: Ez a cikk bemutatja, hogyan használható a HoloLens-kattintás, beleértve a kattintások párosítását, az díjszabást és a helyreállítást.
ms.assetid: 7d4a30fd-cf1d-4c9a-8eb1-1968ccecbe59
ms.date: 09/16/2019
manager: jarrettr
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 83e5a746b6900c547778c71a0855426563458032
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924060"
---
# <a name="use-the-hololens-1st-gen-clicker"></a>A HoloLens (1. generációs) clicker használata

A clicker kifejezetten a HoloLenshez (1. generációs) készült, és egy másik lehetőséget biztosít a hologramok használatának. A HoloLens (1. generációs) külön mezőben található.

Kézmozdulatok helyére használhatja az alkalmazások kiválasztásához, görgetéshez, áthelyezéséhez és átméretezéséhez.

## <a name="clicker-hardware-and-pairing"></a>Clicker hardver és párosítás

A HoloLens (1. generációs) kattintó egy ujjlenyomat-hurokkal rendelkezik, amely megkönnyíti a könnyebb kezelhetőségüket és a jelzőfényt.

![A HoloLens Clicker](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a>Kattintó jelzőfények

A jelzőgomb világítása a következőt jelenti.

- **Villogó fehér**. A clicker párosítási módban van.
- **Gyorsan villogó fehér.** A párosítás sikeres volt.
- **Folytonos fehér**. A clicker (kattintásra) díj van betöltődve.
- **Villogó ;**. Az akkumulátor alacsony.
- **Solidrel**. A kattintó hibába lépett, és újra kell indítania. A párosítás gomb megnyomása közben kattintson a gombra, és tartsa lenyomva 15 másodpercig.

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a>A clicker párosítása a HoloLens -sel (1. generációs)

1. A Bloom kézmozdulattal válassza a **Start** menüt, majd válassza a Beállítások  >  **Eszközök** lehetőséget, és ellenőrizze, hogy a Bluetooth be van-e va.
1. A kattintásra nyomja le és tartsa lenyomva a párosítás gombot, amíg az állapotjelző fény fehér színre nem villog.
1. A párosítási képernyőn válassza a Clicker Pair **(Kattintáspár)**  >  **lehetőséget.**

### <a name="charge-the-clicker"></a>A kattintó díjának felbevall

Ha a clicker akkumulátor alacsony, az akkumulátor kijelzője villogni kezd. Csatlakoztassa a Micro USB-kábelt egy USB-tápegységhez az eszköz feltöltéséhez.

## <a name="use-the-clicker-with-hololens-1st-gen"></a>A clicker használata a HoloLensben (1. generációs)

### <a name="hold-the-clicker"></a>Tartsa lenyomva a kattintást

A kattintáshoz csúsztassa a hurkot a gyűrűre vagy a középső ujjlenyomatra úgy, hogy a Micro USB-port a sajátja felé néz. A behúzásnál ne feledjen.

![A Clicker (Kattintás)](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a>Kattintási kézmozdulatok

A kattintásos kézmozdulatok kis elforgatások, nem pedig a HoloLens kézmozdulatokhoz használt nagyobb mozgások. HoloLens felismeri a kézmozdulatokat, és akkor is rákattint, ha a kattintás a kézmozdulat-kereten kívül [esik,](hololens1-basic-usage.md)így a kattintást az Ön számára legkényelmesebb helyen tarthatja.

- **Válassza a lehetőséget.** Egy hologram, gomb vagy más elem kiválasztásához tekintsen rá, majd kattintson rá.

- Kattintson és tartsa lenyomva a **gombra.** Kattintson a gombra, és tartsa lenyomva a lefelé mutató lefelé mutató ujjlenyomatot, hogy néhányat a koppintással és a lenyomva gombra kattintva és lenyomva tartással is el tud majd látni, például egy hologram áthelyezését vagy átméretezését.

- **Görgessen.** Az alkalmazássávon válassza a **Görgetőeszköz lehetőséget.** Kattintson és tartsa lenyomva a kattintást, majd forgassa fel, le, balra vagy jobbra. A gyorsabb görgetéshez mozgassa a kézzel a görgetőeszköz közepétől távolabb.

- **Nagyítás**. Az alkalmazássávon válassza a **Zoom Tool lehetőséget.** Kattintson és tartsa lenyomva, majd a nagyításhoz felfelé forgassuk a kattintást, vagy kicsinyítsünk le.

> [!TIP]
> A nagyításhoz vagy kicsinyítéshez a Microsoft Edge egy oldalra nézve kattintson duplán.

## <a name="im-having-problems-using-the-hololens-clicker"></a>Problémákat tapasztalok a HoloLens-kattintással

A [kattintással jelölheti](hololens1-clicker.md) ki, görgetheti, áthelyezheti és átméretezheti a hologramokat. Az egyes alkalmazások további kattintásos kézmozdulatokat is támogathatnak.

Ha nem tudja használni a kattintót, ellenőrizze, hogy a díj fel van-e töltve és párosítva van-e a HoloLens-sel. Ha az akkumulátor alacsony, a jelzőfény villogni kezd. A clicker párosításának ellenőrzéséhez válassza a Beállítások eszközök lehetőséget, és ellenőrizze, hogy  >   megjelenik-e. További információ: [A kattintó párosítása.](hololens1-clicker.md)

Ha a kattintó fel van töltve és párosítva van, és továbbra is problémákat tapasztal, állítsa alaphelyzetbe úgy, hogy 15 másodpercig lenyomva tartja a fő gombot és a párosítás gombot. Ezután párosítsa újra a clickert a HoloLens-sel.

Ha a kattintó alaphelyzetbe állítása nem segít, lásd: [Restart or recover the HoloLens clicker (A HoloLens-kattintó újraindítása vagy helyreállítása).](hololens1-clicker.md#restart-or-recover-the-clicker)
## <a name="restart-or-recover-the-clicker"></a>A kattintó újraindítása vagy helyreállítása

Az íme néhány dolog, amit megpróbálhat, ha a HoloLens-kattintó nem válaszol vagy nem működik jól.

### <a name="restart-the-clicker"></a>A clicker újraindítása

Nyomja le és tartsa lenyomva a párosítási gombot a toll tippjével. Ugyanakkor kattintson a gombra, és tartsa lenyomva a kattintást 15 másodpercig. Ha a clicker már párosítva volt a HoloLens-sel, akkor az újraindítás után is párban marad.

Ha a kattintó nem kapcsol be vagy indul újra, próbálja meg a HoloLens-menü használatával felárasni. Ha az akkumulátor nagyon alacsony, eltarthat néhány percig, hogy a fehér jelzőfény begyűjtsen.

### <a name="re-pair-the-clicker"></a>A clicker újra párosítása

Válassza **a Beállítások** Eszközök  >  **lehetőséget,** majd kattintson a kattintásra. Válassza **az Eltávolítás** lehetőséget, várjon néhány másodpercet, majd párosítsa újra a választógombot.

### <a name="recover-the-clicker"></a>A kattintó helyreállítása

Ha az újraindítás és a kattintás újrapározása nem oldja meg a problémát, a Windows Eszköz-helyreállítási eszköz segíthet a helyreállításban. A helyreállítási folyamat tovább is tart, és a clicker szoftver legújabb verzióját fogja telepíteni. Az eszköz csak akkor használható, ha legalább Windows 10 legalább 4 GB szabad tárhellyel rendelkező számítógépre van szüksége.

A kattintást gombra kattintva a következő helyre lehet állítani:

1. Töltse le és telepítse a [Windows Eszköz-helyreállítási eszközt](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) a számítógépre.
1. Csatlakoztassa a clickert a számítógéphez a HoloLenshez csatlakoztatott Micro USB-kábellel.
1. Futtassa a Windows Eszköz-helyreállítási eszközt, és kövesse az utasításokat.

Ha a rendszer nem észleli automatikusan  a kattintást, válassza az Eszköz nem észlelhető lehetőséget, és kövesse az utasításokat az eszköz helyreállítási módba kapcsolására.

