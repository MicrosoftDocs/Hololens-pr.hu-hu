---
title: Akkumulátor és akkumulátor
description: A HoloLens feltöltése és külső akkumulátor-csomagok használata.
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
ms.openlocfilehash: 15ecc698a515987857f556fed97d74f861cd6b20
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379656"
---
# <a name="battery-and-charging"></a>Akkumulátor és akkumulátor

Ez az oldal a HoloLens 2 díjának és a külső akkumulátor-csomagok használatának részleteit tartalmazza.

## <a name="included-charger"></a>Included Charger

A HoloLens 2 által tartalmazott csomagban legfeljebb 9V @ 2A (18W) található. Ha lehetséges, javasoljuk, hogy a díjért a mellékelt étkét használja.  

## <a name="specifications"></a>Specifikációk

A HoloLens 2 [USB-tápellátási](https://www.usb.org/usb-charger-pd) forrásoktól legfeljebb 27 w-ig lehet fizetni. Ha a forrás legalább 10 Wattot tud használni, a HoloLens működési ideje meghosszabbítható (egyes számítási feladatok esetében akár határozatlan ideig). 

> [!NOTE]
> Az USB-A-ről USB-C-re történő kábellel a díj 7,5 Watt-ra lesz korlátozva. A működési idő továbbra is meg fog hosszabbodni, de csak akkor, ha USB-C–C kapcsolaton keresztül csatlakozik.

Ha a HoloLens készenléti módban van, 18 Watt elegendő a belső akkumulátor maximális töltöttségi sebességének eléréséhez. Ha a HoloLens használatban van, a díj lecsökkenthető, mivel a HoloLens prioritást élvez a díjszabásnál.

> [!IMPORTANT]
> Javasoljuk, hogy a HoloLens 2 díja legalább 5V/1,5A legyen. Nem használhatók olyan kábelek, amelyek nem tudnak legalább 5V/1.5A-t használni. 

## <a name="external-battery-packs"></a>Külső akkumulátorcsomagok

A fenti specifikációknak megfelelő akkumulátor-csomagok használhatók a HoloLens 2-ben. Vegye figyelembe azonban, hogy egyes USB-C akkumulátorok újratöltődnek, és ugyanazon az USB-C porton keresztül biztosítják az energiaellátást. Fontos, hogy ezek az akkumulátorcsomagok a [TRY-t implementáljanak. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) hogy a HoloLenst díj ellenében számolják fel. 

## <a name="managing-heat"></a>Hőkezelés

Mint minden más eszköz, a HoloLens díjszabása is hőt generál. Minél gyorsabb a díj, annál több hő jön létre. Emellett a töltöttség alacsonyabb töltöttségi szinten való indítása több hőt generál, mint amikor az akkumulátor többnyire megtelt. Azok az ügyfelek, akiknek hosszabb ideig kell üzemeltetni a HoloLenst a meleg környezetekben, a következő technikákat használhatja:

- A HoloLens 2-t akkor is csatlakoztathatja külső áramforráshoz, ha a belső akkumulátor teljesen fel van töltve.
- Ha egy külső akkumulátor kimerül, a HoloLens továbbra is a belső akkumulátorán fog üzemelni.    
- Ha a hő még mindig problémát jelent a fenti lépések után, fontolja meg egy 1,5A-os díjkorlátot használó akkumulátor vagy 3200 M2-es akkumulátor-használatot. Vegye figyelembe, hogy ez a beállítás nem biztosít olyan sok működési időt, mivel a belső akkumulátor továbbra is lassan lemerül.

## <a name="troubleshooting"></a>Hibaelhárítás


### <a name="hololens-charges-external-battery"></a>HoloLens-díjak külső akkumulátor
Ha a HoloLens 2 nem az akkumulátort, hanem külső akkumulátort tölt fel, az azt jelzi, hogy az akkumulátor nem a TRY-et [implementálja. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). A probléma megoldásának ajánlott módja az újabb akkumulátorra váltás, de usb-A–USB-C kábelre is válthat. Ne feledje, hogy ez 7,5%-os díjra korlátozza a díjszabást.
