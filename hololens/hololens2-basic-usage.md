---
title: Tájékozódás a HoloLens 2-ben
description: Fedezze fel a vegyes valóságot, és ismerkedés azzal az útmutatóval, hogyan használhatja HoloLens 2 eszközt a saját kezűleg.
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
ms.openlocfilehash: cf3770dd55498dbe98abf88d002247646e4db9be
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427271"
---
# <a name="getting-around-hololens-2"></a>Tájékozódás a HoloLens 2-ben

Készen áll a hologramok világának felfedezésére?

Ez az útmutató a következő bevezetőt biztosítja:

- Vegyes valóság interakciója
- A 2. HoloLens hologramok használata a saját HoloLens hangjával
- Navigálás Windows 10 HoloLens (Windows Holographic)

## <a name="discover-mixed-reality"></a>Vegyes valóság felfedezése

A HoloLens a hologramok a fizikai környezettel ötvözik a digitális világot, hogy úgy nézzenek ki és hangzanak, mintha a világ részei lenne. Még ha hologramok is vannak a közelben, mindig láthatja a környezetet, szabadon mozoghat, és interakcióba léphet emberekkel és objektumokkal. Ezt a élményt "vegyes valóságnak" hívjuk.

A holografikus képkockák olyan pozícióba ékezetesek, ahol a tekintete a legérzékenyebb a részletekre, a átlátó objektívek pedig tisztán hagyják a periférialátást. A térbeli hangokkal a hologramokat akkor is figyelheti, ha az Ön mögött van. És mivel HoloLens a fizikai környezetet, hologramokat is helyezzen valós objektumokra, például táblákra és falakra.

A HoloLens sokban hasonló az intelligens telefonnal való használathoz. A kézzel holografikus ablakokat, menüket és gombokat is megérinthet és kezelhet.  

Ha már ismeri ezeket az alapszintű interakciókat, a HoloLens el a problémákat.

> [!TIP]
> Ha jelenleg HoloLens van, a **Tippek** alkalmazás literális gyakorlati oktatóanyagokat biztosít a felhasználókkal való HoloLens.  
> Használja az indítási kézmozdulatot a **Start menüre,** vagy mondja ki a "Go to Start" (Ugrás az indításhoz) lehetőséget, és válassza a **Tippek.**

## <a name="the-hand-tracking-frame"></a>A kézkövetési képkocka

HoloLens rendelkezik olyan érzékelőkkel, amelyek néhány lábat látnak Bármelyik oldalon. Ha a kézhasználatot használja, akkor a kereten belül kell tartania őket, különben HoloLens nem fogják látni őket. A képkocka azonban mozgásban van.  

![Kép a HoloLens-követési képkockáról.](./images/hololens-2-gesture-frame.png)

## <a name="touch-holograms-near-you"></a>Érintési hologramok a közelben

Ha egy hologram van a közelében, közelről vigye a kézzel, és egy fehér körnek kell megjelennie az indexelőavacsa csúcsán.  Ez az **érintéses kurzor** segít a hologramok precíz érintésében és a vele való interakcióban. Ha **kijelöl valamit,** egyszerűen **koppintson** rá az érintéses kurzorral. **A** tartalmat **úgy görgetheti,** hogy az ujjlenyomatával csúsztat a tartalom felszínén, pont úgy, mint egy érintőképernyőn.

Ha **egy** hologramot fog  a közelében, csippentse össze a hüvelyk- és **index-ujjlenyomatát** a hologramon, és tartsa lenyomva. Hogy engedjen el, engedje el az étkét. Ezzel a **kézmozdulattal** mozgathatja, átméretezheti és elforgathatja a 3D-s objektumokat és alkalmazásablakokat a vegyes valóság kezdőlapon.

A helyi menüt úgy hozhatja meg, mint az alkalmazáscsempéken az Start menü **koppintson** és tartsa lenyomva az érintőképernyőn láthatóakhoz hasonlót.

## <a name="use-hand-ray-for-holograms-out-of-reach"></a>A kéz sugarának használata a hologramok nem elérhető eléréséhez

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3ZOum]

Ha nincsenek hologramok a kéz közelében, az **érintéses** kurzor automatikusan el fog rejteni, és a kéz sugárai megjelennek.  A kézi sugárokkal távolról kommunikálhat a hologramokkal.

> [!TIP]
> Ha zavarónak találja a kéz sugarakat, elrejtheti őket az "Hide hand rays" (A kéz sugárának elrejtése) szóval. Hogy újra megjelennek, mondja ki a "Show hand rays" (Show hand rays) szót.

