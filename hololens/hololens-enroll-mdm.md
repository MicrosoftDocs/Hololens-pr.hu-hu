---
title: Regisztráció HoloLens MDM-be
description: Megtudhatja, hogyan regisztrálhat HoloLens mobileszköz-felügyeletben (MDM) több eszköz egyszerűbb kezelése érdekében.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 6c279664fa6051fab2f5e2e8f61e70b55704ae7c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640406"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="0b5c4-103">Regisztráció HoloLens MDM-be</span><span class="sxs-lookup"><span data-stu-id="0b5c4-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="0b5c4-104">Egyidejűleg több Microsoft HoloLens is felügyelhet olyan megoldásokkal, mint a [Microsoft Intune.](/intune/windows-holographic-for-business)</span><span class="sxs-lookup"><span data-stu-id="0b5c4-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="0b5c4-105">Kezelheti a beállításokat, kiválaszthatja a telepíteni kívánt alkalmazásokat, és beállíthatja a szervezet igényeihez igazított biztonsági konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="0b5c4-106">Lásd: A [Holographic Windows-t](/intune/windows-holographic-for-business)futtató eszközök kezelése a Microsoft Intune segítségével, a Windows Holographic által támogatott konfigurációszolgáltatók [(CSP-k)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)és a [Windows Holographic for Business.](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)</span><span class="sxs-lookup"><span data-stu-id="0b5c4-106">See [Manage devices running Windows Holographic with Microsoft Intune](/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="0b5c4-107">A mobileszköz-kezelés (MDM), beleértve a VPN- és BitLocker- és kioszkmódú funkciókat is, csak akkor érhető el, ha az [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="0b5c4-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="0b5c4-108">Követelmények</span><span class="sxs-lookup"><span data-stu-id="0b5c4-108">Requirements</span></span>

 <span data-ttu-id="0b5c4-109">A cégének be kell állítania a Mobile Eszközkezelés (MDM) eszközt a mobileszközök HoloLens kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="0b5c4-110">Az MDM-szolgáltató lehet Microsoft Intune microsoftos MDM API-kat használó külső szolgáltató.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="0b5c4-111">A regisztrálás különböző módjai</span><span class="sxs-lookup"><span data-stu-id="0b5c4-111">Different ways to enroll</span></span>

<span data-ttu-id="0b5c4-112">Az OOBE [vagy](hololens-identity.md) a bejelentkezés után választott identitás típusától függően különböző regisztrációs módszerek állnak a létezik.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="0b5c4-113">Ha az Identity az Azure AD, akkor az OOBE vagy Gépház **alkalmazás-hozzáférés** munkahelyi vagy iskolai Csatlakozás  ->    ->   gombra.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="0b5c4-114">Az Azure AD esetén az [automatikus MDM-regisztráció](hololens-enroll-mdm.md#auto-enrollment-in-mdm) csak akkor történik meg, ha az Azure AD-t regisztrációs URL-címekkel konfigurálták.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="0b5c4-115">Ha az Identity az Azure AD, és az eszköz előre regisztrálva van az Intune MDM-kiszolgálón, és hozzá van rendelve egy adott konfigurációs profil, akkor az Azure AD-Join és az automatikus [MDM-regisztráció](hololens-enroll-mdm.md#auto-enrollment-in-mdm) az OOBE során történik.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="0b5c4-116">Más néven [Autopilot-folyamat](hololens2-autopilot.md) Az [19041.1103-](hololens-release-notes.md#windows-holographic-version-2004)buildek alatt érhető el.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="0b5c4-117">Ha az Identity az MSA, akkor használja **Gépház Alkalmazás-hozzáférés** munkahelyi vagy iskolai  ->    ->  **Csatlakozás** gombot.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="0b5c4-118">Más néven Munkahelyi fiók hozzáadása (AWA) folyamat.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="0b5c4-119">Ha az Identitás helyi felhasználó, akkor Gépház **alkalmazás-hozzáférés** munkahelyi vagy iskolai regisztrációja csak az  ->    ->  **eszközkezelési hivatkozáson keresztül.**</span><span class="sxs-lookup"><span data-stu-id="0b5c4-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="0b5c4-120">Más néven tiszta MDM-regisztrációs folyamat.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="0b5c4-121">Miután regisztrálta az eszközt az MDM-kiszolgálón, az Gépház azt fogja tükrözni, hogy az eszköz regisztrálva van az eszközkezelésben.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="0b5c4-122">Automatikus regisztráció az MDM-be</span><span class="sxs-lookup"><span data-stu-id="0b5c4-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="0b5c4-123">Ha a szervezet azure Prémium-előfizetéssel rendelkezik, akkor az Azure Active Directory (Azure AD) és egy MDM-megoldást használ, amely elfogad egy [Azure](https://azure.microsoft.com/overview/)AD-jogkivonatot a hitelesítéshez (jelenleg csak az Microsoft Intune és az AirWatch támogatja), a rendszergazda konfigurálhatja az Azure AD-t úgy, hogy automatikusan engedélyezze az MDM-regisztrációt, miután a felhasználó bejelentkezett az Azure AD-fiókjával.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="0b5c4-124">Megtudhatja, hogyan konfigurálhatja az Azure AD-regisztrációt.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-124">Learn how to configure Azure AD enrollment.</span></span>](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="0b5c4-125">Ha az automatikus regisztráció engedélyezve van, nincs szükség további manuális regisztrációra.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="0b5c4-126">Amikor a felhasználó Azure AD-fiókkal jelentkezik be, az eszköz az első futtatási folyamat befejezése után regisztrálva lesz az MDM-be.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="0b5c4-127">Ha egy eszköz Csatlakozik az Azure AD-hez, az hatással lehet arra, hogy ki tekinthető [az eszköz tulajdonosának.](security-adminless-os.md#device-owner)</span><span class="sxs-lookup"><span data-stu-id="0b5c4-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="0b5c4-128">A HoloLens Intune-ból való HoloLens-</span><span class="sxs-lookup"><span data-stu-id="0b5c4-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="0b5c4-129">A regisztrációs módszertől függően előfordulhat, hogy az eszköz regisztrációja nem lesz elérhető.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="0b5c4-130">Ha az eszköz Azure AD-fiókkal vagy Autopilot-fiókkal lett regisztrálva, nem lehet azt az Intune-ból regisztrálni.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="0b5c4-131">Ha szeretne lecsatlakozni a HoloLens Azure AD-ről, vagy újracsatlakozni az Azure AD-bérlőhöz, alaphelyzetbe kell [állítania/újra](hololens-recovery.md#reset-the-device) kell perjelesre állítania az eszközt.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](hololens-recovery.md#reset-the-device) the device.</span></span>

<span data-ttu-id="0b5c4-132">Ha az eszköz munkahelyi fiókot hozzáadott MSA-fiókkal lett regisztrálva, vagy egy helyi fiókkal, amely csak eszközkezelésre lett regisztrálva, akkor lehet, hogy az eszköz regisztrációját már nem kell regisztrálnia.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="0b5c4-133">Nyissa meg a Start menü, majd válassza Gépház **alkalmazás-hozzáférés** munkahelyi vagy iskolai  ->    ->  *fiókok leválasztása*  ->  **gombját.**</span><span class="sxs-lookup"><span data-stu-id="0b5c4-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>