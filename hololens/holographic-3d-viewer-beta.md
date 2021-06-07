---
title: A 3D-megjelenítő Beta használata a HoloLensben (1. generációs)
description: Ismerteti a HoloLens beta (1. generációs) által támogatott 3D-megjelenítő fájlok és szolgáltatások típusait, valamint az alkalmazás használatát és hibaelhárítását.
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
ms.openlocfilehash: f5481d6466459667deb99232fdd67c4491798cbe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379538"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>A 3D-megjelenítő Beta használata a HoloLensben (1. generációs)

3D-megjelenítő Beta lehetővé teszi 3D-modellek megtekintését a HoloLensben (1. generációs). A támogatott  .fbx fájlokat megnyithatja és megtekintheti Microsoft Edge, a OneDrive-ból és más alkalmazásokból.

>[!NOTE]
>Ez a cikk a modern Unity **3D-megjelenítő Beta** alkalmazásra vonatkozik, amely támogatja az .fbx fájlokat, és csak a HoloLens (1. generációs) verzióban érhető el. Az előre telepített **3D-megjelenítő** a HoloLens 2-ben támogatja az egyéni .glb 3D-modellek megnyitását a vegyes valóság kezdőlapján (további részletekért lásd: Eszközkövetelmények áttekintése. [](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)

>[!IMPORTANT]
>Bár 3D-megjelenítő Bétaverzió továbbra is elérhető maradhat a Microsoft Store for HoloLens (1. generációs) verzióban, a bétaverzió már nem aktív fejlesztés alatt áll, és már nem támogatott.

Ha nem tudja megnyitni a 3D modellt a 3D-megjelenítő Beta kiadásban, vagy a 3D-modell bizonyos funkciói nem támogatottak, tekintse meg a támogatott tartalomsokajátságokat alább. [](#supported-content-specifications)

3D-modellek a bétaverzióval való használatra való 3D-megjelenítő vagy optimalizálásához lásd az alábbi [3D-modellek 3D-megjelenítő bétaverzióhoz való optimalizálását.](#optimizing-3d-models-for-3d-viewer-beta)

A HoloLensben kétféleképpen nyithatja meg a 3D-s modelleket. További [információ: Az FBX-fájlok megtekintése a HoloLensben.](#viewing-fbx-files-on-hololens)

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

- Kerülje a fekete anyagokat vagy a fekete területeket a textúratérképek között. A hologramok világosak, így a HoloLens feketét (a fény hiányát) transzparensként renderel.
- Mielőtt exportálja az FBX-be a létrehozási eszközből, győződjön meg arról, hogy minden geometria látható és fel van oldva, és a geometriát tartalmazó rétegek nincsenek kikapcsolva vagy sablonosak. A láthatóság nem fog teljesülni.
- Kerülje a csomópontok közötti nagyon nagy fordítási eltolódásokat (például 100 000 egység). Ez a modell jitterét okozhatja az áthelyezett/skálázható/forgatt modell esetében.

### <a name="performance-optimization"></a>Teljesítményoptimalizálás

A legjobb eredmények elérése érdekében tartsa szem előtt a teljesítményt, amikor tartalmat hoz és 3D-megjelenítő HoloLensen a 3D-megjelenítő Beta alkalmazásban. 3D-megjelenítő bétaverzió valós időben renderel tartalmakat, és a teljesítményt a HoloLens hardverképességei biztosítanak.  

A 3D-s modellekben számos olyan változó van, amely hatással lehet a teljesítményre. 3D-megjelenítő bétaverzió egy terhelésre vonatkozó figyelmeztetést fog mutatni, ha több mint 150 000 csúcspont vagy több mint 400 háló van. Az animációk hatással lehetnek más nyitott modellek teljesítményére. A bétaverzióban egyidejűleg megnyitható számmodellek 3D-megjelenítő, csúcsok és hálók teljes száma is [](#file-and-model-limitations)korlátozott (lásd a fájl- és modellkorlátozásokat).  

Ha a 3D modell a modell összetettsége miatt nem fut jól, fontolja meg a következőt:

- Sokszögszám csökkentése
- A gombóbok számának csökkentése a megjelölt animációkban
- Az önálló eltolás elkerülése

A kétoldalas renderelést a 3D-megjelenítő támogatja, bár teljesítménybeli okokból alapértelmezés szerint ki van kapcsolva. Ezt a Részletek oldal **Kétoldalas** gombjával **lehet bekapcsolni.** A legjobb teljesítmény érdekében ne legyen szükség kétoldalas renderelésre a tartalomban.

### <a name="validating-your-3d-model"></a>A 3D modell érvényességének igazolása

Ellenőrizze a modellt úgy, hogy megnyitja 3D-megjelenítő HoloLens bétaverziója alatt. Válassza a **Részletek gombot** a modell jellemzőinek és a nem támogatott tartalmak figyelmeztetésének megtekintéséhez (ha van ilyen).

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>3D-s modellek renderelése valós élettartamú dimenziókkal

Alapértelmezés szerint a 3D-megjelenítő Bétaverzió a felhasználóhoz képest kényelmes méretben és pozícióban jeleníti meg a 3D-modelleket. Ha azonban egy 3D-s modell valós élettartamra vonatkozó mérésekkel való renderelése fontos (például amikor egy helyiségben értékeli a berendezésmodelleket), a tartalom létrehozója beállíthat egy jelzőt a fájl metaadataiban, hogy megakadályozza a modell átméretezését az alkalmazás és a felhasználó számára is.

A modell méretezésének megakadályozásához adjon hozzá egy logikai egyéni attribútumot a jelenet bármely objektumához Microsoft_DisableScale és állítsa true (igaz) értékre. 3D-megjelenítő bétaverzió ezután figyelembe veszi az FBX-fájlba be van ásva az FbxSystemUnit adatokat. A bétaverzió 3D-megjelenítő 1 m FBX egységenként.

## <a name="viewing-fbx-files-on-hololens"></a>FBX-fájlok megtekintése a HoloLensben

### <a name="open-an-fbx-file-from-microsoft-edge"></a>FBX-fájl megnyitása a Microsoft Edge

Az FBX-fájlok közvetlenül egy webhelyről nyithatók meg a HoloLens Microsoft Edge használatával.

1. A Microsoft Edge keresse meg a megtekinteni kívánt FBX-fájlt tartalmazó weblapot.
1. Válassza ki a fájlt a letöltéshez.
1. Ha a letöltés befejeződött,  kattintson a Megnyitás gombra a Microsoft Edge a fájlt a 3D-megjelenítő bétaverzióban.

A letöltött fájl később a Letöltések használatával érhető el és nyitható meg Microsoft Edge. A 3D-modell mentéséhez és a folyamatos hozzáférés biztosításához töltse le a fájlt a számítógépre, és mentse a OneDrive-fiókjába. A fájl ezután a HoloLens OneDrive alkalmazásában nyitható meg.

> [!NOTE]
> Egyes letölthető FBX-modellekkel elérhető webhelyek tömörített ZIP formátumban biztosítják őket. 3D-megjelenítő bétaverzió nem tudja közvetlenül megnyitni a ZIP-fájlokat. Ehelyett a számítógépével bontsa ki az FBX-fájlt, és mentse a OneDrive-fiókjába. A fájl ezután a HoloLens OneDrive alkalmazásában nyitható meg.

### <a name="open-an-fbx-file-from-onedrive"></a>FBX-fájl megnyitása a OneDrive-ról

Az FBX-fájlok a OneDrive-ról a HoloLens OneDrive alkalmazásával nyithatók meg. Győződjön meg arról, hogy telepítette a OneDrive-ot Microsoft Store HoloLens-alkalmazással, és hogy már feltöltötte az FBX-fájlt a OneDrive-ra a számítógépén.

A OneDrive-ban az FBX-fájlok a 3D-megjelenítő Beta használatával nyithatóak meg a HoloLensben a következő két módszer egyikével:

- Indítsa el a OneDrive-ot a HoloLensben, és válassza ki az FBX-fájlt a 3D-megjelenítő megnyitásához.
- Indítsa 3D-megjelenítő bétaverziót, koppintson a légi koppintással az eszköztár megjelenítéséhez, majd válassza a **Fájl megnyitása lehetőséget.** Elindul a OneDrive, amely lehetővé teszi egy FBX-fájl kiválasztását.

## <a name="troubleshooting"></a>Hibaelhárítás

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>3D-s modell megnyitásakor figyelmeztetés jelenik meg

Figyelmeztetés jelenik meg, ha olyan 3D modellt próbál megnyitni, amely a 3D-megjelenítő Beta által nem támogatott funkciókat tartalmaz, vagy ha a modell túl összetett, és ez hatással lehet a teljesítményre. 3D-megjelenítő bétaverzió továbbra is betölti a 3D modellt, de a teljesítmény vagy a vizualizációk hűsége sérülhet.

További információ: [Supported content specifications (Támogatott](#supported-content-specifications) tartalomsifikációk) és [Optimizing 3D models for 3D-megjelenítő Beta (3D-modellek optimalizálása 3D-megjelenítő bétaverzióhoz).](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Egy figyelmeztetés jelenik meg, és a 3D-modell nem töltődik be

Hibaüzenet jelenik meg, ha 3D-megjelenítő Beta nem tud 3D-modellt betölteni összetettség vagy fájlméret miatt, vagy ha az FBX-fájl sérült vagy érvénytelen. Akkor is megjelenik egy hibaüzenet, ha elérte az egyidejűleg megnyitható modellek, csúcsok vagy hálók teljes számára vonatkozó korlátot.  

További információ: [Támogatott tartalomsifikációk](#supported-content-specifications) és [Fájl- és modellkorlátozások.](#file-and-model-limitations)

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>Betöltődik a 3D-modellem, de nem a várt módon jelenik meg

Ha a 3D-modell nem a várt módon jelenik meg 3D-megjelenítő bétaverzióban, koppintson a légi koppintással az eszköztár megjelenítéséhez, majd válassza a **Részletek lehetőséget.** A bétaverzió által nem támogatott 3D-megjelenítő figyelmeztetésekként lesznek kiemelve.

A leggyakoribb probléma a hiányzó textúra, valószínűleg azért, mert nincsenek beágyazva az FBX-fájlba. Ebben az esetben a modell fehéren jelenik meg. Ez a probléma a létrehozási folyamat során úgy hárítható el, ha a létrehozási eszközből az FBX-be exportál, és be van jelölve a beágyazási textúra beállítás.

További információ: [Supported content specifications (Támogatott](#supported-content-specifications) tartalomsifikációk) és [Optimizing 3D models for 3D-megjelenítő Beta (3D-modellek optimalizálása 3D-megjelenítő bétaverzióhoz).](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>Teljesítmény csökken a 3D-s modell megtekintése közben

A 3D-s modellek betöltésekor és megtekintésekor a teljesítményt befolyásolhatja a modell összetettsége, az egyidejűleg megnyitott modellek száma vagy az aktív animációkat bemutató modellek száma.

További információ: [3D-s](#optimizing-3d-models-for-3d-viewer-beta) modellek optimalizálása a 3D-megjelenítő és a fájl- [és modellkorlátozások alapján.](#file-and-model-limitations)

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>Amikor megnyitok egy FBX-fájlt a HoloLensben, az nem nyílik meg a 3D-megjelenítő Bétaverzióban

3D-megjelenítő bétaverzió telepítésekor a rendszer automatikusan társítja a .fbx fájlkiterjesztést.

Ha FBX-fájlt próbál megnyitni, és megjelenik egy párbeszédpanel, amely a Microsoft Store-hoz irányítja, akkor jelenleg nincs .fbx fájlkiterjesztéssel társított alkalmazás a HoloLensben.

Ellenőrizze, hogy 3D-megjelenítő bétaverzió telepítve van-e. Ha nincs telepítve, töltse le Microsoft Store HoloLensről.

Ha 3D-megjelenítő bétaverzió már telepítve van, indítsa el 3D-megjelenítő Bétaverziót, majd próbálja meg újra megnyitni a fájlt. Ha a probléma továbbra is fennáll, távolítsa el és telepítse újra 3D-megjelenítő Bétaverziót. Ez újra társítja az .fbx fájlkiterjesztést a 3D-megjelenítő Bétaverzióval.

Ha egy FBX-fájl megnyitásakor a 3D-megjelenítő Beta helyett egy másik alkalmazást nyit meg, az alkalmazás valószínűleg az 3D-megjelenítő Beta után lett telepítve, és átveszi a társítást az .fbx fájlkiterjesztéssel. Ha azt 3D-megjelenítő, hogy a bétaverzió .fbx fájlkiterjesztéssel legyen társítva, távolítsa el és telepítse újra 3D-megjelenítő Bétaverziót.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>A Bétaverzió Fájl megnyitása 3D-megjelenítő gombja nem indít el alkalmazást

A **Fájl megnyitása gomb** megnyitja a HoloLens fájlválasztó függvényéhez társított alkalmazást. Ha a OneDrive telepítve van, a **Fájl megnyitása gomb** elindítja a OneDrive-ot. Ha azonban jelenleg nincs alkalmazás társítva a HoloLensen telepített fájlválasztó függvénnyel, a rendszer a Microsoft Store.

Ha a **Fájl megnyitása gomb** nem a OneDrive-ot indítja el, akkor az alkalmazás valószínűleg a OneDrive után lett telepítve, és átveszi a fájlválasztó függvény társítását. Ha azt szeretné, hogy a  OneDrive a Bétaverzió Fájl megnyitása gombjának 3D-megjelenítő indul el, távolítsa el és telepítse újra a OneDrive-ot.

Ha a **Fájl megnyitása** gomb nem aktív, akkor lehetséges, hogy egyszerre elérte a bétaverzióban 3D-megjelenítő a modellek számára vonatkozó korlátot. Ha a bétaverzióban 40 modell van 3D-megjelenítő, néhányat be kell zárnia, mielőtt további modelleket nyit meg.

## <a name="additional-resources"></a>További források

- [Támogatási fórumok](http://forums.hololens.com/categories/3d-viewer-beta) – Csak archiválási célokra. Ez a fórum már nem aktív.
- [Harmadik féltől származó közlemények](https://www.microsoft.com/{lang-locale}/legal/products)
