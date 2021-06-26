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
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924366"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="9888b-103">Belső előzetes verzió a Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="9888b-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="9888b-104">Üdvözöljük a HoloLens legújabb Insider Preview buildjeiben!</span><span class="sxs-lookup"><span data-stu-id="9888b-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="9888b-105">Egyszerűen elkezdheti [](hololens-insider.md#start-receiving-insider-builds) a rendszert, és értékes visszajelzést adhat a HoloLens következő jelentős operációsrendszer-frissítésével kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="9888b-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="9888b-106">Windows Insider kibocsátási megjegyzések</span><span class="sxs-lookup"><span data-stu-id="9888b-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="9888b-107">Izgatottan várjuk, hogy ismét új funkciókkal kezdhetjük el a Windows Insiderst.</span><span class="sxs-lookup"><span data-stu-id="9888b-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="9888b-108">Az új buildek a fejlesztői és bétaverziós csatornákra lesznek felkísértve a legújabb frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="9888b-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="9888b-109">Ezt az oldalt folyamatosan frissítjük, ahogy további funkciókat és frissítéseket adunk hozzá a Windows Insider buildhez.</span><span class="sxs-lookup"><span data-stu-id="9888b-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="9888b-110">Legyen izgatott, és készen áll arra, hogy ezeket a frissítéseket a valóságba keverje.</span><span class="sxs-lookup"><span data-stu-id="9888b-110">Get excited and ready to mix these updates into your reality.</span></span> 

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="9888b-111">CSP-módosítások a HoloLensben</span><span class="sxs-lookup"><span data-stu-id="9888b-111">CSP changes on HoloLens</span></span>
 
- <span data-ttu-id="9888b-112">A 20348 Windows Insider.1403-as buildben bevezetett</span><span class="sxs-lookup"><span data-stu-id="9888b-112">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="9888b-113">DevDetail CSP</span><span class="sxs-lookup"><span data-stu-id="9888b-113">DevDetail CSP</span></span>

<span data-ttu-id="9888b-114">A DevDetail CSP mostantól a HoloLens-eszközön található szabad tárterületet is jelenti.</span><span class="sxs-lookup"><span data-stu-id="9888b-114">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="9888b-115">Ennek nagyjából meg kell egyeznie a Beállítások alkalmazás Tárterület lapján látható értékkel.</span><span class="sxs-lookup"><span data-stu-id="9888b-115">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="9888b-116">Az alábbiakban az ezt az információt tartalmazó csomópont található.</span><span class="sxs-lookup"><span data-stu-id="9888b-116">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="9888b-117">./DevDetail/Ext/Microsoft/FreeStorage (csak GET művelet)</span><span class="sxs-lookup"><span data-stu-id="9888b-117">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="9888b-118">DeviceStatus CSP</span><span class="sxs-lookup"><span data-stu-id="9888b-118">DeviceStatus CSP</span></span>

<span data-ttu-id="9888b-119">A DeviceStatus CSP mostantól arról az SSID-ről és BSSID-ről is jelentést készít, amelyhez a HoloLens aktívan csatlakozik.</span><span class="sxs-lookup"><span data-stu-id="9888b-119">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="9888b-120">A következő csomópontok tartalmazzák ezt az információt.</span><span class="sxs-lookup"><span data-stu-id="9888b-120">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="9888b-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-cím* Wi-Fi /SSID</span><span class="sxs-lookup"><span data-stu-id="9888b-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="9888b-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span><span class="sxs-lookup"><span data-stu-id="9888b-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="9888b-123">Példa syncml blobra (MDM-szállítók számára) a NetworkIdentifiers lekérdezéséhez</span><span class="sxs-lookup"><span data-stu-id="9888b-123">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

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

### <a name="fixes-and-improvements"></a><span data-ttu-id="9888b-124">Javítások és fejlesztések:</span><span class="sxs-lookup"><span data-stu-id="9888b-124">Fixes and improvements:</span></span>

