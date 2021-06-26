---
title: Tájékozódás a HoloLens 2-ben
description: Fedezze fel a vegyes valóságot, és ismerkedés ezzel az útmutatóval, amely bemutatja, hogyan használhatja a HoloLens 2-eszközöket a saját kezűleg.
ms.assetid: 5f791a5c-bdb2-4c5d-bf46-4a198de68f21
ms.date: 9/17/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 8acf5659739d58d24add3f299daeacab7132a086
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924587"
---
# <a name="getting-around-hololens-2"></a>Tájékozódás a HoloLens 2-ben

Készen áll a hologramok világának felfedezésére?

Ez az útmutató a következő bevezetőt biztosítja:

- Vegyes valóság interakciója
- A hologramok használata a HoloLens 2-ben a kéz és a hang használatával
- Navigálás a Windows 10 HoloLensben (Windows Holographic)

## <a name="discover-mixed-reality"></a>Vegyes valóság felfedezése

A HoloLensben a hologramok a fizikai környezettel ötvözik a digitális világot, hogy úgy nézzenek ki és hangon, mintha a világ részei lenne. Még ha a hologramok is a közelben vannak, mindig láthatja a környezetet, szabadon mozoghat, és interakcióba léphet emberekkel és objektumokkal. Ezt a tapasztalatot "vegyes valóságnak" hívjuk.

A holografikus képkockák olyan pozícióba ékezetesek, ahol a tekintete a legérzékenyebb a részletekre, a átlátó objektívek pedig tisztán látják a periférialátást. A térbeli hangokkal a hologramok úgy is kitűzve maradtak, hogy figyelnek, még akkor is, ha az Ön mögött van. Mivel a HoloLens megérti a fizikai környezetet, hologramokat is lehet a valós objektumokra, például táblákra és falakra és objektumok köréhelyeket adni.

A HoloLens használata sokban hasonló az intelligens telefonhoz. A kézzel holografikus ablakokat, menüket és gombokat érhet el és kezelhet.  

Ha már ismeri ezeket az alapszintű interakciókat, a HoloLens használata nem lesz egyszerű.

> [!TIP]
> Ha most van egy HoloLens-alkalmazása a közelben, a **Tippek** alkalmazás gyakorlati oktatóanyagokat biztosít a HoloLensen való kézi interakciókhoz.  
> Használja az indítási kézmozdulatot a **Start menüre,** vagy mondja ki a "Go to Start" (Ugrás az indításhoz) lehetőséget, és válassza a **Tippek lehetőséget.**

## <a name="the-hand-tracking-frame"></a>A kézkövetési képkocka

A HoloLens érzékelői néhány lábat látnak bármelyik oldalon. A kézhasználatkor a kereten belül kell tartania őket, különben a HoloLens nem fogja látni őket. A keret azonban mozgásban van.  

![A HoloLens kézkövetési keretét bemutató kép](./images/hololens-2-gesture-frame.png)

## <a name="touch-holograms-near-you"></a>Touch hologramok a közelben

Ha egy hologram van a közelében, vigye a kézét hozzá, és egy fehér körnek kell megjelennie az indexa hegyén.  Ez az **érintéses kurzor,** amely a hologramok finom érintését és a vele való interakciót segíti. Ha **kijelöl valamit,** egyszerűen **koppintson** rá az érintéses kurzorral. **Úgy** **görgetheti** a tartalmat, hogy az ujjlenyomatával csúszik a tartalom felszínére, pont úgy, mint egy érintőképernyőn.

Ahhoz, **hogy** megragadjon egy  hologramot a közelében, csippentse össze a ujjlenyomatát és **indexelési** ujjlenyomatát a hologramon, és tartsa lenyomva. Hogy engedjen el, engedje el az étkét. Ezzel a **kézmozdulattal** áthelyezhetők, átméretezhetők és elforgathatóak a 3D-s objektumok és alkalmazásablakok a vegyes valóság kezdőlapon.

Ha egy helyi **menüt** szeretne, például az alkalmazáscsempéken találhatóakat a Start menü **koppintson** és tartsa lenyomva, ahogy az érintőképernyőn is.

## <a name="use-hand-ray-for-holograms-out-of-reach"></a>A kéz sugarának használata a hologramok el nem éri

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3ZOum]

Ha nincsenek hologramok a kéz közelében, az **érintéses** kurzor automatikusan el fog rejteni, és a kéz sugárai megjelennek a kézről.  A kéz sugárokkal távolról kommunikálhat a hologramokkal.

> [!TIP]
> Ha a kéz sugarai zavarónak találják, elrejtheti őket az "Hide hand rays" (Kézredő sugárok elrejtése) szóval. A "Show hand rays" (Kézredő sugárok megjelenítése) szóval újra megjelentetjük őket.

