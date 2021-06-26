---
title: A HoloLens 1 újraindítása, alaphelyzetbe állítása vagy helyreállítása
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Hogyan használható a Windows Eszköz-helyreállítási eszköz egy kép a HoloLens 1st Gen-ben való flash eleméhez.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, Windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 5963be84a5fbb186c77965d9bbf112713fea8242
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923516"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="cc139-104">A HoloLens újraindítása, alaphelyzetbe állítása vagy helyreállítása (1. generációs)</span><span class="sxs-lookup"><span data-stu-id="cc139-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="cc139-105">Ha problémákat tapasztal a HoloLens-sel kapcsolatban, megpróbálhatja újraindítani vagy alaphelyzetbe állítani az eszközt, vagy akár újra is perelheti az eszközt az eszköz helyreállításával.</span><span class="sxs-lookup"><span data-stu-id="cc139-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="cc139-106">Ez a cikk végigvezeti a javasolt helyreállítási lépések sorrendjén.</span><span class="sxs-lookup"><span data-stu-id="cc139-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="cc139-107">Ha helyre kell állítania egy HoloLens 2-t, tekintse meg [a HoloLens 2](hololens-recovery.md)helyreállítását, mivel ez a folyamat eltér.</span><span class="sxs-lookup"><span data-stu-id="cc139-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="cc139-108">Ez a cikk a HoloLens-eszközre és -szoftverre összpontosít.</span><span class="sxs-lookup"><span data-stu-id="cc139-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="cc139-109">Ha a hologramok nem jól néznek ki, a **[HoloLens-környezet](hololens-environment-considerations.md)** szempontjait és a hologramminőséget javítására irányuló tényezőkkel kapcsolatos információkért tekintse meg.</span><span class="sxs-lookup"><span data-stu-id="cc139-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="cc139-110">Újraindítás</span><span class="sxs-lookup"><span data-stu-id="cc139-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="cc139-111">Biztonságos újraindítás Cortana használatával</span><span class="sxs-lookup"><span data-stu-id="cc139-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="cc139-112">A HoloLens újraindításának legbiztonságosabb módja a Cortana használata, amely általában az első lépés, amikor problémát tapasztal a HoloLensben.</span><span class="sxs-lookup"><span data-stu-id="cc139-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="cc139-113">A Cortana nem minden eszközön érhető el.</span><span class="sxs-lookup"><span data-stu-id="cc139-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="cc139-114">Cortana minden HoloLens- (1. generációs) eszközön elérhető.</span><span class="sxs-lookup"><span data-stu-id="cc139-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="cc139-115">Cortana a Windows Holograpic 2004-es verziójának frissítése előtti builden érhető el a HoloLens 2-eszközökön.</span><span class="sxs-lookup"><span data-stu-id="cc139-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="cc139-116">Kapcsolja be a HoloLenst.</span><span class="sxs-lookup"><span data-stu-id="cc139-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="cc139-117">Győződjön meg arról, hogy a felhasználó be van jelentkezve, és az eszköz nem vár jelszóra a zárolás feloldásához.</span><span class="sxs-lookup"><span data-stu-id="cc139-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="cc139-118">Mondja ki a "Hey Cortana, restart" vagy a "Hey Cortana, restart" (Cortana, újraindítás) parancsot.</span><span class="sxs-lookup"><span data-stu-id="cc139-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="cc139-119">Cortana válaszolni fog, és megerősítést kér.</span><span class="sxs-lookup"><span data-stu-id="cc139-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="cc139-120">Várjon, amíg egy hang lejátszásra vár a kérdés után, majd mondja ki az "Igen" választ.</span><span class="sxs-lookup"><span data-stu-id="cc139-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="cc139-121">Az eszköz újraindul.</span><span class="sxs-lookup"><span data-stu-id="cc139-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="cc139-122">Biztonságos újraindítás a bekapcsoló gombbal</span><span class="sxs-lookup"><span data-stu-id="cc139-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="cc139-123">Ha továbbra sem tudja újraindítani az eszközt, próbálja meg újraindítani a **bekapcsológombbal:**</span><span class="sxs-lookup"><span data-stu-id="cc139-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="cc139-124">Nyomja le és tartsa lenyomva a **bekapcsológombot** 5 másodpercig.</span><span class="sxs-lookup"><span data-stu-id="cc139-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="cc139-125">1 másodperc múlva mind az öt LED-et el fogja látni, majd lassan kikapcsolja őket 1-ről 1-re jobbról balra.</span><span class="sxs-lookup"><span data-stu-id="cc139-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="cc139-126">5 másodperc elteltével az összes LED ki lesz kapcsolva, ami a sikeres leállítást jelzi.</span><span class="sxs-lookup"><span data-stu-id="cc139-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="cc139-127">Ne nyomja le azonnal a gombot, miután az összes LED ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="cc139-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="cc139-128">Várjon 1 percet, amíg a leállítás befejeződik.</span><span class="sxs-lookup"><span data-stu-id="cc139-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="cc139-129">Előfordulhat, hogy a leállítás még a kijelzők kikapcsolása után is folyamatban van.</span><span class="sxs-lookup"><span data-stu-id="cc139-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="cc139-130">Kapcsolja be újra az eszközt  úgy, hogy 1 gombra lenyomva tartja a bekapcsológombot.</span><span class="sxs-lookup"><span data-stu-id="cc139-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="cc139-131">Biztonságos újraindítás a Windows eszközportál</span><span class="sxs-lookup"><span data-stu-id="cc139-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="cc139-132">Ehhez a folyamathoz a HoloLenst fejlesztői eszközként kell konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="cc139-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="cc139-133">További információ: [Windows eszközportál.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="cc139-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="cc139-134">Ha az előző eljárás nem működött, próbálja meg újraindítani az eszközt a [Windows eszközportál.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="cc139-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="cc139-135">A jobb felső sarokban keresse meg az eszköz újraindítási vagy leállítható beállítását.</span><span class="sxs-lookup"><span data-stu-id="cc139-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="cc139-136">Nem biztonságos kényszerített újraindítás</span><span class="sxs-lookup"><span data-stu-id="cc139-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="cc139-137">Ha az előző metódusok nem újraindítják a HoloLenst, kényszerítsen újraindítást.</span><span class="sxs-lookup"><span data-stu-id="cc139-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="cc139-138">Ez a módszer egyenértékű az akkumulátor eltávolításával és újratelepítésével.</span><span class="sxs-lookup"><span data-stu-id="cc139-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="cc139-139">Ez azért veszélyes, mert az eszközt sérült állapotban hagyhatja.</span><span class="sxs-lookup"><span data-stu-id="cc139-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="cc139-140">Ha ez történik, akkor a HoloLenst is fel kell flashmenten.</span><span class="sxs-lookup"><span data-stu-id="cc139-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="cc139-141">Ez egy potenciálisan káros metódus, és csak akkor szabad használni, ha a korábban hivatkozott metódusok nem működtek.</span><span class="sxs-lookup"><span data-stu-id="cc139-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="cc139-142">Tartsa lenyomva a **bekapcsológombot** legalább 10 másodpercig.</span><span class="sxs-lookup"><span data-stu-id="cc139-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="cc139-143">A gomb 10 másodpercnél hosszabb ideig is tartható.</span><span class="sxs-lookup"><span data-stu-id="cc139-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="cc139-144">A LED-tevékenységeket biztonságosan figyelmen kívül hagyhatja.</span><span class="sxs-lookup"><span data-stu-id="cc139-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="cc139-145">Engedje el a gombot, és várjon 2–3 másodpercet.</span><span class="sxs-lookup"><span data-stu-id="cc139-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="cc139-146">Nyomja le és tartsa lenyomva a **bekapcsológombot** 1 gombra.</span><span class="sxs-lookup"><span data-stu-id="cc139-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="cc139-147">Ha továbbra is problémákat  tapasztal, nyomja meg a bekapcsológombot 4 másodpercig, amíg el nem halványulnak az akkumulátor kijelzői, és a képernyő nem jelenít meg hologramokat.</span><span class="sxs-lookup"><span data-stu-id="cc139-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="cc139-148">Várjon 1 percet, majd nyomja meg ismét a **bekapcsológombot** az eszköz bekapcsoláshoz.</span><span class="sxs-lookup"><span data-stu-id="cc139-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="cc139-149">Vissza verzióra való áttűnés – HoloLens (1. generáció)</span><span class="sxs-lookup"><span data-stu-id="cc139-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="cc139-150">Bizonyos esetekben érdemes lehet visszatérni a HoloLens szoftver egy korábbi verziójára.</span><span class="sxs-lookup"><span data-stu-id="cc139-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="cc139-151">Ehhez a Windows Device Recovery eszközzel visszaállíthatja a HoloLenst a korábbi verzióra.</span><span class="sxs-lookup"><span data-stu-id="cc139-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="cc139-152">A korábbi verzióra való visszaút törli a személyes fájlokat és beállításokat.</span><span class="sxs-lookup"><span data-stu-id="cc139-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="cc139-153">A HoloLens 1 korábbi verziójára való visszaúthoz kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="cc139-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="cc139-154">Győződjön meg arról, hogy nincs csatlakoztatva telefon vagy Windows-eszköz a számítógéphez.</span><span class="sxs-lookup"><span data-stu-id="cc139-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="cc139-155">A számítógépen töltse le a [Windows Device Recovery Tool (WDRT) eszközt.](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="cc139-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="cc139-156">Töltse le a [HoloLens évfordulós frissítés helyreállítási csomagját.](https://aka.ms/hololensrecovery)</span><span class="sxs-lookup"><span data-stu-id="cc139-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="cc139-157">Ha a letöltések befejeződnek, nyissa meg a **Fájlkezelő**  >  **Letöltések gombra.**</span><span class="sxs-lookup"><span data-stu-id="cc139-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="cc139-158">Kattintson a jobb gombbal az előbb letöltött tömörített mappára, és válassza az Extract all Extract **(Összes** kibontás) lehetőséget a  >   kicsomagoláshoz.</span><span class="sxs-lookup"><span data-stu-id="cc139-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="cc139-159">Csatlakoztassa a HoloLenst a számítógépéhez a vele együtt használt mikro-USB-kábellel.</span><span class="sxs-lookup"><span data-stu-id="cc139-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="cc139-160">(Ez akkor is működik a legjobban, ha más kábelekkel csatlakoztatta a HoloLenst.)</span><span class="sxs-lookup"><span data-stu-id="cc139-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="cc139-161">A WDRT automatikusan észleli a HoloLenst.</span><span class="sxs-lookup"><span data-stu-id="cc139-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="cc139-162">Válassza a **Microsoft HoloLens** csempét.</span><span class="sxs-lookup"><span data-stu-id="cc139-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="cc139-163">A következő képernyőn válassza a **Manuális** csomagválasztás lehetőséget, és válassza ki a 4. lépésben kicsomagolt mappában található telepítőfájlt.</span><span class="sxs-lookup"><span data-stu-id="cc139-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="cc139-164">(Keress egy .ffu kiterjesztésű fájlt.)</span><span class="sxs-lookup"><span data-stu-id="cc139-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="cc139-165">Válassza **a Szoftver telepítése lehetőséget,** és kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="cc139-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="cc139-166">Ha a WDRT nem észleli a HoloLenst, próbálja meg újraindítani a számítógépet.</span><span class="sxs-lookup"><span data-stu-id="cc139-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="cc139-167">Ha ez nem működik, jelölje be a **Saját eszköz nem** észlelhető lehetőséget, válassza a Microsoft HoloLens lehetőséget, majd kövesse az utasításokat. </span><span class="sxs-lookup"><span data-stu-id="cc139-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="cc139-168">Visszaállítás a gyári beállításokra</span><span class="sxs-lookup"><span data-stu-id="cc139-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="cc139-169">Az akkumulátor alaphelyzetbe állításhoz legalább 40%-os töltöttség szükséges.</span><span class="sxs-lookup"><span data-stu-id="cc139-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="cc139-170">Ha a HoloLensben továbbra is probléma van, próbálja meg visszaállítani a gyári állapotra.</span><span class="sxs-lookup"><span data-stu-id="cc139-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="cc139-171">Ez a lépés megtartja a rajta telepített Windows Holographic szoftver verzióját, és minden mást visszaad a gyári beállításoknak.</span><span class="sxs-lookup"><span data-stu-id="cc139-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="cc139-172">Ha alaphelyzetbe állítja az eszközt, az összes személyes adata, alkalmazása és beállítása törlődik, beleértve a TPM alaphelyzetbe állítási adatait is.</span><span class="sxs-lookup"><span data-stu-id="cc139-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="cc139-173">Az alaphelyzetbe állítás csak a Windows Holographic legújabb telepített verzióját telepíti.</span><span class="sxs-lookup"><span data-stu-id="cc139-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="cc139-174">Minden inicializálási lépést újra végre kell majd hoznia (be kell állítania, csatlakoznia kell a Wi-Fi-hez, létre kell hoznia egy felhasználói fiókot, le kell töltenie az alkalmazásokat stb.).</span><span class="sxs-lookup"><span data-stu-id="cc139-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="cc139-175">Nyissa meg a Beállítások alkalmazást, majd válassza az **Update**  >  **Recovery lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="cc139-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="cc139-176">Válassza az **Eszköz alaphelyzetbe állítása** lehetőséget, és olvassa el a megerősítő üzenetet.</span><span class="sxs-lookup"><span data-stu-id="cc139-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="cc139-177">Erősítse meg az alaphelyzetbe állítást.</span><span class="sxs-lookup"><span data-stu-id="cc139-177">Confirm the reset.</span></span> <span data-ttu-id="cc139-178">Az eszköz újraindul, és megjeleníti a forgó fogaskerékkészletet és a folyamatjelző sávot.</span><span class="sxs-lookup"><span data-stu-id="cc139-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="cc139-179">Várjon körülbelül 30 percet, amíg a folyamat befejeződik.</span><span class="sxs-lookup"><span data-stu-id="cc139-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="cc139-180">Amikor végzett, az eszköz újraindul a "kész" felhasználói élményben.</span><span class="sxs-lookup"><span data-stu-id="cc139-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="cc139-181">Az operációs rendszer újratelepítése</span><span class="sxs-lookup"><span data-stu-id="cc139-181">Reinstall the operating system</span></span>

<span data-ttu-id="cc139-182">Ha az eszköz újraindítása és alaphelyzetbe állítása után is probléma lép fel, egy helyreállítási eszközzel újratelepítheti a HoloLens operációs rendszert és a belső vezérlőprogramot.</span><span class="sxs-lookup"><span data-stu-id="cc139-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="cc139-183">A HoloLensnek az alaphelyzetbe állításhoz szükséges adatai egy teljes flash frissítésbe (FFU) vannak csomagolva, amely egy .iso-, .wim- vagy .vhd-fájlhoz hasonlít.</span><span class="sxs-lookup"><span data-stu-id="cc139-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="cc139-184">Tudnivalók az FFU képfájlformátumokról.</span><span class="sxs-lookup"><span data-stu-id="cc139-184">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="cc139-185">A Windows Eszköz-helyreállítási eszközzel új operációs rendszert telepíthet a HoloLens (1. generációs) eszközére.</span><span class="sxs-lookup"><span data-stu-id="cc139-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="cc139-186">Az eszköz használata előtt nézze meg, hogy a HoloLens újraindítása vagy alaphelyzetbe állítása megoldja-e a problémát.</span><span class="sxs-lookup"><span data-stu-id="cc139-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="cc139-187">A helyreállítási folyamat több ideig is eltért.</span><span class="sxs-lookup"><span data-stu-id="cc139-187">The recovery process may take a while.</span></span> <span data-ttu-id="cc139-188">Ha ez megtörtént, a Windows Holographic szoftver legújabb verziója lesz telepítve.</span><span class="sxs-lookup"><span data-stu-id="cc139-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="cc139-189">Az eszköz csak akkor használható, ha Windows 10 vagy újabb, legalább 4 GB szabad tárhellyel.</span><span class="sxs-lookup"><span data-stu-id="cc139-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="cc139-190">Ez az eszköz nem futtatható virtuális gépen.</span><span class="sxs-lookup"><span data-stu-id="cc139-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="cc139-191">A HoloLens helyreállítása</span><span class="sxs-lookup"><span data-stu-id="cc139-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="cc139-192">Töltse le és telepítse a [Windows Eszköz-helyreállítási eszközt](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) a számítógépre.</span><span class="sxs-lookup"><span data-stu-id="cc139-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="cc139-193">Csatlakoztassa a HoloLenst (1st gen) a számítógéphez a HoloLenshez csatlakoztatott Micro USB-kábellel.</span><span class="sxs-lookup"><span data-stu-id="cc139-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="cc139-194">Nyissa meg a Windows Eszköz-helyreállítási eszközt, és kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="cc139-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="cc139-195">Ha a HoloLens (1. generációs) nem észlelhető automatikusan, válassza a **Saját eszköz nem észlelhető lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="cc139-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="cc139-196">Ezután kövesse az utasításokat az eszköz helyreállítási módba való beállításhoz.</span><span class="sxs-lookup"><span data-stu-id="cc139-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="cc139-197">Manuális flash mód</span><span class="sxs-lookup"><span data-stu-id="cc139-197">Manual flashing mode</span></span>

<span data-ttu-id="cc139-198">Ha a rendszer nem észleli az eszközt, kövesse az alábbi lépéseket a flash (flash) módba való beállításhoz:</span><span class="sxs-lookup"><span data-stu-id="cc139-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="cc139-199">Válassza le az eszközt bármely áramforrásról.</span><span class="sxs-lookup"><span data-stu-id="cc139-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="cc139-200">Ha az eszköz be van kapcsolva, tartsa lenyomva a **bekapcsológombot,** amíg teljesen ki nem vált.</span><span class="sxs-lookup"><span data-stu-id="cc139-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="cc139-201">Tartsa lenyomva **a kötetet fel** gomb, és koppintson röviden a **bekapcsoló gombra.**</span><span class="sxs-lookup"><span data-stu-id="cc139-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="cc139-202">Az eszköznek csak a középső LED-et szabad elindulni és megjelenítenie.</span><span class="sxs-lookup"><span data-stu-id="cc139-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="cc139-203">Csatlakoztassa az eszközt a számítógéphez.</span><span class="sxs-lookup"><span data-stu-id="cc139-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="cc139-204">Nyissa meg a Windows Eszköz-helyreállítási eszközt.</span><span class="sxs-lookup"><span data-stu-id="cc139-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="cc139-205">Válassza **a Nem észlelhető az eszközöm lehetőséget,** majd a **HoloLens lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="cc139-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="cc139-206">Az eszköz helyreállításához kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="cc139-206">Follow the instructions to recover your device.</span></span>
