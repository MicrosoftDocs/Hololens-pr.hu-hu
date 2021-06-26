---
title: HoloLens 2 akkumulátor és díjszabás
description: A HoloLens feltöltése és külső akkumulátorok használata.
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
ms.openlocfilehash: acbc3e52240f420d384fa372684966d7220d53c6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923584"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 akkumulátor és díjszabás

Ez az oldal a HoloLens 2 díjának és a külső akkumulátorok használatának részleteit tartalmazza.

## <a name="charging-the-device"></a>Az eszköz díjszabása

Használja a HoloLens 2-höz csatlakoztatott kábellel és USB [Type-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) kábellel, mivel ez a legjobb módszer az eszköz feltöltésére. A HoloLens 2 által tartalmazott fogat legfeljebb 9V @ 2A (18W) biztosít. A mellékelt fali kábelen kívül a HoloLens 2-eszközök kevesebb mint 65 perc alatt töltik fel az akkumulátort, amikor az eszköz készenléti állapotban van. Ha ezek a tápegységek nem érhetők el, győződjön meg arról, hogy az elérhető tápegység legalább 15W áramellátást tud támogatni.

> [!NOTE]
> Ha lehetséges, ne használja a pc-t az eszköz USB-kapcsolaton keresztüli feltöltésére, ami lassú.

## <a name="checking-the-battery-charge-level"></a>Az akkumulátor töltöttségi szintjének ellenőrzése
Ha az eszköz megfelelően elindult és fut, háromféleképpen ellenőrizheti az akkumulátor töltöttségi szintjét:

- A HoloLens eszköz felhasználói felületének főmenüjéről.
- Tekintse meg a LED-et a bekapcsológomb közelében (40%-os díjért legalább két SSD-t kell látnia).
    - Ha az eszköz töltődik, az akkumulátor kijelzője felgyúgyítással jelzi az aktuális töltöttségi szintet.  Az utolsó világítás elhalványul és kihalványul, ami aktív díjszabást jelez.
    - Ha a HoloLens be van stb., az akkumulátor kijelzője öt lépéssel jeleníti meg az akkumulátor töltöttségi szintjét.
    - Ha az öt világítás közül csak az egyik van bekapcsolva, az akkumulátor töltöttségi szintje 20% alatt van.
    - Ha az akkumulátor töltöttségi szintje kritikusan alacsony, és megpróbálja bekapcsolni az eszközt, az egyik világítás rövid időre villog, majd kiússik.
- A gazdaszámítógépen nyissa meg a **Fájlkezelő,** és keresse meg HoloLens 2-eszközét a bal oldalon az Ez a **számítógép alatt.** Kattintson a jobb gombbal az eszközre, majd válassza a **Tulajdonságok lehetőséget.** Egy párbeszédpanelen megjelenik az akkumulátor töltöttségi szintje.

   ![A HoloLens 2 tulajdonságokat bemutató képernyője az akkumulátor töltöttségi szintjét jeleníti meg](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Alternatív díjszabási specifikációk

A HoloLens 2 USB [Power Delivery-forrásoktól](https://www.usb.org/usb-charger-pd) legfeljebb 27 w-ig lehet fizetni. Ha a forrás legalább 10 Wattot tud használni, a HoloLens működési ideje meghosszabbítható (egyes számítási feladatok esetében akár határozatlan ideig). 

> [!NOTE]
> Az USB-A-ről USB-C-re történő kábellel a díj 7,5 W-ra lesz korlátozva. A működési idő továbbra is meg fog hosszabbodni, de csak akkor, ha USB-C-ről C-re van szükség.

Ha a HoloLens készenléti módban van, a belső akkumulátor maximális töltöttségi sebességének eléréséhez elegendő 18 W/s. Ha a HoloLens használatban van, a díj lecsökkenthető, mivel a HoloLens a díjszabást előtérbe fontosabbként rangsorol.

> [!IMPORTANT]
> Javasoljuk, hogy a HoloLens 2 díja legalább 5V/1,5A legyen. Nem használhatók olyan kábelek, amelyek nem tudnak legalább 5V/1.5A-t használni. 

### <a name="external-battery-packs"></a>Külső akkumulátorcsomagok

A fenti specifikációknak megfelelő akkumulátor-csomagok a HoloLens 2-ben használhatók. Vegye figyelembe azonban, hogy egyes USB-C akkumulátorok újratöltődnek, és ugyanazon AZ USB-C-porton keresztül biztosítják az energiaellátást. Fontos, hogy ezek az akkumulátorcsomagok a TRY-et [implementáljanak. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) amely biztosítja, hogy a HoloLenst díj ellenében számolják fel. 

### <a name="managing-heat"></a>Hőkezelés

Mint minden más eszköz, a HoloLens díjszabása is hőt hoz létre. Minél gyorsabb a díj, annál több hő keletkezik. Emellett a töltöttség alacsonyabb töltöttségi szinten való indítása több hőt hoz létre, mint amikor az akkumulátor többnyire megtelt. Azok az ügyfelek, akiknek hosszabb ideig kell üzemeltetni a HoloLenst a meleg környezetekben, a következő technikákat használhatja:

- A HoloLens 2-t akkor is csatlakoztathatja külső áramforráshoz, ha a belső akkumulátor teljesen fel van töltve.
- Ha egy külső akkumulátor kimerül, a HoloLens továbbra is a belső akkumulátoron fog üzemelni.    
- Ha a fenti lépések után is problémát jelent az hőkezelés, fontolja meg egy 1,5A-re korlátozza a díjszabást egy akkumulátor- vagy akkumulátor-csomag használatával. Vegye figyelembe, hogy ez a beállítás nem biztosít olyan sok működési időt, mivel a belső akkumulátor továbbra is lassan lemerül.

## <a name="troubleshooting"></a>Hibaelhárítás


### <a name="hololens-charges-external-battery"></a>HoloLens Charges External Battery
Ha a HoloLens 2 nem vele, hanem külső akkumulátorral tölt fel díjat, az azt jelzi, hogy az akkumulátor nem implementálja a [TRY-et. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). A probléma megoldásának ajánlott módja az újabb akkumulátorra váltás, de usb-A–USB-C kábelre is átválthat. Ne feledje, hogy ezzel 7,5 w-re korlátozza a díjszabást.
