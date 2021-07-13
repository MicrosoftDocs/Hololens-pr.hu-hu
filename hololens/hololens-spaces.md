---
title: Fizikai terek leképezés HoloLens
description: HoloLens, hogyan néz ki egy tér az idő alatt. A felhasználók úgy könnyíthetik meg ezt a folyamatot, hogy HoloLens bizonyos módokon átköltöztik a tárhelyen.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, tervezés, térbeli leképezés, HoloLens, felületrekonstrukció, háló, fejkövetés, leképezés
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640041"
---
# <a name="map-physical-spaces-with-hololens"></a><span data-ttu-id="c01f9-105">Fizikai terek leképezés HoloLens</span><span class="sxs-lookup"><span data-stu-id="c01f9-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="c01f9-106">HoloLens a hologramokat a fizikai világával ötvözi.</span><span class="sxs-lookup"><span data-stu-id="c01f9-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="c01f9-107">Ahhoz, hogy HoloLens meg tudjanak ismerkedni az Ön körüli fizikai világgal, és ne feledje, hol vannak a hologramok a térben.</span><span class="sxs-lookup"><span data-stu-id="c01f9-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="c01f9-108">Idővel a HoloLens felépíti *a* látott környezet térbeli térképét.</span><span class="sxs-lookup"><span data-stu-id="c01f9-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="c01f9-109">HoloLens frissíti a térképet a környezet változásaival.</span><span class="sxs-lookup"><span data-stu-id="c01f9-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="c01f9-110">Amíg be van jelentkezve, és az eszköz be van kapcsolva, a HoloLens és frissíti a térbeli térképeket.</span><span class="sxs-lookup"><span data-stu-id="c01f9-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="c01f9-111">Ha az eszközt úgy tartja vagy koptatja, hogy a kamerák egy helyre mutatnak, a HoloLens megpróbálja leképezni a területet.</span><span class="sxs-lookup"><span data-stu-id="c01f9-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="c01f9-112">Bár a HoloLens természetes módon tanulja meg a helyet az idő alatt, vannak olyan módszerek, amelyek segítségével gyorsabban és hatékonyabban HoloLens leképezheti a területet.</span><span class="sxs-lookup"><span data-stu-id="c01f9-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="c01f9-113">Ha a HoloLens nem tudja leképezni a tárhelyet, vagy nincs megfelelő állapotban, HoloLens korlátozott módba léphet.</span><span class="sxs-lookup"><span data-stu-id="c01f9-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="c01f9-114">Korlátozott módban nem fog tudni hologramokat a környezetében használni.</span><span class="sxs-lookup"><span data-stu-id="c01f9-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="c01f9-115">Ez a cikk bemutatja, HoloLens térbeli leképezéseket, hogyan fejleszthet térbeli leképezést, és hogyan kezelheti a HoloLens gyűjtött térbeli adatokat.</span><span class="sxs-lookup"><span data-stu-id="c01f9-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <a name="choosing-and-setting-up-and-your-space"></a><span data-ttu-id="c01f9-116">A hely és a hely kiválasztása és beállítása</span><span class="sxs-lookup"><span data-stu-id="c01f9-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="c01f9-117">A környezetben található funkciók megnehezítik a HoloLens számára a tér értelmezését.</span><span class="sxs-lookup"><span data-stu-id="c01f9-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="c01f9-118">A fényszintek, a tér anyagai, az objektumok elrendezése stb. mind hatással lehetnek arra, HoloLens leképeznek egy területet.</span><span class="sxs-lookup"><span data-stu-id="c01f9-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="c01f9-119">HoloLens a legjobban bizonyos típusú környezetekben működik.</span><span class="sxs-lookup"><span data-stu-id="c01f9-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="c01f9-120">A legjobb térbeli térkép előállításához válasszon ki egy megfelelő fényű és sok helyből álló helyiséget.</span><span class="sxs-lookup"><span data-stu-id="c01f9-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="c01f9-121">Kerülje a sötét tereket és olyan helyiségeket, amelyek sok sötét, sötét vagy átlátszó felületű (például tükrözött vagy rátermetes) felületekkel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="c01f9-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="c01f9-122">HoloLens beltéri használatra van optimalizálva.</span><span class="sxs-lookup"><span data-stu-id="c01f9-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="c01f9-123">A térbeli leképezés akkor is Wi-Fi, ha a hálózat be van kapcsolva, bár nem kell hálózathoz csatlakoztatni.</span><span class="sxs-lookup"><span data-stu-id="c01f9-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="c01f9-124">HoloLens akkor is Wi-Fi hozzáférési pontokat, ha nincs csatlakoztatva vagy hitelesítve.</span><span class="sxs-lookup"><span data-stu-id="c01f9-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="c01f9-125">HoloLens funkció nem változik meg, hogy a hozzáférési pontok csak internetkapcsolattal vagy intranettel/helyi hálózattal csatlakoznak-e.</span><span class="sxs-lookup"><span data-stu-id="c01f9-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="c01f9-126">A HoloLens biztonságos, veszélyforrások nélkül használhatók.</span><span class="sxs-lookup"><span data-stu-id="c01f9-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="c01f9-127">[További információ a biztonságról:](https://support.microsoft.com/help/4023454/safety-information).</span><span class="sxs-lookup"><span data-stu-id="c01f9-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <a name="mapping-your-space"></a><span data-ttu-id="c01f9-128">A tér leképezése</span><span class="sxs-lookup"><span data-stu-id="c01f9-128">Mapping your space</span></span>

