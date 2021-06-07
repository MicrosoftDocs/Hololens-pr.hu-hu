---
title: Fizikai terek leképezés a HoloLens segítségével
description: A HoloLens megtanulja, hogyan néz ki egy tér az idő alatt. A felhasználók úgy könnyíthetik meg ezt a folyamatot, hogy bizonyos módokon átköltöztik a HoloLenst a téren.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, tervezés, térbeli leképezés, HoloLens, felületrekonstrukció, háló, fejkövetés, leképezés
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 7cedf2af90744477c33736087c85a43168167707
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379579"
---
# <a name="map-physical-spaces-with-hololens"></a>Fizikai terek leképezés a HoloLens segítségével

A HoloLens a hologramokat a fizikai világgal ötvözi. A HoloLensnek meg kell tanulnia az Ön körüli fizikai világot, és emlékeznie kell arra, hogy hol helyezzen hologramokat a térben.

Idővel a HoloLens felépíti *a* látott környezet térbeli térképét.  A HoloLens frissíti a térképet a környezet változásának fényében. Amíg be van jelentkezve, és az eszköz be van kapcsolva, a HoloLens létrehozza és frissíti a térbeli térképeket. Ha az eszközt úgy tartja vagy koptatja, hogy a kamerák egy helyre mutatnak, a HoloLens megpróbálja leképezni a területet. Bár a HoloLens idővel természetes módon tanulja meg a helyet, vannak olyan módszerek, amelyek segítségével a HoloLens gyorsabban és hatékonyabban tudja leképezni a helyet.  

> [!NOTE]
> Ha a HoloLens nem tudja leképezni a tárhelyet, vagy nem működik, a HoloLens korlátozott módba léphet. Korlátozott módban nem fog tudni hologramokat a környezetében használni.

Ez a cikk bemutatja, hogyan térképeik le a HoloLens a tereket, hogyan javítható a térbeli leképezés, és hogyan kezelhetők a HoloLens által gyűjtött térbeli adatok.

## <a name="choosing-and-setting-up-and-your-space"></a>A hely és a hely kiválasztása és beállítása

A környezet funkciói megnehezítik a HoloLens számára a tér értelmezését. A fényszintek, a tér anyagai, az objektumok elrendezése stb. mind hatással lehetnek arra, hogy a HoloLens hogyan leképez egy területet.

A HoloLens bizonyos típusú környezetekben működik a legjobban. A legjobb térbeli térkép előállításához válasszon ki egy megfelelő fényű és sok helyből álló helyiséget. Kerülje a sötét tereket és olyan helyiségeket, amelyek sok sötét, sötét vagy átlátszó felületű (például tükrözött vagy rátermetes) felületekkel rendelkeznek.

A HoloLens beltéri használatra van optimalizálva. A térbeli leképezés akkor is Wi-Fi, ha a hálózat be van kapcsolva, bár nem kell hálózathoz csatlakoztatni. A HoloLens akkor Wi-Fi be a hozzáférési pontokat, ha nincs csatlakoztatva vagy hitelesítve. A HoloLens funkciói nem változnak meg, hogy a hozzáférési pontok internethez csatlakoznak, vagy csak intranetes/helyiek.

