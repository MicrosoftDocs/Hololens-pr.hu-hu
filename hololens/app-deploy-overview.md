---
title: Áttekintés – Alkalmazáskezelés
description: 'Első lépések: a vegyes valóságú alkalmazáskezelés áttekintése mobileszköz-felügyelet, Vállalati Microsoft Áruház és kiépítési csomagok használatával.'
keywords: HoloLens, felhasználó, fiók, alkalmazás, alkalmazáskezelés,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635551"
---
# <a name="app-management-overview"></a><span data-ttu-id="32b52-104">Alkalmazáskezelés: Áttekintés</span><span class="sxs-lookup"><span data-stu-id="32b52-104">App Management: Overview</span></span>

<span data-ttu-id="32b52-105">Az alkalmazásokat négy különböző útvonalon telepítheti: **Mobile Eszközkezelés (MDM),** **Microsoft Store Vállalatoknak**, **Microsoft Store**, vagy telepítésükön **keresztül.**</span><span class="sxs-lookup"><span data-stu-id="32b52-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="32b52-106">Mobileszköz-felügyelet (MDM)</span><span class="sxs-lookup"><span data-stu-id="32b52-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="32b52-107">Az MDM-megoldások lehetővé teszik az informatikai döntéshozók és a rendszergazdák számára, hogy privát módon automatikusan telepítik (leküldik) a házon belüli, üzletági alkalmazásokat, vagy alkalmazásokat vásárolnak az áruházon keresztül a felhasználók egy csoportja számára.</span><span class="sxs-lookup"><span data-stu-id="32b52-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="32b52-108">HoloLens eszközök az alkalmazáskezeléshez Microsoft Endpoint Manager (Intune) [működnek a legjobban.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="32b52-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="32b52-109">Az Intune emellett lehetővé teszi a felhasználók számára az IT által felügyelt alkalmazások finomhangolt vezérlését a Céges portál használatával.</span><span class="sxs-lookup"><span data-stu-id="32b52-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="32b52-110">Az alábbi utasításokat azok a felhasználók számára ismertetjük, akik az Intune-nal szeretnék kezelni az alkalmazásokat.</span><span class="sxs-lookup"><span data-stu-id="32b52-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="32b52-111">A Microsoft az Intune használatát javasolja az alkalmazás- és eszközkezeléshez.</span><span class="sxs-lookup"><span data-stu-id="32b52-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="32b52-112">A Eszközkezelés (MDM) a következőre vonatkozik:</span><span class="sxs-lookup"><span data-stu-id="32b52-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="32b52-113">Telepített MDM + Céges portál</span><span class="sxs-lookup"><span data-stu-id="32b52-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="32b52-114">Üzletági (nem nyilvános) alkalmazások</span><span class="sxs-lookup"><span data-stu-id="32b52-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="32b52-115">Az elérhető alkalmazások manuális telepítése a Céges portál</span><span class="sxs-lookup"><span data-stu-id="32b52-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="32b52-116">Rendszergazdai leküldés MDM-szabályzaton keresztül</span><span class="sxs-lookup"><span data-stu-id="32b52-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="32b52-117">Automatikus frissítés MDM-en keresztül</span><span class="sxs-lookup"><span data-stu-id="32b52-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="32b52-118">Vállalati Microsoft Áruház</span><span class="sxs-lookup"><span data-stu-id="32b52-118">Microsoft Store for Business</span></span>

