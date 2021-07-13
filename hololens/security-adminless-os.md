---
title: Rendszergazdai jogosultsággal nem kapcsolatos operációsrendszer-biztonság
description: Ismerje meg a rendszergazda nélküli operációs rendszereket, az eszköztulajdonosokat és a biztonságot HoloLens vegyes valóságú eszközökön.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: biztonság, hololens, adminless, admin-less, operating system, admin-less operating system, admin os, admin-less os, hololens 2, hololens2 security,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639403"
---
# <a name="admin-less-operating-system"></a><span data-ttu-id="efda0-104">Rendszergazdai jogosultságokkal nem működő operációs rendszer</span><span class="sxs-lookup"><span data-stu-id="efda0-104">Admin-less operating system</span></span>

<span data-ttu-id="efda0-105">HoloLens 2. beállítás minimálisra csökkenti a jogosultságok eszkalálására vonatkozó felületet azáltal, hogy letiltja a Rendszergazdák csoport támogatását, és korlátozza az összes külső UWP-alkalmazáskódot, hogy az alkalmazás csak általános jogú felhasználóként legyen végrehajtva az AppContainer-védőfalon belül.</span><span class="sxs-lookup"><span data-stu-id="efda0-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="efda0-106">Ez a kód csak olyan képességek által védett erőforrásokhoz kap hozzáférést, amelyek explicit módon az alkalmazásban egy nem védett felhasználó számára vannak megszabadulva, valamint az összes AppContainers számára elérhető erőforrásokhoz.</span><span class="sxs-lookup"><span data-stu-id="efda0-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="efda0-107">Ezek az alkalmazásképességek továbbra is a háromszintű besorolási modellel rendelkeznek:</span><span class="sxs-lookup"><span data-stu-id="efda0-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="efda0-108">Általános kérdések</span><span class="sxs-lookup"><span data-stu-id="efda0-108">General</span></span>
  * <span data-ttu-id="efda0-109">Korlátozott hozzáférésű</span><span class="sxs-lookup"><span data-stu-id="efda0-109">Restricted</span></span>
  * <span data-ttu-id="efda0-110">Windows</span><span class="sxs-lookup"><span data-stu-id="efda0-110">Windows</span></span>

<span data-ttu-id="efda0-111">Windows összetevők az AppContainer-védőfalat is kihasználják a rendszer UWPs-ekkel.</span><span class="sxs-lookup"><span data-stu-id="efda0-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="efda0-112">A Universal Windows Platformról (UWP) az [UWP dokumentációjában talál további információt.](/windows/uwp/)</span><span class="sxs-lookup"><span data-stu-id="efda0-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](/windows/uwp/).</span></span> <span data-ttu-id="efda0-113">Emellett a nagyobb jogosultságcsökkentési igényekkel rendelkező Windows-összetevők (például a böngészőtartalom oldalai vagy elemzői) a Less Privileged AppContainer (LPAC) védőkészletet használják, amely csökkenti az összes AppContainers számára elérhető erőforráskészlethez való hozzáférést.</span><span class="sxs-lookup"><span data-stu-id="efda0-113">Additionally, Windows components with greater privilege reduction needs (like browser content pages or parsers) use the Less Privileged AppContainer (LPAC) sandbox, which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <a name="device-owner"></a><span data-ttu-id="efda0-114">Az eszköz tulajdonosa</span><span class="sxs-lookup"><span data-stu-id="efda0-114">Device owner</span></span>

<span data-ttu-id="efda0-115">Végezetül, az eszközre vonatkozó meghatározott műveletek végrehajtása, például az eszköz bérlőhöz vagy felhasználókezeléshez való csatlakozása csak "eszköztulajdonosok" számára engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="efda0-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="efda0-116">Ezt a csoportot az eszköz felhasználói töltik ki az alábbi lépések egyikével:</span><span class="sxs-lookup"><span data-stu-id="efda0-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="efda0-117">Az eszköz első felhasználója mindig Tulajdonosként van ki jelölni.</span><span class="sxs-lookup"><span data-stu-id="efda0-117">The first user on the device is always designated an Owner.</span></span> 
> [!IMPORTANT]
><span data-ttu-id="efda0-118">Az Azure AD-felhasználók kivételt képeznek ez alól a szabály alól, ha az eszköz Autopilot- vagy tömeges Azure AD-regisztráción keresztül csatlakozik az Azure AD-hez, amely nem valódi felhasználót használ.</span><span class="sxs-lookup"><span data-stu-id="efda0-118">For Azure AD Users, the exception to this rule is that if the device is Azure AD joined via Autopilot or bulk Azure AD enrollment, which uses a non-real user.</span></span> <span data-ttu-id="efda0-119">Ebben az esetben előfordulhat, hogy az eszközre bejelentkező első AAD-felhasználó nem lesz automatikusan eszköztulajdonos, kivéve, ha a felhasználóhoz hozzá van rendelve a "globális rendszergazda" vagy az "eszköz-rendszergazda" Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="efda0-119">In this case, the first AAD user to sign into the device may not be made device owner automatically unless that user has the "global administrator" or "device administrator" role assigned in Azure portal.</span></span> <span data-ttu-id="efda0-120">További információért tekintse meg az alábbi megjegyzést.</span><span class="sxs-lookup"><span data-stu-id="efda0-120">For more information, see the note below.</span></span>  

  * <span data-ttu-id="efda0-121">Ha egy felhasználót tulajdonosként léptet elő a felhasználói felületről Gépház egy másik tulajdonos használja az eszközön.</span><span class="sxs-lookup"><span data-stu-id="efda0-121">When a user is promoted to be an Owner from the Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="efda0-122">Ha az eszköz tulajdonosa már nem érhető el (elhagyja a vállalatot), és az eszköz csatlakozik az Azure AD-hez, a bérlői rendszergazda új felhasználóra módosíthatja az eszköz tulajdonosát a Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="efda0-122">If the device owner is no longer available (leaves the company) and the device is Azure AD joined, the Tenant Admin can change the device owner to a new user in Azure portal.</span></span> <span data-ttu-id="efda0-123">Az Azure AD-bérlő globális rendszergazdái és eszköz-rendszergazdái tulajdonosként vannak implicit módon bejelentkezve az eszközön anélkül, hogy az előző lépések valamelyikére szükség volna.</span><span class="sxs-lookup"><span data-stu-id="efda0-123">Global Administrators and Device Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span>  

 <span data-ttu-id="efda0-124">A rendszergazdák adatvédelmi szabályzatokkal kezelhetik, hogy mely alkalmazások [férhetnek](/windows/client-management/mdm/policy-csp-privacy) hozzá.</span><span class="sxs-lookup"><span data-stu-id="efda0-124">IT administrators can manage what apps can access through [Privacy](/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 

> [!NOTE]
> <span data-ttu-id="efda0-125">Ha többet szeretne tudni arról, hogy ki lett eszköztulajdonos egy Azure AD-hez csatlakozott eszközön, tekintse meg a ["Helyi](/azure/active-directory/devices/assign-local-admin) rendszergazda hozzárendelése" dokumentációt (de olvassa el a "helyi rendszergazda" olvasott "eszköztulajdonosként" című témakört, mivel a rendszergazda nem létezik a HoloLens).</span><span class="sxs-lookup"><span data-stu-id="efda0-125">To understand more about who is made a device owner on an Azure AD joined device, see [“Assign Local Admin” documentation](/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>