---
title: A hang használata a HoloLens
description: Megtudhatja Cortana hogyan segíthetnek az HoloLens különböző dolgok, többek között a hangparancsok, a diktálás és a hologram-interakciók.
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6e3dd8f7dc90cea158d000251973ec75dc76a90
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036021"
---
# <a name="use-your-voice-to-operate-hololens"></a>A hang használata a HoloLens

A hangjával szinte bármit el lehet HoloLens, például egy gyors fényképre vagy egy alkalmazás megnyitására. Számos hangparancs beépített HoloLens, míg mások a Cortana.

Ez a cikk bemutatja, hogyan szabályozhatja a HoloLens és a holografikus világát a hangjával és a Cortana.

> [!NOTE]
> A Beszéd csak bizonyos [nyelveken támogatott.](hololens2-language-support.md) A beszéd nyelve nem a billentyűzet, Windows, a megjelenítési nyelven alapul.  
>  
> A nyelvi Windows a Time (Idő) Gépház Language (Nyelv)   >  **kiválasztásával ellenőrizheti.**  >  

## <a name="built-in-voice-commands"></a>Beépített hangparancsok

Ezekkel az alapszintű HoloLens gyorsabban el lehet haladni. A használathoz engedélyeznie kell a Speechet az eszköz első futtatásakor vagy az Gépház  >  **speech**  >  **eszközben.** A képernyő tetején található állapot alapján mindig ellenőrizheti, hogy engedélyezve van-e a Start menü. A 2. HoloLens microsoftos felhőalapú szolgáltatásokat használja a legjobb beszédfelismerési eredmények eléréséhez. A szolgáltatás letiltásához azonban Gépház is használhatja. Ehhez a következő Gépház kapcsolja ki **az Online beszédfelismerést.** A beállítás módosítása után a 2. HoloLens csak helyileg fogja feldolgozni a hangadatokat a parancsok és a diktálás felismeréséhez, és a Cortana nem lesz elérhető.

### <a name="general-speech-commands"></a>Általános beszédparancsok

Használja ezeket a parancsokat a Windows Mixed Reality, hogy gyorsabb legyen. Egyes parancsok a tekintet kurzorát használják, amelyet a "select" (kijelölés) paranccsal lehet felhozni.

> [!NOTE]
> A kéz sugarai nem támogatottak a HoloLens (1. gen).

| Mondja el ezt | Cél |
| - | - |
| "Select" (Kijelölés) | A tekintet kurzorának felfelé mozgatásához mondja a "select" (kijelölés) lehetőséget. Ezután fordítsa el a fejet, hogy a kurzort a kijelölni kívánt dolog fölé helyezze, és mondja ki ismét a "select" (kijelölés) lehetőséget. |
| "Ugrás az indításhoz" |  A Start menü megnyitása |
| "Bezárás"  | Zárja be a Start menü |
| A gyorsműveletek menüjének a "Go to Start" (Ugrás az indításhoz) parancsra, majd a "Mixed reality home" (Vegyes valóság kezdőlapja) szóra kell feljönni.  | Hagyja el a modern alkalmazást |
| "A kéz sugárának elrejtése" / "Show hand ray" | A kéz sugárának elrejtése és megjelenítése |
| "Mit mondjak?"  | Az elérhető beszédparancsok |

A 2. HoloLens 19041.x verziójától kezdve a következő parancsokat is használhatja:

| Mondja el ezt | Cél |
| - | - |
| "Eszköz újraindítása" | Egy párbeszéd segítségével erősítse meg, hogy újra szeretné indítani az eszközt. Az újraindításhoz mondja az "igen" szót. |
| "Eszköz leállítása" | Egy párbeszéd segítségével erősítse meg, hogy ki szeretné kapcsolni az eszközt. A megerősítéshez igent kell mondania. |
| "Fényerő felfelé/lefelé" | A kijelző fényerejének növelése vagy csökkentése 10%-kal. |
| "Kötet felfelé/lefelé" | Növelje vagy csökkentse a kötetet 10%-kal. |
| "Mi az IP-címem" | Egy párbeszéd megjelenítése az eszköz aktuális IP-címével a helyi hálózaton. |
| "Képpel" | Rögzítsen egy vegyes valóságú fényképet arról, amit jelenleg lát. |
| "Videó megtekintése" | Kezdjen el egy vegyes valóságú videó felvételét. | 
| "Rögzítés leállítása" | Leállítja az aktuális vegyes valóságú videófelvételt, ha van folyamatban. |

### <a name="hologram-commands"></a>Hologram-parancsok

A parancsok használatának 3D-s objektumra, hologramra vagy alkalmazásablakra kell nézve.

