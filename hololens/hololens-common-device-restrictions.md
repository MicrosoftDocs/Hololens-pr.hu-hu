---
title: Gyakori eszközkorlátozások
description: Naprakészen tarthatja a vegyes valóságú eszköz általános eszközkorlátozásait HoloLens beállításait.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2021
ms.reviewer: aboeger
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 12dd061565c88fed65d1152c224be9ebbc7185d4
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924300"
---
# <a name="common-device-restrictions"></a>Gyakori eszközkorlátozások

Ez az útmutató segít az informatikai szakembereknek megérteni a vállalat operációs rendszeréhez Windows 10 Holographic általánosabb felügyeleti lehetőségeket. Az MDM-rendszer dokumentációjában tájékozódhat arról, hogyan engedélyezik ezeket a szabályzatokat az MDM-szállító. Nem minden MDM-rendszer támogatja az útmutatóban ismertetett összes beállítást. Egyes szabályzatok OMA-URI XML-fájlokon keresztül támogatják az egyéni szabályzatokat. Lásd: [Microsoft Intune egyéni szabályzatok támogatása.](/mem/intune/configuration/custom-settings-windows-10) Az elnevezési konvenciók az MDM-beszállítók között is eltérőek lehetnek.

## <a name="prevent-changing-of-settings"></a>Beállítások módosításának megakadályozása

Az alkalmazottak általában módosíthatjak bizonyos személyes eszközbeállításokat, amelyek zárolását a vállalati eszközökön is lehet. Az alkalmazottak interaktív módon módosíthatja a HoloLens beállítások felhasználói felületén keresztül. Az MDM használatával korlátozhatja, hogy a felhasználók milyen beállításokat módosíthatnak.
A következő lista azokat a gyakran használt MDM-beállításokat sorolja fel, Windows 10 Holographic a beállítások korlátozásának konfigurálásában:

- [VPN engedélyezése:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Engedélyezi a felhasználó számára a VPN-beállítások módosítását
- [Wi-Fi manuális konfigurálás engedélyezése:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Lehetővé teszi, hogy a Wi-Fi MDM által kiépített hálózatokon kívül is létesítsen kapcsolatokat
- [Manuális MDM-igénylések igénylésének engedélyezése](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Azt határozza meg, hogy a felhasználók törölhetik-e a munkahelyi fiókot (vagyis törölhetik-e az eszköz az MDM-rendszerből való törlését)

A [Holographic Windows 20H2-es verziója](hololens-release-notes.md#windows-holographic-version-20h2) hozzáadva HoloLens 2-es eszközökhöz:

- [Kiépítési csomag hozzáadásának engedélyezése:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Ha a felhasználók új kiépítési csomagokat adhatnak hozzá, új értékekkel felülírhatja őket.
- [Kiépítési csomag eltávolításának engedélyezése:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Váltógomb, ha a felhasználók eltávolítják a kiépítési csomagokat, így válthatnak a korábban zárolt beállítások között.

Hozzáadva [Windows Holographic 21H2-es verziójában:](hololens-release-notes.md#windows-holographic-version-21h2)

- [A RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly) szabályzat lehetővé teszi, hogy a Microsoft Store-alkalmazás úgy legyen konfigurálva, hogy csak a szervezet számára konfigurált privát tárolót mutassa, így a hozzáférést csak az Ön által elérhetővé tett alkalmazásokra korlátozza.

További részletek a szabályzatbeállításokról a támogatott HoloLens [CSP-k között](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Hardverkorlátozások

Windows 10 Holographic eszközök a legtechnológiásbb technológiát használják, amely olyan népszerű hardverszolgáltatásokat tartalmaz, mint a kamerák, mikrofonok, beszélők, USB-adapterek, Bluetooth interfészek és Wi-Fi. A funkciók rendelkezésre állásának szabályozására hardverkorlátozások használhatók.
Az alábbi lista azokat a gyakran használt MDM-beállításokat sorolja fel, Windows 10 Holographic hardverkorlátozások konfigurálásában támogatott:

> [!NOTE]
> Ezen hardverkorlátozások némelyike hatással van a kapcsolatra, és segít az adatvédelemben.

- [Wi-Fi engedélyezése:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Azt határozza meg, hogy a felhasználók engedélyezhetik-e és használhatják-e a Wi-Fi-választógombot az eszközeiken.
- [USB-kapcsolat engedélyezése:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Azt határozza meg, hogy az USB-kapcsolat engedélyezve van-e (nincs hatással az USB-feltöltésre).
- [Az Bluetooth engedélyezése:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Azt határozza meg, hogy a felhasználók engedélyezhetik-e és Bluetooth az eszközükön a választógombot.
- [Kamera korlátozása:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Meghatározza, Windows alkalmazások hozzáférhetnek-e a kamerához.
- [Mikrofonok korlátozása:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Meghatározza, Windows alkalmazások hozzáférhetnek-e a mikrofonhoz.

A [Holographic Windows 20H2-es verziója](hololens-release-notes.md#windows-holographic-version-20h2) hozzáadva HoloLens 2-es eszközökhöz:

- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) A kijelző kikapcsolásáig beállított idő zárolja az eszközt a kijelző kikapcsolásával.
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) A kijelző kikapcsolásáig beállított idő zárolja az eszközt a kijelző kikapcsolásával.
