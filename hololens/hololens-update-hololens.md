---
title: A HoloLens 2 frissítése
description: Megtudhatja, hogyan ellenőrizheti a HoloLens buildszámát, hogyan tarthatja naprakészen az eszközfrissítéseket, hogyan csatlakozhat az Insiders programhoz, és hogyan ússíthatja vissza a frissítéseket.
keywords: how-to, update, roll back, HoloLens, check build, build number
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924111"
---
# <a name="update-hololens-2"></a><span data-ttu-id="d478d-104">A HoloLens 2 frissítése</span><span class="sxs-lookup"><span data-stu-id="d478d-104">Update HoloLens 2</span></span>

<span data-ttu-id="d478d-105">A HoloLens Windows Update, mint más Windows 10 eszközök.</span><span class="sxs-lookup"><span data-stu-id="d478d-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="d478d-106">A HoloLens automatikusan letölti és telepíti a rendszerfrissítéseket, amikor csatlakoztatva vannak az áramellátáshoz és csatlakoznak az internethez, még készenléti állapotban is.</span><span class="sxs-lookup"><span data-stu-id="d478d-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="d478d-107">Ez a cikk a HoloLens-eszközöket a következő eszközökhöz fogja használni:</span><span class="sxs-lookup"><span data-stu-id="d478d-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="d478d-108">az operációs rendszer aktuális verziójának megtekintése (buildszám)</span><span class="sxs-lookup"><span data-stu-id="d478d-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="d478d-109">frissítések keresése</span><span class="sxs-lookup"><span data-stu-id="d478d-109">checking for updates</span></span>
- <span data-ttu-id="d478d-110">a HoloLens manuális frissítése</span><span class="sxs-lookup"><span data-stu-id="d478d-110">manually updating HoloLens</span></span>
- <span data-ttu-id="d478d-111">korábbi frissítésre való visszagördülés</span><span class="sxs-lookup"><span data-stu-id="d478d-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="d478d-112">Ellenőrizze az operációs rendszer verzióját (buildszám)</span><span class="sxs-lookup"><span data-stu-id="d478d-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="d478d-113">A rendszer verziószámát (buildszám) a Settings (Beállítások) alkalmazás megnyitásával és a System About **(Rendszerről)** lehetőség kiválasztásával  >  **ellenőrizheti.**</span><span class="sxs-lookup"><span data-stu-id="d478d-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="d478d-114">Frissítések keresése és manuális frissítés</span><span class="sxs-lookup"><span data-stu-id="d478d-114">Check for updates and manually update</span></span>

<span data-ttu-id="d478d-115">A beállítások között bármikor ellenőrizheti a frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="d478d-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="d478d-116">Az elérhető frissítések és az új frissítések keresése:</span><span class="sxs-lookup"><span data-stu-id="d478d-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="d478d-117">Nyissa meg a **Gépházat**.</span><span class="sxs-lookup"><span data-stu-id="d478d-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="d478d-118">Lépjen az **Update & Security**  >  **Windows Update.**</span><span class="sxs-lookup"><span data-stu-id="d478d-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="d478d-119">Válassza a **Frissítések keresése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d478d-119">Select **Check for updates**.</span></span>

<span data-ttu-id="d478d-120">Ha van elérhető frissítés, az elkezdi letölteni az új verziót.</span><span class="sxs-lookup"><span data-stu-id="d478d-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="d478d-121">A letöltés befejezése után válassza az **Újraindítás** most gombot a telepítés aktiválásához.</span><span class="sxs-lookup"><span data-stu-id="d478d-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="d478d-122">Ha az eszköz 40% alatti, és nincs csatlakoztatva, az újraindítás nem indítja el a frissítés telepítését.</span><span class="sxs-lookup"><span data-stu-id="d478d-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="d478d-123">Amíg a HoloLens telepíti a frissítést, forgó fogaskerékeket és folyamatjelzőt jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="d478d-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="d478d-124">Ez idő alatt ne kapcsolja ki a HoloLenst.</span><span class="sxs-lookup"><span data-stu-id="d478d-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="d478d-125">A telepítés befejezése után a rendszer automatikusan újraindul.</span><span class="sxs-lookup"><span data-stu-id="d478d-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="d478d-126">A HoloLens egyszerre csak egy frissítést alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="d478d-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="d478d-127">Ha a HoloLens egynél több verzióval régebbi, előfordulhat, hogy többször is végig kell futnia a frissítési folyamaton, hogy teljesen naprakész legyen.</span><span class="sxs-lookup"><span data-stu-id="d478d-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="d478d-128">Vissza korábbi verzióra való áttért</span><span class="sxs-lookup"><span data-stu-id="d478d-128">Go back to a previous version</span></span>

<span data-ttu-id="d478d-129">Bizonyos esetekben érdemes lehet visszatérni a HoloLens szoftver egy korábbi verziójára.</span><span class="sxs-lookup"><span data-stu-id="d478d-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="d478d-130">A javasolt lépések a következőek:</span><span class="sxs-lookup"><span data-stu-id="d478d-130">The recommended steps are:</span></span>

