---
title: A HoloLens beállítása kioszkként
description: Megtudhatja, hogyan konfigurálhatja és használhatja a kioszkkonfigurációt az alkalmazások zárolására a HoloLens eszközökön.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 25227184ec33b134215dbd1f42f7b920b26dc29c
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659590"
---
# <a name="set-up-hololens-as-a-kiosk"></a>A HoloLens beállítása kioszkként

Az eszköz kioszkmódban való futtatásának konfigurálásával HoloLens eszközt rögzített célú eszközként (más néven *kioszkként)* is konfigurálhatja. A kioszkmód korlátozza az eszközön elérhető alkalmazásokat (vagy felhasználókat). A kioszkmód kényelmes funkció, amely segítségével egy HoloLens-eszközt üzleti alkalmazásoknak dedikálhat, vagy az HoloLens-eszközt egy alkalmazásbemutatóban használhatja.

Ez a cikk a teljes kioszkkonfigurációnak az egyes eszközökre jellemző HoloLens információkat. A különböző típusú számítógép-Windows és konfigurálásukról a Számítógépek és digitális aláírások konfigurálása asztali kiadásokon Windows [általános információkat.](/windows/configuration/kiosk-methods)  

> [!IMPORTANT]  
> A kioszkmód határozza meg, hogy mely alkalmazások érhetők el, amikor egy felhasználó bejelentkezik az eszközre. A kioszkmód azonban nem biztonsági módszer. Nem akadályoz meg, hogy az "engedélyezett" alkalmazások egy másik, nem engedélyezett alkalmazást nyitnak meg. Ha meg kell tiltani az alkalmazások vagy folyamatok megnyitását, a Windows Defender [(WDAC) CSP](/windows/client-management/mdm/applicationcontrol-csp) használatával hozza létre a megfelelő szabályzatokat.
>
> További információ a Microsoft-szolgáltatások, hogy a felhasználók a 2. HoloLens által használt fejlett biztonsági szintet biztosítják. További információk az állapotelválasztásról és -elkülönítésről – [Defender-védelem.](security-state-separation-isolation.md#defender-protections) Vagy megtudhatja, hogyan engedélyezheti vagy tilthatja Windows PowerShell HoloLens 2 eszközön a [WDAC](/mem/intune/configuration/custom-profile-hololens)és a Microsoft Intune.

A kioszkmód egyalkalmazásos vagy többalkalmazásos konfigurációban is használható, a három folyamat egyikének használatával pedig beállíthatja és üzembe helyezheti a kioszkkonfigurációt.

> [!IMPORTANT]  
> A többalkalmazásos konfiguráció törlésével eltávolítja a hozzárendelt hozzáférési funkció által létrehozott felhasználói zárolási profilokat. A szabályzatok módosításait azonban nem visszaállítja. A szabályzatok visszaállításához vissza kell állítania az eszközt a gyári beállításokra.

## <a name="plan-the-kiosk-deployment"></a>A kioszk üzembe helyezésének megterve

A kioszk megtervezésekor az alábbi kérdésekre kell választ adni. Íme néhány döntés, amit át kell gondolni az oldal elolvasása során, valamint néhány megfontolandó szempont ezekhez a kérdésekhez.
1. **Who kioszkot fogja használni, és milyen típusú [fiókot(ak)t](hololens-identity.md) fognak használni?** Ezt a döntést valószínűleg már meghozta, és nem kell módosítania a kioszk érdekében, de a kioszk hozzárendelését később befolyásolja.
1. **Felhasználónként/csoportonként eltérő kioszkra van szükség, vagy egyes felhasználóknál nincs engedélyezve kioszk?** Ha igen, a kioszkot XML-en keresztül kell létrehoznia. 
1. **Hány alkalmazás lesz a kioszkban?** Ha több mint 1 alkalmazással van, szüksége lesz egy többalkalmazásos kioszkra. 
1. **Mely alkalmazások lesznek a kioszkban?** Az alábbi AUMID-ket használva a saját alkalmazásai mellett In-Box alkalmazásokat is hozzáadhat.
1. **Hogyan tervezi üzembe helyezni a kioszkot?** Ha MDM-et regisztrál, javasoljuk, hogy használja az MDM-et a kioszk üzembe helyezéséhez. Ha nem MDM-et használ, akkor a kiépítési csomaggal való üzembe helyezés elérhető.  

### <a name="kiosk-mode-requirements"></a>A kioszkmód követelményei

A kioszkmód használatára HoloLens 2.eszköz bármelyikét konfigurálhatja.

> [!IMPORTANT]
> A kioszkmód csak akkor érhető el, ha az eszköz Windows Holographic for Business. Mind HoloLens 2 eszköz Windows Holographic for Business, és nincs más kiadás. Minden HoloLens 2 eszköz képes kioszkmódban futni.
>
> HoloLens (1. generációs) eszközöket az operációs rendszer buildszáma és az operációs rendszer kiadása szempontjából is frissíteni kell. További információ a HoloLens (1. Windows Holographic for Business [kiadásra.](hololens1-upgrade-enterprise.md) Egy HoloLens (1. generációs) eszköz kioszkmód használatára való frissítéséhez először meg kell győződnie arról, hogy az eszköz Windows 10, 1803-as vagy újabb verziót futtat. Ha az Windows Device Recovery eszközt használta az HoloLens-eszköz (1. generációs) helyreállításához az alapértelmezett buildre, vagy ha telepítette a legújabb frissítéseket, az eszköz készen áll a konfigurálására.

> [!IMPORTANT]  
> A kioszkmódban futó eszközök védelme érdekében érdemes lehet olyan eszközkezelési szabályzatokat hozzáadni, amelyek kikapcsolják az olyan funkciókat, mint az USB-kapcsolat. Emellett ellenőrizze a frissítési kör beállításait, és győződjön meg arról, hogy az automatikus frissítések nem lépnek fel munkaidőben.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Döntés az egyalkalmazásos kioszk és a többalkalmazásos kioszk között

Az egyalkalmazásos kioszk elindítja a megadott alkalmazást, amikor a felhasználó bejelentkezik az eszközre. A Start menü le van tiltva, ahogyan Cortana. A HoloLens 2-es eszköz nem válaszol az Indítás [kézmozdulatra.](hololens2-basic-usage.md#start-gesture) A HoloLens (1. generációs) eszköz nem válaszol a [Bloom-kézmozdulatra.](hololens1-basic-usage.md) Mivel csak egy alkalmazás futtatható, a felhasználó nem tud más alkalmazásokat futtatni.

A többalkalmazásos kioszk megjeleníti a Start menü amikor a felhasználó bejelentkezik az eszközre. A kioszkkonfiguráció határozza meg, hogy mely alkalmazások érhetők el a Start menü. A többalkalmazásos kioszkokkal könnyen érthető felhasználói élményt nyújthat, ha csak azokat a dolgokat mutatja be nekik, amelyekre szükségük van, és eltávolítja azokat a dolgokat, amelyekre nincs szükségük.

Az alábbi táblázat a különböző kioszkmódok funkcióit sorolja fel.

| &nbsp; |Start menü |Gyorsműveletek menü |Kamera és videó |Miracast |Cortana |Beépített hangparancsok |
| --- | --- | --- | --- | --- | --- | --- | 
|Egyalkalmazásos kioszk |Disabled (Letiltva) |Disabled (Letiltva) |Disabled (Letiltva) |Disabled (Letiltva)   |Disabled (Letiltva) |Engedélyezve<sup>1</sup> |
|Többalkalmazásos kioszk |Engedélyezve |<sup>Engedélyezve 2</sup> |Elérhető<sup>2</sup> |Elérhető<sup>2</sup> |Elérhető<sup>2, 3</sup>  |Engedélyezve<sup>1</sup> |

> <sup>1</sup> A letiltott funkciókhoz kapcsolódó hangparancsok nem működnek.  
> <sup>2</sup> További információ a funkciók konfigurálásról: [Select kioszk apps (Kioszkalkalmazások kiválasztása).](#plan-kiosk-apps)  
> <sup>3</sup> Még ha Cortana is le van tiltva, a beépített hangparancsok engedélyezve vannak.

Az alábbi táblázat a különböző kioszkmódok felhasználói támogatási funkcióit sorolja fel.

| &nbsp; |Támogatott felhasználótípusok | Automatikus bejelentkezés | Több hozzáférési szint |
| --- | --- | --- | --- |
|Egyalkalmazásos kioszk | Microsoft-fiók (MSA) Azure Active Directory (Azure AD) vagy helyi fiókban |Igen |Nem |
|Többalkalmazásos kioszk |Azure AD-fiók |Nem |Igen |

A képességek használatára vonatkozó példákat az alábbi táblázatban talál.

|Egyalkalmazásos kioszkot a következőre használhat: |Használjon többalkalmazásos kioszkot a következőre: |
| --- | --- |
|Olyan eszköz, amely csak Dynamics 365-útmutatót futtat új alkalmazottak számára. |Olyan eszköz, amely számos alkalmazott számára futtat útmutatókat és távsegítségeket. |
|Csak egyéni alkalmazást futtató eszköz. |Olyan eszköz, amely a legtöbb felhasználó számára kioszkként működik (csak egyéni alkalmazást futtat), de egy adott felhasználócsoport számára standard eszközként működik. |

### <a name="plan-kiosk-apps"></a>Kioszkalkalmazások megterve

A kioszkalkalmazások kiválasztásával kapcsolatos általános információkért lásd: [Guidelines for choose an app for assigned access (kioszkmód)](/windows/configuration/guidelines-for-assigned-access-app).

Ha a Windows Eszközportál egyalkalmazásos kioszkot konfigurál, a telepítési folyamat során kell kiválasztania az alkalmazást.  

Ha Mobile Eszközkezelés (MDM) rendszert vagy kiépítési csomagot használ a kioszkmód konfigurálása érdekében, az [AssignedAccess konfigurációszolgáltató (CSP)](/windows/client-management/mdm/assignedaccess-csp) használatával adhatja meg az alkalmazásokat. A CSP [alkalmazásfelhasználói modellben használt azonosítókat (AUMID) használ](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) az alkalmazások azonosításához. Az alábbi táblázat néhány, többalkalmazásos kioszkban használható, használatra használt alkalmazás AUMID-ját sorolja fel.

> [!IMPORTANT]
> A kioszkmód határozza meg, hogy mely alkalmazások érhetők el, amikor egy felhasználó bejelentkezik az eszközre. A kioszkmód azonban nem biztonsági módszer. Nem akadályoz meg, hogy az "engedélyezett" alkalmazások egy másik, nem engedélyezett alkalmazást nyitnak meg. Mivel ez nem korlátozza ezt a viselkedést, az alkalmazások továbbra is elindíthatóak az Edge-ben, a Fájlkezelőben és a Microsoft Store alkalmazásokban. Ha egyes alkalmazásokat nem szeretne kioszkból indítani, használja a [Windows Defender (WDAC) CSP-t](/windows/client-management/mdm/applicationcontrol-csp) a megfelelő szabályzatok létrehozásához. 
> 
> Emellett a Mixed Reality kezdőlapja nem lehet kioszkalkalmazásként beállítani.

<a id="aumids"></a>

|Alkalmazásnév |AUMID (AUMID) |
| --- | --- |
|3D-megjelenítő |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Naptár |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|<sup>1., 2. kamera</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3.</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! alkalmazás |
|Eszközválasztó a HoloLens (1. generációs) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Eszközválasztó a 2. HoloLens oldalon |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Dynamics 365-útmutatók |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|Visszajelzési &nbsp; központ |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! App |
|Fájlkezelő |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Régi Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Új Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> |&nbsp; |
|Filmek & TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Fotók |Microsoft. Windows. Photos \_ 8wekyb3d8bbwe \! App |
|Régi Gépház |HolographicSystemSettings_cw5n1h2txyewy! App |
|Új Gépház |BAEAEF15-9CAF-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Tippek |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> A fénykép- vagy videórögzítés engedélyezéséhez kioszkalkalmazásként engedélyeznie kell a Kamera alkalmazást.  
> <sup>2</sup> A Kamera alkalmazás engedélyezésekor vegye figyelembe a következő feltételeket:
> - A Gyorsműveletek menüben található a Fénykép és a Videó gomb.  
> - Emellett engedélyeznie kell egy olyan alkalmazást (például Fényképek, Mail vagy OneDrive), amely képes képekkel interakcióba lépni vagy lekérni.  
>  
> <sup>3</sup> Még ha nem is engedélyezi a Cortana kioszkalkalmazásként, a beépített hangparancsok is engedélyezve vannak. A letiltott funkciókhoz kapcsolódó parancsok azonban hatás nélkül használhatók.  
> <sup>4</sup> A közvetlen Miracast engedélyezhető. A kioszkalkalmazásként való Miracast engedélyezéséhez engedélyezze a Kamera alkalmazást és az Eszközválasztó alkalmazást.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Kioszkprofilok megtervezője felhasználókhoz vagy csoportokhoz

Amikor xml-fájlt hoz létre, vagy az Intune felhasználói felületén hoz létre kioszkot, figyelembe kell vennie, hogy ki lesz a Kioszk felhasználója. A kioszkkonfigurációk egy adott fiókra vagy Azure AD-csoportokra korlátozhatók. 

A kioszkok általában egy felhasználó vagy egy felhasználói csoport számára vannak engedélyezve. Ha azonban saját XML-kioszkot szeretne írni, érdemes megfontolni a globálisan hozzárendelt hozzáférést, amelyben a kioszk az eszköz szintjén lesz alkalmazva, identitástól függetlenül. Ha ez a helyzet, olvassa el [a globális hozzáférésű kioszkokat.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>HA XML-fájlt hoz létre:
-   Sokan hoznak létre több kioszkprofilt, és mindegyiket különböző felhasználókhoz/csoportokhoz rendelik. Ilyen például az Azure AD-csoport kioszkja, amely számos alkalmazással rendelkezik, és egy Látogató, amely több alkalmazásos kioszktal és egyetlen alkalmazással rendelkezik.
-   A kioszkkonfiguráció neve **profilazonosító** lesz, és egy GUID azonosítóval lesz.
-   Ezt a profilt a konfigurációk szakaszban úgy rendelheti hozzá, hogy megadja a felhasználó típusát, és ugyanazt a GUID azonosítót használja a **DefaultProfile azonosítóhoz.**
- Létrehozható egy XML-fájl, de továbbra is alkalmazható az eszközre az MDM-en keresztül egy egyéni OMA HoloLens URI eszközkonfigurációs profil létrehozásával, majd annak egy eszközcsoportra való alkalmazásával a következő URI érték használatával: ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Ha kioszkot hoz létre az Intune-ban.
-   Minden eszköz csak egyetlen kioszkprofilt kaphat, ellenkező esetben ütközést fog létrehozni, és egyáltalán nem kap kioszkkonfigurációt. 
    -   Más típusú profilok és szabályzatok, például a kioszkkonfigurációs profilhoz nem kapcsolódó eszközkorlátozások nem ütköznek a kioszkkonfigurációs profillal.
-   A kioszk minden olyan felhasználó számára engedélyezve lesz, aki a Felhasználói bejelentkezési típus része. Ez egy felhasználóval vagy Azure AD-csoporttal lesz beállítva. 
-   A Kioszkkonfiguráció és a Felhasználói bejelentkezés **típusa** (a kioszkba bejelentkező felhasználók) és az Alkalmazások kiválasztása után az Eszközkonfigurációt továbbra is hozzá kell rendelni egy csoporthoz. A Hozzárendelt csoport(ök) határozza meg, hogy mely eszközök kapják meg a kioszkeszköz konfigurációját, de nem lép interakcióba, ha a kioszk engedélyezve van vagy sem. 
    - A konfigurációs profilok Intune-ban való hozzárendelésének hatásairól a felhasználói és eszközprofilok hozzárendelése a [Microsoft Intune.](/intune/configuration/device-profile-assign)

### <a name="select-a-deployment-method"></a>Üzembe helyezési módszer kiválasztása

A kioszkkonfigurációk telepítéséhez az alábbi módszerek egyikét választhatja:

- [Microsoft Intune mobileszköz-kezelési (MDM) szolgáltatás](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Kiépítési csomag](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Eszközportál](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Mivel ez a módszer megköveteli, hogy a Fejlesztői mód engedélyezve legyen az eszközön, javasoljuk, hogy csak bemutatókhoz használja.

Az alábbi táblázat az egyes üzembe helyezési módszerek képességeit és előnyeit sorolja fel.

| &nbsp; |Üzembe helyezés a Windows Eszközportál |Üzembe helyezés kiépítési csomag használatával |Üzembe helyezés MDM használatával |
| --------------------------- | ------------- | -------------------- | ---- |
|Egyalkalmazásos kioszkok üzembe helyezése   | Igen           | Igen                  | Igen  |
|Többalkalmazásos kioszkok üzembe helyezése    | Nem            | Igen                  | Igen  |
|Üzembe helyezés csak helyi eszközökön | Igen           | Igen                  | Nem   |
|Üzembe helyezés fejlesztői móddal |Kötelező       | Nem szükséges            | Nem szükséges   |
|Üzembe helyezés Azure Active Directory (Azure AD) használatával  | Nem szükséges            | Nem szükséges                   | Kötelező  |
|Automatikus üzembe helyezés      | Nem            | Nem                   | Igen  |
|Üzembe helyezés sebessége            | Gyors       | Gyors                 | Lassú |
|Nagy léptékű üzembe helyezés | Nem ajánlott    | Ajánlott        | Ajánlott |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Egyetlen Microsoft Intune vagy többalkalmazásos kioszk beállítása többalkalmazásos vagy más MDM használatával

Ha a kioszkmódot egy vagy Microsoft Intune MDM-rendszerrel is be Microsoft Intune, kövesse az alábbi lépéseket.

1. [Készítse elő az eszközök regisztrálását.](#mdmenroll)
1. [Hozzon létre egy kioszkkonfigurációs profilt.](#mdmprofile)
1. Konfigurálja a kioszkot.
   - [Egyalkalmazásos kioszk beállításainak konfigurálása.](#mdmconfigsingle)
   - [Többalkalmazásos kioszk beállításainak konfigurálása.](#mdmconfigmulti)
1. [Rendelje hozzá a kioszkkonfigurációs profilt egy csoporthoz.](#mdmassign)
1. Az eszközök üzembe helyezése.
   - [Egyalkalmazásos kioszk üzembe helyezése.](#mdmsingledeploy)
   - [Többalkalmazásos kioszk üzembe helyezése.](#mdmmultideploy)

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, &ndash; 1. lépés: Felkészülés az eszközök regisztrálásához

Az MDM-rendszert beállíthatja úgy, hogy a HoloLens automatikusan regisztrálja az eszközöket, amikor a felhasználó először jelentkezik be, vagy hogy a felhasználók manuálisan regisztrálják az eszközöket. Az eszközöket az Azure AD-tartományhoz is hozzá kell rendelni, és hozzá kell rendelni a megfelelő csoportokhoz.

Az eszközök regisztrálásával kapcsolatos további információkért lásd: Regisztráció HoloLens az [MDM-hez](hololens-enroll-mdm.md) és az Intune regisztrációs [módszereihez Windows eszközökhöz.](/mem/intune/enrollment/windows-enrollment-methods)

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, &ndash; 2. lépés: Kioszkkonfigurációs profil létrehozása

1. Nyissa meg [az Azure](https://portal.azure.com/) Portalt, és jelentkezzen be Intune-rendszergazda fiókjába.
1. Válassza **Microsoft Intune**  >  **Eszközkonfiguráció – Profilok Profil** létrehozása  >  **lehetőséget.**
1. Adja meg a profil nevét.
1. Válassza **a Platform** Windows 10 és  >  **újabb** lehetőséget, majd válassza az **Eszközkorlátozások**  > **profiltípust.**
1. Válassza **a**  >  **Kioszk konfigurálása** lehetőséget, majd válasszon az alábbiak közül:
   - Egyalkalmazásos kioszk létrehozásához válassza a **Kioszkmód**  >  **Egyalkalmazásos kioszk lehetőséget.**
   - Többalkalmazásos kioszk létrehozásához válassza a **Kioszkmód**  >  **Többalkalmazásos kioszk lehetőséget.**
1. A kioszk konfigurálásához válassza a Hozzáadás **lehetőséget.**

A következő lépések a kívánt kioszktípustól függően eltérőek lehetnek. További információért válasszon az alábbi lehetőségek közül:  

- [Egyalkalmazásos kioszk](#mdmconfigsingle)
- [Többalkalmazásos kioszk](#mdmconfigmulti)

A kioszkkonfigurációs profil létrehozásáról további információt az Eszközbeállítások konfigurálása és Windows 10 Windows Holographic for Business dedikált [kioszkként](/intune/configuration/kiosk-settings)való futtatásához az Intune használatával.

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, 3. lépés (egyalkalmazásos) &ndash;  Egyalkalmazásos kioszk beállításainak konfigurálása

Ez a szakasz az egyalkalmazásos kioszkbeállításokat foglalja össze. További részletekért tekintse meg a következő cikkeket:

- A kioszkkonfigurációs profilok Intune-ban való konfigurálásával kapcsolatos információkért lásd: [Kioszkmód](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)konfigurálása a Microsoft Intune.
- Az egyalkalmazásos kioszkok Intune-ban elérhető beállításaival kapcsolatos további információkért lásd: Egy teljes képernyős alkalmazás teljes képernyős [kioszkja](/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Más MDM-szolgáltatásokhoz a szolgáltató dokumentációjában talál útmutatást. Ha egyéni XML-konfigurációt kell használnia egy kioszk beállítására az MDM-szolgáltatásban, hozzon létre egy XML-fájlt, amely meghatározza a [kioszkkonfigurációt.](#ppkioskconfig)

1. Válassza **a Felhasználói bejelentkezés** típusa Helyi felhasználói fiók lehetőséget, majd adja meg annak a helyi (eszköz) fióknak vagy Microsoft-fióknak (MSA) a felhasználónevét, amely bejelentkezhet a  >  kioszkra.
   > [!NOTE]  
   > Az **Automatikus bejelentkezésű** felhasználói fiókokat a Windows Holographic for Business nem támogatja.
1. Válassza **az Alkalmazástípus**  >  **Áruházbeli alkalmazás** lehetőséget, majd válasszon ki egy alkalmazást a listából.

A következő lépés a [profil](#mdmassign) hozzárendelése egy csoporthoz.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, 3. lépés (többalkalmazásos) Többalkalmazásos &ndash; kioszk beállításainak konfigurálása

Ez a szakasz a többalkalmazásos kioszkok által megkövetelt beállításokat foglalja össze. További részleteket az alábbi cikkekben találhat:

- A kioszkkonfigurációs profilok Intune-ban való konfigurálásával kapcsolatos információkért lásd: [Kioszkmód](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)konfigurálása a Microsoft Intune.
- További információ a többalkalmazásos kioszkok Intune-ban elérhető beállításairól: [Többalkalmazásos kioszkok](/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Más MDM-szolgáltatásokhoz a szolgáltató dokumentációjában talál útmutatást. Ha egyéni XML-konfigurációt kell használnia egy kioszk beállítására az MDM-szolgáltatásban, hozzon létre egy XML-fájlt, amely meghatározza a [kioszkkonfigurációt.](#ppkioskconfig) XML-fájl használata esetén ügyeljen arra, hogy tartalmazza a [Start (Indítás) elrendezést.](#start-layout-for-hololens)  
- Igény szerint egyéni Start elrendezést is használhat az Intune-nal vagy más MDM-szolgáltatásokkal. További információ: [Start layout file for MDM (Intune and others) (Elrendezésfájl létrehozása az MDM-hez (Intune és egyebek)](#start-layout-file-for-mdm-intune-and-others)).

1. S **módú Windows 10 válassza a Célcsoport**  >  **lehetőséget Nem.**  
>[!NOTE]  
> Az S mód nem támogatott a Windows Holographic for Business.

1. Válassza **a Felhasználói bejelentkezés típusa** Azure  >  **AD-felhasználó** vagy -csoport, vagy a HoloLens bejelentkezési típust a látogató számára, majd adjon hozzá egy vagy több felhasználói csoportot   >  vagy fiókot.  

   A kioszkélményt csak azok a  felhasználók használhatják, akik a Felhasználói bejelentkezés típusa beállításban megadott csoportokhoz vagy fiókokhoz tartoznak.

1. Válasszon ki egy vagy több alkalmazást az alábbi beállításokkal:
   - Feltöltött üzletági alkalmazás hozzáadásához válassza az **Áruházbeli** alkalmazás hozzáadása lehetőséget, majd válassza ki a kívánt alkalmazást.
   - Ha az alkalmazás AUMID-ját megadásával szeretne hozzáadni, válassza a Hozzáadás **AUMID** alapján lehetőséget, majd adja meg az alkalmazás AUMID-ját. [Tekintse meg az elérhető AUMID-ket](#aumids)

A következő lépés a [profil](#mdmassign) hozzárendelése egy csoporthoz.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, 4. &ndash; lépés: A kioszkkonfigurációs profil hozzárendelése csoporthoz

A **kioszkkonfigurációs** profil Hozzárendelések lapján beállíthatja, hogy hol szeretné telepíteni a kioszkkonfigurációt. A legegyszerűbb esetben hozzárendeli a kioszkkonfigurációs profilt egy olyan csoporthoz, amely az HoloLens eszközt fogja tartalmazni, amikor az eszköz regisztrálva lesz az MDM-be.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, 5. lépés (egyalkalmazásos) &ndash; Egyalkalmazásos kioszk üzembe helyezése

Ha MDM-rendszert használ, az eszközt az OOBE során regisztrálhatja az MDM-ben. Az OOBE befejeződés után egyszerűen bejelentkezik az eszközre.

Az OOBE során kövesse az alábbi lépéseket:

1. Jelentkezzen be a kioszkkonfigurációs profilban megadott fiókkal.
1. Regisztrálja az eszközt. Győződjön meg arról, hogy az eszköz hozzá van adva ahhoz a csoporthoz, amelyhez a kioszkkonfigurációs profil hozzá van rendelve.
1. Várja meg az OOBE befejezését, az áruházbeli alkalmazás letöltését és telepítését, valamint a szabályzatok alkalmazását. Ezután indítsa újra az eszközt.

Amikor legközelebb bejelentkezik az eszközre, a kioszkalkalmazásnak automatikusan elindul.

Ha ezen a ponton nem látja a kioszkkonfigurációt, ellenőrizze [a hozzárendelés állapotát.](/intune/configuration/device-profile-monitor)

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, 5. lépés (többalkalmazásos) &ndash; Többalkalmazásos kioszk üzembe helyezése

Ha MDM-rendszert használ, az eszközt az Azure AD-bérlőhöz is használhatja, és az OOBE során regisztrálhatja az eszközt az MDM-ben. Ha szükséges, adja meg a regisztrációs adatokat a felhasználóknak, hogy az OOBE-folyamat során elérhetők legyen.

> [!NOTE]  
> Ha felhasználókat tartalmazó csoporthoz rendelte a kioszkkonfigurációs profilt, győződjön meg arról, hogy az egyik ilyen felhasználói fiók az első fiók az eszközre való bejelentkezéshez.

Az OOBE során kövesse az alábbi lépéseket:

1. Jelentkezzen be a Felhasználói bejelentkezés típusa csoporthoz **tartozó fiókkal.**
1. Regisztrálja az eszközt.
1. Várjon, amíg a kioszkkonfigurációs profil részét képezi minden alkalmazás letöltése és telepítése. Emellett várja meg a szabályzatok alkalmazását.  
1. Az OOBE befejeződése után további alkalmazásokat telepíthet a Microsoft Áruházból vagy a telepítés után. [Az eszközhöz](/mem/intune/apps/apps-deploy#assign-an-app) tartozó csoporthoz szükséges alkalmazások automatikus telepítése.
1. A telepítés befejezése után indítsa újra az eszközt.

Amikor legközelebb bejelentkezik az eszközre egy felhasználói bejelentkezéshez tartozó fiókkal, a kioszkalkalmazásnak automatikusan elindul.

Ha ezen a ponton nem látja a kioszkkonfigurációt, ellenőrizze [a hozzárendelés állapotát.](/intune/configuration/device-profile-monitor)

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Kiépítési csomag használata egyalkalmazásos vagy többalkalmazásos kioszk beállítására

A kioszkmód kiépítési csomag használatával való beállítását az alábbi lépésekkel lehet beállítani.

1. [Hozzon létre egy XML-fájlt, amely meghatározza a kioszkkonfigurációt.](#ppkioskconfig), beleértve a [Start elrendezést is.](#start-layout-for-hololens)
2. [Adja hozzá az XML-fájlt egy kiépítési csomaghoz.](#ppconfigadd)
3. [Alkalmazza a kiépítési csomagot a HoloLens.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Kiépítési csomag, &ndash; 1. lépés: Kioszkkonfigurációs XML-fájl létrehozása

Kövesse [az általános utasításokat egy kioszkkonfigurációs XML-fájl](/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)létrehozásához Windows asztali számítógéphez, kivéve a következőket:

- Ne foglalja bele a klasszikus Windows alkalmazásokba (Win32). HoloLens nem támogatja ezeket az alkalmazásokat.
- Használja a [helyőrző elrendezésének kezdő XML-fájlját](#start-layout-for-hololens) a HoloLens.
- Nem kötelező: Vendég hozzáférés hozzáadása a kioszkkonfigurációhoz

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Nem kötelező: Vendég hozzáférés hozzáadása a kioszkkonfigurációhoz

Az [ **XML-fájl Configs**](/windows/configuration/lock-down-windows-10-to-specific-apps#configs)(Konfigurációk) szakaszában konfigurálhat egy **Látogató** nevű speciális csoportot, amely lehetővé teszi a vendégek számára a kioszk használatát. Ha a kioszk úgy van konfigurálva, hogy támogassa a **Látogató** speciális csoportot, a bejelentkezési oldalon egy **"Vendég"** lehetőség lesz hozzáadva. A **vendégfiókhoz** nincs szükség jelszóra, és a fiókhoz társított összes adat törlődik a fiók kiesése után.

A vendégfiók **engedélyezéséhez** adja hozzá a következő kódrészletet a kioszkkonfigurációs XML-fájlhoz:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>Látogatói automatikus bejelentkezés engedélyezése

A [Holographic Windows 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) és újabb verziójú buildek:
- Az AAD- és a nem ADD-konfigurációk egyaránt támogatják a látogatói fiókok automatikus bejelentkezését a kioszkmódokhoz.

##### <a name="non-aad-configuration"></a>Nem AAD-konfiguráció

1. Hozzon létre egy kiépítési csomagot, amely:
    1. Úgy konfigurálja a Futásidejű beállításokat/AssignedAccess-t, hogy engedélyezze a látogatói fiókokat.
    1. Ha szükséges, regisztrálja az eszközt az MDM-be (Futásidejű beállítások/Munkahely/Regisztrációk), hogy később kezelhető legyen.
    1. Ne hozzon létre helyi fiókot
2. [Alkalmazza a kiépítési csomagot.](hololens-provisioning.md)

##### <a name="aad-configuration"></a>AAD-konfiguráció

A kioszkmódhoz konfigurált AAD-hez csatlakozott eszközök egyetlen gomb koppintással bejelentkeztetnek egy látogatói fiókot a bejelentkezési képernyőről. Miután bejelentkezett a látogatói fiókba, az eszköz nem kéri újra a bejelentkezést, amíg a Látogató kijelentkezik a Start menüből, vagy újra nem indítják az eszközt.

A látogatói automatikus bejelentkezés egyéni [OMA-URI szabályzat](/mem/intune/configuration/custom-settings-windows-10)segítségével kezelhető:

- URI-érték: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| Szabályzat |Description |Konfigurációk 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Lehetővé teszi a látogató számára a kioszkba való automatikus bejelentkezést. | 1 (Igen), 0 (Nem, alapértelmezés.) |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Helyőrző Kezdő elrendezése HoloLens

Ha egy [kiépítési csomaggal](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) konfigurál egy többalkalmazásos kioszkot, az eljáráshoz indítási elrendezésre van szükség. A start elrendezés testreszabása nem támogatott a Windows Holographic for Business. Ezért helyőrzőt kell használnia a Start elrendezésben.

> [!NOTE]  
> Mivel egy egyalkalmazásos kioszk elindítja a kioszkalkalmazást, amikor egy felhasználó bejelentkezik, nem használ Start menü és nem kell Start elrendezést használnia.

> [!NOTE]  
> Ha [MDM-et](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) használ egy többalkalmazásos kioszk beállítására, használhat Indítás elrendezést is. További információ: [Helyőrző Start elrendezési fájl az MDM-hez (Intune és egyebek).](#start-layout-file-for-mdm-intune-and-others)

A Start elrendezéshez adja hozzá a **következő StartLayout** szakaszt a kioszkkiépítési XML-fájlhoz:

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>Helyőrző Start elrendezési fájl az MDM-hez (Intune és egyebek)

Mentse az alábbi mintát XML-fájlként. Ezt a fájlt akkor használhatja, ha a többalkalmazásos kioszkot a Microsoft Intune (vagy egy másik, kioszkprofilt szolgáltató MDM-szolgáltatásban) konfigurálja.

> [!NOTE]
> Ha egyéni beállítást és teljes XML-konfigurációt kell használnia egy kioszk beállítására az MDM-szolgáltatásban, használja a kiépítési csomag elrendezésének indítási [utasításait.](#start-layout-for-hololens)

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Péld. package, 2. &ndash; lépés: A kioszkkonfigurációs XML-fájl hozzáadása kiépítési csomaghoz

1. Nyissa [meg Windows Configuration Designert.](https://www.microsoft.com/store/apps/9nblggh4tx22)
1. Válassza **a Speciális kiépítés** lehetőséget, adja meg a projekt nevét, majd válassza a Tovább **lehetőséget.**
1. Válassza **Windows 10 Holographic** lehetőséget, majd kattintson a **Tovább gombra.**
1. Válassza a **Befejezés** gombot. Megnyílik a csomag munkaterülete.
1. Válassza **a Runtime settings**  >  AssignedAccess MultiAppAssignedAccessSettings (Futtatási **beállítások: AssignedAccess**  >  **MultiAppAssignedAccessSettings) lehetőséget.**
1. A középső panelen a **Tallózás gombra** kattintva keresse meg és válassza ki a létrehozott kioszkkonfigurációs XML-fájlt.

   ![Képernyőkép a KonfigurációtervezőBen a MultiAppAssignedAccessSettings Windows](./images/multiappassignedaccesssettings.png)

1. **Nem kötelező.** (Ha az eszköz kezdeti beállítása után szeretné alkalmazni a kiépítési csomagot, és már van rendszergazdai felhasználó a kioszkeszközön, hagyja ki ezt a lépést.) Válassza **a Futásidejű beállítások** &gt; **Fiókok** felhasználói &gt; **lehetőséget,** majd hozzon létre egy felhasználói fiókot. Adjon meg egy felhasználónevet és egy jelszót, majd válassza a **UserGroup-rendszergazdák**  >  **lehetőséget.**  
  
     Ezzel a fiókkal megtekintheti a kiépítési állapotot és a naplókat.  
1. **Nem kötelező.** (Ha már rendelkezik nem rendszergazdai fiókkal a kioszkeszközön, hagyja ki ezt a lépést.) Válassza **a Futásidejű beállítások** &gt; **Fiókok** &gt; **felhasználói** lehetőséget, majd hozzon létre egy helyi felhasználói fiókot. Győződjön meg arról, hogy a felhasználónév megegyezik a konfigurációs XML-fájlban megadott fiók nevével. Válassza **a UserGroup**  >  **Standard Users lehetőséget.**
1. Válassza a **Fájl**  >  **mentése lehetőséget.**
1. Válassza **a**  >  **Kiépítési csomag exportálása,** majd a   >  **Tulajdonosi rendszergazda lehetőséget.** Ez magasabb prioritást ad meg ennek a kiépítési csomagnak, mint a más forrásokból az eszközre alkalmazott kiépítési csomagoknak.
1. Kattintson a **Tovább** gombra.
1. A **Kiépítési csomag biztonsága lapon** válasszon egy biztonsági lehetőséget.
   > [!IMPORTANT]  
   > Ha a **Csomagalá aláírásának engedélyezése** lehetőséget választja, ki kell választania egy érvényes tanúsítványt a csomag aláírásához. Ehhez válassza a **Tallózás** lehetőséget, és válassza ki a csomag aláíráshoz használni kívánt tanúsítványt.
   
   > [!CAUTION]  
   > Ne jelölje be a **Csomagtitkosítás engedélyezése lehetőséget.** A HoloLens esetén ez a beállítás a kiépítés sikertelen lesz.
1. Kattintson a **Tovább** gombra.
1. Adja meg a kimeneti helyet, ahová a kiépítési csomagot el szeretné látni a felépítéskor. Alapértelmezés szerint a Windows Configuration Designer a projektmappát használja kimeneti helyként. Ha módosítani szeretné a kimeneti helyet, válassza a Tallózás **lehetőséget.** Ha elkészült, válassza a Tovább **lehetőséget.**
1. Válassza **a Build (Build)** lehetőséget a csomag felépítésének elkezdődjön. A kiépítési csomag kiépítése nem tart sokáig. A build oldal megjeleníti a projektinformációkat, a folyamatjelző sáv pedig a build állapotát jelzi.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Kiépítési csomag, 3. &ndash; lépés: A kiépítési csomag alkalmazása a HoloLens

A "HoloLens konfigurálása kiépítési csomag használatával" cikk részletes utasításokat tartalmaz a kiépítési csomag a következő körülmények között való alkalmazásával:

- Kezdetben alkalmazhat [egy kiépítési](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)csomagot a HoloLens során.

- A telepítés [után üzembe HoloLens is alkalmazhat egy kiépítési csomagot.](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>A Windows Eszközportál egyalkalmazásos kioszk beállítására

Ha a kioszkmódot a Windows Eszközportál meg, kövesse az alábbi lépéseket.

1. [Állítsa be a HoloLens eszközt az Windows Eszközportál.](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal) A Eszközportál egy webkiszolgáló a HoloLens, amelyhez a számítógép webböngészőjéből csatlakozhat.

    > [!CAUTION]
    > Amikor beállít egy HoloLens a Eszközportál, engedélyeznie kell a Fejlesztői módot az eszközön. A fejlesztői mód olyan eszközön, amely Windows Holographic for Business lehetővé teszi az alkalmazások oldalbetöltését. Ez a beállítás azonban azzal a kockázattal jár, hogy a felhasználó olyan alkalmazásokat telepíthet, amelyek nem voltak a Microsoft Store. A rendszergazdák letilthatják a fejlesztői mód engedélyezését az **ApplicationManagement/AllowDeveloper Unlock** beállítás használatával a [Házirend CSP-ben.](/windows/client-management/mdm/policy-configuration-service-provider) [További információ a Fejlesztői módról.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Egy számítógépen csatlakozzon a HoloLens [Wi-Fi vagy](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) [USB használatával.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Tegye a következők egyikét:
   - Ha először csatlakozik a Windows Eszközportál, hozzon létre [egy felhasználónevet és egy jelszót](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Adja meg a korábban beállított felhasználónevet és jelszót.

    > [!TIP]
    > Ha tanúsítványhibát lát a böngészőben, kövesse [az alábbi hibaelhárítási lépéseket.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)

1. A Windows Eszközportál válassza a **Kioszkmód lehetőséget.**

1. Válassza **a Kioszkmód engedélyezése lehetőséget,** válassza ki az eszköz indításakor futtatni kívánt alkalmazást, majd válassza a **Mentés lehetőséget.**

    ![Kioszkmód](images/kiosk.png)
1. Indítsa újra HoloLens. Ha még meg van nyitva Eszközportál lap, válassza az **Újraindítás** lehetőséget az oldal tetején.

> [!NOTE]
> A kioszkmód az Eszközportál REST API-ján keresztül állítható be úgy, hogy a POST-ot /api/holographic/kioszkmode/settings értékre állítva egy kötelező lekérdezési sztringparaméterrel ("kioszkModeEnabled" "true" (igaz) vagy "false" (hamis) értékkel), valamint egy választható paraméterrel ("startupApp" egy csomagnév értékével). Vegye figyelembe, hogy a Eszközportál csak fejlesztőknek készült, és nem engedélyezhető nem fejlesztői eszközökön. A REST API a jövőbeli frissítésekben/kiadásokban változhatnak.

## <a name="more-information"></a>További információ

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Tekintse meg, hogyan konfigurálható kioszk egy kiépítési csomag használatával.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Globális hozzárendelt hozzáférés – Kioszkmód
- Csökkentett identitáskezelés a kioszkmódhoz, azáltal, hogy engedélyezi a kioszkmódot a rendszer szintjén alkalmazva az új kioszkmódot.

Ez az új funkció lehetővé teszi, hogy a rendszergazda egy HoloLens 2-es eszközt konfiguráljon több alkalmazás kioszkmódhoz, amely rendszerszinten alkalmazható, nem rendelkezik affinitással semmilyen identitással a rendszeren, és mindenkire érvényes, aki bejelentkezik az eszközre. Az új HoloLens további részletekért tekintse meg a globálisan hozzárendelt hozzáférési [kioszkok](hololens-global-assigned-access-kiosk.md) dokumentációját.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Alkalmazás automatikus indítása többalkalmazásos kioszkmódban 
- Összpontosított élmény az automatikus alkalmazásindítással, tovább növelve a Kioszk módhoz kiválasztott felhasználói felület és alkalmazásválasztások számának növelése.

Csak a többalkalmazásos kioszkmódra vonatkozik, és csak 1 alkalmazás jelölhető ki automatikus indításra a hozzárendelt hozzáférés konfigurációjának alábbi kiemelt attribútumával. 

Az alkalmazás automatikusan elindul, amikor a felhasználó bejelentkezik. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>A kioszkmód viselkedésének változásai a hibák kezelésével
Ha a kioszkmód alkalmazása során hibák lépnek fel, a következő viselkedés jelenik meg:

- A Holographic Windows 20H2 - HoloLens verzióban az összes alkalmazás 20H2 Start menü.
- Windows Holographic, 20H2-es verzió – ha egy eszköz kioszkkonfigurációval rendelkezik, amely a globális hozzáférés és az AAD-csoporttaghoz rendelt hozzáférés kombinációjából áll, az AAD-csoporttagság sikertelen meghatározása esetén a felhasználó "semmi sem jelenik meg a Start menüben" menüben.

![Kép a kioszkmódról, ha az sikertelen.](images/hololens-kiosk-failure-behavior.png )


- A [Holographic Windows 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziótól kezdve a Kioszkmód a globális hozzárendelt hozzáférést keres, mielőtt megjelenít egy üres Start menüt. A kioszkmód vissza fog állni egy globális kioszkkonfigurációra (ha van ilyen), ha az AAD-csoport kioszkmódjában hibák lépnek fel.

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Azure AD-csoporttagság gyorsítótárazése offline kioszkhoz

- Biztonságosabb kioszkmód az elérhető alkalmazások kioszkmódban való meghibásodásának kiküszöbölésével.
- Engedélyezett offline kioszkok Azure AD-csoportokkal való használatra akár 60 napig.

Ez a szabályzat szabályozza, hogy hány napig használható az Azure AD-csoporttagság gyorsítótára az Azure AD-csoportokat célzó hozzárendelt hozzáférés-konfigurációkhoz a bejelentkezett felhasználók számára. Ha ez a szabályzatérték csak 0-snál nagyobb értékre van állítva, akkor a rendszer másként nem használja a gyorsítótárat.  

Név: AADGroupMembershipCacheValidityInDays URI érték: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Perc – 0 nap  
Maximum – 60 nap 

A szabályzat megfelelő használatának lépései: 
1. Hozzon létre egy eszközkonfigurációs profilt az Azure AD-csoportokat megcélzó kioszkeszközhöz, és rendelje hozzá HoloLens eszközhöz. 
1. Hozzon létre egy egyéni OMA URI-alapú eszközkonfigurációt, amely a kívánt számú napra (> 0) állítja be ezt a szabályzatértéket, és rendelje hozzá HoloLens eszközhöz. 
    1. Az URI értéket az OMA-URI szövegmezőben a következőként kell megadni: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Az érték minimális/maximálisan megengedett lehet.
1. Regisztrálja HoloLens eszközöket, és ellenőrizze, hogy mindkét konfiguráció alkalmazva lesz-e az eszközre. 
1. Az Azure AD-felhasználó 1-es felhasználónak be kell jelentkeznie, ha elérhető az internet, és ha a felhasználó bejelentkezik, és az Azure AD-csoporttagság sikeres megerősítést nyer, létrejön a gyorsítótár. 
1. Az 1. Azure AD-felhasználó mostantól offline állapotba HoloLens, és kioszkmódhoz használhatja, ha a szabályzat értéke X számú napot tesz lehetővé. 
1. A 4. és az 5. lépés megismételhető bármely más Azure AD-felhasználó N felhasználója számára. Itt az a legfontosabb, hogy minden Azure AD-felhasználónak be kell jelentkeznie az eszközre az internet használatával, hogy legalább egyszer megállapítsuk, hogy tagja-e annak az Azure AD-csoportnak, amelyhez a kioszkkonfigurációt megcélozták. 
 
> [!NOTE]
> Amíg egy Azure AD-felhasználó esetében végre nem hajtotta a 4. lépést, a "leválasztott" környezetekben hiba lép fel. 


## <a name="xml-kiosk-code-samples-for-hololens"></a>XML kioszkkódminták HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Több alkalmazás kioszkmódja, amely egy Azure AD-csoportot céloz meg. 
Ez a kioszk üzembe helyez egy kioszkot, amely az Azure AD-csoport felhasználói számára engedélyezve lesz a kioszk módban, amely a következő 3 alkalmazást tartalmazza: Gépház, Remote Assist és Visszajelzési központ. A minta azonnali használatra való módosításához módosítsa az alább kiemelt GUID-azonosítót úgy, hogy megfeleljen egy saját Azure AD-csoportnak. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Több alkalmazás kioszkmódja, amely az Azure AD-fiókot célozza.
Ez a kioszk egyetlen felhasználó számára helyez üzembe egy kioszkot, amely a következő 3 alkalmazást tartalmazza: Gépház, Remote Assist és Visszajelzési központ. A minta azonnali használatra való módosításához módosítsa az alább kiemelt fiókot úgy, hogy megfeleljen egy saját Azure AD-fióknak. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

