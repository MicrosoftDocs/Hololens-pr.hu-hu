---
title: Fájlok megkeresása és mentése a HoloLensben
description: Megtudhatja, hogyan használhatja Fájlkezelő HoloLensben a fájlok megnyitásához, megtekintéséhez és kezeléséhez a vegyes valóságú eszközön.
keywords: how-to, file picker, files, photos, videos, pictures, OneDrive, storage, file explorer, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378026"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="ecfd0-104">Fájlok megkeresését, megnyitását és mentését a HoloLensben</span><span class="sxs-lookup"><span data-stu-id="ecfd0-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="ecfd0-105">A HoloLensen létrehozott fájlok, köztük a fényképek és videók közvetlenül a HoloLens-eszközre vannak mentve.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="ecfd0-106">Ezeket ugyanúgy megtekintheti és kezelheti, mint a fájlokat a Windows 10:</span><span class="sxs-lookup"><span data-stu-id="ecfd0-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="ecfd0-107">A helyi Fájlkezelő alkalmazással férhet hozzá.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="ecfd0-108">Egy alkalmazás tárhelyében.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-108">Within an app's storage.</span></span>
- <span data-ttu-id="ecfd0-109">Egy speciális mappában (például a videóban vagy a zenetárban).</span><span class="sxs-lookup"><span data-stu-id="ecfd0-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="ecfd0-110">Alkalmazásokat és fájlválasztót (például OneDrive-ot) tartalmazó tárolási szolgáltatás használata.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="ecfd0-111">A HoloLenshez csatlakoztatott asztali számítógép használata USB-kábelen keresztül, MTP (Media Transfer Protocol) támogatással.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="ecfd0-112">Fájlok megtekintése a HoloLensben a Fájlkezelő</span><span class="sxs-lookup"><span data-stu-id="ecfd0-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="ecfd0-113">Az összes HoloLens 2-eszközre és HoloLensre (1. generációs) vonatkozik a [HoloLens Windows 10 2018. áprilisi frissítése (RS4)](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)óta.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="ecfd0-114">A Fájlkezelő a HoloLensben fájlokat, köztük 3D-objektumokat, dokumentumokat és képeket is megtekinthet és kezelhet az eszközön.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="ecfd0-115">A **kezdéshez**   >  **Minden alkalmazás**   >  **Fájlkezelő** a Start menüt.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="ecfd0-116">Ha a bal felső panelen nincsenek Fájlkezelő, válassza az **Ez az eszköz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="ecfd0-117">Ha nem lát fájlokat a Fájlkezelő a "Legutóbbi" szűrő lehet aktív (az óra ikon ki van emelve a bal oldali panelen).</span><span class="sxs-lookup"><span data-stu-id="ecfd0-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="ecfd0-118">Ennek kijavításaként  válassza az Ez az eszköz dokumentum ikont a bal oldali panelen (az óra ikon alatt), vagy nyissa meg a menüt, és válassza az Ez az **eszköz lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="ecfd0-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="ecfd0-119">Fényképek és videók megkeresve és megtekintése</span><span class="sxs-lookup"><span data-stu-id="ecfd0-119">Find and view your photos and videos</span></span>

<span data-ttu-id="ecfd0-120">[A vegyes valóságú rögzítéssel](holographic-photos-and-videos.md) vegyes valóságú fényképeket és videókat készíthet a HoloLensen.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="ecfd0-121">Ezek a fényképek és videók az eszköz Camera Roll mappájába vannak mentve.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="ecfd0-122">A HoloLens-sel készített fényképeket és videókat a következővel lehet elérni:</span><span class="sxs-lookup"><span data-stu-id="ecfd0-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="ecfd0-123">A Camera Roll elérése közvetlenül a [Photos alkalmazásban.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="ecfd0-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="ecfd0-124">fényképek és videók feltöltése felhőalapú tárhelyre a fényképek és videók OneDrive-ba való szinkronizálása által.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="ecfd0-125">a Vegyes valóság rögzítése lap [Windows eszközportál.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)</span><span class="sxs-lookup"><span data-stu-id="ecfd0-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="ecfd0-126">Photos alkalmazás</span><span class="sxs-lookup"><span data-stu-id="ecfd0-126">Photos app</span></span>

