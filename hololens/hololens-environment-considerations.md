---
title: HoloLens környezettel kapcsolatos szempontok
description: A lehető legjobb felhasználói élményt HoloLens az eszköz a szemnek és a környezetnek való optimalizálása során.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: holografikus képkocka, látómező, fov, környezet, környezet, how-to, HoloLens, mixed reality, mixed reality headsetek
ms.openlocfilehash: 6976527d759e768fa5da72f96395a8b7b390cefd
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427305"
---
# <a name="hololens-environment-considerations"></a>HoloLens környezettel kapcsolatos szempontok

HoloLens a holografikus környezetet a "valós" világgal ötvözi, és hologramokat helyez el a környezetében. Egy holografikus alkalmazásablak "lefagy" a falon, egy holografikus ballerina az asztallapon pörg, és a tudatlan barát fejére dől a füle. Ha magával ragadó játékot vagy alkalmazást használ, a holografikus világ elterjed majd, és kitölti a környezetet, de látható és mozoghat a térben.

A hologramok a helyükön maradnak, még akkor is, ha kikapcsolja az eszközt.

## <a name="setting-up-an-environment"></a>Környezet beállítása

HoloLens eszközök tudják, hogyan helyezzenek el stabil  és pontos hologramokat a felhasználók téren való nyomon követésével. Megfelelő követés nélkül az eszköz nem érti a környezetet vagy a benne található felhasználót. Hologramok nem a megfelelő helyeken jelennek meg, nem minden alkalommal jelennek meg ugyanazon a helyen, vagy egyáltalán nem jelennek meg. A felhasználók nyomon követéséhez használt adatokat a térbeli *térkép ábrázolja.*  

A teljesítmény nyomon követését nagy mértékben befolyásolja a felhasználó környezete, és a környezet hangolása a stabil és konzisztens követéshez nem tudomány, hanem tudomány. A nyomon követés érdekében számos különböző környezeti tényező van összefedve, Mixed Reality fejlesztőként azonban több tényezőt is figyelembe kell vennie, hogy a jobb nyomkövetés érdekében hangoljon egy helyet.

### <a name="lighting"></a>Megvilágítás

Windows Mixed Reality a vizualizációs világítást használja a felhasználó tartózkodási helyének nyomon követéséhez. Ha egy környezet túl világos, a kamerák telítettek, és semmi sem látható. Ha a környezet túl sötét, a kamerák nem tudnak elég információt felvenni, és semmi sem látható. A világításnak egyenletesnek és megfelelően világosnak kell lennie, hogy az emberek erőfeszítés nélkül látják őket, de ne olyan világosak, hogy a fény ne legyen látható.  

Azok a területek is problémásak, ahol egy átfogó halvány területen világos színű pontok vannak, mivel a kamerának alkalmazkodni kell a világos területek be- és kifelé mozgatáskor. Ez azt okozhatja, hogy az eszköz "elveszhet", és úgy gondolja, hogy a fényváltozás a hely változásának megfelelő. Egy terület stabil fényszintje jobb nyomon követést biztosít.  

A külső világítás a követő instabilitását is okozhatja, mivel a nap jelentősen változhat idővel. Ha például egy nyári és téli időszakban ugyanabban a térben kell nyomon követni, az jelentősen eltérő eredményeket fog elérni, mivel a második villanyfény az év különböző időszakában magasabb lehet.  

Ha van egy 500-1000-es mérője, akkor jó kezdőnek 500-1000 forint.  

#### <a name="types-of-lighting"></a>Megvilágítási típusok

A tér különböző típusú világítása is befolyásolhatja a követést. A villanykörték olyan pulzust adnak, amikor az áramáram átfut rajta – ha a áram-vissza írási gyakoriság 50 Hz, akkor a fényjel 50 Hz-nél. Ez az emberi élet nem vette észre. A HoloLens 30 kamera azonban látja ezeket a változásokat – egyes képkockák jól begyújtottak, némelyik rosszul lesz begyújtva, és néhány túl lesz fedve, mivel a kamera megpróbálja kompenzálni a fény pulzusát.  

Az Egyesült Államokban az elektromos áram szabványa 60 Hz, ezért a villanykörte pulzusát a HoloLens HoloLens 60 Hz-es pulzusa a HoloLens 30 FORD-s képkocka-értékéhez igazítja. Számos országban azonban 50 Hz-es AC-gyakorisági szabvány van, ami azt jelenti, hogy HoloLens egyes képkockák az pulzusok során lesznek felveve, mások viszont nem. Az európai fényviszonyok különösen is problémákat okozhatnak.  

Van néhány dolog, amit megpróbálhat megoldani a problémák megoldásához. A hőmérséklet, a villanykörte kora és a bemelegítési ciklusok gyakori okai a villanykörték eleredésének és cseréjének. A villanykörték megsziratása és az aktuális rajzolás állandósítása is segíthet.  

### <a name="items-in-a-space"></a>Egy térben lévő elemek

