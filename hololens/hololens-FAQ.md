---
title: Gyakori kérdések a HoloLens hologramokkal kapcsolatban
description: Kérdése van a hologramok HoloLens vagy kommunikációja ről?  Ez a cikk gyors választ és további forrásokat tartalmaz.
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032502"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Hologramok és interakciók hibaelhárítása

Ez a cikk a hologramok elhelyezésével, a szóközök alkalmazásával és a hologramokkal kapcsolatos jelentéskészítéssel kapcsolatos problémákat hárítja el.

Ha problémákba merült fel, győződjön meg a következőről:
- Próbálja [meg újraindítani,](hololens-restart-recover.md) hogy lássa, ez megoldja-e a problémát.
- A hibaelhárítás előtt ellenőrizze, hogy HoloLens díj fel van-e [számolva](hololens2-charging.md) (legalább egy óra után). 


A visszajelzési alkalmazással küldje el nekünk a problémára vonatkozó információkat. A Visszajelzés alkalmazást a [ **Start menüben** találja.](holographic-home.md) 

Tippek a saját HoloLens [elhasználódásához: Adjust Fit](hololens2-setup.md#adjust-fit).

<a id="list"></a>
- [Új szóközöket nem lehet létrehozni](#new-spaces-cant-be-created)
- [A szóközök nem azonosíthatók vagy tölthetők be](#spaces-cant-be-identified-or-loaded)
- [Hogyan összes szóközt?](#how-do-i-delete-all-spaces)
- [Hologramok nem néz ki jól, vagy mozog](#holograms-dont-look-right-or-are-moving-around)
- ["A hely megkeresve" üzenet](#finding-your-space-message)
- [A várt hologramok nem ömlnek a saját térembe](#expected-holograms-arent-showing-in-my-space)
- [Nem lehet hologramokat elhelyezni vagy a korábban elhelyezett hologramokat látni](#cant-place-holograms-or-see-previously-placed-holograms)
- [Hologramok eltűnnek, vagy más hologramba vagy objektumokba vannak bevetve](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologramok a fal másik oldalán jelennek meg](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Úgy tűnik, hogy miután elhelyez egy hologramot a falon, úgy tűnik, hogy lebegőg](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
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

A szóközöket manuálisan is betöltheti, vagy a System Spaces (Rendszerterek) **Gépház**  >    >  **kezelheti.**

[Vissza a listához](#list)

## <a name="how-do-i-delete-all-spaces"></a>Hogyan összes szóközt?

*Hamarosan érkezik*

[Vissza a listához](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Hologramok nem néz ki jól, vagy mozog

Ha a hologramok nem néznek ki jól (például jittery vagy shaky, vagy fekete javításokat lát ezeken), próbálja ki az alábbi javításokat:

- [Megtisztítja az eszköz vizorát,](hololens1-hardware.md#care-and-cleaning) és győződjön meg arról, hogy semmi sem blokkolja az érzékelőket.
- Győződjön meg arról, hogy egy jól begyújtott helyiségben van, ahol nincs túl sok közvetlen semmi.
- Próbálja ki a környezetet, és vizsgálja meg a környezetet, hogy HoloLens jobban beolvassa őket.
- Ha sok hologramot helyezett el, próbáljon meg eltávolítani néhányat.

Ha továbbra is problémákba merült fel, próbálja meg a Indítóalkalmazást futtatni. Ez az alkalmazás HoloLens csak azért, hogy a hologramok a lehető legjobban kinézhessenek. Ehhez a Rendszer-segédprogramok **Gépház**  >    >  **meg.** A **Felbesivatás** alatt válassza a **Open Egyedek lehetőséget.**

[Vissza a listához](#list)

## <a name="finding-your-space-message"></a>"A hely megkeresve" üzenet

Amikor HoloLens vagy helyet tölt be, egy rövid üzenet jelenik meg, amely a következőt mondja: "A hely megkeresve". Ha ez az üzenet néhány másodpercnél tovább jelenik meg, egy újabb üzenet jelenik meg a Start menü a "Still looking for your space" (Továbbra is a saját tárhelyet keresi) üzenet jelenik meg.

Ezek az üzenetek azt jelentik, HoloLens nem lehet leképezni a területet. Ebben az esetben megnyithat alkalmazásokat, de nem tud hologramokat a környezetében.

Ha gyakran látja ezeket az üzeneteket, próbálkozzon az alábbi javításokkal:

- Győződjön meg arról, hogy egy jól begyújtott helyiségben van, ahol nincs túl sok közvetlen semmi.
- Győződjön meg arról, hogy az eszköz vizora tiszta. [Ismerje meg, hogyan tisztítható meg a vizor.](hololens1-hardware.md#care-and-cleaning)
- Győződjön meg arról, hogy erős Wi-Fi jellel. Ha olyan új környezetbe lép, amely nem rendelkezik Wi-Fi gyenge Wi-Fi jellel, HoloLens nem fogja megtalálni a teret. Ellenőrizze a Wi-Fi kapcsolatát a **Gépház**  >  **&amp; Wi-Fi hálózatán.**  >  
- Próbáljon lassabban haladni.

[Vissza a listához](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>A várt hologramok nem ömlnek a saját térembe

Ha nem látja a elhelyezett hologramokat, vagy ha nem várt hologramokat lát, próbálkozzon az alábbi javításokkal:

- Kapcsolj be néhány világítást. HoloLens jól kis helyen működik a legjobban.
- Távolítsa el azokat a hologramokat, amelyekre nincs szüksége, ha a **Gépház** a Hologramok  >    >    >  **hologramok eltávolítása gombra.** Ha szükséges, válassza az **Összes hologram eltávolítása lehetőséget.**

  > [!NOTE]
  > Ha a tér elrendezése vagy megvilágítása jelentősen változik, előfordulhat, hogy az eszköz nem tudja azonosítani a tárhelyet, és nem tudja mutatni a hologramokat.

[Vissza a listához](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Nem lehet hologramokat elhelyezni vagy a korábban elhelyezett hologramokat látni

Ha HoloLens nem tudja leképezni vagy betölteni a tárhelyet, korlátozott módba lép, és nem fog tudni hologramokat elhelyezni vagy a elhelyezett hologramokat látni. Néhány dolog, amelyet érdemes kipróbálni:

- Győződjön meg arról, hogy elegendő fény van a környezetben, hogy HoloLens és leképezni tudja a területet.
- Álljon egy és három méter között, ahonnan a hologramot el akarja tenni.
- Ne helyezzen hologramokat fekete vagy tükröző felületekre.
- Győződjön meg arról, hogy egy hálózati Wi-Fi csatlakozik. Ha nem csatlakozik Wi-Fi-hálózathoz, HoloLens azonosítani és betölteni egy ismert területet.
- Járja végig a helyiségeket, HoloLens át tudja-e ásni a környezetet. A már beolvasott elemek vizsgálatának ellenőrzéshez koppintson a levegőre a leképezési háló ábrának a felfedéséhez.
- Ha új tárhelyet kell létrehoznia, csatlakozzon a Wi-Fi-hálózathoz, majd indítsa újra a HoloLens.
- Ha látnia kell, hogy a megfelelő terület aktív-e, vagy manuálisan be kell töltenie egy szóközt, a **Rendszerhelyek Gépház**  >    >  **meg.**
- Ha a megfelelő terület be van töltve, és továbbra is problémákat tapasztal, az sérült lehet. A probléma megoldásához válassza ki a helyet, majd válassza az Eltávolítás **lehetőséget.** A terület eltávolítása után a HoloLens elkezdi leképezni a környezetet, és új helyet létrehozni.

[Vissza a listához](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologramok eltűnnek, vagy más hologramba vagy objektumokba vannak bevetve

Ha túl közel kerül egy hologramhoz, az ideiglenesen eltűnik, és visszaállítja &mdash; a hologramot, csak elmozdul tőle. Ha több hologramot is közel helyezett egymáshoz, előfordulhat, hogy néhány eltűnik. Próbáljon meg eltávolítani néhányat.

Hologramok más hologramok, illetve objektumok, például falfalak is blokkolják vagy bezárják. Ha ez történik, próbálkozzon az alábbi javításokkal:

- Ha a hologram egy másik hologramba van beivatva, helyezze át a beékelt hologramot egy másik helyre. Ehhez válassza a **Beállítás** lehetőséget, majd koppintson és tartsa lenyomva a pozíciójához.
- Ha a hologram be van ékesedve egy falba, válassza a **Beállítás** lehetőséget, majd haladjon a fal felé, amíg meg nem jelenik a hologram. Koppintson és tartsa lenyomva, majd húzza előre és ki a hologramot a falról.
- Ha nem tudja kézmozdulatokkal áthelyezni a hologramot, távolítsa el a hangjával. Tekintsen a hologramra, majd mondja ki az "Eltávolítás" szót. Ezután nyissa meg újra a hologramot, és helyezze egy új helyre.

[Vissza a listához](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologramok a fal másik oldalán jelennek meg

Ha nagyon közel van egy falhoz, vagy HoloLens még nem vizsgálta be a falat, a következő helyiségben hologramokat láthat. A fal beolvasásakor álljon egy-három méter közé a faltól, és tekintsen rá.

Egy fekete vagy reflektív objektum (például egy fekete heverő vagy egy névtelen hűtő) a fal közelében problémákat okozhat, amikor HoloLens megpróbálnak beolvasni a falba. Ilyen objektum esetén vizsgálja meg a fal másik oldalát.

[Vissza a listához](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Miután elhelyez egy hologramot a falon, úgy tűnik, hogy lebegőg

Egy hologram, amely egy falra kerül, általában úgy tűnik, hogy körülbelül egy inch messze van a faltól. Ha úgy tűnik, hogy távol van, próbálkozzon az alábbi javításokkal:

- Amikor hologramot ad egy falhoz, álljon a faltól egy-három méter közé, és közvetlenül a fal felé néz.
- Légi koppintással koppintson a falra a térképes háló ábrának a felfedéséhez. Győződjön meg arról, hogy a háló a falhoz igazodik. Ha nem, távolítsa el a hologramot, ismét a falon, majd próbálkozzon újra.
- Ha a probléma továbbra is fennáll, futtassa a Tanácsadó alkalmazást. Ezt a következő Gépház  >    >  **találja:**.

[Vissza a listához](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Az alkalmazások túl közel jelennek meg az áthelyezés után

Próbálja ki, és vizsgálja meg azt a területet, ahová az alkalmazást helyezi, hogy a HoloLens különböző szögekből vizsgálja a területet. [Az eszköz vizorának tisztítása](hololens1-hardware.md#care-and-cleaning) is segíthet.

[Vissza a listához](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Instabil vagy nem használt hologramokkal kapcsolatos problémák jelentése
 
1. Rögzítsen egy Vegyes valóság rögzítése [a](holographic-photos-and-videos.md#capture-a-mixed-reality-video) problémáról. Ezt a videót később feltöltheti a Visszajelzési központ fájlként.  
1. Engedélyezze a teljes telemetriát a **Gépház** app -> **Privacy** Diagnostics & visszajelzéssel, és a Választható diagnosztikai adatok alatt győződjön meg arról, hogy a váltógomb Be  ->   van **állítva** 
1. Szerezze be a legújabb hologramméret- és stabilitási javításokat a [legújabb Windows Holographic OS (20H2 vagy újabb) verzióra való frissítésével.](hololens-release-notes.md#windows-holographic-version-20h2) A frissítés után hajtsa végre a következőket:
    1. Az összes Hologramok eltávolítása  Gépház app -> **System** Hologramok -> majd válassza az Összes hologram eltávolítása lehetőséget, és kezdje egy új  ->   térképpel. 
    1. Hozzon létre egy új térképet a térről a HoloLens és körbejárása a helyiségben, és a tér minden területén és felszínén. Ezt 2–3 percig tegye meg.
    1. VÉGEZZEN IPD-címszibrációt. Ugrás a **Gépház**  >    >  **segédprogramjaira.** A **Felberektálás** alatt válassza a **Nyitott ének lehetőséget.**
    1. Tesztelje újra a forgatókönyvet, és ellenőrizze, hogy továbbra is fennáll-e.
1. Ha a frissítés nem oldja meg a problémát, jelentsen be [egy Visszajelzési központ problémát.](hololens-feedback.md) A visszajelzés kitöltése után a  Megosztás gombbal létrehozhat egy könnyen megosztható hivatkozást, amely az ügyfélszolgálattal való kapcsolatfelvételkor küldhető el.

[Vissza a listához](#list)