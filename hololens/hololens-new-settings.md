---
title: Az új Beállítások alkalmazás bevezetése
description: Tudnivalók az új Beállítások alkalmazásról
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, beállítások, alkalmazásválasztó, kötet
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bf1a2080c15346843b9ea9b2d0dc93154e185107
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379658"
---
# <a name="new-settings-app"></a>Új beállítások alkalmazás

A [Windows Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójával bevezetjük a Settings alkalmazás új verzióját. Az új Beállítások alkalmazás új funkciókat és kibővített beállításokat tartalmaz a HoloLens 2-hez a következő területeken: Hang, Power & sleep, Network & Internet, Alkalmazások, Fiókok, Könnyű kezelés stb.

> [!NOTE]
> Mivel az új Beállítások alkalmazás különbözik az örökölt Beállítások alkalmazástól, a környezetben korábban elhelyezett beállítások ablakai frissítéskor el lesznek távolítva.

![Új beállítások alkalmazás kezdőlapja](images/new-settings-app.png)

**Új funkciók és beállítások**
- Beállítások keresése: a beállításokat a Beállítások kezdőlapon kulcsszavak vagy a beállítás nevének használatával keresheti meg.
- A rendszer > [színezése](hololens2-display.md#how-to-use-display-color-calibration)
    - Válasszon egy alternatív színprofilt a HoloLens 2-es megjelenítéshez.
- System > Sound:
  - Bemeneti és kimeneti hangeszközök: egymástól függetlenül válassza ki a bemeneti és kimeneti hangeszközöket (például Bluetooth-kábelen keresztüli hanglejátszást, vagy USB-C mikrofont használjon a hangbemenethez).
    > [!NOTE]
    > A HoloLens 2 nem támogatja a Bluetooth-mikrofonokat.
  - Alkalmazáskötet: az egyes alkalmazások kötetét egymástól függetlenül módosíthatja. Lásd: [alkalmazásonkénti kötetvezérlés.](holographic-home.md#per-app-volume-control)
- A > Power &: megadhatja, hogy az eszköz mikor legyen alvó üzemmódban egy bizonyos tétlenség után.
- Rendszer > akkumulátor: manuálisan engedélyezheti az takarékos üzemmód üzemmódot, vagy beállíthatja az akkumulátor töltöttségi küszöbértékét, amely takarékos üzemmód bekapcsolja automatikusan.
- USB> eszközök: alapértelmezés szerint letilthatja az USB-kapcsolatokat.
- Hálózati & internet:
  - Az USB-C Ethernet-adapterek mostantól a Hálózati adapterek & jelennek meg.
  - Elérhetőek az USB-C Ethernet-adapter beállításai, beleértve annak IP-címét is.
  - Mostantól engedélyezheti a repülőgép üzemmódot a HoloLens 2-ben.
- Alkalmazások: alaphelyzetbe állíthatja a fájl- és hivatkozástípusokhoz használt alapértelmezett alkalmazásokat. További információ: [Alapértelmezett alkalmazásválasztó.](holographic-home.md#default-app-picker)
- Fiókok > Egyéb felhasználók: az eszköztulajdonosok felhasználókat adhatnak hozzá, frissítheti a normál felhasználókat az eszköztulajdonosokra, visszaminősítheti az eszköztulajdonosokat a normál felhasználókra, és eltávolíthat felhasználókat.
- Könnyű kezelés: szövegméret és néhány vizuális hatás módosítása.

**Ismert problémák**
- A korábban elhelyezett Beállítások ablakokat a rendszer eltávolítja (lásd a fenti megjegyzést).
- A Továbbiakban nem nevezheti át az eszközt a Beállítások alkalmazással. A rendszergazdák a [Windows Autopilot for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) eszköznévsablon vagy az MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName csomópont használatával nevezheti át az eszközöket.
- Az Ethernet-oldal mindig egy virtuális Ethernet-eszközt ("UsbNcm") mutat.
- Előfordulhat, hogy az új Microsoft Edge akkumulátor-használata nem pontos, mivel az UWP-adapterréteg által támogatott Win32 asztali alkalmazás (hamarosan nem várható javítás).

