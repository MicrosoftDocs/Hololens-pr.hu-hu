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
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639216"
---
# <a name="common-device-restrictions"></a>Gyakori eszközkorlátozások 

Ez az útmutató segít az informatikai szakembereknek megérteni a vállalati operációs rendszerhez Windows 10 Holographic általánosabb felügyeleti lehetőségeket. Az MDM-rendszer dokumentációjában tájékozódhat arról, hogyan engedélyezik ezeket a szabályzatokat az MDM-szállító. Nem minden MDM-rendszer támogatja az útmutatóban ismertetett összes beállítást. Egyes szabályzatok OMA-URI XML-fájlokon keresztül támogatják az egyéni szabályzatokat. Lásd: [Microsoft Intune egyéni szabályzatok támogatása.](/mem/intune/configuration/custom-settings-windows-10) Az elnevezési konvenciók az MDM-beszállítók között is eltérőek lehetnek.

## <a name="prevent-changing-of-settings"></a>Beállítások módosításának megakadályozása
Az alkalmazottak általában módosíthatjak bizonyos személyes eszközbeállításokat, amelyek zárolását a vállalati eszközökön is lehet. Az alkalmazottak interaktív módon módosíthatja a HoloLens beállítások felhasználói felületén keresztül. Az MDM használatával korlátozhatja, hogy a felhasználók milyen változásokat módosíthatnak. A következő lista azokat a gyakran használt MDM-beállításokat sorolja fel, Windows 10 Holographic a beállítások korlátozásának konfigurálásában:
-   [VPN engedélyezése:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Engedélyezi a felhasználó számára a VPN-beállítások módosítását
-   [Wi-Fi manuális konfigurálás engedélyezése:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Lehetővé teszi a felhasználók számára, Wi-Fi MDM által kiépített hálózatokon kívül is létesítsen kapcsolatokat
-   [Manuális MDM-igénylések igénylésének engedélyezése](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Azt határozza meg, hogy a felhasználók törölhetik-e a munkahelyi fiókot (vagyis törölhetik-e az eszköz az MDM-rendszerből való törlését)

Az Windows [Holographic 20H2-es verziója](hololens-release-notes.md#windows-holographic-version-20h2) hozzáadva HoloLens 2-es eszközökhöz:
- [Kiépítési csomag hozzáadásának engedélyezése:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Ha a felhasználók új kiépítési csomagokat adhatnak hozzá, új értékekkel felülírhatja őket.
- [Kiépítési csomag eltávolításának engedélyezése:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Váltógomb, ha a felhasználók eltávolítják a kiépítési csomagokat, így válthatnak a korábban zárolt beállítások között.

További részleteket a szabályzatbeállításokról a támogatott HoloLens csp-k [között talál.](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Hardverkorlátozások
Windows 10 Holographic eszközök a legtechnológiásbb technológiát használják, amely olyan népszerű hardverszolgáltatásokat tartalmaz, mint a kamerák, mikrofonok, beszélők, USB-adapterek, Bluetooth interfészek és Wi-Fi. A funkciók rendelkezésre állásának szabályozására hardverkorlátozások használhatók.
Az alábbi lista azokat a gyakran használt MDM-beállításokat sorolja fel, Windows 10 Holographic a hardverkorlátozások konfigurálásában:

> [!NOTE]
> Ezen hardverkorlátozások némelyike hatással van a kapcsolatra, és segít az adatvédelemben.

-   [Wi-Fi engedélyezése:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Azt határozza meg, hogy a felhasználók engedélyezhetik-e és használják-e a Wi-Fi-választógombot az eszközeiken.
-   [USB-kapcsolat engedélyezése:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Azt határozza meg, hogy az USB-kapcsolat engedélyezve van-e (nincs hatással az USB-feltöltésre).
-   [Az Bluetooth engedélyezése:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Azt határozza meg, hogy a felhasználók engedélyezhetik-e és Bluetooth az eszközükön a választógombot.
-   [Kamera korlátozása:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Meghatározza, Windows alkalmazások hozzáférhetnek-e a kamerához.
-   [Mikrofonok korlátozása:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Meghatározza, Windows alkalmazások hozzáférhetnek-e a mikrofonhoz.

Hozzáadva [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) HoloLens 2 eszköz esetében. 
- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) A kijelző kikapcsolásáig beállított idő zárolja az eszközt a kijelző kikapcsolásával. 
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) A kijelző kikapcsolásáig beállított idő zárolja az eszközt a kijelző kikapcsolásával. 
