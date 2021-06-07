---
title: Alkalmazások megkeresheti, telepítheti és eltávolíthatja őket
description: A Microsoft Store a HoloLens-sel használt alkalmazások és játékok forrása.  További információ a holografikus alkalmazások kereséséről, telepítéséről és eltávolításáról.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: hololens, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b44ee3f9ce5aa31205feb9bb27202351e0014364
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379531"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a><span data-ttu-id="7dd80-105">Alkalmazások megkeresheti, telepítheti és eltávolíthatja őket a Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="7dd80-105">Find, install, and uninstall applications from the Microsoft Store</span></span>

<span data-ttu-id="7dd80-106">A Microsoft Store a HoloLens-sel használt alkalmazások és játékok forrása.</span><span class="sxs-lookup"><span data-stu-id="7dd80-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span></span> <span data-ttu-id="7dd80-107">Ha a HoloLens áruházában van, minden ott látható alkalmazás futni fog rajta.</span><span class="sxs-lookup"><span data-stu-id="7dd80-107">When you go to the Store on your HoloLens, any apps you see there will run on it.</span></span>

<span data-ttu-id="7dd80-108">A HoloLens-alkalmazások 2D nézetet vagy holografikus nézetet használhatnak.</span><span class="sxs-lookup"><span data-stu-id="7dd80-108">Apps on HoloLens use either 2D view or holographic view.</span></span> <span data-ttu-id="7dd80-109">A 2D nézetet használó alkalmazások windowsosak, és az Ön köré is el lehet őket különülni.</span><span class="sxs-lookup"><span data-stu-id="7dd80-109">Apps that use 2D view look like windows and can be positioned all around you.</span></span> <span data-ttu-id="7dd80-110">A holografikus nézetet használó alkalmazások körülveszi, és ön lesz az egyetlen alkalmazás, amit lát.</span><span class="sxs-lookup"><span data-stu-id="7dd80-110">Apps that use holographic view surround you and become the only app you see.</span></span>

<span data-ttu-id="7dd80-111">A HoloLens számos meglévő alkalmazást támogat a Microsoft Store, valamint a Kifejezetten a HoloLenshez készült új alkalmazásokat.</span><span class="sxs-lookup"><span data-stu-id="7dd80-111">HoloLens supports many existing applications from the Microsoft Store, and new apps built specifically for HoloLens.</span></span>  <span data-ttu-id="7dd80-112">Ez a cikk a világ különböző oldalának holografikus alkalmazásait Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="7dd80-112">This article focuses on holographic applications from the Microsoft Store.</span></span>

