---
title: Fájlok megkeresása és mentése a HoloLens
description: Megtudhatja, hogyan használhatja Fájlkezelő a HoloLens vegyes valóságú eszközön lévő fájlok megnyitásához, megtekintéséhez és kezeléséhez.
keywords: how-to, file picker, files, photos, videos, pictures, OneDrive, storage, file explorer, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428353"
---
# <a name="find-open-and-save-files-on-hololens"></a>Fájlok megkeresása, megnyitása és mentése a HoloLens

A rendszer a HoloLens létrehozott fájlokat, köztük a fényképeket és videókat is, közvetlenül a saját HoloLens menti. Ezeket ugyanúgy megtekintheti és kezelheti, mint a fájlokat a Windows 10:

- A helyi Fájlkezelő alkalmazással férhet hozzá.
- Egy alkalmazás tárhelyében.
- Egy speciális mappában (például a videóban vagy a zenetárban).
- Alkalmazásokat és fájlválasztót (például alkalmazás- és fájlválasztót) tartalmazó tárolási szolgáltatás OneDrive.
- USB-kábelen keresztül csatlakoztatott asztali HoloLens MTP (Media Transfer Protocol) támogatással.

## <a name="view-files-on-hololens-using-file-explorer"></a>Fájlok megtekintése a HoloLens a Fájlkezelő

> A 2018. áprilisi Windows 10 (RS4) frissítéstől HoloLens 2 eszközre és HoloLens [-re (1. generációs) vonatkozik](/windows/mixed-reality/release-notes-april-2018)a HoloLens.

A Fájlkezelő a HoloLens megtekintheti és kezelheti az eszközön lévő fájlokat, beleértve a 3D-objektumokat, dokumentumokat és képeket. A **kezdéshez**   >  **Minden alkalmazás**   >  **Fájlkezelő** a Start menüt.

> [!TIP]
> Ha a bal felső panelen nincsenek Fájlkezelő, válassza az **Ez az eszköz** lehetőséget a bal felső panelen.

Ha nem lát fájlokat a Fájlkezelő a "Legutóbbi" szűrő lehet aktív (az óra ikon ki van emelve a bal oldali panelen). Ennek kijavításaként  válassza az Ez az eszköz dokumentum ikont a bal oldali panelen (az óra ikon alatt), vagy nyissa meg a menüt, és válassza az Ez az **eszköz lehetőséget.**

## <a name="find-and-view-your-photos-and-videos"></a>Fényképek és videók megkeresve és megtekintése

[A vegyes valóságú rögzítés](holographic-photos-and-videos.md) lehetővé teszi, hogy vegyes valóságú fényképeket és videókat készítsen HoloLens.  Ezek a fényképek és videók az eszköz Camera Roll mappájába vannak mentve.

A következő HoloLens férhet hozzá a fényképekhez és videókhoz:

- A Camera Roll elérése közvetlenül a [Photos alkalmazásban.](holographic-photos-and-videos.md)
- fényképeket és videókat tölthet fel a felhőtárhelyre a fényképek és videók szinkronizálása OneDrive.
- a Vegyes valóság rögzítése lap [Windows Eszközportál.](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)

### <a name="photos-app"></a>Fényképek alkalmazás

A Photos alkalmazás a **Start** menü egyik alapértelmezett alkalmazása, és beépített HoloLens. További információ a [tartalmak a Photos alkalmazással való megtekintéséről.](holographic-photos-and-videos.md)

Az alkalmazás OneDrive [is](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) telepíthető a Microsoft Store, hogy más eszközökkel szinkronizálja a fényképeket.

### <a name="onedrive-app"></a>OneDrive alkalmazás

[OneDrive](https://onedrive.live.com/) lehetővé teszi a fényképek és videók bármely eszközzel és felhasználóval való hozzáférését, kezelését és megosztását. A HoloLens rögzített fényképek és videók eléréséhez töltse [](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) le OneDrive alkalmazás Microsoft Store a HoloLens. A letöltés után nyissa meg a OneDrive alkalmazást, válassza a Gépház feltöltése lehetőséget, majd kapcsolja be a  >   **Kamera feltöltése lehetőséget.**

### <a name="connect-to-a-pc"></a>Csatlakozás pc-re

Ha a HoloLens [a Windows 10 2018.](/windows/mixed-reality/release-notes-april-2018) áprilisi vagy újabb frissítését futtatja, csatlakoztathatja az HoloLens-t egy Windows 10-számítógéphez USB-kábellel, hogy az MTP (media transfer Protocol) használatával böngésszen az eszközön található fényképek és videók között. Ha pin-kód vagy jelszó van beállítva az eszközön, győződjön meg arról, hogy az eszköz fel van oldva a fájlok tallózásához.  

Ha engedélyezte a [Windows Eszközportál,](/windows/mixed-reality/using-the-windows-device-portal)a használatával tallózhatja, lekérheti és kezelheti az eszközön tárolt fényképeket és videókat.

## <a name="access-files-within-an-app"></a>Alkalmazáson belüli fájlok elérése

Ha egy alkalmazás fájlokat ment az eszközre, az alkalmazással elérheti őket.

### <a name="requesting-files-from-another-app"></a>Fájlok kérése egy másik alkalmazásból

Egy alkalmazás kérheti egy fájl mentését, vagy megnyithat egy fájlt egy másik alkalmazásból [fájlválasztók használatával.](/windows/mixed-reality/app-model#file-pickers)

### <a name="known-folders"></a>Ismert mappák

HoloLens számos olyan ismert mappát [támogat,](/windows/mixed-reality/app-model#known-folders) amelyek hozzáférését az alkalmazások kérhetik.

## <a name="view-hololens-files-on-your-pc"></a>A HoloLens megtekintése a számítógépen

Más mobileszközökhöz hasonlóan csatlakoztassa HoloLens számítógépéhez az MTP (Media Transfer Protocol) segítségével, és nyissa meg a Fájlkezelő-t a számítógépen a HoloLens-kódtárak eléréséhez az egyszerű átvitel érdekében.

A számítógép HoloLens fájlok Fájlkezelő a számítógépen:

1. Jelentkezzen be a HoloLens, majd csatlakoztassa a számítógéphez az usb-kábellel, amely a HoloLens.

1. Válassza **az Eszköz megnyitása lehetőséget a Fájlkezelő** megtekintéséhez, Fájlkezelő nyissa meg a Fájlkezelő a számítógépen, és keresse meg az eszközt.

A saját számítógépével kapcsolatos HoloLens jobb gombbal kattintson az eszköz nevére a Fájlkezelő, majd válassza a Tulajdonságok **lehetőséget.**

> [!NOTE]
> HoloLens (1. generációs) nem támogatja a külső merevlemezhez vagy SD-kártyákhoz való csatlakozást.

## <a name="sync-to-the-cloud"></a>Szinkronizálás a felhővel

Ha fényképeket és más fájlokat HoloLens a felhőbe, telepítse és OneDrive a HoloLens. A OneDrive megkeresi a saját Microsoft Store a HoloLens.

HoloLens nem biztonsági mentést ad az alkalmazás fájljairól és adatairól, ezért jó ötlet a fontos dolgokat a OneDrive. Így ha alaphelyzetbe állítja az eszközt, vagy eltávolít egy alkalmazást, az adatokról biztonsági adatokat fog kapni.
