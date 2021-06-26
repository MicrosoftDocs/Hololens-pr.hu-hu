---
title: A HoloLens 2 üzembe helyezésének megtervezése kereskedelmi környezetben
description: Megismerheti a HoloLens vállalati környezetekben való üzembe helyezésének és kezelésének alapvető igényeit, beleértve az infrastruktúrát, az Azure Active Directoryt és a mobileszköz-felügyeletet.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961429"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="b024d-103">A HoloLens 2 üzembe helyezésének megtervezése kereskedelmi környezetben</span><span class="sxs-lookup"><span data-stu-id="b024d-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="b024d-104">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="b024d-104">Overview</span></span>
> [!NOTE]
> <span data-ttu-id="b024d-105">Az áttekintés célja, hogy segítse az informatikai szakembereket abban, hogy megértsék, milyen szempontokat kell figyelembe venni a Microsoft HoloLens 2 eszköz telepítésével és kezelésével kapcsolatban a szervezeten belül.</span><span class="sxs-lookup"><span data-stu-id="b024d-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="b024d-106">Az eszköz végfelhasználói számára lásd: [Az első lépések](hololens2-setup.md) alapjai.</span><span class="sxs-lookup"><span data-stu-id="b024d-106">For device end users, see [The Basics](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="b024d-107">A HoloLens 2 Windows 10 Holographic, amely robusztus, rugalmas, beépített mobileszköz- és alkalmazáskezelési technológiákat biztosít a szervezeteknek.</span><span class="sxs-lookup"><span data-stu-id="b024d-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="b024d-108">Windows 10 Holographic támogatja a teljes eszköz-életciklus kezelését, így a vállalatok szabályozni lehet eszközeik, adataik és alkalmazásaik kezelését.</span><span class="sxs-lookup"><span data-stu-id="b024d-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="b024d-109">A HoloLens 2 könnyen beépíthető a szabványos életciklus-eljárásokba, az eszközök regisztrálásán, konfigurálásán és alkalmazáskezelésén át a karbantartásig és kivezetésig egy átfogó mobileszköz-kezelési megoldás használatával.</span><span class="sxs-lookup"><span data-stu-id="b024d-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="b024d-110">Az alábbi lépések végigvezetik a HoloLens 2 szervezeten belüli bevezetésének folyamatán.</span><span class="sxs-lookup"><span data-stu-id="b024d-110">The following steps can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| | |
|--|--|
| ![1. lépés](images/1green.png)| <br/> <span data-ttu-id="b024d-112">**[Gyakori üzembe helyezési forgatókönyvek:](hololens-requirements.md)** Megismerheti az üzembe helyezési forgatókönyveket, és megismerheti a HoloLens 2-eszközök üzembe helyezéséhez szükséges alapvető összetevőket.</span><span class="sxs-lookup"><span data-stu-id="b024d-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![2. lépés](images/2green.png)| <br/> <span data-ttu-id="b024d-114">**[Előkészítés:](#prepare)** Ismerkedjen meg a HoloLens 2-hez szükséges infrastruktúra-nélkülözhetetlenekkel.</span><span class="sxs-lookup"><span data-stu-id="b024d-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![3. lépés](images/3green.png) | <br/> <span data-ttu-id="b024d-116">**[Konfigurálás:](#configure)** Megtudhatja, hogyan konfigurálhatja a felhőalapú üzembe helyezés alapvető összetevőit.</span><span class="sxs-lookup"><span data-stu-id="b024d-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![4. lépés](images/4green.png) | <br/> <span data-ttu-id="b024d-118">**[Üzembe](#deploy)** helyezés: Megismerheti az eszközök üzembe helyezésének és az alkalmazások biztonságos és hatékony terjesztésének mikéntját.</span><span class="sxs-lookup"><span data-stu-id="b024d-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![5. lépés](images/5green.png) | <br/> <span data-ttu-id="b024d-120">**[Karbantartás:](#maintain)** Derítse ki, mire van szükség a HoloLens 2-eszközök állapotának megfelelő fenntartásához és a vállalati szabályzatnak való megfelelőség biztosításához.</span><span class="sxs-lookup"><span data-stu-id="b024d-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

## <a name="prepare"></a><span data-ttu-id="b024d-121">Előkészítés</span><span class="sxs-lookup"><span data-stu-id="b024d-121">Prepare</span></span>

<span data-ttu-id="b024d-122">Ismerje meg a HoloLens 2 funkcióinak teljes készletéhez szükséges alapvető infrastruktúra-szolgáltatásokat.</span><span class="sxs-lookup"><span data-stu-id="b024d-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span> 

| <span data-ttu-id="b024d-123">Összetevő</span><span class="sxs-lookup"><span data-stu-id="b024d-123">Component</span></span> | <span data-ttu-id="b024d-124">Leírás</span><span class="sxs-lookup"><span data-stu-id="b024d-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="b024d-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="b024d-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="b024d-126">Identitás- és hozzáférés-kezelés a HoloLens 2 számára</span><span class="sxs-lookup"><span data-stu-id="b024d-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="b024d-127">Mobileszköz-kezelés</span><span class="sxs-lookup"><span data-stu-id="b024d-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="b024d-128">Felügyeli a bérlőhöz csatlakoztatott HoloLens 2-eszközöket</span><span class="sxs-lookup"><span data-stu-id="b024d-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="b024d-129">Wi-Fi-hálózat</span><span class="sxs-lookup"><span data-stu-id="b024d-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="b024d-130">Wi-Fi elérhető, és az eszközök csatlakoztatva vannak az internethez</span><span class="sxs-lookup"><span data-stu-id="b024d-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="b024d-131">Konfigurálás</span><span class="sxs-lookup"><span data-stu-id="b024d-131">Configure</span></span>

<span data-ttu-id="b024d-132">Az Intune-t és az Autopilotot kevés érintéssel használható megoldásként használhatja a HoloLens 2 a szervezet Azure AD-bérlőjéhez és MDM-éhez való regisztrálására és konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="b024d-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="b024d-133">Összetevő</span><span class="sxs-lookup"><span data-stu-id="b024d-133">Component</span></span> | <span data-ttu-id="b024d-134">Leírás</span><span class="sxs-lookup"><span data-stu-id="b024d-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="b024d-135">Automatikus regisztráció</span><span class="sxs-lookup"><span data-stu-id="b024d-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="b024d-136">A kezdeti bejelentkezést követően az eszközök automatikusan regisztrálnak az Azure AD-ban, és regisztrálnak az MDM-be</span><span class="sxs-lookup"><span data-stu-id="b024d-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="b024d-137">Alkalmazáslicencek</span><span class="sxs-lookup"><span data-stu-id="b024d-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="b024d-138">Felhasználókra, felhasználói csoportokra vagy eszközcsoportokra is alkalmazható</span><span class="sxs-lookup"><span data-stu-id="b024d-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="b024d-139">Azure-felhasználók és -csoportok</span><span class="sxs-lookup"><span data-stu-id="b024d-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="b024d-140">Segít a Konfigurációk és licencek hozzárendelésében a HoloLens 2-hez</span><span class="sxs-lookup"><span data-stu-id="b024d-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="b024d-141">Üzembe helyezés</span><span class="sxs-lookup"><span data-stu-id="b024d-141">Deploy</span></span>

<span data-ttu-id="b024d-142">HoloLens 2-eszközök terjesztése és konfigurációjuk ellenőrzése.</span><span class="sxs-lookup"><span data-stu-id="b024d-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="b024d-143">Összetevő</span><span class="sxs-lookup"><span data-stu-id="b024d-143">Component</span></span> | <span data-ttu-id="b024d-144">Leírás</span><span class="sxs-lookup"><span data-stu-id="b024d-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="b024d-145">Regisztráció ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="b024d-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="b024d-146">Ellenőrizze, hogy az eszközhöz csatlakozott-e az Azure AD a beállításokból vagy az Azure Portalról</span><span class="sxs-lookup"><span data-stu-id="b024d-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="b024d-147">Tanúsítvány érvényesítése</span><span class="sxs-lookup"><span data-stu-id="b024d-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="b024d-148">Ellenőrizze a beállításokat, és ellenőrizze, hogy megfelelően történt-e az elosztásuk</span><span class="sxs-lookup"><span data-stu-id="b024d-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="b024d-149">Alkalmazástelepítések ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="b024d-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="b024d-150">Ellenőrizze, hogy az alkalmazás jelen van-e, és működik-e a HoloLens 2-ben</span><span class="sxs-lookup"><span data-stu-id="b024d-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="b024d-151">Karbantartás</span><span class="sxs-lookup"><span data-stu-id="b024d-151">Maintain</span></span>

<span data-ttu-id="b024d-152">A Windows Update Vállalatoknak MDM-rendszerrel vagy az alkalmazásokkal együtt Microsoft Store a HoloLens 2-flotta és az alkalmazások frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="b024d-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="b024d-153">Összetevő</span><span class="sxs-lookup"><span data-stu-id="b024d-153">Component</span></span> | <span data-ttu-id="b024d-154">Leírás</span><span class="sxs-lookup"><span data-stu-id="b024d-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="b024d-155">A HoloLens 2 frissítése</span><span class="sxs-lookup"><span data-stu-id="b024d-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="b024d-156">Szükség szerint konfigurálja a frissítéseket a Vállalati Windows-frissítések szolgáltatáson keresztül</span><span class="sxs-lookup"><span data-stu-id="b024d-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="b024d-157">Alkalmazások frissítése</span><span class="sxs-lookup"><span data-stu-id="b024d-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="b024d-158">Konfigurálás az MDM-rendszeren vagy a Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="b024d-158">Configure through your MDM system or the Microsoft Store</span></span>
