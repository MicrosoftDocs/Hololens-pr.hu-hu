---
title: A HoloLens beállítása kereskedelmi környezetben
description: További információ a HoloLens vállalati környezetekben való üzembe helyezéséről és kezeléséről, beleértve az infrastruktúrát, az Azure Active Directoryt és a mobileszköz-felügyeletet.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: e6aebfca076294de34068cd075d954220d7f4686
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378113"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>HoloLens 2 vállalati üzembe helyezés és felügyelet

Ennek az áttekintésnek a célja, hogy segítse az informatikai szakembereket abban, hogy megértsék a vállalaton Microsoft HoloLens 2 eszköz üzembe helyezésének és felügyeletének szempontjait.

A HoloLens 2 Windows 10 Holographic, amely robusztus, rugalmas, beépített mobileszköz- és alkalmazáskezelési technológiákat biztosít a szervezeteknek. Windows 10 Holographic támogatja a teljes eszköz-életciklus kezelését, hogy a vállalatok szabályozni ellenőrizzék eszközeik, adataik és alkalmazásaik kezelését. A HoloLens 2 egyszerűen beépíthető a szabványos életciklus-eljárásokba, az eszközök regisztrálásán, konfigurálásán és alkalmazáskezelésén át a karbantartásig és kivezetésig egy átfogó mobileszköz-kezelési megoldással.

## <a name="prepare"></a>Előkészítés

A HoloLens 2 vállalati környezetben való üzembe helyezésének előkészítése során számos szempontot érdemes áttekinteni és értelmezni a HoloLens 2 skálázható üzembe helyezésének megtervezése során.

### <a name="infrastructure-essentials"></a>Infrastructure Essentials

A HoloLens 2 vállalati üzembe helyezési forgatókönyvében bizonyos alapvető infrastruktúra-szolgáltatások szükségesek a képességek teljes készletének támogatásához. A HoloLens 2 modern [mobileszközökre Eszközkezelés](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) az üzembe helyezést és a felügyeletet szem előtt tartva. Az Azure AD Join + MDM használata az egyre növekvő mobil munkaerő elérésének elsődleges eszközét jelenti. Az alábbi témakörök rövid áttekintést nyújtanak az egyes infrastruktúra-összetevőkről, amelyek figyelembe lesznek véve a HoloLens 2 üzembe helyezésének tervezése során.

### <a name="azure-active-directory"></a>Azure Active Directory
Az Azure AD egy felhőalapú címtárszolgáltatás, amely identitás- és hozzáférés-kezelési funkciókat biztosít. Integrálhatja a meglévő helyszíni könyvtárakkal egy hibrid identitásmegoldás létrehozásához. Az Microsoft Office 365-öt vagy Intune-t használó szervezetek már használják az Azure AD-t, amely három kiadással rendelkezik: Ingyenes, Prémium P1 és Prémium P2 (lásd a Azure Active Directory [kiadásokat).](https://azure.microsoft.com/documentation/articles/active-directory-editions/) Minden kiadás támogatja az Azure AD-eszközregisztrációt, de az automatikus MDM-regisztráció engedélyezéséhez Prémium P1 szükséges. A HoloLens 2-nek Azure Active Directory Kell csatlakoznia a legtöbb vállalati szintű funkció és funkció engedélyezéséhez.

> [!NOTE]
> A helyszíni Active Directory a Join nem támogatott a HoloLens 2-ben.

### <a name="mobile-device-management"></a>Mobileszköz-kezelés
A HoloLens 2 kifejezetten a Mobile Eszközkezelés (MDM) rendszerek által vállalati környezetben való használatra lett tervezve. A Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)a Enterprise Mobility + Security része, egy felhőalapú MDM-rendszer, amely a vállalat eszközeit kezeli. Az Office 365-hez hasonló az Intune az Azure AD-t használja az identitáskezeléshez, így az alkalmazottak ugyanazokkal a hitelesítő adatokkal regisztrálják az eszközöket az Intune-ban, amelyekkel bejelentkeznek az Office 365-be. Több MDM-rendszer támogatja Windows 10 és a legtöbb támogatja a személyes és vállalati eszközök üzembe helyezésének forgatókönyvét. Az MDM-rendszerek a HoloLens 2 alkalmazástelepítéseit és frissítéseit is kezelhetik. A HoloLens 2-t támogató egyéb MDM-szolgáltatók jelenleg a következők: AirWatch, MobileIron stb. Minden MDM-rendszerszállító egyenlő hozzáféréssel rendelkezik az Windows 10 eszközkezelési konfigurációszolgáltatókhoz, így az IT-szervezetek szabadon kiválaszthatják a felügyeleti követelményeiknek leginkább megfelelő rendszert, akár Microsoft Intune, akár külső MDM-terméket.