A HoloLenst csak biztonságos, veszélyforrások nélkül használhatók. [További információ a biztonságról:](https://support.microsoft.com/help/4023454/safety-information).

## <a name="mapping-your-space"></a>A tér leképezése

Most már készen áll a tartalék leképezésére.  Amikor a HoloLens elkezdi leképezni a környezetet, egy, a térben elterjedő hálógrafikát fog látni.  A vegyes valóságú otthonban a leképezett felület kiválasztásával aktiválhatja a térképet.

Az alábbi irányelvek alapján nagyszerű térbeli térképeket lehet kihozni.

### <a name="understand-the-scenarios-for-the-area"></a>A terület forgatókönyvei

Fontos, hogy a legtöbb időt a HoloLens használatával töltse, hogy a térkép releváns és teljes legyen. Ha például a HoloLens felhasználói forgatókönyve az A pontról a B pontra való áthelyezést foglalja magában, járja be ezt az útvonalat 2-3-szor, és haladjon végig minden irányban.  

### <a name="walk-slowly-around-the-space"></a>Lassan járdáljon a tér körül

Ha túl gyorsan járja a területet, valószínű, hogy a HoloLens nem fog leképezési területeket kihagyni. Lassan járja körbe a területet, és minden 5–8 láb között megáll, és a környezetét is meg kell néznie.  

A zökkenőmentes mozgás a HoloLens-térképet is hatékonyabban segítik.

### <a name="look-in-all-directions"></a>Minden irányban

A tér leképezésével a HoloLens több adatot biztosít a pontok egymáshoz viszonyított viszonyának helyéhez.  

Ha például nem keres, előfordulhat, hogy a HoloLens nem tudja, hol van a felső határ egy helyiségben.  

Ne felejtsen el lenézni a padlóra a tér leképezésén.

### <a name="cover-key-areas-multiple-times"></a>A legfontosabb területek többszöri lefedve

Ha többször is végigköltöz egy területen, az segít az első bemutatóban esetleg kihagyott funkciók behúzásában. Egy ideális térkép felépítéséhez próbáljon meg kétszer vagy háromszor bejárni egy területet.

Ha lehetséges, a mozgások ismétlése közben időt fordítson egy területre egy irányban, majd fordítsa meg és járja vissza a utat.

### <a name="take-your-time-mapping-the-area"></a>A terület leképezése

A HoloLens teljes leképezés és a környezethez való igazodása 15–20 percet is igénybe vehet. Ha van olyan hely, ahol gyakran tervezi használni a HoloLenst, a későbbiekben megelőzheti a problémákat, ha előre leképezi ezt az időt.  

## <a name="possible-errors-in-the-spatial-map"></a>Lehetséges hibák a térbeli térképen

A térbeli leképezési adatok hibái néhány kategóriába sorolhatók:

- *Rések:* Valós felületek hiányoznak a térbeli leképezési adatokból.
- *A felszínek* olyan térbeli leképezési adatokban léteznek, amelyek a való világban nem léteznek.
- *Wormegegek:* A HoloLens elveszíti a térbeli térkép egy részét, ha úgy gondolja, hogy a térkép egy másik részén található, mint amilyen valójában.
- *Torzítás:* A térbeli leképezési adatok felületei nem teljesen igazodnak a valós felületekhez, leküldve vagy kihúzva.

Ha ezen hibák bármelyikét látja, küldjön visszajelzést a [FeedbackHubon.](hololens-feedback.md)

## <a name="security-and-storage-for-spatial-data"></a>Térbeli adatok biztonsága és tárolása

Windows 10 1803-as vagy újabb Microsoft HoloLens a leképezési adatokat egy helyi (eszközön található) adatbázisban tárolja.

A HoloLens-felhasználók akkor sem férhetnek hozzá közvetlenül a térképadatbázishoz, ha az eszköz számítógéphez van csatlakoztatva, vagy ha az Fájlkezelő használja. Ha a BitLocker engedélyezve van a HoloLensben, a rendszer a tárolt térképadatokat is titkosítja a teljes kötetpel együtt.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Térképadatok és ismert szóközök eltávolítása a HoloLensből

A Térképadatok törlésének két beállítása van a Beállítások > **System > Hologramsban:**

- A közeli hologramok törléséhez válassza a **Közeli hologramok eltávolítása lehetőséget.** Ez a parancs törli a térképadatokat és a rögzített hologramokat az aktuális térhez. Ha továbbra is ugyanabban a térben használja az eszközt, az létrehoz és tárol egy teljesen új térkép szakaszt a törölt adatok lecseréléséhez.

   > [!NOTE]
   > A "Közeli" hologramok olyan hologramok, amelyek az aktuális tér azonos térképszakaszában vannak horgonyozva.

   Ezzel a beállítással például úgy ürítheti ki a munkához kapcsolódó térképadatokat, hogy az ne legyen hatással az otthoni térképadatokra.

- Az összes hologram törléséhez válassza az **Összes hologram eltávolítása lehetőséget.** Ez a parancs törli az eszközön tárolt összes térképadatot, valamint az összes rögzített hologramot. Explicit módon el kell látnia minden hologramot. A korábban elhelyezett hologramokat nem fogja tudni újra kiveszni.

> [!NOTE]
> A közeli vagy az összes hologram eltávolítása után a HoloLens azonnal megkezdi az aktuális tér beolvasását és leképezését.

### <a name="wi-fi-data-in-spatial-maps"></a>Wi-Fi adatok térbeli térképekben való használata

A HoloLens Wi-Fi, hogy korrelálják az ismert terek HoloLens-adatbázisában tárolt hologram-helyeket és térképszakaszokat. Az Wi-Fi nem érhetők el a felhasználók számára, és nem küldhetőek el a Microsoftnak a felhő vagy telemetria használatával.

Amíg a Wi-Fi engedélyezve van, a HoloLens korrelál a térképadatokat a közeli Wi-Fi hozzáférési pontokkal. Nincs különbség a viselkedésben, függetlenül attól, hogy egy hálózat csatlakoztatva van-e vagy csak a közelben van-e. Ha Wi-Fi le van tiltva, a HoloLens továbbra is keres a térben. A HoloLensnek azonban több térképadatot kell keresnie a Spaces-adatbázisban, és több időre lehet szüksége a hologramok megkeresésével. A Wi-Fi információk nélkül a HoloLensnek össze kell hasonlítani az aktív vizsgálatot az eszközön tárolt összes hologramhorgony-horgonyval és térképszakaszokkal, hogy megtalálja a térkép megfelelő részét.

## <a name="related-topics"></a>Kapcsolódó témakörök

- [Térbeli leképezés kialakítása](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
