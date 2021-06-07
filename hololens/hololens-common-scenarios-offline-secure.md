---
title: Gyakori forgatókönyvek – Offline biztonságos HoloLens 2
description: Ismerje meg, hogyan állíthat be offline biztonságos üzembe helyezést és alkalmazástelepítési forgatókönyvet a HoloLens-eszközök üzembe helyezéséhez.
keywords: HoloLens, felügyelet, offline, offline biztonságos
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378013"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Gyakori forgatókönyvek – Offline biztonságos HoloLens 2

## <a name="overview"></a>Áttekintés

Ez az útmutató útmutatást nyújt egy minta kiépítési csomag alkalmazásához, amely le fogja zárni a HoloLens 2-t biztonságos környezetekben való használatra az alábbi korlátozásokkal:

-   Tiltsa le a Wi-Fi-t.
-   Tiltsa le a BlueTobellt.
-   Mikrofonok letiltása.
-   Megakadályozza a kiépítési csomagok hozzáadását vagy eltávolítását.
-   A fenti korlátozott összetevők bármelyikét egyetlen felhasználó sem engedélyezheti.

[![Offline biztonságos forgatókönyv ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Előkészítés

Windows 10 számítógép beállítása
1. [Töltse le a legújabb HoloLens 2 operációsrendszer-fájlt](https://aka.ms/hololens2download) közvetlenül egy számítógépre. 
   1. Ennek a konfigurációnak a támogatását az 19041.1117-es és az azt feletti build tartalmazza.
1. Az Advanced Recovery Companion (ARC) eszköz letöltése/telepítése a [Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) gépre
1. Töltse le/telepítse a [windowsos konfigurációtervező (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) legújabb eszközét a Microsoft Store gépére.
1. [Töltse le a OfflineSecureHL2_Sample mappát a projektfájlokkal](https://aka.ms/HoloLensDocs-SecureOfflineSample) együtt a PPKG felépítéséhez.
1. Készítse elő az offline [Line of Business alkalmazást a PPKG üzembe helyezéséhez.](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Konfigurálás

Biztonságos konfiguráció kiépítési csomagjának összeállítása

1. Indítsa el a WCD eszközt a számítógépén.
1. Válassza **a File -> Open project (Projekt megnyitása) lehetőséget.**
  1. Navigáljon a korábban mentett OfflineSecureHL2_Sample mappához, és válassza a következőt: OfflineSecureHL2_Sample.icdproj.xml
1. Meg kell nyitnia a projektet, és meg kell lennie az Elérhető testreszabások listájának:

   > [!div class="mx-imgBorder"]
   > ![Képernyőkép a WCD-ben megnyitott konfigurációs csomagról](images/offline-secure-sample-wcd.png)

   Az ebben a kiépítési csomagban beállított konfigurációk:
   
   |     Elem                                                |     Beállítás                       |     Leírás                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Fiókok / Felhasználók                                    |     Helyi felhasználónév és & jelszó    |     Ezekhez az offline eszközökhöz egyetlen felhasználónevet és jelszót kell beállítani és megosztani az eszköz összes felhasználója számára.          |
   |     Első élmény / HoloLens / SkipCalibration       |     Igaz                          |     Csak a kezdeti eszközbeállítás során hagyja ki a hitelesítést                                                                             |
   |     Első élmény / HoloLens / SkipTraining          |     Igaz                          |     Kihagyja az eszköz betanítása a kezdeti eszközbeállítás során                                                                              |
   |     Első tapasztalat / HoloLens / Wi-Fi                  |     Igaz                          |     Kihagyja Wi-Fi konfigurációs lépését a kezdeti eszközbeállítás során                                                                                 |
   |     Szabályzatok/Kapcsolatok/AllowBlueto adat                |     Nem                            |     A Bluetooth letiltása                                                                                                             |
   |     Szabályzatok/Tapasztalat/AllowCortana                    |     Nem                            |     Letiltja Cortanát (a lehetséges problémák kiküszöböléséhez, mivel a mikrofonok le vannak tiltva)                                          |
   |     Policies/MixedReality/MicrophoneDisabled            |     Igen                           |     Letiltja a mikrofont                                                                                                            |
   |     Szabályzatok/adatvédelem/LetAppsAccessLocation              |     Megtagadás kényszerítve                    |     Megakadályozza, hogy az alkalmazások hozzáférjenek a helyadatokhoz (a lehetséges problémák kiküszöbölése érdekében, mivel a helykövetés le van tiltva)    |
   |     Szabályzatok/Adatvédelem/LetAppsAccessMicrophone            |     Megtagadás kényszerítve                    |     Megakadályozza, hogy az alkalmazások hozzáférjenek a mikrofonhoz (a lehetséges problémák kiküszöbölése érdekében, mivel a mikrofonok le vannak tiltva)           |
   |     Policies/Security/AllowAddProvisioningPackage       |     Nem                            |     Megakadályozza, hogy bárki olyan kiépítési csomagokat adjon hozzá, amelyek megpróbálhatják felülbírálni a zárolt szabályzatokat.                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     Nem                            |     Megakadályozza, hogy bárki eltávolítsa ezt a zárolt kiépítési csomagot.                                                           |
   |     Házirendek/Rendszer/AllowLocation                       |     Nem                            |     Megakadályozza, hogy az eszköz helyadatokat kövessen nyomon.                                                                        |
   |     Szabályzatok/Wi-Fi/AllowWiFi                             |     Nem                            |     Letiltja a Wi-Fi                                                                                                                 |

1. A Futásidejű beállítások alatt válassza a **Fiókok / Felhasználók / Felhasználónév: Holo / Jelszó lehetőséget.**

   Jegyezze fel a jelszót, és szükség esetén állítsa alaphelyzetbe.

1. Lépjen a UniversalAppInstall /UserContextApp lapra, és konfigurálja az ezen eszközökre telepíteni fog [LOB](app-deploy-provisioning-package.md) alkalmazást.

   > [!div class="mx-imgBorder"]
   > ![Az alkalmazás WCD-ben való hozzáadásának helyének képernyőképe.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Ha elkészült, válassza az "Exportálás" gombot, és kövesse az összes kérést, amíg létre nem jön a kiépítési csomag.

   > [!div class="mx-imgBorder"]
   > ![Képernyőkép a csomag Exportálás gombjáról a WCD-ben.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Üzembe helyezés

1. Csatlakoztassa a HL2-t a Windows 10 számítógépéhez USB-kábelen keresztül.
1. Indítsa el az ARC eszközt, és válassza a **HoloLens 2 lehetőséget**

   ![A HoloLens 2 tiszta perjeles kezdőképernyője](images/ARC2.png)

1. A következő képernyőn válassza a **Manuális csomagválasztás lehetőséget.**

   ![HoloLens 2 ARC információs képernyő](images/arc_device_info.png)

1. Keresse meg a korábban letöltött .ffu fájlt, és válassza a **Megnyitás lehetőséget.**
1. A Figyelmeztetés lapon válassza a Folytatás **lehetőséget.**

   ![HoloLens 2 ARC figyelmeztető képernyő](images/arc_warning.png)

1. Várja meg, amíg az ARC eszköz befejezi a HoloLens 2 operációs rendszer telepítését.
1. Miután az eszköz befejezte a telepítést és elindul a rendszer, lépjen a Fájlkezelő könyvtárba, és másolja a korábban mentett PPKG-fájlt az eszközmappába.

   > [!div class="mx-imgBorder"]
   > ![PPKG-fájl a számítógépen Fájlkezelő ablakban.](images/offline-secure-file-explorer.png)

1. A HoloLens 2-ben nyomja le a következő gomb kombinált gombra a kiépítési csomag futtatásához: Koppintson egyszerre a **Kötet** le és a **Bekapcsológomb** gombra.
1. A rendszer kérni fogja a kiépítési csomag alkalmazását, majd válassza a **Megerősítés lehetőséget.**
1. Ha a kiépítési csomag befejeződött, kattintson az **OK gombra.**
1. Ezután be kell jelentkeznie az eszközre a megosztott helyi fiókkal és jelszóval.

## <a name="maintain"></a>Karbantartás

Ezzel a konfigurációval javasoljuk, hogy indítsa újra a fenti folyamatot, és perjelelje újra az eszközt az ARC eszközzel, és alkalmaz egy új PPKG-t az operációs rendszer és/vagy alkalmazás(ek) frissítéséhez.