<span data-ttu-id="c01f9-129">Most már készen áll a tartalék leképezésére.</span><span class="sxs-lookup"><span data-stu-id="c01f9-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="c01f9-130">Amikor HoloLens elkezdi leképezni a környezetet, egy hálós ábra fog elterjedni a térben.</span><span class="sxs-lookup"><span data-stu-id="c01f9-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="c01f9-131">A vegyes valóságú otthonban a leképezett felület kiválasztásával aktiválhatja a térképet.</span><span class="sxs-lookup"><span data-stu-id="c01f9-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="c01f9-132">Az alábbi irányelvek alapján nagyszerű térbeli térképeket lehet kihozni.</span><span class="sxs-lookup"><span data-stu-id="c01f9-132">Here are guidelines for building a great spatial map.</span></span>

### <a name="understand-the-scenarios-for-the-area"></a><span data-ttu-id="c01f9-133">A terület forgatókönyvei</span><span class="sxs-lookup"><span data-stu-id="c01f9-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="c01f9-134">Fontos, hogy a legtöbb időt azzal töltse, amikor a HoloLens használja, hogy a térkép releváns és teljes legyen.</span><span class="sxs-lookup"><span data-stu-id="c01f9-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="c01f9-135">Ha például egy felhasználói forgatókönyvben HoloLens az A pontról a B pontra, járja be ezt az útvonalat 2-3-szor, és haladjon végig minden irányban.</span><span class="sxs-lookup"><span data-stu-id="c01f9-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <a name="walk-slowly-around-the-space"></a><span data-ttu-id="c01f9-136">Lassan járdáljon a tér körül</span><span class="sxs-lookup"><span data-stu-id="c01f9-136">Walk slowly around the space</span></span>

<span data-ttu-id="c01f9-137">Ha túl gyorsan járja a területet, valószínű, hogy a HoloLens kihagyja a leképezési területeket.</span><span class="sxs-lookup"><span data-stu-id="c01f9-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="c01f9-138">Lassan járja körbe a területet, és minden 5–8 láb között megáll, és a környezetét is meg kell néznie.</span><span class="sxs-lookup"><span data-stu-id="c01f9-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="c01f9-139">A zökkenőmentes mozgás a HoloLens is segít a térkép hatékonyabban.</span><span class="sxs-lookup"><span data-stu-id="c01f9-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <a name="look-in-all-directions"></a><span data-ttu-id="c01f9-140">Minden irányban</span><span class="sxs-lookup"><span data-stu-id="c01f9-140">Look in all directions</span></span>

<span data-ttu-id="c01f9-141">A tér leképezésén való HoloLens több adatot biztosít a pontok egymáshoz viszonyított viszonyában.</span><span class="sxs-lookup"><span data-stu-id="c01f9-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="c01f9-142">Ha például nem keres, előfordulhat, hogy a HoloLens tudja, hol van a felső határ egy helyiségben.</span><span class="sxs-lookup"><span data-stu-id="c01f9-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="c01f9-143">Ne felejtsen el lenézni a padlóra a tér leképezésén.</span><span class="sxs-lookup"><span data-stu-id="c01f9-143">Don't forget to look down at the floor as you map the space.</span></span>