HoloLens egyedi környezeti nevezetességeket, más néven jellemzőket használ a hely helyének azonosításához.  

Az eszközök szinte soha nem tudják nyomon követni a funkciókat nem takarékoskodó területen, mivel nem tudhatja, hogy hol van a tér. A jellemzők egy tér falának hozzáadása általában jó módszer a követés javítására. A falra koppintott poszterek, szimbólumok, növények, egyedi objektumok vagy más hasonló elemek mind segítenek. A zavaros asztal jó példa a jó nyomon követéshez vezető környezetre – egy területen számos különböző funkció található.  

Emellett egyedi jellemzőket is használhat ugyanabban a térben. Ugyanaz a poszter például többször is meg lesz ismételve egy falon, ami összezavarhatja az eszközt, mivel a HoloLens nem fogja tudni, hogy az ismétlődő poszterek melyikét nézik. Az egyedi jellemzők hozzáadásának egyik gyakori módja a maszkolási szalagsorok használata, amelyek egyedi, nem ismétlődő mintákat hoznak létre a tér fala és padlója mentén.  

Jó kérdést kell feltennie magának: ha csak egy kis jelenetre kíváncsi, akkor egyedileg meg tudná találni magát a térben? Ha nem, akkor valószínű, hogy az eszköz nyomon követése is problémába fog esni.

#### <a name="wormholes"></a>Wormholes (Wormholes)

Ha két azonos terület vagy régió van, a követő azt gondolhatja, hogy azonosak. Ez azt a eredménythez vezet, hogy az eszköz ráveszi magát arra, hogy valahol máshol van. Az ilyen típusú ismétlődő területeket *wormegegnek hívjuk.*  

A wormholes elkerülése érdekében próbálja meg megelőzni az azonos területeket ugyanabban a térben. Azonos területek lehetnek például a gyári állomások, az épületek ablakai, a kiszolgálóállványok vagy a munkaállomások. A területek címkézése vagy egyedi jellemzők hozzáadása az egyes hasonló területekhez segíthet a wormholes mérséklése érdekében.

### <a name="movement-in-a-space"></a>Mozgás egy térben

Ha a környezet folyamatosan változik és változik, az eszköz nem rendelkezik olyan stabil funkciókkal, amelyek között keresve lehet.  

Minél több mozgó objektum található egy térben, köztük személyek is, annál könnyebb a nyomon követés elveszni. Ismert, hogy a futószalagok, a különböző szerkezetű elemek és sok ember a térben is nyomon követési problémákat okozhat.

A HoloLens gyorsan alkalmazkodni tudnak ezekhez a változásokhoz, de csak akkor, ha ez a terület jól látható az eszköz számára. A ritkábban látható területek késést okozhatnak a valósággal, ami hibákat okozhat a térbeli térképen. Egy felhasználó például beolvas egy barátját, majd megfordul, miközben a barát elhagyja a helyiséget. A barát "szelleme" egészen addig marad a térleképezési adatokban, amíg a felhasználó újra be nem vizsgálja a most üres területet.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>A felhasználó és a tér elemeinek közelsége

Hasonlóan ahhoz, ahogy az emberek nem tudnak jól koncentrálni a szemhez közel lévő objektumokra, HoloLens, ha objektumok állnak a kameráihoz közel. Ha egy objektum túl közel van ahhoz, hogy mindkét kamerával látható legyen, vagy ha egy objektum blokkol egy kamerát, az eszköz sokkal több problémát fog okozhatni az objektum nyomon követése során.  

A kamerák nem látnak 15 cm-nél közelebb egy objektumtól.

### <a name="surfaces-in-a-space"></a>Felület egy térben

Az erősen tükröző felületek valószínűleg eltérőek lesznek a szögtől függően, ami hatással van a követésre. Gondoljon egy teljesen új autóra – amikor mozog a rajta, a fény tükrözi a tárgyakat, és különböző objektumokat lát a felületen mozgáskor. A követő számára a felületen tükrözött különböző objektumok egy változó környezetet képviselnek, és az eszköz elveszíti a követést.

A kevesebb tárgyakat könnyebb nyomon követni.

### <a name="wi-fi-fingerprint-considerations"></a>Wi-Fi ujjlenyomattal kapcsolatos szempontok

Amíg a Wi-Fi engedélyezve van, Wi-Fi a térképadatok egy ujjlenyomattal lesznek korrelálva, még akkor is, ha nem csatlakoznak tényleges Wi-Fi-hálózathoz/útválasztóhoz. További Wi-Fi nélkül a hely és a hologramok kissé lassabban ismerhetőek fel. Ha a Wi-Fi jelek jelentősen változnak, az eszköz azt gondolhatja, hogy teljesen más helyen van.

A rendszer nem küld hálózati azonosítást (például SSID-t vagy MAC-címet) a Microsoftnak, és minden Wi-Fi-hivatkozás helyi szinten marad a HoloLens.

## <a name="mapping-new-spaces"></a>Új szóközök leképezése