### <a name="select-using-air-tap"></a>Kijelölés légi koppintással

Ha valamit ki kell választania a **kézi sugár használatával,** kövesse az alábbi lépéseket:

1. Az elem megcélzott elemét egy, a telefonról származó kézbefedő sugár segítségével adja meg. Nem kell felemni a teljes karot, alacsonyan és kényelmesen tarthatja a könyökét.
1. Irányítsa fel az indexaját közvetlenül a felső határ felé.
1. A légi **koppintás** kézmozdulatának végrehajtásához csippentse össze a hüvelyk- és indexaját, majd engedje el őket gyorsan.

   ![Légi koppintásos kézmozdulat animációja.](./images/hololens-air-tap.gif)

### <a name="grab-using-air-tap-and-hold"></a>Fogás légi koppintással és tartsa lenyomva

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxnh]

Ha egy hologramot vagy görgetőalkalmazás-tartalmat fog a kéz sugár **használatával,** kezdjen egy légi koppintással, de ne szabadodjon ki, hanem tartsa együtt az arcot.

A **légi koppintással és** lenyomva nyomással végezze el a következő műveleteket a kézi sugár használatával:

- **Görgessen.** Az alkalmazásablak tartalmának görgetéshez koppintson a levegőre, és tartsa lenyomva a tartalmat, majd mozgassa felfelé és lefelé vagy oldalra a kézzel sugárját.
- Fogja meg a **et.** Ha egy alkalmazásablakot vagy hologramot meg kell ragadni, célozza meg az alkalmazás címsorát vagy hologramját a kézbefedő sugárral, majd koppintson és tartsa lenyomva.
- **Nyissa meg a helyi menüket.** A helyi menük megnyitásához légi koppintással és kézbenyomással tartsa lenyomva a sugarat.

## <a name="start-gesture"></a>Kézmozdulat elindítani

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]

A Start kézmozdulat megnyitja a **Start menü.**  A Start kézmozdulat végrehajtásához tartsa a kézmozdulatát az Ön felé néző kezében. Megjelenik egy **Indítás ikon** a belső belső burkolat felett. Koppintson erre az ikonra a másik kézzel.  A Start menü megnyílik **ott, ahol a következőt keresi:**.

> [!TIP]
>
> - A Start kézmozdulatot addig használhatja, amíg a kézkövetési kereten belül van.  Nem kell lenézni a Start ikonra. Tartsa alacsonyan és kényelmesen a könyökét, és nézze meg, hol szeretné megnyitni Start menü szemeket.
> - Ha a Start menü nem a kívánt helyen nyílt meg, egyszerűen mozgassa a fejét az áthelyezéshez.
> - Ha nem tudja be olvasni a kisebb szöveget a Start menü, lépjen közelebb hozzá a megnyitása után.
> - Ha a kéz kis mértékben el van tért a keret oldalára, akkor is megtekintheti a Start menü-t a belső burkolatra koppintva, még akkor is, ha nem látja az ikont.

![A Start ikont és a Start kézmozdulatot bemutató kép.](./images/hololens-2-start-gesture.png)

A **Start menü** a Start kézmozdulattal zárhatja be, ha a Start menü meg van nyitva.  A következőt is meg Start menü a "Close" (Bezárás) szót.

### <a name="one-handed-start-gesture"></a>Egy egy szándékú indítási kézmozdulat

