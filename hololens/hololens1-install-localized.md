---
title: A HoloLens honosított verzióinak telepítése
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378223"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>A HoloLens honosított verzióinak telepítése (1. generációs)

Ahhoz, hogy átváltson a HoloLens kínai vagy japán verziójára, a Windows Device Recovery Tool (WDRT) használatával le kell töltenie a nyelvhez szükséges buildet egy számítógépre, majd telepítenie kell a HoloLensen.

> [!IMPORTANT]
> A WDRT használatával a HoloLens kínai vagy japán buildje törli a meglévő adatokat, például a személyes fájlokat és beállításokat a HoloLensből. 

1. A számítógépen töltse le és telepítse a [Windows Device Recovery Tool (WDRT) eszközt.](https://support.microsoft.com/help/12379)
1. Töltse le a csomagot a számítógépére a kívánt nyelvhez:  [Egyszerűsített kínai vagy](https://aka.ms/hololensdownload-ch) [japán](https://aka.ms/hololensdownload-jp).
1. A letöltés befejezése után válassza a **Letöltések Fájlkezelő**  >  **lehetőséget.** Kattintson a jobb gombbal az előbb letöltött tömörített mappára, és válassza az Extract all Extract **(Összes** kibontás) lehetőséget a  >   kicsomagoláshoz.
1. Csatlakoztassa a HoloLenst a számítógépéhez a kiszállító mikro-USB-kábellel. (Ez akkor is működik a legjobban, ha más kábelekkel csatlakoztatta a HoloLenst.)
1. Miután az eszköz automatikusan észleli a HoloLenst, válassza a Microsoft HoloLens csempét.
1. A következő képernyőn válassza a **Manuális** csomagválasztás lehetőséget, és válassza ki azt a telepítőfájlt, amely a   4. lépésben kicsomagolt mappában található. (Keresse meg a ".ffu" kiterjesztésű fájlt.) 
1. Válassza **a Szoftver telepítése lehetőséget,** és kövesse az utasításokat. 
1. A build telepítése után a HoloLens telepítése automatikusan elindul. Helyezze az eszközre, és kövesse a beállítási utasításokat. 

Ha végzett a beállítással, kattintson a Beállítások frissítése & Security Windows Insider Program elemre, és ellenőrizze, hogy konfigurálva van-e a legújabb előzetes verziójú  >    >  buildek fogadására. Az angol előzetes buildhez Windows Insider Program a HoloLens kínai és japán verziói is naprakészek maradnak a legújabb előzetes verziójú buildekkel.

> [!NOTE]
>  
> - A Beállítások alkalmazás nem használható a rendszer nyelvének angol, japán és kínai nyelven való módosítására. Az eszközrendszer nyelvének kizárólag az új buildek flash (flash) használata támogatott.
> - Bár a képernyőn megjelenő Pinyin-billentyűzettel egyszerűsített kínai vagy japán szöveget is beírhat, az egyszerűsített kínai vagy japán szöveg Bluetooth-hardveres billentyűzettel való begépelése jelenleg nem támogatott.  Kínai vagy japán HoloLensen azonban továbbra is használhatja a Bluetooth-billentyűzetet az angol nyelv begépelésével (a hardveres billentyűzet angol nyelvű begépelésével a ~ billentyű lenyomása után válthat).
