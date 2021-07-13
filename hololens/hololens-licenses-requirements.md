---
title: Licenckövetelmények
description: Tartsa naprakészen a mobileszköz-kezeléshez, a mobileszköz-kezeléshez, a HoloLens és a Remote Assisthöz szükséges licencelési követelményeket és irányelveket.
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
- HoloLens 2
ms.openlocfilehash: d0d8aa648df7901dec8636942e43aa549e626d7e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635891"
---
# <a name="license-requirements"></a>Licenckövetelmények

## <a name="hololens-2-device-managed"></a>HoloLens 2. eszköz (felügyelt)

[Azure AD-fiók](https://docs.microsoft.com/azure/active-directory/)

> [!IMPORTANT]
> Active Directory (AD) nem használható a HoloLens kezelésére.

[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) másik MDM-et.
- [Windows Autopilot for HoloLens 2](hololens2-autopilot.md)– leegyszerűsíti a kiépítési élményt mind a rendszergazdák, mind a végfelhasználók számára. A rendszergazdák előre konfigurálhatnak HoloLens 2 szabályzatot, és az első rendszerindításkor az eszközök a végfelhasználói beavatkozás nélkül, üzleti használatra kész állapotba lesznek telepítve. 

  > [!NOTE]
  > Windows Az Autopilot használatához [először az Azure P1-et](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) és az automatikus regisztrációt kell konfigurálni a kis érintéssel használható AutoPilot-folyamathoz és az eszközök üzembe helyezéséhez. [](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) 

### <a name="business-use-case"></a>Üzleti felhasználás esete: 

- ["A" üzembe](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) helyezési forgatókönyv – koncepció igazolása vagy próbatelepítés.

- [B üzembe helyezési](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) forgatókönyv – nagy léptékű üzembe helyezés.

## <a name="hololens-2-device-only-non-managed"></a>HoloLens 2. csak eszköz (nem felügyelt)

Microsoft-fiók (MSA) vagy helyi fiók használata esetén nincs szükség további licencre ezekhez a fiókokhoz.

[Helyi fiók](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts)

- Ezt a fiókot [előre](hololens-provisioning.md#provisioning-package-hololens-wizard) ki kellépítenünk a Windows Configuration Designer (WCD) használatával.

[Microsoft-fiók (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> Az ilyen fiókokat használó eszközök esetében nem támogatott több felhasználó használata.

### <a name="business-use-case"></a>Üzleti felhasználás esete: 

- [C telepítési forgatókönyv](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) – offline vagy biztonságos üzembe helyezés.
 
## <a name="dynamics-365-licensing-and-requirements"></a>Dynamics 365 – Licencelés és követelmények

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>Rendszergazda

- Azure AD-fiók (az előfizetés megvásárlásához és a licencek hozzárendeléséhez szükséges)
- [Remote Assist-előfizetés](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (vagy [Remote Assist próbaverzió)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist-felhasználó

- Azure AD-fiók

- Remote Assist-licenc 

  > [!NOTE]
  > Microsoft Teams Remote Assist csomaggal van csomagolva

- Hálózati kapcsolat

#### <a name="microsoft-teams-user"></a>Microsoft Teams felhasználó

- Azure AD-fiók

- Microsoft Teams vagy [Teams Freemium .](https://products.office.com/microsoft-teams/free)

- Hálózati kapcsolat

Ha ezt a [több-bérlős](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)forgatókönyvet tervezi, előfordulhat, hogy információs korlátok licencre van szüksége. Ebből [a cikkből megállapíthatja,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) hogy szükség van-e information barrier licencre.

### <a name="dynamics-365-guides"></a>Dynamics 365-útmutatók 

#### <a name="admin"></a>Rendszergazda

- Azure AD-fiók (az előfizetés megvásárlásához és a licencek hozzárendeléséhez szükséges)
- Dynamics 365 [Guides-előfizetés vagy ingyenes próbaverzió](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Útmutatók szerzője

1. Azure AD-fiók
1. [Dynamics 365 Guides-licenc](/dynamics365/mixed-reality/guides/requirements)
1. Számítógépekre vagy számítógépekre telepített Dynamics 365-útmutatók HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (az Analytics-irányítópult megtekintésére használatos)
1. Szerzői szerepkör (útmutatók létrehozásához)
1. Hálózati kapcsolat

#### <a name="guides-user"></a>Útmutatók felhasználója

1. Azure AD-fiók
1. [Dynamics 365 Guides-licenc](/dynamics365/mixed-reality/guides/requirements)
1. Telepített Dynamics 365-útmutatók HoloLens
1. Operátori szerepkör (teszteléshez vagy útmutatókhoz)
1. Hálózati kapcsolat
