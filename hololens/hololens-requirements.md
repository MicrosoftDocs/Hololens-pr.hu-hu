---
title: Gyakori üzembe helyezési forgatókönyvek
description: További információ a vállalati környezetekben HoloLens és kezeléséről, beleértve az infrastruktúrát, a Azure Active Directory és a mobileszköz-kezelésről.
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
ms.openlocfilehash: 5a4f251f3ca6eae5e85e4d763074e035039159cb
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428763"
---
# <a name="common-deployment-scenarios"></a>Gyakori üzembe helyezési forgatókönyvek

## <a name="overview"></a>Áttekintés

Az új eszközök üzembe helyezésének kiderítésében nehéz lehet az első próbálkozáskor. Ebben a 2 eszköznek a szervezeten Microsoft HoloLens üzembe helyezésének és kezelésének különböző módjait osztjuk meg.

Nagy méretekben üzembe helyezett megoldásokat szeretne. Szeretnénk odahozni. Először is vegyük át az eszközök , tehát a hologramok üzembe helyezésének lépéseit, hogy értéket teremtsünk a vegyes valóság célhelyzete számára, akár d365 Remote Assist, akár útmutatók, vagy egy Ön által létrehozott Azure Mixed Reality szolgáltatást használó alkalmazás.

Ön lehet egy üzleti döntéshozó, it-szakember vagy egy innovációs csapat, amely vállalaton HoloLens vállalaton belül. A koncepció igazolása és a skálázható üzembe helyezés között az üzembe helyezési útmutatóink HoloLens az it-infrastruktúrán belüli fejlesztést – függetlenül attól, hogy mekkora vagy kicsi. A leggyakoribb telepítési forgatókönyvek a következők:

| Eset |Használat | Kulcsfontosságú pontok |
|---------|---------|---------|
| [A forgatókönyv: Felhőhöz csatlakoztatott eszközök](hololens2-cloud-connected-overview.md) | Az üzembe helyezés első megkezdésekor kicsiben kezdhet, és egyetlen, a felhőhöz csatlakoztatott eszközt helyezhet üzembe az alapvető folyamat érdekében. | Az eszközök a felhőszolgáltatásokhoz és a nyilvános internethez lesznek csatlakoztatva. Ez az ügyfélesetek, helyszíni szolgáltatások és a koncepció igazolása esetén a legmegfelelőbb.|
| [B forgatókönyv: Szervezeti hálózat](hololens2-corp-connected-overview.md) | Amikor nagy léptékben helyez üzembe éles környezetben, előfordulhat, hogy integrálni kell magát a saját szervezet hálózatával. | Az eszközök egy "Céges" Wi-Fi-hálózathoz csatlakoznak. Ez a legmegfelelőbb a belső felhasználók számára, vagy a vállalati környezetben való használatra.|
| [C forgatókönyv: Offline biztonságos környezet](hololens-common-scenarios-offline-secure.md) | Egyes alapvető fontosságú folyamatok vagy vállalati szabályzatok offline környezetek használatát követelik meg. | Az eszközök egy rendkívül korlátozó hálózathoz csatlakoznak, vagy kizárólag offline eszközök lesznek. Ez a legmegfelelőbb a rendkívül biztonságos környezetekhez vagy távoli helyeken az internetkapcsolattal kapcsolatos korlátozásokhoz. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>A forgatókönyv: Üzembe helyezés felhőhöz csatlakoztatott eszközökön

Ez a forgatókönyv hasonló a felügyelt mobileszközök vállalati telepítéséhez. HoloLens 2. üzembe helyezése elsősorban vállalati hálózaton kívülre készült környezetekben való használatra. A vállalati erőforrások nem érhetők el, vagy VPN-en keresztül korlátozhatóak.

