---
title: A HoloLens 2 megjelenítése
description: Megjelenik a HoloLens 2-re vonatkozó elvárások. Útmutatás a megjelenítések konfigurálásához a legjobb képminőség érdekében.
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
ms.openlocfilehash: 71dff00ff75feea4408979d2ce69fb14bf9bf3b7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379625"
---
# <a name="hololens-2-display"></a>HoloLens 2-es megjelenítés

A HoloLens 2 kijelző a hullámvezetők és a világos kivetítők kombinációja. A felhasználók végigtekintnek a hullámos úton – a vizoron belüli objektívek –, amikor a headsetet viselik. A világos kivetítők a házon belül vannak, arow felett. A HoloLens 2 világítást használ a kijelző megjelenítéséhez.

## <a name="troubleshooting"></a>Hibaelhárítás

HoloLens 2 esetén a következő lépésekkel biztosíthatja a megjelenítésekben megjelenő hologramok legjobb vizuális minőségét:

* **Növelje a kijelző fényerejét.** A hologramok akkor jelennek meg a legjobban, ha a kijelző a legtisztább szinten van.
* **Közelebb hozza a szemhez a vizort.** A vizort a saját szemének legközelebbi pozícióhoz vassa le.
* **Tolja le a vizort.** Próbálja meg lejjebb mozgatni a fogat, ami azt eredményezi, hogy a vizor közelebb kerül az orrhoz.
* **Szemredúsztás.** A kijelző az összetűnés távolság (IPD) és a szem tekintete alapján optimalizálja a megjelenített képeket. Ha nem futtatja a szemredúsztásokat, a kép minősége rosszabb lehet. A szemredúsztás futtatásához kattintson a **Settings**  >  **System**  >  **Egyedek**  >  **futtatására való szemkontraszt elemre.**
* **Futtassa a megjelenítési színnek való megfelelőt.** A [Windows Holographic 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) és  újabb verzióiban alternatív színprofilt is választhat a HoloLens 2-es megjelenítéshez. Ez segíthet a színek pontosabb megjelenítésében, különösen alacsonyabb megjelenítési fényerejénél. A színkorrektálás  megjelenítése a Beállítások alkalmazásban, a Rendszerbeállítások lapon > **található.**

    > [!NOTE]
    > Mivel ez a beállítás új színprofilt ment a megjelenítési belső vezérlőprogramba, ez egy eszközönkénti beállítás (és nem az egyes felhasználói fiókok egyedi beállítása).

### <a name="how-to-use-display-color-calibration"></a>A megjelenítési színek színezésének használata
1. Indítsa el **a Beállítások** alkalmazást, és lépjen a System > **És elemre.**
1. A **Színkorrektálás megjelenítése alatt** válassza a Megjelenítés **színkorrektálás gombját.**
1. Elindul a színekkel való megjelenítés élménye, és arra bátorítja, hogy a vizor a megfelelő helyen legyen.
1. Az utasítási párbeszédpanelek megnyitása után a kijelző automatikusan 30%-os fényerejére halványul.
    > [!TIP]
    > Ha nem látja a halvány jeleneteket a környezetében, manuálisan módosíthatja a HoloLens 2 fényerejét az eszköz bal oldalán található világítási gombokkal.
1. Válassza az 1–6. gombot, hogy azonnal kipróbálja az egyes színprofilokat, és keresse meg azt, amely a leginkább hasonlít a szemére (ez általában azt jelenti, hogy a profil, amely segít a jelenetnek a legsemlegesebbnek megjelenni, a szürke skálázási mintával és a hajszínszínekkel, amelyek a vártnak megfelelőnek jelennek meg.)

    ![Színjelenet megjelenítése](images/color-cal-ui.png)
    
6. Ha elégedett a kiválasztott profillal, válassza a **Save & Exit (Kilépés)** gombot
1. Ha nem szeretne módosításokat tenni, válassza a Mégse & **Kilépés** gombot, és a módosítások vissza lesznek állva

