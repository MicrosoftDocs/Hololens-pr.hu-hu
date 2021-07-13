---
title: Telepítési útmutató – Vállalati csatlakoztatott HoloLens 2 Dynamics 365-útmutatók – Karbantartás
description: Megtudhatja, hogyan tarthatja fenn HoloLens 2 eszközét egy vállalati csatlakoztatott hálózaton keresztül a Dynamics 365-útmutatók segítségével.
keywords: HoloLens, felügyelet, vállalati kapcsolat, Dynamics 365-útmutatók, AAD, Azure AD, MDM, Mobile Eszközkezelés
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636996"
---
# <a name="maintain---corporate-connected-guide"></a><span data-ttu-id="b6b88-104">Karbantartás – Vállalati csatlakoztatott útmutató</span><span class="sxs-lookup"><span data-stu-id="b6b88-104">Maintain - Corporate Connected Guide</span></span>

## <a name="update-hololens"></a><span data-ttu-id="b6b88-105">Frissítés HoloLens</span><span class="sxs-lookup"><span data-stu-id="b6b88-105">Update HoloLens</span></span>

<span data-ttu-id="b6b88-106">A Microsoft úgy tervezte meg az Windows Update for Businesst, hogy Windows rendszergazdák számára további frissítésközpontú felügyeleti képességeket biztosítson, például lehetővé teszi frissítések telepítését eszközcsoportokra, valamint karbantartási időszakokat határozzon meg a frissítések telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="b6b88-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="b6b88-107">A frissítések kezelésének egyik népszerű módja a 30 napos funkció-halasztás.</span><span class="sxs-lookup"><span data-stu-id="b6b88-107">One popular method of managing updates is to do a feature deferral of 30 days.</span></span> <span data-ttu-id="b6b88-108">Ez lehetővé teszi a rendszergazdák számára az új funkciók frissítését és előzetes megtekintését, így első kézből szereznek ismereteket, és értesítik az ügyfélszolgálatot az új változásokról.</span><span class="sxs-lookup"><span data-stu-id="b6b88-108">This allows Admins to update and preview new features, gaining first hand knowledge and informing your support desk of any new changes.</span></span>

<span data-ttu-id="b6b88-109">Megtudhatja, hogyan kezelheti [a HoloLens frissítéseit,](/hololens/hololens-updates)beleértve az ütemezett napokat, az ütemezett időpontokat és az aktív órák beállítását az eszközön, hogy az munkaidőn kívül frissülni tudjon.</span><span class="sxs-lookup"><span data-stu-id="b6b88-109">Learn how to [manage HoloLens updates](/hololens/hololens-updates), including scheduled days, scheduled time, and setting active hours on the device, so it will update outside of working hours.</span></span>

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a><span data-ttu-id="b6b88-110">Dynamics 365-útmutatók (és egyéb áruházbeli alkalmazások) frissítése</span><span class="sxs-lookup"><span data-stu-id="b6b88-110">How to update Dynamics 365 Guides (and other store apps)</span></span>

