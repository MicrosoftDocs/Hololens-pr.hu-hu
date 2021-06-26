---
title: Üzembe helyezési útmutató – Felhőhöz csatlakoztatott HoloLens 2 üzembe helyezése nagy méretekben a Remote Assist segítségével – Előkészítés
description: Megtudhatja, hogyan készítheti elő a HoloLens-eszközök felhőhöz csatlakoztatott hálózaton keresztüli regisztrálását az Azure Active Directory és az identitáskezelés használatával.
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
ms.openlocfilehash: 21132ed5d1e84d92a877747ac9a4c090b177ca08
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924570"
---
# <a name="prepare---cloud-connected-guide"></a>Előkészítés – Felhőhöz csatlakoztatott útmutató

A cikk végére be fogja állítani az Azure AD-t és az MDM-et, és többet fog érteni az Azure AD-fiókok és a hálózati követelmények használatával kapcsolatban. Az útmutató ezen szakasza segít Önnek és a szervezetnek felkészülni a HoloLens 2 felhőbeli üzembe helyezésére és a Dynamics 365 Remote Assist használatára. Át fogja látni az infrastruktúra egyes darabjainak fontosságát, valamint hivatkozásokat biztosít az útmutatókhoz, amelyek segítségével szükség szerint állíthatja be ezeket a részeket.

## <a name="infrastructure-essentials"></a>Infrastructure Essentials

Mind a személyes, mind a vállalati üzembe helyezési forgatókönyvek esetében az MDM-rendszer a virtuális eszközök üzembe helyezéséhez és kezeléséhez Windows 10 Holographic infrastruktúra. A prémium szintű Azure AD-előfizetést ajánlott identitásszolgáltatóként használni, és bizonyos képességek támogatásához szükséges.

### <a name="azure-active-directory"></a>Azure Active Directory

