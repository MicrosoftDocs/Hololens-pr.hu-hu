---
title: Az új Gépház bevezetése
description: További tudnivalók az új Gépház alkalmazásról
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, beállítások, alkalmazásválasztó, kötet
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: e6da84c180ef596b63b6d41229bd094354ab1221
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640168"
---
# <a name="new-settings-app"></a>Új Gépház alkalmazás

A [Windows Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójával bevezetjük a Gépház új verzióját. Az új Gépház alkalmazás új funkciókat és kibővített beállításokat tartalmaz a HoloLens 2-hez a következő területeken: Hang, Power & sleep, Network & Internet, Alkalmazások, Fiókok, Könnyű kezelés stb.

> [!NOTE]
> Mivel az új Gépház alkalmazás különbözik az örökölt Gépház-alkalmazástól, a Gépház környezetben korábban elhelyezett összes Gépház frissítéskor el lesz távolítva.

![Új Gépház alkalmazás kezdőlapja](images/new-settings-app.png)

**Új funkciók és beállítások**
- Gépház keresés: keressen rá a beállításokra a Gépház a kezdőlapon kulcsszavak vagy a beállítás nevének használatával.
- A rendszer > [színezése](hololens2-display.md#how-to-use-display-color-calibration)
    - Válasszon egy alternatív színprofilt a HoloLens 2 megjelenítéshez.
- System > Sound:
  - Bemeneti és kimeneti hangeszközök: egymástól függetlenül válassza ki a bemeneti és kimeneti hangeszközöket (például hanganyagot figyelhet Bluetooth hanganyagokkal, vagy USB-C mikrofont használhat a hangbemenethez).
    > [!NOTE]
    > Bluetooth 2. HoloLens nem támogatja a mikrofonokat.
  - Alkalmazáskötet: az egyes alkalmazások kötetét egymástól függetlenül módosíthatja. Lásd: [alkalmazásonkénti kötetvezérlés.](holographic-home.md#per-app-volume-control)
- A > Power & alvó üzemmódban: válassza ki, hogy az eszköz mikor alvó üzemmódba ússzanak egy bizonyos tétlenség után.
- Rendszer > akkumulátor: manuálisan engedélyezheti az takarékos üzemmód üzemmódot, vagy beállíthatja az akkumulátor töltöttségi küszöbértékét, amely takarékos üzemmód bekapcsolja automatikusan.
- USB> eszközök: alapértelmezés szerint letilthatja az USB-kapcsolatokat.
- Hálózati & internet:
  - Az USB-C Ethernet-adapterek mostantól a Hálózati adapterek & jelennek meg.
  - Elérhetőek az USB-C Ethernet-adapter beállításai, beleértve annak IP-címét is.
  - Mostantól a 2. HoloLens engedélyezheti a repülőgép üzemmódot.
- Alkalmazások: alaphelyzetbe állíthatja a fájl- és hivatkozástípusokhoz használt alapértelmezett alkalmazásokat. További információ: [Alapértelmezett alkalmazásválasztó.](holographic-home.md#default-app-picker)
- Fiókok > Egyéb felhasználók: az eszköztulajdonosok felhasználókat adhatnak hozzá, frissítheti a normál felhasználókat az eszköztulajdonosokra, visszaminősítheti az eszköztulajdonosokat az általános felhasználókra, és eltávolíthat felhasználókat.
- Könnyű kezelés: szövegméret és néhány vizuális hatás módosítása.

**Ismert problémák**
- A korábban Gépház el lesz távolítva (lásd a fenti megjegyzést).
- A továbbiakban nem nevezheti át az eszközt a Gépház alkalmazással. A rendszergazdák az HoloLens 2 eszköznév-sablonhoz Windows [Autopilot](hololens2-autopilot.md) vagy az MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName csomópont használatával nevezheti át az eszközöket.
- Az Ethernet-oldal mindig egy virtuális Ethernet-eszközt ("UsbNcm") mutat.
- Előfordulhat, hogy az új Microsoft Edge akkumulátor-használata az UWP-adapterréteg által támogatott Win32 asztali alkalmazás természetéből adódóan nem lesz pontos (hamarosan nem várható javítás).

