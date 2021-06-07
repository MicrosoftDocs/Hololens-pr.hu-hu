---
title: Windows Autopilot HoloLens 2 regisztrációs támogatása
description: Megtudhatja, hogyan kér regisztrációtámogatást az Autopilothoz HoloLens 2-eszközökön.
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
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379657"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>HoloLens 2-regisztrációs támogatás az AutoPilothoz

Az ügyfelek és a Microsoft felhőszolgáltatói (CSP-k) most már regisztrálják a HoloLens 2-eszközöket úgy, hogy közvetlenül beküldik a Microsoft ügyfélszolgálata. Ez az oldal a következő támogatott AutoPilot-regisztrációs forgatókönyvek követelményeit ismerteti:

- **HoloLens 2 Device Autopilot Registration ( HoloLens 2 eszköz Autopilot-regisztrációja).** Kérelmet küld a HoloLens 2-eszközök regisztrálására a Windows Autopilot.
- **HoloLens 2 eszközhardver-kivonatkérés.** Kérést küld a Microsoft ügyfélszolgálata, hogy az ügyfelek vagy CSP-k által az Microsoft Intune-n vagy a Microsoft Partnerközpont.
- **HoloLens 2 Device Autopilot Deregistration**. Az eszközök törlésére vonatkozó Windows Autopilot küld, általában az eszközök életciklusának végén használatos forgatókönyvekben.

Az alábbi táblázat részletesen be  tartalmazza a regisztrációs kérések elküldése előtt begyűjtött adatokat a Microsoft ügyfélszolgálata.

| Szükséges információk | Leírás | Autopilot-regisztráció  | Hardveres kivonat kérése | Autopilot-regisztráció |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory bérlőazonosítója    |    A Azure Active Directory globálisan egyedi azonosító (GUID), amely eltér a szervezet nevétől vagy tartománytól.    A bérlőazonosító megkereséhez jelentkezzen be az [Azure Portalra.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory tartománynév    |   A legfelső szintű tartománynév; Például: contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Tulajdonjog igazolása    |   A tulajdonjog igazolásának ellenőrzéséhez töltse fel az eredeti értékesítési vagy számla formátumú számlát. A képernyőképek nem fogadhatóak el. Az értékesítési vagy számlajegyzéknek tartalmaznia kell a következőket: Eszköz sorozatszámai. Vállalat neve.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Eszközök sorozatszámai    |   Excel-fájl feltöltése CSV formátumban, új sorban minden eszköz-sorozatszámmal.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Támogatási kérések elküldése

> [!div class="nextstepaction"]
> [Autopilot-regisztrációs támogatás beküldését a HoloLens 2-hez](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