- <span data-ttu-id="9888b-125">Kijavítottunk egy ismert hibát, Eszközportál amikor nem volt [rákérdezés zárolt fájlok letöltésére.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="9888b-125">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="9888b-126">Kijavítottunk egy ismert hibát, amely Eszközportál és letöltés időkorrekta [miatt ki volt javítva.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="9888b-126">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="9888b-127">Insider-buildek fogadásának kezdete</span><span class="sxs-lookup"><span data-stu-id="9888b-127">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="9888b-128">Ha a közelmúltban nem frissített, indítsa újra az eszközt az állapot frissítéséhez, és szerezze be a legújabb buildet.</span><span class="sxs-lookup"><span data-stu-id="9888b-128">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="9888b-129">Az "Eszköz újraindítása" hangparancs jól működik.</span><span class="sxs-lookup"><span data-stu-id="9888b-129">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="9888b-130">Az Újraindítás gombot a Beállítások/beállítások Windows Insider Program.</span><span class="sxs-lookup"><span data-stu-id="9888b-130">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="9888b-131">Előfordulhat, hogy egy hiba történt a háttéren, amely miatt ön is találkozhatott, így újra a útjára fog menni.</span><span class="sxs-lookup"><span data-stu-id="9888b-131">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="9888b-132">HoloLens 2-eszközön válassza a Settings Update & Security Windows Insider Program ( Első lépések)  >    >   **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="9888b-132">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="9888b-133">Csatolja a regisztrációhoz használt fiókot Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="9888b-133">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="9888b-134">A Windows Insider most már a Csatornákra költözik.</span><span class="sxs-lookup"><span data-stu-id="9888b-134">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="9888b-135">A **Gyors** kör lesz a **Fejlesztői** csatorna, a **Lassú** kör lesz a **Béta csatorna,** a Kiadási **előnézeti** kör pedig a Kiadás **előnézete csatorna** lesz.</span><span class="sxs-lookup"><span data-stu-id="9888b-135">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="9888b-136">A leképezés a következő: Windows Insider magyarázata További információ: Introducing Windows Insider Channels on Windows Blogs (A Windows blogok Windows Insider ![ ](images/WindowsInsiderChannels.png) [csatornái).](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)</span><span class="sxs-lookup"><span data-stu-id="9888b-136">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="9888b-137">Ezután válassza a **Windows** aktív fejlesztése lehetőséget, válassza ki, hogy szeretné-e fogadni a **Dev Channelt** vagy Béta csatorna **buildeket,** és tekintse át a program feltételeit.</span><span class="sxs-lookup"><span data-stu-id="9888b-137">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="9888b-138">A **befejezéshez válassza > Újraindítás most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9888b-138">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="9888b-139">Az eszköz újraindítása után a Settings (Beállítások) > **Update & Security > Check for updates** to get the latest build (Frissítések keresése a legújabb buildhez) lapon.</span><span class="sxs-lookup"><span data-stu-id="9888b-139">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="9888b-140">Hiba 0x80070490 hiba a hiba körül</span><span class="sxs-lookup"><span data-stu-id="9888b-140">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="9888b-141">Ha frissítési hibát 0x80070490 a Dev vagy a Beta csatornán való frissítéskor, próbálkozzon a következő rövid távú munkával.</span><span class="sxs-lookup"><span data-stu-id="9888b-141">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="9888b-142">Ez magában foglalja a belső csatorna áthelyezését, a frissítés be- és áthelyezését, majd az Insider-csatorna vissza mozgatát.</span><span class="sxs-lookup"><span data-stu-id="9888b-142">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="9888b-143">Első fázis – Előzetes kiadás</span><span class="sxs-lookup"><span data-stu-id="9888b-143">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="9888b-144">Beállítások, Biztonsági & frissítése, majd Windows Insider Program a Kiadási előzetes **csatorna lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="9888b-144">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="9888b-145">Beállítások, Biztonsági & frissítése, Windows Update, **Frissítések keresése.**</span><span class="sxs-lookup"><span data-stu-id="9888b-145">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="9888b-146">A frissítés után folytassa a második fázisra.</span><span class="sxs-lookup"><span data-stu-id="9888b-146">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="9888b-147">Második fázis – Fejlesztői csatorna</span><span class="sxs-lookup"><span data-stu-id="9888b-147">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="9888b-148">Beállítások, Biztonsági & frissítése, Windows Insider Program válassza a **Dev Channel lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="9888b-148">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="9888b-149">Beállítások, Biztonsági & frissítése, Windows Update, **Frissítések keresése.**</span><span class="sxs-lookup"><span data-stu-id="9888b-149">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="9888b-150">FFU letöltési és flash utasítások</span><span class="sxs-lookup"><span data-stu-id="9888b-150">FFU download and flash directions</span></span>
<span data-ttu-id="9888b-151">Az aláírt ffu repülőjárattal való teszteléshez először fel kell oldania az eszköz zárolását, mielőtt felrakná a repülőjárat aláírt ffu-ját.</span><span class="sxs-lookup"><span data-stu-id="9888b-151">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="9888b-152">Pc-n:</span><span class="sxs-lookup"><span data-stu-id="9888b-152">On PC:</span></span>
    1. <span data-ttu-id="9888b-153">Töltse le a ffu-t a számítógépére a [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) ről.</span><span class="sxs-lookup"><span data-stu-id="9888b-153">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="9888b-154">Telepítse az ARC-t (Advanced Recovery Companion) a Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="9888b-154">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="9888b-155">A HoloLens – Flight Unlock: Open  >  **Settings Update & Security**  >  **Windows Insider Program** majd regisztráljon, indítsa újra az eszközt.</span><span class="sxs-lookup"><span data-stu-id="9888b-155">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="9888b-156">Flash FFU – Most már az ARC használatával is meg flashlheti a repülőjárat aláírt FFU-ját.</span><span class="sxs-lookup"><span data-stu-id="9888b-156">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="9888b-157">Visszajelzés küldése és problémák jelentése</span><span class="sxs-lookup"><span data-stu-id="9888b-157">Provide feedback and report issues</span></span>
<span data-ttu-id="9888b-158">A HoloLensen Visszajelzési központ [alkalmazással](hololens-feedback.md) visszajelzést küldhet, és jelentést küldhet a problémákról.</span><span class="sxs-lookup"><span data-stu-id="9888b-158">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="9888b-159">A Visszajelzési központ biztosítja, hogy minden szükséges diagnosztikai információ bekerül a hibakeresésbe és a probléma megoldásához.</span><span class="sxs-lookup"><span data-stu-id="9888b-159">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="9888b-160">A HoloLens kínai és japán verziójával kapcsolatos problémákat ugyanúgy kell jelenteni.</span><span class="sxs-lookup"><span data-stu-id="9888b-160">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="9888b-161">Mindenképpen fogadja el azt a kérdést, amely megkérdezi, hogy szeretné Visszajelzési központ szeretné-e elérni a Dokumentumok mappát (válassza az **Igen** lehetőséget, amikor a rendszer kéri).</span><span class="sxs-lookup"><span data-stu-id="9888b-161">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="9888b-162">Megjegyzés fejlesztőknek</span><span class="sxs-lookup"><span data-stu-id="9888b-162">Note for developers</span></span>
<span data-ttu-id="9888b-163">Nyugodtan kipróbálhatja alkalmazásait a HoloLens Insider buildjére építve.</span><span class="sxs-lookup"><span data-stu-id="9888b-163">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="9888b-164">Az első lépésekhez tekintse meg a [HoloLens fejlesztői](https://developer.microsoft.com/windows/mixed-reality/development) dokumentációját.</span><span class="sxs-lookup"><span data-stu-id="9888b-164">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="9888b-165">Ugyanezek az utasítások működnek a HoloLens Insider-buildjén is.</span><span class="sxs-lookup"><span data-stu-id="9888b-165">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="9888b-166">Használhatja a Unity ugyanazon buildjéhez és Visual Studio, mint a HoloLens-fejlesztéshez.</span><span class="sxs-lookup"><span data-stu-id="9888b-166">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="9888b-167">Insider-buildek fogadásának leállítása</span><span class="sxs-lookup"><span data-stu-id="9888b-167">Stop receiving Insider builds</span></span>
<span data-ttu-id="9888b-168">Ha már nem szeretné megkapni a Windows Holographic Insider-buildjét, kikapcsolhatja, ha a HoloLens éles buildet futtat, vagy az Advanced Recovery Companion segítségével helyreállíthatja az eszközt a Windows Holographic nem insider verziójára. [](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="9888b-168">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="9888b-169">Megjelenik egy ismert probléma, amely miatt az Insider Preview buildre való regisztrációt manuálisan újratelepítő felhasználók kék képernyőt tapasztalnak.</span><span class="sxs-lookup"><span data-stu-id="9888b-169">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="9888b-170">Ezt követően manuálisan kell helyreállítania az eszközt.</span><span class="sxs-lookup"><span data-stu-id="9888b-170">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="9888b-171">Ha szeretne többet tudni arról, hogy ez hatással lenne-e az Ön számára, tekintse meg ezt az ismert [problémát.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="9888b-171">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="9888b-172">Annak ellenőrzése, hogy a HoloLens éles buildet futtat-e:</span><span class="sxs-lookup"><span data-stu-id="9888b-172">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="9888b-173">A Settings **(Beállítások) > System > About (A** rendszerről) lapon keresse meg a build számát.</span><span class="sxs-lookup"><span data-stu-id="9888b-173">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="9888b-174">[Az éles buildszámokat a kibocsátási megjegyzésekben láthatja.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="9888b-174">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="9888b-175">Az Insider-buildek lemondása:</span><span class="sxs-lookup"><span data-stu-id="9888b-175">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="9888b-176">Éles buildet futtató HoloLensen válassza a Beállítások > **Update & Security > Windows Insider Program** lehetőséget, és válassza a Stop **Insider builds lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="9888b-176">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="9888b-177">Az eszköz lemondáshoz kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="9888b-177">Follow the instructions to opt out your device.</span></span>
