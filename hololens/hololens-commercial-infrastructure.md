---
title: Infrastruktúra-irányelvek HoloLens
description: Ismerje meg a hálózati eszközök infrastruktúrával kapcsolatos irányelveit HoloLens beleértve a vezeték nélküli hálózat támogatását, a távsegítség és a mobileszköz-kezelés kezelését.
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
ms.openlocfilehash: e3f87c524ce0f8af05ec8c92877d46facd962fb4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639284"
---
# <a name="configure-your-network-for-hololens"></a>A hálózat konfigurálása HoloLens

A dokumentum ezen részében a következő személyekre lesz szükség:

1. Hálózati rendszergazda, aki rendelkezik a proxy/tűzfal módosításaihoz szükséges engedélyekkel
2. Azure Active Directory Admin
3. Mobileszközök Eszközkezelő rendszergazdája

## <a name="infrastructure-requirements"></a>Infrastruktúrakövetelmények

HoloLens lényegében egy azure Windows integrált mobileszköz.  Kereskedelmi környezetekben működik a vezeték nélküli hálózattal (Wi-Fi) és hozzáféréssel a Microsoft-szolgáltatások.

A kritikus fontosságú felhőszolgáltatások közé tartoznak a következők:

- Azure active directory (Azure AD)
- Windows Frissítés (WU)

A kereskedelmi ügyfeleknek nagyvállalati mobilitási felügyeleti (EMM) vagy mobileszköz-kezelési (MDM) infrastruktúrára van szükségük a nagy HoloLens kezeléséhez.  Ez az útmutató [Microsoft Intune,](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) bár a Microsoft Policy teljes körű támogatásával minden szolgáltató támogathatja a HoloLens.  Kérdezze meg a mobileszköz-kezelő szolgáltatót, hogy támogatja-e HoloLens 2.

HoloLens nem támogatja a felhővel nem leválasztott élmények egy korlátozott készletét.

### <a name="wireless-network-eap-support"></a>Vezeték nélküli hálózat EAP-támogatása

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>HoloLens Konkrét hálózati követelmények

Győződjön meg arról, [hogy a végpontok](hololens-offline.md) listája engedélyezve van a hálózati tűzfalon. Ez lehetővé teszi a HoloLens megfelelő működését.

### <a name="remote-assist-specific-network-requirements"></a>A Remote Assist konkrét hálózati követelményei

