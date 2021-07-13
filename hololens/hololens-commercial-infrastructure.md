---
title: Infrastruktúra-irányelvek HoloLens
description: Ismerje meg a hálózati eszközök infrastruktúrával kapcsolatos irányelveit HoloLens beleértve a vezeték nélküli hálózat támogatását, a távsegítség és a mobileszköz-kezelés kezelését.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3f87c524ce0f8af05ec8c92877d46facd962fb4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639284"
---
# <a name="configure-your-network-for-hololens"></a><span data-ttu-id="e42f7-103">A hálózat konfigurálása HoloLens</span><span class="sxs-lookup"><span data-stu-id="e42f7-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="e42f7-104">A dokumentum ezen részében a következő személyekre lesz szükség:</span><span class="sxs-lookup"><span data-stu-id="e42f7-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="e42f7-105">Hálózati rendszergazda, aki rendelkezik a proxy/tűzfal módosításaihoz szükséges engedélyekkel</span><span class="sxs-lookup"><span data-stu-id="e42f7-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="e42f7-106">Azure Active Directory Admin</span><span class="sxs-lookup"><span data-stu-id="e42f7-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="e42f7-107">Mobileszközök Eszközkezelő rendszergazdája</span><span class="sxs-lookup"><span data-stu-id="e42f7-107">Mobile Device Manager Admin</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="e42f7-108">Infrastruktúrakövetelmények</span><span class="sxs-lookup"><span data-stu-id="e42f7-108">Infrastructure Requirements</span></span>

<span data-ttu-id="e42f7-109">HoloLens lényegében egy azure Windows integrált mobileszköz.</span><span class="sxs-lookup"><span data-stu-id="e42f7-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="e42f7-110">Kereskedelmi környezetekben működik a vezeték nélküli hálózattal (Wi-Fi) és hozzáféréssel a Microsoft-szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="e42f7-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="e42f7-111">A kritikus fontosságú felhőszolgáltatások közé tartoznak a következők:</span><span class="sxs-lookup"><span data-stu-id="e42f7-111">Critical cloud services include:</span></span>

- <span data-ttu-id="e42f7-112">Azure active directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="e42f7-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="e42f7-113">Windows Frissítés (WU)</span><span class="sxs-lookup"><span data-stu-id="e42f7-113">Windows Update (WU)</span></span>

<span data-ttu-id="e42f7-114">A kereskedelmi ügyfeleknek nagyvállalati mobilitási felügyeleti (EMM) vagy mobileszköz-kezelési (MDM) infrastruktúrára van szükségük a nagy HoloLens kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="e42f7-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="e42f7-115">Ez az útmutató [Microsoft Intune,](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) bár a Microsoft Policy teljes körű támogatásával minden szolgáltató támogathatja a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e42f7-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="e42f7-116">Kérdezze meg a mobileszköz-kezelő szolgáltatót, hogy támogatja-e HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e42f7-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="e42f7-117">HoloLens nem támogatja a felhővel nem leválasztott élmények egy korlátozott készletét.</span><span class="sxs-lookup"><span data-stu-id="e42f7-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <a name="wireless-network-eap-support"></a><span data-ttu-id="e42f7-118">Vezeték nélküli hálózat EAP-támogatása</span><span class="sxs-lookup"><span data-stu-id="e42f7-118">Wireless network EAP support</span></span>

- <span data-ttu-id="e42f7-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="e42f7-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="e42f7-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="e42f7-120">PEAP-TLS</span></span>
- <span data-ttu-id="e42f7-121">TLS</span><span class="sxs-lookup"><span data-stu-id="e42f7-121">TLS</span></span>
- <span data-ttu-id="e42f7-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="e42f7-122">TTLS-CHAP</span></span>
- <span data-ttu-id="e42f7-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="e42f7-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="e42f7-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="e42f7-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="e42f7-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="e42f7-125">TTLS-PAP</span></span>
- <span data-ttu-id="e42f7-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="e42f7-126">TTLS-TLS</span></span>

