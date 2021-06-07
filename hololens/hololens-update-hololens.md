---
title: A HoloLens frissítése
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378111"
---
# <a name="update-hololens"></a><span data-ttu-id="cbe60-104">A HoloLens frissítése</span><span class="sxs-lookup"><span data-stu-id="cbe60-104">Update HoloLens</span></span>

<span data-ttu-id="cbe60-105">A HoloLens Windows Update, mint más Windows 10 eszközök.</span><span class="sxs-lookup"><span data-stu-id="cbe60-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="cbe60-106">A HoloLens automatikusan letölti és telepíti a rendszerfrissítéseket, amikor csatlakoztatva vannak az áramellátáshoz és csatlakoznak az internethez, még készenléti állapotban is.</span><span class="sxs-lookup"><span data-stu-id="cbe60-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="cbe60-107">Ez a cikk a HoloLens-eszközöket a következő eszközökhöz fogja használni:</span><span class="sxs-lookup"><span data-stu-id="cbe60-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="cbe60-108">az operációs rendszer aktuális verziójának megtekintése (buildszám)</span><span class="sxs-lookup"><span data-stu-id="cbe60-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="cbe60-109">frissítések keresése</span><span class="sxs-lookup"><span data-stu-id="cbe60-109">checking for updates</span></span>
- <span data-ttu-id="cbe60-110">a HoloLens manuális frissítése</span><span class="sxs-lookup"><span data-stu-id="cbe60-110">manually updating HoloLens</span></span>
- <span data-ttu-id="cbe60-111">korábbi frissítésre való visszagördülés</span><span class="sxs-lookup"><span data-stu-id="cbe60-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="cbe60-112">Az operációs rendszer verziójának ellenőrzése (buildszám)</span><span class="sxs-lookup"><span data-stu-id="cbe60-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="cbe60-113">A rendszer verziószámát (buildszám) a Beállítások alkalmazás megnyitásával, majd a Rendszer a következőről **lehetőség** kiválasztásával  >  **ellenőrizheti:**.</span><span class="sxs-lookup"><span data-stu-id="cbe60-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="cbe60-114">Frissítések keresése és manuális frissítés</span><span class="sxs-lookup"><span data-stu-id="cbe60-114">Check for updates and manually update</span></span>

<span data-ttu-id="cbe60-115">A beállítások között bármikor ellenőrizheti a frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="cbe60-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="cbe60-116">Az elérhető frissítések és az új frissítések keresése:</span><span class="sxs-lookup"><span data-stu-id="cbe60-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="cbe60-117">Nyissa meg a **Gépházat**.</span><span class="sxs-lookup"><span data-stu-id="cbe60-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="cbe60-118">Lépjen az **Update & Security**  >  **Windows Update.**</span><span class="sxs-lookup"><span data-stu-id="cbe60-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="cbe60-119">Válassza a **Frissítések keresése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cbe60-119">Select **Check for updates**.</span></span>

