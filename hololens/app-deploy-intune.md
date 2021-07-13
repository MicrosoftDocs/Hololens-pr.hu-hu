---
title: Intune és Céges portál
description: Megtudhatja, hogyan hozhat létre, rendelhet hozzá és hozhat létre kényelmes felhasználói élményt az Intune, a mobileszköz-kezelés és a vállalati portál használatával.
keywords: intune, alkalmazáskezelés, alkalmazás, vállalati portál, portál, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635500"
---
# <a name="intune--company-portal"></a><span data-ttu-id="2a4a4-104">Intune & Céges portál</span><span class="sxs-lookup"><span data-stu-id="2a4a4-104">Intune & Company Portal</span></span>

<span data-ttu-id="2a4a4-105">A Mobile Eszközkezelés (MDM) segítségével a saját egyéni alkalmazásait az [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) használatával telepítheti közvetlenül a saját HoloLens eszközeire.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="2a4a4-106">Microsoft Intune egy felhőalapú szolgáltatás, amely a mobileszköz-felügyeletre (MDM) és mobilalkalmazás-felügyeletre (MAM) összpontosít.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="2a4a4-107">Az Intune része a Microsoft Enterprise Mobility + Security [(EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)csomagnak, és lehetővé teszi, hogy a felhasználók hatékonyan dolgozhatnak, miközben a szervezet adatai is biztonságban maradnak.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="2a4a4-108">További információ az Intune-nal kapcsolatban: [Mi az Intune?](/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="2a4a4-108">To learn more about Intune, read [What is Intune](/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="2a4a4-109">Telepítés</span><span class="sxs-lookup"><span data-stu-id="2a4a4-109">Setup</span></span>

1. <span data-ttu-id="2a4a4-110">Töltsön fel egy alkalmazást egy üzletági alkalmazásba, vagy töltsön fel egy egyéni alkalmazást az Intune-bérlőjébe.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="2a4a4-111">Lásd még: [Vállalati alkalmazáskezelés.](/windows/client-management/mdm/enterprise-app-management)</span><span class="sxs-lookup"><span data-stu-id="2a4a4-111">See also: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="2a4a4-112">[Rendelje hozzá az alkalmazást egy csoporthoz.](/mem/intune/apps/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="2a4a4-112">[Assign your app to a group](/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="2a4a4-113">A kiválasztott hozzárendelési típustól függően az alkalmazás automatikusan kézbesíthető vagy azonnal lekérhetők, ha van néhány alkalmazás.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="2a4a4-114">Az appx csomag létrehozásakor ügyeljen arra, hogy figyelembe veszi az üzembe helyező eszköz(nek) architektúráját.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="2a4a4-115">HoloLens 2. az ARM64, HoloLens (1. generációs) pedig x86.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="2a4a4-116">Ha vegyes eszközkörnyezetet tervez, mindkettőt egyetlen appx csomagba foglalhatja.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="2a4a4-117">Hozzárendelés-típusok</span><span class="sxs-lookup"><span data-stu-id="2a4a4-117">Assignment types</span></span>

<span data-ttu-id="2a4a4-118">Ahhoz, hogy az alkalmazás a regisztrációt követően automatikusan telepítve legyen az eszközön, válassza a **Kötelező** lehetőséget az egyes csoportokhoz.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="2a4a4-119">Ahhoz, hogy az alkalmazás letölthető legyen a vállalati portálon regisztrált eszközökre, válassza az **Elérhető a regisztrált eszközökhöz lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="2a4a4-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="2a4a4-120">End-User felhasználói élmény</span><span class="sxs-lookup"><span data-stu-id="2a4a4-120">End-User Experience</span></span>

<span data-ttu-id="2a4a4-121">Miután beállította a konfigurációt az Intune-ban, készen áll arra, hogy a végfelhasználók megkapják a kiválasztott alkalmazásokat.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="2a4a4-122">Az alábbi lépéseket követve automatikusan lekért alkalmazás(ak)t:</span><span class="sxs-lookup"><span data-stu-id="2a4a4-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="2a4a4-123">Regisztrálja eszközét a bérlővel.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="2a4a4-124">Miután az eszköz regisztrációja befejeződött, meg kell kapnia az alkalmazást az eszközön.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="2a4a4-125">Ha nem látja azonnal az alkalmazást, a Gépház munkahelyi vagy iskolai fiókjának adatai lapon görgessen le a telepített alkalmazás  >    >    >  állapotával kapcsolatos információkért.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="2a4a4-126">Alkalmazások a következő Céges portál:</span><span class="sxs-lookup"><span data-stu-id="2a4a4-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="2a4a4-127">Nyissa meg **a Start menüt,** és válassza a **Microsoft Store.**</span><span class="sxs-lookup"><span data-stu-id="2a4a4-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="2a4a4-128">Keressen rá **a Céges portál,** és töltse le az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="2a4a4-129">Jelentkezzen be a fiókjába.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-129">Sign into your account.</span></span>
4. <span data-ttu-id="2a4a4-130">Válassza ki a megkapni kívánt alkalmazást, és töltse le.</span><span class="sxs-lookup"><span data-stu-id="2a4a4-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="2a4a4-131">További információ az [alkalmazások automatikus telepítéséről és Céges portál](/mem/intune/apps/company-portal-app) telepítéséről és felügyeletéről az [Intune-ban.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="2a4a4-131">Learn more about [auto-installing the Company Portal](/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