<span data-ttu-id="7dd80-113">További információ az egyéni alkalmazások telepítéséről és futtatásáról: [Egyéni holografikus alkalmazások.](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="7dd80-113">To learn more about installing and running custom apps, read [Custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="find-apps"></a><span data-ttu-id="7dd80-114">Alkalmazások megkerese</span><span class="sxs-lookup"><span data-stu-id="7dd80-114">Find apps</span></span>

<span data-ttu-id="7dd80-115">Nyissa meg a Microsoft Store a **Start menüből.**</span><span class="sxs-lookup"><span data-stu-id="7dd80-115">Open the Microsoft Store from the **Start** menu.</span></span> <span data-ttu-id="7dd80-116">Ezután keresse meg az alkalmazásokat és a játékokat.</span><span class="sxs-lookup"><span data-stu-id="7dd80-116">Then browse for apps and games.</span></span> <span data-ttu-id="7dd80-117">A [hangparancsokkal](hololens-cortana.md) a "Keresés" kifejezéssel kereshet, a keresési ablak megnyitása után a "Start dictating" (Diktálás megkezdése) üzenet jelenik meg, majd amikor a rendszer kéri, kezdje el kiadni a keresési kifejezéseket.</span><span class="sxs-lookup"><span data-stu-id="7dd80-117">You can use [voice commands](hololens-cortana.md) to search by saying "Search", once the search window opens say "Start dictating" and then when prompted begin saying your search terms.</span></span>

> [!NOTE]
> <span data-ttu-id="7dd80-118">A HoloLens-eszközök rendszerkövetelményei az alkalmazás build architektúráján alapulnak.</span><span class="sxs-lookup"><span data-stu-id="7dd80-118">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="7dd80-119">Ha a HoloLenshez (1. generációs) készült alkalmazás buildje nem frissült újabb UWP-re az áruházban az ARM architektúracsomaggal, akkor a HoloLens 2-eszközökön nem lesz elérhető.</span><span class="sxs-lookup"><span data-stu-id="7dd80-119">If an app build for HoloLens (1st gen) has not been updated with to a newer UWP in the store to include the ARM architecture package, then it will not be available for HoloLens 2 devices.</span></span> <span data-ttu-id="7dd80-120">Hasonlóképpen, ha egy HoloLens 2-alkalmazás nem tartalmazza az x86-os architektúracsomagot, nem lesz elérhető a HoloLens (1. generációs) eszközökön.</span><span class="sxs-lookup"><span data-stu-id="7dd80-120">Likewise, if a HoloLens 2 app does not include the x86 architecture package, it will not be available for HoloLens (1st gen) devices.</span></span> <span data-ttu-id="7dd80-121">HoloLens-eszközarchitektúrák:</span><span class="sxs-lookup"><span data-stu-id="7dd80-121">HoloLens device architectures:</span></span>
> - <span data-ttu-id="7dd80-122">x86 = HoloLens (1. generációs)</span><span class="sxs-lookup"><span data-stu-id="7dd80-122">x86 = HoloLens (1st gen)</span></span>
> - <span data-ttu-id="7dd80-123">ARM = HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="7dd80-123">ARM = HoloLens 2</span></span>

> [!NOTE]
> <span data-ttu-id="7dd80-124">2021. január 12-én a következő alkalmazások érik el a Támogatás vége a HoloLens-eszközökön.</span><span class="sxs-lookup"><span data-stu-id="7dd80-124">On January 12, 2021 the following apps will reach End of Support on HoloLens devices.</span></span> <span data-ttu-id="7dd80-125">Javasoljuk, hogy használja az alábbi hivatkozást az eszközén az alkalmazás webes verziójának használatára.</span><span class="sxs-lookup"><span data-stu-id="7dd80-125">We encourage you to use the following link on your device to use the web version of the app.</span></span>

| <span data-ttu-id="7dd80-126">Alkalmazás</span><span class="sxs-lookup"><span data-stu-id="7dd80-126">App</span></span>        | <span data-ttu-id="7dd80-127">Hivatkozás</span><span class="sxs-lookup"><span data-stu-id="7dd80-127">Link</span></span>                                          |
|------------|-----------------------------------------------|
| <span data-ttu-id="7dd80-128">Excel Mobile</span><span class="sxs-lookup"><span data-stu-id="7dd80-128">Excel mobile</span></span>      | https://office.live.com/start/Excel.aspx      |
| <span data-ttu-id="7dd80-129">Word Mobile</span><span class="sxs-lookup"><span data-stu-id="7dd80-129">Word mobile</span></span>       | https://office.live.com/start/Word.aspx       |
| <span data-ttu-id="7dd80-130">PowerPoint Mobile</span><span class="sxs-lookup"><span data-stu-id="7dd80-130">PowerPoint mobile</span></span> | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a><span data-ttu-id="7dd80-131">Alkalmazások telepítése</span><span class="sxs-lookup"><span data-stu-id="7dd80-131">Install apps</span></span>

<span data-ttu-id="7dd80-132">Az alkalmazások letöltéséhez egy új fiókkal kell Microsoft-fiók.</span><span class="sxs-lookup"><span data-stu-id="7dd80-132">To download apps, you'll need to be signed in with a Microsoft account.</span></span> <span data-ttu-id="7dd80-133">Egyes alkalmazások ingyenesek, és azonnal letölthetők.</span><span class="sxs-lookup"><span data-stu-id="7dd80-133">Some apps are free and can be downloaded right away.</span></span> <span data-ttu-id="7dd80-134">A vásárlást igénylő alkalmazásokhoz be kell jelentkeznie az Áruházba a Microsoft-fiók és érvényes fizetési módgal kell lennie.</span><span class="sxs-lookup"><span data-stu-id="7dd80-134">For apps that require a purchase, you must be signed in to the Store with your Microsoft account and have a valid payment method.</span></span>

> [!NOTE]
> <span data-ttu-id="7dd80-135">A fióknak, Microsoft Store nem kell egy lennie a bejelentkezett fiókkal.</span><span class="sxs-lookup"><span data-stu-id="7dd80-135">The account you use on Microsoft Store does not have to be the same as the account you are signed in with.</span></span> <span data-ttu-id="7dd80-136">Ha Munkahelyi vagy iskolai fiókot használ a HoloLensben, akkor előfordulhat, hogy a vásárláshoz be kell jelentkeznie személyes fiókjával az Áruházbeli alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="7dd80-136">If you are using a Work or School account on your HoloLens then you may need to sign in with your personal account in the Store App to make a purchase.</span></span>

> [!TIP]
> <span data-ttu-id="7dd80-137">A fizetési mód beállításához [](https://account.microsoft.com/) válassza a Fizetési account.microsoft.com lehetőséget& **fizetési** lehetőség Fizetési  >    >  **lehetőség hozzáadása lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="7dd80-137">To set up a payment method, go to [account.microsoft.com](https://account.microsoft.com/) and select **Payment & billing** > **Payment options** > **Add a payment option**.</span></span>

1. <span data-ttu-id="7dd80-138">A [ **Start menü megnyitásához**](holographic-home.md)hajtson végre egy [Indítás](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) kézmozdulatot vagy Bloom-kézmozdulatot a HoloLensen (1. generációs). [](hololens1-basic-usage.md)</span><span class="sxs-lookup"><span data-stu-id="7dd80-138">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="7dd80-139">Válassza ki a Microsoft Store alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="7dd80-139">Select the Microsoft Store app.</span></span> <span data-ttu-id="7dd80-140">Az Áruház alkalmazás megnyitása után:</span><span class="sxs-lookup"><span data-stu-id="7dd80-140">After the Store app opens:</span></span>
   1. <span data-ttu-id="7dd80-141">A keresősáv használatával keressen alkalmazásokat.</span><span class="sxs-lookup"><span data-stu-id="7dd80-141">Use the search bar to look for applications.</span></span> 
   1. <span data-ttu-id="7dd80-142">Válassza ki a kifejezetten a HoloLenshez készült alapvető alkalmazásokat vagy alkalmazásokat az egyik kiválasztott kategóriából.</span><span class="sxs-lookup"><span data-stu-id="7dd80-142">Select essential apps or apps made specifically for HoloLens from one of the curated categories.</span></span>
   1. <span data-ttu-id="7dd80-143">Az Áruház alkalmazás jobb felső részen válassza a  **"..."** gombot, majd a Saját könyvtár lehetőséget a korábban megvásárolt alkalmazások megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="7dd80-143">On the top right of the Store app, select the **"..."** button and then select **My Library** to view any previously purchased apps.</span></span>

1. <span data-ttu-id="7dd80-144">Válassza **a Lekért** **vagy** Telepítés lehetőséget az alkalmazás oldalán (előfordulhat, hogy vásárlásra van szükség).</span><span class="sxs-lookup"><span data-stu-id="7dd80-144">Select **Get** or **Install** on the application's page (a purchase may be required).</span></span>

## <a name="update-apps"></a><span data-ttu-id="7dd80-145">Alkalmazások frissítése</span><span class="sxs-lookup"><span data-stu-id="7dd80-145">Update Apps</span></span>

<span data-ttu-id="7dd80-146">Ha frissítenie kell egy, a Microsoft Store telepített alkalmazást, frissítheti az alkalmazást a Microsoft Store alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="7dd80-146">To update an app you installed from the Microsoft Store, you can update the app from the Microsoft Store app.</span></span> <span data-ttu-id="7dd80-147">Az alkalmazáshoz telepített Microsoft Store Vállalatoknak frissítheti is az alkalmazásokat a Microsoft Store Vállalatoknak.</span><span class="sxs-lookup"><span data-stu-id="7dd80-147">For apps installed for the Microsoft Store for Business, you can also update those apps from the Microsoft Store for Business.</span></span> 

1. <span data-ttu-id="7dd80-148">A [ **Start menü megnyitásához**](holographic-home.md)hajtson végre egy [Indítás](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) kézmozdulatot vagy Bloom-kézmozdulatot a HoloLensen (1. generációs). [](hololens1-basic-usage.md)</span><span class="sxs-lookup"><span data-stu-id="7dd80-148">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="7dd80-149">Válassza ki az Áruház alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="7dd80-149">Select the Store app.</span></span>

1. <span data-ttu-id="7dd80-150">Keresse meg az Áruház alkalmazás jobb felső sarokban.</span><span class="sxs-lookup"><span data-stu-id="7dd80-150">Look to the top right of the Store app.</span></span> 

1. <span data-ttu-id="7dd80-151">Válassza a **"..."** vagy a "További információk" gombot.</span><span class="sxs-lookup"><span data-stu-id="7dd80-151">Select the **"..."** or “See more” button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7dd80-152">![Microsoft Store alkalmazás képernyőképe.](images/store-update-1.png)</span><span class="sxs-lookup"><span data-stu-id="7dd80-152">![Microsoft Store app screenshot.](images/store-update-1.png)</span></span>

1. <span data-ttu-id="7dd80-153">Válassza **a Letöltések és frissítések lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="7dd80-153">Select **Downloads and updates**.</span></span>
    1. <span data-ttu-id="7dd80-154">Ha az eszköz korábban már azonosított frissítéseket, előfordulhat, hogy egy lefelé mutató nyíl és egy szám jelöli a függőben lévő frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="7dd80-154">If your device has previously identified updates, there may be a down arrow and a number that represents pending updates.</span></span>

1. <span data-ttu-id="7dd80-155">Válassza a **Frissítések lekérte lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="7dd80-155">Select **Get updates**.</span></span> <span data-ttu-id="7dd80-156">Az eszköz most frissítéseket fog keresni, és be fogja állítani őket letöltésre és telepítésre.</span><span class="sxs-lookup"><span data-stu-id="7dd80-156">Your device will now search for updates and set them to download and install.</span></span> 
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7dd80-157">![Microsoft Store képernyőképe a frissítések lekért alkalmazásról.](images/store-update-2.png.jpg)</span><span class="sxs-lookup"><span data-stu-id="7dd80-157">![Microsoft Store app screenshot of getting updates..](images/store-update-2.png.jpg)</span></span>

> [!NOTE]
> <span data-ttu-id="7dd80-158">Ha az eszközön található alkalmazásokat a szervezet terjesztette, ugyanezekkel a kereskedelmi alkalmazáskezelési módszerekkel frissíthetők.</span><span class="sxs-lookup"><span data-stu-id="7dd80-158">If the apps on your device were distributed by your organization they can be updated through the same commercial app management methods.</span></span> <span data-ttu-id="7dd80-159">Ha ez az Ön helyzetére vonatkozik, további információt a kereskedelmi alkalmazások üzembe [helyezésének áttekintésében talál.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7dd80-159">If this applies to your situation, read more via our [overview of commercial app deployment.](app-deploy-overview.md)</span></span>
>
> <span data-ttu-id="7dd80-160">Ha egy saját telepítésű vagy üzembe helyezett egyéni alkalmazást szeretne frissíteni, ugyanezt a módszert kell használnia az alkalmazás frissített verziójával.</span><span class="sxs-lookup"><span data-stu-id="7dd80-160">If you would like to update a custom app that has been sideloaded or deployed, you will need to use the same method with the updated version of your app.</span></span> <span data-ttu-id="7dd80-161">Ha többet szeretne megtudni az egyéni alkalmazások telepítéséről és futtatásáról, olvassa el az [egyéni holografikus alkalmazásokat.](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="7dd80-161">To learn more about installing and running custom apps, read [custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="uninstall-apps"></a><span data-ttu-id="7dd80-162">Alkalmazások eltávolítása</span><span class="sxs-lookup"><span data-stu-id="7dd80-162">Uninstall apps</span></span>

<span data-ttu-id="7dd80-163">Az alkalmazások háromféleképpen távolíthatók el.</span><span class="sxs-lookup"><span data-stu-id="7dd80-163">There are three ways to uninstall applications.</span></span> <span data-ttu-id="7dd80-164">Az alkalmazásokat a következő gombra Microsoft Store, Start menü beállításokból távolíthatja el.</span><span class="sxs-lookup"><span data-stu-id="7dd80-164">You can uninstall applications through the Microsoft Store, Start menu or from Settings.</span></span> 

> [!WARNING]
> <span data-ttu-id="7dd80-165">Nem távolíthat el rendszeralkalmazást vagy a Microsoft Store magát.</span><span class="sxs-lookup"><span data-stu-id="7dd80-165">You can not uninstall a system app or the Microsoft Store itself.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7dd80-166">Ha a HoloLens 2-nek több felhasználója van, az alkalmazás eltávolításához az alkalmazást telepítő felhasználóként kell bejelentkeznie.</span><span class="sxs-lookup"><span data-stu-id="7dd80-166">If your HoloLens 2 has multiple users, you must be logged in as the user who installed the app to uninstall it.</span></span> 

### <a name="uninstall-from-the-microsoft-store"></a><span data-ttu-id="7dd80-167">Eltávolítás a Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="7dd80-167">Uninstall from the Microsoft Store</span></span>

<span data-ttu-id="7dd80-168">Nyissa meg a Microsoft Store **a Start menüből,** majd keresse meg az eltávolítani kívánt alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="7dd80-168">Open the Microsoft Store from the **Start** menu, and then browse for the application you want to uninstall.</span></span>  <span data-ttu-id="7dd80-169">Az Áruház lapon minden telepített alkalmazás rendelkezik egy **Eltávolítás gombbal.**</span><span class="sxs-lookup"><span data-stu-id="7dd80-169">On the Store page, each installed application has an **Uninstall** button.</span></span>

### <a name="uninstall-from-the-start-menu"></a><span data-ttu-id="7dd80-170">Eltávolítás a Start menü</span><span class="sxs-lookup"><span data-stu-id="7dd80-170">Uninstall from the Start menu</span></span>

<span data-ttu-id="7dd80-171">A **Start menüben** vagy a **Minden alkalmazás** nyissa meg az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="7dd80-171">On the **Start** menu or in the **All apps** list, browse to the app.</span></span> <span data-ttu-id="7dd80-172">Válassza ki és tartsa lenyomva, amíg meg nem jelenik a menü, majd válassza az **Eltávolítás lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="7dd80-172">Select and hold until the menu appears, then select **Uninstall**.</span></span>

### <a name="uninstall-from-settings"></a><span data-ttu-id="7dd80-173">Eltávolítás a Beállításokból</span><span class="sxs-lookup"><span data-stu-id="7dd80-173">Uninstall from Settings</span></span>
<span data-ttu-id="7dd80-174">A **Start menüben** válassza a **Beállítások -> lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="7dd80-174">On the **Start** menu, select **Settings -> Apps.**</span></span> <span data-ttu-id="7dd80-175">Keresse meg az alkalmazást a listában, jelölje ki, majd kattintson az **Eltávolítás gombra.**</span><span class="sxs-lookup"><span data-stu-id="7dd80-175">Find the app from the list, select it and then click **Uninstall**.</span></span>

<span data-ttu-id="7dd80-176">Ha nem sikerül eltávolítania egy alkalmazást, kérjük, [visszajelzést](https://docs.microsoft.com/hololens/hololens-feedback) a Visszajelzési központ.</span><span class="sxs-lookup"><span data-stu-id="7dd80-176">If you are unable to uninstall an app, please file [feedback](https://docs.microsoft.com/hololens/hololens-feedback) using the Feedback Hub.</span></span>
