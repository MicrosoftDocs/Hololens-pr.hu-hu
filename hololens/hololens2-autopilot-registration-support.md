---
title: Windows Autopilot-regisztráció támogatása HoloLens 2-es HoloLens
description: Megtudhatja, hogyan lehet regisztrációs támogatást kapni az Autopilothoz HoloLens 2 eszközön.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Robotpilóta
manager: ylempidakis
ms.openlocfilehash: 2304e7ec18eb531cce431fb93c7abf38f2c9a1cef30f0d6c6fcaac6c95281f8e
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661791"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>HoloLens 2. regisztráció támogatása az Autopilothoz

Az ügyfelek és a Microsoft felhőszolgáltatók (CSP-k) most már 2 HoloLens regisztrálhat, ha közvetlenül kéréseket Microsoft ügyfélszolgálata. Ez az oldal a következő támogatott AutoPilot-regisztrációs forgatókönyvek követelményeit ismerteti:

- **HoloLens 2. eszköz Autopilot-regisztrációja.** Két eszköz autopilot HoloLens ban való regisztrálásának kérését Windows küld.
- **HoloLens 2. eszközhardver-kivonatkérés.** Kérést küld a Microsoft ügyfélszolgálata, hogy az ügyfelek vagy CSP-k által az Microsoft Intune vagy a Microsoft által regisztrált eszközök önkiszolgáló regisztrálásához használható hardver-Partnerközpont.
- **HoloLens 2. eszköz autopilot-regisztrációját.** Az Eszközök törlésére vonatkozó kérést küld az Windows Autopilotból, általában az eszközök életciklusának végén használatos forgatókönyvekben.

Az alábbi táblázat részletesen be  tartalmazza a regisztrációs kérések elküldése előtt begyűjtött adatokat a Microsoft ügyfélszolgálata.

| Szükséges információk | Description | Autopilot-regisztráció  | Hardveres kivonat kérése | Autopilot-regisztráció |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory Bérlőazonosító    |    A Azure Active Directory globálisan egyedi azonosító (GUID), amely eltér a szervezet nevétől vagy tartománytól.    A bérlőazonosító megkereséhez jelentkezzen be az [Azure Portalra.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory Tartománynév    |   A legfelső szintű tartománynév; Például: contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Tulajdonjog igazolása    |   A tulajdonjog igazolásának ellenőrzéséhez töltse fel az eredeti értékesítési vagy számla formátumú számlát. A képernyőképek nem fogadhatóak el. Az értékesítési vagy számlajegyzéknek tartalmaznia kell a következőket: Eszköz sorozatszámai. Vállalat neve.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Eszközök sorozatszámai    |   Töltse Excel csv formátumú fájlt, és minden eszköz sorozatszámát egy új sorban töltse fel.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Támogatási kérések elküldése

> [!div class="nextstepaction"]
> [Autopilot-regisztrációs támogatás elküldése a 2. HoloLens számára](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
