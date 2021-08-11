---
title: Globális hozzárendelt hozzáférés
description: 'Első lépések: OMA-URI használata a globális hozzáférésű kioszkok számára az Intune-nal és a Windows konfigurációtervezővel.'
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
ms.openlocfilehash: d36192e7f65f7fe2ccc7ff8699484a19b3d5d3a7ccab0167d2dbdcaf64bb5880
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664041"
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

2. Értékként frissítse és illessze be a következő tartalmat:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Hogyan használható a globális hozzárendelt hozzáférés a Windows Configuration Designerben?

1. Frissítse és mentse a fent említett XML-blobot XML-fájlként. 

2. Kövesse a Kiépítési csomag használata egyalkalmazásos vagy többalkalmazásos [kioszk](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)beállítását, különösen a "Prov. package, step 2 – Add the kioszk configuration XML file to a provisioning package" (csomag, 2. lépés – A kioszkkonfigurációs XML-fájl hozzáadása egy kiépítési csomaghoz) és tekintse meg az előző lépésben mentett XML-fájlt.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>Létrehozhatok olyan konfigurációt, amelyben a globális mindenkire vonatkozik, és külön konfiguráció vonatkozik 1 Azure AD-fiókra vagy Azure AD-csoportra? 

Igen, tekintse meg az alábbi XML-blob példáját. A globális hozzárendelt hozzáférési profil akkor lesz alkalmazva a HoloLens amikor a bejelentkezett felhasználóhoz nem talál egy adott profilt, így ez a bejelentkezett felhasználó alapértelmezett kioszkmódú konfigurációja.
Példa a használni szükséges XML-blobra:

> [!NOTE]
> Vegye figyelembe a kiemelt területeket, amelyek a jelekkel vannak `<!-` jelölve. Ezekhez a területekhez a beállításoknak megfelelően kell módosításokat tenni.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>Eszköztulajdonosok kizárása a globális hozzárendelt hozzáférési profilból

Ez a funkció lehetővé teszi, hogy a globális hozzárendelt hozzáférésből ki legyen zárva a HoloLens felhasználó, aki az "Eszköz tulajdonosa" a vállalaton.[](security-adminless-os.md) A funkció előnyeinek kihasználása érdekében az XML-blobban többalkalmazásos kioszkkonfiguráció esetén győződjön meg arról, hogy a kiemelt sorok hozzá vannak adva:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>További globális hozzáférési példák

Ez egy példa globális hozzáférésű kioszkra, amely azt jelenti, hogy amikor egy felhasználó bejelentkezik, többalkalmazásos kioszkot kap az Gépház App, Visszajelzési központ és Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Ez a példa egy globálisan hozzárendelt hozzáférésű kioszk, amely kizárja az eszköz tulajdonosát, és ha bármely más Azure AD-felhasználó bejelentkezik, többalkalmazásos kioszkot kap az Gépház App, Visszajelzési központ és Microsoft Edge. Ez a kioszk egy látogatói fiók másodlagos kioszkkonfigurációját is tartalmazza, amelybe bárki bejelentkezhet a zárolási képernyőn. Amikor egy felhasználó bejelentkezik a látogatói fiókba, többalkalmazásos kioszkot kap, amely csak a Visszajelzési központ rendelkezik.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
