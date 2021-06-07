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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378010"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Üzembe helyezési útmutató – Felhőhöz csatlakoztatott HoloLens 2 Remote Assist segítségével – Áttekintés

Ez az útmutató segítséget nyújt az informatikai szakembereknek Microsoft HoloLens 2-es eszköz tervezésében és üzembe helyezésében azzal a céllal, hogy a Dynamics 365 Remote Assist használatra kész, felhőbeli kapcsolatot nyújt a szervezettel. Ne feledje, hogy ez modellként szolgál majd a különböző HoloLens 2-es esetekre vonatkozó, a cégnél a koncepció igazolására szolgáló üzembe helyezéshez.

Az útmutató során bemutatja, hogyan regisztrálhatóak az eszközök az eszközfelügyeletben, hogyan alkalmazhat licenceket szükség szerint, és hogyan ellenőrizheti, hogy a végfelhasználók képesek-e azonnal használni a Remote Assist eszközt az eszköz beállításakor. Ehhez az üzembe helyezéshez és a futtatáshoz szükséges fontos infrastruktúra-részleteket fogjuk átfedni – a HoloLens 2-ben nagy léptékben való üzembe helyezést.

[![Felhőhöz csatlakoztatott forgatókönyv ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)
## <a name="in-this-guide"></a>Ebben az útmutatóban

Ennek az útmutatónak az a konkrét célja, hogy a Remote Assistet a szervezeten belül a HoloLens-eszközökön is bevezesse. A cél eléréséhez szükséges szükséges szükségleteket is át fogjuk fedni. Annak érdekében, hogy továbbra is erre a célra összpontosítson, bizonyos előkészítési és konfigurációk előre ki lesznek választva az üzembe helyezésre való optimalizálás vagy a konfigurálni szükséges elemek csökkentése érdekében. Értesülni fog ezekről a lehetőségekről, és az üzleti igényeinek megfelelően testre szabhatja az üzemelő példányát.

Ez a beállítás hasonló az [A forgatókönyvhöz:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)Üzembe helyezés felhőalapú csatlakozású eszközökön , amely számos koncepció igazolási üzembe helyezéshez jó választás, többek között a következőkhöz:

- Wi-Fi hálózatok általában teljesen nyitva vannak az internet és a felhőszolgáltatások számára
- Azure AD-csatlakozás automatikus MDM-regisztrációval – MDM (Intune) által felügyelt
- A felhasználók a saját vállalati fiókjukkal (Azure AD) jelentkeznek be
  - Egy vagy több felhasználó támogatott eszközönként
- Az eszköz zárolási konfigurációjának különböző szintjei adott esetekben alkalmazhatók, a Teljesen nyitotttól az egyalkalmazásos kioszkig



Ebben az útmutatóban nem alkalmazunk más eszközkorlátozásokat vagy konfigurációkat, azonban javasoljuk, hogy a befejezés után ismerkedje meg ezeket a lehetőségeket.

## <a name="learn-about-remote-assist"></a>Tudnivalók a Remote Assist szolgáltatásról

A Remote Assist lehetővé teszi az együttműködésen alapuló karbantartást és javítást, a távvizsgálatot, valamint a tudás megosztását és betanítását. Ha különböző szerepkörökben és helyeken található személyeket kapcsol össze, a Remote Assist segítségével a technikusok a Microsoft Teams távoli közreműködőivel is csatlakozhatnak. A videók, képernyőképek és jegyzetek kombinálása valós időben oldják meg a problémákat, még akkor is,&#39;nem ugyanazon a helyen vannak. A távoli közreműködők referenciaképeket, sémákat és egyéb hasznos információkat szúrnak be a technikusok&#39;fizikai tárhelyén, hogy hivatkozni tudjanak a sémára, miközben fej-felfelé és kéz nélkül dolgoznak a HoloLensen.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>Ebben az útmutatóban a következőt fogja:

Készítsen:

> [!div class="checklist"]
> - [Ismerje meg a HoloLens 2-eszközök infrastruktúrájának alapvető tudnivalókat.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Tudjon meg többet az Azure AD-ről, és állítson be egyet,&#39;még nem használja.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Tudnivalók az identitáskezelésről és az Azure AD-fiókok legjobb beállításáról.](hololens2-cloud-connected-prepare.md#identity-management)
> - [További információ az MDM-ről és az Intune beállításról, ha&#39;még nem készült el.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Ismerje meg a Remote Assist hálózati követelményeit.](hololens2-cloud-connected-prepare.md#network)
> - [Választható lehetőség: VPN a szervezeti erőforrásokhoz való csatlakozáshoz](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

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

