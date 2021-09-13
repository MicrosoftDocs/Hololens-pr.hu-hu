---
title: Az HoloLens konfigurálása kiépítési csomaggal (HoloLens)
description: Windows segítségével a rendszergazdák rendszerkép nélkül konfigurálhatják a végfelhasználói eszközöket.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9474774b47858003cc11363a5f325f589b0732ab
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032907"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>Az HoloLens konfigurálása kiépítési csomag használatával

[Windows segítségével a](/windows/configuration/provisioning-packages/provisioning-packages) rendszergazdák rendszerkép nélkül konfigurálhatják a végfelhasználói eszközöket. Windows A Configuration Designer olyan rendszerképek és futásidejű beállítások konfigurálásához használható eszköz, amelyek aztán beépítetten kiépítési csomagokba vannak beépítve.

A kiépítési HoloLens többek között a következő konfigurációs beállításokat alkalmazhatja:

- Frissítés [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- Helyi fiók beállítása
- Kapcsolat Wi-Fi beállítása
- Tanúsítványok alkalmazása az eszközre
- Fejlesztői mód engedélyezése
- Konfigurálja a kioszkmódot a részletes [utasítások szerint.](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)

## <a name="provisioning-package-hololens-wizard"></a>Kiépítési csomag HoloLens varázsló

A HoloLens varázsló segítségével a következő beállításokat konfigurálhatja egy kiépítési csomagban:

- Frissítés az Enterprise kiadásra

    > [!NOTE]
    > Ez csak az 1. HoloLens eszközökhöz használható. Gépház kiépítési csomagban található licencek csak akkor lesznek alkalmazva, ha a kiépítési csomag kiadásfrissítési licencet tartalmaz az Windows Holographic for Business-hoz, vagy ha az eszköz már frissítve lett a [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

- Az első HoloLens konfigurálása (OOBE)
- A hálózati Wi-Fi konfigurálása
- Az eszköz regisztrálása Azure Active Directory vagy helyi fiók létrehozása
- Tanúsítványok hozzáadása
- Fejlesztői mód engedélyezése
- Konfigurálja a kioszkmódot a részletes [utasítások szerint.](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)

> [!WARNING]
> A konfigurációtervezőt Windows kell futtatnia a Windows 10, hogy Azure Active Directory bármelyik varázslóval konfigurálja a regisztrációt.

A kiépítési csomagok többek között felügyeleti utasításokat és szabályzatokat, egyéni hálózati kapcsolatokat és szabályzatokat tartalmazhatnak.

> [!TIP]
> Az asztali varázslóval hozzon létre egy csomagot a közös beállításokkal, majd váltson át a speciális szerkesztőre más beállítások, alkalmazások, szabályzatok stb. hozzáadásához.

## <a name="steps-for-creating-provisioning-packages"></a>Kiépítési csomagok létrehozásának lépései

1. **1. lehetőség:** [A Microsoft Store.](https://www.microsoft.com/store/apps/9nblggh4tx22) Ez 2 HoloLens képességre is vonatkozik.
2. **2. lehetőség:** A Windows [Assessment and Deployment Kit (ADK) for Windows 10.](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit) Ha az Windows ADK-ból telepíti az Windows Configuration **Designert,** válassza a Konfigurációtervező lehetőséget a Válassza ki a telepíteni kívánt **szolgáltatásokat párbeszédpanelen.** Ez a lehetőség nem tartalmazza HoloLens 2 képességet.

> [!NOTE]
> Ha tudja, hogy offline számítógépet fog használni, és hozzá kell férni az Windows Configuration Designerhez, kövesse az Advanced Recovery Companion [offline app install(hololens-recovery.md#downloading-arc-without-using-the-app-store) útmutatóját. A Windows a Configuration Designerben. 

### <a name="2-create-the-provisioning-package"></a>2. A kiépítési csomag létrehozása

A Windows Configuration Designer eszközzel hozzon létre egy kiépítési csomagot.

1. Nyissa meg Windows Configuration Designert (alapértelmezés szerint: %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. Válassza **a Kiépítés HoloLens lehetőséget.**

   ![Az ICD indítási beállításai.](images/icd-create-options-1703.png)

3. Nevezze el a projektet, és válassza a **Befejezés lehetőséget.**

4. Olvassa el az Első lépések **oldalon található utasításokat,** és válassza a Tovább **lehetőséget.** Az asztali kiépítés oldalai a következő lépéseken végigmennek.
  
> [!IMPORTANT]
> Kiépítési csomag létrehozása során bizalmas adatokat is tartalmazhat a projektfájlokban és a kiépítési csomag (.ppkg) fájljában. Bár lehetősége van a .ppkg fájl titkosítására, a projektfájlok nincsenek titkosítva. A projektfájlokat biztonságos helyen tárolja, és törölje a projektfájlokat, amikor már nincs rájuk szükség.

### <a name="configure-settings"></a>Beállítások konfigurálása

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Keresse meg és válassza ki a vállalati licencfájlt a HoloLens frissítéshez.</br></br>Az Igen vagy a <strong>Nem</strong> kapcsolóval <strong>elrejtheti</strong> az első élmény részeit.</br></br>Ha anélkül szeretne beállítani egy eszközt, hogy csatlakoznia kellene egy <strong></strong> Wi-Fi-hálózathoz, állítsa a Beállítás kihagyása Wi-Fi beállítást Be <strong>beállításra.</strong></br></br>Válassza ki azt a régiót és időzónát, amelyben az eszközt használni fogja. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>Ebben a szakaszban megadhatja annak a vezeték nélküli hálózatnak Wi-Fi adatait, amelyekhez az eszköznek automatikusan csatlakoznia kell. Ehhez válassza a <strong>Be</strong>lehetőséget, adja meg az SSID-t, a hálózat típusát<strong>(Open</strong> vagy <strong>WPA2-Personal</strong>), és (HA <strong>WPA2-Personal</strong>) a vezeték nélküli hálózat jelszavát.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Regisztrálhatja az eszközt a Azure Active Directory, vagy létrehozhat egy helyi fiókot az eszközön</br></br>Mielőtt egy Windows Configuration Designer varázslóval konfigurálja az Azure AD-regisztrációt, állítsa be az <a href="/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](/azure/active-directory/active-directory-azureadjoin-setup)">Azure AD-csatlakozást a szervezetben.</a> Az <strong>Azure</strong> AD-bérlőben a felhasználónkénti eszközök maximális száma határozza meg, hogy a varázslóban lekért tömeges jogkivonat hányszor használható. Ha regisztrálnia kell az eszközt az Azure AD-ban, válassza ki ezt a lehetőséget, és adjon meg egy rövid nevet a varázslóval lekért tömeges jogkivonathoz. Állítson be lejárati dátumot a jogkivonathoz (a jogkivonat lekért dátumtól számított legfeljebb 30 nap). Válassza <strong>a Get bulk token (Csoportos jogkivonat beszerzése) lehetőséget.</strong> A <strong>Let&#39;get you signed in (Be</strong> kell szereznie a bejelentkezett eszközt) ablakban adjon meg egy olyan fiókot, amely engedéllyel rendelkezik az eszköz Azure AD-hez való csatlakozásához, majd adja meg a jelszót. Válassza <strong>az Elfogadás lehetőséget,</strong> Windows a Configuration Designernek a szükséges engedélyeket. </br></br>Helyi fiók létrehozásához válassza ki ezt a lehetőséget, és adjon meg egy felhasználónevet és egy jelszót. </br></br><strong>Fontos:</strong> <br />(Csak Windows 10 1607-es verzió esetén) Ha helyi fiókot hoz létre a kiépítési csomagban, 42 naponta módosítania kell a jelszót <strong>Gépház</strong> alkalmazással. Ha a jelszó nem változott ebben az időszakban, előfordulhat, hogy a fiók zárolva van, és nem tud bejelentkezni.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Az eszköz tanúsítvánnyal való ellátáshoz kattintson a <strong>Tanúsítvány hozzáadása elemre.</strong> Adja meg a tanúsítvány nevét, majd keresse meg és válassza ki a használni kívánt tanúsítványt.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Az Igen <strong>vagy</strong> a <strong>Nem</strong> kapcsolóval engedélyezheti a fejlesztői módot a HoloLens. <a href="/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">További információ a Fejlesztői módról.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Ne állítson be jelszót a kiépítési csomag védelméhez. Ha a kiépítési csomagot jelszó védi, a HoloLens kiépítése sikertelen lesz.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Ha végzett, válassza a **Létrehozás lehetőséget.** Ez csak néhány másodpercet vesz igénybe. A csomag létrehozása után a csomag tárolóhelye hivatkozásként jelenik meg az oldal alján.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. Kiépítési csomag létrehozása a HoloLens speciális kiépítéssel

> [!NOTE]
> A Speciális kiépítésben  létrehozott kiépítési csomagoknak nem kell kiadásfrissítési licencet tartalmazniuk az Windows Holographic for Business-hoz, hogy sikeresen alkalmazzanak egy HoloLens (1. generációs) példányra. [További információ a Windows Holographic for Business (1. HoloLens gen) ről.](hololens1-upgrade-enterprise.md)

1. A Windows Configuration Designer kezdőlapján válassza a **Speciális kiépítés lehetőséget.**
2. Az **Enter project details (Projekt részleteinek megadása)** ablakban adja meg a projekt nevét és helyét. Ha szükséges, adjon meg egy rövid leírást a projekt leírására.

3. Kattintson a **Tovább** gombra.

4. A Megtekinteni **és konfigurálni kívánt** beállítások kiválasztása ablakban válassza a **Windows 10 Holographic,** majd a Tovább **lehetőséget.**

5. Válassza a **Befejezés** gombot.

6. Bontsa ki **a Futásidejű beállítások** bontsa ki, és szabja testre a csomagot a cikkben [később ismertetett beállítások bármelyikének használatával.](#what-you-can-configure)

    > [!IMPORTANT]
    > (Csak Windows 10 1607-es verzió esetén) Ha helyi fiókot hoz létre a kiépítési csomagban, 42 naponta módosítania kell a jelszót **Gépház** alkalmazással. Ha a jelszó nem változott ebben az időszakban, előfordulhat, hogy a fiók zárolva van, és nem tud bejelentkezni. Ha a felhasználói fiók zárolva van, teljes [eszköz-helyreállítást kell végrehajtania.](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)

7. Válassza a **Fájl**  >  **mentése lehetőséget.**

8. Olvassa el a figyelmeztetést, amely szerint a projektfájlok bizalmas adatokat tartalmazhatnak, majd kattintson az **OK gombra.**

    > [!IMPORTANT]
    > Kiépítési csomag létrehozása során bizalmas adatokat is tartalmazhat a projektfájlokban és a kiépítési csomag (.ppkg) fájljában. Bár lehetősége van a .ppkg fájl titkosítására, a projektfájlok nincsenek titkosítva. A projektfájlokat biztonságos helyen tárolja, és törölje a projektfájlokat, amikor már nincs rájuk szükség.

9. Válassza **a**  >  **Kiépítési csomag exportálása lehetőséget.**

10. Módosítsa **a Tulajdonost** **rendszergazdai fiókra.** Ez magasabb prioritást ad meg ennek a kiépítési csomagnak, mint a más forrásokból az eszközre alkalmazott kiépítési csomagoknak. Kattintson a **Tovább** gombra.

11. Állítsa be a package **version (Csomagverzió) értékét.**

    > [!TIP]
    > Módosíthatja a meglévő csomagokat, és módosíthatja a verziószámot a korábban alkalmazott csomagok frissítéséhez.

12. A **Kiépítési csomag Biztonsági adatok kiválasztása területén válassza** a Tovább **lehetőséget.**

    > [!WARNING]
    > Ha titkosítja a kiépítési csomagot, a HoloLens kiépítése sikertelen lesz.  

13. Válassza **a Tovább** lehetőséget annak a kimeneti helynek a megadásához, ahová a kiépítési csomagot létre szeretné hozatni. Alapértelmezés szerint a Windows Configuration Designer a projektmappát használja kimeneti helyként.

    Az alapértelmezett kimeneti **hely** a Tallózás lehetőség választásával is megváltoztatható.

14. Kattintson a **Tovább** gombra.

15. Válassza **a Build (Build)** lehetőséget a csomag felépítésének elkezdődjön. A projekt adatai megjelennek a build oldalán, és a folyamatjelző sáv jelzi a build állapotát.

16. Ha a build elkészült, válassza a **Befejezés lehetőséget.**

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>Kiépítési csomag alkalmazása a HoloLens során

HoloLens a Windows Holographic 2004-es vagy [19041.1103-as](hololens-release-notes.md#windows-holographic-version-2004) vagy újabb buildverziójában található 2 eszköz USB-meghajtót használhat kiépítési csomag alkalmazásához. Egyszerűen másolja a .ppkg fájlt az USB-meghajtó gyökerének. A kiépítési csomagok csak akkor lesznek alkalmazva, ha az USB-meghajtó gyökerében vannak. A több kiépítési csomag egymás után lesz alkalmazva.

HoloLens [Holographic 20H2](hololens-release-notes.md#windows-holographic-version-20h2) vagy újabb Windows 2 eszköz újabb funkciókkal rendelkezik, amelyek leegyszerűsítik és leegyszerűsítik ezt a folyamatot, így automatikus. Tekintse át a következő szakaszokat:

- [Automatikus indítású kiépítés USB-ről](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Kiépítési csomagok automatikus megerősítése az OOBE-ban](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Automatikus kiépítés felhasználói felület használata nélkül](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Az USB-kábellel csatlakoztassa az eszközt egy számítógéphez (vagy a 2. HoloLens USB-meghajtóhoz), majd indítsa el az eszközt. Ne lépjen tovább az OOBE Első kezelhető **pillanat** lapján.
    - A HoloLens (1. generációs) lapon ez az oldal egy kék mezőt tartalmaz.
    - A HoloLens 2. oldalon található a fogmingbird.

2. Röviden nyomja le és engedje el egyszerre a **Volume Down** és a Power (Le- és **bekapcsolás)** gombot.

3. HoloLens eszközként jelenik meg a Fájlkezelő számítógépen.

4. A Fájlkezelő húzza a kiépítési csomagot (.ppkg) az eszköz tárhelyére.

5. Röviden nyomja le és engedje el egyszerre a **Volume Down** és **a Power** (Le- és bekapcsolás) gombokat az OOBE Első kezelhető **pillanat** lapján.

6. Az eszköz megkérdezi, hogy megbízik-e a csomagban, és szeretné-e alkalmazni. Győződjön meg arról, hogy megbízik a csomagban.

7. Látni fogja, hogy a csomag alkalmazása sikeres volt-e. Ha nem sikerült, javíthatja a csomagot, és újra próbálkozhat. Ha sikeres volt, folytassa az OOBE-val.

> [!NOTE]
> Ha az eszközt 2016 augusztusa előtt vásárolta meg, be kell jelentkeznie az eszközre egy Microsoft-fiók használatával, le kell szereznie a legújabb operációsrendszer-frissítést, majd alaphelyzetbe kell állítania az operációs rendszert a kiépítési csomag alkalmazáshoz.

### <a name="auto-launch-provisioning-from-usb"></a>Automatikus indítású kiépítés USB-ről

- Automatizált folyamatok, amelyek kevesebb felhasználói beavatkozást lehetővé teszik, ha a kiépítési csomagokkal rendelkező USB-meghajtókat az OOBE során használják.

A kiadás előtt a felhasználóknak manuálisan kellett elindítaniuk a kiépítési képernyőt az OOBE során a kiépítéshez egy gombkombináció használatával. A felhasználók mostantól kihagyhatja a gombkombinációt egy USB-tároló meghajtón található kiépítési csomag használatával.

1. Csatlakoztassa az USB-meghajtót a kiépítési csomaghoz az OOBE első kezelhető pillanatában
1. Amikor az eszköz készen áll a kiépítésre, az automatikusan megnyitja a kiépítési lapot.

Megjegyzés: Ha egy USB-meghajtó be van csatlakoztatva az eszköz indítása közben, az OOBE számba veszi a meglévő USB-tárolóeszközt, és figyel a további csatlakoztatott usb-meghajtókra is.

Olvassa el a [kiépítési csomagok OOBE során való alkalmazásával kapcsolatos további információért.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Kiépítési csomagok automatikus megerősítése az OOBE-ban
- Ha megjelenik a Kiépítési csomag lap, automatikusan alkalmazza az összes felsorolt csomagot, így kevesebb felhasználói beavatkozást lehetővé tevő automatizált folyamat jelenik meg.

Amikor megjelenik a kiépítés főképernyője, az OOBE 10 másodpercig számol, mielőtt automatikusan elkezdi alkalmazni az összes kiépítési csomagot. A felhasználók a várt csomagok ellenőrzése után ebben a 10 másodpercben is megerősítheti vagy megszakíthatja a műveletet.

### <a name="automatic-provisioning-without-using-ui"></a>Automatikus kiépítés felhasználói felület használata nélkül
- Kombinált automatikus folyamatok a kiépítés kevesebb eszköz-interakciója érdekében. 

Az USB-eszközökről történő kiépítés automatikus indításának és a kiépítési csomagok automatikus megerősítésének kombinálásával a felhasználók HoloLens 2 eszközt automatikusan kiépíthet az eszköz felhasználói felületének használata nélkül, vagy akár be is használhatja az eszközt. Több eszköz esetében továbbra is használhatja ugyanazt az USB-meghajtót és kiépítési csomagot. Ez akkor hasznos, ha egyszerre több eszközt telepít ugyanazon a területen. 

1. [Hozzon létre egy kiépítési csomagot](hololens-provisioning.md) [Windows Configuration Designer használatával.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Másolja a csomagot egy USB-tároló meghajtójára.
1. [A 2-es HoloLens](hololens-insider.md#ffu-download-and-flash-directions) a [19041.1361-es](https://aka.ms/hololens2previewdownload)vagy újabb buildre. 
1. Ha [az Advanced Recovery Companion befejezte](https://www.microsoft.com/store/productId/9P74Z35SFRS8) az eszköz flash (flash) funkcióját, csatlakoztassa az USB-C-kábelhez. 
1. Csatlakoztassa az USB-meghajtót az eszközhöz.
1. Amikor a HoloLens 2. eszköz elindul az OOBE-ban, automatikusan észleli a kiépítési csomagot az USB-meghajtón, és elindítja a kiépítési lapot.
1. 10 másodperc elteltével az eszköz automatikusan alkalmazza a kiépítési csomagot. 

Az eszköz konfigurálása megtörtént, és megjelenik a Sikeres kiépítés képernyő.

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>Kiépítési csomag alkalmazása/eltávolítása a HoloLens után

> [!NOTE]
> Ezek a lépések minden 2 HoloLens eszközre és HoloLens (1. generációs) eszközre vonatkoznak Windows Holographic 1809-es és újabb verzióiban.

A számítógépen kövesse az alábbi lépéseket:
1. Hozzon létre egy kiépítési csomagot a Create a provisioning package for HoloLens using the HoloLens wizard (Kiépítési csomag létrehozása a HoloLens [számára) HoloLens leírtak szerint.](hololens-provisioning.md)
2. Csatlakozás eszközt HoloLens USB-kábelen keresztül csatlakoztatja a számítógéphez. HoloLens eszközként jelenik meg a Fájlkezelő számítógépen.
3. Húzza a kiépítési csomagot az HoloLens.

A saját HoloLens kövesse az alábbi lépéseket:
1. A Fiók **Gépház**  >    >  **hozzáférése munkahelyi vagy iskolai fiókhoz:**. 
2. A **Kapcsolódó Gépház** válassza a Kiépítési csomag hozzáadása vagy eltávolítása **lehetőséget.**
3. A következő oldalon válassza **a Csomag hozzáadása lehetőséget a** fájlválasztó elindításához, majd válassza ki a kiépítési csomagot. Ha a mappa üres, válassza az Ez **az** eszköz, majd a **Dokumentumok lehetőséget.**

A csomag alkalmazása után megjelenik a Telepített **csomagok listájában.** A csomag részleteinek megtekintéséhez vagy a csomag eszközről való eltávolításához válassza ki a felsorolt csomagot.

## <a name="what-you-can-configure"></a>Amit konfigurálhat

A kiépítési csomagok konfigurációszolgáltatókat (CSP-eket) használnak. Ha nem ismeri a CSP-eket, tekintse meg a Bevezetés a konfigurációszolgáltatók [(CSP-k) szolgáltatásba az it-szakemberek számára részt.](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)

A Windows Configuration Designerben a Windows Holographic számára létrehozott kiépítési csomag  beállításai a Holographic által támogatott [CSP-Windows alapulnak.](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) Az alábbi táblázat azokat a beállításokat ismerteti, amelyek konfigurálhatóak a HoloLens.

![Általános futásidejű beállítások a HoloLens.](images/icd-settings.png)

| Beállítás | Leírás |
| --- | --- |
| **Tanúsítványok** | Tanúsítvány központi telepítése a HoloLens.  |
| **ConnectivityProfiles (Kapcsolatprofilok)** | Telepítsen egy Wi-Fi profilt a HoloLens.   |
| **Kiadásfrissítés** | [Frissítsen a Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Házirendek** | A fejlesztői mód engedélyezése vagy HoloLens. [A szabályzatok által támogatott Windows Holographic for Business](/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>Alkalmazás telepítése kiépítési csomagon keresztül

Az alkalmazások 2 eszközön üzembe HoloLens telepíthetők. Ez lehetővé teszi egy könnyen újra használható csomag használatát, amely segít az alkalmazások terjesztésében. Olvassa el az alkalmazások üzembe [helyezésére vonatkozó teljes útmutatót a Kiépítési csomagok segítségével.](app-deploy-provisioning-package.md)  

> [!NOTE]
> HoloLens (1. generációs) csak korlátozott mértékben támogatja az alkalmazások telepítését **(UniversalAppInstall**) egy kiépítési csomag használatával. HoloLens (1. generációs) eszközök csak az OOBE-n keresztül támogatják az alkalmazások PPKG-n keresztüli telepítését, és csak a felhasználói környezet telepítése esetén.
