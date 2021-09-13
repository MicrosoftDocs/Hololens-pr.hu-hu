---
title: Telepítési útmutató – Vállalati csatlakoztatott HoloLens 2 Dynamics 365-útmutatók – Előkészítés
description: A Dynamics 365-útmutatók segítségével megtudhatja, hogyan készítheti elő a HoloLens 2 eszköz vállalati csatlakoztatott hálózaton keresztüli regisztrálását.
keywords: HoloLens, felügyelet, vállalati csatlakoztatható, Dynamics 365-útmutatók, AAD, Azure AD, MDM, Mobile Eszközkezelés
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
ms.openlocfilehash: 5d8fc2eb0a8dafaae0e1b222b7451877975cf90b
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032684"
---
# <a name="prepare---corporate-connected-guide"></a>Előkészítés – Vállalati csatlakoztatott útmutató
## <a name="infrastructure-essentials"></a>Infrastruktúra – alapvető szolgáltatások
Mind a személyes, mind a vállalati telepítési forgatókönyvekben a Mobile Eszközkezelés-rendszer az alapvető infrastruktúra, amely az Windows 10-eszközök telepítéséhez és kezeléséhez szükséges, különösen a HoloLens 2. A [prémium szintű Azure AD előfizetés](/azure/active-directory/fundamentals/active-directory-get-started-premium) használata ajánlott identitásszolgáltatóként, és **bizonyos** képességek támogatásához szükséges.

> [!NOTE]
> Bár a HoloLens 2 mobileszközként van telepítve és kezelhető, általában több felhasználó között megosztott eszközként használják.

