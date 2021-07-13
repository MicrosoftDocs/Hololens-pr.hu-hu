---
title: Kiépítési csomag
description: Ismerje meg az alkalmazások csomagolását, üzembe helyezését, üzembe helyezését és a vállalati alkalmazások üzembe helyezését HoloLens eszközök esetében.
keywords: app, app deployment, enterprise app deployment, provisioning
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5aa554f9e7fdc09c3112b628e0978ac3332bc57d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635517"
---
# <a name="provisioning-package"></a><span data-ttu-id="81893-104">Kiépítési csomag</span><span class="sxs-lookup"><span data-stu-id="81893-104">Provisioning Package</span></span>

<span data-ttu-id="81893-105">A kiépítési csomagokkal előkészítheti és konfigurálhatja az eszközöket egy környezetben anélkül, hogy hozzáféréssel kellene rendelkeznie a végpontkezeléshez.</span><span class="sxs-lookup"><span data-stu-id="81893-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="81893-106">Az eszközök a felhasználó identitásától, a regisztrációs állapottól, az Out of Box (OOBE) használata során, illetve a telepítés során egy kiépítési csomag alkalmazásával is üzembe [helyezhetők.](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="81893-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="81893-107">A kiépítési csomagokra vonatkozó szempontok:</span><span class="sxs-lookup"><span data-stu-id="81893-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="81893-108">Nem nyilvános alkalmazások</span><span class="sxs-lookup"><span data-stu-id="81893-108">Non-Public apps</span></span>
* <span data-ttu-id="81893-109">Csak USB-s oldalbetöltés</span><span class="sxs-lookup"><span data-stu-id="81893-109">USB side-load only</span></span>
* <span data-ttu-id="81893-110">Nincs automatikus frissítés (a PPKG-ken keresztüli manuális frissítést igényel)</span><span class="sxs-lookup"><span data-stu-id="81893-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="81893-111">A kiépítési csomaggal telepített alkalmazásokat a helyi gép tárolójában található tanúsítvánnyal kell aláírni.</span><span class="sxs-lookup"><span data-stu-id="81893-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="81893-112">A kiépítési csomagok csak az eszköz (helyi gép) tárolójára telepíthetnek tanúsítványokat, ezért az alkalmazás és a tanúsítvány is telepíthető ugyanazokkal a kiépítési csomagokkal.</span><span class="sxs-lookup"><span data-stu-id="81893-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="81893-113">Ha ADM-ről telepíti a tanúsítványt, vagy a Tanúsítványkezelővel telepíti, akkor a tanúsítványt a helyi számítógép-tárolóban telepítse az így telepített alkalmazások aláíráshoz. [](certificate-manager.md)</span><span class="sxs-lookup"><span data-stu-id="81893-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="81893-114">A kiépítési csomag létrehozásához szükséges alapvető tudnivalókért látogasson el a HoloLens [provisioning (Kiépítés) HoloLens cikkre.](/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="81893-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](/hololens/hololens-provisioning).</span></span> <span data-ttu-id="81893-115">Egy alkalmazás üzembe helyezéséhez a speciális kiépítéssel kell kezdenie.</span><span class="sxs-lookup"><span data-stu-id="81893-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="81893-116">HoloLens (1. generációs) alkalmazásokat csak korlátozott mértékben támogat **(UniversalAppInstall**) egy kiépítési csomag használatával.</span><span class="sxs-lookup"><span data-stu-id="81893-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="81893-117">HoloLens (1. generációs) eszközök csak az OOBE-n keresztül támogatják az alkalmazások PPKG-n keresztüli telepítését, és csak a felhasználói környezet telepítése esetén.</span><span class="sxs-lookup"><span data-stu-id="81893-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="81893-118">Telepítés</span><span class="sxs-lookup"><span data-stu-id="81893-118">Setup</span></span>

<span data-ttu-id="81893-119">A [Windows Configuration Designerben](https://www.microsoft.com/store/productId/9NBLGGH4TX22) kövesse az alábbi négy lépést.</span><span class="sxs-lookup"><span data-stu-id="81893-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="81893-120">Az ApplicationManagement/AllowAllTrustedApps beállításnál adja meg az "Igen" lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81893-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="81893-121">Lásd: [ApplicationManagement/AllowAllTrustedApps.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)</span><span class="sxs-lookup"><span data-stu-id="81893-121">See: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="81893-122">Lépjen a **UniversalAppInstall**  >  **UserContextAppLicense lapra,** és adja meg a **PackageFamilyName nevet.**</span><span class="sxs-lookup"><span data-stu-id="81893-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="81893-123">Lásd: [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="81893-123">See [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="81893-124">Lásd még: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="81893-124">See also: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="81893-125">A Eszközportál olyan eszközön használhatja, amelybe már telepítette az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="81893-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="81893-126">Látogasson el az Alkalmazások oldalra, és nézze meg a PackageRelativeID sort, amely a "!" A **PackageFamilyName .**</span><span class="sxs-lookup"><span data-stu-id="81893-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="81893-127">Ekkor látni fogja, hogy van egy új, **ApplicationFile nevű szakasza.**</span><span class="sxs-lookup"><span data-stu-id="81893-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="81893-128">Ezen a területen töltheti fel az appx-csomagot.</span><span class="sxs-lookup"><span data-stu-id="81893-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="81893-129">Attól függően, hogy megvásárolta az alkalmazást, vagy saját LOB-alkalmazást épített, fel kell töltenie a licencfájlt vagy a biztonsági tanúsítványt.</span><span class="sxs-lookup"><span data-stu-id="81893-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="81893-130">Licencfájl: lépjen a **UniversalAppInstall**  >  **UserContextAppLicence** elemre, keresse meg és töltse fel a licenc helyét.</span><span class="sxs-lookup"><span data-stu-id="81893-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="81893-131">A biztonsági fájlhoz lépjen a Tanúsítványok **lapra,** és válassza ki az .appx csomag mellé telepíteni kívánt tanúsítványt.</span><span class="sxs-lookup"><span data-stu-id="81893-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="81893-132">Ügyeljen arra, hogy a projektet biztonságos helyre mentse.</span><span class="sxs-lookup"><span data-stu-id="81893-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="81893-133">Ezután **exportálja** **kiépítési csomagként.**</span><span class="sxs-lookup"><span data-stu-id="81893-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="81893-134">Lásd még: [A kiépítési](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)csomag alkalmazása a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="81893-134">See also: [Apply your provisioning package to HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
