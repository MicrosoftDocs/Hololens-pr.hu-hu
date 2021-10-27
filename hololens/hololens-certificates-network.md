---
title: Tanúsítványok és hálózati profilok előkészítése a 2. HoloLens számára
description: Megtudhatja, hogyan konfigurálhatja, használhatja, helyezheti üzembe és háríthatja el a hálózati tanúsítványokat HoloLens 2 vegyes valóságú eszközön.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: cf9e14ffbda01bb1fd9e788385f7b85884d1dc8c
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351617"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Tanúsítványok és hálózati profilok előkészítése a 2. HoloLens számára

A tanúsítványalapú hitelesítés gyakori követelmény a 2. HoloLens ügyfelek számára. Tanúsítványokat követelhet meg a Wi-Fi eléréséhez, a VPN-megoldásokhoz való csatlakozáshoz vagy a szervezet belső erőforrásainak eléréséhez.

Mivel HoloLens 2 eszköz általában az Azure Active Directory (Azure AD) szolgáltatáshoz csatlakozik, és az Intune vagy más MDM-szolgáltató kezeli, ezeket a tanúsítványokat az MDM-megoldással integrált Egyszerű tanúsítványigénylési protokoll (SCEP) vagy nyilvános kulcsú titkosítási szabvány (PKCS) tanúsítványinfra infrastruktúrájával kell telepíteni. 

