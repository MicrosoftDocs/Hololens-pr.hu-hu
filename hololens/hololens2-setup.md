---
title: Új HoloLens 2 előkészítése
description: Megtudhatja, hogyan állíthatja be és állíthatja be első alkalommal a HoloLens 2-eszközt, beleértve az egészségügyi és biztonsági tippeket, valamint a hardveres útmutatókat.
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
ms.openlocfilehash: 22b3dad817260175bccdb89faac0bbae7b210038
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924434"
---
# <a name="get-your-hololens-2-ready-to-use"></a>A HoloLens 2 használatra kész

Az alábbi eljárások segítenek a HoloLens 2 első beállításában.

## <a name="charge-your-hololens"></a>A HoloLens díjának feltöltése

Csatlakoztassa a tápegységet a díjporthoz az USB-C kábellel (a csomagban). Csatlakoztassa a tápegységet egy áramforráshoz. A HoloLens 2 feltöltésének legjobb módja az eszköz tápellátása és USB-C-to-C kábele. A tápellátás 18W energiát ad (9V 2A-n). A mellékelt fali készülék használatával a HoloLens 2-eszközök az akkumulátort kevesebb mint 65 perc alatt megtelik, amikor az eszköz készenléti állapotban van.

A díjszabás és a sebesség attól függően változhat, hogy az eszköz milyen környezetben fut.

- Ha az eszköz töltődik, az akkumulátor kijelzője felgyúgyítással jelzi az aktuális töltöttségi szintet.  Az utolsó világítás elhalványul és kihalványul, ami aktív díjszabást jelez.
- Ha a HoloLens be van stb., az akkumulátor kijelzője az akkumulátor töltöttségi szintjét jeleníti meg növekményekben.
- Ha az öt világítás közül csak az egyik van bekapcsolva, az akkumulátor töltöttségi szintje 20% alatt van.
- Ha az akkumulátor töltöttségi szintje kritikusan alacsony, és megpróbálja bekapcsolni az eszközt, az egyik világítás rövid időre villog, majd kiússik.

