---
title: Egyéni alkalmazások kezelése HoloLens (1. generációs)
description: Megtudhatja, hogyan telepíthet, távolíthat el és telepíthet egyéni holografikus alkalmazásokat HoloLens eszközökön a Eszközportál és Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: a179032978e1fc062273a6754e3b0a1ad50a5211
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635908"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="a4ed4-104">Egyéni alkalmazások kezelése HoloLens (1. generációs)</span><span class="sxs-lookup"><span data-stu-id="a4ed4-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="a4ed4-105">HoloLens számos meglévő alkalmazást támogat a Microsoft Store, valamint a kifejezetten a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a4ed4-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="a4ed4-106">Ez a cikk az egyéni holografikus alkalmazásokkal foglalkozik.</span><span class="sxs-lookup"><span data-stu-id="a4ed4-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="a4ed4-107">További információ az áruházbeli alkalmazásokról: [Alkalmazások kezelése az áruházban.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="a4ed4-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4ed4-108">Az alábbi információk az HoloLens (1. generációs) kiadáshoz, más néven HoloLens Developer Editionhez készültek.</span><span class="sxs-lookup"><span data-stu-id="a4ed4-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="a4ed4-109">Ezért az alkalmazások eszközportálon keresztüli telepítése és az alkalmazások telepítése Visual Studio gyakori volt.</span><span class="sxs-lookup"><span data-stu-id="a4ed4-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="a4ed4-110">Nagyvállalati környezetek esetén nem javasoljuk a Fejlesztői mód engedélyezését, amelyet mindkét módszer használ.</span><span class="sxs-lookup"><span data-stu-id="a4ed4-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="a4ed4-111">Ha egy biztonságos alkalmazástelepítési módszer érdekli, tekintse át az [Alkalmazáskezelés: Áttekintés témakört.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a4ed4-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="a4ed4-112">Ha az alkalmazástelepítés fejlesztői módszerét keresi HoloLens 2 eszköz esetén, tekintse meg a következőt:</span><span class="sxs-lookup"><span data-stu-id="a4ed4-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
>
> - [<span data-ttu-id="a4ed4-113">Eszközportál: Alkalmazás telepítése</span><span class="sxs-lookup"><span data-stu-id="a4ed4-113">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="a4ed4-114">Alkalmazások Visual Studio és hibakeresése a Visual Studio használatával</span><span class="sxs-lookup"><span data-stu-id="a4ed4-114">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="a4ed4-115">Egyedi alkalmazások telepítése</span><span class="sxs-lookup"><span data-stu-id="a4ed4-115">Install custom apps</span></span>

<span data-ttu-id="a4ed4-116">Saját alkalmazásokat telepíthet a HoloLens a Eszközportál vagy az alkalmazások központi telepítésének Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a4ed4-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="a4ed4-117">Alkalmazáscsomag telepítése a Eszközportál</span><span class="sxs-lookup"><span data-stu-id="a4ed4-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="a4ed4-118">Hozzon létre kapcsolatot a [Eszközportál](/windows/mixed-reality/using-the-windows-device-portal) és a cél HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a4ed4-118">Establish a connection from [Device Portal](/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="a4ed4-119">A bal oldali navigációs sávon lépjen az **Alkalmazások lapra.**</span><span class="sxs-lookup"><span data-stu-id="a4ed4-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="a4ed4-120">Az **Alkalmazáscsomag alatt** keresse meg az alkalmazáshoz társított .appx fájlt.</span><span class="sxs-lookup"><span data-stu-id="a4ed4-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="a4ed4-121">Győződjön meg arról, hogy a társított függőségi és tanúsítványfájlokra hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="a4ed4-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="a4ed4-122">Válassza az **Ugrás lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="a4ed4-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a4ed4-123">![Alkalmazásűrlap telepítése Windows Eszközportál a Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="a4ed4-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="a4ed4-124">Üzembe helyezés a Microsoft Visual Studio 2015-ről</span><span class="sxs-lookup"><span data-stu-id="a4ed4-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="a4ed4-125">Nyissa meg az alkalmazás Visual Studio megoldását (.sln fájl).</span><span class="sxs-lookup"><span data-stu-id="a4ed4-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="a4ed4-126">Nyissa meg a projekt **Properties (Tulajdonságok) tulajdonságát.**</span><span class="sxs-lookup"><span data-stu-id="a4ed4-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="a4ed4-127">Válassza ki a következő buildkonfigurációt: **Master/x86/Remote Machine.**</span><span class="sxs-lookup"><span data-stu-id="a4ed4-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="a4ed4-128">A Távoli gép **kiválasztásakor:**</span><span class="sxs-lookup"><span data-stu-id="a4ed4-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="a4ed4-129">Győződjön meg arról, hogy a cím a Wi-Fi IP-címére HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a4ed4-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="a4ed4-130">Állítsa a **hitelesítést Universal (Unencrypted Protocol) (Univerzális (Titkosítatlan protokoll) ) beállításra.**</span><span class="sxs-lookup"><span data-stu-id="a4ed4-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="a4ed4-131">Készítse el a megoldást.</span><span class="sxs-lookup"><span data-stu-id="a4ed4-131">Build your solution.</span></span>

1. <span data-ttu-id="a4ed4-132">Ha a fejlesztői számítógépről telepítenie kell az alkalmazást a HoloLens válassza a **Távoli gép lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="a4ed4-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="a4ed4-133">Ha már létezik build a HoloLens válassza  az Igen lehetőséget az újabb verzió telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="a4ed4-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Távoli gép üzembe helyezése az alkalmazások Microsoft HoloLens a Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="a4ed4-135">Az alkalmazás automatikusan telepítve és automatikusan elindul a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a4ed4-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="a4ed4-136">Miután telepített egy alkalmazást, a következő listában találja **meg:** Minden alkalmazás (**Indítás**  >  **Minden alkalmazás**).</span><span class="sxs-lookup"><span data-stu-id="a4ed4-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
