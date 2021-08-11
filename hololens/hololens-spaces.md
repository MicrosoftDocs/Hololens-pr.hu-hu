---
title: Fizikai terek leképezés HoloLens
description: HoloLens, hogyan néz ki egy tér az idő alatt. A felhasználók úgy könnyíthetik meg ezt a folyamatot, hogy HoloLens bizonyos módokon átköltöztik a tárhelyen.
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
ms.openlocfilehash: d1eef6bdf463aa400504af7b35a0fd2b8e2b44499d6ff7b93e70a2dd5952ef88
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662866"
---
# <a name="map-physical-spaces-with-hololens"></a>Fizikai terek leképezés HoloLens

HoloLens a hologramokat a fizikai világával ötvözi. Ahhoz, hogy HoloLens meg tudjanak ismerkedni az Ön körüli fizikai világgal, és ne feledje, hol vannak a hologramok a térben.

Idővel a HoloLens felépíti *a* látott környezet térbeli térképét.  HoloLens frissíti a térképet a környezet változásaival. Amíg be van jelentkezve, és az eszköz be van kapcsolva, a HoloLens és frissíti a térbeli térképeket. Ha az eszközt úgy tartja vagy koptatja, hogy a kamerák egy helyre mutatnak, a HoloLens megpróbálja leképezni a területet. Bár a HoloLens természetes módon tanulja meg a helyet az idő alatt, vannak olyan módszerek, amelyek segítségével gyorsabban és hatékonyabban HoloLens leképezheti a területet.  

> [!NOTE]
> Ha a HoloLens nem tudja leképezni a tárhelyet, vagy nincs megfelelő állapotban, HoloLens korlátozott módba léphet. Korlátozott módban nem fog tudni hologramokat a környezetében használni.

Ez a cikk bemutatja, HoloLens térbeli leképezéseket, hogyan fejleszthet térbeli leképezést, és hogyan kezelheti a HoloLens gyűjtött térbeli adatokat.

## <a name="choosing-and-setting-up-and-your-space"></a>A hely és a hely kiválasztása és beállítása

A környezetben található funkciók megnehezítik a HoloLens számára a tér értelmezését. A fényszintek, a tér anyagai, az objektumok elrendezése stb. mind hatással lehetnek arra, HoloLens leképeznek egy területet.

HoloLens a legjobban bizonyos típusú környezetekben működik. A legjobb térbeli térkép előállításához válasszon ki egy megfelelő fényű és sok helyből álló helyiséget. Kerülje a sötét tereket és olyan helyiségeket, amelyek sok sötét, sötét vagy átlátszó felületű (például tükrözött vagy rátermetes) felületekkel rendelkeznek.

HoloLens beltéri használatra van optimalizálva. A térbeli leképezés akkor is Wi-Fi, ha a hálózat be van kapcsolva, bár nem kell hálózathoz csatlakoztatni. HoloLens akkor is Wi-Fi hozzáférési pontokat, ha nincs csatlakoztatva vagy hitelesítve. HoloLens funkció nem változik meg, hogy a hozzáférési pontok csak internetkapcsolattal vagy intranettel/helyi hálózattal csatlakoznak-e.

