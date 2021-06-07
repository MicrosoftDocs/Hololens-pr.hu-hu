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
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378157"
---
# <a name="intune--company-portal"></a><span data-ttu-id="f8192-104">Intune & Céges portál</span><span class="sxs-lookup"><span data-stu-id="f8192-104">Intune & Company Portal</span></span>

<span data-ttu-id="f8192-105">A Mobile Eszközkezelés (MDM) segítségével saját egyéni alkalmazásait használhatja a [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) szolgáltatáson keresztül, hogy közvetlenül a HoloLens-eszközökön telepítse őket.</span><span class="sxs-lookup"><span data-stu-id="f8192-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="f8192-106">Microsoft Intune egy felhőalapú szolgáltatás, amely a mobileszköz-felügyeletre (MDM) és mobilalkalmazás-felügyeletre (MAM) összpontosít.</span><span class="sxs-lookup"><span data-stu-id="f8192-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="f8192-107">Az Intune része a Microsoft Enterprise Mobility + Security [(EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)csomagnak, és lehetővé teszi, hogy a felhasználók hatékonyan és a szervezeti adatok védelmével is hatékonyan védve legyenek.</span><span class="sxs-lookup"><span data-stu-id="f8192-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="f8192-108">Az Intune-nal kapcsolatos további információkért olvassa el [a Mi az Az Intune?](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="f8192-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="f8192-109">Telepítés</span><span class="sxs-lookup"><span data-stu-id="f8192-109">Setup</span></span>

1. <span data-ttu-id="f8192-110">Töltsön fel egy alkalmazást egy üzletági alkalmazásba, vagy töltsön fel egy egyéni alkalmazást az Intune-bérlőjébe.</span><span class="sxs-lookup"><span data-stu-id="f8192-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="f8192-111">Lásd még: [Vállalati alkalmazáskezelés.](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)</span><span class="sxs-lookup"><span data-stu-id="f8192-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="f8192-112">[Rendelje hozzá az alkalmazást egy csoporthoz.](https://docs.microsoft.com/mem/intune/apps/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="f8192-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="f8192-113">A kiválasztott hozzárendelési típustól függően az alkalmazás automatikusan kézbesíthető vagy azonnal lekérhetők, ha van néhány alkalmazása.</span><span class="sxs-lookup"><span data-stu-id="f8192-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="f8192-114">Az appx csomag létrehozásakor ügyeljen arra, hogy figyelembe veszi az üzembe helyező eszköz(ék) architektúráját.</span><span class="sxs-lookup"><span data-stu-id="f8192-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="f8192-115">A HoloLens 2 az ARM64, a HoloLens (1. generációs) pedig x86.</span><span class="sxs-lookup"><span data-stu-id="f8192-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="f8192-116">Ha vegyes eszközkörnyezetet tervez, mindkettőt egyetlen appx-csomagba foglalhatja.</span><span class="sxs-lookup"><span data-stu-id="f8192-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="f8192-117">Hozzárendelés-típusok</span><span class="sxs-lookup"><span data-stu-id="f8192-117">Assignment types</span></span>

<span data-ttu-id="f8192-118">Ahhoz, hogy az alkalmazás a regisztrációt követően automatikusan telepítve legyen az eszközön, válassza a **Kötelező** lehetőséget az egyes csoportokhoz.</span><span class="sxs-lookup"><span data-stu-id="f8192-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="f8192-119">Ahhoz, hogy az alkalmazás letölthető legyen a vállalati portálon keresztül regisztrált eszközökre, válassza a Regisztrált eszközökhöz **elérhető lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="f8192-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="f8192-120">End-User felhasználói élmény</span><span class="sxs-lookup"><span data-stu-id="f8192-120">End-User Experience</span></span>

<span data-ttu-id="f8192-121">Miután beállította a konfigurációt az Intune-ban, készen áll arra, hogy a végfelhasználók megkapják a kiválasztott alkalmazásokat.</span><span class="sxs-lookup"><span data-stu-id="f8192-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="f8192-122">Az alábbi lépéseket követve automatikusan lekért alkalmazás(ak)t:</span><span class="sxs-lookup"><span data-stu-id="f8192-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="f8192-123">Regisztrálja az eszközt a bérlővel.</span><span class="sxs-lookup"><span data-stu-id="f8192-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="f8192-124">Miután az eszköz regisztrációja befejeződött, meg kell kapnia az alkalmazást az eszközön.</span><span class="sxs-lookup"><span data-stu-id="f8192-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="f8192-125">Ha nem látja azonnal az alkalmazást, a Beállítások fiókok munkahelyi vagy iskolai fiókjának adatai között görgessen le a telepített alkalmazás   >    >    >   állapotával kapcsolatos információkért.</span><span class="sxs-lookup"><span data-stu-id="f8192-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="f8192-126">Alkalmazások letöltése a Céges portál:</span><span class="sxs-lookup"><span data-stu-id="f8192-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="f8192-127">Nyissa meg **a Start menüt,** és válassza a **Microsoft Store.**</span><span class="sxs-lookup"><span data-stu-id="f8192-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="f8192-128">Keressen rá **a Céges portál,** és töltse le az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="f8192-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="f8192-129">Jelentkezzen be a fiókjába.</span><span class="sxs-lookup"><span data-stu-id="f8192-129">Sign into your account.</span></span>
4. <span data-ttu-id="f8192-130">Válassza ki és töltse le a megkapni kívánt alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="f8192-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="f8192-131">További információ az [alkalmazások automatikus telepítéséről és Céges portál](https://docs.microsoft.com/mem/intune/apps/company-portal-app) és felügyeletéről az [Intune-ban.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="f8192-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