### <a name="cover-key-areas-multiple-times"></a><span data-ttu-id="c01f9-144">A legfontosabb területek többszöri lefedve</span><span class="sxs-lookup"><span data-stu-id="c01f9-144">Cover key areas multiple times</span></span>

<span data-ttu-id="c01f9-145">Ha többször is végigköltöz egy területen, az segít az első bemutatóban esetleg kihagyott funkciók behúzásában.</span><span class="sxs-lookup"><span data-stu-id="c01f9-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="c01f9-146">Egy ideális térkép felépítéséhez próbáljon meg kétszer vagy háromszor bejárni egy területet.</span><span class="sxs-lookup"><span data-stu-id="c01f9-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="c01f9-147">Ha lehetséges, a mozgás ismétlése közben időt fordítson egy területre egy irányban, majd fordítsa meg és járja vissza az utat.</span><span class="sxs-lookup"><span data-stu-id="c01f9-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <a name="take-your-time-mapping-the-area"></a><span data-ttu-id="c01f9-148">A terület leképezése</span><span class="sxs-lookup"><span data-stu-id="c01f9-148">Take your time mapping the area</span></span>

<span data-ttu-id="c01f9-149">15–20 percig is eltarthat, HoloLens a rendszer teljes mértékben leképezi magát, és alkalmazkodik a környezethez.</span><span class="sxs-lookup"><span data-stu-id="c01f9-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="c01f9-150">Ha van olyan terület, ahol gyakran tervezi használni a HoloLens, akkor ezt az időt előre meg kell tervezni a terület leképezésével, a későbbiekben megelőzheti a problémákat.</span><span class="sxs-lookup"><span data-stu-id="c01f9-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <a name="possible-errors-in-the-spatial-map"></a><span data-ttu-id="c01f9-151">Lehetséges hibák a térbeli térképen</span><span class="sxs-lookup"><span data-stu-id="c01f9-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="c01f9-152">A térbeli leképezési adatok hibái néhány kategóriába sorolhatók:</span><span class="sxs-lookup"><span data-stu-id="c01f9-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="c01f9-153">*Rések:* Valós felületek hiányoznak a térbeli leképezési adatokból.</span><span class="sxs-lookup"><span data-stu-id="c01f9-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="c01f9-154">*A felszínek* olyan térbeli leképezési adatokban léteznek, amelyek a való világban nem léteznek.</span><span class="sxs-lookup"><span data-stu-id="c01f9-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="c01f9-155">*Worm HoloLens:* a térbeli térkép "elveszíti" részét, úgy gondolva, hogy a térkép egy másik részén található, mint amilyen valójában.</span><span class="sxs-lookup"><span data-stu-id="c01f9-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="c01f9-156">*Torzítás:* A térbeli leképezési adatok felületei nem teljesen igazodnak a valós felületekhez, leküldve vagy kihúzva.</span><span class="sxs-lookup"><span data-stu-id="c01f9-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="c01f9-157">Ha ezen hibák bármelyikét látja, küldjön visszajelzést a [FeedbackHubon.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="c01f9-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <a name="security-and-storage-for-spatial-data"></a><span data-ttu-id="c01f9-158">Térbeli adatok biztonsága és tárolása</span><span class="sxs-lookup"><span data-stu-id="c01f9-158">Security and storage for spatial data</span></span>

<span data-ttu-id="c01f9-159">Windows 10 1803-as vagy újabb Microsoft HoloLens a leképezési adatokat egy helyi (eszközön található) adatbázisban tárolja.</span><span class="sxs-lookup"><span data-stu-id="c01f9-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="c01f9-160">HoloLens a felhasználók akkor sem férhetnek hozzá közvetlenül a térképadatbázishoz, ha az eszköz számítógéphez van csatlakoztatva, vagy ha az Fájlkezelő használja.</span><span class="sxs-lookup"><span data-stu-id="c01f9-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="c01f9-161">Ha a BitLocker engedélyezve van a HoloLens, a rendszer a tárolt térképadatokat is titkosítja a teljes kötetpel együtt.</span><span class="sxs-lookup"><span data-stu-id="c01f9-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <a name="remove-map-data-and-known-spaces-from-hololens"></a><span data-ttu-id="c01f9-162">Térképadatok és ismert szóközök eltávolítása a HoloLens</span><span class="sxs-lookup"><span data-stu-id="c01f9-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="c01f9-163">Két lehetőség van a térképadatok törlésére a **Gépház > System > Hologramok:**</span><span class="sxs-lookup"><span data-stu-id="c01f9-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="c01f9-164">A közeli hologramok törléséhez válassza a **Közeli hologramok eltávolítása lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="c01f9-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="c01f9-165">Ez a parancs törli a térképadatokat és a rögzített hologramokat az aktuális térhez.</span><span class="sxs-lookup"><span data-stu-id="c01f9-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="c01f9-166">Ha továbbra is ugyanabban a térben használja az eszközt, az létrehoz és tárol egy teljesen új térkép szakaszt a törölt adatok lecseréléséhez.</span><span class="sxs-lookup"><span data-stu-id="c01f9-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c01f9-167">A "Közeli" hologramok olyan hologramok, amelyek az aktuális tér azonos térképszakaszában vannak horgonyozva.</span><span class="sxs-lookup"><span data-stu-id="c01f9-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="c01f9-168">Ezzel a beállítással például úgy ürítheti ki a munkához kapcsolódó térképadatokat, hogy az ne legyen hatással az otthoni térképadatokra.</span><span class="sxs-lookup"><span data-stu-id="c01f9-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="c01f9-169">Az összes hologram törléséhez válassza az **Összes hologram eltávolítása lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="c01f9-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="c01f9-170">Ez a parancs törli az eszközön tárolt összes térképadatot, valamint az összes rögzített hologramot.</span><span class="sxs-lookup"><span data-stu-id="c01f9-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="c01f9-171">Explicit módon el kell látnia minden hologramot.</span><span class="sxs-lookup"><span data-stu-id="c01f9-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="c01f9-172">A korábban elhelyezett hologramokat nem fogja tudni újra kiveszni.</span><span class="sxs-lookup"><span data-stu-id="c01f9-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="c01f9-173">Miután eltávolítja a közeli vagy az összes hologramot, a HoloLens azonnal megkezdi az aktuális tér beolvasását és leképezését.</span><span class="sxs-lookup"><span data-stu-id="c01f9-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <a name="wi-fi-data-in-spatial-maps"></a><span data-ttu-id="c01f9-174">Wi-Fi adatok térbeli térképekben való használata</span><span class="sxs-lookup"><span data-stu-id="c01f9-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="c01f9-175">HoloLens a Wi-Fi, hogy korrelálják az ismert terek adatbázisában tárolt hologram HoloLens helyeket és térképszakaszokat.</span><span class="sxs-lookup"><span data-stu-id="c01f9-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="c01f9-176">Az Wi-Fi nem érhetők el a felhasználók számára, és nem küldhetőek el a Microsoftnak a felhő vagy telemetria használatával.</span><span class="sxs-lookup"><span data-stu-id="c01f9-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="c01f9-177">Amíg a Wi-Fi engedélyezve van, a HoloLens a közeli és a közeli Wi-Fi korrelál.</span><span class="sxs-lookup"><span data-stu-id="c01f9-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="c01f9-178">Nincs különbség a viselkedésben, függetlenül attól, hogy egy hálózat csatlakoztatva van-e vagy csak a közelben van-e.</span><span class="sxs-lookup"><span data-stu-id="c01f9-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="c01f9-179">Ha Wi-Fi le van tiltva, a HoloLens továbbra is keres a térben.</span><span class="sxs-lookup"><span data-stu-id="c01f9-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="c01f9-180">A HoloLens azonban több térképadatot kell keresnie a spaces adatbázisban, és több időre lehet szüksége a hologramok kereséséhez.</span><span class="sxs-lookup"><span data-stu-id="c01f9-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="c01f9-181">A Wi-Fi információ nélkül a HoloLens-nek össze kell hasonlítani az aktív vizsgálatokat az eszközön tárolt összes hologramhorgony-horgonyval és térképszakaszokkal, hogy megtalálja a térkép megfelelő részét.</span><span class="sxs-lookup"><span data-stu-id="c01f9-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c01f9-182">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="c01f9-182">Related topics</span></span>

- [<span data-ttu-id="c01f9-183">Térbeli leképezés kialakítása</span><span class="sxs-lookup"><span data-stu-id="c01f9-183">Spatial mapping design</span></span>](/windows/mixed-reality/spatial-mapping)
