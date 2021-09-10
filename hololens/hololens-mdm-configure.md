---
title: A Microsoft intune Endpoint Manager használata a HoloLens kezeléséhez
description: Megtudhatja, hogyan konfigurálhatja a CSP-t, a szabályzatokat és kezelheti HoloLens vegyes valóságú eszközöket nagy méretekben az Intune-nal.
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
ms.openlocfilehash: 5485a4b2558a11a6c0545ec8b3405c120cff287c
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427376"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>A Microsoft intune Endpoint Manager használata a HoloLens kezeléséhez

Az MDM-en keresztül számos különböző beállítás kezelhető. Az Intune-eszközök csoportosíthatók, és a konfigurációk telepíthetők a felhasználók vagy eszközök ezen csoportjaira. Az alkalmazások telepíthetők és kezelhetők, beállíthatók az eszközök a hálózathoz való csatlakozásra, valamint konfigurálhatóak a frissítések a kívánt időpontban és a szükséges frissítési körön. 

## <a name="how-to-manage-via-intune"></a>Kezelés az Intune-nal

### <a name="device-categories-and-groups"></a>Eszközkategóriák és csoportok
Az Intune-nal létrehozhat eszközkategóriákat, amelyek automatikusan hozzáadják az eszközöket a csoportokhoz az Ön által létrehozott kategóriák (például mérnöki, orvosi, fejlesztői stb.) alapján. A cél a Windows Holographic for Business rendszerű eszközök felügyeletének megkönnyítése.
További információ: [Eszközök csoportokba kategorizálása](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Eszközkonfigurációs profilok
Az Intune olyan beállításokat és funkciókat kínál, amelyeket Ön engedélyezhet vagy letilthat a vállalatához tartozó különböző eszközökön. Ezek a beállítások és funkciók profilok használatával kezelhetők. Létrehozhat például egy olyan profilt, amely engedélyezi a Cortana, vagy a Microsoft Defender Smart Screent használja a Windows Holographic for Business.
Profiljaiban OMA-URI használatával testre szabhat néhány beállítást, létrehozhat eszközkorlátozásokat és konfigurálhatja a virtuális magánhálózatokat (VPN) és a Wi-Fit.
[A konfigurációs profilok és](/mem/intune/configuration/device-profiles)a [profiláttekintés – első lépések.](/mem/intune/configuration/device-profile-create)

## <a name="examples-of-what-can-be-managed-and-configured"></a>Példák a kezelhető és konfigurálható beállításokra

Az MDM eszközök kezelésére való használata számos kiválasztható elemet biztosít. 

### <a name="wi-fi"></a>Wi-Fi
A [Wi-Fi-beállítások](/mem/intune/configuration/wi-fi-settings-configure) a vezeték nélküli hálózat beállításait rendeli hozzá felhasználókhoz és eszközökhöz. Ha hozzárendel egy Wi-Fi profilt, a felhasználók anélkül férhetnek hozzá a vállalati Wi-Fi, hogy azt maguknak kell konfigurálniuk.
További információ a [hálózat konfigurálásról a HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Tanúsítványok
A tanúsítványok azáltal növelik a biztonságot, hogy fiókhitelesítést, Wi-Fi, VPN-titkosítást és a webes tartalmak SSL-titkosítását biztosítják. Bár a rendszergazdák manuálisan kezelhetik az eszközökön található tanúsítványokat a kiépítési csomagokon keresztül, ajánlott eljárás az MDM-rendszer használata a tanúsítványok teljes életcikluson keresztüli kezelésére– a regisztrációtól a megújításon és visszavonáson át. Az MDM-rendszer automatikusan telepítheti ezeket a tanúsítványokat az eszközök tanúsítványtárolóiba az eszköz regisztrálása után (amennyiben az MDM-rendszer támogatja az Egyszerű tanúsítványigénylési protokoll (SCEP) vagy a nyilvános kulcsú titkosítási szabványokat #12 (PKCS #12)). Az MDM lekérdezheti és törölheti is a regisztrált ügyféltanúsítványokat, vagy új beléptetési kérelmet aktiválhat az aktuális tanúsítvány lejárta előtt. 

### <a name="proxy"></a>Proxy
A legtöbb vállalati intranetes hálózat proxyt használ a belső forgalom kezelésére. A HoloLens 2-es Wi-Fi konfigurálhat proxykiszolgálót ethernetes és Wi-Fi kapcsolatokhoz. Ezek a beállítások nem vonatkoznak a VPN-kapcsolatokra. További részletek a proxybeállításokról a [Windows 10: NetworkProxy CSP.](/windows/client-management/mdm/networkproxy-csp)

### <a name="vpn"></a>VPN
A szervezetek gyakran VPN használatával szabályozják az alkalmazásokhoz és erőforrásokhoz való hozzáférést a vállalat intranetén. HoloLens 2. lépés támogatja az SSL VPN-kapcsolatokat, amelyekhez egy letölthető beépülő modul szükséges a Microsoft Store, és amelyek az Ön által választott VPN-gyártóra vonatkoznak. 
- További információ a [VPN-ről a HoloLens.](hololens-network.md#vpn)
- A VPN-profilokkal kapcsolatos további részletekért lásd: [VPNv2 CSP.](/windows/client-management/mdm/vpnv2-csp)

### <a name="deploy-and-manage-apps"></a>Alkalmazások központi telepítése és kezelése
Az Intune használatával alkalmazásokat adhat hozzá a Windows Holographic for Business rendszerű eszközeihez. Az MDM-megoldások lehetővé teszik az informatikai döntéshozók és a rendszergazdák számára, hogy privát módon, automatikusan telepítik (leküldik) a házon belüli, üzletági alkalmazásokat, vagy alkalmazásokat vásárolnak az áruházon keresztül a felhasználók egy csoportja számára. Alkalmazások telepítésére több mód is van, többek között:
-   [Intune és Céges portál]( app-deploy-intune.md)
-   [Vállalati Microsoft Áruház]( app-deploy-store-business.md)

További információ az Intune-nal való alkalmazáskezelésről.
-   [Alkalmazások hozzáadása az Intune-hoz](/mem/intune/apps/apps-add)
-   [Microsoft Áruházbeli alkalmazások hozzáadása](/mem/intune/apps/store-apps-windows)
-   [Saját készítésű alkalmazások hozzáadása](/mem/intune/apps/lob-apps-windows)
- [Alkalmazások hozzárendelése csoportokhoz](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Szoftverfrissítések
Az Intune tartalmaz egy frissítési körök nevű funkciót a Windows 10-es eszközökhöz. A frissítési körökhöz tartozik a frissítések telepítési módját meghatározó beállítások egy csoportja. Létrehozhat például egy karbantartási időszakot a frissítések telepítésére vagy eldöntheti, hogy kíván-e újraindítást a frissítések telepítése után. Egy frissítési kör több Windows Holographic for Business rendszerű eszközre is alkalmazható.
További információ a frissítések [kezelésével és HoloLens](hololens-updates.md) Intune-nal történő [kezelésével kapcsolatban.](/mem/intune/protect/windows-update-for-business-configure)

### <a name="configure-kiosk-mode"></a>Teljes képernyős mód konfigurálása
Az Intune-ban elérhető megosztott vagy vendégszámítógép funkciókkal konfigurálhatja a Windows Holographic for Business eszközöket teljes képernyős módban való futtatásra. Ezek az eszközök futtathatnak egyetlen alkalmazást (egyalkalmazásos kioszkmód) vagy több alkalmazást (többalkalmazásos kioszkmód). A kioszkmód egy olyan felhasználói felület, amely alapértelmezés szerint azt szabályozhatja, hogy mely identitások mely alkalmazásokhoz férnek hozzá.
Megtudhatja, [hogyan állíthatja be a HoloLens kioszkként]( hololens-kiosk.md)

