---
title: Újraindítás, alaphelyzetbe állítás vagy helyreállítás HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: How to use Advanced Recovery Companion to flash an image to HoloLens 2.
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
ms.openlocfilehash: 0124453ef9e3b21722acaf2c6b438ebdfbd65043
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635942"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="4b0a8-104">A 2. HoloLens újraindítása, visszaállítása vagy helyreállítása</span><span class="sxs-lookup"><span data-stu-id="4b0a8-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="4b0a8-105">A hibaelhárítási eljárás elkezdése előtt győződjön meg arról, hogy az eszköz **20–40** százalék akkumulátor-kapacitással rendelkezik, ha lehetséges.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="4b0a8-106">A [tápkapcsoló alatt](hololens2-setup.md#lights-that-indicate-the-battery-level) található akkumulátorjelző világítással gyorsan ellenőrizheti az akkumulátor kapacitását anélkül, hogy bejelentkezik az eszközre.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="4b0a8-107">Használja a 2. kábellel együtt HoloLens USB [Type-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) kábelt, mivel ez a legjobb módszer az eszköz feltöltésére.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="4b0a8-108">A tápellátás 18W energiát ad (9V 2A-n).</span><span class="sxs-lookup"><span data-stu-id="4b0a8-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="4b0a8-109">A mellékelt fali kábel használatával HoloLens 2 eszköz kevesebb mint 65 perc alatt megtelhet, amikor az eszköz készenléti állapotban van.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="4b0a8-110">Ha ezek a tápegységek nem érhetők el, győződjön meg arról, hogy az elérhető tápegység legalább 15W áramellátást tud támogatni.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="4b0a8-111">Ha lehetséges, ne használja a pc-t az eszköz USB-kapcsolaton keresztüli feltöltésére, ami lassú.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="4b0a8-112">Ha az eszköz megfelelően elindult és fut, háromféleképpen ellenőrizheti az akkumulátor töltöttségi szintjét:</span><span class="sxs-lookup"><span data-stu-id="4b0a8-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="4b0a8-113">Az eszköz felhasználói felületének főmenü HoloLens meg.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="4b0a8-114">Tekintse meg a LED-et a bekapcsológomb közelében (40%-os díjért legalább két SSD-t kell látnia).</span><span class="sxs-lookup"><span data-stu-id="4b0a8-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="4b0a8-115">Ha az eszköz töltődik, az akkumulátor kijelzője felgyúgyítással jelzi az aktuális töltöttségi szintet.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="4b0a8-116">Az utolsó világítás elhalványul és kihalványul, ami aktív díjszabást jelez.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="4b0a8-117">Ha a HoloLens be van stb., az akkumulátor kijelzője öt növekményben jeleníti meg az akkumulátor töltöttségi szintjét.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="4b0a8-118">Ha az öt világítás közül csak az egyik van bekapcsolva, az akkumulátor töltöttségi szintje 20% alatt van.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="4b0a8-119">Ha az akkumulátor töltöttségi szintje kritikusan alacsony, és megpróbálja bekapcsolni az eszközt, az egyik világítás rövid időre villog, majd kiússik.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="4b0a8-120">A gazdagépen nyissa meg a **Fájlkezelő,** és keresse meg a HoloLens 2-es eszközt a bal oldalon az Ez a **számítógép alatt.**</span><span class="sxs-lookup"><span data-stu-id="4b0a8-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="4b0a8-121">Kattintson a jobb gombbal az eszközre, majd válassza a **Tulajdonságok lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="4b0a8-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="4b0a8-122">Egy párbeszédpanelen megjelenik az akkumulátor töltöttségi szintje.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-122">A dialog box will show the battery charge level.</span></span>

   ![A HoloLens 2 tulajdonságot bemutató képernyő az akkumulátor töltöttségi szintjét jeleníti meg](images/ResetRecovery2.png)

<span data-ttu-id="4b0a8-124">Ha az eszköz nem indítható el az indítási menüben, jegyezze fel a LED megjelenését és az eszköz enumerálását a gazdagépen.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="4b0a8-125">Ezután kövesse a [hibaelhárítási útmutatót.](hololens-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="4b0a8-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="4b0a8-126">Ha az eszköz állapota nem egyezik a hibaelhárítási útmutatóban felsorolt állapotok egyikével sem, hajtsa végre a merevlemez-visszaállítási eljárást úgy, hogy az eszköz a tápegységhez, nem pedig a gazdagéphez csatlakozik. [](hololens-recovery.md#hard-reset-procedure)</span><span class="sxs-lookup"><span data-stu-id="4b0a8-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="4b0a8-127">Várjon legalább egy órát, amíg az eszköz díjat számít fel.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="4b0a8-128">Az eszköz alaphelyzetbe állítása</span><span class="sxs-lookup"><span data-stu-id="4b0a8-128">Reset the device</span></span>

<span data-ttu-id="4b0a8-129">Bizonyos körülmények között előfordulhat, hogy manuálisan kell alaphelyzetbe állítania az eszközt a szoftver felhasználói felületének használata nélkül.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="4b0a8-130">Szabványos eljárás</span><span class="sxs-lookup"><span data-stu-id="4b0a8-130">Standard procedure</span></span>

1. <span data-ttu-id="4b0a8-131">A Type-C kábel leválasztása az eszköz tápellátásról vagy a gazdaszámítógépről való leválasztása érdekében.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="4b0a8-132">Nyomja le és tartsa lenyomva a **bekapcsológombot** 15 másodpercig.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="4b0a8-133">Minden LED-nek kikapcsolva kell lennie.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="4b0a8-134">Várjon 2–3 másodpercet, majd nyomja le röviden a **bekapcsológombot.**</span><span class="sxs-lookup"><span data-stu-id="4b0a8-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="4b0a8-135">A bekapcsológombhoz közeli LED-ek kigyűjnek, és az eszköz elindul.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="4b0a8-136">Csatlakozás a gazdagépre, majd nyissa meg a Eszközkezelő.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="4b0a8-137">(A Windows 10 nyomja le az **Windows** billentyűt, majd az **X** billentyűt, és válassza a **Eszközkezelő** lehetőséget.) Győződjön meg arról, hogy az eszköz helyesen számba *veszi Microsoft HoloLens* az alábbi képen látható módon:</span><span class="sxs-lookup"><span data-stu-id="4b0a8-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2. MicrosoftHoloLensRecovery devive manager](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="4b0a8-139">A nem állítható alaphelyzetbe állítási eljárás</span><span class="sxs-lookup"><span data-stu-id="4b0a8-139">Hard-reset procedure</span></span>

<span data-ttu-id="4b0a8-140">Ha a normál alaphelyzetbe állítási eljárás nem működött, használja a nem állítható alaphelyzetbe állítási eljárást:</span><span class="sxs-lookup"><span data-stu-id="4b0a8-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="4b0a8-141">A Type-C kábel leválasztása az eszköz tápellátásról vagy a gazdaszámítógépről való leválasztása érdekében.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="4b0a8-142">Tartsa lenyomva a **hangerőt**  +  **15** másodpercig.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="4b0a8-143">Az eszköz automatikusan újraindul.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="4b0a8-144">Csatlakozás a gazdagépre.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-144">Connect the device to the host PC.</span></span>


5. <span data-ttu-id="4b0a8-145">Nyissa Eszközkezelő gombra (Windows 10 nyomja le a **Windows,** majd az **X** billentyűt, majd válassza a **Eszközkezelő).**</span><span class="sxs-lookup"><span data-stu-id="4b0a8-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="4b0a8-146">Győződjön meg arról, hogy az eszköz helyesen számba *veszi Microsoft HoloLens* az alábbi képen látható módon:</span><span class="sxs-lookup"><span data-stu-id="4b0a8-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2. maanger MicrosoftHoloLensRecovery eszköz](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="4b0a8-148">Az eszköz perjelének tisztítása</span><span class="sxs-lookup"><span data-stu-id="4b0a8-148">Clean-reflash the device</span></span>

<span data-ttu-id="4b0a8-149">Rendkívüli helyzetekben előfordulhat, hogy a 2. HoloLens kell".</span><span class="sxs-lookup"><span data-stu-id="4b0a8-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="4b0a8-150">Vegye figyelembe, hogy a tiszta perjel várhatóan nem érinti a következő problémákat:</span><span class="sxs-lookup"><span data-stu-id="4b0a8-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="4b0a8-151">Szín egységes megjelenítése</span><span class="sxs-lookup"><span data-stu-id="4b0a8-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="4b0a8-152">Rendszerindítás hanggal, de nincs megjelenítendő kimenet</span><span class="sxs-lookup"><span data-stu-id="4b0a8-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="4b0a8-153">1-3-5 LED minta</span><span class="sxs-lookup"><span data-stu-id="4b0a8-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="4b0a8-154">Túlmelegedés</span><span class="sxs-lookup"><span data-stu-id="4b0a8-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="4b0a8-155">Operációsrendszer-összeomlások (amelyek eltérnek az alkalmazás-összeomlástól)</span><span class="sxs-lookup"><span data-stu-id="4b0a8-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="4b0a8-156">Az eszközt két módon lehet újrafedni.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="4b0a8-157">Mindkét esetben először telepítenie kell az Advanced Recovery Companion alkalmazást a [Windows áruházból.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="4b0a8-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="4b0a8-158">Ha újrafűnésbe állítja az eszközt, az összes személyes adata, alkalmazása és beállítása törlődik, beleértve a TPM alaphelyzetbe állítási információit is.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="4b0a8-159">Alapértelmezés szerint az Advanced Recovery Companion a legújabb funkció kiadási build [](hololens-release-notes.md#) letöltésére van beállítva. Itt elolvashatja a kibocsátási megjegyzéseket a legújabb funkció kiadásának megismerése érdekében.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="4b0a8-160">Ha a 2.HoloLens-es teljes flash frissítés (FFU) legújabb csomagját le kell töltenie az eszköz reflash (perjeles perjellel) az Advanced Recovery Companion segítségével, kattintson ide a legújabb havi HoloLens 2-es rendszerkép [letöltéséhez.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="4b0a8-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="4b0a8-161">Ez a verzió a legújabb általánosan elérhető build.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="4b0a8-162">A perjeles eljárás előtt győződjön meg arról, hogy az alkalmazás telepítve van és fut a Windows 10 számítógépen, és készen áll az eszköz észlelésére.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="4b0a8-163">Arról is győződjön meg HoloLens hogy a díj összege legalább 40%.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 tiszta perjeles képernyőfelvétel](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="4b0a8-165">Normál eljárás</span><span class="sxs-lookup"><span data-stu-id="4b0a8-165">Normal procedure</span></span>

1. <span data-ttu-id="4b0a8-166">Amíg a HoloLens eszköz fut, csatlakoztassa azt Windows 10 számítógéphez, ahol korábban megnyitotta az Advanced Recovery Companion alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="4b0a8-167">A rendszer automatikusan észleli az eszközt, és a Speciális helyreállítást kísérő alkalmazás felhasználói felülete elindítja a frissítési folyamatot:</span><span class="sxs-lookup"><span data-stu-id="4b0a8-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 tiszta perjel kezdőképernyője](images/ARC2.png)

3. <span data-ttu-id="4b0a8-169">Válassza ki HoloLens 2. eszközt az Advanced Recovery Companion alkalmazás felhasználói felületén, és kövesse az utasításokat a perjel befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="4b0a8-170">Manuális eljárás</span><span class="sxs-lookup"><span data-stu-id="4b0a8-170">Manual procedure</span></span>

<span data-ttu-id="4b0a8-171">Ha a 2. HoloLens nem indul el megfelelően, vagy ha az Advanced Recovery Companion nem tudja észlelni az eszközt, előfordulhat, hogy helyreállítási módba kell tennie az eszközt:</span><span class="sxs-lookup"><span data-stu-id="4b0a8-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="4b0a8-172">A Type-C kábel leválasztása az eszköz tápellátásról vagy a gazdaszámítógépről való leválasztása érdekében.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="4b0a8-173">Nyomja le és tartsa lenyomva a **bekapcsológombot** 15 másodpercig.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="4b0a8-174">Minden LED-nek ki kell kapcsolnia.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="4b0a8-175">A hangerőszabályzó **gomb megnyomása** közben nyomja le és engedje el a **bekapcsológombot** az eszköz elindítani.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="4b0a8-176">Várjon 15 másodpercet, majd engedje fel **a kötet felfelé gombját.**</span><span class="sxs-lookup"><span data-stu-id="4b0a8-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="4b0a8-177">Csak az öt LED középső LED-e lesz begyűjtve.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="4b0a8-178">Csatlakozás a gazdagépre, és nyissa meg a Eszközkezelő.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="4b0a8-179">(A Windows 10 nyomja le a **Windows,** majd az **X** billentyűt, majd válassza a **Eszközkezelő** lehetőséget.) Győződjön meg arról, hogy az eszköz helyesen számba veszi Microsoft HoloLens az alábbi képen látható módon:</span><span class="sxs-lookup"><span data-stu-id="4b0a8-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2. microsoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="4b0a8-181">A rendszer automatikusan észleli az eszközt, és a Speciális helyreállítást kísérő alkalmazás felhasználói felülete elindítja a frissítési folyamatot:</span><span class="sxs-lookup"><span data-stu-id="4b0a8-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens két tiszta perjeles képernyő](images/ARC2.png)

6. <span data-ttu-id="4b0a8-183">Válassza ki HoloLens 2. eszközt az Advanced Recovery Companion alkalmazás felhasználói felületén, majd kövesse az utasításokat a perjel befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="4b0a8-184">Speciális helyreállítási társ hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="4b0a8-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="4b0a8-185">A flash kísérlet előtt győződjön meg arról, hogy az eszköz 40%-os vagy annál nagyobb díjat számol fel.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="4b0a8-186">Ellenőrizze, hogy az eszköz nincs-e feloldva.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-186">Check your device is unlocked.</span></span>

1. <span data-ttu-id="4b0a8-187">Ellenőrizze, hogy az eszköz közvetlenül a gazdaszámítógéphez van-e csatlakoztatva, nem hubhoz.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-187">Check your device is plugged directly into the host PC, not a hub.</span></span>

1. <span data-ttu-id="4b0a8-188">Ha az eszköz nem jelenik meg az univerzális serial bus-illesztőprogramok HoloLens/HoloLens recovery eszközként, ellenőrizze a következőt:</span><span class="sxs-lookup"><span data-stu-id="4b0a8-188">If your device is not showing as a HoloLens/HoloLens Recovery device under Universal Serial Bus Drivers, check:</span></span>
    1. <span data-ttu-id="4b0a8-189">**Portok,** Qualcomm HS-USB-eszközként</span><span class="sxs-lookup"><span data-stu-id="4b0a8-189">**Ports**, as a Qualcomm HS-USB device</span></span>
    1.   <span data-ttu-id="4b0a8-190">**Egyéb eszközök**, mint QUSB_BULK eszköz – a gazdaszámítógépről hiányoznak az eszköz észleléséhez szükséges HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-190">**Other Devices**, as a QUSB_BULK device - your host PC is missing the necessary drivers to detect your HoloLens.</span></span> <span data-ttu-id="4b0a8-191">Kattintson a jobb gombbal, és válassza az Illesztőprogram frissítése lehetőséget, keressen rá az illesztőprogramok online kifejezésre, vagy jelölje be az Opcionális frissítések lehetőséget [a Windows beállítások között.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674)</span><span class="sxs-lookup"><span data-stu-id="4b0a8-191">Right click and select Update Driver and search for drivers online or [check Optional Updates in your Windows Update settings](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674).</span></span> <span data-ttu-id="4b0a8-192">Az illesztőprogram letöltése után az ARC-nek képesnek kell lennie észlelni.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-192">After the driver is downloaded, ARC should be able to detect it.</span></span>
 
1. <span data-ttu-id="4b0a8-193">Ha az ARC nem észleli az eszközt, ellenőrizze, hogy tud-e csatlakozni az eszközhöz Fájlkezelő számítógépen található kapcsolaton keresztül.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-193">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="4b0a8-194">Ha nem tudja;</span><span class="sxs-lookup"><span data-stu-id="4b0a8-194">If you cannot;</span></span>

    1.  <span data-ttu-id="4b0a8-195">Előfordulhat, hogy az eszközön USB-szabályzatok tiltják le a kapcsolatot.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-195">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="4b0a8-196">Ha igen, próbálja ki [a Manuális flash módot.](hololens-recovery.md#manual-procedure)</span><span class="sxs-lookup"><span data-stu-id="4b0a8-196">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="4b0a8-197">Ha nincsenek házirendek, próbálkozzon egy másik USB-kábellel.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-197">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="4b0a8-198">Ellenőrizze, hogy az eszköz nem [1-3-5 LED-es mintát jelenít-e meg.](hololens2-setup.md#lights-to-indicate-problems)</span><span class="sxs-lookup"><span data-stu-id="4b0a8-198">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="4b0a8-199">Az ARC letöltése az Alkalmazás-áruház használata nélkül</span><span class="sxs-lookup"><span data-stu-id="4b0a8-199">Download ARC without using the app store</span></span>

<span data-ttu-id="4b0a8-200">Ha az IT-környezet megakadályozza a Windows Store alkalmazás használatát, vagy korlátozza a kiskereskedelmi áruházhoz való hozzáférést, a rendszergazda "offline" telepítési útvonalon elérhetővé tudja tenni az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-200">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="4b0a8-201">A rendszergazdák az alkalmazást a System Center Configuration Manager (SCCM) vagy az Intune szolgáltatáson keresztül is terjeszthetik.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-201">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="4b0a8-202">Ez az útmutató az Advanced Recovery Companion funkcióval foglalkozik, de a folyamat más "offline" alkalmazásokhoz is használható.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-202">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="4b0a8-203">Az üzembe helyezési útvonal engedélyezéséhez kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4b0a8-203">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="4b0a8-204">A Microsoft Store Vállalatoknak [jelentkezzen](https://businessstore.microsoft.com) be egy Azure Active Directory identitással.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-204">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="4b0a8-205">A Kezelés **– Gépház.**</span><span class="sxs-lookup"><span data-stu-id="4b0a8-205">Go to **Manage – Settings**.</span></span> <span data-ttu-id="4b0a8-206">A Vásárlási **élmény alatt kapcsolja** be az Offline alkalmazások megjelenítése **et.**</span><span class="sxs-lookup"><span data-stu-id="4b0a8-206">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="4b0a8-207">Keresse fel **a csoportomért való vásárlást,** és keressen rá az [**_Advanced Recovery Companion kifejezésre._**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="4b0a8-207">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="4b0a8-208">Módosítsa a **Licenc típusa beállítását** **_offline _,_*majd válassza a _ Kezelés\* lehetőséget.*\*</span><span class="sxs-lookup"><span data-stu-id="4b0a8-208">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="4b0a8-209">A **Csomag letöltése offline használatra alatt** válassza a második kék Letöltés **gombot.**</span><span class="sxs-lookup"><span data-stu-id="4b0a8-209">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="4b0a8-210">Győződjön meg arról, hogy a *fájlkiterjesztés .appxbundle.*</span><span class="sxs-lookup"><span data-stu-id="4b0a8-210">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="4b0a8-211">Ha az asztali számítógép jelenleg rendelkezik internet-hozzáféréssel, kattintson duplán a csomagra az alkalmazás telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-211">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="4b0a8-212">Ha a célszámítógépen nincs internetkapcsolat, kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4b0a8-212">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="4b0a8-213">Válassza ki a nem kódolatlan licencet, majd válassza a **Licenc létrehozása lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="4b0a8-213">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="4b0a8-214">A **Szükséges keretrendszerek alatt válassza** a Letöltés **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="4b0a8-214">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="4b0a8-215">A DISM használatával alkalmazza a csomagot a függőséggel és a licenccel.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-215">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="4b0a8-216">Futtassa a következő parancsot egy rendszergazdai parancssorból:</span><span class="sxs-lookup"><span data-stu-id="4b0a8-216">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="4b0a8-217">Előfordulhat, hogy a jelen példakódban lévő verziószám nem egyezik a jelenleg elérhető verzióval.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-217">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="4b0a8-218">Előfordulhat, hogy más letöltési helyet választott, mint a példában.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-218">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="4b0a8-219">Szükség szerint módosítja a parancsot.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-219">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="4b0a8-220">Ha az FFU offline telepítéséhez az Advanced Recovery Companiont tervezi használni, hasznos lehet a flash lemezkép letöltése.</span><span class="sxs-lookup"><span data-stu-id="4b0a8-220">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="4b0a8-221">[**Töltse le a 2. HoloLens aktuális rendszerképét.**](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="4b0a8-221">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="4b0a8-222">Egyéb erőforrások:</span><span class="sxs-lookup"><span data-stu-id="4b0a8-222">Other resources:</span></span>
- [<span data-ttu-id="4b0a8-223">Offline alkalmazások terjesztése</span><span class="sxs-lookup"><span data-stu-id="4b0a8-223">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="4b0a8-224">DISM alkalmazáscsomag (.appx vagy .appxbundle) – karbantartási parancssori beállítások</span><span class="sxs-lookup"><span data-stu-id="4b0a8-224">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
