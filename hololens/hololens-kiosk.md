---
title: A HoloLens beállítása kioszkként
description: Megtudhatja, hogyan állíthat be és használhat kioszkkonfigurációt az alkalmazások zárolásához a HoloLens eszközökön.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e856ac74e959743e8d05ea6acf583700a6450373
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032560"
---
# <a name="set-up-hololens-as-a-kiosk"></a>A HoloLens beállítása kioszkként

## <a name="what-is-kiosk-mode"></a>Mi az a kioszkmód?

A Kioszkmód funkcióval szabályozhatja, hogy mely alkalmazások jelennek meg a Start menüben, amikor egy felhasználó bejelentkezik a HoloLens. Két támogatott forgatókönyv íme:

1. **Egyalkalmazásos kioszkmód** – Nem jelenik meg a Start menü, és a rendszer automatikusan elindít egy alkalmazást, amikor a felhasználó bejelentkezik. <br> *A példa a* következőt használja: Olyan eszköz, amely csak a Dynamics 365 Guides alkalmazást futtatja.
2. **Többalkalmazásos kioszkmód** – Start menü csak azokat az alkalmazásokat jeleníti meg, amelyek kioszkkonfigurációban voltak megadva, amikor egy felhasználó bejelentkezik. Az alkalmazások szükség esetén automatikusan elindíthatóak. <br> *A példa* a következőt használja: Olyan eszköz, amely csak az Áruházbeli alkalmazást, Visszajelzési központ alkalmazást Gépház a Start menüben.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>A kioszkmód felhasználói bejelentkező élményének leírása

Az alábbi táblázat a különböző kioszkmódok funkcióit sorolja fel.

| &nbsp; |Start menü |Gyorsműveletek menü |Kamera és videó |Miracast |Cortana |Beépített hangparancsok |
| --- | --- | --- | --- | --- | --- | --- |
|Egyalkalmazásos kioszk |Disabled (Letiltva) |Disabled (Letiltva) |Disabled (Letiltva) |Disabled (Letiltva)   |Disabled (Letiltva) |Engedélyezve* |
|Többalkalmazásos kioszk |Engedélyezve |Engedélyezve*  |Elérhető*  |Elérhető* |Elérhető*   |Engedélyezve*  |

