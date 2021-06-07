---
title: Infrastruktúra-irányelvek a HoloLenshez
description: Ismerje meg a HoloLens-eszközök infrastruktúrával kapcsolatos irányelveit, beleértve a vezeték nélküli hálózatok támogatását, a távsegítség és a mobileszköz-kezelés kezelését.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4eb55bec56e53de9195ac87e0491eefd91992f3d
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379517"
---
# <a name="configure-your-network-for-hololens"></a>A hálózat konfigurálása a HoloLenshez

A dokumentum ezen részében a következő személyekre lesz szükség:

1. Hálózati rendszergazda, aki rendelkezik a proxy/tűzfal módosításaihoz szükséges engedélyekkel
2. Azure Active Directory rendszergazda
3. Mobil Eszközkezelő-rendszergazda

## <a name="infrastructure-requirements"></a>Infrastruktúrakövetelmények

A HoloLens lényegében egy Azure-ral integrált Windows-mobileszköz.  Kereskedelmi környezetekben működik a legjobban vezeték nélküli hálózattal (Wi-Fi) és hozzáféréssel a Microsoft-szolgáltatások.

A kritikus fontosságú felhőszolgáltatások közé tartoznak a következők:

- Azure active directory (Azure AD)
- Windows Update (WU)

A kereskedelmi ügyfeleknek nagyvállalati mobilitási felügyeleti (EMM) vagy mobileszköz-kezelési (MDM) infrastruktúrára van szükségük a HoloLens-eszközök nagy léptékű felügyeletéhez.  Ez az útmutató [Microsoft Intune,](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) bár a Microsoft Policy teljes körű támogatásával minden szolgáltató támogathatja a HoloLenst.  Kérdezze meg mobileszköz-kezelő szolgáltatóját, hogy támogatják-e a HoloLens 2-t.

A HoloLens a felhővel nem kapcsolatos élmények egy korlátozott készletét támogatja.

### <a name="wireless-network-eap-support"></a>Vezeték nélküli hálózat EAP-támogatása

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>HoloLens-specifikus hálózati követelmények

Győződjön meg arról, [hogy a végpontok](hololens-offline.md) listája engedélyezve van a hálózati tűzfalon. Ez lehetővé teszi a HoloLens megfelelő működését.

### <a name="remote-assist-specific-network-requirements"></a>A Remote Assist konkrét hálózati követelményei

