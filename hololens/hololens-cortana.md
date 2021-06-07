---
title: A Hang használata a HoloLens működtetéséhez
description: Megtudhatja, hogyan segíthet Cortana különféle műveletekben a HoloLens vegyes valóságú eszközein, beleértve a hangparancsokat, a diktálást és a hologram-interakciókat.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379601"
---
# <a name="use-your-voice-to-operate-hololens"></a>A Hang használata a HoloLens működtetéséhez

A hangjával szinte bármit meg tud tenni a HoloLensen, például egy gyors fényképen vagy egy alkalmazás megnyitásán. Számos hangparancs be van építve a HoloLensbe, míg mások a Cortanán keresztül érhetők el.

Ez a cikk bemutatja, hogyan szabályozhatja a HoloLenst és a holografikus világot a hangjával és Cortanával.

> [!NOTE]
> A Beszéd csak bizonyos [nyelveken támogatott.](hololens2-language-support.md) A beszédnyelv a Windows megjelenítési nyelvén alapul, nem a billentyűzeten.  
>  
> A Windows megjelenítési nyelvének ellenőrzéséhez válassza a **Beállítások ideje** és a  >  **Nyelv**  >  **lehetőséget.**

## <a name="built-in-voice-commands"></a>Beépített hangparancsok

Ezekkel az alapszintű parancsokkal gyorsabban körbeveszi a HoloLenst. A használathoz engedélyeznie kell a Speechet az eszköz első futtatásakor vagy a **Beállítások**  >  **adatvédelmi beszédében.**  >   A képernyő tetején található állapot alapján mindig ellenőrizheti, hogy engedélyezve van-e a Start menü. A legjobb beszédfelismerési eredmények eléréséhez a HoloLens 2 a Microsoft felhőalapú szolgáltatásait használja. A Beállítások használatával azonban letilthatja ezt a funkciót. Ehhez a Beállítások menüben kapcsolja ki az **Online beszédfelismerést.** A beállítás módosítása után a HoloLens 2 csak helyben fogja feldolgozni a hangadatokat a parancsok és a diktálás felismeréséhez, Cortana pedig nem lesz elérhető.

### <a name="general-speech-commands"></a>Általános beszédparancsok

Használja ezeket a parancsokat a Windows Mixed Reality, hogy gyorsabb legyen. Egyes parancsok a tekintet kurzorát használják, amelyet a "select" (kijelölés) paranccsal lehet felhozni.

> [!NOTE]
> A holoLens (1. generációs) nem támogatja a kézcsomóképeket.

| Mondja el ezt | Cél |
| - | - |
| "Select" (Kijelölés) | A tekintet kurzorának felfelé mozgatásához mondja a "select" (kijelölés) lehetőséget. Ezután fordítsa el a fejet, hogy a kurzort a kijelölni kívánt dolog fölé helyezze, és mondja ki ismét a "select" (kijelölés) lehetőséget. |
| "Ugrás az indításhoz" |  A Start menü megnyitása |
| "Bezárás"  | Zárja be a Start menü |
| A gyorsműveletek menüjének a "Go to Start" (Ugrás az indításhoz) parancsra, majd a "Mixed reality home" (Vegyes valóság kezdőlapja) szóra kell feljönni.  | Hagyja el a modern alkalmazást |
| "A kéz sugárának elrejtése" / "Show hand ray" | Kézzeli sugár elrejtése és megjelenítése |
| "Mit mondjak?"  | Az elérhető beszédparancsok |

A HoloLens 2 19041.x verziójától kezdve a következő parancsokat is használhatja:

| Mondja el ezt | Cél |
| - | - |
| "Eszköz újraindítása" | Egy párbeszéd segítségével erősítse meg, hogy újra szeretné indítani az eszközt. Az újraindításhoz igent kell mondania. |
| "Eszköz leállítása" | Egy párbeszéd segítségével erősítse meg, hogy ki szeretné kapcsolni az eszközt. A megerősítéshez igent kell mondania. |
| "Fényerő felfelé/lefelé" | A kijelző fényerejének növelése vagy csökkentése 10%-kal. |
| "Kötet felfelé/lefelé" | Növelje vagy csökkentse a kötetet 10%-kal. |
| "Mi az IP-címem" | Egy párbeszéd megjelenítése az eszköz aktuális IP-címével a helyi hálózaton. |
| "Képpel" | Rögzítsen egy vegyes valóságú fényképet arról, amit jelenleg lát. |
| "Take a video" | Kezdjen el egy vegyes valóságú videó felvételét. | 
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

