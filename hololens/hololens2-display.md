---
title: HoloLens 2. lépés megjelenítési hibaelhárítása
description: A 2 HoloLens elvárásai megjelenik. Útmutatás a megjelenítések konfigurálásához a legjobb képminőség érdekében.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: megjelenítés, színezés, kényelem, vizualizációk, minőség, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 38bab16d2d0d4ace5879f00c133d66b9974e4b2a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036133"
---
# <a name="hololens-2-display-troubleshooting"></a>HoloLens 2. lépés megjelenítési hibaelhárítása

## <a name="overview"></a>Áttekintés
A HoloLens 2-es megjelenítés hullámvezetők és világos kivetítők kombinációját jeleníti meg. A felhasználók a vizoron belüli objektíveket is végigküldik a hullámos úton, amikor a headsetet viselik. A fényküldők a házon belül vannak, arow(ház) felett. HoloLens 2 napvilágítást használ a kijelző kijelzéseként.

## <a name="troubleshooting"></a>Hibaelhárítás

A következő lépésekkel biztosíthatja a megjelenítésekben megjelenő hologramok legjobb vizuális minőségét:

* **Növelje a kijelző fényerejét.** Hologramok akkor jelenik meg a legjobban, ha a kijelző a legtisztább szinten jelenik meg. Ha be van HoloLens, a kijelzőgombok a vizor bal oldalán, a halom közelében vannak.
* **A vizort közelebb kell vinnie a szemhez.** A vizort a saját szemével legközelebbi pozícióba ássa le.
* **A vizor lefelé tolódása.** Próbálja meg lefelé mozgatni a fogat, ami azt eredményezi, hogy a vizor közelebb kerül az orrhoz.
* **[Szemreszeknáció.](hololens-calibration.md#calibrating-your-hololens-2)** A kijelző a képoptimalikus képoptimalikus megjelenítéshez használja az összetupláris távolságot (IPD) és a tekintetet. Ha nem futtat szemreszektálásokat, a kép minősége rosszabb lehet. A szemredúsztás futtatásához Gépház   >  **a System**  >  **Egyedek**  >  **futtatására.**
* **Futtassa a megjelenítési színkorrektálást.** A [Windows Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1) és újabb verzióiban  alternatív színprofilt is választhat a HoloLens 2-es verziójához. Ez segíthet a színek pontosabb megjelenítésében, különösen alacsonyabb megjelenítési fényerejénél. A színkorrektálás megjelenítése a Gépház **a** Rendszer és > **lapon** található.

    > [!NOTE]
    > Mivel ez a beállítás egy új színprofilt ment a megjelenítési belső vezérlőprogramba, ez egy eszközönkénti beállítás (és nem egyedi az egyes felhasználói fiókok számára).

### <a name="how-to-use-display-color-calibration"></a>A kijelző színkorrektálásának használata
1. Indítsa el **a Gépház** alkalmazást, és **navigáljon a System > (Rendszer- és >) lapra.**
1. A **Színkorrektálás megjelenítése alatt** válassza a Megjelenítés **színkorrektálásának futtatása** gombot.
1. Elindul a színekkel való megjelenítés élménye, és arra bátorítja, hogy a vizor a megfelelő helyen legyen.
1. Az utasítási párbeszédpanelek megnyitása után a kijelző automatikusan 30%-os fényerejére halványul.
    > [!TIP]
    > Ha nem látja a halvány jeleneteket a környezetében, manuálisan módosíthatja a HoloLens 2 fényerejét az eszköz bal oldalán található fényerejét jelző gombokkal.
1. Válassza az 1–6. gombot, hogy azonnal kipróbálja az egyes színprofilokat, és keresse meg azt, amely a leginkább hasonlít a szemére (ez általában azt jelenti, hogy a jelenetnek leginkább megfelelő profil jelenik meg a legsemlegesebbnek, a szürkeárnyalatos mintázattal és a vékony tonének pedig a várt módon kell megjelennie.)

    ![Színjelenet megjelenítése.](images/color-cal-ui.png)
    
6. Ha elégedett a kiválasztott profillal, válassza a **Mentés & Kilépés gombot**
1. Ha nem szeretne módosításokat tenni, válassza a Mégse & **Kilépés** gombot, és a módosítások visszaállnak

> [!TIP]
> A megjelenítési színbeállítás használata során az alábbi tippeket kell szem előtt tartania:
> - A megjelenítési színek színkorrektálását bármikor újra Gépház, amikor csak szeretné
> - Ha az eszközön bárki korábban már használta a színprofilok beállítását, a legutóbbi módosítás dátuma/időpontja megjelenik a Gépház oldalon
> - A megjelenítési színek színkorrektálásának újrafuttatásakor a korábban mentett színprofil ki lesz emelve, és a 0. profil nem jelenik meg (mivel a 0. profil a megjelenítés eredeti színprofilját jelöli)
> - Ha vissza szeretne állítani a megjelenítés eredeti színprofiljára, ezt a Gépház oldalon (lásd: a színprofil [alaphelyzetbe állítása)](#how-to-reset-color-profile)

### <a name="how-to-reset-color-profile"></a>Színprofil alaphelyzetbe állítása

Ha nem elégedett a 2. HoloLens egyéni színprofillal, visszaállíthatja az eszköz eredeti színprofilját:
1. Indítsa el **a Gépház** alkalmazást, és **navigáljon a System > (Rendszer- és >) lapra.**
1. A **Színkorrektálás megjelenítése alatt** válassza a Visszaállítás alapértelmezett **színprofilra gombot.**
1. Amikor megnyílik a  párbeszédpanel, válassza az Újraindítás lehetőséget, ha készen áll a 2. HoloLens újraindítására, és alkalmazza a módosításokat.

### <a name="top-display-color-calibration-known-issues"></a>A legjobb megjelenítési színekkel kapcsolatos ismert problémák

- A Gépház lapon az állapotsring, amely a színprofil legutóbbi módosulásának időpontját jelzi, elajánl, amíg újra be nem Gépház 
    - **Megkerülő** megoldás: Válasszon ki egy Gépház lapot, majd válassza újra a Hibatanúslat oldalt.
- Ha a HoloLens 2-es kijelző alvó üzemmódba kerül a kijelző színének színkorrektálásának futtatása közben, az később vissza fog menni a vegyes valóságú otthonra, és a kijelző fényerejének szintje továbbra is halványan jelenik meg.
- Előfordulhat, hogy néhányszor le kell nyomni a kijelzőgombokat az eszköz bal oldalán, hogy azok a várt módon működjön.
- A honosítás nem minden piac esetében teljes

## <a name="faq"></a>GYIK

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Milyen mintázatok jelennek meg időnként a kijelző alsó sarkaiban?

Esetenként a HoloLens 2. pont különböző mintákat jelenít meg a kijelző bal alsó és jobb sarkában. Példák alább láthatók (animált GIF-ek). Ez a minta a 2-es HoloLens normál működésének része, amely az optimális élmény érdekében bejelönli a kijelzőt.

![Kétfázisú minta.](./images/DAT-Biphase-Fiducial.gif) ![GEO minta](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>Miért nem tudok pontos képet a 2 HoloLens képről?

A HoloLens 2. megjelenítés emberi szem számára lett kialakítva. Az eszköz aktív színkorrekciós rendszerrel rendelkezik, amely alkalmazkodik a felhasználó szeméhez. Az emberi szemhez képest a kamerák másképp látják a környezeteket, és az alábbiakban néhány olyan tényezőt láthatunk, amelyek hatással lehetnek a kamera és a felhasználó által látható adatok közötti inkonzisztenciára.

* **Szem pozíciója.** A HoloLens 2. kijelző kifejezetten a felhasználó szem helyére lett tervezve. A HoloLens 2 szemkövetési technológiát alkalmaz a felhasználó szempozícióhoz való alkalmazkodáshoz. Egy néhány milliméterrel helytelenül áthelyezett kamera képszenzációhoz vezethet. A kamerával való pontos elhelyezés nehéz feladat, és pontosan meg kell egyeznie azzal a helymeghatározással és szemcsempével, amelynek színkorrekcióját az eszköz végzi.
* **Szemmozgás.** A kijelző alkalmazkodik a felhasználók szemének mozgásához a színek módosításához. A megjelenített adatok eltérhetnek attól függően, hogy a felhasználó a képernyő közepére, élére vagy sarkára néz-e. Egyetlen képrögzítés esetén a legjobb esetben is csak azt mutathatnánk meg, hogy milyen a megjelenítés a szem tekintetének megfelelő tengelyen.
* **Távmemónis megtekintés.** A HoloLens 2. megjelenítés úgy van kialakítva, hogy mindkét szemével megtekinthető legyen. Az agy alkalmazkodik két képhez, és összeolvad. Az egyetlen megjelenítést megjelenítő képek figyelmen kívül hagyják a másik kijelzőről származó információkat.
* **Kamera kitettségi ideje.** A kamera kitettségi ideje a másodperc 1/120-adának pontos többszöröse kell legyen. A HoloLens képkockaarány 120 Hz. A 2. HoloLens képrajzolása miatt egyetlen képkockát sem elég egyetlen képkockát rögzítenünk ahhoz, hogy megegyezz az ember vizuális élményének. Ugyanakkor, ha az eszköz egyáltalán – akár mikromovementsben is – mozog, a rendszer a hologramok stabilizálása érdekében reprodukálja a megjelenített képet. Több képkockát úgy rögzíthet, hogy közben HoloLens ne mozogjon, általában laboratóriumi telepítésre van szükség.
* **Kameraméret.** A pontos kép rögzítéséhez a kamera méretének legalább 3 mm-nek kell lennie. A kis méretű mobiltelefonos kamerák kisebb területről integrálják a világítást, mint az emberi szem. Az eszköz színkorrekciót alkalmaz a nagyobb súmok által megfigyelt mintákra. Kis tárgyak esetén az egységességi minták a rendszer által alkalmazott színkorrekciók ellenére is élesek és láthatóak maradnak.
* **Kamera-bejárati pupillák.** A kamera hátsó pupillának legalább 3 mm-es méretűnek kell lennie a pontos kép rögzítéséhez. Ellenkező esetben a kamera olyan gyakori mintákat rögzít, amelyek nem láthatók a szem számára. A bejárati tanuló pozíciójának a kamera előtt kell lennie, és szemtől enyhülési távolságba kell kerülnie, hogy ne legyen a rögzített kép eltérései és egyéb változatai.
* **Kamera pozíciója.** A HoloLens 2 megjelenítéséhez szükséges követelményeknek megfelelő kamerák nagyobbak, és nehéz a fényképezőgépet elég közel tartani az HoloLens 2-es megjelenítéshez, hogy megfigyelje a szín javított képét. Ha a kamera nem a megfelelő helyen van, a színkorrekció negatívan befolyásolhatja a 2 HoloLens rögzítését.
* **Képkorrekció.** A tipikus digitális kamerák és okostelefon-kamerák hangredukációs görbét (TRC) alkalmaznak, amely növeli a kontrasztot és a színt, így egy tetszetebb eredményt biztosítanak. Ha egy 2 HoloLens jelenik meg, ez a hanggörbék nem egységesek.

Minderől, hogy a specializált ipari kamerák továbbra is rögzítheti a reprezentatív képeket a HoloLens 2. kijelzőről. Sajnos az okostelefonok, a fogyasztói és a professzionális kamerák nem rögzítik a 2. HoloLens a felhasználó által látható képeket.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Mit tesz a szemredőbráció a képminőség megjelenítéséhez?

A HoloLens 2 képernyő aktív színekkel javítja a képeket a felhasználó szemének pozíciója alapján. [A](hololens-calibration.md) szemredúsztás két fontos bemenetet biztosít: (1) a felhasználó interpupilláris távolságát (IPD) és (2) az egyes szemeket jelölő irányt. Szemredőzés nélkül a rendszer alapértelmezés szerint névleges szempozíciót tart szemmozgás nélkül. Az aktív színkorrekció és a javítás hiányának különbsége maguktól a felhasználó fiziológiájától függ. Azok a felhasználók például, akik a rendszer alapértelmezett IPD-címével azonosak, kevesebb színkorrekciós fejlesztést fognak látni. Míg azok a felhasználók, akik sokkal szűkebb vagy szélesebb IPD-címmel vannak beállítva, mint a rendszer alapértelmezése, a megjelenített képben több változás jelenik meg.

Vegye figyelembe, hogy a [Holographic 20H2 Windows](hololens-release-notes.md#windows-holographic-version-20h2) új funkciója automatikusan észleli a szem [pozícióját.](hololens-calibration.md#auto-eye-position-support) 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>Mi a megjelenítési különbség a HoloLens (1. generációs) és a HoloLens között?

Az ügyfelek által az 1-es (1 HoloLens tapasztalása után a Microsoftnak adott első kérések közül (1) növekedett a mezőnézet, és (2) a fényerejének növelése. A technológiai fejlesztések lehetővé tették, hogy a Microsoft olyan hullámútút készítsen, amelyek megduplázták a nézet területének a kétszeresét, és olyan fényk kivetítőket, amelyek akár háromszor világosabb kijelzővel is használhatók. A hardver a megjelenítési képminőség három kereskedelmi viszonyát állítja be: (1) a nézet mezője, (2) a fényerejét és (3) a szín egységességét. A folyamatos technológiai fejlődés minden területen lehetővé teszi a fejlesztést anélkül, hogy egy másik területnek is feláldozza magát. Ez idő előtt a meglévő technológia beállítja az ilyen korlátozásokra vonatkozó korlátokat.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>Milyen fejlesztések fognak fejlődni a HoloLens 2 képminőség javítása érdekében?

Bár számos vizsgálat van folyamatban a képminőség javítása érdekében, a következő területek várhatók a közelgő frissítésekben:

* **Automatikus szempozíció.** Ez a funkció lehetővé teszi, hogy a szemszibrációs eljárások a háttérben is lezajlnak. Az aktív színkorrekció munkához a felhasználóknak többé nem kell szemredőznünk. Ehelyett csak működni fog.
* **Színkorrektérések fejlesztései.** Ez a frissítés a sötétebb színek (például sötétszürke) színértékeivel foglalkozik. Jelenleg a dimmer színek piros hangvételt választnak. Ez a probléma akkor is előfordul, ha a teljes kijelző halványan jelenik meg – a teljes kijelző piros színnel jelenik meg. Ez a probléma a piros színcsatornában végzett túl sok tevékenység eredménye a sötétebb színekhez. Ezen a dimmer-színeken jellemezte a görbe görbe vonalát, és dolgozunk azon, hogy a felhasználóknál is görbét vetünk. Az eredmény nagyobb színpontosság lesz a színskála fényspektrumában. Nem módosítja a fehér hátterek megjelenését teljes fényerejével. Továbbra is a sötét módú tervezési minták használatát javasoljuk az alkalmazásokban.
* **Olvasási mód.** Az alkalmazásfejlesztők a jobb angular-felbontás érdekében cserélik ki a megjelenítési mezőt. Az alkalmazásfejlesztők felülbírálhatják a leképezési mátrixot, így a tartalom a kijelző rajzolási felbontásában jelenik meg. Ez a funkció 30%-kal csökkenti a látómezőt, és ennek megfelelően növeli az angular-felbontást. Már dolgozunk ezen képesség bevezetésén a Mixed Reality [eszközkészletben.](https://github.com/Microsoft/MixedRealityToolkit-Unity) Ha elérhető, az olvasási mód bármely 2 HoloLens operációs rendszeren működik – nem függ az operációs rendszer frissítéstől.

Az operációs rendszer frissítéseit a rendszer automatikusan kézbesíti. A szoftverfejlesztés korai kiadását a belső előzetes verziós programon keresztül is tesztelheti.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Milyen útmutatás érhető el a fejlesztők számára a sötét mód tervezési alapelveinek alkalmazásával?

A fehér hátterek elkerülése érdekében a felhasználók a legjobb élményt tapasztalják. A sötét mód egy olyan tervezési elv, amelyet az alkalmazások fekete vagy sötét színű hátterek használatára használnak. A rendszerbeállítások alapértelmezett beállítása a sötét mód, és a **rendszerszín** beállításának Gépház  >    >  **módosíthatók.**

Javasoljuk a fejlesztőknek, hogy kövessék a sötét mód tervezési útmutatót:

* [Fejlesztői tervezési irányelvek a HoloLens megjelenítéshez](/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Ajánlott betűméretek](/windows/mixed-reality/typography#recommended-font-size)

Ha egy hologram fehér hátteret igényel, a hologram mérete kisebb legyen, mint a kijelző teljes nézete. Ez a méret lehetővé teszi, hogy a felhasználók a hologramot a kijelző közepére helyezzenek.

### <a name="how-do-you-clean-a-hololens-2-display"></a>Hogyan lehet megtisztítani a HoloLens 2-es megjelenítést?

Mikrofiberos rázkák használatával törölje a vizort. A vizor tisztítása 70%-os isopropyl-tartalmú éttermital világosítja fel a nyirkot, majd törölje a vizort. Olvassa el a teljes útmutatót [a HoloLens 2 tisztítási GYIK dokumentumban.](hololens2-maintenance.md)
