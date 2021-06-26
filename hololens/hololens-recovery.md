---
title: A HoloLens újraindítása, alaphelyzetbe állítása vagy helyreállítása
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: How to use Advanced Recovery Companion to flash an image to HoloLens 2 (Az Advanced Recovery Companion használata kép a HoloLens 2-ben való flashhez).
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: be33eb5d06ee7d63f1f598792ff75605b0eb4424
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923635"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="69833-104">A HoloLens 2 újraindítása, alaphelyzetbe állítása vagy helyreállítása</span><span class="sxs-lookup"><span data-stu-id="69833-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="69833-105">A hibaelhárítási eljárás elkezdése előtt győződjön meg arról, hogy az eszköz **20–40%-os** akkumulátor-kapacitással rendelkezik, ha lehetséges.</span><span class="sxs-lookup"><span data-stu-id="69833-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="69833-106">A [tápkapcsoló alatt](hololens2-setup.md#lights-that-indicate-the-battery-level) található akkumulátorjelző világítással gyorsan ellenőrizheti az akkumulátor kapacitását anélkül, hogy bejelentkezik az eszközre.</span><span class="sxs-lookup"><span data-stu-id="69833-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="69833-107">Használja a HoloLens 2-höz csatlakoztatott usb [type-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) kábelt, mivel ez a legjobb módszer az eszköz feltöltésére.</span><span class="sxs-lookup"><span data-stu-id="69833-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="69833-108">A akkumulátor 18W energiát ad (9V at 2A).</span><span class="sxs-lookup"><span data-stu-id="69833-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="69833-109">A mellékelt fali akkumulátor használatával a HoloLens 2-eszközök az akkumulátort kevesebb mint 65 perc alatt megtelik, amikor az eszköz készenléti állapotban van.</span><span class="sxs-lookup"><span data-stu-id="69833-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="69833-110">Ha ezek a kiegészítők nem érhetők el, győződjön meg arról, hogy a rendelkezésre álló tápegység legalább 15W energiát képes támogatni.</span><span class="sxs-lookup"><span data-stu-id="69833-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="69833-111">Ha lehetséges, kerülje a számítógép usb-kapcsolaton keresztüli feltöltését, ami lassú.</span><span class="sxs-lookup"><span data-stu-id="69833-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="69833-112">Ha az eszköz megfelelően elindult és fut, az akkumulátor töltöttségi szintjét háromféleképpen ellenőrizheti:</span><span class="sxs-lookup"><span data-stu-id="69833-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="69833-113">A HoloLens eszköz felhasználói felületének főmenüjéről.</span><span class="sxs-lookup"><span data-stu-id="69833-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="69833-114">Tekintse meg a LED-et a bekapcsológomb közelében (40%-os díjért legalább két folytonos LED-et kell látnia).</span><span class="sxs-lookup"><span data-stu-id="69833-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="69833-115">Ha az eszköz töltődik, az akkumulátor kijelzője felgyúsodik, és jelzi az aktuális töltöttségi szintet.</span><span class="sxs-lookup"><span data-stu-id="69833-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="69833-116">Az utolsó világítás elhalványul, és kihalványul, ami aktív díjszabást jelez.</span><span class="sxs-lookup"><span data-stu-id="69833-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="69833-117">Ha a HoloLens be van stb., az akkumulátor kijelzője öt lépéssel jeleníti meg az akkumulátor töltöttségi szintjét.</span><span class="sxs-lookup"><span data-stu-id="69833-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="69833-118">Ha az öt világítás közül csak az egyik van bekapcsolva, az akkumulátor töltöttségi szintje 20% alatt van.</span><span class="sxs-lookup"><span data-stu-id="69833-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="69833-119">Ha az akkumulátor töltöttségi szintje kritikusan alacsony, és megpróbálja bekapcsolni az eszközt, az egyik világítás rövid időre villog, majd kiússik.</span><span class="sxs-lookup"><span data-stu-id="69833-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="69833-120">A gazdagépen nyissa meg a **Fájlkezelő,** és keresse meg a HoloLens 2 eszközt a bal oldalon az Ez a **számítógép alatt.**</span><span class="sxs-lookup"><span data-stu-id="69833-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="69833-121">Kattintson a jobb gombbal az eszközre, majd válassza a **Tulajdonságok lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="69833-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="69833-122">Egy párbeszédpanelen megjelenik az akkumulátor töltöttségi szintje.</span><span class="sxs-lookup"><span data-stu-id="69833-122">A dialog box will show the battery charge level.</span></span>

   ![A HoloLens 2 tulajdonságokat bemutató képernyője az akkumulátor töltöttségi szintjét jeleníti meg](images/ResetRecovery2.png)

