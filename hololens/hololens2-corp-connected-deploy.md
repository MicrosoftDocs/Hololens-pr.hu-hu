---
title: Üzembe helyezési útmutató – Vállalati csatlakoztatott HoloLens 2 Dynamics 365-útmutatók – Üzembe helyezés
description: A Dynamics 365-útmutatók segítségével megtudhatja, hogyan állíthatja be HoloLens 2 eszköz üzembe helyezését egy vállalati csatlakoztatott hálózaton keresztül.
keywords: HoloLens, felügyelet, céghez csatlakoztatott, Dynamics 365-útmutatók, AAD, Azure AD, MDM, Mobile Eszközkezelés
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
ms.openlocfilehash: f9435ce94986a851bb7744eeea48fa6e411454f5090d7ae11c869ba6f27dc942
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660200"
---
# <a name="deploy---corporate-connected-guide"></a>Üzembe helyezés – Vállalati csatlakoztatott útmutató

Az egyes üzembe helyezések fontos részét képezi annak biztosítása, hogy az üzembe helyezés megfelelően legyen beállítva, mielőtt saját maga teszteli azt, így zökkenőmentes felhasználói élményt biztosít a végfelhasználó számára.

Mivel az Wi-Fi-tanúsítványt MDM-en keresztül telepítjük, először be kell álltatnunk az HoloLens-t, és regisztrálni kell az eszközöket egy nyílt Wi-Fi-hálózaton vagy egy olyan hálózaton, amely nem igényli a tanúsítványt. Miután a HoloLens OOBE és Enrolled befejeződött, az eszköz megkapja a korábban konfigurált hálózati tanúsítványt és LOB-t, és ellenőrizjük, hogy mindkét eszközt megkapta-e az eszköz.

Ezt követően meg tudja erősíteni, hogy a tesztelési útmutatót is meg tudja-e tenni és üzemeltetni tudja.

## <a name="enrollment-validation"></a>Regisztráció ellenőrzése

Most, hogy minden megfelelően van konfigurálva az Azure AD-hez és az MDM-regisztrációhoz, a többinek egy illesztésnek kell lennie. Szüksége lesz egy Wi-Fi kapcsolatra és HoloLens eszközre, valamint egy korábban konfigurált Azure AD felhasználói fiókra.

