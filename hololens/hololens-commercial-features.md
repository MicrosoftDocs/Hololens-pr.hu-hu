---
title: HoloLens 2 képesség és megoldás
description: Ismerje meg a Microsoft HoloLens kereskedelmi funkciókat, amelyek megkönnyítik a vállalkozások számára a HoloLens kezelését.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 06/28/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: skerewa
appliesto:
- HoloLens 2
keywords: HoloLens 2, kereskedelmi, funkciók, mdm, mobileszköz-kezelés, kioszkmód, alkalmazások, identitás, Bitlocker, iris, Windows Hello, Azure-alapú, Autopilot, vegyes valóság, WDAC
ms.openlocfilehash: 88a75224909fd64e387cfb5677056e2ae5d62e4b3518aa758f22ec66a86a8355
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665342"
---
# <a name="hololens-2-capabilities-and-solutions"></a>HoloLens 2 képesség és megoldás

## <a name="what-can-hololens-2-do-for-you"></a>Mit HoloLens a 2.

Határok nélkül működhet együtt, és precízen működhet együtt az alkalmazottak termelékenységének növelése érdekében a 2. HoloLens alkalmazásokkal. A beépített hangparancsok, a szemkövetés és a világvezetők segítségével fej-fej mellett maradhat, és a feladatok hiba nélküli, biztonságos elvégzésére összpontosíthat folyamatosan. Csatlakozás a távoli munkatársakkal, és egy fizikai környezetben elterjedő, kiterjedt holografikus vásznon dolgozva gyorsan megoldhatja a problémákat a munka során. A megtérülés azonnal használható a Microsoft biztonságával, megbízhatóságával és méretezhetőségével támogatott alkalmazások robusztus ökoszisztémájában.  

[!INCLUDE [solutions](includes/hlsolutions.md)]

## <a name="hololens-2-capabilities"></a>HoloLens 2 képesség

Mitől olyan hatékony a HoloLens 2?

| Szolgáltatás | Leírás |
|---------|-------------|
| Világ horgonyzása | A rögzített hologramok pontosan a helyén maradnak. HoloLens 2. tag érti a munkaterületet. Így a digitális tartalom az idő múlása alatt is megmarad – olyan objektumokhoz vagy felületekhez rögzítetten, ahol dolgozik. |
| Kézkövetés | A hologramok érintése, megragadás és áthelyezése természetesnek érzi magát. HoloLens 2 a saját kézhez alkalmazkodik az interakciók újnak talált elégedettsége érdekében. |
| Szemkövetés | Új kontextus és emberi megértés. HoloLens 2. felfogja, hogy pontosan hol keres, így valós időben képes megérteni a szándékot és a hologramokat a szemének megfelelően igazítani. |
| Hang engedélyezve | A beépített hangparancsokkal gyorsan navigálhat és működtethet HoloLens 2.- ben, ha a kézzel egy feladattal van elfoglalva. |
| Ergonomikus | HoloLens 2. része kis (3,28 kg), amely a kiterjesztett használatot támogató betárcsázásos illeszkedő rendszert tartalmaz. |
| Large FoV | Bontsa ki a holografikus vásznat nagy felbontású, nagy méretű nézetben. |
| Távkioldós | Szabadon mozoghat vezetékek és külső csomagok nélkül, hogy továbblépni tudjon a feladatra. |
| Azure-alapú | Streamelhet kiváló minőségű 3D-tartalmakat, amelyek egy olyan helyhez és/vagy objektumhoz rögzítettek, amely megmarad a vegyes valóságú Azure-szolgáltatásokat használó felhasználók között.
| Vegyes valóság rögzítése | Fényképként vagy videóként dokumentálja a felhasználói élményt, és valós időben oszthatja meg másokkal. |
| Vállalati Windows Hello | Az írisz alapú biometrikus hitelesítéssel gyorsan és biztonságosan beléphet a munka folyamatába. |
| Windows Autopilot | A 2. HoloLens szolgáltatásokat úgy kell beállítani és előre konfigurálni, hogy azonnal használatra készek az elosztott munkawebhelyek között. |
| Operációs rendszer frissítései | Tartsa biztonságban a havi karbantartási frissítéseket, és használja ki az új hatékonysági és kezelhetőségi képességeket a két éves kiadásokban. |
| Eszközök egyszerű kezelése | Egyszerre több HoloLens 2 eszközt kezelhet olyan megoldásokkal, mint Microsoft Intune, a VMware Workspace One, a MobileIron stb. |
| Szabályozott környezetekben való működés | HoloLens 2. osztály egy kiterjedt eszközportfólióval rendelkezik, amely támogatja a szigorúan szabályozott környezeteket, beleértve az ISO 5.0 osztályt és az UL I. osztály 2. osztályt. |