\*További információ a letiltott funkciók engedélyezéséről, illetve arról, hogy a hangparancsok hogyan lépnek interakcióba a letiltott funkciókkal és Cortana az [HoloLens AUMID-k használatával.](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>A kioszkmód konfigurálása előtt megfontolandó legfontosabb általános szempontok

1. Határozza meg, hogy milyen típusú felhasználói fiókkal jelentkezik be HoloLens-ba a környezetében – HoloLens támogatja a Azure Active Directory-, Microsoft-, MICROSOFT- (MSA-) és helyi fiókokat. Emellett az ideiglenesen létrehozott, vendégeknek/látogatóknak nevezett fiókok is támogatottak (csak az AAD-beléptető eszközök esetében). További információ: [Manage user identity and sign-in for HoloLens.](hololens-identity.md)
2. A kioszkmód céljainak meghatározása – Azt határozza meg, hogy mindenki, egyetlen felhasználó, bizonyos felhasználók vagy az AAD-csoportok tagjai stb.
3. Több alkalmazásos kioszkmód esetén határozza meg a Start menüben megmutatja az alkalmazás(ak)t. Minden alkalmazáshoz szükség lesz az alkalmazásfelhasználói modell azonosítójára [(AUMID).](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)
4. Állapítsa meg, hogy a rendszer alkalmazza-e a kioszkmódot a HoloLens kiépítési csomagokkal vagy a Mobile Eszközkezelés (MDM) kiszolgálóval.

## <a name="security-considerations"></a>Biztonsági szempontok

A kioszkmód nem tekinthető biztonsági módszernek, hanem a felhasználói bejelentkezés indítási élményének szabályozására. A kioszkmódot kombinálhatja az alább említett beállításokkal, ha speciális biztonsági igények vannak:

- Ha Gépház alkalmazás kioszkmódban való megjelenítéseként van konfigurálva, és szeretné szabályozni, hogy mely oldalak jelennek meg az Gépház alkalmazásban, tekintse meg az Oldaloldalak Gépház [megjelenítése](settings-uri-list.md)
- Ha szabályozni szeretné bizonyos hardverképességek( például kamera, kamera, Bluetooth stb.) hozzáférését bizonyos alkalmazások esetében, tekintse meg a [2.](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2)által támogatott szabályzatok csp-HoloLens – Windows Client Management (Ügyfélkezelés) alatt. Az ötletekért tekintse át a [gyakori eszközkorlátozásokat.](hololens-common-device-restrictions.md)
- A kioszkmód nem tiltja a (kioszkmód részeként konfigurált) alkalmazások más alkalmazások indítását. Ha teljesen le szeretné tiltani bizonyos alkalmazások/folyamatok elindítását a HoloLens-ban, tekintse meg a Use [Windows Defender Application Control on HoloLens 2 devices in Microsoft Intune - Azure](/mem/intune/configuration/custom-profile-hololens) (Az Windows Defender Application Control használata HoloLens 2 eszközön a Microsoft Intune - Azure

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>A kioszkmód fő technikai szempontjai a HoloLens

Csak akkor érvényes, ha a futásidejű kiépítési csomagok használatát vagy a kioszkkonfigurációk manuális létrehozását tervezi. A kioszkmód konfigurációja XML-alapú hierarchikus struktúrát használ:

- A hozzárendelt hozzáférési profil határozza meg, hogy mely alkalmazások jelennek meg a Start menüben kioszkmódban. Több profilt is definiálhat ugyanabban az XML-struktúrában, amelyekre később hivatkozhat.
- A hozzárendelt hozzáférési konfiguráció az adott profil profilja és célfelhasználóira hivatkozik, például egy adott felhasználóra, AAD-csoportra vagy látogatóra stb. A használati forgatókönyvek összetettségétől függően több konfigurációt is definiálhat ugyanabban az XML-struktúrában (lásd az alábbi támogatott forgatókönyvek szakaszt).
- További információ: [AssignedAccess CSP.](/windows/client-management/mdm/assignedaccess-csp)

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Az identitástípuson alapuló teljes kioszkmód támogatott forgatókönyvei

A [forgatókönyv alapján tekintse](hololens-kiosk-reference.md#kiosk-xml-code-samples) meg a referenciahivatkozásokat, és szükség szerint frissítsen a másolás beillesztése előtt.

> [!NOTE]
> Csak akkor használjon XML-t, ha nem használja az Intune felhasználói felületét a kioszkkonfiguráció létrehozásához.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Helyi fiókként vagy MSA-ként bejelentkező felhasználók esetén

| **Kívánt kioszkélmény** | **Ajánlott kioszkkonfiguráció** | **A konfigurálás módjai**  | **Megjegyzések** |
| --- | --- | --- | --- |
| Minden bejelentkező felhasználó kioszkélményt kap. | [Több alkalmazás globális hozzárendelt hozzáférési profiljának konfigurálása](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune sablon létrehozása](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Futásidejű kiépítés – Több alkalmazás](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | A globálisan hozzárendelt [hozzáféréshez 20H2 és újabb build szükséges](hololens-release-notes.md#windows-holographic-version-20h2) |
| A bejelentkező adott felhasználó kioszkélményt kap.  | [Konfiguráljon egy vagy több alkalmazáshoz hozzárendelt hozzáférési profilt (szükség szerint) egy adott felhasználó nevének megadásával.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [A támogatott lehetőségeket alább láthatja.](#steps-in-configuring-kiosk-mode-for-hololens) | Az egyalkalmazásos kioszkmódban csak a helyi felhasználói fiók vagy az MSA-fiók támogatott a HoloLens. <br> Többalkalmazásos kioszkmód esetén csak az MSA-fiók vagy az AAD-fiók támogatott a HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>AAD-fiókkal bejelentkező felhasználók számára

| **Kívánt kioszkélmény** | **Ajánlott kioszkkonfiguráció** | **A konfigurálás módjai** | **Megjegyzések** |
| --- | --- | --- | --- |
| Minden bejelentkező felhasználó kioszkélményt kap. | [Több alkalmazás globális hozzárendelt hozzáférési profiljának konfigurálása](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune sablon létrehozása](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Futásidejű kiépítés – Több alkalmazás](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | A globálisan hozzárendelt [hozzáféréshez 20H2 és újabb build szükséges](hololens-release-notes.md#windows-holographic-version-20h2) |
| Minden bejelentkező felhasználó kioszkélményt kap, kivéve bizonyos felhasználókat. | [Konfiguráljon több alkalmazáshoz globálisan hozzárendelt hozzáférési profilt](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners)úgy, hogy kizár bizonyos felhasználókat (akiknek eszköztulajdonosoknak kell lennie). | • [Microsoft Intune sablon létrehozása](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Futásidejű kiépítés – Több alkalmazás](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | A globálisan hozzárendelt [hozzáféréshez 20H2 és újabb build szükséges](hololens-release-notes.md#windows-holographic-version-20h2) |
| Minden AAD-felhasználó külön kioszkélményt kap az adott felhasználó számára. | [Konfigurálja a hozzárendelt hozzáférési konfigurációt minden felhasználóhoz, aki megadja az AAD-fiók nevét.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune sablon létrehozása](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Futásidejű kiépítés – Több alkalmazás](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| A különböző AAD-csoportok felhasználói csak a saját csoportjukhoz használható kioszkmódot tapasztalnak. | [Konfigurálja a hozzárendelt hozzáférési konfigurációt az egyes kívánt AAD-csoportokhoz.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune sablon létrehozása](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Futásidejű kiépítés – Több alkalmazás](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • Ha egy felhasználó bejelentkezik és HoloLens csatlakozik az internethez, és a felhasználó olyan AAD-csoport tagja, amelyhez kioszkkonfiguráció tartozik, a felhasználó az adott AAD-csoport teljes kioszkját tapasztalja. <br> • Ha nincs elérhető internet a felhasználói bejelentkezés során, a felhasználó hiba HoloLens [tapasztalja.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Ha az internet rendelkezésre állása nem garantált, amikor a felhasználó bejelentkezik, és AAD-csoportalapú kioszkot kell használnia, fontolja meg az [AADGroupMembershipCacheValidityInDayspolicy függvényt.](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk) <br> • Az AAD-csoportokkal való optimális bejelentkezéshez az [AADGroupMembershipCacheValidityInDayspolicy](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk) használata ajánlott |
| Azok a felhasználók, akiknek ideiglenes HoloLens kell használniuk, teljes kioszkélményt tapasztalnak. | [A látogatókhoz hozzárendelt hozzáférési konfiguráció konfigurálása](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune sablon létrehozása](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Futásidejű kiépítés – Egyetlen alkalmazás](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • Az ideiglenes felhasználói fiókot a rendszer HoloLens a bejelentkezéshez, és az ideiglenes felhasználó kijelentkeztével eltávolítja. <br> • Fontolja meg a [látogató automatikus bejelentkezési szabályzatának engedélyezését.](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience) |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>A kioszkmód konfigurálásához szükséges lépések HoloLens

A kioszkkonfigurációk a következő módokon lehet létrehozni és alkalmazni:

1. Az MDM-kiszolgáló felhasználói felületén, például az Intune kioszksablonjaival vagy egyéni OMA-URI-konfigurációival, amelyeket a rendszer távolról alkalmaz a HoloLens.
2. A futásidejű kiépítési csomagokkal, amelyeket a rendszer közvetlenül a HoloLens.

A konfigurálás következő módjai: válassza ki a használni kívánt folyamatnak megfelelő lapot.

1. [Microsoft Intune alkalmazás kioszksablonjának létrehozása](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune alkalmazás kioszksablonjának létrehozása](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune sablon létrehozása](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Futásidejű kiépítés – Több alkalmazás](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Futásidejű kiépítés – Egyetlen alkalmazás](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>Hogyan jelentkezhetnek be automatikusan a látogatói fiókok a kioszkélménybe?

A [Holographic Windows 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) és újabb verziókban:

- Az AAD- és a nem ADD-konfigurációk egyaránt támogatják a látogatói fiókok automatikus bejelentkezését a kioszkmódokhoz.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>Támogatott a kioszkélmény HoloLens (1. generációs)?

A kioszkmód csak akkor érhető el, ha az eszköz Windows Holographic for Business. Minden HoloLens 2 eszköz Windows Holographic for Business, és nincs más kiadás. Minden HoloLens 2 eszköz képes kioszkmódban is futni.

HoloLens (1. generációs) eszközöket az operációs rendszer buildszáma és az operációs rendszer kiadása szempontjából is frissíteni kell. Az itt található további információ a HoloLens (1. generációs) frissítéséről [Windows Holographic for Business](hololens1-upgrade-enterprise.md) kiadásra. Egy HoloLens (1. generációs) eszköz kioszkmód használatára való frissítéséhez először meg kell győződnie arról, hogy az eszköz Windows 10, 1803-as vagy újabb verziót futtat. Ha az Windows Device Recovery eszközt használta a HoloLens-eszköz (1. generációs) alapértelmezett buildre való helyreállításához, vagy ha telepítette a legújabb frissítéseket, az eszköz készen áll a konfigurálására.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Hogyan használható az eszközportál a kioszk nem éles környezetben való konfigurálását?

Állítsa be [a HoloLens eszközt a Windows Eszközportál.](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) A Eszközportál egy webkiszolgáló a HoloLens, amelyhez a számítógépén található webböngészőből csatlakozhat.

 > [!CAUTION]
 > Amikor beállít egy HoloLens a Eszközportál, engedélyeznie kell a Fejlesztői módot az eszközön. A fejlesztői mód olyan eszközön, Windows Holographic for Business lehetővé teszi az alkalmazások saját ről való betöltését. Ez a beállítás azonban azzal a kockázattal jár, hogy a felhasználó olyan alkalmazásokat telepíthet, amelyek nem voltak a Microsoft Store. A rendszergazdák letilthatják a fejlesztői mód engedélyezését az **ApplicationManagement/AllowDeveloper Unlock** beállítással a Házirend [CSP-ben.](/windows/client-management/mdm/policy-configuration-service-provider) [További információ a fejlesztői módról.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

A kioszkmód az Eszközportál REST API-ján keresztül állítható be úgy, hogy post parancsot ad az /api/holographic/kioszkmode/settings elemhez egy kötelező lekérdezési sztringparaméterrel ("kioszkModeEnabled" "true" vagy "false" értékkel), valamint egy opcionális paraméterrel ("startupApp" egy csomagnév értékével). Ne feledje, Eszközportál csak fejlesztőknek készült, és nem szabad engedélyezni a nem fejlesztői eszközökön. A REST API jövőbeli frissítések/kiadások változhatnak.

## <a name="troubleshooting"></a>Hibaelhárítás

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Probléma – A Start menüben nem jelennek meg alkalmazások kioszkmódban

**Hibajelenségek**

Ha a kioszkmód alkalmazása során hibák lépnek fel, a következő viselkedés jelenik meg:

- A holografikus Windows 20H2 - HoloLens az összes alkalmazást a Start menü.
- Windows Holographic, 20H2-es verzió – ha egy eszköz kioszkkonfigurációval rendelkezik, amely a globális és az AAD-csoporttaghoz rendelt hozzáférés kombinációjából áll, ha az AAD-csoporttagság meghatározása sikertelen, a felhasználó "semmi sem jelenik meg a Start menüben" menüben.

    ![Kép a kioszkmódról, ha meghibásodik.](images/hololens-kiosk-failure-behavior.png )

- A [Holographic Windows 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziótól kezdve a Kioszk mód a globális hozzárendelt hozzáférést keres, mielőtt megjelenít egy üres Start menüt. Ha az AAD-csoport kioszkmódja sikertelen, a kioszkmód vissza fog tért a globális kioszkkonfigurációra (ha van ilyen).

**Hibaelhárítási lépések**

- Ellenőrizze, hogy az alkalmazás AUMID azonosítója helyesen van-e megadva, és nem tartalmaz-e verziókat. Példákért [tekintse HoloLens AUMID-ket](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) a beérkezett alkalmazásokhoz.
- Győződjön meg arról, hogy az alkalmazás telepítve van az adott felhasználó eszközén.
- Ha a kioszkkonfiguráció AAD-csoportokon alapul, ellenőrizze, hogy van-e internetkapcsolat, amikor az AAD-felhasználó bejelentkezik. Ha szeretné, konfigurálja a [MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) szabályzatot, hogy az internet nélkül is működhet.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Probléma – A kioszkmódú csomagok kiépítése sikertelen volt

**Hibajelenségek**

Az alábbihoz hasonló párbeszédpanel jelenik meg.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Hibaelhárítási lépések**

1. Kattintson a fenti párbeszédpanelen látható hiperhivatkozásra.
1. Nyissa meg az ICD.log-t egy szövegszerkesztőben, és annak tartalma jelzi a hibát.

> [!NOTE]
> Ha több kísérletet is tett, ellenőrizze az időbélyegeket a naplóban. Ez csak az aktuális problémák ellenőrzésében segít.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Probléma – A kiépítési csomag sikeresen le lett építve, de nem sikerült alkalmazni.

**Hibajelenségek**

Hiba jelenik meg a kiépítési csomag Hololensen való alkalmazásakor

**Hibaelhárítási lépések**

1. Keresse meg azt a mappát, Windows Configuration Designer-projekt létezik a futásidejű kiépítési csomaghoz.
1. Nyissa meg az ICD.log-t, és ellenőrizze, hogy nincsenek-e hibák a naplóban a kiépítési csomag kiépítése során. Néhány hiba nem jelenik meg a build során, de továbbra is naplózásra kerül az ICD.log fájlban

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Probléma – Az AAD-csoporthoz rendelt több alkalmazáshoz rendelt hozzáférés nem működik

**Hibajelenségek**

Az AAD-felhasználó bejelentkezése esetén az eszköz nem vált kioszkmódba

**Hibaelhárítási lépések**

- A Hozzárendelt hozzáférés konfigurációs XML-fájljában győződjön meg arról, hogy annak az AAD-csoportnak a GUID-ja, amelynek a bejelentkezett felhasználó a tagja, és nem az AAD-felhasználó GUID-ja van használva.
- Győződjön meg arról, hogy az Intune-portálon az AAD-felhasználó valóban a megcélzott AAD-csoport tagjaként jelenik meg.