Amikor új szóközt ad meg (vagy betölt egy meglévőt), egy, a térben elterülő hálós grafikát fog látni. Ez azt jelenti, hogy az eszköz leképezi a környezetet. Bár a HoloLens idővel teret tanulnak, tippek és trükkök is rendelkezésre állnak a terek leképezésére.

## <a name="environment-management"></a>A környezet kezelése

Két beállítás van, amelyek lehetővé teszik a felhasználók számára, hogy "megtisztítsák" a hologramokat, és HoloLens" a szóközt. A beállítások **Hologramok** és környezetekben léteznek, a második beállítás pedig  az Adatvédelem alatt is megjelenik a beállításalkalmazásban.  

1. **Törölje a közeli hologramokat.** Ha ezt a beállítást választja, HoloLens törli az összes rögzített hologramot és az eszköz "aktuális térben" tárolt térképi adatait. Ha a hologramok ismét ugyanoda kerülnek, létrejön egy új térképszakasz, amely az adatbázisban lesz tárolva.

1. **Törölje az összes hologramot.** Ezzel a beállítással a HoloLens törli az ÖSSZES térképadatot és rögzített hologramokat a teljes adatbázisból. A rendszer nem fogja újra felfedezni a hologramokat, és minden hologramot újonnan kell elhelyezni az adatbázis térképszakaszainak tárolására.

## <a name="hologram-quality"></a>Hologram minősége

Hologramok a környezetben – magas, alacsony és körül lehet helyezni – de egy holografikus képkockán fogja látni őket, amely [a](/windows/mixed-reality/holographic-frame) tekintete előtt áll. A legjobb nézet érdekében állítsa be az eszközt úgy, hogy a teljes képkockát lássa. Ne aggódjon, ha körbe járja a környezetét, és felfedezi a felfedezést!

Ahhoz, hogy [a hologramok](/windows/mixed-reality/hologram) szépnek, egyértelműnek és stabilnak nézzenek, HoloLens csak Ön számára kell besziratálni a hologramokat. A folyamat végigvezeti a HoloLens, amikor először beállít egy újat. Később, ha a hologramok nem jól néznek ki, vagy sok hibát lát, módosításokat is lehet végezni.

Ha nem tudja leképezni a helyeket, próbálja meg törölni a közeli hologramokat, és újra leképezni a területet.

### <a name="calibration"></a>Kalibrációs

Ha a hologramok jitterynek vagy rezdülnek, vagy ha problémája van a hologramok elhelyezésekor, az első dolog, amit meg kell próbálnia, az [Az utánozás alkalmazás.](hololens-calibration.md) Ez az alkalmazás abban is segíthet, ha bármilyen kellemetlenséget tapasztal a HoloLens.

A Utilities alkalmazáshoz való Gépház  >    >  **stb.** Válassza **az Open Egyedek** megnyitása lehetőséget, és kövesse az utasításokat.

Ha valaki más is használni fogja a HoloLens, akkor először futtatnia kell a Hibakezelő alkalmazást, hogy az eszköz megfelelően be legyen állítva számukra.

## <a name="temperature-and-regulatory-information"></a>Hőmérsékleti és szabályozási információk

[HoloLens információk:](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)Többek között a hőmérsékleti tartományra, a megsemmisítésre, a rádió- és TV-interferenciára vonatkozó információkat tartalmaz.

Az "információ" részleteit HoloLens [az Anyagok](https://www.microsoft.com/legal/compliance/materials-substances) és > REACH Article 33 Disclosure on Environmental Compliance (PDF) dokumentumban.

Az alábbi irányelveket kell követnie az eszköz használata esetén:

1. Az eszközt egy órával az eszköz használata előtt egy olyan környezetben tárolja, amely a hőmérsékleti tartományon belül van (készenlétben vagy kikapcsolva).
1. Az eszközt hőmérsékleti tartományon belüli környezetben használja.
1. Az eszközt beltéri környezetben használja.
1. Az eszköz árnyékolása; Még a beltéri környezetben is elkerülheti a közvetlen aknát, ha ablakok vagy skylightok vannak.
1. Ha követi a fenti irányelveket, de váratlan problémákat tapasztal, kövesse az alábbi lépéseket a visszajelzések [küldéséhez.](hololens-feedback.md) 
    1. Ellenőrizze, **hogy a Teljes** vagy a **Választható** telemetria engedélyezve van-e az eszközön. Ha nem, engedélyezze. 
    >[!CAUTION]
    > A telemetria nem visszamenőleges a hőesemények esetén – a hőmérsékleti események során engedélyezni kell, különben a rendszer nem rögzíti a szükséges adatokat.
    
    2. Reprodukálja a fűtési problémát.
    3. A dátum és az időpont, amikor a incidens történt.
    4. Küldjön [visszajelzést.](hololens-feedback.md)

## <a name="see-also"></a>Lásd még

- [Térbeli leképezés kialakítása](/windows/mixed-reality/spatial-mapping)
- [Hologramok](/windows/mixed-reality/hologram)
