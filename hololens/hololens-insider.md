---
title: Belső előzetes verzió a Microsoft HoloLens
description: Ismerje meg az Insider-buildek első lépéseit, és adjon értékes visszajelzést a HoloLens következő jelentős operációsrendszer-frissítésével kapcsolatban.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977224"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="3d660-103">Belső előzetes verzió a Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="3d660-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="3d660-104">Üdvözöljük a HoloLens legújabb Insider Preview buildjeiben!</span><span class="sxs-lookup"><span data-stu-id="3d660-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="3d660-105">Egyszerűen elkezdheti [](hololens-insider.md#start-receiving-insider-builds) a rendszert, és értékes visszajelzést adhat a HoloLens következő jelentős operációsrendszer-frissítésével kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="3d660-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="3d660-106">Windows Insider kibocsátási megjegyzések</span><span class="sxs-lookup"><span data-stu-id="3d660-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="3d660-107">Izgatottan várjuk, hogy ismét új funkciókkal kezdhetjük el a Windows Insiderst.</span><span class="sxs-lookup"><span data-stu-id="3d660-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="3d660-108">Az új buildek a fejlesztői és bétaverziós csatornákra lesznek felkísértve a legújabb frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="3d660-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="3d660-109">Ezt az oldalt folyamatosan frissítjük, ahogy további funkciókat és frissítéseket adunk hozzá a Windows Insider buildhez.</span><span class="sxs-lookup"><span data-stu-id="3d660-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="3d660-110">Legyen izgatott, és készen áll arra, hogy ezeket a frissítéseket a valóságba keverje.</span><span class="sxs-lookup"><span data-stu-id="3d660-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="3d660-111">Szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="3d660-111">Feature</span></span>                 | <span data-ttu-id="3d660-112">Leírás</span><span class="sxs-lookup"><span data-stu-id="3d660-112">Description</span></span>                | <span data-ttu-id="3d660-113">Célfelhasználók</span><span class="sxs-lookup"><span data-stu-id="3d660-113">Target Users</span></span> | <span data-ttu-id="3d660-114">Build bevezetve</span><span class="sxs-lookup"><span data-stu-id="3d660-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| <span data-ttu-id="3d660-115">CSP-módosítások a HoloLensben</span><span class="sxs-lookup"><span data-stu-id="3d660-115">CSP Changes on HoloLens</span></span> | <span data-ttu-id="3d660-116">Új CSP-k az adatok lekérdezéséhez</span><span class="sxs-lookup"><span data-stu-id="3d660-116">New CSPs for to query data</span></span> | <span data-ttu-id="3d660-117">It-rendszergazdák</span><span class="sxs-lookup"><span data-stu-id="3d660-117">IT Admins</span></span>    | <span data-ttu-id="3d660-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="3d660-118">20348.1403</span></span>                 |

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="3d660-119">CSP-módosítások a HoloLensben</span><span class="sxs-lookup"><span data-stu-id="3d660-119">CSP changes on HoloLens</span></span>

- <span data-ttu-id="3d660-120">A 20348 Windows Insider.1403-as buildben bevezetett</span><span class="sxs-lookup"><span data-stu-id="3d660-120">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="3d660-121">DevDetail CSP</span><span class="sxs-lookup"><span data-stu-id="3d660-121">DevDetail CSP</span></span>

<span data-ttu-id="3d660-122">A DevDetail CSP mostantól a HoloLens-eszközön található szabad tárterületet is jelenti.</span><span class="sxs-lookup"><span data-stu-id="3d660-122">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="3d660-123">Ennek nagyjából meg kell egyeznie a Beállítások alkalmazás Tárterület lapján látható értékkel.</span><span class="sxs-lookup"><span data-stu-id="3d660-123">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="3d660-124">Az alábbiakban az ezt az információt tartalmazó csomópont található.</span><span class="sxs-lookup"><span data-stu-id="3d660-124">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="3d660-125">./DevDetail/Ext/Microsoft/FreeStorage (csak GET művelet)</span><span class="sxs-lookup"><span data-stu-id="3d660-125">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="3d660-126">DeviceStatus CSP</span><span class="sxs-lookup"><span data-stu-id="3d660-126">DeviceStatus CSP</span></span>

<span data-ttu-id="3d660-127">A DeviceStatus CSP mostantól arról az SSID-ről és BSSID-ről is jelentést készít, amelyhez a HoloLens aktívan csatlakozik.</span><span class="sxs-lookup"><span data-stu-id="3d660-127">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="3d660-128">A következő csomópontok tartalmazzák ezt az információt.</span><span class="sxs-lookup"><span data-stu-id="3d660-128">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="3d660-129">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-cím* Wi-Fi /SSID</span><span class="sxs-lookup"><span data-stu-id="3d660-129">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="3d660-130">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span><span class="sxs-lookup"><span data-stu-id="3d660-130">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="3d660-131">Példa syncml blobra (MDM-szállítók számára) a NetworkIdentifiers lekérdezéséhez</span><span class="sxs-lookup"><span data-stu-id="3d660-131">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a><span data-ttu-id="3d660-132">Javítások és fejlesztések:</span><span class="sxs-lookup"><span data-stu-id="3d660-132">Fixes and improvements:</span></span>

