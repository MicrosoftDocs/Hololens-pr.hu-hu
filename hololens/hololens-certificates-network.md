---
title: Tanúsítványok és hálózati profilok előkészítése a HoloLens 2-hez
description: Megtudhatja, hogyan konfigurálhatja, használhatja, telepítheti és háríthatja el a hálózati tanúsítványokat a HoloLens 2 vegyes valóságú eszközökön.
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
ms.openlocfilehash: eedb451847757eba02465d7ded4494b9712497ff
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379518"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Tanúsítványok és hálózati profilok előkészítése a HoloLens 2-hez

A Tanúsítványalapú hitelesítés gyakori követelmény a HoloLens 2-t használó ügyfelek számára. Tanúsítványokra lehet szükség a Wi-Fi eléréséhez, a VPN-megoldásokhoz való csatlakozáshoz vagy a szervezet belső erőforrásainak eléréséhez.

Mivel a HoloLens 2-eszközök általában az Azure Active Directory (Azure AD) szolgáltatáshoz csatlakoznak, és az Intune vagy más MDM-szolgáltató kezeli, ezeket a tanúsítványokat az MDM-megoldással integrált Egyszerű tanúsítványigénylési protokoll (SCEP) vagy nyilvános kulcsú titkosítási szabvány (PKCS) tanúsítványinfra infrastruktúrával kell telepíteni. 

>[!NOTE]
> Ha nem rendelkezik MDM-szolgáltatóval, akkor is telepíthet tanúsítványokat egy kiépítési csomaggal [a](https://docs.microsoft.com/hololens/hololens-provisioning#steps-for-creating-provisioning-packages) [Windows Configuration Designerben](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) vagy a Tanúsítványkezelőben a Beállítások **> Update & Security > Tanúsítványkezelőben.** [](https://docs.microsoft.com/hololens/certificate-manager)

## <a name="certificate-requirements"></a>Tanúsítványkövetelmények
A tanúsítványok SCEP- vagy PKCS-infrastruktúrán keresztüli telepítéséhez főtanúsítványokra van szükség. Előfordulhat, hogy a szervezet más alkalmazásai és szolgáltatásai főtanúsítványokat is üzembe kell helyezni a HoloLens 2-eszközökön. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi csatlakozási követelmények
Ahhoz, hogy egy eszköz automatikusan meg tudja adni a vállalati hálózathoz Wi-Fi szükséges konfigurációt, szüksége lesz egy Wi-Fi konfigurációs profilra. Konfigurálhatja úgy az Intune-t vagy más MDM-szolgáltatót, hogy ezeket a profilokat az eszközökre telepítse. Ha a hálózati biztonság megköveteli, hogy az eszközök a helyi tartományhoz is csatlakoznak, akkor előfordulhat, hogy ki kell értékelnie Wi-Fi hálózati infrastruktúráját, hogy az kompatibilis legyen a HoloLens 2-eszközökkel (a HoloLens 2-eszközök csak Azure AD-hez csatlakoznak).

## <a name="deploy-certificate-infrastructure"></a>Tanúsítványinfra infrastruktúra üzembe helyezése
Ha még nem létezik SCEP- vagy PKCS-infrastruktúra, elő kell készítenie egyet. Az SCEP- vagy PKCS-tanúsítványok hitelesítéshez való használatának támogatásához az Intune [tanúsítvány-összekötőt igényel.](https://docs.microsoft.com/mem/intune/protect/certificate-connectors)

> [!NOTE]
> Ha az SCEP-t Microsoft hitelesítésszolgáltatóval használja, a tanúsítványt [(NDES Hálózati eszközök tanúsítványigénylési szolgáltatása](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes) is konfigurálnia kell

További információ: [Tanúsítványprofil konfigurálása az](https://docs.microsoft.com/intune/certificates-configure) eszközökhöz a Microsoft Intune.

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Tanúsítványok és Wi-Fi-/VPN-profil üzembe helyezése
A tanúsítványok és profilok telepítéséhez kövesse az alábbi lépéseket:
1.  Hozzon létre egy profilt az egyes fő- és köztes tanúsítványokhoz (lásd: [Megbízható tanúsítványprofilok létrehozása.)](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) Ezen profilok mindegyikének olyan leírással kell lennie, amely tartalmaz egy lejárati dátumot DD/HH/YYYY formátumban. **A lejárati dátum nélküli tanúsítványprofilok nem lesznek telepítve.**
1.  Hozzon létre egy profilt minden SCEP- vagy PKCS-tanúsítványhoz (lásd: SCEP-tanúsítványprofil létrehozása vagy [PKCS-tanúsítványprofil létrehozása).](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Mindegyik profilnak olyan leírással kell rendelkezik, amely tartalmaz egy lejárati dátumot DD/HH/YYYY formátumban. **A lejárati dátum nélküli tanúsítványprofilok nem lesznek telepítve.**

    > [!NOTE]
    > Mivel a HoloLens 2-t sokan megosztott eszköznek, eszközönként több felhasználónak tekintik, ajánlott eszköztanúsítványokat telepíteni felhasználói tanúsítványok helyett Wi-Fi hitelesítéshez, ahol lehetséges

3.  Hozzon létre egy profilt minden vállalati hálózati Wi-Fi számára (lásd: [Wi-Fi-beállítások](https://docs.microsoft.com/intune/wi-fi-settings-windows)a Windows 10 és újabb eszközökhöz). 
    > [!NOTE]
    > Javasoljuk, hogy Wi-Fi felhasználói csoportok [](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) helyett eszközcsoportokhoz rendeli hozzá a profilt. 

    > [!TIP]
    > Munkaprofilt a vállalati hálózaton Wi-Fi számítógépéről Windows 10 exportálhat. Ez az exportálás létrehoz egy XML-fájlt az összes aktuális beállítással. Ezután importálja ezt a fájlt az Intune-ba, és használja Wi-Fi HoloLens 2-eszközeihez. Lásd: [Exportálás és importálás Wi-Fi windowsos eszközökre vonatkozó beállításokhoz.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Hozzon létre egy profilt az egyes vállalati VPN-hez (lásd a Windows 10 és a Windows Holographic eszközbeállításokat a VPN-kapcsolatok Intune-nal [való hozzáadásához).](https://docs.microsoft.com/intune/vpn-settings-windows-10)

## <a name="troubleshooting-certificates"></a>Tanúsítványok hibaelhárítása

Abban az esetben, ha ellenőriznie kell, hogy a [](certificate-manager.md) tanúsítvány megfelelően van-e telepítve, használja az eszközön a Tanúsítványkezelőt annak ellenőrzéséhez, hogy a tanúsítvány jelen van-e.  

>[!WARNING]
> Bár az MDM által telepített tanúsítványokat megtekintheti a Tanúsítványkezelőben, a Tanúsítványkezelőben nem távolíthatja el őket. Ezeket az MDM-ről kell eltávolítania.


