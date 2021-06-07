---
title: Üzembe helyezési útmutató – Felhőhöz csatlakoztatott HoloLens 2 üzembe helyezése nagy méretekben a Remote Assist segítségével – Üzembe helyezés
description: Megtudhatja, hogyan ellenőrizheti a regisztrációt és a Remote Assistet HoloLens-eszközökhöz egy felhőhöz csatlakoztatott hálózaton keresztül.
keywords: HoloLens, felügyelet, felhőhöz csatlakoztatott, Remote Assist, AAD, Azure AD, MDM, Mobile Eszközkezelés
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378170"
---
# <a name="deploy---cloud-connected-guide"></a>Üzembe helyezés – Felhőhöz csatlakoztatott útmutató

Most, hogy mindent konfigurált, készen kell állnia az eszközök terjesztésére. Most azonban itt az az alkalom, amikor először ellenőriznie kell a beállítást. Először ellenőrizze az Azure AD-csatlakozást és az MDM-regisztrációt, majd ellenőrizze, hogy elhelyezhető-e Remote Assist-hívás.

## <a name="enrollment-validation"></a>Regisztráció ellenőrzése

Most, hogy minden megfelelően van konfigurálva az Azure AD-hez és az MDM-regisztrációhoz, a többinek egy illesztésnek kell lennie. A&#39;szüksége lesz egy Wi-Fi-kapcsolatra és a HoloLens-eszközre, valamint az egyik korábban konfigurált AAD-felhasználói fiókra.

Ha az eszköz jelenleg&#39;gyári beállítások között található, itt az ideje, hogy újrafésüljük az [eszközt.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Miután az eszköz az OOBE-ban van,&#39;műveleteket kell kezdenie, és követnie kell az utasításokat. 
1. A kritikus kérdés akkor lesz, amikor a rendszer **megkérdezi, hogy ki a HoloLens tulajdona?** Válassza **a Saját munkahelyi vagy iskolai tulajdonban van lehetőséget,** és adja meg Az Azure AD-fiókja hitelesítő adatait.
1. Ha a regisztráció sikeres,&#39;a rendszer kérni fogja a PIN-kód beállítását. Ez a PIN-kód az eszköz egyedi a felhasználó számára. A rendszer az íriszvizsgálatokat, a hangadatokat és a telemetriai beállításokat is kérni fogja, és végül&#39;megtudhatja, hogyan nyithatja meg a Start menüt és OOBE-t.
1. Miután a kezdőlapra Mixed Reality nyissa meg a Start menü az előbb megtanult **Indítás** kézmozdulattal.
1. Válassza a **Beállítások alkalmazást,** majd a **Rendszer lehetőséget.** Az első információ, amelyet&#39;fog látni, az eszköz neve, amely a HoloLens 2-eszközhöz HOLOLENS lesz, amelyet egy hat karakterből álló sztring &quot; &quot; követ.
1. Jegyezze fel ezt a nevet.

![HoloLens 2 beállítások – About (A HoloLens 2 beállításai )](./images/hololens2-settings-about.jpg)

7. A Beállítások alkalmazásban ellenőrizheti, hogy az eszköz sikeresen regisztrálva van-e az Azure AD-ban. A **Beállítások lapon** válassza a Fiókok **Hozzáférés** munkahelyi vagy iskolai  ->  **alkalmazáshoz lehetőséget.** Ezen a képernyőn ellenőrizheti, hogy sikeresen regisztrált-e. Ehhez a Connected to nameofAAD&#39;Azure AD (Csatlakoztatva a következőhöz)&#39;&quot; Azure AD-hez.  Csatlakoztatva _ausername_ @ _nameofAAD_.onmicrosoft.com. &quot;


Annak ellenőrzéséhez, hogy az eszköz rendelkezik-e Azure AD-beléptetve, ellenőriznünk kell a Azure Active Directory a Azure Portal [](https://portal.azure.com/#home)  ->  **Azure Active Directory** Devices All  ->  **devices**  ->  **(Minden** eszköz) eszközről, és rákereshet az eszköz nevére. Látni&#39;, hogy az eszköz a Azure Active Directory.


![Azure Active Directory – Eszköz](./images/aad-enrollment.png)

Ezután&#39;be kell jelentkeznie a [Microsoft Endpoint Manager felügyeleti központjába.](https://endpoint.microsoft.com/#home) Jelentkezzen be, és válassza az **Eszközök,** majd **a Minden eszköz lehetőséget.** Innen megkeresheti a HoloLens-eszköz&#39;nevét. A HoloLens megjelenik az Intune-ban.

![Intune – Eszköz](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Remote Assist hívásérvényesítés

Miután ellenőrizte&#39;hogy az eszköz regisztrálva van-e az AAD-ban és az MDM-&#39;ideje távoli segítő hívást is tesztelni. Az ellenőrzéshez&#39;HoloLens-eszközre és egy Windows 10 PC-re, valamint egy második Azure AD-felhasználói fiókra lesz szüksége a számítógéphez.

Ez az ellenőrzési lépés feltételezi, hogy korábban már befejezte az utolsó érvényesítési lépést, és az eszköz regisztrálva van, és az Azure AD-felhasználó az eszközön van.


1. Ha még nem telepítette a Microsoft Teamst a számítógépén, a Teamst innen [töltheti le.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Jelentkezzen be a Teamsbe a második Azure AD-felhasználói fiókkal, mint amely jelenleg be van jelentkezve a HoloLensbe. Miután bejelentkezett a számítógépére, készen áll a hívás fogadására.
3. Oldja fel a HoloLens zárolását, és jelentkezzen be.
4. A Remote Assist alkalmazás elindításához nyissa meg a **Start menüt,** és válassza a **Remote Assist lehetőséget.** A Remote Assist nem csupán beérkezett üzenetekhez való alkalmazásként van csomagolva, hanem a HoloLens 2&#39;start menüjében is rögzítve van. Ha nem látja&#39;a Start menü, nyissa meg a **Minden alkalmazás,** és keresse meg.
5. A Remote Assist elindulás után az eszköznek az [SSO-n](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) keresztül kell azonosítania a felhasználót, és be kell jelentkeznie az alkalmazásba.
6. Az alkalmazásban válassza a **Keresés lehetőséget,** és keresse meg a második felhasználót a számítógépen. Válassza ki a hívást elindítani kívánt felhasználót.
7. A számítógépről válaszoljon a hívásra.

Gratulálunk,&#39;sikeresen csatlakozott, és a távoli segítő hívása van. Mindenképpen próbálja ki a távoli segédszolgáltatásokat, például a következő funkciókat:

- [Jegyzet inking (Jegyzet inking)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Fájl megosztása és megtekintése vegyes valóságban](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Segítség egy másik HoloLens-alkalmazásban](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Következő lépés

> [!div class="nextstepaction"]
> [Felhőhöz csatlakoztatott üzemelő példány – Karbantartás](hololens2-cloud-connected-maintain.md)