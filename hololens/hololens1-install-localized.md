---
title: Az alkalmazás honosított verzióinak HoloLens
description: Ismerje meg, hogyan telepítheti a HoloLens (1. generációs) honosított verzióit, beleértve a kínai és a japán verziót is.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427060"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>A HoloLens honosított verzióinak telepítése (1. generációs)

Az HoloLens kínai vagy japán verziójára való váltáshoz a Windows Device Recovery Tool (WDRT) eszközzel kell letöltenie a nyelvhez szükséges buildet a számítógépre, majd telepítenie kell a HoloLens.

> [!IMPORTANT]
> A WDRT használatával a kínai vagy japán nyelvű buildek HoloLens törli a meglévő adatokat, például a személyes fájlokat és beállításokat a HoloLens. 

1. Töltse le és telepítse a Windows [Device Recovery Tool (WDRT) eszközt.](https://support.microsoft.com/help/12379)
1. Töltse le a csomagot a számítógépére a kívánt nyelvhez:  [Egyszerűsített kínai vagy](https://aka.ms/hololensdownload-ch) [japán](https://aka.ms/hololensdownload-jp).
1. A letöltés befejezése után válassza a **Letöltések Fájlkezelő**  >  **lehetőséget.** Kattintson a jobb gombbal az előbb letöltött tömörített mappára, és válassza az Extract all Extract **(Összes** kibontás) lehetőséget a  >   kicsomagoláshoz.
1. Csatlakozás a HoloLens a számítógépére a kiszállító mikro-USB-kábellel. (Ez akkor is működik a legjobban, ha más kábelekkel csatlakoztatta HoloLens-t.)
1. Miután az eszköz automatikusan észleli a HoloLens, válassza a Microsoft HoloLens csempét.
1. A következő képernyőn válassza a **Manuális** csomagválasztás lehetőséget, és válassza ki azt a telepítőfájlt, amely a   4. lépésben kicsomagolt mappában található. (Keresse meg a ".ffu" kiterjesztésű fájlt.) 
1. Válassza **a Szoftver telepítése lehetőséget,** és kövesse az utasításokat. 
1. A build telepítése után a HoloLens automatikusan elindul. Helyezze az eszközt, és kövesse a beállítási utasításokat. 

Ha végzett a beállítással, a Gépház Update & Security Windows Insider Program lapra lépés után ellenőrizze, hogy a legújabb előzetes verziójú buildek fogadására van-e  >    >  konfigurálva. Az angol előzetes buildhez Windows Insider Program a HoloLens a legújabb előzetes buildekkel naprakészen tartja a kínai és a japán változatot.

> [!NOTE]
>  
> - A Gépház nem módosíthatja a rendszer nyelvét angol, japán és kínai nyelven. Az eszközrendszer nyelvének kizárólag az új buildek flash (flash) használata támogatott.
> - Bár a képernyőn megjelenő Pinyin billentyűzettel egyszerűsített kínai vagy japán nyelvű szöveget is beírhat, az egyszerűsített kínai vagy japán nyelvű szövegek Bluetooth hardveres billentyűzettel való begépelése jelenleg nem támogatott.  Kínai vagy japán nyelvű HoloLens azonban továbbra is használhatja a Bluetooth-billentyűzetet az angol nyelvű szöveg begépelhez (ha a hardveres billentyűzetet angolra való begépelni, nyomja le a ~ billentyűt).
