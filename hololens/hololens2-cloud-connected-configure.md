---
title: Telepítési útmutató – 2. HoloLens felhőhöz csatlakoztatott telepítés nagy méretekben a Remote Assist segítségével – Konfigurálás
description: Megtudhatja, hogyan állíthat be konfigurációkat a HoloLens eszközök nagy léptékű, felhőhöz csatlakoztatott hálózaton keresztüli regisztrálásához a Remote Assist segítségével.
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
ms.openlocfilehash: 8e6999157c6f5a396812df26f748c771581b61d63709918abb2ae45063810ef8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660560"
---
# <a name="configure---cloud-connected-guide"></a>Konfigurálás – Felhőhöz csatlakoztatott útmutató

Az útmutató ezen szakaszában azt&#39;, hogyan állíthatja be a bérlőhöz az automatikus regisztrációt, és hogyan alkalmazhat licenceket az Intune-hoz és a Remote Assisthöz is.

## <a name="azure-users-and-groups"></a>Azure-felhasználók és -csoportok

Az Azure és a bővítmény által az Intune felhasználók és csoportok használatával segít a konfigurációk és licencek hozzárendelésében. A központi telepítési folyamat érvényességének és az egyik felhasználóról a másikra történő remote assist hívásának&#39;két felhasználói fiókra lesz szüksége.

A licencek hozzárendelése céljából egyetlen felhasználói csoportot is lehet használni. Mindkét felhasználót ugyanoda a csoportba illesztheti, és az Intune-hoz és a Remote Assisthez licencet alkalmazhatunk a csoportra.

Ha még nem&#39;rendelkezik hozzáféréssel két Azure AD-fiókhoz egy felhasználói csoportban, használhatja; A következő rövid útmutatókat íme:

- [Felhasználó létrehozása](/mem/intune/fundamentals/quickstart-create-user)
- [Csoport létrehozása](/mem/intune/fundamentals/quickstart-create-group)
- [Felhasználók hozzáadása csoporthoz](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Létrehozott felhasználók hozzáadása csoport létrehozásához
- [Az Azure AD konfigurálása](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) az eszközök felhasználói csoportokhoz való csatlakozásának engedélyezése érdekében – Győződjön meg arról, hogy az új felhasználói csoport rendelkezik az eszközök Azure AD-beli regisztrálásához szükséges engedéllyel

## <a name="auto-enrollment-on-hololens-2"></a>Automatikus regisztráció a 2. HoloLens-

A zökkenőmentes és zökkenőmentes élmény érdekében a Azure Active Directory Join (AADJ) és az Automatikus regisztráció beállítása az Intune-ban HoloLens 2-es eszközökhöz a legjobb megoldás. Ez lehetővé teszi a felhasználók számára, hogy az OOBE során megnyissák a szervezeti bejelentkezési hitelesítő adatokat, és automatikusan regisztrálnak az Azure AD-ben, és regisztrálják az eszközt az MDM-ben.

A használatával [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)szolgáltatásokat, és navigálhat néhány oldalon, amíg ki nem választjuk a Próbaverzió Prémium lehetőséget. Azt is észreveheti, hogy az 1 prémium szintű Azure Active Directory a 2., az automatikus regisztráció P1-hez elegendő. Kiválaszthatja az Intune lehetőséget, kiválaszthatja az automatikus regisztráció felhasználói hatókörét, és kiválaszthatja a korábban létrehozott csoportot.

Részletes információkért és lépésekért olvassa el az Automatikus regisztráció engedélyezése az [Intune-ban útmutatót.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="application-licenses"></a>Alkalmazáslicencek

Az alkalmazáslicenc lehetővé teszi, hogy a felhasználó telepítse a vállalat által vásárolt alkalmazásokat, vagy frissítsen egy ingyenes próbaverzióról egy alkalmazás teljes verziójára. Az alkalmazáslicencek felhasználókra, felhasználói csoportokra vagy eszközcsoportokra is alkalmazhatók. A&#39;Remote Assist-licencekre lesz szüksége a szervezet felhasználói számára a Remote Assist használatára. Ebben az útmutatóban Remote Assist-licenceket rendelünk a fent létrehozott felhasználói csoporthoz az [Azure-felhasználók és -csoportok alatt.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

A licenckövetelmények eltérőek lehetnek attól függően, hogy a felhasználó egy eszközről fogja-e hívni a Remote Assist hívást, vagy távoli közreműködő lesz a Microsoft Teams. Alapértelmezés szerint a Remote Assist és Teams jelölőnégyzetek is meg vannak jelölve. Ebben az útmutatóban azt javasoljuk, hogy hagyja bejelölve az alapértelmezett jelölőnégyzeteket.

1. További információ a különböző [licencelési és termékkövetelményeket szerepkörenként.](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) A Remote Assist-licenceknek több típusa is létezik, ezért győződjön meg arról, hogy az igényeinek megfelelőt kell kapnia.
2. A&#39;szüksége lesz [a licencre.](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
3. [Alkalmazza a licenceket](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) a csoportra.

## <a name="next-step"></a>Következő lépés

> [!div class="nextstepaction"]
> [Felhőhöz csatlakoztatott üzemelő példány – Üzembe helyezés](hololens2-cloud-connected-deploy.md)