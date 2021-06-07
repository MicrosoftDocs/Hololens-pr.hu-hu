---
title: Biztonsági tervezés
description: Biztonsági tervezés
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: biztonság, hololens, biztonság, mérnöki tevékenység
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: cecc556841033ee394f36915f4cae8839dad08df
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379556"
---
# <a name="security-engineering"></a><span data-ttu-id="ce2f3-104">Biztonsági tervezés</span><span class="sxs-lookup"><span data-stu-id="ce2f3-104">Security engineering</span></span>

<span data-ttu-id="ce2f3-105">A Microsoft számos erőforrással és csapattal rendelkezik, amelyek a vállalat mérnöki protokolljainak optimalizálására, a megfelelőség biztosítására és az ügyfelek bizalmának biztosítására vannak optimalizálva.</span><span class="sxs-lookup"><span data-stu-id="ce2f3-105">Microsoft has several resources and teams devoted to optimizing the company’s engineering protocols, addressing compliance, and ensuring customer trust.</span></span> 

  * <span data-ttu-id="ce2f3-106">A Microsoft biztonsági mérnöki fejlesztési gyakorlatával kapcsolatos további információkért lásd: [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl)( Biztonsági fejlesztési életciklus (SDL).</span><span class="sxs-lookup"><span data-stu-id="ce2f3-106">To learn more about Microsoft’s security engineering development practices, see the [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl).</span></span>
  * <span data-ttu-id="ce2f3-107">A Microsoft és így a HoloLens 2 lehetővé teszi az ügyfelek számára, hogy döntéseket hozzanak az adatgyűjtés és -gyűjtés mikéntjéhez és [miértjéhez,](https://privacy.microsoft.com/)amelyeket a Microsoft adatvédelmi szabályzata () tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="ce2f3-107">Microsoft, and therefore HoloLens 2, empowers customers to make choices about how and why data is collected and used, which can be further explored in [Microsoft’s Privacy policy](https://privacy.microsoft.com/).</span></span> 
  * <span data-ttu-id="ce2f3-108">[Microsoft Biztonsági reagálási központ (MSRC)](https://www.microsoft.com/msrc) a defender közösség része, így hatékony biztonsági rés-jelentéskészítési élményt, valamint hatékony kategorizálást és biztonsági hibákra adott választ biztosít.</span><span class="sxs-lookup"><span data-stu-id="ce2f3-108">[Microsoft Security Response Center (MSRC)](https://www.microsoft.com/msrc) is part of the defender community, providing an efficient vulnerability reporting experience and an effective categorization and response to security bugs.</span></span> 

## <a name="updates-and-patches"></a><span data-ttu-id="ce2f3-109">Frissítések és javítások</span><span class="sxs-lookup"><span data-stu-id="ce2f3-109">Updates and patches</span></span>

<span data-ttu-id="ce2f3-110">A biztonsági frissítéseket és a javításokat minden hónap második keddén adták ki.</span><span class="sxs-lookup"><span data-stu-id="ce2f3-110">Security updates and patches are released on the second Tuesday of each month.</span></span> <span data-ttu-id="ce2f3-111">A Microsoft által a jelentett biztonsági rések következő lépéseit kiértékelő feltételekért tekintse meg a Microsoft Biztonsági reagálási központ biztonsági karbantartási feltételek [oldalát.](https://www.microsoft.com/msrc/windows-security-servicing-criteria)</span><span class="sxs-lookup"><span data-stu-id="ce2f3-111">In order to understand the criteria used by Microsoft to evaluate next steps for a reported vulnerability, see the Microsoft Security Response Center’s [Security Servicing Criteria page](https://www.microsoft.com/msrc/windows-security-servicing-criteria).</span></span> 

<span data-ttu-id="ce2f3-112">A HoloLens 2-frissítések MDM-en keresztüli kezelésével kapcsolatos útmutatásért lásd: [HoloLens-frissítések kezelése.](https://docs.microsoft.com/hololens/hololens-updates)</span><span class="sxs-lookup"><span data-stu-id="ce2f3-112">For guidance on managing HoloLens 2 updates via MDM, see [Manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates).</span></span> <span data-ttu-id="ce2f3-113">A HoloLens 2 operációs rendszerének frissítési üteme megegyezik a Windows 10; évente két frissítés van, az egyik springben, a másik pedig ősszel történik.</span><span class="sxs-lookup"><span data-stu-id="ce2f3-113">The operating system update cadence for HoloLens 2 matches that of Windows 10; there are two updates per year, one taking place in Spring and the other in Fall.</span></span> <span data-ttu-id="ce2f3-114">Az eszközök az operációs rendszer frissítései során való biztonságának további tudnivalókért lásd: [Állapotelválasztás és elkülönítés.](security-state-separation-isolation.md)</span><span class="sxs-lookup"><span data-stu-id="ce2f3-114">For more on how devices are secured during OS updates, see [State separation and isolation](security-state-separation-isolation.md).</span></span> 

<span data-ttu-id="ce2f3-115">A rendszergazdák a szabályzatfrissítési szabályzatról a Policy CSP – Update (Szabályzat csp- és frissítés) [című témakörben olvashatnak bővebben.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update)</span><span class="sxs-lookup"><span data-stu-id="ce2f3-115">IT admins can learn more about update policy at [Policy CSP - Update](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update).</span></span> 
