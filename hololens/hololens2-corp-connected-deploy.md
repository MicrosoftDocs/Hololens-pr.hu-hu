---
title: Üzembe helyezési útmutató – Vállalati csatlakoztatott HoloLens 2 Dynamics 365-útmutatók – Üzembe helyezés
description: A Dynamics 365-útmutatók segítségével megtudhatja, hogyan állíthatja be HoloLens 2. eszköz üzembe helyezését vállalati csatlakoztatott hálózaton keresztül.
keywords: HoloLens, felügyelet, vállalati kapcsolat, Dynamics 365-útmutatók, AAD, Azure AD, MDM, Mobile Eszközkezelés
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
ms.openlocfilehash: 7df2b00b2d87be7b9ad4a5d84c83251ec0ebec4d
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189681"
---
# <a name="deploy---corporate-connected-guide"></a>Üzembe helyezés – Vállalati csatlakoztatott útmutató

Az egyes üzembe helyezések fontos részét képezi annak biztosítása, hogy az üzemelő példány megfelelően legyen beállítva, mielőtt saját maga teszteli azt, így zökkenőmentes felhasználói élményt biztosít a végfelhasználó számára.

Mivel az Wi-Fi-tanúsítványt MDM-en keresztül telepítjük, először be kell álltatnunk az HoloLens-t, és regisztrálni kell az eszközöket egy nyílt Wi-Fi-hálózaton vagy egy olyan hálózaton, amely nem igényli a tanúsítványt. Ha az HoloLens befejeződött az OOBE és a Enrolled (Regisztráció) folyamat, az eszköz megkapja a korábban konfigurált hálózati tanúsítványt és LOB-t, és ellenőrizjük, hogy az eszköz mindkét üzenetet megkapta-e.

Ezt követően meggyőződhet arról, hogy egy teszt útmutatót is tud majd szerzői és működtetni.

## <a name="enrollment-validation"></a>Regisztráció ellenőrzése

Most, hogy minden megfelelően van konfigurálva az Azure AD-hez és az MDM-regisztrációhoz, a többinek egy illesztésnek kell lennie. Szüksége lesz egy Wi-Fi kapcsolatra és HoloLens eszközre, valamint egy korábban konfigurált Azure AD felhasználói fiókra.