Az Azure AD egy felhőalapú címtárszolgáltatás, amely identitás- és hozzáférés-kezelési funkciókat biztosít. A Microsoft Office 365-öt vagy Intune-t használó szervezetek már használják az Azure AD-t, amely három kiadással rendelkezik: Ingyenes, Prémium P1 és Prémium P2 (lásd a Azure Active Directory [kiadásokat).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Minden kiadás támogatja az Azure AD-eszközregisztrációt, de az MDM automatikus regisztrálásának engedélyezéséhez prémium P1 csomag szükséges, amelyet később használni fog ebben az útmutatóban.

> [!IMPORTANT]
> Fontos, hogy legyen egy Azure Active Directory, mivel a HoloLens-eszközök nem támogatják a helyszíni AD-csatlakozást. Ha még nincs&#39;, Azure Active Directory új bérlő létrehozása [a](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)Azure Active Directory.

## <a name="identity-management"></a>Identitáskezelés

Az alkalmazottak csak egy fiókot használhatnak egy eszköz inicializálására,&#39;fontos, hogy a szervezet szabályozza, hogy melyik fiók legyen először engedélyezve. A kiválasztott fiók határozza meg, hogy ki szabályozza az eszközt, és befolyásolja a felügyeleti képességeket.

Ebben az útmutatóban azt választottuk, hogy a használt [identitáshoz](https://docs.microsoft.com/hololens/hololens-identity) Azure AD-fiókokat vagy Azure Active Directory használjuk. Az Azure AD-fiókoknak számos előnye van, például:

- Az alkalmazottak Azure AD-fiókjukkal regisztrálják az eszközt az Azure AD-ban, és automatikusan regisztrálják azt a szervezetnél&#39;MDM-megoldásában (Azure AD+MDM – prémium szintű Azure AD).
- Az Azure AD-fiókok támogatják [az egyszeri bejelentkezést.](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) Amikor egy felhasználó bejelentkezik a Remote Assist szolgáltatásba, a rendszer felismeri a bejelentkezett Azure AD-felhasználó identitását, és a felhasználó bejelentkezik az alkalmazásba a zökkenőmentes élmény érdekében.
- Az Azure AD-fiókok további hitelesítési [lehetőségekkel is](https://docs.microsoft.com/hololens/hololens-identity) [Vállalati Windows Hello.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) Az Írisz bejelentkezési felhasználója nem csak egy másik eszközről jelentkezhet be, de FIDO biztonsági kulcsokat is használhat.

### <a name="mobile-device-management"></a>Mobileszköz-kezelés

A Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)a Enterprise Mobility + Security része, egy felhőalapú MDM-rendszer, amely a bérlőhöz csatlakoztatott eszközöket kezeli. Az Office 365-hez hasonló az Intune az Azure AD-t használja az identitáskezeléshez, így az alkalmazottak ugyanazokkal a hitelesítő adatokkal regisztrálják az eszközöket az Intune-ban, amelyekkel bejelentkeznek az Office 365-be. Az Intune a teljes MDM-megoldás érdekében támogatja az egyéb operációs rendszereket (például iOS és Android) is. Ebben az útmutatóban azt&#39;, hogy az Intune segítségével nagy méretekben is üzembe helyezést engedélyezünk a HoloLens 2-ben.

> [!IMPORTANT]
> A Mobile Eszközkezelés. Ha még nem&#39;be, kövesse ezt az útmutatót és az Intune első lépések [útmutatóját.](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Több MDM-rendszer támogatja Windows 10 és a legtöbb támogatja a személyes és vállalati eszközök üzembe helyezésének forgatókönyvét. A szolgáltatást támogató MDM-Windows 10 Holographic jelenleg a következők: AirWatch, MobileIron stb. A legtöbb iparágvezető MDM-szállító már támogatja az Azure AD-integrációt. Az Azure AD-t támogató MDM-szállítókat a [következő](https://azure.microsoft.com/marketplace/)Azure Marketplace.

## <a name="network"></a>Network (Hálózat)

Ebben a beállításban arra számítunk, hogy a HoloLens 2-eszközök bármely elérhető nyílt hálózati Wi-Fi csatlakoznak az internethez. Mivel a felhasználónak a hálózati kapcsolatot hely alapján is módosítania kell, meg kell tanulnia, hogyan csatlakoztathatja [a HoloLens-eszközöket Wi-Fi-hez.](https://docs.microsoft.com/hololens/hololens-network)

A Dynamics 365 Remote Assist többféle hálózati feltételt biztosít, beleértve a sávszélességet, a késést, a jittert és a csomagvesztést, amelyek hatással lehetnek a videóhívási élményre. Bár a hang- és videohívások kisebb sávszélességű környezetekben is lehetségesek, teljesítménycsökkenést tapasztalhat. A Dynamics 365 Remote Assist HoloLensen való használata esetén a következő hálózati követelményeket kell szem előtt tartani:

**Minimum:** 1,5 Mb/s fel/le sebességet igényel a társközi HD-minőségi videohívások 30 másodperces HD 1080p felbontású hívásához.

**Optimális:** A hd 1080p felbontással hívható, társközi HD-minőségi videohívások esetén 4–5 Mbps fel-/le sebességűnek kell lennie.

További információ:

- [A hálózatra vonatkozó követelmények](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Hálózatoptimalizálási javaslatok](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>Nem kötelező: A HoloLens csatlakoztatása VPN-hez

Az útmutatóhoz csatlakozó eszközök és külső felhőhálózaton keresztül fognak csatlakozni a hálózathoz. Előfordulhat, hogy a vállalati erőforrások eléréséhez vpn&#39;kell csatlakoztatnia az eszközöket. Az eszközöket többféleképpen is csatlakoztathatja VPN-hez, ahol a végfelhasználó az eszköz felhasználói felületén keresztül csatlakozhat, vagy az eszközök kezelhetők, és a PPKG-ből vagy MDM-ből is fogadhatják a VPN-profilt. A VPN beállítását ez&#39;cikk nem fedi le, ezért ha többet szeretne megtudni&#39;különböző VPN-protokolljairól vagy a VPN-kezelés módjairól, olvassa el ezeket az útmutatókat a [HoloLensről](https://docs.microsoft.com/hololens/hololens-network#vpn) és a VPN-ről.

## <a name="next-step"></a>Következő lépés

> [!div class="nextstepaction"]
> [Felhőhöz csatlakoztatott üzemelő példány – Konfigurálás](hololens2-cloud-connected-configure.md)
