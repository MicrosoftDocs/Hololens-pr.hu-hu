---
title: A HoloLens újraindítása, alaphelyzetbe állítása vagy helyreállítása
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Az Advanced Recovery Companion használata egy kép a HoloLens 2-ben való flash (flash) funkcióját használva.
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
ms.openlocfilehash: afd782df1c68e8441b14823e0d961317914140e3
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379583"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="99be6-104">A HoloLens 2 újraindítása, alaphelyzetbe állítása vagy helyreállítása</span><span class="sxs-lookup"><span data-stu-id="99be6-104">Restart, reset, or recover HoloLens 2</span></span>

## <a name="charge-the-device"></a><span data-ttu-id="99be6-105">Az eszköz díjának feltöltése</span><span class="sxs-lookup"><span data-stu-id="99be6-105">Charge the device</span></span>

>[!IMPORTANT]
> <span data-ttu-id="99be6-106">A hibaelhárítási eljárás elkezdése előtt győződjön meg arról, hogy az eszköz **20–40** százalék akkumulátor-kapacitással rendelkezik, ha lehetséges.</span><span class="sxs-lookup"><span data-stu-id="99be6-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="99be6-107">A [tápkapcsoló alatt](hololens2-setup.md#lights-that-indicate-the-battery-level) található akkumulátorjelző világítással gyorsan ellenőrizheti az akkumulátor kapacitását anélkül, hogy bejelentkezik az eszközre.</span><span class="sxs-lookup"><span data-stu-id="99be6-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="99be6-108">Használja a HoloLens 2-höz csatlakoztatott kábellel és USB [Type-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) kábellel, mivel ez a legjobb módszer az eszköz feltöltésére.</span><span class="sxs-lookup"><span data-stu-id="99be6-108">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="99be6-109">A tápellátás 18W energiát ad (9V 2A-n).</span><span class="sxs-lookup"><span data-stu-id="99be6-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="99be6-110">A mellékelt fali készülék használatával a HoloLens 2-eszközök az akkumulátort kevesebb mint 65 perc alatt megtelik, amikor az eszköz készenléti állapotban van.</span><span class="sxs-lookup"><span data-stu-id="99be6-110">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="99be6-111">Ha ezek a tápegységek nem érhetők el, győződjön meg arról, hogy az elérhető tápegység legalább 15W áramellátást tud támogatni.</span><span class="sxs-lookup"><span data-stu-id="99be6-111">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="99be6-112">Ha lehetséges, ne használja a pc-t az eszköz USB-kapcsolaton keresztüli feltöltésére, ami lassú.</span><span class="sxs-lookup"><span data-stu-id="99be6-112">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="99be6-113">Ha az eszköz megfelelően elindult és fut, háromféleképpen ellenőrizheti az akkumulátor töltöttségi szintjét:</span><span class="sxs-lookup"><span data-stu-id="99be6-113">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="99be6-114">A HoloLens eszköz felhasználói felületének főmenüjéről.</span><span class="sxs-lookup"><span data-stu-id="99be6-114">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="99be6-115">Tekintse meg a LED-et a bekapcsológomb közelében (40%-os díjért legalább két SSD-t kell látnia).</span><span class="sxs-lookup"><span data-stu-id="99be6-115">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="99be6-116">Ha az eszköz töltődik, az akkumulátor kijelzője felgyúgyítással jelzi az aktuális töltöttségi szintet.</span><span class="sxs-lookup"><span data-stu-id="99be6-116">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="99be6-117">Az utolsó világítás elhalványul és kihalványul, ami aktív díjszabást jelez.</span><span class="sxs-lookup"><span data-stu-id="99be6-117">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="99be6-118">Ha a HoloLens be van stb., az akkumulátor kijelzője öt lépéssel jeleníti meg az akkumulátor töltöttségi szintjét.</span><span class="sxs-lookup"><span data-stu-id="99be6-118">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="99be6-119">Ha az öt világítás közül csak az egyik van bekapcsolva, az akkumulátor töltöttségi szintje 20% alatt van.</span><span class="sxs-lookup"><span data-stu-id="99be6-119">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="99be6-120">Ha az akkumulátor töltöttségi szintje kritikusan alacsony, és megpróbálja bekapcsolni az eszközt, az egyik világítás rövid időre villog, majd kiússik.</span><span class="sxs-lookup"><span data-stu-id="99be6-120">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="99be6-121">A gazdaszámítógépen nyissa meg a **Fájlkezelő,** és keresse meg HoloLens 2-eszközét a bal oldalon az Ez a **számítógép alatt.**</span><span class="sxs-lookup"><span data-stu-id="99be6-121">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="99be6-122">Kattintson a jobb gombbal az eszközre, majd válassza a **Tulajdonságok lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="99be6-122">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="99be6-123">Egy párbeszédpanelen megjelenik az akkumulátor töltöttségi szintje.</span><span class="sxs-lookup"><span data-stu-id="99be6-123">A dialog box will show the battery charge level.</span></span>

   ![A HoloLens 2 tulajdonságokat bemutató képernyője az akkumulátor töltöttségi szintjét jeleníti meg](images/ResetRecovery2.png)