Ha az eszköz jelenleg nem gyári beállításokat használ, ideje [újrafésülni az eszközt.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Miután az eszköz az OOBE-ban van, el kell kezdenie a műveleteket, és követnie kell az utasításokat.

2. Csatlakozás olyan nyílt hálózati Wi-Fi, amely nem igényel tanúsítványokat a Wi-Fi-hálózathoz való csatlakozáshoz. Ez lehetővé teszi, hogy az eszköz letöltse a tanúsítványt, amely a kezdeti beállítás után Wi-Fi a szervezet eszközén.

3. A kritikus kérdés akkor lesz, amikor a rendszer **megkérdezi, hogy Who-e a HoloLens?** Válassza **a Saját munkahelyi vagy iskolai tulajdonban van lehetőséget,** és adja meg Az Azure AD-fiókja hitelesítő adatait.

4. Ha a regisztráció sikeres, a rendszer kérni fogja a PIN-kód beállítását. Ez a PIN-kód a felhasználó egyedi eszköze. Emellett meg kell adnia az Íriszvizsgálatokat, a hangadatokat és a telemetriai beállításokat, végül pedig megtudhatja, hogyan nyithatja meg a Start menüt, és hogyan fejezhatja be az OOBE-t.

5. Miután a kezdőlapra Mixed Reality, nyissa meg Start menü az  előbb megtanult Indítás kézmozdulattal.

6. Válassza ki a **Gépház** alkalmazást, majd válassza a **Rendszer lehetőséget.** Az első információ, amit látni fog, az eszköz neve, amely a HoloLens 2-es eszközhöz a HOLOLENS lesz, amelyet egy hat karakterből álló sztring &quot; &quot; követ.

7. Jegyezze fel ezt a nevet.

    ![HoloLens 2 Gépház képernyő.](./images/hololens2-settings-about.jpg)

8. Ellenőrizze, hogy az eszköz sikeresen csatlakozott-e az Azure AD-hez. Kétféleképpen lehetséges:

    1.  Az Gépház alkalmazás. A **Gépház** fiókok   ->  **hozzáférése munkahelyi vagy iskolai fiókhoz lehetőséget.** Ezen a képernyőn ellenőrizheti, hogy sikeresen regisztrált-e. Ehhez a Connected to nameofAAD&#39;Azure AD (Csatlakoztatva a következőhöz)&#39;&quot; Azure AD-hez. Csatlakoztatva a *yourusername@nameofAAD.onmicrosoft.com* következővel: . Ez ellenőrzi, hogy az eszköz csatlakozik-e a szervezethez&#39;Azure AD-hez.

    1. A [Azure Portal.](https://portal.azure.com/#home) Keresse meg **Azure Active Directory**  ->  **Eszközök**  ->  **Minden eszköz adatokat,** és keressen rá az eszköz nevére. Az Összekapcsolás típusa alatt az "Azure AD Joined" (Azure AD-hez csatlakozott) szöveg fog ni.
        ![Ellenőrizze a Csatlakozás típusát az Azure AD-ban.](./images/hololens2-devices-all-devices.png)

9. Ellenőrizze, hogy az eszköz regisztrálva van-e az MDM-hez. Kétféleképpen lehetséges:

    1. A **Gépház** válassza **a Fiókok**  ->  **hozzáférése munkahelyi vagy iskolai fiókhoz lehetőséget.** Ezen a képernyőn ellenőrizheti, hogy sikeresen regisztrált-e. Ehhez a Connected to nameofAAD&#39;Azure AD (Csatlakoztatva a következőhöz)&#39;&quot; Azure AD-hez. Csatlakoztatva a *yourusername@nameofAAD.onmicrosoft.com* következővel: . Ebben a Hozzáférés munkahelyi vagy iskolai fiókban válassza a Connected to nameofAAD&#39;s Azure AD (Csatlakoztatva a névhez)&#39;&quot; Azure AD-hez. Connected by yourusername@nameofAAD.onmicrosoft.com &quot; (Csatlakoztatva a következővel) és válassza az **Info (Információ)** gombot.

    1. [Microsoft Endpoint Manager Felügyeleti központ .](https://endpoint.microsoft.com/#home) Jelentkezzen be, és válassza az **Eszközök,** majd **a Minden eszköz lehetőséget.** Innen megkeresheti a HoloLens eszköz&#39;nevét. Az Intune-ban a HoloLens kell lennie.

        ![Ellenőrizze, hogy az Intune kezeli-e az Azure AD-ban.](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi tanúsítvány érvényesítése

Az eszköznek már megkapta a Wi-Fi tanúsítványt. A legegyszerűbb ellenőrzés az, ha megpróbál csatlakozni ahhoz a Wi-Fi kapcsolathoz,&#39;megkapta a tanúsítványt. Nyissa meg a **Gépház** alkalmazást, navigáljon a Hálózati **&amp; internet**  ->  **Wi-Fi-hálózathoz,** és válassza ki a Wi-Fi-kapcsolatot. A csatlakozás után nyissa meg a Microsoft Edge alkalmazást, és ellenőrizze, hogy el tud-e navigálni egy webhelyre.

Annak megerősítéséhez, hogy megkapta a tanúsítványt az eszközön, használja a [Tanúsítványkezelőt.](/hololens/certificate-manager)

## <a name="validate-lob-app-install"></a>LOB-alkalmazás telepítésének ellenőrzése

A felügyelt alkalmazás telepítési folyamatának ellenőrzéséhez ellenőrizze, hogy az alkalmazás telepítve van-e, vagy ellenőrizze a Gépház. Ha egy LOB-alkalmazást kötelező telepítésként konfigurál a csoport számára, a HoloLens-alkalmazásnak a hozzárendelt csoport egyik felhasználójával való regisztrálása után az alkalmazás automatikusan letölti az alkalmazást a HoloLens.

Nyissa meg a Start menü, és válassza a **Minden alkalmazás** lehetőséget. Az alkalmazások számától függően előfordulhat, hogy az  oldal felfelé vagy lefelé **gombjait kell használnia.**

Az alkalmazás eszközre való telepítésének ellenőrzéséhez ezt az **Gépház** Accounts Access work or school (Hozzáférés munkahelyi vagy iskolai fiókokhoz) lapon ellenőrizheti. Válassza ki a fiókot, majd az Info (Információ) gombot, és görgessen lefelé az eszközre alkalmazott különböző konfigurációk és alkalmazások az  ->    ->  MDM-től. 

A telepítés Intune-ból való érvényesítéséhez lépjen a [MEM-portál](https://endpoint.microsoft.com/#home)  ->  **Alkalmazások** -> Minden alkalmazás   -> *ANameOfYourApp eszköz* telepítési  ->  **állapotlapjára.**

További információ: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Dynamics 365-útmutatók ellenőrzése

Az Útmutatók alkalmazás különféle módokon használható a HoloLens, a szerzői és üzemeltetési környezetben. Az útmutatót az üzemeltetés előtt be kell fejeznie.

### <a name="authoring-the-guide"></a>Útmutató írása

Ehhez a gyors ellenőrzéshez nem kell sokat tenni. Egyszerűen válassza ki a számítógépen előkészített útmutatót. A holografikus horgonyok gyors [ellenőrzéshez](/dynamics365/mixed-reality/guides/hololens-app-anchor)a útmutatóhoz kell horgonyt használnia. Ezt követően helyezze el [a lépéseket és modelleket.](/dynamics365/mixed-reality/guides/hololens-app-orientation)

>[!NOTE]
> A szerzői **szerepkörre lesz szüksége** a számítógépen való bejelentkezéshez és a szerzői HoloLens. Az Operátor szerepkör csak olvasható, és nem rendelkezik hozzáféréssel a PC-alkalmazáshoz.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Az útmutató működtetési útmutatója

Ha a hologramok a helyén vannak, tesztelheti az útmutatót. 
- Operátor **mód kiválasztása**
- Kattintson végig az útmutató lépései között.

Az útmutató működtetésével kapcsolatos további részletes útmutatásért tekintse meg az alábbi forrásokat:

[Útmutató üzemeltetése a Dynamics 365-útmutatókban – áttekintés](/dynamics365/mixed-reality/guides/operator-overview)

[A Lépés kártya használata operátorként a Dynamics 365-útmutatókban](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Következő lépés 
> [!div class="nextstepaction"]
> [Vállalati csatlakoztatott üzemelő példány – Karbantartás](hololens2-corp-connected-maintain.md)
