---
title: Telepítési útmutató – Vállalati csatlakoztatott HoloLens 2 Dynamics 365-útmutatók – Karbantartás
description: Megtudhatja, hogyan tarthatja fenn HoloLens 2 eszközét egy vállalati csatlakoztatott hálózaton keresztül a Dynamics 365-útmutatók segítségével.
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
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636996"
---
# <a name="maintain---corporate-connected-guide"></a>Karbantartás – Vállalati csatlakoztatott útmutató

## <a name="update-hololens"></a>Frissítés HoloLens

A Microsoft úgy tervezte meg az Windows Update for Businesst, hogy Windows rendszergazdák számára további frissítésközpontú felügyeleti képességeket biztosítson, például lehetővé teszi frissítések telepítését eszközcsoportokra, valamint karbantartási időszakokat határozzon meg a frissítések telepítéséhez.

A frissítések kezelésének egyik népszerű módja a 30 napos funkció-halasztás. Ez lehetővé teszi a rendszergazdák számára az új funkciók frissítését és előzetes megtekintését, így első kézből szereznek ismereteket, és értesítik az ügyfélszolgálatot az új változásokról.

Megtudhatja, hogyan kezelheti [a HoloLens frissítéseit,](/hololens/hololens-updates)beleértve az ütemezett napokat, az ütemezett időpontokat és az aktív órák beállítását az eszközön, hogy az munkaidőn kívül frissülni tudjon.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Dynamics 365-útmutatók (és egyéb áruházbeli alkalmazások) frissítése

A Dynamics 365-útmutatók egy In-Box alkalmazás, amely a Microsoft Store frissíthető. Az alkalmazáson keresztül letöltött Microsoft Store frissíthetők a Microsoft Store [alkalmazáson](/hololens/holographic-store-apps#update-apps) keresztül.

## <a name="how-to-update-lob-apps"></a>LOB-alkalmazások frissítése

Az LOB-alkalmazások ugyanúgy frissíthetők, mint az Intune-ban. Az alkalmazások frissíthetők az Intune-ban, ha az új alkalmazást magasabb verziószámmal tölti fel a meglévő alkalmazáskonfigurációba. Amikor az eszköz szinkronizál az Intune-nal, megfigyeli, hogy az alkalmazás újabb verzióban jelenik meg, és a rendszer letölti az újabb alkalmazást, és lecseréli a régi alkalmazást.

1. Az újabb alkalmazás feltöltéséhez lépjen a [MEM-portál](https://endpoint.microsoft.com/#home)  ->  **Alkalmazások** -> Minden alkalmazás  ->  *TheNameOfYourApp Tulajdonságai*  ->  **elemre.**
2. Az Alkalmazás adatai mellett válassza a Szerkesztés **lehetőséget.**
3. A Frissíteni kívánt &quot; fájl kiválasztása &quot; értékeként válassza ki a fájlt.
4. Innen a helyi menüben nyissa meg a fájlkezelőt, és töltse fel az LOB alkalmazás újabb verzióját. Győződjön meg arról, hogy szükség szerint tartalmaz függőségeket.

További információ: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)

## <a name="development-plan"></a>Fejlesztési terv

Most, hogy sikeresen regisztrálta az eszközt, készen áll arra, hogy további LOB-alkalmazásokat telepítsen az eszközeire. Ebben az útmutatóban egy mintaalkalmazást használunk, de valószínűbb, hogy a szervezet igényeinek megfelelő egyéni alkalmazásokat szeretne használni.

Ha már rendelkezik LOB-alkalmazással, készen áll az alkalmazás [MDM-ben való üzembe helyezésére.](/hololens/app-deploy-intune) Ha más módszert szeretne használni, tekintse át az [HoloLens 2.](/hololens/app-deploy-overview) év alkalmazástelepítési áttekintését, amelyből megtudhatja, hogyan helyezheti üzembe az LOB-alkalmazást az eszközökön.

Ha még nem hoz létre saját LOB-alkalmazást, vagy még létrehozás alatt áll, tekintse [](/windows/mixed-reality/design/design) át a vegyes valóságú fejlesztési dokumentumokban a tervezést és prototípus-készítést, vagy ismerje meg a vegyes valóságú fejlesztés alapvető [fogalmait.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Támogatási csomag

A támogatási csomag kitűnően alkalmas a helyzetre. Hasznos, ha valaki vagy egy csoport be van tanítva az HoloLens-eszközökön a regisztrációs folyamat hibaelhárítására, valamint a HoloLens-eszköz általános használatára a szervezeten belül. Annak érdekében, hogy a felhasználók minél gyorsabban megoldják a problémáikat, javasoljuk, hogy az eszkalációs folyamatot a következő sorrendhez hasonlóan kell kezelnie:

1. Az ügyfélszolgálat.
2. Az HoloLens szakértő csapata
3. [HoloLens Docs](/hololens/)  /  [HoloLens Docs hibaelhárítása](/hololens/hololens-troubleshooting)
4. [Kapcsolatfelvétel az ügyfélszolgálattal](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Eszközkezelés

Ez az útmutató a Mobile Eszközkezelés (MDM) beállításával, valamint néhány eszközkonfiguráció beállításával és az olyan beállítások alkalmazásával kapcsolatban volt szó, amelyek lehetővé teszik a Wi-Fi tanúsítványok és proxyk hozzáférését. Az MDM-et azonban eszközkorlátozások alkalmazására is használhatja CSP-k és szabályzatok segítségével.

Sok esetben az eszközökre kapcsolati korlátozások vonatkoznak, például Bluetooth, VPN, USB, vagy akár a kamera vagy a mikrofon hozzáférésének kikapcsolása. Ha ezek bármelyike érdekli, javasoljuk, hogy olvassa el az általános [eszközkorlátozási oldalt.](/hololens/hololens-common-device-restrictions)

Más összetettebb eszközkorlátozásokat is használhat. Például:

- Korlátozza a Gépház-alkalmazásban megtekinthető oldalakat a [SettingsPageVisibility](/hololens/settings-uri-list)(Lap láthatósága) használatával, így a felhasználók csak a módosítania szükséges beállításokhoz férhetnek hozzá, például módosíthatják Wi-Fi kapcsolatukat.
- A [Kioszk mód használatával](/hololens/hololens-kiosk) korlátozhatja az eszköz felhasználói felületét. A kioszkokat beállíthatja úgy, hogy egyetlen alkalmazást, vagy több alkalmazást is mutassanak egy egyéni kezdőlapon. A kioszkok különböző felhasználói élményt is kínálnak.
- [Windows alkalmazásvezérlés (WDAC) segítségével bizonyos](/hololens/windows-defender-application-control-wdac) alkalmazásokat vagy folyamatokat nem lehet teljesen elindítani.

Ha többet szeretne megtudni az eszközkezelés vagy az eszközkorlátozások további módszereiről, olvassa el a következő lépést, és olvassa el Eszközkezelés [áttekintését.](/hololens/hololens-csp-policy-overview)





