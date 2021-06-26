---
title: A cloud connected HoloLens 2 with Remote Assist áttekintése
description: Megtudhatja, hogyan regisztrálható HoloLens 2-eszközök felhőhöz csatlakoztatott hálózaton keresztül a Dynamics 365 Remote Assist használatával.
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
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923533"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Üzembe helyezési útmutató – Felhőhöz csatlakoztatott HoloLens 2 Remote Assist segítségével – Áttekintés

Ez az útmutató segítséget nyújt az informatikai szakembereknek abban, hogy 2 Microsoft HoloLens a Remote Assist segítségével tervezze meg és telepítsék a szervezetüket. Ez modellként szolgál majd a különböző HoloLens 2-es esetekre vonatkozó, a cégnél a koncepció igazolására szolgáló üzembe helyezéshez. A beállítás hasonló az [A forgatókönyvhöz: Üzembe helyezés felhőalapú csatlakozású eszközökön.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a) 

Az útmutató során bemutatja, hogyan regisztrálhatóak az eszközök az eszközfelügyeletben, hogyan alkalmazhat licenceket szükség szerint, és hogyan ellenőrizheti, hogy a végfelhasználók képesek-e azonnal használni a Remote Assist eszközt az eszköz beállításakor. Ehhez át fogjuk látni az üzembe helyezéshez és a futtatáshoz szükséges fontos infrastruktúra-részleteket– a HoloLens 2-ben nagy léptékben való üzembe helyezést. Ebben az útmutatóban nem alkalmazunk más eszközkorlátozásokat vagy konfigurációkat, azonban javasoljuk, hogy a befejezés után ismerkedje meg ezeket a lehetőségeket.

## <a name="prerequisites"></a>Előfeltételek

A HoloLens 2 üzembe helyezéséhez a következő infrastruktúrát kell üzembe helyezni. Ha nem, az Azure és az Intune beállítását ez az útmutató tartalmazza:

- Wi-Fi
    - A hálózatok általában nyitva vannak az internet és a felhőszolgáltatások számára
- Azure Active Directory (Azure AD) Csatlakozás az MDM automatikus regisztrációjával[(Azure AD P1 előfizetés](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) szükséges)
- MDM (Intune) által felügyelt
    - Egy vagy több alkalmazás MDM-en keresztül van telepítve.
- A felhasználók a saját vállalati fiókjukkal (Azure AD) jelentkeznek be
    - Eszközönként egy vagy több felhasználó támogatott.

:::image type="content" alt-text="Felhőhöz csatlakoztatott forgatókönyv" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Tudnivalók a Remote Assist szolgáltatásról

A Remote Assist lehetővé teszi az együttműködésen alapuló karbantartást és javítást, a távvizsgálatot, valamint a tudás megosztását és betanítását. Ha különböző szerepkörökben és helyeken található személyeket kapcsol össze, a Remote Assist segítségével a technikusok egy távoli közreműködővel is csatlakozhatnak a Microsoft Teamsben. A videók, képernyőképek és jegyzetek kombinálása valós időben oldják meg a problémákat, még akkor is,&#39;nem ugyanazon a helyen vannak. A távoli közreműködők referenciaképeket, sémákat és egyéb hasznos információkat szúrnak be a technikusok&#39;fizikai tárhelyén, hogy hivatkozni tudjanak a sémára, miközben fej-felfelé és kéz nélkül dolgoznak a HoloLensen.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist – licencelés és követelmények

- Azure AD-fiók (az előfizetés megvásárlásához és a licencek hozzárendeléséhez szükséges)
- [Remote Assist-előfizetés](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (vagy [Remote Assist próbaverzió)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist-felhasználó

- Remote Assist-licenc
- Hálózati kapcsolat

#### <a name="microsoft-teams-user"></a>Microsoft Teams-felhasználó

- Microsoft Teams vagy [Teams Freemium](https://products.office.com/microsoft-teams/free).
- Hálózati kapcsolat

Ha ezt a [](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)több-bérlős forgatókönyvet tervezi, előfordulhat, hogy információ-korlátok licencre van szüksége. Ebből [a cikkből megállapíthatja,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) hogy szükség van-e information barrier licencre.

## <a name="in-this-guide-you-will"></a>Ebben az útmutatóban a következőt fogja:

Készítsen:

> [!div class="checklist"]
> - [Ismerje meg a HoloLens 2-eszközök infrastruktúrájának alapvető tudnivalókat.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Tudjon meg többet az Azure AD-ről, és állítson be egyet,&#39;még nem használja.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Tudnivalók az identitáskezelésről és az Azure AD-fiókok legjobb beállításáról.](hololens2-cloud-connected-prepare.md#identity-management)
> - [További információ az MDM-ről és az Intune beállításról, ha&#39;még nem készült el.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Ismerje meg a Remote Assist hálózati követelményeit.](hololens2-cloud-connected-prepare.md#network)
> - [Választható lehetőség: VPN a szervezeti erőforrásokhoz való csatlakozáshoz](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Konfigurálja:

> [!div class="checklist"]
> - [Felhasználók és csoportok létrehozása.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Automatikus regisztráció beállítása az Azure AD-ban.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Az alkalmazáslicencek hozzárendelése.](hololens2-cloud-connected-configure.md#application-licenses)

Üzembe helyezés:

> [!div class="checklist"]
> - [A HoloLens 2 beállítása és a regisztráció ellenőrzése.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Ellenőrizze, hogy tud-e Remote Assist-hívást hívni.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Fenntartani:

> [!div class="checklist"]
> - [A Remote Assist frissítése a Microsoft Store használatával.](hololens2-cloud-connected-maintain.md#updates)
> - [Támogatási csomag készítés.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Fejlesztési terv.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Következő lépés

> [!div class="nextstepaction"]
> [Felhőhöz csatlakoztatott üzemelő példány – Előkészítés](hololens2-cloud-connected-prepare.md)

