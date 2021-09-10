---
title: Fizikai terek leképezés HoloLens
description: HoloLens megtanulja, hogyan néz ki egy tér az idő alatt. A felhasználók úgy könnyíthetik meg ezt a folyamatot, hogy a HoloLens bizonyos módokon átköltöznek a térben.
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
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428177"
---
# <a name="map-physical-spaces-with-hololens"></a>Fizikai terek leképezés HoloLens

HoloLens a hologramokat a fizikai világgal ötvözi. Ahhoz, hogy HoloLens megismerje az Ön körüli fizikai világot, és ne feledje, hol helyezzen hologramokat a térben.

Idővel a HoloLens *felépíti* a látott környezet térbeli térképét.  HoloLens frissíti a térképet a környezet változásának során. Amíg be van jelentkezve, és az eszköz be van kapcsolva, a HoloLens létrehozza és frissíti a térbeli térképeket. Ha az eszközt úgy tartja vagy koptatja, hogy a kamerák egy helyre mutatnak, a HoloLens megpróbálja leképezni a területet. Bár a HoloLens idővel természetes módon tanulja meg a helyet, vannak olyan módszerek, amelyek segítségével HoloLens és hatékonyabban leképezheti a területet.  

> [!NOTE]
> Ha a HoloLens nem tudja leképezni a tárhelyet, vagy nem túl jól működik, HoloLens korlátozott módba léphet. Korlátozott módban nem fog tudni hologramokat tenni a környezetbe.

Ez a cikk bemutatja, HoloLens térbeli térképeket, hogyan fejleszthető a térbeli leképezés, és hogyan kezelhetők a térbeli HoloLens adatok.

## <a name="choosing-and-setting-up-and-your-space"></a>A hely és a terület kiválasztása és beállítása

A környezetben található funkciók megnehezítheti a HoloLens számára a tér értelmezését. A fényszintek, a tér anyagai, az objektumok elrendezése stb. mind hatással lehetnek arra, HoloLens leképeznek egy területet.

HoloLens a legjobban bizonyos típusú környezetekben működik. A legjobb tértérkép előállításához válasszon ki egy megfelelő fényű és bőséges térközt biztosít. Kerülje a sötét tereket és a sok sötét, hüllős vagy átlátszó felületű helyiségeket (például a tükrözéseket vagy a huziszos éttermi tárgyakat).

HoloLens beltéri használatra van optimalizálva. A térbeli leképezés akkor Wi-Fi, ha a hálózat be van kapcsolva, bár nem kell hálózathoz csatlakoztatni. HoloLens akkor is Wi-Fi hozzáférési pontokat, ha nincs csatlakoztatva vagy hitelesítve. HoloLens funkció nem változik meg, hogy a hozzáférési pontok csak internetkapcsolattal vagy intranettel/helyivel csatlakoznak-e.

