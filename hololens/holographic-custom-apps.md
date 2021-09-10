---
title: Egyéni alkalmazások kezelése HoloLens (1. generációs)
description: Útmutató egyéni holografikus alkalmazások telepítéséhez, eltávolításához és oldalbetöltéséhez HoloLens eszközökre a Eszközportál és Visual Studio.
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
ms.openlocfilehash: b6769c36f821ee3619ac9b62efd637ac561192bb
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427222"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Egyéni alkalmazások kezelése HoloLens (1. generációs)

HoloLens számos meglévő alkalmazást támogat a Microsoft Store, valamint a kifejezetten a HoloLens. Ez a cikk az egyéni holografikus alkalmazásokkal foglalkozik.  

További információ az áruházbeli alkalmazásokról: [Alkalmazások kezelése az áruházban.](holographic-store-apps.md)

> [!IMPORTANT]
> A következő információ jött létre a HoloLens (1. generációs), más néven HoloLens Developer Edition kiadáshoz. Az ilyen alkalmazások eszközportálon keresztüli telepítése és az alkalmazások Visual Studio történő telepítése gyakori volt. Nagyvállalati környezetek esetén nem javasoljuk a Fejlesztői mód engedélyezését, amelyet mindkét módszer használ. Ha érdekli egy biztonságos alkalmazástelepítési módszer, tekintse át az [Alkalmazáskezelés: Áttekintés témakört.](app-deploy-overview.md)
>
> Ha az alkalmazástelepítés fejlesztői módszerét keresi HoloLens 2 eszköz esetén, tekintse meg a következőt:
>
> - [Eszközportál: Alkalmazás telepítése](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Alkalmazások Visual Studio és hibakeresése a Visual Studio használatával](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Egyedi alkalmazások telepítése

Saját alkalmazásokat telepíthet a HoloLens a Eszközportál vagy az alkalmazások központi telepítéséhez a Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Alkalmazáscsomag telepítése a Eszközportál

1. Hozzon létre kapcsolatot a [Eszközportál](/windows/mixed-reality/using-the-windows-device-portal) és a cél HoloLens.

1. A bal oldali navigációs sávon lépjen az **Alkalmazások lapra.**

1. Az **Alkalmazáscsomag alatt** keresse meg az alkalmazáshoz társított .appx fájlt.

   > [!IMPORTANT]
   > Győződjön meg arról, hogy a társított függőségi és tanúsítványfájlokra hivatkozik.

1. Válassza a **Go lehetőséget.**

   > [!div class="mx-imgBorder"]
   > ![Telepítse az alkalmazásűrlap Windows Eszközportál a Microsoft HoloLens.](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Üzembe helyezés a Microsoft Visual Studio 2015-ről

1. Nyissa meg az alkalmazás Visual Studio megoldását (.sln fájl).

1. Nyissa meg a projekt **Properties (Tulajdonságok) tulajdonságát.**

1. Válassza ki a következő buildkonfigurációt: **Master/x86/Remote Machine.**

1. A Távoli gép **kiválasztásakor:**
   - Győződjön meg arról, hogy a cím a Wi-Fi IP-címére HoloLens.
   - Állítsa a **hitelesítést Universal (Unencrypted Protocol) (Univerzális (Titkosítatlan protokoll) ) beállításra.**
   
1. Készítse el a megoldást.

1. Ha a fejlesztői számítógépről telepítenie kell az alkalmazást a HoloLens válassza a **Távoli gép lehetőséget.** Ha már létezik build a HoloLens válassza az **Igen** lehetőséget az újabb verzió telepítéséhez.  

   ![Távoli gép üzembe helyezése az alkalmazások Microsoft HoloLens a Visual Studio.](images/vs2015-remotedeployment.jpg)  
   
1. Az alkalmazás automatikusan telepítve és automatikusan elindul a HoloLens.

Miután telepített egy alkalmazást, az alkalmazás a  Minden alkalmazás listájában található (**Minden alkalmazás**  >  ).
