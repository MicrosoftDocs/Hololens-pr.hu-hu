---
title: Gyakori forgatókönyvek – Offline biztonságos HoloLens 2
description: Ismerje meg, hogyan állíthat be offline biztonságos üzembe helyezést és alkalmazástelepítési forgatókönyvet a HoloLens üzembe helyezéssel.
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
ms.openlocfilehash: 10d1955249630202a05fbf2057e1d175855ce0b5
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189120"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Gyakori forgatókönyvek – Offline biztonságos HoloLens 2

## <a name="overview"></a>Áttekintés

Ez az útmutató útmutatást nyújt egy minta kiépítési csomag alkalmazásához, amely a 2. HoloLens-t zárolja a biztonságos környezetekben való használathoz, a következő korlátozásokkal:

-   Tiltsa le a Wi-Fi-t.
-   Tiltsa le a BlueTo fiókokat.
-   Mikrofonok letiltása.
-   Megakadályozza a kiépítési csomagok hozzáadását vagy eltávolítását.
-   A fenti korlátozott összetevők bármelyikét egyetlen felhasználó sem engedélyezheti.

[![Offline biztonságos forgatókönyv. ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Előkészítés

Windows 10 Számítógép beállítása
1. [Töltse le a HoloLens 2 operációsrendszer-fájlt](https://aka.ms/hololens2download) közvetlenül a számítógépre. 
   1. Ennek a konfigurációnak a támogatását az 19041.1117-es és azt feletti build tartalmazza.
1. Az Advanced Recovery Companion (ARC) eszköz letöltése/telepítése a [Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) gépre
1. Töltse le/telepítse [a Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) eszközét a Microsoft Store gépére.
1. [Töltse le a OfflineSecureHL2_Sample mappát a projektfájlokkal](https://aka.ms/HoloLensDocs-SecureOfflineSample) együtt a PPKG felépítéséhez.
1. Készítse elő az offline [Üzletági alkalmazást a PPKG üzembe helyezéséhez.](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Konfigurálás

Biztonságos konfigurációs kiépítési csomag összeállítása

1. Indítsa el a WCD eszközt a számítógépén.
1. Válassza **a File -> Open project (Projekt megnyitása) lehetőséget.**
  1. Navigáljon a korábban mentett OfflineSecureHL2_Sample mappához, és válassza a következőt: OfflineSecureHL2_Sample.icdproj.xml
1. Meg kell nyitnia a projektet, és meg kell lennie a Rendelkezésre álló testreszabások listájának:

   > [!div class="mx-imgBorder"]
   > ![Képernyőkép a MEGNYITOTT konfigurációs csomagról a WCD-ben.](images/offline-secure-sample-wcd.png)

   Az ebben a kiépítési csomagban beállított konfigurációk:
   
   |     Elem                                                |     Beállítás                       |     Leírás                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Fiókok /Felhasználók                                    |     Helyi felhasználónév & jelszó    |     Ezekhez az offline eszközökhöz egyetlen felhasználónevet és jelszót kell beállítani és megosztani az eszköz összes felhasználója számára.          |
   |     Első tapasztalatok / HoloLens / SkipCalibration       |     Igaz                          |     Csak a kezdeti eszközbeállítás során hagyja ki a hitelesítést                                                                             |
   |     Első élmény / HoloLens / SkipTraining          |     Igaz                          |     Kihagyja az eszközbeképzést az eszköz kezdeti beállítása során                                                                              |
   |     Első élmény / HoloLens / Wi-Fi                  |     Igaz                          |     Kihagyja Wi-Fi konfigurációt a kezdeti eszközbeállítás során                                                                                 |
   |     Szabályzatok/Kapcsolatok/AllowBluetoue                |     No                            |     Letiltja a Bluetooth                                                                                                             |
   |     Szabályzatok/Felhasználói élmény/AllowCortana                    |     No                            |     Letiltja a Cortana (a lehetséges problémák kiküszöbölése érdekében, mivel a mikrofonok le vannak tiltva)                                          |
   |     Policies/MixedReality/MicrophoneDisabled            |     Yes                           |     Letiltja a mikrofont                                                                                                            |
   |     Szabályzatok/Adatvédelem/LetAppsAccessLocation              |     Megtagadás kényszerítve                    |     Megakadályozza, hogy az alkalmazások hozzáférjenek a helyadatokhoz (a lehetséges problémák kiküszöbölése érdekében, mivel a helykövetés le van tiltva)    |
   |     Szabályzatok/Adatvédelem/LetAppsAccessMicrophone            |     Megtagadás kényszerítve                    |     Megakadályozza, hogy az alkalmazások hozzáférjenek a mikrofonhoz (a lehetséges problémák kiküszöbölése érdekében, mivel a mikrofonok le vannak tiltva)           |
   |     Policies/Security/AllowAddProvisioningPackage       |     No                            |     Megakadályozza, hogy bárki olyan kiépítési csomagokat adjon hozzá, amelyek felülbírálhatják a zárolt szabályzatokat.                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     No                            |     Megakadályozza, hogy bárki eltávolítsa ezt a zárolt kiépítési csomagot.                                                           |
   |     Szabályzatok/Rendszer/AllowLocation                       |     No                            |     Megakadályozza, hogy az eszköz helyadatokat kövessen nyomon.                                                                        |
   |     Házirendek/WiFi/AllowWiFi                             |     No                            |     Letiltja a Wi-Fi                                                                                                                 |

1. A Runtime Gépház válassza a **Fiókok / Felhasználók / Felhasználónév: Holo / Jelszó lehetőséget.**

   Jegyezze fel a jelszót, és szükség esetén állítsa alaphelyzetbe.

1. Lépjen a UniversalAppInstall / UserContextApp lapra, és konfigurálja az ezeken az eszközökön üzembe helyezni fog [LOB-alkalmazást.](app-deploy-provisioning-package.md)

   > [!div class="mx-imgBorder"]
   > ![Képernyőkép az alkalmazás WCD-ben való hozzáadásának helyéhez.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Ha elkészült, válassza az "Exportálás" gombot, és kövesse az összes kérést, amíg létre nem jön a kiépítési csomag.

   > [!div class="mx-imgBorder"]
   > ![A csomag Exportálás gombjának képernyőképe a WCD-ben.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Üzembe helyezés

1. Csatlakozás HL2 csatlakoztatása a Windows 10 SZÁMÍTÓGÉPhez USB-kábelen keresztül.
1. Indítsa el az ARC eszközt, és válassza **a HoloLens 2. lehetőséget**

   ![HoloLens 2 tiszta perjeles kezdőképernyő.](images/ARC2.png)

1. A következő képernyőn válassza a **Manuális csomagválasztás lehetőséget.**

   ![HoloLens 2 ARC információs képernyő.](images/arc_device_info.png)

1. Keresse meg a korábban letöltött .ffu fájlt, és válassza a **Megnyitás lehetőséget.**
1. A Figyelmeztetés lapon válassza a Folytatás **lehetőséget.**

   ![HoloLens 2 ARC figyelmeztető képernyő.](images/arc_warning.png)

1. Várjon, amíg az ARC eszköz befejezi a HoloLens 2 operációs rendszer telepítését.
1. Miután az eszköz befejezte a telepítést, és újra elindul a rendszer, lépjen a Fájlkezelő, és másolja a korábban mentett PPKG-fájlt az eszközmappába.

   > [!div class="mx-imgBorder"]
   > ![PPKG-fájl a számítógépen Fájlkezelő ablakban.](images/offline-secure-file-explorer.png)

1. A 2. HoloLens nyomja le a következő gomb kombinált gombra a Kiépítési csomag futtatásához: Koppintson egyszerre a **Kötet** le és a **Bekapcsológomb** gombra.
1. A rendszer kérni fogja a kiépítési csomag alkalmazását, majd válassza a **Megerősítés lehetőséget.**
1. Ha a kiépítési csomag befejeződött, kattintson az **OK gombra.**
1. Ezután a rendszer felkéri, hogy jelentkezzen be az eszközre a megosztott helyi fiókkal és jelszóval.

## <a name="maintain"></a>Karbantartás

Ezzel a konfigurációval javasoljuk, hogy indítsa újra a fenti folyamatot, és perjelekkel perjelelje az eszközt az ARC eszközzel, és alkalmaz egy új PPKG-t az operációs rendszer és/vagy alkalmazás(ek) frissítéséhez.
