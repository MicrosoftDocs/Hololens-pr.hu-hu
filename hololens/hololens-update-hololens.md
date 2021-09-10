---
title: 2 HoloLens frissítés
description: Megtudhatja, hogyan ellenőrizheti HoloLens buildszámát, hogyan tarthatja naprakészen az eszközfrissítéseket, hogyan csatlakozhat az Insiders programhoz, és hogyan ússíthatja vissza a frissítéseket.
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427913"
---
# <a name="update-hololens-2"></a>2 HoloLens frissítés

## <a name="overview"></a>Áttekintés

Mindig dolgozunk az új funkciókon, hibajavításon és biztonsági frissítéseken. Értesítést kap, ha ezek a frissítések készen állnak.

Az Ön igényeinek megfelelően a HoloLens automatikusan letölti és telepíti a rendszerfrissítéseket, amikor csatlakoztatva vannak az áramellátáshoz, csatlakoznak az internethez, és akár készenléti állapotban is.

Annak érdekében, HoloLens a rendszer mindig frissült, hagyja csatlakoztatva a vele együtt érkezett tokot. Emellett azt is szeretné, HoloLens az internethez. Így automatikusan letölti és telepíti a rendszerfrissítéseket. 

A Windows Frissítési szolgáltatással a frissítési folyamat több aspektusát is szabályozhatja, például hogy mely eszközök mely frissítéseket kapják meg. Ez a vezérlő azért hasznos, mert az eszközök egy részéhez frissítéseket HoloLens tesztelés céljából. Ezután a többi frissítését is ki kell egészítenünk. De különböző frissítési ütemezéseket is meghatározhat a különböző típusú frissítésekhez.

## <a name="types-of-updates"></a>A frissítések típusai

A HoloLens kétféle frissítés automatikusan kezelhető. 

- Funkciófrissítések: évente kétszer adták ki.
- Minőségi frissítések: tartalmazza a kritikus fontosságú biztonsági frissítéseket. Havonta vagy szükség szerint adták ki őket.

Az  / **AllowAutoUpdate frissítéssel** kezelheti a frissítések keresését, letöltését és telepítését. 

## <a name="scheduling-updates"></a>Frissítések ütemezése

Frissítési ütemezést is be lehet állítani. Ez lehet egy adott napon vagy naponta, egy adott időpontban. Például 17:00-kor vagy az aktív órákon kívül.

Végül néhány szó a frissítési stratégia megtervezéséről. Támogatjuk a frissítés halasztásokat. Így eldöntheti, hogy mennyi ideig várjon, amíg a Microsoft kiad egy frissítést, és telepíti a frissítést az eszközökre.

Előfordul, hogy egy vállalat először az összes új funkciót szeretné kipróbálni, hogy minden jól működik- e, és ismeri az új frissítéseket, hogy a támogatási csapat felkészült legyen. Miután megerősítik, hogy minden rendben van, a frissítéseket az egész vállalatnál elérhetőre ják. Ha az eszközök részcsoportját különböző halasztó szabályzatokkal (más néven frissítési körökhöz) társítja, koordinálhatja a frissítésbe való bevezetési stratégiát a szervezet számára.

## <a name="hololens-update-tools"></a>HoloLens eszközök telepítése

Ez a szakasz a következő HoloLens be:

- frissítések keresése
- manuális frissítés HoloLens
- az operációs rendszer aktuális verziójának megtekintése (buildszám)
- korábbi frissítésre való visszagördülés

### <a name="check-for-updates-and-manually-update"></a>Frissítések keresése és manuális frissítés

A beállítások között bármikor ellenőrizheti a frissítéseket.  Az elérhető frissítések és az új frissítések keresése:

1. Nyissa meg a **Gépházat**.
1. Lépjen az **Update & Security Windows Update**  >  **(Frissítés Windows) lapra.**
1. Válassza a **Frissítések keresése** lehetőséget.

Ha van elérhető frissítés, az elkezdi letölteni az új verziót. A letöltés befejezése után válassza az **Újraindítás most** gombot a telepítés aktiválásához. Ha az eszköz 40% alatti, és nincs csatlakoztatva, az újraindítás nem indítja el a frissítés telepítését.

Amíg a HoloLens telepíti a frissítést, forgó fogaskerékeket és folyamatjelzőt jelenít meg. Ez idő alatt ne kapcsolja HoloLens a számítógépét. A telepítés befejezése után automatikusan újraindul.

