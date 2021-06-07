---
title: Kiépítési csomag
description: Ismerje meg az alkalmazások csomagolását, üzembe helyezését, üzembe helyezését és üzembe helyezését HoloLens-eszközökhöz.
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378086"
---
# <a name="provisioning-package"></a><span data-ttu-id="2c3fe-104">Kiépítési csomag</span><span class="sxs-lookup"><span data-stu-id="2c3fe-104">Provisioning Package</span></span>

<span data-ttu-id="2c3fe-105">A kiépítési csomagokkal előkészítheti és konfigurálhatja az eszközöket egy környezetben anélkül, hogy hozzáféréssel kellene rendelkeznie a végpontkezeléshez.</span><span class="sxs-lookup"><span data-stu-id="2c3fe-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="2c3fe-106">Az eszközök a felhasználó identitásától, a regisztrációs állapottól, a OOBE (OOBE) használata során, illetve a telepítés során egy kiépítési csomag alkalmazásával is üzembe [helyezhetők.](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="2c3fe-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="2c3fe-107">A kiépítési csomagokra vonatkozó szempontok:</span><span class="sxs-lookup"><span data-stu-id="2c3fe-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="2c3fe-108">Nem nyilvános alkalmazások</span><span class="sxs-lookup"><span data-stu-id="2c3fe-108">Non-Public apps</span></span>
* <span data-ttu-id="2c3fe-109">Csak USB-s oldalbetöltés</span><span class="sxs-lookup"><span data-stu-id="2c3fe-109">USB side-load only</span></span>
* <span data-ttu-id="2c3fe-110">Nincs automatikus frissítés (manuális frissítést igényel a PPKG-k segítségével)</span><span class="sxs-lookup"><span data-stu-id="2c3fe-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="2c3fe-111">A kiépítési csomaggal telepített alkalmazásokat a helyi gép tárolójában található tanúsítvánnyal kell aláírni.</span><span class="sxs-lookup"><span data-stu-id="2c3fe-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="2c3fe-112">A kiépítési csomagok csak az eszköz (helyi gép) tárolójára telepíthetnek tanúsítványokat, ezért az alkalmazás és a tanúsítvány is telepíthető ugyanazokkal a kiépítési csomagokkal.</span><span class="sxs-lookup"><span data-stu-id="2c3fe-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="2c3fe-113">Ha a tanúsítványt az MDM-ről telepíti, vagy a Tanúsítványkezelővel [telepíti,](certificate-manager.md)akkor a tanúsítványt a helyi számítógép-tárolóban kell telepítenie, hogy ezzel a módszerrel alá tudja írni a telepített alkalmazásokat.</span><span class="sxs-lookup"><span data-stu-id="2c3fe-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="2c3fe-114">A HoloLens-eszközökhöz használható kiépítési csomag létrehozásának alapjait a [HoloLens provisioning (HoloLens-kiépítés) cikk tartalmazza.](https://docs.microsoft.com/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="2c3fe-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="2c3fe-115">Az alkalmazások üzembe helyezéséhez speciális kiépítéssel kell kezdenie.</span><span class="sxs-lookup"><span data-stu-id="2c3fe-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="2c3fe-116">A HoloLens (1. generációs) korlátozott mértékben támogatja az alkalmazások telepítését **(UniversalAppInstall**) egy kiépítési csomag használatával.</span><span class="sxs-lookup"><span data-stu-id="2c3fe-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="2c3fe-117">A HoloLens- (1. generációs) eszközök csak az OOBE és csak a felhasználói környezet telepítése esetén támogatják az alkalmazások PPKG-n keresztüli telepítését.</span><span class="sxs-lookup"><span data-stu-id="2c3fe-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="2c3fe-118">Telepítés</span><span class="sxs-lookup"><span data-stu-id="2c3fe-118">Setup</span></span>

<span data-ttu-id="2c3fe-119">A [Windows Configuration Designerben](https://www.microsoft.com/store/productId/9NBLGGH4TX22) kövesse az alábbi négy lépést.</span><span class="sxs-lookup"><span data-stu-id="2c3fe-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="2c3fe-120">Állítsa az ApplicationManagement/AllowAllTrustedApps halmazt "Igen" -ra.</span><span class="sxs-lookup"><span data-stu-id="2c3fe-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="2c3fe-121">Lásd: [ApplicationManagement/AllowAllTrustedApps.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)</span><span class="sxs-lookup"><span data-stu-id="2c3fe-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="2c3fe-122">Lépjen a **UniversalAppInstall**  >  **UserContextAppLicense pontra, és** adja meg **a PackageFamilyName nevet.**</span><span class="sxs-lookup"><span data-stu-id="2c3fe-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="2c3fe-123">Lásd: [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="2c3fe-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="2c3fe-124">Lásd még: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="2c3fe-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="2c3fe-125">Használhatja a Eszközportál olyan eszközön, amelyre már telepítette az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="2c3fe-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="2c3fe-126">Látogasson el az Alkalmazások oldalra, és nézze meg a PackageRelativeID sort, az összes információt a "!" A **PackageFamilyName .**</span><span class="sxs-lookup"><span data-stu-id="2c3fe-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="2c3fe-127">Ezután látni fogja, hogy van egy új szakasza, az **ApplicationFile.**</span><span class="sxs-lookup"><span data-stu-id="2c3fe-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="2c3fe-128">Ezen a területen töltheti fel az appx-csomagot.</span><span class="sxs-lookup"><span data-stu-id="2c3fe-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="2c3fe-129">Attól függően, hogy megvásárolta az alkalmazást, vagy saját LOB-alkalmazást épített, fel kell töltenie a licencfájlt vagy a biztonsági tanúsítványt.</span><span class="sxs-lookup"><span data-stu-id="2c3fe-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="2c3fe-130">Licencfájl: lépjen a **UniversalAppInstall**  >  **UserContextAppLicence** elemre, keresse meg a licenc helyét, és töltse fel.</span><span class="sxs-lookup"><span data-stu-id="2c3fe-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="2c3fe-131">A biztonsági fájlhoz lépjen a Tanúsítványok **lapra,** és válassza ki az .appx csomaggal együtt telepíteni kívánt tanúsítványt.</span><span class="sxs-lookup"><span data-stu-id="2c3fe-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="2c3fe-132">Mindenképpen mentse a projektet egy biztonságos helyre.</span><span class="sxs-lookup"><span data-stu-id="2c3fe-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="2c3fe-133">Ezután **exportálja** **kiépítési csomagként.**</span><span class="sxs-lookup"><span data-stu-id="2c3fe-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="2c3fe-134">Lásd még: [A kiépítési csomag alkalmazása a HoloLensre.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="2c3fe-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
