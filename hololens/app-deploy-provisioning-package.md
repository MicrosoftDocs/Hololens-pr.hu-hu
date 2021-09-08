---
title: Kiépítési csomag
description: Ismerje meg az alkalmazások csomagolását, üzembe helyezését, üzembe helyezését és vállalati alkalmazások üzembe helyezését HoloLens eszközök esetében.
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
ms.sourcegitcommit: f480d3cc8d549fa356e05df6ce15e9517f5b978a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2021
ms.locfileid: "123610989"
---
# <a name="provisioning-package"></a>Kiépítési csomag

A kiépítési csomagokkal előkészítheti és konfigurálhatja az eszközöket egy környezetben anélkül, hogy hozzáféréssel kellene rendelkeznie a végpontkezeléshez. Az eszközök a felhasználó identitásától, a regisztrációs állapottól, az Out of Box (OOBE) használata során, illetve a telepítés során egy kiépítési csomag alkalmazásával is üzembe [helyezhetők.](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## <a name="provisioning-packages-considerations"></a>Kiépítési csomagok – megfontolandó szempontok

* Nem nyilvános alkalmazások
* Csak USB-s oldalbetöltés
* Nincs automatikus frissítés (a PPKG-ken keresztüli manuális frissítéseket igényel)

A kiépítési csomaggal telepített alkalmazásokat a helyi gép tárolójában található tanúsítvánnyal kell aláírni. A kiépítési csomagok csak az eszköz (helyi gép) tárolójában telepíthet tanúsítványokat. Ezért egy alkalmazás és egy tanúsítvány is telepíthető ugyanazokkal a kiépítési csomagokkal. Ha ADM-ről telepíti a tanúsítványt, vagy a Tanúsítványkezelővel telepíti, akkor a tanúsítványt a helyi számítógép-tárolóban telepítse az így telepített alkalmazások aláíráshoz. [](certificate-manager.md)

A kiépítési csomag létrehozásához szükséges alapvető információkért látogasson el a HoloLens [provisioning (Kiépítés) HoloLens cikkre.](/hololens/hololens-provisioning) Egy alkalmazás üzembe helyezéséhez a speciális kiépítéssel kell kezdenie.

> [!NOTE]
> HoloLens (1. generációs) alkalmazásokat csak korlátozott mértékben támogat **(UniversalAppInstall**) egy kiépítési csomag használatával. HoloLens (1. generációs) eszközök csak az OOBE-n keresztül támogatják az alkalmazások PPKG-n keresztüli telepítését, és csak a felhasználói környezet telepítése esetén.

## <a name="setup"></a>Telepítés

A [Windows configuration designerben kövesse](https://www.microsoft.com/store/productId/9NBLGGH4TX22) az alábbi négy lépést.

1. Az ApplicationManagement/AllowAllTrustedApps beállításnál adja meg az "Igen" lehetőséget. Lásd: [ApplicationManagement/AllowAllTrustedApps.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)

2. Lépjen a **UniversalAppInstall**  >  **UserContextApp lapra, és adja** meg a **PackageFamilyName nevet.** Lásd: [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).

   A Eszközportál olyan eszközön használhatja, amelybe már telepítette az alkalmazást. Látogasson el az Alkalmazások oldalra, és nézze meg a PackageRelativeID sort, amely a "!" A **PackageFamilyName .**

3. Ekkor látni fogja, hogy van egy új, **ApplicationFile nevű szakasza.** Ezen a területen töltheti fel az appx-csomagot.

4. Attól függően, hogy megvásárolta az alkalmazást, vagy saját LOB-alkalmazást épített, fel kell töltenie a licencfájlt vagy a biztonsági tanúsítványt.

    - Licencfájl esetén: lépjen a **UniversalAppInstall**  >  **UserContextAppLicence** pontra, és adja meg a licenctermék azonosítóját. Új <b>szakasz: LicenseProductID:</b><i>alicenseproductid</i> létrejön, válassza ki ezt az új szakaszt, és tallózással keresse meg a licenc helyét, és töltse fel.
        - Lásd: [UserContextAppLicense.](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)
    - A biztonsági fájlhoz lépjen a Tanúsítványok **lapra,** és válassza ki az .appx csomag mellé telepíteni kívánt tanúsítványt.

Ügyeljen arra, hogy a projektet biztonságos helyre mentse. Ezután **exportálja** **kiépítési csomagként.**  

Lásd még: [A kiépítési csomag alkalmazása a HoloLens.](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
