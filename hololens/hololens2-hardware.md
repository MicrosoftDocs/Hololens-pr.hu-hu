---
title: HoloLens 2 hardver
description: Ismerje meg a 2. Microsoft HoloLens összetevőit, amely a microsoftos operációs rendszereket futtató, nem thered holografikus Microsoft-Windows 10.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 10/20/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: c1d83577400126903a80999c46ddaeabddaba029
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036129"
---
# <a name="about-hololens-2"></a>A 2 HoloLens ről

![HoloLens 2 oldalnézet.](images/hololens2-breakdown.png)

Microsoft HoloLens 2. szám egy nem therett holografikus számítógép.  Pontosítja a HoloLens (1. generációs) által indított holografikus számítástechnika utazását, hogy kényelmesebb és magával ragadó élményt nyújtson, és több lehetőség legyen a vegyes valóságban való együttműködésre. HoloLens 2. verziója a [Windows Holographic OS-ben](hololens-release-notes.md)fut, amely a Windows 10 "ízén" alapul, és robusztus, nagy teljesítményű és biztonságos platformot biztosít a felhasználóknak, rendszergazdáknak és fejlesztőknek. 

> [!NOTE]
> A Windows 11-es bejelentése a legújabb PC-s verzióra Windows. 2021 májusában elindítottunk egy jelentős operációsrendszer-frissítést HoloLens 2. kiadásra, és az őszre vonatkozó ügyfél-visszajelzések alapján dolgozunk egy hamarosan megjelenő kiadáson. [](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067)

A 2. HoloLens felhasználói fiók szükséges.

## <a name="hololens-components"></a>HoloLens összetevők

- **Visor**. A HoloLens és kijelzőit tartalmazza. A vizort felfelé forgathatja, miközben a vizort HoloLens.
- **Headband ( fejsáv)**. A tengelyre HoloLens a beállítókerékkel bontsa ki a fejsávot. A HoloLens után húzza meg a rögzítőkereket úgy, hogy jobbra fordul, amíg a fejsáv el nem oszlott.
- **A fényerő gombok.** Ha be van HoloLens, a fényerejét jelző gombok a vizor bal oldalán, a halom közelében vannak.
- **Hangerőgombok.** Ha a HoloLens, a hangerőszabályzó gombok a vizor jobb oldalán, a halom közelében vannak.
- **Bekapcsológomb.** A HoloLens bekapcsológomb a hátsó külső burkolat jobb oldalán található.
- **USB-C port.** Ha be HoloLens, az USB-C-port a hátsó külső fedés jobb oldalán található a Tápkapcsoló alatt.

## <a name="in-the-box"></a>A mezőben