### <a name="select-using-air-tap"></a>Kijelölés a légi koppintással

Ha kiválaszt valamit a **kéz sugarával,** kövesse az alábbi lépéseket:

1. Az elem megcélzott elemét egy, a telefonról származó kézbefedő sugár használatával. Nem kell a teljes karot megemelni, alacsonyan kell tartania a fogat, és kényelmesen kell tartania.
1. Az indexamutatót egyenesen a felső határ felé irányítjuk.
1. A légi **koppintás** kézmozdulatának végrehajtásához csippentse össze a hüvelykujját és az indexelő ujjlenyomatát, majd engedje el őket gyorsan.

   ![Légi koppintásos kézmozdulat animációja](./images/hololens-air-tap.gif)

### <a name="grab-using-air-tap-and-hold"></a>Fogás légi koppintással és tartsa lenyomva

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxnh]

Ha egy hologramot vagy görgetni az alkalmazásablak tartalmát a kéz sugarával, kezdjen egy légi koppintással, de ne szabadossa ki őket, hanem tartsa együtt az arcot.

Használjon **légi koppintással és** tartsa lenyomva a következő műveleteket a kézi sugár használatával:

- **Görgessen le.** Az alkalmazásablak tartalmának görgetéshez koppintson a levegőre, és tartsa lenyomva a tartalmat, majd mozgassa felfelé, lefelé vagy oldalra a kéz sugárát.
- **Ragadja meg a et.** Egy alkalmazásablak vagy hologram megragadáshoz célozza meg az alkalmazás címsorát vagy hologramját a kéz sugarával, majd koppintson és tartsa lenyomva a légi koppintást.
- **Nyissa meg a helyi menüket.** A helyi menük megnyitásához koppintson a légi koppintással és tartsa lenyomva a kéz sugarával.

## <a name="start-gesture"></a>Kézmozdulat elindítani

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]

A Start kézmozdulat megnyitja a **Start menü.**  A Start kézmozdulat végrehajtásához tartsa a kézmozdulatot az Ön felé néző kézmozdulattal. Egy Indítás ikon jelenik **meg** a belső burkolat felett. Koppintson erre az ikonra a másik kézzel.  A Start menü a következő hely **nyílik meg:**.

> [!TIP]
>
> - A Start kézmozdulatot addig használhatja, amíg a kézkövetési kereten belül van.  Nem kell lenézni a Start ikonra. Tartsa alacsonyan és kényelmesen a fogát, és keresse meg azt az irányt, ahol a Start menü meg kell nyitnia.
> - Ha a Start menü nem a kívánt helyen nyílt meg, egyszerűen mozgassa a fejét az áthelyezéshez.
> - Ha nem tudja be olvasni a kisebb szöveget a Start menü, lépjen közelebb hozzá a megnyitása után.
> - Ha a kéz kissé el van vava a keret oldalára, akkor is megtekintheti a Start menü a belső vázra koppintva, még akkor is, ha nem látja az ikont.

![A Start ikont és a Start kézmozdulatot bemutató kép](./images/hololens-2-start-gesture.png)

A **Start menü** a Start kézmozdulatot, ha a Start menü meg van nyitva.  A következőt is meg Start menü a "Bezárás" szót.

### <a name="one-handed-start-gesture"></a>Egy kézzel használható indítási kézmozdulat

