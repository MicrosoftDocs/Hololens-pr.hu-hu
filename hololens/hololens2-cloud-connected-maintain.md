---
title: Üzembe helyezési útmutató – HoloLens 2. felhőhöz csatlakoztatott, nagy léptékű üzembe helyezés a Remote Assist segítségével – Karbantartás
description: Maradjon naprakész a felhőhöz csatlakoztatott hálózaton keresztüli hálózati HoloLens karbantartásával és támogatásával kapcsolatos tippjeinket.
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
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427403"
---
# <a name="maintain---cloud-connected-guide"></a>Karbantartás – Felhőhöz csatlakoztatott útmutató

## <a name="updates"></a>Frissítések

A Microsoft úgy tervezte meg az Windows Update for Businesst, hogy Windows frissítésközpontú felügyeleti képességeket biztosítson a rendszergazdák számára, például lehetővé teszi frissítések telepítését eszközcsoportokra, valamint karbantartási időszakokat határozzon meg a frissítések telepítéséhez.

Megtudhatja, hogyan kezelheti [HoloLens frissítéseket,](/hololens/hololens-updates) beleértve az ütemezett napokat, az ütemezett időpontokat és az aktív órák beállítását az eszközön úgy, hogy a frissítések munkaidőn kívül is frissüljanak.

A Remote Assist egy In-Box alkalmazás, amely a Microsoft Store frissítheti. Az alkalmazáson keresztül letöltött Microsoft Store manuálisan is frissíthetők a Microsoft Store [alkalmazáson](/hololens/holographic-store-apps#update-apps) keresztül.

## <a name="support-plan"></a>Támogatási csomag

A támogatási csomag kitűnően alkalmas. Hasznos, ha valaki vagy egy csoport be van tanítva az HoloLens-eszközökön a regisztrációs folyamat hibaelhárítására, valamint a HoloLens eszköz általános használatára. Annak érdekében, hogy a felhasználók minél gyorsabban megoldják a problémákat, javasoljuk, hogy az eszkalációs folyamatot a következő sorrendhez hasonlóan kell kezelnie:

1. Az Ügyfélszolgálat.
2. A HoloLens szakértő csapata
3. [HoloLens Docs](/hololens/)  /  [HoloLens Docs hibaelhárítása](/hololens/hololens-troubleshooting)
4. [Kapcsolatfelvétel az ügyfélszolgálattal](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Fejlesztési terv

Most, hogy sikeresen regisztrálta az eszközét, készen áll az üzletági alkalmazások (LOB-alkalmazások) telepítésére az eszközökön. Ezek a szervezet igényeihez&#39;egyéni alkalmazások.

Ha már rendelkezik üzletági alkalmazással,&#39;készen áll az alkalmazás [MDM-en keresztüli üzembe helyezésére.](/hololens/app-deploy-intune) Ha&#39;módszert szeretne, tekintse át az [HoloLens 2.](/hololens/app-deploy-overview) alkalmazásának üzembe helyezését áttekintő témakört, amelyből megtudhatja, hogyan helyezheti üzembe az LOB-alkalmazást az eszközein.

Ha még nem&#39;saját LOB-alkalmazást, vagy még fejlesztés alatt áll, tekintse át [](/windows/mixed-reality/design/design) a vegyes valóságú fejlesztési dokumentumokban a tervezést és prototípus-készítést, vagy ismerje meg a vegyes valóságú fejlesztés alapvető [fogalmait.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Eszközkezelés 

Bár ez az útmutató a Mobile Eszközkezelés (MDM) beállításával kapcsolatos volt, nem az eszközökre vonatkozó eszközkorlátozások vagy szabályzatok alkalmazásával lett alkalmazva. Az eszközkezelés használható a tanúsítványok lekullával való hozzáféréshez, vagy a hozzáférés korlátozására különböző eszközkorlátozásokkal. 

Az eszközök sok esetben kapcsolati korlátozásokkal( például Bluetooth, VPN, USB, vagy akár a kamerához vagy mikrofonhoz való hozzáférés kikapcsolása is előfordulhat. Ha ezen érdeklődések bármelyike érdekli, javasoljuk, hogy olvassa el az általános [eszközkorlátozási oldalt.](hololens-common-device-restrictions.md)

Egyéb összetettebb eszközkorlátozásokat is használhat. Például:

- Korlátozza a Gépház-alkalmazásban megtekinthető oldalakat a [SettingsPageVisibility](settings-uri-list.md)(Lap láthatósága) használatával, így a felhasználók csak a módosítania szükséges beállításokhoz férhetnek hozzá, például módosíthatják Wi-Fi kapcsolatukat.
- A [Kioszk mód használatával](hololens-kiosk.md) korlátozhatja az eszköz felhasználói felületét a felhasználók számára. A kioszkokat beállíthatja úgy, hogy egyetlen alkalmazást, vagy több alkalmazást is mutassanak egy egyéni kezdőlapon. A kioszkok különböző élményeket is kínálnak a különböző felhasználók számára.  
- [Windows alkalmazásvezérlés (WDAC) használata,](windows-defender-application-control-wdac.md) hogy bizonyos alkalmazások vagy folyamatok ne indulnak el teljesen.

Ha szeretne többet megtudni az eszközkezelés vagy az eszközkorlátozások további módszereiről, akkor a következő lépéssel olvassa el a Eszközkezelés áttekintését.

## <a name="next-step"></a>Következő lépés

> [!div class="nextstepaction"]
> [Olvassa el a CSP-k és Eszközkezelés áttekintését](hololens-csp-policy-overview.md)