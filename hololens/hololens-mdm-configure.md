---
title: HoloLens-eszközök kezelése Endpoint Manager Microsoft Intune-nal
description: Megtudhatja, hogyan konfigurálhatja a CsP-t, a szabályzatokat és a HoloLens vegyes valóságú eszközök nagy léptékű felügyeletét az MDM használatával az Intune-nal.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ce288afdcb112c17ffde75078d641f3637a8448c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378121"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>HoloLens-eszközök kezelése Endpoint Manager Microsoft Intune-nal

Az MDM-en keresztül számos különböző beállítás kezelhető. Az Intune-eszközök csoportosíthatók, és a konfigurációk telepíthetők a felhasználók vagy eszközök csoportjaira. Az alkalmazások telepíthetők és kezelhetők, beállíthatók az eszközök a hálózathoz való csatlakozásra, valamint konfigurálhatóak a frissítések a kívánt időpontban és a szükséges frissítési körön. 

## <a name="how-to-manage-via-intune"></a>Kezelés az Intune-nal

### <a name="device-categories-and-groups"></a>Eszközkategóriák és csoportok
Az Intune-nal eszközkategóriákat hozhat létre, amelyek automatikusan hozzáadják az eszközöket a csoportokhoz az Ön által létrehozott kategóriák (például mérnöki, orvosi, fejlesztői stb.) alapján. A cél a Windows Holographic for Business rendszerű eszközök felügyeletének megkönnyítése.
További információ: [Eszközök csoportokba kategorizálása](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Eszközkonfigurációs profilok
Az Intune olyan beállításokat és funkciókat kínál, amelyeket Ön engedélyezhet vagy letilthat a vállalatához tartozó különböző eszközökön. Ezek a beállítások és funkciók profilok használatával kezelhetők. Létrehozhat például egy olyan profilt, amely engedélyezi Cortanát, vagy a Microsoft Defender Smart Screent használja a Windows Holographic for Business.
Profiljaiban OMA-URI használatával testre szabhat néhány beállítást, létrehozhat eszközkorlátozásokat és konfigurálhatja a virtuális magánhálózatokat (VPN) és a Wi-Fit.
[A konfigurációs profilok és](https://docs.microsoft.com/mem/intune/configuration/device-profiles)a [profiláttekintés – első lépések.](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)

## <a name="examples-of-what-can-be-managed-and-configured"></a>Példák a kezelhető és konfigurálható beállításokra

Ha MDM-et használ az eszközök kezeléséhez, számos kiválasztható elemet biztosít. 

### <a name="wi-fi"></a>Wi-Fi
A [Wi-Fi-beállítások](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) a vezeték nélküli hálózat beállításait rendeli hozzá felhasználókhoz és eszközökhöz. Ha hozzárendel egy Wi-Fi profilt, a felhasználók anélkül férhetnek hozzá a vállalati Wi-Fi, hogy azt maguknak kell konfigurálniuk.
További információ a [hálózat HoloLenshez való konfigurálásról](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Tanúsítványok
A tanúsítványok azáltal növelik a biztonságot, hogy fiókhitelesítést, Wi-Fi, VPN-titkosítást és a webes tartalmak SSL-titkosítását biztosítják. Bár a rendszergazdák manuálisan kezelhetik az eszközökön található tanúsítványokat a kiépítési csomagokon keresztül, ajánlott eljárás az MDM-rendszert használni a tanúsítványok teljes életcikluson keresztüli kezelésére a regisztrációtól a megújításon és visszavonáson át. Az MDM-rendszer automatikusan üzembe tudja helyezni ezeket a tanúsítványokat az eszközök tanúsítványtárolóiban az eszköz regisztrálása után (amennyiben az MDM-rendszer támogatja az Egyszerű tanúsítványigénylési protokoll (SCEP) vagy a nyilvános kulcsú titkosítási szabványokat #12 (PKCS #12)). Az MDM lekérdezheti és törölheti is a regisztrált ügyféltanúsítványokat, vagy új beléptetési kérelmet aktiválhat az aktuális tanúsítvány lejárta előtt. 

### <a name="proxy"></a>Proxy
A legtöbb vállalati intranetes hálózat proxyt használ a belső forgalom kezelésére. A HoloLens 2-ben proxykiszolgálót konfigurálhat ethernetes és Wi-Fi kapcsolatokhoz. Ezek a beállítások nem vonatkoznak a VPN-kapcsolatokra. További információ a proxybeállításokról a [Windows 10: NetworkProxy CSP.](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)

### <a name="vpn"></a>VPN
A szervezetek gyakran VPN használatával szabályozják az alkalmazásokhoz és erőforrásokhoz való hozzáférést a vállalat intranetén. A HoloLens 2 támogatja az SSL VPN-kapcsolatokat, amelyekhez letölthető beépülő modulra van szükség a Microsoft Store és amelyek az Ön által választott VPN-gyártóra vonatkoznak. 
- További információ a [VPN-ről a HoloLensben.](hololens-network.md#vpn)
- A VPN-profilokkal kapcsolatos további részletekért lásd: [VPNv2 CSP.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)

### <a name="deploy-and-manage-apps"></a>Alkalmazások központi telepítése és kezelése
Az Intune használatával alkalmazásokat adhat hozzá a Windows Holographic for Business rendszerű eszközeihez. Az MDM-megoldások lehetővé teszik az informatikai döntéshozók és a rendszergazdák számára, hogy privát módon automatikusan telepítik (leküldik) a házon belüli, üzletági alkalmazásokat, vagy alkalmazásokat vásárolnak az áruházon keresztül a felhasználók egy csoportja számára. Alkalmazások telepítésére több mód is van, többek között:
-   [Intune és Céges portál]( app-deploy-intune.md)
-   [Vállalati Microsoft Áruház]( app-deploy-store-business.md)

További információ az Intune-nal való alkalmazáskezelésről.
-   [Alkalmazások hozzáadása az Intune-hoz](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Microsoft Áruházbeli alkalmazások hozzáadása](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [Saját készítésű alkalmazások hozzáadása](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [Alkalmazások hozzárendelése csoportokhoz](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Szoftverfrissítések
Az Intune tartalmaz egy frissítési körök nevű funkciót a Windows 10-es eszközökhöz. A frissítési körökhöz tartozik a frissítések telepítési módját meghatározó beállítások egy csoportja. Létrehozhat például egy karbantartási időszakot a frissítések telepítésére vagy eldöntheti, hogy kíván-e újraindítást a frissítések telepítése után. Egy frissítési kör több Windows Holographic for Business rendszerű eszközre is alkalmazható.
További információ a [HoloLens-frissítések](hololens-updates.md) kezelésével és a szoftverfrissítések [Intune-nal való kezelésével kapcsolatban.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)

### <a name="configure-kiosk-mode"></a>Teljes képernyős mód konfigurálása
Az Intune-ban elérhető megosztott vagy vendégszámítógép funkciókkal konfigurálhatja a Windows Holographic for Business eszközöket teljes képernyős módban való futtatásra. Ezek az eszközök futtathatnak egyetlen alkalmazást (egyalkalmazásos kioszkmód) vagy több alkalmazást (többalkalmazásos kioszkmód). A kioszkmód egy olyan felhasználói felület, amely alapértelmezés szerint azt szabályozhatja, hogy mely identitások mely alkalmazásokhoz férnek hozzá.
Megtudhatja, [hogyan állíthatja be a HoloLenst kioszkként]( hololens-kiosk.md)

