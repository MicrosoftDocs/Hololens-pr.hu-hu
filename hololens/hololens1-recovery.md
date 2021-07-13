---
title: Újraindítás, alaphelyzetbe állítás vagy helyreállítás HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: A Windows Eszköz-helyreállítási eszköz használata egy kép flash-HoloLens az 1. generációs rendszerképhez.
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
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635228"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="bf7d0-104">Újraindítás, alaphelyzetbe állítás vagy helyreállítás HoloLens (1. generációs)</span><span class="sxs-lookup"><span data-stu-id="bf7d0-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="bf7d0-105">Ha problémákat tapasztal a HoloLens, megpróbálhatja újraindítani vagy alaphelyzetbe állítani az eszközt, vagy akár újra is perjeleket állíthat be az eszköz helyreállításával.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="bf7d0-106">Ez a cikk végigvezeti a javasolt helyreállítási lépések sorrendjén.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="bf7d0-107">Ha a 2. HoloLens helyre kell állítania, tekintse meg [a 2.](hololens-recovery.md)HoloLens a folyamat eltérését.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="bf7d0-108">Ez a cikk a HoloLens eszközre és szoftverre összpontosít.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="bf7d0-109">Ha a hologramok nem megfelelőek, tekintse meg a HoloLens környezeti szempontokat a hologramminőséget javítására irányuló tényezőkkel kapcsolatos információkért. **[](hololens-environment-considerations.md)**</span><span class="sxs-lookup"><span data-stu-id="bf7d0-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="bf7d0-110">Újraindítás</span><span class="sxs-lookup"><span data-stu-id="bf7d0-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="bf7d0-111">Biztonságos újraindítás a Cortana</span><span class="sxs-lookup"><span data-stu-id="bf7d0-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="bf7d0-112">A HoloLens újraindításának legbiztonságosabb módja az Cortana használata, amely általában az első lépés, amikor problémát tapasztal a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="bf7d0-113">Cortana nem minden eszközön érhető el.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="bf7d0-114">Cortana az összes HoloLens (1. generációs) eszközön elérhető.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="bf7d0-115">Cortana a HoloLens Holograpic 2004-es verziójának frissítése előtt Windows 2 builden érhető el.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="bf7d0-116">Kapcsolja be a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="bf7d0-117">Győződjön meg arról, hogy a felhasználó be van jelentkezve, és az eszköz nem vár jelszóra a zárolás feloldásához.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="bf7d0-118">Mondja ki a "Hey Cortana, restart" vagy a "Hey Cortana, restart" szót.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="bf7d0-119">Cortana válaszol, és megerősítést kér.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="bf7d0-120">Várjon, amíg egy hang lejátszásra vár a kérdés után, majd mondja ki az "Igen" választ.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="bf7d0-121">Az eszköz újraindul.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="bf7d0-122">Biztonságos újraindítás a bekapcsoló gombbal</span><span class="sxs-lookup"><span data-stu-id="bf7d0-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="bf7d0-123">Ha továbbra sem tudja újraindítani az eszközt, próbálja meg újraindítani a **bekapcsológombbal:**</span><span class="sxs-lookup"><span data-stu-id="bf7d0-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="bf7d0-124">Nyomja le és tartsa lenyomva a **bekapcsológombot** 5 másodpercig.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="bf7d0-125">1 másodperc múlva mind az öt LED-et kikapcsolja, majd fokozatosan kikapcsolja őket jobbról balra.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="bf7d0-126">5 másodperc elteltével az összes LED ki lesz kapcsolva, ami a sikeres leállítást jelzi.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="bf7d0-127">Ne nyomja le azonnal a gombot, miután az összes LED ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="bf7d0-128">Várjon 1 percet, amíg a leállítás befejeződik.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="bf7d0-129">Előfordulhat, hogy a leállítás még a kijelzők kikapcsolása után is folyamatban van.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="bf7d0-130">Kapcsolja be újra az eszközt  úgy, hogy 1 gombra lenyomva tartja a bekapcsológombot.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="bf7d0-131">Biztonságos újraindítás a Windows Eszközportál</span><span class="sxs-lookup"><span data-stu-id="bf7d0-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="bf7d0-132">Ehhez a folyamathoz HoloLens eszközként kell konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="bf7d0-133">További információ: [Windows Eszközportál.](/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="bf7d0-133">Learn more at [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="bf7d0-134">Ha az előző eljárás nem működött, próbálja meg újraindítani az eszközt a [következő Windows Eszközportál.](/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="bf7d0-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="bf7d0-135">A jobb felső sarokban keresse meg az eszköz újraindítási vagy leállítható beállítását.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="bf7d0-136">Nem biztonságos kényszerített újraindítás</span><span class="sxs-lookup"><span data-stu-id="bf7d0-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="bf7d0-137">Ha az előző metódusok nem indítani a HoloLens, kényszerítsen újraindítást.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="bf7d0-138">Ez a módszer egyenértékű az akkumulátor eltávolításával és újratelepítésével.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="bf7d0-139">Ez azért veszélyes, mert az eszközt sérült állapotban hagyhatja.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="bf7d0-140">Ha ez történik, akkor flash-et kell HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="bf7d0-141">Ez egy potenciálisan káros metódus, és csak akkor szabad használni, ha a korábban hivatkozott metódusok nem működtek.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="bf7d0-142">Tartsa lenyomva a **bekapcsológombot** legalább 10 másodpercig.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="bf7d0-143">A gomb 10 másodpercnél hosszabb ideig is tartható.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="bf7d0-144">A LED-tevékenységeket biztonságosan figyelmen kívül hagyhatja.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="bf7d0-145">Engedje el a gombot, és várjon 2–3 másodpercet.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="bf7d0-146">Nyomja le és tartsa lenyomva a **bekapcsológombot** 1 gombra.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="bf7d0-147">Ha továbbra is problémákat  tapasztal, nyomja meg a bekapcsológombot 4 másodpercig, amíg el nem halványulnak az akkumulátor kijelzői, és a képernyő nem jelenít meg hologramokat.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="bf7d0-148">Várjon 1 percet, majd nyomja meg ismét a **bekapcsológombot** az eszköz bekapcsoláshoz.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="bf7d0-149">Vissza verzióra való áttűnés – HoloLens (1. generáció)</span><span class="sxs-lookup"><span data-stu-id="bf7d0-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="bf7d0-150">Bizonyos esetekben érdemes lehet a szoftver korábbi verziójára HoloLens vissza.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="bf7d0-151">Ezt a Windows Eszköz-helyreállítási eszközzel állíthatja vissza HoloLens korábbi verzióra.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="bf7d0-152">A korábbi verzióra való visszaút törli a személyes fájlokat és beállításokat.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="bf7d0-153">Az 1. verzió korábbi HoloLens kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="bf7d0-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="bf7d0-154">Győződjön meg arról, hogy nincs telefonja vagy Windows számítógéphez csatlakoztatva.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="bf7d0-155">A számítógépen töltse le a [Windows Device Recovery Tool (WDRT) eszközt.](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="bf7d0-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="bf7d0-156">Töltse le [a HoloLens évfordulós frissítés helyreállítási csomagját.](https://aka.ms/hololensrecovery)</span><span class="sxs-lookup"><span data-stu-id="bf7d0-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="bf7d0-157">Ha a letöltések befejeződnek, nyissa meg a **Fájlkezelő**  >  **Letöltések gombra.**</span><span class="sxs-lookup"><span data-stu-id="bf7d0-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="bf7d0-158">Kattintson a jobb gombbal az előbb letöltött tömörített mappára, és válassza az Extract all Extract **(Összes** kibontás) lehetőséget a  >   kicsomagoláshoz.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="bf7d0-159">Csatlakozás a HoloLens a számítógépére a hozzá csatlakoztatott mikro-USB-kábellel.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="bf7d0-160">(Ez akkor is a legjobban működik, ha más kábelekkel csatlakoztatta HoloLens-t.)</span><span class="sxs-lookup"><span data-stu-id="bf7d0-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="bf7d0-161">A WDRT automatikusan észleli a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="bf7d0-162">Válassza a **Microsoft HoloLens** csempét.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="bf7d0-163">A következő képernyőn válassza a **Manuális** csomagválasztás lehetőséget, és válassza ki a 4. lépésben kicsomagolt mappában található telepítőfájlt.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="bf7d0-164">(Keress egy .ffu kiterjesztésű fájlt.)</span><span class="sxs-lookup"><span data-stu-id="bf7d0-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="bf7d0-165">Válassza **a Szoftver telepítése lehetőséget,** és kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="bf7d0-166">Ha a WDRT nem észleli a HoloLens, indítsa újra a számítógépet.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="bf7d0-167">Ha ez nem működik, jelölje be a Saját **eszköz nem** észlelhető lehetőséget, válassza a Microsoft HoloLens **lehetőséget,** majd kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="bf7d0-168">Visszaállítás a gyári beállításokra</span><span class="sxs-lookup"><span data-stu-id="bf7d0-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="bf7d0-169">Az akkumulátor alaphelyzetbe állításhoz legalább 40%-os töltöttség szükséges.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="bf7d0-170">Ha a HoloLens továbbra is problémát jelent, próbálja meg gyári állapotba állítani.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="bf7d0-171">Ez a lépés megtartja a Windows telepített Holographic szoftver verzióját, és minden mást a gyári beállításokba ad vissza.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="bf7d0-172">Ha alaphelyzetbe állítja az eszközt, az összes személyes adata, alkalmazása és beállítása törlődik, beleértve a TPM alaphelyzetbe állítási adatait is.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="bf7d0-173">Az alaphelyzetbe állítás csak a holographic rendszer legújabb telepített Windows telepíti.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="bf7d0-174">Minden inicializálási lépést újra végre kell majd hoznia (be kell állítania, csatlakoznia kell a Wi-Fi-hez, létre kell hoznia egy felhasználói fiókot, le kell töltenie az alkalmazásokat stb.).</span><span class="sxs-lookup"><span data-stu-id="bf7d0-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="bf7d0-175">Nyissa meg a Gépház alkalmazást, majd válassza az **Update**  >  **Recovery lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="bf7d0-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="bf7d0-176">Válassza az **Eszköz alaphelyzetbe állítása** lehetőséget, és olvassa el a megerősítő üzenetet.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="bf7d0-177">Erősítse meg az alaphelyzetbe állítást.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-177">Confirm the reset.</span></span> <span data-ttu-id="bf7d0-178">Az eszköz újraindul, és megjeleníti a forgó fogaskerékkészletet és a folyamatjelző sávot.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="bf7d0-179">Várjon körülbelül 30 percet, amíg a folyamat befejeződik.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="bf7d0-180">Amikor végzett, az eszköz újraindul a "kész" felhasználói élményben.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="bf7d0-181">Az operációs rendszer újratelepítése</span><span class="sxs-lookup"><span data-stu-id="bf7d0-181">Reinstall the operating system</span></span>

<span data-ttu-id="bf7d0-182">Ha az eszköz újraindítása és alaphelyzetbe állítása után is probléma lép fel, egy helyreállítási eszközzel újratelepítheti a HoloLens operációs rendszert és a belső vezérlőprogramot.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="bf7d0-183">Az alaphelyzetbe állításhoz HoloLens adatok egy teljes flash frissítésbe (FFU) vannak csomagolva, amely egy .iso-, .wim- vagy .vhd-fájlhoz hasonlít.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="bf7d0-184">Tudnivalók az FFU képfájlformátumokról.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-184">Learn about FFU image file formats.</span></span>](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="bf7d0-185">Az új operációs rendszert a HoloLens (1. generációs) a Windows eszköz használatával telepítheti.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="bf7d0-186">Az eszköz használata előtt nézze meg, hogy a számítógép újraindítása vagy alaphelyzetbe állítása HoloLens megoldja a problémát.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="bf7d0-187">A helyreállítási folyamat több ideig is eltért.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-187">The recovery process may take a while.</span></span> <span data-ttu-id="bf7d0-188">Amikor végzett, a rendszer telepíti a Windows legújabb verzióját.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="bf7d0-189">Az eszköz csak akkor használható, ha legalább Windows 10 legalább 4 GB szabad tárhellyel rendelkező számítógépre van szükség.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="bf7d0-190">Ez az eszköz nem futtatható virtuális gépen.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="bf7d0-191">A HoloLens</span><span class="sxs-lookup"><span data-stu-id="bf7d0-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="bf7d0-192">Töltse le és telepítse [Windows Eszköz-helyreállítási eszközt](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) a számítógépre.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="bf7d0-193">Csatlakozás a HoloLens (1. generációs) csatlakoztatását a számítógéphez a számítógéphez csatlakoztatott Micro USB-kábellel HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="bf7d0-194">Nyissa meg Windows Eszköz-helyreállítási eszközt, és kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="bf7d0-195">Ha a HoloLens (1. generációs) nem észlelhető automatikusan, válassza a **Saját eszköz nem észlelhető lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="bf7d0-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="bf7d0-196">Ezután kövesse az utasításokat az eszköz helyreállítási módba való beállításhoz.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="bf7d0-197">Manuális flash mód</span><span class="sxs-lookup"><span data-stu-id="bf7d0-197">Manual flashing mode</span></span>

<span data-ttu-id="bf7d0-198">Ha a rendszer nem észleli az eszközt, kövesse az alábbi lépéseket a flash (flash) módba való beállításhoz:</span><span class="sxs-lookup"><span data-stu-id="bf7d0-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="bf7d0-199">Válassza le az eszközt bármely áramforrásról.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="bf7d0-200">Ha az eszköz be van kapcsolva, tartsa lenyomva a **bekapcsológombot,** amíg teljesen ki nem vált.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="bf7d0-201">Tartsa lenyomva **a hangerőt gombot,** és koppintson röviden a **bekapcsoló gombra.**</span><span class="sxs-lookup"><span data-stu-id="bf7d0-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="bf7d0-202">Az eszköznek el kell indulni, és csak a középső LED-et kell megjelenítenie.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="bf7d0-203">Csatlakoztassa az eszközt a számítógéphez.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="bf7d0-204">Nyissa meg Windows Eszköz-helyreállítási eszközt.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="bf7d0-205">Válassza **a Saját eszköz nem észlelhető lehetőséget,** majd válassza a **HoloLens.**</span><span class="sxs-lookup"><span data-stu-id="bf7d0-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="bf7d0-206">Az eszköz helyreállításához kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="bf7d0-206">Follow the instructions to recover your device.</span></span>
