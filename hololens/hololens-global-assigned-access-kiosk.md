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
# <a name="global-assigned-access--kiosk"></a>Globális hozzárendelt hozzáférés – Teljes kioszk

Ez a funkció HoloLens 2-es eszközt konfigurál több alkalmazás kioszkmódhoz, amely rendszerszinten alkalmazható, nem rendelkezik affinitással semmilyen identitással a rendszeren, és mindenkire érvényes, aki bejelentkezik az eszközre.

> [!NOTE]
> Ez a funkció jelenleg csak belső Windows érhető el. Ha szeretné kipróbálni ezt a funkciót, mielőtt az általánosan elérhető lenne [](hololens-insider.md) a HoloLens-kiadásokban, olvassa el a Windows Insider-buildeket.

## <a name="how-to-use-global-assigned-access-in-intune"></a>Hogyan használható a globális hozzárendelt hozzáférés az Intune-ban?

> [!NOTE]
> Vegye figyelembe a "<!-" jelű területeket. Ezekhez a területekhez a beállításoknak megfelelően kell módosításokat tenni.

1. Hozzon létre egy egyéni OMA URI eszközkonfigurációs profilt az alábbiak szerint, és alkalmazza HoloLens eszközcsoportra:

    URI-érték: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Globális hozzárendelt hozzáférés OMA-URI az Intune-ban](images/global-assigned-access-omauri.png)

2. Az értékhez frissítse és illessze be a következő tartalmat:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Hogyan használható a globális hozzárendelt hozzáférés Windows Configuration Designerben?

1. Frissítse és mentse a fent említett XML-blobot XML-fájlként. 

2. Kövesse a Kiépítési csomag használata egyalkalmazásos vagy többalkalmazásos [kioszk](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)beállítását, különösen a "Prov. package, step 2 – Add the kioszk configuration XML file to a provisioning package" (csomag, 2. lépés – A kioszkkonfigurációs XML-fájl hozzáadása egy kiépítési csomaghoz) és tekintse meg az előző lépésben mentett XML-fájlt.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>Létrehozhatok olyan konfigurációt, amelyben a globális mindenkire vonatkozik, és külön konfiguráció vonatkozik 1 Azure AD-fiókra vagy Azure AD-csoportra? 

Igen, tekintse meg az alábbi XML-blob példáját. A globális hozzárendelt hozzáférési profil akkor lesz alkalmazva a HoloLens amikor a bejelentkezett felhasználóhoz nem talál egy adott profilt, így ez a bejelentkezett felhasználó alapértelmezett kioszkmódú konfigurációja.
Példa a használni szükséges XML-blobra:

> [!NOTE]
> Vegye figyelembe a kiemelt területeket, amelyek a jelekkel vannak `<!-` jelölve. Ezekhez a területekhez a beállításoknak megfelelően kell módosításokat tenni.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>Eszköztulajdonosok kizárása a globális hozzárendelt hozzáférési profilból

Ez a funkció lehetővé teszi, hogy a felhasználók, akik a vállalaton[](security-adminless-os.md)"Eszköztulajdonosnak" minősülnek HoloLens ki lesznek zárva a globális hozzárendelt hozzáférésből. A funkció előnyeinek kihasználása érdekében az XML-blobban többalkalmazásos kioszkkonfiguráció esetén győződjön meg arról, hogy a kiemelt sorok fel vannak adva:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>További globális hozzáférési példák

Ez egy példa globális hozzáférésű kioszkra, amely azt jelenti, hogy amikor egy felhasználó bejelentkezik, többalkalmazásos kioszkot kap az Gépház App, Visszajelzési központ és Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Ez a példa egy globálisan hozzárendelt hozzáférésű kioszk, amely kizárja az eszköz tulajdonosát, és ha bármely más Azure AD-felhasználó bejelentkezik, többalkalmazásos kioszkot kap az Gépház App, Visszajelzési központ és Microsoft Edge. Ez a kioszk egy látogatói fiók másodlagos kioszkkonfigurációját is tartalmazza, amelybe bárki bejelentkezhet a zárolási képernyőn. Amikor egy felhasználó bejelentkezik a látogatói fiókba, többalkalmazásos kioszkot kap, amely csak a Visszajelzési központ rendelkezik.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
