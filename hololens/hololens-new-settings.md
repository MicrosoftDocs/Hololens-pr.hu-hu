---
title: Az új Gépház bevezetése
description: Tudnivalók az új Gépház alkalmazásról
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, beállítások, alkalmazásválasztó, kötet
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 4187ae99a25fc6dd3f407410da27568d4b2b6865934b0c615680f295ec7977be
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663066"
---
# <a name="new-settings-app"></a>Új Gépház alkalmazás

A [Windows Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójával bevezetjük a Gépház új verzióját. Az új Gépház alkalmazás új funkciókat és kibővített beállításokat tartalmaz a 2. HoloLens-hez a következő területeken: Hang, Power & sleep, Network & Internet, Alkalmazások, Fiókok, Könnyű kezelés stb.

> [!NOTE]
> Mivel az új Gépház alkalmazás különbözik az örökölt Gépház-alkalmazástól, a Gépház környezetben korábban elhelyezett összes Gépház el lesz távolítva frissítéskor.

![Új Gépház kezdőlapja](images/new-settings-app.png)

**Új funkciók és beállítások**
- Gépház keresés: a beállításokat a kezdőlapon Gépház kulcsszavak vagy a beállítás nevének használatával keresheti meg.
- A rendszer > [színezése](hololens2-display.md#how-to-use-display-color-calibration)
    - Válasszon egy alternatív színprofilt a HoloLens 2-es megjelenítéshez.
- System > Sound:
  - Hangbemeneti és -kimeneti eszközök: egymástól függetlenül válassza ki a bemeneti és kimeneti hangeszközöket (például egy hanganyagot Bluetooth hanganyagon keresztül, vagy használjon USB-C mikrofont a hangbemenethez).
    > [!NOTE]
    > Bluetooth 2. HoloLens nem támogatja a mikrofonokat.
  - Alkalmazáskötet: az egyes alkalmazások kötetének egymástól független beállítása. Lásd: [alkalmazáskötet-vezérlőnként.](holographic-home.md#per-app-volume-control)
- A > Power &: megadhatja, hogy az eszköz mikor alvó üzemmódba ússzanak egy bizonyos tétlenség után.
- Rendszer > Akkumulátor: manuálisan engedélyezze az takarékos üzemmód üzemmódot, vagy állítson be egy akkumulátor-küszöbértéket, amely takarékos üzemmód bekapcsolja automatikusan.
- USB> eszközök: alapértelmezés szerint letilthatja az USB-kapcsolatokat.
- Hálózati & internet:
  - Az USB-C Ethernet-adapterek mostantól megjelennek a Hálózati adapterek & interneten.
  - Az USB-C Ethernet-adapter beállításai már elérhetők, beleértve annak IP-címét is.
  - Mostantól a 2. HoloLens engedélyezheti a repülőgép üzemmódot.
- Alkalmazások: alaphelyzetbe állíthatja a fájl- és hivatkozástípusokhoz használt alapértelmezett alkalmazásokat. További információ: [Alapértelmezett alkalmazásválasztó.](holographic-home.md#default-app-picker)
- Fiókok > felhasználók: az eszköztulajdonosok felhasználókat adhatnak hozzá, frissítheti az általános felhasználókat az eszköztulajdonosokra, visszaminősítheti az eszköztulajdonosokat normál felhasználókra, és eltávolíthat felhasználókat.
- Könnyű kezelés: szövegméret és néhány vizuális hatás módosítása.

**Ismert problémák**
- A korábban Gépház windows el lesz távolítva (lásd a fenti megjegyzést).
- A továbbiakban nem nevezheti át az eszközt a Gépház alkalmazással. A rendszergazdák az HoloLens 2 eszköznév-sablonhoz Windows [Autopilot](hololens2-autopilot.md) vagy az MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName csomópont használatával nevezheti át az eszközöket.
- Az Ethernet-oldalon mindig megjelenik egy virtuális Ethernet-eszköz ("UsbNcm").
- Előfordulhat, hogy az új Microsoft Edge akkumulátor-használata az UWP-adapterréteg által támogatott Win32 asztali alkalmazás természetéből adódóan nem pontos (hamarosan nem várható javítás).

