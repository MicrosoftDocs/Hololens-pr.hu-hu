---
title: A HoloLens megosztása több felhasználóval
description: A HoloLenst konfigurálhatja úgy, hogy több fiókkal Azure Active Directory, vagy több, egyetlen fiókot használó felhasználóval osztva.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378120"
---
# <a name="share-your-hololens-with-multiple-people"></a><span data-ttu-id="efff4-103">A HoloLens megosztása több felhasználóval</span><span class="sxs-lookup"><span data-stu-id="efff4-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="efff4-104">Gyakori, hogy egy HoloLenst sokak között osztunk meg, vagy sokak osztoznak HoloLens-eszközökön.</span><span class="sxs-lookup"><span data-stu-id="efff4-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="efff4-105">Ez a cikk az eszközök megosztásának különböző módjait ismerteti.</span><span class="sxs-lookup"><span data-stu-id="efff4-105">This article describes the different ways in which you can share a device.</span></span>

## <a name="share-with-multiple-people-each-using-their-own-account"></a><span data-ttu-id="efff4-106">Megosztás több felhasználóval, mindegyiket a saját fiókjával</span><span class="sxs-lookup"><span data-stu-id="efff4-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="efff4-107">**Előfeltétel:** A HoloLens-eszköznek Windows 10 1803-as vagy újabb verziójú verziójának kell futnia.</span><span class="sxs-lookup"><span data-stu-id="efff4-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="efff4-108">A HoloLenst (1. generációs) is frissíteni kell a [Windows Holographic for Business.](hololens-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="efff4-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="efff4-109">Amikor saját fiókokat Azure Active Directory (Azure AD) használ, egyszerre több felhasználó is megtarthatja saját felhasználói beállításait és felhasználói adatait az eszközön.</span><span class="sxs-lookup"><span data-stu-id="efff4-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="efff4-110">Annak érdekében, hogy többen is használják a saját fiókjukat a HoloLensben, az alábbi lépésekkel konfigurálhatja:</span><span class="sxs-lookup"><span data-stu-id="efff4-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="efff4-111">Győződjön meg arról, hogy az eszköz Windows 10 1803-as vagy újabb verzióját használja.</span><span class="sxs-lookup"><span data-stu-id="efff4-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="efff4-112">Ha HoloLens-eszközt (1. generációs) használ, frissítse az eszközt a [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="efff4-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="efff4-113">Az eszköz beállításakor válassza a Saját munkahelyi **vagy** iskolai tulajdonú lehetőséget, és jelentkezzen be egy Azure AD-fiókkal.</span><span class="sxs-lookup"><span data-stu-id="efff4-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="efff4-114">A beállítás befejezése után győződjön megarról, hogy a fiókbeállítások  >  **(Beállításfiókok)** tartalmazzák az **Egyéb felhasználók beállítást.**</span><span class="sxs-lookup"><span data-stu-id="efff4-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="efff4-115">A HoloLens használata érdekében minden felhasználó az alábbi lépéseket követi:</span><span class="sxs-lookup"><span data-stu-id="efff4-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="efff4-116">Ha egy másik felhasználó már használja az eszközt, tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="efff4-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="efff4-117">A készenléti állapotba való visszatéréshez nyomja le egyszer a bekapcsológombot, majd a zárolási képernyőre való visszatéréshez nyomja le újra a bekapcsológombot</span><span class="sxs-lookup"><span data-stu-id="efff4-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="efff4-118">A HoloLens 2-felhasználók a felhasználó csempéjét Start menü aktuális felhasználó kijelentkeztetése érdekében.</span><span class="sxs-lookup"><span data-stu-id="efff4-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="efff4-119">Jelentkezzen be az eszközre az Azure AD-fiók hitelesítő adataival.</span><span class="sxs-lookup"><span data-stu-id="efff4-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="efff4-120">Ha első alkalommal használja az eszközt, a [saját](hololens-calibration.md) szemére kell állítania a HoloLenst.</span><span class="sxs-lookup"><span data-stu-id="efff4-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="efff4-121">Az eszköz felhasználóinak listáját úgy láthatja, hogy eltávolít egy felhasználót az eszközről, ha a Beállítások fiókok  >    >  **– Egyéb felhasználók lehetőséget használja.**</span><span class="sxs-lookup"><span data-stu-id="efff4-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <a name="share-with-multiple-people-all-using-the-same-account"></a><span data-ttu-id="efff4-122">Megosztás több felhasználóval, mind ugyanazt a fiókot használva</span><span class="sxs-lookup"><span data-stu-id="efff4-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="efff4-123">Egy HoloLens-eszközt több felhasználó is megoszthat egyetlen felhasználói fiók használatával.</span><span class="sxs-lookup"><span data-stu-id="efff4-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="efff4-124">**A HoloLens 2-ben,** amikor egy új felhasználó először helyezi a fejére az eszközt (miközben ugyanazt a fiókot tartja bejelentkezve), az eszköz arra kéri az új felhasználót, hogy gyorsan állítsa be és szabja személyre a megtekintési élményt.</span><span class="sxs-lookup"><span data-stu-id="efff4-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="efff4-125">Az eszköz tárolhatja a hőmérsékleti információkat, így a jövőben automatikusan optimalizálhatja az egyes felhasználók megtekintési élményének minőségét és kényelmi élményét.</span><span class="sxs-lookup"><span data-stu-id="efff4-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="efff4-126">A felhasználóknak nem kell újra bekalkenni az eszközt.</span><span class="sxs-lookup"><span data-stu-id="efff4-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="efff4-127">A fiókot megosztó **HoloLens- (1. generációs)** felhasználóknak újra kell kérniük az újraszámítást a Beállítások alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="efff4-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="efff4-128">További információ a [beszibrálásról.](hololens-calibration.md)</span><span class="sxs-lookup"><span data-stu-id="efff4-128">Read more about [calibration](hololens-calibration.md).</span></span>
