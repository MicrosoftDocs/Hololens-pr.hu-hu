---
title: Új HoloLens előkészítése
description: Megtudhatja, hogyan állíthatja be és állíthatja be HoloLens 2-es eszközét először, beleértve az egészségügyi és biztonsági tippeket, valamint a hardveres útmutatókat.
keywords: hololens, világítás, fit, kényelmi, alkatrészek
ms.assetid: 02692dcf-aa22-4d1e-bd00-f89f51048e32
ms.date: 9/17/2019
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 77c061c53806e7410d73ecf3aaa20d74c217ea33
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427806"
---
# <a name="get-your-hololens-2-ready-to-use"></a>A 2. HoloLens használatra kész

Az alábbi eljárások segítenek első alkalommal HoloLens 2- es HoloLens beállításában.

## <a name="charge-your-hololens"></a>Az HoloLens

Csatlakozás a tápellátást a díjporthoz az USB-C kábellel (a csomagban). Csatlakoztassa a tápegységet egy áramforráshoz. Az eszköz tápellátása és USB-C-to-C kábele a legjobb módszer a 2-es HoloLens feltöltésére. A akkumulátor 18W energiát ad (9V at 2A). A mellékelt fali akkumulátor használatával HoloLens 2 eszköz az akkumulátort kevesebb mint 65 perc alatt megtelheti, amikor az eszköz készenléti állapotban van.

A díjszabás és a sebesség attól függően változhat, hogy az eszköz milyen környezetben fut.

- Ha az eszköz töltődik, az akkumulátor kijelzője felgyúgyítással jelzi az aktuális töltöttségi szintet.  Az utolsó világítás elhalványul, és kihalványul, ami aktív díjszabást jelez.
- Ha a HoloLens be van stb., az akkumulátor kijelzője az akkumulátor töltöttségi szintjét jeleníti meg növekményekben.
- Ha az öt fény közül csak az egyik van bekapcsolva, az akkumulátor töltöttségi szintje 20% alatt van.
- Ha az akkumulátor töltöttségi szintje kritikusan alacsony, és megpróbálja bekapcsolni az eszközt, az egyik világítás rövid időre villog, majd kiússik.