<span data-ttu-id="ecfd0-127">A Photos alkalmazás a **Start** menü egyik alapértelmezett alkalmazása, amely beépített a HoloLenshez.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="ecfd0-128">További információ a [tartalmak a Photos alkalmazással való megtekintéséről.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="ecfd0-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="ecfd0-129">A [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) alkalmazást az alkalmazásból is Microsoft Store a fényképek más eszközökkel való szinkronizálásához.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="ecfd0-130">OneDrive alkalmazás</span><span class="sxs-lookup"><span data-stu-id="ecfd0-130">OneDrive app</span></span>

<span data-ttu-id="ecfd0-131">[A OneDrive](https://onedrive.live.com/) lehetővé teszi a fényképek és videók bármely eszközzel és felhasználóval való hozzáférését, kezelését és megosztását.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="ecfd0-132">A HoloLensben rögzített fényképek és videók eléréséhez töltse le a [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) alkalmazást a HoloLens Microsoft Store-fájlból.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="ecfd0-133">A letöltés után nyissa meg a OneDrive alkalmazást, válassza a **Beállítások** Kamera feltöltése lehetőséget, majd kapcsolja  >  be a **Kamera feltöltése beállítást.**</span><span class="sxs-lookup"><span data-stu-id="ecfd0-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="ecfd0-134">Csatlakozás számítógéphez</span><span class="sxs-lookup"><span data-stu-id="ecfd0-134">Connect to a PC</span></span>

<span data-ttu-id="ecfd0-135">Ha a HoloLens [a 2018.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) áprilisi vagy újabb Windows 10-frissítést futtatja, csatlakoztathatja a HoloLenst egy Windows 10-számítógéphez USB-kábellel, hogy az MTP (médiaátviteli protokoll) használatával böngésszen az eszközön található fényképek és videók között.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="ecfd0-136">Ha pin-kód vagy jelszó van beállítva az eszközön, győződjön meg arról, hogy az eszköz fel van oldva a fájlok tallózásához.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="ecfd0-137">Ha engedélyezte a [Windows eszközportál,](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)a használatával tallózhatja, lekérheti és kezelheti az eszközön tárolt fényképeket és videókat.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="ecfd0-138">Alkalmazáson belüli fájlok elérése</span><span class="sxs-lookup"><span data-stu-id="ecfd0-138">Access files within an app</span></span>

<span data-ttu-id="ecfd0-139">Ha egy alkalmazás fájlokat ment az eszközön, az alkalmazással elérheti őket.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="ecfd0-140">Fájlok kérése egy másik alkalmazásból</span><span class="sxs-lookup"><span data-stu-id="ecfd0-140">Requesting files from another app</span></span>

<span data-ttu-id="ecfd0-141">Egy alkalmazás kérheti egy fájl mentését, vagy fájlválasztók használatával megnyithat egy fájlt egy [másik alkalmazásból.](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)</span><span class="sxs-lookup"><span data-stu-id="ecfd0-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="ecfd0-142">Ismert mappák</span><span class="sxs-lookup"><span data-stu-id="ecfd0-142">Known folders</span></span>

<span data-ttu-id="ecfd0-143">A HoloLens számos olyan ismert mappát [támogat,](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) amelyek hozzáférését az alkalmazások kérhetik.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="ecfd0-144">HoloLens-fájlok megtekintése a számítógépen</span><span class="sxs-lookup"><span data-stu-id="ecfd0-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="ecfd0-145">Más mobileszközökhöz hasonlóan csatlakoztassa a HoloLenst az asztali számítógéphez az MTP (Media Transfer Protocol) használatával, és nyissa meg a Fájlkezelő-t a számítógépen a HoloLens-kódtárak eléréséhez az egyszerű átvitel érdekében.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="ecfd0-146">A HoloLens-fájlok Fájlkezelő a számítógépen:</span><span class="sxs-lookup"><span data-stu-id="ecfd0-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="ecfd0-147">Jelentkezzen be a HoloLensbe, majd csatlakoztassa a számítógéphez a HoloLenshez csatlakoztatott USB-kábellel.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="ecfd0-148">Válassza **az Eszköz megnyitása lehetőséget a Fájlkezelő** megtekintéséhez, vagy nyissa Fájlkezelő a számítógépen, és navigáljon az eszközre.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="ecfd0-149">A HoloLens adataihoz kattintson a jobb gombbal az eszköz nevére a Fájlkezelő, majd válassza a Tulajdonságok **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="ecfd0-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="ecfd0-150">A HoloLens (1. generációs) nem támogatja a külső merevlemezek vagy SD-kártyák csatlakoztatását.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="ecfd0-151">Szinkronizálás a felhővel</span><span class="sxs-lookup"><span data-stu-id="ecfd0-151">Sync to the cloud</span></span>

<span data-ttu-id="ecfd0-152">A HoloLensben tárolt fényképek és egyéb fájlok felhőbe való szinkronizáláshoz telepítse és állítsa be a OneDrive-ot a HoloLensen.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="ecfd0-153">A OneDrive-ot a HoloLens Microsoft Store megkeresésével keresheti meg.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="ecfd0-154">A HoloLens nem biztonsági mentést ad az alkalmazás fájljairól és adatairól, ezért jó ötlet a fontos adatokat a OneDrive-ra menteni.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="ecfd0-155">Így ha alaphelyzetbe állítja az eszközt, vagy eltávolít egy alkalmazást, az adatokról biztonsági adatokat fog kapni.</span><span class="sxs-lookup"><span data-stu-id="ecfd0-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
