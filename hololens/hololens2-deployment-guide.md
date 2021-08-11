---
title: Külső ügyfelek telepítési útmutatója
description: A 2. HoloLens útmutatója külső ügyfelekhez (példaként a Remote assist segítségével)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 495be858c235931ed591b097e6b5951f7197c3f7a62bd1aaa16bea65a4e3885f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659892"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>A 2 HoloLens telepítése külső ügyfelekre a Remote Assist alkalmazással

Ez az útmutató segítséget nyújt az informatikai szakembereknek a következő célok Microsoft HoloLens 2 eszköz üzembe helyezésében a szervezetben:

1. Felhőalapú csatlakozás HoloLens 2 eszközhöz
1. 2 HoloLens hitel hitele külső ügyfeleknek használatra
1. Kölcsönszerződéses eszközök biztonságossá tere

Ez az útmutató HoloLens [2.](#general-deployment-recommendations-and-instructions) központi telepítési javaslatokat tartalmaz, amelyek HoloLens 2. központi telepítési forgatókönyvre vonatkoznak, és az ügyfelek által a Remote Assist külső használatra történő telepítésekor gyakran merült fel aggályok. [](#common-concerns)

## <a name="scenario-description"></a>Forgatókönyv leírása

Ebben a dokumentumban a Contoso vállalat egy HoloLens 2-es eszközt szeretne kiszületni egy külső ügyfél üzemének rövid és hosszú távú használatra. Ha az ügyfélnek segítségre van szüksége a szervizelési géphez, az ügyfél a Contoso vállalat által megadott hitelesítő adatokkal jelentkezik be az HoloLens 2-es eszközre, és a Remote Assist használatával kapcsolatba lép a Contoso vállalat szakértőivel.

A Remote Assistről itt olvashat [bővebben.](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="requirements-for-this-scenario"></a>A forgatókönyv követelményei

1. [Azure AD](/azure/active-directory/fundamentals/active-directory-whatis)
1. Mobileszközök Eszközkezelő , például [az Intune](/mem/intune/fundamentals/free-trial-sign-up)
1. Remote Assist-licenc
    1. [A Remote Assist vásárlása](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Remote Assist próbaverziója](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Gyakori problémák

- [Annak biztosítása, hogy a külső ügyfelek ne tudjanak kommunikálni egymással](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Annak biztosítása, hogy az ügyfelek ne férnek hozzá a vállalati erőforrásokhoz](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Alkalmazások korlátozása](#how-to-restrict-apps)
- [Jelszavak kezelése](#how-to-manage-passwords)
- [Annak biztosítása, hogy az ügyfelek ne férnek hozzá a csevegési előzményekhez](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Annak biztosítása, hogy a külső ügyfelek ne tudjanak kommunikálni egymással

Mivel a Remote Assist HoloLens HoloLens hívások nem támogatottak, az ügyfelek kereshetnek, de nem tudnak kommunikálni egymással. Annak további korlátozására, hogy ki kereshet és hívhat meg  [ügyfeleket,](/microsoft-365/compliance/information-barriers) az információs korlátok korlátozhatják, hogy kikkel kommunikálhatnak az ügyfelek. Egy másik megfontolható lehetőség a [hatókörrel kapcsolatos címtárkeresés használata](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Mivel az egyszeri bejelentkezés engedélyezve van, fontos letiltani a böngészőt a [**WDAC használatával.**](/hololens/windows-defender-application-control-wdac) Ha egy külső ügyfél megnyitja a böngészőt, és a Teams webes verzióját használja, az ügyfél hozzáférhet a hívási/csevegési előzményekhez.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Annak biztosítása, hogy az ügyfelek ne férnek hozzá a vállalati erőforrásokhoz

Két lehetőség közül választhat.

Az első lehetőség a többrétegű megközelítés:

1. Csak olyan licenceket rendeljen hozzá, amelyekre a felhasználónak szüksége van. Ha nem rendel hozzá OneDrive, Outlook, SharePoint, Yammer-t stb. a felhasználóhoz, akkor nem fog hozzáférni ezekhez az erőforrásokhoz. A felhasználóknak csak a Remote Assist-, Intune- és AAD-licencekre lesz szükségük a kezdéshez.
1. Letilthatja az olyan alkalmazásokat (például e-maileket), amelyekhez nem szeretné, hogy az ügyfelek hozzáférjenek (lásd: Alkalmazások [korlátozása).](#how-to-restrict-apps)
1. Ne ossza meg a felhasználóneveket és a jelszót az ügyfelekkel. A 2. HoloLens való bejelentkezéshez szükség van egy e-mail-címre és egy numerikus PIN-kódra.

A második lehetőség az ügyfeleket tartalmazó különálló bérlő létrehozása (lásd az 1.1-es rendszerképet).

**1.1-es kép**

![Szolgáltatásbérlő rendszerképe](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Alkalmazások korlátozása

[A kioszkmód](/hololens/hololens-kiosk) és/vagy [WDAC (Windows Defender alkalmazásvezérlés)](/hololens/windows-defender-application-control-wdac) az alkalmazások korlátozásának lehetőségei.

### <a name="how-to-manage-passwords"></a>Jelszavak kezelése

1. Jelszó lejáratának eltávolítása. Ez azonban növeli annak esélyét, hogy egy fiók biztonsága sérül. Az NIST-jelszóra vonatkozó javaslat a jelszavak módosítása 30–90 naponta.
1. Hosszabbítsa meg a jelszó lejárati HoloLens 2 eszközre a 90 napot meghaladóra.
1. Az eszközöket vissza kell visszaküldeni a Contosónak, hogy módosítsa a jelszavakat. Ez azonban problémákat okozhat, ha az eszközök várhatóan több mint 90 napig lesznek az ügyfél üzemében.  
1. A több ügyfélnek küldött eszközök esetében állítsa vissza a jelszavakat, mielőtt az eszközt az ügyfelekhez szállítja.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Annak biztosítása, hogy az ügyfelek ne férnek hozzá a csevegési előzményekhez

A Remote Assist minden munkamenet után törli a csevegési előzményeket. A csevegési előzmények azonban elérhetők lesznek a Microsoft Teams számára.

> [!NOTE]
> Mivel az egyszeri bejelentkezés engedélyezve van, fontos letiltani a böngészőt a [**WDAC használatával.**](/hololens/windows-defender-application-control-wdac) Ha egy külső ügyfél megnyitja a böngészőt, és az Teams webes verzióját használja, az ügyfél hozzáférhet a hívási/csevegési előzményekhez.

## <a name="general-deployment-recommendations-and-instructions"></a>Általános üzembe helyezési Javaslatok és utasítások

A 2. üzembe helyezési HoloLens esetén a következőket javasoljuk:

1. [Alapkonfigurációként használja HoloLens operációs](https://aka.ms/hololens2download) rendszer legújabb kiadását.
1. Felhasználóalapú vagy eszközalapú licencek hozzárendelése:
    1. A felhasználó- és eszközalapú licencek egyaránt az alábbi lépéseket követik:
        1. [Hozzon létre egy csoportot az AAD-ban, és adjon](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) hozzá tagokat HoloLens/RA-felhasználók számára.
        1. [Rendeljen eszközalapú vagy felhasználóalapú licenceket](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) ehhez a csoporthoz.
        1. (Nem kötelező) Célcsoportokat is megcélzhat az MDM-szabályzatok számára.

1. Az eszközöknek az AAD-nek a bérlőhöz kell csatlakozva, automatikusan [regisztráltnak](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)kell lennie, és az [automatikus próba-teszten keresztül kell konfigurálni őket.](/hololens/hololens2-autopilot)
    1. Vegye figyelembe, hogy az eszköz első felhasználója lesz az eszköz tulajdonosa.
    1. Vegye figyelembe, hogy ha az eszköz AAD-hez csatlakozik, a csatlakozást hajtható végre felhasználó lesz az eszköz tulajdonosa.
    1. További információ: [Eszköztulajdonos.](/hololens/security-adminless-os#device-owner)
1. [A bérlő zárolja](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) az eszközt, hogy az csak a bérlőhöz csatlakozva csatlakozik.
    1. **További hivatkozás: Bérlői** [zárolási CSP.](/windows/client-management/mdm/tenantlockdown-csp)
1. Itt globálisan hozzárendelt hozzáféréssel konfigurálhatja a [kioszkot.](/hololens/hololens-global-assigned-access-kiosk)
1. Javasoljuk, hogy tiltsa le a következő (nem kötelező) képességeket:
    1. Az eszköz fejlesztői módba való beállításának lehetősége [itt található.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. A számítógéphez való csatlakozás HoloLens a másolási dátum letiltásához tiltsa [le az USB-t.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Ha nem szeretné letiltani az USB-t, de szeretné, hogy a kiépítési csomag USB-kapcsolaton keresztül alkalmazható az eszközre, kövesse az itt található [**utasításokat.**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. A [WDAC használatával](/hololens/windows-defender-application-control-wdac) engedélyezheti vagy letilthatja az alkalmazásokat HoloLens 2 eszközön.
1. A telepítés részeként frissítse a Remote Assistet a legújabb verzióra. Erre két lehetőség van:
    1. Ezt a Remote **Assist --Windows Microsoft Store --> -->** és az Update App (Alkalmazás frissítése) > meg.
    1. [Az ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) – amely lehetővé teszi az alkalmazás automatikus frissítését – alapértelmezés szerint engedélyezve van. Tartsa csatlakoztatva az eszközt a frissítések fogadása érdekében.
1. [Tiltsa le az összes](/hololens/settings-uri-list) beállításoldalt, kivéve a hálózati beállításokat, hogy a felhasználók vendéghálózathoz csatlakozva csatlakoznak az ügyfélhelyeken.
1. [A HoloLens frissítések kezelése](/hololens/hololens-updates)
    1. Lehetőség az [operációs rendszer frissítésének vezérlésére](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) vagy a szabadon áramló forgalomra.
1. [Gyakori eszközkorlátozások.](/hololens/hololens-common-device-restrictions)