1. <span data-ttu-id="d478d-131">Lépjen kapcsolatba az ügyfélszolgálattal, és nézze meg, hogy meg tudják-e oldani a problémát.</span><span class="sxs-lookup"><span data-stu-id="d478d-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="d478d-132">Győződjön **meg** arról, hogy a választható vagy **a** teljes telemetria engedélyezve van – így a hiba könnyebben kezelhető és könnyebben diagnosztizálható a mérnökök számára.</span><span class="sxs-lookup"><span data-stu-id="d478d-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="d478d-133">[A fájlvisszacsatolás](hololens-feedback.md) a lehető leíró jellegű.</span><span class="sxs-lookup"><span data-stu-id="d478d-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="d478d-134">Jegyezze fel a címet, vagy használja a megosztási funkciót, hogy megosztja a hibát a támogatási szolgálattal.</span><span class="sxs-lookup"><span data-stu-id="d478d-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="d478d-135">Lépjen kapcsolatba az [ügyfélszolgálattal.](https://aka.ms/hlsupport)</span><span class="sxs-lookup"><span data-stu-id="d478d-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="d478d-136">Ha a problémát úgy kell megoldani, hogy visszatér egy korábbi verzióhoz, akkor meg tudják oldani az FFU-t az eszköz flash (FFU) szolgáltatásához.</span><span class="sxs-lookup"><span data-stu-id="d478d-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="d478d-137">Ha ez nem működik, állítsa alaphelyzetbe vagy [perjelre a HoloLens 2-t az Advanced Recovery Companion (Speciális helyreállítás-kísérő) funkcióval.](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="d478d-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="d478d-138">A számítógépen töltse le az [Advanced Recovery Companiont a](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="d478d-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="d478d-139">Győződjön meg arról, hogy nincs csatlakoztatva telefon vagy Windows-eszköz a számítógéphez.</span><span class="sxs-lookup"><span data-stu-id="d478d-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="d478d-140">Válassza ki, hogy melyik verziót szeretné flash-ként látni:</span><span class="sxs-lookup"><span data-stu-id="d478d-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="d478d-141">Letöltheti a [legújabb HoloLens 2-kiadást.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="d478d-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="d478d-142">Használhatja az ARC-gazdagépek alapértelmezett buildét.</span><span class="sxs-lookup"><span data-stu-id="d478d-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="d478d-143">(Ha ezt a lehetőséget választja, hagyja ki a következő lépést.)</span><span class="sxs-lookup"><span data-stu-id="d478d-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="d478d-144">Használhatja a megadott buildtámogatást.</span><span class="sxs-lookup"><span data-stu-id="d478d-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="d478d-145">Ha végzett ezekkel a letöltésekkel, nyissa meg **Fájlkezelő**  >  **letöltések gombra.**</span><span class="sxs-lookup"><span data-stu-id="d478d-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="d478d-146">Kattintson a jobb gombbal az előbb letöltött tömörített mappára, és válassza az Extract all Extract **(Összes** kibontás) lehetőséget a  >   kicsomagoláshoz.</span><span class="sxs-lookup"><span data-stu-id="d478d-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="d478d-147">Csatlakoztassa a HoloLenst a számítógépéhez EGY USB-A–USB-C kábellel.</span><span class="sxs-lookup"><span data-stu-id="d478d-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="d478d-148">(Ez akkor is működik a legjobban, ha más kábelekkel csatlakoztatta a HoloLenst.)</span><span class="sxs-lookup"><span data-stu-id="d478d-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="d478d-149">Az Advanced Recovery Companion automatikusan észleli a HoloLenst.</span><span class="sxs-lookup"><span data-stu-id="d478d-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="d478d-150">Válassza a **Microsoft HoloLens** csempét.</span><span class="sxs-lookup"><span data-stu-id="d478d-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="d478d-151">A következő képernyőn válassza a **Manuális** csomagválasztás lehetőséget, majd válassza ki a telepítési fájlt, amely a 4. lépésben kicsomagolt mappában található.</span><span class="sxs-lookup"><span data-stu-id="d478d-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="d478d-152">(Keress egy .ffu kiterjesztésű fájlt.)</span><span class="sxs-lookup"><span data-stu-id="d478d-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="d478d-153">Válassza **a Szoftver telepítése lehetőséget,** és kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="d478d-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="d478d-154">A korábbi verzióra való visszaút törli a személyes fájlokat és beállításokat.</span><span class="sxs-lookup"><span data-stu-id="d478d-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="d478d-155">Emellett ha meg szeretne maradni az aktuálisan telepített kiadásban, manuálisan is szüneteltetheti a [frissítéseket.](hololens-updates.md#pause-updates-via-device)</span><span class="sxs-lookup"><span data-stu-id="d478d-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="d478d-156">Ez időt ad a mérnöki csapatnak a probléma megoldására.</span><span class="sxs-lookup"><span data-stu-id="d478d-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="d478d-157">Windows Insider Program HoloLensen</span><span class="sxs-lookup"><span data-stu-id="d478d-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="d478d-158">Szeretné látni a HoloLens legújabb funkcióit?</span><span class="sxs-lookup"><span data-stu-id="d478d-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="d478d-159">Ha igen, csatlakozzon a Windows Insider Program; Hozzáférést kap a HoloLens-szoftverfrissítések előzetes buildjéhez, mielőtt azok nyilvánosan elérhetővé tenék őket.</span><span class="sxs-lookup"><span data-stu-id="d478d-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="d478d-160">[A Windows Insider előzetes verzió Microsoft HoloLens.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="d478d-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