1. A Remote Assist optimális teljesítményéhez ajánlott sávszélesség 1,5 Mb/s. További [információkért tekintse meg a részletes](https://docs.microsoft.com/MicrosoftTeams/prepare-network) hálózati követelményeket.
**(Vegye figyelembe, hogy ha a hálózaton nincs legalább 1,5 Mbbps hálózati sebesség, a Remote Assist továbbra is működni fog. A minőség azonban rossz lehet).**
1. Győződjön meg arról, hogy ezek a portok és URL-címek engedélyezve vannak a hálózati tűzfalon a Microsoft Teams működésének engedélyezéséhez. Maradjon naprakész a legújabb [portlistával.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

- További információ a Remote Assist konkrét [hálózati követelményeiről.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements) 
- További információ a szervezet hálózatának a [Microsoft Teamshez](https://docs.microsoft.com/MicrosoftTeams/prepare-network) való előkészítéséről

### <a name="guides-specific-network-requirements"></a>Útmutatók konkrét hálózati követelményekhez

Az útmutatók csak az alkalmazás letöltéséhez és használatához igényelnek hálózati hozzáférést.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory útmutató

> [!NOTE]
> Erre a lépésre csak akkor van szükség, ha a vállalata a HoloLens felügyeletét tervezi.

1. Győződjön meg arról, hogy rendelkezik Azure AD-licenccel.
További információkért tekintse meg a HoloLens-licenckövetelményeket. [](hololens-licenses-requirements.md)

1. Ha automatikus regisztrációt tervez használni, konfigurálnia kell az [Azure AD-regisztrációt.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Győződjön meg arról, hogy a vállalat felhasználói a Azure Active Directory (Azure AD) vannak.
A felhasználók [hozzáadásához kövesse](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) az alábbi utasításokat.

1. Javasoljuk, hogy azok a felhasználók, akiknek hasonló licencre van szükségük, ugyanoda a csoportba kerülnek.
    1. [Csoport létrehozása](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Felhasználók hozzáadása csoportokhoz](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Győződjön meg arról, hogy a vállalat felhasználóihoz (vagy felhasználói csoportjához) hozzá van rendelve a szükséges licencek.
Ha licenceket kell hozzárendelni, kövesse az [alábbi utasításokat.](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)

1. Ezt a lépést csak akkor tegye meg, ha a felhasználóknak regisztrálniuk kell a HoloLens-/mobileszközüket az Ön számára (három lehetőség van). Ezek a lépések biztosítják, hogy a vállalat felhasználói (vagy felhasználói csoportok) hozzáadhatnak eszközöket.
    1. **1. lehetőség:** Adjon engedélyt minden felhasználónak az eszközök Azure AD-hez való csatlakozásához.
**Jelentkezzen be a Azure Portal rendszergazdaként**  >  **Azure Active Directory**  >  **Eszközök**  >  **Eszközbeállítások**  >
 **Állítsa a Users may join devices to Azure AD (Felhasználók csatlakozhatnak az eszközökhöz az Azure AD-be) *beállítását All (Mind) beállításra***

    1. **2. lehetőség:** Adjon engedélyt a kiválasztott felhasználóknak/csoportoknak az eszközök Azure AD-be való beléptetését az **Azure Portal-ba** rendszergazdaként Azure Active Directory-eszközök eszközbeállításokkal Állítsa be, hogy a felhasználók az  >    >    >    >
 **Azure AD-hez** csatlakozva a Kiválasztott rendszerképhez csatlakozzanak, amely az 
 ![ Azure AD-hez csatlakozott eszközök konfigurációját mutatja](images/azure-ad-image.png)

    1. **3. lehetőség:** Letilthatja, hogy az összes felhasználó az eszközeit a tartományhoz csatlakozzon. Ez azt jelenti, hogy minden eszközt manuálisan kell regisztrálni.

## <a name="mobile-device-manager-guidance"></a>Mobileszközök Eszközkezelő útmutató

### <a name="ongoing-device-management"></a>Folyamatban lévő eszközkezelés

> [!NOTE]
> Erre a lépésre csak akkor van szükség, ha a vállalata a HoloLens kezelését tervezi.

A folyamatos eszközkezelés a mobileszköz-kezelési infrastruktúrától függ.  A legtöbb esetben ugyanaz az általános funkció, de a felhasználói felület széles körben változhat.

1. [A CSP-k (konfigurációs szolgáltatók)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lehetővé teszi felügyeleti beállítások létrehozására és központi telepítésére a hálózaton elérhető eszközök számára. Referenciaként [tekintse meg a HoloLens CSP-k](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) listáját.

1. [A megfelelőségi szabályzatok](https://docs.microsoft.com/intune/device-compliance-get-started) olyan szabályok és beállítások, amelyeknek az eszközöknek meg kell felelnie, hogy megfeleljenek a vállalati infrastruktúrának. Ezeket a szabályzatokat feltételes hozzáféréssel használva letilthatja a nem megfelelő eszközök vállalati erőforrásaihoz való hozzáférést. Létrehozhat például olyan szabályzatot, amely megköveteli a Bitlocker engedélyezését.

1. [Megfelelőségi szabályzat létrehozása.](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)

1. A feltételes hozzáférés engedélyezi/letiltja a mobileszközök és mobilalkalmazások hozzáférését a vállalati erőforrásokhoz. Két dokumentum, amelyek hasznosak lehetnek, a [CA üzembe helyezésének megterve és](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) az ajánlott [eljárások.](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)

1. [Ez a cikk](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) az Intune HoloLenshez szükséges felügyeleti eszközeit tárgyalja.

1. [Eszközprofil létrehozása](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Frissítések kezelése

Az Intune frissítési körök nevű funkciót tartalmaz a Windows 10-eszközökhöz, beleértve a HoloLens 2-t és a HoloLens v1-et (Holographic for Business verzióval). A frissítési körök olyan beállításokat tartalmaznak, amelyek meghatározzák a frissítések telepítésének mikéntját és mikorját.

Létrehozhat például egy karbantartási időszakot a frissítések telepítésére vagy eldöntheti, hogy kíván-e újraindítást a frissítések telepítése után.  Dönthet úgy is, hogy határozatlan időre felfüggeszti a frissítéseket, amíg készen nem áll a frissítésre.

További információ a [frissítési körök Intune-nal való konfigurálásával kapcsolatban.](https://docs.microsoft.com/intune/windows-update-for-business-configure)

### <a name="application-management"></a>Alkalmazáskezelés

HoloLens-alkalmazások kezelése a következőn keresztül:

1. Microsoft Store  
  A Microsoft Store a legjobb módja az alkalmazások Terjesztésének és fogyasztásának a HoloLensen.  Az áruházban már elérhető alapvető HoloLens-alkalmazások nagyszerű készlete érhető el, vagy közzéteheti [sajátját](https://docs.microsoft.com/windows/uwp/publish/)is.  
  Az áruházban található összes alkalmazás nyilvánosan elérhető mindenki számára, de ha nem elfogadható, tekintse meg a Microsoft Store Vállalatoknak.  

1. [Vállalati Microsoft Áruház](https://docs.microsoft.com/microsoft-store/)  
  Microsoft Store Vállalatoknak és az Education egy egyéni áruház a vállalati környezethez.  Lehetővé teszi az Microsoft Store és a HoloLens beépített Windows 10 a szervezet alkalmazásait megkeresheti, beszerezheti, terjesztheti és kezelheti.  Emellett lehetővé teszi olyan alkalmazások üzembe helyezését is, amelyek csak a kereskedelmi környezetére vonatkoznak, a világra nem.

1. Alkalmazások központi telepítése és kezelése az Intune-nal vagy más mobileszköz-kezelési megoldással  
  A legtöbb mobileszköz-kezelési megoldás, így az Intune is lehetővé teszi üzletági alkalmazások közvetlen üzembe helyezését regisztrált eszközökre.  Az Intune [alkalmazástelepítésről ebben a cikkben talál további részleteket.](https://docs.microsoft.com/intune/apps-deploy)

1. _nem ajánlott_ Eszközportál  
  Az alkalmazások közvetlenül a HoloLensre is telepíthetők a Windows eszközportál.  Ez nem ajánlott, mivel a fejlesztői módot engedélyezni kell az eszközportál használatára.

További információ az [alkalmazások HoloLensen való telepítéséről.](https://docs.microsoft.com/hololens/hololens-install-apps)

### <a name="certificates"></a>Tanúsítványok

A tanúsítványokat az MDM-szolgáltatón keresztül terjesztheti. Ha a vállalata tanúsítványokat igényel, az Intune támogatja a PKCS, a PFX és az SCEP-tanúsítványokat. Fontos tisztában lennie a vállalat számára megfelelő tanúsítvánnyal. Tekintse meg [a tanúsítványkonfigurációk dokumentációját](https://docs.microsoft.com/intune/protect/certificates-configure) annak meghatározásához, hogy melyik tanúsítvány a legmegfelelőbb az Ön számára. Ha holoLens-hitelesítéshez tervez tanúsítványokat használni, a PFX vagy az SCEP megfelelő lehet az Ön számára.

Az SCEP használatának lépései a [következők.](https://docs.microsoft.com/intune/protect/certificates-profile-scep)

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Frissítés a Holographics for Business Commercial Suite-hoz

> [!NOTE]
> A Windows Holographics for Business (kereskedelmi csomag) csak a HoloLens 1. generációs eszközökhöz használható. A profil nem lesz alkalmazva a HoloLens 2-eszközökre.

A kereskedelmi csomagra való frissítésre vonatkozó utasításokat a [holografikus](https://docs.microsoft.com/intune/configuration/holographic-upgrade) frissítés dokumentációjában találja.

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Kioszkmód konfigurálása a Microsoft Intune

1. Szinkronizálás Microsoft Store Intune-nal (lásd az alábbi [utasításokat).](https://docs.microsoft.com/intune/apps/windows-store-for-business)

1. Az alkalmazásbeállítások ellenőrzése
    1. Jelentkezzen be Microsoft Store vállalati fiókjába
    1. **Az >-termékek és -szolgáltatások kezelése > alkalmazások és szoftverek > Válassza ki azt az alkalmazást, amely szinkronizálni szeretné > Privát áruház rendelkezésre állási > Válassza a "Mindenki" vagy "Adott csoportok" lehetőséget.**
        >[!NOTE]
        >Ha nem látja a kívánt alkalmazást, az áruházban való kereséssel "le kell szereznie" az alkalmazást. Kattintson a jobb felső sarokban található "Keresés" > az alkalmazás nevére, majd > az alkalmazásra, és > **a "Get"** lehetőséget.
    1. Ha nem látja az alkalmazásait az **Intune-ban > Ügyfélalkalmazások** > Apps alkalmazásban, előfordulhat, hogy újra [szinkronizálni](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) kell az alkalmazásokat.

1. [Eszközprofil létrehozása kioszkmódhoz](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Az "Azure AD" felhasználói bejelentkezési típussal különböző kioszkmódú felhasználói élményt konfigurálhat a különböző felhasználók számára. Ez a lehetőség azonban csak többalkalmazásos kioszkmódban érhető el. A többalkalmazásos kioszkmód csak egy alkalmazással és több alkalmazással is működik.

![A kioszkmód Intune-nal való konfigurálást bemutató kép](images/aad-kioskmode.png)

Más MDM-szolgáltatásokhoz a szolgáltató dokumentációjában talál útmutatást. Ha egyéni beállítást és teljes XML-konfigurációt kell használnia egy kioszk beállítására az MDM-szolgáltatásban, tekintse meg a [HoloLens kioszk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) utasításait.

## <a name="certificates-and-authentication"></a>Tanúsítványok és hitelesítés

A tanúsítványok az MDM-en keresztül telepíthetők (lásd az [MDM szakasz "tanúsítványok" című szakaszát).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance) A tanúsítványok a HoloLensben is üzembe helyezhetők csomagbeépítéssel. További információt [a HoloLens provisioning (HoloLens-kiépítés)](hololens-provisioning.md) oldalon található.

### <a name="additional-intune-quick-links"></a>Az Intune további gyorshivatkozásai

1. [Profilok létrehozása:](https://docs.microsoft.com/intune/configuration/device-profile-create) A profilokkal olyan beállításokat adhat hozzá és konfigurálhatja, amelyek le lesznek állítva a szervezet eszközeire.

