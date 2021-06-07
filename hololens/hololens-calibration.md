---
title: A vizualizáció minőségének és kényelmi javítására
description: Ismerje meg, hogyan lehet a HoloLens-eszközökön található vizualizációk minőségének javítása érdekében beárosíthatja az összetupláris távolságot (IPD).
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
ms.openlocfilehash: e975e2ccd978d4ec6b5331af0ae566af116711c5
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379523"
---
# <a name="improve-visual-quality-and-comfort"></a>A vizualizáció minőségének és kényelmi javítására

A HoloLens 2 és a HoloLens (1. generációs) egyaránt jobban működik, ha az Ön egyedi szemének megfelelően vannak beállítva.

Bár mindkét eszköznek a legjobb hologramos megtekintési élményhez kell a hitelesítést használnia, különböző hitelesítési technológiákat és technikákat alkalmaznak.  Ugrás a [HoloLens 2-re vagy](#calibrating-your-hololens-2) [a HoloLens (1. generációs) számára.](#calibrating-your-hololens-1st-gen)

## <a name="calibrating-your-hololens-2"></a>A HoloLens 2-

A HoloLens 2 szemkövetési technológiával javítja a virtuális környezettel való interakciót és a látást. A HoloLens 2 kalkulátora biztosítja, hogy pontosan nyomon tudja követni a tekintetét (és bárki másét, aki az eszközt használja). Segít a felhasználói kényelemben, a hologram-igazításban és a kézkövetésben is. A besziratás után a hologramok akkor is megfelelően jelennek meg, ha a vizor a fejében eltolást vált.

A HoloLens 2 a következő körülmények között kéri a felhasználót az eszköz bekalkennelésére:

- A felhasználó először használja az eszközt
- A felhasználó korábban nem döntött a lemondási folyamatról
- A hitelesítési folyamat nem sikerült, amikor a felhasználó utoljára használta az eszközt
- A felhasználó törölte a profilokat
- Az eszközt a rendszer kikapcsolja, és visszaveszi, és a fenti körülmények bármelyike érvényes 


![Hangolási kérés a tekintethez való igazodáshoz.](./images/07-et-adjust-for-your-eyes.png)

A folyamat során célokat (gemeket) fogunk keresni. Nem gond, ha villog a tudat alatt, de a helyiségben lévő többi objektum helyett a gemre összpontosít.  A gemre összpontosítva a HoloLens megismeri a holografikus világ renderelésének szempozícióját.

![A figyelmeztetés arra kéri a felhasználót, hogy tartsa a fejét, és kövesse a pontokat a szemével.](./images/07-et-hold-head-still.png)

![Egy gem-példával adhatja meg a parancssort.](./images/08-et-gems.png)

![Hangolási kérés.](./images/09-et-adjusting.png)

Ha a beszkennálás sikeres volt, megjelenik egy sikeres műveletről képernyő.  Ha nem, olvassa el a [meghibásodások diagnosztizálásának további tudnivalókat.](#troubleshooting-hololens-2-calibration)

![Sikeres beesés kérése.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Eszköz vagy munkamenet megosztásakor való hitelesítés

Több felhasználó is megoszthat egy HoloLens 2-eszközt anélkül, hogy mindenki végig kellene mennie az eszköz beállításán. Amikor egy új felhasználó először helyezi a fejére az eszközt, a HoloLens 2 automatikusan felszólítja a felhasználót a vizualizációk beokakorlára. Ha egy korábban már hitelesített vizualizációt használó felhasználó a fejére helyezi az eszközt, a kijelző zökkenőmentesen igazodik a minőséghez és a kényelmes megtekintéshez.  

### <a name="manually-starting-the-calibration-process"></a>Manuálisan el kell indulnia a hitelesítési folyamatnak

1. A start kézmozdulattal nyissa meg a [ **Start menüt.**](hololens2-basic-usage.md#start-gesture)
1. Ha a Beállítások alkalmazás nincs kitűzve a **Start menübe,** válassza a **Minden alkalmazás lehetőséget.**
1. Válassza **a Beállítások,** majd a   >  **Rendszer-szemredúsztás**  >  **Szemszirebráció**  >  **jelölőnégyzetet.**

   ![A Settings (Beállítások) alkalmazás, amely a Run eye (Szem futtatása) beállítást mutatja](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Automatikus szempozíció támogatása

A HoloLens 2 szempozíciói lehetővé teszik a pontos hologram-pozíciót, a kényelmes megtekintést és a jobb megjelenítési minőséget. A szempozíciók kiszámítása belsőleg, a szemkövetési számítás részeként történt. Ehhez azonban minden felhasználónak szemkövetést kell követnie, még akkor is, ha a felhasználói élményhez nincs szükség szemre való betekintő adatokra.

**Az automatikus szempozíció (Auto Eye Position, AEP)** lehetővé teszi, hogy ezek a forgatókönyvek interakciómentes módon számítsák ki a felhasználó szempozícióit. Az automatikus szempozíció a felhasználó eszközre való indításakor automatikusan elkezd dolgozni a háttérben. Ha a felhasználó nem rendelkezik korábbi szemkövetési követéssel, az Auto Eye Position 20–30 másodperces feldolgozási idő után elkezdi a felhasználó szempozícióját a kijelző rendszer számára. A felhasználói adatok nem maradnak meg az eszközön, és ez a folyamat meg lesz ismételve, ha a felhasználó kikapcsolja és visszateszi az eszközt, vagy ha az eszköz újraindul vagy felébreszti az alvó állapotból.

Az Auto Eye Position funkcióval a rendszer viselkedése megváltozik, ha egy nem skálázott felhasználó helyezi el az eszközt. Ebben a kontextusban a nem skálázott felhasználó olyanra utal, aki még nem ment keresztül az eszközön korábban a szemkövetési folyamaton.

| Aktív alkalmazás | Korábbi viselkedés | Viselkedés a Windows Holographic 20H2 Update-től |
|:-------------------|:-----------------|:-----------------------------------|
| Nem tekintetre képes alkalmazás vagy Holographic Shell |Megjelenik a szemkövetési párbeszédpanel. | Nem jelenik meg kérdés. |
| Tekintet-kompatibilis alkalmazás | Megjelenik a szemkövetési párbeszédpanel. | A szemkövetési üzenet csak akkor jelenik meg, ha az alkalmazás hozzáfér a szemstreamhez. |

Ha a felhasználó nem tekintetet használó alkalmazásról a tekinteti adatokhoz hozzáférő alkalmazásra tér át, megjelenik a figyelmeztetés. 

Minden más rendszerviselkedés hasonló lesz ahhoz, amikor az aktuális felhasználó nem használ aktív szemkövetést. Az egy kézzel használható Indítás kézmozdulat például nem lesz engedélyezve. A kezdeti beállításhoz a kezdőélmény nem változik.

A szemre vonatkozó tekinteti adatokat vagy pontos hologrampozíciót igénylő élmények esetén javasoljuk, hogy a nem skálázott felhasználók a szemkövetési követést futtassanak. Elérhető a szemkövetési kérdezésből vagy a Start menüből a Beállítások alkalmazás elindításával, majd a **System > > Eye > Való** alkalmazás kiválasztásával.

#### <a name="deferred-calibration-prompt"></a>Késleltetett figyelmeztetés

Az Auto Eye Position (Automatikus szem pozíciója) beállítás esetén a szemkövetési figyelmeztetési párbeszédpanelt a rendszer késlelteti, amíg egy alkalmazás be nem kéri a Szem tekintete adatait. Ez biztosítja, hogy a rendszer ne kér a felhasználótól figyelmeztetést, ha az aktív alkalmazáshoz nincs szükség tekintetre. Ha az alkalmazásnak tekinteti adatokra van szüksége, és az aktuális felhasználó nincs beállítva, a felhasználó egy figyelmeztetést kap. Ez a viselkedés felhasználható a szemkövetési megjelenítő parancssor megjelenítésére a megfelelő időpontban. Ez a módszer a következő okokból ajánlott:

1.  A Szemkövetési üzenet párbeszédpanelen a felhasználó részletes információkat talál arról, hogy miért van szükség a szemkövetésre.
2.  A felhasználó számára egy mód arra, hogy visszautasítsa a beoklott tekintetét.

Ha a felhasználó úgy dönt, hogy elindítja a szemkövetési görbét, a fókusznak vissza kell térnie az eredeti alkalmazáshoz a vizsgálat befejezése után. 

### <a name="troubleshooting-hololens-2-calibration"></a>HoloLens 2-hibák elhárítása

A legtöbb ember számára működnie kell, de vannak olyan esetek, amikor a beszibrálás sikertelen.
  
Néhány lehetséges ok a meghibásodásra:

- Elvonja a figyelmet, és nem követi a célokat
- Nem megfelelően el van állítva a trágár vagy karcolt eszköz vagy az eszköz vizora
- Trágár vagy karcolt szemüveg
- Bizonyos típusú kapcsolattartási objektívek és szemüveg (színes kapcsolattartó objektívek, néhány toric contact lenses, IR-blokkoló szemüveg, néhány magas szemüveg, napszemüveg vagy hasonló)
- Jobban kiejtve és perjeles mellékekkel
- Haj vagy vastag szemüveg, ha nem látják a tekintetét az eszközön
- Bizonyos szemfizikai, szemkörülmények vagy szemműveletek, például keskeny szem, hosszú szempillák, amblyadás, nystagmus, a LASIK vagy más szemműveletek bizonyos esetekben

Sikertelen kísérlet esetén próbálkozzon a következővel:

- Az eszköz vizorának tisztítása
- Szemüveg tisztítása
- Az eszköz vizorának a lehető legnagyobb közelében való eltolás
- Objektumok mozgatása a vizorban az útból (például haj)
- Világítás bekapcsolása a helyiségben, vagy a közvetlen világításból való eltálás

Ha minden útmutatót követte, és a tiltása továbbra sem sikerül, letilthatja a figyelmeztetést a Beállításokban. Visszajelzést is küldhet a következő [Visszajelzési központ.](hololens-feedback.md)

A képszínekkel vagy a fényerejével kapcsolatos [hibaelhárítással kapcsolatos információkat is itt láthatja.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Az IPD beállítása nem alkalmazható a HoloLens 2-re, mivel a szempozíciókat a rendszer számítja ki. 

### <a name="calibration-data-and-security"></a>Biztonsági és adatkezelési adatok

A kockázatra vonatkozó információkat a rendszer helyben tárolja az eszközön, és nincs társítva fiókinformációkhoz. Nincs nyilvántartás róla, hogy ki használta az eszközt anélkül, hogy az be lett volna küldve. Ez azt jelenti, hogy az új felhasználóknak az eszköz első használatakor be kell állítani a vizualizációkat, és azok a felhasználók, akik korábban nem voltak megfelelően beállítva, vagy sikertelen volt a figyelmeztetésük.

Az eszköz akár 50 profilt tárolhat helyileg. A szám elérése után az eszköz automatikusan törli a legrégebbi nem használt profilt.

A személyes adatok mindig törölhetők az eszközről a Settings Privacy Eye tracker **(Beállítások**  >  **adatvédelmi**  >  **szem követője) lapon.**  

### <a name="disable-calibration"></a>Tiltsa le a beszk

A figyelmeztetést az alábbi lépésekkel is letilthatja:

1. Válassza **a Beállítások**  >  **Rendszerkombráció**  >  **lehetőséget.**
1. Kapcsolja ki **a When a new person uses this HoloLens (Ha egy új személy használja ezt a HoloLenst) kapcsolja ki, automatikusan kérje a szemszétebrálás futtatását.**

> [!IMPORTANT]
> Ez a beállítás hátrányosan befolyásolhatja a hologram renderelési minőségét és kényelmi szolgáltatását.  Ha kikapcsolja ezt a beállítást, a szemkövetéstől függő funkciók (például a szöveg görgetése) többé nem működnek a magával ragadó alkalmazásokban.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 szemkövetési technológia

Az eszköz szemkövetési technológiájával javítja a megjelenítési minőséget, és gondoskodik arról, hogy minden hologram pontosan és kényelmesen látható legyen 3D-ben. Mivel a szemüket nevezetességként használja, az eszköz minden felhasználóhoz képes alkalmazkodni, és hangolni tudja a vizualizációit, ahogy a headset kis mértékben eltolt a használat során.  Minden módosítást a rendszer azonnal, manuális hangolás nélkül végez el.
> [!NOTE]
> Az IPD beállítása nem alkalmazható a Hololens 2-re, mivel a szempozíciókat a rendszer számítja ki.

A HoloLens-alkalmazások szemkövetéssel követik nyomon, hogy hol keres valós időben. Ez a fejlesztők által használható fő képesség, amely lehetővé teszi a kontextus, az emberi megértés és az interakciók egy teljesen új szintjét a Holographic felhasználói élményben. A fejlesztőknek semmit sem kell tenni ahhoz, hogy ezt a képességet használják.

## <a name="calibrating-your-hololens-1st-gen"></a>A HoloLens (1. generációs)

A HoloLens (1. generációs) a hologramos megjelenítést az [összecsuplott](https://en.wikipedia.org/wiki/Interpupillary_distance) távolság (IPD) alapján állítja be. Ha az IPD nem pontos, a hologramok instabilnak vagy helytelen távolságnak is megjelenhetnek. A vizualizációk minőségét úgy javíthatja, ha az eszközt az összetűnés távolságra (IPD) kell felbefésülni.

Amikor beállít egy HoloLens- (1. generációs) eszközt, a rendszer arra kéri, hogy állítsa be a vizualizációkat, miután Cortana bevezette magát. Javasoljuk, hogy a beállítási fázisban teljes körűen el kell készítenie a javasolt eljárást. Ezt azonban kihagyhatja, ha megvárja, amíg Cortana fel nem kéri, majd ki nem mondja a "Skip" (Kihagyás) parancsot.

A hitelesítési folyamat során HoloLens megkéri, hogy igazítsa az ujjlenyomatát egy szemenkénti hat célsorozattal. HoloLens ezzel a folyamattal adja meg helyesen az IPD-t a szemének.

![AZ IPD-ujjlenyomat igazítása képernyő a második lépésben](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Manuálisan indítsa el a hitelesítési folyamatot

Ha frissítenie kell a kijelzőt, vagy ha egy új felhasználónak módosítania kell azt, bármikor manuálisan futtathatja a Felhasználóbarát alkalmazást. A Rendszer alapértelmezés szerint telepíti a Tanúsítvány alkalmazást. A Hozzáférést a Start menüből vagy a **Beállítások** alkalmazásból lehet elérni.

A Start **menü futtatásához** kövesse az alábbi lépéseket:

1. A [Bloom-kézmozdulattal](hololens1-basic-usage.md) nyissa meg a **Start menüt.**
1. Az összes alkalmazás megtekintéséhez válassza a **+** lehetőséget.
1. Válassza **a Visszatendálás** lehetőséget.

![Hozzáférés a alkalmazáshoz a rendszerhéjból](./images/calibration-shell.png)

![A indítóalkalmazás élő kockaként jelenik meg az elindítása után](./images/calibration-livecube-200px.png)

A Settings alkalmazás a Következő lépésekkel futtatható a Saját alkalmazás futtatásához:

1. A [Bloom-kézmozdulattal](hololens1-basic-usage.md) nyissa meg a **Start menüt.**
1. Ha **a Beállítások** nincs kitűzve a Start **menübe,** válassza a **+** lehetőséget az összes alkalmazás megtekintéséhez.
1. Válassza a **Beállítások** lehetőséget.
1. Válassza a **System**  >  **Utilities**  >  **OpenUtilities Open És a et.**

![A alkalmazás elindítása a beállítási alkalmazásból](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Modern headsetek

Egyes modern headsetek lehetővé teszi az IPD-beállítás testreszabását. A headset IPD-címének módosításához nyissa meg a Settings alkalmazást, válassza a Mixed reality Headset display **(Vegyes valóság** headset-kijelző) lehetőséget, majd mozgassa  >  a csúszkavezérlőt. A módosításokat valós időben láthatja a headsetben. Ha ismeri az IPD-címét, például az optometrist felkeresve közvetlenül is megadhatja.

Ezt a beállítást a számítógépen is módosíthatja a **Beállítások**  >  **Vegyes valóság**  >  **Headset kijelző kiválasztásával.**

Ha a headset nem támogatja az IPD testreszabását, ez a beállítás le lesz tiltva.
