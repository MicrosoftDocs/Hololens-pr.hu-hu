---
title: 2 HoloLens frissítés
description: Megtudhatja, hogyan ellenőrizheti a HoloLens buildszámát, hogyan tarthatja naprakészen az eszközfrissítéseket, hogyan csatlakozhat az Insiders programhoz, és hogyan úsíthatja vissza a frissítéseket.
keywords: how-to, update, roll back, HoloLens, check build, build number
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: f39fc2c6c0aaf16f304f38216a424c3811eb439d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032867"
---
# <a name="update-hololens-2"></a>2 HoloLens frissítés

## <a name="overview"></a>Áttekintés

Mindig dolgozunk az új funkciókon, hibajavításon és biztonsági frissítéseken. Értesítést kap, ha ezek a frissítések készen állnak.

Az Ön igényeinek megfelelően a HoloLens automatikusan letölti és telepíti a rendszerfrissítéseket, amikor csatlakoztatva van az áramellátáshoz, csatlakozik az internethez, és akár készenléti állapotban is.

Annak érdekében, HoloLens mindig frissítve legyen, hagyja csatlakoztatva a vele együtt érkezett tokhoz. Emellett azt is szeretné, HoloLens az internethez. Így automatikusan letölti és telepíti a rendszerfrissítéseket. 

A Windows Update szolgáltatással a frissítési folyamat több aspektusát is szabályozhatja, például hogy mely eszközök mely frissítéseket kapják meg. Ez a vezérlő azért hasznos, mert tesztelni tudja a HoloLens frissítéseit. Ezután a többi frissítésre is ki kell egészítenünk a frissítéseket. De különböző frissítési ütemezéseket is meghatározhat a különböző típusú frissítésekhez.

## <a name="types-of-updates"></a>A frissítések típusai

A HoloLens kétféle frissítés automatikusan kezelhető. 

- Funkciófrissítések: évente kétszer adták ki.
- Minőségi frissítések: kritikus fontosságú biztonsági frissítéseket tartalmaznak. Havonta vagy szükség szerint adták ki őket.

Használja **az Update** / **AllowAutoUpdate (AllowAutoUpdate** frissítése) lehetőséget a frissítések vizsgálatának, letöltésének és telepítésének kezeléséhez. 

## <a name="scheduling-updates"></a>Frissítések ütemezése

A frissítési ütemezést is beállíthatja. Ez lehet egy adott napon vagy naponta, egy adott időpontban. Például 17:00-kor vagy az aktív órán kívül.

Végül pedig néhány szót a frissítési stratégia megtervezéséről. Támogatjuk a frissítés halasztásokat. Így eldöntheti, hogy mennyi ideig várjon, amíg a Microsoft kiad egy frissítést a frissítésnek az eszközökön való telepítéséhez.

Előfordul, hogy egy vállalat először az összes új funkciót szeretné kipróbálni, hogy minden jól működik, és ismeri az új frissítéseket, hogy a támogatási csapat felkészült legyen. Miután megerősítik, hogy minden rendben van, a frissítéseket az egész vállalat számára elérhetőre ják. Ha az eszközök részkészleteit különböző halasztó házirendekkel(más néven frissítési körökhöz) társítja, koordinálhatja a frissítés-bevezetési stratégiát a szervezet számára.

## <a name="hololens-update-tools"></a>HoloLens eszközök frissítése

Ez a szakasz a következő HoloLens be:

- frissítések keresése
- manuális frissítés HoloLens
- az operációs rendszer aktuális verziójának megtekintése (buildszám)
- korábbi frissítésre való visszagördülés

### <a name="check-for-updates-and-manually-update"></a>Frissítések keresése és manuális frissítés

A beállítások között bármikor ellenőrizheti a frissítéseket.  Az elérhető frissítések és az új frissítések keresése:

1. Nyissa meg a **Gépházat**.
1. Lépjen az **Update & Security Windows** Update  >  **(Frissítés Windows) lapra.**
1. Válassza a **Frissítések keresése** lehetőséget.

Ha van elérhető frissítés, a rendszer elkezdi letölteni az új verziót. A letöltés befejezése után válassza az **Újraindítás most** gombot a telepítés aktiválásához. Ha az eszköz 40% alatti, és nincs csatlakoztatva, az újraindítás nem indítja el a frissítés telepítését.