> [!TIP]
> Íme néhány hasznos tipp, amely a megjelenítési színek színbeállításának használata során hasznos lehet:
> - A megjelenítési színek színkorrektálását bármikor újra futtathatja a Beállítások között
> - Ha az eszközről valaki korábban már használta a beállítást a színprofilok módosításához, a legutóbbi módosítás dátuma és időpontja megjelenik a Beállítások lapon.
> - Amikor újra futtatja a megjelenítési színek színkiszínezését, a korábban mentett színprofil ki lesz emelve, és a 0. profil nem jelenik meg (mivel a 0. profil a megjelenítés eredeti színprofilját jelöli)
> - Ha vissza szeretne állítani a megjelenítés eredeti színprofiljára, ezt a Beállítások lapon használhatja (lásd a színprofil alaphelyzetbe [állítását)](#how-to-reset-color-profile)

### <a name="how-to-reset-color-profile"></a>Színprofil alaphelyzetbe állítása

Ha nem elégedett a HoloLens 2-ben mentett egyéni színprofillal, visszaállíthatja az eszköz eredeti színprofilját:
1. Indítsa el **a Beállítások** alkalmazást, és lépjen a System > **És elemre.**
1. A **Színkorrektálás megjelenítése alatt** válassza a Visszaállítás alapértelmezett **színprofilra gombot.**
1. Amikor megnyílik a párbeszédpanel, válassza **az** Újraindítás lehetőséget, ha készen áll a HoloLens 2 újraindítására és a módosítások alkalmazására.

### <a name="top-display-color-calibration-known-issues"></a>A legjobb megjelenítési színekkel kapcsolatos ismert problémák

- A Beállítások lapon az állapotsring, amely a színprofil legutóbbi módosításának időpontját jelzi, elavult, amíg újra be nem töltse a Beállítások lapot 
    - **Áthidaló** megoldás: Válasszon ki egy másik Beállítások lapot, majd válassza újra a Hibabeesés lapot.
- Ha a HoloLens 2 alvó üzemmódba kerül a kijelző színének színkorrektálásának futtatása közben, az később folytatódik a vegyes valóság kezdőlapján, és a kijelző fényerejének szintje továbbra is halványan jelenik meg.
- Előfordulhat, hogy néhányszor fel-/le kell nyomni az eszköz bal oldalán található világítási gombokat, hogy azok a várt módon működjön.
- A honosítás nem minden piac esetében teljes

## <a name="faq"></a>GYIK

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Milyen mintázatok jelennek meg időnként a kijelző alsó sarkaiban?

Esetenként a HoloLens 2 különböző mintákat jelenít meg a kijelző bal alsó és jobb sarkában. Példák alább láthatók (animált GIF-ek). Ez a minta a HoloLens 2-eszköz normál működésének része, amely a kijelzőt az optimális élmény érdekében bekalkenneli.

![Kétfázisú minta](./images/DAT-Biphase-Fiducial.gif) ![GEO minta](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>Miért nem tudok pontos képet lefényképezni a HoloLens 2-es megjelenítésről?

A HoloLens 2 kijelzőt emberi szem számára tervezték. Az eszköz aktív színkorrekciós rendszerrel rendelkezik, amely alkalmazkodik a felhasználó szeméhez. Az emberi szemhez képest a kamerák a környezeteket másképp látják, és az alábbiakban néhány olyan tényezőt látnak, amelyek hatással lehetnek a kamera által rögzített és a felhasználó által látható adatok közötti inkonzisztenciára.

* **Szem pozíciója.** A HoloLens 2 kijelző kifejezetten a felhasználó szempozíciója számára készült. A HoloLens 2 szemkövetési technológiát alkalmaz a felhasználó szempozícióhoz való alkalmazkodáshoz. Egy néhány milliméterrel helytelenül áthelyezett kamera képszenzációhoz vezethet. A kamerával való pontos elhelyezés nehéz feladat, és pontosan meg kell egyeznie a színkorrekciót végző eszköz helyével és szemével.
* **Szemmozgás.** A kijelző alkalmazkodik a felhasználó szemének mozgásához a színek módosításához. A megjelenített adatok eltérhetnek attól függően, hogy a felhasználó a képernyő közepét, élét vagy sarkát nézi. Egyetlen képrögzítés esetén a legjobb esetben is csak a tekintet irányának megfelelő tengely megjelenítése látható.
* **Távértekvő megtekintés.** A HoloLens 2 kijelző úgy van kialakítva, hogy mindkét szemével megtekinthető legyen. Az agy alkalmazkodik két képhez, és összeolvasztja őket. Az egyetlen megjelenítést megjelenítő képek figyelmen kívül hagyják a másik kijelzőről származó információkat.
* **Kamera kitettségi ideje.** A kamera kitettségi ideje a másodperc 1/120-adának pontos többszöröse kell legyen. A HoloLens megjelenítési képkocka-sebessége 120 Hz. Mivel a HoloLens 2 képeket rajzol, egyetlen képkockát sem elég egyetlen képkockát rögzíteni ahhoz, hogy az egy ember által tapasztalt képi élményt meg tudja egyezni. Ugyanakkor, ha az eszköz egyáltalán – még a mikroszolgáltatásokban is – mozog, a rendszer újra kiveszi a képet a kijelzőről, hogy stabilizálja a hologramokat. Ha több képkockát rögzít, miközben a HoloLens nem mozog, általában laboratóriumi telepítés szükséges.
* **Kameraméret.** A pontos kép rögzítéséhez a kamera méretének legalább 3 mm-nek kell lennie. A kis méretű mobiltelefonos kamerák kisebb területről integrálják a világítást, mint az emberi szem. Az eszköz színkorrekciót alkalmaz a nagyobb mellök által megfigyelt mintákra. Kis méretű öklök esetén az egységességi minták élesebbek, és a rendszer által alkalmazott színkorrekciók ellenére is láthatóak maradnak.
* **Kamerabereklám.** A kamerának legalább 3 mm-es méretűnek kell lennie a pontos kép rögzítéséhez. Ellenkező esetben a kamera olyan gyakori mintákat rögzít, amelyek nem láthatók a szem számára. A bevezető tanuló pozíciójának a kamera előtt kell lennie, és a szem enyhülési távolsága mellett kell lennie, hogy elkerülje a rögzített kép eltérését és egyéb variációit.
* **Kamera pozíciója.** A HoloLens 2 megjelenítési követelményeinek megfelelő kamerák nagyobbak, és nehéz a holoLens 2-es kijelzőhez elég közel tartani a kamerát, hogy megfigyelje a színekkel javított képet. Ha a kamera nem a megfelelő helyen van, a színkorrekció negatívan befolyásolhatja a HoloLens 2 kijelző rögzítését.
* **Képkorrekció.** A tipikus digitális kamerák és okostelefon-kamerák hangredukációs görbét (TRC) alkalmaznak, amely növeli a kontrasztot és a színt, hogy a megfelelőbb eredményt nyújtson. HoloLens 2-es megjelenítésre alkalmazva ez a hanggörbék nem egységesek.

Mindezeken túl speciális ipari kamerák is rögzíthetik a HoloLens 2 kijelző reprezentatív képeit. Sajnos az okostelefonok, a fogyasztók és a professzionális kamerák nem rögzítik a holoLens 2-ben a felhasználó által látható képeket.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Mit tesz a szemredrebráció a képminőség megjelenítéséhez?

A HoloLens 2-ben aktív szín jelenik meg, amely a felhasználó szemének pozíciója alapján javítja a képeket. [A](hololens-calibration.md) szemkontraszt két fontos bemenetet biztosít: (1) a felhasználó interpupilláris távolságát (IPD) és (2) az egyes szemeket jelölő irányt. A szemmozgás nélkül a rendszer alapértelmezés szerint névleges szempozíciót tart szemmozgás nélkül. Az aktív színkorrekció és a nincs javítás közötti különbség a felhasználó fiziológiáján múlik. Azok a felhasználók például, akiknél az IPD-cím ugyanaz, mint a rendszer alapértelmezése, kevesebb színkorrekciós fejlesztést fognak látni. Bár a rendszer alapértelmezett IPD-címnél sokkal szűkebb vagy szélesebb IP-címmel felhasználói több módosítást fognak látni a megjelenített képen.

Vegye figyelembe, hogy a [Windows Holographic 20H2](hololens-release-notes.md#windows-holographic-version-20h2) új szolgáltatása automatikusan észleli a szem [pozícióját.](hololens-calibration.md#auto-eye-position-support) 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>Milyen megjelenítési különbségek vannak a HoloLens (1. generációs) és a HoloLens 2 között?

Az ügyfelek a HoloLens 1 holoLenst tapasztalása után (1) növelték a megtekintési mezőt, és (2) növelték a fényerejét. A technológiai fejlesztések lehetővé tették, hogy a Microsoft olyan hullámútút készítsen, amely megduplázta a nézőpont területét, és olyan fény kivetítőket készítsen, amelyek legfeljebb háromszor világosak. A hardver a megjelenítési képminőség három kereskedelmi halmazának alapértékét állítja be: (1) mezőnézet, (2) fényerejét és (3) szín egységességét. A folyamatos technológiai fejlődés minden területen lehetővé teszi a fejlesztést anélkül, hogy egy másik területet feláldozunk. A meglévő technológia e körülmények között beállítja a korlátokat.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>Milyen fejlesztések fognak javítani a HoloLens 2 képminőségén?

Bár számos vizsgálat van folyamatban a képminőség javítása érdekében, a következő területek várhatók a soron következő frissítésekben:

* **Automatikus szempozíció.** Ez a funkció lehetővé teszi, hogy a szemúti eljárások a háttérben lezajlnak. Az aktív színkorrekció munkához a felhasználóknak többé nem kell szemredő színkorrekciót futtatni. Ehelyett csak működni fog.
* **Színjavítások fejlesztései.** Ez a frissítés a sötétebb színek (például sötétszürke) színértékeivel foglalkozik. Jelenleg a dimmer színek piros hangvételt választnak. Ez a probléma akkor is előfordul, ha a teljes kijelző halványan jelenik meg – a teljes kijelző piros színeket kap. Ez a probléma annak az eredménye, hogy a piros színcsatorna túl sok tevékenységet végzett a sötétebb színekhez. Ezen a dimmer-színeken jellemezte a görbe görbéit, és dolgozunk azon, hogy felhasználói eljárásokat kínálunk. Az eredmény nagyobb színpontosság lesz a fényerejének spektrumában. Ez nem módosítja a fehér hátterek megjelenését teljes fényerejével. Továbbra is a sötét módú tervezési minták használatát javasoljuk az alkalmazásokban.
* **Olvasási mód.** Az alkalmazásfejlesztők a jobb angular-felbontás érdekében cserélik a megjelenítési mezőt. Az alkalmazásfejlesztők felülbírálhatják a leképezési mátrixot, így a tartalom a kijelző rajzolási felbontásában jelenik meg. Ez a funkció 30%-kal csökkenti a látómezőt, és ennek megfelelően növeli az angular-felbontást. Folyamatban van ennek a képességnek a bevezetése a [Mixed Reality eszközkészletben.](https://github.com/Microsoft/MixedRealityToolkit-Unity) Ha elérhető, az olvasási mód minden HoloLens 2 operációs rendszeren működik – nem függ az operációs rendszer frissítéstől.

Az operációs rendszer frissítéseit a rendszer automatikusan kézbesíti. A belső előzetes verziós programon keresztül a szoftverfejlesztés korai kiadását is tesztelheti.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Milyen útmutatás érhető el a fejlesztők számára a sötét mód tervezési alapelveinek alkalmazásával?

A fehér hátterek elkerülésekor a felhasználók a legjobb élményt tapasztalják. A sötét mód egy olyan tervezési elv, amelyet az alkalmazások fekete vagy sötét színű hátterek használatára használnak. A rendszerbeállítások alapértelmezett beállítása sötét mód, és a **Beállítások**  >  **rendszerszíne lapon módosítható.**  >  

Javasoljuk a fejlesztőknek, hogy kövessék a sötét mód tervezési útmutatót:

* [Fejlesztői tervezési irányelvek HoloLens-megjelenítéshez](https://docs.microsoft.com/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Ajánlott betűméretek](https://docs.microsoft.com/windows/mixed-reality/typography#recommended-font-size)

Ha egy hologram fehér hátteret igényel, a hologram mérete ne legyen kisebb, mint a kijelző teljes látómezője. Ez a méret lehetővé teszi, hogy a felhasználók a hologramot a kijelző közepére helyezzenek.

### <a name="how-do-you-clean-a-hololens-2-display"></a>Hogyan lehet megtisztítani a HoloLens 2-kijelzőket?

Mikrofiberos málnával törölje ki a vizort. A vizor tisztítására használjon 70%-os isopropyl-ét, hogy kismempénítsen egy arcot, majd törölje a vizort. Olvassa el a teljes útmutatót a [HoloLens 2 cleaning FAQ (A HoloLens 2 tisztítása – GYIK) című cikkben.](hololens2-maintenance.md)
