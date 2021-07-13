---
title: Fájlok megkeresása és mentése a HoloLens
description: Megtudhatja, hogyan használhatja Fájlkezelő a HoloLens vegyes valóságú eszközön lévő fájlok megnyitásához, megtekintéséhez és kezeléséhez.
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
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636180"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="902d5-104">Fájlok megkeresása, megnyitása és mentése a HoloLens</span><span class="sxs-lookup"><span data-stu-id="902d5-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="902d5-105">A HoloLens létrehozott fájlok, köztük a fényképek és videók közvetlenül a saját HoloLens vannak mentve.</span><span class="sxs-lookup"><span data-stu-id="902d5-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="902d5-106">Ezeket ugyanúgy megtekintheti és kezelheti, mint a fájlokat a Windows 10:</span><span class="sxs-lookup"><span data-stu-id="902d5-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="902d5-107">A helyi Fájlkezelő alkalmazással férhet hozzá.</span><span class="sxs-lookup"><span data-stu-id="902d5-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="902d5-108">Egy alkalmazás tárhelyében.</span><span class="sxs-lookup"><span data-stu-id="902d5-108">Within an app's storage.</span></span>
- <span data-ttu-id="902d5-109">Egy speciális mappában (például a videóban vagy a zenetárban).</span><span class="sxs-lookup"><span data-stu-id="902d5-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="902d5-110">Alkalmazásokat és fájlválasztót (például alkalmazás- és fájlválasztót) tartalmazó tárolási szolgáltatás OneDrive.</span><span class="sxs-lookup"><span data-stu-id="902d5-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="902d5-111">Usb-kábelen keresztül csatlakoztatott asztali HoloLens MTP (Media Transfer Protocol) támogatással.</span><span class="sxs-lookup"><span data-stu-id="902d5-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="902d5-112">Fájlok megtekintése a HoloLens a Fájlkezelő</span><span class="sxs-lookup"><span data-stu-id="902d5-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="902d5-113">A [2018.](/windows/mixed-reality/release-notes-april-2018)áprilisi Windows 10 (RS4) frissítéstől HoloLens 2 eszközre és HoloLens (1. generációs) HoloLens.</span><span class="sxs-lookup"><span data-stu-id="902d5-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="902d5-114">A Fájlkezelő a HoloLens megtekintheti és kezelheti az eszközön lévő fájlokat, beleértve a 3D-objektumokat, dokumentumokat és képeket.</span><span class="sxs-lookup"><span data-stu-id="902d5-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="902d5-115">A **kezdéshez**   >  **Minden alkalmazás**   >  **Fájlkezelő** a Start menüt.</span><span class="sxs-lookup"><span data-stu-id="902d5-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="902d5-116">Ha nincsenek fájlok a Fájlkezelő, válassza az **Ez az eszköz** lehetőséget a bal felső panelen.</span><span class="sxs-lookup"><span data-stu-id="902d5-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="902d5-117">Ha nem lát fájlokat a Fájlkezelő a "Legutóbbi" szűrő lehet aktív (az óra ikon ki van emelve a bal oldali panelen).</span><span class="sxs-lookup"><span data-stu-id="902d5-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="902d5-118">Ennek kijavításaként  válassza az Ez az eszköz dokumentum ikont a bal oldali panelen (az óra ikon alatt), vagy nyissa meg a menüt, és válassza az Ez az **eszköz lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="902d5-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="902d5-119">Fényképek és videók megkeresve és megtekintése</span><span class="sxs-lookup"><span data-stu-id="902d5-119">Find and view your photos and videos</span></span>

<span data-ttu-id="902d5-120">[A vegyes valóságú rögzítés](holographic-photos-and-videos.md) lehetővé teszi, hogy vegyes valóságú fényképeket és videókat készítsen HoloLens.</span><span class="sxs-lookup"><span data-stu-id="902d5-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="902d5-121">Ezek a fényképek és videók az eszköz Camera Roll mappájába vannak mentve.</span><span class="sxs-lookup"><span data-stu-id="902d5-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="902d5-122">Az alkalmazással készített fényképeket és videókat a következő HoloLens elérheti:</span><span class="sxs-lookup"><span data-stu-id="902d5-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="902d5-123">A Camera Roll elérése közvetlenül a [Photos alkalmazásban.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="902d5-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="902d5-124">fényképeket és videókat tölthet fel a felhőtárhelyre a fényképek és videók szinkronizálása OneDrive.</span><span class="sxs-lookup"><span data-stu-id="902d5-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="902d5-125">a Vegyes valóság rögzítése lap [Windows Eszközportál.](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)</span><span class="sxs-lookup"><span data-stu-id="902d5-125">using the Mixed Reality Capture page of the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="902d5-126">Fényképek alkalmazás</span><span class="sxs-lookup"><span data-stu-id="902d5-126">Photos app</span></span>

<span data-ttu-id="902d5-127">A Photos alkalmazás a **Start** menü egyik alapértelmezett alkalmazása, amely beépített HoloLens.</span><span class="sxs-lookup"><span data-stu-id="902d5-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="902d5-128">További információ a [tartalmak a Photos alkalmazással való megtekintéséről.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="902d5-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="902d5-129">A OneDrive [is telepítheti](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) a Microsoft Store, hogy más eszközökkel szinkronizálja a fényképeket.</span><span class="sxs-lookup"><span data-stu-id="902d5-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="902d5-130">OneDrive alkalmazás</span><span class="sxs-lookup"><span data-stu-id="902d5-130">OneDrive app</span></span>

