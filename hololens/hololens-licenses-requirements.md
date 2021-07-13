---
title: Licenckövetelmények
description: Tartsa naprakészen a mobileszköz-kezeléshez, a mobileszköz-kezeléshez, a HoloLens és a Remote Assisthöz szükséges licencelési követelményeket és irányelveket.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: bd7a7d03c81dced4fb66d8ebb176887811e823c9
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640278"
---
# <a name="license-requirements"></a><span data-ttu-id="82498-103">Licenckövetelmények</span><span class="sxs-lookup"><span data-stu-id="82498-103">License requirements</span></span>

## <a name="hololens-2-device-managed"></a><span data-ttu-id="82498-104">HoloLens 2. eszköz (felügyelt)</span><span class="sxs-lookup"><span data-stu-id="82498-104">HoloLens 2 Device (managed)</span></span>

[<span data-ttu-id="82498-105">Azure AD-fiók</span><span class="sxs-lookup"><span data-stu-id="82498-105">Azure AD Account</span></span>](/azure/active-directory/)

> [!IMPORTANT]
> <span data-ttu-id="82498-106">Active Directory (AD) nem használható a HoloLens kezelésére.</span><span class="sxs-lookup"><span data-stu-id="82498-106">Active Directory (AD) cannot be used to manage HoloLens devices.</span></span>