> [!IMPORTANT]
> Az egy kézzel használható Indítás kézmozdulat a következő:
>
> 1. Frissítenie kell a 2019. novemberi frissítésre (18363.1039-es build) vagy újabb verzióra.
> 1. A szemkövetési funkció megfelelő működését az eszközön kell berakni. Ha nem lát a Start ikon körüli pályára ható pontokat, amikor ránéz, a [tekintete](https://docs.microsoft.com/hololens/hololens-calibration#calibrating-your-hololens-2) nem lesz beállítva az eszközön.

A Start kézmozdulatot egyetlen kézzel is végrehajthatja. Ehhez tartsa fel a kezében az álló labdáját, és nézze meg a belső burkolat start **(Indítás)** ikonját. **Miközben a ikont tartja** szem előtt, csippentse össze a hüvelykujját és az indexelő ujjlenyomatát.

![A Start ikont és az egy kézzel használható indítási kézmozdulatot bemutató kép](./images/hololens-2-start-alternative.png)

## <a name="start-menu-mixed-reality-home-and-apps"></a>Start menü, vegyes valóság kezdőlapja és alkalmazásai

Készen áll mindezen kéz-interakciók tesztelésére?!

A telepített alkalmazásokat a [](holographic-home.md) Start menü a holoLenshez a következő [Microsoft Store.](holographic-store-apps.md)

Ahogy a Windows rendszerű számítógépek mindig az asztalon kezdik el a felhasználói élményt, a HoloLens is mindig a vegyes **valóságú otthonban** indul, ha be van kapcsolva.  A Start menü alkalmazásablakokat, alkalmazásindítókat és 3D-tartalmakat nyithat meg és helyezzen el a vegyes valóság kezdőlapján. A HoloLens meg fogja emlékezni a fizikai térben való elhelyezésüket.

Nyissa meg **a Start menü,** majd válassza a **Beállítások alkalmazás** csempét. Megnyílik egy alkalmazásablak az Ön előtt.

A Beállítások egy példa egy 2D-s alkalmazásablakot használó **HoloLens-alkalmazásra.**  Nagyon hasonlít a PC-n elérhető Windows-alkalmazásokhoz.

Most ismét megnyithatja a **Start menü,** és kiválaszthatja a **Tippek alkalmazás csempéjét.** Az alkalmazás **3D-s** alkalmazásindítója megjelenik az Ön előtt. Az alkalmazás megnyitásához válassza a  lejátszás gombot a indítón.

A Tippek egy példa egy modern **alkalmazásra.** A modern alkalmazások elhoznak a vegyes valóság otthonról, amikor az fut, és az lesz az egyetlen alkalmazás, amit lát.  A kilépéshez fel kell hoznia a Start menü, és az alul található **Mixed Reality kezdőlap** gombot kell választania.

### <a name="power-menu-from-start"></a>Power menu from Start

Egy új menü, amely lehetővé teszi, hogy a felhasználó kijelentkeztetje, leállítsa és újraindítsa az eszközt. A HoloLens-kezdőképernyő jelzi, hogy mikor érhető el rendszerfrissítés.

#### <a name="how-to-use"></a>Használat

1. Nyissa meg a HoloLens-kezdőképernyő [a Start](hololens2-basic-usage.md#start-gesture) kézmozdulattal, vagy mondja ki a "Go to Start" (Ugrás az indításhoz) gombra.

2. Figyelje meg a felhasználói profil képe melletti három pont ikont (...):

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Válassza ki a felhasználói profil képét a saját kezűleg vagy a "Power" hangparancs használatával.

4. Megjelenik egy menü, amely az eszköz kijelentkeztet, újraindítható vagy leállítható beállításait tartalmaz:

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Válassza ki a menüelemet a HoloLens kijelentkeztetésével, újraindításával vagy leállítával. Előfordulhat, hogy a Kijelentkezás lehetőség nem érhető el, ha az eszköz egyetlen [Microsoft-fiókhoz (MSA)](hololens-identity.md)vagy helyi fiókhoz van beállítva.

6. Zárja be a menüt máshová való érintéssel, vagy zárja be Start menü a Start kézmozdulattal.

[Itt további információt olvashat a Start menü](holographic-home.md) vegyes valóság kezdőlapról, beleértve az alkalmazások HoloLens 2-ben való használatát és kezelését.

## <a name="move-resize-and-rotate-holograms"></a>Hologramok áthelyezése, átméretezése és elforgatása

A vegyes valóságú otthonok alkalmazásablakai és 3D-objektumai kéz-, kéz sugár- és hangparancsokkal áthelyezhetők, átméretezhetők és elforgathatóak.

### <a name="moving-holograms"></a>Hologramok mozgatva

Helyezzen át egy hologramot vagy alkalmazást az alábbi lépésekkel:

1. Ragadja meg a hologramot a hologramon a mutató-ujjlenyomat és -ujjlenyomat csippentésével, vagy a kézzel lefelé, majd zárja be a hátát.  Ragadjon meg egy 3D hologramot bárhol a kék határolókereten belül.  Alkalmazásablakhoz ragadja meg annak címsorát.
1. Anélkül, hogy el kellene hagynia, mozgassa a kezében a hologramot. Ha így mozgat egy alkalmazásablakot, az alkalmazás ablaka automatikusan arccal áll szemben a mozgása közben, így könnyebben használhatja az új pozícióját.  
1. Engedje el az ujját, hogy eltoldja.

### <a name="resizing-holograms"></a>Hologramok átméretezése

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3ZYIb]

A 3D hologramok és alkalmazásablakok sarkában megjelenő átméretezési fogópontokat fogja meg és használja az átméretezéshez. 

Az alkalmazásablakok ezen a módon való átméretezésekor az ablak tartalmának mérete ennek megfelelően nő, és könnyebben olvashatóvá válik.

Ha át szeretné méretezni az  alkalmazásablakot úgy, hogy több tartalom jelenjen meg az ablakban, használja az alkalmazásablak oldalán és alsó szélén található átméretezési fogópontokat.

Az Öntől távolabbi hologramok átméretezésének két módja van. A hologram két sarkát is megragadhatja, vagy használhatja az átméretezési vezérlőket.

### <a name="rotating-holograms"></a>Rotációs hologramok

3D hologramok esetén ragadja meg és használja a határolókeret függőleges szélein megjelenő forgó fogópontokat.

Alkalmazásablakok esetén az alkalmazásablakok áthelyezésének hatására az alkalmazás automatikusan elforgatódik, és arccal jelenik meg.

Egy 3D hologramot vagy alkalmazásablakot mindkét kézzel **(vagy** kézzel sugár) is foghat egyszerre, majd:

- A hologram átméretezése érdekében helyezze közelebb vagy távolról a kézzel.
- A hologram elforgatása érdekében mozgassa közelebbről és közelebbről a kézzel a törzsét.

### <a name="follow-me-stop-following"></a>Kövessen, és ne kövesse tovább

A hologramok és az alkalmazásablakok ott maradnak, ahová a világba helyezte őket.  Ez nem mindig kényelmes, ha mozgásban kell lennie, és azt szeretné, hogy az alkalmazás látható maradjon. Ha azt kéri egy alkalmazástól,  hogy kezdjen el vagy ne kövessen, válassza az alkalmazás ablakának jobb felső sarkában (a Bezárás gomb mellett) a Követés **gombra** kattintva.  A következő alkalmazásablak egy modern alkalmazásba is beemelődhet.

## <a name="use-hololens-with-your-voice"></a>A HoloLens használata a hangjával

A hangjával a legtöbb olyan dolgot is meg tudja tenni, mint a HoloLensen, például egy gyors fényképen vagy egy alkalmazás megnyitásán.

| Cél | Mondja el ezt |
| - | - |
| A Start menü megnyitása | "Ugrás az indításhoz" |
| Válassza ezt: | A tekintet kurzorának felfelé mozgatásához mondja a "select" (kijelölés) lehetőséget. Ezután fordítsa el a fejet, hogy a kurzort a kijelölni kívánt dolog fölé helyezze, és mondja ki ismét a "select" (kijelölés) lehetőséget. |
| Az elérhető beszédparancsok | "Mit mondjak?" |

 [További hangparancsok és beszédhasználati módok a HoloLensben](hololens-cortana.md)

## <a name="swipe-to-type"></a>Pöccintéssel gépeléssel

Egyes ügyfelek gyorsabban "gépelnek" a virtuális billentyűzeten a begépelni kívánt szó alakjának megformálása által. A [Windows Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójával mostantól pöccintsen egyszerre egy szót úgy, hogy a holografikus billentyűzet síkján végigadja az ujjlenyomata hegyét, elforgatja a szó alakját, majd a billentyűzet síkján az ujjlenyomata hegyét elboríthatja. Pöccintéssel anélkül pöccinthet a szavak után, hogy le kellene nyomni a szóközt, ha a szavak között eltávolítja az ujját a billentyűzetről. A funkció akkor működik, ha pöccintéssel követi az ujját a billentyűzeten.

Vegye figyelembe, hogy ez a funkció a holografikus billentyűzet természetéből adódóan nem mindig tud az ujjlenyomatával szembeni ellenállást használni és elsajátítani (ellentétben a mobiltelefonos kijelzővel). Ezt a funkciót nyilvános kiadásra értékeljük, ezért fontos visszajelzése; Ha hasznosnak találja a funkciót, vagy pozitív visszajelzést szeretne küldeni, kérjük, lépjen velünk velünk a [Visszajelzési központ.](hololens-feedback.md)

## <a name="next-steps"></a>Következő lépések

Gratulálunk! Készen áll a HoloLens 2 használatára!

Most már konfigurálhatja a HoloLens 2-t az igényeinek megfelelően.  Az egyéb lehetőségek, amelyekre szükség lehet, az alábbiak:

- [Bluetooth-eszközök, például egér és billentyűzet csatlakoztatása](hololens-connect-devices.md)
- [Alkalmazások telepítése az áruházból](holographic-store-apps.md)
- [A HoloLens megosztása másokkal](hololens-multiple-users.md)

> [!TIP]
> Próbálja ki [a Hologramok tervezése](https://www.microsoft.com/p/designing-holograms/9nxwnjklrzwd?rtc=1&activetab=pivot:overviewtab) alkalmazást.

Ha Ön rendszergazda, tekintse [](hololens-requirements.md) át a Gyakori üzembehelyezések című témakört, amely segítséget kér a HoloLens 2 a szervezetben való üzembe helyezéséhez.