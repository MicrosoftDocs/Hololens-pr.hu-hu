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
ms.openlocfilehash: 32f4cce668b2f8a483dbef3f4b41a0ceb8267dcc202f2be9d32ecec4061d0c21
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659574"
---
# <a name="supported-languages-for-hololens-2"></a>A 2. HoloLens támogatott nyelvei

HoloLens 2. nyelv a következő nyelvekre van honosított. A honosítási funkciók közé tartoznak a beszédparancsok és a diktálás, a billentyűzetkiosztások és az alkalmazáson belüli OCR-felismerés.

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

A 2. HoloLens egyes funkciói a Windows nyelvet használják. A Windows nyelv a következő beállításokra van hatással a Windows és a honosítást támogató alkalmazások esetén:

- A felhasználói felület szövegnyelve.
- A beszéd nyelve.
- A képernyőn megjelenő billentyűzet alapértelmezett elrendezése.

## <a name="change-the-language-or-keyboard-layout"></a>A nyelv vagy a billentyűzet elrendezésének módosítása

A telepítési folyamat konfigurálja a HoloLens egy adott régióhoz és nyelvhez. Ezt a konfigurációt a következő cikk **Time & language (Idő és Gépház)** **szakaszában Gépház.**

> [!NOTE]  
> A beszéd és a diktálás nyelve a megjelenítési nyelvtől függ (és megegyezik) Windows nyelvtől.

### <a name="to-change-the-windows-display-language"></a>A megjelenítési nyelv Windows módosítása

1. Nyissa meg **a Start menüt,** majd válassza a **Gépház** és  >  **nyelvi nyelv**  >  **lehetőséget.**
2. Válassza **Windows nyelvet,** majd válasszon nyelvet.  

Ha a keresett támogatott nyelv nem található a menüben, kövesse az alábbi lépéseket:  

1. Az **Előnyben részesített nyelvek alatt** válassza a Nyelv hozzáadása **lehetőséget.**
2. Keresse meg és adja hozzá a nyelvet.
3. Válassza Windows **a nyelv megjelenítésére** vonatkozó menüt, majd válassza ki az előző lépésben hozzáadott nyelvet.

### <a name="to-change-the-keyboard-layout"></a>A billentyűzetkiosztás módosítása

Billentyűzetkiosztás hozzáadásához vagy eltávolításához nyissa meg a  **Start** menüt, majd válassza a Gépház a &  >  **billentyűzet**  >  **lehetőséget.**

Ha a HoloLens több billentyűzetkiosztást is tartalmaz, az Elrendezés billentyűvel válthat közöttük.  Az **Elrendezés** billentyű a képernyő billentyűzetének jobb alsó sarkában található.

> [!NOTE]  
> A képernyőn megjelenő billentyűzet az Input Method Editor (IME) használatával karaktereket ír be nyelveken, például japán nyelven. A HoloLens azonban nem támogatja az IME-t Bluetooth billentyűzeteket.
>  
> Bár az IME-t a képernyőn megjelenő billentyűzettel együtt használja, továbbra is használhatja a billentyűzetet Bluetooth gépelje be az angol nyelvet. A billentyűzetek közötti váltáshoz nyomja le a tilde karakter **~** () gombot.
