---
title: Telepítési útmutató – Felhőhöz csatlakoztatott HoloLens 2. példány nagy léptékű üzembe helyezése a Remote Assist segítségével – Üzembe helyezés
description: Megtudhatja, hogyan ellenőrizheti a regisztrációt és a Remote Assist eszközt HoloLens egy felhőhöz csatlakoztatott hálózaton keresztül.
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
ms.openlocfilehash: b0597806d58d7bf16fe6f6c766af3f9662fca7e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635177"
---
# <a name="deploy---cloud-connected-guide"></a>Üzembe helyezés – Felhőhöz csatlakoztatott útmutató

Most, hogy mindent konfigurált, készen kell állnia az eszközök terjesztésére. Most azonban itt az az alkalom, amikor először ellenőriznie kell a beállítást. Először ellenőrizni kell az Azure AD-csatlakozás és az MDM-regisztráció folyamatát, majd ellenőrizni kell, hogy el lehet-e helyezni egy Remote Assist-hívást.

## <a name="enrollment-validation"></a>Regisztráció ellenőrzése

Most, hogy minden megfelelően van konfigurálva az Azure AD-hez és az MDM-regisztrációhoz, a többinek egy illesztésnek kell lennie. Szüksége&#39;kapcsolatra és Wi-Fi a HoloLens eszközre, valamint az egyik korábban konfigurált AAD-felhasználói fiókra.

Ha az eszköz jelenleg&#39;gyári beállításokban található, ideje [újrafésülni](/hololens/hololens-recovery#clean-reflash-the-device)az eszközt.

1. Miután az eszköz az OOBE-ban van,&#39;műveleteket kell kezdenie, és követnie kell az utasításokat. 
1. A kritikus kérdés akkor lesz, amikor a rendszer **megkérdezi, hogy Who-e a HoloLens?** Válassza **a Saját munkahelyi vagy iskolai tulajdonban van lehetőséget,** és adja meg Az Azure AD-fiókja hitelesítő adatait.
1. Ha a regisztráció sikeres,&#39;a rendszer pin-kód beállítását kéri. Ez a PIN-kód a felhasználó egyedi eszköze. Emellett meg kell adnia az Íriszvizsgálatokat, a hangadatokat és a telemetriai beállításokat, végül pedig&#39;, hogyan nyithatja meg a Start menüt, és hogyan fejezhatja be az OOBE-t.
1. Miután a Kezdőlapra Mixed Reality nyissa meg a Start menü az előbb megtanult **Indítás** kézmozdulattal.
1. Válassza ki a **Gépház** alkalmazást, majd válassza a **Rendszer lehetőséget.** Az első információ,&#39;az Eszköz neve, amely a HoloLens 2-es eszközhöz HOLOLENS lesz, amelyet hat karakterből álló sztring &quot; &quot; követ.
1. Jegyezze fel ezt a nevet.

![HoloLens 2. Gépház – About](./images/hololens2-settings-about.jpg)

7. Az eszköz Azure AD-beli sikeres regisztrációját a Gépház ellenőrizheti. A **Gépház** **fiókok**  ->  **hozzáférése munkahelyi vagy iskolai fiókhoz lehetőséget.** Ezen a képernyőn ellenőrizheti, hogy sikeresen regisztrált-e. Ehhez a Connected to nameofAAD&#39;Azure AD (Csatlakoztatva a következőhöz)&#39;&quot; Azure AD-hez.  Csatlakoztatva _a következővel: yourusername_ @ _nameofAAD_.onmicrosoft.com. &quot;


Annak ellenőrzéséhez, hogy az eszköz rendelkezik-e Azure AD-beléptetve, Azure Active Directory a Azure Portal [](https://portal.azure.com/#home)  ->  **Azure Active Directory** Devices All  ->  **devices**  ->  **(Minden** eszköz) Azure Portal, és rákereshet az eszköz nevére. Látni&#39;, hogy az eszköz a Azure Active Directory.


![Azure Active Directory – Eszköz](./images/aad-enrollment.png)

Ezután&#39;be kell jelentkeznie a felügyeleti [Microsoft Endpoint Manager központba.](https://endpoint.microsoft.com/#home) Jelentkezzen be, és válassza az **Eszközök,** majd **a Minden eszköz lehetőséget.** Innen megkeresheti a HoloLens eszközén&#39;nevét. Az Intune-ban a HoloLens kell lennie.

![Intune – Eszköz](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Remote Assist hívásérvényesítése

Miután ellenőrizte&#39;hogy az eszköz regisztrálva van-e az AAD-ban és az MDM-&#39;, el kell&#39;egy Remote Assist teszthívást. Az ellenőrzéshez&#39;szüksége lesz az HoloLens-eszközre és egy Windows 10 PC-re, valamint egy második Azure AD felhasználói fiókra a számítógépen.

Ez az ellenőrzési lépés feltételezi, hogy korábban már befejezte az utolsó érvényesítési lépést, és az eszköz regisztrálva van, és az Azure AD-felhasználó az eszközön van.


1. Ha még nincs telepítve Microsoft Teams számítógépen, itt [töltheti le Teams alkalmazást.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Jelentkezzen be Teams a második Azure AD-felhasználói fiókkal, mint az aktuálisan a HoloLens. Miután bejelentkezett a számítógépére, készen áll a hívás fogadására.
3. Oldja fel a HoloLens és jelentkezzen be.
4. A Remote Assist alkalmazás elindításához nyissa meg a **Start menüt,** és válassza a **Remote Assist lehetőséget.** A Remote Assist nem csak beérkezett üzenetekhez való alkalmazásként van csomagolva, hanem a HoloLens 2&#39;start menüben is rögzítve van. Ha nem látja&#39;a Start menü, nyissa meg a Minden alkalmazás **listában.**
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