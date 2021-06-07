---
title: Üzembe helyezési útmutató – Céghez csatlakoztatott HoloLens 2 Dynamics 365-útmutatók – Karbantartás
description: Útmutató a HoloLens 2-eszközök vállalati csatlakoztatott hálózaton keresztüli fenntartásához Dynamics 365-útmutatók segítségével.
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
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378108"
---
# <a name="maintain---corporate-connected-guide"></a>Karbantartás – Vállalati csatlakoztatott útmutató

## <a name="update-hololens"></a>A HoloLens frissítése

A Microsoft Windows Update Vállalatoknak, hogy további Windows Update-központú felügyeleti képességeket biztosítson a rendszergazdáknak, például lehetővé teszi frissítések telepítését eszközcsoportokra, valamint karbantartási időszakokat határozzon meg a frissítések telepítéséhez.

A frissítések kezelésének egyik népszerű módja a 30 napos funkció-halasztás. Ez lehetővé teszi a rendszergazdák számára az új funkciók frissítését és előzetes megtekintését, így első kézből szereznek ismereteket, és értesítik az ügyfélszolgálatot az új változásokról.

Megtudhatja, hogyan kezelheti a [HoloLens-frissítéseket,](https://docs.microsoft.com/hololens/hololens-updates)beleértve az ütemezett napokat, az ütemezett időt és az aktív órák beállítását az eszközön, hogy munkaidőn kívül frissüljenek.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Dynamics 365-útmutatók (és egyéb áruházbeli alkalmazások) frissítése

A Dynamics 365-útmutatók egy In-Box alkalmazás, amely a Microsoft Store frissíthető. Az alkalmazáson keresztül letöltött Microsoft Store frissíthetők a Microsoft Store [alkalmazáson](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) keresztül.

## <a name="how-to-update-lob-apps"></a>LOB-alkalmazások frissítése

Az LOB-alkalmazások ugyanúgy frissíthetők, mint az Intune-ban. Az alkalmazások frissíthetők az Intune-ban, ha az új alkalmazást magasabb verziószámmal tölti fel a meglévő alkalmazáskonfigurációba. Amikor az eszköz szinkronizál az Intune-nal, megfigyeli, hogy az alkalmazás újabb verziójú, és a rendszer letölti az újabb alkalmazást, és lecseréli a régi alkalmazást.

1. Az újabb alkalmazás feltöltéséhez lépjen a [MEM-portál](https://endpoint.microsoft.com/#home)  ->  **Alkalmazások** -> Minden alkalmazás  ->  *TheNameOfYourApp Tulajdonságai*  ->  **elemre.**
2. Az Alkalmazás adatai mellett válassza a Szerkesztés **lehetőséget.**
3. A Frissíteni kívánt &quot; fájl kiválasztása értéknél &quot; válassza ki a fájlt.
4. Innen a helyi menüben nyissa meg a fájlkezelőt, és töltse fel az LOB-alkalmazás újabb verzióját. Győződjön meg arról, hogy szükség szerint tartalmazza a függőségeket.

További információ: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="development-plan"></a>Fejlesztési terv

Most, hogy sikeresen regisztrálta az eszközt, készen áll arra, hogy további LOB-alkalmazásokat telepítsen az eszközeire. Ebben az útmutatóban egy mintaalkalmazást használunk, de valószínűbb, hogy a szervezet igényeinek megfelelő egyéni alkalmazásokat szeretne használni.

Ha már rendelkezik LOB-alkalmazással, készen áll az alkalmazás [MDM-ben való üzembe helyezésére.](https://docs.microsoft.com/hololens/app-deploy-intune) Ha más módszert szeretne használni, tekintse át a [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) alkalmazástelepítési áttekintését, amelyből megtudhatja, hogyan helyezheti üzembe LOB-alkalmazását az eszközein.

Ha még nem hoz létre saját LOB-alkalmazást, vagy még létrehozás alatt áll, tekintse [](https://docs.microsoft.com/windows/mixed-reality/design/design) át a vegyes valóságú fejlesztési dokumentumokban a tervezést és prototípus-készítést, vagy ismerje meg a vegyes valóságú fejlesztés alapvető [fogalmait.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Támogatási csomag

A támogatási csomag kitűnően alkalmas. Hasznos lehet, ha valaki vagy egy csoport betanítja a HoloLens-eszközökön a regisztrációs folyamat hibaelhárítását, valamint a HoloLens-eszköz általános használatát a szervezeten belül. Annak érdekében, hogy a felhasználók minél gyorsabban megoldják a problémákat, javasoljuk, hogy az eszkalációs folyamatot a következő sorrendhez hasonlóan kell kezelnie:

1. Az Ügyfélszolgálat.
2. HoloLens-szakértő csapata
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [HoloLens hibaelhárítási dokumentumok](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Kapcsolatfelvétel az ügyfélszolgálattal](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Eszközkezelés

Ez az útmutató a Mobile Eszközkezelés (MDM) beállításával, valamint néhány eszközkonfiguráció beállításával, valamint az olyan beállítások alkalmazásával kapcsolatban volt szó, amelyek lehetővé teszik a hozzáférést Wi-Fi tanúsítványokkal és proxyval kapcsolatban. Az MDM-et azonban eszközkorlátozások alkalmazására is használhatja CSP-k és szabályzatok segítségével.

Sok esetben az eszközökre kapcsolati korlátozások is vonatkoznak, például Bluetooth, VPN, USB, vagy akár a kamera vagy a mikrofon hozzáférésének kikapcsolása. Ha ezek bármelyike érdekli, javasoljuk, hogy olvassa el az általános [eszközkorlátozási oldalt.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

Egyéb összetettebb eszközkorlátozásokat is használhat. Például:

- A BeállításokLap láthatósága beállítással korlátozhatja a [](https://docs.microsoft.com/hololens/settings-uri-list)Beállítások alkalmazásban megtekinthető oldalakat, így a felhasználók csak a módosítania szükséges beállításokhoz férhetnek hozzá, például módosíthatják Wi-Fi kapcsolatukat.
- A [Kioszk mód használatával](https://docs.microsoft.com/hololens/hololens-kiosk) korlátozhatja az eszköz felhasználói felületét a felhasználók számára. A kioszkokat beállíthatja úgy, hogy egyetlen alkalmazást mutassanak, vagy több alkalmazást egy egyéni kezdőlapon. A kioszkok különböző élményeket is kínálnak a különböző felhasználók számára.
- [A Windows alkalmazásvezérlés (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) segítségével bizonyos alkalmazások vagy folyamatok nem indulnak el teljesen.

Ha többet szeretne megtudni az eszközkezelés vagy az eszközkorlátozások további módszereiről, akkor a következő lépéssel olvassa el a Eszközkezelés [áttekintését.](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)





