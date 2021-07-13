---
title: Csatlakozás usb Bluetooth-C-eszközök csatlakoztatása
description: A vegyes valóságú eszközökről Bluetooth USB-C-eszközökhöz és -kiegészítőkhez való HoloLens első lépések.
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
ms.openlocfilehash: 5fed56d7a0beeda0a0d96eddc63aaee872f3e52d
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639097"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="0a463-103">Csatlakozás usb Bluetooth-C-eszközök csatlakoztatása</span><span class="sxs-lookup"><span data-stu-id="0a463-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="0a463-104">Eszközök Bluetooth párosítása</span><span class="sxs-lookup"><span data-stu-id="0a463-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="0a463-105">HoloLens 2. a következő osztályokat támogatja a Bluetooth eszközök esetében:</span><span class="sxs-lookup"><span data-stu-id="0a463-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="0a463-106">[HID ::](/windows-hardware/drivers/hid/)</span><span class="sxs-lookup"><span data-stu-id="0a463-106">[HID](/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="0a463-107">Egér</span><span class="sxs-lookup"><span data-stu-id="0a463-107">Mouse</span></span>
    - <span data-ttu-id="0a463-108">Billentyűzet</span><span class="sxs-lookup"><span data-stu-id="0a463-108">Keyboard</span></span>
- <span data-ttu-id="0a463-109">Hangkimeneti (A2DP) eszközök</span><span class="sxs-lookup"><span data-stu-id="0a463-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="0a463-110">HoloLens 2. Bluetooth API-kat támogatja:</span><span class="sxs-lookup"><span data-stu-id="0a463-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="0a463-111">[ÜGYFÉL-kiszolgáló](/windows/uwp/devices-sensors/gatt-server) és [-kiszolgáló](/windows/uwp/devices-sensors/gatt-client)</span><span class="sxs-lookup"><span data-stu-id="0a463-111">GATT [Server](/windows/uwp/devices-sensors/gatt-server) and [Client](/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="0a463-112">Rfcomm</span><span class="sxs-lookup"><span data-stu-id="0a463-112">RFCOMM</span></span>](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="0a463-113">Előfordulhat, hogy telepítenie kell a megfelelő társalkalmazásokat a Microsoft Store, hogy ténylegesen használva legyen a HID és a HOZZÁértő eszközök.</span><span class="sxs-lookup"><span data-stu-id="0a463-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="0a463-114">HoloLens (1. generációs) a következő osztályokat támogatja a Bluetooth eszközök esetében:</span><span class="sxs-lookup"><span data-stu-id="0a463-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="0a463-115">Egér</span><span class="sxs-lookup"><span data-stu-id="0a463-115">Mouse</span></span>
- <span data-ttu-id="0a463-116">Billentyűzet</span><span class="sxs-lookup"><span data-stu-id="0a463-116">Keyboard</span></span>
- [<span data-ttu-id="0a463-117">HoloLens (1. generációs) kattintás</span><span class="sxs-lookup"><span data-stu-id="0a463-117">HoloLens (1st gen) clicker</span></span>](hololens1-clicker.md)

> [!NOTE]
> <span data-ttu-id="0a463-118">Más típusú Bluetooth eszközök, például a beszélők, a headsetek, az okostelefonok és a játékpanelek, az eszközbeállítások között HoloLens listában.</span><span class="sxs-lookup"><span data-stu-id="0a463-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="0a463-119">Ezek az eszközök azonban nem támogatottak a HoloLens (1. generációs) eszközökön.</span><span class="sxs-lookup"><span data-stu-id="0a463-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="0a463-120">További információért tekintse meg a [HoloLens Gépház listázza az eszközöket, de](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)az eszközök nem működnek.</span><span class="sxs-lookup"><span data-stu-id="0a463-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="0a463-121">Billentyűzet vagy Bluetooth párosítása</span><span class="sxs-lookup"><span data-stu-id="0a463-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="0a463-122">Kapcsolja be a billentyűzetet vagy az egeret, és tegye felderíthetővé.</span><span class="sxs-lookup"><span data-stu-id="0a463-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="0a463-123">Ha meg szeretne ismerkedni az eszköz felderítésének mikéntjével, keresse fel az eszközön található információkat (vagy a dokumentációt), vagy keresse fel a gyártó webhelyét.</span><span class="sxs-lookup"><span data-stu-id="0a463-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="0a463-124">Használja a Bloom kézmozdulatot (HoloLens (1. gen)) vagy az indítási kézmozdulatot (HoloLens 2) a **Start** menüre való ugráshoz, majd válassza a **Gépház.**</span><span class="sxs-lookup"><span data-stu-id="0a463-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="0a463-125">Válassza **az Eszközök** lehetőséget, és győződjön meg arról, Bluetooth be van-e va.</span><span class="sxs-lookup"><span data-stu-id="0a463-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="0a463-126">Ha látja az eszköz nevét, válassza a **Pár** lehetőséget, majd kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="0a463-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="0a463-127">Az Bluetooth letiltása</span><span class="sxs-lookup"><span data-stu-id="0a463-127">Disable Bluetooth</span></span>

<span data-ttu-id="0a463-128">Ez az eljárás kikapcsolja a Bluetooth RF-összetevőit, és Bluetooth funkciót a Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0a463-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="0a463-129">Használja a Bloom kézmozdulatot (HoloLens (1. gen)) vagy az indítási kézmozdulatot (HoloLens 2) a **Start** menüre, majd válassza a Gépház  >  **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="0a463-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="0a463-130">Húzza a csúszkakapcsolót **a Bluetooth** a **Ki állásba.**</span><span class="sxs-lookup"><span data-stu-id="0a463-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="0a463-131">HoloLens 2. Csatlakozás USB-C-eszközök</span><span class="sxs-lookup"><span data-stu-id="0a463-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="0a463-132">HoloLens 2. táblázat az USB-C-eszközök következő osztályát támogatja:</span><span class="sxs-lookup"><span data-stu-id="0a463-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="0a463-133">Tömeges tárolóeszközök (például ujjlenyomatos meghajtók)</span><span class="sxs-lookup"><span data-stu-id="0a463-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="0a463-134">Ethernet-adapterek (beleértve az Ethernet+díjszabást)</span><span class="sxs-lookup"><span data-stu-id="0a463-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="0a463-135">USB-C-to-3.5mm digitális hangadapterek</span><span class="sxs-lookup"><span data-stu-id="0a463-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="0a463-136">USB-C digitális audio-headsetek (beleértve a headset-adaptereket és a díjszabást)</span><span class="sxs-lookup"><span data-stu-id="0a463-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="0a463-137">USB-C külső mikrofonok ([Windows Holographic, 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) és újabb verziók)</span><span class="sxs-lookup"><span data-stu-id="0a463-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="0a463-138">Vezetékes egér</span><span class="sxs-lookup"><span data-stu-id="0a463-138">Wired mouse</span></span>
- <span data-ttu-id="0a463-139">Vezetékes billentyűzet</span><span class="sxs-lookup"><span data-stu-id="0a463-139">Wired keyboard</span></span>
- <span data-ttu-id="0a463-140">Kombinált PD hubok (USB A plusz PD-díjszabás)</span><span class="sxs-lookup"><span data-stu-id="0a463-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="0a463-141">Az ügyfelek visszajelzésére válaszul korlátozott támogatást engedélyeztünk a közvetlenül a hálózatra csatlakoztatott mobilhálózati HoloLens USB-C-n keresztül.</span><span class="sxs-lookup"><span data-stu-id="0a463-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="0a463-142">További [Csatlakozás mobilhálózatra és 5G-re](hololens-cellular.md) való adatátvitelről.</span><span class="sxs-lookup"><span data-stu-id="0a463-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="0a463-143">USB-C külső mikrofon támogatása</span><span class="sxs-lookup"><span data-stu-id="0a463-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a463-144">Az USB-mikrofon csatlakoztatása nem lesz automatikusan beállítva **bemeneti eszközként.**</span><span class="sxs-lookup"><span data-stu-id="0a463-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="0a463-145">USB-C-kábelek csatlakoztatása esetén a felhasználók megfigyelhetik, hogy a mikrofon hanganyaga automatikusan a mikrofonhoz lesz átirányítva, de a HoloLens operációs rendszer a belső mikrofontömböt a többi bemeneti eszköz fölé rangsorítja.</span><span class="sxs-lookup"><span data-stu-id="0a463-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="0a463-146">**USB-C mikrofon használata érdekében kövesse az alábbi lépéseket.**</span><span class="sxs-lookup"><span data-stu-id="0a463-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="0a463-147">A külső mikrofonok nem használhatók buildben a [Holographic Windows 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) vagy újabb verziója előtt.</span><span class="sxs-lookup"><span data-stu-id="0a463-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="0a463-148">A felhasználók a Hangbeállítások panelen  választhatnak USB-C-hez csatlakoztatott külső mikrofonokat.</span><span class="sxs-lookup"><span data-stu-id="0a463-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="0a463-149">Az USB-C-mikrofonok hívásra, felvételre stb. használhatók.</span><span class="sxs-lookup"><span data-stu-id="0a463-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="0a463-150">Nyissa meg **a Gépház** alkalmazást, és válassza a **System**  >  **Sound lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="0a463-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Hang Gépház](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="0a463-152">Ha külső mikrofonokat használ a **Remote Assist** segítségével, a felhasználóknak a "Hangeszközök kezelése" hivatkozásra kell kattintanunk.</span><span class="sxs-lookup"><span data-stu-id="0a463-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="0a463-153">Ezután a legördülő menüben állítsa a  külső mikrofont Alapértelmezett vagy **Kommunikációs alapértelmezettre.**</span><span class="sxs-lookup"><span data-stu-id="0a463-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="0a463-154">Az **Alapértelmezett beállítás** azt jelenti, hogy a külső mikrofon mindenhol használatban lesz.</span><span class="sxs-lookup"><span data-stu-id="0a463-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="0a463-155">A **Kommunikáció alapértelmezett beállítása** azt jelenti, hogy a külső mikrofon a Remote Assistben és más kommunikációs alkalmazásokban lesz használva, de a HoloLens mic tömb továbbra is használható más feladatokhoz.</span><span class="sxs-lookup"><span data-stu-id="0a463-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Hangeszközök kezelése](images/usbc-mic-2.png)

<br>

![Mikrofon alapértelmezett beállítása](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="0a463-158">Mi a helyzet a Bluetooth támogatással?</span><span class="sxs-lookup"><span data-stu-id="0a463-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="0a463-159">Sajnos a Bluetooth mikrofonok jelenleg nem támogatottak a 2. HoloLens esetén.</span><span class="sxs-lookup"><span data-stu-id="0a463-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="0a463-160">USB-C hubok</span><span class="sxs-lookup"><span data-stu-id="0a463-160">USB-C Hubs</span></span>

<span data-ttu-id="0a463-161">Előfordulhat, hogy egyes felhasználóknak egyszerre több eszközt is csatlakoztatnia kell.</span><span class="sxs-lookup"><span data-stu-id="0a463-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="0a463-162">Azok a felhasználók, akik [USB-C-mikrofont](#usb-c-external-microphone-support) és egy másik csatlakoztatott eszközt is használni szeretnék, az USB-C hubok az ügyfél igényeihez illeszkedhetnek.</span><span class="sxs-lookup"><span data-stu-id="0a463-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="0a463-163">A Microsoft nem tesztelte ezeket az eszközöket, és nem is ajánlunk semmilyen konkrét márkát.</span><span class="sxs-lookup"><span data-stu-id="0a463-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="0a463-164">**Az USB-C hubra és a csatlakoztatott eszközökre vonatkozó követelmények:**</span><span class="sxs-lookup"><span data-stu-id="0a463-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="0a463-165">A csatlakoztatott eszközökhöz nem szükséges illesztőprogramot telepíteni.</span><span class="sxs-lookup"><span data-stu-id="0a463-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="0a463-166">Az összes csatlakoztatott eszköz teljes energiafogyasztásnak 4,5 Watt alatt kell lennie.</span><span class="sxs-lookup"><span data-stu-id="0a463-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="0a463-167">Csatlakozás a Miracast</span><span class="sxs-lookup"><span data-stu-id="0a463-167">Connect to Miracast</span></span>

<span data-ttu-id="0a463-168">A Miracast kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="0a463-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="0a463-169">Tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="0a463-169">Do one of the following:</span></span>  

   - <span data-ttu-id="0a463-170">Nyissa meg **a Start menüt,** és válassza a **Megjelenítés ikont.**</span><span class="sxs-lookup"><span data-stu-id="0a463-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="0a463-171">Mondja ki Csatlakozás" szót, miközben a **Start menüre tekint.**</span><span class="sxs-lookup"><span data-stu-id="0a463-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="0a463-172">A megjelenő eszközök listájában válasszon ki egy elérhető eszközt.</span><span class="sxs-lookup"><span data-stu-id="0a463-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="0a463-173">A kivetítés megkezdéséhez töltse ki a párosítást.</span><span class="sxs-lookup"><span data-stu-id="0a463-173">Complete the pairing to begin projecting.</span></span>
