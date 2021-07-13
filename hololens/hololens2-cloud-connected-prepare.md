---
title: Üzembe helyezési útmutató – HoloLens 2. környezet nagy léptékű üzembe helyezése a Remote Assist segítségével – Előkészítés
description: Megtudhatja, hogyan készítheti elő a HoloLens eszközök felhőhöz csatlakoztatott hálózaton keresztüli regisztrálására az Azure Active Directory és az identitáskezelés használatával.
keywords: HoloLens, felügyelet, felhőhöz csatlakoztatott, Remote Assist, AAD, Azure AD, MDM, Mobile Eszközkezelés
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f747a2893ed3551e91a81bdbf5971deefbf6ce46
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637132"
---
# <a name="prepare---cloud-connected-guide"></a>Előkészítés – Felhőhöz csatlakoztatott útmutató

A cikk végére be fogja állítani az Azure AD-t és az MDM-et, és többet fog érteni az Azure AD-fiókok és a hálózati követelmények használatával kapcsolatban. Az útmutató ezen szakasza segít Önnek és a szervezetnek felkészülni a HoloLens 2. felhőben való üzembe helyezésére és a Dynamics 365 Remote Assist használatára. Át fogja látni az infrastruktúra egyes darabjainak fontosságát, valamint hivatkozásokat biztosít az útmutatókhoz, amelyek segítségével szükség szerint állíthatja be ezeket a részeket.

## <a name="infrastructure-essentials"></a>Infrastruktúra – alapvető szolgáltatások

Mind a személyes, mind a vállalati üzembe helyezési forgatókönyvekben az MDM-rendszer az alapvető infrastruktúra, amely az eszközök üzembe helyezéséhez és Windows 10 Holographic kezeléséhez szükséges. A prémium szintű Azure AD-előfizetés használata ajánlott identitásszolgáltatóként, és bizonyos képességek támogatásához szükséges.

### <a name="azure-active-directory"></a>Azure Active Directory

