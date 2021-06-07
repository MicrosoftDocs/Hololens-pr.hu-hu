---
title: Üzembe helyezési útmutató – Vállalati összekapcsolt HoloLens 2 Dynamics 365-útmutatókkal – Üzembe helyezés
description: Útmutató a HoloLens 2-eszközök vállalati csatlakoztatott hálózaton keresztüli üzembe helyezéséhez Dynamics 365-útmutatók segítségével.
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
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378069"
---
# <a name="deploy---corporate-connected-guide"></a>Üzembe helyezés – Vállalati csatlakoztatott útmutató

Az egyes üzembe helyezések fontos részét képezi annak biztosítása, hogy az üzemelő példány megfelelően legyen beállítva, mielőtt saját maga teszteli azt, így zökkenőmentes felhasználói élményt biztosít a végfelhasználó számára.

Mivel az Wi-Fi-tanúsítványt MDM-en keresztül telepítjük, először be kell álltatnunk a HoloLenst, és regisztrálni kell az eszközöket egy nyílt Wi-Fi-hálózaton vagy egy olyan hálózaton, amely nem igényli a tanúsítványt. Miután a HoloLens befejezte az OOBE-t és a Beléptetést, az eszköz megkapja a korábban konfigurált hálózati tanúsítványt és LOB-t, és ellenőrizjük, hogy mindkét eszköz megkapta-e.

Ezt követően meggyőződhet arról, hogy a tesztelési útmutatót is meg tudja majd tenni és működtetni is tudja.

## <a name="enrollment-validation"></a>Regisztráció ellenőrzése

Most, hogy minden megfelelően van konfigurálva az Azure AD-hez és az MDM-regisztrációhoz, a többinek egy illesztésnek kell lennie. Szüksége lesz egy virtuális Wi-Fi a HoloLens-eszközre, valamint az egyik korábban konfigurált Azure AD-felhasználói fiókra.

