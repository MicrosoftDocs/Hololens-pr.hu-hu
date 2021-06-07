---
title: Telepítési útmutató – Céghez csatlakoztatott HoloLens 2 Dynamics 365-útmutatókkal – Konfigurálás
description: Útmutató a HoloLens 2-eszközök vállalati csatlakoztatott hálózaton keresztüli üzembe helyezéséhez szükséges konfigurációk beállításához a Dynamics 365-útmutatók segítségével.
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
ms.openlocfilehash: 939efc28a0c3255cc9a38af3cd8dd9aa8fc2ac98
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378008"
---
# <a name="configure---corporate-connected-guide"></a>Konfigurálás – Vállalati csatlakoztatott útmutató

## <a name="azure-users-and-groups"></a>Azure-felhasználók és -csoportok

Az Azure és a bővítmény által az Intune felhasználók és csoportok használatával segít a konfigurációk és licencek hozzárendelésében. Az üzembe helyezési folyamat ellenőrzése és az útmutató létrehozása és működtetés ellenőrzése érdekében&#39;felhasználói fiókra lesz szüksége.

Egyetlen felhasználói csoportot is létre lehet hozva kifejezetten a licencek hozzárendelése érdekében.

Ha még nem&#39;rendelkezik hozzáféréssel két Azure AD-fiókhoz egy felhasználói csoportban, használhatja; A következő rövid útmutatókat íme:

