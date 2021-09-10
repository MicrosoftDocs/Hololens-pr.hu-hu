---
title: A 2. HoloLens támogatott nyelvei
description: Ismerje meg a 2. HoloLens támogatott nyelveket, a billentyűzetkiosztások megváltoztatását és a Windows frissítését.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 115225
- CSSTroubleshooting
keywords: localize, language support, display language, keyboard language, IME, keyboard layout
ms.date: 03/12/2020
audience: ITPro
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: dc3de0c95f17c821816bad278de5717bc24a2c29
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428568"
---
# <a name="supported-languages-for-hololens-2"></a>A 2. HoloLens támogatott nyelvei

HoloLens 2. nyelv a következő nyelvekre van honosított. A honosítási funkciók közé tartoznak a beszédparancsok, a diktálás, a billentyűzetkiosztások és az alkalmazások OCR-felismerése.

- Egyszerűsített kínai (Kína)
- Angol (Ausztrália)
- Angol (Kanada)
- Angol (Egyesült Királyság)
- angol (Egyesült Államok)
- Francia (Kanada)
- Francia (Franciaország)
- Német (Németország)
- Olasz (Olaszország)
- Japán (Japán)
- Spanyol (Spanyolország)

HoloLens 2. a következő nyelveket is támogatja. Ez a támogatás azonban nem tartalmazza a beszédparancsokat és a diktálás funkcióit.

- Hagyományos kínai (Tajvan és Hongkong)
- Holland (Hollandia)
- Koreai (Dél-Korea)

A 2. HoloLens egyes funkciói a Windows nyelvet használják. A Windows nyelv a következő beállításokra van hatással a Windows és a honosítást támogató alkalmazások esetében:

- A felhasználói felület szövegnyelve.
- A beszéd nyelve.
- A képernyőn megjelenő billentyűzet alapértelmezett elrendezése.

## <a name="change-the-language-or-keyboard-layout"></a>A nyelv vagy a billentyűzet elrendezésének módosítása

A telepítési folyamat konfigurálja a HoloLens egy adott régióhoz és nyelvhez. Ezt a konfigurációt az & **Time Gépház című** szakaszában **módosíthatja.**

> [!NOTE]  
> A beszéd és a diktálás nyelve a megjelenítési nyelvtől függ (és megegyezik) Windows nyelvtől.

### <a name="to-change-the-windows-display-language"></a>A megjelenítési nyelv Windows módosítása

1. Nyissa meg **a Start menüt,** majd válassza **a** Gépház  >  **és nyelvi**  >  **nyelv lehetőséget.**
2. Válassza **Windows megjelenítési nyelvet,** majd válasszon ki egy nyelvet.  

Ha a keresett támogatott nyelv nem található a menüben, kövesse az alábbi lépéseket:  

1. Az **Előnyben részesített nyelvek alatt** válassza a Nyelv hozzáadása **lehetőséget.**
2. Keresse meg és adja hozzá a nyelvet.
3. Válassza Windows **a nyelv megjelenítésére** vonatkozó menüt, majd válassza ki az előző lépésben hozzáadott nyelvet.

### <a name="to-change-the-keyboard-layout"></a>A billentyűzetkiosztás módosítása

Billentyűzetkiosztás hozzáadásához vagy eltávolításához nyissa meg a  **Start** menüt, majd válassza a Gépház  >  **a & billentyűzet**  >  **lehetőséget.**

Ha a HoloLens több billentyűzetkiosztása is van, váltson közöttük az Elrendezés billentyűvel.  Az **Elrendezés** billentyű a képernyőn megjelenő billentyűzet jobb alsó sarkában található.

> [!NOTE]  
> A képernyőn megjelenő billentyűzet az Input Method Editor (IME) használatával karaktereket ír be nyelveken, például japán nyelven. A HoloLens azonban nem támogatja az IME-t Bluetooth billentyűzeteket.
>  
> Bár az IME-t a képernyőn megjelenő billentyűzettel együtt használja, továbbra is használhatja a billentyűzetet Bluetooth gépelje be az angol nyelvet. A billentyűzetek közötti váltáshoz nyomja le a tilde karakter **~** () gombot.
