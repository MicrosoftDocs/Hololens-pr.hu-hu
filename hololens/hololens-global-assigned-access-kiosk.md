---
title: Globális hozzáférés hozzárendelve
description: Bevezetés a globális hozzáférésű kioszkok OMA-URI-azonosítójának Intune-nal és Windows-konfigurációtervezővel való használatához.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, hozzárendelt hozzáférés, kioszk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b86d88c7487043c6fcb057f03f353a57e44ef781
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379594"
---
# <a name="global-assigned-access--kiosk"></a><span data-ttu-id="07452-104">Globális hozzáférés – Teljes kioszk</span><span class="sxs-lookup"><span data-stu-id="07452-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="07452-105">Ez a funkció a HoloLens 2-eszközt több alkalmazásos kioszkmódhoz konfigurálja, amely rendszerszinten alkalmazható, nem rendelkezik affinitással semmilyen identitással a rendszeren, és mindenkire érvényes, aki bejelentkezik az eszközre.</span><span class="sxs-lookup"><span data-stu-id="07452-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="07452-106">Ez a funkció jelenleg csak a Windows Insider érhető el.</span><span class="sxs-lookup"><span data-stu-id="07452-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="07452-107">Ha ki szeretné próbálni ezt a funkciót, mielőtt az általánosan elérhető [](hololens-insider.md) lenne a HoloLens-kiadásokban, olvassa el a Windows Insider buildeket.</span><span class="sxs-lookup"><span data-stu-id="07452-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <a name="how-to-use-global-assigned-access-in-intune"></a><span data-ttu-id="07452-108">Hogyan használható a globális hozzárendelt hozzáférés az Intune-ban?</span><span class="sxs-lookup"><span data-stu-id="07452-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="07452-109">Vegye figyelembe a "<!-" jelölésű területeket.</span><span class="sxs-lookup"><span data-stu-id="07452-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="07452-110">Ezekhez a területekhez módosítania kell a beállításait.</span><span class="sxs-lookup"><span data-stu-id="07452-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="07452-111">Hozzon létre egy egyéni OMA URI eszközkonfigurációs profilt az alábbiak szerint, és alkalmazza a HoloLens-eszközcsoportra:</span><span class="sxs-lookup"><span data-stu-id="07452-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="07452-112">URI-érték: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="07452-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="07452-113">![Globálisan hozzárendelt hozzáférés OMA-URI az Intune-ban](images/global-assigned-access-omauri.png)</span><span class="sxs-lookup"><span data-stu-id="07452-113">![Global Assigned Access OMA-URI in Intune](images/global-assigned-access-omauri.png)</span></span>

2. <span data-ttu-id="07452-114">Az értékhez frissítse és illessze be a következő tartalmat:</span><span class="sxs-lookup"><span data-stu-id="07452-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a><span data-ttu-id="07452-115">Hogyan használható a globális hozzáférés a Windows Configuration Designerben?</span><span class="sxs-lookup"><span data-stu-id="07452-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="07452-116">Frissítse és mentse a fent említett XML-blobot XML-fájlként.</span><span class="sxs-lookup"><span data-stu-id="07452-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="07452-117">Kövesse a Kiépítési csomag használata egyalkalmazásos vagy többalkalmazásos [kioszk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)beállítását, különösen a "Prov.</span><span class="sxs-lookup"><span data-stu-id="07452-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="07452-118">package, step 2 – Add the kioszk configuration XML file to a provisioning package" (csomag, 2. lépés– A kioszkkonfigurációs XML-fájl hozzáadása egy kiépítési csomaghoz) és tekintse meg az előző lépésben mentett XML-fájlt.</span><span class="sxs-lookup"><span data-stu-id="07452-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a><span data-ttu-id="07452-119">Létrehozhatok olyan konfigurációt, amelyben a globális mindenkire vonatkozik, és külön konfiguráció vonatkozik 1 Azure AD-fiókra vagy Azure AD-csoportra?</span><span class="sxs-lookup"><span data-stu-id="07452-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="07452-120">Igen, tekintse meg az alábbi XML-blob példáját.</span><span class="sxs-lookup"><span data-stu-id="07452-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="07452-121">A globálisan hozzárendelt hozzáférési profil akkor lesz alkalmazva a HoloLensen, ha nem található a bejelentkezett felhasználóhoz megadott profil, így ez a bejelentkezett felhasználó alapértelmezett kioszkmód-konfigurációja.</span><span class="sxs-lookup"><span data-stu-id="07452-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="07452-122">Példa a használni használt XML-blobra:</span><span class="sxs-lookup"><span data-stu-id="07452-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="07452-123">Vegye figyelembe a kiemelt területeket, amelyek a jelekkel vannak `<!-` megjelölve.</span><span class="sxs-lookup"><span data-stu-id="07452-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="07452-124">Ezekhez a területekhez módosítania kell a beállításait.</span><span class="sxs-lookup"><span data-stu-id="07452-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a><span data-ttu-id="07452-125">Eszköztulajdonosok kizárása a globális hozzárendelt hozzáférési profilból</span><span class="sxs-lookup"><span data-stu-id="07452-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="07452-126">Ez a funkció lehetővé teszi, hogy a HoloLensen[](security-adminless-os.md)"Eszköztulajdonosnak" minősülő felhasználó ki legyen zárva a globális hozzárendelt hozzáférésből.</span><span class="sxs-lookup"><span data-stu-id="07452-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="07452-127">A funkció előnyeinek kihasználása érdekében az XML-blobban többalkalmazásos kioszkkonfigurációhoz ügyeljen arra, hogy a kiemelt sorok hozzáadva is hozzáadva:</span><span class="sxs-lookup"><span data-stu-id="07452-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a><span data-ttu-id="07452-128">További globális hozzáférési példák</span><span class="sxs-lookup"><span data-stu-id="07452-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="07452-129">Ez egy példa a globális hozzáférésű kioszkra, amely azt jelenti, hogy amikor egy felhasználó bejelentkezik, többalkalmazásos kioszkot kap a Beállítások alkalmazással, a Visszajelzési központ és a Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="07452-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="07452-130">Ez a példa egy globálisan hozzárendelt hozzáférésű kioszk, amely kizárja az eszköz tulajdonosát, és amikor bármely más Azure AD-felhasználó bejelentkezik, többalkalmazásos kioszkot kap a Beállítások alkalmazással, a Visszajelzési központ és a Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="07452-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="07452-131">Ez a kioszk egy látogatói fiók másodlagos kioszkkonfigurációját is tartalmazza, amelybe bárki bejelentkezhet a zárolási képernyőn.</span><span class="sxs-lookup"><span data-stu-id="07452-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="07452-132">Amikor egy felhasználó bejelentkezik a látogatói fiókba, többalkalmazásos kioszkot kap, amely csak a Visszajelzési központ rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="07452-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