Ha az eszköz jelenleg nem gyári beállításokat használ, ideje [újrafésülni az eszközt.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Miután az eszköz az OOBE-ban van, el kell kezdenie a műveleteket, és követnie kell az utasításokat.

2. Csatlakozzon egy nyílt Wi-Fi hálózathoz, amely nem igényel tanúsítványokat a Wi-Fi-hálózathoz való csatlakozáshoz. Ez lehetővé teszi, hogy az eszköz letöltse a tanúsítványt, amely a kezdeti beállítás után Wi-Fi a szervezet eszközén.

3. A kritikus kérdés akkor lesz, amikor a rendszer megkérdezi, hogy ki a **HoloLens tulajdonában?** Válassza **a Saját munkahelyi vagy iskolai tulajdonban van lehetőséget,** és adja meg Az Azure AD-fiókja hitelesítő adatait.

4. Ha a regisztráció sikeres, a rendszer kérni fogja a PIN-kód beállítását. Ez a PIN-kód a felhasználó egyedi eszköze. Emellett meg kell adnia az Íriszvizsgálatokat, a hangadatokat és a telemetriai beállításokat is, végül pedig megtudhatja, hogyan nyithatja meg a Start menüt, és hogyan fejezhatja be az OOBE-t.

5. Miután a kezdőlapra Mixed Reality, nyissa meg Start menü az  előbb megtanult Indítás kézmozdulattal.

6. Válassza a **Beállítások alkalmazást,** majd a **Rendszer lehetőséget.** Az első információ, amit látni fog, az eszköz neve, amely a HoloLens 2-eszközhöz a HOLOLENS lesz, amelyet hat karakterből álló sztring &quot; &quot; követ.

7. Jegyezze fel ezt a nevet.

    ![HoloLens 2 Beállítások képernyő](./images/hololens2-settings-about.jpg)

8. Ellenőrizze, hogy az eszköz sikeresen csatlakozott-e az Azure AD-hez. Kétféleképpen lehetséges:

    1.  A Beállítások alkalmazás. A **Beállítások menüben** **válassza a Fiókok**  ->  **hozzáférése munkahelyi vagy iskolai fiókhoz lehetőséget.** Ezen a képernyőn ellenőrizheti, hogy sikeresen regisztrált-e, ha a Connected to nameofAAD&#39;Azure AD (Csatlakoztatva a névhez)&#39;&quot; Azure AD-hez. Csatlakoztatva a *yourusername@nameofAAD.onmicrosoft.com* következővel: . Ez ellenőrzi, hogy az eszköz csatlakozik-e a&#39;Azure AD-hez.

    1. A [Azure Portal.](https://portal.azure.com/#home) Keresse meg **Azure Active Directory**  ->  **Eszközök**  ->  **Minden eszköz adatokat,** és keressen rá az eszköz nevére. Az Összekapcsolás típusa alatt az "Azure AD Joined" (Azure AD-hez csatlakozott) szöveg fog ni.
        ![Csatlakozás típusának ellenőrzése az Azure AD-ban](./images/hololens2-devices-all-devices.png)

9. Ellenőrizze, hogy az eszköz regisztrálva van-e az MDM-hez. Kétféleképpen lehetséges:

    1. A **Beállítások menüben** válassza **a Fiókok elérése** munkahelyi vagy iskolai  ->  **fiókhoz lehetőséget.** Ezen a képernyőn ellenőrizheti, hogy sikeresen regisztrált-e, ha a Connected to nameofAAD&#39;Azure AD (Csatlakoztatva a névhez)&#39;&quot; Azure AD-hez. Csatlakoztatva a *yourusername@nameofAAD.onmicrosoft.com* következővel: . Ebben a Hozzáférés munkahelyi vagy iskolai fiókban válassza a Connected to nameofAAD&#39;s Azure AD (Csatlakoztatva a névhez)&#39;&quot; Azure AD-hez. Connected by yourusername@nameofAAD.onmicrosoft.com &quot; (Csatlakoztatva a következővel) és válassza az **Info (Információ)** gombot.

    1. [Microsoft Endpoint Manager Felügyeleti központ.](https://endpoint.microsoft.com/#home) Jelentkezzen be, és válassza az **Eszközök,** majd **a Minden eszköz lehetőséget.** Innen megkeresheti a HoloLens-eszköz&#39;nevét. A HoloLens megjelenik az Intune-ban.

        ![Intune-felügyelet ellenőrzése az Azure AD-ban](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi tanúsítvány érvényesítése

Az eszköznek már megkapta a Wi-Fi tanúsítványt. A legegyszerűbb ellenőrzés az, ha megpróbál csatlakozni ahhoz a Wi-Fi kapcsolathoz,&#39;megkapta a tanúsítványt. Nyissa meg a **Beállítások** alkalmazást, lépjen a Hálózati **&amp; internet**  ->  **Wi-Fi elemre,** és válassza ki a Wi-Fi-kapcsolatot. A csatlakozás után nyissa meg a Microsoft Edge alkalmazást, és ellenőrizze, hogy el tud-e navigálni egy webhelyre.

Annak megerősítéséhez, hogy megkapta a tanúsítványt az eszközön, használja a [Tanúsítványkezelőt.](https://docs.microsoft.com/hololens/certificate-manager)

## <a name="validate-lob-app-install"></a>LOB-alkalmazás telepítésének ellenőrzése

A felügyelt alkalmazás telepítési folyamatának ellenőrzéséhez ellenőrizze, hogy telepítve van-e az alkalmazás, vagy jelölje be a Beállítások jelölőnégyzetet. Ha egy LOB-alkalmazást kötelező telepítésként konfigurál a csoport számára, miután regisztrálta a HoloLenst egy felhasználóval a hozzárendelt csoportban, az alkalmazás automatikusan letölti az alkalmazást a HoloLensbe.

Nyissa meg a Start menü, és válassza a **Minden alkalmazás** lehetőséget. Az alkalmazások számától függően előfordulhat, hogy az  oldal felfelé vagy lefelé **gombjait kell használnia.**

Az alkalmazás eszközre való telepítésének ellenőrzéséhez ezt a Settings Accounts Access munkahelyi vagy iskolai fiókon keresztül tudja megtenni. Válassza ki a fiókot, majd kattintson az Információ gombra, és görgessen le az eszközre az  ->    ->    MDM-től alkalmazott különböző konfigurációk és alkalmazások eléréséhez.

A telepítés Intune-ból való érvényesítéséhez lépjen a [MEM-portál](https://endpoint.microsoft.com/#home)Alkalmazások -> Minden alkalmazás  ->     -> *ANameOfYourApp eszköz* telepítési  ->  **állapotlapjára.**

További információ: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Dynamics 365-útmutatók ellenőrzése

A Útmutatók alkalmazásnak vannak módjai a HoloLensen, a szerzői és üzemeltetési módok. Az útmutatót az üzemeltetés előtt be kell fejeznie.

### <a name="authoring-the-guide"></a>Útmutató írása

Ehhez a gyors ellenőrzéshez nem kell sokat tenni. Egyszerűen válassza ki a számítógépen előkészített útmutatót. A rövid ellenőrzéshez a holografikus horgonyt kell használnia az útmutatóhoz. [](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor) Ezt követően helyezze el [a lépéseket és modelleket.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)

>[!NOTE]
> A Szerző **szerepkörre szüksége** lesz a számítógépre való bejelentkezéshez és a HoloLensen a szerzőhöz. Az Operátor szerepkör csak olvasható, és nincs hozzáférése a PC-alkalmazáshoz.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Az útmutató működtetési útmutatója

Ha a hologramok a helyén vannak, tesztelheti az útmutatót. 
- Operátori **mód kiválasztása**
- Kattintson végig az útmutató lépései között.

Az útmutató működtetésével kapcsolatos további részletes útmutatásért tekintse meg az alábbi forrásforrásokat:

[Útmutató üzemeltetése a Dynamics 365-útmutatókban – áttekintés](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[A Lépés kártya használata operátorként a Dynamics 365-útmutatókban](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Következő lépés 
> [!div class="nextstepaction"]
> [Vállalati csatlakoztatott üzemelő példány – Karbantartás](hololens2-corp-connected-maintain.md)
