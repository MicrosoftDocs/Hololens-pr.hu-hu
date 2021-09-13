---
title: Windows Autopilot-regisztráció támogatása HoloLens 2. HoloLens
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
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036157"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>HoloLens 2. regisztráció támogatása az AutoPilothoz

Az ügyfelek és a Microsoft felhőszolgáltatói (CSP-k) mostantól 2 HoloLens regisztrálhat, ha közvetlenül kéréseket Microsoft ügyfélszolgálata. Ez az oldal a következő támogatott AutoPilot-regisztrációs forgatókönyvek követelményeit ismerteti:

- **HoloLens 2. eszköz Autopilot-regisztrációja.** Két eszköz autopilot HoloLens ban való regisztrálásának kérését Windows el.
- **HoloLens 2 eszközhardver-kivonatkérés.** Kérést küld a Microsoft ügyfélszolgálata, hogy olyan hardveres Microsoft Intune biztosítson, amelyek segítségével az ügyfelek vagy csp-k ön regisztrálják az eszközöket a Microsoft Intune vagy a Microsoft Partnerközpont.
- **HoloLens 2. eszköz autopilot-regisztrációját.** Az Eszközök törlésére vonatkozó kérést küld Windows Autopilotból, általában az eszközök életciklusának végén használatos forgatókönyvekben.

Az alábbi táblázat részletesen be  tartalmazza a regisztrációs kérések elküldése előtt összegyűjthető információkat a Microsoft ügyfélszolgálata.

| Szükséges információk | Description | Autopilot-regisztráció  | Hardveres kivonat kérése | Autopilot-regisztráció |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory Bérlőazonosító    |    A Azure Active Directory azonosítója egy globálisan egyedi azonosító (GUID), amely eltér a szervezet nevétől vagy tartománytól.    A bérlőazonosító megkereséhez jelentkezzen be az [Azure Portalra.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory Tartománynév    |   A legfelső szintű tartománynév; Például: contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Tulajdonjog igazolása    |   A tulajdonjog igazolását az eredeti értékesítési vagy számla PDF formátumú feltöltésével ellenőrizheti. A képernyőképek nem fogadhatóak el. Az értékesítési vagy számlajegyzéknek tartalmaznia kell a következőket: Eszköz sorozatszámai. Vállalat neve.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Eszközök sorozatszámai    |   Töltse Excel CSV formátumban található fájlt, és minden eszköz sorozatszámát egy új sorban töltse fel.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Támogatási kérések elküldése

> [!div class="nextstepaction"]
> [Autopilot-regisztrációs támogatás elküldése HoloLens 2. HoloLens](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