## <a name="managing-hololens-2-in-your-organization"></a>A HoloLens 2. kezelése a szervezetben
HoloLens 2. része olyan funkciókat tartalmaz, amelyek megkönnyítik a szervezetek számára a HoloLens kezelését és használatát. Az eszköz tartalmaz néhány funkciót, míg mások a [Mobile Eszközkezelés (MDM)](hololens-mdm-configure.md) segítségével [](hololens-provisioning.md) HoloLens vagy a Configuration Designer használatával kiépítési csomagokon Windows [keresztül.](app-deploy-provisioning-package.md#setup)

| akarok... | Megoldás | Description |  
|---------| ------------|------------|
A végfelhasználók bejelentkezésének kezelése | [**Identitás**](hololens-identity.md) | HoloLens 2. csoport többféle felhasználói identitást támogat – Azure Active Directory (AAD), Microsoft-fiók (MSA) és helyi fiókok.  |
| Felhasználói adatok titkosítása | [**Adatbiztonság**](security-encryption-data-protection.md) | A 2. HoloLens bitLocker adattitkosítása a többi eszközével azonos szintű biztonsági Windows biztosít. | 
Hololens-eszközök kezelése a szervezetben | [**Mobileszköz-kezelés**](hololens-mdm-configure.md) | Beállítások kezelése, alkalmazások kiválasztása a telepítéshez és a szervezet igényeihez igazított biztonsági konfigurációk beállításához HoloLens 2 eszközön egy központi helyről. | 
|Az új felhasználók és eszközök beállítási ideje minimálisra csökkentése | [**Autopilot**](hololens2-autopilot.md) | Konfigurálja a használatra elérhető felhasználói élményt (OOBE) a Microsoft Endpoint Manager és lehetővé teszi a végfelhasználók számára, hogy kis vagy semmilyen interakcióval előkészítsék az eszközöket az üzleti használatra. |  
| Az eszközök operációsrendszer-frissítésének szabályozása | [**Windows Üzleti frissítés**](hololens-updates.md#managing-updates-by-using-windows-update-for-business) | Windows Az Update for Business szabályozott operációsrendszer-frissítéseket biztosít az eszközökhöz, és támogatja a hosszú távú karbantartási csatornát. |  
| Adott és LOB-alkalmazások letöltésének engedélyezése |[**Alkalmazáskezelés**](app-deploy-overview.md) | Válassza ki, hogyan terjesztheti és vezérelheti az alkalmazásokat 2 HoloLens csoport számára. | 
| Adott alkalmazások megjelenítése vagy elrejtése a Start menüben |[**Teljes képernyős mód**](hololens-kiosk.md) | Konfigurálja HoloLens 2.-t, hogy rögzített célú eszközként működve alkalmazásbemutatókban vagy dedikált üzleti alkalmazásokban használhatók. 
| A környezet védelme az alkalmazások zárolásának segítségével | [**WDAC**](windows-defender-application-control-wdac.md) | Windows Defender Az alkalmazásvezérlés (WDAC) megakadályozza, hogy az eszköz felhasználója elindítsa az alkalmazásokat és folyamatokat.
| Eszközbiztonság kezelése alkalmazásokra és folyamatokra vonatkozó szabályokkal | [**Szabályzatok (CSP-k)**](hololens-csp-policy-overview.md) | A rendszergazdák a 2. HoloLens támogatott házirend-CSP-k meglévő listájával határozhatják meg és valósítják meg a szabályzatbeállításokat. |  
| Az eszközök internetkapcsolatának kezelése | [**Hálózat és kapcsolatok**](hololens-certificates-network.md) | Tanúsítványalapú hitelesítéssel férhet hozzá Wi-Fi-hez, VPN-hez vagy belső erőforrásokhoz. | 
| Az eszköz megosztása több felhasználóval | [**Automatikusan testreszabott megjelenítés**](hololens-calibration.md#auto-eye-position-support) | HoloLens 2 kijelző automatikusan az automatikus szempozícióhoz (AEP) igazodik, így nincs szükség manuális beírási folyamat futtatására, ha az eszköz meg van osztva a [felhasználók között.](hololens-multiple-users.md) |

Ismerje meg [a fenti megoldások licencelési](hololens-licenses-requirements.md) követelményeit.

## <a name="next-steps"></a>Következő lépések
> [!div class="nextstepaction"]
> [Ismerkedés HoloLens két lehetőséggel](hololens2-options.md)

> [!div class="nextstepaction"]
>[A 2 HoloLens telepítés megtervezése](hololens-requirements.md) 