- **[A Berow (Betal) pad ..](https://www.microsoft.com/p/microsoft-hololens-2-brow-pad/90z10rsslqp0)** Szükség szerint eltávolíthatja és lecserélheti arow padot.
- **[Terhelési rekent](https://www.microsoft.com/p/microsoft-hololens-2-overhead-strap/8wxl8wmk1f7z)**. Ha mozgás közben berakja a HoloLens, használja a terhelési szalagot, hogy az eszköz a helyén maradjon. Ha hosszabb ideig HoloLens az eszközt, a terhelési csökkentés kényelmesebbé teszi az eszköz elhasználódását.
- **[USB-C csatlakozó és kábel.](https://www.microsoft.com/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5)** A tápellátás az áramforráshoz csatlakozik. Az USB-C kábellel csatlakoztassa a HoloLens a tápegységhez a díjszabáshoz, vagy csatlakoztassa HoloLens számítógépéhez.
- **Mikrofiber-** és . A vizor tisztítására HoloLens használható.

### <a name="power-supply-details"></a>Energiaellátás részletei

A legjobb díjszabási mechanizmus a tápegység és az eszközhöz csatlakoztatott USB-kábel. A tápegység egy 18W-os kábel.  A 9V-t 2A-n látja el.

A díjszabás és a sebesség attól függően változhat, hogy az eszköz milyen környezetben fut.

Annak érdekében, hogy az eszköz a belső akkumulátor töltöttségi százaléka alatt is fenntartható/előre haladható legyen, legalább 15W-os kábelre kell csatlakoztatni.

## <a name="device-specifications"></a>Eszközspecifikációk

### <a name="display"></a>Megjelenítés

|   | &nbsp; |
|---|---|
| **Optika** | Átfedő holografikus objektívek (waveguides) |
| **Holografikus felbontás** | 2k 3:2-es fénymotorok |
| **Holografikus sűrűség** | >2,5k radián (radiánonkénti világos pontok) |
| **Szemalapú renderelés** | Optimalizálás megjelenítése 3D szempozícióhoz |

### <a name="sensors"></a>Érzékelők

|   | &nbsp; |
|---|---|
| **Fejkövetés** | 4 látható fénykamera |
| **Szemkövetés** | 2 Érzékelő (IR) kamerák |
| **Mélység** | 1 MP-es mélységérzékelő |
| **Inertiális mérési egység (IMU)** | Gyorsulásmérő, groscope, mérőmérő |
| **Fényképezőgép** | 8 MP-es továbbra is, 1080p30 videó |

![HoloLens 2 érzékelő.](images/hololens2-front-view.png)

> [!NOTE]
> Ne fedje le a képen kihívott érzékelőket. A fejkövetési kamerák nagyon széles FOV-t kínálnak, és semmi sem lehet körülveszve amellett, hogy nem fedi el őket.

### <a name="audio-and-speech"></a>Hang és beszéd

|   | &nbsp; |
|---|---|
| **Mikrofontömb** | 5 csatorna |
| **Hangszórók** | Beépített térbeli hang |

### <a name="compute-and-connectivity"></a>Számítás és kapcsolatok

|   | &nbsp; |
|---|---|
| **Rendszer lapkán** | A Qualcomm Snapdragon 850 számítási platform [részletei](https://www.qualcomm.com/products/snapdragon-850-mobile-compute-platform) |
| **Holografikus feldolgozási egység** | Második generációs, egyénileg létrehozott holografikus feldolgozási egység |
| **Memória** | 4 GB-os LPDDR4x rendszer-DRAM |
| **Storage** | 64 GB-os UFS 2.1 |
| **Wi-Fi** | 802.11ac 2x2 |
| **Bluetooth** | 5.0 |
| **USB** | USB Type-C DRP |

### <a name="power"></a>Energiaellátás

|   | &nbsp; |
|---|---|
| **Akkumulátor élettartama** | 2–3 órányi aktív használat. Legfeljebb két hét készenléti idő. |
| **Akkumulátor-technológia** | [Lithium-akkumulátorok](https://www.microsoft.com/download/details.aspx?id=43388) |
| **Díjszabási viselkedés** | Teljesen működőképes a díjszabáskor |
| **Hűtés típusa** | Passzívan hűtött (ventilátorok nélkül) |
| **Power Draw** | Annak érdekében, hogy az eszköz a belső akkumulátor töltöttségi százaléka alatt is fenntartható/előre haladható legyen, legalább 15W-os kábelre kell csatlakoztatni. |

### <a name="fit"></a>Alkalmazás

|   | &nbsp; |
|---|---|
| **Méretezés** | Egyetlen méret állítható sávkal.  Napszemüvegek felett elfér |
| **Tömeg** | 566 gramm |

## <a name="device-capabilities"></a>Eszközképességek

### <a name="human-understanding"></a>Emberi értelem

|   | &nbsp; |
|---|---|
| **Kézkövetés** | Kétmagos, teljesen kifejlett modell, közvetlen manipuláció |
| **Szemkövetés** | Valós idejű követés |
| **Hang** | Az eszköz vezérlése és vezérlése; Cortana nyelv használata internetkapcsolattal |

### <a name="environment-understanding"></a>Környezetértek ismertetése

|   | &nbsp; |
|---|---|
| **Hat szabadságfok (6DoF) nyomon követése** | Világméretű pozíciókövetés |
| **Térbeli leképezés** | Valós idejű környezeti háló |
| **Vegyes valóság rögzítése** | Vegyes hologram és fizikai környezet – fényképek és videók |

## <a name="pre-installed-software"></a>Előre telepített szoftverek

| &nbsp; | &nbsp; |
|---|---|
| **Windows Holografikus operációs rendszer** | A [Windows Holographic OS-Windows 10](hololens-release-notes.md)a felhasználók a 2. verzión keresztül vegyes valóságú környezetben is használhatnak alkalmazásokat HoloLens játékokat.
| **3D-megjelenítő** | [3D-megjelenítő](https://www.microsoft.com/p/3d-viewer/9nblggh42ths?activetab=pivot:overviewtab) lehetővé teszi a 3D modellek és animációk valós idejű megtekintését.|
| **Cortana** | [Cortana,](https://www.microsoft.com/p/cortana/9nffx4szz23l?activetab=pivot:overviewtab)a személyi hatékonyságnövelő segéd segítségével mindig a fontos dolgokon maradhat, és időt takaríthat meg a szükséges eredmények megtalálásában.  |
| **Dynamics 365-útmutatók** |  [A Dynamics 365-útmutatók segítségével az](https://www.microsoft.com/p/microsoft-dynamics-365-guides/9n038fb42kkb?activetab=pivot:overviewtab) alkalmazottak gyorsabban tanulhatnak új készségeket a HoloLens eszközökön. |
| **Dynamics 365 Remote Assist** | [A Microsoft Dynamics 365 Remote Assist](https://www.microsoft.com/p/microsoft-dynamics-365-remote-assist/9p77qgw10k9m?activetab=pivot:overviewtab) lehetővé teszi a technikusok számára, hogy együttműködhetnek a távoli közreműködőkkel és oldják meg a problémákat a Microsoft Teams vagy a Dynamics 365 Remote Assist használatával.  |
| **Visszajelzési központ** | [Visszajelzési központ](https://www.microsoft.com/p/feedback-hub/9nblggh4r32n?activetab=pivot:overviewtab) visszajelzést adhat a Windows és alkalmazásokról a javaslatok vagy problémák megosztásával.  |
| **Fájlkezelő** | Fájlkezelő grafikus felhasználói felületet biztosít a fájlrendszerek eléréséhez. |
| **Mail és Calendar** | A [Mail és a Calendar](https://www.microsoft.com/p/mail-and-calendar/9wzdncrfhvqm#activetab=pivot:overviewtab) alkalmazással naprakész maradhat e-mailjeiről, kezelheti az ütemezést, és kapcsolatban maradhat a kapcsolattartóival. |
| **Microsoft Edge** | Microsoft Edge világosztályú teljesítményt nyújt, és böngészés közben nagyobb adatvédelmet, nagyobb hatékonyságot és több értéket biztosít. |
| **Microsoft Store** | A [Microsoft Store](https://www.microsoft.com) a forrás az olyan alkalmazásokhoz és játékokhoz, amelyek a HoloLens.|
| **Filmek & TV** | [A filmek & a legújabb](https://www.microsoft.com/p/movies-tv/9wzdncrfj3p2?activetab=pivot:overviewtab) szórakozást egy egyszerű, gyors és elegáns alkalmazásban kínálják. |
| **OneDrive** | [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3?activetab=pivot:overviewtab) segítségével bárhonnan elérheti és szerkesztheti az összes eszközén található fájlokat.  |
| **Fotók** | [A Photos](https://www.microsoft.com/p/microsoft-photos/9wzdncrfjbh4?activetab=pivot:overviewtab) lehetővé teszi a fényképek és videók megtekintését és szerkesztését, filmek készítése és videók létrehozásához.  |
| **Beállítások** | A Gépház az a hely, ahol testre szabhatja a Holographic Windows működését.  |
| **Tippek** | [Tippek](https://www.microsoft.com/p/microsoft-tips/9wzdncrdtbjj?activetab=pivot:overviewtab) segítségével meglepő és kevésbé ismert dolgokat sajáthat el, amelyekre a Holographic Windows van. |

## <a name="device-certifications"></a>Eszköztanúsítások

### <a name="safety"></a>Biztonság

* [Termékbiztonság](https://support.microsoft.com/en-us/help/4023454/safety-information)
* [Termékbiztonsági figyelmeztetések és utasítások](https://support.microsoft.com/en-us/help/4558037/product-safety-warnings-and-instructions)
* Szembiztonság: HoloLens 2. szabvány tesztelése megtörtént, és megfelel az ANSI Z87.1, CSA Z94.3 és EN 166 alapvető hatásvédelmi követelményeinek.
* [SAR-információk](https://support.microsoft.com/help/12673/mobile-devices-sar-information)

### <a name="regulatory-information"></a>Szabályozási információk
[HoloLens:](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)Többek között a hőmérsékletre, a megsemmisítésre, a rádió- és tv-interferenciára vonatkozó információkat tartalmaz.

## <a name="warranty-information"></a>Jótállási információk

Microsoft HoloLens 2.) standard korlátozott [jótállási garanciával rendelkezik.](https://support.microsoft.com/topic/warranties-extended-service-plans-and-terms-conditions-for-your-device-eedf7a23-84a7-1a47-480b-0e10503eedf5) 


A vásárlásra Microsoft Store [használati feltételek és értékesítések vonatkoznak.](https://www.microsoft.com/storedocs/terms-of-sale?rtc=1) Minden értékesítés végleges. Nincs visszatérítés.

A 2 HoloLens megvásárlása esetén elfogadja a [szoftverlicenc-szerződést.](https://www.microsoft.com/Useterms/)

Nem 13 évesnél fiatalabb gyermekek számára tervezték.

## <a name="package-dimensions"></a>Csomagdimenziók

|      Mérés               |      Egységek metrika     |      Egységek száma     |
|--------------------------------|-----------------------|-------------------------|
|     Egység hossza                |     378,97 mm          |     14,920 hüvelyk       |
|     Egység szélessége                 |     247,90 mm          |     9,760 hüvelyk        |
|     Egység mélysége                 |     163,07 mm          |     6,420 hüvelyk        |
|     Egység súlyozása                |     2,878 kg           |     6,344 kg           |
|     Exterior Shipper Length    |     446,00 mm          |     17,559 hüvelyk       |
|     Shipper Width (Szállítási szélesség)     |     257,99 mm          |     10,157 hüvelyk       |
|     Exterior Shipper Depth     |     172,01 mm          |     6,772 hüvelyk        |
|     Exterior Shipper Weight    |     3,284 kg           |     7,240 font           |

> [!NOTE]
> - Egység: A 2. HoloLens fekete, kiskereskedelmi stílusú dobozt értékesítik.
> - Shipper: The packaging szállítmányozás a Unit körül.

## <a name="finding-the-serial-number"></a>A sorozatszám megkeresása

A vizor alatt HoloLens 2 eszköz sorozatszáma látható.

1. Emelje fel az eszköz vizorát.
1. Keresse meg arow pad közelében.
1. A sorozatszám a fogasság közelében található.

   <img src="images/serial-number-diagram-hl2.png" alt=Null width="625" height="903" />

A sorozatszám egy csatlakoztatott számítógépen is megtalálható:

1. Az eszköz csatlakoztatása
1. Lépjen az **Ez a számítógép a** fájlkezelőben lapra
1. Kattintson a jobb **gombbal, és válassza** a HoloLens tulajdonságait
1. Ez megjeleníti az eszköz sorozatszámát az alábbi képernyőképen látható módon.

   <br/><img src="images/ResetRecovery2.png" alt=null line width="400" height="600" />

## <a name="next-steps"></a>Következő lépés(ék)

> [!div class="nextstepaction"]
> [A HoloLens 2 kiadás összehasonlítása](hololens2-options.md)

> [!div class="nextstepaction"]
> [A 2. HoloLens beállítása és kezdete](hololens2-setup.md)