[![Forgatókönyv Diagram.](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>A következő esetekben használja

Tekintse meg ezt az üzembe helyezési modellt a következő hez:

* Koncepció igazolásának, próba- és helyszíni szolgáltatásainak üzembe helyezése
* A [Remote Assist telepítése](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>Alapszintű gyakori konfigurációk

* Wi-Fi hálózatok általában teljesen nyitva vannak az internet és a felhőszolgáltatások számára
* Azure AD-csatlakozás mobile Eszközkezelés (MDM) automatikus regisztrációval – MDM (Intune) által felügyelt
* A felhasználók a saját vállalati fiókjukkal (Azure AD) jelentkeznek be
  * Egy vagy több felhasználó támogatott eszközönként
* Az eszközzárolási konfigurációk különböző szintjei adott esetek alapján vannak alkalmazva, a teljesen nyitotttól az egyalkalmazásos kioszkig.
* Egy vagy több alkalmazás MDM-en keresztül van telepítve

### <a name="common-challenges"></a>Gyakori kihívások

* A 2. HoloLens MDM-konfigurációk meghatározása a forgatókönyv követelményei alapján

A megfelelő, felhőhöz csatlakoztatott útmutató bemutatja, hogyan regisztrálható HoloLens 2. lépés az eszközfelügyeletre, hogyan alkalmazhat licenceket szükség szerint, és hogyan ellenőrizheti, hogy a végfelhasználók az eszköz beállításakor azonnal tudják-e használni a Remote Assistet.

> [!div class="nextstepaction"]
> [Felhőhöz csatlakoztatott üzembe helyezési útmutató](hololens2-cloud-connected-overview.md)

A Külső ügyfelek útmutató segítségével rövid vagy hosszú távú külső használatra telepíthet eszközöket egy távoli helyen.

> [!div class="nextstepaction"]
> [Felhőhöz csatlakoztatott (külső ügyfelek) üzembe helyezési útmutatója](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>B forgatókönyv: Üzembe helyezés a szervezet hálózatán belül

Ez a forgatókönyv megegyezik a legtöbb számítógép Windows 10 klasszikus üzembe helyezéssel. HoloLens 2. hiba elsősorban a vállalati hálózaton való használatra van telepítve, és belső vállalati erőforrásokhoz fér hozzá. Az internet és a felhőszolgáltatások korlátozottak lehetnek. 

[![A B1 forgatókönyv diagramja.](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![A B2 forgatókönyv diagramja.](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>A következő esetekben használja

Tekintse meg ezt az üzembe helyezési modellt a következő hez:

* Belső felhasználók
* Nagy léptékű üzembe helyezés (próba- és éles környezet) a vállalati környezetben

### <a name="basic-common-configurations"></a>Alapszintű gyakori konfigurációk

* Wi-Fi egy belső vállalati hálózat, amely hozzáféréssel rendelkezik a belső erőforrásokhoz, és korlátozott hozzáféréssel rendelkezik az internethez vagy a felhőszolgáltatásokhoz.
* Azure AD-csatlakozás automatikus MDM-regisztrációval
* MDM (Intune) által felügyelt
* A felhasználók a saját vállalati fiókjukkal (Azure AD) jelentkeznek be
  * Egy vagy több felhasználó támogatott eszközönként
* Az eszközzárolási konfigurációk különböző szintjei adott esetek alapján vannak alkalmazva, a teljesen nyitotttól az egyalkalmazásos kioszkig.
* Egy vagy több alkalmazás MDM-en keresztül van telepítve

### <a name="common-challenges"></a>Gyakori kihívások

* HoloLens 2. pont nem támogatja a helyszíni AD-csatlakozást vagy -csatlakozást (SCCM System Center Configuration Manager. Csak az Azure AD-hez csatlakozzon az MDM-hez. Ebben a forgatókönyvben számos vállalat még mindig Windows 10 számítógépeket helyez üzembe az SCCM által felügyelt helyszíni AD-hez csatlakozott eszközökként, és előfordulhat, hogy nincs telepítve/konfigurálva a belső Windows 10-eszközök felhőalapú MDM-megoldásokon keresztüli felügyeletéhez szükséges infrastruktúra.
* Mivel HoloLens 2. verzió egy felhőalapú eszköz, nagy mértékben támaszkodik az internethez és a felhőhöz kapcsolódó szolgáltatásokra a felhasználói hitelesítéshez, az operációs rendszer frissítéséhez, az MDM-felügyelethez stb. Vállalati hálózathoz való csatlakozáskor a proxy-/tűzfalszabályokat nagy valószínűséggel úgy kell módosítani, hogy HoloLens 2. vagy a rajta futó alkalmazások hozzáférését engedélyezték.
* A Wi-Fi kapcsolatokhoz általában tanúsítványokra van szükség az eszköz vagy a felhasználó hálózaton való hitelesítéséhez. A tanúsítványoknak az MDM-Windows 10 keresztüli telepítéséhez szükséges infrastruktúra vagy beállítások konfigurálása kihívást jelenthet.

A megfelelő vállalati csatlakoztatott útmutató útmutatást ad a HoloLens 2 regisztrálására a meglévő eszközkezelésben, a licencek szükség szerint történő alkalmazásával és annak ellenőrzésével, hogy a végfelhasználók képesek-e Dynamics 365-útmutatót működtetni, valamint egyéni üzletági alkalmazásokat használni az eszköz beállítása után.

> [!div class="nextstepaction"]
> [Vállalati csatlakoztatott üzembe helyezési útmutató](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>C forgatókönyv: Üzembe helyezés biztonságos offline környezetben

Ez egy tipikus üzembe helyezés a rendkívül biztonságos vagy bizalmas helyeken. HoloLens 2. pont elsősorban offline használatra van telepítve, hálózat- vagy internet-hozzáférés nélkül.

[![Offline biztonságos diagram 1.](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>A következő esetekben használja

Tekintse meg ezt az üzembe helyezési modellt a következő hez:

* Rendkívül biztonságos környezetek, ahol az adatokat házon át kell őrizni
* "Élmények", ahol a nyilvánosság az eszközöket fogja használni
* Internetkapcsolattal kapcsolatos probléma a távoli területen

### <a name="basic-common-configurations"></a>Alapszintű gyakori konfigurációk

* Wi-Fi kapcsolat le van tiltva. Szükség esetén az Ethernet USB-kapcsolaton keresztül is engedélyezhető a helyi hálózati kapcsolathoz
* Nem felügyelt
* Helyi felhasználói fiók az eszközbe való bejelentkezéshez
  * HoloLens 2. lehetőség csak egy helyi fiókot támogat
* Az eszközzárolási konfigurációk különböző szintjei a kiépítési csomagokon keresztül alkalmazhatók adott esetekben. Ezek a konfigurációk általában a biztonságos környezeti követelmények miatt korlátozottak
* Egy vagy több alkalmazás üzembe helyezése a kiépítési csomagon keresztül

### <a name="common-challenges"></a>Gyakori kihívások

* A kiépítési csomagokon keresztül korlátozott számú konfiguráció érhető el
* A felhőszolgáltatások nem használhatók, ezért 2 HoloLens korlátozva.
* Nagyobb adminisztrációs terhelés, mivel ezeket az eszközöket manuálisan kell beállítani, konfigurálni és frissíteni.

A megfelelő offline biztonságos útmutató útmutatást nyújt egy minta kiépítési csomag alkalmazásához, amely a 2. HoloLens zárolja a biztonságos környezetekben való használathoz.

> [!div class="nextstepaction"]
> [Offline biztonságos környezet üzembe helyezési útmutatója](hololens-common-scenarios-offline-secure.md)
