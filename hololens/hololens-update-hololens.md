---
title: 2 HoloLens frissítés
description: Megtudhatja, hogyan ellenőrizheti HoloLens buildszámát, hogyan tarthatja naprakészen az eszközfrissítéseket, hogyan csatlakozhat az Insiders programhoz, és hogyan ússíthatja vissza a frissítéseket.
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
ms.openlocfilehash: 49036135ba13a93d2e8be97a7f3a95d50785c5c5
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034263"
---
# <a name="update-hololens-2"></a>2 HoloLens frissítés

## <a name="overview"></a>Áttekintés

Mindig dolgozunk az új funkciókon, hibajavításon és biztonsági frissítéseken. Értesítést kap, ha ezek a frissítések készen állnak.

Az Ön igényeinek megfelelően a HoloLens automatikusan letölti és telepíti a rendszerfrissítéseket, amikor csatlakoztatva vannak az hálózathoz, csatlakoznak az internethez, és akár készenléti állapotban is.

Annak érdekében, HoloLens mindig frissült, hagyja csatlakoztatva a vele együtt érkezett tokhoz. Azt is szeretné, hogy HoloLens az internethez. Így automatikusan letölti és telepíti a rendszerfrissítéseket. 

A Windows Frissítési szolgáltatással a frissítési folyamat több aspektusát is szabályozhatja, például hogy mely eszközök mely frissítéseket kapják meg. Ez a vezérlő azért hasznos, mert tesztelni tudja az eszközök HoloLens frissítéseit. Ezután a többi frissítését is ki kell egészítenünk. De különböző frissítési ütemezéseket is meghatározhat a különböző típusú frissítésekhez.

## <a name="types-of-updates"></a>A frissítések típusai

A HoloLens kétféle frissítés automatikusan kezelhető.

- Funkciófrissítések: évente kétszer adták ki.
- Minőségi frissítések: tartalmazza a kritikus fontosságú biztonsági frissítéseket. Havonta vagy szükség szerint adták ki őket.

Az  / **AllowAutoUpdate frissítéssel** kezelheti a frissítések keresését, letöltését és telepítését. 

## <a name="scheduling-updates"></a>Frissítések ütemezése

Frissítési ütemezést is be lehet állítani. Ez lehet egy adott nap, vagy minden nap, egy adott időpontban. Például 17:00-kor vagy az aktív órákon kívül.

Végül néhány szó a frissítési stratégia megtervezéséről. Támogatjuk a frissítések halasztását, így Ön eldöntheti, hogy mennyi ideig várjon, amíg a Microsoft kiad egy frissítést, és telepíti a frissítést az eszközökre.

Előfordul, hogy egy vállalat először az összes új funkciót szeretné kipróbálni annak érdekében, hogy minden jól működik, és ismeri az új frissítéseket, hogy a támogatási csapat felkészült legyen. Miután megerősítik, hogy minden rendben van, a frissítéseket az egész vállalatnál elérhetőre ják. Ha az eszközök részkészleteit különböző halasztó szabályzatokkal(más néven frissítési körökhöz) társítja, koordinálhatja a frissítésbe való bevezetési stratégiát a szervezet számára.

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

Ha van elérhető frissítés, az elkezdi letölteni az új verziót. A letöltés befejezése után válassza az **Újraindítás most** gombot a telepítés aktiválásához. Ha az eszköz 40% alatti, és nincs csatlakoztatva, az újraindítás nem indítja el a frissítés telepítését.

Amíg a HoloLens telepíti a frissítést, forgó fogaskerék és folyamatjelző jelenik meg. Ne kapcsolja ki a HoloLens ebben az időszakban. A telepítés befejezése után a rendszer automatikusan újraindul.

HoloLens a rendszer egyszerre csak egy frissítést alkalmaz.  Ha a HoloLens egynél több verzióval régebbi, előfordulhat, hogy többször is végig kell futnia a frissítési folyamaton, hogy teljesen naprakész legyen.

### <a name="check-your-operating-system-version-build-number"></a>Ellenőrizze az operációs rendszer verzióját (buildszám)

A rendszer verziószámát (buildszámát) úgy ellenőrizheti, hogy megnyitja a **Gépház,** és kiválasztja a Rendszer a   >  **következőről:** lehetőséget.

### <a name="go-back-to-a-previous-version"></a>Vissza korábbi verzióra való áttért

Bizonyos esetekben érdemes lehet a szoftver korábbi verziójára HoloLens vissza. A javasolt lépések aek:

1. Lépjen kapcsolatba az ügyfélszolgálattal, és nézze meg, hogy meg tudják-e oldani a problémát.
    1. Győződjön **meg** arról, hogy a választható vagy **a** teljes telemetria engedélyezve van – így a hiba könnyebben kezelhető és könnyebben diagnosztizálható a mérnökök számára.
    1. A [Fájlvisszacsatolás](hololens-feedback.md) lehetőségnek a lehető leírónak kell lennie. Jegyezze fel a címet, vagy használja a megosztási funkciót, hogy megosztja a hibát a támogatási szolgálattal.
    1. Lépjen kapcsolatba a [támogatási szolgálattal.](https://aka.ms/hlsupport) Ha az Ön problémája az, amelyet egy korábbi verzióra való visszatérés után meg kell oldani, akkor meg tudják oldani az FFU-t az eszköz flash elemének flash (FFU) segítségével.

1. Ha ez nem működik, az Advanced Recovery Companion (Speciális helyreállítás-kísérő) HoloLens újra a [2.](hololens-recovery.md#clean-reflash-the-device)HoloLens.

> [!NOTE]
> A korábbi verzióra való visszaút törli a személyes fájlokat és beállításokat.

Emellett ha meg szeretne maradni az aktuálisan telepített kiadásban, manuálisan is szüneteltetheti a [frissítéseket.](hololens-updates.md#pause-updates-via-device) Ez időt ad a mérnöki csapatnak a probléma megoldására.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program a HoloLens

Szeretné látni a legújabb HoloLens?  Ha igen, csatlakozzon a Windows Insider Program; A nyilvános verzióban elérhetővé HoloLens elérhetővé HoloLens előzetes verziójú buildjéhez.

[Szerezze Windows Insider előzetes kiadását a Microsoft HoloLens.](hololens-insider.md)