A HoloLens biztonságos, veszélyforrások nélkül használhatók. [További információ a biztonságról:](https://support.microsoft.com/help/4023454/safety-information).

## <a name="mapping-your-space"></a>A tér leképezése

Most már készen áll a tartalék leképezésére.  Amikor HoloLens kezd feltérképezni a környezetet, egy, a térben elterjedő hálós ábrát fog látni.  A vegyes valóságú kezdőlapon a leképezett felület kiválasztásával aktiválhatja a térkép megjelenítéset.

Az alábbi irányelvek alapján nagyszerű térbeli térképeket lehet kihozni.

### <a name="understand-the-scenarios-for-the-area"></a>A terület forgatókönyvei

Fontos, hogy a legtöbb időt azzal töltse, amikor a HoloLens, hogy a térkép releváns és teljes legyen. Ha például egy felhasználói forgatókönyvben HoloLens az A pontról a B pontra való áthelyezést, járja be ezt az útvonalat 2-3-szor, és minden irányban haladjon.  

### <a name="walk-slowly-around-the-space"></a>Lassan haladjon végig a téren

Ha túl gyorsan járja a területet, valószínű, hogy a HoloLens fog lemaradni a leképezési területekről. Lassan haladjon a tér körül, és 15–8 lábon megállva nézze meg a környezetet.  

A zökkenőmentes mozgás a HoloLens is segít a leképezésben.

### <a name="look-in-all-directions"></a>Minden irányban

Ha a tértérképet keresi, a HoloLens több adatot ad meg, hogy a pontok hol vannak egymáshoz viszonyítva.  

Ha például nem keres, előfordulhat, hogy a HoloLens tudja, hol van a felső határ egy helyiségben.  

Ne felejtsen el lenézni a padlóra a tér leképezéskor.

### <a name="cover-key-areas-multiple-times"></a>A főbb területek többszöri lefedődhet

Ha többször végigköltöz egy területen, az segít az első bemutatóban esetleg kihagyott funkciók behúzásában. Egy ideális térkép felépítéséhez próbáljon meg két-három alkalommal bejárni egy területet.

Ha lehetséges, a mozgások ismétlése közben időt kell töltenie azzal, hogy végig kell haladni egy területen az egyik irányban, majd oda-vissza kell fordulnia, ahogy előtért.

### <a name="take-your-time-mapping-the-area"></a>Időt kell a terület leképezésére

15–20 percet is igénybe HoloLens, hogy a rendszer teljes mértékben leképezi magát, és igazodik a környezethez. Ha van olyan terület, ahol gyakran tervez használni egy HoloLens, akkor a terület leképezésére használt idő a későbbiekben megakadályozhatja a problémákat.  

## <a name="possible-errors-in-the-spatial-map"></a>Lehetséges hibák a térbeli térképen

A térbeli leképezési adatok hibái néhány kategóriába sorolhatók:

- *Rések:* Valós felületek hiányoznak a térleképezési adatokból.
- *Imre:* A felszínek olyan térbeli leképezési adatokban léteznek, amelyek nem léteznek a való világban.
- *Wormholes*: HoloLens térbeli térkép "elveszíti" részét, úgy gondolva, hogy a térkép egy másik részén található, mint amilyen valójában.
- *Torzítás:* A térbeli leképezési adatokban a felületek nem teljesen igazodnak a valós felületekhez, vagy leküldve vagy kihúzva.

Ha ezen hibák bármelyikét látja, küldjön visszajelzést a [FeedbackHubon.](hololens-feedback.md)

## <a name="security-and-storage-for-spatial-data"></a>Térbeli adatok biztonsága és tárolása

Windows 10 1803-as vagy újabb Microsoft HoloLens a leképezési adatokat egy helyi (eszközön található) adatbázisban tárolja.

HoloLens felhasználók akkor sem férhetnek hozzá közvetlenül a térképadatbázishoz, ha az eszköz számítógéphez van csatlakoztatva, vagy ha a Fájlkezelő használják. Ha a BitLocker engedélyezve van a HoloLens, a rendszer a tárolt térképadatokat is titkosítja a teljes kötetpel együtt.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Térképadatok és ismert szóközök eltávolítása a HoloLens

Két lehetőség van a térképadatok törlésére a **Gépház > System > Hologramok:**

- A közeli hologramok törléséhez válassza a **Közeli hologramok eltávolítása lehetőséget.** Ez a parancs törli a térképadatokat és a rögzített hologramokat az aktuális térhez. Ha továbbra is ugyanabban a térben használja az eszközt, az létrehoz és tárol egy teljesen új térképszakaszt a törölt adatok lecseréléséhez.

   > [!NOTE]
   > A "Közeli" hologramok olyan hologramok, amelyek az aktuális tér ugyanazon térképszakaszában vannak horgonyozva.

   Ezzel a beállítással például anélkül törölhet munkához kapcsolódó térképadatokat, hogy az hatással lenne az otthoni térképadatokra.

- Az összes hologram törléséhez válassza az **Összes hologram eltávolítása lehetőséget.** Ez a parancs törli az eszközön tárolt összes térképadatot, valamint az összes rögzített hologramot. Explicit módon el kell látnia minden hologramot. A korábban elhelyezett hologramokat nem fogja tudni újra kiveszni.

> [!NOTE]
> Miután eltávolítja a közeli vagy az összes hologramot, a HoloLens azonnal megkezdi az aktuális tér beolvasását és leképezését.

### <a name="wi-fi-data-in-spatial-maps"></a>Wi-Fi adatok térbeli térképekben való használata

HoloLens olyan Wi-Fi tárol, amelyek segítenek korrelálni az ismert terek adatbázisában tárolt hologram-helyeket HoloLens térképszakaszokat. A Wi-Fi nem érhetők el a felhasználók számára, és nem küldhetőek el a Microsoftnak a felhő vagy telemetria használatával.

Amíg a Wi-Fi engedélyezve van, a HoloLens korrelál a közeli és a Wi-Fi hozzáférési pontokkal. Nincs különbség a viselkedésben, függetlenül attól, hogy egy hálózat csatlakoztatva van vagy csak a közelben van észlelve. Ha Wi-Fi le van tiltva, a HoloLens továbbra is keres a térben. A HoloLens azonban több térképadatot kell keresnie a Spaces-adatbázisban, és több időre lehet szüksége a hologramok megkereséséhez. A Wi-Fi információ nélkül a HoloLens-nek össze kell hasonlítania az aktív vizsgálatot az eszközön tárolt hologramhorgonyokkal és térképszakaszokkal, hogy megtalálja a térkép megfelelő részét.

## <a name="related-topics"></a>Kapcsolódó témakörök

- [Térbeli leképezés kialakítása](/windows/mixed-reality/spatial-mapping)
