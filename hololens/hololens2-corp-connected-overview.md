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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032691"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Telepítési útmutató – Vállalati csatlakoztatott HoloLens 2 Dynamics 365-útmutatók – Áttekintés

Ez az útmutató segít az informatikai szakembereknek a Dynamics 365-útmutatók (útmutatók) segítségével Microsoft HoloLens 2 eszköz tervezésében és üzembe helyezésében a szervezetben. Ez az útmutató nagyszerű a próba- és éles környezetek üzembe helyezéséhez, és hasonló a B forgatókönyvhöz: Üzembe helyezés a szervezet hálózati [útmutatója alapján.](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) A koncepció igazolásának tesztelése után ennek az útmutatónak a segítségével integrálja a HoloLens a szervezetbe.

Ebben az útmutatóban azt ismertetjük, hogyan regisztrálhatóak az eszközök a meglévő eszközkezelésben, hogyan alkalmazhat licenceket szükség szerint, és hogyan ellenőrizheti, hogy a végfelhasználók képesek-e Dynamics 365-útmutatót üzemeltetni, valamint hogyan használhatnak egyéni üzletági alkalmazásokat az eszköz beállítása után. 

## <a name="prerequisites"></a>Előfeltételek

A következő infrastruktúrának már a helyén kell lennie:
- Wi-Fi
    - Belső vállalati hálózat, amely hozzáfér a belső erőforrásokhoz, és korlátozott hozzáféréssel rendelkezik az internethez vagy a felhőszolgáltatásokhoz
    - Eszközalapú tanúsítványalapú hitelesítés.
- Azure Active Directory (Azure AD) Csatlakozás az MDM automatikus regisztrációjával[(Azure AD P1 előfizetés](/azure/active-directory/fundamentals/active-directory-whatis) szükséges)
- MDM (Intune) által felügyelt
    - Egy vagy több alkalmazás MDM-en keresztül van telepítve.
- Network (Hálózat) 
    - Tanúsítványok (SCEP vagy PKCS)
    - Proxy konfigurálása
- A felhasználók a saját vállalati fiókjukkal (Azure AD) jelentkeznek be
    - Eszközönként egy vagy több felhasználó támogatott.
- Különböző szintű eszközzárolási konfigurációk alkalmazhatók adott esetekben, a Teljesen nyitotttól az Egyalkalmazásos kioszkig.

## <a name="guides-licensing-and-requirements"></a>[Útmutatók a licenceléshez és a követelményekhez](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Azure AD-fiók
- Dynamics 365-útmutatók alkalmazások PC-n és HoloLens
- Dynamics 365-útmutatók előfizetés
    - Microsoft Dataverse (benne)
    - Power Apps (benne)
- Power BI Desktop
- Hálózati kapcsolat

[![Vállalati csatlakoztatott hálózat diagramja, 1. fázis. ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Vállalati csatlakoztatott hálózat diagramja, 2. fázis. ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>Ebben az útmutatóban a következőt fogja:
### <a name="prepare"></a>Előkészítés
> [!div class="checklist"]
>- [Ismerje meg a 2 eszköz HoloLens alapvető infrastruktúráját.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Tudjon meg többet az Azure AD-ről, és állítson be egyet, ha még nincs ilyen.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Tudnivalók az identitáskezelésről és az Azure AD-fiókok legjobb beállításáról.](hololens2-corp-connected-prepare.md#identity-management)
>- [További információ az MDM-ről és az Intune beállításról, ha még nincs kész.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Ismerkedjen meg a tanúsítványalapú Wi-Fi-vel.](hololens2-corp-connected-prepare.md#certificates)
>- [Ismerkedjen meg a Proxyval.](hololens2-corp-connected-prepare.md#proxy)
>- [Az üzletági alkalmazások használatának a saját maga által használt mottója.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [További információ a céges útmutatók használatának módjairól.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Konfigurálás
> [!div class="checklist"]
>- [Felhasználók és csoportok létrehozása.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Az automatikus regisztráció beállítása.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Tanúsítványok és profilok beállítása Wi-Fi vállalati kapcsolatokhoz Wi-Fi profilokhoz.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Üzletági (LOB) alkalmazáscsomagok feltöltése és hozzárendelése.](hololens2-corp-connected-configure.md#app-deployment)
>- [Dynamics 365-útmutatók beállítása.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [A kioszkmód konfigurálása (nem kötelező).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [A WDAC konfigurálása (nem kötelező).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Üzembe helyezés
> [!div class="checklist"]
>-  [Az eszköz és az MDM segítségével történő regisztráció ellenőrzése.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Ellenőrizze Wi-Fi tanúsítványokat.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Ellenőrizze az LOB-alkalmazás telepítését.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Útmutatók érvényesítése szerzői és üzemeltetési útmutatóval.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Karbantartás
> [!div class="checklist"]
>- [Frissítse HoloLens 2. frissítést.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Útmutatók (áruházbeli alkalmazások) frissítése.](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [LOB-alkalmazások frissítése.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Fejlesztési terv.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Támogatási csomag készítés.](hololens2-corp-connected-maintain.md#support-plan)
>- [Eszközkezelési lehetőségek.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Következő lépés 
> [!div class="nextstepaction"]
> [Vállalati csatlakoztatott üzemelő példány – Előkészítés](hololens2-corp-connected-prepare.md)
