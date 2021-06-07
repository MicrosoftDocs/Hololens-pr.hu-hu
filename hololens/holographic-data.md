---
title: Fájlok megkeresása és mentése a HoloLensben
description: Megtudhatja, hogyan használhatja Fájlkezelő HoloLensben a fájlok megnyitásához, megtekintéséhez és kezeléséhez a vegyes valóságú eszközön.
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
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378026"
---
# <a name="find-open-and-save-files-on-hololens"></a>Fájlok megkeresését, megnyitását és mentését a HoloLensben

A HoloLensen létrehozott fájlok, köztük a fényképek és videók közvetlenül a HoloLens-eszközre vannak mentve. Ezeket ugyanúgy megtekintheti és kezelheti, mint a fájlokat a Windows 10:

- A helyi Fájlkezelő alkalmazással férhet hozzá.
- Egy alkalmazás tárhelyében.
- Egy speciális mappában (például a videóban vagy a zenetárban).
- Alkalmazásokat és fájlválasztót (például OneDrive-ot) tartalmazó tárolási szolgáltatás használata.
- A HoloLenshez csatlakoztatott asztali számítógép használata USB-kábelen keresztül, MTP (Media Transfer Protocol) támogatással.

## <a name="view-files-on-hololens-using-file-explorer"></a>Fájlok megtekintése a HoloLensben a Fájlkezelő

> Az összes HoloLens 2-eszközre és HoloLensre (1. generációs) vonatkozik a [HoloLens Windows 10 2018. áprilisi frissítése (RS4)](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)óta.

A Fájlkezelő a HoloLensben fájlokat, köztük 3D-objektumokat, dokumentumokat és képeket is megtekinthet és kezelhet az eszközön. A **kezdéshez**   >  **Minden alkalmazás**   >  **Fájlkezelő** a Start menüt.

> [!TIP]
> Ha a bal felső panelen nincsenek Fájlkezelő, válassza az **Ez az eszköz** lehetőséget.

Ha nem lát fájlokat a Fájlkezelő a "Legutóbbi" szűrő lehet aktív (az óra ikon ki van emelve a bal oldali panelen). Ennek kijavításaként  válassza az Ez az eszköz dokumentum ikont a bal oldali panelen (az óra ikon alatt), vagy nyissa meg a menüt, és válassza az Ez az **eszköz lehetőséget.**

## <a name="find-and-view-your-photos-and-videos"></a>Fényképek és videók megkeresve és megtekintése

[A vegyes valóságú rögzítéssel](holographic-photos-and-videos.md) vegyes valóságú fényképeket és videókat készíthet a HoloLensen.  Ezek a fényképek és videók az eszköz Camera Roll mappájába vannak mentve.

A HoloLens-sel készített fényképeket és videókat a következővel lehet elérni:

- A Camera Roll elérése közvetlenül a [Photos alkalmazásban.](holographic-photos-and-videos.md)
- fényképek és videók feltöltése felhőalapú tárhelyre a fényképek és videók OneDrive-ba való szinkronizálása által.
- a Vegyes valóság rögzítése lap [Windows eszközportál.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)

### <a name="photos-app"></a>Photos alkalmazás

A Photos alkalmazás a **Start** menü egyik alapértelmezett alkalmazása, amely beépített a HoloLenshez. További információ a [tartalmak a Photos alkalmazással való megtekintéséről.](holographic-photos-and-videos.md)

A [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) alkalmazást az alkalmazásból is Microsoft Store a fényképek más eszközökkel való szinkronizálásához.

### <a name="onedrive-app"></a>OneDrive alkalmazás

[A OneDrive](https://onedrive.live.com/) lehetővé teszi a fényképek és videók bármely eszközzel és felhasználóval való hozzáférését, kezelését és megosztását. A HoloLensben rögzített fényképek és videók eléréséhez töltse le a [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) alkalmazást a HoloLens Microsoft Store-fájlból. A letöltés után nyissa meg a OneDrive alkalmazást, válassza a **Beállítások** Kamera feltöltése lehetőséget, majd kapcsolja  >  be a **Kamera feltöltése beállítást.**

### <a name="connect-to-a-pc"></a>Csatlakozás számítógéphez

Ha a HoloLens [a 2018.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) áprilisi vagy újabb Windows 10-frissítést futtatja, csatlakoztathatja a HoloLenst egy Windows 10-számítógéphez USB-kábellel, hogy az MTP (médiaátviteli protokoll) használatával böngésszen az eszközön található fényképek és videók között. Ha pin-kód vagy jelszó van beállítva az eszközön, győződjön meg arról, hogy az eszköz fel van oldva a fájlok tallózásához.  

Ha engedélyezte a [Windows eszközportál,](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)a használatával tallózhatja, lekérheti és kezelheti az eszközön tárolt fényképeket és videókat.

## <a name="access-files-within-an-app"></a>Alkalmazáson belüli fájlok elérése

Ha egy alkalmazás fájlokat ment az eszközön, az alkalmazással elérheti őket.

### <a name="requesting-files-from-another-app"></a>Fájlok kérése egy másik alkalmazásból

Egy alkalmazás kérheti egy fájl mentését, vagy fájlválasztók használatával megnyithat egy fájlt egy [másik alkalmazásból.](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)

### <a name="known-folders"></a>Ismert mappák

A HoloLens számos olyan ismert mappát [támogat,](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) amelyek hozzáférését az alkalmazások kérhetik.

## <a name="view-hololens-files-on-your-pc"></a>HoloLens-fájlok megtekintése a számítógépen

Más mobileszközökhöz hasonlóan csatlakoztassa a HoloLenst az asztali számítógéphez az MTP (Media Transfer Protocol) használatával, és nyissa meg a Fájlkezelő-t a számítógépen a HoloLens-kódtárak eléréséhez az egyszerű átvitel érdekében.

A HoloLens-fájlok Fájlkezelő a számítógépen:

1. Jelentkezzen be a HoloLensbe, majd csatlakoztassa a számítógéphez a HoloLenshez csatlakoztatott USB-kábellel.

1. Válassza **az Eszköz megnyitása lehetőséget a Fájlkezelő** megtekintéséhez, vagy nyissa Fájlkezelő a számítógépen, és navigáljon az eszközre.

A HoloLens adataihoz kattintson a jobb gombbal az eszköz nevére a Fájlkezelő, majd válassza a Tulajdonságok **lehetőséget.**

> [!NOTE]
> A HoloLens (1. generációs) nem támogatja a külső merevlemezek vagy SD-kártyák csatlakoztatását.

## <a name="sync-to-the-cloud"></a>Szinkronizálás a felhővel

A HoloLensben tárolt fényképek és egyéb fájlok felhőbe való szinkronizáláshoz telepítse és állítsa be a OneDrive-ot a HoloLensen. A OneDrive-ot a HoloLens Microsoft Store megkeresésével keresheti meg.

A HoloLens nem biztonsági mentést ad az alkalmazás fájljairól és adatairól, ezért jó ötlet a fontos adatokat a OneDrive-ra menteni. Így ha alaphelyzetbe állítja az eszközt, vagy eltávolít egy alkalmazást, az adatokról biztonsági adatokat fog kapni.
