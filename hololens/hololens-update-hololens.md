---
title: A HoloLens frissítése
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378111"
---
# <a name="update-hololens"></a>A HoloLens frissítése

A HoloLens Windows Update, mint más Windows 10 eszközök. A HoloLens automatikusan letölti és telepíti a rendszerfrissítéseket, amikor csatlakoztatva vannak az áramellátáshoz és csatlakoznak az internethez, még készenléti állapotban is.

Ez a cikk a HoloLens-eszközöket a következő eszközökhöz fogja használni:

- az operációs rendszer aktuális verziójának megtekintése (buildszám)
- frissítések keresése
- a HoloLens manuális frissítése
- korábbi frissítésre való visszagördülés

## <a name="check-your-operating-system-version-build-number"></a>Az operációs rendszer verziójának ellenőrzése (buildszám)

A rendszer verziószámát (buildszám) a Beállítások alkalmazás megnyitásával, majd a Rendszer a következőről **lehetőség** kiválasztásával  >  **ellenőrizheti:**.

## <a name="check-for-updates-and-manually-update"></a>Frissítések keresése és manuális frissítés

A beállítások között bármikor ellenőrizheti a frissítéseket.  Az elérhető frissítések és az új frissítések keresése:

1. Nyissa meg a **Gépházat**.
1. Lépjen az **Update & Security**  >  **Windows Update.**
1. Válassza a **Frissítések keresése** lehetőséget.

Ha van elérhető frissítés, az elkezdi letölteni az új verziót. A letöltés befejezése után válassza az **Újraindítás most** gombot a telepítés aktiválásához. Ha az eszköz 40% alatti, és nincs csatlakoztatva, az újraindítás nem indítja el a frissítés telepítését.

Amíg a HoloLens telepíti a frissítést, forgó fogaskerékeket és folyamatjelzőt jelenít meg. Ez idő alatt ne kapcsolja ki a HoloLenst. A telepítés befejezése után a rendszer automatikusan újraindul.

A HoloLens egyszerre csak egy frissítést alkalmaz.  Ha a HoloLens egynél több verzióval régebbi, előfordulhat, hogy többször is végig kell futnia a frissítési folyamaton, hogy teljesen naprakész legyen.

## <a name="go-back-to-a-previous-version---hololens-2"></a>Vissza verzióra való áttűnés – HoloLens 2

Bizonyos esetekben érdemes lehet visszatérni a HoloLens szoftver egy korábbi verziójára. Ehhez az Advanced Recovery Companion használatával visszaállíthatja a HoloLenst a korábbi verzióra.

> [!NOTE]
> A korábbi verzióra való visszaút törli a személyes fájlokat és beállításokat.

A HoloLens 2 egy korábbi verziójára való visszaúthoz kövesse az alábbi lépéseket:

1. Győződjön meg arról, hogy nincs csatlakoztatva telefon vagy Windows-eszköz a számítógéphez.
1. A számítógépen töltse le az [Advanced Recovery Companiont a](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) Microsoft Store.
1. Töltse le [a legújabb HoloLens 2-kiadást.](https://aka.ms/hololens2download)
1. Ha végzett ezekkel a letöltésekkel, nyissa meg a **Fájlkezelő**  >  **Letöltések ját.** Kattintson a jobb gombbal az előbb letöltött tömörített mappára, és válassza az Extract all Extract **(Összes** kibontás) lehetőséget a  >   kicsomagoláshoz.
1. Csatlakoztassa a HoloLenst a számítógépéhez EGY USB-A–USB-C kábellel. (Ez akkor is működik a legjobban, ha más kábelekkel csatlakoztatta a HoloLenst.)
1. Az Advanced Recovery Companion automatikusan észleli a HoloLenst. Válassza a **Microsoft HoloLens** csempét.
1. A következő képernyőn válassza a **Manuális** csomagválasztás lehetőséget, majd válassza ki a 4. lépésben kicsomagolt mappában található telepítőfájlt. (Keress egy .ffu kiterjesztésű fájlt.)
1. Válassza **a Szoftver telepítése lehetőséget,** és kövesse az utasításokat.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Vissza verzióra való áttűnés – HoloLens (1. generáció)

Bizonyos esetekben érdemes lehet visszatérni a HoloLens szoftver egy korábbi verziójára. Ezt a Windows Eszköz-helyreállítási eszközzel használhatja a HoloLens korábbi verzióra való visszaállításához.

> [!NOTE]
> A korábbi verzióra való visszaút törli a személyes fájlokat és beállításokat.

A HoloLens 1 egy korábbi verziójára való visszaúthoz kövesse az alábbi lépéseket:

1. Győződjön meg arról, hogy nincs csatlakoztatva telefon vagy Windows-eszköz a számítógéphez.
1. A számítógépen töltse le a [Windows Device Recovery Tool (WDRT) eszközt.](https://support.microsoft.com/help/12379)
1. Töltse le a [HoloLens évfordulós frissítés helyreállítási csomagját.](https://aka.ms/hololensrecovery)
1. Ha a letöltések befejeződnek, nyissa meg a **Fájlkezelő**  >  **Letöltések gombra.** Kattintson a jobb gombbal az előbb letöltött tömörített mappára, és válassza az Extract all Extract **(Összes** kibontás) lehetőséget a  >   kicsomagoláshoz.
1. Csatlakoztassa a HoloLenst a számítógépéhez a vele együtt használt mikro-USB-kábellel. (Ez akkor is működik a legjobban, ha más kábelekkel csatlakoztatta a HoloLenst.)
1. A WDRT automatikusan észleli a HoloLenst. Válassza a **Microsoft HoloLens** csempét.
1. A következő képernyőn válassza a **Manuális** csomagválasztás lehetőséget, és válassza ki a 4. lépésben kicsomagolt mappában található telepítőfájlt. (Keress egy .ffu kiterjesztésű fájlt.)
1. Válassza **a Szoftver telepítése lehetőséget,** és kövesse az utasításokat.

> [!NOTE]
> Ha a WDRT nem észleli a HoloLenst, próbálja meg újraindítani a számítógépet. Ha ez nem működik, válassza a **Saját eszköz** nem észlelhető lehetőséget, válassza a Microsoft HoloLens **lehetőséget,** majd kövesse az utasításokat.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program HoloLensen

Szeretné látni a HoloLens legújabb funkcióit?  Ha igen, csatlakozzon a Windows Insider Program; Hozzáférést kap a HoloLens-szoftverfrissítések előzetes buildjéhez, mielőtt azok nyilvánosan elérhetővé tenék őket.

[A Windows Insider előzetes verzió Microsoft HoloLens.](hololens-insider.md)
