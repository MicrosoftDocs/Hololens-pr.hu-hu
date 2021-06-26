---
title: Csatlakozás Bluetooth- és USB-C-eszközökhöz
description: Az első lépések a Bluetooth- és USB-C-eszközökhöz és -kiegészítőkhez való kapcsolódáshoz a HoloLens vegyes valóságú eszközeiről.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e02950bf6cb70e381e3bc5850509bc65267759c1
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924179"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="2f5d3-103">Csatlakozás Bluetooth- és USB-C-eszközökhöz</span><span class="sxs-lookup"><span data-stu-id="2f5d3-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="2f5d3-104">Bluetooth-eszközök párosítása</span><span class="sxs-lookup"><span data-stu-id="2f5d3-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="2f5d3-105">A HoloLens 2 a Bluetooth-eszközök következő osztályát támogatja:</span><span class="sxs-lookup"><span data-stu-id="2f5d3-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="2f5d3-106">[HID ::](https://docs.microsoft.com/windows-hardware/drivers/hid/)</span><span class="sxs-lookup"><span data-stu-id="2f5d3-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="2f5d3-107">Egér</span><span class="sxs-lookup"><span data-stu-id="2f5d3-107">Mouse</span></span>
    - <span data-ttu-id="2f5d3-108">Billentyűzet</span><span class="sxs-lookup"><span data-stu-id="2f5d3-108">Keyboard</span></span>
- <span data-ttu-id="2f5d3-109">Hangkimeneti (A2DP) eszközök</span><span class="sxs-lookup"><span data-stu-id="2f5d3-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="2f5d3-110">A HoloLens 2 a következő Bluetooth API-kat támogatja:</span><span class="sxs-lookup"><span data-stu-id="2f5d3-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="2f5d3-111">ANNAK [kiszolgálója](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) és [ügyfele](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span><span class="sxs-lookup"><span data-stu-id="2f5d3-111">GATT [Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) and [Client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="2f5d3-112">Rfcomm</span><span class="sxs-lookup"><span data-stu-id="2f5d3-112">RFCOMM</span></span>](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="2f5d3-113">Előfordulhat, hogy telepítenie kell a megfelelő társalkalmazásokat a Microsoft Store a HID és a AZDM-eszközök ténylegesen való használatához.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="2f5d3-114">A HoloLens (1. generációs) a Bluetooth-eszközök következő osztályát támogatja:</span><span class="sxs-lookup"><span data-stu-id="2f5d3-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="2f5d3-115">Egér</span><span class="sxs-lookup"><span data-stu-id="2f5d3-115">Mouse</span></span>
- <span data-ttu-id="2f5d3-116">Billentyűzet</span><span class="sxs-lookup"><span data-stu-id="2f5d3-116">Keyboard</span></span>
- [<span data-ttu-id="2f5d3-117">HoloLens (1. generációs) clicker</span><span class="sxs-lookup"><span data-stu-id="2f5d3-117">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="2f5d3-118">A HoloLens beállításai között más Típusú Bluetooth-eszközök, például beszélők, headsetek, okostelefonok és játékpanelek is fel vannak sorolva.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="2f5d3-119">Ezek az eszközök azonban nem támogatottak a HoloLensben (1. generációs verzió).</span><span class="sxs-lookup"><span data-stu-id="2f5d3-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="2f5d3-120">További információkért lásd: [A HoloLens-beállítások](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)listázza az eszközöket elérhetőként, de az eszközök nem működnek.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="2f5d3-121">Bluetooth-billentyűzet vagy -egér párosítása</span><span class="sxs-lookup"><span data-stu-id="2f5d3-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="2f5d3-122">Kapcsolja be a billentyűzetet vagy az egeret, és tegye felderíthetővé.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="2f5d3-123">Ha meg szeretne ismerkedni az eszköz felderítésének mikéntjével, keresse fel az eszközre vonatkozó információkat (vagy a dokumentációját), vagy keresse fel a gyártó webhelyét.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="2f5d3-124">Használja a Bloom-kézmozdulatot (HoloLens (1. generációs)) vagy az indítási kézmozdulatot (HoloLens 2) a **Start** menüben, majd válassza a **Beállítások lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="2f5d3-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="2f5d3-125">Válassza **az Eszközök** lehetőséget, és ellenőrizze, hogy a Bluetooth be van-e stb.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="2f5d3-126">Ha látja az eszköz nevét, válassza a **Pár** lehetőséget, majd kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="2f5d3-127">Bluetooth letiltása</span><span class="sxs-lookup"><span data-stu-id="2f5d3-127">Disable Bluetooth</span></span>

<span data-ttu-id="2f5d3-128">Ez az eljárás kikapcsolja a Bluetooth-választó rf-összetevőit, és letiltja az összes Bluetooth-funkciót a Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="2f5d3-129">Használja a Bloom-kézmozdulatot (HoloLens (1. generációs)) vagy az indítási kézmozdulatot (HoloLens 2) a **Start** menüben, majd válassza a Beállítások  >  **Eszközök lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="2f5d3-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="2f5d3-130">Húzza a **Bluetooth csúszkakapcsolóját** a **Ki állásba.**</span><span class="sxs-lookup"><span data-stu-id="2f5d3-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="2f5d3-131">HoloLens 2: USB-C-eszközök csatlakoztatása</span><span class="sxs-lookup"><span data-stu-id="2f5d3-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="2f5d3-132">A HoloLens 2 az USB-C-eszközök következő osztályát támogatja:</span><span class="sxs-lookup"><span data-stu-id="2f5d3-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="2f5d3-133">Tömeges tárolóeszközök (például ujjlenyomat-meghajtók)</span><span class="sxs-lookup"><span data-stu-id="2f5d3-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="2f5d3-134">Ethernet-adapterek (beleértve az Ethernet+díjszabást)</span><span class="sxs-lookup"><span data-stu-id="2f5d3-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="2f5d3-135">USB-C-to-3.5mm digitális hangadapterek</span><span class="sxs-lookup"><span data-stu-id="2f5d3-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="2f5d3-136">USB-C digitális audio-headsetek (beleértve a headset adaptereket és a díjszabást)</span><span class="sxs-lookup"><span data-stu-id="2f5d3-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="2f5d3-137">USB-C külső mikrofonok ([Windows Holographic, 21H1-es és](hololens-release-notes.md#windows-holographic-version-21h1) újabb verziók)</span><span class="sxs-lookup"><span data-stu-id="2f5d3-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="2f5d3-138">Vezetékes egér</span><span class="sxs-lookup"><span data-stu-id="2f5d3-138">Wired mouse</span></span>
- <span data-ttu-id="2f5d3-139">Vezetékes billentyűzet</span><span class="sxs-lookup"><span data-stu-id="2f5d3-139">Wired keyboard</span></span>
- <span data-ttu-id="2f5d3-140">Kombinált PD hubok (USB A plusz PD-díjszabás)</span><span class="sxs-lookup"><span data-stu-id="2f5d3-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="2f5d3-141">Az ügyfelek visszajelzésére válaszul korlátozott támogatást engedélyeztünk a HoloLenshez USB-C-n keresztül közvetlenül a HoloLenshez csatlakoztatott mobilkapcsolatok számára.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="2f5d3-142">További [információ: Connect to Cellular and 5G (Csatlakozás mobilhálózathoz](hololens-cellular.md) és 5G-hez).</span><span class="sxs-lookup"><span data-stu-id="2f5d3-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="2f5d3-143">USB-C külső mikrofon támogatása</span><span class="sxs-lookup"><span data-stu-id="2f5d3-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f5d3-144">Az USB-mikrofon csatlakoztatása nem lesz automatikusan beállítva **bemeneti eszközként.**</span><span class="sxs-lookup"><span data-stu-id="2f5d3-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="2f5d3-145">USB-C-kábelek csatlakoztatása esetén a felhasználók megfigyelhetik, hogy a hanganyag automatikusan a mikrofonhoz lesz átirányítva, de a HoloLens operációs rendszer a belső mikrofontömböt a többi bemeneti eszköz fölé rangsorítja.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="2f5d3-146">**USB-C mikrofon használata érdekében kövesse az alábbi lépéseket.**</span><span class="sxs-lookup"><span data-stu-id="2f5d3-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="2f5d3-147">A külső mikrofonok nem használhatók a [Windows Holographic előtti, 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) vagy újabb verziójú buildekben.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="2f5d3-148">A felhasználók a Hangbeállítások panelen választhatnak USB-C-hez csatlakoztatott külső **mikrofonokat.**</span><span class="sxs-lookup"><span data-stu-id="2f5d3-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="2f5d3-149">Az USB-C-mikrofonok hívásra, felvételre stb. használhatók.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="2f5d3-150">Nyissa meg a **Beállítások** alkalmazást, és válassza a **System**  >  **Sound lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="2f5d3-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Hangbeállítások](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="2f5d3-152">Ha külső mikrofonokat használ a **Remote Assist** segítségével, a felhasználóknak a "Hangeszközök kezelése" hivatkozásra kell kattintanunk.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="2f5d3-153">Ezután a legördülő menüben állítsa a  külső mikrofont Alapértelmezett vagy **Kommunikációs alapértelmezettre.**</span><span class="sxs-lookup"><span data-stu-id="2f5d3-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="2f5d3-154">Az **Alapértelmezett beállítás** azt jelenti, hogy a külső mikrofon mindenhol használatban lesz.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="2f5d3-155">A **Kommunikáció alapértelmezett beállítása** azt jelenti, hogy a külső mikrofon a Remote Assist és más kommunikációs alkalmazásokban lesz használva, de a HoloLens mic tömb továbbra is használható más feladatokhoz.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Hangeszközök kezelése](images/usbc-mic-2.png)

<br>

![Mikrofon alapértelmezett beállítása](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="2f5d3-158">Mi a helyzet a Bluetooth-mikrofonok támogatásával?</span><span class="sxs-lookup"><span data-stu-id="2f5d3-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="2f5d3-159">Sajnos a Bluetooth-mikrofonok jelenleg még nem támogatottak a HoloLens 2-ben.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="2f5d3-160">USB-C hubok</span><span class="sxs-lookup"><span data-stu-id="2f5d3-160">USB-C Hubs</span></span>

<span data-ttu-id="2f5d3-161">Előfordulhat, hogy egyes felhasználóknak egyszerre több eszközt kell csatlakoztatnia.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="2f5d3-162">Azok a felhasználók, akik [USB-C-mikrofont](#usb-c-external-microphone-support) és egy másik csatlakoztatott eszközt is használni szeretnék, az USB-C hubok illeszkedhetnek az ügyfél igényeihez.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="2f5d3-163">A Microsoft nem tesztelte ezeket az eszközöket, és nem is ajánlunk semmilyen konkrét márkát.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="2f5d3-164">**Az USB-C hubra és a csatlakoztatott eszközökre vonatkozó követelmények:**</span><span class="sxs-lookup"><span data-stu-id="2f5d3-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="2f5d3-165">A csatlakoztatott eszközökre nem lehet szükség illesztőprogram telepítésére.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="2f5d3-166">Az összes csatlakoztatott eszköz teljes áramfelvételének 4,5 Energiafogyasztás alatt kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="2f5d3-167">Csatlakozás a Miracasthoz</span><span class="sxs-lookup"><span data-stu-id="2f5d3-167">Connect to Miracast</span></span>

<span data-ttu-id="2f5d3-168">A Miracast használatának lépései a következők:</span><span class="sxs-lookup"><span data-stu-id="2f5d3-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="2f5d3-169">Tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="2f5d3-169">Do one of the following:</span></span>  

   - <span data-ttu-id="2f5d3-170">Nyissa meg **a Start menüt,** és válassza a **Megjelenítés ikont.**</span><span class="sxs-lookup"><span data-stu-id="2f5d3-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="2f5d3-171">Mondja a "Csatlakozás" parancsot, miközben a **Start menüre tekint.**</span><span class="sxs-lookup"><span data-stu-id="2f5d3-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="2f5d3-172">A megjelenő eszközök listájában válasszon ki egy elérhető eszközt.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="2f5d3-173">A kivetítés megkezdéséhez töltse ki a párosítást.</span><span class="sxs-lookup"><span data-stu-id="2f5d3-173">Complete the pairing to begin projecting.</span></span>
