---
title: HoloLens környezettel kapcsolatos szempontok
description: A lehető legjobb felhasználói élményt HoloLens, amikor az eszközt a szemére és a környezetére optimalizálja.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: holografikus képkocka, látómező, fov, tárhelyek, környezet, HoloLens, vegyes valóság, vegyes valóságú headsetek
ms.openlocfilehash: 6976527d759e768fa5da72f96395a8b7b390cefd
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036081"
---
# <a name="hololens-environment-considerations"></a>HoloLens környezettel kapcsolatos szempontok

HoloLens holografikus környezetet ötvözi a "valós" világgal, és hologramokat helyez el a környezetében. Egy holografikus alkalmazásablak "lefagy" a falon, egy holografikus ballerina az asztallapon pörg, a tudatlan barátjának a fejére ékesedik. Ha magával ragadó játékokat vagy alkalmazásokat használ, a holografikus világ elterjed, és kitölti a környezetet, de a tér továbbra is látható és mozoghat.

A hologramok az eszköz kikapcsolása után is a helyén maradnak.

## <a name="setting-up-an-environment"></a>Környezet beállítása

HoloLens eszközök tudják, hogyan lehet stabil és  pontos hologramokat adni a felhasználók egy térben való nyomon követésével. Megfelelő követés nélkül az eszköz nem érti a környezetet vagy a benne található felhasználót. Hologramok nem a megfelelő helyeken jelennek meg, nem minden alkalommal jelennek meg ugyanabban a helyen, vagy egyáltalán nem jelennek meg. A felhasználók nyomon követéséhez használt adatokat a térbeli *térkép ábrázolja.*  

A teljesítmény nyomon követését nagy mértékben befolyásolja a felhasználó környezete, és a környezet finomhangolása a stabil és konzisztens követéshez nem tudomány, hanem tudomány. A nyomon követés érdekében számos különböző környezeti tényező van összefedve, Mixed Reality fejlesztőként azonban több tényezőt is figyelembe kell vennie, hogy a hely finomhangolható legyen a jobb nyomon követés érdekében.

### <a name="lighting"></a>Megvilágítás

Windows Mixed Reality vizuális világítást használ a felhasználó tartózkodási helyének nyomon követéséhez. Ha egy környezet túl világos, a kamerák telítettek, és semmi sem látható. Ha a környezet túl sötét, a kamerák nem tudnak elég információt felvenni, és semmi sem látható. A világításnak egyenletesnek és megfelelően világosnak kell lennie, és az emberek nem látnak erőfeszítés nélkül, de nem annyira világosak, mint a fény, amit meg kell nézni.  

Azok a területek is problémásak, ahol egy átfogó halvány területen világos színű pontok vannak, mivel a kamerának alkalmazkodnia kell, amikor be- és kifelé mozog. Ez azt okozhatja, hogy az eszköz "elveszhet", és úgy gondolja, hogy a fényváltozás a hely változásának megfelelő. Egy terület stabil fényszintje jobb nyomon követést fog vezetni.  

A külső világítás a követő instabillá is válhat, mivel a nap idővel jelentősen változhat. Egy nyári és téli időszak azonos területén végzett követés például jelentősen eltérő eredményeket ad, mivel a külső második jelzőfény az év különböző időszakában magasabb lehet.  

Ha van egy mérője, egy stabil 500-1000 másodperces szám jó kezdésnek.  

#### <a name="types-of-lighting"></a>Megvilágítási típusok

A tér különböző fénytípusa is befolyásolhatja a követést. A villanykörték olyan pulzust érnek el, amely a áram-áramot futtatja– ha az AC-gyakoriság 50 Hz, akkor a fényjel 50 Hz-nél. Ember számára ez a sikligálás fel sem fog feltűnni. A HoloLens 30 kamera azonban látja ezeket a változásokat – egyes képkockák jól begyújtottak, némelyik rosszul lesz begyújtva, néhány pedig túl lesz fedve, miközben a kamera megpróbálja kompenzálni a fényalagos pulzusokat.  

Az Egyesült Államokban az elektromos áram szabványa 60 Hz, ezért a villanykörte pulzusát HoloLens HoloLens 60 Hz-es pulzusa a 30 FORD-s képkockaszinthez igazítja HoloLens. Számos országban azonban 50 Hz-es AC-gyakorisági szabvány van, ami azt jelenti, hogy HoloLens néhány képkockát a pulzusok során, míg mások nem. Az európai fényviszonyok különösen is problémákat okozhatnak.  

Van néhány dolog, amit megpróbálhat megoldani a problémák megoldásához. A hőmérséklet, a villanykörte kora és a bemelegítési ciklusok gyakori okai a villanykörték fel- és cserélése. A villanykörték megsziratása és az aktuális rajzolás állandósítása is segíthet.  

### <a name="items-in-a-space"></a>Egy térben lévő elemek

HoloLens egyedi környezeti nevezetességeket( más néven *jellemzőket)* használ, hogy egy térben keresse meg magát.  