- [Felhasználó létrehozása](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Csoport létrehozása](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Felhasználók hozzáadása csoporthoz](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Létrehozott felhasználók hozzáadása csoport létrehozásához
- [Az Azure AD konfigurálása](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) az eszközök felhasználói csoportokhoz való csatlakozásának engedélyezése érdekében – Győződjön meg arról, hogy az új felhasználói csoport rendelkezik az eszközök Azure AD-beli regisztrálásához szükséges engedéllyel

## <a name="auto-enrollment-on-hololens-2"></a>Automatikus regisztráció a HoloLens 2-ben

A zökkenőmentes és zökkenőmentes élmény érdekében az Azure Active Directory Join (AADJ) és az Automatikus regisztráció beállítása az Intune-ban a HoloLens 2-eszközökhöz a megoldás. Ez lehetővé teszi, hogy a felhasználók a szervezeti bejelentkezési hitelesítő adatokat az OOBE során adja meg, és automatikusan regisztrálnak az Azure AD-ben, és regisztrálják az eszközt az MDM-ben.

A [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)a szolgáltatásokat, és navigálhat néhány oldalon, amíg ki nem választjuk a Prémium szintű próbaverziót. Észreveheti, hogy a P1 prémium szintű Azure Active Directory 1 és 2 között van. Kiválaszthatja az Intune lehetőséget, kiválaszthatja az automatikus regisztráció felhasználói hatókörét, és kiválaszthatja a korábban létrehozott csoportot.

Részletes információkért és lépésekért olvassa el az Automatikus regisztráció engedélyezése az [Intune-ban útmutatót.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>Vállalati Wi-Fi kapcsolat

A Wi-Fi kapcsolatok általában tanúsítványalapú hitelesítést igényelnek a HoloLens 2-t használó ügyfelek számára. Ezeket a tanúsítványokat az MDM-megoldással integrált Egyszerű tanúsítványigénylési protokoll (SCEP) vagy nyilvános kulcsú titkosítási szabvány (PKCS) tanúsítványinfra infrastruktúrájának használatával kell telepítenie. Ha az Intune-Wi-Fi, tanúsítványokat és proxybeállításokat telepít, zökkenőmentes felhasználói élményt biztosít a végfelhasználók számára.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Tanúsítványok és tanúsítványprofilok Wi-Fi központi telepítése

A tanúsítványok és profilok Microsoft Endpoint Manager keresztüli telepítéséhez kövesse az alábbi lépéseket:

1. Hozzon létre egy profilt az egyes fő- és köztes tanúsítványokhoz (lásd: [Megbízható tanúsítványprofilok létrehozása).](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) Ezen profilok mindegyikének olyan leírással kell lennie, amely tartalmaz egy lejárati dátumot DD/HH/YYYY formátumban. 

    > [!CAUTION]
    > **A lejárati dátum nélküli tanúsítványprofilok nem lesznek telepítve.**

2.  Hozzon létre egy profilt minden SCEP- vagy PKCS-tanúsítványhoz (lásd: SCEP-tanúsítványprofil létrehozása vagy [PKCS-tanúsítványprofil létrehozása).](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Mindegyik profilnak olyan leírással kell rendelkezik, amely tartalmaz egy lejárati dátumot DD/HH/YYYY formátumban. 

    > [!CAUTION]
    > **A lejárati dátum nélküli tanúsítványprofilok nem lesznek telepítve.**

    > [!Note]
    > Mivel a HoloLens 2-t sokan megosztott eszköznek tekintik, vagyis eszközönként több felhasználó is, ajánlott felhasználói tanúsítványok helyett eszköztanúsítványokat telepíteni Wi-Fi hitelesítéshez, ahol lehetséges.

3.  Hozzon létre egy profilt a vállalati hálózati Wi-Fi számára (lásd: [Wi-Fi-beállítások Windows 10 és újabb eszközökhöz).](https://docs.microsoft.com/intune/wi-fi-settings-windows) A saját Wi-Fi választhatja a szervezet proxybeállításának használatát.
 
    A választható lehetőségek:
    - **Nincs**: Semmilyen proxybeállítás nincs konfigurálva.
    - **Manuális konfigurálás:** Adja meg a **proxykiszolgáló IP-címét** és **portszámát.**
    - **Automatikus konfigurálás:** Adja meg az automatikus proxykonfigurációs (PAC) parancsfájlra mutató URL-címet. Írja be például a következőt: *http://proxy.contoso.com/proxy.pac* .

    A PAC-fájlokkal kapcsolatos további információkért lásd: [Proxy auto-Configuration (PAC) fájl](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (nem Microsoft-webhely megnyitása).
 
    > [!Note]
    > Javasoljuk, hogy Wi-Fi felhasználói csoportok helyett eszközcsoportokhoz rendeli hozzá a profilt.
     
    > [!Tip]
    > Munkaprofilt a vállalati hálózaton Wi-Fi számítógépéről Windows 10 exportálhat. Ez az exportálás létrehoz egy XML-fájlt az összes aktuális beállítással. Ezután importálja ezt a fájlt az Intune-ba, és használja Wi-Fi HoloLens 2-eszközeihez. Lásd: [Wi-Fi-beállítások exportálása és importálása Windows rendszerű eszközökhöz](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Rendelje](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) hozzá az eszközprofilokat a HoloLens-eszközcsoporthoz.

2.  [Az Eszközprofilok](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) figyelése az Intune-ban.

Ha probléma ad Wi-Fi profilokkal, akkor az Eszközkonfigurációs profilok [hibaelhárítása az IntuneWi-Fi ban témakörben található.](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Külső internet-hozzáférés hibaelhárítása vállalati kapcsolattal
Ha a szolgáltatások megpróbálnak nem egy beállított proxyn keresztülmenni, előfordulhat, hogy a tűzfalon keresztül próbálnak csatlakozni. A hibák elhárításához hozzáadhatja a tűzfalszabályok végpontspecifikus listáját.

Ha a tűzfalportok blokkolják, [](https://docs.microsoft.com/hololens/hololens-offline) engedélyezzen néhány gyakori végpontot a HoloLenshez.

Az Útmutatók adott portjai is engedélyezhetők: Internetről elérhető URL-címek, amelyek a csatlakozáshoz szükségesek [a Microsoft Dynamics CRM Online.](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)

## <a name="app-deployment"></a>Alkalmazástelepítés

Az LOB-alkalmazások MDM-en keresztüli üzembe helyezése egy könnyen skálázható módszer, amely automatikusan üzembe helyezhető az eszközökre a létrehozott csoportban való regisztráció után.

Ha még fejleszti az alkalmazásait, vagy még nincs ilyen alkalmazása, használhatja az MRTK-példák központjának egy mintaalkalmazását. Ez a mintaalkalmazás használatra kész, és nem igényel Unityt vagy Visual Studio. [Töltse le az MRTK-példák mintaalkalmazást.](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)

Ha inkább saját alkalmazást szeretne használni, vagy ha az alkalmazásfejlesztés iránt érdeklődik Mixed Reality, tekintse át a Mixed Reality [dokumentációját.](https://docs.microsoft.com/windows/mixed-reality/design/design)

> [!NOTE]
> A HoloLens-eszközök rendszerkövetelményei az alkalmazás build architektúráján alapulnak. A HoloLens 2-eszközök ARM-architektúrát használnak. Amikor alkalmazásokat hoz Visual Studio, győződjön meg arról, hogy az eszköznek megfelelő architektúrát választotta ki, és tartalmazza a szükséges függőségeket.

> [!IMPORTANT]
> LOB-alkalmazások telepítésekor fontos, hogy a tanúsítványt is feltöltsük az Intune-ba, és hozzárendeljük ugyan ahhoz a csoporthoz, amely az alkalmazást használni fogja, különben nem fog megfelelően telepíteni.

### <a name="upload-and-assign-the-app"></a>Az alkalmazás feltöltése és hozzárendelése

1. Lépjen a [MEM felügyeleti központba.](https://endpoint.microsoft.com/#home)

2. Válassza **az Alkalmazások**  ->  **Minden alkalmazás,** majd a **+ Hozzáadás gombot.**

3. Az Egyéb alatt válassza **az Üzletági alkalmazás lehetőséget.** Kattintson a **kijelölésre.**

4. Válassza ki az alkalmazáscsomag-fájlt. Ez az APPXBUNDLE-fájl, vagy a példánkban az alkalmazás _az MRTK Examples Hub \_ 2.4.2.0 \_ arm \_ Master.appxbundle_.

5. A hiányzó függőségekről értesítést kap. Ebben az esetben fel kell töltenünk a _Microsoft.VCLibs.ARM.14.00.appx fájlt._ Keresse meg a Fájl **kiválasztása alatt.**

6. Kattintson az OK gombra.

7. A következő képernyőn a kötelező mezők automatikusan ki lesznek töltve. Kattintson a **Tovább** gombra.

8. A Kötelező alatt adja hozzá a korábban létrehozott csoportot, hogy ez az alkalmazás kötelező legyen a csoporthoz. Ennek hatására az alkalmazás automatikusan letölti az alkalmazást a csoportba regisztrált eszközökre. Kattintson a **Tovább** gombra.

9. Válassza a **Létrehozás** lehetőséget.

További információ: [Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Telepítési útmutatók: Alkalmazáslicencek, adatverzum és szerzői

A Dynamics 365-útmutatók használata előtt el kell készülni a használatra. Három területet kell előkészítenünk: felhasználók, az adatverem és maguk az útmutatók.

### <a name="users-and-application-licenses"></a>Felhasználók és alkalmazáslicencek

Ahhoz, hogy valaki útmutatókat használ, Azure AD-fiókot kell használnia, amelyet korábban már beállítottunk ebben az útmutatóban.

Emellett Dynamics 365-útmutatók licencet kell hozzárendelni a létrehozott felhasználóhoz. Ezt a következőből fogja [Microsoft 365 Felügyeleti központ.](https://admin.microsoft.com/AdminPortal/Home) Rendelje hozzá a licencet az elsődleges Azure-fiókjához is.

Az [alkalmazáslicencek alkalmazására](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) vonatkozó részletes útmutatásért kövesse ezt a képekkel rendelkező rövid útmutatót.

### <a name="set-up-the-dataverse"></a>Az adatverzum beállítása

Éles környezet [beállítását](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) két előfeltételnek kell teljesítenie. Rendszergazdai [**szerepkörrel**](https://docs.microsoft.com/power-platform/admin/database-security) kell  **lennie,**  és Power Apps-licenccel [**(vagy**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) olyan [**Dynamics 365-útmutatók**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) licenccel, amely Power Apps tartalmaz). Ha az útmutató alapján hozta létre az Azure AD-t, akkor megfelel a rendszergazda szerepkör-követelményeinek. Az előző lépésben egy Útmutatók licencet is hozzárendeltünk.

Ebben az útmutatóban [egy Microsoft Dataverse-környezetet hozhat létre:](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)

1. Először is használja a [Power Platform felügyeleti központja](https://admin.powerplatform.microsoft.com/environments) és hozzon létre egy új környezetet.
2. Az Új **környezet létrehozásakor a** Típus mezőbe írja be a&#39;éles környezet lesz **kiválasztva.** 
3. Fontos a Create a database for this environment (Adatbázis **létrehozása ehhez a környezethez) kapcsoló ki- és bekapcsolni?**  kapcsolót **Igen.**
4. Az Adatbázis  **hozzáadása párbeszédpanelen**  állítsa a  **Dynamics 365-alkalmazások**  engedélyezése beállítást  **Igenre.**

Az adatverem elemeinek maximális fájlméretét szeretné növelni. A maximális fájlméret növelésével nagyobb 3D-s modelleket vagy videofájlokat tölthet fel, amelyekre később az útmutatókban lesz majd majd használni. Kövesse egy rövid útmutatót a [fájl maximális méretének a módosításhoz.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Végül telepítenie és konfigurálnia kell [a megoldást.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution) A [Power Platform felügyeleti központja](https://admin.powerplatform.microsoft.com/environments)válassza az **Erőforrások** \& gt; lehetőséget.  **Dynamics 365-alkalmazások :** válassza a **Dynamics 365-útmutatók** lehetőséget a listában, majd válassza a **Telepítés lehetőséget.**  

Az alkalmazások használata előtt [hozzá](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) kell adni egy Útmutatók biztonsági szerepkört.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Tesztelési útmutató létrehozása a számítógépen a Szerzői írással

Az útmutatók létrehozásakor mindig a számítógépen fog elindulni. A lépések létrehozása, a modellek kiválasztása és az útmutató rögzítésének útmutatója. Ezt követően az útmutató tartalmát később szerzői módban helyezi el a HoloLens-eszközön. Ebben az útmutatóban egy rövid, minimális lépéseket és modelleket is tartalmazó tesztelési útmutatót javasolunk.

Ha az útmutatók szerzőiről szeretne tanulni, kezdje itt a [szerzői áttekintéssel.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview) Vagy a gyors nyomon követhetőségért tekintse meg ezt a rövid videót.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Nem kötelező: Kioszkmód

A kioszkmód egy olyan mód, amely lehetővé vált, hogy a rendszergazdák úgy konfigurálják a Start menü felhasználói felületét, hogy csak egyetlen alkalmazást vagy alkalmazásokat mutassanak. A kioszkok adott felhasználókra, csoportokra vagy eszközszinten is alkalmazhatók; és bizonyos esetekben kizárhat bizonyos felhasználókat a kioszkból, így továbbra is hozzáférhetnek a normál Start menühöz.

A kioszkmód számos különböző változóval rendelkezik, mind a hatókörben, mind a konfigurációkban, amelyek beállíthatók, valamint a Kioszk a HoloLensben való üzembe helyezésének módszerei. Ezen változók miatt a kioszkmód nem  kötelezőként lesz meghagyva ehhez az útmutatóhoz, és a rendszer nem használja újra. Ha úgy véli, hogy üzleti célokat kell kioszkként beállítania a HoloLenst a felhasználóknak, vagy többet szeretne megtudni arról, hogyan állíthatja be [a HoloLenst.](https://docs.microsoft.com/hololens/hololens-kiosk)

## <a name="optional-wdac"></a>Nem kötelező: WDAC

A WDAC lehetővé teszi, hogy a rendszergazda úgy konfigurálja az eszközeit, hogy letiltsa az alkalmazások elindítását az eszközökön. Ez eltér az eszközkorlátozási módszerektől, például a Kioszk módtól, ahol a felhasználó egy olyan felhasználói felületet kap, amely elrejti az eszközön található alkalmazásokat, de továbbra is elindítható. Bár a WDAC van megvalósítva, az alkalmazások továbbra is láthatók a Minden alkalmazás listában, de megakadályozza, hogy az eszköz felhasználója elindítsa ezeket az alkalmazásokat és folyamatokat.

További információ: [Use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)

[Windows Defender alkalmazásvezérlés – WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Következő lépés 
> [!div class="nextstepaction"]
> [Vállalati csatlakoztatott üzembe helyezés – Üzembe helyezés](hololens2-corp-connected-deploy.md)