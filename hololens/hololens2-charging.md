---
title: HoloLens 2 akkumulátor és az akkumulátortöltés
description: A HoloLens és használata.
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: b117542704968150639a47956a8142d7232fcc66d696feb61ec4fffdaa49df59
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660578"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 akkumulátor és az akkumulátortöltés

Ez az oldal a 2-es HoloLens és a külső akkumulátorok használatával kapcsolatos részleteket tartalmaz.

## <a name="charging-the-device"></a>Az eszköz díjszabása

Használja a kábellel és a 2-es kábellel együtt HoloLens [USB Type-C-kábelt,](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) mivel ez a legjobb módszer az eszköz feltöltésére. A 2. HoloLens által tartalmazott szám legfeljebb 9V @ 2A (18W) lehet. A mellékelt falfelület mellett HoloLens 2 eszköz az akkumulátort kevesebb mint 65 perc alatt megtelheti, amikor az eszköz készenléti állapotban van. Ha ezek a kiegészítők nem érhetők el, győződjön meg arról, hogy a rendelkezésre álló tápegység legalább 15W energiát képes támogatni.

> [!NOTE]
> Ha lehetséges, kerülje a számítógép usb-kapcsolaton keresztüli feltöltését, ami lassú.

## <a name="checking-the-battery-charge-level"></a>Az akkumulátor töltöttségi szintjének ellenőrzése
Ha az eszköz megfelelően elindult és fut, háromféleképpen ellenőrizheti az akkumulátor töltöttségi szintjét:

- Az eszköz felhasználói felületének főmenü HoloLens meg.
- Tekintse meg a LED-et a bekapcsológomb közelében (40%-os díjért legalább két folytonos LED-et kell látnia).
    - Ha az eszköz töltődik, az akkumulátor kijelzője felgyúgyítással jelzi az aktuális töltöttségi szintet.  Az utolsó világítás ki- és behalványul, ami aktív díjszabást jelez.
    - Ha a HoloLens be van stb., az akkumulátor kijelzője öt növekményben jeleníti meg az akkumulátor töltöttségi szintjét.
    - Ha az öt fény közül csak az egyik van bekapcsolva, az akkumulátor töltöttségi szintje 20% alatt van.
    - Ha az akkumulátor töltöttségi szintje kritikusan alacsony, és megpróbálja bekapcsolni az eszközt, az egyik világítás rövid időre villog, majd kiússik.
- A gazdagépen nyissa meg a **Fájlkezelő,** és keresse meg a HoloLens 2-es eszközt a bal oldalon az Ez a **számítógép alatt.** Kattintson a jobb gombbal az eszközre, majd válassza a **Tulajdonságok lehetőséget.** Egy párbeszédpanelen megjelenik az akkumulátor töltöttségi szintje.

   ![A HoloLens 2 tulajdonság képernyőjén az akkumulátor töltöttségi szintje látható](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Alternatív díjszabási specifikációk

HoloLens 2 usb tápellátási [](https://www.usb.org/usb-charger-pd) forrásból 27 W-ig lehet fizetni. Ha a forrás legalább 10 Wattot tud használni, a HoloLens (egyes számítási feladatok esetében akár határozatlan ideig) meghosszabbítható. 

> [!NOTE]
> Az USB-A-ről USB-C-re történő kábellel a díj 7,5 Wattra lesz korlátozva. A működési idő továbbra is meg fog hosszabbodni, de csak akkor, ha USB-C–C kapcsolaton keresztül csatlakozik.

Ha HoloLens módban van, 18 Watt elegendő a belső akkumulátor maximális töltöttségi sebességének eléréséhez. Ha HoloLens van használatban, a díj mértéke csökkenhet, mivel HoloLens prioritást élveznek a díjszabásnál.

> [!IMPORTANT]
> Javasoljuk, hogy legalább 2 HoloLens 5V/1,5A díjért. Nem használhatók olyan kábelek, amelyek nem tudnak legalább 5V/1.5A-t használni. 

### <a name="external-battery-packs"></a>Külső akkumulátorcsomagok

A fenti specifikációknak megfelelő akkumulátor-csomagok a 2. HoloLens használhatók. Vegye figyelembe azonban, hogy egyes USB-C akkumulátorok újratöltődnek, és ugyanazon az USB-C porton keresztül biztosítják az energiaellátást. Fontos, hogy ezek az akkumulátorcsomagok a [TRY-t implementáljanak. Az SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) azért, hogy HoloLens díjat számítsunk fel a díj ellenében. 

### <a name="managing-heat"></a>Hőkezelés

Mint minden más eszköz, az HoloLens generál hőt. Minél gyorsabb a díj, annál több hő jön létre. Emellett a töltöttség alacsonyabb töltöttségi szinten való indítása több hőt generál, mint amikor az akkumulátor többnyire megtelt. Azok az ügyfelek, akiknek hosszabb HoloLens kell üzemeltetni a gyors környezetekben, a következő technikákat használhatja:

- A 2. HoloLens csatlakoztathatja egy külső áramforráshoz akkor is, ha a belső akkumulátor teljesen fel van töltve.
- Ha egy külső akkumulátor kimerül, a HoloLens továbbra is a belső akkumulátoron fog üzemelni.    
- Ha a hő továbbra is problémát jelent a fenti lépések után, fontolja meg egy 1,5A-re korlátozza az óradíjat 1,5A-re korlátozást használó akkumulátort vagy akkumulátort. Vegye figyelembe, hogy ez a beállítás nem biztosít olyan sok működési időt, mivel a belső akkumulátor továbbra is lassan lemerül.

## <a name="troubleshooting"></a>Hibaelhárítás


### <a name="hololens-charges-external-battery"></a>HoloLens Díjak külső akkumulátor
Ha HoloLens 2 akkumulátort tölt fel a terhelés helyett, az azt jelzi, hogy az akkumulátor nem a TRY elemet [implementálja. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). A probléma megoldásának ajánlott módja az újabb akkumulátorra váltás, de usb-A–USB-C kábelre is válthat. Ne feledje, hogy ez 7,5%-os díjra korlátozza a díjszabást.