1. A Remote Assist optimális teljesítményéhez ajánlott sávszélesség 1,5 Mb/s. További [információkért tekintse meg a részletes hálózati](/MicrosoftTeams/prepare-network) követelményeket.
**(Vegye figyelembe, hogy ha a hálózaton nincs legalább 1,5 MB/s sebességű hálózati sebesség, a Remote Assist továbbra is működni fog. A minőség azonban rossz lehet).**
1. Győződjön meg arról, hogy ezek a portok és URL-címek engedélyezve vannak a hálózati tűzfalon a Microsoft Teams működéséhez. Maradjon naprakész a legújabb [portlistával.](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

- További információ a Remote Assist konkrét [hálózati követelményeiről.](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements) 
- További információ arról, hogyan [készítheti elő a](/MicrosoftTeams/prepare-network) szervezet hálózatát a Microsoft Teams

### <a name="guides-specific-network-requirements"></a>Útmutatók konkrét hálózati követelményekhez

Az útmutatók csak az alkalmazás letöltéséhez és használatához igényelnek hálózati hozzáférést.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory Útmutatást

> [!NOTE]
> Erre a lépésre csak akkor van szükség, ha a vállalata az adatok HoloLens.

1. Győződjön meg arról, hogy rendelkezik Azure AD-licenccel.
További [HoloLens tekintse meg a licenckövetelményeket.](hololens-licenses-requirements.md)

1. Ha automatikus regisztrációt tervez használni, konfigurálnia kell az [Azure AD-regisztrációt.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Győződjön meg arról, hogy a vállalat felhasználói a Azure Active Directory (Azure AD) vannak.
A felhasználók [hozzáadásához kövesse](/azure/active-directory/fundamentals/add-users-azure-active-directory) az alábbi utasításokat.

1. Javasoljuk, hogy azok a felhasználók, akiknek hasonló licencre van szükségük, ugyanoda a csoportba kerülnek.
    1. [Csoport létrehozása](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Felhasználók hozzáadása csoportokhoz](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Győződjön meg arról, hogy a vállalat felhasználóihoz (vagy felhasználói csoportjához) hozzá van rendelve a szükséges licencek.
Ha licenceket kell hozzárendelni, kövesse az [alábbi utasításokat.](/azure/active-directory/fundamentals/license-users-groups)

1. Ezt a lépést csak akkor tegye meg, ha a felhasználóknak regisztrálniuk kell HoloLens/Mobile-eszközüket az Ön számára (három lehetőség van). Ezek a lépések biztosítják, hogy a vállalat felhasználói (vagy felhasználói csoportok) eszközöket adhatnak hozzá.
    1. **1. lehetőség:** Adjon engedélyt minden felhasználónak az eszközök Azure AD-hez való csatlakozásához.
**Jelentkezzen be a Azure Portal rendszergazdaként**  >  **Azure Active Directory**  >  **Eszközök**  >  **Eszköz Gépház**  >
 **Állítsa a Users may join devices to Azure AD (Felhasználók csatlakozhatnak az eszközökhöz az Azure AD-be) *beállítását All (Mind)***

    1. **2. lehetőség:** Adjon engedélyt a kiválasztott felhasználóknak/csoportoknak az eszközök Azure AD-be való beléptetését az **Azure Portal-ba**  >  **rendszergazdaként Azure Active Directory**  >  **Gépház-eszközök** eszközkészlete Felhasználók csatlakozhatnak az Azure  >    >
 **AD-hez** a Kiválasztott rendszerképhez, amely az Azure 
 ![ AD-hez csatlakozott eszközök konfigurációját mutatja](images/azure-ad-image.png)

    1. **3. lehetőség:** Letilthatja, hogy az összes felhasználó az eszközeit a tartományhoz csatlakozzon. Ez azt jelenti, hogy minden eszközt manuálisan kell regisztrálni.

## <a name="mobile-device-manager-guidance"></a>Mobileszközök Eszközkezelő útmutató

### <a name="ongoing-device-management"></a>Folyamatban lévő eszközkezelés

> [!NOTE]
> Erre a lépésre csak akkor van szükség, ha a vállalata az alkalmazás HoloLens.

A folyamatos eszközkezelés a mobileszköz-kezelési infrastruktúrától függ.  A legtöbb esetben ugyanaz az általános funkció, de a felhasználói felület széles körben változhat.

1. [A CSP-k (konfigurációs szolgáltatók)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lehetővé teszi felügyeleti beállítások létrehozására és központi telepítésére a hálózaton elérhető eszközök számára. Referenciaként [tekintse meg a HoloLens CSP-k](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) listáját.

1. [A megfelelőségi szabályzatok](/intune/device-compliance-get-started) olyan szabályok és beállítások, amelyeknek az eszközöknek meg kell felelnie, hogy megfeleljenek a vállalati infrastruktúrának. Ezeket a szabályzatokat feltételes hozzáféréssel használva letilthatja a nem megfelelő eszközök vállalati erőforrásaihoz való hozzáférést. Létrehozhat például olyan szabályzatot, amely megköveteli a Bitlocker engedélyezését.

1. [Megfelelőségi szabályzat létrehozása.](/intune/protect/compliance-policy-create-windows)

1. A feltételes hozzáférés engedélyezi/letiltja a mobileszközök és mobilalkalmazások hozzáférését a vállalati erőforrásokhoz. Két dokumentum, amelyek hasznosak lehetnek, a [CA üzembe helyezésének megterve és](/azure/active-directory/conditional-access/plan-conditional-access) az ajánlott [eljárások.](/azure/active-directory/conditional-access/best-practices)

1. [Ez a cikk](/intune/fundamentals/windows-holographic-for-business) az Intune felügyeleti eszközeit tárgyalja HoloLens.

1. [Eszközprofil létrehozása](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Frissítések kezelése

Az Intune frissítési körök nevű funkciót tartalmaz a Windows 10-eszközökhöz, beleértve a HoloLens 2-es és HoloLens 1-es (Holographic for Business verzióval) funkciókat. A frissítési körök olyan beállításokat tartalmaznak, amelyek meghatározzák a frissítések telepítésének mikéntját és mikorját.

Létrehozhat például egy karbantartási időszakot a frissítések telepítésére vagy eldöntheti, hogy kíván-e újraindítást a frissítések telepítése után.  Dönthet úgy is, hogy határozatlan időre felfüggeszti a frissítéseket, amíg készen nem áll a frissítésre.

További információ a [frissítési körök Intune-nal való konfigurálásával kapcsolatban.](/intune/windows-update-for-business-configure)

### <a name="application-management"></a>Alkalmazáskezelés

A HoloLens kezelése a következőn keresztül:

1. Microsoft Store  
  A Microsoft Store a legjobb módszer az alkalmazások terjesztésére és HoloLens.  Az áruházban már elérhető alapalkalmazások HoloLens, de saját alkalmazásokat is [közzétehet.](/windows/uwp/publish/)  
  Az áruházban található összes alkalmazás nyilvánosan elérhető mindenki számára, de ha nem elfogadható, tekintse meg a Microsoft Store Vállalatoknak.  

1. [Vállalati Microsoft Áruház](/microsoft-store/)  
  Microsoft Store Vállalatoknak és Az Education egy egyéni áruház a vállalati környezethez.  Lehetővé teszi, hogy a Microsoft Store beépített Windows 10 és HoloLens megkeresheti, beszerezheti, terjesztheti és kezelheti a szervezet alkalmazásait.  Emellett lehetővé teszi olyan alkalmazások üzembe helyezését is, amelyek csak a kereskedelmi környezetére vonatkoznak, a világra nem.

1. Alkalmazások központi telepítése és kezelése az Intune-nal vagy más mobileszköz-kezelési megoldással  
  A legtöbb mobileszköz-kezelési megoldás, beleértve az Intune-t is, lehetővé teszi üzletági alkalmazások közvetlen üzembe helyezését regisztrált eszközökre.  Az Intune [alkalmazástelepítésről ebben a cikkben talál további részleteket.](/intune/apps-deploy)

1. _nem ajánlott_ Eszközportál  
  Az alkalmazások közvetlenül a HoloLens is telepíthetők Windows Eszközportál.  Ez nem ajánlott, mivel a fejlesztői módot engedélyezni kell az eszközportál használatára.

További információ az [alkalmazások telepítéséről a HoloLens.](hololens-install-apps.md)

### <a name="certificates"></a>Tanúsítványok

A tanúsítványokat az MDM-szolgáltatón keresztül terjesztheti. Ha a vállalata tanúsítványokat igényel, az Intune támogatja a PKCS, a PFX és az SCEP-tanúsítványokat. Fontos tisztában lennie a vállalat számára megfelelő tanúsítvánnyal. Tekintse meg [a tanúsítványkonfigurációk dokumentációját](/intune/protect/certificates-configure) annak meghatározásához, hogy melyik tanúsítvány a legmegfelelőbb az Ön számára. Ha tanúsítványokat tervez használni HoloLens hitelesítéshez, a PFX vagy az SCEP megfelelő lehet az Ön számára.

Az SCEP használatának lépései a [következők.](/intune/protect/certificates-profile-scep)

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Frissítés a Holographics for Business Commercial Suite-hoz

> [!NOTE]
> Windows A Holographics for Business (kereskedelmi csomag) csak HoloLens 1. generációs eszközökhöz használható. A profil nem lesz alkalmazva 2 HoloLens eszközre.

A kereskedelmi csomagra való frissítésre vonatkozó utasításokat a [holografikus](/intune/configuration/holographic-upgrade) frissítési dokumentációban találja.

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Kioszkmód konfigurálása a Microsoft Intune

1. Szinkronizálja Microsoft Store Intune-nal (lásd az alábbi [utasításokat).](/intune/apps/windows-store-for-business)

1. Az alkalmazásbeállítások ellenőrzése
    1. Jelentkezzen be Microsoft Store üzleti fiókjába
    1. **Az > termékek és szolgáltatások kezelése > Alkalmazások és szoftverszolgáltatások > Válassza ki > Privát áruház rendelkezésre állása lehetőséget, majd > válassza > "Mindenki" vagy "Adott csoportok" lehetőséget.**
        >[!NOTE]
        >Ha nem látja a kívánt alkalmazást, az áruházban való kereséssel "le kell szereznie" az alkalmazást. Kattintson a jobb felső sarokban található "Keresés" > be az alkalmazás nevét, majd > kattintson az alkalmazásra, és **> a "Bekeresés" lehetőséget.**
    1. Ha nem látja az **alkalmazásokat** az Intune-ban > Client Apps > Apps alkalmazásban, előfordulhat, hogy újra [szinkronizálni](/intune/apps/windows-store-for-business#synchronize-apps) kell az alkalmazásokat.

1. [Eszközprofil létrehozása kioszkmódhoz](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> A különböző felhasználókat úgy konfigurálhatja, hogy különböző kioszkmódú felhasználói felületekkel használja az "Azure AD"-t a "Felhasználói bejelentkezés típusa" beállítással. Ez a lehetőség azonban csak többalkalmazásos kioszkmódban érhető el. A többalkalmazásos kioszkmód csak egy alkalmazással és több alkalmazással is működik.

![A kioszkmód Intune-nal való konfigurálást bemutató kép](images/aad-kioskmode.png)

Más MDM-szolgáltatásokhoz a szolgáltató dokumentációjában talál útmutatást. Ha egyéni beállítást és teljes XML-konfigurációt kell használnia egy [kioszk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) MDM-szolgáltatásban való beállítására, tekintse meg a teljes képernyős HoloLens utasításokat.

## <a name="certificates-and-authentication"></a>Tanúsítványok és hitelesítés

A tanúsítványok MDM-en keresztül telepíthetők (lásd az [MDM szakasz "tanúsítványok" szakaszát).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance) A tanúsítványok a csomag kiépítése HoloLens is üzembe helyezhetők. További [információkért HoloLens provisioning (Kiépítés)](hololens-provisioning.md) oldalon található.

### <a name="additional-intune-quick-links"></a>Az Intune további gyorshivatkozásai

1. [Profilok létrehozása:](/intune/configuration/device-profile-create) A profilok lehetővé teszik a szervezet eszközeire lekért beállítások hozzáadását és konfigurálát.

