---
title: Licenckövetelmények
description: Tartsa naprakészen a mobileszköz-kezeléshez, a mobileszköz-kezeléshez, a HoloLens és a Remote Assisthöz szükséges összes licencelési követelményt és útmutatót.
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
ms.openlocfilehash: 6224cd5e07794d9fca3c0a406e787d1a3fd88b43
ms.sourcegitcommit: bd55edcc855e20d6709c7e535573f43785155d41
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/24/2021
ms.locfileid: "114661712"
---
# <a name="license-requirements"></a>Licenckövetelmények

## <a name="overview"></a>Áttekintés
Ez az oldal magas szintű áttekintést nyújt a felügyelt és a nem felügyelt HoloLens 2 eszköz a szervezetben való üzembe helyezéséhez szükséges licencekről és fiókokról. A Dynamics 365 Remote Assist és [útmutatók licencelési](#dynamics-365-remote-assist) információit [is tartalmazza.](#dynamics-365-guides)

## <a name="hololens-2-license-and-account-requirements"></a>HoloLens 2 licenc- és fiókkövetelmény

 
|       &nbsp;      | Felügyelt HoloLens | Nem HoloLens |
|-------------------|-----------------|---------------------|
| **Üzleti felhasználás esete** | | |
| [Üzembe helyezés felhőhöz csatlakoztatott eszközökön – koncepció igazolása/próbatelepítés](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [Üzembe helyezés a szervezet hálózatán belül – nagy léptékű üzembe helyezés](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [Üzembe helyezés biztonságos offline környezetben](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **Licencek** | | |
| Azure Active Directory | ✔️ | |
| MDM (Intune<sup>1</sup> vagy <sup>2</sup>) | ✔️  | |
| **Fiókok** |  | |
| Azure AD-rendszergazdai fiók | ✔️ |  |
| Azure AD felhasználói fiók | ✔️ | |
| [Microsoft-fiók (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [Helyi fiók](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- <sup>1.</sup> [Automatikus regisztráció az](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) eszköz kezdeti beállítása során, amely regisztrálja a Azure Active Directory, és lehetővé teszi az eszköz Intune-nal való felügyeletét.
- <sup>2</sup> [Windows Autopilot for HoloLens 2](hololens2-autopilot.md) leegyszerűsíti a kiépítési élményt mind a rendszergazdák, mind a végfelhasználók számára. A rendszergazdák előre konfigurálni HoloLens 2 szabályzatot, és az első rendszerindításkor az eszközök a végfelhasználói beavatkozás nélkül, üzleti használatra kész állapotba lesznek telepítve.
- <sup>3</sup> Ezt a fiókot [előre](hololens-provisioning.md#provisioning-package-hololens-wizard) ki kellépítenünk a Windows Configuration Designer (WCD) használatával.

> [!IMPORTANT]
> Active Directory (AD) nem használható a HoloLens kezelésére.
 
> [!WARNING]
> Az MSA-t vagy helyi fiókot használó eszközök nem támogatnak több felhasználót.

## <a name="dynamics-365-licensing-and-requirements"></a>Dynamics 365 – Licencelés és követelmények

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>Rendszergazda

- Azure AD-fiók (az előfizetés megvásárlásához és a licencek hozzárendeléséhez szükséges)
- [Remote Assist-előfizetés](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (vagy [Remote Assist próbaverzió)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist-felhasználó

- Azure AD-fiók

- Remote Assist-licenc 

  > [!NOTE]
  > Microsoft Teams Remote Assist csomaggal van csomagolva

- Hálózati kapcsolat

#### <a name="microsoft-teams-user"></a>Microsoft Teams felhasználó

- Azure AD-fiók

- Microsoft Teams [Freemium Teams vagy más](https://products.office.com/microsoft-teams/free)

- Hálózati kapcsolat

Ha ezt a [](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)több-bérlős forgatókönyvet tervezi, előfordulhat, hogy információ-korlátok licencre van szüksége. Ebből [a cikkből megállapíthatja,](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) hogy szükség van-e information barrier licencre.

### <a name="dynamics-365-guides"></a>Dynamics 365-útmutatók 

#### <a name="admin"></a>Rendszergazda

1. Azure AD-fiók (az előfizetés megvásárlásához és a licencek hozzárendeléséhez szükséges)
2. Dynamics 365-útmutatók [előfizetése vagy ingyenes próbaverziója](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Útmutatók szerzője

1. Azure AD-fiók
1. [Dynamics 365-útmutatók licence](/dynamics365/mixed-reality/guides/requirements)
1. Számítógépekre vagy számítógépekre telepített Dynamics 365-útmutatók HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (az Analytics-irányítópult megtekintésére használható)
1. Szerzői szerepkör (útmutatók létrehozásához)
1. Hálózati kapcsolat

#### <a name="guides-user"></a>Útmutatók felhasználója

1. Azure AD-fiók
1. [Dynamics 365-útmutatók licence](/dynamics365/mixed-reality/guides/requirements)
1. Dynamics 365-útmutatók alkalmazás telepítve HoloLens
1. Operátori szerepkör (teszteléshez vagy útmutatókhoz)
1. Hálózati kapcsolat
