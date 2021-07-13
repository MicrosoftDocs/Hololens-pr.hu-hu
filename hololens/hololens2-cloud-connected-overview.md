---
title: A 2. felhőhöz csatlakoztatott HoloLens áttekintése Remote Assist segítségével
description: Megtudhatja, hogyan regisztrálható HoloLens 2 eszköz egy felhőhöz csatlakoztatott hálózaton a Dynamics 365 Remote Assist használatával.
keywords: HoloLens, felügyelet, felhőhöz csatlakoztatott, Remote Assist, AAD, Azure AD, MDM, Mobile Eszközkezelés
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 86d36275d5cf1296ca3e9fec90684a188a29f3f0
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635126"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="4d5fc-104">Üzembe helyezési útmutató – 2. felhőhöz csatlakoztatott HoloLens Remote Assist segítségével – Áttekintés</span><span class="sxs-lookup"><span data-stu-id="4d5fc-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="4d5fc-105">Ez az útmutató segítséget nyújt az informatikai szakembereknek abban, hogy 2 Microsoft HoloLens távoli segítséget nyújtva megtervenék és üzembe helyeznék őket a szervezetben.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="4d5fc-106">Ez modellként szolgál majd a vállalatnál a két különböző HoloLens során a koncepció igazolása üzembe helyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="4d5fc-107">A beállítás hasonló az [A forgatókönyvhöz: Üzembe helyezés a felhőhöz csatlakozott eszközökön.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="4d5fc-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="4d5fc-108">Az útmutató azt is bemutatja, hogyan regisztrálhatóak az eszközök az eszközfelügyeletben, hogyan alkalmazhat licenceket szükség szerint, és hogyan ellenőrizheti, hogy a végfelhasználók képesek-e azonnal használni a Remote Assist eszközt az eszköz beállításakor.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="4d5fc-109">Ehhez át fogjuk látni az infrastruktúra fontos, a beállításhoz és a futtatáshoz szükséges részleteket– a 2. HoloLens nagy léptékű üzembe helyezést.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="4d5fc-110">Ebben az útmutatóban nem alkalmazunk más eszközkorlátozásokat vagy konfigurációkat, azonban javasoljuk, hogy a befejezés után ismerkedje meg ezeket a lehetőségeket.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4d5fc-111">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="4d5fc-111">Prerequisites</span></span>

<span data-ttu-id="4d5fc-112">Az alábbi infrastruktúrát kell üzembe helyezni a 2. HoloLens üzembe helyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="4d5fc-113">Ha nem, az Azure és az Intune beállítását ez az útmutató tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="4d5fc-113">If not, setting up Azure and Intune is included in this guide:</span></span>

<span data-ttu-id="4d5fc-114">Ez a beállítás hasonló az [A forgatókönyvhöz:](/hololens/common-scenarios#scenario-a)Üzembe helyezés felhőalapú csatlakozású eszközökre , ami jó lehetőség számos koncepció igazolása üzembe helyezéséhez, többek között a következőkhöz:</span><span class="sxs-lookup"><span data-stu-id="4d5fc-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="4d5fc-115">Wi-Fi hálózatok általában teljesen nyitva vannak az internet és a felhőszolgáltatások számára</span><span class="sxs-lookup"><span data-stu-id="4d5fc-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="4d5fc-116">Azure AD-csatlakozás automatikus MDM-regisztrációval – MDM (Intune) által felügyelt</span><span class="sxs-lookup"><span data-stu-id="4d5fc-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="4d5fc-117">A felhasználók a saját vállalati fiókjukkal (Azure AD) jelentkeznek be</span><span class="sxs-lookup"><span data-stu-id="4d5fc-117">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="4d5fc-118">Eszközönként egy vagy több felhasználó támogatott.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-118">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Felhőhöz csatlakoztatott forgatókönyv" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="4d5fc-120">Tudnivalók a Remote Assist szolgáltatásról</span><span class="sxs-lookup"><span data-stu-id="4d5fc-120">Learn about Remote Assist</span></span>

<span data-ttu-id="4d5fc-121">A Remote Assist lehetővé teszi az együttműködésen alapuló karbantartást és javítást, távfelügyeletet, valamint tudásmegosztást és képzést.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-121">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="4d5fc-122">Ha különböző szerepkörökben és helyeken található személyeket kapcsol össze, a Remote Assist segítségével egy technikus egy távoli közreműködővel is Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-122">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="4d5fc-123">A videókat, képernyőképeket és jegyzeteket kombinálva valós időben oldják meg a problémákat, még akkor is,&#39;nem ugyanazon a helyen vannak.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-123">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="4d5fc-124">A távoli közreműködők referenciaképeket, sémákat és egyéb hasznos információkat szúrnak be a technikusok&#39;fizikai tárhelyén, így hivatkozni tudnak a sémára, miközben fej- és kéz nélküli munkát végezhetnek HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-124">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="4d5fc-125">Remote Assist – licencelés és követelmények</span><span class="sxs-lookup"><span data-stu-id="4d5fc-125">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="4d5fc-126">Azure AD-fiók (az előfizetés megvásárlásához és a licencek hozzárendeléséhez szükséges)</span><span class="sxs-lookup"><span data-stu-id="4d5fc-126">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="4d5fc-127">[Remote Assist-előfizetés](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (vagy [Remote Assist próbaverzió)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="4d5fc-127">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="4d5fc-128">Dynamics 365 Remote Assist-felhasználó</span><span class="sxs-lookup"><span data-stu-id="4d5fc-128">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="4d5fc-129">Remote Assist-licenc</span><span class="sxs-lookup"><span data-stu-id="4d5fc-129">Remote Assist license</span></span>
- <span data-ttu-id="4d5fc-130">Hálózati kapcsolat</span><span class="sxs-lookup"><span data-stu-id="4d5fc-130">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="4d5fc-131">Microsoft Teams felhasználó</span><span class="sxs-lookup"><span data-stu-id="4d5fc-131">Microsoft Teams user</span></span>

- <span data-ttu-id="4d5fc-132">Microsoft Teams vagy [Teams Freemium .](https://products.office.com/microsoft-teams/free)</span><span class="sxs-lookup"><span data-stu-id="4d5fc-132">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="4d5fc-133">Hálózati kapcsolat</span><span class="sxs-lookup"><span data-stu-id="4d5fc-133">Network connectivity</span></span>

<span data-ttu-id="4d5fc-134">Ha ezt a [több-bérlős](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)forgatókönyvet tervezi, előfordulhat, hogy információs korlátok licencre van szüksége.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-134">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="4d5fc-135">Ebből [a cikkből megállapíthatja,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) hogy szükség van-e information barrier licencre.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-135">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="4d5fc-136">Ebben az útmutatóban a következőt fogja:</span><span class="sxs-lookup"><span data-stu-id="4d5fc-136">In this guide you will:</span></span>

<span data-ttu-id="4d5fc-137">Készítsen:</span><span class="sxs-lookup"><span data-stu-id="4d5fc-137">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="4d5fc-138">Ismerje meg a 2 eszköz HoloLens alapvető infrastruktúráját.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-138">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="4d5fc-139">Tudjon meg többet az Azure AD-ről, és állítson be egyet,&#39;még nem használja.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-139">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="4d5fc-140">Tudnivalók az identitáskezelésről és az Azure AD-fiókok legjobb beállításáról.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-140">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="4d5fc-141">Tudjon meg többet az MDM-ről, és ha még nem&#39;, állítsa be az Intune-t.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-141">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="4d5fc-142">Ismerje meg a Remote Assist hálózatra vonatkozó követelményeit.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-142">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="4d5fc-143">Választható lehetőség: VPN a szervezeti erőforrásokhoz való csatlakozáshoz</span><span class="sxs-lookup"><span data-stu-id="4d5fc-143">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="4d5fc-144">Konfigurálja:</span><span class="sxs-lookup"><span data-stu-id="4d5fc-144">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="4d5fc-145">Felhasználók és csoportok létrehozása.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-145">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="4d5fc-146">Automatikus regisztráció beállítása az Azure AD-ban.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-146">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="4d5fc-147">Az alkalmazáslicencek hozzárendelése.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-147">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="4d5fc-148">Üzembe helyezés:</span><span class="sxs-lookup"><span data-stu-id="4d5fc-148">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="4d5fc-149">Állítsa be a 2 HoloLens- és érvényesítse a regisztrációt.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-149">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="4d5fc-150">Ellenőrizze, hogy tud-e Remote Assist-hívást hívni.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-150">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="4d5fc-151">Fenntartani:</span><span class="sxs-lookup"><span data-stu-id="4d5fc-151">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="4d5fc-152">A Remote Assist frissítése a Microsoft Store alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-152">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="4d5fc-153">Támogatási csomag készítés.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-153">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="4d5fc-154">Fejlesztési terv.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-154">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="4d5fc-155">Következő lépés</span><span class="sxs-lookup"><span data-stu-id="4d5fc-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4d5fc-156">Felhőhöz csatlakoztatott üzemelő példány – Előkészítés</span><span class="sxs-lookup"><span data-stu-id="4d5fc-156">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

