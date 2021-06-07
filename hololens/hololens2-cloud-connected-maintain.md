---
title: Üzembe helyezési útmutató – Felhőhöz csatlakoztatott HoloLens 2 üzembe helyezése nagy méretekben a Remote Assist segítségével – Karbantartás
description: Naprakész maradhat a HoloLens-eszközök felhőhöz csatlakoztatott hálózaton keresztüli karbantartására és támogatására vonatkozó tippjeinket.
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378168"
---
# <a name="maintain---cloud-connected-guide"></a>Karbantartás – Felhőhöz csatlakoztatott útmutató

## <a name="updates"></a>Frissítések

A Microsoft Windows Update Vállalatoknak, hogy további Windows Update-központú felügyeleti képességeket biztosítson a rendszergazdák számára, például lehetővé teszi frissítések telepítését eszközcsoportokra, valamint karbantartási időszakokat határozzon meg a frissítések telepítéséhez.

Ismerje meg, hogyan kezelheti [a HoloLens-frissítéseket,](https://docs.microsoft.com/hololens/hololens-updates) beleértve az ütemezett napokat, az ütemezett időpontokat és az aktív órák beállítását az eszközön úgy, hogy munkaidőn kívül frissüljenek.

A Remote Assist egy In-Box alkalmazás, amely a Microsoft Store frissítheti. Az alkalmazáson keresztül letöltött Microsoft Store az alkalmazáson [](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) keresztül Microsoft Store manuálisan.

## <a name="support-plan"></a>Támogatási csomag

A támogatási csomag kitűnően alkalmas a helyzetre. Hasznos, ha be kell tanítani valakit vagy egy csoportot a HoloLens-eszközök regisztrációs folyamatának hibaelhárítására, valamint a HoloLens-eszköz általános használatára a szervezeten belül. Annak érdekében, hogy a felhasználók minél gyorsabban megoldják a problémáikat, javasoljuk, hogy az eszkalációs folyamatot a következő sorrendhez hasonlóan kell kezelnie:

1. A támogatási szolgálat.
2. HoloLens-szakértő csapata
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [HoloLens – Hibaelhárítási dokumentumok](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Kapcsolatfelvétel az ügyfélszolgálattal](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Fejlesztési terv

Az eszköz sikeres regisztrálása után készen áll az üzletági alkalmazások (LOB-alkalmazások) telepítésére az eszközökön. Ezek a szervezet igényeihez&#39;egyéni alkalmazások.

Ha már rendelkezik üzletági alkalmazással, készen&#39;az alkalmazás [MDM-alkalmazással való üzembe helyezésére.](https://docs.microsoft.com/hololens/app-deploy-intune) Ha szeretné&#39;módszert, tekintse át a [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) alkalmazástelepítési áttekintését, amelyből megtudhatja, hogyan helyezheti üzembe LOB-alkalmazását az eszközein.

Ha még nem&#39;saját LOB-alkalmazást, vagy még létrehozás alatt áll, tekintse át a [](https://docs.microsoft.com/windows/mixed-reality/design/design) vegyes valóságú fejlesztési dokumentumokban a tervezést és a prototípus-készítést, vagy ismerje meg az alapvető fogalmakat a vegyes valóságú fejlesztés elkezdéséhez. [](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Eszközkezelés 

Bár ez az útmutató a Mobile Eszközkezelés (MDM) beállítását is érintette, nem az eszközökre vonatkozó eszközkorlátozások vagy szabályzatok alkalmazása volt alkalmazva. Az eszközkezelés lehetővé teszi a hozzáférést a tanúsítványok lekullával, vagy korlátozhatja a hozzáférést különböző eszközkorlátozásokkal. 

Az eszközök sok esetben kapcsolati korlátozásokkal ( például Bluetooth, VPN, USB) vagy akár a kamera vagy a mikrofon hozzáférésének kikapcsolása is előfordulhatnak. Ha ezek bármelyike érdekli, javasoljuk, hogy olvassa el az általános [eszközkorlátozási oldalt.](hololens-common-device-restrictions.md)

Más összetettebb eszközkorlátozásokat is használhat. Például:

- A BeállításokLap láthatósága beállítással korlátozhatja a [](settings-uri-list.md)Beállítások alkalmazásban megtekinthető oldalakat, így a felhasználók csak a módosítania szükséges beállításokhoz férhetnek hozzá, például módosíthatják Wi-Fi kapcsolatukat.
- A [Kioszk mód használatával](hololens-kiosk.md) korlátozhatja az eszköz felhasználói felületét. A kioszkokat beállíthatja úgy, hogy egyetlen alkalmazást, vagy több alkalmazást is mutassanak egy egyéni kezdőlapon. A kioszkok különböző felhasználói élményt is kínálnak.  
- [A Windows alkalmazásvezérlés (WDAC)](windows-defender-application-control-wdac.md) segítségével bizonyos alkalmazások vagy folyamatok nem indulnak el teljesen.

Ha többet szeretne megtudni az eszközkezelés vagy az eszközkorlátozások különböző módszereiről, olvassa el a következő lépést, és olvassa el Eszközkezelés áttekintését.

## <a name="next-step"></a>Következő lépés

> [!div class="nextstepaction"]
> [Olvassa el a CSP-k és Eszközkezelés áttekintését](hololens-csp-policy-overview.md)