Ha [további információra van szüksége,](hololens2-charging.md#charging-the-device) itt olvashatja az eszközök díjszabásának teljes részleteit. 

## <a name="adjust-fit"></a>Igazítás igazítása

Helyezze a HoloLens 2-t a fejéhez. Ha szemüveget koptat, hagyja őket be.  Arow padnak az Ön öklének kell lennie, a háttérsávnak pedig a fejének közepén.

Szükség esetén terjessze ki a fejsávot a beállítókerék elforgatásával, majd lazítsa le a terhelési tárcsat.

![A HoloLens 2 igazítása és módosításai](images/hololens2-fit.png)

### <a name="attach-and-detach-the-overhead-strap"></a>Csatolja és válassza le a többletterhelési költségeket

A terhelési rekedtre nincs szükség, de a HoloLens 2 hosszabb ideig tartó használatát is kényelmesebbé teszi.

A terhelési rekesztőlap elülső elülső része leválasztható, majd a behúzható hurokba csúsztatható behúzva. Az újratoláshoz húzza ki a hurkot, és csúsztassa vissza a back-back() hurkot.

A terhelési rekulátor hátának leválasztása előtt nyomja le az egyes kapcsolati fülek alatti gombot, és húzza le az öklét. Az újracsatlakozáshoz nyomja le a kapcsolati lapokat a tárolóhelyekre, amíg rá nem kattint.

![Csatolja vagy távolítsa el a HoloLens 2 fejfejet](images/hololens2-headstrap.png)

## <a name="turn-on-the-hololens-2"></a>A HoloLens 2 bekapcsolás

A HoloLens 2 bekapcsoláshoz nyomja le a Power gombot.  A Tápkapcsoló alatti LED-ek az akkumulátor töltöttségi szintjét jelenítik meg.

> [!NOTE]
> Ahhoz, hogy a HoloLens 2-t első alkalommal bekapcsolja, a be- és bekapcsolás után legalább 4 másodpercig tartsa lenyomva a bekapcsológombot. Amikor legközelebb bekapcsolja a HoloLens 2-t, az egy rövid bekapcsológombbal kezdődik.

### <a name="power-button-actions-for-different-power-transitions"></a>Bekapcsológomb-műveletek a különböző energiaátmenetek számára

| Cél | A művelet végrehajtása | A HoloLens 2 ezt fogja tenni |
| - | - | - |
| A bekapcsolás | Egyetlen gombnyomással. | Mind az öt világítás be van kapcsolva, majd úgy vált, hogy jelezze az akkumulátor töltöttségi szintjét. Négy másodperc elteltével egy hang lejátszása megkezdődik. |
| Alvó üzemmód | Egyetlen gombnyomással. | Mind az öt világítás be van kapcsolva, majd egyszerre csak egyszer kell elhalványítani. A világítás kikapcsolása után egy hang lejátszása után a képernyőn megjelenik a "Goodbye" üzenet. |
| Felébresztés alvó üzemmódból | Egyetlen gombnyomással. | Mind az öt világítás be van kapcsolva, majd úgy vált, hogy jelezze az akkumulátor töltöttségi szintjét. A hang azonnal lejátszásra kerül. |
| A kikapcsolása | Tartsa lenyomva az 5-öst. |  Mind az öt világítás be van kapcsolva, majd egyszerre csak egyszer kell elhalványítani. A világítás kikapcsolása után egy hang lejátszása után a képernyőn megjelenik a "Goodbye" üzenet. |
| A HoloLens újraindításának kényszerítés, ha nem válaszol | Tartsa lenyomva a 10-eseket. | Mind az öt világítás be van kapcsolva, majd egyszerre csak egyszer kell elhalványítani. A világítás kikapcsolása után. |

## <a name="hololens-behavior-reference"></a>HoloLens-viselkedési referencia

Nem tudja, mit jelentenek a jelzőfények a HoloLensen? Tudni szeretné, hogyan kell viselkednie a HoloLensnek a díjszabás közben?  Itt van néhány segítség!

### <a name="charging-behavior"></a>Díjszabási viselkedés

| Az eszköz állapota | Művelet | A HoloLens 2 ezt fogja tenni |
| - | - | - |
| KI | USB-kábel csatlakoztatása | Az eszköz bekapcsolja a kijelzőt jelző világítással, amely az akkumulátor töltöttségi szintjét mutatja, és az eszköz elkezdi a díjszabást.
| ON | USB-kábel eltávolítása | Az eszköz nem töltődik le
| ON | USB-kábel csatlakoztatása | Az eszköz elkezdi a díjszabást
| Alvás | USB-kábel csatlakoztatása | Az eszköz elkezdi a díjszabást
| Alvás | USB-kábel eltávolítása | Az eszköz nem töltődik le
| BEKAPCSOLVA, csatlakoztatott USB-kábellel | Az eszköz kikapcsolása | Az eszköz az akkumulátor töltöttségi szintjét jelző jelző világítással bekapcsolja az eszközt, és az eszköz elkezdi a díjszabást |

### <a name="lights-that-indicate-the-battery-level"></a>Az akkumulátor töltöttségi szintjét jelző világítás

| Világítások száma | Akkumulátor töltöttségi szintje |
| - | - |
| Négy tartós fény, egy ki- és bevilágítás | 100% és 81% között (teljes díj) |
| Három folyamatos világítás, egy ki- és be- és bevilágítás | 80% és 61% között |
| Két tartós fény, egy ki- és bevilágítás | 60% és 41% között |
| Egy folytonos fény, egy be- és kiviláguló fény | 40% és 21% között |
| Egy világos ki- és berekedő | 20% és 5% közötti vagy alacsonyabb (kritikus akkumulátor) |

### <a name="sleep-behavior"></a>Alvó üzemmód működése

| Az eszköz állapota | Művelet | A HoloLens 2 ezt fogja tenni |
| - | - | - |
| ON | Egyetlen bekapcsológomb lenyomása | Az eszköz átvált a SLEEP állapotra, és kikapcsolja az összes jelzőfényt |
| ON | 3 percig nincs mozgás | Az eszköz átvált a SLEEP állapotra, és kikapcsolja az összes jelzőfényt |
| Alvás | Egyetlen bekapcsológomb megnyomása | Az eszköz bekapcsolt állapotra vált, és bekapcsolja a jelzőfényeket |

### <a name="lights-to-indicate-problems"></a>A problémákat jelző világítás

| Ha ezt a | Ezt a világítással lehet megtenni | Ez azt jelenti, hogy |
| - | - | - |
| Nyomja meg a Power gombot. | Az egyik villanykörtét ötször meggyújtja, majd kikapcsol. | A HoloLens-akkumulátor kritikusan alacsony. Számolja fel a HoloLens díját. |
| Nyomja meg a Power gombot. | Mind az öt fény ötször villog, majd kikapcsol. |  A HoloLens nem indul el megfelelően, és hibaállapotban van. [Az eszköz helyreállításához telepítse](hololens-recovery.md) újra az operációs rendszert. |
| Nyomja meg a Power gombot. | Az 1., 3. és 5. világítás folyamatosan együtt villog. |  Előfordulhat, hogy a HoloLens hardverhibája van. Lépjen kapcsolatba az [ügyfélszolgálattal.](https://support.microsoft.com/en-us/supportforbusiness/productselection?sapid=3ec35c62-022f-466b-3a1e-dbbb7b9a55fb) |

## <a name="safety-and-comfort"></a>Biztonság és kényelem

### <a name="use-hololens-in-safe-surroundings"></a>A HoloLens használata biztonságos környezetben

HoloLens-ét biztonságos térben használhatja, amely ingyenesen használható, és nem kell veszélyben lenni. Ne használja, ha tiszta nézőpontra van szüksége, vagy nem tudja teljes figyelmet fordítani, például egy jármű üzemeltetése vagy más potenciálisan veszélyes tevékenységek során.

### <a name="stay-comfortable"></a>Maradjon kényelmes

Tartsa röviden az első néhány munkamenetét a HoloLensben, és mindenképpen tartson szüneteket. Ha kényelmetlenül érzi magát, álljon meg és ne álljon meg, amíg jobban nem érzi magát. Ez magában foglalhatja az átmeneti érzeteket, a mozgást, a érzeteket, a diszorientációt, a tudatot, a szemterhelést vagy a szemtörzset.

Lásd: [termékbiztonsági figyelmeztetések és utasítások.](https://support.microsoft.com/help/4558037/product-safety-warnings-and-instructions)

> [!div class="nextstepaction"]
> [A HoloLens 2 beállítása](hololens2-start.md)
