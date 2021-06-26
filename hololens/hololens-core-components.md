---
title: A HoloLens 2 üzembe helyezésének megtervezése kereskedelmi környezetben
description: Megismerheti a HoloLens vállalati környezetekben való üzembe helyezésének és kezelésének alapvető igényeit, beleértve az infrastruktúrát, az Azure Active Directoryt és a mobileszköz-felügyeletet.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961429"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>A HoloLens 2 üzembe helyezésének megtervezése kereskedelmi környezetben

## <a name="overview"></a>Áttekintés
> [!NOTE]
> Az áttekintés célja, hogy segítse az informatikai szakembereket abban, hogy megértsék, milyen szempontokat kell figyelembe venni a Microsoft HoloLens 2 eszköz telepítésével és kezelésével kapcsolatban a szervezeten belül. Az eszköz végfelhasználói számára lásd: [Az első lépések](hololens2-setup.md) alapjai.

A HoloLens 2 Windows 10 Holographic, amely robusztus, rugalmas, beépített mobileszköz- és alkalmazáskezelési technológiákat biztosít a szervezeteknek. Windows 10 Holographic támogatja a teljes eszköz-életciklus kezelését, így a vállalatok szabályozni lehet eszközeik, adataik és alkalmazásaik kezelését. A HoloLens 2 könnyen beépíthető a szabványos életciklus-eljárásokba, az eszközök regisztrálásán, konfigurálásán és alkalmazáskezelésén át a karbantartásig és kivezetésig egy átfogó mobileszköz-kezelési megoldás használatával.

Az alábbi lépések végigvezetik a HoloLens 2 szervezeten belüli bevezetésének folyamatán.

| | |
|--|--|
| ![1. lépés](images/1green.png)| <br/> **[Gyakori üzembe helyezési forgatókönyvek:](hololens-requirements.md)** Megismerheti az üzembe helyezési forgatókönyveket, és megismerheti a HoloLens 2-eszközök üzembe helyezéséhez szükséges alapvető összetevőket. |
| ![2. lépés](images/2green.png)| <br/> **[Előkészítés:](#prepare)** Ismerkedjen meg a HoloLens 2-hez szükséges infrastruktúra-nélkülözhetetlenekkel. |
| ![3. lépés](images/3green.png) | <br/> **[Konfigurálás:](#configure)** Megtudhatja, hogyan konfigurálhatja a felhőalapú üzembe helyezés alapvető összetevőit. |
| ![4. lépés](images/4green.png) | <br/> **[Üzembe](#deploy)** helyezés: Megismerheti az eszközök üzembe helyezésének és az alkalmazások biztonságos és hatékony terjesztésének mikéntját. |
| ![5. lépés](images/5green.png) | <br/> **[Karbantartás:](#maintain)** Derítse ki, mire van szükség a HoloLens 2-eszközök állapotának megfelelő fenntartásához és a vállalati szabályzatnak való megfelelőség biztosításához. |

## <a name="prepare"></a>Előkészítés

Ismerje meg a HoloLens 2 funkcióinak teljes készletéhez szükséges alapvető infrastruktúra-szolgáltatásokat. 

| Összetevő | Leírás |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Identitás- és hozzáférés-kezelés a HoloLens 2 számára  |
| [Mobileszköz-kezelés](hololens-mdm-configure.md)| Felügyeli a bérlőhöz csatlakoztatott HoloLens 2-eszközöket  |
| [Wi-Fi-hálózat](hololens-commercial-infrastructure.md)| Wi-Fi elérhető, és az eszközök csatlakoztatva vannak az internethez  |

## <a name="configure"></a>Konfigurálás

Az Intune-t és az Autopilotot kevés érintéssel használható megoldásként használhatja a HoloLens 2 a szervezet Azure AD-bérlőjéhez és MDM-éhez való regisztrálására és konfigurálásához.

| Összetevő | Leírás |
|-----------|------------|
| [Automatikus regisztráció](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | A kezdeti bejelentkezést követően az eszközök automatikusan regisztrálnak az Azure AD-ban, és regisztrálnak az MDM-be  |
| [Alkalmazáslicencek](hololens2-cloud-connected-configure.md#application-licenses)| Felhasználókra, felhasználói csoportokra vagy eszközcsoportokra is alkalmazható  |
| [Azure-felhasználók és -csoportok](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Segít a Konfigurációk és licencek hozzárendelésében a HoloLens 2-hez  |

## <a name="deploy"></a>Üzembe helyezés

HoloLens 2-eszközök terjesztése és konfigurációjuk ellenőrzése. 

| Összetevő | Leírás |
|-----------|------------|
| [Regisztráció ellenőrzése](hololens2-corp-connected-deploy.md#enrollment-validation) | Ellenőrizze, hogy az eszközhöz csatlakozott-e az Azure AD a beállításokból vagy az Azure Portalról |
| [Tanúsítvány érvényesítése](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Ellenőrizze a beállításokat, és ellenőrizze, hogy megfelelően történt-e az elosztásuk |
| [Alkalmazástelepítések ellenőrzése](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Ellenőrizze, hogy az alkalmazás jelen van-e, és működik-e a HoloLens 2-ben |

## <a name="maintain"></a>Karbantartás

A Windows Update Vállalatoknak MDM-rendszerrel vagy az alkalmazásokkal együtt Microsoft Store a HoloLens 2-flotta és az alkalmazások frissítéséhez.

| Összetevő | Leírás |
|-----------|------------|
| [A HoloLens 2 frissítése](hololens-updates.md) | Szükség szerint konfigurálja a frissítéseket a Vállalati Windows-frissítések szolgáltatáson keresztül |
| [Alkalmazások frissítése](app-deploy-overview.md) | Konfigurálás az MDM-rendszeren vagy a Microsoft Store
