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
# <a name="battery-and-charging"></a><span data-ttu-id="b66c4-103">Akkumulátor és akkumulátor</span><span class="sxs-lookup"><span data-stu-id="b66c4-103">Battery and Charging</span></span>

<span data-ttu-id="b66c4-104">Ez az oldal a HoloLens 2 díjának és a külső akkumulátor-csomagok használatának részleteit tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b66c4-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="included-charger"></a><span data-ttu-id="b66c4-105">Included Charger</span><span class="sxs-lookup"><span data-stu-id="b66c4-105">Included Charger</span></span>

<span data-ttu-id="b66c4-106">A HoloLens 2 által tartalmazott csomagban legfeljebb 9V @ 2A (18W) található.</span><span class="sxs-lookup"><span data-stu-id="b66c4-106">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="b66c4-107">Ha lehetséges, javasoljuk, hogy a díjért a mellékelt étkét használja.</span><span class="sxs-lookup"><span data-stu-id="b66c4-107">When possible, it's highly recommended to charge using the included charger.</span></span>  

## <a name="specifications"></a><span data-ttu-id="b66c4-108">Specifikációk</span><span class="sxs-lookup"><span data-stu-id="b66c4-108">Specifications</span></span>

<span data-ttu-id="b66c4-109">A HoloLens 2 [USB-tápellátási](https://www.usb.org/usb-charger-pd) forrásoktól legfeljebb 27 w-ig lehet fizetni.</span><span class="sxs-lookup"><span data-stu-id="b66c4-109">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="b66c4-110">Ha a forrás legalább 10 Wattot tud használni, a HoloLens működési ideje meghosszabbítható (egyes számítási feladatok esetében akár határozatlan ideig).</span><span class="sxs-lookup"><span data-stu-id="b66c4-110">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="b66c4-111">Az USB-A-ről USB-C-re történő kábellel a díj 7,5 Watt-ra lesz korlátozva.</span><span class="sxs-lookup"><span data-stu-id="b66c4-111">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="b66c4-112">A működési idő továbbra is meg fog hosszabbodni, de csak akkor, ha USB-C–C kapcsolaton keresztül csatlakozik.</span><span class="sxs-lookup"><span data-stu-id="b66c4-112">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="b66c4-113">Ha a HoloLens készenléti módban van, 18 Watt elegendő a belső akkumulátor maximális töltöttségi sebességének eléréséhez.</span><span class="sxs-lookup"><span data-stu-id="b66c4-113">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="b66c4-114">Ha a HoloLens használatban van, a díj lecsökkenthető, mivel a HoloLens prioritást élvez a díjszabásnál.</span><span class="sxs-lookup"><span data-stu-id="b66c4-114">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b66c4-115">Javasoljuk, hogy a HoloLens 2 díja legalább 5V/1,5A legyen.</span><span class="sxs-lookup"><span data-stu-id="b66c4-115">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="b66c4-116">Nem használhatók olyan kábelek, amelyek nem tudnak legalább 5V/1.5A-t használni.</span><span class="sxs-lookup"><span data-stu-id="b66c4-116">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

## <a name="external-battery-packs"></a><span data-ttu-id="b66c4-117">Külső akkumulátorcsomagok</span><span class="sxs-lookup"><span data-stu-id="b66c4-117">External Battery Packs</span></span>

<span data-ttu-id="b66c4-118">A fenti specifikációknak megfelelő akkumulátor-csomagok használhatók a HoloLens 2-ben.</span><span class="sxs-lookup"><span data-stu-id="b66c4-118">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="b66c4-119">Vegye figyelembe azonban, hogy egyes USB-C akkumulátorok újratöltődnek, és ugyanazon az USB-C porton keresztül biztosítják az energiaellátást.</span><span class="sxs-lookup"><span data-stu-id="b66c4-119">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="b66c4-120">Fontos, hogy ezek az akkumulátorcsomagok a [TRY-t implementáljanak. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) hogy a HoloLenst díj ellenében számolják fel.</span><span class="sxs-lookup"><span data-stu-id="b66c4-120">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

## <a name="managing-heat"></a><span data-ttu-id="b66c4-121">Hőkezelés</span><span class="sxs-lookup"><span data-stu-id="b66c4-121">Managing Heat</span></span>

<span data-ttu-id="b66c4-122">Mint minden más eszköz, a HoloLens díjszabása is hőt generál.</span><span class="sxs-lookup"><span data-stu-id="b66c4-122">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="b66c4-123">Minél gyorsabb a díj, annál több hő jön létre.</span><span class="sxs-lookup"><span data-stu-id="b66c4-123">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="b66c4-124">Emellett a töltöttség alacsonyabb töltöttségi szinten való indítása több hőt generál, mint amikor az akkumulátor többnyire megtelt.</span><span class="sxs-lookup"><span data-stu-id="b66c4-124">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="b66c4-125">Azok az ügyfelek, akiknek hosszabb ideig kell üzemeltetni a HoloLenst a meleg környezetekben, a következő technikákat használhatja:</span><span class="sxs-lookup"><span data-stu-id="b66c4-125">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="b66c4-126">A HoloLens 2-t akkor is csatlakoztathatja külső áramforráshoz, ha a belső akkumulátor teljesen fel van töltve.</span><span class="sxs-lookup"><span data-stu-id="b66c4-126">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="b66c4-127">Ha egy külső akkumulátor kimerül, a HoloLens továbbra is a belső akkumulátorán fog üzemelni.</span><span class="sxs-lookup"><span data-stu-id="b66c4-127">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="b66c4-128">Ha a hő még mindig problémát jelent a fenti lépések után, fontolja meg egy 1,5A-os díjkorlátot használó akkumulátor vagy 3200 M2-es akkumulátor-használatot.</span><span class="sxs-lookup"><span data-stu-id="b66c4-128">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="b66c4-129">Vegye figyelembe, hogy ez a beállítás nem biztosít olyan sok működési időt, mivel a belső akkumulátor továbbra is lassan lemerül.</span><span class="sxs-lookup"><span data-stu-id="b66c4-129">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b66c4-130">Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="b66c4-130">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="b66c4-131">HoloLens-díjak külső akkumulátor</span><span class="sxs-lookup"><span data-stu-id="b66c4-131">HoloLens Charges External Battery</span></span>
<span data-ttu-id="b66c4-132">Ha a HoloLens 2 nem az akkumulátort, hanem külső akkumulátort tölt fel, az azt jelzi, hogy az akkumulátor nem a TRY-et [implementálja. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span><span class="sxs-lookup"><span data-stu-id="b66c4-132">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="b66c4-133">A probléma megoldásának ajánlott módja az újabb akkumulátorra váltás, de usb-A–USB-C kábelre is válthat.</span><span class="sxs-lookup"><span data-stu-id="b66c4-133">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="b66c4-134">Ne feledje, hogy ez 7,5%-os díjra korlátozza a díjszabást.</span><span class="sxs-lookup"><span data-stu-id="b66c4-134">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
