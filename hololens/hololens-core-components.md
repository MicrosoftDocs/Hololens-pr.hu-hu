---
title: 2. HoloLens megtervezése kereskedelmi környezetben
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
ms.openlocfilehash: 8273813d85c3b2df2c1a551fb0322a867a5a9c64fdd05e9a85a2097b1590fb62
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664336"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>2. HoloLens megtervezése kereskedelmi környezetben

## <a name="overview"></a>Áttekintés

> [!NOTE]
> Ennek az áttekintésnek a célja, hogy segítse az informatikai szakembereket abban, hogy megértsék a vállalat 2 Microsoft HoloLens eszközének telepítésével és kezelésével kapcsolatos szempontokat. Az eszköz végfelhasználói számára lásd: Get your HoloLens 2 ready to use to get started (A [2.](hololens2-setup.md) HoloLens használatra kész az első lépésekhez).

HoloLens 2. Windows 10 Holographic, amely robusztus, rugalmas, beépített mobileszköz- és alkalmazáskezelési technológiákat biztosít a szervezeteknek. Windows 10 Holographic támogatja a teljes eszköz-életciklus kezelését, így a vállalatok szabályozni lehet eszközeik, adataik és alkalmazásaik kezelését. A HoloLens 2., amely egy átfogó mobileszköz-kezelési megoldással egyszerűen beépíthető a szabványos életciklus-eljárásokba, az eszközök regisztrálásán, konfigurálásán és alkalmazáskezelésén át a karbantartásig és kivezetésig.

A következő lépések és videó végigvezeti a HoloLens 2. bevezetésének folyamatán.

| &nbsp; | &nbsp; |
|--|--|
| ![1. lépés](images/1green.png)| <br/> **[Gyakori telepítési forgatókönyvek:](hololens-requirements.md)** Megismerheti a telepítési forgatókönyveket, és megismerheti a két eszköz üzembe helyezéséhez HoloLens alapvető összetevőket. |
| ![2. lépés](images/2green.png)| <br/> **[Előkészítés:](#prepare)** Ismerkedjen meg a 2. HoloLens szükséges infrastruktúrával. |
| ![3. lépés](images/3green.png) | <br/> **[Konfigurálás:](#configure)** Megtudhatja, hogyan konfigurálhatja a felhőalapú üzembe helyezés alapvető összetevőit. |
| ![4. lépés](images/4green.png) | <br/> **[Üzembe](#deploy)** helyezés: Ismerje meg, hogyan helyezheti üzembe eszközeit, és hogyan terjesztheti biztonságosan és hatékonyan az alkalmazásokat. |
| ![5. lépés](images/5green.png) | <br/> **[Karbantartás:](#maintain)** Derítse ki, mi szükséges a két eszköz állapotának megfelelő HoloLens és a vállalati szabályzatnak való megfelelés biztosításához. |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Előkészítés

Ismerje meg az alapvető infrastruktúra-szolgáltatásokat, amelyek a 2. HoloLens teljes készletének támogatásához szükségesek.

| Összetevő | Leírás |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Identitás- és hozzáféréskezelést biztosít a 2. HoloLens számára  |
| [Mobileszköz-kezelés](hololens-mdm-configure.md)| A HoloLens 2 eszköz kezelését kezeli  |
| [Wi-Fi-hálózat](hololens-commercial-infrastructure.md)| Wi-Fi elérhető, és az eszközök csatlakoztatva vannak az internethez  |

## <a name="configure"></a>Konfigurálás

Az Intune-t és az Autopilotot 2. HoloLens-megoldásként használhatja a szervezet Azure AD-bérlőjéhez és MDM-éhez való regisztráláshoz és konfigurálásához.

| Összetevő | Leírás |
|-----------|------------|
| [Automatikus regisztráció](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | A kezdeti bejelentkezés után az eszközök automatikusan regisztrálnak az Azure AD-be, és regisztrálnak az MDM-be  |
| [Alkalmazáslicencek](hololens2-cloud-connected-configure.md#application-licenses)| Felhasználókra, felhasználói csoportokra vagy eszközcsoportokra is alkalmazható  |
| [Azure-felhasználók és -csoportok](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Konfigurációk és licencek hozzárendelését segíti a 2. HoloLens számára  |

## <a name="deploy"></a>Üzembe helyezés

Ossza ki a HoloLens 2 eszközt, és ellenőrizze azok konfigurációját. 

| Összetevő | Leírás |
|-----------|------------|
| [Regisztráció ellenőrzése](hololens2-corp-connected-deploy.md#enrollment-validation) | Ellenőrizze, hogy az eszközhöz csatlakozott-e az Azure AD Gépház vagy az Azure Portal |
| [Tanúsítvány érvényesítése](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Ellenőrizze a beállításokat, és ellenőrizze, hogy megfelelően vannak-e elosztva |
| [Alkalmazástelepítések ellenőrzése](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Győződjön meg arról, hogy az alkalmazás 2. HoloLens működik |

## <a name="maintain"></a>Karbantartás

Az Windows Update for Business, valamint az MDM-rendszer vagy a Microsoft Store használatával naprakészen tarthatja 2-es HoloLens-flotta és alkalmazások flottafrissítését.

| Összetevő | Leírás |
|-----------|------------|
| [2 HoloLens frissítés](hololens-updates.md) | Frissítések konfigurálása az üzleti Windows frissítésekkel |
| [Alkalmazások frissítése](app-deploy-overview.md) | Konfigurálás az MDM-rendszeren vagy a Microsoft Store
