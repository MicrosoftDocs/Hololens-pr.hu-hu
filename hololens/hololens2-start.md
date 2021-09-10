---
title: A 2. HoloLens beállítása
description: Megtudhatja, hogyan állíthatja be HoloLens Wi-Fi 2. fiókot első alkalommal egy Microsoft- (MSA-) vagy Azure Active Directory-fiókkal (AAD) egy hálózaton keresztül.
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 8f07ed42c873b62b3b4201c2756b55bbb29707d3
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427302"
---
# <a name="set-up-your-hololens-2"></a>A 2. HoloLens beállítása

Az első alkalommal, amikor bekapcsolja a HoloLens, a rendszer végigvezeti az eszköz beállításán, a felhasználói fiókkal való bejelentkezésen és a HoloLens a szemének.  Ez a szakasz végigvezeti a HoloLens 2. kezdeti beállítási folyamatán.

A következő szakaszban megtudhatja, hogyan dolgozhat a hologramokkal HoloLens és hogyan kommunikálhat a hologramokkal. A cikkre való ugráshoz lásd: [Getting around HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Előkészületek

Mielőtt hozzá kezd, győződjön meg arról, hogy a következők állnak rendelkezésre:

**Egy hálózati kapcsolat.** A beállításhoz a HoloLens kell csatlakoztatnia a hálózathoz. A HoloLens 2-vel csatlakozhat Wi-Fi ethernet használatával (USB-C-to-Ethernet adapter szükséges). Az első csatlakozáskor szüksége lesz egy nyílt vagy jelszóval védett hálózatra, amely nem igényel webhely megnyitását vagy tanúsítványokkal való csatlakozást. [További információ a által HoloLens webhelyekről.](hololens-offline.md)

**Egy Microsoft-fiók.** Be kell jelentkeznie a HoloLens egy Microsoft-fiók (vagy a munkahelyi fiókjával, ha az eszköz a vállalat tulajdonában van). Ha még nincs saját Microsoft-fiók, account.microsoft.com és [](https://account.microsoft.com) állítson be egyet ingyenesen.

**Biztonságos, jól világított tér, amely nem jár veszélyekkel.** [Egészségügyi és biztonsági információk.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**Az opcionális kényelmi kiegészítők,** amelyek a HoloLens, segítenek a legkényelmesebb választásban. [További információ a illeszkedésről és a kényelemről.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>A Windows beállítása

A 2. HoloLens első alkalommal az első feladata a Holographic Windows beállítása.  Amikor elkezdi a HoloLens, a zene hallatán egy Microsoft-embléma látható.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

Látni fogja, hogy egy madár van a közelben.

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

Az Ön kezében fogta a kezében.

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

Gombra kattint a Microsoft emblémája. Nyomja meg a gombot, HoloLens 2. lépés végigkúton az alábbi lépéseken:

1. Válassza ki a nyelvet.

    <img src="images/04-language.png" width="500px" alt="Select language">

1. Válassza ki a régiót.

    <img src="images/05-region.png" width="500px" alt="Select region">

1. A HoloLens be a szemének.  Ha úgy dönt, hogy kihagyja a hitelesítést, a rendszer a következő bejelentkezéskor kérni fogja. 

    1. Először módosítania kell a vizort.
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. A besziratáláshoz célokat (más néven gemeket) kell látnia. Nem gond, ha villog vagy bezárja a tekintetét a bepillantás közben, de nem próbál más objektumokra nézni a helyiségben vagy a fizikai térben. HoloLens segítségével megismerheti a szem pozícióját, hogy jobban renderelje a holografikus világát. 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        A hitelesítés után a hologramok akkor is helyesen jelennek meg, ha a vizor a fejében eltolást vált. A rendszer helyben tárolja a helyi eszközön található adatokat, és nem társítja őket fiókinformációkhoz. További információ: [Az adatok és a biztonság.](hololens-calibration.md#calibration-data-and-security)

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. Csatlakozás (válassza az Wi-Fi ethernet-kapcsolat lehetőséget).

     HoloLens automatikusan beállítja az időzónát a hálózati Wi-Fi alapján. A telepítés befejezése után az időzónát a Gépház módosíthatja.

    ![Csatlakozás Wi-Fi-hálózathoz.](images/11-network.png)

    > [!NOTE] 
    > Ha az Wi-Fi-lépésen túlhaladt, és később másik hálózatra kell váltania, miközben  még be van állítva, a Kötet le és a Bekapcsológombok egyidejűleg is használhatók, hogy visszatérjen erre a lépésre, ha 2019 októberében vagy később futtatja az operációs rendszer verzióját.  Korábbi verziók esetén előfordulhat, [](hololens-recovery.md) hogy alaphelyzetbe kell állítania az eszközt, vagy újra kell indítania egy olyan helyen, ahol a Wi-Fi-hálózat nem érhető el, hogy megakadályozza az automatikus csatlakozást.
    > 
    > Azt is vegye figyelembe, HoloLens telepítés során két perces hitelesítőadat-időtúllépési idő van beállítva. A felhasználónevet/jelszót két percen belül meg kell adni, különben a rendszer automatikusan törli a felhasználónév mezőt.

1. HoloLens 2. példa AutoPilot-profilt keres és alkalmaz, ha van ilyen. Ezen a képernyőn nincs szükség műveletre.
 
    ![Autopilot-profilkeresés.](images/autopilot-profile-search.png) 

1. Kattintson **az Elfogadás** gombra a licencelési képernyőn.

    ![Windows licencszerződést.](images/windows-license-agreement.png)

1. Jelentkezzen be a felhasználói fiókjába. Választhat, hogy a saját munkahelyi **vagy** iskolai tulajdonom, és **az én tulajdonom.**

    ![Állítsa be a felhasználót.](images/13-device-owner.png)
    - Ha a Saját munkahelyi vagy iskolai tulajdonú lehetőséget **választja,** egy Azure AD-fiókkal jelentkezik be. Ha a szervezet prémium szintű Azure AD és konfigurálta az automatikus MDM-regisztrációt, a HoloLens regisztrál az MDM-be. Ha a szervezet nem használ prémium szintű Azure AD, az automatikus MDM-regisztráció nem érhető el. Ebben az esetben manuálisan kell regisztrálnia az HoloLens [eszközkezelésben.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Adja meg a szervezeti fiók adatait.
        1. Fogadja el az adatvédelmi nyilatkozatot és a végfelhasználói licencszerződést.
        1. Jelentkezzen be Azure AD-beli hitelesítő adataival. Ez átirányítható a szervezet bejelentkezési oldalára.
        1. Folytassa az eszköz beállítását.

    - Ha a Saját **tulajdonom lehetőséget választja,** egy új Microsoft-fiók. A telepítés befejezése után manuálisan regisztrálhatja a HoloLens [eszközkezelésben.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Adja meg Microsoft-fiók adatait.
        2. Írja be a jelszót. Ha a Microsoft-fiók [kétlépéses ellenőrzést (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)igényel, akkor teljes körű ellenőrzési folyamatot kell végrehajtania.

        
1. Az Iris-bejelentkezés beállításához válassza a **Tovább lehetőséget.** Hasonló élményt fog tapasztalni, mint a szemkontraszt. Amikor **a vizsgálat** befejeződött, válassza a Kész lehetőséget. Választhatja a **Kihagyás lehetőséget is** a lépés kihagyása előtt.
    
    <img src="images/setup-iris.png" width="500px" alt="Iris setup">

    <img src="images/iris-setup-complete.png" width="500px" alt="Iris setup completion">

     
  
1. Pin-kódot fog beállítani az eszközre való bejelentkezéshez. Ez a PIN-kód eszközspecifikus. 

    ![A Windows Hello.](images/setup-windows-hello.png)

    ![Pin Windows Hello pin-kód beállítása.](images/windows-hello-pin.png)

    ![Windows Hello A telepítés sikeres volt.](images/windows-hello-successful.png) 

    
1. Válassza ki, hogy a 2. HoloLens szeretné-e engedélyezni a beszédet.

    <img src="images/22-do-more-with-voice.png" width="500px" alt="Enable Cortana">

1. Válassza ki, hogy a 2. HoloLens szeretné-e engedélyezni a helyet.
    
    <img src="images/setup-location-services.png" width="500px" alt="Enable location services">

1. Válassza ki a telemetria szintjét. Ha lehetséges, engedélyezze a választható telemetriát. Ezek az információk nagy segítséget HoloLens mérnöki csapatnak.

    <img src="images/24-telemetry.png" width="500px" alt="Telemetry level">


1. Ismerje meg, hogyan használhatja az indítási kézmozdulatot HoloLens 2.

    <img src="images/26-01-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 1">

    <img src="images/26-02-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 2">
    
    > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]
    
    Gratulálunk!  A telepítés befejeződött, és készen áll a HoloLens!

## <a name="next-steps"></a>Következő lépések

1. Azonnal elkezdhet interakciót Mixed Reality és navigálhat Windows 10 HoloLens-on – a **Tippek** alkalmazás gyakorlati oktatóanyagokat is elérhető a kéz-interakciókhoz. Az indítási kézmozdulattal a Start menüre vagy a "Ugrás az indításhoz" szövegre használhatja, majd válassza a Tippek.

1. Az alábbi gombra kattintva tovább olvashat a 2. HoloLens való ismerkedésről.

> [!div class="nextstepaction"]
> [Tájékozódás a HoloLens 2-ben](hololens2-basic-usage.md)
