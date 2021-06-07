---
title: Csatlakozás Bluetooth- és USB-C-eszközökhöz
description: A Bluetooth- és USB-C-eszközökhöz és -kiegészítőkhez való csatlakozás első lépések a HoloLens vegyes valóságú eszközeiről.
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
ms.openlocfilehash: ffae65a6e1c096242ae7a28c488896c65df1c62d
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379603"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Csatlakozás Bluetooth- és USB-C-eszközökhöz

## <a name="pair-bluetooth-devices"></a>Bluetooth-eszközök párosítása

A HoloLens 2 a Bluetooth-eszközök következő osztályát támogatja:

- [HID ::](https://docs.microsoft.com/windows-hardware/drivers/hid/)
    - Egér
    - Billentyűzet
- Hangkimeneti (A2DP) eszközök

A HoloLens 2 a következő Bluetooth API-kat támogatja:
- [REL-kiszolgáló](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) és [-ügyfél](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)
- [Rfcomm](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Előfordulhat, hogy telepítenie kell a megfelelő társalkalmazásokat a Microsoft Store hogy ténylegesen használva legyen a HID és a FOG ESZKÖZ.

A HoloLens (1. generációs) a Bluetooth-eszközök következő osztályát támogatja:

- Egér
- Billentyűzet
- [HoloLens (1. generációs) kattintás](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> Más Típusú Bluetooth-eszközök, például beszélők, headsetek, okostelefonok és játékpanelek elérhetőként érhetők el a HoloLens beállításaiban. Ezek az eszközök azonban nem támogatottak a HoloLensben (1. generációs verzió). További információkért lásd: [A HoloLens-beállítások felsorolják](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)az eszközöket, ha elérhetők, de az eszközök nem működnek.

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Bluetooth-billentyűzet vagy -egér párosítása

1. Kapcsolja be a billentyűzetet vagy az egeret, és tegye felderíthetővé. Ha meg szeretne ismerkedni az eszköz felderítésének mikéntjéről, keresse fel az eszközön található információkat (vagy a dokumentációt), vagy keresse fel a gyártó webhelyét.

1. Használja a Bloom kézmozdulatot (HoloLens (1. generációs)) vagy az indítási kézmozdulatot (HoloLens 2) a **Start** menüre, majd válassza a **Beállítások lehetőséget.**

1. Válassza **az Eszközök** lehetőséget, és ellenőrizze, hogy a Bluetooth be van-e va.  

1. Ha látja az eszköz nevét, válassza a **Pár** lehetőséget, majd kövesse az utasításokat.

## <a name="disable-bluetooth"></a>Bluetooth letiltása

Ez az eljárás kikapcsolja a Bluetooth-választó RF-összetevőit, és letilt minden Bluetooth-funkciót a Microsoft HoloLens.

1. Használja a Bloom kézmozdulatot (HoloLens (1. generációs)) vagy az indítási kézmozdulatot (HoloLens 2) a **Start** menüre, majd válassza a Beállítások  >  **Eszközök lehetőséget.**

1. Húzza a **Bluetooth csúszkakapcsolóját** a **Ki állásba.**

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: USB-C-eszközök csatlakoztatása

A HoloLens 2 az USB-C-eszközök következő osztályát támogatja:

- Tömeges tárolóeszközök (például ujjlenyomatos meghajtók)
- Ethernet-adapterek (beleértve az Ethernet+díjszabást)
- USB-C-to-3.5mm digitális hangadapterek
- USB-C digitális audio-headsetek (beleértve a headset-adaptereket és a díjszabást)
- USB-C külső mikrofonok ([Windows Holographic, 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) és újabb verziók)
- Vezetékes egér
- Vezetékes billentyűzet
- Kombinált PD hubok (USB A plusz PD-díjszabás)


> [!NOTE]
> Az ügyfelek visszajelzésére válaszul korlátozott támogatást engedélyeztünk a HoloLenshez USB-C-n keresztül közvetlenül a HoloLenshez kapcsolódó mobilkapcsolatok számára. További [információ: Connect to Cellular and 5G (Csatlakozás mobilhálózathoz](hololens-cellular.md) és 5G-hez).

### <a name="usb-c-external-microphone-support"></a>USB-C külső mikrofon támogatása

> [!IMPORTANT]
> Az USB-mikrofon csatlakoztatása nem lesz automatikusan beállítva **bemeneti eszközként.** USB-C-kábelek csatlakoztatása esetén a felhasználók megfigyelhetik, hogy a mikrofon hanganyaga automatikusan a mikrofonhoz lesz átirányítva, de a HoloLens operációs rendszer a belső mikrofontömböt a többi bemeneti eszköz fölé rangsorítja. **USB-C mikrofon használata érdekében kövesse az alábbi lépéseket.**

> [!NOTE]
> A külső mikrofonok a Windows [Holographic 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) vagy újabb verzióját megelőző buildek esetén nem használhatók. 

A felhasználók a Hangbeállítások panelen  választhatnak USB-C-hez csatlakoztatott külső mikrofonokat. Az USB-C-mikrofonok hívásra, felvételre stb. használhatók.

Nyissa meg a **Beállítások** alkalmazást, és válassza a **Rendszerhang**  >  **lehetőséget.**

![Hangbeállítások](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Ha külső mikrofonokat használ a **Remote Assist** segítségével, a felhasználóknak a "Hangeszközök kezelése" hivatkozásra kell kattintanunk.
>
> Ezután a legördülő menüben állítsa a  külső mikrofont Alapértelmezett vagy **Kommunikációs alapértelmezettre.** Az **Alapértelmezett beállítás** azt jelenti, hogy a külső mikrofon mindenhol használatban lesz.
>
> A **Kommunikáció alapértelmezett beállítása** azt jelenti, hogy a külső mikrofon a Remote Assistben és más kommunikációs alkalmazásokban lesz használva, de a HoloLens mic tömb továbbra is használható más feladatokhoz.

![Hangeszközök kezelése](images/usbc-mic-2.png)

<br>

![Mikrofon alapértelmezett beállítása](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Mi a helyzet a Bluetooth-mikrofonok támogatásával?

Sajnos a Bluetooth-mikrofonok jelenleg még nem támogatottak a HoloLens 2-ben.

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C-mikrofonok hibaelhárítása

Vegye figyelembe, hogy egyes USB-C-mikrofonok helytelenül jelentik magukat mikrofonként és *beszélőként* is. Ez a mikrofonnal, és nem a HoloLens-sel van probléma. Ha ezen mikrofonok valamelyikét a HoloLenshez csatlakoztatja, a hang elveszhet. Szerencsére van egy egyszerű javítás.  

A **Settings** System Sound  ->  **(Beállítások rendszerhangja)** lapon explicit módon állítsa be a beépített beszélők  ->   **(Analog Feature Audio Driver)** alapértelmezett **eszközként való beállítását.** A HoloLensnek akkor is meg kell emlékeznie erre a beállításra, ha a mikrofont eltávolítják, majd később újracsatlakoztatják.

![USB-C-mikrofonok hibaelhárítása](images/usbc-mic-4.png)
### <a name="usb-c-hubs"></a>USB-C hubok

Előfordulhat, hogy egyes felhasználóknak egyszerre több eszközt is csatlakoztatnia kell. Azok a felhasználók, akik [USB-C-mikrofont](#usb-c-external-microphone-support) és egy másik csatlakoztatott eszközt is használni szeretnék, az USB-C hubok az ügyfél igényeihez illeszkedhetnek. A Microsoft nem tesztelte ezeket az eszközöket, és nem is ajánlunk semmilyen konkrét márkát.

**Az USB-C hubra és a csatlakoztatott eszközökre vonatkozó követelmények:**

- A csatlakoztatott eszközökre nem lehet szükség illesztőprogram telepítésére.
- Az összes csatlakoztatott eszköz teljes energiafogyasztásnak 4,5 Watt alatt kell lennie.

## <a name="connect-to-miracast"></a>Csatlakozás a Miracasthoz

A Miracast használatának lépései a következők:

1. Tegye a következők egyikét:  

   - Nyissa meg **a Start menüt,** és válassza a **Megjelenítés ikont.**
   - Mondja a "Csatlakozás" szót, miközben a **Start menüre tekint.**  

1. A megjelenő eszközök listájában válasszon ki egy elérhető eszközt.

1. A kivetítés megkezdéséhez töltse ki a párosítást.