### <a name="hololens-specific-network-requirements"></a><span data-ttu-id="e42f7-127">HoloLens Konkrét hálózati követelmények</span><span class="sxs-lookup"><span data-stu-id="e42f7-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="e42f7-128">Győződjön meg arról, [hogy a végpontok](hololens-offline.md) listája engedélyezve van a hálózati tűzfalon.</span><span class="sxs-lookup"><span data-stu-id="e42f7-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="e42f7-129">Ez lehetővé teszi a HoloLens megfelelő működését.</span><span class="sxs-lookup"><span data-stu-id="e42f7-129">This will enable HoloLens to function properly.</span></span>

### <a name="remote-assist-specific-network-requirements"></a><span data-ttu-id="e42f7-130">A Remote Assist konkrét hálózati követelményei</span><span class="sxs-lookup"><span data-stu-id="e42f7-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="e42f7-131">A Remote Assist optimális teljesítményéhez ajánlott sávszélesség 1,5 Mb/s.</span><span class="sxs-lookup"><span data-stu-id="e42f7-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="e42f7-132">További [információkért tekintse meg a részletes hálózati](/MicrosoftTeams/prepare-network) követelményeket.</span><span class="sxs-lookup"><span data-stu-id="e42f7-132">See the [detailed network requirements](/MicrosoftTeams/prepare-network) for additional information.</span></span>
<span data-ttu-id="e42f7-133">**(Vegye figyelembe, hogy ha a hálózaton nincs legalább 1,5 MB/s sebességű hálózati sebesség, a Remote Assist továbbra is működni fog. A minőség azonban rossz lehet).**</span><span class="sxs-lookup"><span data-stu-id="e42f7-133">**(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work. However, quality may suffer).**</span></span>
1. <span data-ttu-id="e42f7-134">Győződjön meg arról, hogy ezek a portok és URL-címek engedélyezve vannak a hálózati tűzfalon a Microsoft Teams működéséhez.</span><span class="sxs-lookup"><span data-stu-id="e42f7-134">Make sure that these ports and URLs are allowed on your network firewall to enable Microsoft Teams to function.</span></span> <span data-ttu-id="e42f7-135">Maradjon naprakész a legújabb [portlistával.](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="e42f7-135">Stay up to date with the [latest list of ports](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="e42f7-136">További információ a Remote Assist konkrét [hálózati követelményeiről.](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)</span><span class="sxs-lookup"><span data-stu-id="e42f7-136">Learn more about the specific [Network Requirements for Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="e42f7-137">További információ arról, hogyan [készítheti elő a](/MicrosoftTeams/prepare-network) szervezet hálózatát a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e42f7-137">Learn more about how to [prepare your organization's network for Microsoft Teams](/MicrosoftTeams/prepare-network)</span></span>

### <a name="guides-specific-network-requirements"></a><span data-ttu-id="e42f7-138">Útmutatók konkrét hálózati követelményekhez</span><span class="sxs-lookup"><span data-stu-id="e42f7-138">Guides Specific Network Requirements</span></span>

<span data-ttu-id="e42f7-139">Az útmutatók csak az alkalmazás letöltéséhez és használatához igényelnek hálózati hozzáférést.</span><span class="sxs-lookup"><span data-stu-id="e42f7-139">Guides only require network access to download and use the app.</span></span>

## <a name="azure-active-directory-guidance"></a><span data-ttu-id="e42f7-140">Azure Active Directory Útmutatást</span><span class="sxs-lookup"><span data-stu-id="e42f7-140">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="e42f7-141">Erre a lépésre csak akkor van szükség, ha a vállalata az adatok HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e42f7-141">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="e42f7-142">Győződjön meg arról, hogy rendelkezik Azure AD-licenccel.</span><span class="sxs-lookup"><span data-stu-id="e42f7-142">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="e42f7-143">További [HoloLens tekintse meg a licenckövetelményeket.](hololens-licenses-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="e42f7-143">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="e42f7-144">Ha automatikus regisztrációt tervez használni, konfigurálnia kell az [Azure AD-regisztrációt.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span><span class="sxs-lookup"><span data-stu-id="e42f7-144">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="e42f7-145">Győződjön meg arról, hogy a vállalat felhasználói a Azure Active Directory (Azure AD) vannak.</span><span class="sxs-lookup"><span data-stu-id="e42f7-145">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="e42f7-146">A felhasználók [hozzáadásához kövesse](/azure/active-directory/fundamentals/add-users-azure-active-directory) az alábbi utasításokat.</span><span class="sxs-lookup"><span data-stu-id="e42f7-146">See the following [instructions](/azure/active-directory/fundamentals/add-users-azure-active-directory) for adding users.</span></span>

1. <span data-ttu-id="e42f7-147">Javasoljuk, hogy azok a felhasználók, akiknek hasonló licencre van szükségük, ugyanoda a csoportba kerülnek.</span><span class="sxs-lookup"><span data-stu-id="e42f7-147">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="e42f7-148">Csoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="e42f7-148">Create a Group</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="e42f7-149">Felhasználók hozzáadása csoportokhoz</span><span class="sxs-lookup"><span data-stu-id="e42f7-149">Add users to groups</span></span>](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="e42f7-150">Győződjön meg arról, hogy a vállalat felhasználóihoz (vagy felhasználói csoportjához) hozzá van rendelve a szükséges licencek.</span><span class="sxs-lookup"><span data-stu-id="e42f7-150">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="e42f7-151">Ha licenceket kell hozzárendelni, kövesse az [alábbi utasításokat.](/azure/active-directory/fundamentals/license-users-groups)</span><span class="sxs-lookup"><span data-stu-id="e42f7-151">If you need to assign licenses, follow these [directions](/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="e42f7-152">Ezt a lépést csak akkor tegye meg, ha a felhasználóknak regisztrálniuk kell HoloLens/Mobile-eszközüket az Ön számára (három lehetőség van). Ezek a lépések biztosítják, hogy a vállalat felhasználói (vagy felhasználói csoportok) eszközöket adhatnak hozzá.</span><span class="sxs-lookup"><span data-stu-id="e42f7-152">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="e42f7-153">**1. lehetőség:** Adjon engedélyt minden felhasználónak az eszközök Azure AD-hez való csatlakozásához.</span><span class="sxs-lookup"><span data-stu-id="e42f7-153">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="e42f7-154">**Jelentkezzen be a Azure Portal rendszergazdaként**  >  **Azure Active Directory**  >  **Eszközök**  >  **Eszköz Gépház**  >
 **Állítsa a Users may join devices to Azure AD (Felhasználók csatlakozhatnak az eszközökhöz az Azure AD-be) *beállítását All (Mind)***</span><span class="sxs-lookup"><span data-stu-id="e42f7-154">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="e42f7-155">**2. lehetőség:** Adjon engedélyt a kiválasztott felhasználóknak/csoportoknak az eszközök Azure AD-be való beléptetését az **Azure Portal-ba**  >  **rendszergazdaként Azure Active Directory**  >  **Gépház-eszközök** eszközkészlete Felhasználók csatlakozhatnak az Azure  >    >
 **AD-hez** a Kiválasztott rendszerképhez, amely az Azure 
 ![ AD-hez csatlakozott eszközök konfigurációját mutatja](images/azure-ad-image.png)</span><span class="sxs-lookup"><span data-stu-id="e42f7-155">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices](images/azure-ad-image.png)</span></span>

    1. <span data-ttu-id="e42f7-156">**3. lehetőség:** Letilthatja, hogy az összes felhasználó az eszközeit a tartományhoz csatlakozzon.</span><span class="sxs-lookup"><span data-stu-id="e42f7-156">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="e42f7-157">Ez azt jelenti, hogy minden eszközt manuálisan kell regisztrálni.</span><span class="sxs-lookup"><span data-stu-id="e42f7-157">This means that all devices will need to be manually enrolled.</span></span>

## <a name="mobile-device-manager-guidance"></a><span data-ttu-id="e42f7-158">Mobileszközök Eszközkezelő útmutató</span><span class="sxs-lookup"><span data-stu-id="e42f7-158">Mobile Device Manager Guidance</span></span>

### <a name="ongoing-device-management"></a><span data-ttu-id="e42f7-159">Folyamatban lévő eszközkezelés</span><span class="sxs-lookup"><span data-stu-id="e42f7-159">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="e42f7-160">Erre a lépésre csak akkor van szükség, ha a vállalata az alkalmazás HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e42f7-160">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="e42f7-161">A folyamatos eszközkezelés a mobileszköz-kezelési infrastruktúrától függ.</span><span class="sxs-lookup"><span data-stu-id="e42f7-161">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="e42f7-162">A legtöbb esetben ugyanaz az általános funkció, de a felhasználói felület széles körben változhat.</span><span class="sxs-lookup"><span data-stu-id="e42f7-162">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="e42f7-163">[A CSP-k (konfigurációs szolgáltatók)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lehetővé teszi felügyeleti beállítások létrehozására és központi telepítésére a hálózaton elérhető eszközök számára.</span><span class="sxs-lookup"><span data-stu-id="e42f7-163">[CSPs (Configuration Service Providers)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lets you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="e42f7-164">Referenciaként [tekintse meg a HoloLens CSP-k](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) listáját.</span><span class="sxs-lookup"><span data-stu-id="e42f7-164">See the [list of HoloLens CSPs](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) for reference.</span></span>

1. <span data-ttu-id="e42f7-165">[A megfelelőségi szabályzatok](/intune/device-compliance-get-started) olyan szabályok és beállítások, amelyeknek az eszközöknek meg kell felelnie, hogy megfeleljenek a vállalati infrastruktúrának.</span><span class="sxs-lookup"><span data-stu-id="e42f7-165">[Compliance policies](/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="e42f7-166">Ezeket a szabályzatokat feltételes hozzáféréssel használva letilthatja a nem megfelelő eszközök vállalati erőforrásaihoz való hozzáférést.</span><span class="sxs-lookup"><span data-stu-id="e42f7-166">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="e42f7-167">Létrehozhat például olyan szabályzatot, amely megköveteli a Bitlocker engedélyezését.</span><span class="sxs-lookup"><span data-stu-id="e42f7-167">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="e42f7-168">[Megfelelőségi szabályzat létrehozása.](/intune/protect/compliance-policy-create-windows)</span><span class="sxs-lookup"><span data-stu-id="e42f7-168">[Create Compliance Policy](/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="e42f7-169">A feltételes hozzáférés engedélyezi/letiltja a mobileszközök és mobilalkalmazások hozzáférését a vállalati erőforrásokhoz.</span><span class="sxs-lookup"><span data-stu-id="e42f7-169">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="e42f7-170">Két dokumentum, amelyek hasznosak lehetnek, a [CA üzembe helyezésének megterve és](/azure/active-directory/conditional-access/plan-conditional-access) az ajánlott [eljárások.](/azure/active-directory/conditional-access/best-practices)</span><span class="sxs-lookup"><span data-stu-id="e42f7-170">Two documents you may find helpful are [Plan your CA Deployment](/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="e42f7-171">[Ez a cikk](/intune/fundamentals/windows-holographic-for-business) az Intune felügyeleti eszközeit tárgyalja HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e42f7-171">[This article](/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="e42f7-172">Eszközprofil létrehozása</span><span class="sxs-lookup"><span data-stu-id="e42f7-172">Create a device profile</span></span>](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a><span data-ttu-id="e42f7-173">Frissítések kezelése</span><span class="sxs-lookup"><span data-stu-id="e42f7-173">Manage updates</span></span>

<span data-ttu-id="e42f7-174">Az Intune frissítési körök nevű funkciót tartalmaz a Windows 10-eszközökhöz, beleértve a HoloLens 2-es és HoloLens 1-es (Holographic for Business verzióval) funkciókat.</span><span class="sxs-lookup"><span data-stu-id="e42f7-174">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="e42f7-175">A frissítési körök olyan beállításokat tartalmaznak, amelyek meghatározzák a frissítések telepítésének mikéntját és mikorját.</span><span class="sxs-lookup"><span data-stu-id="e42f7-175">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="e42f7-176">Létrehozhat például egy karbantartási időszakot a frissítések telepítésére vagy eldöntheti, hogy kíván-e újraindítást a frissítések telepítése után.</span><span class="sxs-lookup"><span data-stu-id="e42f7-176">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="e42f7-177">Dönthet úgy is, hogy határozatlan időre felfüggeszti a frissítéseket, amíg készen nem áll a frissítésre.</span><span class="sxs-lookup"><span data-stu-id="e42f7-177">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="e42f7-178">További információ a [frissítési körök Intune-nal való konfigurálásával kapcsolatban.](/intune/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="e42f7-178">Read more about [configuring update rings with Intune](/intune/windows-update-for-business-configure).</span></span>

### <a name="application-management"></a><span data-ttu-id="e42f7-179">Alkalmazáskezelés</span><span class="sxs-lookup"><span data-stu-id="e42f7-179">Application management</span></span>

<span data-ttu-id="e42f7-180">A HoloLens kezelése a következőn keresztül:</span><span class="sxs-lookup"><span data-stu-id="e42f7-180">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="e42f7-181">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="e42f7-181">Microsoft Store</span></span>  
  <span data-ttu-id="e42f7-182">A Microsoft Store a legjobb módszer az alkalmazások terjesztésére és HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e42f7-182">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="e42f7-183">Az áruházban már elérhető alapalkalmazások HoloLens, de saját alkalmazásokat is [közzétehet.](/windows/uwp/publish/)</span><span class="sxs-lookup"><span data-stu-id="e42f7-183">There is a great set of core HoloLens applications already available in the store or you can [publish your own](/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="e42f7-184">Az áruházban található összes alkalmazás nyilvánosan elérhető mindenki számára, de ha nem elfogadható, tekintse meg a Microsoft Store Vállalatoknak.</span><span class="sxs-lookup"><span data-stu-id="e42f7-184">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="e42f7-185">Vállalati Microsoft Áruház</span><span class="sxs-lookup"><span data-stu-id="e42f7-185">Microsoft Store for Business</span></span>](/microsoft-store/)  
  <span data-ttu-id="e42f7-186">Microsoft Store Vállalatoknak és Az Education egy egyéni áruház a vállalati környezethez.</span><span class="sxs-lookup"><span data-stu-id="e42f7-186">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="e42f7-187">Lehetővé teszi, hogy a Microsoft Store beépített Windows 10 és HoloLens megkeresheti, beszerezheti, terjesztheti és kezelheti a szervezet alkalmazásait.</span><span class="sxs-lookup"><span data-stu-id="e42f7-187">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="e42f7-188">Emellett lehetővé teszi olyan alkalmazások üzembe helyezését is, amelyek csak a kereskedelmi környezetére vonatkoznak, a világra nem.</span><span class="sxs-lookup"><span data-stu-id="e42f7-188">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="e42f7-189">Alkalmazások központi telepítése és kezelése az Intune-nal vagy más mobileszköz-kezelési megoldással</span><span class="sxs-lookup"><span data-stu-id="e42f7-189">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="e42f7-190">A legtöbb mobileszköz-kezelési megoldás, beleértve az Intune-t is, lehetővé teszi üzletági alkalmazások közvetlen üzembe helyezését regisztrált eszközökre.</span><span class="sxs-lookup"><span data-stu-id="e42f7-190">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="e42f7-191">Az Intune [alkalmazástelepítésről ebben a cikkben talál további részleteket.](/intune/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="e42f7-191">See this article for [Intune app install](/intune/apps-deploy).</span></span>

1. <span data-ttu-id="e42f7-192">_nem ajánlott_ Eszközportál</span><span class="sxs-lookup"><span data-stu-id="e42f7-192">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="e42f7-193">Az alkalmazások közvetlenül a HoloLens is telepíthetők Windows Eszközportál.</span><span class="sxs-lookup"><span data-stu-id="e42f7-193">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="e42f7-194">Ez nem ajánlott, mivel a fejlesztői módot engedélyezni kell az eszközportál használatára.</span><span class="sxs-lookup"><span data-stu-id="e42f7-194">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="e42f7-195">További információ az [alkalmazások telepítéséről a HoloLens.](hololens-install-apps.md)</span><span class="sxs-lookup"><span data-stu-id="e42f7-195">Read more about [installing apps on HoloLens](hololens-install-apps.md).</span></span>

### <a name="certificates"></a><span data-ttu-id="e42f7-196">Tanúsítványok</span><span class="sxs-lookup"><span data-stu-id="e42f7-196">Certificates</span></span>

<span data-ttu-id="e42f7-197">A tanúsítványokat az MDM-szolgáltatón keresztül terjesztheti.</span><span class="sxs-lookup"><span data-stu-id="e42f7-197">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="e42f7-198">Ha a vállalata tanúsítványokat igényel, az Intune támogatja a PKCS, a PFX és az SCEP-tanúsítványokat.</span><span class="sxs-lookup"><span data-stu-id="e42f7-198">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="e42f7-199">Fontos tisztában lennie a vállalat számára megfelelő tanúsítvánnyal.</span><span class="sxs-lookup"><span data-stu-id="e42f7-199">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="e42f7-200">Tekintse meg [a tanúsítványkonfigurációk dokumentációját](/intune/protect/certificates-configure) annak meghatározásához, hogy melyik tanúsítvány a legmegfelelőbb az Ön számára.</span><span class="sxs-lookup"><span data-stu-id="e42f7-200">Please visit the [certificate configurations](/intune/protect/certificates-configure) documentation to determine which cert is best for you.</span></span> <span data-ttu-id="e42f7-201">Ha tanúsítványokat tervez használni HoloLens hitelesítéshez, a PFX vagy az SCEP megfelelő lehet az Ön számára.</span><span class="sxs-lookup"><span data-stu-id="e42f7-201">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="e42f7-202">Az SCEP használatának lépései a [következők.](/intune/protect/certificates-profile-scep)</span><span class="sxs-lookup"><span data-stu-id="e42f7-202">See the following steps for using [SCEP](/intune/protect/certificates-profile-scep).</span></span>

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a><span data-ttu-id="e42f7-203">Frissítés a Holographics for Business Commercial Suite-hoz</span><span class="sxs-lookup"><span data-stu-id="e42f7-203">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="e42f7-204">Windows A Holographics for Business (kereskedelmi csomag) csak HoloLens 1. generációs eszközökhöz használható.</span><span class="sxs-lookup"><span data-stu-id="e42f7-204">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="e42f7-205">A profil nem lesz alkalmazva 2 HoloLens eszközre.</span><span class="sxs-lookup"><span data-stu-id="e42f7-205">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="e42f7-206">A kereskedelmi csomagra való frissítésre vonatkozó utasításokat a [holografikus](/intune/configuration/holographic-upgrade) frissítési dokumentációban találja.</span><span class="sxs-lookup"><span data-stu-id="e42f7-206">You can find directions for upgrading to the commercial suite in the [holographic upgrade](/intune/configuration/holographic-upgrade) documentation.</span></span>

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a><span data-ttu-id="e42f7-207">Kioszkmód konfigurálása a Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e42f7-207">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="e42f7-208">Szinkronizálja Microsoft Store Intune-nal (lásd az alábbi [utasításokat).](/intune/apps/windows-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="e42f7-208">Sync Microsoft Store to Intune (See the following [instructions](/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="e42f7-209">Az alkalmazásbeállítások ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="e42f7-209">Check your app settings</span></span>
    1. <span data-ttu-id="e42f7-210">Jelentkezzen be Microsoft Store üzleti fiókjába</span><span class="sxs-lookup"><span data-stu-id="e42f7-210">Log into your Microsoft Store Business account</span></span>
    1. <span data-ttu-id="e42f7-211">**Az > termékek és szolgáltatások kezelése > Alkalmazások és szoftverszolgáltatások > Válassza ki > Privát áruház rendelkezésre állása lehetőséget, majd > válassza > "Mindenki" vagy "Adott csoportok" lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="e42f7-211">**Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**</span></span>
        >[!NOTE]
        ><span data-ttu-id="e42f7-212">Ha nem látja a kívánt alkalmazást, az áruházban való kereséssel "le kell szereznie" az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="e42f7-212">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="e42f7-213">Kattintson a jobb felső sarokban található "Keresés" > be az alkalmazás nevét, majd > kattintson az alkalmazásra, és **> a "Bekeresés" lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="e42f7-213">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="e42f7-214">Ha nem látja az **alkalmazásokat** az Intune-ban > Client Apps > Apps alkalmazásban, előfordulhat, hogy újra [szinkronizálni](/intune/apps/windows-store-for-business#synchronize-apps) kell az alkalmazásokat.</span><span class="sxs-lookup"><span data-stu-id="e42f7-214">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="e42f7-215">Eszközprofil létrehozása kioszkmódhoz</span><span class="sxs-lookup"><span data-stu-id="e42f7-215">Create a device profile for Kiosk mode</span></span>](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="e42f7-216">A különböző felhasználókat úgy konfigurálhatja, hogy különböző kioszkmódú felhasználói felületekkel használja az "Azure AD"-t a "Felhasználói bejelentkezés típusa" beállítással.</span><span class="sxs-lookup"><span data-stu-id="e42f7-216">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="e42f7-217">Ez a lehetőség azonban csak többalkalmazásos kioszkmódban érhető el.</span><span class="sxs-lookup"><span data-stu-id="e42f7-217">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="e42f7-218">A többalkalmazásos kioszkmód csak egy alkalmazással és több alkalmazással is működik.</span><span class="sxs-lookup"><span data-stu-id="e42f7-218">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![A kioszkmód Intune-nal való konfigurálást bemutató kép](images/aad-kioskmode.png)

<span data-ttu-id="e42f7-220">Más MDM-szolgáltatásokhoz a szolgáltató dokumentációjában talál útmutatást.</span><span class="sxs-lookup"><span data-stu-id="e42f7-220">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="e42f7-221">Ha egyéni beállítást és teljes XML-konfigurációt kell használnia egy [kioszk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) MDM-szolgáltatásban való beállítására, tekintse meg a teljes képernyős HoloLens utasításokat.</span><span class="sxs-lookup"><span data-stu-id="e42f7-221">Refer to the [HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) instructions if you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service.</span></span>

## <a name="certificates-and-authentication"></a><span data-ttu-id="e42f7-222">Tanúsítványok és hitelesítés</span><span class="sxs-lookup"><span data-stu-id="e42f7-222">Certificates and Authentication</span></span>

<span data-ttu-id="e42f7-223">A tanúsítványok MDM-en keresztül telepíthetők (lásd az [MDM szakasz "tanúsítványok" szakaszát).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)</span><span class="sxs-lookup"><span data-stu-id="e42f7-223">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="e42f7-224">A tanúsítványok a csomag kiépítése HoloLens is üzembe helyezhetők.</span><span class="sxs-lookup"><span data-stu-id="e42f7-224">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="e42f7-225">További [információkért HoloLens provisioning (Kiépítés)](hololens-provisioning.md) oldalon található.</span><span class="sxs-lookup"><span data-stu-id="e42f7-225">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <a name="additional-intune-quick-links"></a><span data-ttu-id="e42f7-226">Az Intune további gyorshivatkozásai</span><span class="sxs-lookup"><span data-stu-id="e42f7-226">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="e42f7-227">[Profilok létrehozása:](/intune/configuration/device-profile-create) A profilok lehetővé teszik a szervezet eszközeire lekért beállítások hozzáadását és konfigurálát.</span><span class="sxs-lookup"><span data-stu-id="e42f7-227">[Create Profiles:](/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

