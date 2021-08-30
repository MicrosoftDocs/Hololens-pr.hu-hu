---
title: 2. felhőhöz csatlakoztatott HoloLens telepítése külső ügyfelek számára
description: Telepítési útmutató a HoloLens 2. ponthoz a külső ügyfelek számára (példaként a Távoli segítséget nyújtva)
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: d5cd9c380e0d276f0a8aa9efac14cf44885446e5
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190327"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>2. felhőhöz csatlakoztatott HoloLens telepítése külső ügyfelek számára

Ez az útmutató kiegészíti a felhőhöz csatlakoztatott [üzembe helyezési útmutatót.](hololens2-cloud-connected-overview.md) Olyan helyzetekben használják, amikor a szervezet két eszközt HoloLens egy külső ügyfél létesítményébe rövid vagy hosszú távú használatra. A külső ügyfél bejelentkezik a HoloLens 2. eszközre a szervezet által megadott hitelesítő adatokkal, és a [Remote Assist](/dynamics365/mixed-reality/remote-assist/ra-overview) segítségével kapcsolatba lép a szakértőkkel. Ez az útmutató HoloLens [2.](#general-deployment-recommendations) központi telepítési javaslatokat tartalmaz, amelyek a legtöbb [](#common-external-client-deployment-concerns) külső HoloLens 2 telepítési forgatókönyvre vonatkoznak, valamint az ügyfelek által a Remote Assist külső használatra történő telepítésekor gyakran merült fel aggodalmak. 

## <a name="prerequisites"></a>Előfeltételek

A felhőhöz csatlakoztatott üzembe [](hololens2-cloud-connected-overview.md) helyezési útmutatónak megfelelően az alábbi infrastruktúrát kell üzembe helyezni a 2. HoloLens üzembe helyezéséhez.

- Azure AD-csatlakozás MDM automatikus regisztrációval – MDM által felügyelt (Intune)
- A felhasználók a saját vállalati fiókjukkal (Azure AD) jelentkeznek be
    - Eszközönként egy vagy több felhasználó támogatott.

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist licenceléssel és követelményekkel

- Azure AD-fiók (az előfizetés megvásárlásához és a licencek hozzárendeléséhez szükséges)
- [Remote Assist-előfizetés](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (vagy [Remote Assist próbaverzió)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

További [információ a Remote Assist szolgáltatásról.](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist-felhasználó

- Remote Assist-licenc
- Hálózati kapcsolat

### <a name="microsoft-teams-user"></a>Microsoft Teams felhasználó

- Microsoft Teams Vagy [Teams Freemium](https://products.office.com/microsoft-teams/free)
- Hálózati kapcsolat

## <a name="general-deployment-recommendations"></a>Általános üzembe helyezési javaslatok

A 2- HoloLens esetén a következő lépéseket javasoljuk:

1. [Alapkonfigurációként használja HoloLens operációs](https://aka.ms/hololens2download) rendszer legújabb kiadását.
1. Rendeljen felhasználó- vagy eszközalapú licenceket az alábbi lépések szerint:
    1. [Hozzon létre egy csoportot az AAD-ban, és adjon hozzá tagokat](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) a HoloLens/RA-felhasználókhoz.
    1. [Rendeljen eszközalapú vagy felhasználóalapú licenceket](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) ehhez a csoporthoz.
    1. (Nem kötelező) Célcsoportok [mobileszköz-kezelési (MDM) szabályzatok](hololens-enroll-mdm.md) számára.

1. AAD-eszközök csatlakozása a bérlőhöz, [automatikus regisztráció,](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)és konfigurálás [az Autopiloton keresztül.](/hololens/hololens2-autopilot) További információ: [eszköztulajdonos.](/hololens/security-adminless-os#device-owner)
    1. Az eszköz első felhasználója az eszköz tulajdonosa lesz.
    1. Ha az eszköz AAD-be van beléptetve, az összekapcsolt felhasználó lesz az eszköz tulajdonosa.
    
1. [A bérlő zárolja](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) az eszközt, hogy csak az Ön bérlője csatlakoztathatja.
    1. Lásd [még: Bérlői zárolási CSP.](/windows/client-management/mdm/tenantlockdown-csp)

1. [A Kioszkmód konfigurálása globálisan hozzárendelt hozzáféréssel.](/hololens/hololens-global-assigned-access-kiosk)

1. Tiltsa le a következő (nem kötelező) képességeket:
    1. Az eszköz fejlesztői módba való beállítása itt [található.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. A számítógép csatlakoztatásának HoloLens a dátum másolása és az [USB letiltása.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Ha nem szeretné letiltani az USB-t, de szeretne alkalmazni egy kiépítési csomagot az eszközre USB-kapcsolaton keresztül, kövesse a kiépítési csomag telepítésének engedélyezése [utasításokat.](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Az [Windows Defender (WDAC)](/hololens/windows-defender-application-control-wdac) használatával engedélyezheti vagy letilthatja az alkalmazásokat a HoloLens 2 eszközön.
1. A telepítés részeként frissítse a Remote Assistet a legújabb verzióra. Vegye figyelembe a következő két lehetőséget:
    1. A Remote Assist Windows **Microsoft Store --> --> és az Update App**(Alkalmazás frissítése) között.
    1. [Az ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) – amely lehetővé teszi az automatikus alkalmazásfrissítéseket – alapértelmezés szerint engedélyezve van. A frissítések fogadása érdekében tartsa csatlakoztatva az eszközt.
1. [Tiltsa le az összes beállításoldalt,](/hololens/settings-uri-list) kivéve a hálózati beállításokat, hogy a felhasználók vendéghálózathoz csatlakozva csatlakoznak az ügyfélhelyeken.
1. [A HoloLens kezelése](/hololens/hololens-updates)
    1. Lehetőség az [operációs rendszer frissítésének szabályozására](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) vagy a szabadon áramló forgalomra.
1. Gyakori [eszközkorlátozások beállítása.](/hololens/hololens-common-device-restrictions)

A külső ügyfelek most már készen állnak a 2 HoloLens használatára.

## <a name="common-external-client-deployment-concerns"></a>A külső ügyfelek központi telepítésének gyakori aggodalmai

- [Annak biztosítása, hogy az ügyfelek ne kommunikáljanak egymással](#ensure-that-external-clients-cant-communicate-with-one-another)
- [Annak biztosítása, hogy az ügyfelek ne férnek hozzá a vállalati erőforrásokhoz](#ensure-that-clients-wont-have-access-to-company-resources)
- [Alkalmazások elrejtése vagy korlátozása](#hidden-or-restricted-apps)
- [Ügyfelek jelszavainak kezelése](#password-management-for-your-clients) 
- [Annak biztosítása, hogy az ügyfelek ne férnek hozzá a csevegési előzményekhez](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>Győződjön meg arról, hogy a külső ügyfelek nem tudnak kommunikálni egymással

A Remote Assist HoloLens a HoloLens hívások nem támogatottak. Az ügyfelek kereshetnek, de nem kommunikálhatnak egymással. [A felhasználók Microsoft 365](/microsoft-365/compliance/information-barriers) korlátozhatják, hogy ki kereshet és hívhat meg ügyfeleket. Másik lehetőségként egy hatókörrel [Microsoft Teams címtárkeresést is használhat.](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Mivel az egyszeri bejelentkezés engedélyezve van, fontos letiltani a böngészőt [az Windows Defender (WDAC) használatával.](/hololens/windows-defender-application-control-wdac) Ha egy külső ügyfél megnyitja a böngészőt, és a Teams webes verzióját használja, az ügyfél hozzáférhet a csevegési előzményekhez.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>Győződjön meg arról, hogy az ügyfelek nem férnek hozzá a vállalati erőforrásokhoz

Két lehetőség közül választhat.

Az első lehetőség a többrétegű megközelítés:

1. Csak olyan licenceket rendeljen hozzá, amelyekre a felhasználónak szüksége van. Ha nem rendel hozzá OneDrive, Outlook, SharePoint, Yammer stb. hozzárendelést, a felhasználó nem fog hozzáférni ezekhez az erőforrásokhoz. A felhasználóknak csak a Remote Assist-, Intune- és AAD-licencekre lesz szükségük a kezdéshez.
1. Letilthatja az ügyfelek számára nem elérhető alkalmazásokat (lásd: Az alkalmazások rejtettek [vagy korlátozottak).](#apps are hidden or restricted)
1. Ne ossza meg a felhasználóneveket és a jelszót az ügyfelekkel. A 2. HoloLens bejelentkezéshez e-mail-cím és numerikus PIN-kód szükséges.

A második lehetőség az ügyfeleket tartalmazó különálló bérlő létrehozása (lásd az 1.1-es rendszerképet).

**1.1-es kép**

![Szolgáltatásbérlő rendszerképe.](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>Rejtett vagy korlátozott alkalmazások

[A kioszkmód](/hololens/hololens-kiosk) [és/vagy Windows Defender alkalmazásvezérlés (WDAC)](/hololens/windows-efender-application-control-wdac) az alkalmazások elrejtésére és/vagy korlátozására használható lehetőségek.

### <a name="password-management-for-your-clients"></a>Jelszókezelés az ügyfelek számára

1. Jelszó lejáratának eltávolítása. Ez a beállítás azonban megnövelheti annak esélyét, hogy egy fiók biztonsága sérül. A NIST-jelszóra vonatkozó javaslat a jelszavak 30–90 naponta való módosítása.
1. Hosszabbítsa meg a jelszó lejárati HoloLens 2 eszközre a 90 napot meghaladóra.
1. Az eszközöknek vissza kell térnek a szervezethez, hogy módosítsuk a jelszavakat. Ez a beállítás azonban problémákat okozhat, ha az eszközök várhatóan több mint 90 napig lesznek az ügyfél üzemében.  
1. A több ügyfélnek küldött eszközök esetén állítsa vissza a jelszavakat, mielőtt az eszközt az ügyfeleknek küldik.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>Győződjön meg arról, hogy az ügyfelek nem férnek hozzá a csevegési előzményekhez

A Remote Assist minden munkamenet után törli a csevegési előzményeket. A csevegési előzmények azonban elérhetők lesznek a Microsoft Teams számára.

> [!NOTE]
> Mivel az egyszeri bejelentkezés engedélyezve van, fontos letiltani a böngészőt [az Windows Defender (WDAC) használatával.](/hololens/windows-defender-application-control-wdac)  Ha egy külső ügyfél megnyitja a böngészőt, és a Teams webes verzióját használja, az ügyfél hozzáférhet a hívási/csevegési előzményekhez.
