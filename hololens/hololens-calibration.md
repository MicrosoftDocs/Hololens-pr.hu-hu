---
title: A vizualizáció minőségének és kényelmi javítására
description: Ismerje meg, hogyan lehet a HoloLens-eszközökön található vizualizációk minőségének javítása érdekében berakni az összetűnés távolságát (IPD).
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: értesítés, kényelem, vizualizációk, minőség, ipd, HoloLens, Windows Mixed Reality, VR-headsetek
ms.openlocfilehash: 62d83aa5c6032d15b26fbc7938859bdaf74151f4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924145"
---
# <a name="improve-visual-quality-and-comfort"></a>A vizualizáció minőségének és kényelmi javítására

A HoloLens 2 és a HoloLens (1. generációs) is jobban működik, ha az Ön egyedi szemének megfelelően vannak beállítva.

Bár mindkét eszköznek be kell állítania a legjobb hologramos megjelenítési élményt, különböző technológiai technológiákat és technikákat alkalmaznak.  Ugorjon [a HoloLens 2-re vagy](#calibrating-your-hololens-2) a [HoloLens (1. generációs) rebrációra.](#calibrating-your-hololens-1st-gen)

## <a name="calibrating-your-hololens-2"></a>A HoloLens 2-es

A HoloLens 2 szemkövetési technológiával javítja a virtuális környezetek látási és használati élményét. A HoloLens 2 megszámolása biztosítja, hogy pontosan nyomon tudja követni a tekintetét (és bárki másét, aki az eszközt használja). Emellett segít a felhasználói kényelemben, a hologramok igazításában és a kézkövetésben is. A besziranáció után a hologramok akkor is helyesen jelennek meg, ha a vizor a fejében eltolást vált.

A HoloLens 2 a következő körülmények között arra kéri a felhasználót, hogy állítsa be az eszközt:

- A felhasználó először használja az eszközt
- A felhasználó korábban nem választotta ki az eljárást
- A legutolsó alkalommal, amikor a felhasználó használta az eszközt, a hitelesítési folyamat nem sikerült
- A felhasználó törölte a profilokat
- Az eszköz ki van kapcsolva, és vissza lesz kapcsolva, és a fenti körülmények bármelyike érvényes 


![A hang hangolására vonatkozó figyelmeztetés.](./images/07-et-adjust-for-your-eyes.png)

A folyamat során célokat (gemeket) fog keresni. Nem gond, ha villog a helyiségben, de a helyiség többi objektuma helyett a gemre összpontosít.  Ha a gemeket összpontosítja, a HoloLens megismeri a szempozícióját a holografikus világ renderelésével.

![A figyelmeztetés arra kéri a felhasználót, hogy tartsa a fejét, és kövesse a szemével a pontokat.](./images/07-et-hold-head-still.png)

![Egy gem-példával adhatja meg a parancssort.](./images/08-et-gems.png)

![A hangolás kérésének beállítása.](./images/09-et-adjusting.png)

Ha a siker sikerrel járt, megjelenik egy sikeres művelet képernyője.  Ha nem, olvassa el a [meghibásodások diagnosztizálásának további tudnivalókat.](hololens2-display.md#troubleshooting)

![A figyelmeztetés sikeres volt.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Az eszköz vagy munkamenet megosztásakor való elásás

Több felhasználó is megoszthat egy HoloLens 2-eszközt anélkül, hogy minden személynek végig kellene mennie az eszköz beállításán. Amikor egy új felhasználó először helyezi a fejére az eszközt, a HoloLens 2 automatikusan felszólítja a felhasználót, hogy állítsa be a vizualizációkat. Ha egy korábban már hitelesített vizualizációt használó felhasználó a fejére helyezi az eszközt, a kijelző zökkenőmentesen igazodik a minőséghez és a kényelmes megtekintéshez.  

### <a name="manually-starting-the-calibration-process"></a>Manuálisan el kell indulnia a gyártási folyamatnak

1. A Start kézmozdulattal nyissa meg a [ **Start menüt.**](hololens2-basic-usage.md#start-gesture)
1. Ha a Beállítások alkalmazás nincs a Start menüben kitűzve, válassza a **Minden alkalmazás lehetőséget.**
1. Válassza **a Beállítások** lehetőséget, majd a **System**  >  **Egyentetve**  >  **szemfuttafutta**  >  **lehetőséget.**

   ![A Settings (Beállítások) alkalmazás, amely a Run eye (Szemfutás) beállítást mutatja](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Auto Eye Position Support

A HoloLens 2 szempozíciói lehetővé teszik a pontos hologrampozíciót, a kényelmes megtekintést és a jobb megjelenítési minőséget. A szempozíciók kiszámítása belsőleg, a szemkövetési számítások részeként történt. Ehhez azonban minden felhasználónak szemkövetést kell követnie, még akkor is, ha a felhasználói élményhez nem szükséges szembetekintő adat.

**Az automatikus szempozíció (Auto Eye Position, AEP)** lehetővé teszi, hogy ezek a forgatókönyvek interakció nélküli módon számítsák ki a felhasználó szempozícióit. Az automatikus szempozíció automatikusan elindul a háttérben attól kezdve, hogy a felhasználó az eszközre helyezi. Ha a felhasználó nem rendelkezik előzetes szemkövetési követéssel, az Auto Eye Position 20–30 másodperces feldolgozási idő után elkezdi a felhasználó szempozícióját a megjelenítési rendszer számára. A felhasználói adatok nem maradnak meg az eszközön, és ez a folyamat meg lesz ismételve, ha a felhasználó kikapcsolja és újraindítja az eszközt, vagy ha az eszköz újraindul vagy felébreszti az alvó állapotból.

Az Auto Eye Position funkcióval a rendszer viselkedése megváltozik, ha egy nem skálázható felhasználó helyezi el az eszközt. Ebben a kontextusban egy nem skálázható felhasználó olyanra utal, aki korábban még nem ment végig az eszközön a szemkövetési folyamaton.

| Aktív alkalmazás | Korábbi viselkedés | Viselkedés a Windows Holographic 20H2 Update-től |
|:-------------------|:-----------------|:-----------------------------------|
| Nem tekintett alkalmazás vagy Holographic Shell |Megjelenik a szemkövetési párbeszédpanel. | Nem jelenik meg kérdés. |
| Tekintetre képes alkalmazás | Megjelenik a szemkövetési párbeszédpanel. | A szemkövetési üzenet csak akkor jelenik meg, ha az alkalmazás hozzáfér a tekintetfolyamhoz. |

Ha a felhasználó egy nem tekintetet használó alkalmazásról a tekinteti adatokhoz hozzáférő alkalmazásra tér át, megjelenik a figyelmeztetés. 

Minden más rendszerviselkedés hasonló lesz ahhoz, amikor az aktuális felhasználó nem figyel aktív szemkövetéssel. Az egy szándékból indítható indítási kézmozdulat például nem lesz engedélyezve. A kezdeti beállításhoz nem változik az Out-Of-Box-Experience.

Az olyan élmények esetében, amelyek szemretekintés-adatokat vagy pontos hologram-pozíciót igényelnek, azt javasoljuk, hogy a nem skálázott felhasználók a szemkövetési görbét futtassanak. Elérhető a szemkövetési parancssorból vagy a Beállítások alkalmazás start menüből való elindításával, majd a **System > > Eye > Való** futtatás lehetőség kiválasztásával.

#### <a name="deferred-calibration-prompt"></a>Késleltetett figyelmeztetés

Az Auto Eye Position (Automatikus szem pozíciója) beállítás esetén a szemkövetési párbeszédpanelt a rendszer elhalasztja, amíg egy alkalmazás be nem kéri a Szem tekintete adatait. Ez biztosítja, hogy a rendszer ne kér a felhasználótól olyankor, amikor az aktív alkalmazásnak nincs szüksége tekintetre. Ha az alkalmazásnak tekinteti adatokra van szüksége, és az aktuális felhasználó nincs beállítva, a felhasználó egy figyelmeztetést kap. Ezzel a viselkedéssel a megfelelő időpontban megjeleníthető a szemkövetési figyelmeztetés. Ez a módszer a következő okokból ajánlott:

1.  A Szemkövetési üzenet párbeszédpanelen a felhasználó részletes információkat talál arról, hogy miért van szükség a szemkövetésre.
2.  A felhasználó számára egy mód arra, hogy visszautasítsa a berakott tekintetét.

Ha a felhasználó úgy dönt, hogy elindítja a szemkövetési görbét, a fókusznak a vizsgálat befejezése után vissza kell térnie az eredeti alkalmazáshoz. 

### <a name="calibration-data-and-security"></a>Adatok és biztonság megszabadása

A rendszer helyben tárolja a helyi eszközön található adatokat, és nem társítja őket fiókinformációkhoz. Nincs nyilvántartás róla, hogy ki használta az eszközt anélkül, hogy az eszköz be lett volna küldve. Ez azt jelenti, hogy az új felhasználóknak az eszköz első használatakor be kell majd állítani a vizualizációkat, és azok a felhasználók, akik korábban nem, vagy ha sikertelen volt a hitelesítés, nem voltak megfelelően beállítva.

Az eszköz helyileg legfeljebb 50 profilt képes tárolni. A szám elérése után az eszköz automatikusan törli a legrégebbi nem használt profilt.

A személyes adatok mindig törölhetők az eszközről a Settings Privacy Eye tracker **(Beállítások**  >  **adatvédelmi**  >  **szem követője) lapon.**  

### <a name="disable-calibration"></a>Tiltás letiltása

A lekérdező kérést az alábbi lépésekkel is letilthatja:

1. Válassza **a Beállítások**  >  **Rendszerkombráció**  >  **lehetőséget.**
1. Kapcsolja ki a **When a new person uses this HoloLens (Ha egy új személy használja ezt a HoloLenst) kikapcsolásakor a** rendszer automatikusan megkéri, hogy futtasa a szemét.

> [!IMPORTANT]
> Ez a beállítás hátrányosan befolyásolhatja a hologram renderelési minőségét és kényelmi szolgáltatását.  Ha kikapcsolja ezt a beállítást, a szemkövetéstől függő funkciók (például a szöveg görgetése) többé nem működnek a modern alkalmazásokban.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 szemkövetési technológia

Az eszköz a szemkövetési technológiájával javítja a megjelenítési minőséget, és gondoskodik arról, hogy minden hologram pontosan és kényelmesen megtekinthető legyen 3D-ben. Mivel a szemeket nevezetességként használja, az eszköz minden felhasználóhoz képes alkalmazkodni, és hangolni tudja a vizualizációit, miközben a headset használat közben némileg eltolt.  Minden módosítást a rendszer azonnal, manuális hangolás nélkül végez el.
> [!NOTE]
> Az IPD beállítása nem alkalmazható a Hololens 2-re, mivel a szempozíciókat a rendszer számítja ki.

A HoloLens-alkalmazások a szemkövetés segítségével követik nyomon, hogy hol keres valós időben. Ez a fő képesség, amely segítségével a fejlesztők új kontextust, emberi megértést és interakciókat engedélyeznek a Holographic felhasználói élményben. A fejlesztőknek semmit sem kell tennie a funkció használatának használhatja.

## <a name="calibrating-your-hololens-1st-gen"></a>HoloLens (1. generációs)

A HoloLens (1. generációs) beállítja a hologramos megjelenítést az [összecsuplő](https://en.wikipedia.org/wiki/Interpupillary_distance) távolság (IPD) alapján. Ha az IPD nem pontos, a hologramok instabilnak vagy helytelen távolságnak jelennek meg. A vizualizációk minőségét úgy javíthatja, ha az eszközt az összetűnés távolságra (IPD) kell kalkulálni.

Amikor beállít egy HoloLens- (1. generációs) eszközt, a rendszer arra kéri, hogy állítsa be a vizualizációkat, miután Cortana bemutatkozott. Javasoljuk, hogy a beállítási fázisban teljes körűen végre tudja végrehajtani a javasolt eljárást. Ezt azonban kihagyhatja, ha megvárja, amíg Cortana kéri, majd a "Skip" (Kihagyás) üzenetre vár.

A eljárás során HoloLens megkéri, hogy igazítsa az ujjlenyomatát egy szemenkénti hat célsorozattal. HoloLens ezzel a folyamattal adja meg az IPD-címet a saját szemének megfelelően.

![AZ IPD-ujjlenyomat igazítása a második lépésben](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Manuálisan indítsa el a folyamatot

Ha frissítenie kell a görbét, vagy ha egy új felhasználónak módosítania kell azt, akkor bármikor manuálisan futtathatja a Tanácsadó alkalmazást. A Rendszer alapértelmezés szerint telepíti a Hibabeeső alkalmazást. A Start menüből vagy a **Beállítások** alkalmazásból is elérheti.

A Start **menüben** a Következő lépésekkel futtathat Egy ilyen alkalmazást:

1. A [Bloom kézmozdulattal](hololens1-basic-usage.md) nyissa meg a **Start menüt.**
1. Az összes alkalmazás megtekintéséhez válassza a **+** lehetőséget.
1. Válassza **a Felhozás** lehetőséget.

![Hozzáférés a kiszolgáló alkalmazáshoz a rendszerhéjból](./images/calibration-shell.png)

![A indítóalkalmazás élő kockaként jelenik meg az elindítása után](./images/calibration-livecube-200px.png)

A Settings alkalmazás a Következő lépésekkel futtatható:

1. A [Bloom kézmozdulattal](hololens1-basic-usage.md) nyissa meg a **Start menüt.**
1. Ha **a Beállítások** nincs kitűzve a Start **menübe,** válassza a **+** lehetőséget az összes alkalmazás megtekintéséhez.
1. Válassza a **Beállítások** lehetőséget.
1. Válassza **a System**  >  **Utilities** Open És a  >  **Et.**

![A alkalmazás elindítása a beállítási alkalmazásból](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Modern headsetek

Egyes modern headsetek lehetővé teszi az IPD-beállítás testreszabását. A headset IPD-címének módosításához nyissa meg a Settings (Beállítások) alkalmazást, válassza a Mixed reality Headset display **(Mixed reality**  >  **headset-kijelző)** lehetőséget, majd mozgassa a csúszkavezérlőt. A módosításokat valós időben láthatja a headsetben. Ha ismeri az IPD-címét, esetleg az optometrist felkereste, közvetlenül is megadhatja.

Ezt a beállítást a számítógépen is módosíthatja a **Beállítások**  >  **Mixed Reality** Headset kijelző  >  **kiválasztásával.**

Ha a headset nem támogatja az IPD testreszabását, ez a beállítás le lesz tiltva.