Ha [további információra van szüksége,](hololens2-charging.md#charging-the-device) itt olvashatja el az eszközök díjának részletes adatait. 

## <a name="adjust-fit"></a>Igazítás

Helyezze a HoloLens 2. helyére. Ha szemüveget koptat, hagyja őket be.  Arow padnak az Ön öklének kell lennie, a hátsávnak pedig a fej közepén kell lennie.

Szükség esetén a beállítókerék elfordításával terjessze ki a fejsávot, majd lazítsa le a terhelési tárcsat.

![HoloLens 2 igazítás és beállítás.](images/hololens2-fit.png)

### <a name="attach-and-detach-the-overhead-strap"></a>A terhelési terhelés csatolása és leválasztása

A terhelési rekedtre nincs szükség, de hosszabb időszakokban 2 HoloLens is lehet vele.

A terhelési fül elülső része leválasztható, kihookolja a hurkot, és átcsúsztatható a behúzható hurokba arow padon. A visszacsatoláshoz húzza ki a hurkot, és csúsztassa vissza a back-back() hurkot.

A terhelési lap hátának leválasztása előtt nyomja le az egyes kapcsolati fülek alatti gombot, és húzza le az öklét. Az újracsatlakozáshoz nyomja le a kapcsolati lapokat a tárolóhelyekre, amíg rá nem kattint.

![Csatlakoztassa vagy távolítsa el a HoloLens 2 fejes fogat.](images/hololens2-headstrap.png)

## <a name="turn-on-the-hololens-2"></a>A 2 HoloLens bekapcsolás

A 2. HoloLens a Power (Bekapcsoló) gombra kattintva kapcsolhatja be.  A Tápkapcsoló alatti LED-ek az akkumulátor töltöttségi szintjét jelenítik meg.

> [!NOTE]
> Ha első alkalommal HoloLens 2. gombot, a ki- és bekapcsolás után legalább 4 másodpercig tartsa lenyomva a bekapcsológombot. Amikor a 2. HoloLens bekapcsolja, az egy rövid bekapcsológombbal kezdődik.

### <a name="power-button-actions-for-different-power-transitions"></a>Bekapcsológombos műveletek különböző energiaátmenethez

| Cél | A művelet végrehajtása | A HoloLens 2. |
| - | - | - |
| A bekapcsolás | Nyomja le az egy gombot. | Mind az öt világítás be van kapcsolva, majd úgy vált, hogy jelezze az akkumulátor töltöttségi szintjét. Négy másodperc elteltével egy hang lejátszása megkezdődik. |
| Alvó üzemmód | Nyomja le az egy gombot. | Mind az öt világítás be van kapcsolva, majd egyszerre csak egyszer kell elhalványítani. A világítás kikapcsolása után egy hang lejátszása után a képernyőn megjelenik a "Goodbye" üzenet. |
| Felébresztés alvó üzemmódból | Nyomja le az egy gombot. | Mind az öt világítás be van kapcsolva, majd úgy vált, hogy jelezze az akkumulátor töltöttségi szintjét. A hang azonnal lejátszásra kerül. |
| A kikapcsolása | Tartsa lenyomva az 5-öst. |  Mind az öt világítás be van kapcsolva, majd egyszerre csak egyszer kell elhalványítani. A világítás kikapcsolása után egy hang lejátszása után a képernyőn megjelenik a "Goodbye" üzenet. |
| Ha a HoloLens újraindítására kényszeríti, ha nem válaszol | Tartsa lenyomva a 10-eseket. | Mind az öt világítás be van kapcsolva, majd egyszerre csak egyszer kell elhalványítani. A világítás kikapcsolása után. |

## <a name="hololens-behavior-reference"></a>HoloLens viselkedési referencia

Nem tudja, mit jelentenek a kijelző HoloLens? Szeretné tudni, hogyan HoloLens a díjszabás közben?  Itt van néhány segítség!

### <a name="charging-behavior"></a>Díjszabási viselkedés

| Az eszköz állapota | Művelet | HoloLens 2. |
| - | - | - |
| KI | USB-kábel csatlakoztatása | Az eszköz az akkumulátor töltöttségi szintjét jelző jelző világítással bekapcsolja az eszközt, és megkezdi a díjszabást.
| ON | USB-kábel eltávolítása | Az eszköz nem töltődik le
| ON | USB-kábel csatlakoztatása | Az eszköz elkezdi a díjszabást
| ALVÁS | USB-kábel csatlakoztatása | Az eszköz elkezdi a díjszabást
| ALVÁS | USB-kábel eltávolítása | Az eszköz nem töltődik le
| BEKAPCSOLVA USB-kábellel csatlakoztatva | Az eszköz kikapcsolása | Az eszköz az akkumulátor töltöttségi szintjét jelző jelző világítással bekapcsolja az eszközt, és az eszköz elkezdi a díjszabást |

### <a name="lights-that-indicate-the-battery-level"></a>Az akkumulátor töltöttségi szintjét jelző világítás

| Világítások száma | Akkumulátor töltöttségi szintje |
| - | - |
| Négy szilárd fény, egy fény ki- és bereked | 100% és 81% között (teljes díj) |
| Három tartós világítás, egy ki- és bevilágítás | 80% és 61% között |
| Két tartós fény, egy ki- és bevilágítás | 60% és 41% között |
| Egy folytonos fény, egy be- és kiviláguló fény | 40% és 21% között |
| Egy világos ki- és berekedő | 20% és 5% közötti vagy alacsonyabb (kritikus akkumulátor) |

### <a name="sleep-behavior"></a>Alvó üzemmód

| Az eszköz állapota | Művelet | HoloLens 2. |
| - | - | - |
| ON | Egyetlen bekapcsológomb lenyomása | Az eszköz átvált a SLEEP állapotra, és kikapcsolja az összes jelzőfényt |
| ON | 3 percig nincs mozgás | Az eszköz átvált a SLEEP állapotra, és kikapcsolja az összes jelzőfényt |
| ALVÁS | Egyetlen bekapcsológomb megnyomása | Az eszköz bekapcsolt állapotra vált, és bekapcsolja a jelzőfényeket |

### <a name="lights-to-indicate-problems"></a>Problémákat jelző világítás

| Amikor ezt a | Ezt a világítással lehet megtenni | Ez azt jelenti, hogy |
| - | - | - |
| Nyomja meg a Power gombot. | Az egyik fény ötször felgyújt, majd kikapcsol. | Az HoloLens akkumulátor kritikusan alacsony. Számolja fel a HoloLens. |
| Nyomja meg a Power gombot. | Mind az öt világítás ötször villog, majd kikapcsol. |  HoloLens nem indul el megfelelően, és hibaállapotban van. [Az eszköz helyreállításához telepítse](hololens-recovery.md) újra az operációs rendszert. |
| Nyomja meg a Power gombot. | Az 1., 3. és 5. világítás folyamatosan együtt villog. |  HoloLens hardverhiba is előfordulhat. Lépjen kapcsolatba a [támogatási szolgálattal.](https://support.microsoft.com/en-us/supportforbusiness/productselection?sapid=3ec35c62-022f-466b-3a1e-dbbb7b9a55fb) |

## <a name="safety-and-comfort"></a>Biztonság és kényelem

### <a name="use-hololens-in-safe-surroundings"></a>Biztonságos HoloLens környezetben használt HoloLens használata

A HoloLens biztonságos helyen, a veszélyforrásoktól és a veszélyforrásoktól mentesen használhatja. Ne használja, ha tiszta nézőpontra van szüksége, vagy nem tudja teljes figyelmet fordítani, például egy jármű üzemeltetése vagy más potenciálisan veszélyes tevékenységek során.

### <a name="stay-comfortable"></a>Legyen kényelmes

Tartsa röviden az első néhány HoloLens, és mindenképpen tartson szüneteket. Ha kényelmetlennek érzi magát, álljon meg és ne álljon meg, amíg jobban nem érzi magát. Ez magában foglalhatja az érzelmek, a mozgássérült, az öklák, a diszorientáció, a zavar, a szem túlterhelése vagy a szemszavadását.

Lásd [a termékbiztonsági figyelmeztetéseket és utasításokat.](https://support.microsoft.com/help/4558037/product-safety-warnings-and-instructions)

> [!div class="nextstepaction"]
> [A 2 HoloLens beállítása](hololens2-start.md)