Az eszközök szinte soha nem követhetik nyomon a funkciókat nem takarékoskodó területen, mivel nem tudják, hogy hol vannak a térben. A jellemzőknek a tér falán való hozzáadása általában jó módszer a követés javítására. A falra koppintott poszterek, szimbólumok, növények, egyedi objektumok vagy más hasonló elemek mind segítenek. A rendetlen ügyfélszolgálat jó példa a jó nyomon követéshez vezető környezetre – egyetlen területen számos különböző funkció található.  

Emellett egyedi jellemzőket is használhat ugyanabban a térben. Ugyanez a poszter például többször is megismétlődik egy falon, ami összezavarhatja az eszközt, mivel a HoloLens nem fogja tudni, hogy az ismétlődő poszterek melyikét nézi. Az egyedi jellemzők hozzáadásának egyik gyakori módja a maszkolási szalagsorok használata, amelyek egyedi, nem ismétlődő mintákat hoznak létre egy tér fala és padlója mentén.  

A következő kérdést kell feltennie magának: ha csak egy kis mennyiségű jelenetről volt volna szüksége, egyedileg megtalálhatnánk magát a térben? Ha nem, akkor valószínű, hogy az eszköz nyomon követése is problémákba fog esni.

#### <a name="wormholes"></a>Wormegegek

Ha két azonos terület vagy régió van, a követő azt gondolhatja, hogy azonosak. Ennek eredménye az, hogy az eszköz ráveszi magát, hogy azt gondolja, valahol máshol van. Az ilyen típusú ismétlődő területeket *wormegegnek hívjuk.*  

A wormegegek elkerülése érdekében próbálja meg megelőzni az azonos területeket ugyanabban a térben. Azonos területek lehetnek például a gyári állomások, az épületek ablakai, a kiszolgálóállványok vagy a munkaállomások. A területek címkézése vagy egyedi jellemzők hozzáadása az egyes hasonló területekhez segíthet mérsékelni a wormegegeket.

### <a name="movement-in-a-space"></a>Mozgás egy térben

Ha a környezet folyamatosan változik és változik, az eszköz nem rendelkezik stabil funkciókkal, amelyekhez szükség lehet.  

Minél több mozgó objektum van egy térben, beleértve a személyeket is, annál könnyebb elveszíteni a követést. Ismert, hogy a futószalagok, a különböző szerkezetű elemek és a térben sok ember okozhat nyomkövetési problémákat.

A HoloLens gyorsan alkalmazkodni tudnak ezekhez a változásokhoz, de csak akkor, ha ez a terület jól látható az eszköz számára. A ritkábban látott területek késéssel térhetnek vissza a valóságtól, ami hibákat okozhat a térbeli térképen. Egy felhasználó például beolvas egy barátját, majd megfordul, amíg a barát elhagyja a helyiséget. A barát "szellem" ábrázolása megmarad a térbeli leképezési adatokban, amíg a felhasználó újra be nem vizsgálja a most üres területet.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>A felhasználó és a tér elemeinek közelsége

Hasonlóan ahhoz, ahogy az emberek nem tudnak jól a szemük közelében lévő objektumokra koncentrálni, HoloLens, ha objektumok állnak a kamerái közelében. Ha egy objektum túl közel van ahhoz, hogy mindkét kamerával látható legyen, vagy ha egy objektum blokkol egy kamerát, az eszköz sokkal több problémát fog okozhatni az objektum nyomon követése során.  

A kamerák nem láthatnak 15 cm-nél közelebb egy objektumtól.

### <a name="surfaces-in-a-space"></a>Felület egy térben

Az erősen tükröző felületek a szögtől függően valószínűleg eltérőek lesznek, ami hatással van a követésre. Gondoljon egy teljesen új autóra – amikor mozog a rajta, a fény tükrözi a tárgyakat, és különböző tárgyakat lát a felületen mozgáskor. A követő számára a felületen tükrözött különböző objektumok egy változó környezetet képviselnek, és az eszköz elveszíti a követést.

A kevesebb tárgyakat könnyebb nyomon követni.

### <a name="wi-fi-fingerprint-considerations"></a>Wi-Fi ujjlenyomattal kapcsolatos szempontok

Amíg a Wi-Fi engedélyezve van, a térképadatok egy ujjlenyomattal Wi-Fi akkor is korrelálnak, ha nem csatlakoznak tényleges Wi-Fi-hálózathoz/útválasztóhoz. További Wi-Fi nélkül a tárhely és a hologramok kissé lassabban ismerhetőek fel. Ha a Wi-Fi jelek jelentősen változnak, az eszköz azt gondolhatja, hogy teljesen más helyen van.

A rendszer nem küldi el a hálózatazonosítást (például az SSID-t vagy a MAC-címet) a Microsoftnak, és minden Wi-Fi-hivatkozás helyi szinten marad a HoloLens.

## <a name="mapping-new-spaces"></a>Új szóközök leképezése