<span data-ttu-id="32b52-119">A [Microsoft Store Vállalatoknak](app-deploy-store-business.md) az informatikai döntéshozók és a vállalatok rendszergazdái számára ingyenes és fizetős alkalmazások keresését, megszerzését, kezelését és terjesztését teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="32b52-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="32b52-120">A rendszergazdák egyetlen Microsoft Store kezelhetik az alkalmazásokat és a privát üzletági alkalmazásokat, valamint szükség szerint rendelhetnek hozzá és újra felhasználhatnak licenceket.</span><span class="sxs-lookup"><span data-stu-id="32b52-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="32b52-121">További információ: [Prerequisites for using the Microsoft Store Vállalatoknak.](/microsoft-store/prerequisites-microsoft-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="32b52-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="32b52-122">A Microsoft Store Vállalatoknak a következőre vonatkozik:</span><span class="sxs-lookup"><span data-stu-id="32b52-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="32b52-123">Nyilvános vagy üzletági alkalmazások</span><span class="sxs-lookup"><span data-stu-id="32b52-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="32b52-124">A szükséges alkalmazások automatikus telepítése MDM-társításon keresztül</span><span class="sxs-lookup"><span data-stu-id="32b52-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="32b52-125">A felhasználó manuálisan tölt le alkalmazásokat</span><span class="sxs-lookup"><span data-stu-id="32b52-125">User manually downloads apps</span></span>
* <span data-ttu-id="32b52-126">Automatikus frissítés</span><span class="sxs-lookup"><span data-stu-id="32b52-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="32b52-127">Microsoft Áruházbeli alkalmazások</span><span class="sxs-lookup"><span data-stu-id="32b52-127">Microsoft Store apps</span></span>

<span data-ttu-id="32b52-128">A Microsoft Store a vállalatok informatikai döntéshozói és rendszergazdái számára nyilvános alkalmazások keresését, megszerzését, kezelését és terjesztését teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="32b52-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="32b52-129">Ez Microsoft Store a következőre vonatkozik:</span><span class="sxs-lookup"><span data-stu-id="32b52-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="32b52-130">Csak nyilvános alkalmazások</span><span class="sxs-lookup"><span data-stu-id="32b52-130">Public apps only</span></span>
* <span data-ttu-id="32b52-131">A felhasználó manuálisan tölt le alkalmazásokat</span><span class="sxs-lookup"><span data-stu-id="32b52-131">User manually downloads apps</span></span>
* <span data-ttu-id="32b52-132">Automatikus frissítés, ha csatlakozik az internethez</span><span class="sxs-lookup"><span data-stu-id="32b52-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="32b52-133">További információkért látogasson el a [Holographic Store Apps webhelyre.](/hololens/holographic-store-apps)</span><span class="sxs-lookup"><span data-stu-id="32b52-133">For more information, visit [Holographic Store Apps](/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="32b52-134">Telepítés kiépítési csomagokkal</span><span class="sxs-lookup"><span data-stu-id="32b52-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="32b52-135">[A kiépítési](app-deploy-provisioning-package.md) csomagok segítségével egyéni vagy üzletági alkalmazásokat telepíthet, így az informatikai szakemberek és a rendszergazdák gyorsan telepíthet alkalmazásokat egy helyi eszköz(ére) USB-kapcsolaton keresztül.</span><span class="sxs-lookup"><span data-stu-id="32b52-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="32b52-136">Ez a telepítés internetkapcsolat nélkül és bármilyen identitástípus esetén használhatja.</span><span class="sxs-lookup"><span data-stu-id="32b52-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="32b52-137">A kiépítési csomagokkal történő telepítés a következőre vonatkozik:</span><span class="sxs-lookup"><span data-stu-id="32b52-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="32b52-138">Üzletági / saját fejlesztésű (nem nyilvános) alkalmazások</span><span class="sxs-lookup"><span data-stu-id="32b52-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="32b52-139">Nyilvános alkalmazások (ha elérhető offline telepítő)</span><span class="sxs-lookup"><span data-stu-id="32b52-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="32b52-140">Csak USB-meghajtóról történő oldalbetöltés</span><span class="sxs-lookup"><span data-stu-id="32b52-140">USB side-loading only</span></span>
* <span data-ttu-id="32b52-141">Nincs automatikus frissítés (manuális frissítéseket igényel a kiépítési csomagon keresztül)</span><span class="sxs-lookup"><span data-stu-id="32b52-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="32b52-142">Alkalmazások telepítése a 2. HoloLens a Alkalmazástelepítő</span><span class="sxs-lookup"><span data-stu-id="32b52-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="32b52-143">A [Alkalmazástelepítő](app-deploy-app-installer.md) a felhasználók egyszerűen telepíthet alkalmazásokat helyi eszközökre, vagy megoszthatnak egy alkalmazást egy olyan felhasználóval, aki nem ismeri a többi alkalmazástelepítési módszert a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="32b52-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="32b52-144">Ez a Fejlesztői mód engedélyezése vagy az alkalmazás használata nélkül Eszközportál.</span><span class="sxs-lookup"><span data-stu-id="32b52-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="32b52-145">Ez egy egyszerű módszer egy teljesen felépített alkalmazás terjesztésére.</span><span class="sxs-lookup"><span data-stu-id="32b52-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="32b52-146">Függetlenül attól, hogy az alkalmazást egyszerűen egy másik felhasználónak szeretné HoloLens, vagy egyszerűen üzembe szeretné helyezni az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="32b52-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="32b52-147">A telepítés Alkalmazástelepítő a következőre vonatkozik:</span><span class="sxs-lookup"><span data-stu-id="32b52-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="32b52-148">Üzletági / saját fejlesztésű (nem nyilvános) alkalmazások</span><span class="sxs-lookup"><span data-stu-id="32b52-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="32b52-149">Csak oldalbetöltés</span><span class="sxs-lookup"><span data-stu-id="32b52-149">Side-load only</span></span>
* <span data-ttu-id="32b52-150">Nincs szükség fejlesztői módra vagy eszközportálra</span><span class="sxs-lookup"><span data-stu-id="32b52-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="32b52-151">A végfelhasználók könnyen telepíthetők</span><span class="sxs-lookup"><span data-stu-id="32b52-151">Easy for end user to install</span></span>
