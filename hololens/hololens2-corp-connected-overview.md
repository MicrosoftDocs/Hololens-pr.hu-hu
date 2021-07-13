---
title: Telepítési útmutató – Vállalati csatlakoztatott HoloLens 2 Dynamics 365-útmutatók – Áttekintés
description: Ismerje meg, hogyan regisztrálható HoloLens 2 eszköz a Dynamics 365-útmutatók segítségével egy vállalati csatlakoztatott hálózaton.
keywords: HoloLens, felügyelet, vállalati kapcsolat, Dynamics 365-útmutatók, AAD, Azure AD, MDM, Mobile Eszközkezelés
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637013"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="39ed7-104">Telepítési útmutató – Vállalati csatlakoztatott HoloLens 2 Dynamics 365-útmutatók – Áttekintés</span><span class="sxs-lookup"><span data-stu-id="39ed7-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="39ed7-105">Ez az útmutató segít az informatikai szakembereknek a Dynamics 365-útmutatók (útmutatók) segítségével Microsoft HoloLens 2 eszköz tervezésében és üzembe helyezésében a szervezetben.</span><span class="sxs-lookup"><span data-stu-id="39ed7-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="39ed7-106">Ez az útmutató kiváló a próba- és éles környezetek üzembe helyezéséhez, és hasonló a B forgatókönyvhöz: Üzembe helyezés a szervezet hálózati [útmutatója alapján.](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network)</span><span class="sxs-lookup"><span data-stu-id="39ed7-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="39ed7-107">A koncepció igazolásának tesztelése után ennek az útmutatónak a segítségével integrálja a HoloLens a szervezetbe.</span><span class="sxs-lookup"><span data-stu-id="39ed7-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="39ed7-108">Ebben az útmutatóban azt ismertetjük, hogyan regisztrálhatóak az eszközök a meglévő eszközkezelésben, hogyan alkalmazhat licenceket szükség szerint, és hogyan ellenőrizheti, hogy a végfelhasználók képesek-e Dynamics 365-útmutatót üzemeltetni, valamint hogyan használhatnak egyéni üzletági alkalmazásokat az eszköz beállítása után.</span><span class="sxs-lookup"><span data-stu-id="39ed7-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="39ed7-109">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="39ed7-109">Prerequisites</span></span>

<span data-ttu-id="39ed7-110">A következő infrastruktúrának már a helyén kell lennie:</span><span class="sxs-lookup"><span data-stu-id="39ed7-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="39ed7-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="39ed7-111">Wi-Fi</span></span>
    - <span data-ttu-id="39ed7-112">Belső vállalati hálózat, amely hozzáfér a belső erőforrásokhoz, és korlátozott hozzáféréssel rendelkezik az internethez vagy a felhőszolgáltatásokhoz</span><span class="sxs-lookup"><span data-stu-id="39ed7-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="39ed7-113">Eszközalapú tanúsítványalapú hitelesítés.</span><span class="sxs-lookup"><span data-stu-id="39ed7-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="39ed7-114">Azure Active Directory (Azure AD) Csatlakozás az MDM automatikus regisztrációjával[(Azure AD P1 előfizetés](/azure/active-directory/fundamentals/active-directory-whatis) szükséges)</span><span class="sxs-lookup"><span data-stu-id="39ed7-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="39ed7-115">MDM (Intune) által felügyelt</span><span class="sxs-lookup"><span data-stu-id="39ed7-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="39ed7-116">Egy vagy több alkalmazás MDM-en keresztül van telepítve.</span><span class="sxs-lookup"><span data-stu-id="39ed7-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="39ed7-117">Network (Hálózat)</span><span class="sxs-lookup"><span data-stu-id="39ed7-117">Network</span></span> 
    - <span data-ttu-id="39ed7-118">Tanúsítványok (SCEP vagy PKCS)</span><span class="sxs-lookup"><span data-stu-id="39ed7-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="39ed7-119">Proxy konfigurálása</span><span class="sxs-lookup"><span data-stu-id="39ed7-119">Proxy configuration</span></span>
- <span data-ttu-id="39ed7-120">A felhasználók a saját vállalati fiókjukkal (Azure AD) jelentkeznek be</span><span class="sxs-lookup"><span data-stu-id="39ed7-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="39ed7-121">Eszközönként egy vagy több felhasználó támogatott.</span><span class="sxs-lookup"><span data-stu-id="39ed7-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="39ed7-122">Különböző szintű eszközzárolási konfigurációk alkalmazhatók adott esetekben, a Teljesen nyitotttól az Egyalkalmazásos kioszkig.</span><span class="sxs-lookup"><span data-stu-id="39ed7-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="39ed7-123">Útmutatók a licenceléshez és a követelményekhez</span><span class="sxs-lookup"><span data-stu-id="39ed7-123">Guides Licensing and Requirements</span></span>](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- <span data-ttu-id="39ed7-124">Azure AD-fiók</span><span class="sxs-lookup"><span data-stu-id="39ed7-124">Azure AD account</span></span>
- <span data-ttu-id="39ed7-125">Dynamics 365-útmutatók alkalmazások PC-n és HoloLens</span><span class="sxs-lookup"><span data-stu-id="39ed7-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="39ed7-126">Dynamics 365-útmutatók előfizetés</span><span class="sxs-lookup"><span data-stu-id="39ed7-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="39ed7-127">Microsoft Dataverse (benne)</span><span class="sxs-lookup"><span data-stu-id="39ed7-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="39ed7-128">Power Apps (a csomagban)</span><span class="sxs-lookup"><span data-stu-id="39ed7-128">Power Apps (included)</span></span>
- <span data-ttu-id="39ed7-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="39ed7-129">Power BI Desktop</span></span>
- <span data-ttu-id="39ed7-130">Hálózati kapcsolat</span><span class="sxs-lookup"><span data-stu-id="39ed7-130">Network Connectivity</span></span>