Amíg a HoloLens telepíti a frissítést, forgó fogaskerékeket és folyamatjelzőt jelenít meg. Ne kapcsolja ki a HoloLens ebben az időszakban. A telepítés befejezése után automatikusan újraindul.

HoloLens egyszerre csak egy frissítést alkalmaz.  Ha a HoloLens egynél több verzióval van korábbi verzióval, előfordulhat, hogy többször is végig kell futnia a frissítési folyamaton, hogy teljesen naprakész legyen.

### <a name="check-your-operating-system-version-build-number"></a>Az operációs rendszer verziójának ellenőrzése (buildszám)

A rendszer verziószámát (buildszámát)  úgy ellenőrizheti, hogy megnyitja a Gépház a **Rendszerről**  >  **lehetőséget.**

### <a name="go-back-to-a-previous-version"></a>Vissza korábbi verzióra való átkért

Bizonyos esetekben érdemes lehet a szoftver korábbi verziójára HoloLens vissza. A javasolt lépések a következőek:

1. Lépjen kapcsolatba az ügyfélszolgálattal, és nézze meg, hogy meg tudják-e oldani a problémát.
    1. Győződjön **meg** arról, hogy a választható vagy a **teljes** telemetria engedélyezve van – így a hiba könnyebben kezelhető és könnyebben diagnosztizálható a mérnökök számára.
    1. [A fájlvisszacsatolás](hololens-feedback.md) a lehető leíró jellegű. Jegyezze fel a címet, vagy használja a megosztási funkciót, hogy megosztja a hibát a támogatási szolgálattal.
    1. Lépjen kapcsolatba a [támogatási szolgálattal.](https://aka.ms/hlsupport) Ha a problémát úgy kell megoldani, hogy visszatér egy korábbi verzióhoz, meg tudják oldani az FFU-t az eszköz flash (teljes körű) verziójának segítségével.

1. Ha ez nem működik, állítsa alaphelyzetbe a 2. HoloLens vagy perjelet [az Advanced Recovery Companion (Speciális helyreállítás-kísérő) gombra.](hololens-recovery.md)
    1. A számítógépen töltse le az [Advanced Recovery Companiont a](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) Microsoft Store.
    1. Győződjön meg arról, hogy nincs telefonja vagy Windows a számítógéphez csatlakoztatva.
    1. Válassza ki, hogy melyik verzióra szeretne flash-et választani:
        1. Letöltheti a [2-es HoloLens legújabb kiadását.](https://aka.ms/hololens2download)
        1. Használhatja az ARC-gazdagépek alapértelmezett buildét. (Ha ezt a lehetőséget választja, hagyja ki a következő lépést.)
        1. A megadott buildtámogatást használhatja.
    1. Ha végzett ezekkel a letöltésekkel, nyissa meg **a Fájlkezelő**  >  **letöltések gombra.** Kattintson a jobb gombbal a letöltött tömörített mappára, és válassza az Extract all Extract **(Összes** kibontás) lehetőséget a  >   kicsomagoláshoz.
    1. Csatlakozás a HoloLens a számítógépére USB-A–USB-C kábellel. (Ez akkor is működik a legjobban, ha más kábeleket használt a HoloLens csatlakoztatáshoz.)
    1. Az Advanced Recovery Companion automatikusan észleli a HoloLens. Válassza a **Microsoft HoloLens** csempét.
    1. A következő képernyőn válassza a **Manuális** csomagválasztás lehetőséget, majd válassza ki a 4. lépésben kicsomagolt mappában található telepítőfájlt. (Keresse meg a kiterjesztésű `.ffu` fájlt.)
    1. Válassza **a Szoftver telepítése lehetőséget,** és kövesse az utasításokat.

> [!NOTE]
> A korábbi verzióra való visszaút törli a személyes fájlokat és beállításokat.

Továbbá, ha meg szeretné maradni az aktuálisan telepített kiadást, manuálisan is szüneteltetheti [a frissítéseket.](hololens-updates.md#pause-updates-via-device) Ez időt ad a mérnöki csapatnak a probléma megoldására.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program a HoloLens

Szeretné látni a legújabb funkciókat a HoloLens?  Ha igen, csatlakozzon a Windows Insider Program; A szoftverfrissítések előzetes verziójú buildjéhez HoloLens, mielőtt azok nyilvánosan elérhetővé tehetővé tehetőek.

[Tekintse meg Windows Insider előzetes kiadását a Microsoft HoloLens.](hololens-insider.md)