Az Azure AD egy felhőalapú címtárszolgáltatás, amely identitás- és hozzáférés-kezelési funkciókat biztosít. Az Microsoft Office 365 vagy az Intune-t használó szervezetek már használják az Azure AD-t, amely három kiadással rendelkezik: Ingyenes, Prémium P1 és Prémium P2 (lásd: Azure Active Directory [kiadás](https://azure.microsoft.com/documentation/articles/active-directory-editions)).) Minden kiadás támogatja az Azure AD-eszközregisztrációt, de Prémium P1 szükséges az automatikus MDM-regisztráció engedélyezéséhez, amelyet később használni fog ebben az útmutatóban.

> [!IMPORTANT]
> Fontos, hogy legyen egy Azure Active Directory, HoloLens az eszközök nem támogatják a helyszíni AD-csatlakozást. Ha még&#39;rendelkezik beállított Azure Active Directory, akkor az Új bérlő létrehozása [a](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)Azure Active Directory.

## <a name="identity-management"></a>Identitáskezelés

Az alkalmazottak csak egy fiókot használhatnak egy eszköz inicializálására&#39;hogy a szervezet határozza meg először, hogy melyik fiók legyen engedélyezve. A kiválasztott fiók határozza meg, hogy ki szabályozza az eszközt, és befolyásolja a felügyeleti képességeket.

Ebben az útmutatóban azt választottuk, hogy a használt [identitáshoz](/hololens/hololens-identity) Azure AD-fiókokat vagy Azure Active Directory használjuk. Az Azure AD-fiókoknak számos előnye van, például:

- Az alkalmazottak Azure AD-fiókjukkal regisztrálják az eszközt az Azure AD-ban, és automatikusan regisztrálják azt a szervezetnél&#39;MDM-megoldásban (Azure AD+MDM – prémium szintű Azure AD).
- Az Azure AD-fiókok támogatják [az egyszeri bejelentkezést.](/azure/active-directory/manage-apps/what-is-single-sign-on) Amikor egy felhasználó bejelentkezik a Remote Assist szolgáltatásba, a rendszer felismeri a bejelentkezett Azure AD-felhasználó identitását, és a felhasználó bejelentkezik az alkalmazásba a zökkenőmentes élmény érdekében.
- Az Azure AD-fiókok további hitelesítési [lehetőségekkel](/hololens/hololens-identity) is Windows Hello [for Business használatával.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) Az Írisz bejelentkezési felhasználója nem csak egy másik eszközről jelentkezhet be, de FIDO biztonsági kulcsokat is használhat.

### <a name="mobile-device-management"></a>Mobileszköz-kezelés

A Microsoft [Intune](/mem/intune/fundamentals/what-is-intune)a Enterprise Mobility + Security része, egy felhőalapú MDM-rendszer, amely a bérlőhöz csatlakoztatott eszközöket kezeli. A Office 365 az Intune az Azure AD-t használja az identitáskezeléshez, így az alkalmazottak ugyanazokkal a hitelesítő adatokkal regisztrálják az eszközöket az Intune-ban, amelyekkel bejelentkeznek az Office 365. Az Intune a teljes MDM-megoldás érdekében támogatja az egyéb operációs rendszereket (például iOS és Android) is. Ebben az útmutatóban azt&#39;, hogy az Intune használatával nagy méretekben, a 2. HoloLens üzembe helyezését.

> [!IMPORTANT]
> A Mobile Eszközkezelés. Ha még nem&#39;be, kövesse ezt az útmutatót és az Intune első lépések [útmutatóját.](/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Több MDM-rendszer támogatja Windows 10 és a legtöbb támogatja a személyes és vállalati eszközök üzembe helyezését. A szolgáltatást támogató MDM Windows 10 Holographic: AirWatch, MobileIron stb. A legtöbb iparágvezető MDM-szállító már támogatja az Azure AD-integrációt. Az Azure AD-t támogató MDM-szállítókat a következő [Azure Marketplace.](https://azure.microsoft.com/marketplace/)

## <a name="network"></a>Network (Hálózat)

Ebben a beállításban arra számítunk, HoloLens 2 eszköz fog csatlakozni az internethez bármely elérhető nyitott Wi-Fi hálózatról. Mivel a felhasználóknak a hálózati kapcsolatot hely alapján is módosítaniuk kell, meg kell tanulniuk, hogyan csatlakoztathat HoloLens [eszközöket Wi-Fi-hez.](/hololens/hololens-network)

A Dynamics 365 Remote Assist többféle hálózati feltételt biztosít, beleértve a sávszélességet, a késést, a jittert és a csomagvesztést, amelyek hatással lehetnek a videóhívási élményre. Bár a hang- és videohívások kisebb sávszélességű környezetekben is lehetségesek, a funkciók teljesítménycsökkenését tapasztalhatja. A Dynamics 365 Remote Assist HoloLens a hálózati követelményeket kell szem előtt tartani:

**Minimum:** 1,5 Mb/s fel/le sebességet igényel a társközi HD-minőségi videohívások 30 másodperces HD 1080p felbontású hívásához.

**Optimális:** A HD 1080p felbontású, társközi HD-minőségi videóhívások esetén 4–5 Mbps fel/le sebességűnek kell lennie.

További információ:

- [A hálózatra vonatkozó követelmények](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Hálózatoptimalizálási javaslatok](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>Nem kötelező: Csatlakozás VPN HoloLens re való csatlakozás

Az útmutatóhoz csatlakozó eszközök és külső felhőhálózaton keresztül fognak csatlakozni a hálózathoz. Előfordulhat, hogy a vállalati erőforrások eléréséhez vpn&#39;kell csatlakoztatnia az eszközöket. Az eszközöket többféleképpen is csatlakoztathatja VPN-hez, ahol a végfelhasználó az eszköz felhasználói felületén keresztül csatlakozhat, vagy az eszközök kezelhetők, és a PPKG-től vagy MDM-től kaphatják meg a VPN-profilt. A VPN beállítását&#39;ez a cikk nem fedi le, ezért ha többet szeretne megtudni&#39;különböző VPN-protokolljairól vagy a VPN kezelésének módjairól, olvassa el ezeket az útmutatókat a HoloLens és a VPN használatával [kapcsolatban.](/hololens/hololens-network#vpn)

## <a name="next-step"></a>Következő lépés

> [!div class="nextstepaction"]
> [Felhőhöz csatlakoztatott üzemelő példány – Konfigurálás](hololens2-cloud-connected-configure.md)
