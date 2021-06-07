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
ms.openlocfilehash: 4b17fc134846a66046a819c56755d87206c5643e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378211"
---
# <a name="use-the-hololens-1st-gen-clicker"></a><span data-ttu-id="5ecc7-104">A HoloLens (1. generációs) clicker használata</span><span class="sxs-lookup"><span data-stu-id="5ecc7-104">Use the HoloLens (1st gen) clicker</span></span>

<span data-ttu-id="5ecc7-105">A clicker kifejezetten a HoloLenshez (1. generációs) készült, és egy másik lehetőséget biztosít a hologramok használatának.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-105">The clicker was designed specifically for HoloLens (1st gen) and gives you another way to interact with holograms.</span></span> <span data-ttu-id="5ecc7-106">A HoloLens (1. generációs) külön mezőben található.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-106">It comes with HoloLens (1st gen), in a separate box.</span></span>

<span data-ttu-id="5ecc7-107">Kézmozdulatok helyére használhatja az alkalmazások kiválasztásához, görgetéshez, áthelyezéséhez és átméretezéséhez.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-107">Use it in place of hand gestures to select, scroll, move, and resize apps.</span></span>

## <a name="clicker-hardware-and-pairing"></a><span data-ttu-id="5ecc7-108">Kattintóhardver és párosítás</span><span class="sxs-lookup"><span data-stu-id="5ecc7-108">Clicker hardware and pairing</span></span>

<span data-ttu-id="5ecc7-109">A HoloLens (1. generációs) kattintáshoz egy ujjlenyomat-hurok is van, amely megkönnyíti a könnyebb kezelhetőségüket és a jelzőfényt.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-109">The HoloLens (1st gen) clicker has a finger loop to make it easier to hold, and an indicator light.</span></span>