A HoloLens számos gombja és egyéb eleme is reagál  a hangjára,  például kövessen és zárja be az alkalmazássávon, vagy a **Vissza** gombot az Edge-ben. Ha meg kell tudni, hogy egy gomb hangalapú-e,  egy pillanatra a tekintete kurzorát, az érintéses kurzort vagy a rá ható egyik kéz sugarát kell látnia.  Ha a gomb hangalapú, egy hangra tippet fog látni.

### <a name="dictation-mode"></a>Diktálás mód

Unja már a gépelést? Ha a holografikus billentyűzet aktív, váltson diktálás módra. Első lépésekként kattintson a mikrofon gombra, vagy mondja ki a "Diktálás kezdete" lehetőséget. A diktálás leállhoz kattintson ismét a gombra, vagy mondja ki a "Diktálás megállása" szót. Az előbb megszabott adatok törléséhez mondja ki a "Delete that" (Törlés) parancsot. 

> [!NOTE]
> A diktálás módhoz internetkapcsolatra van szükség.

A HoloLens-dictation explicit írásjeleket használ, ami azt jelenti, hogy a használni kívánt írásjelek nevét kell használnia. Íme például a "Hey comma what you up to question mark" **(Vessző,** mit kell vesszővel **vesszőzve) kérdésre.**

Íme az írásjel kulcsszavak, amelyek használhatók:

- Pont, vessző, kérdőjel, felkiáltójel/felkiáltójel
- Új sor/új bekezdés
- Pontosvessző, kettőspont
- Nyisson meg egy vagy több idézőjelet, zárja be az idézőjel(eket)
- Hashtag, mosolygós/mosolygós arc, mosolygós, winky
- Dollár, százalék

Néha hasznos lehet olyan dolgokat kiírni, mint az e-mail-címek. Ha például az van megszabva, az example@outlook.com "E X A M P L E at outlook dot com" (E X A M P L E at outlook dot com) szöveg.

## <a name="do-more-with-cortana"></a>További információ a Cortanával

Cortana sokféle feladatban segíthet a HoloLensen, de a Használt Windows Holographic verziójától függően a képességek eltérőek lehetnek. A Cortana legújabb verziójának frissített képességeiről itt olvashat bővebben: Cortana a következő Windows 10 kiadásban: a fokozott biztonsággal és adatvédelemmel kapcsolatos termelékenységre [összpontosítva.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/) 

![Hey Cortana!](images/cortana-on-hololens.png)

Íme néhány dolog, amit megpróbálhat mondani (ne felejtse el először a "Hey Cortana" szót használni).

**Hé, Cortana...**

- A használható parancsok
- Indítsa <*alkalmazásnevet a*>.
- mennyi az idő?
- A legújabb NBA-pontszámok megjelenítése.
- Mondja el, mit kell ásni.

Ha a *18362.x* vagy korábbi verziót használja, a következő parancsokat is használhatja:

**Hé, Cortana...**

- Növelje a kötetet.
- Csökkentse a fényerejét.
- leállítás.
- Újraindítás.
- menj aludni.
- Néma.
- Helyezze <*alkalmazás>* ide (tekintete arra a pontra, a a helyre, a helyhez, a ahol az alkalmazás áthelyezését el
- Lépjen a Start menüre.
- Képpel.
- Kezdje meg a rögzítést. (Elindítja a videó rögzítését.)
- Állítsa le a rögzítést. (Leállítja a videó rögzítését.)
- Mennyi akkumulátor maradt?

A Microsoft HoloLens nem támogatja a Windows egyes Cortana-funkcióit (például az emlékeztetőket és az értesítéseket), és a Cortana használata régiónként eltérő lehet.

### <a name="turn-cortana-off"></a>Cortana kikapcsolása

Cortana először használja a HoloLenst a beszéd engedélyezésekor. Cortana beállításaiban kikapcsolhatja. A **Minden alkalmazás** válassza a **Cortana-beállítások**  >  **lehetőséget.** Ezután kapcsolja ki a Cortanát, és javaslatokat, ötleteket, emlékeztetőket, riasztásokat és egyéb adatokat adhat meg.

Ha Cortana nem válaszol a "Hé, Cortana" szövegre, ellenőrizze, hogy a beszéd engedélyezve van-e az indításnál, majd a Cortana beállításai között ellenőrizze, hogy be van-e kapcsolva.