<span data-ttu-id="39ed7-131">[![Vállalati csatlakoztatott hálózat diagramja, 1. fázis ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="39ed7-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="39ed7-132">[![Vállalati csatlakoztatott hálózat diagramja, 2. fázis ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="39ed7-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="39ed7-133">Ebben az útmutatóban a következőt fogja:</span><span class="sxs-lookup"><span data-stu-id="39ed7-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="39ed7-134">Előkészítés</span><span class="sxs-lookup"><span data-stu-id="39ed7-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="39ed7-135">Ismerje meg a 2 eszköz HoloLens alapvető infrastruktúráját.</span><span class="sxs-lookup"><span data-stu-id="39ed7-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="39ed7-136">Tudjon meg többet az Azure AD-ről, és állítson be egyet, ha még nincs ilyen.</span><span class="sxs-lookup"><span data-stu-id="39ed7-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="39ed7-137">Tudnivalók az identitáskezelésről és az Azure AD-fiókok legjobb beállításáról.</span><span class="sxs-lookup"><span data-stu-id="39ed7-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="39ed7-138">További információ az MDM-ről és az Intune beállításról, ha még nincs kész.</span><span class="sxs-lookup"><span data-stu-id="39ed7-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="39ed7-139">Ismerkedjen meg a tanúsítványalapú Wi-Fi-vel.</span><span class="sxs-lookup"><span data-stu-id="39ed7-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="39ed7-140">Ismerkedjen meg a Proxyval.</span><span class="sxs-lookup"><span data-stu-id="39ed7-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="39ed7-141">Az üzletági alkalmazások használatának a saját maga által használt mottója.</span><span class="sxs-lookup"><span data-stu-id="39ed7-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="39ed7-142">További információ a céges útmutatók használatának módjairól.</span><span class="sxs-lookup"><span data-stu-id="39ed7-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="39ed7-143">Konfigurálás</span><span class="sxs-lookup"><span data-stu-id="39ed7-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="39ed7-144">Felhasználók és csoportok létrehozása.</span><span class="sxs-lookup"><span data-stu-id="39ed7-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="39ed7-145">Az automatikus regisztráció beállítása.</span><span class="sxs-lookup"><span data-stu-id="39ed7-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="39ed7-146">Tanúsítványok és profilok beállítása Wi-Fi vállalati kapcsolatokhoz Wi-Fi profilokhoz.</span><span class="sxs-lookup"><span data-stu-id="39ed7-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="39ed7-147">Üzletági (LOB) alkalmazáscsomagok feltöltése és hozzárendelése.</span><span class="sxs-lookup"><span data-stu-id="39ed7-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="39ed7-148">Dynamics 365-útmutatók beállítása.</span><span class="sxs-lookup"><span data-stu-id="39ed7-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="39ed7-149">A kioszkmód konfigurálása (nem kötelező).</span><span class="sxs-lookup"><span data-stu-id="39ed7-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="39ed7-150">A WDAC konfigurálása (nem kötelező).</span><span class="sxs-lookup"><span data-stu-id="39ed7-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="39ed7-151">Üzembe helyezés</span><span class="sxs-lookup"><span data-stu-id="39ed7-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="39ed7-152">Az eszköz és az MDM segítségével történő regisztráció ellenőrzése.</span><span class="sxs-lookup"><span data-stu-id="39ed7-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="39ed7-153">Ellenőrizze az Wi-Fi tanúsítványokat.</span><span class="sxs-lookup"><span data-stu-id="39ed7-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="39ed7-154">Ellenőrizze az LOB-alkalmazás telepítését.</span><span class="sxs-lookup"><span data-stu-id="39ed7-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="39ed7-155">Útmutatók érvényesítése szerzői és üzemeltetési útmutatóval.</span><span class="sxs-lookup"><span data-stu-id="39ed7-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="39ed7-156">Karbantartás</span><span class="sxs-lookup"><span data-stu-id="39ed7-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="39ed7-157">Frissítse HoloLens 2. frissítést.</span><span class="sxs-lookup"><span data-stu-id="39ed7-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="39ed7-158">Útmutatók (áruházbeli alkalmazások) frissítése.</span><span class="sxs-lookup"><span data-stu-id="39ed7-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="39ed7-159">LOB-alkalmazások frissítése.</span><span class="sxs-lookup"><span data-stu-id="39ed7-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="39ed7-160">Fejlesztési terv.</span><span class="sxs-lookup"><span data-stu-id="39ed7-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="39ed7-161">Támogatási csomag készítés.</span><span class="sxs-lookup"><span data-stu-id="39ed7-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="39ed7-162">Eszközkezelési lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="39ed7-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="39ed7-163">Következő lépés</span><span class="sxs-lookup"><span data-stu-id="39ed7-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="39ed7-164">Vállalati csatlakoztatott üzemelő példány – Előkészítés</span><span class="sxs-lookup"><span data-stu-id="39ed7-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
