---
title: Külső ügyfelek telepítési útmutatója
description: Üzembe helyezési útmutató a HoloLens 2-hez külső ügyfelek számára (példaként a Remote assist segítségével)
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
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378068"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>A HoloLens 2 telepítése külső ügyfelekre a Remote Assistszel

Ez az útmutató segítséget nyújt az informatikai szakembereknek a következő célok Microsoft HoloLens 2 eszköz telepítéséhez a szervezetben:

1. HoloLens 2-eszközök felhőbeli csatlakoztatása
1. Loan HoloLens 2 devices to external clients for use
1. Kölcsönhiteles eszközök biztonságossá teve

Ez az útmutató általános [HoloLens 2](#general-deployment-recommendations-and-instructions) üzembe helyezési javaslatokat tartalmaz, amelyek [](#common-concerns) a legtöbb HoloLens 2-es telepítési forgatókönyvre vonatkoznak, valamint az ügyfelek által a Remote Assist külső használatra történő telepítésekor gyakran merült fel aggályok.

## <a name="scenario-description"></a>Forgatókönyv leírása

Ebben a dokumentumban a Contoso vállalat egy HoloLens 2-eszközt szeretne egy külső ügyfél üzemének rövid vagy hosszú távú használatra. Ha az ügyfélnek segítségre van szüksége a gépek karbantartásához, az ügyfél bejelentkezik a HoloLens 2-eszközre a Contoso vállalat által megadott hitelesítő adatokkal, és a Remote Assist használatával kapcsolatba lép a Contoso vállalat szakértőivel.

A Remote Assistről itt olvashat [bővebben.](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="requirements-for-this-scenario"></a>A forgatókönyv követelményei

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. Mobileszközök Eszközkezelő – például [az Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. Remote Assist-licenc
    1. [Remote Assist vásárlása](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Remote Assist próbaverziója](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Gyakori problémák

- [Annak biztosítása, hogy a külső ügyfelek ne tudjanak kommunikálni egymással](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Annak biztosítása, hogy az ügyfelek ne férnek hozzá a vállalati erőforrásokhoz](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Alkalmazások korlátozása](#how-to-restrict-apps)
- [Jelszavak kezelése](#how-to-manage-passwords)
- [Annak biztosítása, hogy az ügyfelek ne férnek hozzá a csevegési előzményekhez](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Annak biztosítása, hogy a külső ügyfelek ne tudjanak kommunikálni egymással

Mivel a Remote Assist HoloLens-ről HoloLensre történő hívások nem támogatottak, az ügyfelek kereshetnek, de nem tudnak kommunikálni egymással. Annak további korlátozására, hogy ki kereshet és hívhat meg  [ügyfeleket,](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) az információs korlátok korlátozhatják, hogy kikkel kommunikálhatnak az ügyfelek. Egy másik megfontolható lehetőség a [hatókörrel kapcsolatos címtárkeresés használata](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Mivel az egyszeri bejelentkezés engedélyezve van, fontos letiltani a böngészőt a [**WDAC használatával.**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) Ha egy külső ügyfél megnyitja a böngészőt, és a Teams webes verzióját használja, az ügyfél hozzáférhet a hívási/csevegési előzményekhez.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Annak biztosítása, hogy az ügyfelek ne férnek hozzá a vállalati erőforrásokhoz

Két lehetőség közül választhat.

Az első lehetőség a többrétegű megközelítés:

1. Csak olyan licenceket rendeljen hozzá, amelyekre a felhasználónak szüksége van. Ha nem rendel hozzá OneDrive-ot, Outlookot, SharePointot, Yammert stb. a felhasználóhoz, akkor nem fog hozzáférni ezekhez az erőforrásokhoz. A felhasználóknak csak a Remote Assist-, Intune- és AAD-licencekre lesz szükségük a kezdéshez.
1. Letilthat olyan alkalmazásokat (például e-maileket), amelyekhez nem szeretné, hogy az ügyfelek hozzáférjenek (lásd: Alkalmazások [korlátozása).](#how-to-restrict-apps)
1. Ne ossza meg a felhasználóneveket és a jelszót az ügyfelekkel. A HoloLens 2-be való bejelentkezéshez szükség van egy e-mail-címre és egy numerikus PIN-kódra.

A második lehetőség az ügyfeleket tartalmazó különálló bérlő létrehozása (lásd az 1.1-es rendszerképet).

**1.1-es kép**

![Szolgáltatásbérlő rendszerképe](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Alkalmazások korlátozása

[A kioszkmód](https://docs.microsoft.com/hololens/hololens-kiosk) és/vagy [a WDAC (Windows Defender alkalmazásvezérlés)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) az alkalmazások korlátozására használható lehetőségek.

### <a name="how-to-manage-passwords"></a>Jelszavak kezelése

1. Jelszó lejáratának eltávolítása. Ez azonban növeli annak esélyét, hogy egy fiók biztonsága sérül. A NIST-jelszóra vonatkozó javaslat a jelszavak 30–90 naponta való módosítása.
1. A HoloLens 2-eszközök jelszó-lejáratának meghosszabbítása 90 napnál hosszabbra.
1. Az eszközöket vissza kell térnünk a Contosóhoz a jelszavak módosításahoz. Ez azonban problémákat okozhat, ha az eszközök várhatóan több mint 90 napig lesznek az ügyfél üzemében.  
1. A több ügyfélnek küldött eszközök esetén állítsa vissza a jelszavakat, mielőtt az eszközt az ügyfeleknek küldik.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Annak biztosítása, hogy az ügyfelek ne férnek hozzá a csevegési előzményekhez

A Remote Assist minden munkamenet után törli a csevegési előzményeket. A csevegési előzmények azonban elérhetők lesznek a Microsoft Teams-felhasználó számára.

> [!NOTE]
> Mivel az egyszeri bejelentkezés engedélyezve van, fontos letiltani a böngészőt a [**WDAC használatával.**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) Ha egy külső ügyfél megnyitja a böngészőt, és a Teams webes verzióját használja, az ügyfél hozzáférhet a hívási/csevegési előzményekhez.

## <a name="general-deployment-recommendations-and-instructions"></a>Általános üzembe helyezési javaslatok és utasítások

A HoloLens 2 üzembe helyezési lépései esetén a következőket javasoljuk:

1. Alapkonfigurációként használja a [HoloLens operációs](https://aka.ms/hololens2download) rendszer legújabb kiadását.
1. Felhasználóalapú vagy eszközalapú licencek hozzárendelése:
    1. A felhasználó- és eszközalapú licencek egyaránt az alábbi lépéseket követik:
        1. [Hozzon létre egy csoportot az AAD-ban, és adjon hozzá tagokat](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HoloLens-/RA-felhasználókhoz.
        1. [Rendeljen eszközalapú vagy felhasználóalapú licenceket](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) ehhez a csoporthoz.
        1. (Nem kötelező) Célcsoportokat is megcélzhat az MDM-szabályzatok számára.

1. Az eszközöknek az AAD-nek a bérlőhöz kell csatlakozva, automatikusan [regisztráltnak](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)kell lennie, és az automatikus [próba-teszten keresztül kell konfigurálni őket.](https://docs.microsoft.com/hololens/hololens2-autopilot)
    1. Vegye figyelembe, hogy az eszköz első felhasználója lesz az eszköz tulajdonosa.
    1. Vegye figyelembe, hogy ha az eszköz AAD-hez csatlakozik, akkor az összekapcsolt felhasználó lesz az eszköz tulajdonosa.
    1. További információ: [Eszköztulajdonos.](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)
1. [A bérlő zárolja](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) az eszközt, hogy csak a bérlőhöz csatlakozta.
    1. **További hivatkozás: Bérlői** [zárolási CSP.](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)
1. Konfigurálja a teljes kioszkot a globálisan hozzárendelt hozzáféréssel a [következőhöz:](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk).
1. Javasoljuk, hogy tiltsa le a következő (nem kötelező) képességeket:
    1. Az eszköz fejlesztői módba való beállításának [lehetősége itt található.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Lehetőség a HoloLens számítógéphez csatlakoztatására dátum másolása és [USB letiltása.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Ha nem szeretné letiltani az USB-t, de szeretné, hogy a kiépítési csomag USB-kapcsolaton keresztül alkalmazható az eszközre, kövesse az itt felsorolt [**utasításokat.**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. A [WDAC használatával](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) engedélyezheti vagy letilthatja az alkalmazásokat a HoloLens 2-eszközön.
1. A telepítés részeként frissítse a Remote Assistet a legújabb verzióra. Ezt kétféle lehetőséggel lehet megtenni:
    1. Ehhez a Windows Microsoft Store **--> Remote Assist -->** update app (Alkalmazás frissítése) > meg.
    1. [Az ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) – amely lehetővé teszi az automatikus alkalmazásfrissítéseket – alapértelmezés szerint engedélyezve van. A frissítések fogadása érdekében tartsa csatlakoztatva az eszközt.
1. [Tiltsa le az összes beállításoldalt,](https://docs.microsoft.com/hololens/settings-uri-list) kivéve a hálózati beállításokat, hogy a felhasználók vendéghálózathoz csatlakozva csatlakoznak az ügyfélhelyeken.
1. [HoloLens-frissítések kezelése](https://docs.microsoft.com/hololens/hololens-updates)
    1. Lehetőség az [operációs rendszer frissítésének szabályozására](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) vagy a szabadon áramló forgalomra.
1. [Gyakori eszközkorlátozások.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)
