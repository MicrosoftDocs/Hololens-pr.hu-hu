---
title: Gyakori forgatókönyvek – Offline biztonságos HoloLens 2
description: Ismerje meg, hogyan állíthat be offline biztonságos üzembe helyezést és alkalmazástelepítési forgatókönyvet a HoloLens-eszközök üzembe helyezéséhez.
keywords: HoloLens, felügyelet, offline, offline biztonságos
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378013"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="cb5b2-104">Gyakori forgatókönyvek – Offline biztonságos HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="cb5b2-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="cb5b2-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="cb5b2-105">Overview</span></span>

<span data-ttu-id="cb5b2-106">Ez az útmutató útmutatást nyújt egy minta kiépítési csomag alkalmazásához, amely le fogja zárni a HoloLens 2-t biztonságos környezetekben való használatra az alábbi korlátozásokkal:</span><span class="sxs-lookup"><span data-stu-id="cb5b2-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="cb5b2-107">Tiltsa le a Wi-Fi-t.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-107">Disable WiFi.</span></span>
-   <span data-ttu-id="cb5b2-108">Tiltsa le a BlueTobellt.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="cb5b2-109">Mikrofonok letiltása.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-109">Disable Microphones.</span></span>
-   <span data-ttu-id="cb5b2-110">Megakadályozza a kiépítési csomagok hozzáadását vagy eltávolítását.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="cb5b2-111">A fenti korlátozott összetevők bármelyikét egyetlen felhasználó sem engedélyezheti.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="cb5b2-112">[![Offline biztonságos forgatókönyv ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="cb5b2-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="cb5b2-113">Előkészítés</span><span class="sxs-lookup"><span data-stu-id="cb5b2-113">Prepare</span></span>

<span data-ttu-id="cb5b2-114">Windows 10 számítógép beállítása</span><span class="sxs-lookup"><span data-stu-id="cb5b2-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="cb5b2-115">[Töltse le a legújabb HoloLens 2 operációsrendszer-fájlt](https://aka.ms/hololens2download) közvetlenül egy számítógépre.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="cb5b2-116">Ennek a konfigurációnak a támogatását az 19041.1117-es és az azt feletti build tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="cb5b2-117">Az Advanced Recovery Companion (ARC) eszköz letöltése/telepítése a [Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) gépre</span><span class="sxs-lookup"><span data-stu-id="cb5b2-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="cb5b2-118">Töltse le/telepítse a [windowsos konfigurációtervező (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) legújabb eszközét a Microsoft Store gépére.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="cb5b2-119">[Töltse le a OfflineSecureHL2_Sample mappát a projektfájlokkal](https://aka.ms/HoloLensDocs-SecureOfflineSample) együtt a PPKG felépítéséhez.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="cb5b2-120">Készítse elő az offline [Line of Business alkalmazást a PPKG üzembe helyezéséhez.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="cb5b2-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="cb5b2-121">Konfigurálás</span><span class="sxs-lookup"><span data-stu-id="cb5b2-121">Configure</span></span>

<span data-ttu-id="cb5b2-122">Biztonságos konfiguráció kiépítési csomagjának összeállítása</span><span class="sxs-lookup"><span data-stu-id="cb5b2-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="cb5b2-123">Indítsa el a WCD eszközt a számítógépén.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="cb5b2-124">Válassza **a File -> Open project (Projekt megnyitása) lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="cb5b2-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="cb5b2-125">Navigáljon a korábban mentett OfflineSecureHL2_Sample mappához, és válassza a következőt: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="cb5b2-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="cb5b2-126">Meg kell nyitnia a projektet, és meg kell lennie az Elérhető testreszabások listájának:</span><span class="sxs-lookup"><span data-stu-id="cb5b2-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cb5b2-127">![Képernyőkép a WCD-ben megnyitott konfigurációs csomagról](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="cb5b2-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="cb5b2-128">Az ebben a kiépítési csomagban beállított konfigurációk:</span><span class="sxs-lookup"><span data-stu-id="cb5b2-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="cb5b2-129">Elem</span><span class="sxs-lookup"><span data-stu-id="cb5b2-129">Item</span></span>                                                |     <span data-ttu-id="cb5b2-130">Beállítás</span><span class="sxs-lookup"><span data-stu-id="cb5b2-130">Setting</span></span>                       |     <span data-ttu-id="cb5b2-131">Leírás</span><span class="sxs-lookup"><span data-stu-id="cb5b2-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="cb5b2-132">Fiókok / Felhasználók</span><span class="sxs-lookup"><span data-stu-id="cb5b2-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="cb5b2-133">Helyi felhasználónév és & jelszó</span><span class="sxs-lookup"><span data-stu-id="cb5b2-133">Local User Name & Password</span></span>    |     <span data-ttu-id="cb5b2-134">Ezekhez az offline eszközökhöz egyetlen felhasználónevet és jelszót kell beállítani és megosztani az eszköz összes felhasználója számára.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="cb5b2-135">Első élmény / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="cb5b2-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="cb5b2-136">Igaz</span><span class="sxs-lookup"><span data-stu-id="cb5b2-136">True</span></span>                          |     <span data-ttu-id="cb5b2-137">Csak a kezdeti eszközbeállítás során hagyja ki a hitelesítést</span><span class="sxs-lookup"><span data-stu-id="cb5b2-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="cb5b2-138">Első élmény / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="cb5b2-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="cb5b2-139">Igaz</span><span class="sxs-lookup"><span data-stu-id="cb5b2-139">True</span></span>                          |     <span data-ttu-id="cb5b2-140">Kihagyja az eszköz betanítása a kezdeti eszközbeállítás során</span><span class="sxs-lookup"><span data-stu-id="cb5b2-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="cb5b2-141">Első tapasztalat / HoloLens / Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="cb5b2-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="cb5b2-142">Igaz</span><span class="sxs-lookup"><span data-stu-id="cb5b2-142">True</span></span>                          |     <span data-ttu-id="cb5b2-143">Kihagyja Wi-Fi konfigurációs lépését a kezdeti eszközbeállítás során</span><span class="sxs-lookup"><span data-stu-id="cb5b2-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="cb5b2-144">Szabályzatok/Kapcsolatok/AllowBlueto adat</span><span class="sxs-lookup"><span data-stu-id="cb5b2-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="cb5b2-145">Nem</span><span class="sxs-lookup"><span data-stu-id="cb5b2-145">No</span></span>                            |     <span data-ttu-id="cb5b2-146">A Bluetooth letiltása</span><span class="sxs-lookup"><span data-stu-id="cb5b2-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="cb5b2-147">Szabályzatok/Tapasztalat/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="cb5b2-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="cb5b2-148">Nem</span><span class="sxs-lookup"><span data-stu-id="cb5b2-148">No</span></span>                            |     <span data-ttu-id="cb5b2-149">Letiltja Cortanát (a lehetséges problémák kiküszöböléséhez, mivel a mikrofonok le vannak tiltva)</span><span class="sxs-lookup"><span data-stu-id="cb5b2-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="cb5b2-150">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="cb5b2-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="cb5b2-151">Igen</span><span class="sxs-lookup"><span data-stu-id="cb5b2-151">Yes</span></span>                           |     <span data-ttu-id="cb5b2-152">Letiltja a mikrofont</span><span class="sxs-lookup"><span data-stu-id="cb5b2-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="cb5b2-153">Szabályzatok/adatvédelem/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="cb5b2-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="cb5b2-154">Megtagadás kényszerítve</span><span class="sxs-lookup"><span data-stu-id="cb5b2-154">Force deny</span></span>                    |     <span data-ttu-id="cb5b2-155">Megakadályozza, hogy az alkalmazások hozzáférjenek a helyadatokhoz (a lehetséges problémák kiküszöbölése érdekében, mivel a helykövetés le van tiltva)</span><span class="sxs-lookup"><span data-stu-id="cb5b2-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="cb5b2-156">Szabályzatok/Adatvédelem/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="cb5b2-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="cb5b2-157">Megtagadás kényszerítve</span><span class="sxs-lookup"><span data-stu-id="cb5b2-157">Force deny</span></span>                    |     <span data-ttu-id="cb5b2-158">Megakadályozza, hogy az alkalmazások hozzáférjenek a mikrofonhoz (a lehetséges problémák kiküszöbölése érdekében, mivel a mikrofonok le vannak tiltva)</span><span class="sxs-lookup"><span data-stu-id="cb5b2-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="cb5b2-159">Policies/Security/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="cb5b2-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="cb5b2-160">Nem</span><span class="sxs-lookup"><span data-stu-id="cb5b2-160">No</span></span>                            |     <span data-ttu-id="cb5b2-161">Megakadályozza, hogy bárki olyan kiépítési csomagokat adjon hozzá, amelyek megpróbálhatják felülbírálni a zárolt szabályzatokat.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="cb5b2-162">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="cb5b2-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="cb5b2-163">Nem</span><span class="sxs-lookup"><span data-stu-id="cb5b2-163">No</span></span>                            |     <span data-ttu-id="cb5b2-164">Megakadályozza, hogy bárki eltávolítsa ezt a zárolt kiépítési csomagot.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="cb5b2-165">Házirendek/Rendszer/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="cb5b2-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="cb5b2-166">Nem</span><span class="sxs-lookup"><span data-stu-id="cb5b2-166">No</span></span>                            |     <span data-ttu-id="cb5b2-167">Megakadályozza, hogy az eszköz helyadatokat kövessen nyomon.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="cb5b2-168">Szabályzatok/Wi-Fi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="cb5b2-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="cb5b2-169">Nem</span><span class="sxs-lookup"><span data-stu-id="cb5b2-169">No</span></span>                            |     <span data-ttu-id="cb5b2-170">Letiltja a Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="cb5b2-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="cb5b2-171">A Futásidejű beállítások alatt válassza a **Fiókok / Felhasználók / Felhasználónév: Holo / Jelszó lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="cb5b2-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="cb5b2-172">Jegyezze fel a jelszót, és szükség esetén állítsa alaphelyzetbe.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="cb5b2-173">Lépjen a UniversalAppInstall /UserContextApp lapra, és konfigurálja az ezen eszközökre telepíteni fog [LOB](app-deploy-provisioning-package.md) alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cb5b2-174">![Az alkalmazás WCD-ben való hozzáadásának helyének képernyőképe.](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="cb5b2-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="cb5b2-175">Ha elkészült, válassza az "Exportálás" gombot, és kövesse az összes kérést, amíg létre nem jön a kiépítési csomag.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cb5b2-176">![Képernyőkép a csomag Exportálás gombjáról a WCD-ben.](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="cb5b2-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="cb5b2-177">Üzembe helyezés</span><span class="sxs-lookup"><span data-stu-id="cb5b2-177">Deploy</span></span>

1. <span data-ttu-id="cb5b2-178">Csatlakoztassa a HL2-t a Windows 10 számítógépéhez USB-kábelen keresztül.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="cb5b2-179">Indítsa el az ARC eszközt, és válassza a **HoloLens 2 lehetőséget**</span><span class="sxs-lookup"><span data-stu-id="cb5b2-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![A HoloLens 2 tiszta perjeles kezdőképernyője](images/ARC2.png)

1. <span data-ttu-id="cb5b2-181">A következő képernyőn válassza a **Manuális csomagválasztás lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="cb5b2-181">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 ARC információs képernyő](images/arc_device_info.png)

1. <span data-ttu-id="cb5b2-183">Keresse meg a korábban letöltött .ffu fájlt, és válassza a **Megnyitás lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="cb5b2-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="cb5b2-184">A Figyelmeztetés lapon válassza a Folytatás **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="cb5b2-184">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 ARC figyelmeztető képernyő](images/arc_warning.png)

1. <span data-ttu-id="cb5b2-186">Várja meg, amíg az ARC eszköz befejezi a HoloLens 2 operációs rendszer telepítését.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="cb5b2-187">Miután az eszköz befejezte a telepítést és elindul a rendszer, lépjen a Fájlkezelő könyvtárba, és másolja a korábban mentett PPKG-fájlt az eszközmappába.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cb5b2-188">![PPKG-fájl a számítógépen Fájlkezelő ablakban.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="cb5b2-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="cb5b2-189">A HoloLens 2-ben nyomja le a következő gomb kombinált gombra a kiépítési csomag futtatásához: Koppintson egyszerre a **Kötet** le és a **Bekapcsológomb** gombra.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="cb5b2-190">A rendszer kérni fogja a kiépítési csomag alkalmazását, majd válassza a **Megerősítés lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="cb5b2-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="cb5b2-191">Ha a kiépítési csomag befejeződött, kattintson az **OK gombra.**</span><span class="sxs-lookup"><span data-stu-id="cb5b2-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="cb5b2-192">Ezután be kell jelentkeznie az eszközre a megosztott helyi fiókkal és jelszóval.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="cb5b2-193">Karbantartás</span><span class="sxs-lookup"><span data-stu-id="cb5b2-193">Maintain</span></span>

<span data-ttu-id="cb5b2-194">Ezzel a konfigurációval javasoljuk, hogy indítsa újra a fenti folyamatot, és perjelelje újra az eszközt az ARC eszközzel, és alkalmaz egy új PPKG-t az operációs rendszer és/vagy alkalmazás(ek) frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="cb5b2-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
