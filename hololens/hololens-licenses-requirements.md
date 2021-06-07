---
title: Licenckövetelmények
description: Tartsa naprakészen a mobileszköz-felügyelethez, a HoloLenshez és a Remote Assisthez szükséges licencelési követelményeket és irányelveket.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379593"
---
# <a name="license-requirements"></a>Licenckövetelmények

## <a name="mobile-device-management-mdm-licenses-guidance"></a>Útmutató a Eszközkezelés (MDM) licencekkel kapcsolatos útmutatóhoz

Ha HoloLens-eszközei felügyeletét tervezi, szüksége lesz az Azure AD-re és egy MDM-re. Az Active Director (AD) nem használható HoloLens-eszközök kezelésére.
Ha az Intune-on kívül más MDM-et is használni Azure Active Directory [licenc](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) szükséges.
Ha az Intune-t tervezi MDM-ként [](https://docs.microsoft.com/intune/fundamentals/licenses) használni, olvassa el az Intune-licenceket is magában foglaló csomagok listáját. **Vegye figyelembe, hogy a csomagok többsége tartalmazza az Azure AD-t.**

## <a name="identify-the-licenses-needed-for-your-scenario-and-products"></a>A forgatókönyvhöz és a termékekhez szükséges licencek azonosítása

### <a name="hololens-1st-gen-licenses-requirements"></a>HoloLens (1. generációs) licenckövetelmények

Előfordulhat, hogy frissítenie kell a HoloLens-eszközt (1. generációs) a Windows Holographic for Business. (Annak megállapításához, hogy szükség van-e a frissítésre, tekintse meg a [HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions) kereskedelmi funkcióit.

 Ha igen, a következőket kell megtennie:

- HoloLens Enterprise-licenc XML-fájl létrehozása
- Alkalmazza az XML-fájlt a HoloLensre. Ezt egy kiépítési csomaggal [vagy](hololens-provisioning.md) a [Mobile Eszközkezelő](https://docs.microsoft.com/intune/configuration/holographic-upgrade)

### <a name="remote-assist-license-requirements"></a>Remote Assist licenckövetelmények

Győződjön meg arról, hogy a szükséges licencekkel és eszközzel van, amelyeket a követelmények dokumentációjában [talál.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)

1. [Remote Assist-licenc](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. Vagy próbálkozzon a [Remote Assist próbaverzióval](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
1. [Teams Freemium/Teams](https://products.office.com/microsoft-teams/free)
1. [Azure Active Directory (Azure AD) licenc](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

Ha ezt a **[több-bérlős](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** forgatókönyvet tervezi, előfordulhat, hogy információs korlátok licencre van szüksége. Ebből a [cikkből megállapíthatja,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) hogy szükség van-e information barrier licencre.

### <a name="guides-license-requirements"></a>Útmutatók licenckövetelményei

Tekintse meg a [frissített licencelési és eszközkövetelményeket.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)

1. [Azure Active Directory (Azure AD) licenc](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [Útmutatók](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
