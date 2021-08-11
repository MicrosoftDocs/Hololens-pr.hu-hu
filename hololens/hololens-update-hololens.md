---
title: 2 HoloLens frissítés
description: Megtudhatja, hogyan ellenőrizheti HoloLens buildszámát, hogyan tarthatja naprakészen az eszközfrissítéseket, hogyan csatlakozhat az Insiders programhoz, és hogyan ússíthatja vissza a frissítéseket.
keywords: how-to, update, roll back, HoloLens, check build, build number
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: 7e63fcab4c64f151684a634bb24d9fc31826f6805d52b23c5672add0b6269430
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662831"
---
# <a name="update-hololens-2"></a>2 HoloLens frissítés

HoloLens frissítés Windows, mint a többi Windows 10. A HoloLens automatikusan letölti és telepíti a rendszerfrissítéseket, amikor csatlakoztatva vannak az áramellátáshoz és csatlakoznak az internethez, még készenléti állapotban is.

Ez a cikk a következő HoloLens be:

- az operációs rendszer aktuális verziójának megtekintése (buildszám)
- frissítések keresése
- manuális frissítés HoloLens
- korábbi frissítésre való visszagördülés

## <a name="check-your-operating-system-version-build-number"></a>Ellenőrizze az operációs rendszer verzióját (buildszám)

A rendszer verziószámát (buildszám) úgy ellenőrizheti, hogy megnyitja a Gépház, és kiválasztja a **Rendszer a**  >  **következőről: .**

## <a name="check-for-updates-and-manually-update"></a>Frissítések keresése és manuális frissítés

A beállítások között bármikor ellenőrizheti a frissítéseket.  Az elérhető frissítések és az új frissítések keresése:

1. Nyissa meg a **Gépházat**.
1. Lépjen az **Update & Security Windows** Update  >  **(Frissítés Windows) lapra.**
1. Válassza a **Frissítések keresése** lehetőséget.

Ha van elérhető frissítés, az elkezdi letölteni az új verziót. A letöltés befejezése után válassza az **Újraindítás most** gombot a telepítés aktiválásához. Ha az eszköz 40% alatti, és nincs csatlakoztatva, az újraindítás nem indítja el a frissítés telepítését.

Amíg a HoloLens telepíti a frissítést, forgó fogaskerék és folyamatjelző jelenik meg. Ne kapcsolja ki a HoloLens ebben az időszakban. A telepítés befejezése után a rendszer automatikusan újraindul.

HoloLens a rendszer egyszerre csak egy frissítést alkalmaz.  Ha a HoloLens egynél több verzióval régebbi, előfordulhat, hogy többször is végig kell futnia a frissítési folyamaton, hogy teljesen naprakész legyen.

## <a name="go-back-to-a-previous-version"></a>Vissza korábbi verzióra való áttért

Bizonyos esetekben érdemes lehet a szoftver korábbi verziójára HoloLens vissza. A javasolt lépések a következőek:

1. Lépjen kapcsolatba az ügyfélszolgálattal, és nézze meg, hogy meg tudják-e oldani a problémát.
    1. Győződjön **meg** arról, hogy a választható vagy **a** teljes telemetria engedélyezve van – így a hiba könnyebben kezelhető és könnyebben diagnosztizálható a mérnökök számára.
    1. [A fájlvisszacsatolás](hololens-feedback.md) a lehető leíró jellegű. Jegyezze fel a címet, vagy használja a megosztási funkciót, hogy megosztja a hibát a támogatási szolgálattal.
    1. Lépjen kapcsolatba a [támogatási szolgálattal.](https://aka.ms/hlsupport) Ha a problémát úgy kell megoldani, hogy visszatér egy korábbi verzióhoz, akkor meg tudják oldani az FFU-t az eszköz flash (FFU) szolgáltatásához.

1. Ha ez nem működik, állítsa alaphelyzetbe vagy perjelre a 2. HoloLens az [Advanced Recovery Companion (Speciális helyreállítás-kísérő) funkcióval.](hololens-recovery.md)
    1. A számítógépen töltse le az [Advanced Recovery Companiont a](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) Microsoft Store.
    1. Győződjön meg arról, hogy nincs telefonja vagy Windows számítógéphez csatlakoztatva.
    1. Válassza ki, hogy melyik verziót szeretné flash-ként látni:
        1. Letöltheti a [2. HoloLens legújabb kiadását.](https://aka.ms/hololens2download)
        1. Használhatja az ARC-gazdagépek alapértelmezett buildját. (Ha ezt a lehetőséget választja, hagyja ki a következő lépést.)
        1. Használhatja a megadott buildtámogatást.
    1. Ha végzett ezekkel a letöltésekkel, nyissa meg **Fájlkezelő**  >  **letöltések gombra.** Kattintson a jobb gombbal az előbb letöltött tömörített mappára, és válassza az Extract all Extract **(Összes** kibontás) lehetőséget a  >   kicsomagoláshoz.
    1. Csatlakozás a HoloLens USB-A–USB-C kábellel csatlakoztatja a számítógépéhez. (Ez akkor is a legjobban működik, ha más kábelekkel csatlakoztatta HoloLens-t.)
    1. Az Advanced Recovery Companion automatikusan észleli a HoloLens. Válassza a **Microsoft HoloLens** csempét.
    1. A következő képernyőn válassza a **Manuális** csomagválasztás lehetőséget, majd válassza ki a telepítési fájlt, amely a 4. lépésben kicsomagolt mappában található. (Keress egy .ffu kiterjesztésű fájlt.)
    1. Válassza **a Szoftver telepítése lehetőséget,** és kövesse az utasításokat.

> [!NOTE]
> A korábbi verzióra való visszaút törli a személyes fájlokat és beállításokat.

Emellett ha meg szeretne maradni az aktuálisan telepített kiadásban, manuálisan is szüneteltetheti a [frissítéseket.](hololens-updates.md#pause-updates-via-device) Ez időt ad a mérnöki csapatnak a probléma megoldására.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program a HoloLens

Szeretné látni a HoloLens?  Ha igen, csatlakozzon a Windows Insider Program; A nyilvános verzióban elérhetővé HoloLens előzetes verziójú buildjéhez.

[Az Windows Insider előzetes verziója a Microsoft HoloLens.](hololens-insider.md)
