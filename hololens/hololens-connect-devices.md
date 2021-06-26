---
title: Csatlakozás Bluetooth- és USB-C-eszközökhöz
description: Az első lépések a Bluetooth- és USB-C-eszközökhöz és -kiegészítőkhez való kapcsolódáshoz a HoloLens vegyes valóságú eszközeiről.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e02950bf6cb70e381e3bc5850509bc65267759c1
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924179"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Csatlakozás Bluetooth- és USB-C-eszközökhöz

## <a name="pair-bluetooth-devices"></a>Bluetooth-eszközök párosítása

A HoloLens 2 a Bluetooth-eszközök következő osztályát támogatja:

- [HID ::](https://docs.microsoft.com/windows-hardware/drivers/hid/)
    - Egér
    - Billentyűzet
- Hangkimeneti (A2DP) eszközök

A HoloLens 2 a következő Bluetooth API-kat támogatja:
- ANNAK [kiszolgálója](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) és [ügyfele](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)
- [Rfcomm](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Előfordulhat, hogy telepítenie kell a megfelelő társalkalmazásokat a Microsoft Store a HID és a AZDM-eszközök ténylegesen való használatához.

A HoloLens (1. generációs) a Bluetooth-eszközök következő osztályát támogatja:

- Egér
- Billentyűzet
- [HoloLens (1. generációs) clicker](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> A HoloLens beállításai között más Típusú Bluetooth-eszközök, például beszélők, headsetek, okostelefonok és játékpanelek is fel vannak sorolva. Ezek az eszközök azonban nem támogatottak a HoloLensben (1. generációs verzió). További információkért lásd: [A HoloLens-beállítások](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)listázza az eszközöket elérhetőként, de az eszközök nem működnek.

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Bluetooth-billentyűzet vagy -egér párosítása

1. Kapcsolja be a billentyűzetet vagy az egeret, és tegye felderíthetővé. Ha meg szeretne ismerkedni az eszköz felderítésének mikéntjével, keresse fel az eszközre vonatkozó információkat (vagy a dokumentációját), vagy keresse fel a gyártó webhelyét.

1. Használja a Bloom-kézmozdulatot (HoloLens (1. generációs)) vagy az indítási kézmozdulatot (HoloLens 2) a **Start** menüben, majd válassza a **Beállítások lehetőséget.**

1. Válassza **az Eszközök** lehetőséget, és ellenőrizze, hogy a Bluetooth be van-e stb.  

1. Ha látja az eszköz nevét, válassza a **Pár** lehetőséget, majd kövesse az utasításokat.

## <a name="disable-bluetooth"></a>Bluetooth letiltása

Ez az eljárás kikapcsolja a Bluetooth-választó rf-összetevőit, és letiltja az összes Bluetooth-funkciót a Microsoft HoloLens.

1. Használja a Bloom-kézmozdulatot (HoloLens (1. generációs)) vagy az indítási kézmozdulatot (HoloLens 2) a **Start** menüben, majd válassza a Beállítások  >  **Eszközök lehetőséget.**

1. Húzza a **Bluetooth csúszkakapcsolóját** a **Ki állásba.**

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: USB-C-eszközök csatlakoztatása

A HoloLens 2 az USB-C-eszközök következő osztályát támogatja:

- Tömeges tárolóeszközök (például ujjlenyomat-meghajtók)
- Ethernet-adapterek (beleértve az Ethernet+díjszabást)
- USB-C-to-3.5mm digitális hangadapterek
- USB-C digitális audio-headsetek (beleértve a headset adaptereket és a díjszabást)
- USB-C külső mikrofonok ([Windows Holographic, 21H1-es és](hololens-release-notes.md#windows-holographic-version-21h1) újabb verziók)
- Vezetékes egér
- Vezetékes billentyűzet
- Kombinált PD hubok (USB A plusz PD-díjszabás)


> [!NOTE]
> Az ügyfelek visszajelzésére válaszul korlátozott támogatást engedélyeztünk a HoloLenshez USB-C-n keresztül közvetlenül a HoloLenshez csatlakoztatott mobilkapcsolatok számára. További [információ: Connect to Cellular and 5G (Csatlakozás mobilhálózathoz](hololens-cellular.md) és 5G-hez).

### <a name="usb-c-external-microphone-support"></a>USB-C külső mikrofon támogatása

> [!IMPORTANT]
> Az USB-mikrofon csatlakoztatása nem lesz automatikusan beállítva **bemeneti eszközként.** USB-C-kábelek csatlakoztatása esetén a felhasználók megfigyelhetik, hogy a hanganyag automatikusan a mikrofonhoz lesz átirányítva, de a HoloLens operációs rendszer a belső mikrofontömböt a többi bemeneti eszköz fölé rangsorítja. **USB-C mikrofon használata érdekében kövesse az alábbi lépéseket.**

> [!NOTE]
> A külső mikrofonok nem használhatók a [Windows Holographic előtti, 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) vagy újabb verziójú buildekben. 

A felhasználók a Hangbeállítások panelen választhatnak USB-C-hez csatlakoztatott külső **mikrofonokat.** Az USB-C-mikrofonok hívásra, felvételre stb. használhatók.

Nyissa meg a **Beállítások** alkalmazást, és válassza a **System**  >  **Sound lehetőséget.**

![Hangbeállítások](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Ha külső mikrofonokat használ a **Remote Assist** segítségével, a felhasználóknak a "Hangeszközök kezelése" hivatkozásra kell kattintanunk.
>
> Ezután a legördülő menüben állítsa a  külső mikrofont Alapértelmezett vagy **Kommunikációs alapértelmezettre.** Az **Alapértelmezett beállítás** azt jelenti, hogy a külső mikrofon mindenhol használatban lesz.
>
> A **Kommunikáció alapértelmezett beállítása** azt jelenti, hogy a külső mikrofon a Remote Assist és más kommunikációs alkalmazásokban lesz használva, de a HoloLens mic tömb továbbra is használható más feladatokhoz.

![Hangeszközök kezelése](images/usbc-mic-2.png)

<br>

![Mikrofon alapértelmezett beállítása](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Mi a helyzet a Bluetooth-mikrofonok támogatásával?

Sajnos a Bluetooth-mikrofonok jelenleg még nem támogatottak a HoloLens 2-ben.

### <a name="usb-c-hubs"></a>USB-C hubok

Előfordulhat, hogy egyes felhasználóknak egyszerre több eszközt kell csatlakoztatnia. Azok a felhasználók, akik [USB-C-mikrofont](#usb-c-external-microphone-support) és egy másik csatlakoztatott eszközt is használni szeretnék, az USB-C hubok illeszkedhetnek az ügyfél igényeihez. A Microsoft nem tesztelte ezeket az eszközöket, és nem is ajánlunk semmilyen konkrét márkát.

**Az USB-C hubra és a csatlakoztatott eszközökre vonatkozó követelmények:**

- A csatlakoztatott eszközökre nem lehet szükség illesztőprogram telepítésére.
- Az összes csatlakoztatott eszköz teljes áramfelvételének 4,5 Energiafogyasztás alatt kell lennie.

## <a name="connect-to-miracast"></a>Csatlakozás a Miracasthoz

A Miracast használatának lépései a következők:

1. Tegye a következők egyikét:  

   - Nyissa meg **a Start menüt,** és válassza a **Megjelenítés ikont.**
   - Mondja a "Csatlakozás" parancsot, miközben a **Start menüre tekint.**  

1. A megjelenő eszközök listájában válasszon ki egy elérhető eszközt.

1. A kivetítés megkezdéséhez töltse ki a párosítást.
