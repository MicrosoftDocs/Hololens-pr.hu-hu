---
title: Alkalmazások megkerese, telepítése és eltávolítása
description: A Microsoft Store a forrás az olyan alkalmazásokhoz és játékokhoz, amelyek HoloLens.  További információ a holografikus alkalmazások kereséséről, telepítéséről és eltávolításáról.
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
ms.openlocfilehash: bbbc60decb74942bd7930afb04297f78df33028a
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635857"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a><span data-ttu-id="9bf27-105">Alkalmazások megkeresheti, telepítheti és eltávolíthatja őket a Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="9bf27-105">Find, install, and uninstall applications from the Microsoft Store</span></span>

<span data-ttu-id="9bf27-106">A Microsoft Store az alkalmazásokkal és játékokkal használt alkalmazások és játékok HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9bf27-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span></span> <span data-ttu-id="9bf27-107">Amikor az Áruházat a saját HoloLens, minden ott látható alkalmazás futni fog rajta.</span><span class="sxs-lookup"><span data-stu-id="9bf27-107">When you go to the Store on your HoloLens, any apps you see there will run on it.</span></span>

<span data-ttu-id="9bf27-108">A HoloLens 2D nézetet vagy holografikus nézetet használhatnak.</span><span class="sxs-lookup"><span data-stu-id="9bf27-108">Apps on HoloLens use either 2D view or holographic view.</span></span> <span data-ttu-id="9bf27-109">A 2D nézetet használó alkalmazások windowsosak, és az Ön köré is el lehet őket tetsszen.</span><span class="sxs-lookup"><span data-stu-id="9bf27-109">Apps that use 2D view look like windows and can be positioned all around you.</span></span> <span data-ttu-id="9bf27-110">A holografikus nézetet használó alkalmazások körülveszi, és ön lesz az egyetlen alkalmazás, amit lát.</span><span class="sxs-lookup"><span data-stu-id="9bf27-110">Apps that use holographic view surround you and become the only app you see.</span></span>

<span data-ttu-id="9bf27-111">HoloLens számos meglévő alkalmazást támogat a Microsoft Store- és a kifejezetten a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9bf27-111">HoloLens supports many existing applications from the Microsoft Store, and new apps built specifically for HoloLens.</span></span>  <span data-ttu-id="9bf27-112">Ez a cikk a Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="9bf27-112">This article focuses on holographic applications from the Microsoft Store.</span></span>

