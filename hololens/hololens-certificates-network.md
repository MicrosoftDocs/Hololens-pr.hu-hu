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
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 62eedd0c05bb23f11a4e17a97b4ab5441a2931cf
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427092"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Tanúsítványok és hálózati profilok előkészítése a 2. HoloLens számára

A tanúsítványalapú hitelesítés gyakori követelmény a 2. HoloLens ügyfelek számára. Tanúsítványokat követelhet meg a Wi-Fi eléréséhez, a VPN-megoldásokhoz való csatlakozáshoz vagy a szervezet belső erőforrásainak eléréséhez.

Mivel HoloLens 2 eszköz általában az Azure Active Directory (Azure AD) szolgáltatáshoz csatlakozik, és az Intune vagy más MDM-szolgáltató kezeli, ezeket a tanúsítványokat az MDM-megoldással integrált Egyszerű tanúsítványigénylési protokoll (SCEP) vagy nyilvános kulcsú titkosítási szabvány (PKCS) tanúsítványinfra infrastruktúrájával kell telepíteni. 

>[!NOTE]
> Ha nem rendelkezik MDM-szolgáltatóval, akkor is [](hololens-provisioning.md#steps-for-creating-provisioning-packages) telepíthet tanúsítványokat egy kiépítési [](certificate-manager.md) csomaggal az [Windows Configuration Designerben](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) vagy a Tanúsítványkezelőben az **Gépház > Security & Security > Tanúsítványkezelőben.**

## <a name="certificate-requirements"></a>Tanúsítványkövetelmények
A tanúsítványok SCEP- vagy PKCS-infrastruktúrán keresztüli telepítéséhez főtanúsítványokra van szükség. Előfordulhat, hogy a szervezetben található egyéb alkalmazások és szolgáltatások főtanúsítványokat is HoloLens 2 eszközön. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi csatlakozási követelmények
Ahhoz, hogy egy eszköz automatikusan Wi-Fi a vállalati hálózathoz szükséges konfigurációval, szüksége lesz egy Wi-Fi konfigurációs profilra. Konfigurálhatja az Intune-t vagy más MDM-szolgáltatót, hogy telepítse ezeket a profilokat az eszközeire. Ha a hálózati biztonság megköveteli, hogy az eszközök a helyi tartományhoz is csatlakoznak, akkor előfordulhat, hogy ki kell értékelnie Wi-Fi hálózati infrastruktúrát, hogy az kompatibilis legyen HoloLens 2 eszközzel (a HoloLens 2-es eszközök csak az Azure AD-hez csatlakoznak).

## <a name="deploy-certificate-infrastructure"></a>Tanúsítványinfra infrastruktúra üzembe helyezése
Ha még nem létezik SCEP- vagy PKCS-infrastruktúra, elő kell készítenie egyet. Az SCEP- vagy PKCS-tanúsítványok hitelesítéshez való használatának támogatásához az Intune-nak [tanúsítvány-összekötőt kell használnia.](/mem/intune/protect/certificate-connectors)

> [!NOTE]
> Ha az SCEP-t Microsoft hitelesítésszolgáltatóval használja, a tanúsítványszolgáltatót [(NDES Hálózati eszközök tanúsítványigénylési szolgáltatása is konfigurálnia kell](/mem/intune/protect/certificates-scep-configure#set-up-ndes)

További információ: [Tanúsítványprofil konfigurálása az](/intune/certificates-configure) eszközökhöz a Microsoft Intune.

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Tanúsítványok és Wi-Fi-/VPN-profil üzembe helyezése
A tanúsítványok és profilok telepítéséhez kövesse az alábbi lépéseket:
1.  Hozzon létre egy profilt az egyes fő- és köztes tanúsítványokhoz (lásd: [Megbízható tanúsítványprofilok létrehozása.)](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Mindegyik profilnak olyan leírással kell lennie, amely tartalmaz egy lejárati dátumot DD/HH/YYYY formátumban. **A lejárati dátum nélküli tanúsítványprofilok nem lesznek telepítve.**
1.  Hozzon létre egy profilt minden SCEP- vagy PKCS-tanúsítványhoz (lásd: SCEP-tanúsítványprofil létrehozása vagy [PKCS-tanúsítványprofil létrehozása).](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Mindegyik profilnak olyan leírással kell rendelkezik, amely tartalmaz egy lejárati dátumot DD/HH/YYYY formátumban. **A lejárati dátum nélküli tanúsítványprofilok nem lesznek telepítve.**

    > [!NOTE]
    > Mivel a HoloLens 2-t sokan megosztott eszköznek tekintik, és eszközönként több felhasználó is van, ajánlott felhasználói tanúsítványok helyett eszköztanúsítványokat telepíteni az Wi-Fi hitelesítéshez, ahol lehetséges

3.  Hozzon létre egy profilt minden vállalati hálózati Wi-Fi (lásd: [Wi-Fi-beállítások az Windows 10 és újabb eszközökhöz).](/intune/wi-fi-settings-windows) 
    > [!NOTE]
    > Ha lehetséges, ajánlott a Wi-Fi-profilt az Eszközcsoportokhoz rendelni a Felhasználói csoportok helyett. [](/mem/intune/configuration/device-profile-assign) 

    > [!TIP]
    > Munkaprofilt a vállalati hálózaton Wi-Fi számítógépéről Windows 10 exportálhat. Ez az exportálás létrehoz egy XML-fájlt az összes aktuális beállítással. Ezután importálja ezt a fájlt az Intune-ba, és használja Wi-Fi 2 eszköz HoloLens profiljaként. Lásd: [Export and import Wi-Fi settings for Windows devices (A Windows-eszközök Windows importálása.](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Hozzon létre egy profilt az egyes vállalati VPN-hez (lásd a Windows 10 és Windows [Holographic eszközbeállításokat a VPN-kapcsolatok Intune-nal való hozzáadásához).](/intune/vpn-settings-windows-10)

## <a name="troubleshooting-certificates"></a>Tanúsítványok hibaelhárítása

Abban az esetben, ha ellenőriznie kell, hogy a [](certificate-manager.md) tanúsítvány megfelelően lett-e telepítve, az eszközön található Tanúsítványkezelővel ellenőrizze, hogy a tanúsítvány jelen van-e.  

>[!WARNING]
> Bár az MDM által telepített tanúsítványokat megtekintheti a Tanúsítványkezelőben, a Tanúsítványkezelőben nem távolíthatja el őket. Ezeket el kell távolítania az MDM-ről.


