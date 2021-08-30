---
title: A 2. HoloLens beállítása
description: Ismerje meg, hogyan állíthatja be HoloLens 2. verziójának első beállítását Wi-Fi hálózaton microsoftos (MSA) vagy Azure Active Directory (AAD)-fiókkal.
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
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189766"
---
# <a name="set-up-your-hololens-2"></a>A 2. HoloLens beállítása

Az első alkalommal, amikor bekapcsolja a HoloLens, a rendszer végigvezeti az eszköz beállításán, a felhasználói fiókkal való bejelentkezésen és a HoloLens a szemére.  Ez a szakasz végigvezeti a HoloLens 2. kezdeti beállítási folyamatán.

A következő szakaszban megtudhatja, hogyan dolgozhat a HoloLens és interakcióba léphet a hologramokkal. A cikkre való ugráshoz lásd: [Getting around HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Előkészületek

Mielőtt hozzá is kezd, győződjön meg arról, hogy az alábbiak elérhetők:

**Egy hálózati kapcsolat.** A beállításhoz a HoloLens kell csatlakoztatnia a hálózatot. A HoloLens 2-vel csatlakozhat Wi-Fi vagy Ethernet használatával (USB-C-to-Ethernet adapter szükséges). Az első csatlakozáskor szüksége lesz egy nyílt vagy jelszóval védett hálózatra, amely nem igényel webhelyre való navigálást vagy tanúsítványokat a csatlakozáshoz. [További információ a által HoloLens webhelyekről.](hololens-offline.md)

**Egy Microsoft-fiók**. Be kell jelentkeznie a HoloLens egy Microsoft-fiók -fiókkal (vagy a munkahelyi fiókjával, ha az eszköz a vállalat tulajdonában van). Ha még nem Microsoft-fiók, account.microsoft.com ingyenes beállítását. [](https://account.microsoft.com)

**Biztonságos, jól meggyújtott hely, amely nem jár veszélyekkel.** [Egészségügyi és biztonsági információk.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**Az opcionális kényelmi kiegészítők,** amelyek a HoloLens, a legkényelmesebb illeszkedés érdekében. [További információ a illeszkedésről és a kényelemről.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>A Windows beállítása

A 2. HoloLens első alkalommal az első feladata a Holographic Windows beállítása.  Amikor elkezdi a HoloLens, a zene hallatán egy Microsoft-embléma fog látni.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

Látni fogja, hogy egy madársziva van a közelben.

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

Az Ön kezében lesz.

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

Gombra kattint a Microsoft emblémája. Nyomja meg a gombot, és HoloLens 2. lépés végigveszi a következő lépéseken:

1. Válassza ki a nyelvet.

    <img src="images/04-language.png" width="500px" alt="Select language">

1. Válassza ki a régiót.

    <img src="images/05-region.png" width="500px" alt="Select region">

1. A HoloLens a tekintetét.  Ha úgy dönt, hogy kihagyja a hitelesítést, a rendszer a következő bejelentkezéskor kérni fogja. 

    1. Először is módosítania kell a vizort.
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. A besziratáshoz egy célkészletet (gemeket) fogunk látni. Nem gond, ha villog vagy bezárja a tekintetét a beszibrálás közben, de nem próbál meg a helyiségben vagy a fizikai térben lévő többi objektumra nézni. HoloLens a folyamat során megismeri a szem pozícióját, hogy jobban renderelje a holografikus világot. 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        A besziratás után a hologramok akkor is megfelelően jelennek meg, ha a vizor a fejében eltolást vált. A kockázatra vonatkozó információkat a rendszer helyben tárolja az eszközön, és nincs társítva fiókinformációkhoz. További információkért [lásd: A tanúsítványadatok és a biztonság.](hololens-calibration.md#calibration-data-and-security)

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. Csatlakozás (válassza ki az Wi-Fi ethernet-kapcsolatot).

     HoloLens automatikusan beállítja az időzónát a hálózati Wi-Fi alapján. A telepítés befejezése után az időzónát az alkalmazás Gépház módosíthatja.

    ![Csatlakozás Wi-Fi-hálózathoz.](images/11-network.png)

    > [!NOTE] 
    > Ha túlhalad az Wi-Fi lépésen, és később másik hálózatra kell váltania,  miközben  még be van állítva, egyidejűleg a Kötet le és a Tápellátás gombok lenyomása után visszatérhet ehhez a lépéshez, ha 2019 októberében vagy később operációsrendszer-verziót futtat. Előfordulhat, hogy a korábbi [](hololens-recovery.md) verziókhoz alaphelyzetbe kell állítania az eszközt, vagy újra kell indítania egy olyan helyen, ahol az Wi-Fi-hálózat nem érhető el, hogy megakadályozza az automatikus csatlakozást.
    > 
    > Azt is vegye figyelembe, HoloLens telepítés során a hitelesítő adatok két perces időtúllépést jegyeznek fel. A felhasználónevet/jelszót két percen belül meg kell adni, különben a rendszer automatikusan törli a felhasználónév mezőt.

1. HoloLens 2. példa autopilot-profilt keres és alkalmaz, ha van ilyen. Ezen a képernyőn nincs szükség műveletre.
 
    ![Autopilot-profilkeresés.](images/autopilot-profile-search.png) 

1. Kattintson **az Elfogadás** gombra a licencelési képernyőn.

    ![Windows licencszerződést.](images/windows-license-agreement.png)

1. Jelentkezzen be a felhasználói fiókjába. Választhat, hogy a Saját munkahelyi **vagy** iskolai tulajdonban van, és hogy **az én tulajdonom.**

    ![Állítsa be a felhasználót.](images/13-device-owner.png)
    - Ha a Saját munkahelyi vagy iskolai tulajdonú lehetőséget **választja,** egy Azure AD-fiókkal jelentkezik be. Ha a szervezet prémium szintű Azure AD és konfigurálta az automatikus MDM-regisztrációt, a HoloLens regisztrál az MDM-be. Ha a szervezet nem használ prémium szintű Azure AD, az automatikus MDM-regisztráció nem érhető el. Ebben az esetben manuálisan kell regisztrálnia a HoloLens [eszközkezelésben.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Adja meg a szervezeti fiók adatait.
        1. Fogadja el az adatvédelmi nyilatkozatot és a végfelhasználói licencszerződést.
        1. Jelentkezzen be az Azure AD-beli hitelesítő adataival. Ez átirányíthatja a szervezet bejelentkezési oldalára.
        1. Folytassa az eszköz beállítását.

    - Ha a **Saját tulajdonom lehetőséget választja,** egy új Microsoft-fiók. A telepítés befejezése után manuálisan regisztrálhatja a HoloLens [eszközkezelésben.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Adja meg Microsoft-fiók adatait.
        2. Írja be a jelszót. Ha a Microsoft-fiók [kétlépéses ellenőrzést (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)igényel, akkor teljes körű ellenőrzési folyamatot kell végrehajtania.

        
1. Az Iris-bejelentkezés beállításához válassza a **Tovább lehetőséget.** A szemredúsztáshoz hasonló élményt fog tapasztalni. Amikor **a** vizsgálat befejeződött, válassza a Kész lehetőséget. Választhatja a Kihagyás **lehetőséget is** a lépés kihagyásaként.
    
    <img src="images/setup-iris.png" width="500px" alt="Iris setup">

    <img src="images/iris-setup-complete.png" width="500px" alt="Iris setup completion">

     
  
1. Pin-kódot fog beállítani az eszközre való bejelentkezéshez. Ez a PIN-kód eszközspecifikus. 

    ![A Windows Hello.](images/setup-windows-hello.png)

    ![Pin Windows Hello PIN-kód beállítása.](images/windows-hello-pin.png)

    ![Windows Hello A telepítés sikeres volt.](images/windows-hello-successful.png) 

    
1. Válassza ki, hogy a 2. HoloLens szeretné-e engedélyezni a beszédet.

    <img src="images/22-do-more-with-voice.png" width="500px" alt="Enable Cortana">

1. Válassza ki, hogy a 2. HoloLens szeretné-e engedélyezni.
    
    <img src="images/setup-location-services.png" width="500px" alt="Enable location services">

1. Válassza ki a telemetria szintjét. Ha lehetséges, engedélyezze a választható telemetriát. Ezek az információk nagy segítséget HoloLens mérnöki csapatnak.

    <img src="images/24-telemetry.png" width="500px" alt="Telemetry level">


1. Ismerje meg, hogyan használhatja a 2. HoloLens kézmozdulatot.

    <img src="images/26-01-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 1">

    <img src="images/26-02-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 2">
    
    > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]
    
    Gratulálunk!  A beállítás befejeződött, és készen áll a HoloLens!

## <a name="next-steps"></a>Következő lépések

1. Azonnal elkezdhet interakcióba lépni a Mixed Reality és navigálhat Windows 10-on HoloLens – a **Tippek** alkalmazásban gyakorlati oktatóanyagokat is kap a kézi interakciókhoz. Az indítási kézmozdulattal az Indítás vagy az Ugrás az indításhoz szövegre használhatja, majd válassza a Tippek.

1. Az alábbi gombra kattintva tovább olvashat a 2. HoloLens való ismerkedésről.

> [!div class="nextstepaction"]
> [Tájékozódás a HoloLens 2-ben](hololens2-basic-usage.md)
