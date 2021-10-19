---
title: 2 HoloLens frissítés
description: Megtudhatja, hogyan ellenőrizheti a HoloLens buildszámát, naprakészen tarthatja az eszközfrissítéseket, hogyan csatlakozhat az Insiders programhoz, és hogyan úsíthatja vissza a frissítéseket.
keywords: how-to, update, roll back, HoloLens, check build, build number
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-beehanson
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/11/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 080fb184c7eca3fdb978e860a29764f5012a179e
ms.sourcegitcommit: f105a770814ccd61e88b650448902a03c95b7a3c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/19/2021
ms.locfileid: "130151685"
---
# <a name="update-hololens-2"></a>2 HoloLens frissítés

## <a name="overview"></a>Áttekintés

Mindig dolgozunk az új funkciókon, hibajavításon és biztonsági frissítéseken. Értesítést kap, ha ezek a frissítések készen állnak.

Az Ön igényeinek megfelelően a HoloLens automatikusan letölti és telepíti a rendszerfrissítéseket, amikor csatlakoztatva vannak az hálózathoz, csatlakoznak az internethez, és akár készenléti állapotban is.

Annak érdekében, HoloLens mindig frissítve legyen, hagyja csatlakoztatva a vele együtt érkezett tokhoz. Azt is szeretné, hogy HoloLens az internethez. Így automatikusan letölti és telepíti a rendszerfrissítéseket. 

Az Windows Update szolgáltatással a frissítési folyamat több aspektusát is szabályozhatja, például hogy mely eszközök mely frissítéseket kapják meg. Ez a vezérlő azért hasznos, mert tesztelni tudja a frissítéseket HoloLens egy részéhez. Ezután a többi frissítésre is ki kell egészítenünk a frissítéseket. De különböző frissítési ütemezéseket is meghatározhat a különböző típusú frissítésekhez.

## <a name="types-of-updates"></a>A frissítések típusai

A HoloLens kétféle frissítés automatikusan kezelhető.

- Funkciófrissítések: évente kétszer adták ki.
- Minőségi frissítések: kritikus fontosságú biztonsági frissítéseket tartalmaznak. Havonta vagy szükség szerint adták ki őket.

Használja **az Update** / **AllowAutoUpdate (AllowAutoUpdate** frissítése) lehetőséget a frissítések vizsgálatának, letöltésének és telepítésének kezeléséhez. 

## <a name="scheduling-updates"></a>Frissítések ütemezése

A frissítési ütemezést is beállíthatja. Ez lehet egy adott napon vagy naponta, egy adott időpontban. Például 17:00-kor vagy az aktív órán kívül.

Végül pedig néhány szót a frissítési stratégia megtervezéséről. Támogatjuk a frissítések halasztását, így Ön döntheti el, hogy mennyi ideig várjon, amíg a Microsoft kiad egy frissítést, és telepíti a frissítést az eszközökre.

Előfordul, hogy egy vállalat először az összes új funkciót szeretné kipróbálni annak érdekében, hogy minden jól működik, és ismeri az új frissítéseket, hogy a támogatási csapat felkészült legyen. Miután megerősítik, hogy minden rendben van, a frissítéseket az egész vállalat számára elérhetőre ják. Ha az eszközök részkészleteit különböző halasztó házirendekkel(más néven frissítési körökhöz) társítja, koordinálhatja a frissítés-bevezetési stratégiát a szervezet számára.

## <a name="hololens-update-tools"></a>HoloLens eszközök frissítése

Ez a szakasz a következő HoloLens be:

- frissítések keresése
- manuális frissítés HoloLens
- az operációs rendszer aktuális verziójának megtekintése (buildszám)
- korábbi frissítésre való visszagördülés

### <a name="check-for-updates-and-manually-update"></a>Frissítések keresése és manuális frissítés

A beállítások között bármikor ellenőrizheti a frissítéseket.  Az elérhető frissítések és az új frissítések keresése:

1. Nyissa meg a **Gépházat**.
1. Lépjen az **Update & Security Windows** Update (Frissítés  >  **Windows) lapra.**
1. Válassza a **Frissítések keresése** lehetőséget.

Ha van elérhető frissítés, a rendszer elkezdi letölteni az új verziót. A letöltés befejezése után válassza az **Újraindítás most** gombot a telepítés aktiválásához. Ha az eszköz 40% alatti, és nincs csatlakoztatva, az újraindítás nem indítja el a frissítés telepítését.

Amíg a HoloLens telepíti a frissítést, forgó fogaskerékeket és egy folyamatjelzőt jelenít meg. Ne kapcsolja ki a HoloLens ebben az időszakban. A telepítés befejezése után automatikusan újraindul.

HoloLens egyszerre csak egy frissítést alkalmaz.  Ha a HoloLens egynél több verzióval régebbi, előfordulhat, hogy többször is végig kell futnia a frissítési folyamaton, hogy teljesen naprakész legyen.

### <a name="check-your-operating-system-version-build-number"></a>Az operációs rendszer verziójának ellenőrzése (buildszám)

A rendszer verziószámát (buildszámát) úgy ellenőrizheti, hogy megnyitja a Gépház, és **kiválasztja** a **Rendszer a következőről:**  >  **lehetőséget.**

### <a name="go-back-to-a-previous-version"></a>Vissza korábbi verzióra való átkért

Bizonyos esetekben érdemes lehet a szoftver korábbi verziójára HoloLens vissza. A javasolt lépések a következőek:

1. Lépjen kapcsolatba az ügyfélszolgálattal, és nézze meg, hogy meg tudják-e oldani a problémát.
    1. Győződjön **meg** arról, hogy a választható vagy a **teljes** telemetria engedélyezve van – így a hiba könnyebben kezelhető és könnyebben diagnosztizálható a mérnökök számára.
    1. A [Fájlvisszacsatolás](hololens-feedback.md) lehetőségnek a lehető leírónak kell lennie. Jegyezze fel a címet, vagy használja a megosztási funkciót, hogy megosztja a hibát a támogatási szolgálattal.
    1. Lépjen kapcsolatba a [támogatási szolgálattal.](https://aka.ms/hlsupport) Ha a problémát úgy kell megoldani, hogy visszatér egy korábbi verzióhoz, meg tudják oldani az FFU-t az eszköz flash (teljes körű) verziójának segítségével.

1. Másik lehetőségként az Advanced Recovery Companion (Speciális helyreállítás-kísérő) HoloLens 2. perjelet [is beszúrhat.](hololens-recovery.md#clean-reflash-the-device)
    1.  Válassza ki, hogy melyik verzióra szeretne flash-et választani: 
        1.  A legújabb, [2 HoloLens kiadást töltheti le.](https://aka.ms/hololens2download)
        1.  Használhatja az ARC-gazdagépek alapértelmezett buildét.
        1.  A megadott buildtámogatást használhatja.

> [!NOTE]
> A korábbi verzióra való visszaút törli a személyes fájlokat és beállításokat.

Továbbá, ha meg szeretné maradni az aktuálisan telepített kiadást, manuálisan is szüneteltetheti [a frissítéseket.](hololens-updates.md#pause-updates-via-device) Ez időt ad a mérnöki csapatnak a probléma megoldására.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program a HoloLens

Szeretné látni a legújabb HoloLens?  Ha igen, csatlakozzon a Windows Insider Program; A szoftverfrissítések előzetes verziójú buildjéhez HoloLens, mielőtt azok nyilvánosan elérhetővé tehetővé tehetőek.

[Szerezze Windows Insider előzetes kiadását a Microsoft HoloLens.](hololens-insider.md)