> [!NOTE]
> A HoloLens 2 nem támogatja a hagyományos helyszíni pc-System Center Konfigurációkezelő rendszerek, mint például a System Center Konfigurációkezelő rendszerek.

### <a name="windows-update-for-business"></a>Windows Update Vállalatoknak
A Microsoft Windows Update Vállalatoknak, hogy további Windows Update-központú felügyeleti képességeket biztosítson a rendszergazdáknak, például lehetővé teszi frissítések telepítését eszközcsoportokra, valamint karbantartási időszakokat határozzon meg a frissítések telepítéséhez. A [HoloLens](https://docs.microsoft.com/hololens/hololens-updates) 2-frissítések kezelésével kapcsolatos részletekért tekintse meg a HoloLens-frissítések dokumentációját.

### <a name="certificates"></a>Tanúsítványok
A HoloLens 2 támogatja a tanúsítványok MDM-ben való üzembe helyezését, ha a környezet tanúsítványokat igényel Wi-Fi hálózati hitelesítéshez vagy más erőforrásokhoz való hozzáféréshez. Egyes MDM-infrastruktúrakonfigurációkra szükség lehet a tanúsítványok HoloLens 2-ben való üzembe helyezésének engedélyezéséhez. További információ a tanúsítványok és hálózati profilok [HoloLens 2-hez való előkészítéséről.](https://docs.microsoft.com/hololens/hololens-certificates-network) Ha az Intune-t használja, tekintse meg a tanúsítványkonfiguráció [részleteit.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)

## <a name="configure"></a>Konfigurálás

Az MDM-rendszergazdák szabályzatbeállításokat határozhatnak meg és valósítanak meg az MDM-rendszerben regisztrált összes vállalati eszközön. A használt konfigurációs beállítások az üzembe helyezési forgatókönyvtől függően eltérnek. A Windows 10 konfigurációszolgáltatók (CSP-k) az eszköz konfigurációs beállításainak olvasására, beállítására, módosítására vagy törlésére kínálnak felületet. Ezek a beállítások beállításkulcsra vagy fájlokra vannak leképezve. A HoloLens 2 Windows 10 eszközkezelési CSP-kről a [HoloLens-eszközök](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)által támogatott CSP-k teljes listájában található további információ.

A HoloLens 2 támogatja a CSP-konfigurációk korlátozott készletének egyéni kiépítési csomagokon keresztüli beállítását is. A kiépítési csomagokat általában nem MDM által felügyelt eszközökhöz használják, és manuálisan kell alkalmazni őket az egyes eszközökre. Az egyéni kiépítési csomagok létrehozásáról [a HoloLens kiépítési](https://docs.microsoft.com/hololens/hololens-provisioning) dokumentációjában talál további információt.

> [!NOTE]
> A HoloLens 2 támogatja a [Windows Autopilot,](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)amely egyszerű és egyszerű folyamatot biztosít a vállalati eszközök Windows 10 kezeléséhez.

### <a name="identity-management"></a>Identitáskezelés

Az alkalmazottak csak egy fiókot használhatnak egy eszköz inicializálására,&#39;fontos, hogy a szervezet szabályozza, hogy melyik fiók legyen először engedélyezve. A kiválasztott fiók határozza meg, hogy ki szabályozza az eszközt, és befolyásolja a felügyeleti képességeket. A HoloLens 2 3 fióktípust támogat: helyi felhasználói fiókot, személyes Microsoft-fiókot és Azure Active Directory fiókokat. Erősen ajánlott a Azure Active Directory a vállalati identitáskezelési megoldáshoz, mivel ez minden képességet lehetővé tesz a HoloLens 2-eszközökön. A [HoloLens](https://docs.microsoft.com/hololens/hololens-identity) 2 identitásával kapcsolatos további részletekért tekintse meg a HoloLens-identitásokat.

### <a name="network-and-connectivity"></a>Hálózat és kapcsolatok

Mivel a HoloLens 2 egy felhőalapú eszköz, az online erőforrásokhoz való hálózati hozzáférésre van szükség a teljes funkcionalitás és képességek elérhetővé eléréséhez. Ha a HoloLens 2-eszközöket a vállalati intranetes hálózathoz csatlakoztatva telepíti, előfordulhat, hogy frissítenie kell a proxy-/tűzfalszabályokat, hogy engedélyezze a HoloLens 2 felhőszolgáltatáshoz való hozzáférést. További információért nézze meg a [HoloLens 2](https://docs.microsoft.com/hololens/hololens-offline)operációs rendszer gyakori végpontjainak listáját. Előfordulhat, hogy további végpontok elérésére van szükség ahhoz, hogy az alkalmazások vagy más felhőszolgáltatások sikeresen fusson a HoloLens 2-ben.

Néhány gyakori HoloLens 2-szolgáltatás, amelyek további végpont-hozzáférést követelnek meg, a következők:

- [megkezdése](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365-útmutatók](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 Remote Assist (O365 Teams-infrastruktúra)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>Tanúsítvány központi telepítése

Ha tanúsítványokra van szükség a vállalati Wi-Fi hálózatokhoz vagy a szervezeten belüli egyéb szolgáltatásokhoz való hozzáféréshez, a HoloLens 2 támogatja a felhasználói és eszköztanúsítványok MDM-ben való üzembe helyezését. Megjegyzés: Előfordulhat, hogy az MDM-megoldás további infrastruktúra-konfigurációt igényel a tanúsítványok központi telepítéséhez Windows 10 eszközökön.

### <a name="security-review"></a>Biztonsági felülvizsgálat

A legtöbb nagyvállalati it-részleg megköveteli a vállalati hálózaton üzembe helyezett új eszközök értékelését és áttekintését. Ha a szervezetnek szüksége van a HoloLens 2 biztonsági felülvizsgálatára, további részleteket talál a biztonsági jóváhagyások [beszerzéséhez.](https://docs.microsoft.com/hololens/security-overview)

### <a name="common-hololens-2-device-settings"></a>Gyakori HoloLens 2-eszközbeállítások

A HoloLens 2-eszközök vállalati vállalati környezetben való üzembe helyezésekor számos gyakori eszközkonfigurációt figyelembe kell venni a HoloLens 2 üzembe helyezésének megtervezésekor. Ez a lista a meglehetősen gyakorinak talált konfigurációkat és beállításokat emeli ki, és nem tartalmazza az elérhető lehetőségek teljes listáját:

| Eszközbeállítás | Rövid leírás.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Hardverkorlátozások](hololens-requirements.md#hardware-restrictions)               | A hardverkorlátozások csökkentik a kapcsolatot, és segítenek az adatvédelemben.                        |
| [Wi-Fi-profilok](hololens-requirements.md#wi-fi-profiles)               | Konfigurálja Wi-Fi felhasználói beavatkozás vagy interakció nélkül a profilokat.                              |
| [Tanúsítványok](hololens-requirements.md#certificates-1)               | Fiók- és/vagy Wi-Fi hitelesítés, VPN-titkosítás és a webes tartalom SSL-titkosítása. |
| [Proxy](hololens-requirements.md#proxy)              | Belső forgalom kezelése.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Szabályozhatja az alkalmazásokhoz és erőforrásokhoz való hozzáférést a vállalat intranetén.                               |
| [Kioszkmód](hololens-requirements.md#kiosk-mode) | Korlátozza a felhasználói felületen keresztül a felhasználók számára megjelenő alkalmazásokat. |

#### <a name="hardware-restrictions"></a>Hardverkorlátozások

A HoloLens 2 a legtechnológiásbb technológiát használja, amely olyan népszerű hardverszolgáltatásokat tartalmaz, mint a kamerák, a mikrofonok, a beszélők, az USB-adapterek, a Bluetooth-interfészek és a Wi-Fi. Ezeknek a funkcióknak a rendelkezésre állását hardverkorlátozások használatával szabályozhatja.

Az alábbiakban a HoloLens 2 által a hardverkorlátozások konfigurálásán támogatott leggyakrabban használt MDM-beállításokat soroljuk fel. Ezen hardverkorlátozások némelyike biztosítja a kapcsolatot, és segít az adatvédelemben.

- [**Wi-Fi engedélyezése:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Azt határozza meg, hogy a felhasználók engedélyezhetik-e és Wi-Fi az eszközükön a választógombot
- [**USB-kapcsolat engedélyezése:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Engedélyezve van-e az USB-kapcsolat (&#39;nincs hatással az USB-töltésre)
- [**Bluetooth engedélyezése:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Azt határozza meg, hogy a felhasználók engedélyezhetik-e és használják-e a Bluetooth-választógombot az eszközeiken

További információ az egyéb gyakori [eszközkorlátozásokkal kapcsolatban.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### <a name="wi-fi-profiles"></a>Wi-Fi-profilok

A legtöbb vállalati Wi-Fi tanúsítványokra és egyéb összetett információkra van szükség a felhasználói hozzáférés korlátozására és biztonságossá vált eléréséhez. Ezt a Wi-Fi információt a felhasználók nehezen konfigurálják, de az MDM-rendszerek felhasználói beavatkozás nélkül Wi-Fi konfigurálják ezeket a profilokat. Az MDM-Wi-Fi több profilt is létrehozhat.

További részletek a vállalati Wi-Fi beállításairól Windows 10 Vállalati [profil Wi-Fi-beállításai.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

#### <a name="certificates"></a>Tanúsítványok

A tanúsítványok azáltal növelik a biztonságot, hogy fiókhitelesítést, Wi-Fi, VPN-titkosítást és a webes tartalmak SSL-titkosítását biztosítják. Bár a rendszergazdák manuálisan kezelhetik a tanúsítványokat az eszközökön a kiépítési csomagokon keresztül&#39;, ajánlott eljárás az MDM-rendszer használata a tanúsítványok teljes életciklusukon keresztüli kezelésére– a regisztrációtól a megújításon és visszavonáson át. Az MDM-rendszer automatikusan telepítheti ezeket a tanúsítványokat az eszközökre&#39; tanúsítványtárolókban az eszköz regisztrálása után (amennyiben az MDM-rendszer támogatja az Egyszerű tanúsítványigénylési protokoll (SCEP) vagy a nyilvános kulcsú titkosítási szabványok #12 (PKCS #12)). Az MDM lekérdezheti és törölheti is a regisztrált ügyféltanúsítványokat, vagy új beléptetési kérelmet aktiválhat az aktuális tanúsítvány lejárta előtt.

További információ a tanúsítványok és hálózati profilok [HoloLens 2-hez való előkészítéséről.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### <a name="proxy"></a>Proxy

A legtöbb vállalati intranethálózat proxyt használ a belső forgalom kezelésére. A HoloLens 2-ben konfigurálhat proxykiszolgálót Ethernet- és Wi-Fi kapcsolatokhoz. Ezek a beállítások nem vonatkoznak a VPN-kapcsolatokra.

További információ a proxybeállításokról a [Windows 10: NetworkProxy CSP.](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)

#### <a name="vpn"></a>VPN

A szervezetek gyakran VPN-t használnak a vállalati intraneten található alkalmazások és erőforrások&#39;szabályozásához. A HoloLens 2 támogatja az SSL VPN-kapcsolatokat, amelyekhez letölthető beépülő modulra van szükség a Microsoft Store és amelyek az Ön által választott VPN-gyártóra vonatkoznak.

A VPN-profilokkal kapcsolatos további részletekért lásd: [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### <a name="kiosk-mode"></a>Kioszkmód

A HoloLens 2-eszközt kioszkmódban működő rögzített célú eszközként (más néven kioszkként) konfigurálhatja úgy, hogy az eszköz kioszkmódban fusson. A kioszkmód korlátozza az eszközön elérhető alkalmazásokat (vagy felhasználókat). A kioszkmód egy kényelmes funkció, amely lehetővé teszi a HoloLens 2-eszközök üzleti alkalmazásoknak való dedikálését, vagy a HoloLens 2 eszköz használatát egy alkalmazásbemutatóban.

A HoloLens 2 Kioszk módban való konfigurálásával kapcsolatos további részletekért [lásd: A HoloLens beállítása kioszkként](https://docs.microsoft.com/hololens/hololens-kiosk)

## <a name="deploy"></a>Üzembe helyezés

### <a name="mdm-device-enrollment"></a>MDM-eszközök regisztrálása

Nagyvállalati telepítések esetén [](https://docs.microsoft.com/hololens/hololens-enroll-mdm) ajánlott az eszközöket csak az Azure AD-beléptetéssel és automatikus MDM-regisztrációval (Azure AD+MDM) regisztrált vállalati eszközként regisztrálni az MDM-be. Ehhez több MDM prémium szintű Azure AD is támogatja az automatikus regisztrációt, beleértve az Intune-t is.

További információ az autopilot regisztrációs módszer önálló üzembe [helyezéséről.](https://docs.microsoft.com/hololens/hololens2-autopilot)

### <a name="application-deployment"></a>Alkalmazástelepítés

A mobileszközökön a felhasználók termelékenységét gyakran alkalmazások használják.

Windows 10 lehetővé teszi olyan alkalmazások fejlesztését, amelyek zökkenőmentesen működnek több eszközön a Windows-alkalmazásokhoz készült Univerzális Windows-platform (UWP) használatával.

Az alkalmazások HoloLens 2-eszközökön való üzembe helyezésének több módja is van. Az alkalmazások telepíthetők közvetlenül az MDM-Microsoft Store Vállalatoknak vagy közvetlenül telepíthetők egy kiépítési csomagon keresztül. További részletekért tekintse meg [az](https://docs.microsoft.com/hololens/app-deploy-overview) alkalmazástelepítési dokumentációt.

> [!NOTE]
> A HoloLens 2 csak az UWP ARM64-alkalmazások futtatását támogatja.

## <a name="maintain"></a>Karbantartás

A vállalati it-környezetekben a biztonság és a költségek szabályozásának kiegyensúlyozottnak kell lennie azzal a szándékkal szemben, hogy a felhasználók a legújabb technológiákat biztosítják. Mivel a kibertámadások mindennapossá váltak, fontos megfelelően fenntartani a virtuális Windows 10 állapotát. Az it-csoportnak szabályoznia kell a konfigurációs beállításokat, hogy azok ne tudjanak megfelelőségi eltérést elérni, valamint kikényszerítenie, hogy mely eszközök férnek hozzá a belső alkalmazásokhoz. A HoloLens 2 biztosítja azokat a mobilművelet-kezelési képességeket, amelyek ahhoz szükségesek, hogy az eszközök megfelelnek a vállalati szabályzatnak.

### <a name="os-servicing-options"></a>Az operációs rendszer karbantartási lehetőségei

**Zökkenőmentes frissítési folyamat**

A Microsoft leegyszerűsíti a Windows terméktervezési és -kiadási ciklusát, így a piac által megkövetelt új funkciók, élmények és funkciók minden másnál gyorsabban elérhetőek lesznek. A Microsoft évente két funkciófrissítést tervez kézbesíteni (12 hónapos időszak). **A funkciófrissítések** létrehoznak egy Aktuális ág vagy CB-t, és társított verzióval rendelkezik.

A Microsoft emellett közvetlenül a HoloLens 2-eszközökre is kézbesíti és telepíti a biztonsági és stabilitási frissítéseket. Ezek **a Microsoft által** a Windows Update által kiadott minőségi frissítések havonta érhetők el. A HoloLens 2 ugyanannak a szabványos frissítési folyamatnak a részeként használja fel a funkciófrissítéseket és a minőségi frissítéseket.

A nagyvállalati ügyfelek a HoloLens 2-ben, MDM-rendszer használatával kezelhetik a frissítési élményt és a folyamatot. A legtöbb esetben a frissítési folyamat kezelésére vonatkozó szabályzatok a funkció- és minőségi frissítésekre is érvényesek. További részletek az [MDM HoloLens-frissítésekhez való konfigurálásával kapcsolatosak.](https://docs.microsoft.com/hololens/hololens-updates)

### <a name="managing-applications"></a>Alkalmazások kezelése

A rendszergazdák szabályozhatják, hogy mely alkalmazások telepíthetők a HoloLens 2-re, és hogyan kell őket naprakészen tartani.

A HoloLens 2 támogatja a [Windows Defender Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)alkalmazást, amellyel a rendszergazdák alkalmazáslistákat hozhatnak létre, engedélyeznek vagy engedélyeznek a Microsoft Store. Ez a képesség a beépített alkalmazásokra is kiterjed. Az alkalmazások engedélyezése vagy megtagadása segít biztosítani, hogy a felhasználók a saját eszközeiket a kívánt célokra használják. Azonban nem mindig könnyű megtalálni az egyensúlyt az alkalmazottak által kért, illetve a kérések és a biztonsági szempontok között. Az engedélyező vagy nem engedélyező listák létrehozásához emellett lépést kell tartani az alkalmazás változó környezetében a Microsoft Store.

További részletekért lásd: [Alkalmazásvezérlő CSP.](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)

### <a name="retire"></a>Kivonás

Az eszközök kiesása az eszköz életciklusának utolsó fázisa. Fontos&#39;&#39;hogy az újabb modellekkel lecserélt eszközök biztonságosan kivehetőek, mivel nem szeretné, hogy a vállalati adatok az elvetett eszközökön maradjanak, ami veszélyeztetné az adatok bizalmas kezelését. Az it-csoportnak olyan módszerre is szüksége van, amely megfelelő támogatást nyújt az elveszett vagy ellopott eszközök törlési igényét eltulajdonuló felhasználóknak.

A HoloLens 2 három módszert támogat az eszköz adatokat törölve való adatokat

**MDM Factory-törlés:** Visszaállítja a HoloLens 2-t a gyári rendszerképre a rendszergazda által kezdeményezett MDM-paranccsal. Törli az eszközön tárolt összes adatot.

**Eszköz alaphelyzetbe állítása a Beállításokból:** A végfelhasználók manuálisan alaphelyzetbe állíthatják a HoloLens 2-t az eszköz Beállítások alkalmazásában. Törli az eszközön tárolt összes adatot.

**Speciális helyreállítási társ (ARC):** Az ARC eszközt futtató számítógépeken a felhasználók vagy a rendszergazdák USB-kábelen keresztül flashpel is csatlakoztathatja a számítógéphez csatlakoztatott HoloLens 2-t. Törli az eszközön tárolt összes adatot.

> [!div class="nextstepaction"]
> [Gyakori üzembe helyezési forgatókönyvek](common-scenarios.md)
