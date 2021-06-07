---
title: Egyéni alkalmazások kezelése a HoloLenshez (1. generációs)
description: Megtudhatja, hogyan telepíthet, távolíthat el és telepíthet saját holografikus alkalmazásokat HoloLens-eszközökön a Eszközportál és Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378061"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Egyéni alkalmazások kezelése a HoloLenshez (1. generációs)

A HoloLens számos meglévő alkalmazást támogat a Microsoft Store, valamint a kifejezetten a HoloLenshez készült új alkalmazásokat. Ez a cikk az egyéni holografikus alkalmazásokkal foglalkozik.  

További információ az áruházbeli alkalmazásokról: [Alkalmazások kezelése az áruházban.](holographic-store-apps.md)

> [!IMPORTANT]
> Az alábbi információk a HoloLens (1. generációs), más néven HoloLens Developer Edition kiadáshoz készültek. Az ilyen alkalmazások eszközportálon keresztüli telepítése és az alkalmazások Visual Studio történő telepítése gyakori volt. Nagyvállalati környezetek esetén nem javasoljuk a Fejlesztői mód engedélyezését, amelyet mindkét módszer használ. Ha érdekli egy biztonságos alkalmazástelepítési módszer, tekintse át az [Alkalmazáskezelés: Áttekintés témakört.](app-deploy-overview.md)
>
> Ha a HoloLens 2-eszközök alkalmazástelepítésének fejlesztői módszerét keresi, tekintse meg a következőt:
> - [Eszközportál: Alkalmazás telepítése](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Alkalmazások Visual Studio és hibakeresése a Visual Studio használatával](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Egyedi alkalmazások telepítése

Saját alkalmazásokat telepíthet a HoloLensre a Eszközportál vagy az alkalmazások központi telepítéssel a Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Alkalmazáscsomag telepítése a Eszközportál

1. Hozzon létre kapcsolatot a [Eszközportál](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) a cél HoloLenshez.

1. A bal oldali navigációs sávon lépjen az **Alkalmazások lapra.**

1. Az **Alkalmazáscsomag alatt** keresse meg az alkalmazáshoz társított .appx fájlt.

   > [!IMPORTANT]
   > Győződjön meg arról, hogy a társított függőségi és tanúsítványfájlokra hivatkozik.

1. Válassza a **Go lehetőséget.**

   > [!div class="mx-imgBorder"]
   > ![Alkalmazásűrlap telepítése Windows eszközportál a Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Üzembe helyezés a Microsoft Visual Studio 2015-ről

1. Nyissa meg az alkalmazás Visual Studio megoldását (.sln-fájl).

1. Nyissa meg a projekt **Properties (Tulajdonságok) tulajdonságát.**

1. Válassza ki a következő buildkonfigurációt: **Master/x86/Remote Machine.**

1. A Távoli gép **kiválasztásakor:**
   - Győződjön meg arról, hogy a cím Wi-Fi HoloLens IP-címére mutat.
   - Állítsa a **hitelesítést Universal (Unencrypted Protocol) (Univerzális (titkosítatlan protokoll) ) beállításra.**
   
1. Készítse el a megoldást.

1. Az alkalmazásnak a fejlesztői számítógépről a HoloLensben való üzembe helyezéséhez válassza a **Távoli gép lehetőséget.** Ha már rendelkezik meglévő buildel a HoloLensen, válassza az **Igen** lehetőséget az újabb verzió telepítéséhez.  

   ![Távoli gép üzembe helyezése az alkalmazások Microsoft HoloLens a Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. Az alkalmazás automatikusan telepítve és automatikusan elindul a HoloLensen.

Miután telepítette az alkalmazást, az a következő listában **Minden alkalmazás** meg: (**Start**  >  **Minden alkalmazás**).
