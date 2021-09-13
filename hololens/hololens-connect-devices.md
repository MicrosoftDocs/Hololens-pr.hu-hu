---
title: Csatlakozás usb Bluetooth C-eszközök csatlakoztatása
description: A vegyes valóságú eszközökről Bluetooth USB-C-eszközökhöz és -HoloLens való csatlakozás első lépések.
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
ms.openlocfilehash: d9c8b813ba54edbcfef8d1a32e641dad39a7f193
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036026"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Csatlakozás usb Bluetooth C-eszközök csatlakoztatása

## <a name="pair-bluetooth-devices"></a>Eszközök Bluetooth párosítása

HoloLens 2. a következő osztályokat támogatja a Bluetooth eszközök esetében:

- [HID ::](/windows-hardware/drivers/hid/)
    - Egér
    - Billentyűzet
- Hangkimeneti (A2DP) eszközök

HoloLens 2. száma a következő Bluetooth API-kat támogatja:
- ANNAK [kiszolgálója](/windows/uwp/devices-sensors/gatt-server) és [ügyfele](/windows/uwp/devices-sensors/gatt-client)
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Előfordulhat, hogy telepítenie kell a megfelelő társalkalmazásokat a Microsoft Store a HID és a KÉSZÜLÉK eszközök ténylegesen való használatához.

HoloLens (1. generációs) a következő osztályokat támogatja a Bluetooth eszközök esetében:

- Egér
- Billentyűzet
- [HoloLens (1. generációs) kattintás](hololens1-clicker.md)

> [!NOTE]
> Más típusú Bluetooth eszközök, például a beszélők, a headsetek, az okostelefonok és a játékpanelek a következő beállításokban HoloLens listában. Ezek az eszközök azonban nem támogatottak a HoloLens (1. generációs) eszközökön. További információért tekintse meg az [HoloLens Gépház elérhetőként listázza az eszközöket, de](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)az eszközök nem működnek.

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Billentyűzet vagy Bluetooth párosítása

1. Kapcsolja be a billentyűzetet vagy az egeret, és tegye felderíthetővé. Ha meg szeretne ismerkedni az eszköz felderítésével, keresse fel az eszközön található információkat (vagy annak dokumentációját), vagy keresse fel a gyártó webhelyét.

1. Használja a Bloom kézmozdulatot (HoloLens (1. gen)) vagy az indítási kézmozdulatot (HoloLens 2) a **Start** menüre való ugráshoz, majd válassza a **Gépház.**

1. Válassza **az Eszközök** lehetőséget, és győződjön meg arról, Bluetooth be van-e va.  

1. Ha látja az eszköz nevét, válassza a **Pár** lehetőséget, majd kövesse az utasításokat.

## <a name="disable-bluetooth"></a>Az Bluetooth letiltása

Ez az eljárás kikapcsolja a Bluetooth RF-összetevőit, és letiltja az összes Bluetooth funkciót Microsoft HoloLens.

1. Használja a Bloom kézmozdulatot (HoloLens (1. gen)) vagy az indítási kézmozdulatot (HoloLens 2) a **Start** menüben, majd válassza az **Gépház**  >  **lehetőséget.**

1. Húzza a csúszkakapcsolót **a Bluetooth** a **Ki állásba.**

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2. Csatlakozás USB-C-eszközök

HoloLens 2. a következő USB-C-eszközöket támogatja:

- Tömeges tárolóeszközök (például ujjlenyomat-meghajtók)
- Ethernet-adapterek (beleértve az Ethernet+díjszabást)
- USB-C-to-3.5mm digitális hangadapterek
- USB-C digitális audio-headsetek (beleértve a headset adaptereket és a díjszabást)
- USB-C külső mikrofonok ([Windows Holographic, 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) és újabb verziók)
- Vezetékes egér
- Vezetékes billentyűzet
- Kombinált PD hubok (USB A plusz PD-díjszabás)


> [!NOTE]
> Az ügyfelek visszajelzésére válaszul korlátozott támogatást engedélyeztünk az USB-C-n keresztül közvetlenül a HoloLens csatlakoztatott mobilhálózati kapcsolatokhoz. További [Csatlakozás lásd: Mobilhálózati és 5G-s](hololens-cellular.md) kapcsolat.

### <a name="usb-c-external-microphone-support"></a>USB-C külső mikrofon támogatása

> [!IMPORTANT]
> Az USB-mikrofon csatlakoztatása nem lesz automatikusan beállítva **bemeneti eszközként.** USB-C-kábelek csatlakoztatása esetén a felhasználók megfigyelhetik, hogy a hanganyag automatikusan a mikrofonhoz lesz átirányítva, de az HoloLens operációs rendszer a belső mikrofontömböt a többi bemeneti eszköz fölé rangsorítja. **USB-C mikrofon használata érdekében kövesse az alábbi lépéseket.**

> [!NOTE]
> A külső mikrofonok nem használhatók a [Holographic Windows 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) vagy újabb verziójú buildek esetén. 

A felhasználók a Hangbeállítások panelen választhatnak USB-C-hez csatlakoztatott külső **mikrofonokat.** Az USB-C-mikrofonok hívásra, felvételre stb. használhatók.

Nyissa meg **a Gépház** alkalmazást, és válassza a **System**  >  **Sound lehetőséget.**

![Hang Gépház.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Ha külső mikrofonokat használ a **Remote Assist** segítségével, a felhasználóknak a "Hangeszközök kezelése" hivatkozásra kell kattintanunk.
>
> Ezután a legördülő menüben állítsa a  külső mikrofont Alapértelmezett vagy **Kommunikációs alapértelmezettre.** Az **Alapértelmezett beállítás** azt jelenti, hogy a külső mikrofon mindenhol használatban lesz.
>
> A **Kommunikáció alapértelmezett beállítása** azt jelenti, hogy a külső mikrofon a Remote Assist és más kommunikációs alkalmazásokban lesz használva, de a HoloLens mic tömb továbbra is használható más feladatokhoz.

![Hangeszközök kezelése.](images/usbc-mic-2.png)

<br>

![Mikrofon alapértelmezett beállítása.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Mi a helyzet a Bluetooth támogatással?

Sajnos a Bluetooth mikrofonok jelenleg nem támogatottak a 2. HoloLens támogatottak.

### <a name="usb-c-hubs"></a>USB-C hubok

Előfordulhat, hogy egyes felhasználóknak egyszerre több eszközt kell csatlakoztatnia. Azok a felhasználók, akik [USB-C-mikrofont](#usb-c-external-microphone-support) és egy másik csatlakoztatott eszközt is használni szeretnék, az USB-C hubok illeszkedhetnek az ügyfél igényeihez. A Microsoft nem tesztelte ezeket az eszközöket, és nem is ajánlunk semmilyen konkrét márkát.

**Az USB-C hubra és a csatlakoztatott eszközökre vonatkozó követelmények:**

- A csatlakoztatott eszközökre nem lehet szükség illesztőprogram telepítésére.
- Az összes csatlakoztatott eszköz teljes áramfelvételének 4,5 Energiafogyasztás alatt kell lennie.

## <a name="connect-to-miracast"></a>Csatlakozás a Miracast

A Miracast kövesse az alábbi lépéseket:

1. Tegye a következők egyikét:  

   - Nyissa meg **a Start menüt,** és válassza a **Megjelenítés ikont.**
   - Mondja a "Csatlakozás" parancsot, miközben a **Start menüre tekint.**  

1. A megjelenő eszközök listájában válasszon ki egy elérhető eszközt.

1. A kivetítés megkezdéséhez töltse ki a párosítást.
