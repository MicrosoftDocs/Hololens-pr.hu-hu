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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378010"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="6fd64-104">Üzembe helyezési útmutató – Felhőhöz csatlakoztatott HoloLens 2 Remote Assist segítségével – Áttekintés</span><span class="sxs-lookup"><span data-stu-id="6fd64-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="6fd64-105">Ez az útmutató segítséget nyújt az informatikai szakembereknek Microsoft HoloLens 2-es eszköz tervezésében és üzembe helyezésében azzal a céllal, hogy a Dynamics 365 Remote Assist használatra kész, felhőbeli kapcsolatot nyújt a szervezettel.</span><span class="sxs-lookup"><span data-stu-id="6fd64-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="6fd64-106">Ne feledje, hogy ez modellként szolgál majd a különböző HoloLens 2-es esetekre vonatkozó, a cégnél a koncepció igazolására szolgáló üzembe helyezéshez.</span><span class="sxs-lookup"><span data-stu-id="6fd64-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="6fd64-107">Az útmutató során bemutatja, hogyan regisztrálhatóak az eszközök az eszközfelügyeletben, hogyan alkalmazhat licenceket szükség szerint, és hogyan ellenőrizheti, hogy a végfelhasználók képesek-e azonnal használni a Remote Assist eszközt az eszköz beállításakor.</span><span class="sxs-lookup"><span data-stu-id="6fd64-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="6fd64-108">Ehhez az üzembe helyezéshez és a futtatáshoz szükséges fontos infrastruktúra-részleteket fogjuk átfedni – a HoloLens 2-ben nagy léptékben való üzembe helyezést.</span><span class="sxs-lookup"><span data-stu-id="6fd64-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