A HoloLens biztonságos, veszélyforrások nélkül használhatók. [További információ a biztonságról:](https://support.microsoft.com/help/4023454/safety-information).

## <a name="mapping-your-space"></a>A tér leképezése

Most már készen áll a tartalék leképezésére.  Amikor HoloLens elkezdi leképezni a környezetet, egy, a térben elterjedő hálógrafikát fog látni.  A vegyes valóságú otthonban a leképezett felület kiválasztásával aktiválhatja a térképet.

Az alábbi irányelvek alapján nagyszerű térbeli térképeket lehet kihozni.

### <a name="understand-the-scenarios-for-the-area"></a>A terület forgatókönyvei

Fontos, hogy a legtöbb időt azzal töltse, amikor a HoloLens használja, hogy a térkép releváns és teljes legyen. Ha például egy felhasználói forgatókönyvben HoloLens az A pontról a B pontra, járja be ezt az útvonalat 2-3-szor, és haladjon végig minden irányban.  

### <a name="walk-slowly-around-the-space"></a>Lassan járdáljon a tér körül

Ha túl gyorsan járja a területet, valószínű, hogy a HoloLens kihagyja a leképezési területeket. Lassan járja körbe a területet, és minden 5–8 láb között megáll, és a környezetét is meg kell néznie.  

A zökkenőmentes mozgás a HoloLens is segít a térkép hatékonyabban.

### <a name="look-in-all-directions"></a>Minden irányban

A tér leképezésében való HoloLens több adatot biztosít a pontok egymáshoz viszonyított viszonyában.  

Ha például nem keres, előfordulhat, hogy a HoloLens tudja, hol van a felső határ egy helyiségben.  

Ne felejtsen el lenézni a padlóra a tér leképezéskor.

### <a name="cover-key-areas-multiple-times"></a>A főbb területek többszöri lefedve

Ha többször is végigköltöz egy területen, az segít az első bemutatóban esetleg kihagyott funkciók behúzásában. Egy ideális térkép felépítéséhez próbáljon meg kétszer vagy háromszor bejárni egy területet.

Ha lehetséges, a mozgás ismétlése közben időt fordítson egy területre egy irányban, majd fordítsa meg és járja vissza az utat.

### <a name="take-your-time-mapping-the-area"></a>A terület leképezése

15–20 percig is eltarthat, HoloLens a rendszer teljes mértékben leképezi magát, és alkalmazkodik a környezethez. Ha van olyan terület, ahol gyakran tervezi használni a HoloLens, akkor ezt az időt előre meg kell tervezni a terület leképezésével, a későbbiekben megelőzheti a problémákat.  

## <a name="possible-errors-in-the-spatial-map"></a>Lehetséges hibák a térbeli térképen

A térbeli leképezési adatok hibái néhány kategóriába sorolhatók:

- *Rések:* Valós felületek hiányoznak a térbeli leképezési adatokból.
- *A felszínek* olyan térbeli leképezési adatokban léteznek, amelyek a való világban nem léteznek.
- *Worm HoloLens:* a térbeli térkép "elveszíti" részét, úgy gondolva, hogy a térkép egy másik részén található, mint amilyen valójában.
- *Torzítás:* A térbeli leképezési adatok felületei nem teljesen igazodnak a valós felületekhez, leküldve vagy kihúzva.

Ha ezen hibák bármelyikét látja, küldjön visszajelzést a [FeedbackHubon.](hololens-feedback.md)

## <a name="security-and-storage-for-spatial-data"></a>Térbeli adatok biztonsága és tárolása

Windows 10 1803-as vagy újabb Microsoft HoloLens a leképezési adatokat egy helyi (eszközön található) adatbázisban tárolja.

HoloLens a felhasználók akkor sem férhetnek hozzá közvetlenül a térképadatbázishoz, ha az eszköz számítógéphez van csatlakoztatva, vagy ha az Fájlkezelő használja. Ha a BitLocker engedélyezve van a HoloLens, a rendszer a tárolt térképadatokat is titkosítja a teljes kötetpel együtt.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Térképadatok és ismert szóközök eltávolítása a HoloLens

Két lehetőség van a térképadatok törlésére a **Gépház > System > Hologramok:**

- A közeli hologramok törléséhez válassza **a Közeli hologramok eltávolítása lehetőséget.** Ez a parancs törli a térképadatokat és a rögzített hologramokat az aktuális térhez. Ha továbbra is ugyanabban a térben használja az eszközt, az létrehoz és tárol egy teljesen új térképszakaszt a törölt adatok lecseréléséhez.

   > [!NOTE]
   > A "Közeli" hologramok olyan hologramok, amelyek az aktuális tér azonos térképszakaszában vannak horgonyozva.

   Ezzel a beállítással például a munkával kapcsolatos térképadatokat törölheti anélkül, hogy ez hatással lenne az otthoni térképadatokra.

- Az összes hologram törléséhez válassza az **Összes hologram eltávolítása lehetőséget.** Ez a parancs törli az eszközön tárolt összes térképadatot, valamint az összes rögzített hologramot. Explicit módon el kell látnia minden hologramot. A korábban elhelyezett hologramokat nem fogja tudni újra kiveszni.

> [!NOTE]
> Miután eltávolítja a közeli vagy az összes hologramot, a HoloLens azonnal megkezdi az aktuális tér beolvasását és leképezését.

### <a name="wi-fi-data-in-spatial-maps"></a>Wi-Fi adatok térbeli térképekben való használata

HoloLens a Wi-Fi, hogy korrelálják az ismert terek adatbázisában tárolt hologram HoloLens helyeket és térképszakaszokat. Az Wi-Fi nem érhetők el a felhasználók számára, és nem küldhetőek el a Microsoftnak a felhő vagy telemetria használatával.

Amíg a Wi-Fi engedélyezve van, a HoloLens a közeli és a közeli Wi-Fi korrelál. Nincs különbség a viselkedésben, függetlenül attól, hogy egy hálózat csatlakoztatva van-e vagy csak a közelben van-e. Ha Wi-Fi le van tiltva, a HoloLens továbbra is keres a térben. A HoloLens azonban több térképadatot kell keresnie a spaces adatbázisban, és több időre lehet szüksége a hologramok kereséséhez. A Wi-Fi információ nélkül a HoloLens-nek össze kell hasonlítani az aktív vizsgálatokat az eszközön tárolt összes hologramhorgony-horgonyval és térképszakaszokkal, hogy megtalálja a térkép megfelelő részét.

## <a name="related-topics"></a>Kapcsolódó témakörök

- [Térbeli leképezés kialakítása](/windows/mixed-reality/spatial-mapping)
