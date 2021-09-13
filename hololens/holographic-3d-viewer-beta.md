---
title: A 3D-megjelenítő bétaverzió használata HoloLens (1. generációs)
description: Ismerteti a 3D-megjelenítő (1. generációs) HoloLens bétaverziója által támogatott fájlokat és szolgáltatásokat, valamint az alkalmazás használatát és hibaelhárítását.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 00e99d3f67e9e4371da12612b9b01c3ce58e71bd
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036027"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>A 3D-megjelenítő bétaverzió használata HoloLens (1. generációs)

3D-megjelenítő Bétaverzió lehetővé teszi a 3D modellek megtekintését HoloLens (1. generációs) verzióban. A támogatott  .fbx fájlokat megnyithatja és megtekintheti Microsoft Edge, OneDrive és más alkalmazásokból.

>[!NOTE]
>Ez a cikk a modern Unity **3D-megjelenítő Beta** alkalmazásra vonatkozik, amely támogatja az .fbx fájlokat, és csak HoloLens (1. generációs) verzióban érhető el. Az 3D-megjelenítő  2. HoloLens-ben előre telepített alkalmazás támogatja az egyéni .glb 3D modellek [](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) megnyitását a vegyes valóság kezdőlapon (további részletekért lásd az eszközkövetelmények áttekintését.

>[!IMPORTANT]
>Bár 3D-megjelenítő bétaverzió elérhető maradhat a Microsoft Store for HoloLens (1. generációs) verzióban, a bétaverzió már nem aktív fejlesztés alatt áll, és már nem támogatott.

Ha nem tudja megnyitni a 3D modellt a 3D-megjelenítő Beta kiadásban, vagy a 3D-modell [](#supported-content-specifications) bizonyos funkciói nem támogatottak, tekintse meg a támogatott tartalomsokajátságokat alább.

A 3D-modellek a 3D-megjelenítő Bétaverzióval való használatra való felépítéséhez vagy optimalizálásához lásd az alábbi [3D-modellek 3D-megjelenítő bétaverzióhoz való optimalizálását.](#optimizing-3d-models-for-3d-viewer-beta)

A 3D-s modelleket kétféleképpen nyithatja meg a HoloLens. További [információ: Az FBX-fájlok HoloLens](#viewing-fbx-files-on-hololens) az alábbi táblázatban.

Ha a témakörök elolvasása után problémába fog kerülni, tekintse meg a [hibaelhárítással kapcsolatos alábbi](#troubleshooting) témakört.

## <a name="supported-content-specifications"></a>Támogatott tartalomsifikációk

### <a name="file-format"></a>Fájlformátum

- FBX formátum
- Az FBX 2015.1.0-s maximális kiadása

### <a name="file-size"></a>Fájlméret

- Minimum 5 KB
- Legfeljebb 500 MB

### <a name="geometry"></a>Geometria

- Csak sokszögmodellek. Nincs alhálózati felület vagy NURB
- Jobbos koordinátarendszer
- A shear in transformation mátrixok nem támogatottak

### <a name="textures"></a>Textúrák

- A textúratérképeket be kell ágyazni az FBX-fájlba
- Támogatott képformátumok
  - JPEG- és PNG-képek
  - BMP-képek (24 bites RGB valódi szín)
  - TGA-képek (24 bites RGB és 32 bites RGBQ true-color)
- A textúra maximális felbontása 2048x2048
- Hálónként legfeljebb egy térkép, egy normál térkép és egy tükrözési kockatérkép
- Az 50%- nál alacsonyabb méretű mintázatok alfa csatornája esetén a képpontok el lesznek vetve

### <a name="animation"></a>Animáció

- Méretezési/rotációs/fordítási animáció az egyes objektumokon
- Skeletal (rigged) animáció lenyúzással
  - Csúcsonként legfeljebb 4 befolyásoló tényező

### <a name="materials"></a>Anyagok

- A Rendszer és a Píme anyagai módosítható paraméterekkel támogatottak
- A Microsoft által támogatott anyagtulajdonságok
  - Fő textúra (RGB + Alfa teszt)
  - Color (RGB)
  - Környezeti szín (RGB)
- Pemet támogató anyagtulajdonságok
  - Fő textúra (RGB + Alfa teszt)
  - Color (RGB)
  - Környezeti szín (RGB)
  - Spekulatív szín (RGB)
  - Készség
  - Tükrözés
- Az egyéni anyagok nem támogatottak
- Hálónként legfeljebb egy anyag
- Legfeljebb egy anyagréteg
- Fájlonként legfeljebb 8 anyag

### <a name="file-and-model-limitations"></a>Fájl- és modellkorlátozások

A bétaverzióban egyidejűleg megnyitható modellek, csúcsok és hálók száma erősen korlátozza a fájlok méretét, valamint 3D-megjelenítő számát:

- Modellenként 500 MB maximális fájlméret
- Csúcsok: 600 000 az összes nyitott modellen kombinálva
- Hálók: 1600 az összes nyitott modellen kombinálva
- Egyszerre legfeljebb 40 nyitott modell

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>3D modellek optimalizálása 3D-megjelenítő bétaverzióhoz

### <a name="special-considerations"></a>Különleges szempontok

- Kerülje a fekete anyagokat vagy a fekete területeket a textúratérképek esetén. Hologramok fényből állnak, így a HoloLens (a fény hiánya) átlátszóként jelenik meg.
- Mielőtt exportálja az FBX-be a létrehozási eszközből, győződjön meg arról, hogy minden geometria látható és fel van oldva, és a geometriát tartalmazó rétegek nincsenek kikapcsolva vagy sablonosak. A láthatóság nem fog teljesülni.
- Kerülje a csomópontok közötti nagyon nagy fordítási eltolódásokat (például 100 000 egység). Ez a modell jitterét okozhatja a mozgatás/skálázható/forgatt modell közben.

### <a name="performance-optimization"></a>Teljesítményoptimalizálás

A legjobb eredmények érdekében tartsa szem előtt a teljesítményt, amikor tartalmat hoz 3D-megjelenítő és érvényesít a HoloLens bétaverziós alkalmazásában. 3D-megjelenítő bétaverzió valós időben renderel tartalmat, és a teljesítményre HoloLens hardverképességek vonatkoznak.  

Egy 3D-s modellben számos olyan változó van, amely hatással lehet a teljesítményre. 3D-megjelenítő bétaverzió egy terhelésre vonatkozó figyelmeztetést fog mutatni, ha több mint 150 000 csúcspont vagy több mint 400 háló van. Az animációk hatással lehetnek más nyitott modellek teljesítményére. A bétaverzióban egyidejűleg megnyitható számmodellek 3D-megjelenítő, csúcsok és hálók teljes száma is [](#file-and-model-limitations)korlátozott (lásd a fájl- és modellkorlátozásokat).  

Ha a 3D modell a modell összetettsége miatt nem fut jól, fontolja meg a következőt:

- Sokszögszám csökkentése
- A gombóbok számának csökkentése a megjelölt animációkban
- Az önálló eltolás elkerülése

A bétaverzió támogatja a kétoldalas 3D-megjelenítő, bár teljesítménybeli okokból alapértelmezés szerint ki van kapcsolva. Ezt a Részletek oldal **Kétoldalas** gombjával **lehet bekapcsolni.** A legjobb teljesítmény érdekében ne legyen szükség kétoldalas renderelésre a tartalomban.

### <a name="validating-your-3d-model"></a>A 3D modell érvényességének igazolása

Ellenőrizze a modellt úgy, hogy megnyitja 3D-megjelenítő bétaverzióban a HoloLens. Válassza a **Részletek gombot** a modell jellemzőinek és a nem támogatott tartalmak figyelmeztetésének megtekintéséhez (ha van ilyen).

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>3D-s modellek renderelése valós élettartamú dimenziókkal

Alapértelmezés szerint a 3D-megjelenítő Bétaverzió a felhasználóhoz képest kényelmes méretben és pozícióban jeleníti meg a 3D-modelleket. Ha azonban egy 3D-s modell valós élettartamra vonatkozó mérésekkel való megjelenítése fontos (például amikor egy helyiségben értékeli a berendezésmodelleket), a tartalom létrehozója beállíthat egy jelzőt a fájl metaadataiban, hogy megakadályozza a modell átméretezését az alkalmazás és a felhasználó számára is.

A modell méretezésének megakadályozásához adjon hozzá egy logikai egyéni attribútumot a jelenet bármely objektumához Microsoft_DisableScale és állítsa true (igaz) értékre. 3D-megjelenítő bétaverzió ezt követően figyelembe veszi az FBX-fájlba becslő FbxSystemUnit adatokat. A bétaverzió 3D-megjelenítő 1 m FBX egységenként.

## <a name="viewing-fbx-files-on-hololens"></a>FBX-fájlok megtekintése a HoloLens

### <a name="open-an-fbx-file-from-microsoft-edge"></a>FBX-fájl megnyitása a Microsoft Edge

Az FBX-fájlok közvetlenül egy webhelyről nyithatók meg az Microsoft Edge a HoloLens.

1. A Microsoft Edge keresse meg a megtekinteni kívánt FBX-fájlt tartalmazó weblapot.
1. Válassza ki a fájlt a letöltéshez.
1. Ha a letöltés befejeződött,  kattintson a Megnyitás gombra a Microsoft Edge a fájl megnyitásához a 3D-megjelenítő Bétaverzióban.

A letöltött fájl később a Letöltések használatával érhető el és nyitható meg Microsoft Edge. A 3D modell mentéséhez és a folyamatos hozzáférés biztosításához töltse le a fájlt a számítógépre, és mentse a saját OneDrive fiókjába. A fájl ezután az alkalmazás OneDrive a HoloLens.

> [!NOTE]
> Egyes letölthető FBX-modellekkel elérhető webhelyek tömörített ZIP formátumban biztosítják őket. 3D-megjelenítő bétaverzió nem tudja közvetlenül megnyitni a ZIP-fájlokat. Ehelyett a számítógépével bontsa ki az FBX-fájlt, és mentse a OneDrive fiókjába. A fájl ezután az alkalmazás OneDrive a HoloLens.

### <a name="open-an-fbx-file-from-onedrive"></a>FBX-fájl megnyitása a OneDrive

Az FBX-fájlok a OneDrive a OneDrive alkalmazással nyithatók HoloLens. Győződjön meg arról, hogy OneDrive telepítette Microsoft Store alkalmazást az HoloLens-on, és hogy már feltöltötte az FBX-fájlt OneDrive gépére.

A OneDrive az FBX-fájlok a HoloLens a 3D-megjelenítő Beta használatával az egyik módon nyithatók meg:

- Indítsa OneDrive a HoloLens, és válassza ki az FBX-fájlt a bétaverzióban 3D-megjelenítő megnyitásához.
- Indítsa 3D-megjelenítő bétaverziót, koppintson a levegőre az eszköztár megjelenítéséhez, majd válassza a **Fájl megnyitása lehetőséget.** OneDrive meg, amely lehetővé teszi egy FBX-fájl kiválasztását.

## <a name="troubleshooting"></a>Hibaelhárítás

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>3D-s modell megnyitásakor figyelmeztetés jelenik meg

Figyelmeztetést fog látni, ha olyan 3D-s modellt próbál megnyitni, amely a 3D-megjelenítő Beta által nem támogatott funkciókat tartalmaz, vagy ha a modell túl összetett, és ez hatással lehet a teljesítményre. 3D-megjelenítő bétaverzió továbbra is betölti a 3D modellt, de a teljesítmény vagy a vizualizációk biztonsága sérülhet.

További információ: [Supported content specifications](#supported-content-specifications) (Támogatott tartalmak specifikációi) és [Optimizing 3D models for 3D-megjelenítő Beta (3D-modellek optimalizálása 3D-megjelenítő bétaverzióhoz).](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Egy figyelmeztetés jelenik meg, és a 3D-s modell nem töltődik be

Hibaüzenet jelenik meg, ha 3D-megjelenítő Beta nem tud 3D-modellt betölteni összetettség vagy fájlméret miatt, vagy ha az FBX-fájl sérült vagy érvénytelen. Akkor is megjelenik egy hibaüzenet, ha elérte az egyidejűleg megnyitható modellek, csúcsok vagy hálók teljes számára vonatkozó korlátot.  

További információ: Támogatott [tartalomsajátok](#supported-content-specifications) és [Fájl- és modellkorlátozások.](#file-and-model-limitations)

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>Betöltődik a 3D-s modell, de nem a várt módon jelenik meg

Ha a 3D-modell nem a várt módon jelenik meg 3D-megjelenítő bétaverzióban, koppintson a légi koppintással az eszköztár megjelenítéséhez, majd válassza a **Részletek lehetőséget.** A bétaverzió által nem támogatott 3D-megjelenítő figyelmeztetésként lesznek kiemelve.

A leggyakoribb probléma a hiányzó textúra, valószínűleg azért, mert nincsenek beágyazva az FBX-fájlba. Ebben az esetben a modell fehéren jelenik meg. Ez a probléma úgy hárítható el a létrehozási folyamatban, hogy a létrehozási eszközből az FBX-be exportál a beágyazási mintázatok lehetőség be van jelölve.

További információ: [Supported content specifications](#supported-content-specifications) (Támogatott tartalmak specifikációi) és [Optimizing 3D models for 3D-megjelenítő Beta (3D-modellek optimalizálása 3D-megjelenítő bétaverzióhoz).](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>Teljesítményes leeséseket tapasztalok a 3D-s modell megtekintése közben

A 3D-s modellek betöltésekor és megtekintésekor a teljesítményt befolyásolhatja a modell összetettsége, az egyidejűleg megnyitott modellek száma vagy az aktív animációkat bemutató modellek száma.

További információ: [Optimizing 3D models for 3D-megjelenítő Beta](#optimizing-3d-models-for-3d-viewer-beta) and File and model limitations (3D-modellek optimalizálása a bétaverzió és a 3D-megjelenítő és a [fájl- és modellkorlátozások esetében).](#file-and-model-limitations)

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>Amikor megnyitok egy FBX-fájlt a HoloLens, az nem nyílik meg a 3D-megjelenítő Bétaverzióban

3D-megjelenítő bétaverziót a rendszer automatikusan társítja az .fbx fájlkiterjesztéssel, amikor telepítve van.

Ha FBX-fájlt próbál megnyitni, és megjelenik egy párbeszédpanel, amely az Microsoft Store-hoz irányítja, akkor jelenleg nincs .fbx fájlkiterjesztéssel társított alkalmazás a HoloLens.

Ellenőrizze, hogy 3D-megjelenítő bétaverzió telepítve van-e. Ha nincs telepítve, töltse le a Microsoft Store a HoloLens.

Ha 3D-megjelenítő bétaverzió már telepítve van, indítsa el 3D-megjelenítő Bétaverziót, majd próbálja meg újra megnyitni a fájlt. Ha a probléma továbbra is fennáll, távolítsa el és telepítse újra 3D-megjelenítő bétaverziót. Ez újra társítja az .fbx fájlkiterjesztést a 3D-megjelenítő bétaverzióhoz.

Ha egy FBX-fájl megnyitásakor a 3D-megjelenítő Beta helyett egy másik alkalmazást nyit meg, az alkalmazás valószínűleg a 3D-megjelenítő Beta után lett telepítve, és átveszi a társítást az .fbx fájlkiterjesztéssel. Ha azt szeretné 3D-megjelenítő bétaverzió .fbx fájlkiterjesztéssel legyen társítva, távolítsa el és telepítse újra 3D-megjelenítő Bétaverziót.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>A Bétaverzió Fájl megnyitása 3D-megjelenítő gombja nem indít el alkalmazást

A **Fájl megnyitása gomb** megnyitja a fájlválasztó függvényhez társított alkalmazást a HoloLens. Ha OneDrive van telepítve, a **Fájl megnyitása gombnak** el kell indítania a OneDrive. Ha azonban jelenleg nincs alkalmazás társítva a HoloLens-on telepített fájlválasztó függvényhez, a rendszer a Microsoft Store.

Ha a **Fájl megnyitása gomb** nem a OneDrive indít el, akkor az alkalmazás valószínűleg a OneDrive után lett telepítve, és átveszi a fájlválasztó függvény társítását. Ha inkább OneDrive a Bétaverzió Fájl  megnyitása gombjának kiválasztásakor, távolítsa el 3D-megjelenítő és telepítse újra a OneDrive.

Ha a **Fájl megnyitása** gomb nem aktív, lehetséges, hogy elérte a bétaverzióban egyszerre 3D-megjelenítő modellek maximális számát. Ha 40 modell van megnyitva a 3D-megjelenítő Bétaverzióban, néhányat be kell zárnia, mielőtt további modelleket nyit meg.

## <a name="additional-resources"></a>További források

- [Támogatási fórumok](http://forums.hololens.com/categories/3d-viewer-beta) – Csak archiválási célokra. Ez a fórum már nem aktív.
- [Harmadik féltől származó közlemények](https://www.microsoft.com/{lang-locale}/legal/products)
