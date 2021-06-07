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
# <a name="global-assigned-access--kiosk"></a>Globális hozzáférés – Teljes kioszk

Ez a funkció a HoloLens 2-eszközt több alkalmazásos kioszkmódhoz konfigurálja, amely rendszerszinten alkalmazható, nem rendelkezik affinitással semmilyen identitással a rendszeren, és mindenkire érvényes, aki bejelentkezik az eszközre.

> [!NOTE]
> Ez a funkció jelenleg csak a Windows Insider érhető el. Ha ki szeretné próbálni ezt a funkciót, mielőtt az általánosan elérhető [](hololens-insider.md) lenne a HoloLens-kiadásokban, olvassa el a Windows Insider buildeket.

## <a name="how-to-use-global-assigned-access-in-intune"></a>Hogyan használható a globális hozzárendelt hozzáférés az Intune-ban?

> [!NOTE]
> Vegye figyelembe a "<!-" jelölésű területeket. Ezekhez a területekhez módosítania kell a beállításait.

1. Hozzon létre egy egyéni OMA URI eszközkonfigurációs profilt az alábbiak szerint, és alkalmazza a HoloLens-eszközcsoportra:

    URI-érték: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Globálisan hozzárendelt hozzáférés OMA-URI az Intune-ban](images/global-assigned-access-omauri.png)

2. Az értékhez frissítse és illessze be a következő tartalmat:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Hogyan használható a globális hozzáférés a Windows Configuration Designerben?

1. Frissítse és mentse a fent említett XML-blobot XML-fájlként. 

2. Kövesse a Kiépítési csomag használata egyalkalmazásos vagy többalkalmazásos [kioszk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)beállítását, különösen a "Prov. package, step 2 – Add the kioszk configuration XML file to a provisioning package" (csomag, 2. lépés– A kioszkkonfigurációs XML-fájl hozzáadása egy kiépítési csomaghoz) és tekintse meg az előző lépésben mentett XML-fájlt.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>Létrehozhatok olyan konfigurációt, amelyben a globális mindenkire vonatkozik, és külön konfiguráció vonatkozik 1 Azure AD-fiókra vagy Azure AD-csoportra? 

Igen, tekintse meg az alábbi XML-blob példáját. A globálisan hozzárendelt hozzáférési profil akkor lesz alkalmazva a HoloLensen, ha nem található a bejelentkezett felhasználóhoz megadott profil, így ez a bejelentkezett felhasználó alapértelmezett kioszkmód-konfigurációja.
Példa a használni használt XML-blobra:

> [!NOTE]
> Vegye figyelembe a kiemelt területeket, amelyek a jelekkel vannak `<!-` megjelölve. Ezekhez a területekhez módosítania kell a beállításait.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>Eszköztulajdonosok kizárása a globális hozzárendelt hozzáférési profilból

Ez a funkció lehetővé teszi, hogy a HoloLensen[](security-adminless-os.md)"Eszköztulajdonosnak" minősülő felhasználó ki legyen zárva a globális hozzárendelt hozzáférésből. A funkció előnyeinek kihasználása érdekében az XML-blobban többalkalmazásos kioszkkonfigurációhoz ügyeljen arra, hogy a kiemelt sorok hozzáadva is hozzáadva:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>További globális hozzáférési példák

Ez egy példa a globális hozzáférésű kioszkra, amely azt jelenti, hogy amikor egy felhasználó bejelentkezik, többalkalmazásos kioszkot kap a Beállítások alkalmazással, a Visszajelzési központ és a Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Ez a példa egy globálisan hozzárendelt hozzáférésű kioszk, amely kizárja az eszköz tulajdonosát, és amikor bármely más Azure AD-felhasználó bejelentkezik, többalkalmazásos kioszkot kap a Beállítások alkalmazással, a Visszajelzési központ és a Microsoft Edge. Ez a kioszk egy látogatói fiók másodlagos kioszkkonfigurációját is tartalmazza, amelybe bárki bejelentkezhet a zárolási képernyőn. Amikor egy felhasználó bejelentkezik a látogatói fiókba, többalkalmazásos kioszkot kap, amely csak a Visszajelzési központ rendelkezik.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
