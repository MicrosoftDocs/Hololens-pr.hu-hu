---
title: Licenckövetelmények
description: Tartsa naprakészen a mobileszköz-felügyelethez, a HoloLenshez és a Remote Assisthez szükséges licencelési követelményeket és irányelveket.
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379593"
---
# <a name="license-requirements"></a><span data-ttu-id="91937-103">Licenckövetelmények</span><span class="sxs-lookup"><span data-stu-id="91937-103">License requirements</span></span>

## <a name="mobile-device-management-mdm-licenses-guidance"></a><span data-ttu-id="91937-104">Útmutató a Eszközkezelés (MDM) licencekkel kapcsolatos útmutatóhoz</span><span class="sxs-lookup"><span data-stu-id="91937-104">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="91937-105">Ha HoloLens-eszközei felügyeletét tervezi, szüksége lesz az Azure AD-re és egy MDM-re.</span><span class="sxs-lookup"><span data-stu-id="91937-105">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="91937-106">Az Active Director (AD) nem használható HoloLens-eszközök kezelésére.</span><span class="sxs-lookup"><span data-stu-id="91937-106">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="91937-107">Ha az Intune-on kívül más MDM-et is használni Azure Active Directory [licenc](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) szükséges.</span><span class="sxs-lookup"><span data-stu-id="91937-107">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="91937-108">Ha az Intune-t tervezi MDM-ként [](https://docs.microsoft.com/intune/fundamentals/licenses) használni, olvassa el az Intune-licenceket is magában foglaló csomagok listáját.</span><span class="sxs-lookup"><span data-stu-id="91937-108">If you plan on using Intune as your MDM, read up on the [list of suites](https://docs.microsoft.com/intune/fundamentals/licenses) that include Intune licenses.</span></span> <span data-ttu-id="91937-109">**Vegye figyelembe, hogy a csomagok többsége tartalmazza az Azure AD-t.**</span><span class="sxs-lookup"><span data-stu-id="91937-109">**Please note that Azure AD is included in the majority of these suites.**</span></span>

## <a name="identify-the-licenses-needed-for-your-scenario-and-products"></a><span data-ttu-id="91937-110">A forgatókönyvhöz és a termékekhez szükséges licencek azonosítása</span><span class="sxs-lookup"><span data-stu-id="91937-110">Identify the licenses needed for your scenario and products</span></span>

### <a name="hololens-1st-gen-licenses-requirements"></a><span data-ttu-id="91937-111">HoloLens (1. generációs) licenckövetelmények</span><span class="sxs-lookup"><span data-stu-id="91937-111">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="91937-112">Előfordulhat, hogy frissítenie kell a HoloLens-eszközt (1. generációs) a Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="91937-112">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="91937-113">(Annak megállapításához, hogy szükség van-e a frissítésre, tekintse meg a [HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions) kereskedelmi funkcióit.</span><span class="sxs-lookup"><span data-stu-id="91937-113">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="91937-114">Ha igen, a következőket kell megtennie:</span><span class="sxs-lookup"><span data-stu-id="91937-114">If so, you will need to do the following:</span></span>

- <span data-ttu-id="91937-115">HoloLens Enterprise-licenc XML-fájl létrehozása</span><span class="sxs-lookup"><span data-stu-id="91937-115">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="91937-116">Alkalmazza az XML-fájlt a HoloLensre.</span><span class="sxs-lookup"><span data-stu-id="91937-116">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="91937-117">Ezt egy kiépítési csomaggal [vagy](hololens-provisioning.md) a [Mobile Eszközkezelő](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="91937-117">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <a name="remote-assist-license-requirements"></a><span data-ttu-id="91937-118">Remote Assist licenckövetelmények</span><span class="sxs-lookup"><span data-stu-id="91937-118">Remote Assist License Requirements</span></span>

<span data-ttu-id="91937-119">Győződjön meg arról, hogy a szükséges licencekkel és eszközzel van, amelyeket a követelmények dokumentációjában [talál.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)</span><span class="sxs-lookup"><span data-stu-id="91937-119">Make sure you have the required licensing and device, which you can check in the [requirements](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) documentation.</span></span>

1. [<span data-ttu-id="91937-120">Remote Assist-licenc</span><span class="sxs-lookup"><span data-stu-id="91937-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="91937-121">Vagy próbálkozzon a [Remote Assist próbaverzióval](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="91937-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="91937-122">Teams Freemium/Teams</span><span class="sxs-lookup"><span data-stu-id="91937-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="91937-123">Azure Active Directory (Azure AD) licenc</span><span class="sxs-lookup"><span data-stu-id="91937-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="91937-124">Ha ezt a **[több-bérlős](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** forgatókönyvet tervezi, előfordulhat, hogy információs korlátok licencre van szüksége.</span><span class="sxs-lookup"><span data-stu-id="91937-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="91937-125">Ebből a [cikkből megállapíthatja,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) hogy szükség van-e information barrier licencre.</span><span class="sxs-lookup"><span data-stu-id="91937-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="guides-license-requirements"></a><span data-ttu-id="91937-126">Útmutatók licenckövetelményei</span><span class="sxs-lookup"><span data-stu-id="91937-126">Guides License Requirements</span></span>

<span data-ttu-id="91937-127">Tekintse meg a [frissített licencelési és eszközkövetelményeket.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)</span><span class="sxs-lookup"><span data-stu-id="91937-127">Check out the [updated licensing and device requirements](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="91937-128">Azure Active Directory (Azure AD) licenc</span><span class="sxs-lookup"><span data-stu-id="91937-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="91937-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="91937-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="91937-130">Útmutatók</span><span class="sxs-lookup"><span data-stu-id="91937-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
