---
title: CsP-k és Eszközkezelés konfigurálása – áttekintés
description: Megtudhatja, hogyan konfigurálhatja a CSP-eket, a szabályzatokat és az eszközkezelést Eszközkezelés és kiépítési csomagokkal.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640457"
---
# <a name="configure-csps-and-device-management-overview"></a><span data-ttu-id="439e1-103">CsP-k és Eszközkezelés konfigurálása – áttekintés</span><span class="sxs-lookup"><span data-stu-id="439e1-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="439e1-104">A rendszergazdák a 2. HoloLens házirend-beállításokat határozhatják meg és valósíthatják meg.</span><span class="sxs-lookup"><span data-stu-id="439e1-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="439e1-105">A használt konfigurációs beállítások a telepítési forgatókönyvtől függően különböznek, és a vállalati eszközök a legszélesebb körű vezérlést kínálják az it-itának.</span><span class="sxs-lookup"><span data-stu-id="439e1-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="439e1-106">A Windows 10 konfigurációszolgáltatók (CSP-k) az eszköz konfigurációs beállításainak olvasására, beállítására, módosítására vagy törlésére való felületek.</span><span class="sxs-lookup"><span data-stu-id="439e1-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="439e1-107">Ezek a beállítások beállításkulcsra vagy fájlokra vannak leképezve.</span><span class="sxs-lookup"><span data-stu-id="439e1-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="439e1-108">Egyes konfigurációs szolgáltatók támogatják a WAP formátumot, némelyik támogatja a SyncML-t, néhány pedig mindkettőt.</span><span class="sxs-lookup"><span data-stu-id="439e1-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="439e1-109">Az eszközkezelési CSP-Windows 10 Holographic kapcsolatos további információkért tekintse meg az eszközök által támogatott [CSP-k HoloLens listáját.](/windows/client-management/mdm/configuration-service-provider-reference#hololens)</span><span class="sxs-lookup"><span data-stu-id="439e1-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="439e1-110">A rendszergazdák az eszközökön is kezelhetik a házirendek CSP-ját. Lásd a 2. HoloLens által támogatott [házirend-CSP-k teljes listáját.](/windows/client-management/mdm/policy-csps-supported-by-hololens2)</span><span class="sxs-lookup"><span data-stu-id="439e1-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <a name="configuration-methods"></a><span data-ttu-id="439e1-111">Konfigurációs módszerek</span><span class="sxs-lookup"><span data-stu-id="439e1-111">Configuration methods</span></span>

### <a name="configure-with-mdm"></a><span data-ttu-id="439e1-112">Konfigurálás MDM-sel</span><span class="sxs-lookup"><span data-stu-id="439e1-112">Configure with MDM</span></span>