Ha az eszköz jelenleg nem gyári beállításokat használ, ideje újrafésülni az [eszközt.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Miután az eszköz az OOBE-ban van, el kell kezdenie a műveleteket, és követnie kell az utasításokat.

2. Csatlakozás olyan nyílt hálózati Wi-Fi, amely nem igényel tanúsítványokat a Wi-Fi-hálózathoz való csatlakozáshoz. Ez lehetővé teszi, hogy az eszköz letöltse a tanúsítványt a szervezet Wi-Fi kezdeti beállítás után.

3. A kritikus kérdés akkor lesz, amikor a rendszer **megkérdezi, Who-e a HoloLens?** Válassza **a Saját munkahelyi vagy iskolai tulajdonban van lehetőséget,** és adja meg Az Azure AD-fiókja hitelesítő adatait.

4. Ha a regisztráció sikeres, a rendszer kérni fogja a PIN-kód beállítását. Ez a PIN-kód az eszköz egyedi a felhasználó számára. A rendszer emellett kéri az íriszvizsgálatokat, a hangadatokat és a telemetriai beállításokat, és végül megtanulhatja, hogyan nyithatja meg a Start menüt, és hogyan ooBE-t is befejeztet.

5. Miután a kezdőlapra Mixed Reality, nyissa meg a Start menü az  előbb megtanult Indítás kézmozdulattal.

6. Válassza ki **a Gépház** alkalmazást, majd válassza a **Rendszer lehetőséget.** Az első információ, amit látni fog, az eszköz neve, amely a HoloLens 2-es eszközhöz a HOLOLENS lesz, amelyet hat karakterből álló sztring &quot; &quot; követ.

7. Jegyezze fel ezt a nevet.

    ![HoloLens 2 Gépház képernyő](./images/hololens2-settings-about.jpg)

8. Ellenőrizze, hogy az eszköz sikeresen csatlakozott-e az Azure AD-hez. Kétféleképpen lehet:

    1.  Az Gépház alkalmazás. A **Gépház** **fiókok**  ->  **hozzáférése munkahelyi vagy iskolai fiókhoz lehetőséget.** Ezen a képernyőn ellenőrizheti, hogy sikeresen regisztrált-e. Ehhez a Connected to nameofAAD&#39;Azure AD (Csatlakoztatott a következőhöz) Azure &quot; AD-&#39;jelenik meg. Csatlakoztatva a *yourusername@nameofAAD.onmicrosoft.com* következővel: . Ez ellenőrzi, hogy az eszköz csatlakozik-e a&#39;Azure AD-hez.

    1. A [következő Azure Portal:](https://portal.azure.com/#home). Keresse meg **Azure Active Directory**  ->  **Eszközök**  ->  **Minden eszköz adatokat,** és keressen rá az eszköz nevére. Az Összekapcsolás típusa alatt az "Azure AD Joined" (Azure AD-hez csatlakozva) szöveg fog ni.
        ![Csatlakozás típusának ellenőrzése az Azure AD-ban](./images/hololens2-devices-all-devices.png)

9. Ellenőrizze, hogy az eszköz regisztrálva van-e az MDM-be. Kétféleképpen lehet:

    1. A Gépház válassza **a** **Fiókok Hozzáférés** munkahelyi vagy iskolai  ->  **alkalmazáshoz lehetőséget.** Ezen a képernyőn ellenőrizheti, hogy sikeresen regisztrált-e. Ehhez a Connected to nameofAAD&#39;Azure AD (Csatlakoztatott a következőhöz) Azure &quot; AD-&#39;jelenik meg. Csatlakoztatva a *yourusername@nameofAAD.onmicrosoft.com* következővel: . Ebben a Hozzáférés munkahelyi vagy iskolai fiókban válassza a Connected to nameofAAD&#39;Azure AD (Csatlakoztatva a névhez)&#39;&quot; Azure AD-hez. Csatlakoztatva a yourusername@nameofAAD.onmicrosoft.com &quot; következővel: , és válassza az **Információ** gombot.

    1. [Microsoft Endpoint Manager Felügyeleti központ .](https://endpoint.microsoft.com/#home) Jelentkezzen be, és válassza az **Eszközök,** majd **a Minden eszköz lehetőséget.** Itt kereshet a saját eszközén HoloLens a&#39;nevét. Az Intune-ban a HoloLens kell lennie.

        ![Az Intune által az Azure AD-ban való felügyelet ellenőrzése](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi ellenőrzése

Az eszköznek most már megkapta a Wi-Fi tanúsítványt. A legegyszerűbb ellenőrzés az, ha megpróbál csatlakozni ahhoz Wi-Fi kapcsolathoz, amelyhez&#39;megkapta a tanúsítványt. Nyissa meg a **Gépház** alkalmazást, lépjen a Hálózati **&amp; internet**  ->  **Wi-Fi lapra,** és válassza ki a Wi-Fi-kapcsolatot. A csatlakozás után nyissa meg a Microsoft Edge alkalmazást, és ellenőrizze, hogy el tud-e navigálni egy webhelyre.

Annak megerősítéséhez, hogy megkapta a tanúsítványt az eszközön, használhatja a [Tanúsítványkezelőt.](/hololens/certificate-manager)

## <a name="validate-lob-app-install"></a>LOB-alkalmazás telepítésének ellenőrzése

A felügyelt alkalmazás telepítési folyamatának ellenőrzéséhez ellenőrizze, hogy telepítve van-e az alkalmazás, vagy Gépház. Ha egy LOB-alkalmazást kötelező telepítésként konfigurál a csoport számára, a HoloLens-alkalmazásnak a hozzárendelt csoport egyik felhasználójával való regisztrálása után az alkalmazás automatikusan letölti az alkalmazást a HoloLens.

Nyissa meg a Start menü, és válassza a **Minden alkalmazás.** A telepített alkalmazások számától függően előfordulhat, hogy  az oldal felfelé vagy lefelé **gombjait kell használnia.**

Az alkalmazás eszközre való telepítésének ellenőrzéséhez ezt az **Gépház** Accounts Access munkahelyi vagy iskolai fiókon keresztül tudja megtenni. Válassza ki a fiókot, majd az Információ gombot, és görgessen le az eszközre az  ->    ->  MDM-től  alkalmazott különböző konfigurációk és alkalmazások eléréséhez.

Az Intune-ból való telepítés ellenőrzéséhez lépjen a [MEM-portál](https://endpoint.microsoft.com/#home)  ->  **Alkalmazások** -> Minden alkalmazás   -> *TheNameOfYourApp*  ->  **eszköztelepítési állapotlapjára.**

További információ: [Intune app deployment for HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Dynamics 365-útmutatók ellenőrzése

Az Útmutatók alkalmazásnak vannak módjai a HoloLens, a szerzői és üzemeltetési környezetben. Az útmutatót az üzemeltetés előtt be kell fejeznie.

### <a name="authoring-the-guide"></a>Az útmutató szerzői

Ehhez a gyors ellenőrzéshez nem kell sokat tenni. Egyszerűen válassza ki a számítógépen előkészített útmutatót. A rövid ellenőrzéshez a holografikus horgonyt kell használnia az útmutatóban. [](/dynamics365/mixed-reality/guides/hololens-app-anchor) Ezt követően helyezze el [a lépéseket és a modelleket.](/dynamics365/mixed-reality/guides/hololens-app-orientation)

>[!NOTE]
> A számítógépen **való bejelentkezéshez és a** szerzői szerepkörhöz a HoloLens. Az Operátor szerepkör csak olvasható, és nincs hozzáférése a PC-alkalmazáshoz.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Az útmutató működtetési útmutatója

Ha a hologramok a helyén vannak, tesztelheti az útmutatót. 
- Operátor **mód kiválasztása**
- Kattintson végig az útmutató lépései között.

Az útmutató működtetésével kapcsolatos részletes útmutatásért tekintse meg az alábbi forrásokat:

[Útmutató üzemeltetése a Dynamics 365-útmutatókban – áttekintés](/dynamics365/mixed-reality/guides/operator-overview)

[A Lépés kártya használata operátorként a Dynamics 365-útmutatókban](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Következő lépés 
> [!div class="nextstepaction"]
> [Vállalati csatlakoztatott üzemelő példány – Karbantartás](hololens2-corp-connected-maintain.md)
