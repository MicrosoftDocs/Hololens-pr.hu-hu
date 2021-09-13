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
ms.openlocfilehash: b4692468942da88877370864eda2ce173cc499af
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036148"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 akkumulátor és az akkumulátortöltés

Ez az oldal a 2-es HoloLens és a külső akkumulátorok használatának részleteit tartalmazza.

## <a name="charging-the-device"></a>Az eszköz díjszabása

Használja a kábellel és az [USB Type-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) kábellel együtt a HoloLens 2-es portot, mivel ez a legjobb módszer az eszköz feltöltésére. A 2. HoloLens által tartalmazott csomagban legfeljebb 9V @ 2A (18W) található. A mellékelt falfelületen kívül HoloLens 2 eszköz kevesebb mint 65 perc alatt töltheti fel az akkumulátort, amikor az eszköz készenléti állapotban van. Ha ezek a tápegységek nem érhetők el, győződjön meg arról, hogy az elérhető tápegység legalább 15W áramellátást tud támogatni.

> [!NOTE]
> Ha lehetséges, ne használja a pc-t az eszköz USB-kapcsolaton keresztüli feltöltésére, ami lassú.

## <a name="checking-the-battery-charge-level"></a>Az akkumulátor töltöttségi szintjének ellenőrzése
Ha az eszköz megfelelően elindult és fut, háromféleképpen ellenőrizheti az akkumulátor töltöttségi szintjét:

- Az eszköz felhasználói felületének főmenü HoloLens meg.
- Tekintse meg a LED-et a bekapcsológomb közelében (40%-os díjért legalább két SSD-t kell látnia).
    - Ha az eszköz töltődik, az akkumulátor kijelzője felgyúgyítással jelzi az aktuális töltöttségi szintet.  Az utolsó világítás elhalványul és kihalványul, ami aktív díjszabást jelez.
    - Ha a HoloLens van, az akkumulátor kijelzője öt növekményben jeleníti meg az akkumulátor töltöttségi szintjét.
    - Ha az öt világítás közül csak az egyik van bekapcsolva, az akkumulátor töltöttségi szintje 20% alatt van.
    - Ha az akkumulátor töltöttségi szintje kritikusan alacsony, és megpróbálja bekapcsolni az eszközt, az egyik világítás rövid időre villog, majd kiússik.
- A gazdagépen nyissa meg a **Fájlkezelő,** és keresse meg a HoloLens 2-es eszközt a bal oldalon az Ez a **számítógép alatt.** Kattintson a jobb gombbal az eszközre, majd válassza a **Tulajdonságok lehetőséget.** Egy párbeszédpanelen megjelenik az akkumulátor töltöttségi szintje.

   ![A HoloLens 2 tulajdonságképernyőjén az akkumulátor töltöttségi szintje jelenik meg.](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Alternatív díjszabási specifikációk

HoloLens 2000 000 000 000 000 [USB-meghajtóról](https://www.usb.org/usb-charger-pd) 27 w/s-ig lehet fizetni. Ha a forrás legalább 10 w/s-t tud megszűkülni, HoloLens a működési idő (egyes számítási feladatok esetében akár határozatlan ideig) is meghosszabbítható. 

> [!NOTE]
> Az USB-A-ről USB-C-re történő kábellel a díj 7,5 W-ra lesz korlátozva. A működési idő továbbra is meg fog hosszabbodni, de csak akkor, ha USB-C-ről C-re van szükség.

Ha HoloLens készenléti módban van, a belső akkumulátor maximális töltöttségi sebességének eléréséhez elegendő 18 w/s. Ha HoloLens van használatban, a díj lecsökkenthető, mivel HoloLens a díjszabási prioritásokat.

> [!IMPORTANT]
> Javasoljuk, hogy a HoloLens 5V/1,5A minimum díjat számítsunk fel. Nem használhatók olyan kábelek, amelyek nem tudnak legalább 5V/1.5A-t használni. 

### <a name="external-battery-packs"></a>Külső akkumulátorcsomagok

A fenti specifikációknak megfelelő akkumulátor-csomagok a 2. HoloLens használhatók. Vegye figyelembe azonban, hogy egyes USB-C akkumulátorok újratöltődnek, és ugyanazon AZ USB-C-porton keresztül biztosítanak tápellátást. Fontos, hogy ezek az akkumulátorcsomagok a TRY-et [implementáljanak. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) amely biztosítja, hogy HoloLens díjat számítsunk fel az alapján. 

### <a name="managing-heat"></a>Hőkezelés

Mint minden más eszköz, az HoloLens generál hőt. Minél gyorsabb a díj, annál több hő keletkezik. Emellett a töltöttség alacsonyabb töltöttségi szinten való indítása több hőt hoz létre, mint amikor az akkumulátor többnyire megtelt. Azok az ügyfelek, akiknek hosszabb HoloLens kell használnia a adatokat a meleg környezetekben, a következő technikákat használhatja:

- A 2. HoloLens csatlakoztathatja egy külső áramforráshoz, még akkor is, ha a belső akkumulátor teljesen fel van töltve.
- Ha egy külső akkumulátor kimerül, a HoloLens a belső akkumulátoron fog üzemelni.    
- Ha a fenti lépések után is problémát jelent az hőkezelés, fontolja meg egy 1,5A-re korlátozza a díjszabást egy akkumulátor- vagy akkumulátor-csomag használatával. Vegye figyelembe, hogy ez a beállítás nem biztosít olyan sok működési időt, mivel a belső akkumulátor továbbra is lassan lemerül.

## <a name="troubleshooting"></a>Hibaelhárítás


### <a name="hololens-charges-external-battery"></a>HoloLens Díjak külső akkumulátorra
Ha HoloLens 2., és nem az, hanem egy külső akkumulátort tölt fel, az azt jelzi, hogy az akkumulátor nem implementálja a [TRY-et. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). A probléma megoldásának ajánlott módja az újabb akkumulátorra váltás, de usb-A–USB-C kábelre is átválthat. Ne feledje, hogy ezzel 7,5 w-re korlátozza a díjszabást.
