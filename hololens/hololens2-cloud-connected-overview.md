---
title: A cloud connected HoloLens 2 with Remote Assist áttekintése
description: Megtudhatja, hogyan regisztrálható HoloLens 2-eszközök felhőhöz csatlakoztatott hálózaton keresztül a Dynamics 365 Remote Assist használatával.
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
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923533"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="49415-104">Üzembe helyezési útmutató – Felhőhöz csatlakoztatott HoloLens 2 Remote Assist segítségével – Áttekintés</span><span class="sxs-lookup"><span data-stu-id="49415-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="49415-105">Ez az útmutató segítséget nyújt az informatikai szakembereknek abban, hogy 2 Microsoft HoloLens a Remote Assist segítségével tervezze meg és telepítsék a szervezetüket.</span><span class="sxs-lookup"><span data-stu-id="49415-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="49415-106">Ez modellként szolgál majd a különböző HoloLens 2-es esetekre vonatkozó, a cégnél a koncepció igazolására szolgáló üzembe helyezéshez.</span><span class="sxs-lookup"><span data-stu-id="49415-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="49415-107">A beállítás hasonló az [A forgatókönyvhöz: Üzembe helyezés felhőalapú csatlakozású eszközökön.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="49415-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="49415-108">Az útmutató során bemutatja, hogyan regisztrálhatóak az eszközök az eszközfelügyeletben, hogyan alkalmazhat licenceket szükség szerint, és hogyan ellenőrizheti, hogy a végfelhasználók képesek-e azonnal használni a Remote Assist eszközt az eszköz beállításakor.</span><span class="sxs-lookup"><span data-stu-id="49415-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="49415-109">Ehhez át fogjuk látni az üzembe helyezéshez és a futtatáshoz szükséges fontos infrastruktúra-részleteket– a HoloLens 2-ben nagy léptékben való üzembe helyezést.</span><span class="sxs-lookup"><span data-stu-id="49415-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="49415-110">Ebben az útmutatóban nem alkalmazunk más eszközkorlátozásokat vagy konfigurációkat, azonban javasoljuk, hogy a befejezés után ismerkedje meg ezeket a lehetőségeket.</span><span class="sxs-lookup"><span data-stu-id="49415-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="49415-111">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="49415-111">Prerequisites</span></span>

<span data-ttu-id="49415-112">A HoloLens 2 üzembe helyezéséhez a következő infrastruktúrát kell üzembe helyezni.</span><span class="sxs-lookup"><span data-stu-id="49415-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="49415-113">Ha nem, az Azure és az Intune beállítását ez az útmutató tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="49415-113">If not, setting up Azure and Intune is included in this guide:</span></span>

- <span data-ttu-id="49415-114">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="49415-114">Wi-Fi</span></span>
    - <span data-ttu-id="49415-115">A hálózatok általában nyitva vannak az internet és a felhőszolgáltatások számára</span><span class="sxs-lookup"><span data-stu-id="49415-115">Networks are typically open to the Internet and Cloud services</span></span>
- <span data-ttu-id="49415-116">Azure Active Directory (Azure AD) Csatlakozás az MDM automatikus regisztrációjával[(Azure AD P1 előfizetés](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) szükséges)</span><span class="sxs-lookup"><span data-stu-id="49415-116">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="49415-117">MDM (Intune) által felügyelt</span><span class="sxs-lookup"><span data-stu-id="49415-117">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="49415-118">Egy vagy több alkalmazás MDM-en keresztül van telepítve.</span><span class="sxs-lookup"><span data-stu-id="49415-118">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="49415-119">A felhasználók a saját vállalati fiókjukkal (Azure AD) jelentkeznek be</span><span class="sxs-lookup"><span data-stu-id="49415-119">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="49415-120">Eszközönként egy vagy több felhasználó támogatott.</span><span class="sxs-lookup"><span data-stu-id="49415-120">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Felhőhöz csatlakoztatott forgatókönyv" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="49415-122">Tudnivalók a Remote Assist szolgáltatásról</span><span class="sxs-lookup"><span data-stu-id="49415-122">Learn about Remote Assist</span></span>

<span data-ttu-id="49415-123">A Remote Assist lehetővé teszi az együttműködésen alapuló karbantartást és javítást, a távvizsgálatot, valamint a tudás megosztását és betanítását.</span><span class="sxs-lookup"><span data-stu-id="49415-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="49415-124">Ha különböző szerepkörökben és helyeken található személyeket kapcsol össze, a Remote Assist segítségével a technikusok egy távoli közreműködővel is csatlakozhatnak a Microsoft Teamsben.</span><span class="sxs-lookup"><span data-stu-id="49415-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="49415-125">A videók, képernyőképek és jegyzetek kombinálása valós időben oldják meg a problémákat, még akkor is,&#39;nem ugyanazon a helyen vannak.</span><span class="sxs-lookup"><span data-stu-id="49415-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="49415-126">A távoli közreműködők referenciaképeket, sémákat és egyéb hasznos információkat szúrnak be a technikusok&#39;fizikai tárhelyén, hogy hivatkozni tudjanak a sémára, miközben fej-felfelé és kéz nélkül dolgoznak a HoloLensen.</span><span class="sxs-lookup"><span data-stu-id="49415-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="49415-127">Remote Assist – licencelés és követelmények</span><span class="sxs-lookup"><span data-stu-id="49415-127">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="49415-128">Azure AD-fiók (az előfizetés megvásárlásához és a licencek hozzárendeléséhez szükséges)</span><span class="sxs-lookup"><span data-stu-id="49415-128">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="49415-129">[Remote Assist-előfizetés](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (vagy [Remote Assist próbaverzió)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="49415-129">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="49415-130">Dynamics 365 Remote Assist-felhasználó</span><span class="sxs-lookup"><span data-stu-id="49415-130">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="49415-131">Remote Assist-licenc</span><span class="sxs-lookup"><span data-stu-id="49415-131">Remote Assist license</span></span>
- <span data-ttu-id="49415-132">Hálózati kapcsolat</span><span class="sxs-lookup"><span data-stu-id="49415-132">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="49415-133">Microsoft Teams-felhasználó</span><span class="sxs-lookup"><span data-stu-id="49415-133">Microsoft Teams user</span></span>

- <span data-ttu-id="49415-134">Microsoft Teams vagy [Teams Freemium](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="49415-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="49415-135">Hálózati kapcsolat</span><span class="sxs-lookup"><span data-stu-id="49415-135">Network connectivity</span></span>

<span data-ttu-id="49415-136">Ha ezt a [](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)több-bérlős forgatókönyvet tervezi, előfordulhat, hogy információ-korlátok licencre van szüksége.</span><span class="sxs-lookup"><span data-stu-id="49415-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="49415-137">Ebből [a cikkből megállapíthatja,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) hogy szükség van-e information barrier licencre.</span><span class="sxs-lookup"><span data-stu-id="49415-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="49415-138">Ebben az útmutatóban a következőt fogja:</span><span class="sxs-lookup"><span data-stu-id="49415-138">In this guide you will:</span></span>

<span data-ttu-id="49415-139">Készítsen:</span><span class="sxs-lookup"><span data-stu-id="49415-139">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="49415-140">Ismerje meg a HoloLens 2-eszközök infrastruktúrájának alapvető tudnivalókat.</span><span class="sxs-lookup"><span data-stu-id="49415-140">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="49415-141">Tudjon meg többet az Azure AD-ről, és állítson be egyet,&#39;még nem használja.</span><span class="sxs-lookup"><span data-stu-id="49415-141">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="49415-142">Tudnivalók az identitáskezelésről és az Azure AD-fiókok legjobb beállításáról.</span><span class="sxs-lookup"><span data-stu-id="49415-142">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="49415-143">További információ az MDM-ről és az Intune beállításról, ha&#39;még nem készült el.</span><span class="sxs-lookup"><span data-stu-id="49415-143">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="49415-144">Ismerje meg a Remote Assist hálózati követelményeit.</span><span class="sxs-lookup"><span data-stu-id="49415-144">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="49415-145">Választható lehetőség: VPN a szervezeti erőforrásokhoz való csatlakozáshoz</span><span class="sxs-lookup"><span data-stu-id="49415-145">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="49415-146">Konfigurálja:</span><span class="sxs-lookup"><span data-stu-id="49415-146">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="49415-147">Felhasználók és csoportok létrehozása.</span><span class="sxs-lookup"><span data-stu-id="49415-147">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="49415-148">Automatikus regisztráció beállítása az Azure AD-ban.</span><span class="sxs-lookup"><span data-stu-id="49415-148">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="49415-149">Az alkalmazáslicencek hozzárendelése.</span><span class="sxs-lookup"><span data-stu-id="49415-149">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="49415-150">Üzembe helyezés:</span><span class="sxs-lookup"><span data-stu-id="49415-150">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="49415-151">A HoloLens 2 beállítása és a regisztráció ellenőrzése.</span><span class="sxs-lookup"><span data-stu-id="49415-151">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="49415-152">Ellenőrizze, hogy tud-e Remote Assist-hívást hívni.</span><span class="sxs-lookup"><span data-stu-id="49415-152">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="49415-153">Fenntartani:</span><span class="sxs-lookup"><span data-stu-id="49415-153">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="49415-154">A Remote Assist frissítése a Microsoft Store használatával.</span><span class="sxs-lookup"><span data-stu-id="49415-154">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="49415-155">Támogatási csomag készítés.</span><span class="sxs-lookup"><span data-stu-id="49415-155">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="49415-156">Fejlesztési terv.</span><span class="sxs-lookup"><span data-stu-id="49415-156">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="49415-157">Következő lépés</span><span class="sxs-lookup"><span data-stu-id="49415-157">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="49415-158">Felhőhöz csatlakoztatott üzemelő példány – Előkészítés</span><span class="sxs-lookup"><span data-stu-id="49415-158">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

