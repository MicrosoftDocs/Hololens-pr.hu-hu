---
title: Kereskedelmi funkciók
description: Megismerhet Microsoft HoloLens Commercial Suite funkciókat, amelyek megkönnyítik a vállalatok számára a HoloLens-eszközök kezelését.
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: HoloLens, kereskedelmi, funkciók, mdm, mobileszköz-kezelés, kioszkmód
ms.openlocfilehash: 3682a2633477d68f61dba8a674846857947a3d15
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379513"
---
# <a name="commercial-features"></a>Kereskedelmi funkciók

A HoloLens olyan funkciókat tartalmaz, amelyek megkönnyítik a vállalkozások számára a HoloLens-eszközök kezelését.

Minden HoloLens 2-eszköz kereskedelmi funkciókkal rendelkezik.

A HoloLens (1. generációs) két licencelési lehetőséget tartalmaz: a fejlesztői licencet és egy kereskedelmi licencet. A HoloLens kereskedelmi funkcióinak feloldásához frissítsen a fejlesztői licencről egy kereskedelmi licencre. A vásárláshoz Microsoft HoloLens Commercial Suite forduljon a helyi Microsoft-fiók menedzserhez.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## <a name="key-commercial-features"></a>A legfontosabb kereskedelmi funkciók

- **Kioszkmód.** A HoloLens bemutatókban vagy kioszkmódban való bemutatásával korlátozhatja, hogy mely alkalmazások futtathatók.

  ![Kioszkmódban a HoloLens közvetlenül a választott alkalmazásba indul el.](images/201608-kioskmode-400px.png)

- **Mobil Eszközkezelés (MDM) a HoloLenshez.** Az IT-részleg egyszerre több HoloLens-eszközt is kezelhet olyan megoldásokkal, mint Microsoft Intune. Kezelheti a beállításokat, kiválaszthatja a telepíteni kívánt alkalmazásokat, és beállíthatja a szervezet igényeinek megfelelő biztonsági konfigurációkat.

  ![A Eszközkezelés a HoloLensben vállalati szintű eszközkezelést biztosít több eszközön.](images/201608-enterprisemanagement-400px.png)

- **Windows Update Vállalatoknak.** Windows Update Vállalatoknak operációs rendszer vezérelt frissítéseit biztosítja az eszközökhöz, és támogatja a hosszú távú karbantartási csatornát.
- **Adatbiztonság.** A BitLocker adattitkosítás engedélyezve van a HoloLensben, hogy ugyanolyan szintű biztonságot nyújtson, mint bármely más Windows-eszköz.
- **Munkahelyi hozzáférés.** A szervezeten belül bárki távolról csatlakozhat a vállalati hálózathoz virtuális magánhálózaton (VPN) keresztül a HoloLensen. A HoloLens a hitelesítő adatokat Wi-Fi hálózatokhoz is hozzáférhet.
- **Microsoft Store Vállalatoknak.** Az IT-részleg egy olyan vállalati privát áruházat is beállíthat, amely csak a cég alkalmazásait tartalmazza az Adott HoloLens-használathoz. A vállalati szoftvereket biztonságosan terjesztheti a vállalati felhasználók kiválasztott csoportjának.

## <a name="feature-comparison-between-editions"></a>Funkciók összehasonlítása a kiadások között

|Funkciók |HoloLens (1. generációs) Development Edition |HoloLens (1. generációs) Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|Eszköztitkosítás (BitLocker) | |✔️ |✔️ |
|Virtuális magánhálózat (VPN) | |✔️ |✔️ |
|[Teljes képernyős mód](hololens-kiosk.md) | |✔️ |✔️ |
|**Felügyelet és üzembe helyezés** | | | |
|Mobileszköz-felügyelet (MDM) | |✔️ |✔️ |
|A igénylések igénylésének letiltási lehetősége | |✔️ |✔️ |
|Tanúsítványalapú vállalati Wi-Fi hozzáférés | |✔️ |✔️ |
|Microsoft Store (Fogyasztó) |Ügyfélszolgáltatások |Szűrés MDM használatával |Szűrés MDM használatával |
|[Vállalati áruház portálja](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Biztonság és identitás** | | | |
|Bejelentkezés Azure Active Directory (Azure AD-) fiókkal |✔️ |✔️ |✔️ |
|Bejelentkezés Microsoft-fiókkal (MSA) |✔️ |✔️ |✔️ |
|Új generációs hitelesítő adatok PIN-kód feloldásával |✔️ |✔️ |✔️ |
|[Biztonságos rendszerindítás](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Karbantartás és támogatás** | | | |
|Automatikus rendszerfrissítések érkezésükkor |✔️ |✔️ |✔️ |
|[Windows Update Vállalatoknak](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|Long-Term csatorna (LTSC) | |✔️ |✔️ |

## <a name="enabling-commercial-features"></a>Kereskedelmi funkciók engedélyezése

A szervezet rendszergazdája olyan kereskedelmi funkciókat állíthat be, mint a Microsoft Store Vállalatoknak, a kioszkmód és a Wi-Fi hozzáférés. Az [Microsoft HoloLens](index.yml) dokumentációja részletes útmutatást nyújt az eszközök regisztrálásához és alkalmazások telepítéséhez a Microsoft Store Vállalatoknak.

## <a name="see-also"></a>Lásd még

- [Microsoft HoloLens](index.yml)
- [Teljes képernyős mód](hololens-kiosk.md)
- [A HoloLens-eszközökön támogatott CSP-k](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store for Business és üzletági alkalmazások](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [Üzletági alkalmazások használata](/microsoft-store/working-with-line-of-business-apps)
