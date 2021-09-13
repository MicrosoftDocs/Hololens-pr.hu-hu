---
title: Telepítési útmutató – HoloLens 2. felhőhöz nagy léptékű üzembe helyezés a Remote Assist segítségével – Konfigurálás
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032747"
---
# <a name="configure---cloud-connected-guide"></a>Konfigurálás – Felhőhöz csatlakoztatott útmutató

Az útmutató ezen szakaszában azt&#39;, hogyan állíthatja be a bérlőhöz az automatikus regisztrációt, és hogyan alkalmazhat licenceket az Intune-hoz és a Remote Assisthöz is.

## <a name="azure-users-and-groups"></a>Azure-felhasználók és -csoportok

Az Azure és a bővítmény által használt Intune a felhasználók és csoportok segítségével segít a konfigurációk és licencek hozzárendelésében. A központi telepítési folyamat érvényességének és a Remote Assist hívásának egyik felhasználóról a másikra való építéséhez két&#39;lesz szüksége.

A licencek hozzárendelése céljából egyetlen felhasználói csoportot is lehet használni. Mindkét felhasználót ugyanhoz a csoporthoz illesztheti, és az Intune-hoz és a Remote Assisthez licencet alkalmazhat erre a csoportra.

Ha még&#39;rendelkezik hozzáféréssel két Azure AD-fiókhoz egy felhasználói csoportban, akkor használhatja; A következő rövid útmutatókat íme a következő lépésekhez:

- [Felhasználó létrehozása](/mem/intune/fundamentals/quickstart-create-user)
- [Csoport létrehozása](/mem/intune/fundamentals/quickstart-create-group)
- [Felhasználók hozzáadása csoporthoz](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Létrehozott felhasználók hozzáadása csoport létrehozásához
- [Az Azure AD konfigurálása arra, hogy a](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) felhasználói csoportok eszközöket csatlakozzanak – Győződjön meg arról, hogy az új felhasználói csoport rendelkezik az eszközök Azure AD-beli regisztrálásához szükséges engedéllyel

## <a name="auto-enrollment-on-hololens-2"></a>Automatikus regisztráció a 2 HoloLens n

A zökkenőmentes és zökkenőmentes felhasználói élmény érdekében az Azure Active Directory Join (AADJ) és az Automatikus regisztráció beállítása az Intune-ban HoloLens 2-es eszközökhöz a megoldás. Ez lehetővé teszi a felhasználók számára, hogy az OOBE során megnyissák a szervezet bejelentkezési hitelesítő adatait, és automatikusan regisztrálnak az Azure AD-ben, és regisztrálják az eszközt az MDM-ben.

A [(Microsoft Endpoint Manager)](https://endpoint.microsoft.com/#home)használatával kiválaszthatja a szolgáltatásokat, és navigálhat néhány oldalon, amíg ki nem Prémium a próbaverziót. Azt is észreveheti, hogy prémium szintű Azure Active Directory 1-es és 2-es, az Automatikus regisztráció P1 elegendő. Kiválaszthatja az Intune-t, kiválaszthatja az automatikus regisztráció felhasználói hatókörét, és kiválaszthatja a korábban létrehozott csoportot.

Részletes információkért és lépésekért olvassa el az Automatikus regisztráció engedélyezése az [Intune-hoz útmutatót.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="application-licenses"></a>Alkalmazáslicencek

Az alkalmazáslicenc lehetővé teszi, hogy a felhasználó telepítse a vállalat által vásárolt alkalmazásokat, vagy frissítsen az ingyenes próbaverzióról az alkalmazás teljes verziójára. Az alkalmazáslicencek felhasználókra, felhasználói csoportokra vagy eszközcsoportokra alkalmazhatók. A&#39;Remote Assist-licencekre lesz szüksége a szervezet felhasználói számára a Remote Assist használatára. Ebben az útmutatóban Remote Assist-licenceket rendelünk a fent létrehozott felhasználói csoporthoz az [Azure-felhasználók és -csoportok csoportban.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

A licenckövetelmények eltérőek lehetnek attól függően, hogy a felhasználó egy eszközről fogja-e hívni a Remote Assist hívást, vagy egy távoli közreműködő lesz a Microsoft Teams. Alapértelmezés szerint a Remote Assist és Teams jelölőnégyzetek is meg vannak jelölve. Ebben az útmutatóban azt javasoljuk, hogy hagyja bejelölve az alapértelmezett jelölőnégyzeteket.

1. További információ a különböző licencelési és [termékkövetelményeket szerepkörenként.](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) A Remote Assist-licenceknek több típusa is létezik, ezért mindenképpen az igényeinek megfelelő licenceket szerezze be.
2. A&#39;szüksége lesz [a licencre.](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
3. [Alkalmazza a licenceket](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) a csoportra.

## <a name="next-step"></a>Következő lépés

> [!div class="nextstepaction"]
> [Felhőhöz csatlakoztatott üzembe helyezés – Üzembe helyezés](hololens2-cloud-connected-deploy.md)