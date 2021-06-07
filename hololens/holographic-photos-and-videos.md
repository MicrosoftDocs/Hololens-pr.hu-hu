---
title: Vegyes valóságú fényképek és videók rögzítése, rögzítése és megosztása
description: Megtudhatja, hogyan rögzítheti, rögzítheti és megtekintheti a vegyes valóságú fényképeket és videókat a HoloLens vegyes valóságú eszközeivel. Megtudhatja, hogyan oszthat meg miracast vagy összegyűjtött fájlok segítségével.
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
ms.openlocfilehash: 178dff5d8a30fdd9c5012e2d14f5d4683d6cc23e
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378025"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Vegyes valóságú fényképek és videók létrehozása

A HoloLens lehetővé teszi a felhasználók számára, hogy a való világot a digitális világgal ötvözzék.  A vegyes valóságú rögzítés (MRC) lehetővé teszi, hogy ezt a élményt fényképként vagy videóként rögzítse, vagy megosztja másokkal valós időben.

A vegyes valóságú rögzítés személyes nézőpontot használ, hogy mások is látják a hologramokat. Külső nézőponthoz használja a [spektátornézetet.](https://docs.microsoft.com/windows/mixed-reality/spectator-view) A Spektátor nézet különösen hasznos a bemutatókhoz.

Bár a videók ismerősök és munkatársak között is megoszthatók, a videók másoknak is segíthetnek megtanítani egy alkalmazás használatát, vagy problémákat kommunikálni az alkalmazásokkal és a felhasználói élményekkel.

> [!NOTE]
> Ha nem tud vegyes valóságot rögzíteni, és a HoloLens munkahelyi eszköz, forduljon a rendszergazdához. A kamerához való hozzáférés céges szabályzattal korlátozható.

## <a name="capture-a-mixed-reality-photo"></a>Vegyes valóságú fénykép rögzítése

A HoloLensen többféleképpen is lehet vegyes valóságról fotót venni; Használhatja a hardvergombokat, a hangot vagy a Start menü.

### <a name="hardware-buttons-to-take-photos"></a>Hardvergombok fényképekhez

Az aktuális nézet gyorsképének megtekintéséhez egyszerre nyomja le a hangerőt felfelé és lefelé gombokkal.  Ez egy kicsit hasonló a képernyőképek vagy a nyomtatási képernyő HoloLens-verziójához.

- [Gombhelyek a HoloLens 2-ben](hololens2-hardware.md)
- [Gombhelyek a HoloLensben (1. generációs)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> Ha három **másodpercig tartja** lenyomva a hangerőt és a hangerőt, azzal elkezdi a videó rögzítését, és nem fényképet készít.  A rögzítés leállításhoz egyszerre  koppintson a **fel-** és lekötet gombokra.

### <a name="voice-commands-to-take-photos"></a>Hangparancsok fényképekhez

A HoloLens 2 2004-es (és újabb) verzióján mondja el a "Kép leképe" szót.

HoloLensben (1. generációs) vagy HoloLens 2-ben, az 1903-as verzióban például: "Hé Cortana, képpel."

### <a name="start-menu-to-take-photos"></a>Start menü fényképek készítése

A Start kézmozdulattal váltsa a **Start menüt,** majd válassza a **Kamera ikont.**

Mutasson a fejre a rögzíteni kívánt [](hololens2-basic-usage.md#touch-holograms-near-you) kép irányában, majd koppintson légi koppintással a fényképhez. A további fényképeket továbbra is légi koppintással és rögzítéssel folytathatja. A rendszer menti a készített fényképeket az eszközére.

Használja ismét a Start (Indítás) kézmozdulatot a fényképek rögzítésének a végére.  

## <a name="capture-a-mixed-reality-video"></a>Vegyes valóságú videó rögzítése

A HoloLensben többféleképpen is rögzíthet vegyes valóságról készült videót; Használhatja a hardvergombokat, a hangot vagy a Start menü.

### <a name="hardware-buttons-to-record-videos"></a>Hardvergombok videók rögzítéséhez

A videók rögzítésének leggyorsabb módja, ha  egyszerre nyomja  le és tartsa lenyomva a hangerőt a gombokon, amíg el nem kezdődik a három másodperces visszaszámlálás. A rögzítést úgy állíthatja le, ha egyszerre mindkét gombra koppint.

> [!NOTE]
> A **hangerőt** egyszerre  gyorsan felfelé és lefelé nyomáskor a videó rögzítése helyett fényképet készít.

### <a name="voice-to-record-videos"></a>Videók hangalapú rögzítéséhez

A HoloLens 2., 2004-es (és újabb) verzióján mondja el a "Start recording" (Rögzítés elkezdését) A rögzítést a "Rögzítés leállítása" szóval állíthatja le.

HoloLensben (1. generációs) vagy HoloLens 2-ben, az 1903-as verzióban például: "Hey Cortana, start recording". A rögzítés leállításához mondja ki a "Hey Cortana, stop recording" (Cortana, rögzítés megáll) parancsot.

### <a name="start-menu-to-record-videos"></a>Start menü videók rögzítésének a megtekintése

A Start kézmozdulattal váltsa a **Start menüt,** majd válassza a **Videó ikont.** Mutasson a fejre a rögzíteni kívánt [](hololens2-basic-usage.md#touch-holograms-near-you) adatok irányában, majd koppintson a légi koppintással a rögzítéshez. Három másodperces visszaszámlálás lesz, és megkezdődik a felvétel.

A rögzítés leállításhoz használja a Start (Indítás) kézmozdulatot, és válassza a kiemelt **Videó ikont.** A rendszer menti a videót az eszközére.

> [!NOTE]
> **Csak a HoloLensre (1. generációs) vonatkozik**  
> A [Windows 10 2018. októberi frissítése](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) módosítja a Kézmozdulat és a Windows gomb viselkedését a HoloLensben (1. generációs). A frissítés előtt a Kézmozdulat vagy a Windows gomb leállít egy videofelvételt. A frissítés után azonban a Kézmozdulat vagy a Windows  gomb megnyitja a **Start** menüt (vagy a gyorsműveletek menüt, ha modern alkalmazásban van), amelyből a kiemelt videó ikonra kattintva leállíthatja a rögzítést. 

## <a name="share-what-you-see-in-real-time"></a>Valós idejű megosztás

A HoloLensben látható okat valós időben megoszthatja barátaival és munkatársaival. Létezik néhány módszer:

1. Csatlakozás Miracast-kompatibilis eszközhöz vagy adapterhez tv-n való megtekintéshez.
1. A [Windows eszközportál](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) használata a pc-n való megtekintéshez
1. A Microsoft HoloLens [alkalmazás használata a](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) számítógépen való megtekintéshez.
1. A [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) alkalmazás üzembe helyezése, amely lehetővé teszi az online dolgozók számára, hogy egy távoli szakértőnek streamelje, amit látnak. A távoli szakértő ezután verbálisan vagy jegyzetekkel irányíthatja a frontvonali dolgozót.

> [!NOTE]
> Ahhoz, hogy a holoLens fejlesztői módban Windows eszközportál vagy Microsoft HoloLens alkalmazáson keresztül megoszava megosztja a [látható fájlokat.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)

### <a name="stream-video-with-miracast"></a>Videó streamelése a Miracasttal

A Start kézmozdulattal lépjen a **Start menüre,** majd válassza a **Csatlakozás ikont.** A megjelenő választóban válassza ki azt a Miracast-kompatibilis eszközt vagy adaptert, amelyhez csatlakozni szeretne.

A megosztást a Start kézmozdulattal állíthatja le, és válassza a kiemelt **Csatlakozás ikont.** Mivel streamelést használ, semmi sem lesz mentve az eszközre.

> [!NOTE]
> A Miracast támogatása a (1. generációs) HoloLensben volt engedélyezve a [Windows 10 2018. októberi frissítése.](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)

### <a name="real-time-video-with-windows-device-portal"></a>Valós idejű videó Windows eszközportál

Mivel a Windows eszközportál való megosztáshoz engedélyezni kell a Fejlesztői módot a HoloLensen, a fejlesztői dokumentációban található utasításokat követve állítsa be a Fejlesztői módot, és navigáljon a [Windows eszközportál.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens alkalmazás használata

Mivel a Microsoft HoloLens alkalmazáson keresztüli megosztáshoz engedélyezni kell a Fejlesztői módot a HoloLensen, kövesse a fejlesztői dokumentációban található utasításokat a fejlesztői [mód beállításához.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) Ezután töltse le a [Microsoft HoloLens társalkalmazást,](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) és kövesse az alkalmazáson belüli utasításokat a HoloLenshez való csatlakozáshoz.

Miután beállította az alkalmazást a HoloLens-sel, válassza az Élő **stream** lehetőséget az alkalmazás főmenüjében.

## <a name="view-your-mixed-reality-photos-and-videos"></a>Vegyes valóságú fényképek és videók megtekintése

A vegyes valóságú fényképek és videók az eszköz "Camera Roll" (Kamera roll) eszközére vannak mentve. A mappa tartalmát a HoloLensben a Fájlkezelő alkalmazással tallózhatja (lépjen a Pictures > Camera Roll (Képek és > **gombra).**

A vegyes valóságú fényképeket és videókat a HoloLensen előre telepített Photos alkalmazásban is megtekintheti. Fénykép világbeli kitűzéhez válassza ki azt a Fényképek alkalmazásban, majd válassza a **Hely vegyes világban lehetőséget.** A fényképet a világ más táján is áthelyezheti, miután az el lett helyezve.

A vegyes valóságú fényképek és videók HoloLenshez csatlakoztatott számítógépen való megtekintéséhez és/vagy mentéséhez használhatja az [Windows eszközportál-t](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) vagy a számítógép Fájlkezelő [MTP-n keresztül.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>A Fájlkezelő képek, videók és fájlok lekérte

Más mobileszközökhöz hasonlóan csatlakoztassa a HoloLenst a számítógépéhez, hogy az Fájlkezelő-t is lásson a HoloLens-kódtárak (fényképek, videók, dokumentumok) eléréséhez az egyszerű átvitel érdekében. Ez a módszer könnyen használható, és nem igényel eszközportál vagy Wi-Fi használatát.

1. Oldja fel az eszköz zárolását.
1. Csatlakoztassa az eszközt a számítógéphez USB-kapcsolaton keresztül.
1. Fájlkezelő meg kell nyitnia a számítógépén.
1. Navigáljon ide: Ez a \\ *számítógép a sajátjaolensname*\Internal Storage\Pictures\Camera Roll
1. Másolja a számítógépre a szükséges fájlokat.

Tippek:
- Ha nem lát fájlokat, jelentkezzen be a HoloLensbe, hogy engedélyezze az adatokhoz való hozzáférést.
- Más mappákban, például diagnosztikai fájlokban lévő fájlokat a Dokumentumok mappából is lekért. [](hololens-diagnostic-logs.md#offline-diagnostics)
- A Fájlkezelő eszköztulajdonságok kiválasztásával használhatja a Windows Holographic operációs rendszer verziószámát (belső vezérlőprogram verziója), az eszköz sorozatszámát és az akkumulátor százalékos arányát.
- Ha a szervezet MDM-et használt a [Kapcsolat/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) letiltásához, akkor nem fog tudni csatlakozni az eszközhöz.

## <a name="share-your-mixed-reality-photos-and-videos"></a>Vegyes valóságú fényképek és videók megosztása

A [Windows Holographic 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1)verziója előtt egy vegyes valóságú fénykép vagy videó rögzítése után megjelenik egy előnézet. A **megosztási asszisztenst** az előnézet fölötti Megosztás ikonra kattintva hozhatja meg. Itt kiválaszthatja azt a végpontot, amelyen meg szeretné osztani a fényképet vagy videót.

A Windows Holographic 21H1-es verziója esetén egy vegyes valóságú fénykép vagy videó rögzítése után megjelenik egy előnézet. A **megosztási asszisztenst** az előnézet fölötti Megosztás ikonra kattintva hozhatja meg. Itt kiválaszthatja azt a végpontot (Mail, OneDrive stb.), amelyen meg szeretné osztani a fényképet vagy videót. A HoloLens a közeli eszközökkel való megosztását is engedélyezheti a **Beállítások -> System -> Experiences**(Megosztott élmények) lapon. További részletekért olvassa el a Dolgok megosztása a közeli eszközökkel a [Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

> [!TIP] 
> A OneDrive-ról származó vegyes valóságú fényképeket és videókat is megoszthatja, ha automatikusan feltölti a vegyes valóságú fényképeket és videókat. Nyissa meg a OneDrive alkalmazást a HoloLensben, és jelentkezzen be egy személyes **[Microsoft-fiók,](https://account.microsoft.com)** ha még nem. Válassza a **Beállítások ikont,** majd a **Kamera feltöltése lehetőséget.** Kapcsolja be a Kamera feltöltése figyelőt. A vegyes valóságú fényképek és videók mostantól minden alkalommal fel lesznek töltve a OneDrive-ra, amikor elindítja az alkalmazást a HoloLensben.

> [!NOTE]
> Kamerafeltöltést csak akkor engedélyezhet a OneDrive-ban, ha személyes fiókkal van bejelentkezve a OneDrive Microsoft-fiók. Ha munkahelyi vagy iskolai fiókkal beállította a HoloLenst, hozzáadhat egy személyes Microsoft-fiók a OneDrive alkalmazásban a funkció engedélyezéséhez.

## <a name="limitations-of-mixed-reality-capture"></a>A vegyes valóságú rögzítés korlátozásai

- Vegyes valóságú rögzítés használata esetén a HoloLens képkocka-sebessége felezhető 30 Hz-re.
- A fényképek és videók felbontása csökkenthető, ha a fénykép-/videókamerát már egy másik alkalmazás használja, élő streamelés közben, vagy ha a rendszer erőforrásai alacsonyak.

### <a name="maximum-recording-length"></a>Rögzítés maximális hossza

A HoloLens 2 rendszerű eszközökön a Windows Holographic 20H2-es verziója előtt az eszközön rögzített videók maximális hossza öt perc volt.

Az ügyfelek visszajelzései miatt megnövelte a vegyes [valóságú rögzítések hosszát.](holographic-photos-and-videos.md) A vegyes valóságú rögzítések alapértelmezés szerint nem lesznek 5 percre korlátozva, hanem a felvétel maximális hosszát számítja ki a rendelkezésre álló lemezterület alapján. Az eszköz a teljes lemezterület 80%-ának megfelelő szabad lemezterület alapján megbecsüli a videófelvétel maximális időtartamát.

> [!NOTE]
> A HoloLens a videófelvételek alapértelmezett hosszát használja (5 perc), ha a következők valamelyike történik:
> - A felvétel becsült maximális időtartama kisebb, mint az alapértelmezett 5 perc.
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
