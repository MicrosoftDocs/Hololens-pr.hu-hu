---
title: Vegyes valóságú fényképek és videók rögzítése, rögzítése és megosztása
description: Megtudhatja, hogyan rögzítheti, rögzítheti és megtekintheti a vegyes valóságú fényképeket és videókat HoloLens vegyes valóságú eszközökkel. Megtudhatja, hogyan oszthat meg Miracast vagy összegyűjtött fájlokon keresztül.
keywords: hololens, fénykép, videó, capture, mrc, mixed reality capture, photos, camera, miracast, stream, livestream, demo, record
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 54e9959c03b69db39ff2738e5d4f41f9740ae562b38e8d85998521a4733edad7
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664859"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Vegyes valóságú fényképek és videók létrehozása

HoloLens teszi lehetővé a felhasználók számára, hogy a való világot a digitális világgal keverik.  A vegyes valóságú rögzítés (MRC) lehetővé teszi, hogy ezt a élményt fényképként vagy videóként rögzítse, vagy valós időben ossza meg másokkal.

A vegyes valóságú rögzítés személyes nézőpontot használ, hogy mások is látják a hologramokat. Külső nézőponthoz használja a [spektátornézetet.](/windows/mixed-reality/spectator-view) A Spektátor nézet különösen hasznos a bemutatókhoz.

Bár a videók ismerősök és munkatársak között is megoszthatók, a videók másoknak is segíthetnek megtanítani egy alkalmazás használatát, vagy problémákat kommunikálni az alkalmazásokkal és a felhasználói élményekkel.

> [!NOTE]
> Ha nem tud vegyes valóságot rögzíteni, és a HoloLens munkahelyi eszköz, forduljon a rendszergazdához. A kamerához való hozzáférés céges szabályzattal korlátozható.

## <a name="capture-a-mixed-reality-photo"></a>Vegyes valóságú fénykép rögzítése

A vegyes valóságról többféleképpen is fotót lehet HoloLens; Használhatja a hardvergombokat, a hangot vagy a Start menü.

### <a name="hardware-buttons-to-take-photos"></a>Hardvergombok fényképekhez

Az aktuális nézet gyorsképének megtekintéséhez egyszerre nyomja le a hangerőt felfelé és lefelé gombokkal.  Ez egy kicsit hasonló a HoloLens vagy a nyomtatási képernyő verziójához.