HoloLens egyszerre csak egy frissítést alkalmaz.  Ha a HoloLens egynél több verzióval régebbi, előfordulhat, hogy többször is végig kell futnia a frissítési folyamaton, hogy teljesen naprakész legyen.

### <a name="check-your-operating-system-version-build-number"></a>Ellenőrizze az operációs rendszer verzióját (buildszám)

A rendszer verziószámát (buildszámát) úgy ellenőrizheti, hogy megnyitja a Gépház, és kiválasztja **a**   >  **Rendszerről szó lehetőséget.**

### <a name="go-back-to-a-previous-version"></a>Vissza korábbi verzióra

Bizonyos esetekben érdemes lehet a szoftver korábbi verziójára HoloLens vissza. A javasolt lépések aek:

1. Lépjen kapcsolatba az ügyfélszolgálattal, és nézze meg, hogy meg tudják-e oldani a problémát.
    1. Győződjön **meg** arról, hogy a választható vagy **a** teljes telemetria engedélyezve van – így a hiba könnyebben kezelhető és könnyebben diagnosztizálható a mérnökök számára.
    1. [A fájlvisszacsatolás](hololens-feedback.md) a lehető leíró jellegű. Jegyezze fel a címet, vagy használja a megosztási funkciót, hogy megosztja a hibát a támogatási szolgálattal.
    1. Lépjen kapcsolatba a [támogatási szolgálattal.](https://aka.ms/hlsupport) Ha a problémát úgy kell megoldani, hogy vissza kell térnie egy korábbi verzióhoz, akkor meg tudják oldani az FFU-t az eszköz flash (FFU) szolgáltatásához.

1. Ha ez nem működik, állítsa alaphelyzetbe vagy perjelre a [2. HoloLens az Advanced Recovery Companion (Speciális helyreállítás-kísérő) funkcióval.](hololens-recovery.md)
    1. A számítógépen töltse le az [Advanced Recovery Companiont](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) a Microsoft Store.
    1. Győződjön meg arról, hogy nincs telefonja vagy Windows számítógéphez csatlakoztatva.
    1. Válassza ki, hogy melyik verziót szeretné flash-ként látni:
        1. Letöltheti a [2-es HoloLens legújabb kiadását.](https://aka.ms/hololens2download)
        1. Használhatja az ARC által gazdagépként használt alapértelmezett buildet. (Ha ezt a lehetőséget választja, hagyja ki a következő lépést.)
        1. Használhatja a megadott buildtámogatást.
    1. Ha végzett ezekkel a letöltésekkel, nyissa meg **Fájlkezelő**  >  **letöltések gombra.** Kattintson a jobb gombbal a letöltött tömörített mappára, és válassza az Extract all Extract **(Összes** kibontás) lehetőséget a  >   kicsomagoláshoz.
    1. Csatlakozás a HoloLens USB-A–USB-C kábellel csatlakoztatja a számítógépéhez. (Ez akkor is működik a legjobban, ha más kábelekkel csatlakoztatta HoloLens-t.)
    1. Az Advanced Recovery Companion automatikusan észleli a HoloLens. Válassza a **Microsoft HoloLens** csempét.
    1. A következő képernyőn válassza a **Manuális** csomagválasztás lehetőséget, majd válassza ki a 4. lépésben kicsomagolt mappában található telepítőfájlt. (Keresse meg a kiterjesztésű `.ffu` fájlt.)
    1. Válassza **a Szoftver telepítése lehetőséget,** és kövesse az utasításokat.

> [!NOTE]
> A korábbi verzióra való visszaút törli a személyes fájlokat és beállításokat.

Emellett ha meg szeretne maradni az aktuálisan telepített kiadásban, manuálisan is szüneteltetheti a [frissítéseket.](hololens-updates.md#pause-updates-via-device) Ez időt ad a mérnöki csapatnak a probléma megoldására.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program a HoloLens

Szeretné látni a legújabb HoloLens?  Ha igen, csatlakozzon a Windows Insider Program; A nyilvános verzióban elérhetővé HoloLens elérhetővé HoloLens előzetes verziójú buildjéhez.

[Az Windows Insider előzetes verziója a Microsoft HoloLens.](hololens-insider.md)