<span data-ttu-id="6fd64-109">[![Felhőhöz csatlakoztatott forgatókönyv ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="6fd64-109">[ ![Cloud connected scenario](./images/deployment-guides-revised-scenario-a.png) ](./images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>
## <a name="in-this-guide"></a><span data-ttu-id="6fd64-110">Ebben az útmutatóban</span><span class="sxs-lookup"><span data-stu-id="6fd64-110">In this Guide</span></span>

<span data-ttu-id="6fd64-111">Ennek az útmutatónak az a konkrét célja, hogy a Remote Assistet a szervezeten belül a HoloLens-eszközökön is bevezesse.</span><span class="sxs-lookup"><span data-stu-id="6fd64-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="6fd64-112">A cél eléréséhez szükséges szükséges szükségleteket is át fogjuk fedni.</span><span class="sxs-lookup"><span data-stu-id="6fd64-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="6fd64-113">Annak érdekében, hogy továbbra is erre a célra összpontosítson, bizonyos előkészítési és konfigurációk előre ki lesznek választva az üzembe helyezésre való optimalizálás vagy a konfigurálni szükséges elemek csökkentése érdekében.</span><span class="sxs-lookup"><span data-stu-id="6fd64-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="6fd64-114">Értesülni fog ezekről a lehetőségekről, és az üzleti igényeinek megfelelően testre szabhatja az üzemelő példányát.</span><span class="sxs-lookup"><span data-stu-id="6fd64-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="6fd64-115">Ez a beállítás hasonló az [A forgatókönyvhöz:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)Üzembe helyezés felhőalapú csatlakozású eszközökön , amely számos koncepció igazolási üzembe helyezéshez jó választás, többek között a következőkhöz:</span><span class="sxs-lookup"><span data-stu-id="6fd64-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="6fd64-116">Wi-Fi hálózatok általában teljesen nyitva vannak az internet és a felhőszolgáltatások számára</span><span class="sxs-lookup"><span data-stu-id="6fd64-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="6fd64-117">Azure AD-csatlakozás automatikus MDM-regisztrációval – MDM (Intune) által felügyelt</span><span class="sxs-lookup"><span data-stu-id="6fd64-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="6fd64-118">A felhasználók a saját vállalati fiókjukkal (Azure AD) jelentkeznek be</span><span class="sxs-lookup"><span data-stu-id="6fd64-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="6fd64-119">Egy vagy több felhasználó támogatott eszközönként</span><span class="sxs-lookup"><span data-stu-id="6fd64-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="6fd64-120">Az eszköz zárolási konfigurációjának különböző szintjei adott esetekben alkalmazhatók, a Teljesen nyitotttól az egyalkalmazásos kioszkig</span><span class="sxs-lookup"><span data-stu-id="6fd64-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>



<span data-ttu-id="6fd64-121">Ebben az útmutatóban nem alkalmazunk más eszközkorlátozásokat vagy konfigurációkat, azonban javasoljuk, hogy a befejezés után ismerkedje meg ezeket a lehetőségeket.</span><span class="sxs-lookup"><span data-stu-id="6fd64-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="6fd64-122">Tudnivalók a Remote Assist szolgáltatásról</span><span class="sxs-lookup"><span data-stu-id="6fd64-122">Learn about Remote Assist</span></span>

<span data-ttu-id="6fd64-123">A Remote Assist lehetővé teszi az együttműködésen alapuló karbantartást és javítást, a távvizsgálatot, valamint a tudás megosztását és betanítását.</span><span class="sxs-lookup"><span data-stu-id="6fd64-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="6fd64-124">Ha különböző szerepkörökben és helyeken található személyeket kapcsol össze, a Remote Assist segítségével a technikusok a Microsoft Teams távoli közreműködőivel is csatlakozhatnak.</span><span class="sxs-lookup"><span data-stu-id="6fd64-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="6fd64-125">A videók, képernyőképek és jegyzetek kombinálása valós időben oldják meg a problémákat, még akkor is,&#39;nem ugyanazon a helyen vannak.</span><span class="sxs-lookup"><span data-stu-id="6fd64-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="6fd64-126">A távoli közreműködők referenciaképeket, sémákat és egyéb hasznos információkat szúrnak be a technikusok&#39;fizikai tárhelyén, hogy hivatkozni tudjanak a sémára, miközben fej-felfelé és kéz nélkül dolgoznak a HoloLensen.</span><span class="sxs-lookup"><span data-stu-id="6fd64-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="6fd64-127">Ebben az útmutatóban a következőt fogja:</span><span class="sxs-lookup"><span data-stu-id="6fd64-127">In this guide you will:</span></span>

<span data-ttu-id="6fd64-128">Készítsen:</span><span class="sxs-lookup"><span data-stu-id="6fd64-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="6fd64-129">Ismerje meg a HoloLens 2-eszközök infrastruktúrájának alapvető tudnivalókat.</span><span class="sxs-lookup"><span data-stu-id="6fd64-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="6fd64-130">Tudjon meg többet az Azure AD-ről, és állítson be egyet,&#39;még nem használja.</span><span class="sxs-lookup"><span data-stu-id="6fd64-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="6fd64-131">Tudnivalók az identitáskezelésről és az Azure AD-fiókok legjobb beállításáról.</span><span class="sxs-lookup"><span data-stu-id="6fd64-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="6fd64-132">További információ az MDM-ről és az Intune beállításról, ha&#39;még nem készült el.</span><span class="sxs-lookup"><span data-stu-id="6fd64-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="6fd64-133">Ismerje meg a Remote Assist hálózati követelményeit.</span><span class="sxs-lookup"><span data-stu-id="6fd64-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="6fd64-134">Választható lehetőség: VPN a szervezeti erőforrásokhoz való csatlakozáshoz</span><span class="sxs-lookup"><span data-stu-id="6fd64-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="6fd64-135">Konfigurálja:</span><span class="sxs-lookup"><span data-stu-id="6fd64-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="6fd64-136">Felhasználók és csoportok létrehozása.</span><span class="sxs-lookup"><span data-stu-id="6fd64-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="6fd64-137">Automatikus regisztráció beállítása az Azure AD-ban.</span><span class="sxs-lookup"><span data-stu-id="6fd64-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="6fd64-138">Az alkalmazáslicencek hozzárendelése.</span><span class="sxs-lookup"><span data-stu-id="6fd64-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="6fd64-139">Üzembe helyezés:</span><span class="sxs-lookup"><span data-stu-id="6fd64-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="6fd64-140">A HoloLens 2 beállítása és a regisztráció ellenőrzése.</span><span class="sxs-lookup"><span data-stu-id="6fd64-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="6fd64-141">Ellenőrizze, hogy tud-e Remote Assist-hívást hívni.</span><span class="sxs-lookup"><span data-stu-id="6fd64-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="6fd64-142">Fenntartani:</span><span class="sxs-lookup"><span data-stu-id="6fd64-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="6fd64-143">A Remote Assist frissítése a Microsoft Store használatával.</span><span class="sxs-lookup"><span data-stu-id="6fd64-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="6fd64-144">Támogatási csomag készítés.</span><span class="sxs-lookup"><span data-stu-id="6fd64-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="6fd64-145">Fejlesztési terv.</span><span class="sxs-lookup"><span data-stu-id="6fd64-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="6fd64-146">Következő lépés</span><span class="sxs-lookup"><span data-stu-id="6fd64-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6fd64-147">Felhőhöz csatlakoztatott üzemelő példány – Előkészítés</span><span class="sxs-lookup"><span data-stu-id="6fd64-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

