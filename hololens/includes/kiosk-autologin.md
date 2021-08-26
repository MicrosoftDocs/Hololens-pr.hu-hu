---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859414"
---
# <a name="non-aad-configuration"></a>[Nem AAD-konfiguráció](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>Nem AAD-konfiguráció

1. Hozzon létre egy kiépítési csomagot, amely:
    1. Úgy konfigurálja a Runtime-beállításokat/AssignedAccess-t, hogy engedélyezze a látogatói fiókokat.
    1. Ha szükséges, regisztrálja az eszközt az MDM-be (Futásidejű beállítások/Munkahely/Regisztrációk), hogy később kezelhető legyen.
    1. Ne hozzon létre helyi fiókot
2. [Alkalmazza a kiépítési csomagot.](../hololens-provisioning.md)

# <a name="aad-configuration"></a>[AAD-konfiguráció](#tab/aadlogon)

#### <a name="aad-configuration"></a>AAD-konfiguráció

A kioszkmódhoz konfigurált AAD-hez csatlakozott eszközök egyetlen koppintással bejelentkeztetnek egy látogatói fiókot a bejelentkezési képernyőről. Miután bejelentkezett a látogatói fiókba, az eszköz mindaddig nem kéri újra a bejelentkezést, amíg a Látogatót kifejezetten ki nem jelentkezik a Start menüből, vagy újra nem indítják az eszközt.

A látogatói automatikus bejelentkezés egyéni [OMA-URI-szabályzat](/mem/intune/configuration/custom-settings-windows-10)segítségével kezelhető:

- URI-érték: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Szabályzat | Description | Konfigurációk |
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Lehetővé teszi a látogató számára a kioszkba való automatikus bejelentkezést. | 1 (Igen), 0 (Nem, alapértelmezés.) |