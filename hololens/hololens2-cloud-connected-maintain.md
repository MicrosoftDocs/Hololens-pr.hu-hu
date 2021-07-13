---
title: Telepítési útmutató – Felhőhöz csatlakoztatott HoloLens 2. példány nagy léptékű üzembe helyezése a Remote Assist segítségével – Karbantartás
description: Naprakész maradhat a felhőhöz csatlakoztatott hálózaton keresztüli HoloLens karbantartásával és támogatásával kapcsolatos tippjeinket.
keywords: HoloLens, felügyelet, felhőhöz csatlakoztatott, Remote Assist, AAD, Azure AD, MDM, Mobile Eszközkezelés
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635160"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="8bd43-104">Karbantartás – Felhőhöz csatlakoztatott útmutató</span><span class="sxs-lookup"><span data-stu-id="8bd43-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="8bd43-105">Frissítések</span><span class="sxs-lookup"><span data-stu-id="8bd43-105">Updates</span></span>

<span data-ttu-id="8bd43-106">A Microsoft úgy tervezte meg az Windows Update for Businesst, hogy Windows rendszergazdák számára további frissítésközpontú felügyeleti képességeket biztosítson, például lehetővé teszi frissítések telepítését eszközcsoportokra, valamint karbantartási időszakokat határozzon meg a frissítések telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="8bd43-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="8bd43-107">Megtudhatja, hogyan kezelheti [a HoloLens frissítéseket,](/hololens/hololens-updates) beleértve az ütemezett napokat, az ütemezett időpontokat és az aktív órák beállítását az eszközön, hogy az munkaidőn kívül frissülni tudjon.</span><span class="sxs-lookup"><span data-stu-id="8bd43-107">Learn how to [manage HoloLens updates](/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="8bd43-108">A Remote Assist egy In-Box alkalmazás, amely a Microsoft Store frissítheti.</span><span class="sxs-lookup"><span data-stu-id="8bd43-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="8bd43-109">Az alkalmazáson keresztül letöltött Microsoft Store az alkalmazáson [](/hololens/holographic-store-apps#update-apps) keresztül Microsoft Store manuálisan.</span><span class="sxs-lookup"><span data-stu-id="8bd43-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="8bd43-110">Támogatási csomag</span><span class="sxs-lookup"><span data-stu-id="8bd43-110">Support Plan</span></span>

<span data-ttu-id="8bd43-111">A támogatási csomag kitűnően alkalmas a helyzetre.</span><span class="sxs-lookup"><span data-stu-id="8bd43-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="8bd43-112">Hasznos, ha valakit vagy csoportot tanít be a regisztrációs folyamat hibaelhárítására az HoloLens-eszközökön, és általánosan használja a HoloLens-eszközt a szervezeten belül.</span><span class="sxs-lookup"><span data-stu-id="8bd43-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="8bd43-113">Annak érdekében, hogy a felhasználók minél gyorsabban megoldják a problémáikat, javasoljuk, hogy az eszkalációs folyamatot a következő sorrendhez hasonlóan kell kezelnie:</span><span class="sxs-lookup"><span data-stu-id="8bd43-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="8bd43-114">Az ügyfélszolgálat.</span><span class="sxs-lookup"><span data-stu-id="8bd43-114">Your Support desk.</span></span>
2. <span data-ttu-id="8bd43-115">Az HoloLens szakértő csapata</span><span class="sxs-lookup"><span data-stu-id="8bd43-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="8bd43-116">[HoloLens Docs](/hololens/)  /  [HoloLens Docs hibaelhárítása](/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="8bd43-116">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="8bd43-117">Kapcsolatfelvétel az ügyfélszolgálattal</span><span class="sxs-lookup"><span data-stu-id="8bd43-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="8bd43-118">Fejlesztési terv</span><span class="sxs-lookup"><span data-stu-id="8bd43-118">Development Plan</span></span>

<span data-ttu-id="8bd43-119">Az eszköz sikeres regisztrációja után készen áll az üzletági alkalmazások (LOB-alkalmazások) telepítésére az eszközökön.</span><span class="sxs-lookup"><span data-stu-id="8bd43-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="8bd43-120">Ezek a szervezet igényeihez&#39;egyéni alkalmazások.</span><span class="sxs-lookup"><span data-stu-id="8bd43-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="8bd43-121">Ha már rendelkezik üzletági alkalmazással, készen&#39;az alkalmazás [MDM-en keresztüli üzembe helyezésére.](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="8bd43-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="8bd43-122">Ha&#39;módszert szeretne használni, tekintse át az [HoloLens 2.](/hololens/app-deploy-overview) alkalmazásának üzembe helyezését áttekintő témakört, amelyből megtudhatja, hogyan helyezheti üzembe az LOB-alkalmazást az eszközein.</span><span class="sxs-lookup"><span data-stu-id="8bd43-122">If you&#39;d prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="8bd43-123">Ha még nem&#39;saját LOB-alkalmazást, vagy még létrehozás alatt áll, tekintse át a [](/windows/mixed-reality/design/design) vegyes valóságú fejlesztési dokumentumokban a tervezést és a prototípus-készítést, vagy ismerje meg az alapvető fogalmakat a vegyes valóságú fejlesztés elkezdéséhez. [](/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="8bd43-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="8bd43-124">Eszközkezelés</span><span class="sxs-lookup"><span data-stu-id="8bd43-124">Device Management</span></span> 

<span data-ttu-id="8bd43-125">Bár ez az útmutató a Mobile Eszközkezelés (MDM) beállítását is érintette, nem az eszközökre vonatkozó eszközkorlátozások vagy szabályzatok alkalmazása volt alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="8bd43-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="8bd43-126">Az eszközkezelés lehetővé teszi a hozzáférést a tanúsítványok lekullával vagy a hozzáférés korlátozásával, különböző eszközkorlátozásokkal.</span><span class="sxs-lookup"><span data-stu-id="8bd43-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="8bd43-127">Sok esetben az eszközökre kapcsolati korlátozások vonatkoznak, például Bluetooth, VPN, USB, vagy akár a kamera vagy a mikrofon hozzáférésének kikapcsolása.</span><span class="sxs-lookup"><span data-stu-id="8bd43-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="8bd43-128">Ha ezek bármelyike érdekli, javasoljuk, hogy olvassa el az általános [eszközkorlátozási oldalt.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="8bd43-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="8bd43-129">Más összetettebb eszközkorlátozásokat is használhat.</span><span class="sxs-lookup"><span data-stu-id="8bd43-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="8bd43-130">Például:</span><span class="sxs-lookup"><span data-stu-id="8bd43-130">Such as:</span></span>

- <span data-ttu-id="8bd43-131">Korlátozza a Gépház-alkalmazásban megtekinthető oldalakat a [SettingsPageVisibility](settings-uri-list.md)(Lap láthatósága) használatával, így a felhasználók csak a módosítania szükséges beállításokhoz férhetnek hozzá, például módosíthatják Wi-Fi kapcsolatukat.</span><span class="sxs-lookup"><span data-stu-id="8bd43-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="8bd43-132">A [Kioszk mód használatával](hololens-kiosk.md) korlátozhatja az eszköz felhasználói felületét.</span><span class="sxs-lookup"><span data-stu-id="8bd43-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="8bd43-133">A kioszkokat beállíthatja úgy, hogy egyetlen alkalmazást, vagy több alkalmazást is mutassanak egy egyéni kezdőlapon.</span><span class="sxs-lookup"><span data-stu-id="8bd43-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="8bd43-134">A kioszkok különböző felhasználói élményt is kínálnak.</span><span class="sxs-lookup"><span data-stu-id="8bd43-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="8bd43-135">[Windows alkalmazásvezérlés (WDAC) segítségével bizonyos](windows-defender-application-control-wdac.md) alkalmazásokat vagy folyamatokat nem lehet teljesen elindítani.</span><span class="sxs-lookup"><span data-stu-id="8bd43-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="8bd43-136">Ha többet szeretne megtudni az eszközkezelés vagy az eszközkorlátozások különböző módszereiről, olvassa el a következő lépést, és olvassa el Eszközkezelés áttekintését.</span><span class="sxs-lookup"><span data-stu-id="8bd43-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="8bd43-137">Következő lépés</span><span class="sxs-lookup"><span data-stu-id="8bd43-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8bd43-138">Olvassa el a CSP-k és Eszközkezelés áttekintését</span><span class="sxs-lookup"><span data-stu-id="8bd43-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)