<span data-ttu-id="b6b88-111">A Dynamics 365-útmutatók egy In-Box alkalmazás, amely a Microsoft Store frissíthető.</span><span class="sxs-lookup"><span data-stu-id="b6b88-111">Dynamics 365 Guides is an In-Box app, and can be updated through the Microsoft Store app.</span></span> <span data-ttu-id="b6b88-112">Az alkalmazáson keresztül letöltött Microsoft Store frissíthetők a Microsoft Store [alkalmazáson](/hololens/holographic-store-apps#update-apps) keresztül.</span><span class="sxs-lookup"><span data-stu-id="b6b88-112">For all apps that are downloaded through the Microsoft Store, they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="how-to-update-lob-apps"></a><span data-ttu-id="b6b88-113">LOB-alkalmazások frissítése</span><span class="sxs-lookup"><span data-stu-id="b6b88-113">How to update LOB apps</span></span>

<span data-ttu-id="b6b88-114">Az LOB-alkalmazások ugyanúgy frissíthetők, mint az Intune-ban.</span><span class="sxs-lookup"><span data-stu-id="b6b88-114">LOB apps can be updated in the same way they were added to Intune.</span></span> <span data-ttu-id="b6b88-115">Az alkalmazások frissíthetők az Intune-ban, ha az új alkalmazást magasabb verziószámmal tölti fel a meglévő alkalmazáskonfigurációba.</span><span class="sxs-lookup"><span data-stu-id="b6b88-115">Apps can be updated in Intune by uploading the new app with a higher version number to the existing App configuration.</span></span> <span data-ttu-id="b6b88-116">Amikor az eszköz szinkronizál az Intune-nal, megfigyeli, hogy az alkalmazás újabb verzióban jelenik meg, és a rendszer letölti az újabb alkalmazást, és lecseréli a régi alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="b6b88-116">When the device syncs to Intune, it will observe that there is a newer app version and the newer app will be downloaded and replace the old app.</span></span>

1. <span data-ttu-id="b6b88-117">Az újabb alkalmazás feltöltéséhez lépjen a [MEM-portál](https://endpoint.microsoft.com/#home)  ->  **Alkalmazások** -> Minden alkalmazás  ->  *TheNameOfYourApp Tulajdonságai*  ->  **elemre.**</span><span class="sxs-lookup"><span data-stu-id="b6b88-117">To upload the newer app, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** -> *TheNameOfYourApp* -> **Properties.**</span></span>
2. <span data-ttu-id="b6b88-118">Az Alkalmazás adatai mellett válassza a Szerkesztés **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="b6b88-118">Next to App information, select **Edit.**</span></span>
3. <span data-ttu-id="b6b88-119">A Frissíteni kívánt &quot; fájl kiválasztása &quot; értékeként válassza ki a fájlt.</span><span class="sxs-lookup"><span data-stu-id="b6b88-119">For the value of &quot;Select file to update&quot;, select your file.</span></span>
4. <span data-ttu-id="b6b88-120">Innen a helyi menüben nyissa meg a fájlkezelőt, és töltse fel az LOB alkalmazás újabb verzióját.</span><span class="sxs-lookup"><span data-stu-id="b6b88-120">From here, use the context menu to open your file explorer and upload the newer version of the LOB app.</span></span> <span data-ttu-id="b6b88-121">Győződjön meg arról, hogy szükség szerint tartalmaz függőségeket.</span><span class="sxs-lookup"><span data-stu-id="b6b88-121">Ensure to include dependencies as needed.</span></span>

<span data-ttu-id="b6b88-122">További információ: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="b6b88-122">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="development-plan"></a><span data-ttu-id="b6b88-123">Fejlesztési terv</span><span class="sxs-lookup"><span data-stu-id="b6b88-123">Development Plan</span></span>

<span data-ttu-id="b6b88-124">Most, hogy sikeresen regisztrálta az eszközt, készen áll arra, hogy további LOB-alkalmazásokat telepítsen az eszközeire.</span><span class="sxs-lookup"><span data-stu-id="b6b88-124">With your device successfully enrolled, you are now prepared to deploy more LOB apps to your devices.</span></span> <span data-ttu-id="b6b88-125">Ebben az útmutatóban egy mintaalkalmazást használunk, de valószínűbb, hogy a szervezet igényeinek megfelelő egyéni alkalmazásokat szeretne használni.</span><span class="sxs-lookup"><span data-stu-id="b6b88-125">For the duration of this Guide, we're using a sample app, but it's more likely that you will want to use custom apps built for your organization's needs.</span></span>

<span data-ttu-id="b6b88-126">Ha már rendelkezik LOB-alkalmazással, készen áll az alkalmazás [MDM-ben való üzembe helyezésére.](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="b6b88-126">If you already have a LOB app, then you're ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="b6b88-127">Ha más módszert szeretne használni, tekintse át az [HoloLens 2.](/hololens/app-deploy-overview) év alkalmazástelepítési áttekintését, amelyből megtudhatja, hogyan helyezheti üzembe az LOB-alkalmazást az eszközökön.</span><span class="sxs-lookup"><span data-stu-id="b6b88-127">If you'd prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="b6b88-128">Ha még nem hoz létre saját LOB-alkalmazást, vagy még létrehozás alatt áll, tekintse [](/windows/mixed-reality/design/design) át a vegyes valóságú fejlesztési dokumentumokban a tervezést és prototípus-készítést, vagy ismerje meg a vegyes valóságú fejlesztés alapvető [fogalmait.](/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="b6b88-128">If you've yet to create your own LOB app or are still in the process of creation, then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="support-plan"></a><span data-ttu-id="b6b88-129">Támogatási csomag</span><span class="sxs-lookup"><span data-stu-id="b6b88-129">Support Plan</span></span>

<span data-ttu-id="b6b88-130">A támogatási csomag kitűnően alkalmas a helyzetre.</span><span class="sxs-lookup"><span data-stu-id="b6b88-130">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="b6b88-131">Hasznos, ha valaki vagy egy csoport be van tanítva az HoloLens-eszközökön a regisztrációs folyamat hibaelhárítására, valamint a HoloLens-eszköz általános használatára a szervezeten belül.</span><span class="sxs-lookup"><span data-stu-id="b6b88-131">Having someone, or a group, trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="b6b88-132">Annak érdekében, hogy a felhasználók minél gyorsabban megoldják a problémáikat, javasoljuk, hogy az eszkalációs folyamatot a következő sorrendhez hasonlóan kell kezelnie:</span><span class="sxs-lookup"><span data-stu-id="b6b88-132">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="b6b88-133">Az ügyfélszolgálat.</span><span class="sxs-lookup"><span data-stu-id="b6b88-133">Your Support desk.</span></span>
2. <span data-ttu-id="b6b88-134">Az HoloLens szakértő csapata</span><span class="sxs-lookup"><span data-stu-id="b6b88-134">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="b6b88-135">[HoloLens Docs](/hololens/)  /  [HoloLens Docs hibaelhárítása](/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="b6b88-135">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="b6b88-136">Kapcsolatfelvétel az ügyfélszolgálattal</span><span class="sxs-lookup"><span data-stu-id="b6b88-136">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a><span data-ttu-id="b6b88-137">Eszközkezelés</span><span class="sxs-lookup"><span data-stu-id="b6b88-137">Device Management</span></span>

<span data-ttu-id="b6b88-138">Ez az útmutató a Mobile Eszközkezelés (MDM) beállításával, valamint néhány eszközkonfiguráció beállításával és az olyan beállítások alkalmazásával kapcsolatban volt szó, amelyek lehetővé teszik a Wi-Fi tanúsítványok és proxyk hozzáférését.</span><span class="sxs-lookup"><span data-stu-id="b6b88-138">This guide talked about setting up Mobile Device Management (MDM) and used it to set up some device configurations and apply settings to allow access in terms of Wi-Fi certificates and proxy.</span></span> <span data-ttu-id="b6b88-139">Az MDM-et azonban eszközkorlátozások alkalmazására is használhatja CSP-k és szabályzatok segítségével.</span><span class="sxs-lookup"><span data-stu-id="b6b88-139">However, MDM can also be used to apply device restrictions via CSPs and Policies.</span></span>

<span data-ttu-id="b6b88-140">Sok esetben az eszközökre kapcsolati korlátozások vonatkoznak, például Bluetooth, VPN, USB, vagy akár a kamera vagy a mikrofon hozzáférésének kikapcsolása.</span><span class="sxs-lookup"><span data-stu-id="b6b88-140">In many cases, devices can have connectivity restrictions, such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="b6b88-141">Ha ezek bármelyike érdekli, javasoljuk, hogy olvassa el az általános [eszközkorlátozási oldalt.](/hololens/hololens-common-device-restrictions)</span><span class="sxs-lookup"><span data-stu-id="b6b88-141">If any of these interests you, then we encourage you to read our [common device restrictions page](/hololens/hololens-common-device-restrictions).</span></span>

<span data-ttu-id="b6b88-142">Más összetettebb eszközkorlátozásokat is használhat.</span><span class="sxs-lookup"><span data-stu-id="b6b88-142">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="b6b88-143">Például:</span><span class="sxs-lookup"><span data-stu-id="b6b88-143">Such as:</span></span>

- <span data-ttu-id="b6b88-144">Korlátozza a Gépház-alkalmazásban megtekinthető oldalakat a [SettingsPageVisibility](/hololens/settings-uri-list)(Lap láthatósága) használatával, így a felhasználók csak a módosítania szükséges beállításokhoz férhetnek hozzá, például módosíthatják Wi-Fi kapcsolatukat.</span><span class="sxs-lookup"><span data-stu-id="b6b88-144">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](/hololens/settings-uri-list), allowing users to only access the settings they need to adjust, such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="b6b88-145">A [Kioszk mód használatával](/hololens/hololens-kiosk) korlátozhatja az eszköz felhasználói felületét.</span><span class="sxs-lookup"><span data-stu-id="b6b88-145">Use [Kiosk mode](/hololens/hololens-kiosk) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="b6b88-146">A kioszkokat beállíthatja úgy, hogy egyetlen alkalmazást, vagy több alkalmazást is mutassanak egy egyéni kezdőlapon.</span><span class="sxs-lookup"><span data-stu-id="b6b88-146">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="b6b88-147">A kioszkok különböző felhasználói élményt is kínálnak.</span><span class="sxs-lookup"><span data-stu-id="b6b88-147">Kiosks can also present different experiences to different users.</span></span>
- <span data-ttu-id="b6b88-148">[Windows alkalmazásvezérlés (WDAC) segítségével bizonyos](/hololens/windows-defender-application-control-wdac) alkalmazásokat vagy folyamatokat nem lehet teljesen elindítani.</span><span class="sxs-lookup"><span data-stu-id="b6b88-148">[Windows Application Control (WDAC)](/hololens/windows-defender-application-control-wdac) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="b6b88-149">Ha többet szeretne megtudni az eszközkezelés vagy az eszközkorlátozások további módszereiről, olvassa el a következő lépést, és olvassa el Eszközkezelés [áttekintését.](/hololens/hololens-csp-policy-overview)</span><span class="sxs-lookup"><span data-stu-id="b6b88-149">If you'd like to learn about additional methods of device management or device restrictions, then take the next step and read our [Device Management Overview](/hololens/hololens-csp-policy-overview).</span></span>





