---
title: Üzembe helyezési útmutató – HoloLens 2. felhőhöz csatlakoztatott, nagy léptékű üzembe helyezés a Remote Assist segítségével – Karbantartás
description: Naprakész maradhat a felhőhöz csatlakoztatott hálózaton keresztüli HoloLens karbantartásával és támogatásával kapcsolatos tippjeinket.
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
ms.openlocfilehash: 879f89d84bbae5b4cc187bc8b1fca627036269145b1c2dd82787e3789fef259d
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660375"
---
# <a name="maintain---cloud-connected-guide"></a>Karbantartás – Felhőhöz csatlakoztatott útmutató

## <a name="updates"></a>Frissítések

A Microsoft úgy tervezte meg az Windows Update for Businesst, hogy Windows rendszergazdák számára további frissítésközpontú felügyeleti képességeket biztosítson, például lehetővé teszi frissítések telepítését eszközcsoportokra, valamint karbantartási időszakokat határozzon meg a frissítések telepítéséhez.

Megtudhatja, hogyan kezelheti [a HoloLens frissítéseket,](/hololens/hololens-updates) beleértve az ütemezett napokat, az ütemezett időpontokat és az aktív órák beállítását az eszközön, hogy az munkaidőn kívül frissülni tudjon.

A Remote Assist egy In-Box alkalmazás, amely a Microsoft Store frissítheti. Az alkalmazáson keresztül letöltött Microsoft Store az alkalmazáson [](/hololens/holographic-store-apps#update-apps) keresztül Microsoft Store manuálisan.

## <a name="support-plan"></a>Támogatási csomag

A támogatási csomag kitűnően alkalmas a helyzetre. Hasznos, ha valaki vagy egy csoport be van tanítva a regisztrációs folyamat hibaelhárítására HoloLens-eszközökön, valamint a HoloLens-eszköz általános használatára. Annak érdekében, hogy a felhasználók minél gyorsabban megoldják a problémáikat, javasoljuk, hogy az eszkalációs folyamatot a következő sorrendhez hasonlóan kell kezelnie:

1. Az ügyfélszolgálat.
2. Az HoloLens szakértő csapata
3. [HoloLens Docs](/hololens/)  /  [HoloLens Docs hibaelhárítása](/hololens/hololens-troubleshooting)
4. [Kapcsolatfelvétel az ügyfélszolgálattal](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Fejlesztési terv

Az eszköz sikeres regisztrációja után készen áll az üzletági alkalmazások (LOB-alkalmazások) telepítésére az eszközökön. Ezek a szervezet igényeihez&#39;egyéni alkalmazások.

Ha már rendelkezik üzletági alkalmazással, készen&#39;az alkalmazás [MDM-en keresztüli üzembe helyezésére.](/hololens/app-deploy-intune) Ha&#39;módszert szeretne használni, tekintse át az [HoloLens 2.](/hololens/app-deploy-overview) alkalmazásának üzembe helyezését áttekintő témakört, amelyből megtudhatja, hogyan helyezheti üzembe az LOB-alkalmazást az eszközein.

Ha még nem&#39;saját LOB-alkalmazást, vagy még létrehozás alatt áll, tekintse át a [](/windows/mixed-reality/design/design) vegyes valóságú fejlesztési dokumentumokban a tervezést és a prototípus-készítést, vagy ismerje meg az alapvető fogalmakat a vegyes valóságú fejlesztés elkezdéséhez. [](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Eszközkezelés 

Bár ez az útmutató a Mobile Eszközkezelés (MDM) beállítását is érintette, nem az eszközökre vonatkozó eszközkorlátozások vagy szabályzatok alkalmazása volt alkalmazva. Az eszközkezelés lehetővé teszi a hozzáférést a tanúsítványok lekullával vagy a hozzáférés korlátozásával, különböző eszközkorlátozásokkal. 

Sok esetben az eszközökre kapcsolati korlátozások vonatkoznak, például Bluetooth, VPN, USB, vagy akár a kamera vagy a mikrofon hozzáférésének kikapcsolása. Ha ezek bármelyike érdekli, javasoljuk, hogy olvassa el az általános [eszközkorlátozási oldalt.](hololens-common-device-restrictions.md)

Más összetettebb eszközkorlátozásokat is használhat. Például:

- Korlátozza a Gépház-alkalmazásban megtekinthető oldalakat a [SettingsPageVisibility](settings-uri-list.md)(Lap láthatósága) használatával, így a felhasználók csak a módosítania szükséges beállításokhoz férhetnek hozzá, például módosíthatják Wi-Fi kapcsolatukat.
- A [Kioszk mód használatával](hololens-kiosk.md) korlátozhatja az eszköz felhasználói felületét. A kioszkokat beállíthatja úgy, hogy egyetlen alkalmazást, vagy több alkalmazást is mutassanak egy egyéni kezdőlapon. A kioszkok különböző felhasználói élményt is kínálnak.  
- [Windows alkalmazásvezérlés (WDAC) segítségével bizonyos](windows-defender-application-control-wdac.md) alkalmazásokat vagy folyamatokat nem lehet teljesen elindítani.

Ha többet szeretne megtudni az eszközkezelés vagy az eszközkorlátozások különböző módszereiről, olvassa el a következő lépést, és olvassa el Eszközkezelés áttekintését.

## <a name="next-step"></a>Következő lépés

> [!div class="nextstepaction"]
> [Olvassa el a CSP-k és Eszközkezelés áttekintését](hololens-csp-policy-overview.md)