Amikor új szóközt ad meg (vagy betölt egy meglévőt), egy hálós ábrát fog látni, amely elterül a térben. Ez azt jelenti, hogy az eszköz leképezi a környezetet. Bár a HoloLens idővel teret tanulnak, tippek és trükkök is rendelkezésre állnak a terek leképezésére.

## <a name="environment-management"></a>A környezet kezelése

Két beállítás van, amelyek lehetővé teszik, hogy a felhasználók "megtisztítsák" a hologramokat, és HoloLens" egy szóközt. A beállítások **Hologramok** környezetekben léteznek, a második beállítás pedig az  Adatvédelem alatt is megjelenik a beállításalkalmazásban.  

1. **Törölje a közeli hologramokat.** Ha ezt a beállítást választja, HoloLens törli az összes rögzített hologramot és az eszköz "aktuális területén" tárolt térképadatokat. Ha a hologramok ismét ugyanoda kerülnek, a rendszer létrehoz és tárol egy új térképszakaszt az adatbázisában.

1. **Törölje az összes hologramot.** Ezzel a beállítással a HoloLens törli az ÖSSZES térképadatot és a rögzített hologramokat a teljes adatbázisokban. A rendszer nem fogja újból felfedezni a hologramokat, és minden hologramot újonnan el kell helyezni az adatbázis térképszakaszaiba.

## <a name="hologram-quality"></a>Hologram minősége

Hologramok a környezetben – magas, alacsony és minden más helyen – elhelyezhető, [](/windows/mixed-reality/holographic-frame) de egy holografikus keretben láthatja őket, amely a tekintete előtt található. A legjobb nézet érdekében állítsa be az eszközt úgy, hogy a teljes képkockát lássa. És ne aggódjon, járd végig a környezetét, és fedezze fel!

Ahhoz, [hogy a hologramok](/windows/mixed-reality/hologram) tisztán, egyértelműen és stabilan nézzenek ki, HoloLens csak Önnek kell beszabadulnia. A folyamat végigvezeti HoloLens a folyamat első beállításakor. Később, ha a hologramok nem jól néznek ki, vagy ha számos hibát lát, módosításokat is végezhet.

Ha problémás leképezési tereket használ, próbálja meg törölni a közeli hologramokat, majd újra leképezni a területet.

### <a name="calibration"></a>Kalibrációs

Ha a hologramok jitterynek vagy rezdülnek, vagy ha problémája van a hologramok elhelyezésével, az első dolog, amit ki kell próbálnia, az a Felcsatolás [alkalmazás.](hololens-calibration.md) Ez az alkalmazás abban is segíthet, ha bármilyen kellemetlenséget tapasztal a HoloLens.

A Tanúsítvány alkalmazáshoz való ugráshoz használja a Gépház  >  System Utilities (Rendszer-segédprogramok)  >  **adatokat.** Válassza **az Open Egyedek** megnyitása lehetőséget, és kövesse az utasításokat.

Ha valaki más fogja használni a HoloLens, akkor először futtatnia kell a Hibakezelő alkalmazást, hogy az eszköz megfelelően be legyen állítva számukra.

## <a name="temperature-and-regulatory-information"></a>Hőmérsékleti és szabályozási információk

[HoloLens információk:](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)Többek között a hőmérsékleti tartományra, a megsemmisítésre, a rádió- és tv-interferenciára vonatkozó információkat tartalmaz.

A "környezetről" HoloLens [az Anyagok](https://www.microsoft.com/legal/compliance/materials-substances) és > REACH Article 33 Disclosure on Environmental Compliance (PDF) dokumentumban.

Az alábbi irányelveket kell követnie az eszköz használata esetén:

1. Az eszközt egy órával az eszköz használata előtt tárolja a hőmérsékleti tartományon belüli (Készenléti vagy Ki) környezetben.
1. Az eszközt hőmérsékleti tartományon belüli környezetben használja.
1. Használja az eszközt beltéri környezetben.
1. Árnyékban használja az eszközt; még a beltéri környezetben is elkerülheti a közvetlen aknát windowsos vagy skylights-környezetben.
1. Ha követi a fenti irányelveket, de váratlan problémákat tapasztal, kövesse az alábbi lépéseket a visszajelzés [küldéséhez.](hololens-feedback.md) 
    1. Ellenőrizze, hogy a **Teljes** vagy **a Választható** telemetria engedélyezve van-e az eszközön. Ha nem, engedélyezze. 
    >[!CAUTION]
    > A telemetria nem visszamenőlegesen van aktiválva a hőesemények esetén – engedélyezni kell a hűtés során, különben a rendszer nem rögzíti a szükséges adatokat.
    
    2. Reprodukálja a fűtési problémát.
    3. A hiba dátuma és időpontja.
    4. Küldjön [visszajelzést.](hololens-feedback.md)

## <a name="see-also"></a>Lásd még

- [Térbeli leképezés kialakítása](/windows/mixed-reality/spatial-mapping)
- [Hologramok](/windows/mixed-reality/hologram)
