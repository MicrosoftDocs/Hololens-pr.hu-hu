---
title: HoloLens 2. lépés megjelenítési hibaelhárítása
description: A 2 HoloLens szembeni elvárások megjelenik. Útmutatás a megjelenítések konfigurálásához a legjobb képminőség érdekében.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: megjelenítés, kényelem, kényelmi, vizualizációk, minőség, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 548f484043f2b1cb62ce0e0cfb6450a956d412b3
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636928"
---
# <a name="hololens-2-display-troubleshooting"></a>HoloLens 2. lépés megjelenítési hibaelhárítása

## <a name="overview"></a>Áttekintés
A HoloLens 2. kijelző hullámvezetők és világos kivetítők kombinációját jeleníti meg. A felhasználók végigtekintnek a hullámos úton – a vizoron belüli objektívek –, amikor a headsetet viselik. A világos kivetítők a házon belül vannak, arow felett. HoloLens 2. napvilágítást használ a kijelző megjelenítéséhez.

## <a name="troubleshooting"></a>Hibaelhárítás

A következő lépésekkel biztosíthatja a megjelenítésben megjelenő hologramok legjobb vizuális minőségét:

* **Növelje a kijelző fényerejét.** Hologramok akkor jelenik meg a legjobban, ha a kijelző a legtisztább szinten van. Ha be van HoloLens, a fényerejét jelző gombok a vizor bal oldalán, a csúszka közelében vannak.
* **Közelebb hozza a szemhez a vizort.** A vizort a saját szemének legközelebbi pozícióhoz vassa le.
* **Tolja le a vizort.** Próbálja meg lejjebb mozgatni a fogat, ami azt eredményezi, hogy a vizor közelebb kerül az orrhoz.
* **[Szemkontrasztot kell futtatni.](hololens-calibration.md#calibrating-your-hololens-2)** A kijelző az összetűnés távolság (IPD) és a szem tekintete alapján optimalizálja a megjelenített képeket. Ha nem futtatja a szemredúsztásokat, a kép minősége rosszabb lehet. A szemredúsztás futtatásához Gépház   >  **a**  >  **Rendszerkontraszt**  >  **futtatás szemkontrasztot.**
* **Futtassa a megjelenítési színnek való megfelelőt.** A [Windows Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1) és újabb verzióiban  alternatív színprofilt is választhat a HoloLens 2-es verziójú megjelenítéshez. Ez segíthet a színek pontosabb megjelenítésében, különösen alacsonyabb megjelenítési fényerejénél. A színkorrektálás megjelenítése a Gépház **a** Rendszer és > **lapon található.**

    > [!NOTE]
    > Mivel ez a beállítás új színprofilt ment a megjelenítési belső vezérlőprogramba, ez egy eszközönkénti beállítás (és nem az egyes felhasználói fiókok egyedi beállítása).

### <a name="how-to-use-display-color-calibration"></a>A megjelenítési színek színezésének használata
1. Indítsa el **a Gépház** alkalmazást, és navigáljon a System > ( Biztonsági **rendszer) lapra.**
1. A **Színkorrektálás megjelenítése alatt** válassza a Megjelenítés **színkorrektálás gombját.**
1. Elindul a színekkel való megjelenítés élménye, és arra bátorítja, hogy győződjön meg arról, hogy a vizor a megfelelő helyen van.
1. Az utasítási párbeszédpanelek megnyitása után a kijelző automatikusan 30%-os fényerejére halványul.
    > [!TIP]
    > Ha nem látja a halvány jeleneteket a környezetében, manuálisan módosíthatja a HoloLens 2 fényerejét az eszköz bal oldalán található világítási gombokkal.
1. Válassza az 1–6. gombot, hogy azonnal kipróbálja az egyes színprofilokat, és keresse meg azt, amely a leginkább hasonlít a szemére (ez általában azt jelenti, hogy a profil, amely segít a jelenetnek a legsemlegesebbnek megjelenni, a szürke skálázási mintával és a hajszínszínekkel a vártnak megfelelően jelenik meg.)

    ![Színjelenet megjelenítése](images/color-cal-ui.png)
    
6. Ha elégedett a kiválasztott profillal, válassza a **Save & Exit (Kilépés)** gombot
1. Ha nem szeretne módosításokat tenni, válassza a Megszakítás & **Kilépés** gombot, és a módosítások visszaállnak

> [!TIP]
> Íme néhány hasznos tipp, amely a megjelenítési színek színbeállításának használata során hasznos lehet:
> - Bármikor újra futtathatja a megjelenítési színek színkorrektálását a Gépház, amikor csak szeretné
> - Ha az eszközön korábban már valaki használta a színprofilok beállítását, a legutóbbi módosítás dátuma és időpontja megjelenik a Gépház oldalon
> - Amikor újra futtatja a megjelenítési színek színkiszínezését, a korábban mentett színprofil ki lesz emelve, és a 0. profil nem jelenik meg (mivel a 0. profil a megjelenítés eredeti színprofilját jelöli)
> - Ha vissza szeretne állítani a megjelenítés eredeti színprofiljára, ezt a Gépház oldalon (lásd a színprofil alaphelyzetbe [állítását)](#how-to-reset-color-profile)

### <a name="how-to-reset-color-profile"></a>Színprofil alaphelyzetbe állítása

Ha nem elégedett a 2. HoloLens egyéni színprofillal, visszaállíthatja az eszköz eredeti színprofilját:
1. Indítsa el **a Gépház** alkalmazást, és navigáljon a System > ( Biztonsági **rendszer) lapra.**
1. A **Színkorrektálás megjelenítése alatt** válassza a Visszaállítás alapértelmezett **színprofilra gombot.**
1. Amikor megnyílik a párbeszédpanel, válassza az **Újraindítás** lehetőséget, ha készen áll a 2. HoloLens újraindítására, és alkalmazza a módosításokat.

### <a name="top-display-color-calibration-known-issues"></a>A legjobb megjelenítési színekkel kapcsolatos ismert problémák

- A Gépház az állapotsring, amely a színprofil legutóbbi módosulásáról ad vissza, elajánl, amíg újra be nem Gépház 
    - **Áthidaló** megoldás: Válasszon Gépház, majd válassza újra a Hibabeeső oldalt.
- Ha a HoloLens 2-es képernyő alvó üzemmódba kerül a kijelző színének színre váltás futtatása közben, a későbbiekben folytatódik a vegyes valóság kezdőlapja, és a kijelző fényerejének szintje továbbra is halványan jelenik meg.
- Előfordulhat, hogy néhányszor fel-/le kell nyomni a világítási gombokat az eszköz bal oldalán, hogy azok a várt módon működjön.
- A honosítás nem minden piac esetében teljes

## <a name="faq"></a>GYIK

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Milyen mintázatok jelennek meg időnként a kijelző alsó sarkaiban?

A 2. HoloLens egyes esetekben különböző mintázatok jelennek meg a kijelző bal alsó és jobb sarkában. Példák alább láthatók (animált GIF-ek). Ez a minta a 2- HoloLens normál működésének része, amely az optimális élmény érdekében berakja a kijelzőt.

![Kétfázisú minta](./images/DAT-Biphase-Fiducial.gif) ![GEO minta](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>Miért nem tudok pontos képet a 2. HoloLens képről?

A HoloLens 2. képernyő úgy van kialakítva, hogy emberi szem számára is megtekinthető legyen. Az eszköz aktív színkorrekciós rendszerrel rendelkezik, amely alkalmazkodik a felhasználó szeméhez. Az emberi szemhez képest a kamerák a környezeteket másképp látják, és az alábbiakban néhány olyan tényezőt láthatnak, amelyek hatással lehetnek a kamera által rögzített és a felhasználó által látható adatok közötti inkonzisztenciára.

* **Szem pozíciója.** A HoloLens 2. képernyő kifejezetten a felhasználó szem helyére lett tervezve. A HoloLens 2 szemkövetési technológiát alkalmaz a felhasználó szempozícióhoz való alkalmazkodáshoz. Egy néhány milliméterrel helytelenül áthelyezett kamera képszenzációhoz vezethet. A kamerával való pontos elhelyezés nehéz feladat, és pontosan meg kell egyeznie a színkorrekciót végző eszköz helyével és szemével.
* **Szemmozgás.** A kijelző alkalmazkodik a felhasználó szemének mozgásához a színek módosításához. A megjelenített adatok eltérhetnek attól függően, hogy a felhasználó a képernyő közepére, élére vagy sarkára néz-e. Egyetlen kép rögzítése a legjobb esetben is csak azt mutatja, hogy a kijelző milyen a szem tekintetének megfelelő tengelyen.
* **Távértekvő megtekintés.** A HoloLens 2 megjelenítés úgy van kialakítva, hogy mindkét szemével megtekinthető legyen. Az agy alkalmazkodik két képhez, és összeolvasztja őket. Az egyetlen megjelenítést megjelenítő képek figyelmen kívül hagyják a másik kijelzőről származó információkat.
* **Kamera kitettségi ideje.** A kamera kitettségi ideje a másodperc 1/120-adának pontos többszöröse kell legyen. A HoloLens képkocka-sebesség 120 Hz. A 2. HoloLens képrajzolása miatt egyetlen képkockát sem elég egyezni az emberi látványsal. Ugyanakkor, ha az eszköz egyáltalán – még a mikroszolgáltatásokban is – mozog, a rendszer újra kiveszi a képet a kijelzőről, hogy stabilizálja a hologramokat. A több képkockát úgy rögzítik, hogy közben HoloLens ne mozognak, általában laboratóriumi telepítés szükséges.
* **Kameraméret.** A pontos kép rögzítéséhez a kamera méretének legalább 3 mm-nek kell lennie. A kis méretű mobiltelefonos kamerák kisebb területről integrálják a világítást, mint az emberi szem. Az eszköz színkorrekciót alkalmaz a nagyobb mellök által megfigyelt mintákra. Kis méretű öklök esetén az egységességi minták a rendszer által alkalmazott színkorrekciók ellenére is élesebbek és láthatók maradnak.
* **Kamera-bejárati pupillák.** A kamerának legalább 3 mm-es méretűnek kell lennie a pontos kép rögzítéséhez. Ellenkező esetben a kamera olyan gyakori mintákat rögzít, amelyek nem láthatók a szem számára. A bejárati tanuló pozíciójának a kamera előtt kell lennie, és a szem enyhülési távolsága mellett kell lennie, hogy elkerülje a rögzített kép eltérését és egyéb variációit.
* **Kamera pozíciója.** A HoloLens 2 megjelenítés követelményeinek megfelelő kamerák nagyobbak, és nehéz a HoloLens 2-es megjelenítéshez elég közel tartani a kamerát a színkel javított kép megfigyelése érdekében. Ha a kamera nem a megfelelő helyen van, a színkorrekció negatívan befolyásolhatja a 2 HoloLens rögzítését.
* **Képkorrekció.** A tipikus digitális kamerák és okostelefon-kamerák hangredő görbét (TRC) alkalmaznak, amely növeli a kontrasztot és a színt, hogy a megfelelőbb eredményt nyújtson. Ha egy 2 HoloLens jelenik meg, ez a hanggörbék nem egységesek.

Mindezeken túl a specializált ipari kamerák továbbra is rögzítheti a 2. HoloLens reprezentatív képeket. Sajnos az okostelefonok, a fogyasztók és a professzionális kamerák nem rögzítik a 2. HoloLens képekkel egyező képeket.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Mit tesz a szemredőség a képminőség megjelenítéséhez?

A HoloLens a 2. képernyőn aktív szín jelenik meg, amely a felhasználó szemének pozíciója alapján javítja a képeket. [A](hololens-calibration.md) szemkontraszt két fontos bemenetet biztosít: (1) a felhasználó interpupilláris távolságát (IPD) és (2) az egyes szemeket jelölő irányt. A szemmozgás nélkül a rendszer alapértelmezés szerint névleges szempozíciót tart szemmozgás nélkül. Az aktív színkorrekció és a javítás nélkül közötti különbség a felhasználó fiziológiáján múlik. Azok a felhasználók például, akiknél az IPD-cím ugyanaz, mint a rendszer alapértelmezése, kevesebb színkorrekciós fejlesztést fognak látni. Míg a rendszer alapértelmezett IPD-címnél sokkal szűkebb vagy szélesebb IP-címmel használó felhasználók több változást fognak látni a megjelenített képen.

Vegye figyelembe, hogy a [Holographic 20H2 Windows](hololens-release-notes.md#windows-holographic-version-20h2) egy új szolgáltatása automatikusan észleli a szem [pozícióját.](hololens-calibration.md#auto-eye-position-support) 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>Mi a megjelenítési különbség a HoloLens (1. generációs) és a HoloLens között?

Az ügyfelek a legtöbb kérés közül azt tapasztalták, hogy HoloLens 1-es (1) értékkel növelték a nézetet, és (2) növelték a fényerejét. A technológiai fejlesztések lehetővé tették, hogy a Microsoft olyan hullámútút készítsen, amely megduplázta a nézőpont területét, és olyan fény kivetítőket készítsen, amelyek legfeljebb háromszor világosak. A hardver három, a megjelenítési képminőségre vonatkozó kereskedelmi viszony alapértékét állítja be: (1) a nézet mezője, (2) a fényerejét és (3) a szín egységességét. A folyamatos technológiai fejlődés minden területen lehetővé teszi a fejlesztést anélkül, hogy egy másik területet feláldoznak. E körülmények között a meglévő technológia beállítja az ilyen korlátozásokhoz elérhető korlátokat.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>Milyen fejlesztések fognak fejlődni, amelyek HoloLens 2 képminőséget?

Bár számos vizsgálat van folyamatban a képminőség javítása érdekében, a következő területek várhatók a soron következő frissítésekben:

* **Automatikus szempozíció.** Ez a funkció lehetővé teszi, hogy a háttérben lezajlnak a szemúti eljárások. Az aktív színkorrekció munkához a felhasználóknak többé nem kell szemredő színkorrekciót futtatni. Ehelyett csak működni fog.
* **Színjavítások fejlesztései.** Ez a frissítés a sötétebb színek (például sötétszürke) színértékeivel foglalkozik. Jelenleg a dimmer színek piros hangvételt választnak. Ez a probléma akkor is előfordul, ha a teljes kijelző halványan jelenik meg – a teljes kijelző piros színeket kap. Ez a probléma annak az eredménye, hogy a piros színcsatornában túl sok tevékenység volt ilyen sötét színű. Ezen a dimmer-színeken jellemezte a görbe görbéit, és dolgozunk azon, hogy felhasználói eljárásokat kínálunk. Az eredmény nagyobb színpontosság lesz a fényerejének spektrumában. Ez nem módosítja a fehér hátterek megjelenését teljes fényerejével. Továbbra is a sötét módú tervezési minták használatát javasoljuk az alkalmazásokban.
* **Olvasási mód.** Az alkalmazásfejlesztőknek lehetőség van a megjelenítési mező cseréire a jobb angular-felbontás érdekében. Az alkalmazásfejlesztők felülbírálhatják a leképezési mátrixot, így a tartalom a kijelző rajzolási felbontása szerint jelenik meg. Ez a funkció 30%-kal csökkenti a látómezőt, és ennek megfelelően növeli az angular-felbontást. Folyamatban van ennek a képességnek a bevezetése a [Mixed Reality Eszközkészletben.](https://github.com/Microsoft/MixedRealityToolkit-Unity) Ha elérhető, az olvasási mód bármely 2 HoloLens operációs rendszeren működik – nem függ az operációs rendszer frissítéstől.

Az operációs rendszer frissítéseit a rendszer automatikusan kézbesíti. A belső előzetes verziós programon keresztül a szoftverfejlesztés korai kiadását is tesztelheti.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Milyen útmutatás érhető el a fejlesztők számára a sötét mód tervezési alapelveinek alkalmazásával?

A fehér hátterek elkerülése érdekében a felhasználók a legjobb élményt tapasztalják. A sötét mód egy olyan tervezési elv, amelyet az alkalmazások fekete vagy sötét színű hátterek használatára használnak. A rendszerbeállítások alapértelmezett beállítása a sötét mód, és a **Rendszerszín** Gépház  >    >  **módosíthatók.**

Javasoljuk a fejlesztőknek, hogy kövessék a sötét mód tervezési útmutatót:

* [Fejlesztői tervezési irányelvek HoloLens megjelenítéshez](/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Ajánlott betűméretek](/windows/mixed-reality/typography#recommended-font-size)

Ha egy hologram fehér hátteret igényel, a hologram mérete ne legyen kisebb, mint a kijelző teljes látómezője. Ez a méret lehetővé teszi, hogy a felhasználók a hologramot a kijelző közepére helyezzenek.

### <a name="how-do-you-clean-a-hololens-2-display"></a>Hogyan lehet megtisztítani a HoloLens 2-es megjelenítést?

Mikrofiberos málnával törölje ki a vizort. A vizor tisztítására használjon 70%-os isopropyl-ét, hogy könnyedén megszendítsen egy fogat, majd törölje a vizort. Olvassa el a teljes útmutatót [a HoloLens 2. tisztítási GYIK dokumentumban.](hololens2-maintenance.md)
