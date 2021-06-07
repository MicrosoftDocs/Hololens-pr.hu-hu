---
title: Hibaelhárítás
description: Maradjon naprakész a HoloLens-eszközök problémáinak és hibaelhárítási módszereinek leggyakoribb megoldásaival kapcsolatban.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problémák, hiba, hibaelhárítás, javítás, súgó, támogatás, HoloLens
ms.openlocfilehash: 1039af533b5039eb4eef6599c7cbb480955b0661
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378112"
---
# <a name="troubleshoot-common-issues"></a>Gyakori problémák megoldása

Ez a cikk több gyakori HoloLens-probléma megoldását ismerteti.

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>A HoloLens nem válaszol vagy nem indul el

Ha a HoloLens nem indul el:

- Ha a bekapcsológomb melletti LED-ek nem világadnak meg, vagy csak egy LED villog rövid időre, előfordulhat, hogy fel kell töltenie a [HoloLenst.](hololens-recovery.md#charge-the-device)
- Ha a led-ek felgyújtják a bekapcsológombot, de nem lát semmit a kijelzőkön, állítsa elő az eszköz alaphelyzetbe [állítását.](hololens-recovery.md#hard-reset-procedure)

Ha a HoloLens lefagy vagy nem válaszol:

- Kapcsolja ki a HoloLenst úgy, hogy megnyomja a bekapcsológombot, amíg mind az öt LED ki nem kapcsolja magát, vagy 15 másodpercig, ha a LED-ek nem válaszolnak. A HoloLens-hez nyomja le újra a bekapcsológombot.

Ha ezek a lépések nem működnek, megpróbálhatja helyreállítani [HoloLens 2-](hololens-recovery.md) vagy [HoloLens- (1. generációs) eszközét.](hololens1-recovery.md)

## <a name="holograms-dont-look-good"></a>A hologramok nem jól néznek ki

Ha a hologramok instabilak, jumpyak vagy nem jól néznek ki, próbálkozzon a következővel:

- A HoloLens előlapján található eszköztekintő és érzékelősáv tisztítása.
- A világítás növelése a helyiségben.
- Járdákoljon, és vizsgálja meg a környezetet, hogy a HoloLens jobban át tudja vizsgálni őket.
- A HoloLens-nek a szemére nézve. Ugrás a **Beállítások**  >  **rendszer-segédprogramok**  >  **lapra.** A **Felberektálás** alatt válassza a **Nyitott ének lehetőséget.**
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>A hologramok instabil vagy nem megfelelő megjelenésével kapcsolatos problémák jelentése
 
1. Rögzítsen egy Vegyes valóság rögzítése [a](holographic-photos-and-videos.md#capture-a-mixed-reality-video) problémáról. Ezt a videót később feltöltheti a Visszajelzési központ fájlként.  
1. Engedélyezze a teljes telemetriát a **Settings** (Beállítások) alkalmazás -> **Privacy** Diagnostics & feedback (Visszajelzés) lehetőségével, és a Választható diagnosztikai adatok alatt ellenőrizze, hogy a kapcsoló Be  ->   van-e **állítva** 
1. A legújabb hologramméret- és stabilitási javításokat a legújabb Windows Holographic operációs rendszerre [(20H2 vagy újabb) frissítve.](hololens-release-notes.md#windows-holographic-version-20h2) A frissítés után hajtsa végre a következőket:
    1. Távolítsa el az  összes hologramot a Beállítások alkalmazás -> **System**  ->  **Holograms** -> válassza az **Összes hologram** eltávolítása lehetőséget, és kezdje egy új térképpel.
    1. Hozzon létre egy új térképet a térről a HoloLens berakása és a helyiségben való eljárás és a tér összes területének és felületének a megálmodása által. Ezt 2–3 percig tegye meg.
    1. VÉGEZZEN IPD-címszibrációt. Ugrás a **Beállítások**  >  **rendszer-segédprogramok**  >  **lapra.** A **Felberektálás** alatt válassza a **Nyitott ének lehetőséget.**
    1. Tesztelje újra a forgatókönyvet, és ellenőrizze, hogy továbbra is fennáll-e.
1. Ha a frissítés nem oldja meg a problémát, jelentsen be [egy Visszajelzési központ problémát.](hololens-feedback.md) A visszajelzés kitöltése után a  Megosztás gombbal létrehozhat egy könnyen megosztható hivatkozást, amely az ügyfélszolgálattal való kapcsolatfelvételkor küldhető el.

## <a name="hololens-doesnt-respond-to-hand-input"></a>A HoloLens nem válaszol a bemeneti adatokra

Ahhoz, hogy a HoloLens lássa a kézmozdulatokat, kézmozdulatkeretben kell tartania őket.  A Mixed Reality Kezdőlap visszajelzést ad, amely tudatja, mikor követik nyomon a kézzel.  A Visszajelzések eltérnek a HoloLens különböző verzióiról:
- HoloLensen (1. generációs) a tekintet kurzora pontról gyűrűre változik
- A HoloLens 2-ben egy egérmutató jelenik meg, ha a kéz egy laphoz közel van, és egy kéz sugár jelenik meg, ha a belók távolodnak

Számos modern alkalmazás a Kezdőlaphoz hasonló bemeneti mintákat Mixed Reality követ.  További információ a kézzel bevitt adatok [a HoloLensben (1. generációs)](hololens1-basic-usage.md#use-hololens-with-your-hands) és a [HoloLens 2-ben való használatával kapcsolatban.](hololens2-basic-usage.md#the-hand-tracking-frame)

Vegye figyelembe, hogy a kézkövetés bizonyos típusú kézkövetési funkcióval nem működik.  Gyakori példa a fekete védőkesztyűk, amelyek általában befogadják a világítást, és a mélységi kamera nem tudja felvenni őket.  Ha a munkája során védőkesztyűt is dolgoz, javasoljuk, hogy egy világosabb színt, például kéket vagy szürkét próbáljon ki.  Egy másik példa a nagy méretű, nagy méretű, kézbegyűkösség, amely általában elfedi a kéz alakját. Javasoljuk, hogy a legjobb eredmény érdekében a lehető legjobban illeszkedő, jól illeszkedő védőkét használja.

Ha a vizor ujjlenyomattal vagy elmosott lenyomattal rendelkezik, a HoloLenshez készült mikrofiberos tisztítással megtisztítsa a vizort.

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>A HoloLens nem válaszol a hangparancsomra

Ha Cortana nem válaszol a hangparancsra, győződjön meg arról, hogy Cortana be van kapcsolva. A Minden alkalmazás a **Cortana**  >  **menü**  >  **Jegyzetfüzet-beállítások**  >   menüpontját a módosítások gombra. További információ a beszédről: Use your voice with HoloLens (A hang használata [a HoloLens-sel).](hololens-cortana.md)

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>Nem tudok hologramokat elhelyezni, és nem látom a korábban elhelyezett hologramokat

Ha a HoloLens nem tudja leképezni vagy betölteni a tárhelyet, korlátozott módba lép, és nem fog tudni hologramokat elhelyezni, illetve a elhelyezett hologramokat látni. Néhány dolog, amelyet érdemes kipróbálni:

- Győződjön meg arról, hogy a környezete elég világos, hogy a HoloLens lát és leképezni tudja a helyet.
- Győződjön meg arról, hogy egy hálózati Wi-Fi csatlakozik. Ha nem csatlakozik Wi-Fi-hez, a HoloLens nem tudja azonosítani és betölteni az ismert tárhelyet.
- Ha új területet kell létrehoznia, csatlakozzon a Wi-Fi-hez, majd indítsa újra a HoloLenst.
- Ha meg kell tudni, hogy a megfelelő terület aktív-e, vagy manuálisan be kell töltenie egy szóközt, kattintson a **Beállítások**  >  **Rendszerterek**  >  **elemre.**
- Ha a megfelelő terület van betöltve, és továbbra is problémákat tapasztal, az sérült lehet. A probléma megoldásához válassza ki a helyet, majd válassza az Eltávolítás **lehetőséget.** A terület eltávolítása után a HoloLens elkezdi leképezni a környezetet, és új teret hoz létre.

## <a name="my-hololens-cant-tell-what-space-im-in"></a>A HoloLens nem tudja, hogy melyik térben vagyok

Ha a HoloLens nem tudja automatikusan azonosítani és betölteni a helyet, ellenőrizze a következő tényezőket:

- Győződjön meg arról, hogy csatlakozott a Wi-Fi
- Győződjön meg arról, hogy sok fény van a helyiségben
- Győződjön meg arról, hogy nem történt jelentős változás a környezetben.

A szóközöket manuálisan is betöltheti, vagy kezelheti a szóközöket a **Beállítások**  >  **Rendszerterek**  >  **menüben.**

## <a name="im-getting-a-low-disk-space-error"></a>"Kevés lemezterület" hibaüzenetet kapok

Az alábbiak közül egy vagy több megoldással szabadíthat fel tárhelyet:

- Töröljön néhány nem használt szóközt. Válassza a **Beállítások**  >  **Rendszerterek** lehetőséget, válasszon ki egy szóközt, amelyre már nincs  >  szüksége, majd válassza az Eltávolítás **lehetőséget.**
- Távolítsa el a elhelyezett hologramokat.
- Töröljön néhány képet és videót a Photos alkalmazásból.
- Néhány alkalmazás eltávolítása a HoloLensből. A **Minden alkalmazás** koppintson és tartsa lenyomva az eltávolítani kívánt alkalmazást, majd válassza az **Eltávolítás lehetőséget.**

## <a name="my-hololens-cant-create-a-new-space"></a>A HoloLens nem tud új teret létrehozni

A legvalószínűbb probléma az, hogy kevés a tárhely. Próbálja ki az előző [tippek valamelyikét, hogy](#im-getting-a-low-disk-space-error) lemezterületet szabadít fel.

## <a name="the-hololens-emulator-isnt-working"></a>A HoloLens emulátor nem működik

A HoloLens emulátorról a fejlesztői dokumentációnkban tájékozódhat.  További információ [a HoloLens emulátor hibaelhárításáról.](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)
