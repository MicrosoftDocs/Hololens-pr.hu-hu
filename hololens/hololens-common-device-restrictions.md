---
title: Gyakori eszközkorlátozások
description: Tartsa naprakészen a HoloLens vegyes valóságú eszköz gyakori eszközkorlátozásait és beállításait.
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
ms.openlocfilehash: e9c44466da375611f8864eae1b6e6ceea3ef9b09
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378005"
---
# <a name="common-device-restrictions"></a>Gyakori eszközkorlátozások 

Ez az útmutató segít az informatikai szakembereknek megérteni a vállalati operációs rendszerhez Windows 10 Holographic általánosabb felügyeleti lehetőségeket. Az MDM-rendszer dokumentációjában tájékozódhat arról, hogyan engedélyezik ezeket a szabályzatokat az MDM-szállító. Nem minden MDM-rendszer támogatja az útmutatóban ismertetett összes beállítást. Egyes szabályzatok OMA-URI XML-fájlokon keresztül támogatják az egyéni szabályzatokat. Lásd: [Microsoft Intune egyéni szabályzatok támogatása.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) Az elnevezési konvenciók az MDM-beszállítók között is eltérőek lehetnek.

## <a name="prevent-changing-of-settings"></a>Beállítások módosításának megakadályozása
Az alkalmazottak általában módosíthatjak bizonyos személyes eszközbeállításokat, amelyek zárolását a vállalati eszközökön is lehet. Az alkalmazottak interaktív módon módosíthatják a HoloLens egyes beállításait a beállítások felhasználói felületén. Az MDM használatával korlátozhatja, hogy a felhasználók milyen beállításokat módosíthatnak. A következő lista azokat a gyakran használt MDM-beállításokat sorolja fel, Windows 10 Holographic a beállítások korlátozásának konfigurálásában:
-   [VPN engedélyezése:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Engedélyezi a felhasználó számára a VPN-beállítások módosítását
-   [Wi-Fi manuális konfigurálás engedélyezése:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Lehetővé teszi, hogy a Wi-Fi MDM által kiépített hálózatokon kívül is létesítsen kapcsolatokat
-   [Manuális MDM-igénylések igénylésének engedélyezése](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Azt határozza meg, hogy a felhasználók törölhetik-e a munkahelyi fiókot (vagyis törölhetik-e az eszköz az MDM-rendszerből való törlését)

A [Windows Holographic 20H2-es](hololens-release-notes.md#windows-holographic-version-20h2) verziójának hozzáadása HoloLens 2-eszközökhöz:
- [Kiépítési csomag hozzáadásának engedélyezése:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Ha a felhasználók új kiépítési csomagokat adhatnak hozzá, új értékekkel felülírhatja őket.
- [Kiépítési csomag eltávolításának engedélyezése:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Váltógomb, ha a felhasználók eltávolítják a kiépítési csomagokat, így válthatnak a korábban zárolt beállítások között.

További részletek a szabályzatbeállításokról a HoloLens által támogatott [szabályzat-CSP-k között](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Hardverkorlátozások
Windows 10 Holographic eszközök a legtechnológiásbb technológiát használják, amely olyan népszerű hardverszolgáltatásokat tartalmaz, mint a kamerák, mikrofonok, beszélők, USB-adapterek, Bluetooth-interfészek és Wi-Fi. A hardverkorlátozások segítségével szabályozhatja ezen funkciók rendelkezésre állását.
Az alábbi lista azokat a gyakran használt MDM-beállításokat sorolja fel, Windows 10 Holographic hardverkorlátozások konfigurálásában támogatott:

> [!NOTE]
> Ezen hardverkorlátozások némelyike hatással van a kapcsolatra, és segít az adatvédelemben.

-   [Wi-Fi engedélyezése:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Azt határozza meg, hogy a felhasználók engedélyezhetik-e és használhatják-e a Wi-Fi-választógombot az eszközeiken.
-   [USB-kapcsolat engedélyezése:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Azt határozza meg, hogy az USB-kapcsolat engedélyezve van-e (nincs hatással az USB-feltöltésre).
-   [Bluetooth engedélyezése:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Azt határozza meg, hogy a felhasználók engedélyezhetik-e és használhatják-e a Bluetooth-választógombot az eszközeiken.
-   [Kamera korlátozása:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Meghatározza, hogy a Windows-alkalmazások hozzáférhetnek-e a kamerához.
-   [Mikrofonok korlátozása:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Meghatározza, hogy a Windows-alkalmazások hozzáférhetnek-e a mikrofonhoz.

A [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) a HoloLens 2-eszközökhöz hozzáadva. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) A kijelző kikapcsolásáig beállított idő zárolja az eszközt a kijelző kikapcsolásával. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) A kijelző kikapcsolásáig beállított idő zárolja az eszközt a kijelző kikapcsolásával. 
