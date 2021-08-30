---
title: Üzembe helyezési útmutató – Vállalati csatlakoztatott HoloLens 2 Dynamics 365-útmutatók – Áttekintés
description: Ismerje meg, hogyan regisztrálható HoloLens 2 eszköz a Dynamics 365-útmutatók segítségével egy vállalati csatlakoztatott hálózaton.
keywords: HoloLens, felügyelet, vállalati csatlakoztatható, Dynamics 365-útmutatók, AAD, Azure AD, MDM, Mobile Eszközkezelés
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
ms.openlocfilehash: 541c1080d7f5fe9491d6cb11179ea98b160f687c
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190174"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Telepítési útmutató – Vállalati csatlakoztatott HoloLens 2 Dynamics 365-útmutatók – Áttekintés

Ez az útmutató segít az informatikai szakembereknek a Dynamics 365-útmutatókat (útmutatókat) Microsoft HoloLens 2-es eszközök tervezésében és üzembe helyezésében a szervezetben. Ez az útmutató kiváló a próba- és éles környezetek üzembe helyezéséhez, és hasonló a B forgatókönyvhöz: Üzembe helyezés a szervezet hálózati [útmutatója alapján.](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) A koncepció igazolásának tesztelése után ennek az útmutatónak a segítségével továbbléphat a HoloLens integrálására.

Ebben az útmutatóban azt ismertetjük, hogyan regisztrálhatóak az eszközök a meglévő eszközkezelésben, hogyan alkalmazhat licenceket szükség szerint, és hogyan ellenőrizheti, hogy a végfelhasználók képesek-e Dynamics 365-útmutatót üzemeltetni, valamint hogyan használhatnak egyéni üzletági alkalmazásokat az eszköz beállítása után. 

## <a name="prerequisites"></a>Előfeltételek

A következő infrastruktúrának már a helyén kell lennie:
- Wi-Fi
    - Belső vállalati hálózat, amely hozzáfér a belső erőforrásokhoz, és korlátozott hozzáféréssel rendelkezik az internethez vagy a felhőszolgáltatásokhoz
    - Eszközalapú tanúsítványalapú hitelesítés.
- Azure Active Directory (Azure AD) Csatlakozás az MDM automatikus regisztrációjával[(Azure AD P1 előfizetés szükséges)](/azure/active-directory/fundamentals/active-directory-whatis)
- MDM (Intune) által felügyelt
    - Egy vagy több alkalmazás MDM-en keresztül van telepítve.
- Network (Hálózat) 
    - Tanúsítványok (SCEP vagy PKCS)
    - Proxy konfigurálása
- A felhasználók a saját vállalati fiókjukkal (Azure AD) jelentkeznek be
    - Eszközönként egy vagy több felhasználó támogatott.
- Különböző szintű eszközzárolási konfigurációk alkalmazhatók adott esetekben, a teljesen nyitotttól az egyalkalmazásos kioszkig.

## <a name="guides-licensing-and-requirements"></a>[Útmutatók a licenceléshez és a követelményekhez](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Azure AD-fiók
- Dynamics 365-útmutatók alkalmazások PC-n és HoloLens
- Dynamics 365 Guides-előfizetés
    - Microsoft Dataverse (benne foglalt)
    - Power Apps (tartalmazza)
- Power BI Desktop
- Hálózati kapcsolat

[![Vállalati csatlakoztatott hálózati diagram, 1. fázis. ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Vállalati csatlakoztatott hálózati diagram, 2. fázis. ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>Ebben az útmutatóban a következőt fogja:
### <a name="prepare"></a>Előkészítés
> [!div class="checklist"]
>- [Ismerje meg a 2 eszköz HoloLens alapvető infrastruktúra-tudnivalókat.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Tudjon meg többet az Azure AD-ről, és állítson be egyet, ha még nincs ilyen.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Tudnivalók az identitáskezelésről és az Azure AD-fiókok legjobb beállításáról.](hololens2-corp-connected-prepare.md#identity-management)
>- [További információ az MDM-ről és az Intune beállításról, ha még nincs kész.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Ismerkedjen meg a tanúsítványalapú Wi-Fi-vel.](hololens2-corp-connected-prepare.md#certificates)
>- [Ismerkedjen meg a Proxyval.](hololens2-corp-connected-prepare.md#proxy)
>- [Az üzletági alkalmazások használatának 10.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [További információ az útmutatók szervezeti használatának módjairól.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Konfigurálás
> [!div class="checklist"]
>- [Felhasználók és csoportok létrehozása.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Az automatikus regisztráció beállítása.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [A vállalati tanúsítványok és Wi-Fi profilok beállítása Wi-Fi kapcsolatokhoz.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Üzletági (LOB) alkalmazáscsomagok feltöltése és hozzárendelése.](hololens2-corp-connected-configure.md#app-deployment)
>- [Dynamics 365-útmutatók beállítása.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [A kioszkmód konfigurálása (nem kötelező).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [A WDAC konfigurálása (nem kötelező).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Üzembe helyezés
> [!div class="checklist"]
>-  [A regisztráció ellenőrzése az eszközön és az MDM-en keresztül.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Ellenőrizze az Wi-Fi tanúsítványokat.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Ellenőrizze az LOB-alkalmazás telepítését.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Útmutatók érvényesítése a szerzői és üzemeltetési útmutatón keresztül.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Karbantartás
> [!div class="checklist"]
>- [Frissítse HoloLens 2. frissítést.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Útmutatók frissítése (áruházbeli alkalmazások).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [LOB-alkalmazások frissítése.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Fejlesztési terv.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Támogatási csomag készítés.](hololens2-corp-connected-maintain.md#support-plan)
>- [Eszközkezelési lehetőségek.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Következő lépés 
> [!div class="nextstepaction"]
> [Vállalati csatlakoztatott üzembe helyezés – Előkészítés](hololens2-corp-connected-prepare.md)