- [Gombhelyek a 2 HoloLens n](hololens2-hardware.md)
- [Gombhelyek a HoloLens (1. generációs)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> Ha három **másodpercig tartja** a hangerőt és a hangerőt 3 másodpercig, akkor nem fényképet készít, hanem videót készít.  A rögzítés leállításhoz egyszerre  koppintson a **fel-** és lekötet gombokra.

### <a name="voice-commands-to-take-photos"></a>Hangparancsok fényképekhez

A HoloLens 2., 2004-es (és újabb) verziójában mondja el a "Kép leképe" szót.

A HoloLens (1. generációs) vagy HoloLens 2. HoloLens 1903-as verziójában, például: "Hey Cortana, take a picture."

### <a name="start-menu-to-take-photos"></a>Start menü fényképek készítése

A Start kézmozdulattal váltsa a **Start menüt,** majd válassza a **Kamera ikont.**

Mutasson a fejre a rögzíteni kívánt [](hololens2-basic-usage.md#touch-holograms-near-you) kép irányában, majd koppintson légi koppintással a fényképhez. A további fényképeket továbbra is légi koppintással és rögzítéssel folytathatja. A rendszer menti a készített fényképeket az eszközére.

Használja ismét a Start (Indítás) kézmozdulatot a fényképek rögzítésének a végére.  

## <a name="capture-a-mixed-reality-video"></a>Vegyes valóságú videó rögzítése

Többféleképpen is rögzíthet vegyes valóságot bemutató videót a HoloLens; Használhatja a hardvergombokat, a hangot vagy a Start menü.

### <a name="hardware-buttons-to-record-videos"></a>Hardvergombok videók rögzítéséhez

A videók rögzítésének leggyorsabb módja, ha  egyszerre nyomja  le és tartsa lenyomva a hangerőt a gombokon, amíg el nem kezdődik a három másodperces visszaszámlálás. A rögzítést úgy állíthatja le, ha egyszerre mindkét gombra koppint.

> [!NOTE]
> A **hangerőt** egyszerre  gyorsan fel- és lekötve egyidejűleg lenyomáskor a videó rögzítése helyett fénykép fog készültni.

### <a name="voice-to-record-videos"></a>Videók hangalapú rögzítésére

A HoloLens 2004-es (és újabb) verziójában mondja el a "Rögzítés kezdete" szót. A rögzítést a "Rögzítés leállítása" szóval állíthatja le.

A HoloLens (1. generációs) vagy HoloLens 2. HoloLens 1903-as verziójában, például: "Hey Cortana, start recording". A rögzítés leállításhoz mondja ki a "Hey Cortana, stop recording" (Hé, Cortana, állítsa le a rögzítést).

### <a name="start-menu-to-record-videos"></a>Start menü videók rögzítésének a megtekintése

A Start kézmozdulattal váltsa a **Start menüt,** majd válassza a **Videó ikont.** Mutasson a fejre a rögzíteni kívánt [](hololens2-basic-usage.md#touch-holograms-near-you) adatok irányában, majd koppintson a légi koppintással a rögzítéshez. Három másodperces visszaszámlálás lesz, és megkezdődik a felvétel.

A rögzítés leállításhoz használja a Start (Indítás) kézmozdulatot, és válassza a kiemelt **Videó ikont.** A rendszer menti a videót az eszközére.

> [!NOTE]
> **Csak HoloLens (1. generációs)**  
> A [Windows 10 2018. októberi frissítése](/windows/mixed-reality/release-notes-october-2018) módosítja a Start kézmozdulat és Windows gomb viselkedését a HoloLens (1. gen). A frissítés előtt a Kézmozdulat vagy Windows gomb leállít egy videofelvételt. A frissítés után azonban a Kézmozdulat vagy a Windows gomb  megnyitja a **Start** menüt (vagy a gyorsműveletek  menüt, ha egy modern alkalmazásban van), amelyből a kiemelt videó ikonra kattintva leállíthatja a rögzítést.

## <a name="share-what-you-see-in-real-time"></a>Valós idejű megosztás

A fájlokban látható HoloLens valós időben megoszthatja barátaival és munkatársaival. Létezik néhány módszer:

1. Csatlakozás egy Miracast-kompatibilis eszközhöz vagy adapterhez a TV-n való megtekintéshez.
1. A [Windows Eszközportál](/windows/mixed-reality/using-the-windows-device-portal) használata a pc-n való megtekintéshez
1. A Microsoft HoloLens [alkalmazás használata a](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) számítógépen való megtekintéshez.
1. A [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) alkalmazás üzembe helyezése, amely lehetővé teszi az online dolgozók számára, hogy egy távoli szakértőnek streamelje, amit látnak. A távoli szakértő ezután verbálisan vagy jegyzetekkel irányíthatja a frontvonali dolgozót.

> [!NOTE]
> Ahhoz, hogy a Windows Eszközportál vagy Microsoft HoloLens alkalmazáson keresztül megossa a látható HoloLens fejlesztői [módban legyen.](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)

### <a name="stream-video-with-miracast"></a>Videó streamelése Miracast

A Start kézmozdulattal váltsa a **Start** menüt, majd válassza a Csatlakozás **ikont.** A megjelenő választóban válassza ki azt a Miracast-kompatibilis eszközt vagy adaptert, amelyhez csatlakozni szeretne.

A megosztást a Start kézmozdulattal  állíthatja le, és kiválaszthatja a Csatlakozás ikont. Mivel streamelést használ, semmi sem lesz mentve az eszközre.

> [!NOTE]
> Miracast a (1. generációs) HoloLens a [Windows 10 2018. októberi frissítése.](/windows/mixed-reality/release-notes-october-2018)

### <a name="real-time-video-with-windows-device-portal"></a>Valós idejű videó Windows Eszközportál

Mivel a Windows Eszközportál való megosztáshoz engedélyezni kell a fejlesztői módot a HoloLens- és a fejlesztői dokumentációban található utasításokat követve állítsa be a Fejlesztői módot, és navigáljon a [Windows Eszközportál.](/windows/mixed-reality/using-the-windows-device-portal)

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens alkalmazás használata

Mivel a Microsoft HoloLens alkalmazáson keresztüli megosztáshoz engedélyezni kell a Fejlesztői módot a HoloLens, a Fejlesztői mód beállításához kövesse a fejlesztői [dokumentációban található utasításokat.](/windows/mixed-reality/using-the-windows-device-portal) Ezután töltse le a [Microsoft HoloLens társalkalmazást,](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) és kövesse az alkalmazáson belüli utasításokat az alkalmazáshoz való HoloLens.

Miután beállította az alkalmazást a HoloLens válassza az Élő **stream** lehetőséget az alkalmazás főmenüjében.

## <a name="view-your-mixed-reality-photos-and-videos"></a>Vegyes valóságú fényképek és videók megtekintése

A vegyes valóságú fényképek és videók az eszköz "Camera Roll" (Kamera roll) eszközére vannak mentve. A mappa tartalmát a HoloLens alkalmazással Fájlkezelő (lépjen a Pictures > Camera Roll (Képek és **> gombra).**

A vegyes valóságú fényképeket és videókat a Fényképek alkalmazásban is megtekintheti, amely előre telepítve van a HoloLens. Fénykép világbeli kitűzéhez válassza ki azt a Fényképek alkalmazásban, majd válassza a **Hely vegyes világban lehetőséget.** A fényképet a világ más táján is áthelyezheti, miután az el lett helyezve.

A vegyes valóságú fényképek és videók megtekintéséhez és/vagy mentéséhez egy HoloLens-hez csatlakoztatott számítógépen használhatja az [Windows Eszközportál-t](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) vagy a számítógép Fájlkezelő [MTP-n keresztül.](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>A Fájlkezelő képek, videók és fájlok lekérte

Más mobileszközökhöz hasonlóan csatlakoztassa HoloLens-t a számítógépéhez, hogy Fájlkezelő-kódtárakat (fényképeket, videókat, dokumentumokat) is hozzáférjen a HoloLens-kódtárakhoz az egyszerű átvitel érdekében. Ez a módszer könnyen használható, és nem igényel eszközportál vagy Wi-Fi használatát.

1. Oldja fel az eszköz zárolását.
1. Csatlakozás eszközt USB-kapcsolaton keresztül csatlakoztatja egy számítógéphez.
1. Fájlkezelő meg kell nyitnia a számítógépén.
1. Navigáljon ide: Ez a \\ *számítógép a következő:* \Internal Storage\Pictures\Camera Roll
1. Másolja a számítógépre a szükséges fájlokat.

Tippek:
- Ha nem lát fájlokat, jelentkezzen be a HoloLens, hogy engedélyezze az adatokhoz való hozzáférést.
- Más mappákban, például diagnosztikai fájlokban lévő fájlokat a Dokumentumok mappából is lekért. [](hololens-diagnostic-logs.md#offline-diagnostics)
- A Fájlkezelő eszköztulajdonságokat kiválasztva láthatja Windows Holographic operációs rendszer verziószámát (belső vezérlőprogram verziója), az eszköz sorozatszámát és az akkumulátor százalékos arányát.
- Ha a szervezet MDM-et használt a [Kapcsolat/AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) letiltásához, akkor nem fog tudni csatlakozni az eszközhöz.

## <a name="share-your-mixed-reality-photos-and-videos"></a>Vegyes valóságú fényképek és videók megosztása

A [holografikus Windows 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1)verziója előtt egy vegyes valóságú fénykép vagy videó rögzítése után megjelenik egy előnézet. A **megosztási asszisztenst** az előnézet fölötti Megosztás ikonnal hozhatja meg. Itt kiválaszthatja azt a végpontot, amelyen meg szeretné osztani a fényképet vagy videót.

A Windows Holographic 21H1-es verziójában egy vegyes valóságú fénykép vagy videó rögzítése után megjelenik egy előnézet. A **megosztási asszisztenst** az előnézet fölötti Megosztás ikonnal hozhatja meg. Itt kiválaszthatja azt a végpontot (Mail, OneDrive stb.), amelyen meg szeretné osztani a fényképet vagy videót. Azt is engedélyezheti, HoloLens a közeli eszközökkel való megosztást a **-Gépház -> -> szolgáltatások** között. További részletekért olvassa el a Share [things witharby devices in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)(Dolgok megosztása a közeli eszközökkel a Windows 10.

> [!TIP] 
> A vegyes valóságú fényképeket és videókat a OneDrive is megoszthatja, ha automatikusan feltölti a vegyes valóságú fényképeket és videókat. Nyissa meg a OneDrive alkalmazást a HoloLens, és jelentkezzen be egy személyes **[Microsoft-fiók,](https://account.microsoft.com)** ha még nem. Válassza a **Gépház** ikont, majd a **Kamera feltöltése lehetőséget.** Kapcsolja be a Kamera feltöltése adatokat. A vegyes valóságú fényképek és videók mostantól fel lesznek töltve OneDrive amikor elindítja az alkalmazást a HoloLens.

> [!NOTE]
> Csak akkor engedélyezheti a kamerafeltöltést a OneDrive, ha személyes OneDrive van Microsoft-fiók. Ha munkahelyi vagy HoloLens fiókkal hoz létre munkahelyi vagy iskolai fiókot, a funkció engedélyezéséhez hozzáadhat egy személyes Microsoft-fiók OneDrive alkalmazásban.

## <a name="limitations-of-mixed-reality-capture"></a>A vegyes valóság rögzítésének korlátozásai

- A vegyes valóságú rögzítés használata esetén a HoloLens képkocka-sebessége felezhető 30 Hz-re.
- A fényképek és videók felbontása csökkenthető, ha a fénykép-/videokamerát már egy másik alkalmazás használja, élő streamelés közben, vagy ha a rendszer erőforrásai alacsonyak.

### <a name="maximum-recording-length"></a>Rögzítés maximális hossza

A HoloLens Holographic Windows 20H2-es verziója előtt 2 eszközön az eszközön rögzített videók legfeljebb öt percig voltak korlátozva.

Az ügyfelek visszajelzései miatt növeltünk a vegyes valóságú [rögzítések hosszát.](holographic-photos-and-videos.md) A vegyes valóságú rögzítések alapértelmezés szerint nem lesznek 5 percre korlátozva, hanem a maximális rögzítési hosszt számítják ki a rendelkezésre álló lemezterület alapján. Az eszköz a teljes lemezterület 80%-ának megfelelő szabad lemezterület alapján megbecsüli a videófelvétel maximális időtartamát.

> [!NOTE]
> A HoloLens a videófelvétel alapértelmezett hosszát (5 perc) használja, ha a következők valamelyike bekövetkezik:
> - A becsült maximális rögzítési időtartam kisebb, mint az alapértelmezett 5 perc.
> - A rendelkezésre álló lemezterület kevesebb, mint a teljes lemezterület 20%-a.

## <a name="default-file-format-and-resolution"></a>Alapértelmezett fájlformátum és -felbontás

### <a name="default-photo-format-and-resolution"></a>Alapértelmezett fényképformátum és -felbontás

|  Eszköz  |  Formátum  |  Mellék  |  Feloldás  |
|----------|----------|----------|----------|
| HoloLens 2 | [Jpeg](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (1. generációs) | [Jpeg](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>Rögzített videóformátum és -felbontás

| Eszköz | Formátum | Mellék | Feloldás | Sebesség | Audió |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48 kHz-es audio |
| HoloLens (1. generációs) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48 kHz-es audio |
