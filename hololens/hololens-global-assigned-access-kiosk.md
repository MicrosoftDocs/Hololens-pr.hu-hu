---
title: Globális hozzárendelt hozzáférés
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
ms.openlocfilehash: d89c630da76060fe6c2a049e5fa162e88779bb99
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640423"
---
# <a name="global-assigned-access--kiosk"></a><span data-ttu-id="46a90-104">Globális hozzárendelt hozzáférés – Teljes kioszk</span><span class="sxs-lookup"><span data-stu-id="46a90-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="46a90-105">Ez a funkció HoloLens 2-es eszközt konfigurál több alkalmazás kioszkmódhoz, amely rendszerszinten alkalmazható, nem rendelkezik affinitással semmilyen identitással a rendszeren, és mindenkire érvényes, aki bejelentkezik az eszközre.</span><span class="sxs-lookup"><span data-stu-id="46a90-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="46a90-106">Ez a funkció jelenleg csak belső Windows érhető el.</span><span class="sxs-lookup"><span data-stu-id="46a90-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="46a90-107">Ha szeretné kipróbálni ezt a funkciót, mielőtt az általánosan elérhető lenne [](hololens-insider.md) a HoloLens-kiadásokban, olvassa el a Windows Insider-buildeket.</span><span class="sxs-lookup"><span data-stu-id="46a90-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <a name="how-to-use-global-assigned-access-in-intune"></a><span data-ttu-id="46a90-108">Hogyan használható a globális hozzárendelt hozzáférés az Intune-ban?</span><span class="sxs-lookup"><span data-stu-id="46a90-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="46a90-109">Vegye figyelembe a "<!-" jelű területeket.</span><span class="sxs-lookup"><span data-stu-id="46a90-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="46a90-110">Ezekhez a területekhez a beállításoknak megfelelően kell módosításokat tenni.</span><span class="sxs-lookup"><span data-stu-id="46a90-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="46a90-111">Hozzon létre egy egyéni OMA URI eszközkonfigurációs profilt az alábbiak szerint, és alkalmazza HoloLens eszközcsoportra:</span><span class="sxs-lookup"><span data-stu-id="46a90-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="46a90-112">URI-érték: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="46a90-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="46a90-113">![Globális hozzárendelt hozzáférés OMA-URI az Intune-ban](images/global-assigned-access-omauri.png)</span><span class="sxs-lookup"><span data-stu-id="46a90-113">![Global Assigned Access OMA-URI in Intune](images/global-assigned-access-omauri.png)</span></span>

2. <span data-ttu-id="46a90-114">Az értékhez frissítse és illessze be a következő tartalmat:</span><span class="sxs-lookup"><span data-stu-id="46a90-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a><span data-ttu-id="46a90-115">Hogyan használható a globális hozzárendelt hozzáférés Windows Configuration Designerben?</span><span class="sxs-lookup"><span data-stu-id="46a90-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="46a90-116">Frissítse és mentse a fent említett XML-blobot XML-fájlként.</span><span class="sxs-lookup"><span data-stu-id="46a90-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="46a90-117">Kövesse a Kiépítési csomag használata egyalkalmazásos vagy többalkalmazásos [kioszk](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)beállítását, különösen a "Prov.</span><span class="sxs-lookup"><span data-stu-id="46a90-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="46a90-118">package, step 2 – Add the kioszk configuration XML file to a provisioning package" (csomag, 2. lépés – A kioszkkonfigurációs XML-fájl hozzáadása egy kiépítési csomaghoz) és tekintse meg az előző lépésben mentett XML-fájlt.</span><span class="sxs-lookup"><span data-stu-id="46a90-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a><span data-ttu-id="46a90-119">Létrehozhatok olyan konfigurációt, amelyben a globális mindenkire vonatkozik, és külön konfiguráció vonatkozik 1 Azure AD-fiókra vagy Azure AD-csoportra?</span><span class="sxs-lookup"><span data-stu-id="46a90-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="46a90-120">Igen, tekintse meg az alábbi XML-blob példáját.</span><span class="sxs-lookup"><span data-stu-id="46a90-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="46a90-121">A globális hozzárendelt hozzáférési profil akkor lesz alkalmazva a HoloLens amikor a bejelentkezett felhasználóhoz nem talál egy adott profilt, így ez a bejelentkezett felhasználó alapértelmezett kioszkmódú konfigurációja.</span><span class="sxs-lookup"><span data-stu-id="46a90-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="46a90-122">Példa a használni szükséges XML-blobra:</span><span class="sxs-lookup"><span data-stu-id="46a90-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="46a90-123">Vegye figyelembe a kiemelt területeket, amelyek a jelekkel vannak `<!-` jelölve.</span><span class="sxs-lookup"><span data-stu-id="46a90-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="46a90-124">Ezekhez a területekhez a beállításoknak megfelelően kell módosításokat tenni.</span><span class="sxs-lookup"><span data-stu-id="46a90-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a><span data-ttu-id="46a90-125">Eszköztulajdonosok kizárása a globális hozzárendelt hozzáférési profilból</span><span class="sxs-lookup"><span data-stu-id="46a90-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="46a90-126">Ez a funkció lehetővé teszi, hogy a felhasználók, akik a vállalaton[](security-adminless-os.md)"Eszköztulajdonosnak" minősülnek HoloLens ki lesznek zárva a globális hozzárendelt hozzáférésből.</span><span class="sxs-lookup"><span data-stu-id="46a90-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="46a90-127">A funkció előnyeinek kihasználása érdekében az XML-blobban többalkalmazásos kioszkkonfiguráció esetén győződjön meg arról, hogy a kiemelt sorok fel vannak adva:</span><span class="sxs-lookup"><span data-stu-id="46a90-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a><span data-ttu-id="46a90-128">További globális hozzáférési példák</span><span class="sxs-lookup"><span data-stu-id="46a90-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="46a90-129">Ez egy példa globális hozzáférésű kioszkra, amely azt jelenti, hogy amikor egy felhasználó bejelentkezik, többalkalmazásos kioszkot kap az Gépház App, Visszajelzési központ és Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="46a90-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="46a90-130">Ez a példa egy globálisan hozzárendelt hozzáférésű kioszk, amely kizárja az eszköz tulajdonosát, és ha bármely más Azure AD-felhasználó bejelentkezik, többalkalmazásos kioszkot kap az Gépház App, Visszajelzési központ és Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="46a90-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="46a90-131">Ez a kioszk egy látogatói fiók másodlagos kioszkkonfigurációját is tartalmazza, amelybe bárki bejelentkezhet a zárolási képernyőn.</span><span class="sxs-lookup"><span data-stu-id="46a90-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="46a90-132">Amikor egy felhasználó bejelentkezik a látogatói fiókba, többalkalmazásos kioszkot kap, amely csak a Visszajelzési központ rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="46a90-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
