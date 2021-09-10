---
title: Telepítési útmutató – Vállalati csatlakoztatott HoloLens 2 Dynamics 365-útmutatók – Konfigurálás
description: Megtudhatja, hogyan állíthat be olyan konfigurációkat, amelyek 2 HoloLens vállalati csatlakoztatott hálózaton keresztül telepítik a Dynamics 365-útmutatókat.
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
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428769"
---
# <a name="configure---corporate-connected-guide"></a>Konfigurálás – Vállalati csatlakoztatott útmutató

## <a name="azure-users-and-groups"></a>Azure-felhasználók és -csoportok

Az Azure és a bővítmény által használt Intune a felhasználók és csoportok segítségével segít a konfigurációk és licencek hozzárendelésében. Az üzembe helyezési folyamat ellenőrzéséhez és az útmutató szerzői és működtethetőségének ellenőrzéséhez&#39;felhasználói fiókra lesz szüksége.

Egyetlen felhasználói csoportot is létre lehet hozva kifejezetten a licencek hozzárendelése érdekében.

Ha még nem&#39;rendelkezik hozzáféréssel két Azure AD-fiókhoz egy felhasználói csoportban, ezt használhatja; A következő rövid útmutatókat íme a következő lépésekhez:

- [Felhasználó létrehozása](/mem/intune/fundamentals/quickstart-create-user)
- [Csoport létrehozása](/mem/intune/fundamentals/quickstart-create-group)
- [Felhasználók hozzáadása csoporthoz](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Létrehozott felhasználók hozzáadása csoport létrehozásához
- [Az Azure AD konfigurálása arra, hogy a](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) felhasználói csoportok eszközöket csatlakozzanak – Győződjön meg arról, hogy az új felhasználói csoport rendelkezik az eszközök Azure AD-beli regisztrálásához szükséges engedéllyel

## <a name="auto-enrollment-on-hololens-2"></a>Automatikus regisztráció a 2 HoloLens n

A zökkenőmentes és zökkenőmentes felhasználói élmény érdekében az Azure Active Directory Join (AADJ) és az Automatikus regisztráció beállítása az Intune-ban HoloLens 2 eszközre a megfelelő megoldás. Ez lehetővé teszi a felhasználók számára, hogy az OOBE során megnyissák a cég bejelentkezési hitelesítő adatait, és automatikusan regisztrálnak az Azure AD-ben, és regisztrálják az eszközt az MDM-ben.

A [(Microsoft Endpoint Manager)](https://endpoint.microsoft.com/#home)használatával kiválaszthatja a szolgáltatásokat, és navigálhat néhány oldalon, amíg ki nem Prémium a próbaverziót. Észreveheti, hogy a P1 prémium szintű Azure Active Directory 1 és 2 között van. Kiválaszthatja az Intune-t, kiválaszthatja az automatikus regisztráció felhasználói hatókörét, és kiválaszthatja a korábban létrehozott csoportot.

Részletes információkért és lépésekért olvassa el az Automatikus regisztráció engedélyezése az [Intune-hoz útmutatót.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>Vállalati Wi-Fi kapcsolat

A Wi-Fi kapcsolatok általában tanúsítványalapú hitelesítést igényelnek a 2. HoloLens ügyfelek számára. Ezeket a tanúsítványokat az MDM-megoldással integrált Egyszerű tanúsítványigénylési protokoll (SCEP) vagy nyilvános kulcsú titkosítási szabvány (PKCS) tanúsítványinfra infrastruktúrájának használatával kell telepítenie. Ha az Intune-Wi-Fi, tanúsítványokat és proxybeállításokat telepít, zökkenőmentes felhasználói élményt biztosít a végfelhasználók számára.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Tanúsítványok és tanúsítványprofilok Wi-Fi üzembe

Ha tanúsítványokat és profilokat telepít a Microsoft Endpoint Manager, kövesse az alábbi lépéseket:

1. Hozzon létre egy profilt az egyes fő- és köztes tanúsítványokhoz (lásd: [Megbízható tanúsítványprofilok létrehozása).](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Mindegyik profilnak olyan leírással kell lennie, amely tartalmaz egy lejárati dátumot DD/HH/YYYY formátumban.

    > [!CAUTION]
    > **A lejárati dátum nélküli tanúsítványprofilok nem lesznek telepítve.**

2. Hozzon létre egy profilt minden SCEP- vagy PKCS-tanúsítványhoz (lásd: SCEP-tanúsítványprofil létrehozása vagy [PKCS-tanúsítványprofil létrehozása).](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Mindegyik profilnak olyan leírással kell rendelkezik, amely tartalmaz egy lejárati dátumot DD/HH/YYYY formátumban.

    > [!CAUTION]
    > **A lejárati dátum nélküli tanúsítványprofilok nem lesznek telepítve.**

    > [!Note]
    > Mivel a HoloLens 2-t sokan megosztott eszköznek tekintik, vagyis eszközönként több felhasználónak is, ajánlott felhasználói tanúsítványok helyett eszköztanúsítványokat telepíteni Wi-Fi hitelesítéshez, ahol lehetséges.

3. Hozzon létre egy profilt a vállalati hálózati Wi-Fi (lásd: [Wi-Fi-beállítások az Windows 10 és újabb eszközökhöz).](/intune/wi-fi-settings-windows) A Wi-Fi profilban használhatja a proxybeállításokat a szervezeten belül.

    A választható lehetőségek:
    - **Nincs**: Semmilyen proxybeállítás nincs konfigurálva.
    - **Manuális konfigurálás:** Adja meg a **proxykiszolgáló IP-címét** és **portszámát.**
    - **Automatikus konfigurálás:** Adja meg az automatikus proxykonfigurációs (PAC) parancsfájlra mutató URL-címet. Írja be például a következőt: *http://proxy.contoso.com/proxy.pac* .

    A PAC-fájlokkal kapcsolatos további információkért lásd: [Proxy Auto-Configuration (PAC) fájl](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (egy nem Microsoft-webhely megnyitása).
 
    > [!Note]
    > Ha lehetséges, ajánlott a Wi-Fi a felhasználói csoportok helyett az Eszközcsoportokhoz rendelni a profilt.
     
    > [!Tip]
    > Munkaprofilt a vállalati hálózaton Wi-Fi számítógépéről Windows 10 exportálhat. Ez az exportálás létrehoz egy XML-fájlt az összes aktuális beállítással. Ezután importálja ezt a fájlt az Intune-ba, és használja Wi-Fi 2 eszköz HoloLens profiljaként. Lásd: [Wi-Fi-beállítások exportálása és importálása Windows rendszerű eszközökhöz](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Rendelje](/mem/intune/configuration/device-profile-assign) hozzá az eszközprofilokat HoloLens eszközcsoporthoz.

2.  [Az Eszközprofilok](/mem/intune/configuration/device-profile-monitor) figyelése az Intune-ban.

Ha a profilokkal kapcsolatos problémák Wi-Fi, akkor az Eszközkonfigurációs profilok hibaelhárítása [az IntuneWi-Fi ban témakörben található.](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Külső internet-hozzáférés hibaelhárítása vállalati kapcsolattal
Ha a szolgáltatások megpróbálnak nem egy beállított proxyn keresztülmenni, előfordulhat, hogy a tűzfalon keresztül próbálnak csatlakozni. A hibák elhárításához hozzáadhatja a tűzfalszabályok végpontspecifikus listáját.

Ha a tűzfalportok blokkolják, engedélyezzen néhány gyakori [végpontot](/hololens/hololens-offline) a HoloLens.

Az útmutatók adott portjai is engedélyezhetők: a következő portokhoz való csatlakozáshoz szükséges internetről [elérhető URL-címek Microsoft Dynamics CRM Online.](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)

## <a name="app-deployment"></a>Alkalmazástelepítés

Az LOB-alkalmazások MDM-en keresztüli üzembe helyezése egy könnyen skálázható módszer, amely automatikusan üzembe helyezhető az eszközökre egy létrehozott csoportban való regisztrációkor.

Ha még fejleszti az alkalmazásait, vagy még nincs ilyen alkalmazása, használhatja az MRTK-példák központjának egy mintaalkalmazását. Ez a mintaalkalmazás használatra kész, és nem igényel Unityt vagy Visual Studio. [Töltse le az MRTK-példák mintaalkalmazást.](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)

Ha inkább saját alkalmazást szeretne használni, vagy szeretne alkalmazásfejlesztést Mixed Reality, tekintse át a Mixed Reality [dokumentációját.](/windows/mixed-reality/design/design)

> [!NOTE]
> A HoloLens rendszerkövetelményei az alkalmazás build architektúrája alapján vannak megszabadulva. HoloLens 2 eszköz ARM-architektúrát használ. Amikor alkalmazásokat hoz Visual Studio, győződjön meg arról, hogy az eszköznek megfelelő architektúrát választotta ki, és tartalmazza a szükséges függőségeket.

> [!IMPORTANT]
> Az LOB-alkalmazások telepítésekor fontos, hogy a tanúsítványt az Intune-ba is feltöltsük, és hozzárendeljük ugyan ahhoz a csoporthoz, amely az alkalmazást használni fogja, különben nem fog megfelelően telepíteni.

### <a name="upload-and-assign-the-app"></a>Az alkalmazás feltöltése és hozzárendelése

1. Lépjen a [MEM felügyeleti központba.](https://endpoint.microsoft.com/#home)

2. Válassza **az Alkalmazások**  ->  **Minden alkalmazás,** majd a **+ Hozzáadás gombot.**

3. Az Egyéb alatt válassza **az Üzletági alkalmazás lehetőséget.** Kattintson a **kijelölésre.**

4. Válassza ki az alkalmazáscsomag-fájlt. Ez az Ön APPXBUNDLE-fájlja, vagy ebben a példában az alkalmazás _az MRTK Examples Hub \_ 2.4.2.0 \_ arm \_ Master.appxbundle_.

5. Értesítést kap a hiányzó függőségekről. Ebben az esetben fel kell töltenünk a _Microsoft.VCLibs.ARM.14.00.appx fájlt._ Keresse meg a Fájl **kiválasztása alatt.**

6. Kattintson az OK gombra.

7. A következő képernyőn a kötelező mezők automatikusan ki lesznek töltve. Kattintson a **Tovább** gombra.

8. A Kötelező alatt adja hozzá a korábban létrehozott csoportot, hogy az alkalmazás szükséges legyen a csoporthoz. Ennek hatására az alkalmazás automatikusan letölti az alkalmazást a csoportba regisztrált eszközökre. Kattintson a **Tovább** gombra.

9. Válassza a **Létrehozás** lehetőséget.

További információ: [Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Telepítési útmutatók: Alkalmazáslicencek, adatverzum és szerzői

A Dynamics 365-útmutatók használatának érdekében előkészületeket kell megtennie. Három területet kell előkészítenünk: felhasználók, az adatverzum és maguk az útmutatók.

### <a name="users-and-application-licenses"></a>Felhasználók és alkalmazáslicencek

Ahhoz, hogy valaki útmutatókat használjon, Azure AD-fiókot kell használnia, amelyet korábban ebben az útmutatóban hoztunk létre.

Emellett Dynamics 365-útmutatók licencet kell hozzárendelni a létrehozott felhasználóhoz. Ezt a következőből [Microsoft 365 Felügyeleti központ.](https://admin.microsoft.com/AdminPortal/Home) Rendelje hozzá a licencet az elsődleges Azure-fiókjához is.

Az [alkalmazáslicencek alkalmazására](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) vonatkozó részletes útmutatásért kövesse ezt a képekkel rendelkező rövid útmutatót.

### <a name="set-up-the-dataverse"></a>Az adatverem beállítása

Éles környezet [beállítását](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) két előfeltételnek kell teljesítenie. Rendszergazdai [**szerepkörrel**](/power-platform/admin/database-security) kell **lennie,** és [**Power Apps-licenccel (vagy**](/power-platform/admin/signup-question-and-answer) dynamics [**365-útmutatókhoz**](/dynamics365/mixed-reality/guides/setup-step-one) szükséges licenccel, amely tartalmaz egy Power Apps licencet). Ha ebben az útmutatóban az Azure AD-t hozta létre, akkor megfelel a rendszergazda szerepkör-követelményeinek. Az előző lépésben egy Útmutatók licencet is hozzárendeltünk.

Ebben az útmutatóban [microsoftos adatverzum-környezetet hozhat létre:](/dynamics365/mixed-reality/guides/setup-step-two)

1. Először használja a Power Platform felügyeleti központja [és](https://admin.powerplatform.microsoft.com/environments) hozzon létre egy új környezetet.
2. Az Új környezet létrehozásakor  **a** Típus mezőbe írja be a&#39;éles környezet lesz **kiválasztva.**
3. Fontos a Create a **database for this environment (Adatbázis létrehozása ehhez a környezethez) kapcsolóval?**  kapcsolót **igenre.**
4. Az Adatbázis  **hozzáadása párbeszédpanelen**  állítsa a  **Dynamics 365-alkalmazások**  engedélyezése beállítást Igen  **lehetőségre.**

Az adatverem elemeinek maximális fájlméretét is növelni kell. A maximális fájlméret növelésével nagyobb 3D-s modelleket vagy videofájlokat tölthet fel, amelyekre később az útmutatókban is lesz majd példa. A feltöltési fájl maximális méretének módosításhoz kövesse a következő rövid [útmutatót:](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size).

Végül telepítenie és konfigurálnia kell a [megoldást.](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution) A [Power Platform felügyeleti központja](https://admin.powerplatform.microsoft.com/environments)válassza az **Erőforrások** \& gt; lehetőséget.  **Dynamics 365-alkalmazások,** válassza ki a **Dynamics 365-útmutatók listában,** majd válassza a **Telepítés lehetőséget.**  

Az alkalmazások használata előtt [hozzá](/dynamics365/mixed-reality/guides/assign-role) kell adni egy Útmutatók biztonsági szerepkört.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Tesztelési útmutató létrehozása a számítógépen szerzői útmutatóval

Az útmutatók létrehozásakor mindig a számítógépen fog elindulni. A lépések létrehozása, a modellek kiválasztása és az útmutató rögzítésének útmutatója. Ezt az útmutató tartalmának későbbi, szerzői módban való elhelyezése követi majd a HoloLens eszközén. Ebben az útmutatóban egy rövid, minimális lépéseket és modelleket is tartalmazó tesztelési útmutatót javasolunk.

Ha az útmutatók írásával szeretne kezdeni, kezdje itt a [szerzői áttekintéssel.](/dynamics365/mixed-reality/guides/authoring-overview) Vagy a gyors nyomon követhetőségért tekintse meg ezt a rövid videót.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Nem kötelező: Kioszk mód

A kioszkmód egy olyan mód, amely lehetővé vált, hogy a rendszergazda úgy konfigurálja a Start menü felhasználói felületét, hogy csak egyetlen alkalmazást vagy alkalmazásokat mutasson. A kioszkok adott felhasználókra, csoportokra vagy eszközszinten is alkalmazhatók; és bizonyos esetekben kizárhat bizonyos felhasználókat a kioszkból, így továbbra is hozzáférhetnek a normál Start menühöz.

A kioszkmód számos különböző változóval rendelkezik mind a hatókörben, mind a konfigurációkban, amelyek beállíthatók, valamint a kioszk üzembe helyezésének HoloLens. A fenti változók miatt a kioszkmód nem kötelezőként lesz meghagyva _ehhez_ az útmutatóhoz, és a rendszer nem használja újra. Ha úgy véli, hogy üzleti cél a rendelkezésre álló alkalmazások felhasználókra való korlátozása, vagy szeretne többet megtudni, nyugodtan megtudhatja, hogyan állíthatja be a HoloLens [kioszkként.](/hololens/hololens-kiosk)

## <a name="optional-wdac"></a>Nem kötelező: WDAC

A WDAC lehetővé teszi, hogy a rendszergazda úgy konfigurálja az eszközeit, hogy letiltsa az alkalmazások elindítását az eszközökön. Ez eltér az eszközkorlátozási módszerektől, például a Kioszk módtól, ahol a felhasználó számára egy olyan felhasználói felület van meg, amely elrejti az eszközön található alkalmazásokat, de továbbra is elindítható. Bár a WDAC van megvalósítva, az alkalmazások továbbra is láthatók a Minden alkalmazás listában, de a WDAC megakadályozza, hogy ezeket az alkalmazásokat és folyamatokat az eszköz felhasználója elindítsa.

További információ: [Use WDAC and Windows PowerShell to allow](/mem/intune/configuration/custom-profile-hololens)or block apps on HoloLens 2 devices with Microsoft Intune .

[Windows Defender Alkalmazásvezérlés – WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Következő lépés 
> [!div class="nextstepaction"]
> [Vállalati csatlakoztatott üzembe helyezés – Üzembe helyezés](hololens2-corp-connected-deploy.md)