<span data-ttu-id="439e1-113">A CSP-k és szabályzatok egyszerűen kezelhetők az MDM-rendszerekben regisztrált személyes vagy vállalati eszközök bármelyikén.</span><span class="sxs-lookup"><span data-stu-id="439e1-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="439e1-114">Miután regisztrált egy eszközt az MDM-megoldásban, kezelheti az eszközt vagy eszközkonfigurációkat használó eszközöket.</span><span class="sxs-lookup"><span data-stu-id="439e1-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="439e1-115">További információ a [mobileszközök MDM HoloLens keresztüli kezelésről.](hololens-mdm-configure.md)</span><span class="sxs-lookup"><span data-stu-id="439e1-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <a name="configure-with-provisioning-packages"></a><span data-ttu-id="439e1-116">Konfigurálás kiépítési csomagokkal</span><span class="sxs-lookup"><span data-stu-id="439e1-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="439e1-117">HoloLens 2., támogatja a CSP-konfigurációk korlátozott készletének beállítását HoloLens 2 eszköz számára egyéni kiépítési csomagokon keresztül.</span><span class="sxs-lookup"><span data-stu-id="439e1-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="439e1-118">A kiépítési csomagokat általában nem MDM által felügyelt eszközökhöz használják, és manuálisan kell alkalmazni őket az egyes eszközökre.</span><span class="sxs-lookup"><span data-stu-id="439e1-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="439e1-119">Olvassa el az egyéni [kiépítési csomagok létrehozásáról HoloLens.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="439e1-119">Read information on building custom [Provisioning Packages for HoloLens](hololens-provisioning.md).</span></span>

## <a name="configurations"></a><span data-ttu-id="439e1-120">Konfigurációk</span><span class="sxs-lookup"><span data-stu-id="439e1-120">Configurations</span></span>

### <a name="common-device-restrictions"></a><span data-ttu-id="439e1-121">Gyakori eszközkorlátozások</span><span class="sxs-lookup"><span data-stu-id="439e1-121">Common device restrictions</span></span>

<span data-ttu-id="439e1-122">Bizonyos eszközkorlátozások egyszerűek, és letiltják a funkciókat vagy az eszközhöz való kapcsolódást.</span><span class="sxs-lookup"><span data-stu-id="439e1-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="439e1-123">További információért olvassa el a gyakori [eszközkorlátozásokkal kapcsolatos további tudnivalókat.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="439e1-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <a name="kiosk-modes"></a><span data-ttu-id="439e1-124">Kioszkmódok</span><span class="sxs-lookup"><span data-stu-id="439e1-124">Kiosk modes</span></span>

<span data-ttu-id="439e1-125">A Kioszkmód használatával szabályozhatja, hogy mely identitások férhetnek hozzá alapértelmezés szerint az alkalmazásokhoz.</span><span class="sxs-lookup"><span data-stu-id="439e1-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="439e1-126">A kioszkok egyetlen alkalmazáshoz vagy több alkalmazás felhasználói felületéhez is használhatók.</span><span class="sxs-lookup"><span data-stu-id="439e1-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="439e1-127">A kioszkkonfigurációk az eszköz minden használója számára egyetlen alkalmazástól a különböző csoportok alkalmazásválasztásaitól is függnek.</span><span class="sxs-lookup"><span data-stu-id="439e1-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="439e1-128">A kioszkmód nem teszi lehetővé, hogy az "engedélyezett alkalmazások" más alkalmazásokat indítsanak el, és soha nem volt rendeltetése.</span><span class="sxs-lookup"><span data-stu-id="439e1-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="439e1-129">További információ: [Kioszkmódok és azok használata.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="439e1-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <a name="settings-page-visibility"></a><span data-ttu-id="439e1-130">Gépház Oldal láthatósága</span><span class="sxs-lookup"><span data-stu-id="439e1-130">Settings Page Visibility</span></span>

<span data-ttu-id="439e1-131">Az Gépház szabályzat használatával szabályozhatja, hogy mely identitások férhetnek hozzá alapértelmezés szerint a beállításokhoz.</span><span class="sxs-lookup"><span data-stu-id="439e1-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="439e1-132">Ezzel a szabályzatkal Gépház alkalmazás konfigurálható úgy, hogy csak a kijelölt oldalakat mutassa, vagy elrejtse az összes kijelölt oldalt.</span><span class="sxs-lookup"><span data-stu-id="439e1-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="439e1-133">[Olvassa el, hogyan konfigurálhatja az elérhető oldalakat.](settings-uri-list.md)</span><span class="sxs-lookup"><span data-stu-id="439e1-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="439e1-134">Ez a funkció jelenleg csak az [Insider Windows buildek esetén érhető el.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="439e1-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="439e1-135">Győződjön meg arról, hogy a szolgáltatáshoz használni kívánt eszközök az 19041.1349-es vagy további buildben vannak.</span><span class="sxs-lookup"><span data-stu-id="439e1-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <a name="wdac"></a><span data-ttu-id="439e1-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="439e1-136">WDAC</span></span>

<span data-ttu-id="439e1-137">A WDAC-konfigurációval szabályozhatja, hogy mely alkalmazások/folyamatok indíthatóak el/nem engedélyezettek attól függetlenül, hogy a rendszer kioszkmódban van-e vagy sem.</span><span class="sxs-lookup"><span data-stu-id="439e1-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="439e1-138">Tekintse meg a WDAC áttekintését.</span><span class="sxs-lookup"><span data-stu-id="439e1-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
