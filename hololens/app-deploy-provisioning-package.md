---
title: Kiépítési csomag
description: Ismerje meg az alkalmazások csomagolását, üzembe helyezését, üzembe helyezését és a vállalati alkalmazások üzembe helyezését HoloLens eszközökön.
keywords: app, app deployment, enterprise app deployment, provisioning
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2cb497d850ff7ba2de66f69e8ec53e6dd36b773cc13d01b038def8d539e3b0c1
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665216"
---
# <a name="provisioning-package"></a>Kiépítési csomag

A kiépítési csomagokkal előkészítheti és konfigurálhatja az eszközöket egy környezetben anélkül, hogy hozzáféréssel kellene rendelkeznie a végpontkezeléshez. Az eszközök a felhasználó identitásától, a regisztrációs állapottól, a OOBE (OOBE) használata során, illetve a telepítés során egy kiépítési csomag alkalmazásával is üzembe [helyezhetők.](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## <a name="provisioning-packages-considerations"></a>A kiépítési csomagokra vonatkozó szempontok:

* Nem nyilvános alkalmazások
* Csak USB-s oldalbetöltés
* Nincs automatikus frissítés (manuális frissítést igényel a PPKG-k segítségével)

A kiépítési csomaggal telepített alkalmazásokat a helyi gép tárolójában található tanúsítvánnyal kell aláírni. A kiépítési csomagok csak az eszköz (helyi gép) tárolójára telepíthetnek tanúsítványokat, ezért az alkalmazás és a tanúsítvány is telepíthető ugyanazokkal a kiépítési csomagokkal. Ha a tanúsítványt az MDM-ről telepíti, vagy a Tanúsítványkezelővel [telepíti,](certificate-manager.md)akkor a tanúsítványt a helyi számítógép-tárolóban kell telepítenie, hogy ezzel a módszerrel alá tudja írni a telepített alkalmazásokat.

A kiépítési csomag létrehozásához szükséges alapvető tudnivalókért látogasson el a HoloLens [provisioning (Kiépítés) HoloLens cikkére.](/hololens/hololens-provisioning) Az alkalmazások üzembe helyezéséhez speciális kiépítéssel kell kezdenie.

> [!NOTE]
> HoloLens (1. generációs) csak korlátozott mértékben támogatja az alkalmazások telepítését **(UniversalAppInstall**) egy kiépítési csomag használatával. HoloLens (1. generációs) eszközök csak az OOBE és csak a felhasználói környezet telepítése esetén támogatják az alkalmazások PPKG-n keresztüli telepítését.

## <a name="setup"></a>Telepítés

A [Windows Configuration Designerben](https://www.microsoft.com/store/productId/9NBLGGH4TX22) kövesse az alábbi négy lépést.

1. Állítsa az ApplicationManagement/AllowAllTrustedApps halmazt "Igen" -ra. Lásd: [ApplicationManagement/AllowAllTrustedApps.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)

2. Lépjen a **UniversalAppInstall**  >  **UserContextAppLicense pontra, és** adja meg **a PackageFamilyName nevet.** Lásd: [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall). Lásd még: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Használhatja a Eszközportál olyan eszközön, amelyre már telepítette az alkalmazást. Látogasson el az Alkalmazások oldalra, és nézze meg a PackageRelativeID sort, az összes információt a "!" A **PackageFamilyName .**

3. Ezután látni fogja, hogy van egy új szakasza, az **ApplicationFile.** Ezen a területen töltheti fel az appx-csomagot.

4. Attól függően, hogy megvásárolta az alkalmazást vagy saját LOB-alkalmazást épített, fel kell töltenie a licencfájlt vagy a biztonsági tanúsítványt.

    - Licencfájl: lépjen a **UniversalAppInstall**  >  **UserContextAppLicence** elemre, keresse meg a licenc helyét, és töltse fel.
    - A biztonsági fájlhoz lépjen a Tanúsítványok **lapra,** és válassza ki az .appx csomaggal együtt telepíteni kívánt tanúsítványt.

Mindenképpen mentse a projektet egy biztonságos helyre. Ezután **exportálja** **kiépítési csomagként.**  

Lásd még: [A kiépítési](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)csomag alkalmazása a HoloLens.
