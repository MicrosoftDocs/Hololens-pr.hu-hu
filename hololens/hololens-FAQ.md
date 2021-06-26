---
title: HoloLens-eszközökkel és hologramokkal kapcsolatos gyakori kérdések
description: Kérdése van a HoloLens-sel vagy a hologramokkal való interakcióval kapcsolatban?  Ez a cikk gyors választ és további forrásokat tartalmaz.
keywords: hololens, gyik, ismert probléma, súgó
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924026"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Hologramok és interakciók hibaelhárítása

Ez a cikk a hologramok elhelyezésével, a szóközök alkalmazásával és a hologramokkal kapcsolatos jelentéskészítéssel kapcsolatos problémákat hárítja el.

Ha problémái vannak, mindig győződjön meg a következőről:
- Próbálja [meg újraindítani,](hololens-restart-recover.md) hogy lássa, ez megoldja-e a problémát.
- A hibaelhárítás előtt ellenőrizze, hogy a HoloLens fel van-e töltve [(legalább](hololens2-charging.md) egy óra után). 


A visszajelzési alkalmazással küldje el nekünk a problémára vonatkozó információkat. A Visszajelzés alkalmazás a [ **Start menüben** található.](holographic-home.md) 

A HoloLens elhasználódására vonatkozó tippekért lásd: [Adjust Fit](hololens2-setup.md#adjust-fit).

<a id="list"></a>
- [Új szóközöket nem lehet létrehozni](#new-spaces-cant-be-created)
- [A szóközök nem azonosíthatók vagy tölthetők be](#spaces-cant-be-identified-or-loaded)
- [Hogyan az összes szóközt?](#how-do-i-delete-all-spaces)
- [A hologramok nem néznek ki jól, vagy mozognak](#holograms-dont-look-right-or-are-moving-around)
- ["A hely megkeresása" üzenet](#finding-your-space-message)
- [A várt hologramok nem ömlnek a saját térembe](#expected-holograms-arent-showing-in-my-space)
- [Nem lehet hologramokat elhelyezni vagy korábban elhelyezett hologramokat látni](#cant-place-holograms-or-see-previously-placed-holograms)
- [A hologramok eltűnnek vagy be vannak ékesedve más hologramokbe vagy objektumokba](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologramok jelennek meg a fal másik oldalán](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Miután elhelyez egy hologramot a falon, úgy tűnik, hogy lebegőg](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Az alkalmazások túl közel jelennek meg az áthelyezés után](#apps-appear-too-close-after-moving-them)
- [Instabil vagy nem használt hologramokkal kapcsolatos problémák jelentése](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Új szóközöket nem lehet létrehozni

A legvalószínűbb probléma az, hogy kevés a tárhely. [Szabadítson fel lemezterületet,](hololens-troubleshooting.md#low-disk-space-error) majd próbálja újra.

[Vissza a listához](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>A szóközök nem azonosíthatók vagy tölthetők be

Ha a HoloLens nem tudja automatikusan azonosítani és betölteni a helyet, ellenőrizze a következő tényezőket:

- Győződjön meg arról, hogy csatlakozott a Wi-Fi
- Győződjön meg arról, hogy a helyiségben sok fény található
- Győződjön meg arról, hogy nem történt jelentős változás a környezetben.

A szóközöket manuálisan is betöltheti, vagy kezelheti a szóközöket a **Beállítások**  >  **Rendszerterek**  >  **területről.**

[Vissza a listához](#list)

## <a name="how-do-i-delete-all-spaces"></a>Hogyan az összes szóközt?

*Hamarosan érkezik*

[Vissza a listához](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>A hologramok nem néznek ki jól, vagy mozognak

Ha a hologramok nem néznek ki jól (például jittery vagy shaky, vagy fekete javításokat lát ezeken), próbálja ki az alábbi javítások valamelyikét:

- [Megtisztítja az eszköz vizorát,](hololens1-hardware.md#care-and-cleaning) és győződjön meg arról, hogy semmi sem akadályozza az érzékelőket.
- Győződjön meg arról, hogy egy jól kigyűjtt helyiségben van, ahol nincs túl sok közvetlen semmi.
- Próbálja ki, hogy a környezetét járja, hogy a HoloLens jobban beolvassa őket.
- Ha sok hologramot helyezett el, próbáljon meg eltávolítani néhányat.

Ha továbbra is problémákat tapasztal, próbálja meg elfutni a Indító alkalmazás futtatásával. Ez az alkalmazás a HoloLenst arra használja, hogy a hologramok a lehető legjobban kinézhessenek. Ehhez a Beállítások   >  **rendszer-segédprogramok**  >  **gombra kell átmenni.** A **Az Etikátás** alatt válassza a **Open És a 2012 lehetőséget.**

[Vissza a listához](#list)

## <a name="finding-your-space-message"></a>"A hely megkeresása" üzenet

Amikor HoloLens egy teret tanul vagy tölt be, egy rövid üzenet jelenik meg, amely a következőt mondja: "A hely keresése". Ha ez az üzenet néhány másodpercnél tovább jelenik meg, egy másik üzenet jelenik meg a képernyő alatt Start menü a következő szöveg jelenik meg: "Still looking for your space".

Ezek az üzenetek azt jelentik, hogy a HoloLens nem leképezi a tárhelyet. Ebben az esetben megnyithat alkalmazásokat, de nem tud hologramokat a környezetében.

Ha gyakran látja ezeket az üzeneteket, próbálkozzon az alábbi javításokkal:

- Győződjön meg arról, hogy egy jól kigyűjtt helyiségben van, ahol nincs túl sok közvetlen semmi.
- Győződjön meg arról, hogy az eszköz vizora tiszta. [Ismerje meg, hogyan tisztítható meg a vizor.](hololens1-hardware.md#care-and-cleaning)
- Győződjön meg arról, hogy erős Wi-Fi jellel. Ha olyan új környezetbe lép, amely nem rendelkezik Wi-Fi vagy gyenge Wi-Fi jellel, a HoloLens nem fogja megtalálni a teret. Ellenőrizze a Wi-Fi kapcsolatát a **Beállítások**  >  **Hálózati &amp; internet**  >  **Wi-Fi beállításnál.**
- Próbáljon lassabban haladni.

[Vissza a listához](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>A várt hologramok nem ömlnek a térben

Ha nem látja a elhelyezett hologramokat, vagy olyanokat lát, amelyekre nem számít, próbálkozzon az alábbi javításokkal:

- Kapcsolj be néhány világítást. A HoloLens jól kigyűjtt térben működik a legjobban.
- Távolítsa el a nem szükséges hologramokat a Beállítások  >  **Rendszer**  >  Hologramok Közeli  >  **hologramok eltávolítása lehetőséggel.** Ha szükséges, válassza az **Összes hologram eltávolítása lehetőséget.**

  > [!NOTE]
  > Ha a tér elrendezése vagy megvilágítása jelentősen megváltozik, előfordulhat, hogy az eszköz nem tudja azonosítani a helyet, és nem tudja mutatni a hologramokat.

[Vissza a listához](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Nem lehet hologramokat elhelyezni vagy korábban elhelyezett hologramokat látni

Ha a HoloLens nem tudja leképezni vagy betölteni a tárhelyet, korlátozott módba lép, és nem fog tudni hologramokat elhelyezni, illetve a elhelyezett hologramokat látni. Néhány dolog, amelyet érdemes kipróbálni:

- Győződjön meg arról, hogy a környezete elég világos, hogy a HoloLens lát és leképezni tudja a helyet.
- Álljon egy és három méter között, ahonnan a hologramot el akarja tenni.
- Ne helyezzen hologramokat fekete vagy tükröző felületekre.
- Győződjön meg arról, hogy egy hálózati Wi-Fi csatlakozik. Ha nem csatlakozik Wi-Fi-hez, a HoloLens nem tudja azonosítani és betölteni az ismert tárhelyet.
- Járja be a helyiségeket, hogy HoloLens újra meg tudja ásni a környezetet. A már beolvasott elemek vizsgálatának ellenőrzéshez koppintson a légi koppintással a térképes háló ábrának a felfedéséhez.
- Ha új területet kell létrehoznia, csatlakozzon a Wi-Fi-hez, majd indítsa újra a HoloLenst.
- Ha meg kell tudni, hogy a megfelelő terület aktív-e, vagy manuálisan be kell töltenie egy szóközt, kattintson a **Beállítások**  >  **Rendszerterek**  >  **elemre.**
- Ha a megfelelő terület van betöltve, és továbbra is problémákat tapasztal, az sérült lehet. A probléma megoldásához válassza ki a helyet, majd válassza az Eltávolítás **lehetőséget.** A terület eltávolítása után a HoloLens elkezdi leképezni a környezetet, és új teret létrehozni.

[Vissza a listához](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>A hologramok eltűnnek vagy be vannak ékesedve más hologramokbe vagy objektumokba

Ha túl közel kerül egy hologramhoz, az ideiglenesen eltűnik a hologram visszaállításához, csak lépjen &mdash; tovább. Ha több hologramot is közel helyezett egymáshoz, előfordulhat, hogy néhány eltűnik. Próbáljon meg eltávolítani néhányat.

A hologramokat más hologramok vagy objektumok, például a fal is blokkolhatja vagy be lehet fogni. Ha ez történik, próbálkozzon az alábbi javítások valamelyikével:

- Ha a hologram egy másik hologramban található, helyezze át a beékelt hologramot egy másik helyre. Ehhez válassza a **Beállítás** lehetőséget, majd koppintson a helyére, és tartsa lenyomva.
- Ha a hologram be van ékesedve egy falba, válassza a **Beállítás** lehetőséget, majd haladjon a fal felé, amíg meg nem jelenik a hologram. Koppintson és tartsa lenyomva, majd húzza előre és ki a hologramot a falról.
- Ha kézmozdulatokkal nem tudja áthelyezni a hologramot, a hangjával távolítsa el. Tekintsen a hologramra, majd mondja ki az "Eltávolítás" szót. Ezután nyissa meg újra a hologramot, és helyezze egy új helyre.

[Vissza a listához](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologramok jelennek meg a fal másik oldalán

Ha nagyon közel van egy falhoz, vagy ha a HoloLens még nem vizsgálta le a falat, a következő teremben is láthatja a hologramokat. A fal beolvasására álljon egy-három méter közé a faltól, és tekintsen rá.

Egy fekete vagy reflektív objektum (például egy fekete heverő vagy egy névtelen hűtő) a fal közelében problémákat okozhat, amikor HoloLens megpróbálja beolvasni a falat. Ilyen objektum esetén vizsgálja meg a fal másik oldalát.

[Vissza a listához](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Úgy tűnik, hogy miután elhelyez egy hologramot a falon, úgy tűnik, hogy lebegőg

Egy hologram, amely egy falra kerül, általában úgy tűnik, hogy körülbelül egy hüvelykre van a faltól. Ha úgy tűnik, hogy távol van, próbálkozzon az alábbi javításokkal:

- Ha hologramot ad egy falhoz, álljon a faltól egy és három méter közé, és közvetlenül a fal felé álljon.
- A térképes háló ábráját a falra koppintva légi koppintással fedje fel. Győződjön meg arról, hogy a háló igazodik a falhoz. Ha nem így van, távolítsa el a hologramot, ismét a falon, majd próbálkozzon újra.
- Ha a probléma továbbra is fennáll, futtassa a Tanúsítvány alkalmazást. Ezt a Settings   >  System Utilities **(Beállítások rendszer segédprogramjai)**  >  **lapon találja.**

[Vissza a listához](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Az alkalmazások túl közel jelennek meg az áthelyezés után

Próbáljon meg körbejárást, és vizsgálja meg azt a területet, ahová az alkalmazást helyezi, hogy a HoloLens különböző szögekből vizsgálja a területet. [Az eszköz vizorának tisztítása](hololens1-hardware.md#care-and-cleaning) is segíthet.

[Vissza a listához](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Instabil vagy nem használt hologramokkal kapcsolatos problémák jelentése
 
1. Rögzítsen egy Vegyes valóság rögzítése [a](holographic-photos-and-videos.md#capture-a-mixed-reality-video) problémáról. Ezt a videót később feltöltheti a Visszajelzési központ fájlként.  
1. Engedélyezze a teljes telemetriát a **Beállítások** alkalmazás -> **Privacy** Diagnostics & visszajelzéssel, és a Választható diagnosztikai adatok alatt ellenőrizze, hogy a váltógomb Be  ->   van-e **állítva** 
1. A legújabb hologramméret- és stabilitási javításokat a [legújabb Windows Holographic OS-re (20H2 vagy újabb) frissítve.](hololens-release-notes.md#windows-holographic-version-20h2) A frissítés után hajtsa végre a következőket:
    1. Távolítsa el az összes hologramot a **Beállítások** alkalmazás ->   ->  **System Holograms** -> válassza az **Összes hologram** eltávolítása lehetőséget, és kezdje egy új térképpel.
    1. Hozzon létre egy új térképet a térről a HoloLens-nek bekenve, és körbe járva a helyiségben, és a tér összes területén és felszínén. Ezt 2–3 percig tegye meg.
    1. IPD-beszibráció végrehajtása. Ugrás a **Beállítások**  >  **rendszer-segédprogramok**  >  **lapra.** A **Felbesivatás** alatt válassza a **Open Egyedek lehetőséget.**
    1. Tesztelje újra a forgatókönyvet, és ellenőrizze, hogy továbbra is fennáll-e.
1. Ha a frissítés nem oldja meg a problémát, jelentsen be [egy Visszajelzési központ problémát.](hololens-feedback.md) A visszajelzés kitöltése után a  Megosztás gombbal létrehozhat egy könnyen megosztható hivatkozást, amely az ügyfélszolgálattal való kapcsolatfelvételkor küldhető el.

[Vissza a listához](#list)