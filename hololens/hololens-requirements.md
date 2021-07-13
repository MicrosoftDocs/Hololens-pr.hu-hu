---
title: Gyakori üzembe helyezési forgatókönyvek
description: További információ a vállalati környezetekben HoloLens és kezeléséről, beleértve az infrastruktúrát, a Azure Active Directory és a mobileszköz-kezeléseket.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: ccccdcc7d3188919d02eb5855131137415c12d16
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639828"
---
# <a name="common-deployment-scenarios"></a>Gyakori üzembe helyezési forgatókönyvek

## <a name="overview"></a>Áttekintés

Ez az oldal magas szintű architektúra-áttekintést nyújt három gyakori forgatókönyvhöz, amelyek két Microsoft HoloLens vállalati eszköz üzembe helyezésekor és kezelésekor.

Az eszközök kezelését és a szervezeti erőforrásokhoz való hozzáférést gyakran a már rendelkezésre álló tényezők határozzák meg. A meglévő infrastruktúra alapján a következő forgatókönyvekben tekintse át az általános eszközkezelési stílust (MDM), majd olvassa el a Planning [HoloLens 2 deployments in a commercial](hololens-core-components.md) environment (Az HoloLens 2 üzembe helyezések tervezése kereskedelmi környezetben) útmutatót annak meghatározásához, hogy melyik forgatókönyv illik az igényeihez. Az üzembe helyezés során három megfelelő útmutató is rendelkezésre áll.


 1. [Felhőhöz csatlakoztatott környezet üzembe helyezési útmutatója](hololens2-cloud-connected-overview.md)
     1. [Felhőhöz csatlakoztatott környezet (külső ügyfelek) üzembe helyezési útmutatója](hololens2-deployment-guide.md)
 1. [Útmutató a vállalati hálózatok üzembe helyezéséhez](hololens2-corp-connected-overview.md)
 1. [Offline biztonságos környezet üzembe helyezési útmutatója](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>A forgatókönyv: Üzembe helyezés felhőhöz csatlakoztatott eszközökön

Ez a forgatókönyv hasonló a felügyelt mobileszközök vállalati telepítéséhez. HoloLens 2. üzembe helyezése elsősorban vállalati hálózaton kívülre készült. A vállalati erőforrások nem érhetők el, vagy VPN-en keresztül korlátozhatóak. 
 * Alapszintű gyakori konfigurációk
   * Wi-Fi hálózatok általában teljesen nyitva vannak az internet és a felhőszolgáltatások számára.
   * Azure AD-csatlakozás mobile Eszközkezelés (MDM) automatikus regisztrációval – MDM (Intune) által felügyelt
   * A felhasználók a saját vállalati fiókjukkal (Azure AD) jelentkeznek be
     * Egy vagy több felhasználó támogatott eszközönként
   * Az eszközzárolási konfigurációk különböző szintjei adott esetek alapján vannak alkalmazva, a teljesen nyitotttól az egyalkalmazásos kioszkig.
   * Egy vagy több alkalmazás MDM-en keresztül van telepítve

* Gyakori kihívások
   * A 2. HoloLens MDM-konfigurációk meghatározása a forgatókönyv követelményei alapján.

[![A forgatókönyv ábrája ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

A megfelelő, felhőhöz csatlakoztatott útmutató bemutatja, hogyan regisztrálható HoloLens 2. lépés az eszközfelügyeletben, hogyan alkalmazhat licenceket szükség szerint, és hogyan ellenőrizheti, hogy a végfelhasználók az eszköz beállításakor azonnal tudják-e használni a Remote Assistet. A Külső ügyfelek útmutató segítségével rövid vagy hosszú távú külső használatra telepíthet eszközöket egy távoli helyen.

> [!div class="nextstepaction"]
> [Felhőhöz csatlakoztatott környezet üzembe helyezési útmutatója](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Felhőhöz csatlakoztatott környezet (külső ügyfelek) üzembe helyezési útmutatója](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>B forgatókönyv: Üzembe helyezés a szervezet hálózatán belül

Ez a forgatókönyv megegyezik a legtöbb számítógép klasszikus Windows 10 esetében. HoloLens 2. pont elsősorban a vállalati hálózaton való használatra van telepítve, és belső vállalati erőforrásokhoz fér hozzá. Az internet és a felhőszolgáltatások korlátozottak lehetnek. 

 * Alapszintű gyakori konfigurációk
   * Wi-Fi egy belső vállalati hálózat, amely hozzáfér a belső erőforrásokhoz, és korlátozott hozzáféréssel rendelkezik az internethez vagy a felhőszolgáltatásokhoz.
   * Azure AD-csatlakozás automatikus MDM-regisztrációval
   * MDM (Intune) által felügyelt
   * A felhasználók a saját vállalati fiókjukkal (Azure AD) jelentkeznek be
     * Egy vagy több felhasználó támogatott eszközönként
   * Az eszközzárolási konfigurációk különböző szintjei adott esetek alapján vannak alkalmazva, a teljesen nyitotttól az egyalkalmazásos kioszkig.
   * Egy vagy több alkalmazás MDM-en keresztül van telepítve

 * Gyakori kihívások
   * HoloLens 2. nem támogatja a helyszíni AD-csatlakozást vagy az SCCM-et. Csak az Azure AD-hez csatlakozzon az MDM-hez. Ebben a forgatókönyvben számos vállalat továbbra is Windows 10 számítógépeket helyez üzembe az System Center Configuration Manager (SCCM) által felügyelt helyszíni AD-hez csatlakozott eszközökként, és előfordulhat, hogy nincs telepítve/konfigurálva a belső Windows 10-eszközök felhőalapú MDM-megoldásokon keresztüli kezelésére szolgáló infrastruktúra.
   * Mivel HoloLens 2. felhőalapú eszköz, nagy mértékben támaszkodik az internethez és a felhőhöz kapcsolódó szolgáltatásokra a felhasználóhitelesítéshez, az operációs rendszer frissítéséhez, az MDM-felügyelethez és így tovább. Vállalati hálózathoz való csatlakozáskor a proxy-/tűzfalszabályokat nagy valószínűséggel úgy kell módosítani, hogy HoloLens 2. vagy a rajta futó alkalmazások hozzáférését engedélyezték.
   * A Wi-Fi kapcsolatokhoz általában tanúsítványokra van szükség az eszköz vagy a felhasználó hálózaton való hitelesítéséhez. A tanúsítványok MDM-Windows 10 eszközökre való telepítéséhez szükséges infrastruktúra vagy beállítások konfigurálása kihívást jelenthet.

[![A B1 forgatókönyv diagramja ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![A B2 forgatókönyv diagramja ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

A megfelelő vállalati hálózati útmutató útmutatást ad a HoloLens 2 regisztrálásához a meglévő eszközkezelésben, a licencek szükség szerint történő alkalmazásához és annak ellenőrzéséhez, hogy a végfelhasználók képesek-e Dynamics 365-útmutatót működtetni, valamint egyéni üzletági alkalmazásokat használni az eszköz beállítása után.

> [!div class="nextstepaction"]
> [Útmutató a vállalati hálózatok üzembe helyezéséhez](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>C forgatókönyv: Üzembe helyezés biztonságos offline környezetben

Ez egy tipikus üzembe helyezés a rendkívül biztonságos vagy bizalmas helyeken. HoloLens 2. pont elsősorban offline használatra van telepítve, hálózat és internet-hozzáférés nélkül. 
 * Alapszintű gyakori konfigurációk
   * Wi-Fi kapcsolat le van tiltva. Szükség esetén az Ethernet USB-kapcsolaton keresztül is engedélyezhető a helyi hálózat számára.
   * Nincs felügyelt.
   * Helyi felhasználói fiók az eszközbe való bejelentkezéshez.
     * HoloLens 2. lehetőség csak egy helyi fiókot támogat.
   * Az eszközzárolási konfigurációk különböző szintjei a kiépítési csomagokon keresztül alkalmazhatók adott esetekben. Ezek a konfigurációk általában a biztonságos környezeti követelmények miatt korlátozottak.
   * Egy vagy több alkalmazás üzembe helyezése a kiépítési csomagon keresztül

 * Gyakori kihívások
   * A kiépítési csomagokon keresztül korlátozott számú konfiguráció érhető el
   * A felhőszolgáltatások nem használhatók, ezért 2 HoloLens korlátozva.
   * Nagyobb adminisztrációs terhelés, mivel ezeket az eszközöket manuálisan kell beállítani, konfigurálni és frissíteni.

[![Offline biztonságos diagram 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

A megfelelő offline biztonságos útmutató útmutatást nyújt egy minta kiépítési csomag alkalmazásához, amely a 2. HoloLens zárolja a biztonságos környezetekben való használathoz.

> [!div class="nextstepaction"]
> [Offline biztonságos környezet üzembe helyezési útmutatója](hololens-common-scenarios-offline-secure.md)


