---
title: A hang használata a HoloLens
description: Megtudhatja Cortana hogyan segíthetnek az HoloLens különféle műveletekben a vegyes valóságú eszközökön, beleértve a hangparancsokat, a diktálást és a hologram-interakciókat.
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
ms.openlocfilehash: 2fe7727fb05f983f56f329a6e7f7c25a627a914a1956fc65a9fc047653aae977
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661085"
---
# <a name="use-your-voice-to-operate-hololens"></a>A hang használata a HoloLens

A hangjával szinte bármit el lehet HoloLens, például egy gyors fényképre vagy egy alkalmazás megnyitására. Számos hangparancs be van építve a HoloLens, míg mások a Cortana.

Ez a cikk bemutatja, hogyan szabályozhatja a HoloLens és a holografikus világát a hangjával és Cortana.

> [!NOTE]
> A Speech csak bizonyos [nyelveken támogatott.](hololens2-language-support.md) A beszéd nyelve nem a billentyűzet, Windows a megjelenítési nyelven alapul.  
>  
> A nyelvi Windows a Time (Idő) Gépház   >  **Language (Nyelv)**  >  **kiválasztásával** ellenőrizheti.

## <a name="built-in-voice-commands"></a>Beépített hangparancsok

Ezekkel az alapszintű HoloLens gyorsabban el is eddi a problémákat. A használathoz engedélyeznie kell a Speechet az eszköz első futtatásakor vagy az **adatvédelmi Gépház**  >  **során.**  >   A képernyő tetején található állapot alapján mindig ellenőrizheti, hogy engedélyezve van-e a beszéd Start menü. A legjobb beszédfelismerési eredmények eléréséhez HoloLens 2. példa a Microsoft felhőalapú szolgáltatásait használja. A szolgáltatás letiltásához azonban Gépház is használhatja. Ehhez a következő Gépház kapcsolja ki az **Online beszédfelismerést.** A beállítás módosítása után a 2. HoloLens 2. csak helyileg fogja feldolgozni a hangadatokat a parancsok és a diktálás felismeréséhez, és a Cortana nem lesz elérhető.

### <a name="general-speech-commands"></a>Általános beszédparancsok

Használja ezeket a parancsokat a Windows Mixed Reality, hogy gyorsabb legyen. Egyes parancsok a tekintet kurzorát használják, amelyet a "select" (kijelölés) paranccsal lehet felhozni.

> [!NOTE]
> A kézi sugárok nem támogatottak HoloLens (1. generációs) operációs rendszer esetén.

| Mondja el ezt | Cél |
| - | - |
| "Select" | A tekintet kurzorának felfelé mozgatásához mondja a "select" (kijelölés) lehetőséget. Ezután fordítsa el a fejet, hogy a kurzort a kijelölni kívánt dolog fölé helyezze, és mondja ki újra a "select" (kijelölés) lehetőséget. |
| "Ugrás az indításhoz" |  A Start menü megnyitása |
| "Bezárás"  | Zárja be a Start menü |
| Mondja ki a "Go to Start" (Ugrás az indításhoz) parancsot a gyorsműveletek menüjének, majd a "Mixed reality home" (Vegyes valóság kezdőlapja) parancsnak.  | Hagyja el a modern alkalmazást |
| "A kéz sugárának elrejtése" / "Show hand ray" | Kézzeli sugár elrejtése és megjelenítése |
| "Mit mondjak?"  | Az elérhető beszédparancsok |

A 2. HoloLens 19041.x verziójától kezdve a következő parancsokat is használhatja:

| Mondja el ezt | Cél |
| - | - |
| "Eszköz újraindítása" | Egy párbeszéddel erősítse meg, hogy újra szeretné indítani az eszközt. Az újraindításhoz igent is lehet mondani. |
| "Eszköz leállítása" | Egy párbeszéddel erősítse meg, hogy ki szeretné kapcsolni az eszközt. A megerősítéshez igent kell mondania. |
| "Brightness up/down" | Növelje vagy csökkentse a kijelző fényerejét 10%-kal. |
| "Kötet felfelé/lefelé" | Növelje vagy csökkentse a kötetet 10%-kal. |
| "Mi az IP-címem" | Egy párbeszéd megjelenítése az eszköz aktuális IP-címével a helyi hálózaton. |
| "Képpel" | Készítsen vegyes valóságú fényképet az aktuálisan látható adatokról. |
| "Take a video" | Kezdjen el felvételt készíteni egy vegyes valóságú videóról. | 
| "Rögzítés leállítása" | Leállítja az aktuális vegyes valóságú videófelvételt, ha van folyamatban. |