![A HoloLens Clicker](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a><span data-ttu-id="5ecc7-111">Kattintó jelzőfények</span><span class="sxs-lookup"><span data-stu-id="5ecc7-111">Clicker indicator lights</span></span>

<span data-ttu-id="5ecc7-112">A clicker jelzőfényei a következőt jelentik.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-112">Here's what the lights on the clicker mean.</span></span>

- <span data-ttu-id="5ecc7-113">**Villogó fehér**.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-113">**Blinking white**.</span></span> <span data-ttu-id="5ecc7-114">A clicker párosítási módban van.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-114">The clicker is in pairing mode.</span></span>
- <span data-ttu-id="5ecc7-115">**Gyorsan villogó fehér.**</span><span class="sxs-lookup"><span data-stu-id="5ecc7-115">**Fast-blinking white**.</span></span> <span data-ttu-id="5ecc7-116">A párosítás sikeres volt.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-116">Pairing was successful.</span></span>
- <span data-ttu-id="5ecc7-117">**Folytonos fehér**.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-117">**Solid white**.</span></span> <span data-ttu-id="5ecc7-118">A clicker (kattintásra) díj van betöltődve.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-118">The clicker is charging.</span></span>
- <span data-ttu-id="5ecc7-119">**Villogó ;**.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-119">**Blinking amber**.</span></span> <span data-ttu-id="5ecc7-120">Az akkumulátor alacsony.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-120">The battery is low.</span></span>
- <span data-ttu-id="5ecc7-121">**Solidrel**.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-121">**Solid amber**.</span></span> <span data-ttu-id="5ecc7-122">A kattintó hibába lépett, és újra kell indítania.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-122">The clicker ran into an error and you'll need to restart it.</span></span> <span data-ttu-id="5ecc7-123">A párosítás gomb megnyomása közben kattintson a gombra, és tartsa lenyomva 15 másodpercig.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-123">While pressing the pairing button, click and hold for 15 seconds.</span></span>

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a><span data-ttu-id="5ecc7-124">A clicker párosítása a HoloLens -sel (1. generációs)</span><span class="sxs-lookup"><span data-stu-id="5ecc7-124">Pair the clicker with your HoloLens (1st gen)</span></span>

1. <span data-ttu-id="5ecc7-125">A Bloom kézmozdulattal válassza a **Start** menüt, majd válassza a Beállítások Eszközök lehetőséget,  >   és ellenőrizze, hogy a Bluetooth be van-e va.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-125">Use the bloom gesture to go to **Start**, then select **Settings** > **Devices** and verify that Bluetooth is on.</span></span>
1. <span data-ttu-id="5ecc7-126">A kattintásra nyomja le és tartsa lenyomva a párosítás gombot, amíg az állapotjelző világos színre nem villog.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-126">On the clicker, press and hold the pairing button until the status light blinks white.</span></span>
1. <span data-ttu-id="5ecc7-127">A párosítási képernyőn válassza a Clicker Pair **(Kattintáspár)**  >  **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="5ecc7-127">On the pairing screen, select **Clicker** > **Pair**.</span></span>

### <a name="charge-the-clicker"></a><span data-ttu-id="5ecc7-128">A kattintó díjának felbevall</span><span class="sxs-lookup"><span data-stu-id="5ecc7-128">Charge the clicker</span></span>

<span data-ttu-id="5ecc7-129">Ha a clicker akkumulátor alacsony, az akkumulátor kijelzője villogni kezd.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-129">When the clicker battery is low, the battery indicator will blink amber.</span></span> <span data-ttu-id="5ecc7-130">Csatlakoztassa a Micro USB-kábelt egy USB-tápegységhez az eszköz feltöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-130">Plug the Micro USB cable into a USB power supply to charge the device.</span></span>

## <a name="use-the-clicker-with-hololens-1st-gen"></a><span data-ttu-id="5ecc7-131">A clicker használata a HoloLensben (1. generációs)</span><span class="sxs-lookup"><span data-stu-id="5ecc7-131">Use the clicker with HoloLens (1st gen)</span></span>

### <a name="hold-the-clicker"></a><span data-ttu-id="5ecc7-132">Tartsa lenyomva a kattintást</span><span class="sxs-lookup"><span data-stu-id="5ecc7-132">Hold the clicker</span></span>

<span data-ttu-id="5ecc7-133">A kattintáshoz csúsztassa a hurkot a gyűrűre vagy a középső ujjlenyomatra úgy, hogy a Micro USB-port a saját maga felé ássa az arcot.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-133">To put on the clicker, slide the loop over your ring or middle finger so that the Micro USB port faces toward your wrist.</span></span> <span data-ttu-id="5ecc7-134">A behúzásnál ne feledjen.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-134">Rest your thumb in the indentation.</span></span>

![A Clicker (Kattintás)](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a><span data-ttu-id="5ecc7-136">Kattintási kézmozdulatok</span><span class="sxs-lookup"><span data-stu-id="5ecc7-136">Clicker gestures</span></span>

<span data-ttu-id="5ecc7-137">A kattintásos kézmozdulatok kis elforgatások, nem pedig a HoloLens kézmozdulatokhoz használt nagyobb mozgások.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-137">Clicker gestures are small wrist rotations, not the larger movements used for HoloLens hand gestures.</span></span> <span data-ttu-id="5ecc7-138">HoloLens felismeri a kézmozdulatokat, és akkor is rákattint, ha a kattintás a kézmozdulat-kereten kívül [esik,](hololens1-basic-usage.md)így a kattintást az Ön számára legkényelmesebb helyen tarthatja.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-138">And HoloLens recognizes your gestures and clicks even if the clicker is outside the [gesture frame](hololens1-basic-usage.md), so you can hold the clicker in the position that's most comfortable for you.</span></span>

- <span data-ttu-id="5ecc7-139">**Válassza a lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="5ecc7-139">**Select**.</span></span> <span data-ttu-id="5ecc7-140">Egy hologram, gomb vagy más elem kiválasztásához tekintsen rá, majd kattintson rá.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-140">To select a hologram, button, or other element, gaze at it, then click.</span></span>

- <span data-ttu-id="5ecc7-141">Kattintson és tartsa lenyomva a **gombra.**</span><span class="sxs-lookup"><span data-stu-id="5ecc7-141">**Click and hold**.</span></span> <span data-ttu-id="5ecc7-142">Kattintson a gombra, és tartsa lenyomva a lefelé mutató ujjlenyomatot, és tegye meg néhányat a koppintással és a lenyomva nyomással, például egy hologram áthelyezését vagy átméretezését.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-142">Click and hold your thumb down on the button to do some of the same things you would with tap and hold, such as move or resize a hologram.</span></span>

- <span data-ttu-id="5ecc7-143">**Görgessen.**</span><span class="sxs-lookup"><span data-stu-id="5ecc7-143">**Scroll**.</span></span> <span data-ttu-id="5ecc7-144">Az alkalmazássávon válassza a **Görgetőeszköz lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="5ecc7-144">On the app bar, select **Scroll Tool**.</span></span> <span data-ttu-id="5ecc7-145">Kattintson és tartsa lenyomva a kattintást, majd forgassa fel, le, balra vagy jobbra.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-145">Click and hold, then rotate the clicker up, down, left, or right.</span></span> <span data-ttu-id="5ecc7-146">A gyorsabb görgetéshez mozgassa a kézzel a görgetőeszköz közepétől távolabb.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-146">To scroll faster, move your hand farther from the center of the scroll tool.</span></span>

- <span data-ttu-id="5ecc7-147">**Nagyítás**.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-147">**Zoom**.</span></span> <span data-ttu-id="5ecc7-148">Az alkalmazássávon válassza a **Zoom Tool lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="5ecc7-148">On the app bar, select **Zoom Tool**.</span></span> <span data-ttu-id="5ecc7-149">Kattintson és tartsa lenyomva, majd a nagyításhoz felfelé forgassuk a kattintást, vagy kicsinyítsünk le.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-149">Click and hold, then rotate the clicker up to zoom in, or down to zoom out.</span></span>

> [!TIP]
> <span data-ttu-id="5ecc7-150">Ha nagyít vagy kicsinyít a Microsoft Edge, egy oldalra nézve kattintson duplán.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-150">To zoom in or out when using Microsoft Edge, gaze at a page and double-click.</span></span>

## <a name="restart-or-recover-the-clicker"></a><span data-ttu-id="5ecc7-151">A kattintó újraindítása vagy helyreállítása</span><span class="sxs-lookup"><span data-stu-id="5ecc7-151">Restart or recover the clicker</span></span>

<span data-ttu-id="5ecc7-152">Az íme néhány dolog, amit megpróbálhat, ha a HoloLens-kattintó nem válaszol vagy nem működik jól.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-152">Here are some things to try if the HoloLens clicker is unresponsive or isn’t working well.</span></span>

### <a name="restart-the-clicker"></a><span data-ttu-id="5ecc7-153">A clicker újraindítása</span><span class="sxs-lookup"><span data-stu-id="5ecc7-153">Restart the clicker</span></span>

<span data-ttu-id="5ecc7-154">Nyomja le és tartsa lenyomva a párosítási gombot a toll tippjével.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-154">Use the tip of a pen to press and hold the pairing button.</span></span> <span data-ttu-id="5ecc7-155">Ugyanakkor kattintson a gombra, és tartsa lenyomva a kattintást 15 másodpercig.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-155">At the same time, click and hold the clicker for 15 seconds.</span></span> <span data-ttu-id="5ecc7-156">Ha a clicker már párosítva volt a HoloLens-sel, akkor az újraindítás után is párban marad.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-156">If the clicker was already paired with your HoloLens, it will stay paired after it restarts.</span></span>

<span data-ttu-id="5ecc7-157">Ha a clicker nem kapcsol be vagy indul újra, próbálja meg a HoloLens-menü használatával kitanni a díjat.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-157">If the clicker won't turn on or restart, try charging it by using the HoloLens charger.</span></span> <span data-ttu-id="5ecc7-158">Ha az akkumulátor nagyon alacsony, a fehér jelzőfény be- és bekapcsolás eltarthat néhány percig.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-158">If the battery is very low, it might take a few minutes for the white indicator light to turn on.</span></span>

### <a name="re-pair-the-clicker"></a><span data-ttu-id="5ecc7-159">A clicker újra párosítása</span><span class="sxs-lookup"><span data-stu-id="5ecc7-159">Re-pair the clicker</span></span>

<span data-ttu-id="5ecc7-160">Válassza **a Beállítások** Eszközök  >  **lehetőséget,** majd kattintson a kattintásra.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-160">Select **Settings** > **Devices** and select the clicker.</span></span> <span data-ttu-id="5ecc7-161">Válassza **az Eltávolítás** lehetőséget, várjon néhány másodpercet, majd párosítsa újra a választógombot.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-161">Select **Remove**, wait a few seconds, then pair the clicker again.</span></span>

### <a name="recover-the-clicker"></a><span data-ttu-id="5ecc7-162">A kattintó helyreállítása</span><span class="sxs-lookup"><span data-stu-id="5ecc7-162">Recover the clicker</span></span>

<span data-ttu-id="5ecc7-163">Ha az újraindítás és a kattintás újrapározása nem oldja meg a problémát, a Windows Eszköz-helyreállítási eszköz segíthet a helyreállításban.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-163">If restarting and re-pairing the clicker don’t fix the problem, the Windows Device Recovery Tool can help you recover it.</span></span> <span data-ttu-id="5ecc7-164">A helyreállítási folyamat némi időt is el fog venni, és a kattintásra kattintó szoftver legújabb verzióját fogja telepíteni.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-164">The recovery process may take some time, and it will install the latest version of the clicker software.</span></span> <span data-ttu-id="5ecc7-165">Az eszköz csak akkor használható, ha legalább Windows 10 legalább 4 GB szabad tárhellyel rendelkező számítógépre van szüksége.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-165">To use the tool, you’ll need a computer running Windows 10 or later that has at least 4 GB of free storage space.</span></span>

<span data-ttu-id="5ecc7-166">A kattintó helyreállítása:</span><span class="sxs-lookup"><span data-stu-id="5ecc7-166">To recover the clicker:</span></span>

1. <span data-ttu-id="5ecc7-167">Töltse le és telepítse a [Windows Eszköz-helyreállítási eszközt](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) a számítógépre.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-167">Download and install the [Windows Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) on your computer.</span></span>
1. <span data-ttu-id="5ecc7-168">Csatlakoztassa a clickert a számítógéphez a HoloLenshez csatlakoztatott Micro USB-kábellel.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-168">Connect the clicker to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="5ecc7-169">Futtassa a Windows Eszköz-helyreállítási eszközt, és kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-169">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="5ecc7-170">Ha a rendszer nem észleli automatikusan  a kattintást, válassza az Eszköz nem észlelhető lehetőséget, és kövesse az utasításokat az eszköz helyreállítási módba kapcsolására.</span><span class="sxs-lookup"><span data-stu-id="5ecc7-170">If the clicker isn’t automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>
