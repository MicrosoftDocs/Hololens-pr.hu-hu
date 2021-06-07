---
title: HoloLens biztonsági architektúra
description: Biztonsági architektúra
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: biztonság, hololens, hololens 2, hololens2 biztonság, biztonsági áttekintés, biztonsági architektúra, architektúra, hololens 2 architektúra
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379543"
---
# <a name="security-overview-and-architecture"></a><span data-ttu-id="d36eb-104">Biztonsági áttekintés és architektúra</span><span class="sxs-lookup"><span data-stu-id="d36eb-104">Security overview and architecture</span></span>

<span data-ttu-id="d36eb-105">A HoloLens 2 biztonsági architektúrát az egész világból úgy tervezték meg és alakítottuk ki, hogy ne legyen régebbi biztonsági probléma, és minimális támadási felületet hozzon létre.</span><span class="sxs-lookup"><span data-stu-id="d36eb-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="d36eb-106">Ez az új, innovatív architektúra biztonságos tárolási helyeket és fejlett biztonsági elemeket kínál olyan mechanizmusokkal, amelyek képesek védeni az operációs rendszereket a potenciális fenyegetésektől és biztonsági résektől.</span><span class="sxs-lookup"><span data-stu-id="d36eb-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="d36eb-107">A HoloLens 2 a hardver, a szoftver, a hálózat és a szolgáltatások kombinálása által biztosítja a teljes biztonságot, miközben optimális felhasználói élményt nyújt a felhasználónak.</span><span class="sxs-lookup"><span data-stu-id="d36eb-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="d36eb-108">A HoloLens 2-ben a biztonsági funkciók nagy része automatikusan bekapcsol, így minimálisra van szükség az operációs rendszer helyes beállításához és konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="d36eb-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="d36eb-109">A Windows HoloLens 2 és az operációs rendszer architektúrája az alábbi innovatív biztonsági funkciókat kínálja:</span><span class="sxs-lookup"><span data-stu-id="d36eb-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="d36eb-110">**Állapotok elkülönítése** és elkülönítése: Ez az új architektúra megvédi a HoloLens 2 operációs rendszer kritikus részeit a változásoktól, például az alapvető operációs rendszer megbízható állapotba való rendszerindításához szükségeseket.</span><span class="sxs-lookup"><span data-stu-id="d36eb-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="d36eb-111">Az elkülönítési technológia arra használható, hogy a nem megbízható alkalmazásokat a védőfalon belül korlátozzák, így azok ne tudják befolyásolni a rendszer biztonságát.</span><span class="sxs-lookup"><span data-stu-id="d36eb-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="d36eb-112">A teljes operációs rendszer biztonságos szakaszokra van osztva, amelyek mindegyikét különböző biztonsági technológiák kombinációja védi.</span><span class="sxs-lookup"><span data-stu-id="d36eb-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="d36eb-113">**Adatvédelem:** Ha egy felhasználó eszköze elveszett vagy ellopták, a HoloLens 2 megakadályozza, hogy jogosulatlan alkalmazások bizalmas adatokat olvassanak be az adatok BitLocker-titkosításának használatával.</span><span class="sxs-lookup"><span data-stu-id="d36eb-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="d36eb-114">**Jelszóval** nem rendelkező operációs rendszer: A régebbi, jelszóalapú operációs rendszerek akaratlanul is adathalászati fenyegetéseknek tehetnek ki felhasználókat, és gyakran felelősek a feltört fiókokért.</span><span class="sxs-lookup"><span data-stu-id="d36eb-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="d36eb-115">Windows Holographic for Business megszünteti a jelszavak használatát az MSA- és Az Azure AD-bejelentkezéshez, és megerősíti a felhasználói identitások védelmét Windows Hello™ FIDO2-bejelentkezéssel.</span><span class="sxs-lookup"><span data-stu-id="d36eb-115">Windows Holographic for Business eliminates the use of passwords for MSA and Azure AD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="d36eb-116">A FIDO2 támogatásához az eszköznek az 19041-es vagy újabb builden kell lennie.</span><span class="sxs-lookup"><span data-stu-id="d36eb-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="d36eb-117">**Hálózati biztonság:** A HoloLens 2 továbbfejlesztett protokollok és alapértelmezett beállítások révén növeli a felhasználók hálózati biztonságát.</span><span class="sxs-lookup"><span data-stu-id="d36eb-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
