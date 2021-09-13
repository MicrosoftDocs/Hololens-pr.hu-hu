---
title: Telepítési útmutató – Felhőhöz csatlakoztatott HoloLens 2. példány nagy léptékű üzembe helyezése a Remote Assist segítségével – Üzembe helyezés
description: Megtudhatja, hogyan ellenőrizheti a regisztrációt és a Remote Assist eszközt HoloLens egy felhőhöz csatlakoztatott hálózaton keresztül.
keywords: HoloLens, felügyelet, felhőhöz csatlakoztatott, Remote Assist, AAD, Azure AD, MDM, mobile Eszközkezelés
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
ms.openlocfilehash: 519770badab9f260316fe4cfff4bf453a7c971a7
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032740"
---
# <a name="deploy---cloud-connected-guide"></a>Üzembe helyezés – Felhőhöz csatlakoztatott útmutató

Most, hogy mindent konfigurált, készen kell állnia az eszközök terjesztésére. Most azonban itt az az alkalom, amikor először ellenőriznie kell a beállítást. Először ellenőrizni kell az Azure AD-csatlakozás és az MDM-regisztráció folyamatát, majd ellenőrizni kell, hogy el lehet-e helyezni egy Remote Assist-hívást.

## <a name="enrollment-validation"></a>Regisztráció ellenőrzése

Most, hogy minden megfelelően van konfigurálva az Azure AD-hez és az MDM-regisztrációhoz, a többinek egy illesztésnek kell lennie. Szüksége&#39;kapcsolatra és Wi-Fi a HoloLens-eszközre, valamint az egyik korábban konfigurált AAD-felhasználói fiókra.

Ha az eszköz jelenleg&#39;gyári beállításokban található, ideje [újrafésülni](/hololens/hololens-recovery#clean-reflash-the-device)az eszközt.

1. Miután az eszköz az OOBE-ban van,&#39;kell kezdenie a műveleteket, és követnie kell az utasításokat. 
1. A kritikus kérdés akkor lesz, amikor a rendszer **megkérdezi, hogy Who-e ennek a HoloLens?** Válassza **a Saját munkahelyi vagy iskolai tulajdonban van lehetőséget,** és adja meg Az Azure AD-fiókja hitelesítő adatait.
1. Ha a regisztráció sikeres,&#39;a rendszer a PIN-kód beállítását fogja kérni. Ez a PIN-kód a felhasználó egyedi eszköze. Emellett meg kell adnia az Íriszvizsgálatokat, a hangadatokat és a telemetriai beállításokat, végül pedig&#39;a Start menü megnyitását és az OOBE befejezését.
1. Miután a Kezdőlapra Mixed Reality nyissa meg a Start menü az előbb megtanult **Indítás** kézmozdulattal.
1. Válassza ki **a Gépház** alkalmazást, majd válassza a **Rendszer lehetőséget.** Az első információ, amelyet&#39;fog látni, az eszköz neve, amely a HoloLens 2-es eszközhöz a HOLOLENS lesz, amelyet egy hat karakterből álló sztring &quot; &quot; követ.
1. Jegyezze fel ezt a nevet.

![HoloLens 2 Gépház – Körülbelül.](./images/hololens2-settings-about.jpg)

7. Az eszköz Azure AD-beli sikeres regisztrációját a Gépház ellenőrizheti. A **Gépház** fiókok   ->  **hozzáférése munkahelyi vagy iskolai fiókhoz lehetőséget.** Ezen a képernyőn ellenőrizheti, hogy sikeresen regisztrált-e. Ehhez a Connected &quot; to _nameofAAD_&#39;Azure AD (Csatlakoztatva az Azure AD-hez)&#39;megjelenik. Csatlakoztatva _a következővel: yourusername_ @ _nameofAAD_.onmicrosoft.com. &quot;


Annak ellenőrzéséhez, hogy az eszköz rendelkezik-e Azure AD-beléptetve, ellenőriznünk kell a Azure Active Directory Azure Portal [](https://portal.azure.com/#home)Azure Active Directory Devices All devices (Minden eszköz) Azure Active Directory, és rákeresünk az eszköz  ->    ->    ->  nevére. Láthatja&#39;hogy az eszköz a Azure Active Directory.


![Azure Active Directory – Eszköz.](./images/aad-enrollment.png)

Ezután&#39;be kell jelentkeznie a felügyeleti [Microsoft Endpoint Manager központba.](https://endpoint.microsoft.com/#home) Jelentkezzen be, és válassza az **Eszközök,** majd **a Minden eszköz lehetőséget.** Itt megkeresheti a HoloLens eszköz&#39;nevét. Az Intune-ban a HoloLens kell lennie.

![Intune – Eszköz.](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Remote Assist hívásérvényesítése

Miután ellenőrizte&#39;hogy az eszköz regisztrálva van-e az AAD-ban és az MDM-&#39;, el kell&#39;egy Remote Assist-teszthívást. Az ellenőrzéshez&#39;szüksége lesz az HoloLens-eszközre és egy Windows 10-számítógépre, valamint egy második Azure AD-felhasználói fiókra a számítógépen.

Ez az ellenőrzési lépés feltételezi, hogy korábban már befejezte az utolsó érvényesítési lépést, és az eszköz regisztrálva van, és az Azure AD-felhasználó az eszközön van.


1. Ha még nincs telepítve Microsoft Teams a számítógépen, itt Teams [letöltheti.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Jelentkezzen be Teams a második Azure AD-beli felhasználói fiókkal, mint ami jelenleg be van jelentkezve a HoloLens. Miután bejelentkezett a számítógépére, készen áll a hívás fogadására.
3. Oldja fel a HoloLens és jelentkezzen be.
4. A Remote Assist alkalmazás elindításához nyissa meg a **Start menüt,** és válassza a **Remote Assist lehetőséget.** A Remote Assist nem csupán beérkezett üzenetekhez való alkalmazásként van csomagolva, hanem a HoloLens 2&#39;start menüben is rögzítve van. Ha nem látja&#39;a Start menü, nyissa meg a Minden alkalmazás **listát,** és keresse meg.
5. A Remote Assist elindulás után azonosítania kell az eszköz felhasználóját az [SSO-n keresztül,](/azure/active-directory/manage-apps/what-is-single-sign-on) és be kell jelentkeznie az alkalmazásba.
6. Az alkalmazáson belül válassza a **Keresés lehetőséget,** és keresse meg a második felhasználót a számítógépen. Válassza ki a hívást elindítani kívánt felhasználót.
7. A számítógépről válaszoljon a hívásra.

Gratulálunk,&#39;sikeresen csatlakozott, és a távoli segítő hívása van. Győződjön meg arról, hogy kipróbál bizonyos távoli segédszolgáltatásokat, például a következőt:

- [Jegyzet inking (Jegyzet inking)](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Fájl megosztása és megtekintés vegyes valóságban](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Segítség egy másik HoloLens alkalmazásban](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Következő lépés

> [!div class="nextstepaction"]
> [Felhőhöz csatlakoztatott üzemelő példány – Karbantartás](hololens2-cloud-connected-maintain.md)