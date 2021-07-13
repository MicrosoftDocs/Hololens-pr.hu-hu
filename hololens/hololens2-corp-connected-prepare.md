---
title: Üzembe helyezési útmutató – Vállalati csatlakoztatott HoloLens 2 Dynamics 365-útmutatók – Előkészítés
description: A Dynamics 365 útmutatóiból megtudhatja, hogyan HoloLens 2 eszköz vállalati hálózaton keresztüli regisztrálására.
keywords: HoloLens, felügyelet, céghez csatlakoztatott, Dynamics 365-útmutatók, AAD, Azure AD, MDM, Mobile Eszközkezelés
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 88e7d0614cf95f32eaa0434724eddbcb5b8cf863
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636979"
---
# <a name="prepare---corporate-connected-guide"></a>Előkészítés – Vállalati csatlakoztatott útmutató
## <a name="infrastructure-essentials"></a>Infrastructure Essentials
Mind a személyes, mind a vállalati telepítési forgatókönyvekben a Mobile Eszközkezelés (MDM) rendszer az Windows 10-eszközök üzembe helyezéséhez és kezeléséhez szükséges alapvető infrastruktúra, különösen a 2. HoloLens rendszer. A [prémium szintű Azure AD előfizetés](/azure/active-directory/fundamentals/active-directory-get-started-premium) ajánlott identitásszolgáltatóként, és **bizonyos** képességek támogatásához szükséges.

> [!NOTE]
> Bár a HoloLens 2 telepítése és kezelése mobileszközként történt, általában több felhasználó között megosztott eszközként használják.

