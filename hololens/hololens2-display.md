---
title: HoloLens 2 megjelenítési hibaelhárítás
description: A HoloLens 2 elvárásai megjelenik. Útmutatás a megjelenítések konfigurálásához a legjobb képminőség érdekében.
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
ms.openlocfilehash: 96bacd79d559bc0adcd42665c4a8b4af856b58b0
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923618"
---
# <a name="hololens-2-display-troubleshooting"></a>HoloLens 2 megjelenítési hibaelhárítás

## <a name="overview"></a>Áttekintés
A HoloLens 2 kijelző a hullámvezetők és a világos kivetítők kombinációja. Ha a headsetet viselik, a felhasználók a vizoron belüli objektíveket is végigküldik a hullámvezetőkben. A fényküldők a házon belül vannak, arow(ház) felett. A HoloLens 2 villanykörtét használ a megjelenítéshez.

## <a name="troubleshooting"></a>Hibaelhárítás

A következő lépésekkel biztosíthatja a megjelenítésekben megjelenő hologramok legjobb vizuális minőségét:

* **Növelje a kijelző fényerejét.** A hologramok akkor jelennek meg a legjobban, ha a kijelző a legvilágosabb. A HoloLens berakásakor a fényerejét jelző gombok a vizor bal oldalán, a völgy közelében vannak.
* **A vizort közelebb kell vinnie a szemhez.** A vizort a saját szemével legközelebbi pozícióba ássa le.
* **A vizor lefelé tolódása.** Próbálja meg lejjebb helyezni a fogat, ami azt eredményezi, hogy a vizor közelebb kerül az orrhoz.
* **[Szemreszeknáció.](hololens-calibration.md#calibrating-your-hololens-2)** A kijelző a képoptimalikus képoptimalikus megjelenítéshez használja az összetupláris távolságot (IPD) és a tekintetet. Ha nem futtat szemreszedt, a kép minősége rosszabbra is shozható. A szemredúsztás futtatásához kattintson a **Beállítások**  >  Rendszer a 100-edik  >    >  **szemre.**
* **Futtassa a megjelenítési színkorrektálást.** A [Windows Holographic 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) és  újabb verzióiban alternatív színprofilt is választhat a HoloLens 2-es megjelenítéshez. Ez segíthet a színek pontosabb megjelenítésében, különösen alacsonyabb megjelenítési fényerejénél. A színkorrektálást a Beállítások alkalmazásban, a **Rendszerbeállítások** lapon, a > lapon lehet megjeleníteni. 

    > [!NOTE]
    > Mivel ez a beállítás egy új színprofilt ment a megjelenítési belső vezérlőprogramba, ez egy eszközönkénti beállítás (és nem egyedi az egyes felhasználói fiókok számára).

### <a name="how-to-use-display-color-calibration"></a>A kijelző színkorrektálásának használata
1. Indítsa el **a Beállítások** alkalmazást, és **navigáljon a System > Egyedek elemre.**
1. A **Színkorrektálás megjelenítése alatt** válassza a Megjelenítés **színkorrektálásának futtatása** gombot.
1. Elindul a színekkel való megjelenítés élménye, és arra bátorítja, hogy a vizor a megfelelő helyen legyen.
1. Az utasítási párbeszédpanelek megnyitása után a kijelző automatikusan 30%-os fényerejére halványul.
    > [!TIP]
    > Ha nem látja a halvány jeleneteket a környezetében, manuálisan módosíthatja a HoloLens 2 fényerejét az eszköz bal oldalán található fényerejét jelző gombokkal.
1. Válassza az 1–6. gombot, hogy azonnal kipróbálja az egyes színprofilokat, és keresse meg azt, amely a leginkább hasonlít a szemére (ez általában azt jelenti, hogy a jelenetnek leginkább megfelelő profil jelenik meg a legsemlegesebbnek, a szürkeárnyalatos mintázattal és a vékony tonének pedig az elvárt módon kell megjelennie.)

    ![Színjelenet megjelenítése](images/color-cal-ui.png)
    
6. Ha elégedett a kiválasztott profillal, válassza a **Mentés & Kilépés gombot**
1. Ha nem szeretne módosításokat tenni, válassza a Mégse & **Kilépés** gombot, és a módosítások visszaállnak

> [!TIP]
> A megjelenítési színbeállítás használata során az alábbi tippeket kell szem előtt tartania:
> - A megjelenítési színek színkorrektálását bármikor újra futtathatja a Beállításokban
> - Ha az eszközön bárki korábban használta a színprofilok módosítására vonatkozó beállítást, a legutóbbi módosítás dátuma/időpontja megjelenik a Beállítások lapon
> - A megjelenítési színek színkorrektálásának újrafuttatásakor a korábban mentett színprofil ki lesz emelve, és a 0. profil nem jelenik meg (mivel a 0. profil a megjelenítés eredeti színprofilját jelöli)
> - Ha vissza szeretne állítani a megjelenítés eredeti színprofiljára, ezt a Beállítások lapon használhatja (lásd a színprofil [alaphelyzetbe](#how-to-reset-color-profile)állítását)

### <a name="how-to-reset-color-profile"></a>Színprofil alaphelyzetbe állítása

Ha nem elégedett a HoloLens 2-ben mentett egyéni színprofillal, visszaállíthatja az eszköz eredeti színprofilját:
1. Indítsa el **a Beállítások** alkalmazást, és **navigáljon a System > Egyedek elemre.**
1. A **Színkorrektálás megjelenítése alatt** válassza a Visszaállítás alapértelmezett **színprofilra gombot.**
1. Amikor megnyílik a párbeszédpanel, válassza **az** Újraindítás lehetőséget, ha készen áll a HoloLens 2 újraindítására és a módosítások alkalmazására.

### <a name="top-display-color-calibration-known-issues"></a>A legjobb megjelenítési színekkel kapcsolatos ismert problémák

- A Beállítások lapon az állapotsring, amely a színprofil legutóbbi módosításának időpontját jelzi, elajánl, amíg újra be nem tölti a Beállítások lapot 
    - **Áthidaló** megoldás: Válasszon ki egy másik Beállítások lapot, majd válassza újra a Hibalapon.
- Ha a HoloLens 2 alvó üzemmódba vált a kijelző színének színkorrektálásának futtatása közben, később ismét a vegyes valóságú otthonra tér vissza, és a kijelző fényerejének szintje továbbra is halványan jelenik meg.
- Előfordulhat, hogy néhányszor le kell nyomni a kijelzőgombokat az eszköz bal oldalán, hogy azok a várt módon működjön.
- A honosítás nem minden piac esetében teljes

## <a name="faq"></a>GYIK

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Milyen mintázatok jelennek meg időnként a kijelző alsó sarkaiban?

Esetenként a HoloLens 2 különböző mintákat jelenít meg a kijelző bal alsó és jobb sarkában. Példák alább láthatók (animált GIF-ek). Ez a minta a HoloLens 2-eszköz normál működésének része, amely a kijelzőt az optimális élmény érdekében berakja.

![Kétfázisú minta](./images/DAT-Biphase-Fiducial.gif) ![GEO minta](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>Miért nem tudok pontos képet venni a HoloLens 2-es kijelzőmről?

A HoloLens 2-es kijelző emberi szem számára készült. Az eszköz aktív színkorrekciós rendszerrel rendelkezik, amely alkalmazkodik a felhasználó szeméhez. Az emberi szemhez képest a kamerák másképp látják a környezeteket, és az alábbiakban néhány olyan tényezőt láthatunk, amelyek hatással lehetnek a kamera és a felhasználó által látható adatok közötti inkonzisztenciára.

* **Szem pozíciója.** A HoloLens 2 kijelző kifejezetten a felhasználó szem helyzetének megfelelő. A HoloLens 2 szemkövetési technológiát alkalmaz a felhasználó szempozícióhoz való alkalmazkodáshoz. Egy néhány milliméterrel helytelenül áthelyezett kamera képszenzációhoz vezethet. A kamerával való pontos elhelyezés nehéz feladat, és pontosan meg kell egyeznie azzal a helymeghatározással és szemcsempével, amelynek színkorrekcióját az eszköz végzi.
* **Szemmozgás.** A kijelző alkalmazkodik a felhasználók szemének mozgásához a színek módosításához. A megjelenített adatok eltérhetnek attól függően, hogy a felhasználó a képernyő közepére, élére vagy sarkára néz-e. Egyetlen képrögzítés esetén a legjobb esetben is csak azt mutathatnánk meg, hogy milyen a megjelenítés a szem tekintetének megfelelő tengelyen.
* **Távmemónis megtekintés.** A HoloLens 2-es kijelző úgy van kialakítva, hogy mindkét szemével megtekinthető legyen. Az agy alkalmazkodik két képhez, és összeolvad. Az egyetlen megjelenítést megjelenítő képek figyelmen kívül hagyják a másik kijelzőről származó információkat.
* **Kamera kitettségi ideje.** A kamera kitettségi idejét a másodperc 1/120-adának pontos többszörösének kell lennie. A HoloLens megjelenítési képkocka-sebessége 120 Hz. Mivel a HoloLens 2 képeket rajzol, egyetlen képkockát sem elég egyetlen képkockát rögzíteni ahhoz, hogy az egy ember által tapasztaltakhoz illeszkedő legyen. Ugyanakkor, ha az eszköz egyáltalán – akár mikromovementsben is – mozog, a rendszer a hologramok stabilizálása érdekében reprodukálja a megjelenített képet. Ha több képkockát rögzít, miközben a HoloLens nem mozog, általában laboratóriumi telepítés szükséges.
* **Kameraméret.** A pontos kép rögzítéséhez a kamera méretének legalább 3 mm-nek kell lennie. A kis méretű mobiltelefonos kamerák kisebb területről integrálják a világítást, mint az emberi szem. Az eszköz színkorrekciót alkalmaz a nagyobb méretű mintákra. Kis tárgyak esetén az egységességi minták a rendszer által alkalmazott színkorrekciók ellenére is élesek és láthatóak maradnak.
* **Kamera-bejárati pupillák.** A pontos kép rögzítéséhez a kamera hátsó pupillának legalább 3 mm-esnek kell lennie. Ellenkező esetben a kamera olyan gyakori mintákat rögzít, amelyek nem láthatók a szem számára. A bejárati tanuló pozíciójának a kamera előtt kell lennie, és szemtől enyhülési távolságba kell kerülnie, hogy ne legyen a rögzített kép aberrációja és egyéb változatai.
* **Kamera pozíciója.** A HoloLens 2 megjelenítéséhez szükséges követelményeknek megfelelő kamerák nagyobbak, és nehéz a kamerát elég közel helyezze a HoloLens 2 kijelzőjére, hogy megfigyelje a színkel javított képet. Ha a kamera nem a megfelelő helyen van, a színkorrekció negatívan befolyásolhatja a HoloLens 2 kijelző rögzítését.
* **Képkorrekció.** A tipikus digitális kamerák és okostelefon-kamerák hangredukációs görbét (TRC) alkalmaznak, amely növeli a kontrasztot és a színt, így egy tetszetebb eredményt biztosítanak. HoloLens 2-es megjelenítésre alkalmazva ez a hanggörbék nem egységesek.

Minderől, hogy a specializált ipari kamerák továbbra is rögzítheti a HoloLens 2-es kijelzőről származó reprezentatív képeket. Sajnos az okostelefonok, a fogyasztók és a professzionális kamerák nem rögzítik a holoLens 2 felhasználó által látható képekkel egyező képeket.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Mit tesz a szemredrebráció a képminőség megjelenítéséhez?

A HoloLens 2-ben aktív szín jelenik meg, amely a felhasználó szemének pozíciója alapján javítja a képeket. [A](hololens-calibration.md) szemkontraszt két fontos bemenetet biztosít: (1) a felhasználó interpupilláris távolságát (IPD) és (2) az egyes szemeket jelölő irányt. A szemmozgás nélkül a rendszer alapértelmezés szerint névleges szempozíciót tart szemmozgás nélkül. Az aktív színkorrekció és a nincs javítás közötti különbség a felhasználó fiziológiáján múlik. Azok a felhasználók például, akiknél az IPD-cím ugyanaz, mint a rendszer alapértelmezése, kevesebb színkorrekciós fejlesztést fognak látni. Míg a rendszer alapértelmezett IPD-címnél sokkal szűkebb vagy szélesebb IP-címmel használó felhasználók több változást fognak látni a megjelenített képen.

Vegye figyelembe, hogy a [Windows Holographic 20H2](hololens-release-notes.md#windows-holographic-version-20h2) egy új szolgáltatása automatikusan észleli a szem [pozícióját.](hololens-calibration.md#auto-eye-position-support) 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>Milyen megjelenítési különbségek vannak a HoloLens (1. generációs) és a HoloLens 2 között?

Az ügyfelek a HoloLens 1 holoLenst tapasztalása után (1) növelték a megtekintési mezőt, és (2) növelték a fényerejét. A technológiai fejlesztések lehetővé tették, hogy a Microsoft olyan hullámútút készítsen, amely megduplázta a nézőpont területét, és olyan fény kivetítőket készítsen, amelyek legfeljebb háromszor világosak. A hardver három, a megjelenítési képminőségre vonatkozó kereskedelmi viszony alapértékét állítja be: (1) a nézet mezője, (2) a fényerejét és (3) a szín egységességét. A folyamatos technológiai fejlődés minden területen lehetővé teszi a fejlesztést anélkül, hogy egy másik területet feláldoznak. E körülmények között a meglévő technológia beállítja az ilyen korlátozásokhoz elérhető korlátokat.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>Milyen fejlesztések fognak javítani a HoloLens 2 képminőségén?

Bár számos vizsgálat van folyamatban a képminőség javítása érdekében, a következő területek várhatók a soron következő frissítésekben:

* **Automatikus szempozíció.** Ez a funkció lehetővé teszi, hogy a szemúti eljárások a háttérben lezajlnak. Az aktív színkorrekció munkához a felhasználóknak többé nem kell szemredő színkorrekciót futtatni. Ehelyett csak működni fog.
* **Színjavítások fejlesztései.** Ez a frissítés a sötétebb színek (például sötétszürke) színértékeivel foglalkozik. Jelenleg a dimmer színek piros hangvételt választnak. Ez a probléma akkor is előfordul, ha a teljes kijelző halványan jelenik meg – a teljes kijelző piros színeket kap. Ez a probléma annak az eredménye, hogy a piros színcsatorna túl sok tevékenységet végzett a sötétebb színekhez. Ezen a dimmer-színeken jellemezte a görbe görbéit, és dolgozunk azon, hogy felhasználói eljárásokat kínálunk. Az eredmény nagyobb színpontosság lesz a fényerejének spektrumában. Ez nem módosítja a fehér hátterek megjelenését teljes fényerejével. Továbbra is a sötét módú tervezési minták használatát javasoljuk az alkalmazásokban.
* **Olvasási mód.** Az alkalmazásfejlesztők a jobb angular-felbontás érdekében cserélik a megjelenítési mezőt. Az alkalmazásfejlesztők felülbírálhatják a leképezési mátrixot, így a tartalom a kijelző rajzolási felbontásában jelenik meg. Ez a funkció 30%-kal csökkenti a látómezőt, és ennek megfelelően növeli az angular-felbontást. Folyamatban van ennek a képességnek a bevezetése a [Mixed Reality Eszközkészletben.](https://github.com/Microsoft/MixedRealityToolkit-Unity) Ha elérhető, az olvasási mód minden HoloLens 2 operációs rendszeren működik – nem függ az operációs rendszer frissítéstől.

Az operációs rendszer frissítéseit a rendszer automatikusan kézbesíti. A belső előzetes verziós programon keresztül a szoftverfejlesztés korai kiadását is tesztelheti.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Milyen útmutatás érhető el a fejlesztők számára a sötét mód tervezési alapelveinek alkalmazásával?

A fehér hátterek elkerülésekor a felhasználók a legjobb élményt tapasztalják. A sötét mód egy olyan tervezési elv, amelyet az alkalmazások fekete vagy sötét színű hátterek használatára használnak. A rendszerbeállítások alapértelmezett beállítása sötét mód, és a **Beállítások**  >  **rendszerszíne lapon módosítható.**  >  

Javasoljuk a fejlesztőknek, hogy kövessék a sötét mód tervezési útmutatót:

* [Fejlesztői tervezési irányelvek HoloLens-megjelenítéshez](https://docs.microsoft.com/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Ajánlott betűméretek](https://docs.microsoft.com/windows/mixed-reality/typography#recommended-font-size)

Ha egy hologram fehér hátteret igényel, a hologram mérete ne legyen kisebb, mint a kijelző teljes látómezője. Ez a méret lehetővé teszi, hogy a felhasználók a hologramot a kijelző közepére helyezzenek.

### <a name="how-do-you-clean-a-hololens-2-display"></a>Hogyan lehet megtisztítani a HoloLens 2-kijelzőket?

Mikrofiberos málnával törölje ki a vizort. A vizor tisztítására használjon 70%-os isopropyl-ét, hogy könnyedén megszendítsen egy fogat, majd törölje a vizort. Olvassa el a teljes útmutatót a [HoloLens 2 cleaning FAQ (A HoloLens 2 tisztítása – GYIK) című cikkben.](hololens2-maintenance.md)
