---
title: Tanúsítványkezelő
description: Megtudhatja, hogyan telepíthet, kezelhet és távolíthat el tanúsítványokat manuálisan a HoloLens 2 vegyes valóságú eszközökön.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378041"
---
# <a name="certificate-manager"></a><span data-ttu-id="58ab2-103">Tanúsítványkezelő</span><span class="sxs-lookup"><span data-stu-id="58ab2-103">Certificate Manager</span></span>

- <span data-ttu-id="58ab2-104">Továbbfejlesztett naplózási, diagnosztikai és érvényesítési eszközök az eszközbiztonság és -megfelelőség érdekében az új Tanúsítványkezelővel.</span><span class="sxs-lookup"><span data-stu-id="58ab2-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="58ab2-105">Ez a képesség lehetővé teszi a tanúsítványok kereskedelmi környezetekben való nagy léptékű üzembe helyezését, hibaelhárítását és érvényesítését.</span><span class="sxs-lookup"><span data-stu-id="58ab2-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="58ab2-106">A Windows Holographic 20H2-es verziójában tanúsítványkezelőt ad hozzá a HoloLens 2 Beállítások alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="58ab2-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="58ab2-107">A Biztonsági **tanúsítványok > frissítése & lapra > meg.**</span><span class="sxs-lookup"><span data-stu-id="58ab2-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="58ab2-108">Ez a funkció egyszerű és felhasználóbarát módja a tanúsítványok megtekintésének, telepítésének és eltávolításának az eszközön.</span><span class="sxs-lookup"><span data-stu-id="58ab2-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="58ab2-109">Az új Tanúsítványkezelővel a rendszergazdák és a felhasználók továbbfejlesztett naplózási, diagnosztikai és érvényesítési eszközökkel gondoskodnak az eszközök biztonságának és megfelelőségének biztosításáról.</span><span class="sxs-lookup"><span data-stu-id="58ab2-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="58ab2-110">**Naplózás:** A tanúsítvány megfelelő telepítésének ellenőrzése vagy annak ellenőrzése, hogy a tanúsítvány megfelelően lett-e eltávolítva.</span><span class="sxs-lookup"><span data-stu-id="58ab2-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="58ab2-111">**Diagnosztika:** Ha problémák merülnek fel, a megfelelő tanúsítványoknak az eszközön való létezik-e a hitelesítése időt takarít meg, és segít a hibaelhárításban.</span><span class="sxs-lookup"><span data-stu-id="58ab2-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="58ab2-112">**Érvényesítés:** Annak ellenőrzése, hogy a tanúsítvány a kívánt célt szolgálja-e és működik-e, jelentős időt takaríthat meg, különösen kereskedelmi környezetekben, mielőtt nagyobb léptékben helyez üzembe tanúsítványokat.</span><span class="sxs-lookup"><span data-stu-id="58ab2-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="58ab2-113">Ha gyorsan meg kell találnia egy adott tanúsítványt a listában, lehetőség van név, tároló vagy lejárati dátum szerint rendezni.</span><span class="sxs-lookup"><span data-stu-id="58ab2-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="58ab2-114">A felhasználók közvetlenül is kereshetnek tanúsítványt.</span><span class="sxs-lookup"><span data-stu-id="58ab2-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="58ab2-115">Az egyes tanúsítványtulajdonságok megtekintéséhez jelölje ki a tanúsítványt, majd kattintson az **Információ elemre.**</span><span class="sxs-lookup"><span data-stu-id="58ab2-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="58ab2-116">A tanúsítványtelepítés jelenleg a .cer és a .crt fájlokat támogatja.</span><span class="sxs-lookup"><span data-stu-id="58ab2-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="58ab2-117">Az eszköztulajdonosok a helyi gépen és az aktuális felhasználónál telepíthet tanúsítványokat;  minden más felhasználó csak az Aktuális felhasználóra telepíthető.</span><span class="sxs-lookup"><span data-stu-id="58ab2-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="58ab2-118">A felhasználók csak a beállítások felhasználói felületről távolítják el a közvetlenül telepített tanúsítványokat.</span><span class="sxs-lookup"><span data-stu-id="58ab2-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="58ab2-119">Ha egy tanúsítvány más módon lett telepítve, akkor ugyanezen mechanizmussal kell eltávolítani.</span><span class="sxs-lookup"><span data-stu-id="58ab2-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="58ab2-120">Tanúsítvány telepítése:</span><span class="sxs-lookup"><span data-stu-id="58ab2-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="58ab2-121">Csatlakoztassa a HoloLens 2-t egy számítógéphez.</span><span class="sxs-lookup"><span data-stu-id="58ab2-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="58ab2-122">Helyezze el a telepíteni kívánt tanúsítványfájlt a HoloLens 2-es helyén.</span><span class="sxs-lookup"><span data-stu-id="58ab2-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="58ab2-123">Lépjen a **Settings App > Update & Security > Certificates**(Tanúsítványok frissítése) lapra, és válassza a Tanúsítvány telepítése lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="58ab2-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="58ab2-124">Kattintson **a Fájl importálása** elemre, és keresse meg a helyet, ahol a tanúsítványt mentette.</span><span class="sxs-lookup"><span data-stu-id="58ab2-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="58ab2-125">Válassza **a Store Location (Áruház helye) lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="58ab2-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="58ab2-126">Válassza **a Tanúsítványtároló lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="58ab2-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="58ab2-127">Kattintson az **Install** (Telepítés) gombra.</span><span class="sxs-lookup"><span data-stu-id="58ab2-127">Click **Install**.</span></span>

<span data-ttu-id="58ab2-128">A tanúsítványnak most már telepítve kell lennie az eszközön.</span><span class="sxs-lookup"><span data-stu-id="58ab2-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="58ab2-129">Tanúsítvány eltávolítása:</span><span class="sxs-lookup"><span data-stu-id="58ab2-129">To remove a certificate:</span></span> 
>[!WARNING]
> <span data-ttu-id="58ab2-130">Bár az MDM által telepített tanúsítványokat megtekintheti a Tanúsítványkezelőben, a Tanúsítványkezelőben nem távolíthatja el őket.</span><span class="sxs-lookup"><span data-stu-id="58ab2-130">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="58ab2-131">Ezeket az MDM-ről kell eltávolítania.</span><span class="sxs-lookup"><span data-stu-id="58ab2-131">You must uninstall them through MDM.</span></span>
1. <span data-ttu-id="58ab2-132">Lépjen a Settings App > Update and Security > Certificates (Tanúsítványok **>) elemre.**</span><span class="sxs-lookup"><span data-stu-id="58ab2-132">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="58ab2-133">Keresse meg a tanúsítványt név alapján a keresőmezőben.</span><span class="sxs-lookup"><span data-stu-id="58ab2-133">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="58ab2-134">Válassza ki a tanúsítványt.</span><span class="sxs-lookup"><span data-stu-id="58ab2-134">Select the certificate.</span></span>
1. <span data-ttu-id="58ab2-135">Kattintson az **Eltávolítás gombra.**</span><span class="sxs-lookup"><span data-stu-id="58ab2-135">Click **Remove**</span></span>
1. <span data-ttu-id="58ab2-136">Ha  a rendszer megerősítést kér, válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="58ab2-136">Select **Yes** when prompted for confirmation.</span></span>



![Tanúsítványmegjelenítő a Beállítások alkalmazásban a Tanúsítványok alatt](images/certificate-viewer-device.jpg)

![Kép arról, hogyan telepíthet tanúsítványt a Tanúsítvány felhasználói felületén a Beállítások menüben.](images/certificate-device-install.jpg)
