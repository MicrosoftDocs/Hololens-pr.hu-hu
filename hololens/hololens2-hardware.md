---
title: HoloLens 2 hardver
description: Ismerje meg a 2. Microsoft HoloLens összetevőit, amely a microsoftos operációs rendszereket futtató, nem thered holografikus Microsoft-számítógép Windows 10.
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
ms.openlocfilehash: 88687559310a9abc24f34c416880e02caf535177
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924519"
---
# <a name="about-hololens-2"></a>A HoloLens 2

![HoloLens 2 oldalnézet](images/hololens2-breakdown.png)

Microsoft HoloLens 2. példa egy nem therett holografikus számítógép.  Pontosítja a HoloLens (1. generációs) által indított holografikus számítástechnika útját, hogy kényelmesebb és lebilincselőbb élményt nyújtson, több lehetőséggel párosítva a vegyes valóságban való együttműködéshez. A HoloLens 2 a [Windows Holographic OS-t](hololens-release-notes.md)futtatja, amely a Windows 10 "ízén" alapul, és egy robusztus, nagy teljesítményű és biztonságos platformot biztosít a felhasználóknak, rendszergazdáknak és fejlesztőknek. 

> [!NOTE]
> A legutóbbi Windows 11-bejelentés a Windows PC-s verziójára összpontosított. 2021 májusában elindítottunk egy jelentős operációsrendszer-frissítést [a](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) HoloLens 2-höz, és az őszre vonatkozó ügyfél-visszajelzések alapján dolgozunk egy hamarosan megjelenő kiadáson.

A HoloLens 2 használatához felhasználói fiók szükséges.

## <a name="hololens-components"></a>HoloLens-összetevők

- **Visor**. A HoloLens-érzékelőket és -kijelzőket tartalmazza. A vizort felfelé forgathatja, miközben a HoloLenst viseli.
- **Headband ( fejsáv)**. A HoloLensre való felhozásához használja a beállítási kereket a fejsáv kibontásához. Ha a HoloLens már a helyén van, húzza meg a rögzítőkereket úgy, hogy jobbra fordul, amíg a fejsáv el nem oszlott.
- **A fényerő gombok.** A HoloLens berakásakor a fényerejét jelző gombok a vizor bal oldalán, a völgy közelében vannak.
- **Hangerőgombok.** A HoloLens befogyatkozása esetén a hangerőszabályzó gombok a vizor jobb oldalán, a halom közelében vannak.
- **Bekapcsológomb.** A HoloLens bekapcsológombja a hátsó külső burkolat jobb oldalán található.
- **USB-C port.** A HoloLens berakásakor az USB-C port a hátsó külső fedés jobb oldalán, a Power gomb alatt található.

## <a name="in-the-box"></a>A mezőben

