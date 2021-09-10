---
title: Kiépítési csomag
description: Ismerje meg az alkalmazások csomagolását, üzembe helyezését, üzembe helyezését és a vállalati alkalmazások üzembe helyezését HoloLens eszközök esetében.
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
ms.openlocfilehash: d071f4326a35a9ea61e2069618da7107bb808f04
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427645"
---
# <a name="provisioning-package"></a>Kiépítési csomag

A kiépítési csomagokkal előkészítheti és konfigurálhatja az eszközöket egy környezetben anélkül, hogy hozzáféréssel kellene rendelkeznie a végpontkezeléshez. Az eszközök a felhasználó identitásától, a regisztrációs állapottól, a OOBE (OOBE) használata során, illetve a telepítés során egy kiépítési csomag alkalmazásával is üzembe [helyezhetők.](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## <a name="provisioning-packages-considerations"></a>Kiépítési csomagok – megfontolandó szempontok

* Nem nyilvános alkalmazások
* Csak USB-s oldalbetöltés
* Nincs automatikus frissítés (manuális frissítést igényel a PPKG-k segítségével)

A kiépítési csomaggal telepített alkalmazásokat a helyi gép tárolójában található tanúsítvánnyal kell aláírni. A kiépítési csomagok csak az eszköz (helyi gép) tárolójában telepíthet tanúsítványokat. Ezért egy alkalmazás és egy tanúsítvány is telepíthető ugyanazokkal a kiépítési csomagokkal. Ha az MDM-ről telepíti a [](certificate-manager.md)tanúsítványt, vagy a Tanúsítványkezelővel telepíti, a tanúsítványt a helyi számítógép-tárolóban kell telepítenie, hogy ezzel a módszerrel alá tudja írni a telepített alkalmazásokat.

A kiépítési csomag létrehozásához szükséges alapismeretekért látogasson el a HoloLens [provisioning (Kiépítés) HoloLens cikkére.](/hololens/hololens-provisioning) Az alkalmazások üzembe helyezéséhez speciális kiépítéssel kell kezdenie.

> [!NOTE]
> HoloLens (1. generációs) csak korlátozott mértékben támogatja az alkalmazások telepítését **(UniversalAppInstall**) egy kiépítési csomag használatával. HoloLens (1. generációs) eszközök csak OOBE környezetben és csak felhasználói környezet telepítése esetén támogatják az alkalmazások PPKG-n keresztüli telepítését.

## <a name="setup"></a>Telepítés

A [Windows Configuration Designerben kövesse](https://www.microsoft.com/store/productId/9NBLGGH4TX22) az alábbi négy lépést.

1. Állítsa az ApplicationManagement/AllowAllTrustedApps halmazt "Igen" -ra. Lásd: [ApplicationManagement/AllowAllTrustedApps.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)

2. Lépjen a **UniversalAppInstall**  >  **UserContextApp lapra, és** adja meg **a PackageFamilyName nevet.** Lásd: [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).

   Használhatja a Eszközportál olyan eszközön, amelyre már telepítette az alkalmazást. Látogasson el az Alkalmazások oldalra, és nézze meg a PackageRelativeID sort, az összes információt a "!" A **PackageFamilyName .**

3. Ezután látni fogja, hogy van egy új szakasza, az **ApplicationFile.** Ezen a területen töltheti fel az appx-csomagot.

4. Attól függően, hogy megvásárolta az alkalmazást, vagy saját LOB-alkalmazást épített, fel kell töltenie a licencfájlt vagy a biztonsági tanúsítványt.

    - Licencfájl esetén: lépjen a **UniversalAppInstall**  >  **UserContextAppLicence** pontra, és adja meg a licenctermék azonosítóját. Egy új <b>Szakasz LicenseProductID:</b><i>a yourlicenseproductid</i> létrejön, válassza ki ezt az új szakaszt, és tallózással keresse meg a licenc helyét, és töltse fel.
        - Lásd: [UserContextAppLicense.](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)
    - A biztonsági fájlhoz lépjen a Tanúsítványok **lapra,** és válassza ki az .appx csomaggal együtt telepíteni kívánt tanúsítványt.

Mindenképpen mentse a projektet egy biztonságos helyre. Ezután **exportálja** **kiépítési csomagként.**  

Lásd még: [A kiépítési csomag alkalmazása a HoloLens.](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