<span data-ttu-id="902d5-131">[OneDrive](https://onedrive.live.com/) lehetővé teszi a fényképek és videók bármely eszközzel és felhasználóval való hozzáférését, kezelését és megosztását.</span><span class="sxs-lookup"><span data-stu-id="902d5-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="902d5-132">A HoloLens rögzített fényképek és videók eléréséhez töltse [](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) le OneDrive alkalmazást a Microsoft Store a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="902d5-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="902d5-133">A letöltés után nyissa meg a OneDrive alkalmazást, válassza a Gépház  >  **feltöltése** lehetőséget, majd kapcsolja be a **Kamera feltöltése lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="902d5-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="902d5-134">Csatlakozás számítógépekre</span><span class="sxs-lookup"><span data-stu-id="902d5-134">Connect to a PC</span></span>

<span data-ttu-id="902d5-135">Ha a HoloLens [a Windows 10 2018.](/windows/mixed-reality/release-notes-april-2018) áprilisi vagy újabb frissítését futtatja, csatlakoztathatja az HoloLens-t egy Windows 10-számítógéphez USB-kábellel, hogy az MTP (media Transfer Protocol) használatával böngésszen az eszközön található fényképek és videók között.</span><span class="sxs-lookup"><span data-stu-id="902d5-135">If your HoloLens is running the [Windows 10 April 2018 update](/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="902d5-136">Ha pin-kód vagy jelszó van beállítva az eszközön, győződjön meg arról, hogy az eszköz fel van oldva a fájlok tallózásához.</span><span class="sxs-lookup"><span data-stu-id="902d5-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="902d5-137">Ha engedélyezte a [Windows Eszközportál,](/windows/mixed-reality/using-the-windows-device-portal)a használatával tallózhatja, lekérheti és kezelheti az eszközön tárolt fényképeket és videókat.</span><span class="sxs-lookup"><span data-stu-id="902d5-137">If you have enabled the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="902d5-138">Alkalmazáson belüli fájlok elérése</span><span class="sxs-lookup"><span data-stu-id="902d5-138">Access files within an app</span></span>

<span data-ttu-id="902d5-139">Ha egy alkalmazás fájlokat ment az eszközre, az alkalmazással elérheti őket.</span><span class="sxs-lookup"><span data-stu-id="902d5-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="902d5-140">Fájlok kérése egy másik alkalmazásból</span><span class="sxs-lookup"><span data-stu-id="902d5-140">Requesting files from another app</span></span>

<span data-ttu-id="902d5-141">Egy alkalmazás kérheti egy fájl mentését, vagy fájlválasztók használatával megnyithat egy fájlt egy [másik alkalmazásból.](/windows/mixed-reality/app-model#file-pickers)</span><span class="sxs-lookup"><span data-stu-id="902d5-141">An application can request to save a file or open a file from another app by using [file pickers](/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="902d5-142">Ismert mappák</span><span class="sxs-lookup"><span data-stu-id="902d5-142">Known folders</span></span>

<span data-ttu-id="902d5-143">HoloLens számos olyan ismert mappát [támogat,](/windows/mixed-reality/app-model#known-folders) amelyekhez az alkalmazások hozzáférést kérhetnek.</span><span class="sxs-lookup"><span data-stu-id="902d5-143">HoloLens supports a number of [known folders](/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="902d5-144">A HoloLens megtekintése a számítógépen</span><span class="sxs-lookup"><span data-stu-id="902d5-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="902d5-145">Más mobileszközökhöz hasonlóan csatlakoztassa HoloLens számítógépéhez az MTP (Media Transfer Protocol) segítségével, és nyissa meg a Fájlkezelő-t a számítógépen, hogy hozzáférjen HoloLens kódtárához az egyszerű átvitel érdekében.</span><span class="sxs-lookup"><span data-stu-id="902d5-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="902d5-146">A számítógép HoloLens fájlok Fájlkezelő a számítógépen:</span><span class="sxs-lookup"><span data-stu-id="902d5-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="902d5-147">Jelentkezzen be a HoloLens, majd csatlakoztassa a számítógéphez az usb-kábellel, amely a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="902d5-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="902d5-148">Válassza **az Eszköz megnyitása lehetőséget a Fájlkezelő** megtekintéséhez, vagy nyissa Fájlkezelő a számítógépen, és navigáljon az eszközre.</span><span class="sxs-lookup"><span data-stu-id="902d5-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="902d5-149">A számítógépe adatai HoloLens kattintson a jobb gombbal az eszköz nevére a Fájlkezelő, majd válassza a Tulajdonságok **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="902d5-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="902d5-150">HoloLens (1. generációs) nem támogatja a külső merevlemezek vagy SD-kártyák csatlakoztatását.</span><span class="sxs-lookup"><span data-stu-id="902d5-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="902d5-151">Szinkronizálás a felhővel</span><span class="sxs-lookup"><span data-stu-id="902d5-151">Sync to the cloud</span></span>

<span data-ttu-id="902d5-152">Ha fényképeket és más fájlokat HoloLens a felhőbe, telepítse és OneDrive a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="902d5-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="902d5-153">A OneDrive kereséshez keresse meg a Microsoft Store a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="902d5-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="902d5-154">HoloLens nem biztonsági mentést ad az alkalmazás fájljairól és adatairól, ezért jó ötlet a fontos dolgokat a OneDrive.</span><span class="sxs-lookup"><span data-stu-id="902d5-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="902d5-155">Így ha alaphelyzetbe állítja az eszközt, vagy eltávolít egy alkalmazást, az adatokról biztonsági adatokat fog kapni.</span><span class="sxs-lookup"><span data-stu-id="902d5-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