| Mondja el ezt | Cél |
| - | - |
| "Nagyobb" | Nagyobbra |
| "Kisebb" | Legyen kisebb |
| "Face me" | Fordítsa meg a szemének |
| "Áthelyezés" | Helyezze át (kövesse a tekintetét) |
| "Bezárás" | Zárja be |
| "Follow me" / "Stop following" | Kövesse, ahogy mozog |

### <a name="see-it-say-it"></a>Tekintse meg, mondja ki

Számos gomb és a HoloLens is reagál a hangjára–  például  kövessen és zárja be  az alkalmazássávon, vagy a Vissza gombot az Edge-ben. Ha meg kell tudni, hogy egy gomb hangalapú-e,  egy pillanatra a tekintete kurzorát, az érintéses kurzort vagy az egyik kéz sugárát kell rá ásni.  Ha a gomb hangalapú, egy hangparancsot fog látni.

### <a name="dictation-mode"></a>Diktálás mód

Unja a gépelést? Bármikor váltson diktálás módra, ha a holografikus billentyűzet aktív. Első lépésekként kattintson a mikrofon gombra, vagy mondja ki a "Diktálás kezdete" lehetőséget. A diktálás leállhoz kattintson ismét a gombra, vagy mondja ki a "Diktálás megállása" szót. Az előbb megszabott adatok törléséhez mondja ki a "Delete that" (Törlés) parancsot. 

> [!NOTE]
> A diktálás mód csak akkor használható, ha rendelkezik internetkapcsolattal.

HoloLens a dictation explicit írásjeleket használ, ami azt jelenti, hogy a használni kívánt írásjelek nevét kell használnia. Íme például a "Hey comma what you up to question mark" **(Vessző,** mit kell vesszővel **vesszőzve) kérdésre.**

Íme az írásjel kulcsszavak, amelyek használhatók:

- Pont, vessző, kérdőjel, felkiáltójel/felkiáltójel
- Új sor/új bekezdés
- Pontosvessző, kettőspont
- Nyisson meg egy vagy több idézőjelet, zárja be az idézőjel(eket)
- Hashtag, mosolygós/mosolygós arc, mosolygós, winky
- Dollár, százalék

Néha hasznos lehet olyan dolgokat kiírni, mint az e-mail-címek. Ha például az van megszabva, az example@outlook.com "E X A M P L E at outlook dot com" (E X A P L E at outlook dot com) szöveg.

## <a name="do-more-with-cortana"></a>További információ a Cortana

Cortana a szolgáltatásban sokféle dolgot HoloLens, de a holographic Windows verziójától függően a képességek eltérőek lehetnek. A Cortana legújabb verziójának frissített képességeiről itt Cortana következő Windows 10-kiadásban olvashat [bővebben:](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)a fokozott biztonsággal és adatvédelemmel kapcsolatos termelékenységre összpontosítva. 

![Hé, Cortana!](images/cortana-on-hololens.png)

Íme néhány dolog, amit megpróbálhat mondani (ne felejtse el először a "Hey Cortana" szót).

**Hé, Cortana...**

- A használható parancsok
- Indítsa <*alkalmazásnevet a*>.
- Mennyi az idő?
- A legújabb NBA-pontszámok megjelenítése.
- Mondja el, mit kell ásni.

Ha a *18362.x* vagy korábbi verziót használja, a következő parancsokat is használhatja:

**Hé, Cortana...**

- Növelje a kötetet.
- Csökkentse a fényerejét.
- Leállítás.
- Újraindítás.
- Menj aludni.
- Néma.
- Helyezze <*alkalmazás>* ide (tekintete arra a pontra, a a helyre
- Lépjen a Start menüre.
- Képpel.
- Kezdje meg a rögzítést. (Elindítja a videó rögzítését.)
- Állítsa le a rögzítést. (Leállítja a videó rögzítését.)
- Mennyi akkumulátor maradt?

A Cortana nem támogatja a Windows Windows egyes funkcióit (például az emlékeztetőket és az értesítéseket) az Microsoft HoloLens-ban, és az Cortana használata régiónként eltérő lehet.

### <a name="turn-cortana-off"></a>A Cortana kikapcsolása

Cortana első alkalommal használja a HoloLens amikor engedélyezi a beszédet. Kikapcsolhatja a Cortana beállításaiban. A lista **Minden alkalmazás** válassza **a** Cortana  >  **Gépház** lehetőséget. Ezután kapcsolja ki a Cortana adhat javaslatokat, ötleteket, emlékeztetőket, riasztásokat stb.

Ha Cortana nem válaszol a "Hey Cortana" szövegre, ellenőrizze, hogy a beszéd engedélyezve van-e a Start menüben, majd a Cortana beállításai között ellenőrizze, hogy be van-e kapcsolva.
