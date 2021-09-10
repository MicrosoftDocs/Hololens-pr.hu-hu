---
title: Üzembe helyezési útmutató – Vállalati csatlakoztatott HoloLens 2 Dynamics 365-útmutatók – Karbantartás
description: A Dynamics 365 HoloLens útmutatók segítségével megtudhatja, hogyan tarthatja fenn HoloLens 2 eszközét egy vállalati csatlakoztatott hálózaton keresztül.
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
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428104"
---
# <a name="maintain---corporate-connected-guide"></a>Karbantartás – Vállalati csatlakoztatott útmutató

## <a name="update-hololens"></a>Frissítés HoloLens

A Microsoft úgy tervezte meg az Windows Update for Businesst, hogy Windows frissítésközpontú felügyeleti képességeket biztosítson a rendszergazdák számára, például lehetővé teszi frissítések telepítését eszközcsoportokon, valamint karbantartási időszakokat határozzon meg a frissítések telepítéséhez.

A frissítések kezelésének egyik népszerű módja a 30 napos funkció-halasztás. Ez lehetővé teszi a rendszergazdák számára az új funkciók frissítését és előzetes megtekintését, így első kézből szereznek ismereteket, és értesítik az ügyfélszolgálatot az új változásokról.

Megtudhatja, hogyan kezelheti [a HoloLens frissítéseit,](/hololens/hololens-updates)beleértve az ütemezett napokat, az ütemezett időt és az aktív órák beállítását az eszközön, hogy a frissítések munkaidőn kívül is frissüljanak.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Dynamics 365-útmutatók (és egyéb áruházbeli alkalmazások) frissítése

A Dynamics 365-útmutatók egy In-Box alkalmazás, amely a Microsoft Store frissíthető. Az alkalmazáson keresztül letöltött Microsoft Store manuálisan is frissíthetők a Microsoft Store [alkalmazáson](/hololens/holographic-store-apps#update-apps) keresztül.

## <a name="how-to-update-lob-apps"></a>LOB-alkalmazások frissítése

Az LOB-alkalmazások ugyanúgy frissíthetők, mint az Intune-ban. Az alkalmazások frissíthetők az Intune-ban, ha az új alkalmazást magasabb verziószámmal tölti fel a meglévő alkalmazáskonfigurációba. Amikor az eszköz szinkronizál az Intune-nal, megfigyeli, hogy az alkalmazás újabb verzióval jelenik meg, és letölti az újabb alkalmazást, és lecseréli a régi alkalmazást.

1. Az újabb alkalmazás feltöltéséhez lépjen a [MEM-portál](https://endpoint.microsoft.com/#home)  ->  **Alkalmazások** -> Minden alkalmazás  ->  *TheNameOfYourApp Tulajdonságai*  ->  **elemre.**
2. Az Alkalmazás adatai mellett válassza a Szerkesztés **lehetőséget.**
3. A Frissíteni kívánt &quot; fájl kiválasztása értéknél &quot; válassza ki a fájlt.
4. Innen a helyi menüben nyissa meg a fájlkezelőt, és töltse fel az LOB-alkalmazás újabb verzióját. Győződjön meg arról, hogy szükség szerint tartalmazza a függőségeket.

További információ: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)

## <a name="development-plan"></a>Fejlesztési terv

Most, hogy sikeresen regisztrálta az eszközt, készen áll arra, hogy további LOB-alkalmazásokat telepítsen az eszközeire. Ebben az útmutatóban egy mintaalkalmazást használunk, de valószínűbb, hogy a szervezet igényeinek megfelelő egyéni alkalmazásokat szeretne használni.

Ha már rendelkezik LOB-alkalmazással, akkor készen áll az alkalmazás [MDM-ben való üzembe helyezésére.](/hololens/app-deploy-intune) Ha más módszert szeretne használni, tekintse át az [HoloLens 2.](/hololens/app-deploy-overview) alkalmazásának üzembe helyezését áttekintő témakört, amelyből megtudhatja, hogyan helyezheti üzembe az LOB-alkalmazást az eszközein.

Ha még nem hoz létre saját LOB-alkalmazást, vagy még létrehozás alatt áll, tekintse [](/windows/mixed-reality/design/design) át a vegyes valóságú fejlesztési dokumentumokban a tervezést és prototípus-készítést, vagy ismerje meg a vegyes valóságú fejlesztés alapvető [fogalmait.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Támogatási csomag

A támogatási csomag kitűnően alkalmas. Hasznos lehet, ha valaki vagy egy csoport betanítja a regisztrációs folyamat hibaelhárítását HoloLens-eszközökön, valamint a HoloLens eszköz általános használatát a szervezeten belül. Annak érdekében, hogy a felhasználók minél gyorsabban megoldják a problémákat, javasoljuk, hogy az eszkalációs folyamatot a következő sorrendhez hasonlóan kell kezelnie:

1. Az Ügyfélszolgálat.
2. A HoloLens szakértő csapata
3. [HoloLens Docs](/hololens/)  /  [HoloLens Docs hibaelhárítása](/hololens/hololens-troubleshooting)
4. [Kapcsolatfelvétel az ügyfélszolgálattal](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Eszközkezelés

Ez az útmutató a Mobile Eszközkezelés (MDM) beállítását, valamint egyes eszközkonfigurációk beállítására és a tanúsítványokkal és proxyként történő hozzáférésre vonatkozó beállítások alkalmazásával Wi-Fi be. Az MDM-et azonban eszközkorlátozások alkalmazására is használhatja CSP-k és szabályzatok segítségével.

Sok esetben az eszközökre kapcsolati korlátozások is vonatkoznak, például Bluetooth, VPN, USB, vagy akár a kamera vagy a mikrofon hozzáférésének kikapcsolása. Ha ezek bármelyike érdekli, javasoljuk, hogy olvassa el az általános [eszközkorlátozási oldalt.](/hololens/hololens-common-device-restrictions)

Egyéb összetettebb eszközkorlátozásokat is használhat. Például:

- Korlátozza a Gépház-alkalmazásban megtekinthető oldalakat a [SettingsPageVisibility](/hololens/settings-uri-list)(Lap láthatósága) használatával, így a felhasználók csak a módosítania szükséges beállításokhoz férhetnek hozzá, például módosíthatják a Wi-Fi kapcsolatukat.
- A [Kioszk mód használatával](/hololens/hololens-kiosk) korlátozhatja az eszköz felhasználói felületét a felhasználók számára. A kioszkokat beállíthatja úgy, hogy egyetlen alkalmazást, vagy több alkalmazást is mutassanak egy egyéni kezdőlapon. A kioszkok különböző élményeket is kínálnak a különböző felhasználók számára.
- [Windows alkalmazásvezérlés (WDAC) használata,](/hololens/windows-defender-application-control-wdac) hogy bizonyos alkalmazások vagy folyamatok ne indulnak el teljesen.

Ha többet szeretne megtudni az eszközkezelés vagy az eszközkorlátozások további módszereiről, olvassa el a következő lépést, és olvassa el Eszközkezelés [áttekintését.](/hololens/hololens-csp-policy-overview)





