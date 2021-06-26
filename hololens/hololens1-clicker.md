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
# <a name="use-the-hololens-1st-gen-clicker"></a><span data-ttu-id="d0578-104">A HoloLens (1. generációs) clicker használata</span><span class="sxs-lookup"><span data-stu-id="d0578-104">Use the HoloLens (1st gen) clicker</span></span>

<span data-ttu-id="d0578-105">A clicker kifejezetten a HoloLenshez (1. generációs) készült, és egy másik lehetőséget biztosít a hologramok használatának.</span><span class="sxs-lookup"><span data-stu-id="d0578-105">The clicker was designed specifically for HoloLens (1st gen) and gives you another way to interact with holograms.</span></span> <span data-ttu-id="d0578-106">A HoloLens (1. generációs) külön mezőben található.</span><span class="sxs-lookup"><span data-stu-id="d0578-106">It comes with HoloLens (1st gen), in a separate box.</span></span>

<span data-ttu-id="d0578-107">Kézmozdulatok helyére használhatja az alkalmazások kiválasztásához, görgetéshez, áthelyezéséhez és átméretezéséhez.</span><span class="sxs-lookup"><span data-stu-id="d0578-107">Use it in place of hand gestures to select, scroll, move, and resize apps.</span></span>

## <a name="clicker-hardware-and-pairing"></a><span data-ttu-id="d0578-108">Clicker hardver és párosítás</span><span class="sxs-lookup"><span data-stu-id="d0578-108">Clicker hardware and pairing</span></span>

<span data-ttu-id="d0578-109">A HoloLens (1. generációs) kattintó egy ujjlenyomat-hurokkal rendelkezik, amely megkönnyíti a könnyebb kezelhetőségüket és a jelzőfényt.</span><span class="sxs-lookup"><span data-stu-id="d0578-109">The HoloLens (1st gen) clicker has a finger loop to make it easier to hold, and an indicator light.</span></span>