## <a name="azure-active-directory"></a>Azure Active Directory
Az Azure AD egy felhőalapú címtárszolgáltatás, amely identitás- és hozzáférés-kezelési funkciókat biztosít. Az Microsoft Office 365 vagy az Intune-t használó szervezetek már használják az Azure AD-t, amely három kiadással rendelkezik: Ingyenes, Prémium P1 és Prémium P2 (lásd a Azure Active Directory [kiadásokat).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Minden kiadás támogatja az Azure AD-eszközregisztrációt, de Prémium P1 szükséges az automatikus MDM-regisztráció engedélyezéséhez, amelyet később használni fog ebben az útmutatóban.
> [!Important]
> Elengedhetetlen, hogy legyen egy Azure AD HoloLens mivel az eszközök nem támogatják a helyszíni AD-csatlakozást. Ha még nem rendelkezik beállított Azure AD-vel, kövesse az első lépésekhez szükséges utasításokat, és hozzon létre egy új bérlőt [a Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>Identitáskezelés
Ebben az útmutatóban [a használt identitás](/hololens/hololens-identity) Azure AD-fiókok lesznek. Az Azure AD-fiókoknak számos előnye van, például:

- Az alkalmazottak Azure AD-fiókjukkal regisztrálják az eszközt az Azure AD-ban, és automatikusan regisztrálják azt a szervezet MDM-megoldásában (Azure AD+MDM – egy prémium szintű Azure AD-előfizetés [szükséges](/azure/active-directory/fundamentals/active-directory-get-started-premium)hozzá).
- Az Azure AD-fiókok további hitelesítési [lehetőségekkel is](/hololens/hololens-identity) Windows Hello [for Business használatával.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) Az Írisz bejelentkezés mellett a felhasználók bejelentkeznek egy másik eszközről, vagy FIDO biztonsági kulcsokat is használhatnak.

> [!WARNING] 
> Az alkalmazottak csak egy fiókot használhatnak egy eszköz inicializálására, ezért rendkívül fontos, hogy a szervezet először azt szabályozza, hogy melyik **fiók legyen engedélyezve.** A kiválasztott fiók határozza meg, hogy ki szabályozza az eszközt, és befolyásolja a felügyeleti képességeket.

## <a name="mobile-device-management"></a>Mobileszköz-kezelés
Microsoft Intune A Enterprise Mobility + Security része egy felhőalapú MDM-rendszer, amely a bérlőhöz csatlakoztatott eszközöket kezeli. A Office 365 az Intune az Azure AD-t használja az identitáskezeléshez, így az alkalmazottak ugyanazokkal a hitelesítő adatokkal regisztrálják az eszközöket az Intune-ban, amelyekkel bejelentkeznek az Office 365. Az Intune a teljes MDM-megoldás érdekében támogatja az egyéb operációs rendszereket (például iOS és Android) is. Ebben az útmutatóban az Intune-nal fogunk üzembe helyezést engedélyezni a belső hálózaton a 2. HoloLens használatával.
> [!Important] 
> A Mobile Eszközkezelés. Ha még nincs beállítva, kövesse ezt az útmutatót és az Intune első lépések útmutatóját.

> [!Important]
> Az útmutatók használatának érdekében Azure AD-fiókra van szükség.

> [!Note] 
> Több MDM-rendszer támogatja a Windows 10 és a legtöbb támogatja a személyes és vállalati eszközök üzembe helyezését. A szolgáltatást támogató MDM Windows 10 Holographic: AirWatch, MobileIron stb. A legtöbb iparágvezető MDM-szállító már támogatja az Azure AD-integrációt. Az Azure AD-t támogató MDM-szállítók legfrissebb listáját a következő [Azure Marketplace.](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)

## <a name="network-access"></a>Hálózati hozzáférés 
A Dynamics 365-útmutatók felhőalapú alkalmazások. Ha a hálózati rendszergazda rendelkezik egy jóváhagyólistával, előfordulhat, hogy hozzá kell adnia a Dynamics 365-kiszolgálókhoz való csatlakozáshoz szükséges IP-címeket és/vagy végpontokat. [További információ az IP-címek és URL-címek letiltásának feloldásáról.](/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Tanúsítványok
A tanúsítványok azáltal növelik a biztonságot, hogy fiókhitelesítést, Wi-Fi hitelesítést, VPN-titkosítást és a webes tartalmak SSL-titkosítását biztosítják. Bár a rendszergazdák manuálisan kezelhetik az eszközökön található tanúsítványokat a kiépítési csomagokon keresztül, ajánlott eljárás az MDM-rendszer használata a tanúsítványok kezelésére a teljes életciklusuk során – a regisztrációtól a megújításon és visszavonáson át. 

Az MDM-rendszer a regisztrálás után automatikusan üzembe tudja helyezni ezeket a tanúsítványokat az eszközök tanúsítványtárolóiban (amennyiben az MDM-rendszer támogatja az **Egyszerű tanúsítványigénylési protokoll (SCEP)** vagy a nyilvános **kulcsú titkosítási szabványokat #12 (PKCS #12).** [Ismerje meg a -hez használt](/mem/intune/protect/certificates-configure)tanúsítványtípusokat és Microsoft Intune. Az MDM lekérdezheti és törölheti is a regisztrált ügyféltanúsítványokat, vagy új beléptetési kérelmet aktiválhat az aktuális tanúsítvány lejárta előtt.

Ha az MDM-rendszerek már konfigurálva vannak tanúsítványokhoz, a Tanúsítványok és hálózati profilok előkészítése [a 2.](/hololens/hololens-certificates-network) HoloLens-hez referenciával kezdheti meg a tanúsítványok és profilok központi telepítését a HoloLens 2-es eszközökhöz.

## <a name="scep"></a>SCEP

Az SCEP-telepítéshez a következő szolgáltatások szükségesek, a Web alkalmazásproxy server kivételével.

- [Hitelesítésszolgáltató](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES kiszolgálói szerepkör](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune Csatlakozó](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Az NDES URL-címet a vállalati hálózaton kívül is közzé kell tenni [az Azure AD-alkalmazásproxy vagy a webelérési proxy használatával.](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) Másik választott fordított proxyt is használhat.

![SCEP-adatfolyam.](./images/hololens2-scep-info-flow.png)

Ha a hálózata még nem támogatja az SCEP-t, vagy nem biztos benne, hogy a hálózata megfelelően van-e beállítva az SCEP-hez az Intune-nal, akkor a Configure  [infrastructure to support SCEP with Intune](/mem/intune/protect/certificates-scep-configure)(Infrastruktúra konfigurálása az SCEP Intune-nal való támogatásához) referenciát.

Ha az infrastruktúra már támogatja az SCEP-t, létre kell hoznia egy profilt [minden](/mem/intune/protect/certificates-profile-scep) olyan SCEP-tanúsítványhoz, HoloLens 2. tanúsítványt fogja használni. [](/mem/configmgr/protect/deploy-use/create-certificate-profiles) Ha SCEP-problémái vannak, használja az SCEP-tanúsítványprofilok használatának hibaelhárítása tanúsítványokat az SCEP-tanúsítványprofilokkal való [Microsoft Intune.](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)

## <a name="pkcs"></a>PKCS
Az Intune a privát és nyilvános kulcspáros (PKCS-) tanúsítványok használatát is támogatja. További [információ: Use private and public key certificates in Microsoft Intune (Privát](/mem/intune/protect/certificates-pfx-configure) és nyilvános kulcsú tanúsítványok használata a Microsoft Intune-ban).

## <a name="proxy"></a>Proxy
A legtöbb vállalati intranetes hálózat proxyt használ a külső forgalom kezelésére. A HoloLens 2-es porton konfigurálhat proxykiszolgálót Ethernet-, Wi-Fi VPN-kapcsolatokhoz.

A proxynak többféle típusa és a proxy konfigurálható. Ebben az útmutatóban a **Wi-Fi proxyt választjuk, PAC URL-címen** keresztül adhatja meg és MDM-en keresztül helyezheti üzembe. Ez azzal jár, hogy az MDM-en keresztül automatikusan üzembe helyezhetők, frissíthető a PAC-fájl a kiszolgáló:port konfiguráció helyett, végül pedig proxyt használva konfigurálhatja Wi-Fi proxyt úgy, hogy csak egyetlen Wi-Fi-kapcsolatra vonatkozik, és lehetővé teszi, hogy az eszközök akkor is használhatók, ha más helyen csatlakoznak.

További részletek a proxybeállításokról a Windows 10: [Create a Wi-Fi profile for devices in Microsoft Intune - Azure](/mem/intune/configuration/wi-fi-settings-configure)..

## <a name="line-of-business-apps"></a>Üzletági alkalmazások 
Bár számos alkalmazás telepíthető a Microsoft Store, valószínű, hogy saját egyéni alkalmazással is van, amelyet kifejezetten vegyes valóságban való használatra hozott létre. Ezeket az egyéni alkalmazásokat üzletági (Line of Business, LOB) alkalmazásoknak nevezzük.
  
Az alkalmazásokat többféleképpen is üzembe helyezheti HoloLens 2 eszközön. Az alkalmazások telepíthetők közvetlenül az MDM-ről, a Microsoft Store Vállalatoknak (MSfB) vagy közvetlenül telepíthetők egy kiépítési csomagon keresztül. Az útmutató kedvéért az MDM-en keresztül telepítünk alkalmazásokat a szükséges alkalmazástelepítés használatával. Ez lehetővé teszi, hogy az LOB-alkalmazások automatikusan letöltsön a HoloLens eszközökre, miután befejezték a regisztrációt.

Azok számára, akik nem a saját LOB-jukkal, egy mintaalkalmazást biztosítunk az üzembe helyezési folyamat teszteléséhez. Ez az alkalmazás lesz az [MRTK-példák](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) alkalmazás, és már előre felépítették és becsomagolták a koncepció igazolásának teszteléséhez.

Az alkalmazástelepítéssel kapcsolatos további részleteket az [Alkalmazáskezelés: Áttekintés](/hololens/app-deploy-overview)oldalon talál.

> [!NOTE]
> HoloLens 2. része csak az UWP ARM64-alkalmazások futtatását támogatja.

## <a name="guides-playbook"></a>Útmutatók – forgatókönyv
Az útmutatók egy Microsoft Dataverse-környezetet használ adattárként az útmutatók alkalmazáshoz. Fontos, hogy jobban át tudja látni, hogyan kommunikál a Dataverse-környezet az útmutatók alkalmazásaival és a bérlővel. Ebben az útmutatóban nem fedjük le az adatverzum kezelését, de tekintse át a [Dynamics 365-útmutatók – Dynamics 365-útmutatók](/dynamics365/mixed-reality/guides/admin-deployment-playbook)üzembe helyezésének alapfogalmait Mixed Reality.

## <a name="next-step"></a>Következő lépés 
> [!div class="nextstepaction"]
> [Vállalati csatlakoztatott üzembe helyezés – Konfigurálás](hololens2-corp-connected-configure.md)