> [!IMPORTANT]
> Az egy szándékú Indítás kézmozdulat a következő:
>
> 1. Frissítenie kell a 2019. novemberi frissítésre (18363.1039-es build) vagy újabb verzióra.
> 1. A szemkövetés megfelelő működését az eszközön kell berakni. Ha nem lát a Start ikon körüli pályára ható pontokat, amikor ránéz, a [tekintete](/hololens/hololens-calibration#calibrating-your-hololens-2) nem lesz beállítva az eszközön.

A Start kézmozdulatot egyetlen kézzel is végrehajthatja. Ehhez tartsa a kézét az Ön felé néző kezében, és nézze meg a belső burkolaton **lévő** Start (Indítás) ikont. **Miközben a ikonon tartja a szemét,** csippentse össze a hüvelyk- és index-ujjlenyomatát.

![A Start ikont és az egy szándékú indítási kézmozdulatot bemutató kép.](./images/hololens-2-start-alternative.png)

## <a name="start-menu-mixed-reality-home-and-apps"></a>Start menü, vegyes valóság kezdőlapja és alkalmazásai

Készen áll arra, hogy ezeket a kéz-interakciókat tesztelje?

A telepített alkalmazásokat a [](holographic-home.md) Start menü a következő HoloLens találhatja [meg Microsoft Store:](holographic-store-apps.md).

Ahogy Windows gép mindig az asztalon kezdi a felhasználói élményt, HoloLens mindig a vegyes valóság **kezdőlapon** indul, amikor be van kapcsolva.  A Start menü alkalmazásablakokat, alkalmazásindítókat és 3D-tartalmakat nyithat meg és helyezzen el a vegyes valóság kezdőlapján. A fizikai térben való elhelyezésüket a HoloLens.

Nyissa meg **Start menü** alkalmazást, majd válassza **Gépház** alkalmazás csempéjét. Megnyílik egy alkalmazásablak az Ön előtt.

Gépház egy 2D-s HoloLens használó **alkalmazás.**  Nagyon hasonlít a PC-n Windows alkalmazáshoz.

Most újra megnyithatja a **Start menü,** és kiválaszthatja **a Tippek** alkalmazás csempéjét. Az alkalmazás **3D-s** alkalmazásindítója megjelenik az Ön előtt. Az alkalmazás megnyitásához válassza a  lejátszás gombot a indítón.

Tippek egy példa egy modern **alkalmazásra.** A modern alkalmazások elhoznak a vegyes valóságból, amikor az fut, és az lesz az egyetlen alkalmazás, amit lát.  A kilépéshez meg kell Start menü a mixed **reality kezdőlap** gombját.

### <a name="power-menu-from-start"></a>A Power menü a Start menüből

Új menü, amely lehetővé teszi, hogy a felhasználó kijelentkeztetje, leállítsa és újraindítsa az eszközt. A rendszerfrissítés HoloLens kezdőképernyő mutatója.

#### <a name="how-to-use"></a>Használat

1. Nyissa meg HoloLens kezdőképernyő a [Start kézmozdulattal,](hololens2-basic-usage.md#start-gesture) vagy mondja ki a "Go to Start" (Ugrás az indításhoz) gombra.

2. Figyelje meg a felhasználói profil képe melletti három pont ikont (...):

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Válassza ki a felhasználói profil képét a saját kezűleg vagy a "Power" hangparancs használatával.

4. Megjelenik egy menü, amely az eszköz kijelentkeztet, újraindítható vagy leállítható beállításait tartalmaz:

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Válassza ki a menüelemet, hogy kijelentkezjön, újraindítsa vagy leállítsa HoloLens. Előfordulhat, hogy a Kijelentkezás lehetőség nem érhető el, ha az eszköz egyetlen [Microsoft-fiókhoz (MSA)](hololens-identity.md)vagy helyi fiókhoz van beállítva.

6. Zárja be a menüt úgy, hogy máshová Start menü a Start kézmozdulattal.

[Itt további információt olvashat a Start menü](holographic-home.md) vegyes valóság kezdőlapról, beleértve az alkalmazások használatát és kezelését a 2. HoloLens oldalon.

## <a name="move-resize-and-rotate-holograms"></a>Hologramok áthelyezése, átméretezése és elforgatása

A vegyes valóságú otthonban az alkalmazásablakokat és a 3D-objektumokat kéz-, sugár- és hangparancsokkal mozgathatja, átméretezheti és elforgathatja.

### <a name="moving-holograms"></a>Hologramok mozgatás

Helyezzen át egy hologramot vagy alkalmazást az alábbi lépésekkel:

1. Ragadja meg a hologramot a hologramra rátpintva az indexaját és a ujjlenyomatát, vagy a kézzel lefelé, majd zárja be a kezében.  Ragadjon meg egy 3D hologramot bárhol a kék határolókereten belül.  Alkalmazásablakhoz ragadja meg annak címsorát.
1. Anélkül, hogy el kellene hagynia a hologramot, mozgassa a kézzel a hologramot. Ha így mozgat egy alkalmazásablakot, az alkalmazás ablaka automatikusan arcot vált a mozgása közben, így könnyebben használható az új pozíciójában.  
1. Engedje el az ujját, hogy eltenjük.

### <a name="resizing-holograms"></a>Hologramok átméretezése

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3ZYIb]

A 3D hologramok és az alkalmazásablakok sarkában megjelenő átméretezési fogópontokat fogja meg és használja az átméretezéshez. 

Az alkalmazásablakok ezen a módon való átméretezésekor az ablak tartalma ennek megfelelően nő, és könnyebben olvashatóvá válik.

Ha át szeretne méretezni egy  alkalmazásablakot úgy, hogy több tartalom jelenjen meg az ablakban, használja az alkalmazásablak oldalán és alsó szélein található átméretezési fogópontokat.

Az Öntől távolabbi hologramok átméretezésének két módja van. A hologram két sarkát is megragadhatja, vagy használhatja az átméretezés vezérlőit.

### <a name="rotating-holograms"></a>Rotációs hologramok

3D hologramok esetén ragadja meg és használja a határolókeret függőleges szélein megjelenő elforgatás fogópontokat.

Alkalmazásablakok esetén az alkalmazásablakok áthelyezésének hatására az alkalmazás automatikusan elfordul, és ön előtt jelenik meg.

Egy 3D hologramot vagy alkalmazásablakot mindkét kézzel **(vagy** kézzel) egyszerre is megragadhat, majd:

- Helyezze közelebb egymáshoz vagy távolról a hologram átméretezését.
- A hologram elforgatása érdekében mozgassa közelebbről és közelebbről a kézzel a törzsét.

### <a name="follow-me-stop-following"></a>Kövessen, és ne kövesse tovább

Hologramok alkalmazásablakok és alkalmazásablakok ott maradnak, ahová a világba helyezte őket.  Ez nem mindig kényelmes, ha mozgásban kell lennie, és azt szeretné, hogy az alkalmazás látható maradjon. Ha meg kell kérnie egy alkalmazást, hogy kezdje el vagy állítsa le a követést, válassza az alkalmazás ablakának jobb felső sarkában (a Bezárás gomb mellett) a Követés **gombra** kattintva.   Az ezt követő alkalmazásablakok egy modern alkalmazásba is beemelődnek.

## <a name="use-hololens-with-your-voice"></a>A HoloLens használata a hangjával

A hangjával a legtöbb olyan dolgot el tudja tenni, mint a két HoloLens, például egy gyors fényképen vagy egy alkalmazás megnyitásán.

| Cél | Mondja el ezt |
| - | - |
| A Start menü megnyitása | "Ugrás az indításhoz" |
| Válassza ezt: | A tekintet kurzorának felfelé mozgatásához mondja a "select" (kijelölés) lehetőséget. Ezután fordítsa el a fejet, hogy a kurzort a kijelölni kívánt dolog fölé helyezze, és mondja ki újra a "select" (kijelölés) lehetőséget. |
| Az elérhető beszédparancsok | "Mit mondjak?" |

 [További hangparancsok és beszédfelismerési módszerek HoloLens](hololens-cortana.md)

## <a name="swipe-to-type"></a>Pöccintés a begépelhez

Egyes ügyfelek gyorsabban "gépelnek" a virtuális billentyűzeten a begépelni kívánt szó alakjának megformálása által. A [Windows Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójával mostantól pöccintsen egyszerre egy szót az ujjlenyomata hegyének a holografikus billentyűzet síkján való áthúzásával, a szó alakjának áthúzásával, majd az ujjlenyomata csúcsának a billentyűzetsíkról való eltolásával. Pöccintsen a követő szavak között anélkül, hogy le kellene nyomni a szóközt úgy, hogy a szavak között eltávolítja az ujját a billentyűzetről. A funkció akkor működik, ha pöccintés nyomát látja az ujjlenyomata billentyűzeten való mozgása után.

Vegye figyelembe, hogy ez a funkció a holografikus billentyűzet természetéből adódóan nem mindig tud az ujjlenyomatával szemben ellenállást használni (ellentétben a mobiltelefonos kijelzővel). Ezt a funkciót nyilvános kiadásra értékeljük, ezért fontos a visszajelzése; ha hasznosnak találja a funkciót, vagy pozitív visszajelzést szeretne küldeni, kérjük, forduljon hozzánk a [Visszajelzési központ.](hololens-feedback.md)

## <a name="next-steps"></a>Következő lépések

Gratulálunk! Készen áll a 2. HoloLens használatára!

Most már konfigurálhatja a 2 HoloLens-es konfigurációt az igényeinek megfelelően.  A következő lehetőségeket is kipróbálhatja:

- [Bluetooth-eszközök, például egér és billentyűzet csatlakoztatása](hololens-connect-devices.md)
- [Alkalmazások telepítése az áruházból](holographic-store-apps.md)
- [A HoloLens megosztása másokkal](hololens-multiple-users.md)

> [!TIP]
> Próbálja ki [a Hologramok](https://www.microsoft.com/p/designing-holograms/9nxwnjklrzwd?rtc=1&activetab=pivot:overviewtab) alkalmazást.

Ha Ön rendszergazda, tekintse [](hololens-requirements.md) át az általános telepítési forgatókönyveket, ha segítségre van szüksége a 2. HoloLens üzembe helyezéséhez.