<span data-ttu-id="9bf27-113">További információ az egyéni alkalmazások telepítéséről és futtatásáról: [Egyéni holografikus alkalmazások.](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="9bf27-113">To learn more about installing and running custom apps, read [Custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="find-apps"></a><span data-ttu-id="9bf27-114">Alkalmazások megkerese</span><span class="sxs-lookup"><span data-stu-id="9bf27-114">Find apps</span></span>

<span data-ttu-id="9bf27-115">Nyissa meg a Microsoft Store a **Start menüből.**</span><span class="sxs-lookup"><span data-stu-id="9bf27-115">Open the Microsoft Store from the **Start** menu.</span></span> <span data-ttu-id="9bf27-116">Ezután keresse meg az alkalmazásokat és játékokat.</span><span class="sxs-lookup"><span data-stu-id="9bf27-116">Then browse for apps and games.</span></span> <span data-ttu-id="9bf27-117">A hangparancsokkal a "Keresés" kifejezéssel kereshet, a keresési ablak megnyitása után a "Start dictating" (Diktálás megkezdése) üzenet jelenik meg, majd amikor a rendszer kéri, kezdje el kiadni a keresési kifejezéseket. [](hololens-cortana.md)</span><span class="sxs-lookup"><span data-stu-id="9bf27-117">You can use [voice commands](hololens-cortana.md) to search by saying "Search", once the search window opens say "Start dictating" and then when prompted begin saying your search terms.</span></span>

> [!NOTE]
> <span data-ttu-id="9bf27-118">A HoloLens rendszerkövetelményei az alkalmazás build architektúrája alapján vannak felépítve.</span><span class="sxs-lookup"><span data-stu-id="9bf27-118">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="9bf27-119">Ha az HoloLens (1. generációs) alkalmazás buildje nem lett frissítve az áruházban egy újabb UWP-re az ARM-architektúracsomaggal, akkor az arm architektúracsomag nem lesz elérhető HoloLens 2 eszköz esetén.</span><span class="sxs-lookup"><span data-stu-id="9bf27-119">If an app build for HoloLens (1st gen) has not been updated with to a newer UWP in the store to include the ARM architecture package, then it will not be available for HoloLens 2 devices.</span></span> <span data-ttu-id="9bf27-120">Hasonlóképpen, ha egy HoloLens 2-es alkalmazás nem tartalmazza az x86 architektúracsomagot, nem lesz elérhető HoloLens (1. generációs) eszközökhöz.</span><span class="sxs-lookup"><span data-stu-id="9bf27-120">Likewise, if a HoloLens 2 app does not include the x86 architecture package, it will not be available for HoloLens (1st gen) devices.</span></span> <span data-ttu-id="9bf27-121">HoloLens eszközarchitektúrák:</span><span class="sxs-lookup"><span data-stu-id="9bf27-121">HoloLens device architectures:</span></span>
> - <span data-ttu-id="9bf27-122">x86 = HoloLens (1. generációs)</span><span class="sxs-lookup"><span data-stu-id="9bf27-122">x86 = HoloLens (1st gen)</span></span>
> - <span data-ttu-id="9bf27-123">ARM = HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="9bf27-123">ARM = HoloLens 2</span></span>

> [!NOTE]
> <span data-ttu-id="9bf27-124">2021. január 12-én a következő alkalmazások érik el a Támogatás vége a HoloLens eszközökön.</span><span class="sxs-lookup"><span data-stu-id="9bf27-124">On January 12, 2021 the following apps will reach End of Support on HoloLens devices.</span></span> <span data-ttu-id="9bf27-125">Javasoljuk, hogy használja az alábbi hivatkozást az eszközén az alkalmazás webes verziójának használatára.</span><span class="sxs-lookup"><span data-stu-id="9bf27-125">We encourage you to use the following link on your device to use the web version of the app.</span></span>

| <span data-ttu-id="9bf27-126">Alkalmazás</span><span class="sxs-lookup"><span data-stu-id="9bf27-126">App</span></span>        | <span data-ttu-id="9bf27-127">Hivatkozás</span><span class="sxs-lookup"><span data-stu-id="9bf27-127">Link</span></span>                                          |
|------------|-----------------------------------------------|
| <span data-ttu-id="9bf27-128">Excel mobil</span><span class="sxs-lookup"><span data-stu-id="9bf27-128">Excel mobile</span></span>      | https://office.live.com/start/Excel.aspx      |
| <span data-ttu-id="9bf27-129">Word Mobile</span><span class="sxs-lookup"><span data-stu-id="9bf27-129">Word mobile</span></span>       | https://office.live.com/start/Word.aspx       |
| <span data-ttu-id="9bf27-130">PowerPoint mobil</span><span class="sxs-lookup"><span data-stu-id="9bf27-130">PowerPoint mobile</span></span> | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a><span data-ttu-id="9bf27-131">Alkalmazások telepítése</span><span class="sxs-lookup"><span data-stu-id="9bf27-131">Install apps</span></span>

<span data-ttu-id="9bf27-132">Az alkalmazások letöltéséhez egy fiókkal kell Microsoft-fiók.</span><span class="sxs-lookup"><span data-stu-id="9bf27-132">To download apps, you'll need to be signed in with a Microsoft account.</span></span> <span data-ttu-id="9bf27-133">Egyes alkalmazások ingyenesek, és azonnal letölthetők.</span><span class="sxs-lookup"><span data-stu-id="9bf27-133">Some apps are free and can be downloaded right away.</span></span> <span data-ttu-id="9bf27-134">A vásárlást igénylő alkalmazásokhoz be kell jelentkeznie az Áruházba a Microsoft-fiók és érvényes fizetési módgal kell lennie.</span><span class="sxs-lookup"><span data-stu-id="9bf27-134">For apps that require a purchase, you must be signed in to the Store with your Microsoft account and have a valid payment method.</span></span>

> [!NOTE]
> <span data-ttu-id="9bf27-135">A fióknak, Microsoft Store kell lennie a bejelentkezett fiókkal.</span><span class="sxs-lookup"><span data-stu-id="9bf27-135">The account you use on Microsoft Store does not have to be the same as the account you are signed in with.</span></span> <span data-ttu-id="9bf27-136">Ha munkahelyi vagy iskolai fiókot használ a HoloLens akkor előfordulhat, hogy be kell jelentkeznie személyes fiókjával az Áruházbeli alkalmazásban a vásárláshoz.</span><span class="sxs-lookup"><span data-stu-id="9bf27-136">If you are using a Work or School account on your HoloLens then you may need to sign in with your personal account in the Store App to make a purchase.</span></span>

> [!TIP]
> <span data-ttu-id="9bf27-137">A fizetési mód beállításához [](https://account.microsoft.com/) válassza a Fizetési account.microsoft.com lehetőséget& **fizetési** lehetőség Fizetési  >    >  **lehetőség hozzáadása lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="9bf27-137">To set up a payment method, go to [account.microsoft.com](https://account.microsoft.com/) and select **Payment & billing** > **Payment options** > **Add a payment option**.</span></span>

1. <span data-ttu-id="9bf27-138">A [ **Start menü megnyitásához**](holographic-home.md)hajtson végre egy [Indítás](/hololens/hololens2-basic-usage#start-gesture) kézmozdulatot vagy [bloom](hololens1-basic-usage.md) kézmozdulatot a HoloLens (1. gen).</span><span class="sxs-lookup"><span data-stu-id="9bf27-138">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="9bf27-139">Válassza ki Microsoft Store alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="9bf27-139">Select the Microsoft Store app.</span></span> <span data-ttu-id="9bf27-140">Az Áruház alkalmazás megnyitása után:</span><span class="sxs-lookup"><span data-stu-id="9bf27-140">After the Store app opens:</span></span>
   1. <span data-ttu-id="9bf27-141">A keresősáv használatával alkalmazásokat kereshet.</span><span class="sxs-lookup"><span data-stu-id="9bf27-141">Use the search bar to look for applications.</span></span> 
   1. <span data-ttu-id="9bf27-142">Válassza ki a kifejezetten a HoloLens alkalmazásokra készült alapvető alkalmazásokat a kiválasztott kategóriák egyikében.</span><span class="sxs-lookup"><span data-stu-id="9bf27-142">Select essential apps or apps made specifically for HoloLens from one of the curated categories.</span></span>
   1. <span data-ttu-id="9bf27-143">Az Áruház alkalmazás jobb felső részen válassza a  **"..."** gombot, majd a Saját könyvtár lehetőséget a korábban megvásárolt alkalmazások megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="9bf27-143">On the top right of the Store app, select the **"..."** button and then select **My Library** to view any previously purchased apps.</span></span>

1. <span data-ttu-id="9bf27-144">Válassza **a Lekért** **vagy** Telepítés lehetőséget az alkalmazás oldalán (előfordulhat, hogy vásárlásra van szükség).</span><span class="sxs-lookup"><span data-stu-id="9bf27-144">Select **Get** or **Install** on the application's page (a purchase may be required).</span></span>

## <a name="update-apps"></a><span data-ttu-id="9bf27-145">Alkalmazások frissítése</span><span class="sxs-lookup"><span data-stu-id="9bf27-145">Update Apps</span></span>

<span data-ttu-id="9bf27-146">Ha frissítenie kell egy, a Microsoft Store telepített alkalmazást, az alkalmazást a Microsoft Store frissítheti.</span><span class="sxs-lookup"><span data-stu-id="9bf27-146">To update an app you installed from the Microsoft Store, you can update the app from the Microsoft Store app.</span></span> <span data-ttu-id="9bf27-147">Az alkalmazáshoz telepített Microsoft Store Vállalatoknak frissítheti is az alkalmazásokat a Microsoft Store Vállalatoknak.</span><span class="sxs-lookup"><span data-stu-id="9bf27-147">For apps installed for the Microsoft Store for Business, you can also update those apps from the Microsoft Store for Business.</span></span> 

1. <span data-ttu-id="9bf27-148">A [ **Start menü megnyitásához**](holographic-home.md)hajtson végre egy [Indítás](/hololens/hololens2-basic-usage#start-gesture) kézmozdulatot vagy [bloom](hololens1-basic-usage.md) kézmozdulatot a HoloLens (1. gen).</span><span class="sxs-lookup"><span data-stu-id="9bf27-148">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="9bf27-149">Válassza ki az Áruház alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="9bf27-149">Select the Store app.</span></span>

1. <span data-ttu-id="9bf27-150">Keresse meg az Áruház alkalmazás jobb felső sarokban.</span><span class="sxs-lookup"><span data-stu-id="9bf27-150">Look to the top right of the Store app.</span></span> 

1. <span data-ttu-id="9bf27-151">Válassza a **"..."** vagy a "További információ" gombot.</span><span class="sxs-lookup"><span data-stu-id="9bf27-151">Select the **"..."** or “See more” button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9bf27-152">![Microsoft Store alkalmazás képernyőképe.](images/store-update-1.png)</span><span class="sxs-lookup"><span data-stu-id="9bf27-152">![Microsoft Store app screenshot.](images/store-update-1.png)</span></span>

1. <span data-ttu-id="9bf27-153">Válassza **a Letöltések és frissítések lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="9bf27-153">Select **Downloads and updates**.</span></span>
    1. <span data-ttu-id="9bf27-154">Ha az eszköz korábban már azonosított frissítéseket, előfordulhat, hogy egy lefelé mutató nyíl és egy szám jelöli a függőben lévő frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="9bf27-154">If your device has previously identified updates, there may be a down arrow and a number that represents pending updates.</span></span>

1. <span data-ttu-id="9bf27-155">Válassza a **Frissítések lekérte lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="9bf27-155">Select **Get updates**.</span></span> <span data-ttu-id="9bf27-156">Az eszköz most frissítéseket keres, és be fogja állítani őket letöltésre és telepítésre.</span><span class="sxs-lookup"><span data-stu-id="9bf27-156">Your device will now search for updates and set them to download and install.</span></span> 
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9bf27-157">![Microsoft Store képernyőkép a frissítések lekért alkalmazásról.](images/store-update-2.png.jpg)</span><span class="sxs-lookup"><span data-stu-id="9bf27-157">![Microsoft Store app screenshot of getting updates..](images/store-update-2.png.jpg)</span></span>

> [!NOTE]
> <span data-ttu-id="9bf27-158">Ha az eszközön található alkalmazásokat a szervezet terjesztette, ugyanezekkel a kereskedelmi alkalmazáskezelési módszerekkel frissíthetők.</span><span class="sxs-lookup"><span data-stu-id="9bf27-158">If the apps on your device were distributed by your organization they can be updated through the same commercial app management methods.</span></span> <span data-ttu-id="9bf27-159">Ha ez az Ön helyzetére vonatkozik, további információt a kereskedelmi alkalmazások üzembe [helyezésének áttekintésében talál.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9bf27-159">If this applies to your situation, read more via our [overview of commercial app deployment.](app-deploy-overview.md)</span></span>
>
> <span data-ttu-id="9bf27-160">Ha egy saját telepítésű vagy üzembe helyezett egyéni alkalmazást szeretne frissíteni, ugyanezt a módszert kell használnia az alkalmazás frissített verziójával.</span><span class="sxs-lookup"><span data-stu-id="9bf27-160">If you would like to update a custom app that has been sideloaded or deployed, you will need to use the same method with the updated version of your app.</span></span> <span data-ttu-id="9bf27-161">Ha többet szeretne megtudni az egyéni alkalmazások telepítéséről és futtatásáról, olvassa el az [egyéni holografikus alkalmazásokat.](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="9bf27-161">To learn more about installing and running custom apps, read [custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="uninstall-apps"></a><span data-ttu-id="9bf27-162">Alkalmazások eltávolítása</span><span class="sxs-lookup"><span data-stu-id="9bf27-162">Uninstall apps</span></span>

<span data-ttu-id="9bf27-163">Az alkalmazások háromféleképpen távolíthatók el.</span><span class="sxs-lookup"><span data-stu-id="9bf27-163">There are three ways to uninstall applications.</span></span> <span data-ttu-id="9bf27-164">Az alkalmazásokat a Microsoft Store, Start menü vagy a Gépház.</span><span class="sxs-lookup"><span data-stu-id="9bf27-164">You can uninstall applications through the Microsoft Store, Start menu or from Settings.</span></span> 

> [!WARNING]
> <span data-ttu-id="9bf27-165">Nem távolíthat el rendszeralkalmazást vagy a Microsoft Store magát.</span><span class="sxs-lookup"><span data-stu-id="9bf27-165">You can not uninstall a system app or the Microsoft Store itself.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9bf27-166">Ha a 2. HoloLens felhasználó több felhasználóval rendelkezik, az alkalmazás eltávolításához az alkalmazást telepítő felhasználóként kell bejelentkeznie.</span><span class="sxs-lookup"><span data-stu-id="9bf27-166">If your HoloLens 2 has multiple users, you must be logged in as the user who installed the app to uninstall it.</span></span> 

### <a name="uninstall-from-the-microsoft-store"></a><span data-ttu-id="9bf27-167">Eltávolítás a Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="9bf27-167">Uninstall from the Microsoft Store</span></span>

<span data-ttu-id="9bf27-168">Nyissa meg Microsoft Store a **Start** menüből, majd keresse meg az eltávolítani kívánt alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="9bf27-168">Open the Microsoft Store from the **Start** menu, and then browse for the application you want to uninstall.</span></span>  <span data-ttu-id="9bf27-169">Az Áruház lapon minden telepített alkalmazás rendelkezik egy **Eltávolítás gombbal.**</span><span class="sxs-lookup"><span data-stu-id="9bf27-169">On the Store page, each installed application has an **Uninstall** button.</span></span>

### <a name="uninstall-from-the-start-menu"></a><span data-ttu-id="9bf27-170">Eltávolítás a Start menü</span><span class="sxs-lookup"><span data-stu-id="9bf27-170">Uninstall from the Start menu</span></span>

<span data-ttu-id="9bf27-171">A **Start menüben** vagy a **Minden alkalmazás** nyissa meg az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="9bf27-171">On the **Start** menu or in the **All apps** list, browse to the app.</span></span> <span data-ttu-id="9bf27-172">Válassza ki és tartsa lenyomva, amíg meg nem jelenik a menü, majd válassza az **Eltávolítás lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="9bf27-172">Select and hold until the menu appears, then select **Uninstall**.</span></span>

### <a name="uninstall-from-settings"></a><span data-ttu-id="9bf27-173">Eltávolítás Gépház</span><span class="sxs-lookup"><span data-stu-id="9bf27-173">Uninstall from Settings</span></span>
<span data-ttu-id="9bf27-174">A **Start menüben** válassza a Gépház **-> lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="9bf27-174">On the **Start** menu, select **Settings -> Apps.**</span></span> <span data-ttu-id="9bf27-175">Keresse meg az alkalmazást a listában, jelölje ki, majd kattintson az **Eltávolítás gombra.**</span><span class="sxs-lookup"><span data-stu-id="9bf27-175">Find the app from the list, select it and then click **Uninstall**.</span></span>

<span data-ttu-id="9bf27-176">Ha nem sikerül eltávolítania egy alkalmazást, kérjük, [visszajelzést](/hololens/hololens-feedback) a Visszajelzési központ.</span><span class="sxs-lookup"><span data-stu-id="9bf27-176">If you are unable to uninstall an app, please file [feedback](/hololens/hololens-feedback) using the Feedback Hub.</span></span>