## <a name="azure-active-directory"></a>Azure Active Directory
Az Azure AD egy felhőalapú címtárszolgáltatás, amely identitás- és hozzáférés-kezelési funkciókat biztosít. Az Microsoft Office 365 vagy Intune-t használó szervezetek már használják az Azure AD-t, amely három kiadással rendelkezik: Ingyenes, Prémium P1 és Prémium P2 (lásd a Azure Active Directory [kiadásokat).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Minden kiadás támogatja az Azure AD-eszközregisztrációt, de Prémium P1 szükséges az automatikus MDM-regisztráció engedélyezéséhez, amelyet később használni fog ebben az útmutatóban.
> [!Important]
> Elengedhetetlen, hogy legyen egy Azure AD HoloLens mivel az eszközök nem támogatják a helyszíni AD-csatlakozást. Ha még nem rendelkezik beállított Azure AD-beállításokkal, kövesse az első lépésekhez szükséges utasításokat, és hozzon létre egy új bérlőt [a Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>Identitáskezelés
Ebben az útmutatóban a [használt identitás](/hololens/hololens-identity) Azure AD-fiókok lesznek. Az Azure AD-fiókoknak számos előnye van, például:

- Az alkalmazottak Azure AD-fiókjukkal regisztrálják az eszközt az Azure AD-ban, és automatikusan regisztrálják azt a szervezet MDM-megoldásában (Azure AD+MDM – egy prémium szintű Azure AD-előfizetés szükséges [hozzá).](/azure/active-directory/fundamentals/active-directory-get-started-premium)
- Az Azure AD-fiókok további hitelesítési [lehetőségekkel](/hololens/hololens-identity) is Windows Hello [vállalati verzión keresztül.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) Az Írisz bejelentkezés mellett a felhasználók bejelentkeznek egy másik eszközről, vagy FIDO biztonsági kulcsokat használhatnak.

> [!WARNING] 
> Az alkalmazottak csak egy fiókot használhatnak egy eszköz inicializálására, ezért rendkívül fontos, hogy a szervezet szabályozza, hogy melyik **fiók legyen engedélyezve először.** A kiválasztott fiók határozza meg, hogy ki szabályozza az eszközt, és befolyásolja a felügyeleti képességeket.

## <a name="mobile-device-management"></a>Mobileszköz-kezelés
Microsoft Intune A Enterprise Mobility + Security része egy felhőalapú MDM-rendszer, amely a bérlőhöz csatlakoztatott eszközöket kezeli. A Office 365 az Intune az Azure AD-t használja az identitáskezeléshez, így az alkalmazottak ugyanazokkal a hitelesítő adatokkal regisztrálják az eszközöket az Intune-ban, amelyekkel bejelentkeznek az Office 365. Az Intune a teljes MDM-megoldás érdekében támogatja az egyéb operációs rendszereket (például iOS és Android) is. Ebben az útmutatóban az Intune-nal fogunk üzembe helyezést engedélyezni a belső hálózaton a 2. HoloLens használatával.
> [!Important] 
> A Mobile Eszközkezelés. Ha még nincs beállítva, kövesse ezt az útmutatót és az Intune első lépések útmutatóját.

> [!Important]
> Az útmutatók használatának érdekében Azure AD-fiókra van szükség.

> [!Note] 
> Több MDM-rendszer támogatja a Windows 10 és a legtöbb támogatja a személyes és vállalati eszközök üzembe helyezését. A szolgáltatást támogató MDM-Windows 10 Holographic a következők: AirWatch, MobileIron stb. A legtöbb iparágvezető MDM-szállító már támogatja az Azure AD-integrációt. Az Azure AD-t támogató MDM-szállítók legfrissebb listáját a következő [Azure Marketplace.](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)

## <a name="network-access"></a>Hálózati hozzáférés 
A Dynamics 365-útmutatók felhőalapú alkalmazások. Ha a hálózati rendszergazda rendelkezik jóváhagyólistával, előfordulhat, hogy hozzá kell adniuk a Dynamics 365-kiszolgálókhoz való csatlakozáshoz szükséges IP-címeket és/vagy végpontokat. [További információ az IP-címek és URL-címek tiltásának feloldásáról.](/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Tanúsítványok
A tanúsítványok azáltal növelik a biztonságot, hogy fiókhitelesítést, Wi-Fi, VPN-titkosítást és a webes tartalmak SSL-titkosítását biztosítják. Bár a rendszergazdák manuálisan kezelhetik a tanúsítványokat az eszközökön a kiépítési csomagokon keresztül, ajánlott eljárás az MDM-rendszert használni a tanúsítványok teljes életcikluson keresztüli kezelésére a regisztrációtól a megújításon és visszavonáson át. 

Az MDM-rendszer a regisztrálás után automatikusan üzembe tudja helyezni ezeket a tanúsítványokat az eszközök tanúsítványtárolóiban (amennyiben az MDM-rendszer támogatja az **Egyszerű tanúsítványigénylési protokoll (SCEP)** vagy a nyilvános kulcsú titkosítási **szabványokat #12 (PKCS #12).** [Ismerje meg a -hez használt](/mem/intune/protect/certificates-configure)tanúsítványtípusokat és Microsoft Intune. Az MDM lekérdezheti és törölheti is a regisztrált ügyféltanúsítványokat, vagy új beléptetési kérelmet aktiválhat az aktuális tanúsítvány lejárta előtt.

Ha az MDM-rendszerek már konfigurálva vannak tanúsítványokhoz, a Tanúsítványok és hálózati profilok előkészítése [HoloLens 2-hez referenciával](/hololens/hololens-certificates-network) kezdheti meg a tanúsítványok és profilok központi telepítését a HoloLens 2-es eszközökhöz.

## <a name="scep"></a>SCEP

Az SCEP-telepítéshez a következő szolgáltatások szükségesek, a Web alkalmazásproxy kivételével.

- [Hitelesítésszolgáltató](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES-kiszolgálói szerepkör](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune Csatlakozó](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Az NDES URL-címet a vállalati hálózaton kívül is közzé kell tenni az [Azure AD alkalmazásproxy vagy a webelérési proxy használatával.](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) Másik választott fordított proxyt is használhat.

![SCEP-adatfolyam](./images/hololens2-scep-info-flow.png)

Ha a hálózata még nem támogatja az SCEP-t, vagy nem biztos benne, hogy a hálózata megfelelően van beállítva az SCEP-hez az Intune-nal, akkor az Infrastruktúra konfigurálása az SCEP Intune-nal való támogatására való konfigurálásról nyújt [segítséget.](/mem/intune/protect/certificates-scep-configure)

Ha az infrastruktúra már támogatja az SCEP-t, létre kell hoznia egy profilt [minden](/mem/intune/protect/certificates-profile-scep) olyan SCEP-tanúsítványhoz, amit [a](/mem/configmgr/protect/deploy-use/create-certificate-profiles) HoloLens 2 használni fog. Ha SCEP-problémái vannak, használja az SCEP-tanúsítványprofilok használatának hibaelhárítása tanúsítványokat az SCEP-tanúsítványprofilokkal való [Microsoft Intune.](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)

## <a name="pkcs"></a>PKCS
Az Intune a titkos és nyilvános kulcspáros (PKCS-) tanúsítványok használatát is támogatja. További [információ: Use private and public key certificates in Microsoft Intune use private and public key certificates in Microsoft Intune.](/mem/intune/protect/certificates-pfx-configure)

## <a name="proxy"></a>Proxy
A legtöbb vállalati intranetes hálózat proxyt használ a külső forgalom kezelésére. A HoloLens 2-ben konfigurálhat proxykiszolgálót Ethernet-, hálózati és VPNWi-Fi kapcsolatok létesítése esetén.

A proxyknak és a proxyk konfigurálásának több típusa is létezik. Ebben az útmutatóban a Wi-Fi proxyt választjuk, PAC URL-címen keresztül adhatja meg **és MDM-en keresztül helyezheti üzembe.** Ez azzal az előnnyel jár, hogy az MDM-en keresztül történik az automatikus üzembe helyezés, a PAC-fájl frissítése a kiszolgáló:port konfiguráció helyett Wi-Fi, végül pedig proxy konfigurálása proxy használatával, amely csak egyetlen Wi-Fi-kapcsolatra vonatkozik, így az eszközök akkor is használhatók, ha más helyen csatlakoznak.

További részletek a proxybeállításokról a Windows 10: [Create a Wi-Fi profile for devices in Microsoft Intune - Azure](/mem/intune/configuration/wi-fi-settings-configure).

## <a name="line-of-business-apps"></a>Üzletági alkalmazások 
Bár számos alkalmazás telepíthető a Microsoft Store, valószínű, hogy saját egyéni alkalmazással is van, amelyet kifejezetten vegyes valóságban való használatra hozott létre. Ezeket az üzleti szervezetben elosztott egyéni alkalmazásokat üzletági (LOB) alkalmazásoknak nevezzük.
  
Az alkalmazásokat többféleképpen is üzembe helyezheti HoloLens 2 eszközön. Az alkalmazások telepíthetők közvetlenül az MDM-ről, a Microsoft Store Vállalatoknak (MSfB) vagy közvetlenül telepíthetők egy kiépítési csomagon keresztül. Az útmutató kedvéért MDM-en keresztül telepítünk alkalmazásokat a szükséges alkalmazástelepítés használatával. Ez lehetővé teszi, hogy az LOB-alkalmazások automatikusan letöltődtek a HoloLens eszközökre, miután befejezték a regisztrációt.

Azok számára, akik nem a saját LOB-jukkal, biztosítunk egy mintaalkalmazást az üzembe helyezési folyamat teszteléséhez. Ez az alkalmazás lesz az [MRTK-példák](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) alkalmazás, és már előre felépítették és becsomagolták a koncepció igazolásának teszteléséhez.

Az alkalmazástelepítéssel kapcsolatos további részleteket az [Alkalmazáskezelés: Áttekintés témakörben talál.](/hololens/app-deploy-overview)

> [!NOTE]
> HoloLens 2. része csak az UWP ARM64-alkalmazások futtatását támogatja.

## <a name="guides-playbook"></a>Útmutatók – forgatókönyv
Az útmutatók microsoftos adatverzum-környezetet használ adattárként az útmutatók alkalmazáshoz. Fontos, hogy jobban át tudja látni, hogyan kommunikál az adatverzum-környezet az útmutatók alkalmazásaival és a bérlővel. Ebben az útmutatóban nem fedjük le az adatverzum kezelését, de tekintse át a [Dynamics 365-útmutatók – Dynamics 365-útmutatók](/dynamics365/mixed-reality/guides/admin-deployment-playbook)üzembe helyezésének alapvető Mixed Reality.

## <a name="next-step"></a>Következő lépés 
> [!div class="nextstepaction"]
> [Vállalati csatlakoztatott üzembe helyezés – Konfigurálás](hololens2-corp-connected-configure.md)