>[!NOTE]
> Ha nem rendelkezik MDM-szolgáltatóval, akkor is [](hololens-provisioning.md#create-the-provisioning-package) telepíthet tanúsítványokat egy kiépítési [](certificate-manager.md) csomagon keresztül az [Windows Configuration Designerben](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) vagy a Tanúsítványkezelőben az **Gépház > Update & Security > Certificate Manager**(Tanúsítványkezelő) segítségével.

## <a name="certificate-requirements"></a>Tanúsítványkövetelmények
A tanúsítványok SCEP- vagy PKCS-infrastruktúrán keresztüli telepítéséhez főtanúsítványokra van szükség. Előfordulhat, hogy a szervezet más alkalmazásai és szolgáltatásai főtanúsítványokat is HoloLens 2 eszközön. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi csatlakozási követelmények
Ahhoz, hogy egy eszköz automatikusan Wi-Fi a vállalati hálózathoz szükséges konfigurációval, szüksége lesz egy Wi-Fi konfigurációs profilra. Konfigurálhatja az Intune-t vagy más MDM-szolgáltatót, hogy telepítse ezeket a profilokat az eszközeire. Ha a hálózati biztonság megköveteli, hogy az eszközök a helyi tartományhoz is csatlakoznak, akkor előfordulhat, hogy ki kell értékelnie Wi-Fi hálózati infrastruktúrát, hogy az kompatibilis legyen az HoloLens 2 eszközzel (a HoloLens 2-es eszközök csak az Azure AD-hez csatlakoznak).

## <a name="deploy-certificate-infrastructure"></a>Tanúsítványinfra infrastruktúra üzembe helyezése
Ha még nem létezik SCEP- vagy PKCS-infrastruktúra, elő kell készítenie egyet. Az SCEP- vagy PKCS-tanúsítványok hitelesítéshez való használatának támogatásához az Intune-nak [tanúsítvány-összekötőt kell használnia.](/mem/intune/protect/certificate-connectors)

> [!NOTE]
> Ha az SCEP-t Microsoft hitelesítésszolgáltatóval használja, a tanúsítványt [(NDES Hálózati eszközök tanúsítványigénylési szolgáltatása](/mem/intune/protect/certificates-scep-configure#set-up-ndes) is konfigurálnia kell

További információ: [Tanúsítványprofil konfigurálása az](/intune/certificates-configure) eszközökhöz a Microsoft Intune.

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Tanúsítványok és Wi-Fi-/VPN-profil üzembe helyezése
Tanúsítványok és profilok telepítéséhez kövesse az alábbi lépéseket:

1.  Hozzon létre egy profilt az egyes fő- és köztes tanúsítványokhoz (lásd: [Megbízható tanúsítványprofilok létrehozása.)](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Mindegyik profilnak olyan leírással kell lennie, amely tartalmaz egy lejárati dátumot DD/HH/YYYY formátumban. **A lejárati dátum nélküli tanúsítványprofilok nem lesznek telepítve.**

2.  Hozzon létre egy profilt minden SCEP- vagy PKCS-tanúsítványhoz (lásd: SCEP-tanúsítványprofil létrehozása vagy [PKCS-tanúsítványprofil létrehozása).](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Mindegyik profilnak olyan leírással kell rendelkezik, amely tartalmaz egy lejárati dátumot DD/HH/YYYY formátumban. **A lejárati dátum nélküli tanúsítványprofilok nem lesznek telepítve.**

    > [!NOTE]
    > Mivel a HoloLens 2-t sokan megosztott eszköznek tekintik, és eszközönként több felhasználó is van, ajánlott felhasználói tanúsítványok helyett eszköztanúsítványokat telepíteni Wi-Fi hitelesítéshez, ahol lehetséges

3.  Hozzon létre egy profilt az egyes vállalati hálózati Wi-Fi (lásd: [Wi-Fi-beállítások](/intune/wi-fi-settings-windows)az Windows 10 és újabb eszközökhöz). 

    > [!NOTE]
    > Javasoljuk, hogy Wi-Fi profilt [](/mem/intune/configuration/device-profile-assign) a felhasználói csoportok helyett eszközcsoportokhoz, ahol lehetséges. 

    > [!TIP]
    > Munkaprofilt exportálhat Wi-Fi vállalati hálózaton Windows 10 számítógépéről is. Ez az exportálás létrehoz egy XML-fájlt az összes aktuális beállítással. Ezután importálja ezt a fájlt az Intune-ba, és használja Wi-Fi 2 eszköz HoloLens profiljaként. Lásd: [Export and import Wi-Fi settings for Windows devices (A Windows-eszközök Windows importálása.](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Hozzon létre egy profilt az egyes vállalati VPN-hez (lásd Windows 10 holografikus eszközbeállítások Windows a VPN-kapcsolatok Intune-nal való [hozzáadásához).](/intune/vpn-settings-windows-10)

## <a name="troubleshooting"></a>Hibaelhárítás

### <a name="issue---unable-to-connect-with-network-using-certificate-based-authentication"></a>Probléma – Nem lehet csatlakozni a hálózathoz tanúsítványalapú hitelesítéssel ###

**Hibajelenségek**

Az eszköz nem tud hálózati kapcsolatot létesíteni tanúsítványalapú hitelesítéssel.

**Hibaelhárítási lépések**

1. Abban az esetben, ha ellenőriznie kell, hogy a [](certificate-manager.md) tanúsítvány megfelelően lett-e telepítve, az eszközön található Tanúsítványkezelővel ellenőrizze, hogy a tanúsítvány jelen van-e.  

    >[!WARNING]
    > Bár az MDM által telepített tanúsítványokat megtekintheti a Tanúsítványkezelőben, a Tanúsítványkezelőben nem távolíthatja el őket. Ezeket az MDM-ről kell eltávolítania.

2. Csak az Intune esetében, ha Egyszerű tanúsítványigénylési protokoll (SCEP) tanúsítványokat telepít, győződjön meg arról, hogy az Hálózati eszközök tanúsítványigénylési szolgáltatása-kiszolgáló URL-címe elérhető az eszközről. [A beállítással kapcsolatos információkért tekintse](/mem/intune/protect/certificates-profile-scep) meg az Intune SCEP-tanúsítványait. Ha az NDES-kiszolgáló teljes tartománya helyett CNAME-et használ, ellenőrizze, hogy a probléma megoldása megfelelően történik-e. Ezt az URL-címet írja be az eszköz webböngészőjébe.
