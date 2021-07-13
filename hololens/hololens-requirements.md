---
title: Gyakori üzembe helyezési forgatókönyvek
description: További információ a vállalati környezetek üzembe helyezéséről és HoloLens, beleértve az infrastruktúrát, a Azure Active Directory és a mobileszköz-kezelésről.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 72b9e61c52d6f4f08cf5a29baf7b01c29fae7489
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635466"
---
# <a name="common-deployment-scenarios"></a>Gyakori üzembe helyezési forgatókönyvek

## <a name="overview"></a>Áttekintés

Ez az oldal magas szintű architektúra-áttekintést nyújt három olyan gyakori forgatókönyvhöz, amelyek 2 Microsoft HoloLens vállalati eszköz üzembe helyezésekor és kezelésekor.

Az eszközök kezelését és a szervezeti erőforrásokhoz való hozzáférést gyakran nagyrészt a már rendelkezésre álló tényezők határozzák meg. A meglévő infrastruktúra alapján kérjük, tekintse át az általános eszközkezelési stílust (MDM) a következő forgatókönyvekben, majd olvassa el a Planning [HoloLens 2 deployments in a commercial](hololens-core-components.md) environment (Az HoloLens 2. üzemelő példányok tervezése kereskedelmi környezetben) útmutatót annak meghatározásához, hogy melyik forgatókönyv illik az igényeihez. Az üzembe helyezés során három kapcsolódó útmutató is rendelkezésre áll.


 1. [Útmutató a felhőhöz csatlakoztatott környezet üzembe helyezéséhez](hololens2-cloud-connected-overview.md)
     1. [Felhőhöz csatlakoztatott környezet (külső ügyfelek) üzembe helyezési útmutatója](hololens2-deployment-guide.md)
 1. [Vállalati hálózat üzembe helyezési útmutatója](hololens2-corp-connected-overview.md)
 1. [Offline biztonságos környezet üzembe helyezési útmutatója](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>A forgatókönyv: Üzembe helyezés felhőhöz csatlakoztatott eszközökön

Ez a forgatókönyv hasonló a felügyelt mobileszközök vállalaton belüli üzembe helyezéséhez. HoloLens 2. része elsősorban vállalati hálózaton kívülre készült környezetekben való használatra van telepítve. A vállalati erőforrások nem érhetők el, vagy VPN-en keresztül korlátozhatóak. 
 * Alapszintű gyakori konfigurációk
   * Wi-Fi hálózatok általában teljesen nyitva vannak az internet és a felhőszolgáltatások számára.
   * Azure AD Join with Mobile Eszközkezelés (MDM) Auto Enrollment – MDM (Intune) Managed
   * A felhasználók a saját vállalati fiókjukkal (Azure AD) jelentkeznek be
     * Egy vagy több felhasználó támogatott eszközönként
   * Az eszközzárolási konfigurációk különböző szintjei adott esetekben vannak alkalmazva, a Teljes megnyitástól az Egyalkalmazásos kioszkig.
   * Egy vagy több alkalmazás MDM-en keresztül van telepítve

* Gyakori kihívások
   * A 2. HoloLens MDM-konfigurációk meghatározása a forgatókönyv követelményei alapján.

[![Diagram a forgatókönyvről ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

A megfelelő, felhőhöz csatlakoztatott útmutató bemutatja, hogyan regisztrálható HoloLens 2. lépés az eszköz felügyeletére, hogyan alkalmazhat licenceket szükség szerint, és hogyan ellenőrizheti, hogy a végfelhasználók az eszköz beállításakor azonnal tudják-e használni a Remote Assistet. A Külső ügyfelek útmutató segítségével rövid vagy hosszú távú külső használatra telepíthet eszközöket távoli helyekre.

> [!div class="nextstepaction"]
> [Útmutató a felhőhöz csatlakoztatott környezet üzembe helyezéséhez](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Felhőhöz csatlakoztatott környezet (külső ügyfelek) üzembe helyezési útmutatója](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>B forgatókönyv: Üzembe helyezés a szervezet hálózatán belül

Ez a forgatókönyv megegyezik a legtöbb számítógép klasszikus Windows 10 esetében. HoloLens 2. pont elsősorban a vállalati hálózaton való használatra van telepítve, és belső vállalati erőforrásokhoz fér hozzá. Az internetes és a felhőszolgáltatások korlátozottak lehetnek. 

 * Alapszintű gyakori konfigurációk
   * Wi-Fi egy belső vállalati hálózat, amely hozzáfér a belső erőforrásokhoz, és korlátozott hozzáféréssel rendelkezik az internethez vagy a felhőszolgáltatásokhoz.
   * Azure AD-csatlakozás MDM automatikus regisztrációval
   * MDM (Intune) által felügyelt
   * A felhasználók a saját vállalati fiókjukkal (Azure AD) jelentkeznek be
     * Egy vagy több felhasználó támogatott eszközönként
   * Az eszközzárolási konfigurációk különböző szintjei adott esetekben vannak alkalmazva, a Teljes megnyitástól az Egyalkalmazásos kioszkig.
   * Egy vagy több alkalmazás MDM-en keresztül van telepítve

 * Gyakori kihívások
   * HoloLens 2. nem támogatja a helyszíni AD-csatlakozást vagy az SCCM-et. Csak az Azure AD-hez csatlakozzon az MDM-hez. Ebben a forgatókönyvben számos vállalat továbbra is üzembe helyez Windows 10 számítógépeket helyszíni AD-hez csatlakozott, az System Center Configuration Manager (SCCM) által felügyelt eszközökként, és előfordulhat, hogy nem telepítettek/konfiguráltak belső Windows 10-eszközök felhőalapú MDM-megoldásokon keresztüli kezelésére szolgáló infrastruktúrát.
   * Mivel HoloLens 2. verzió egy felhőalapú eszköz, nagy mértékben támaszkodik az internethez és a felhőhöz kapcsolódó szolgáltatásokra a felhasználói hitelesítéshez, az operációs rendszer frissítéséhez, az MDM-felügyelethez és így tovább. Vállalati hálózathoz való csatlakozáskor a proxy-/tűzfalszabályokat valószínűleg úgy kell módosítani, hogy HoloLens 2. vagy a rajta futó alkalmazások hozzáférését engedélyezték.
   * A Wi-Fi kapcsolat általában tanúsítványokat igényel az eszköz vagy a felhasználó hálózaton való hitelesítéséhez. A tanúsítványoknak az MDM-Windows 10 keresztüli telepítéséhez szükséges infrastruktúra vagy beállítások konfigurálása kihívást jelenthet.

[![A B1 forgatókönyv diagramja ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![A B2 forgatókönyv ábrája ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

A megfelelő vállalati hálózati útmutató útmutatást ad a HoloLens 2 regisztrálásához a meglévő eszközkezelésben, a licencek szükség szerint történő alkalmazásához és annak ellenőrzéséhez, hogy a végfelhasználók képesek-e Dynamics 365-útmutatót üzemeltetni, valamint hogyan használhatnak egyéni üzletági alkalmazásokat az eszköz beállítása után.

> [!div class="nextstepaction"]
> [Vállalati hálózat üzembe helyezési útmutatója](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>C forgatókönyv: Üzembe helyezés biztonságos offline környezetben

Ez egy tipikus üzembe helyezés rendkívül biztonságos vagy bizalmas helyek esetén. HoloLens 2. pont elsősorban offline használatra van telepítve, hálózat és internet-hozzáférés nélkül. 
 * Alapszintű gyakori konfigurációk
   * Wi-Fi kapcsolat le van tiltva. Szükség esetén az Ethernet USB-kapcsolaton keresztül is engedélyezhető a lan-kapcsolathoz.
   * Nem felügyelt.
   * Helyi felhasználói fiók az eszközbe való bejelentkezéshez.
     * HoloLens 2. lehetőség csak egy helyi fiókot támogat.
   * Az eszköz zárolási konfigurációjának különböző szintjei a kiépítési csomagokon keresztül alkalmazhatók adott esetekben. Ezek a konfigurációk általában a biztonságos környezeti követelmények miatt korlátozottak.
   * Egy vagy több alkalmazás üzembe helyezése a kiépítési csomaggal

 * Gyakori kihívások
   * A kiépítési csomagokon keresztül korlátozott számú konfiguráció érhető el
   * A felhőszolgáltatások nem használhatók, ezért 2 HoloLens korlátozva.
   * Nagyobb adminisztrációs terhelés, mivel ezeket az eszközöket manuálisan kell beállítani, konfigurálni és frissíteni.

[![Offline biztonságos kapcsolat – 1. ábra ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

A megfelelő offline biztonságos útmutató útmutatást nyújt egy minta kiépítési csomag alkalmazásához, amely a 2. HoloLens zárolja a biztonságos környezetekben való használathoz.

> [!div class="nextstepaction"]
> [Offline biztonságos környezet üzembe helyezési útmutatója](hololens-common-scenarios-offline-secure.md)