![A HoloLens Clicker](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a><span data-ttu-id="d0578-111">Kattintó jelzőfények</span><span class="sxs-lookup"><span data-stu-id="d0578-111">Clicker indicator lights</span></span>

<span data-ttu-id="d0578-112">A jelzőgomb világítása a következőt jelenti.</span><span class="sxs-lookup"><span data-stu-id="d0578-112">Here's what the lights on the clicker mean.</span></span>

- <span data-ttu-id="d0578-113">**Villogó fehér**.</span><span class="sxs-lookup"><span data-stu-id="d0578-113">**Blinking white**.</span></span> <span data-ttu-id="d0578-114">A clicker párosítási módban van.</span><span class="sxs-lookup"><span data-stu-id="d0578-114">The clicker is in pairing mode.</span></span>
- <span data-ttu-id="d0578-115">**Gyorsan villogó fehér.**</span><span class="sxs-lookup"><span data-stu-id="d0578-115">**Fast-blinking white**.</span></span> <span data-ttu-id="d0578-116">A párosítás sikeres volt.</span><span class="sxs-lookup"><span data-stu-id="d0578-116">Pairing was successful.</span></span>
- <span data-ttu-id="d0578-117">**Folytonos fehér**.</span><span class="sxs-lookup"><span data-stu-id="d0578-117">**Solid white**.</span></span> <span data-ttu-id="d0578-118">A clicker (kattintásra) díj van betöltődve.</span><span class="sxs-lookup"><span data-stu-id="d0578-118">The clicker is charging.</span></span>
- <span data-ttu-id="d0578-119">**Villogó ;**.</span><span class="sxs-lookup"><span data-stu-id="d0578-119">**Blinking amber**.</span></span> <span data-ttu-id="d0578-120">Az akkumulátor alacsony.</span><span class="sxs-lookup"><span data-stu-id="d0578-120">The battery is low.</span></span>
- <span data-ttu-id="d0578-121">**Solidrel**.</span><span class="sxs-lookup"><span data-stu-id="d0578-121">**Solid amber**.</span></span> <span data-ttu-id="d0578-122">A kattintó hibába lépett, és újra kell indítania.</span><span class="sxs-lookup"><span data-stu-id="d0578-122">The clicker ran into an error and you'll need to restart it.</span></span> <span data-ttu-id="d0578-123">A párosítás gomb megnyomása közben kattintson a gombra, és tartsa lenyomva 15 másodpercig.</span><span class="sxs-lookup"><span data-stu-id="d0578-123">While pressing the pairing button, click and hold for 15 seconds.</span></span>

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a><span data-ttu-id="d0578-124">A clicker párosítása a HoloLens -sel (1. generációs)</span><span class="sxs-lookup"><span data-stu-id="d0578-124">Pair the clicker with your HoloLens (1st gen)</span></span>

1. <span data-ttu-id="d0578-125">A Bloom kézmozdulattal válassza a **Start** menüt, majd válassza a Beállítások  >  **Eszközök** lehetőséget, és ellenőrizze, hogy a Bluetooth be van-e va.</span><span class="sxs-lookup"><span data-stu-id="d0578-125">Use the bloom gesture to go to **Start**, then select **Settings** > **Devices** and verify that Bluetooth is on.</span></span>
1. <span data-ttu-id="d0578-126">A kattintásra nyomja le és tartsa lenyomva a párosítás gombot, amíg az állapotjelző fény fehér színre nem villog.</span><span class="sxs-lookup"><span data-stu-id="d0578-126">On the clicker, press and hold the pairing button until the status light blinks white.</span></span>
1. <span data-ttu-id="d0578-127">A párosítási képernyőn válassza a Clicker Pair **(Kattintáspár)**  >  **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="d0578-127">On the pairing screen, select **Clicker** > **Pair**.</span></span>

### <a name="charge-the-clicker"></a><span data-ttu-id="d0578-128">A kattintó díjának felbevall</span><span class="sxs-lookup"><span data-stu-id="d0578-128">Charge the clicker</span></span>

<span data-ttu-id="d0578-129">Ha a clicker akkumulátor alacsony, az akkumulátor kijelzője villogni kezd.</span><span class="sxs-lookup"><span data-stu-id="d0578-129">When the clicker battery is low, the battery indicator will blink amber.</span></span> <span data-ttu-id="d0578-130">Csatlakoztassa a Micro USB-kábelt egy USB-tápegységhez az eszköz feltöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="d0578-130">Plug the Micro USB cable into a USB power supply to charge the device.</span></span>

## <a name="use-the-clicker-with-hololens-1st-gen"></a><span data-ttu-id="d0578-131">A clicker használata a HoloLensben (1. generációs)</span><span class="sxs-lookup"><span data-stu-id="d0578-131">Use the clicker with HoloLens (1st gen)</span></span>

### <a name="hold-the-clicker"></a><span data-ttu-id="d0578-132">Tartsa lenyomva a kattintást</span><span class="sxs-lookup"><span data-stu-id="d0578-132">Hold the clicker</span></span>

<span data-ttu-id="d0578-133">A kattintáshoz csúsztassa a hurkot a gyűrűre vagy a középső ujjlenyomatra úgy, hogy a Micro USB-port a sajátja felé néz.</span><span class="sxs-lookup"><span data-stu-id="d0578-133">To put on the clicker, slide the loop over your ring or middle finger so that the Micro USB port faces toward your wrist.</span></span> <span data-ttu-id="d0578-134">A behúzásnál ne feledjen.</span><span class="sxs-lookup"><span data-stu-id="d0578-134">Rest your thumb in the indentation.</span></span>

![A Clicker (Kattintás)](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a><span data-ttu-id="d0578-136">Kattintási kézmozdulatok</span><span class="sxs-lookup"><span data-stu-id="d0578-136">Clicker gestures</span></span>

<span data-ttu-id="d0578-137">A kattintásos kézmozdulatok kis elforgatások, nem pedig a HoloLens kézmozdulatokhoz használt nagyobb mozgások.</span><span class="sxs-lookup"><span data-stu-id="d0578-137">Clicker gestures are small wrist rotations, not the larger movements used for HoloLens hand gestures.</span></span> <span data-ttu-id="d0578-138">HoloLens felismeri a kézmozdulatokat, és akkor is rákattint, ha a kattintás a kézmozdulat-kereten kívül [esik,](hololens1-basic-usage.md)így a kattintást az Ön számára legkényelmesebb helyen tarthatja.</span><span class="sxs-lookup"><span data-stu-id="d0578-138">And HoloLens recognizes your gestures and clicks even if the clicker is outside the [gesture frame](hololens1-basic-usage.md), so you can hold the clicker in the position that's most comfortable for you.</span></span>

- <span data-ttu-id="d0578-139">**Válassza a lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="d0578-139">**Select**.</span></span> <span data-ttu-id="d0578-140">Egy hologram, gomb vagy más elem kiválasztásához tekintsen rá, majd kattintson rá.</span><span class="sxs-lookup"><span data-stu-id="d0578-140">To select a hologram, button, or other element, gaze at it, then click.</span></span>

- <span data-ttu-id="d0578-141">Kattintson és tartsa lenyomva a **gombra.**</span><span class="sxs-lookup"><span data-stu-id="d0578-141">**Click and hold**.</span></span> <span data-ttu-id="d0578-142">Kattintson a gombra, és tartsa lenyomva a lefelé mutató lefelé mutató ujjlenyomatot, hogy néhányat a koppintással és a lenyomva gombra kattintva és lenyomva tartással is el tud majd látni, például egy hologram áthelyezését vagy átméretezését.</span><span class="sxs-lookup"><span data-stu-id="d0578-142">Click and hold your thumb down on the button to do some of the same things you would with tap and hold, such as move or resize a hologram.</span></span>

- <span data-ttu-id="d0578-143">**Görgessen.**</span><span class="sxs-lookup"><span data-stu-id="d0578-143">**Scroll**.</span></span> <span data-ttu-id="d0578-144">Az alkalmazássávon válassza a **Görgetőeszköz lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="d0578-144">On the app bar, select **Scroll Tool**.</span></span> <span data-ttu-id="d0578-145">Kattintson és tartsa lenyomva a kattintást, majd forgassa fel, le, balra vagy jobbra.</span><span class="sxs-lookup"><span data-stu-id="d0578-145">Click and hold, then rotate the clicker up, down, left, or right.</span></span> <span data-ttu-id="d0578-146">A gyorsabb görgetéshez mozgassa a kézzel a görgetőeszköz közepétől távolabb.</span><span class="sxs-lookup"><span data-stu-id="d0578-146">To scroll faster, move your hand farther from the center of the scroll tool.</span></span>

- <span data-ttu-id="d0578-147">**Nagyítás**.</span><span class="sxs-lookup"><span data-stu-id="d0578-147">**Zoom**.</span></span> <span data-ttu-id="d0578-148">Az alkalmazássávon válassza a **Zoom Tool lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="d0578-148">On the app bar, select **Zoom Tool**.</span></span> <span data-ttu-id="d0578-149">Kattintson és tartsa lenyomva, majd a nagyításhoz felfelé forgassuk a kattintást, vagy kicsinyítsünk le.</span><span class="sxs-lookup"><span data-stu-id="d0578-149">Click and hold, then rotate the clicker up to zoom in, or down to zoom out.</span></span>

> [!TIP]
> <span data-ttu-id="d0578-150">A nagyításhoz vagy kicsinyítéshez a Microsoft Edge egy oldalra nézve kattintson duplán.</span><span class="sxs-lookup"><span data-stu-id="d0578-150">To zoom in or out when using Microsoft Edge, gaze at a page and double-click.</span></span>

## <a name="im-having-problems-using-the-hololens-clicker"></a><span data-ttu-id="d0578-151">Problémákat tapasztalok a HoloLens-kattintással</span><span class="sxs-lookup"><span data-stu-id="d0578-151">I'm having problems using the HoloLens clicker</span></span>

<span data-ttu-id="d0578-152">A [kattintással jelölheti](hololens1-clicker.md) ki, görgetheti, áthelyezheti és átméretezheti a hologramokat.</span><span class="sxs-lookup"><span data-stu-id="d0578-152">Use the [clicker](hololens1-clicker.md) to select, scroll, move, and resize holograms.</span></span> <span data-ttu-id="d0578-153">Az egyes alkalmazások további kattintásos kézmozdulatokat is támogathatnak.</span><span class="sxs-lookup"><span data-stu-id="d0578-153">Individual apps may support additional clicker gestures.</span></span>

<span data-ttu-id="d0578-154">Ha nem tudja használni a kattintót, ellenőrizze, hogy a díj fel van-e töltve és párosítva van-e a HoloLens-sel.</span><span class="sxs-lookup"><span data-stu-id="d0578-154">If you're having trouble using the clicker, make sure that it's charged and paired with your HoloLens.</span></span> <span data-ttu-id="d0578-155">Ha az akkumulátor alacsony, a jelzőfény villogni kezd.</span><span class="sxs-lookup"><span data-stu-id="d0578-155">If the battery is low, the indicator light blinks amber.</span></span> <span data-ttu-id="d0578-156">A clicker párosításának ellenőrzéséhez válassza a Beállítások eszközök lehetőséget, és ellenőrizze, hogy  >   megjelenik-e.</span><span class="sxs-lookup"><span data-stu-id="d0578-156">To verify that the clicker is paired, go to **Settings** > **Devices** and see if it shows up there.</span></span> <span data-ttu-id="d0578-157">További információ: [A kattintó párosítása.](hololens1-clicker.md)</span><span class="sxs-lookup"><span data-stu-id="d0578-157">For more information, see [Pair the clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="d0578-158">Ha a kattintó fel van töltve és párosítva van, és továbbra is problémákat tapasztal, állítsa alaphelyzetbe úgy, hogy 15 másodpercig lenyomva tartja a fő gombot és a párosítás gombot.</span><span class="sxs-lookup"><span data-stu-id="d0578-158">If the clicker is charged and paired and you're still having problems, reset it by holding down the main button and the pairing button for 15 seconds.</span></span> <span data-ttu-id="d0578-159">Ezután párosítsa újra a clickert a HoloLens-sel.</span><span class="sxs-lookup"><span data-stu-id="d0578-159">Then pair the clicker with your HoloLens again.</span></span>

<span data-ttu-id="d0578-160">Ha a kattintó alaphelyzetbe állítása nem segít, lásd: [Restart or recover the HoloLens clicker (A HoloLens-kattintó újraindítása vagy helyreállítása).](hololens1-clicker.md#restart-or-recover-the-clicker)</span><span class="sxs-lookup"><span data-stu-id="d0578-160">If resetting the clicker doesn't help, see [Restart or recover the HoloLens clicker](hololens1-clicker.md#restart-or-recover-the-clicker).</span></span>
## <a name="restart-or-recover-the-clicker"></a><span data-ttu-id="d0578-161">A kattintó újraindítása vagy helyreállítása</span><span class="sxs-lookup"><span data-stu-id="d0578-161">Restart or recover the clicker</span></span>

<span data-ttu-id="d0578-162">Az íme néhány dolog, amit megpróbálhat, ha a HoloLens-kattintó nem válaszol vagy nem működik jól.</span><span class="sxs-lookup"><span data-stu-id="d0578-162">Here are some things to try if the HoloLens clicker is unresponsive or isn’t working well.</span></span>

### <a name="restart-the-clicker"></a><span data-ttu-id="d0578-163">A clicker újraindítása</span><span class="sxs-lookup"><span data-stu-id="d0578-163">Restart the clicker</span></span>

<span data-ttu-id="d0578-164">Nyomja le és tartsa lenyomva a párosítási gombot a toll tippjével.</span><span class="sxs-lookup"><span data-stu-id="d0578-164">Use the tip of a pen to press and hold the pairing button.</span></span> <span data-ttu-id="d0578-165">Ugyanakkor kattintson a gombra, és tartsa lenyomva a kattintást 15 másodpercig.</span><span class="sxs-lookup"><span data-stu-id="d0578-165">At the same time, click and hold the clicker for 15 seconds.</span></span> <span data-ttu-id="d0578-166">Ha a clicker már párosítva volt a HoloLens-sel, akkor az újraindítás után is párban marad.</span><span class="sxs-lookup"><span data-stu-id="d0578-166">If the clicker was already paired with your HoloLens, it will stay paired after it restarts.</span></span>

<span data-ttu-id="d0578-167">Ha a kattintó nem kapcsol be vagy indul újra, próbálja meg a HoloLens-menü használatával felárasni.</span><span class="sxs-lookup"><span data-stu-id="d0578-167">If the clicker won't turn on or restart, try charging it by using the HoloLens charger.</span></span> <span data-ttu-id="d0578-168">Ha az akkumulátor nagyon alacsony, eltarthat néhány percig, hogy a fehér jelzőfény begyűjtsen.</span><span class="sxs-lookup"><span data-stu-id="d0578-168">If the battery is very low, it might take a few minutes for the white indicator light to turn on.</span></span>

### <a name="re-pair-the-clicker"></a><span data-ttu-id="d0578-169">A clicker újra párosítása</span><span class="sxs-lookup"><span data-stu-id="d0578-169">Re-pair the clicker</span></span>

<span data-ttu-id="d0578-170">Válassza **a Beállítások** Eszközök  >  **lehetőséget,** majd kattintson a kattintásra.</span><span class="sxs-lookup"><span data-stu-id="d0578-170">Select **Settings** > **Devices** and select the clicker.</span></span> <span data-ttu-id="d0578-171">Válassza **az Eltávolítás** lehetőséget, várjon néhány másodpercet, majd párosítsa újra a választógombot.</span><span class="sxs-lookup"><span data-stu-id="d0578-171">Select **Remove**, wait a few seconds, then pair the clicker again.</span></span>

### <a name="recover-the-clicker"></a><span data-ttu-id="d0578-172">A kattintó helyreállítása</span><span class="sxs-lookup"><span data-stu-id="d0578-172">Recover the clicker</span></span>

<span data-ttu-id="d0578-173">Ha az újraindítás és a kattintás újrapározása nem oldja meg a problémát, a Windows Eszköz-helyreállítási eszköz segíthet a helyreállításban.</span><span class="sxs-lookup"><span data-stu-id="d0578-173">If restarting and re-pairing the clicker don’t fix the problem, the Windows Device Recovery Tool can help you recover it.</span></span> <span data-ttu-id="d0578-174">A helyreállítási folyamat tovább is tart, és a clicker szoftver legújabb verzióját fogja telepíteni.</span><span class="sxs-lookup"><span data-stu-id="d0578-174">The recovery process may take some time, and it will install the latest version of the clicker software.</span></span> <span data-ttu-id="d0578-175">Az eszköz csak akkor használható, ha legalább Windows 10 legalább 4 GB szabad tárhellyel rendelkező számítógépre van szüksége.</span><span class="sxs-lookup"><span data-stu-id="d0578-175">To use the tool, you’ll need a computer running Windows 10 or later that has at least 4 GB of free storage space.</span></span>

<span data-ttu-id="d0578-176">A kattintást gombra kattintva a következő helyre lehet állítani:</span><span class="sxs-lookup"><span data-stu-id="d0578-176">To recover the clicker:</span></span>

1. <span data-ttu-id="d0578-177">Töltse le és telepítse a [Windows Eszköz-helyreállítási eszközt](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) a számítógépre.</span><span class="sxs-lookup"><span data-stu-id="d0578-177">Download and install the [Windows Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) on your computer.</span></span>
1. <span data-ttu-id="d0578-178">Csatlakoztassa a clickert a számítógéphez a HoloLenshez csatlakoztatott Micro USB-kábellel.</span><span class="sxs-lookup"><span data-stu-id="d0578-178">Connect the clicker to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="d0578-179">Futtassa a Windows Eszköz-helyreállítási eszközt, és kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="d0578-179">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="d0578-180">Ha a rendszer nem észleli automatikusan  a kattintást, válassza az Eszköz nem észlelhető lehetőséget, és kövesse az utasításokat az eszköz helyreállítási módba kapcsolására.</span><span class="sxs-lookup"><span data-stu-id="d0578-180">If the clicker isn’t automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>