### <a name="hologram-commands"></a>Hologramparancsok

A parancsok használatának 3D-s objektumra, hologramra vagy alkalmazásablakra való tekintete.

| Mondja el ezt | Cél |
| - | - |
| "Nagyobb" | Nagyobbra |
| "Kisebb" | Legyen kisebb |
| "Face me" | Fordítsa meg a szemének |
| "Áthelyezés" | Helyezze át (kövesse a tekintetét) |
| "Bezárás" | Zárja be |
| "Follow me" / "Stop following" | Kövesse, ahogy mozog |

### <a name="see-it-say-it"></a>Tekintse meg, mondja ki

A képernyő számos gombja és HoloLens reagálnak a hangjára **is–** ilyen például a Követés és bezárás az alkalmazássávon vagy a Vissza **gomb** az Edge-ben.  Ha meg kell tudni, hogy egy gomb hangalapú-e,  a kurzorra ható tekintetet, az érintéses kurzort vagy az egyik kézzel rákapcsolódó sugarat kell egy pillanatra felrakni.  Ha a gomb hangalapú, egy hangajánlott tippet fog látni.

### <a name="dictation-mode"></a>Diktálás mód

Unja már a gépelést? Bármikor váltson diktálás módra, ha a holografikus billentyűzet aktív. Első lépésekhez kattintson a mikrofon gombra, vagy mondja ki a "Diktálás kezdete" lehetőséget. A diktálás leállításhoz kattintson ismét a gombra, vagy mondja ki a "Stop dictating" (Diktálás megállása) lehetőséget. Az előbb lekért adatok törléséhez mondja ki a "Delete that" (Törlés) parancsot. 

> [!NOTE]
> A diktálás mód csak internetkapcsolat használatával használható.

HoloLens a diktálás explicit írásjeleket használ, ami azt jelenti, hogy a használni kívánt írásjelek nevét kell használnia. Például így szólhat: "Hé, **vessző,** mit hozunk fel **a kérdőjelre."**

Az írásjeleket a következő kulcsszavakkal használhatja:

- Pont, vessző, kérdőjel, felkiáltójel/felkiáltójel
- Új sor/új bekezdés
- Pontosvessző, kettőspont
- Nyisson meg egy vagy több idézőjelet, zárja be az idézőjel(eket)
- Hashtag, mosolygó/mosolygó arc, fúny, winky
- Dollár, százalék

Néha hasznos lehet olyan dolgokat kiírni, mint az e-mail-címek. Ha például a van example@outlook.com megszabva, az "E X A M P L E at outlook dot com" (E X A P L E at outlook dot com)

## <a name="do-more-with-cortana"></a>További információ a Cortana

Cortana segítségével sokféle dolgot is HoloLens, de attól függően, hogy a Holographic Windows melyik verzióját használja, a képességek eltérőek lehetnek. A Cortana legújabb verziójának frissített képességeiről a Cortana következő kiadásában Windows 10 olvashat [bővebben:](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)a hatékonyságot és a fokozott biztonságot és adatvédelmet. 

![Hé, Cortana!](images/cortana-on-hololens.png)

Íme néhány dolog, amit megpróbálhat mondani (ne felejtse el először a "Hey Cortana" szót).

**Hé, Cortana...**

- A használható parancsok
- Indítsa <*alkalmazás nevét a*>.
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
- Helyezze <*alkalmazás nevét*> ide (és tekintsen arra a pontra, a helyre, a
- Lépjen a Start menüre.
- Képpel.
- Kezdje meg a rögzítést. (Elindítja a videó rögzítését.)
- Állítsa le a rögzítést. (Leállítja a videó rögzítését.)
- Mennyi akkumulátor maradt?

A Cortana nem támogatja a Windows Windows egyes funkcióit (például az emlékeztetőket és az értesítéseket) az Microsoft HoloLens-ban, és az Cortana használata régiónként eltérő lehet.

### <a name="turn-cortana-off"></a>A Cortana kikapcsolása

Cortana első alkalommal használja a HoloLens a beszéd engedélyezésekor. Kikapcsolhatja a Cortana beállításaiban. A lista **Minden alkalmazás** válassza **a** Cortana  >  **Gépház** lehetőséget. Ezután kapcsolja ki a Cortana adhat javaslatokat, ötleteket, emlékeztetőket, riasztásokat stb.

Ha Cortana nem válaszol a "Hey Cortana" szövegre, ellenőrizze, hogy a beszéd engedélyezve van-e a Start menüben, majd a Cortana beállításai között ellenőrizze, hogy be van-e kapcsolva.
