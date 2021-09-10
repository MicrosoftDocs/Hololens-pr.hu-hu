---
title: A vizualizáció minőségének és kényelmi javítására
description: Ismerje meg, hogyan lehet az összetűnés távolság (IPD) bekalibrációját a vizualizációk minőségének javítása érdekében HoloLens eszközökön.
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
ms.openlocfilehash: b3d917c71ac7441aeaf8dcbc25748ee07b9fbfa3
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427855"
---
# <a name="improve-visual-quality-and-comfort"></a>A vizualizáció minőségének és kényelmi javítására

HoloLens 2 és HoloLens (1. generációs) is jobban működik, ha az Ön egyedi szemének megfelelően vannak beállítva.

Bár mindkét eszköznek a legjobb hologramos megtekintési élményre kell beszabadnia, különböző technológiai technológiákat és technikákat alkalmaznak.  Ugorjon [a HoloLens 2-](#calibrating-your-hololens-2) vagy [HoloLens (1. generációs) berekentséghez.](#calibrating-your-hololens-1st-gen)

## <a name="calibrating-your-hololens-2"></a>A 2. HoloLens megszabadul

HoloLens 2. felhasználó szemkövetési technológiát használ a virtuális környezet jobb látási és interakciós élményéhez. A 2. HoloLens megszámolása biztosítja, hogy pontosan nyomon tudja követni a tekintetét (és bárki más szemét, aki az eszközt használja). Emellett segít a felhasználói kényelemben, a hologramok igazításában és a kézkövetésben is. A hitelesítés után a hologramok akkor is helyesen jelennek meg, ha a vizor a fejében eltolást vált.

HoloLens 2. eset arra kéri a felhasználót, hogy a következő körülmények között állítsa be az eszköz bekalkalmaját:

- A felhasználó először használja az eszközt
- A felhasználó korábban nem választotta ki az eljárást
- A személyes eljárás nem sikerült, amikor a felhasználó utoljára használta az eszközt
- A felhasználó törölte a profilokat
- Az eszköz ki van kapcsolva, és vissza lesz kapcsolva, és a fenti körülmények bármelyike érvényes 


![A hang hangolására vonatkozó figyelmeztetés.](./images/07-et-adjust-for-your-eyes.png)

A folyamat során célokat (gemeket) fog keresni. Nem gond, ha villog a bepillantás közben, de a helyiség többi objektuma helyett a gemre összpontosíthat.  A gemre való összpontosítás HoloLens, hogy megismerje a holografikus világ renderelésének szempozícióját.

![A figyelmeztetés arra kéri a felhasználót, hogy tartsa a fejét, és kövesse a szemével a pontokat.](./images/07-et-hold-head-still.png)

![Egy gem-példával adhatja meg a parancssort.](./images/08-et-gems.png)

![A hangolás kérésének beállítása.](./images/09-et-adjusting.png)

Ha a siker sikerrel járt, megjelenik egy sikeres művelet képernyője.  Ha nem, olvassa el a [meghibásodások diagnosztizálásának további tudnivalókat.](hololens2-display.md#troubleshooting)

![A figyelmeztetés sikeres volt.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Az eszköz vagy munkamenet megosztásakor való elásás

Több felhasználó osztozhat egy HoloLens 2 eszközön anélkül, hogy minden személynek végig kellene mennie az eszközbeállításon. Amikor egy új felhasználó először helyezi a fejére az eszközt, a 2. HoloLens a 2. lépés automatikusan felszólítja a felhasználót a vizualizációk beraknira. Ha egy korábban már hitelesített vizualizációt használó felhasználó a fejére helyezi az eszközt, a kijelző zökkenőmentesen igazodik a minőséghez és a kényelmes megtekintéshez.  

### <a name="manually-starting-the-calibration-process"></a>Manuálisan el kell indulnia a gyártási folyamatnak

1. Az indítási kézmozdulattal nyissa meg a [**Start menü.**](hololens2-basic-usage.md#start-gesture)
1. Ha a Gépház alkalmazás nincs kitűzve a **Start menübe,** válassza a **Minden alkalmazás lehetőséget.**
1. Válassza **Gépház** lehetőséget, majd válassza a **System**  >  **Egyedek**  >  **szemkontraszt futtatása**  >  **lehetőséget.**

   ![A Gépház alkalmazást, amely a Run eye (Futtatás szem) beállítást mutatja.](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Automatikus szempozíció támogatása

A HoloLens 2-ben a szempozíciók lehetővé teszik a pontos hologrampozíciót, a kényelmes megtekintést és a jobb megjelenítési minőséget. A szempozíciók kiszámítása belsőleg, a szemkövetési számítások részeként történt. Ehhez azonban minden felhasználónak szemkövetést kell követnie, még akkor is, ha a felhasználói élményhez nem szükséges szembetekintő adat.

**Az automatikus szempozíció (Auto Eye Position, AEP)** lehetővé teszi, hogy ezek a forgatókönyvek interakció nélküli módon számítsák ki a felhasználó szempozícióit. Az automatikus szempozíció automatikusan elindul a háttérben attól kezdve, hogy a felhasználó az eszközre helyezi. Ha a felhasználó nem rendelkezik előzetes szemkövetési követéssel, az Auto Eye Position 20–30 másodperces feldolgozási idő után elkezdi a felhasználó szempozícióját a megjelenítési rendszer számára. A felhasználói adatok nem maradnak meg az eszközön, és ez a folyamat meg lesz ismételve, ha a felhasználó kikapcsolja és visszateszi az eszközt, vagy ha az eszköz újraindul vagy felébreszti az alvó állapotból.

Az Auto Eye Position funkcióval a rendszer viselkedése megváltozik, ha egy nem skálázható felhasználó helyezi el az eszközt. Ebben a kontextusban a nem skálázható felhasználó olyanra utal, aki még nem ment végig az eszközön a szemkövetési folyamaton.

| Aktív alkalmazás | Korábbi viselkedés | A Holographic Windows 20H2-es frissítésének viselkedése |
|:-------------------|:-----------------|:-----------------------------------|
| Nem tekintett alkalmazás vagy Holographic Shell |Megjelenik a szemkövetési párbeszédpanel. | Nem jelenik meg kérdés. |
| Tekintetre képes alkalmazás | Megjelenik a szemkövetési párbeszédpanel. | A szemkövetési üzenet csak akkor jelenik meg, ha az alkalmazás hozzáfér a tekintetfolyamhoz. |

Ha a felhasználó egy nem tekintetet használó alkalmazásról a tekinteti adatokhoz hozzáférő alkalmazásra tér át, megjelenik a figyelmeztetés. 

Minden más rendszerviselkedés hasonló lesz ahhoz, amikor az aktuális felhasználó nem figyel aktív szemkövetéssel. Az egy szándékból indítható indítási kézmozdulat például nem lesz engedélyezve. A kezdeti beállításhoz nem változik az Out-Of-Box-Experience.

Az olyan élmények esetében, amelyek szemretekintés-adatokat vagy pontos hologram-pozíciót igényelnek, azt javasoljuk, hogy a nem skálázott felhasználók a szemkövetési görbét futtassanak. Elérhető a szemkövetési parancssorból, vagy úgy, hogy elindítja a Gépház-alkalmazást a Start menüből, majd a **System > Egy** szem > és a Run eye > elemet választva.

#### <a name="deferred-calibration-prompt"></a>Késleltetett figyelmeztetés

Az Auto Eye Position (Automatikus szem pozíciója) beállítás esetén a Szemkövetési igénylés párbeszédpanelt a rendszer elhalasztja, amíg egy alkalmazás be nem kéri a Szem tekintete adatokat. Ez biztosítja, hogy a rendszer ne kér a felhasználótól olyankor, amikor az aktív alkalmazásnak nincs szüksége tekintetre. Ha az alkalmazásnak tekinteti adatokra van szüksége, és az aktuális felhasználó nincs beállítva, a felhasználó egy figyelmeztetést kap. Ezzel a viselkedéssel a megfelelő időpontban megjeleníthető a szemkövetési figyelmeztetés. Ez a módszer a következő okokból ajánlott:

1.  A Szemkövetési üzenet párbeszédpanelen a felhasználó részletes információkat talál arról, hogy miért van szükség a szemkövetésre.
2.  A felhasználó számára egy mód arra, hogy visszautasítsa a berakott tekintetét.

Ha a felhasználó úgy dönt, hogy elindítja a szemkövetési görbét, a vizsgálat befejezése után a fókusznak vissza kell térnie az eredeti alkalmazáshoz. 

### <a name="calibration-data-and-security"></a>Adatok és biztonság megszabadása

A rendszer helyben tárolja a helyi eszközön található adatokat, és nem társítja őket fiókinformációkhoz. Nincs nyilvántartás róla, hogy ki használta az eszközt engedély nélkül. Ez azt jelenti, hogy az új felhasználóknak az eszköz első használatakor be kell majd állítani a vizualizációkat, és azok a felhasználók, akik korábban nem, vagy ha sikertelen volt a hitelesítés, nem voltak sikeresek.

Az eszköz helyileg legfeljebb 50 profilt képes tárolni. A szám elérése után az eszköz automatikusan törli a legrégebbi nem használt profilt.

A személyes adatok mindig törölhetők az eszközről a **Gépház**  >  **Privacy**  >  **Eye tracker eszközről.**  

### <a name="disable-calibration"></a>Tiltás letiltása

A lekérdező kérést az alábbi lépésekkel is letilthatja:

1. Válassza **Gépház**  >  **rendszerkombráció**  >  **lehetőséget.**
1. Kapcsolja ki a When a new person uses this **HoloLens, automatically ask to run eye egy színre.**

   > [!IMPORTANT]
   > Ez a beállítás hátrányosan befolyásolhatja a hologram renderelési minőségét és kényelmi szolgáltatását.  Ha kikapcsolja ezt a beállítást, a szemkövetéstől függő funkciók (például a szöveg görgetése) többé nem működnek a modern alkalmazásokban.

> [!NOTE]
> A Gépház kapcsoló el lett távolítva Windows Holographic 20H2-es verziójától az Auto Eye Position Support (Automatikus szempozíció [támogatása) kezdettől](hololens-release-notes.md#auto-eye-position-support)fogva. A figyelmeztetés csak akkor jelenik meg automatikusan, ha egy nem skálázott felhasználó szemkövetést használó alkalmazást használ.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 szemkövetési technológia

Az eszköz a szemkövetési technológiájával javítja a megjelenítési minőséget, és gondoskodik arról, hogy minden hologram pontosan és kényelmesen megtekinthető legyen 3D-ben. Mivel a szemeket nevezetességként használja, az eszköz minden felhasználóhoz képes alkalmazkodni, és hangolni tudja a vizualizációit, miközben a headset használat közben némileg eltolt.  Minden módosítást a rendszer azonnal, manuális hangolás nélkül végez el.
> [!NOTE]
> Az IPD beállítása nem alkalmazható a Hololens 2-re, mivel a szempozíciókat a rendszer számítja ki.

HoloLens alkalmazások szemkövetéssel követik nyomon, hogy hol keres valós időben. Ez a fő képesség, amely segítségével a fejlesztők teljesen új kontextust, emberi megértést és interakciókat engedélyeznek a Holographic felhasználói élményben. A fejlesztőknek semmit sem kell tennie a funkció használatának használhatja.

## <a name="calibrating-your-hololens-1st-gen"></a>A HoloLens (1. generációs)

HoloLens (1. generációs) beállítja a hologramos megjelenítést az [interpupilláris](https://en.wikipedia.org/wiki/Interpupillary_distance) távolság (IPD) alapján. Ha az IPD nem pontos, a hologramok instabilnak vagy helytelen távolságnak jelennek meg. A vizualizációk minőségét úgy javíthatja, ha az eszközt az összetűnés távolságra (IPD) kell kalkulálni.

Amikor beállít egy HoloLens (1. generációs) eszközt, a rendszer felszólítja a vizualizációk Cortana bemutatja magát. Javasoljuk, hogy a beállítási fázisban teljes körűen végre tudja végrehajtani a javasolt eljárást. Ezt azonban kihagyhatja, ha megvárja, amíg Cortana a rendszer, majd a "Kihagyás" üzenetre vár.

A folyamat során a HoloLens megkéri, hogy igazítsa az ujjlenyomatát egy szemenkénti hat célsorozattal. HoloLens ezzel a folyamattal állíthatja be az IPD-címet a saját szemének megfelelően.

![AZ IPD-ujjlenyomat igazítása a második lépésben.](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Manuálisan indítsa el a folyamatot

Ha frissítenie kell a görbét, vagy ha egy új felhasználónak módosítania kell azt, bármikor manuálisan futtathatja a Tanácsadó alkalmazást. A Rendszer alapértelmezés szerint telepíti a Hibabeeső alkalmazást. A Hozzáférést a **Start** menüből vagy a Gépház is elérheti.

A Start **menüben** a Következő lépésekkel futtathat Egy ilyen alkalmazást:

1. A [Bloom kézmozdulattal](hololens1-basic-usage.md) nyissa meg a **Start menüt.**
1. Az összes alkalmazás megtekintéséhez válassza a **+** lehetőséget.
1. Válassza **a Felhozás** lehetőséget.

   ![Hozzáférés a kiszolgáló alkalmazáshoz a rendszerhéjból.](./images/calibration-shell.png)

   ![A megjelenítő alkalmazás az elindítása után élő kockaként jelenik meg.](./images/calibration-livecube-200px.png)

A Gépház alkalmazás futtatásához kövesse az alábbi lépéseket:

1. A [Bloom kézmozdulattal](hololens1-basic-usage.md) nyissa meg a **Start menüt.**
1. Ha **Gépház** nincs kitűzve a **Start** menübe, válassza a lehetőséget az összes **+** alkalmazás megtekintéséhez.
1. Válassza a **Beállítások** lehetőséget.
1. Válassza **a System**  >  **Utilities** Open És a  >  **Et.**

   ![A alkalmazás elindítása a beállítási alkalmazásból.](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Modern headsetek

Egyes modern headsetek lehetővé teszi az IPD-beállítás testreszabását. A headset IPD-címének beállítását a Gépház nyissa meg, és válassza a Mixed reality Headset display **(Mixed reality** headset-kijelző) lehetőséget, majd mozgassa a  >  csúszkavezérlőt. A módosításokat valós időben láthatja a headsetben. Ha ismeri az IPD-címét, például az optometrist felkereste, közvetlenül is megadhatja.

Ezt a beállítást a számítógépen is módosíthatja, ha a Mixed reality **Gépház**  >  **a**  >  **megjelenik.**

Ha a headset nem támogatja az IPD testreszabását, ez a beállítás le lesz tiltva.
