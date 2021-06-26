---
title: A HoloLens 2 frissítése
description: Megtudhatja, hogyan ellenőrizheti a HoloLens buildszámát, hogyan tarthatja naprakészen az eszközfrissítéseket, hogyan csatlakozhat az Insiders programhoz, és hogyan ússíthatja vissza a frissítéseket.
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
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924111"
---
# <a name="update-hololens-2"></a>A HoloLens 2 frissítése

A HoloLens Windows Update, mint más Windows 10 eszközök. A HoloLens automatikusan letölti és telepíti a rendszerfrissítéseket, amikor csatlakoztatva vannak az áramellátáshoz és csatlakoznak az internethez, még készenléti állapotban is.

Ez a cikk a HoloLens-eszközöket a következő eszközökhöz fogja használni:

- az operációs rendszer aktuális verziójának megtekintése (buildszám)
- frissítések keresése
- a HoloLens manuális frissítése
- korábbi frissítésre való visszagördülés

## <a name="check-your-operating-system-version-build-number"></a>Ellenőrizze az operációs rendszer verzióját (buildszám)

A rendszer verziószámát (buildszám) a Settings (Beállítások) alkalmazás megnyitásával és a System About **(Rendszerről)** lehetőség kiválasztásával  >  **ellenőrizheti.**

## <a name="check-for-updates-and-manually-update"></a>Frissítések keresése és manuális frissítés

A beállítások között bármikor ellenőrizheti a frissítéseket.  Az elérhető frissítések és az új frissítések keresése:

1. Nyissa meg a **Gépházat**.
1. Lépjen az **Update & Security**  >  **Windows Update.**
1. Válassza a **Frissítések keresése** lehetőséget.

Ha van elérhető frissítés, az elkezdi letölteni az új verziót. A letöltés befejezése után válassza az **Újraindítás** most gombot a telepítés aktiválásához. Ha az eszköz 40% alatti, és nincs csatlakoztatva, az újraindítás nem indítja el a frissítés telepítését.

Amíg a HoloLens telepíti a frissítést, forgó fogaskerékeket és folyamatjelzőt jelenít meg. Ez idő alatt ne kapcsolja ki a HoloLenst. A telepítés befejezése után a rendszer automatikusan újraindul.

A HoloLens egyszerre csak egy frissítést alkalmaz.  Ha a HoloLens egynél több verzióval régebbi, előfordulhat, hogy többször is végig kell futnia a frissítési folyamaton, hogy teljesen naprakész legyen.

## <a name="go-back-to-a-previous-version"></a>Vissza korábbi verzióra való áttért

Bizonyos esetekben érdemes lehet visszatérni a HoloLens szoftver egy korábbi verziójára. A javasolt lépések a következőek:

1. Lépjen kapcsolatba az ügyfélszolgálattal, és nézze meg, hogy meg tudják-e oldani a problémát.
    1. Győződjön **meg** arról, hogy a választható vagy **a** teljes telemetria engedélyezve van – így a hiba könnyebben kezelhető és könnyebben diagnosztizálható a mérnökök számára.
    1. [A fájlvisszacsatolás](hololens-feedback.md) a lehető leíró jellegű. Jegyezze fel a címet, vagy használja a megosztási funkciót, hogy megosztja a hibát a támogatási szolgálattal.
    1. Lépjen kapcsolatba az [ügyfélszolgálattal.](https://aka.ms/hlsupport) Ha a problémát úgy kell megoldani, hogy visszatér egy korábbi verzióhoz, akkor meg tudják oldani az FFU-t az eszköz flash (FFU) szolgáltatásához.

1. Ha ez nem működik, állítsa alaphelyzetbe vagy [perjelre a HoloLens 2-t az Advanced Recovery Companion (Speciális helyreállítás-kísérő) funkcióval.](hololens-recovery.md)
    1. A számítógépen töltse le az [Advanced Recovery Companiont a](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) Microsoft Store.
    1. Győződjön meg arról, hogy nincs csatlakoztatva telefon vagy Windows-eszköz a számítógéphez.
    1. Válassza ki, hogy melyik verziót szeretné flash-ként látni:
        1. Letöltheti a [legújabb HoloLens 2-kiadást.](https://aka.ms/hololens2download)
        1. Használhatja az ARC-gazdagépek alapértelmezett buildét. (Ha ezt a lehetőséget választja, hagyja ki a következő lépést.)
        1. Használhatja a megadott buildtámogatást.
    1. Ha végzett ezekkel a letöltésekkel, nyissa meg **Fájlkezelő**  >  **letöltések gombra.** Kattintson a jobb gombbal az előbb letöltött tömörített mappára, és válassza az Extract all Extract **(Összes** kibontás) lehetőséget a  >   kicsomagoláshoz.
    1. Csatlakoztassa a HoloLenst a számítógépéhez EGY USB-A–USB-C kábellel. (Ez akkor is működik a legjobban, ha más kábelekkel csatlakoztatta a HoloLenst.)
    1. Az Advanced Recovery Companion automatikusan észleli a HoloLenst. Válassza a **Microsoft HoloLens** csempét.
    1. A következő képernyőn válassza a **Manuális** csomagválasztás lehetőséget, majd válassza ki a telepítési fájlt, amely a 4. lépésben kicsomagolt mappában található. (Keress egy .ffu kiterjesztésű fájlt.)
    1. Válassza **a Szoftver telepítése lehetőséget,** és kövesse az utasításokat.

> [!NOTE]
> A korábbi verzióra való visszaút törli a személyes fájlokat és beállításokat.

Emellett ha meg szeretne maradni az aktuálisan telepített kiadásban, manuálisan is szüneteltetheti a [frissítéseket.](hololens-updates.md#pause-updates-via-device) Ez időt ad a mérnöki csapatnak a probléma megoldására.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program HoloLensen

Szeretné látni a HoloLens legújabb funkcióit?  Ha igen, csatlakozzon a Windows Insider Program; Hozzáférést kap a HoloLens-szoftverfrissítések előzetes buildjéhez, mielőtt azok nyilvánosan elérhetővé tenék őket.

[A Windows Insider előzetes verzió Microsoft HoloLens.](hololens-insider.md)