<span data-ttu-id="99be6-125">Ha az eszköz nem indítható el az indítási menüben, jegyezze fel a LED megjelenését és az eszköz enumerálását a gazdagépen.</span><span class="sxs-lookup"><span data-stu-id="99be6-125">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="99be6-126">Ezután kövesse a [hibaelhárítási útmutatót.](hololens-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="99be6-126">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="99be6-127">Ha az eszköz állapota nem egyezik a hibaelhárítási útmutatóban felsorolt állapotok egyikével sem, hajtsa végre a merevlemez-visszaállítási eljárást úgy, hogy az eszköz a tápegységhez, nem pedig a gazdagéphez csatlakozik. [](hololens-recovery.md#hard-reset-procedure)</span><span class="sxs-lookup"><span data-stu-id="99be6-127">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="99be6-128">Várjon legalább egy órát, amíg az eszköz díjat számít fel.</span><span class="sxs-lookup"><span data-stu-id="99be6-128">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="99be6-129">Az eszköz alaphelyzetbe állítása</span><span class="sxs-lookup"><span data-stu-id="99be6-129">Reset the device</span></span>

<span data-ttu-id="99be6-130">Bizonyos körülmények között előfordulhat, hogy manuálisan kell alaphelyzetbe állítania az eszközt a szoftver felhasználói felületének használata nélkül.</span><span class="sxs-lookup"><span data-stu-id="99be6-130">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="99be6-131">Szabványos eljárás</span><span class="sxs-lookup"><span data-stu-id="99be6-131">Standard procedure</span></span>

1. <span data-ttu-id="99be6-132">A Type-C kábel leválasztása az eszköz tápellátásról vagy a gazdaszámítógépről való leválasztása érdekében.</span><span class="sxs-lookup"><span data-stu-id="99be6-132">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="99be6-133">Nyomja le és tartsa lenyomva a **bekapcsológombot** 15 másodpercig.</span><span class="sxs-lookup"><span data-stu-id="99be6-133">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="99be6-134">Minden LED-nek kikapcsolva kell lennie.</span><span class="sxs-lookup"><span data-stu-id="99be6-134">All LEDs should be off.</span></span>

3. <span data-ttu-id="99be6-135">Várjon 2–3 másodpercet, majd nyomja le röviden a **bekapcsológombot.**</span><span class="sxs-lookup"><span data-stu-id="99be6-135">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="99be6-136">A bekapcsológombhoz közeli LED-ek kigyűjnek, és az eszköz elindul.</span><span class="sxs-lookup"><span data-stu-id="99be6-136">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="99be6-137">Csatlakoztassa az eszközt a gazdagéphez, majd nyissa meg Eszközkezelő.</span><span class="sxs-lookup"><span data-stu-id="99be6-137">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="99be6-138">(A Windows 10 nyomja le a **Windows** billentyűt, majd az **X** billentyűt, és válassza a Eszközkezelő **lehetőséget.)** Győződjön meg arról, hogy az eszköz helyesen számba *veszi Microsoft HoloLens* az alábbi képen látható módon:</span><span class="sxs-lookup"><span data-stu-id="99be6-138">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery devive manager](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="99be6-140">A nem állítható alaphelyzetbe állítási eljárás</span><span class="sxs-lookup"><span data-stu-id="99be6-140">Hard-reset procedure</span></span>

<span data-ttu-id="99be6-141">Ha a normál alaphelyzetbe állítási eljárás nem működött, használja a nem állítható alaphelyzetbe állítási eljárást:</span><span class="sxs-lookup"><span data-stu-id="99be6-141">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="99be6-142">A Type-C kábel leválasztása az eszköz tápellátásról vagy a gazdaszámítógépről való leválasztása érdekében.</span><span class="sxs-lookup"><span data-stu-id="99be6-142">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="99be6-143">Tartsa lenyomva a **hangerőt**  +  **15** másodpercig.</span><span class="sxs-lookup"><span data-stu-id="99be6-143">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="99be6-144">Az eszköz automatikusan újraindul.</span><span class="sxs-lookup"><span data-stu-id="99be6-144">The device will automatically restart.</span></span>

4. <span data-ttu-id="99be6-145">Csatlakoztassa az eszközt a gazdagéphez.</span><span class="sxs-lookup"><span data-stu-id="99be6-145">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="99be6-146">Nyissa Eszközkezelő gombra (Windows 10 a **Windows** billentyűt, majd az **X** billentyűt, majd válassza a **Eszközkezelő)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="99be6-146">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="99be6-147">Győződjön meg arról, hogy az eszköz helyesen számba *veszi Microsoft HoloLens* az alábbi képen látható módon:</span><span class="sxs-lookup"><span data-stu-id="99be6-147">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery eszköz maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="99be6-149">Az eszköz perjelének tisztítása</span><span class="sxs-lookup"><span data-stu-id="99be6-149">Clean-reflash the device</span></span>

<span data-ttu-id="99be6-150">Rendkívüli helyzetekben előfordulhat, hogy a HoloLens 2-t "tiszta flash"-re kell felrakni.</span><span class="sxs-lookup"><span data-stu-id="99be6-150">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="99be6-151">Vegye figyelembe, hogy a perjeles perjel várhatóan nem érinti a következő problémákat:</span><span class="sxs-lookup"><span data-stu-id="99be6-151">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="99be6-152">Szín egységes megjelenítése</span><span class="sxs-lookup"><span data-stu-id="99be6-152">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="99be6-153">Rendszerindítás hanggal, de nincs megjelenítendő kimenet</span><span class="sxs-lookup"><span data-stu-id="99be6-153">Booting with sound but no display output</span></span>
- [<span data-ttu-id="99be6-154">1-3-5 LED minta</span><span class="sxs-lookup"><span data-stu-id="99be6-154">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="99be6-155">Túlmelegedés</span><span class="sxs-lookup"><span data-stu-id="99be6-155">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="99be6-156">Operációsrendszer-összeomlások (amelyek eltérnek az alkalmazás-összeomlástól)</span><span class="sxs-lookup"><span data-stu-id="99be6-156">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="99be6-157">Az eszközt két módon lehet újrafedni.</span><span class="sxs-lookup"><span data-stu-id="99be6-157">There are two ways to reflash the device.</span></span> <span data-ttu-id="99be6-158">Mindkét esetben először telepítenie kell az [Advanced Recovery Companion alkalmazást a Windows Áruházból.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="99be6-158">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="99be6-159">Ha újrafűnésbe állítja az eszközt, az összes személyes adata, alkalmazása és beállítása törlődik, beleértve a TPM alaphelyzetbe állítási információit is.</span><span class="sxs-lookup"><span data-stu-id="99be6-159">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="99be6-160">Alapértelmezés szerint az Advanced Recovery Companion a legújabb funkció kiadási build [](hololens-release-notes.md#) letöltésére van beállítva. Itt elolvashatja a kibocsátási megjegyzéseket a legújabb funkció kiadásának megismerése érdekében.</span><span class="sxs-lookup"><span data-stu-id="99be6-160">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="99be6-161">Ha a legújabb HoloLens 2 Full Flash Update -csomagot (FFU) le kell töltenie az eszköz reflash eleméhez az Advanced Recovery Companion segítségével, kattintson ide a legújabb havi [HoloLens 2 rendszerkép letöltéséhez.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="99be6-161">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="99be6-162">Ez a verzió a legújabb általánosan elérhető build.</span><span class="sxs-lookup"><span data-stu-id="99be6-162">This version is the latest generally available build.</span></span>

<span data-ttu-id="99be6-163">A perjeles eljárás előtt győződjön meg arról, hogy az alkalmazás telepítve van és fut a Windows 10 számítógépen, és készen áll az eszköz észlelésére.</span><span class="sxs-lookup"><span data-stu-id="99be6-163">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="99be6-164">Arról is győződjön meg, hogy a HoloLensért legalább 40%-os díjat kell fizetnie.</span><span class="sxs-lookup"><span data-stu-id="99be6-164">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 – tiszta perjel képernyőfelvétel](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="99be6-166">Normál eljárás</span><span class="sxs-lookup"><span data-stu-id="99be6-166">Normal procedure</span></span>

1. <span data-ttu-id="99be6-167">Amíg a HoloLens-eszköz fut, csatlakoztassa a Windows 10 számítógéphez, ahol korábban megnyitotta az Advanced Recovery Companion alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="99be6-167">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="99be6-168">A rendszer automatikusan észleli az eszközt, és a Speciális helyreállítást kísérő alkalmazás felhasználói felülete elindítja a frissítési folyamatot:</span><span class="sxs-lookup"><span data-stu-id="99be6-168">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![A HoloLens 2 tiszta perjeles kezdőképernyője](images/ARC2.png)

3. <span data-ttu-id="99be6-170">Válassza ki a HoloLens 2 eszközt az Advanced Recovery Companion alkalmazás felhasználói felületén, és kövesse az utasításokat a perjel befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="99be6-170">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="99be6-171">Manuális eljárás</span><span class="sxs-lookup"><span data-stu-id="99be6-171">Manual procedure</span></span>

<span data-ttu-id="99be6-172">Ha a HoloLens 2 nem indul el megfelelően, vagy ha az Advanced Recovery Companion nem tudja észlelni az eszközt, előfordulhat, hogy helyreállítási módba kell tennie az eszközt:</span><span class="sxs-lookup"><span data-stu-id="99be6-172">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="99be6-173">A Type-C kábel leválasztása az eszköz tápellátásról vagy a gazdaszámítógépről való leválasztása érdekében.</span><span class="sxs-lookup"><span data-stu-id="99be6-173">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="99be6-174">Nyomja le és tartsa lenyomva a **bekapcsológombot** 15 másodpercig.</span><span class="sxs-lookup"><span data-stu-id="99be6-174">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="99be6-175">Minden LED-nek ki kell kapcsolnia.</span><span class="sxs-lookup"><span data-stu-id="99be6-175">All LEDs should turn off.</span></span>

3. <span data-ttu-id="99be6-176">A hangerőszabályzó **gomb megnyomása** közben nyomja le és engedje el a **bekapcsológombot** az eszköz elindítani.</span><span class="sxs-lookup"><span data-stu-id="99be6-176">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="99be6-177">Várjon 15 másodpercet, majd engedje fel **a kötet felfelé gombját.**</span><span class="sxs-lookup"><span data-stu-id="99be6-177">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="99be6-178">Csak az öt LED középső LED-e lesz begyűjtve.</span><span class="sxs-lookup"><span data-stu-id="99be6-178">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="99be6-179">Csatlakoztassa az eszközt a gazdagéphez, és nyissa meg Eszközkezelő.</span><span class="sxs-lookup"><span data-stu-id="99be6-179">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="99be6-180">(A Windows 10 nyomja le a **Windows** billentyűt, majd az **X** billentyűt, és válassza a Eszközkezelő **lehetőséget.)** Győződjön meg arról, hogy az eszköz helyesen számba veszi Microsoft HoloLens az alábbi képen látható módon:</span><span class="sxs-lookup"><span data-stu-id="99be6-180">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="99be6-182">A rendszer automatikusan észleli az eszközt, és a Speciális helyreállítást kísérő alkalmazás felhasználói felülete elindítja a frissítési folyamatot:</span><span class="sxs-lookup"><span data-stu-id="99be6-182">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![A HoloLens 2 tiszta perjeles képernyője](images/ARC2.png)

6. <span data-ttu-id="99be6-184">Válassza ki a HoloLens 2 eszközt az Advanced Recovery Companion alkalmazás felhasználói felületén, majd kövesse az utasításokat a perjel befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="99be6-184">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="99be6-185">Speciális helyreállítási társ hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="99be6-185">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="99be6-186">A flash kísérlet előtt győződjön meg arról, hogy az eszköz 40%-os vagy annál nagyobb díjat számol fel.</span><span class="sxs-lookup"><span data-stu-id="99be6-186">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="99be6-187">Ellenőrizze, hogy az eszköz zárolása fel van-e oldva.</span><span class="sxs-lookup"><span data-stu-id="99be6-187">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="99be6-188">Ha az ARC nem észleli az eszközt, ellenőrizze, hogy tud-e csatlakozni az eszközhöz Fájlkezelő számítógépen található kapcsolaton keresztül.</span><span class="sxs-lookup"><span data-stu-id="99be6-188">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="99be6-189">Ha nem tudja;</span><span class="sxs-lookup"><span data-stu-id="99be6-189">If you cannot;</span></span>

    1.  <span data-ttu-id="99be6-190">Előfordulhat, hogy az eszközön USB-szabályzatok tiltják le a kapcsolatot.</span><span class="sxs-lookup"><span data-stu-id="99be6-190">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="99be6-191">Ha igen, próbálja ki [a Manuális flash módot.](hololens-recovery.md#manual-procedure)</span><span class="sxs-lookup"><span data-stu-id="99be6-191">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="99be6-192">Ha nincsenek házirendek, próbálkozzon egy másik USB-kábellel.</span><span class="sxs-lookup"><span data-stu-id="99be6-192">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="99be6-193">Ellenőrizze, hogy az eszköz nem [1-3-5 LED-es mintát jelenít-e meg.](hololens2-setup.md#lights-to-indicate-problems)</span><span class="sxs-lookup"><span data-stu-id="99be6-193">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="99be6-194">Az ARC letöltése az Alkalmazás-áruház használata nélkül</span><span class="sxs-lookup"><span data-stu-id="99be6-194">Download ARC without using the app store</span></span>

<span data-ttu-id="99be6-195">Ha az it-környezet megakadályozza a Windows Áruházbeli alkalmazás használatát, vagy korlátozza a kiskereskedelmi áruházhoz való hozzáférést, a rendszergazda "offline" telepítési útvonalon elérhetővé tudja tenni az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="99be6-195">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="99be6-196">A rendszergazdák az alkalmazást a System Center Konfigurációkezelő (SCCM) vagy az Intune segítségével is terjesztheti.</span><span class="sxs-lookup"><span data-stu-id="99be6-196">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="99be6-197">Ez az útmutató a Speciális helyreállítási segédre összpontosít, de a folyamat más "offline" alkalmazásokhoz is használható.</span><span class="sxs-lookup"><span data-stu-id="99be6-197">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="99be6-198">Az üzembe helyezési útvonal engedélyezéséhez kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="99be6-198">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="99be6-199">A [Microsoft Store Vállalatoknak,](https://businessstore.microsoft.com) és jelentkezzen be egy Azure Active Directory identitással.</span><span class="sxs-lookup"><span data-stu-id="99be6-199">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="99be6-200">Kattintson a **Kezelés – Beállítások elemre.**</span><span class="sxs-lookup"><span data-stu-id="99be6-200">Go to **Manage – Settings**.</span></span> <span data-ttu-id="99be6-201">A Vásárlási **élmény alatt kapcsolja** be az Offline alkalmazások megjelenítése **et.**</span><span class="sxs-lookup"><span data-stu-id="99be6-201">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="99be6-202">Keresse fel **a csoportomért való vásárlást,** és keressen rá az [**_Advanced Recovery Companion kifejezésre._**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="99be6-202">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="99be6-203">Módosítsa a **Licenc típusa beállítását** **_offline _,_*majd válassza a _ Kezelés\* lehetőséget.*\*</span><span class="sxs-lookup"><span data-stu-id="99be6-203">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="99be6-204">A **Csomag letöltése offline használatra alatt válassza** a második kék Letöltés **gombot.**</span><span class="sxs-lookup"><span data-stu-id="99be6-204">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="99be6-205">Győződjön meg arról, hogy a *fájlkiterjesztés .appxbundle.*</span><span class="sxs-lookup"><span data-stu-id="99be6-205">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="99be6-206">Ha az asztali számítógép jelenleg rendelkezik internet-hozzáféréssel, kattintson duplán a csomagra az alkalmazás telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="99be6-206">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="99be6-207">Ha a célszámítógépen nincs internetkapcsolat, kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="99be6-207">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="99be6-208">Válassza ki a nem kódolatlan licencet, majd válassza a **Licenc létrehozása lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="99be6-208">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="99be6-209">A **Szükséges keretrendszerek alatt válassza** a Letöltés **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="99be6-209">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="99be6-210">A DISM használatával alkalmazza a csomagot a függőséggel és a licenccel.</span><span class="sxs-lookup"><span data-stu-id="99be6-210">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="99be6-211">Futtassa a következő parancsot egy rendszergazdai parancssorból:</span><span class="sxs-lookup"><span data-stu-id="99be6-211">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="99be6-212">Előfordulhat, hogy a jelen példakódban lévő verziószám nem egyezik a jelenleg elérhető verzióval.</span><span class="sxs-lookup"><span data-stu-id="99be6-212">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="99be6-213">Előfordulhat, hogy más letöltési helyet választott, mint a példában.</span><span class="sxs-lookup"><span data-stu-id="99be6-213">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="99be6-214">Szükség szerint módosítja a parancsot.</span><span class="sxs-lookup"><span data-stu-id="99be6-214">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="99be6-215">Ha az Advanced Recovery Companion használatával tervezi offline telepíteni az FFU-t, hasznos lehet a flash lemezkép letöltése.</span><span class="sxs-lookup"><span data-stu-id="99be6-215">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="99be6-216">[**Töltse le a HoloLens 2 aktuális rendszerképét.**](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="99be6-216">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="99be6-217">Egyéb erőforrások:</span><span class="sxs-lookup"><span data-stu-id="99be6-217">Other resources:</span></span>
- [<span data-ttu-id="99be6-218">Offline alkalmazások terjesztése</span><span class="sxs-lookup"><span data-stu-id="99be6-218">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="99be6-219">DISM alkalmazáscsomag (.appx vagy .appxbundle) – karbantartási parancssori beállítások</span><span class="sxs-lookup"><span data-stu-id="99be6-219">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
