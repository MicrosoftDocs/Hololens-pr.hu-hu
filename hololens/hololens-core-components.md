---
title: A HoloLens 2. telepítés megtervezése kereskedelmi környezetben
description: Megismerheti a vállalati környezetek üzembe helyezésének és kezelésének alapvető HoloLens, beleértve az infrastruktúrát, az Azure Active Directoryt és a mobileszköz-felügyeletet.
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
ms.openlocfilehash: 8605d1a889fb9facdab0e9585a43a61880155952
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427580"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>A HoloLens 2. telepítés megtervezése kereskedelmi környezetben

## <a name="overview"></a>Áttekintés

> [!NOTE]
> Ennek az áttekintésnek a célja, hogy segítse az informatikai szakembereket abban, hogy megértsék, milyen szempontokat kell figyelembe venni Microsoft HoloLens 2 eszköz telepítésével és kezelésével kapcsolatban a szervezeten belül. Az eszköz végfelhasználói számára lásd: Get your HoloLens 2 ready to use to get started (A [2.](hololens2-setup.md) HoloLens használatra kész az első lépésekhez).

HoloLens 2. Windows 10 Holographic, amely robusztus, rugalmas, beépített mobileszköz- és alkalmazáskezelési technológiákat biztosít a szervezeteknek. Windows 10 Holographic támogatja a teljes eszköz-életciklus kezelését, így a vállalatok szabályozni lehet eszközeik, adataik és alkalmazásaik kezelését. A HoloLens 2. csomag egyszerűen beépíthető a szabványos életciklus-eljárásokba, az eszközök regisztrálásán, konfigurálásán és alkalmazáskezelésén át a karbantartásig és kivezetésig egy átfogó mobileszköz-kezelési megoldás használatával.

Az alábbi lépések és videók végigvezetik a HoloLens 2. bevezetésének folyamatán.

| &nbsp; | &nbsp; |
|--|--|
| ![1. lépés](images/1green.png)| <br/> **[Gyakori telepítési forgatókönyvek:](hololens-requirements.md)** Megismerheti a telepítési forgatókönyveket, és megismerheti a két eszköz üzembe helyezéséhez HoloLens alapvető összetevőket. |
| ![2. lépés](images/2green.png)| <br/> **[Előkészítés:](#prepare)** Ismerkedjen meg a 2. HoloLens szükséges infrastruktúrával. |
| ![3. lépés](images/3green.png) | <br/> **[Konfigurálás:](#configure)** Megtudhatja, hogyan konfigurálhatja a felhőalapú üzembe helyezés alapvető összetevőit. |
| ![4. lépés:](images/4green.png) | <br/> **[Üzembe](#deploy)** helyezés: Megismerheti az eszközök üzembe helyezésének és az alkalmazások biztonságos és hatékony terjesztésének mikéntjére vonatkozó információkat. |
| ![5. lépés](images/5green.png) | <br/> **[Karbantartás:](#maintain)** Derítse ki, mire van szükség a 2 eszköz HoloLens állapotának megfelelő fenntartásához és a vállalati szabályzatnak való megfelelés biztosításához. |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Előkészítés

Ismerje meg a 2. HoloLens összes képességének támogatásához szükséges alapvető infrastruktúra-szolgáltatásokat.

| Összetevő | Leírás |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Identitás- és hozzáféréskezelést biztosít a 2. HoloLens számára  |
| [Mobileszköz-kezelés](hololens-mdm-configure.md)| Felügyeli HoloLens 2, a bérlőhöz csatlakoztatott eszközt  |
| [Wi-Fi-hálózat](hololens-commercial-infrastructure.md)| Wi-Fi elérhető, és az eszközök csatlakoztatva vannak az internethez  |

## <a name="configure"></a>Konfigurálás

Az Intune-t és az Autopilotot 2. HoloLens 2. szintű regisztrációhoz és konfigurálásához használhatja a szervezet Azure AD-bérlőjéhez és MDM-éhez.

| Összetevő | Leírás |
|-----------|------------|
| [Automatikus regisztráció](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | A kezdeti bejelentkezést követően az eszközök automatikusan regisztrálnak az Azure AD-ban, és regisztrálnak az MDM-be  |
| [Alkalmazáslicencek](hololens2-cloud-connected-configure.md#application-licenses)| Felhasználókra, felhasználói csoportokra vagy eszközcsoportokra is alkalmazható  |
| [Azure-felhasználók és -csoportok](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Konfigurációk és licencek hozzárendelését segíti a 2. HoloLens számára  |

## <a name="deploy"></a>Üzembe helyezés

Ossza ki HoloLens 2 eszközt, és ellenőrizze azok konfigurációját. 

| Összetevő | Leírás |
|-----------|------------|
| [Regisztráció ellenőrzése](hololens2-corp-connected-deploy.md#enrollment-validation) | Ellenőrizze, hogy az eszköz csatlakozott-e az Azure AD Gépház vagy az Azure Portalról |
| [Tanúsítvány érvényesítése](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Ellenőrizze a beállításokat, és ellenőrizze, hogy megfelelően történt-e az elosztásuk |
| [Alkalmazástelepítések ellenőrzése](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Győződjön meg arról, hogy az alkalmazás 2. HoloLens működik |

## <a name="maintain"></a>Karbantartás

Az Windows Update for Business, valamint az MDM-rendszer vagy a Microsoft Store használatával naprakészen tarthatja HoloLens 2- és alkalmazásflottát.

| Összetevő | Leírás |
|-----------|------------|
| [2 HoloLens frissítése](hololens-updates.md) | Szükség szerint konfigurálhatja a frissítéseket az Windows frissítésekkel |
| [Alkalmazások frissítése](app-deploy-overview.md) | Konfigurálás az MDM-rendszeren vagy a Microsoft Store
