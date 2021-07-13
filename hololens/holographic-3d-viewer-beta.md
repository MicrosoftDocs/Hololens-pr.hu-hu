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
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635483"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>A 3D-megjelenítő bétaverzió használata HoloLens (1. generációs)

3D-megjelenítő Bétaverzió lehetővé teszi a 3D modellek megtekintését HoloLens (1. generációs) verzióban. A támogatott  .fbx fájlokat megnyithatja és megtekintheti Microsoft Edge, OneDrive és más alkalmazásokból.

>[!NOTE]
>Ez a cikk a modern Unity **3D-megjelenítő Beta** alkalmazásra vonatkozik, amely támogatja az .fbx fájlokat, és csak HoloLens (1. generációs) verzióban érhető el. Az 3D-megjelenítő  2. HoloLens-ben előre telepített alkalmazás támogatja az egyéni .glb 3D [](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) modellek megnyitását a vegyes valóság kezdőlapon (további részletekért lásd az eszközkövetelmények áttekintését.

>[!IMPORTANT]
>Bár 3D-megjelenítő bétaverzió elérhető maradhat a Microsoft Store for HoloLens (1. generációs) verzióban, már nem aktív fejlesztés alatt áll, és már nem támogatott.

Ha nem tudja megnyitni a 3D-s modellt a 3D-megjelenítő Beta kiadásban, vagy a 3D-modell bizonyos funkciói nem támogatottak, tekintse meg alább a támogatott tartalomsokajátságokat. [](#supported-content-specifications)

A 3D-modellek a bétaverzióval való használatra való 3D-megjelenítő vagy optimalizálásáról lásd az alábbi [3D-s](#optimizing-3d-models-for-3d-viewer-beta) modellek 3D-megjelenítő bétaverzióhoz való optimalizálását.

A 3D-s modelleket kétféleképpen nyithatja meg a HoloLens. További információért lásd az [FBX-fájlok HoloLens](#viewing-fbx-files-on-hololens) az alábbi táblázatot.

Ha a témakörök elolvasása után problémába fog kerülni, tekintse meg a [hibaelhárítással kapcsolatos alábbi](#troubleshooting) témakört.

## <a name="supported-content-specifications"></a>Támogatott tartalomsokajátok

### <a name="file-format"></a>Fájlformátum

- FBX formátum
- FBX-kiadás maximuma, 2015.1.0

### <a name="file-size"></a>Fájlméret

- Minimum 5 KB
- Legfeljebb 500 MB

### <a name="geometry"></a>Geometria

- Csak sokszögmodellek. Nincs alhálózati felület vagy NURB
- Jobbos koordinátarendszer
- Az átalakítási mátrixok shearok nem támogatottak

### <a name="textures"></a>Textúrák

- A textúratérképeket be kell ágyazni az FBX-fájlba
- Támogatott képformátumok
  - JPEG- és PNG-képek
  - BMP-képek (24 bites RGB valódi szín)
  - TGA-képek (24 bites RGB és 32 bites RGBQ valódi szín)
- A textúra maximális felbontása 2048x2048
- Hálónként legfeljebb egy leképezés, egy normál térkép és egy tükrözési kockatérkép
- A sima mintázatok alfa csatornája esetén a képpontok el lesznek vetve, ha az 50% alatti

### <a name="animation"></a>Animáció

- Méretezési/rotációs/fordítási animáció az egyes objektumokon
- Skeletal (rigged) animáció lekicsinyítve
  - Csúcsonként legfeljebb 4 befolyásoló tényező

### <a name="materials"></a>Anyagok

- A Rendszer és a Pése anyagok támogatottak, amelyek módosítható paraméterekkel vannak támogatva
- Támogatott anyagtulajdonságok a:
  - Fő textúra (RGB + Alfa teszt)
  - Color (RGB)
  - Környezeti szín (RGB)
- A Pemet támogató anyagtulajdonságok
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

- Kerülje a fekete anyagokat vagy a fekete területeket a textúratérképek között. Hologramok fényből készült, így a HoloLens (a fény hiánya) átlátszóként jelenik meg.
- Az FBX-be a létrehozási eszközből való exportálás előtt győződjön meg arról, hogy minden geometria látható és fel van oldva, és a geometriát tartalmazó rétegek nincsenek kikapcsolva vagy sablonosak. A láthatóság nem teljesül.
- Kerülje a csomópontok közötti nagyon nagy fordítási eltolásokat (például 100 000 egység). Ez azt okozhatja, hogy a modell jittert vált ki, miközben áthelyezik, skálázják vagy elforgatják.

### <a name="performance-optimization"></a>Teljesítményoptimalizálás

A legjobb eredmények elérése érdekében tartsa szem előtt a teljesítményt, amikor tartalmat hoz 3D-megjelenítő és érvényesít a HoloLens bétaverziós alkalmazásában. 3D-megjelenítő bétaverzió valós időben renderel tartalmakat, és a teljesítményre HoloLens hardverképességek vonatkoznak.  

A 3D-s modellekben számos olyan változó van, amely hatással lehet a teljesítményre. 3D-megjelenítő bétaverzió egy terhelésre vonatkozó figyelmeztetést fog mutatni, ha több mint 150 000 csúcspont vagy több mint 400 háló van. Az animációk hatással lehetnek más nyitott modellek teljesítményére. A bétaverzióban egyidejűleg megnyitható összes számmodell 3D-megjelenítő re, csúcspontra és hálóra is korlátozások vonatkoznak (lásd: Fájl- és [modellkorlátozások).](#file-and-model-limitations)  

Ha a 3D modell a modell összetettsége miatt nem fut jól, fontolja meg a következőt:

- Sokszögszám csökkentése
- A gombóék számának csökkentése a megjelölt animációban
- Az önelzáródás elkerülése

A bétaverzió támogatja a kétoldalas 3D-megjelenítő renderelést, bár teljesítménybeli okokból alapértelmezés szerint ki van kapcsolva. Ezt a Részletek oldal **Kétoldalas** gombjával **lehet bekapcsolni.** A legjobb teljesítmény érdekében ne legyen szükség kétoldalas renderelésre a tartalomban.

### <a name="validating-your-3d-model"></a>A 3D-modell érvényességének igazolása

Ellenőrizze a modellt úgy, hogy megnyitja 3D-megjelenítő bétaverzióban a HoloLens. A Részletek **gombra** kattintva megtekintheti a modell jellemzőit és a nem támogatott tartalmakra vonatkozó figyelmeztetéseket (ha van ilyen).

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>3D-s modellek renderelése valós életből való dimenziókkal

Alapértelmezés szerint a 3D-megjelenítő Bétaverzió a felhasználóhoz képest kényelmes méretben és pozícióban jeleníti meg a 3D-modelleket. Ha azonban egy 3D-s modell valós életből való méréssel való renderelése fontos (például amikor egy helyiségben értékeli a berendezésmodelleket), a tartalom létrehozója beállíthat egy jelzőt a fájl metaadataiban, hogy megakadályozza a modell átméretezését az alkalmazás és a felhasználó számára is.

A modell méretezésének megakadályozásához adjon hozzá egy logikai egyéni attribútumot a jelenet bármely objektumához, Microsoft_DisableScale állítsa true (igaz) értékre. 3D-megjelenítő Beta figyelembe veszi az FBX-fájlba be van ékelve az FbxSystemUnit adatokat. A bétaverziós 3D-megjelenítő 1 méter FBX egységenként.

## <a name="viewing-fbx-files-on-hololens"></a>FBX-fájlok megtekintése a HoloLens

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Nyisson meg egy FBX-fájlt a Microsoft Edge

Az FBX-fájlok közvetlenül egy webhelyről nyithatók meg a Microsoft Edge a HoloLens.

1. A Microsoft Edge keresse meg a megtekinteni kívánt FBX-fájlt tartalmazó weblapot.
1. Válassza ki a fájlt a letöltéshez.
1. Ha a letöltés befejeződött,  kattintson a Megnyitás gombra a Microsoft Edge a fájl bétaverzióban 3D-megjelenítő megnyitásához.

A letöltött fájl később a Letöltések használatával érhető el és nyitható meg Microsoft Edge. A 3D-modell mentéséhez és a folyamatos hozzáférés biztosításához töltse le a fájlt a számítógépre, és mentse a saját OneDrive fiókjába. A fájl ezután a OneDrive a HoloLens.

> [!NOTE]
> Egyes letölthető FBX-modellekkel elérhető webhelyek tömörített ZIP formátumban biztosítják őket. 3D-megjelenítő bétaverzió nem tudja közvetlenül megnyitni a ZIP-fájlokat. Ehelyett a számítógépével bontsa ki az FBX-fájlt, és mentse a OneDrive fiókjába. A fájl ezután a OneDrive a HoloLens.

### <a name="open-an-fbx-file-from-onedrive"></a>FBX-fájl megnyitása a OneDrive

Az FBX-fájlok a OneDrive a OneDrive alkalmazással HoloLens. Győződjön meg arról, hogy OneDrive telepítette az Microsoft Store-alkalmazást a HoloLens-n, és hogy már feltöltötte az FBX-fájlt a OneDrive gépére.

A OneDrive az FBX-fájlok a HoloLens a 3D-megjelenítő Beta használatával kétféleképpen nyithatók meg:

- Indítsa OneDrive a HoloLens, és válassza ki az FBX-fájlt, hogy a bétaverzióban 3D-megjelenítő meg.
- Indítsa 3D-megjelenítő bétaverziót, koppintson a légi koppintással az eszköztár megjelenítéséhez, majd válassza a **Fájl megnyitása lehetőséget.** OneDrive elindul, így kiválaszthatja az FBX-fájlt.

## <a name="troubleshooting"></a>Hibaelhárítás

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>3D-s modell megnyitásakor figyelmeztetés jelenik meg

Figyelmeztetés jelenik meg, ha olyan 3D modellt próbál megnyitni, amely a 3D-megjelenítő Beta által nem támogatott funkciókat tartalmaz, vagy ha a modell túl összetett, és ez hatással lehet a teljesítményre. 3D-megjelenítő bétaverzió továbbra is betölti a 3D modellt, de a teljesítmény vagy a vizualizációk hűsége sérülhet.

További információ: [Supported content specifications (Támogatott](#supported-content-specifications) tartalomsifikációk) és [Optimizing 3D models for 3D-megjelenítő Beta (3D-modellek optimalizálása 3D-megjelenítő bétaverzióhoz).](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Egy figyelmeztetés jelenik meg, és a 3D-modell nem töltődik be

Hibaüzenet jelenik meg, ha 3D-megjelenítő Beta nem tud 3D-modellt betölteni összetettség vagy fájlméret miatt, vagy ha az FBX-fájl sérült vagy érvénytelen. Akkor is megjelenik egy hibaüzenet, ha elérte az egyidejűleg megnyitható modellek, csúcsok vagy hálók teljes számára vonatkozó korlátot.  

További információ: [Támogatott tartalomsifikációk](#supported-content-specifications) és [Fájl- és modellkorlátozások.](#file-and-model-limitations)

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>Betöltődik a 3D-modellem, de nem a várt módon jelenik meg

Ha a 3D-modell nem a várt módon jelenik meg 3D-megjelenítő bétaverzióban, koppintson a légi koppintással az eszköztár megjelenítéséhez, majd válassza a **Részletek lehetőséget.** A bétaverzió által nem támogatott 3D-megjelenítő figyelmeztetésekként lesznek kiemelve.

A leggyakoribb probléma a hiányzó textúra, valószínűleg azért, mert nincsenek beágyazva az FBX-fájlba. Ebben az esetben a modell fehéren jelenik meg. Ez a probléma a létrehozási folyamat során úgy hárítható el, ha a létrehozási eszközből az FBX-be exportál, és be van jelölve a beágyazási mintázatok beállítás.

További információ: [Supported content specifications (Támogatott](#supported-content-specifications) tartalomsifikációk) és [Optimizing 3D models for 3D-megjelenítő Beta (3D-modellek optimalizálása 3D-megjelenítő bétaverzióhoz).](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>Teljesítmény csökken a 3D-s modell megtekintése közben

A 3D-s modellek betöltésekor és megtekintésekor a teljesítményt befolyásolhatja a modell összetettsége, az egyidejűleg megnyitott modellek száma vagy az aktív animációkat bemutató modellek száma.

További információ: [3D-s](#optimizing-3d-models-for-3d-viewer-beta) modellek optimalizálása a 3D-megjelenítő és a fájl- [és modellkorlátozások alapján.](#file-and-model-limitations)

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>Amikor megnyitok egy FBX-fájlt a HoloLens, az nem nyílik meg a 3D-megjelenítő Bétaverzióban

3D-megjelenítő bétaverzió telepítésekor a rendszer automatikusan társítja a .fbx fájlkiterjesztést.

Ha FBX-fájlt próbál megnyitni, és megjelenik egy párbeszédpanel, amely a Microsoft Store-hoz irányítja, akkor jelenleg nincs .fbx fájlkiterjesztéssel társított alkalmazás a HoloLens.

Ellenőrizze, hogy 3D-megjelenítő bétaverzió telepítve van-e. Ha nincs telepítve, töltse le a Microsoft Store a HoloLens.

Ha 3D-megjelenítő bétaverzió már telepítve van, indítsa el 3D-megjelenítő Bétaverziót, majd próbálja meg újra megnyitni a fájlt. Ha a probléma továbbra is fennáll, távolítsa el és telepítse újra 3D-megjelenítő Bétaverziót. Ez újra társítja az .fbx fájlkiterjesztést a 3D-megjelenítő Bétaverzióval.

Ha egy FBX-fájl megnyitásakor a 3D-megjelenítő Beta helyett egy másik alkalmazást nyit meg, az alkalmazás valószínűleg az 3D-megjelenítő Beta után lett telepítve, és átveszi a társítást az .fbx fájlkiterjesztéssel. Ha azt 3D-megjelenítő, hogy a bétaverzió .fbx fájlkiterjesztéssel legyen társítva, távolítsa el és telepítse újra 3D-megjelenítő Bétaverziót.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>A Bétaverzió Fájl megnyitása 3D-megjelenítő gombja nem indít el alkalmazást

A **Fájl megnyitása gomb** megnyitja a fájlválasztó függvényhez társított alkalmazást a HoloLens. Ha OneDrive van telepítve, a Fájl megnyitása **gombnak** OneDrive. Ha azonban jelenleg nincs alkalmazás társítva a HoloLens-on telepített fájlválasztó függvénnyel, a rendszer a Microsoft Store.

Ha a **Fájl megnyitása gomb** nem a OneDrive indít el, akkor az alkalmazás valószínűleg a OneDrive után lett telepítve, és átveszi a fájlválasztó függvény társítását. Ha inkább a OneDrive szeretné indítani,  amikor a bétaverzióban a Fájl megnyitása 3D-megjelenítő gombra kattint, távolítsa el és telepítse újra a OneDrive.

Ha a **Fájl megnyitása** gomb nem aktív, akkor lehetséges, hogy egyszerre elérte a bétaverzióban 3D-megjelenítő a modellek számára vonatkozó korlátot. Ha a bétaverzióban 40 modell van 3D-megjelenítő, néhányat be kell zárnia, mielőtt további modelleket nyit meg.

## <a name="additional-resources"></a>További források

- [Támogatási fórumok](http://forums.hololens.com/categories/3d-viewer-beta) – Csak archiválási célokra. Ez a fórum már nem aktív.
- [Harmadik féltől származó közlemények](https://www.microsoft.com/{lang-locale}/legal/products)
