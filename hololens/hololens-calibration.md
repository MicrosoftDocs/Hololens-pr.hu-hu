---
title: A vizualizáció minőségének és kényelmi javítására
description: Megtudhatja, hogyan lehet az összetűnés távolság (IPD) alapján a vizualizációk minőségének javítása érdekében HoloLens eszközökre.
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
keywords: élmény, kényelem, vizualizációk, minőség, ipd, HoloLens, Windows Mixed Reality, VR-headsetek
ms.openlocfilehash: b3d917c71ac7441aeaf8dcbc25748ee07b9fbfa3
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189205"
---
# <a name="improve-visual-quality-and-comfort"></a>A vizualizáció minőségének és kényelmi javítására

HoloLens 2. és HoloLens (1. generációs) is jobban működik, ha az egyedi szemének megfelelően vannak beállítva.

Bár mindkét eszköznek a legjobb hologramos megtekintési élményre kell beszabadnia, különböző technológiai technológiákat és technikákat alkalmaznak.  Ugorjon [a HoloLens 2-](#calibrating-your-hololens-2) vagy [HoloLens (1. generációs) beszennárba.](#calibrating-your-hololens-1st-gen)

## <a name="calibrating-your-hololens-2"></a>A 2. HoloLens meg

HoloLens 2. felhasználó szemkövetési technológiát használ a virtuális környezet jobb látási és interakciós élményéhez. A 2. HoloLens biztosítja, hogy pontosan nyomon tudja követni a tekintetét (és bárki másét, aki az eszközt használja). Segít a felhasználói kényelemben, a hologram-igazításban és a kézkövetésben is. A besziratás után a hologramok akkor is megfelelően jelennek meg, ha a vizor a fejében eltolást vált.

HoloLens 2. üzenet arra kéri a felhasználót, hogy a következő körülmények között állítsa be az eszközt:

- A felhasználó először használja az eszközt
- A felhasználó korábban nem döntött a lemondási folyamatról
- A hitelesítési folyamat nem sikerült, amikor a felhasználó utoljára használta az eszközt
- A felhasználó törölte a profilokat
- Az eszközt a rendszer kikapcsolja és visszaveszi, és a fenti körülmények bármelyike érvényes 


![Hangolási kérés a tekintethez való igazodáshoz.](./images/07-et-adjust-for-your-eyes.png)

A folyamat során célokat (gemeket) fog keresni. Nem gond, ha villog a tudat alatt, de a helyiség többi objektuma helyett a gemekkel kell próbálkozni.  A gemre összpontosítva HoloLens, hogy megismerje a holografikus világ renderelésének szempozícióját.

![A figyelmeztetés arra kéri a felhasználót, hogy tartsa a fejét, és kövesse a szemével a pontokat.](./images/07-et-hold-head-still.png)

![Egy gem-példával adhatja meg a parancssort.](./images/08-et-gems.png)

![Hangolási kérés.](./images/09-et-adjusting.png)

Ha a beszkennálás sikeres volt, megjelenik egy sikeres műveletről képernyő.  Ha nem, olvassa el a [meghibásodások diagnosztizálásának további tudnivalókat.](hololens2-display.md#troubleshooting)

![Sikeres beesés kérése.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Eszköz vagy munkamenet megosztásakor való hitelesítés

Több felhasználó is megoszthat egy HoloLens 2 eszközt anélkül, hogy minden személynek végig kellene mennie az eszköz beállításán. Amikor egy új felhasználó először helyezi a fejére az eszközt, a 2. HoloLens kéri a felhasználót, hogy állítsa be a vizualizációkat. Ha egy korábban már hitelesített vizualizációt használó felhasználó a fejére helyezi az eszközt, a kijelző zökkenőmentesen igazodik a minőséghez és a kényelmes megtekintéshez.  

### <a name="manually-starting-the-calibration-process"></a>Manuálisan el kell indulnia a hitelesítési folyamatnak

1. Az indítási kézmozdulattal nyissa meg a [**Start menü.**](hololens2-basic-usage.md#start-gesture)
1. Ha a Gépház alkalmazás nincs kitűzve a **Start menübe,** válassza a **Minden alkalmazás lehetőséget.**
1. Válassza **Gépház** lehetőséget, majd válassza a **System**  >  **Egyentús szemredúsztás**  >    >  **szemreszibráció lehetőséget.**

   ![A Gépház alkalmazást, amely a Szemfuttassa a szemkontraszt lehetőséget mutatja.](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Automatikus szempozíció támogatása

A 2 HoloLens szempozíciók lehetővé teszik a pontos hologram-pozíciót, a kényelmes megtekintést és a jobb megjelenítési minőséget. A szempozíciók kiszámítása belsőleg, a szemkövetési számítás részeként történt. Ehhez azonban minden felhasználónak szemkövetést kell követnie, még akkor is, ha a felhasználói élményhez nincs szükség szemre való betekintő adatokra.

**Az automatikus szempozíció (Auto Eye Position, AEP)** lehetővé teszi, hogy ezek a forgatókönyvek interakciómentes módon számítsák ki a felhasználó szempozícióit. Az automatikus szempozíció a felhasználó eszközre való indításakor automatikusan elkezd dolgozni a háttérben. Ha a felhasználó nem rendelkezik korábbi szemkövetési követéssel, az Auto Eye Position 20–30 másodperces feldolgozási idő után elkezdi a felhasználó szempozícióját a kijelző rendszer számára. A felhasználói adatok nem maradnak meg az eszközön, és ez a folyamat meg lesz ismételve, ha a felhasználó kikapcsolja és visszateszi az eszközt, vagy ha az eszköz újraindul vagy felébreszti az alvó állapotból.

Az Auto Eye Position funkcióval a rendszer viselkedése megváltozik, ha egy nem skálázott felhasználó az eszközt helyezi el. Ebben a kontextusban a nem skálázott felhasználó olyanra utal, aki még nem ment keresztül az eszközön korábban a szemkövetési folyamaton.

| Aktív alkalmazás | Korábbi viselkedés | Viselkedés a holografikus Windows 20H2-es verziójának frissítésével |
|:-------------------|:-----------------|:-----------------------------------|
| Nem tekintetre képes alkalmazás vagy Holographic Shell |Megjelenik a szemkövetési párbeszédpanel. | Nem jelenik meg kérdés. |
| Tekintet-kompatibilis alkalmazás | Megjelenik a szemkövetési párbeszédpanel. | A szemkövetési üzenet csak akkor jelenik meg, ha az alkalmazás hozzáfér a szemstreamhez. |

Ha a felhasználó nem tekintetet használó alkalmazásról a tekinteti adatokhoz hozzáférő alkalmazásra tér át, megjelenik a figyelmeztetés. 

Minden más rendszerviselkedés hasonló lesz ahhoz, amikor az aktuális felhasználó nem használ aktív szemkövetést. Az Egy kézből indítható kézmozdulat például nem lesz engedélyezve. A kezdeti beállításhoz a kezdőélmény nem változik.

A szemre vonatkozó tekinteti adatokat vagy pontos hologrampozíciót igénylő élmények esetén javasoljuk, hogy a nem skálázott felhasználók a szemkövetési követést futtassanak. Elérhető a szemkövetési kérdezésből, vagy úgy, hogy a start menüből elindítja a Gépház alkalmazást, majd a **System > > Eye > És** a Run eye (Szemszirasztás) lehetőséget választva.

#### <a name="deferred-calibration-prompt"></a>Késleltetett figyelmeztetés

Az Auto Eye Position (Automatikus szem pozíciója) funkcióval a Szemkövetési igénylés párbeszédablakot a rendszer késlelteti, amíg egy alkalmazás be nem kéri a Szem tekintete adatait. Ez biztosítja, hogy a rendszer ne kér a felhasználótól figyelmeztetést, ha az aktív alkalmazáshoz nincs szükség tekintetre. Ha az alkalmazásnak tekinteti adatokra van szüksége, és az aktuális felhasználó nincs beállítva, a felhasználónak figyelmeztetést kell adnia. Ez a viselkedés felhasználható a szemkövetési megjelenítő parancssor megjelenítésére a megfelelő időpontban. Ez a módszer a következő okokból ajánlott:

1.  A Szemkövetési üzenet párbeszédpanelen a felhasználó részletes információkat talál arról, hogy miért van szükség a szemkövetésre.
2.  A felhasználó számára egy mód arra, hogy visszautasítsa a beoklott tekintetét.

Ha a felhasználó úgy dönt, hogy elindítja a szemkövetési görbét, a vizsgálat befejezése után a fókusznak vissza kell térnie az eredeti alkalmazáshoz. 

### <a name="calibration-data-and-security"></a>Biztonsági és adatkezelési adatok

A kockázatra vonatkozó információkat a rendszer helyben tárolja az eszközön, és nincs társítva fiókinformációkhoz. Nincs nyilvántartás róla, hogy ki használta az eszközt anélkül, hogy az be lett volna küldve. Ez azt jelenti, hogy az új felhasználóknak az eszköz első használatakor be kell állítani a vizualizációkat, és azok a felhasználók, akik korábban nem voltak megfelelően beállítva, vagy sikertelen volt a figyelmeztetésük.

Az eszköz akár 50 profilt tárolhat helyileg. A szám elérése után az eszköz automatikusan törli a legrégebbi nem használt profilt.

A személyes adatok mindig törölhetők az eszközről a **Gépház**  >  **Privacy**  >  **Eye tracker eszközben.**  

### <a name="disable-calibration"></a>Tiltsa le a tiltásokat

A figyelmeztetést az alábbi lépésekkel is letilthatja:

1. Válassza **Gépház**  >  **rendszerkomikálás**  >  **lehetőséget.**
1. Kapcsolja ki a When a new person uses this **HoloLens, automatically ask to run eye egybráció.**

   > [!IMPORTANT]
   > Ez a beállítás hátrányosan befolyásolhatja a hologram renderelési minőségét és kényelmi szolgáltatását.  Ha kikapcsolja ezt a beállítást, a szemkövetéstől függő funkciók (például a szöveg görgetése) többé nem működnek a magával ragadó alkalmazásokban.

> [!NOTE]
> A Gépház kapcsoló el lett távolítva Windows Holographic 20H2-es verziójától az Auto Eye Position Support (Automatikus szempozíció támogatása) [kezdettől fogva.](hololens-release-notes.md#auto-eye-position-support) A figyelmeztetés csak akkor jelenik meg automatikusan, ha egy nem minősített felhasználó szemkövetésre képes alkalmazást használ.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 szemkövetési technológia

Az eszköz szemkövetési technológiájával javítja a megjelenítési minőséget, és gondoskodik arról, hogy minden hologram pontosan és kényelmesen látható legyen 3D-ben. Mivel a szemüket nevezetességként használja, az eszköz minden felhasználóhoz képes alkalmazkodni, és hangolni tudja a vizualizációit, ahogy a headset kis mértékben eltolt a használat során.  Minden módosítást a rendszer azonnal, manuális hangolás nélkül végez el.
> [!NOTE]
> Az IPD beállítása nem alkalmazható a Hololens 2-re, mivel a szem pozícióit a rendszer számítja ki.

HoloLens alkalmazások szemkövetéssel követik nyomon, hogy hol keres valós időben. Ez a fejlesztők által használható fő képesség, amely lehetővé teszi a kontextus, az emberi megértés és az interakciók egy teljesen új szintjét a Holographic felhasználói élményben. A fejlesztőknek semmit sem kell tenni ahhoz, hogy ezt a képességet használják.

## <a name="calibrating-your-hololens-1st-gen"></a>A HoloLens (1. generációs)

HoloLens (1. generációs) beállítja a hologramos megjelenítést az [összetupláris távolság](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD) alapján. Ha az IPD nem pontos, a hologramok instabilnak vagy helytelen távolságnak is megjelenhetnek. A vizualizációk minőségét úgy javíthatja, ha az eszközt az összetűnés távolságra (IPD) kell felbefésülni.

Amikor beállít egy HoloLens (1. generációs) eszközt, a rendszer felszólítja a vizualizációk Cortana bemutatja magát. Javasoljuk, hogy a beállítási fázisban teljes körűen el kell készítenie a javasolt eljárást. Ezt azonban kihagyhatja, ha megvárja, amíg Cortana a rendszer, majd a "Kihagyás" üzenetre vár.

A folyamat során a HoloLens megkéri, hogy igazítsa az ujjlenyomatát egy szemenkénti hat célsorozattal. HoloLens ezzel a folyamattal állíthatja be az IPD-címet a saját szemének megfelelően.

![AZ IPD-ujjlenyomat igazítása a második lépésben.](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Manuálisan indítsa el a folyamatot

Ha frissítenie kell a görbét, vagy ha egy új felhasználónak módosítania kell azt, bármikor manuálisan futtathatja a Tanácsadó alkalmazást. A Rendszer alapértelmezés szerint telepíti a Hibabeeső alkalmazást. A Hozzáférést a **Start** menüből vagy a Gépház használhatja.

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

Ezt a beállítást a számítógépen is módosíthatja a Mixed reality headset Gépház  >    >  **kiválasztásával.**

Ha a headset nem támogatja az IPD testreszabását, ez a beállítás le lesz tiltva.