- **[A Berow (Betal) pad ..](https://www.microsoft.com/p/microsoft-hololens-2-brow-pad/90z10rsslqp0)** Szükség szerint eltávolíthatja és lecserélheti arow padot.
- **[Terhelési rekent](https://www.microsoft.com/p/microsoft-hololens-2-overhead-strap/8wxl8wmk1f7z)**. Ha mozgás közben berakja a HoloLenst, használja a többletterhelési szalagot, hogy az eszköz a helyén maradjon. Ha hosszabb ideig beköti a HoloLenst, a terhelési csökkentés kényelmesebbé teszi az eszköz elhasználódását.
- **[USB-C csatlakozó és kábel.](https://www.microsoft.com/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5)** A tápellátás az áramforráshoz csatlakozik. Az USB-C kábellel csatlakoztassa a HoloLenst a tápegységhez, vagy csatlakoztassa a HoloLenst a számítógépéhez.
- **Mikrofiber-** és . A HoloLens-vizor tisztítására használható.

### <a name="power-supply-details"></a>Energiaellátás részletei

A legjobb díjszabási mechanizmus a tápegység és az eszközhöz csatlakoztatott USB-kábel. A tápegység egy 18W-os kábel.  A 9V-t 2A-n látja el.

A díjszabás és a sebesség attól függően változhat, hogy az eszköz milyen környezetben fut.

Annak érdekében, hogy az eszköz a belső akkumulátor töltöttségi százaléka alatt is fenntartható/előre haladható legyen, legalább 15W-os kábelre kell csatlakoztatni.

## <a name="device-specifications"></a>Eszközspecifikációk

### <a name="display"></a>Megjelenítés

|   |   |
| - | - |
| Optika | Átfedő holografikus objektívek (waveguides) |
| Holografikus felbontás | 2k 3:2-es fénymotorok |
| Holografikus sűrűség | >2,5k radián (radiánonkénti világos pontok) |
| Szemalapú renderelés | Optimalizálás megjelenítése 3D szempozícióhoz |

### <a name="sensors"></a>Érzékelők

|   |   |
| - | - |
| Fejkövetés | 4 látható fénykamera |
| Szemkövetés | 2 Érzékelő (IR) kamerák |
| Mélység | 1 MP-es mélységérzékelő |
| Inertiális mérési egység (IMU) | Gyorsulásmérő, groscope, mérőmérő |
| Kamera | 8 MP-es továbbra is, 1080p30 videó |

![HoloLens 2-érzékelők](images/hololens2-front-view.png)

> [!NOTE]
> Ne fedje le a képen kihívott érzékelőket. A fejkövetési kamerák nagyon széles FOV-t kínálnak, és semmi sem lehet körülveszve amellett, hogy nem fedi el őket.

### <a name="audio-and-speech"></a>Hang és beszéd

|   |   |
| - | - |
| Mikrofontömb | 5 csatorna |
| Hangszórók | Beépített térbeli hang |

### <a name="compute-and-connectivity"></a>Számítás és kapcsolatok

|   |   |
| - | - |
| Rendszer lapkán | A Qualcomm Snapdragon 850 számítási platform [részletei](https://www.qualcomm.com/products/snapdragon-850-mobile-compute-platform) |
| Holografikus feldolgozási egység | Második generációs, egyénileg létrehozott holografikus feldolgozási egység |
| Memória | 4 GB-os LPDDR4x rendszer-DRAM |
| Tárolás | 64 GB-os UFS 2.1 |
| Wifi | 802.11ac 2x2 |
| Bluetooth | 5.0 |
| USB | USB Type-C DRP |

### <a name="power"></a>Energiaellátás

|   |   |
| - | - |
| Akkumulátor élettartama | 2–3 órányi aktív használat. Legfeljebb két hét készenléti idő. |
| Akkumulátor-technológia | [Lithium-akkumulátorok](https://www.microsoft.com/download/details.aspx?id=43388) |
| Díjszabási viselkedés | Teljesen működőképes a díjszabáskor |
| Hűtés típusa | Passzívan hűtött (ventilátorok nélkül) |
| Power Draw | Annak érdekében, hogy az eszköz a belső akkumulátor töltöttségi százaléka alatt is fenntartható/előre haladható legyen, legalább 15W-os kábelre kell csatlakoztatni. |

### <a name="fit"></a>Alkalmazás

|   |   |
| - | - |
| Méretezés | Egyméretű, állítható sávkal.  Beférkedő szemüveg |
| Tömeg | 566 gramm |

## <a name="device-capabilities"></a>Eszközképességek

### <a name="human-understanding"></a>Emberi értelem

|   |   |
| - | - |
| Kézkövetés | Kétmagos, teljes körűen kifejlett modell, közvetlen manipuláció |
| Szemkövetés | Valós idejű követés |
| Hang | Parancs és vezérlés az eszközön; Cortana természetes nyelve internetkapcsolattal |

### <a name="environment-understanding"></a>Környezetek ismertetése

|   |   |
| - | - |
| Hat szabadságfok (6DoF) követés | Világméretű pozíciókövetés |
| Térbeli leképezés | Valós idejű környezeti háló |
| Vegyes valóság rögzítése | Vegyes hologram- és fizikai környezeti fényképek és videók |

## <a name="pre-installed-software"></a>Előre telepített szoftverek

|   |   |
| - | - |
| Windows Holographic operációs rendszer | A [Windows Holographic os](hololens-release-notes.md)Windows 10 a felhasználók a HoloLens 2-n keresztül vegyes valóságú környezetben is használhatjak alkalmazásukat és játékukat.
| 3D-megjelenítő | [3D-megjelenítő](https://www.microsoft.com/p/3d-viewer/9nblggh42ths?activetab=pivot:overviewtab) lehetővé teszi a 3D modellek és animációk valós idejű megtekintését.|
| Cortana | [Cortana,](https://www.microsoft.com/p/cortana/9nffx4szz23l?activetab=pivot:overviewtab)a személyes hatékonyságnövelő segédje segít a fontos dolgokban maradni, és időt takarít meg a szükséges adatok megtalálására.  |
| Dynamics 365-útmutatók |  [A Dynamics 365-útmutatók segítségével](https://www.microsoft.com/p/microsoft-dynamics-365-guides/9n038fb42kkb?activetab=pivot:overviewtab) az alkalmazottak gyorsabban tanulhatnak új készségeket a HoloLens-eszközökön. |
| Dynamics 365 Remote Assist | [A Microsoft Dynamics 365 Remote Assist](https://www.microsoft.com/p/microsoft-dynamics-365-remote-assist/9p77qgw10k9m?activetab=pivot:overviewtab) lehetővé teszi a technikusok számára, hogy a Microsoft Teams vagy a Dynamics 365 Remote Assist használatával együttműködjön és megoldják a távoli közreműködőkkel kapcsolatos problémákat.  |
| Visszajelzési központ | [Visszajelzési központ](https://www.microsoft.com/p/feedback-hub/9nblggh4r32n?activetab=pivot:overviewtab) visszajelzést küldhet a Windowsról és az alkalmazásokról a javaslatainak vagy problémáinak megosztásával.  |
| Fájlkezelő | Fájlkezelő grafikus felhasználói felületet biztosít a fájlrendszerek eléréséhez. |
| Mail és Calendar | A [Mail és a Calendar](https://www.microsoft.com/p/mail-and-calendar/9wzdncrfhvqm#activetab=pivot:overviewtab) alkalmazással naprakész maradhat az e-mailjeiről, kezelheti az ütemezést, és kapcsolatban maradhat a névjegyekkel. |  
| Microsoft Edge | Microsoft Edge világosztályú teljesítményt nyújt több adatvédelemmel, nagyobb hatékonysággal és több értékkel a böngészés során. |
| Microsoft Store | A [Microsoft Store](https://www.microsoft.com) a HoloLens-sel használt alkalmazások és játékok forrása.|
| Filmek & TV | [A filmek & TV-vel](https://www.microsoft.com/p/movies-tv/9wzdncrfj3p2?activetab=pivot:overviewtab) egy egyszerű, gyors és elegáns alkalmazásban lehet a legújabb szórakozást kínálni. |
| OneDrive | [A OneDrive-val](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3?activetab=pivot:overviewtab) bárhonnan elérheti és szerkesztheti a fájlokat az összes eszközről.  |
| Fotók| [A Photos](https://www.microsoft.com/p/microsoft-photos/9wzdncrfjbh4?activetab=pivot:overviewtab) lehetővé teszi a fényképek és videók megtekintését és szerkesztését, a filmek készítése és a videók létrehozásához.  |
| Beállítások | A Beállítások alkalmazás az a hely, ahol részletesen testre szabhatja a Windows Holographic működését.  |
| Tippek | [A Tippek](https://www.microsoft.com/p/microsoft-tips/9wzdncrdtbjj?activetab=pivot:overviewtab) segítségével meglepő és kevésbé ismert dolgokat sajáthat el a Windows Holographicban. |

## <a name="device-certifications"></a>Eszköztanúsítások

### <a name="safety"></a>Biztonság

* [Termékbiztonság](https://support.microsoft.com/en-us/help/4023454/safety-information)
* [Termékbiztonsági figyelmeztetések és utasítások](https://support.microsoft.com/en-us/help/4558037/product-safety-warnings-and-instructions)
* Szembiztonság: A HoloLens 2 tesztelése megtörtént, és megfelel az ANSI Z87.1, CSA Z94.3 és EN 166 alapvető hatásvédelmi követelményeinek.
* [SAR-információk](https://support.microsoft.com/help/12673/mobile-devices-sar-information)

### <a name="regulatory-information"></a>Szabályozási információk
[HoloLens-szabályozás:](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)Többek között a hőmérséklettel, a megsemmisítéssel, a rádió- és TV-interferenciákkal kapcsolatos információkat tartalmaz.

## <a name="warranty-information"></a>Jótállási információk

Microsoft HoloLens 2., standard korlátozott [garanciával rendelkezik.](https://support.microsoft.com/topic/warranties-extended-service-plans-and-terms-conditions-for-your-device-eedf7a23-84a7-1a47-480b-0e10503eedf5) 


A vásárlásra Microsoft Store és értékesítési feltételek [vonatkoznak.](https://www.microsoft.com/storedocs/terms-of-sale?rtc=1) Minden értékesítés végleges. Nincs visszatérítés.

A HoloLens 2 megvásárlásával elfogadja a [szoftverlicenc-szerződést.](https://www.microsoft.com/Useterms/)

Nem 13 évesnél fiatalabb gyermekek számára tervezték.

## <a name="package-dimensions"></a>Csomagdimenziók

|      Mérés               |      Egységek metrika     |      Egységek száma     |
|--------------------------------|-----------------------|-------------------------|
|     Egység hossza                |     378,97 mm          |     14,920 hüvelyk       |
|     Egység szélessége                 |     247,90 mm          |     9,760 hüvelyk        |
|     Egységmélység                 |     163,07 mm          |     6,420 hüvelyk        |
|     Egység súlyozása                |     2,878 kg           |     6,344 kg           |
|     Exterior Shipper Length    |     446,00 mm          |     17,559 hüvelyk       |
|     Shipper Width (Szállítási szélesség)     |     257,99 mm          |     10,157 hüvelyk       |
|     Shipper Depth (Szállítási mélység)     |     172,01 mm          |     6,772 hüvelyk        |
|     Shipper Weight (Szállítási súly)    |     3,284 kg           |     7,240 font           |

> [!NOTE]
> - Egység: A HoloLens 2 fekete, kiskereskedelmi stílusú dobozt értékesítik.
> - Shipper:The packaging szállítmányozás a Unit körül.

## <a name="finding-the-serial-number"></a>A sorozatszám megkeresása

A HoloLens 2-eszközök sorozatszáma a vizor alatt van kinyomtatva.

1. Emelje fel az eszköz vizorát.
1. Nézze meg arow pad közelében.
1. A sorozatszám a burkolat közelében található.

<img src="images/serial-number-diagram-hl2.png" alt=Null width="625" height="903" />

A sorozatszám egy csatlakoztatott számítógépen is megtalálható:

1. Az eszköz csatlakoztatása
1. Nyissa meg **ezt a számítógépet a** fájlkezelőben
1. Kattintson a jobb **gombbal, és válassza a** HoloLens-eszköz tulajdonságai lehetőséget
1. Ez megjeleníti az eszköz sorozatának számát az alábbi képernyőképen látható módon.

<img src="images/ResetRecovery2.png" alt=null line width="400" height="600" />

## <a name="next-steps"></a>Következő lépés(ék)

> [!div class="nextstepaction"]
> [A HoloLens 2 kiadásainak összehasonlítása](hololens2-options.md)

> [!div class="nextstepaction"]
> [A HoloLens 2 beállítása és kezdete](hololens2-setup.md)
