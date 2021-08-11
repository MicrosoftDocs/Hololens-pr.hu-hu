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
ms.openlocfilehash: d9b752c820af8dbceb2b6b9f3c7a7be4df910805b5a5014bb3e3650551392ce8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664318"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Tanúsítványok és hálózati profilok előkészítése a 2. HoloLens számára

A tanúsítványalapú hitelesítés gyakori követelmény a 2. HoloLens ügyfelek számára. Tanúsítványokra lehet szükség a Wi-Fi eléréséhez, a VPN-megoldásokhoz való csatlakozáshoz vagy a szervezet belső erőforrásainak eléréséhez.

Mivel HoloLens 2 eszköz általában az Azure Active Directory (Azure AD) szolgáltatáshoz csatlakozik, és az Intune vagy más MDM-szolgáltató kezeli, ezeket a tanúsítványokat az MDM-megoldással integrált Egyszerű tanúsítványigénylési protokoll (SCEP) vagy nyilvános kulcsú titkosítási szabvány (PKCS) tanúsítványinfra infrastruktúrájával kell telepíteni. 

>[!NOTE]
> Ha nem rendelkezik MDM-szolgáltatóval, akkor is [](hololens-provisioning.md#steps-for-creating-provisioning-packages) telepíthet tanúsítványokat egy kiépítési [](certificate-manager.md) csomagon keresztül az [Windows Configuration Designerben](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) vagy a Tanúsítványkezelőben az Gépház > **Update & Security > Tanúsítványkezelőben.**

## <a name="certificate-requirements"></a>Tanúsítványkövetelmények
A tanúsítványok SCEP- vagy PKCS-infrastruktúrán keresztüli telepítéséhez főtanúsítványokra van szükség. Előfordulhat, hogy a szervezet más alkalmazásai és szolgáltatásai főtanúsítványokat is üzembe kell helyezni HoloLens 2 eszközön. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi csatlakozási követelmények
Ahhoz, hogy egy eszköz automatikusan meg tudja adni a vállalati hálózathoz Wi-Fi szükséges konfigurációt, szüksége lesz egy Wi-Fi konfigurációs profilra. Konfigurálhatja úgy az Intune-t vagy más MDM-szolgáltatót, hogy ezeket a profilokat az eszközökre telepítse. Ha a hálózati biztonság megköveteli, hogy az eszközök a helyi tartományhoz is csatlakoznak, akkor előfordulhat, hogy ki kell értékelnie Wi-Fi hálózati infrastruktúráját, hogy az kompatibilis legyen az HoloLens 2-es eszközzel (a HoloLens 2-es eszközök csak az Azure AD-hez csatlakoznak).

## <a name="deploy-certificate-infrastructure"></a>Tanúsítványinfra infrastruktúra üzembe helyezése
Ha még nem létezik SCEP- vagy PKCS-infrastruktúra, elő kell készítenie egyet. Az SCEP- vagy PKCS-tanúsítványok hitelesítéshez való használatának támogatásához az Intune [tanúsítvány-összekötőt igényel.](/mem/intune/protect/certificate-connectors)

> [!NOTE]
> Ha az SCEP-t Microsoft hitelesítésszolgáltatóval használja, a tanúsítványt [(NDES Hálózati eszközök tanúsítványigénylési szolgáltatása](/mem/intune/protect/certificates-scep-configure#set-up-ndes) is konfigurálnia kell

További információ: [Tanúsítványprofil konfigurálása az](/intune/certificates-configure) eszközökhöz a Microsoft Intune.

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Tanúsítványok és Wi-Fi-/VPN-profil üzembe helyezése
A tanúsítványok és profilok telepítéséhez kövesse az alábbi lépéseket:
1.  Hozzon létre egy profilt az egyes fő- és köztes tanúsítványokhoz (lásd: [Megbízható tanúsítványprofilok létrehozása.)](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Ezen profilok mindegyikének olyan leírással kell lennie, amely tartalmaz egy lejárati dátumot DD/HH/YYYY formátumban. **A lejárati dátum nélküli tanúsítványprofilok nem lesznek telepítve.**
1.  Hozzon létre egy profilt minden SCEP- vagy PKCS-tanúsítványhoz (lásd: SCEP-tanúsítványprofil létrehozása vagy [PKCS-tanúsítványprofil létrehozása).](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Mindegyik profilnak olyan leírással kell rendelkezik, amely tartalmaz egy lejárati dátumot DD/HH/YYYY formátumban. **A lejárati dátum nélküli tanúsítványprofilok nem lesznek telepítve.**

    > [!NOTE]
    > Mivel a HoloLens 2.-t sok megosztott eszköznek, eszközönként több felhasználónak tekintjük, ajánlott a felhasználói tanúsítványok helyett eszköztanúsítványokat telepíteni Wi-Fi hitelesítéshez, ahol lehetséges

3.  Hozzon létre egy profilt minden vállalati hálózati Wi-Fi számára (lásd: [Wi-Fi-beállítások](/intune/wi-fi-settings-windows)a Windows 10 és újabb eszközökhöz). 
    > [!NOTE]
    > Javasoljuk, hogy Wi-Fi felhasználói csoportok [](/mem/intune/configuration/device-profile-assign) helyett eszközcsoportokhoz rendeli hozzá a profilt. 

    > [!TIP]
    > Munkaprofilt a vállalati hálózaton Wi-Fi számítógépéről Windows 10 exportálhat. Ez az exportálás létrehoz egy XML-fájlt az összes aktuális beállítással. Ezután importálja ezt a fájlt az Intune-ba, és használja Wi-Fi 2 eszköz HoloLens profiljaként. Lásd: [Export and import Wi-Fi settings for Windows devices (A Windows beállításainak exportálása és importálása).](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Hozzon létre egy profilt az egyes vállalati VPN-hez (lásd Windows 10 holographic Windows a VPN-kapcsolatok Intune-nal való [hozzáadásához).](/intune/vpn-settings-windows-10)

## <a name="troubleshooting-certificates"></a>Tanúsítványok hibaelhárítása

Abban az esetben, ha ellenőriznie kell, hogy a [](certificate-manager.md) tanúsítvány megfelelően van-e telepítve, használja az eszközön a Tanúsítványkezelőt annak ellenőrzéséhez, hogy a tanúsítvány jelen van-e.  

>[!WARNING]
> Bár az MDM által telepített tanúsítványokat megtekintheti a Tanúsítványkezelőben, a Tanúsítványkezelőben nem távolíthatja el őket. Ezeket az MDM-ről kell eltávolítania.