<span data-ttu-id="69833-124">Ha az eszköz nem indítható el az indítási menüben, jegyezze fel a LED megjelenését és az eszköz enumerálását a gazdagépen.</span><span class="sxs-lookup"><span data-stu-id="69833-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="69833-125">Ezután kövesse [a hibaelhárítási útmutatót.](hololens-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="69833-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="69833-126">Ha az eszköz állapota nem egyezik a hibaelhárítási útmutatóban felsorolt állapotokkal, hajtsa végre a merevlemez-visszaállítási eljárást úgy, hogy az eszköz a tápellátáshoz, nem pedig a gazdagéphez csatlakozik. [](hololens-recovery.md#hard-reset-procedure)</span><span class="sxs-lookup"><span data-stu-id="69833-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="69833-127">Várjon legalább egy órát, amíg az eszköz díjat számít fel.</span><span class="sxs-lookup"><span data-stu-id="69833-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="69833-128">Az eszköz alaphelyzetbe állítása</span><span class="sxs-lookup"><span data-stu-id="69833-128">Reset the device</span></span>

<span data-ttu-id="69833-129">Bizonyos körülmények között előfordulhat, hogy manuálisan kell alaphelyzetbe állítania az eszközt a szoftver felhasználói felületének használata nélkül.</span><span class="sxs-lookup"><span data-stu-id="69833-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="69833-130">Szabványos eljárás</span><span class="sxs-lookup"><span data-stu-id="69833-130">Standard procedure</span></span>

1. <span data-ttu-id="69833-131">A Type-C kábel leválasztása az eszköz tápellátásról vagy a gazdaszámítógépről való leválasztása érdekében.</span><span class="sxs-lookup"><span data-stu-id="69833-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="69833-132">Nyomja le és tartsa lenyomva a **bekapcsológombot** 15 másodpercig.</span><span class="sxs-lookup"><span data-stu-id="69833-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="69833-133">Minden LED-nek kikapcsolva kell lennie.</span><span class="sxs-lookup"><span data-stu-id="69833-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="69833-134">Várjon 2–3 másodpercet, majd nyomja le röviden a **bekapcsológombot.**</span><span class="sxs-lookup"><span data-stu-id="69833-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="69833-135">A bekapcsológombhoz közeli LED-ek kigyűjnek, és az eszköz elindul.</span><span class="sxs-lookup"><span data-stu-id="69833-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="69833-136">Csatlakoztassa az eszközt a gazdagéphez, majd nyissa meg Eszközkezelő.</span><span class="sxs-lookup"><span data-stu-id="69833-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="69833-137">(A Windows 10 nyomja le a **Windows** billentyűt, majd az **X** billentyűt, és válassza a **Eszközkezelő** lehetőséget.) Győződjön meg arról, hogy az eszköz helyesen számba veszi *Microsoft HoloLens* az alábbi képen látható módon:</span><span class="sxs-lookup"><span data-stu-id="69833-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery devive manager](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="69833-139">Visszaállítási eljárás</span><span class="sxs-lookup"><span data-stu-id="69833-139">Hard-reset procedure</span></span>

<span data-ttu-id="69833-140">Ha a normál alaphelyzetbe állítási eljárás nem működött, használja a visszaállítható visszaállítási eljárást:</span><span class="sxs-lookup"><span data-stu-id="69833-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="69833-141">A Type-C kábel leválasztása az eszköz tápellátásról vagy a gazdaszámítógépről való leválasztása érdekében.</span><span class="sxs-lookup"><span data-stu-id="69833-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="69833-142">Tartsa lenyomva a **hangerőt**  +   15 másodpercig.</span><span class="sxs-lookup"><span data-stu-id="69833-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="69833-143">Az eszköz automatikusan újraindul.</span><span class="sxs-lookup"><span data-stu-id="69833-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="69833-144">Csatlakoztassa az eszközt a gazdaszámítógéphez.</span><span class="sxs-lookup"><span data-stu-id="69833-144">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="69833-145">Nyissa Eszközkezelő a Windows 10 (a windowsos billentyűvel, majd az **X** billentyűvel, majd válassza a **Eszközkezelő)** lehetőséget. </span><span class="sxs-lookup"><span data-stu-id="69833-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="69833-146">Győződjön meg arról, hogy az eszköz helyesen számba veszi *Microsoft HoloLens* az alábbi képen látható módon:</span><span class="sxs-lookup"><span data-stu-id="69833-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery eszköz maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="69833-148">Az eszköz perjelének tisztítása</span><span class="sxs-lookup"><span data-stu-id="69833-148">Clean-reflash the device</span></span>

<span data-ttu-id="69833-149">Rendkívüli helyzetekben előfordulhat, hogy a HoloLens 2-t "tiszta flash"-re kell "felrakni".</span><span class="sxs-lookup"><span data-stu-id="69833-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="69833-150">Vegye figyelembe, hogy a perjeles perjel várhatóan nem érinti a következő problémákat:</span><span class="sxs-lookup"><span data-stu-id="69833-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="69833-151">Szín egységességének megjelenítése</span><span class="sxs-lookup"><span data-stu-id="69833-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="69833-152">Rendszerindítás hanggal, de nem jelenik meg a kimenet</span><span class="sxs-lookup"><span data-stu-id="69833-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="69833-153">1-3-5 LED minta</span><span class="sxs-lookup"><span data-stu-id="69833-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="69833-154">Túlmelegedés</span><span class="sxs-lookup"><span data-stu-id="69833-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="69833-155">Operációsrendszer-összeomlások (amelyek eltérnek az alkalmazás-összeomlástól)</span><span class="sxs-lookup"><span data-stu-id="69833-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="69833-156">Az eszközt két módon lehet újrafedni.</span><span class="sxs-lookup"><span data-stu-id="69833-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="69833-157">Mindkét esetben először telepítenie kell az [Advanced Recovery Companiont a Windows Áruházból.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="69833-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="69833-158">Ha újrafésedi az eszközt, az összes személyes adata, alkalmazása és beállítása törlődik, beleértve a TPM alaphelyzetbe állítási információit is.</span><span class="sxs-lookup"><span data-stu-id="69833-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="69833-159">Alapértelmezés szerint az Advanced Recovery Companion a legújabb funkció kiadási build [](hololens-release-notes.md#) letöltésére van beállítva. Itt elolvashatja a kibocsátási megjegyzéseket a legújabb funkció kiadásának megismerése érdekében.</span><span class="sxs-lookup"><span data-stu-id="69833-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="69833-160">Ha a legújabb HoloLens 2 Full Flash Update -csomagot (FFU) le kell töltenie az eszköz reflash eleméhez az Advanced Recovery Companion segítségével, kattintson ide a legújabb havi [HoloLens 2](https://aka.ms/hololens2download)rendszerkép letöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="69833-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="69833-161">Ez a verzió a legújabb általánosan elérhető build.</span><span class="sxs-lookup"><span data-stu-id="69833-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="69833-162">A perjeles eljárás előtt győződjön meg arról, hogy az alkalmazás telepítve van és fut a Windows 10 számítógépen, és készen áll az eszköz észlelésére.</span><span class="sxs-lookup"><span data-stu-id="69833-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="69833-163">Arról is győződjön meg, hogy a HoloLensért legalább 40%-os díjat kell fizetnie.</span><span class="sxs-lookup"><span data-stu-id="69833-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 – tiszta perjel képernyőfelvétel](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="69833-165">Normál eljárás</span><span class="sxs-lookup"><span data-stu-id="69833-165">Normal procedure</span></span>

1. <span data-ttu-id="69833-166">Amíg a HoloLens-eszköz fut, csatlakoztassa a Windows 10 számítógéphez, ahol korábban megnyitotta az Advanced Recovery-társalkalmazást.</span><span class="sxs-lookup"><span data-stu-id="69833-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="69833-167">A rendszer automatikusan észleli az eszközt, és a Speciális helyreállítást kísérő alkalmazás felhasználói felülete elindítja a frissítési folyamatot:</span><span class="sxs-lookup"><span data-stu-id="69833-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![A HoloLens 2 tiszta perjeles kezdőképernyője](images/ARC2.png)

3. <span data-ttu-id="69833-169">Válassza ki a HoloLens 2 eszközt az Advanced Recovery Companion alkalmazás felhasználói felületén, és kövesse az utasításokat a perjel befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="69833-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="69833-170">Manuális eljárás</span><span class="sxs-lookup"><span data-stu-id="69833-170">Manual procedure</span></span>

<span data-ttu-id="69833-171">Ha a HoloLens 2 nem indul el megfelelően, vagy ha az Advanced Recovery Companion nem tudja észlelni az eszközt, előfordulhat, hogy helyreállítási módba kell tennie az eszközt:</span><span class="sxs-lookup"><span data-stu-id="69833-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="69833-172">A Type-C kábel leválasztása az eszköz tápellátásról vagy a gazdaszámítógépről való leválasztása érdekében.</span><span class="sxs-lookup"><span data-stu-id="69833-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="69833-173">Nyomja le és tartsa lenyomva a **bekapcsológombot** 15 másodpercig.</span><span class="sxs-lookup"><span data-stu-id="69833-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="69833-174">Minden LED-nek ki kell kapcsolnia.</span><span class="sxs-lookup"><span data-stu-id="69833-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="69833-175">A hangerőszabályzó **gomb megnyomása** közben nyomja le és engedje el a **bekapcsológombot** az eszköz elindítani.</span><span class="sxs-lookup"><span data-stu-id="69833-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="69833-176">Várjon 15 másodpercet, majd engedje fel **a kötet fel gombját.**</span><span class="sxs-lookup"><span data-stu-id="69833-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="69833-177">Csak az öt LED középső LED-e lesz begyűjteve.</span><span class="sxs-lookup"><span data-stu-id="69833-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="69833-178">Csatlakoztassa az eszközt a gazdagéphez, és nyissa meg Eszközkezelő.</span><span class="sxs-lookup"><span data-stu-id="69833-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="69833-179">(A Windows 10 nyomja le a **Windows** billentyűt, majd az **X** billentyűt, majd válassza a Eszközkezelő **lehetőséget.)** Győződjön meg arról, hogy az eszköz helyesen számba veszi Microsoft HoloLens az alábbi képen látható módon:</span><span class="sxs-lookup"><span data-stu-id="69833-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="69833-181">A rendszer automatikusan észleli az eszközt, és a Speciális helyreállítást kísérő alkalmazás felhasználói felülete elindítja a frissítési folyamatot:</span><span class="sxs-lookup"><span data-stu-id="69833-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![A HoloLens 2 tiszta perjeles képernyője](images/ARC2.png)

6. <span data-ttu-id="69833-183">Válassza ki a HoloLens 2 eszközt az Advanced Recovery Companion alkalmazás felhasználói felületén, majd kövesse az utasításokat a perjel befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="69833-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="69833-184">Az Advanced Recovery Companion hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="69833-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="69833-185">Mielőtt megpróbálkozás a flash eszközzel, győződjön meg arról, hogy az eszköz 40%-os vagy annál nagyobb díjat számít fel.</span><span class="sxs-lookup"><span data-stu-id="69833-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="69833-186">Ellenőrizze, hogy az eszköz zárolása fel van-e oldva.</span><span class="sxs-lookup"><span data-stu-id="69833-186">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="69833-187">Ha az ARC nem észleli az eszközt, ellenőrizze, hogy tud-e csatlakozni az eszközhöz Fájlkezelő számítógépen található kapcsolaton keresztül.</span><span class="sxs-lookup"><span data-stu-id="69833-187">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="69833-188">Ha nem tudja;</span><span class="sxs-lookup"><span data-stu-id="69833-188">If you cannot;</span></span>

    1.  <span data-ttu-id="69833-189">Előfordulhat, hogy az eszközön USB-szabályzatok tiltják le ezt a kapcsolatot.</span><span class="sxs-lookup"><span data-stu-id="69833-189">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="69833-190">Ha igen, próbálja ki [a Manual Flashing mode (Manuális flash mód) módot.](hololens-recovery.md#manual-procedure)</span><span class="sxs-lookup"><span data-stu-id="69833-190">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="69833-191">Ha nincsenek házirendek, próbálkozzon egy másik USB-kábellel.</span><span class="sxs-lookup"><span data-stu-id="69833-191">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="69833-192">Ellenőrizze, hogy az eszköz nem [1-3-5 LED-es mintát jelenít-e meg.](hololens2-setup.md#lights-to-indicate-problems)</span><span class="sxs-lookup"><span data-stu-id="69833-192">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="69833-193">AZ ARC letöltése az alkalmazás-áruház használata nélkül</span><span class="sxs-lookup"><span data-stu-id="69833-193">Download ARC without using the app store</span></span>

<span data-ttu-id="69833-194">Ha az it-környezet megakadályozza a Windows Áruházbeli alkalmazás használatát, vagy korlátozza a kiskereskedelmi áruházhoz való hozzáférést, a rendszergazda "offline" telepítési útvonalon keresztül elérhetővé tudja tenni az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="69833-194">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="69833-195">A rendszergazdák az alkalmazást a System Center Konfigurációkezelő (SCCM) vagy az Intune használatával is terjesztheti.</span><span class="sxs-lookup"><span data-stu-id="69833-195">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="69833-196">Ez az útmutató az Advanced Recovery Companion funkcióval foglalkozik, de a folyamat más "offline" alkalmazásokhoz is használható.</span><span class="sxs-lookup"><span data-stu-id="69833-196">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="69833-197">Az üzembe helyezési útvonal engedélyezéséhez kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="69833-197">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="69833-198">A Microsoft Store Vállalatoknak [jelentkezzen](https://businessstore.microsoft.com) be egy Azure Active Directory identitással.</span><span class="sxs-lookup"><span data-stu-id="69833-198">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="69833-199">Kattintson a **Kezelés – Beállítások elemre.**</span><span class="sxs-lookup"><span data-stu-id="69833-199">Go to **Manage – Settings**.</span></span> <span data-ttu-id="69833-200">A Vásárlási **élmény alatt kapcsolja** be az Offline alkalmazások megjelenítése **et.**</span><span class="sxs-lookup"><span data-stu-id="69833-200">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="69833-201">Keresse fel **a csoportomért való vásárlást,** és keressen rá az [**_Advanced Recovery Companion kifejezésre._**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="69833-201">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="69833-202">Módosítsa a **Licenc típusa beállítását** **_offline _,_*majd válassza a _ Kezelés\* lehetőséget.*\*</span><span class="sxs-lookup"><span data-stu-id="69833-202">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="69833-203">A **Csomag letöltése offline használatra alatt válassza** a második kék Letöltés **gombot.**</span><span class="sxs-lookup"><span data-stu-id="69833-203">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="69833-204">Győződjön meg arról, hogy a *fájlkiterjesztés .appxbundle.*</span><span class="sxs-lookup"><span data-stu-id="69833-204">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="69833-205">Ha az asztali számítógép jelenleg rendelkezik internet-hozzáféréssel, kattintson duplán a csomagra az alkalmazás telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="69833-205">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="69833-206">Ha a célszámítógépen nincs internetkapcsolat, kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="69833-206">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="69833-207">Válassza ki a nem kódolatlan licencet, majd válassza a **Licenc létrehozása lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="69833-207">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="69833-208">A **Szükséges keretrendszerek alatt válassza** a Letöltés **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="69833-208">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="69833-209">A DISM használatával alkalmazza a csomagot a függőséggel és a licenccel.</span><span class="sxs-lookup"><span data-stu-id="69833-209">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="69833-210">Futtassa a következő parancsot egy rendszergazdai parancssorból:</span><span class="sxs-lookup"><span data-stu-id="69833-210">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="69833-211">Előfordulhat, hogy a jelen példakódban lévő verziószám nem egyezik a jelenleg elérhető verzióval.</span><span class="sxs-lookup"><span data-stu-id="69833-211">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="69833-212">Előfordulhat, hogy más letöltési helyet választott, mint a példában.</span><span class="sxs-lookup"><span data-stu-id="69833-212">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="69833-213">Szükség szerint módosítja a parancsot.</span><span class="sxs-lookup"><span data-stu-id="69833-213">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="69833-214">Ha az FFU offline telepítéséhez az Advanced Recovery Companiont tervezi használni, hasznos lehet a flash lemezkép letöltése.</span><span class="sxs-lookup"><span data-stu-id="69833-214">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="69833-215">[**Töltse le a HoloLens 2 aktuális rendszerképét.**](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="69833-215">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="69833-216">Egyéb erőforrások:</span><span class="sxs-lookup"><span data-stu-id="69833-216">Other resources:</span></span>
- [<span data-ttu-id="69833-217">Offline alkalmazások terjesztése</span><span class="sxs-lookup"><span data-stu-id="69833-217">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="69833-218">DISM alkalmazáscsomag (.appx vagy .appxbundle) – karbantartási parancssori beállítások</span><span class="sxs-lookup"><span data-stu-id="69833-218">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