- <span data-ttu-id="3d660-133">Kijavítottunk egy ismert hibát, Eszközportál amikor nem volt [rákérdezés zárolt fájlok letöltésére.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="3d660-133">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="3d660-134">Kijavítottunk egy ismert hibát, amely Eszközportál és letöltés időkorrekta [miatt ki volt javítva.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="3d660-134">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="3d660-135">Insider-buildek fogadásának kezdete</span><span class="sxs-lookup"><span data-stu-id="3d660-135">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="3d660-136">Ha a közelmúltban nem frissített, indítsa újra az eszközt az állapot frissítéséhez, és szerezze be a legújabb buildet.</span><span class="sxs-lookup"><span data-stu-id="3d660-136">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="3d660-137">Az "Eszköz újraindítása" hangparancs jól működik.</span><span class="sxs-lookup"><span data-stu-id="3d660-137">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="3d660-138">Az Újraindítás gombot a Beállítások/beállítások Windows Insider Program.</span><span class="sxs-lookup"><span data-stu-id="3d660-138">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="3d660-139">Előfordulhat, hogy egy hiba történt a háttéren, amely miatt ön is találkozhatott, így újra a útjára fog menni.</span><span class="sxs-lookup"><span data-stu-id="3d660-139">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="3d660-140">HoloLens 2-eszközön válassza a Settings Update & Security Windows Insider Program ( Első lépések)  >    >   **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="3d660-140">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="3d660-141">Csatolja a regisztrációhoz használt fiókot Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="3d660-141">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="3d660-142">A Windows Insider most már a Csatornákra költözik.</span><span class="sxs-lookup"><span data-stu-id="3d660-142">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="3d660-143">A **Gyors** kör lesz a **Fejlesztői** csatorna, a **Lassú** kör lesz a **Béta csatorna,** a Kiadási **előnézeti** kör pedig a Kiadás **előnézete csatorna** lesz.</span><span class="sxs-lookup"><span data-stu-id="3d660-143">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="3d660-144">A leképezés a következő: Windows Insider magyarázata További információ: Introducing Windows Insider Channels on Windows Blogs (A Windows blogok Windows Insider ![ ](images/WindowsInsiderChannels.png) [csatornái).](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)</span><span class="sxs-lookup"><span data-stu-id="3d660-144">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="3d660-145">Ezután válassza a **Windows** aktív fejlesztése lehetőséget, válassza ki, hogy szeretné-e fogadni a **Dev Channelt** vagy Béta csatorna **buildeket,** és tekintse át a program feltételeit.</span><span class="sxs-lookup"><span data-stu-id="3d660-145">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="3d660-146">A **befejezéshez válassza > Újraindítás most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3d660-146">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="3d660-147">Az eszköz újraindítása után a Settings (Beállítások) > **Update & Security > Check for updates** to get the latest build (Frissítések keresése a legújabb buildhez) lapon.</span><span class="sxs-lookup"><span data-stu-id="3d660-147">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="3d660-148">Hiba 0x80070490 hiba a hiba körül</span><span class="sxs-lookup"><span data-stu-id="3d660-148">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="3d660-149">Ha frissítési hibát 0x80070490 a Dev vagy a Beta csatornán való frissítéskor, próbálkozzon a következő rövid távú munkával.</span><span class="sxs-lookup"><span data-stu-id="3d660-149">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="3d660-150">Ez magában foglalja a belső csatorna áthelyezését, a frissítés be- és áthelyezését, majd az Insider-csatorna vissza mozgatát.</span><span class="sxs-lookup"><span data-stu-id="3d660-150">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="3d660-151">Első fázis – Előzetes kiadás</span><span class="sxs-lookup"><span data-stu-id="3d660-151">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="3d660-152">Beállítások, Biztonsági & frissítése, majd Windows Insider Program a Kiadási előzetes **csatorna lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="3d660-152">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="3d660-153">Beállítások, Biztonsági & frissítése, Windows Update, **Frissítések keresése.**</span><span class="sxs-lookup"><span data-stu-id="3d660-153">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="3d660-154">A frissítés után folytassa a második fázisra.</span><span class="sxs-lookup"><span data-stu-id="3d660-154">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="3d660-155">Második fázis – Fejlesztői csatorna</span><span class="sxs-lookup"><span data-stu-id="3d660-155">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="3d660-156">Beállítások, Biztonsági & frissítése, Windows Insider Program válassza a **Dev Channel lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="3d660-156">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="3d660-157">Beállítások, Biztonsági & frissítése, Windows Update, **Frissítések keresése.**</span><span class="sxs-lookup"><span data-stu-id="3d660-157">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="3d660-158">FFU letöltési és flash utasítások</span><span class="sxs-lookup"><span data-stu-id="3d660-158">FFU download and flash directions</span></span>
<span data-ttu-id="3d660-159">Az aláírt ffu repülőjárattal való teszteléshez először fel kell oldania az eszköz zárolását, mielőtt felrakná a repülőjárat aláírt ffu-ját.</span><span class="sxs-lookup"><span data-stu-id="3d660-159">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="3d660-160">Pc-n:</span><span class="sxs-lookup"><span data-stu-id="3d660-160">On PC:</span></span>
    1. <span data-ttu-id="3d660-161">Töltse le a ffu-t a számítógépére a [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) ről.</span><span class="sxs-lookup"><span data-stu-id="3d660-161">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="3d660-162">Telepítse az ARC-t (Advanced Recovery Companion) a Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="3d660-162">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="3d660-163">A HoloLens – Flight Unlock: Open  >  **Settings Update & Security**  >  **Windows Insider Program** majd regisztráljon, indítsa újra az eszközt.</span><span class="sxs-lookup"><span data-stu-id="3d660-163">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="3d660-164">Flash FFU – Most már az ARC használatával is meg flashlheti a repülőjárat aláírt FFU-ját.</span><span class="sxs-lookup"><span data-stu-id="3d660-164">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="3d660-165">Visszajelzés küldése és problémák jelentése</span><span class="sxs-lookup"><span data-stu-id="3d660-165">Provide feedback and report issues</span></span>
<span data-ttu-id="3d660-166">A HoloLensen Visszajelzési központ [alkalmazással](hololens-feedback.md) visszajelzést küldhet, és jelentést küldhet a problémákról.</span><span class="sxs-lookup"><span data-stu-id="3d660-166">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="3d660-167">A Visszajelzési központ biztosítja, hogy minden szükséges diagnosztikai információ bekerül a hibakeresésbe és a probléma megoldásához.</span><span class="sxs-lookup"><span data-stu-id="3d660-167">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="3d660-168">A HoloLens kínai és japán verziójával kapcsolatos problémákat ugyanúgy kell jelenteni.</span><span class="sxs-lookup"><span data-stu-id="3d660-168">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="3d660-169">Mindenképpen fogadja el azt a kérdést, amely megkérdezi, hogy szeretné Visszajelzési központ szeretné-e elérni a Dokumentumok mappát (válassza az **Igen** lehetőséget, amikor a rendszer kéri).</span><span class="sxs-lookup"><span data-stu-id="3d660-169">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="3d660-170">Megjegyzés fejlesztőknek</span><span class="sxs-lookup"><span data-stu-id="3d660-170">Note for developers</span></span>
<span data-ttu-id="3d660-171">Nyugodtan kipróbálhatja alkalmazásait a HoloLens Insider buildjére építve.</span><span class="sxs-lookup"><span data-stu-id="3d660-171">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="3d660-172">Az első lépésekhez tekintse meg a [HoloLens fejlesztői](https://developer.microsoft.com/windows/mixed-reality/development) dokumentációját.</span><span class="sxs-lookup"><span data-stu-id="3d660-172">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="3d660-173">Ugyanezek az utasítások működnek a HoloLens Insider-buildjén is.</span><span class="sxs-lookup"><span data-stu-id="3d660-173">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="3d660-174">Használhatja a Unity ugyanazon buildjéhez és Visual Studio, mint a HoloLens-fejlesztéshez.</span><span class="sxs-lookup"><span data-stu-id="3d660-174">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="3d660-175">Insider-buildek fogadásának leállítása</span><span class="sxs-lookup"><span data-stu-id="3d660-175">Stop receiving Insider builds</span></span>
<span data-ttu-id="3d660-176">Ha már nem szeretné megkapni a Windows Holographic Insider-buildjét, kikapcsolhatja, ha a HoloLens éles buildet futtat, vagy az Advanced Recovery Companion segítségével helyreállíthatja az eszközt a Windows Holographic nem insider verziójára. [](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="3d660-176">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="3d660-177">Megjelenik egy ismert probléma, amely miatt az Insider Preview buildre való regisztrációt manuálisan újratelepítő felhasználók kék képernyőt tapasztalnak.</span><span class="sxs-lookup"><span data-stu-id="3d660-177">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="3d660-178">Ezt követően manuálisan kell helyreállítania az eszközt.</span><span class="sxs-lookup"><span data-stu-id="3d660-178">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="3d660-179">Ha szeretne többet tudni arról, hogy ez hatással lenne-e az Ön számára, tekintse meg ezt az ismert [problémát.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="3d660-179">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="3d660-180">Annak ellenőrzése, hogy a HoloLens éles buildet futtat-e:</span><span class="sxs-lookup"><span data-stu-id="3d660-180">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="3d660-181">A Settings **(Beállítások) > System > About (A** rendszerről) lapon keresse meg a build számát.</span><span class="sxs-lookup"><span data-stu-id="3d660-181">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="3d660-182">[Tekintse meg az éles buildszámok kibocsátási megjegyzéseit.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="3d660-182">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="3d660-183">Az Insider-buildek lemondása:</span><span class="sxs-lookup"><span data-stu-id="3d660-183">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="3d660-184">Éles buildet futtató HoloLensen válassza a Beállítások > **Update & Security > Windows Insider Program** lehetőséget, és válassza a Stop **Insider builds** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3d660-184">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="3d660-185">Az eszköz lemondáshoz kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="3d660-185">Follow the instructions to opt out your device.</span></span>