<span data-ttu-id="82498-107">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) másik MDM-et.</span><span class="sxs-lookup"><span data-stu-id="82498-107">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) or another MDM.</span></span>
- <span data-ttu-id="82498-108">[Windows Autopilot for HoloLens 2](hololens2-autopilot.md)– leegyszerűsíti a kiépítési élményt mind a rendszergazdák, mind a végfelhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="82498-108">[Windows Autopilot for HoloLens 2](hololens2-autopilot.md)- simplifies the provisioning experience for both IT admins and end users.</span></span> <span data-ttu-id="82498-109">A rendszergazdák előre konfigurálhatnak HoloLens 2 szabályzatot, és az első rendszerindításkor az eszközök a végfelhasználói beavatkozás nélkül, üzleti használatra kész állapotba lesznek telepítve.</span><span class="sxs-lookup"><span data-stu-id="82498-109">IT admins can preconfigure HoloLens 2 policies, and upon first boot, devices will be deployed in business-ready state with zero end-user interaction.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="82498-110">Windows Az Autopilot használatához [először az Azure P1-et](/azure/active-directory/fundamentals/active-directory-whatis) és az automatikus regisztrációt kell konfigurálni a kis érintéssel használható AutoPilot-folyamathoz és az eszközök üzembe helyezéséhez. [](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="82498-110">Windows Autopilot requires [Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) and [Auto-enrollment](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) to be configured first for the low-touch Autopilot flow and device deployment.</span></span> 

### <a name="business-use-case"></a><span data-ttu-id="82498-111">Üzleti felhasználás esete:</span><span class="sxs-lookup"><span data-stu-id="82498-111">Business Use Case:</span></span> 

- <span data-ttu-id="82498-112">["A" üzembe](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) helyezési forgatókönyv – koncepció igazolása vagy próbatelepítés.</span><span class="sxs-lookup"><span data-stu-id="82498-112">[Deployment Scenario A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - proof-of-concept or pilot deployment.</span></span>

- <span data-ttu-id="82498-113">[B üzembe helyezési](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) forgatókönyv – nagy léptékű üzembe helyezés.</span><span class="sxs-lookup"><span data-stu-id="82498-113">[Deployment Scenario B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - deployment at scale.</span></span>

## <a name="hololens-2-device-only-non-managed"></a><span data-ttu-id="82498-114">HoloLens 2. csak eszköz (nem felügyelt)</span><span class="sxs-lookup"><span data-stu-id="82498-114">HoloLens 2 Device-only (non-managed)</span></span>

<span data-ttu-id="82498-115">Microsoft-fiók (MSA) vagy helyi fiók használata esetén nincs szükség további licencre ezekhez a fiókokhoz.</span><span class="sxs-lookup"><span data-stu-id="82498-115">When using either a Microsoft Account (MSA) or Local account no additional licenses are required for these accounts.</span></span>

[<span data-ttu-id="82498-116">Helyi fiók</span><span class="sxs-lookup"><span data-stu-id="82498-116">Local Account</span></span>](/windows/security/identity-protection/access-control/local-accounts)

- <span data-ttu-id="82498-117">Ezt a fiókot [előre](hololens-provisioning.md#provisioning-package-hololens-wizard) ki kellépítenünk a Windows Configuration Designer (WCD) használatával.</span><span class="sxs-lookup"><span data-stu-id="82498-117">This account must be [provisioned](hololens-provisioning.md#provisioning-package-hololens-wizard) ahead of time with Windows Configuration Designer (WCD).</span></span>

[<span data-ttu-id="82498-118">Microsoft-fiók (MSA)</span><span class="sxs-lookup"><span data-stu-id="82498-118">Microsoft Account (MSA)</span></span>](/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> <span data-ttu-id="82498-119">Az ilyen fiókokat használó eszközök esetében nem támogatott több felhasználó használata.</span><span class="sxs-lookup"><span data-stu-id="82498-119">Multiple users are not supported for a device using either of these accounts.</span></span>

### <a name="business-use-case"></a><span data-ttu-id="82498-120">Üzleti felhasználás esete:</span><span class="sxs-lookup"><span data-stu-id="82498-120">Business Use Case:</span></span> 

- <span data-ttu-id="82498-121">[C telepítési forgatókönyv](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) – offline vagy biztonságos üzembe helyezés.</span><span class="sxs-lookup"><span data-stu-id="82498-121">[Deployment Scenario C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) - offline or secure deployment.</span></span>
 
## <a name="dynamics-365-licensing-and-requirements"></a><span data-ttu-id="82498-122">Dynamics 365 – Licencelés és követelmények</span><span class="sxs-lookup"><span data-stu-id="82498-122">Dynamics 365 Licensing and Requirements</span></span>

### <a name="dynamics-365-remote-assist"></a><span data-ttu-id="82498-123">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="82498-123">Dynamics 365 Remote Assist</span></span> 

#### <a name="admin"></a><span data-ttu-id="82498-124">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="82498-124">Admin</span></span>

- <span data-ttu-id="82498-125">Azure AD-fiók (az előfizetés megvásárlásához és a licencek hozzárendeléséhez szükséges)</span><span class="sxs-lookup"><span data-stu-id="82498-125">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="82498-126">[Remote Assist-előfizetés](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (vagy [Remote Assist próbaverzió)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="82498-126">[Remote Assist subscription](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="82498-127">Dynamics 365 Remote Assist-felhasználó</span><span class="sxs-lookup"><span data-stu-id="82498-127">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="82498-128">Azure AD-fiók</span><span class="sxs-lookup"><span data-stu-id="82498-128">Azure AD account</span></span>

- <span data-ttu-id="82498-129">Remote Assist-licenc</span><span class="sxs-lookup"><span data-stu-id="82498-129">Remote Assist license</span></span> 

  > [!NOTE]
  > <span data-ttu-id="82498-130">Microsoft Teams Remote Assist csomaggal van csomagolva</span><span class="sxs-lookup"><span data-stu-id="82498-130">Microsoft Teams is bundled with Remote Assist</span></span>

- <span data-ttu-id="82498-131">Hálózati kapcsolat</span><span class="sxs-lookup"><span data-stu-id="82498-131">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="82498-132">Microsoft Teams felhasználó</span><span class="sxs-lookup"><span data-stu-id="82498-132">Microsoft Teams user</span></span>

- <span data-ttu-id="82498-133">Azure AD-fiók</span><span class="sxs-lookup"><span data-stu-id="82498-133">Azure AD account</span></span>

- <span data-ttu-id="82498-134">Microsoft Teams vagy [Teams Freemium .](https://products.office.com/microsoft-teams/free)</span><span class="sxs-lookup"><span data-stu-id="82498-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>

- <span data-ttu-id="82498-135">Hálózati kapcsolat</span><span class="sxs-lookup"><span data-stu-id="82498-135">Network connectivity</span></span>

<span data-ttu-id="82498-136">Ha ezt a [több-bérlős](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)forgatókönyvet tervezi, előfordulhat, hogy információs korlátok licencre van szüksége.</span><span class="sxs-lookup"><span data-stu-id="82498-136">If you plan on implementing this [cross-tenant scenario](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="82498-137">Ebből [a cikkből megállapíthatja,](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) hogy szükség van-e information barrier licencre.</span><span class="sxs-lookup"><span data-stu-id="82498-137">See [this article](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="dynamics-365-guides"></a><span data-ttu-id="82498-138">Dynamics 365-útmutatók</span><span class="sxs-lookup"><span data-stu-id="82498-138">Dynamics 365 Guides</span></span> 

#### <a name="admin"></a><span data-ttu-id="82498-139">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="82498-139">Admin</span></span>

- <span data-ttu-id="82498-140">Azure AD-fiók (az előfizetés megvásárlásához és a licencek hozzárendeléséhez szükséges)</span><span class="sxs-lookup"><span data-stu-id="82498-140">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="82498-141">Dynamics 365 [Guides-előfizetés vagy ingyenes próbaverzió](/dynamics365/mixed-reality/guides/setup-step-one)</span><span class="sxs-lookup"><span data-stu-id="82498-141">Dynamics 365 [Guides subscription or free trial](/dynamics365/mixed-reality/guides/setup-step-one)</span></span>

#### <a name="guides-author"></a><span data-ttu-id="82498-142">Útmutatók szerzője</span><span class="sxs-lookup"><span data-stu-id="82498-142">Guides Author</span></span>

1. <span data-ttu-id="82498-143">Azure AD-fiók</span><span class="sxs-lookup"><span data-stu-id="82498-143">Azure AD account</span></span>
1. [<span data-ttu-id="82498-144">Dynamics 365 Guides-licenc</span><span class="sxs-lookup"><span data-stu-id="82498-144">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="82498-145">Számítógépekre vagy számítógépekre telepített Dynamics 365-útmutatók HoloLens</span><span class="sxs-lookup"><span data-stu-id="82498-145">Dynamics 365 Guides application installed on a PC or HoloLens</span></span>
1. <span data-ttu-id="82498-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (az Analytics-irányítópult megtekintésére használatos)</span><span class="sxs-lookup"><span data-stu-id="82498-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (used to view the Analytics dashboard)</span></span>
1. <span data-ttu-id="82498-147">Szerzői szerepkör (útmutatók létrehozásához)</span><span class="sxs-lookup"><span data-stu-id="82498-147">Author role (for creating guides)</span></span>
1. <span data-ttu-id="82498-148">Hálózati kapcsolat</span><span class="sxs-lookup"><span data-stu-id="82498-148">Network Connectivity</span></span>

#### <a name="guides-user"></a><span data-ttu-id="82498-149">Útmutatók felhasználója</span><span class="sxs-lookup"><span data-stu-id="82498-149">Guides User</span></span>

1. <span data-ttu-id="82498-150">Azure AD-fiók</span><span class="sxs-lookup"><span data-stu-id="82498-150">Azure AD account</span></span>
1. [<span data-ttu-id="82498-151">Dynamics 365 Guides-licenc</span><span class="sxs-lookup"><span data-stu-id="82498-151">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="82498-152">Telepített Dynamics 365-útmutatók HoloLens</span><span class="sxs-lookup"><span data-stu-id="82498-152">Dynamics 365 Guides app installed on a HoloLens</span></span>
1. <span data-ttu-id="82498-153">Operátori szerepkör (teszteléshez vagy útmutatókhoz)</span><span class="sxs-lookup"><span data-stu-id="82498-153">Operator role (for testing or using guides)</span></span>
1. <span data-ttu-id="82498-154">Hálózati kapcsolat</span><span class="sxs-lookup"><span data-stu-id="82498-154">Network Connectivity</span></span>