<span data-ttu-id="cbe60-120">Ha van elérhető frissítés, az elkezdi letölteni az új verziót.</span><span class="sxs-lookup"><span data-stu-id="cbe60-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="cbe60-121">A letöltés befejezése után válassza az **Újraindítás most** gombot a telepítés aktiválásához.</span><span class="sxs-lookup"><span data-stu-id="cbe60-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="cbe60-122">Ha az eszköz 40% alatti, és nincs csatlakoztatva, az újraindítás nem indítja el a frissítés telepítését.</span><span class="sxs-lookup"><span data-stu-id="cbe60-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="cbe60-123">Amíg a HoloLens telepíti a frissítést, forgó fogaskerékeket és folyamatjelzőt jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="cbe60-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="cbe60-124">Ez idő alatt ne kapcsolja ki a HoloLenst.</span><span class="sxs-lookup"><span data-stu-id="cbe60-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="cbe60-125">A telepítés befejezése után a rendszer automatikusan újraindul.</span><span class="sxs-lookup"><span data-stu-id="cbe60-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="cbe60-126">A HoloLens egyszerre csak egy frissítést alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="cbe60-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="cbe60-127">Ha a HoloLens egynél több verzióval régebbi, előfordulhat, hogy többször is végig kell futnia a frissítési folyamaton, hogy teljesen naprakész legyen.</span><span class="sxs-lookup"><span data-stu-id="cbe60-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="cbe60-128">Vissza verzióra való áttűnés – HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="cbe60-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="cbe60-129">Bizonyos esetekben érdemes lehet visszatérni a HoloLens szoftver egy korábbi verziójára.</span><span class="sxs-lookup"><span data-stu-id="cbe60-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="cbe60-130">Ehhez az Advanced Recovery Companion használatával visszaállíthatja a HoloLenst a korábbi verzióra.</span><span class="sxs-lookup"><span data-stu-id="cbe60-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="cbe60-131">A korábbi verzióra való visszaút törli a személyes fájlokat és beállításokat.</span><span class="sxs-lookup"><span data-stu-id="cbe60-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="cbe60-132">A HoloLens 2 egy korábbi verziójára való visszaúthoz kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="cbe60-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="cbe60-133">Győződjön meg arról, hogy nincs csatlakoztatva telefon vagy Windows-eszköz a számítógéphez.</span><span class="sxs-lookup"><span data-stu-id="cbe60-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="cbe60-134">A számítógépen töltse le az [Advanced Recovery Companiont a](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="cbe60-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="cbe60-135">Töltse le [a legújabb HoloLens 2-kiadást.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="cbe60-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="cbe60-136">Ha végzett ezekkel a letöltésekkel, nyissa meg a **Fájlkezelő**  >  **Letöltések ját.**</span><span class="sxs-lookup"><span data-stu-id="cbe60-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="cbe60-137">Kattintson a jobb gombbal az előbb letöltött tömörített mappára, és válassza az Extract all Extract **(Összes** kibontás) lehetőséget a  >   kicsomagoláshoz.</span><span class="sxs-lookup"><span data-stu-id="cbe60-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="cbe60-138">Csatlakoztassa a HoloLenst a számítógépéhez EGY USB-A–USB-C kábellel.</span><span class="sxs-lookup"><span data-stu-id="cbe60-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="cbe60-139">(Ez akkor is működik a legjobban, ha más kábelekkel csatlakoztatta a HoloLenst.)</span><span class="sxs-lookup"><span data-stu-id="cbe60-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="cbe60-140">Az Advanced Recovery Companion automatikusan észleli a HoloLenst.</span><span class="sxs-lookup"><span data-stu-id="cbe60-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="cbe60-141">Válassza a **Microsoft HoloLens** csempét.</span><span class="sxs-lookup"><span data-stu-id="cbe60-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="cbe60-142">A következő képernyőn válassza a **Manuális** csomagválasztás lehetőséget, majd válassza ki a 4. lépésben kicsomagolt mappában található telepítőfájlt.</span><span class="sxs-lookup"><span data-stu-id="cbe60-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="cbe60-143">(Keress egy .ffu kiterjesztésű fájlt.)</span><span class="sxs-lookup"><span data-stu-id="cbe60-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="cbe60-144">Válassza **a Szoftver telepítése lehetőséget,** és kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="cbe60-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="cbe60-145">Vissza verzióra való áttűnés – HoloLens (1. generáció)</span><span class="sxs-lookup"><span data-stu-id="cbe60-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="cbe60-146">Bizonyos esetekben érdemes lehet visszatérni a HoloLens szoftver egy korábbi verziójára.</span><span class="sxs-lookup"><span data-stu-id="cbe60-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="cbe60-147">Ezt a Windows Eszköz-helyreállítási eszközzel használhatja a HoloLens korábbi verzióra való visszaállításához.</span><span class="sxs-lookup"><span data-stu-id="cbe60-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="cbe60-148">A korábbi verzióra való visszaút törli a személyes fájlokat és beállításokat.</span><span class="sxs-lookup"><span data-stu-id="cbe60-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="cbe60-149">A HoloLens 1 egy korábbi verziójára való visszaúthoz kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="cbe60-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="cbe60-150">Győződjön meg arról, hogy nincs csatlakoztatva telefon vagy Windows-eszköz a számítógéphez.</span><span class="sxs-lookup"><span data-stu-id="cbe60-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="cbe60-151">A számítógépen töltse le a [Windows Device Recovery Tool (WDRT) eszközt.](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="cbe60-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="cbe60-152">Töltse le a [HoloLens évfordulós frissítés helyreállítási csomagját.](https://aka.ms/hololensrecovery)</span><span class="sxs-lookup"><span data-stu-id="cbe60-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="cbe60-153">Ha a letöltések befejeződnek, nyissa meg a **Fájlkezelő**  >  **Letöltések gombra.**</span><span class="sxs-lookup"><span data-stu-id="cbe60-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="cbe60-154">Kattintson a jobb gombbal az előbb letöltött tömörített mappára, és válassza az Extract all Extract **(Összes** kibontás) lehetőséget a  >   kicsomagoláshoz.</span><span class="sxs-lookup"><span data-stu-id="cbe60-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="cbe60-155">Csatlakoztassa a HoloLenst a számítógépéhez a vele együtt használt mikro-USB-kábellel.</span><span class="sxs-lookup"><span data-stu-id="cbe60-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="cbe60-156">(Ez akkor is működik a legjobban, ha más kábelekkel csatlakoztatta a HoloLenst.)</span><span class="sxs-lookup"><span data-stu-id="cbe60-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="cbe60-157">A WDRT automatikusan észleli a HoloLenst.</span><span class="sxs-lookup"><span data-stu-id="cbe60-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="cbe60-158">Válassza a **Microsoft HoloLens** csempét.</span><span class="sxs-lookup"><span data-stu-id="cbe60-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="cbe60-159">A következő képernyőn válassza a **Manuális** csomagválasztás lehetőséget, és válassza ki a 4. lépésben kicsomagolt mappában található telepítőfájlt.</span><span class="sxs-lookup"><span data-stu-id="cbe60-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="cbe60-160">(Keress egy .ffu kiterjesztésű fájlt.)</span><span class="sxs-lookup"><span data-stu-id="cbe60-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="cbe60-161">Válassza **a Szoftver telepítése lehetőséget,** és kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="cbe60-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="cbe60-162">Ha a WDRT nem észleli a HoloLenst, próbálja meg újraindítani a számítógépet.</span><span class="sxs-lookup"><span data-stu-id="cbe60-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="cbe60-163">Ha ez nem működik, válassza a **Saját eszköz** nem észlelhető lehetőséget, válassza a Microsoft HoloLens **lehetőséget,** majd kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="cbe60-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="cbe60-164">Windows Insider Program HoloLensen</span><span class="sxs-lookup"><span data-stu-id="cbe60-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="cbe60-165">Szeretné látni a HoloLens legújabb funkcióit?</span><span class="sxs-lookup"><span data-stu-id="cbe60-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="cbe60-166">Ha igen, csatlakozzon a Windows Insider Program; Hozzáférést kap a HoloLens-szoftverfrissítések előzetes buildjéhez, mielőtt azok nyilvánosan elérhetővé tenék őket.</span><span class="sxs-lookup"><span data-stu-id="cbe60-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="cbe60-167">[A Windows Insider előzetes verzió Microsoft HoloLens.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="cbe60-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
