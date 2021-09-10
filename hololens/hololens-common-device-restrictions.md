---
title: Gyakori eszközkorlátozások
description: Naprakészen tarthatja a vegyes valóságú eszköz általános eszközkorlátozásait HoloLens beállításait.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 769cacc1803af9d9e9bf1079f8cd5671f194c3bc
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427961"
---
# <a name="common-device-restrictions"></a>Gyakori eszközkorlátozások 

Ez az útmutató segít az informatikai szakembereknek megérteni a vállalat operációs rendszeréhez Windows 10 Holographic általánosabb felügyeleti lehetőségeket. Az MDM-rendszer dokumentációjában tájékozódhat arról, hogyan engedélyezi ezeket a szabályzatokat az MDM-szállító. Nem minden MDM-rendszer támogatja az útmutatóban ismertetett összes beállítást. Némelyik támogatja az egyéni szabályzatokat az OMA-URI XML-fájlokon keresztül. Lásd [Microsoft Intune egyéni szabályzatok támogatását.](/mem/intune/configuration/custom-settings-windows-10) Az elnevezési konvenciók az MDM-beszállítók között is eltérőek lehetnek.

## <a name="prevent-changing-of-settings"></a>Beállítások módosításának megakadályozása
Az alkalmazottak általában módosíthatjak bizonyos személyes eszközbeállításokat, amelyek zárolását a céges eszközökön is lehet. Az alkalmazottak interaktív módon módosíthatja a HoloLens beállítások felhasználói felületén keresztül. Az MDM használatával korlátozhatja, hogy a felhasználók milyen változásokat módosíthatnak. A következő lista azokat a gyakran használt MDM-beállításokat sorolja fel, Windows 10 Holographic a beállítások korlátozásait támogatja:
-   [VPN engedélyezése:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Engedélyezi a felhasználó számára a VPN-beállítások módosítását
-   [Wi-Fi manuális konfigurálás engedélyezése:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Lehetővé teszi, hogy a Wi-Fi MDM által kiépített hálózatokon kívül is létesítsen kapcsolatokat
-   [Manuális MDM-igénylések igénylésének engedélyezése](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Azt határozza meg, hogy a felhasználók törölhetik-e a munkahelyi fiókot (vagyis törölhetik-e az eszköz MDM-rendszerből való törlését)

A [holografikus Windows 20H2-es](hololens-release-notes.md#windows-holographic-version-20h2) verziója hozzáadva HoloLens 2 eszközökhöz:
- [Kiépítési csomag hozzáadásának engedélyezése:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Be- és bekapcsolhatja, hogy a felhasználók hozzáadhatnak-e új kiépítési csomagokat, felülírva az új értékeket.
- [Kiépítési csomag eltávolításának engedélyezése:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Kapcsolódhat, ha a felhasználók eltávolítják a kiépítési csomagokat, így válthatnak a korábban zárolt beállítások között.

További részletek a szabályzatbeállításokról a támogatott HoloLens [CSP-k között](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Hardverkorlátozások
Windows 10 Holographic eszközök a legtechnológiásbb technológiát használják, amely olyan népszerű hardverszolgáltatásokat tartalmaz, mint a kamerák, mikrofonok, beszélők, USB-adapterek, Bluetooth interfészek és Wi-Fi. Ezeknek a funkcióknak a rendelkezésre állását hardverkorlátozások használatával szabályozhatja.
Az alábbi lista azokat a gyakran használt MDM-beállításokat sorolja fel, Windows 10 Holographic támogatja a hardverkorlátozások konfigurálását:

> [!NOTE]
> Ezen hardverkorlátozások némelyike hatással van a kapcsolatra, és segít az adatvédelemben.

-   [Wi-Fi engedélyezése:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Azt határozza meg, hogy a felhasználók engedélyezhetik-e és használhatják-e a Wi-Fi-választógombot az eszközeiken.
-   [USB-kapcsolat engedélyezése:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Azt határozza meg, hogy az USB-kapcsolat engedélyezve van-e (nincs hatással az USB-díjszabásra).
-   [Az Bluetooth engedélyezése:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Azt határozza meg, hogy a felhasználók engedélyezhetik-e és Bluetooth az eszközükön a választógombot.
-   [Kamera korlátozása:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Meghatározza, Windows alkalmazások hozzáférhetnek-e a kamerához.
-   [Mikrofonok korlátozása:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Meghatározza, Windows alkalmazások hozzáférhetnek-e a mikrofonhoz.

Hozzáadva [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) HoloLens 2 eszköz esetében. 
- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Állítsa be, hogy mennyi idő után kapcsolja ki a kijelzőt, és a kijelző kikapcsolásával zárolja az eszközt. 
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Állítsa be, hogy mennyi idő után kapcsolja ki a kijelzőt, és a kijelző kikapcsolásával zárolja az eszközt. 
