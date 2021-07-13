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
ms.openlocfilehash: 5aa554f9e7fdc09c3112b628e0978ac3332bc57d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635517"
---
# <a name="provisioning-package"></a>Kiépítési csomag

A kiépítési csomagokkal előkészítheti és konfigurálhatja az eszközöket egy környezetben anélkül, hogy hozzáféréssel kellene rendelkeznie a végpontkezeléshez. Az eszközök a felhasználó identitásától, a regisztrációs állapottól, az Out of Box (OOBE) használata során, illetve a telepítés során egy kiépítési csomag alkalmazásával is üzembe [helyezhetők.](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## <a name="provisioning-packages-considerations"></a>A kiépítési csomagokra vonatkozó szempontok:

* Nem nyilvános alkalmazások
* Csak USB-s oldalbetöltés
* Nincs automatikus frissítés (a PPKG-ken keresztüli manuális frissítést igényel)

A kiépítési csomaggal telepített alkalmazásokat a helyi gép tárolójában található tanúsítvánnyal kell aláírni. A kiépítési csomagok csak az eszköz (helyi gép) tárolójára telepíthetnek tanúsítványokat, ezért az alkalmazás és a tanúsítvány is telepíthető ugyanazokkal a kiépítési csomagokkal. Ha ADM-ről telepíti a tanúsítványt, vagy a Tanúsítványkezelővel telepíti, akkor a tanúsítványt a helyi számítógép-tárolóban telepítse az így telepített alkalmazások aláíráshoz. [](certificate-manager.md)

A kiépítési csomag létrehozásához szükséges alapvető tudnivalókért látogasson el a HoloLens [provisioning (Kiépítés) HoloLens cikkre.](/hololens/hololens-provisioning) Egy alkalmazás üzembe helyezéséhez a speciális kiépítéssel kell kezdenie.

> [!NOTE]
> HoloLens (1. generációs) alkalmazásokat csak korlátozott mértékben támogat **(UniversalAppInstall**) egy kiépítési csomag használatával. HoloLens (1. generációs) eszközök csak az OOBE-n keresztül támogatják az alkalmazások PPKG-n keresztüli telepítését, és csak a felhasználói környezet telepítése esetén.

## <a name="setup"></a>Telepítés

A [Windows Configuration Designerben](https://www.microsoft.com/store/productId/9NBLGGH4TX22) kövesse az alábbi négy lépést.

1. Az ApplicationManagement/AllowAllTrustedApps beállításnál adja meg az "Igen" lehetőséget. Lásd: [ApplicationManagement/AllowAllTrustedApps.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)

2. Lépjen a **UniversalAppInstall**  >  **UserContextAppLicense lapra,** és adja meg a **PackageFamilyName nevet.** Lásd: [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall). Lásd még: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   A Eszközportál olyan eszközön használhatja, amelybe már telepítette az alkalmazást. Látogasson el az Alkalmazások oldalra, és nézze meg a PackageRelativeID sort, amely a "!" A **PackageFamilyName .**

3. Ekkor látni fogja, hogy van egy új, **ApplicationFile nevű szakasza.** Ezen a területen töltheti fel az appx-csomagot.

4. Attól függően, hogy megvásárolta az alkalmazást, vagy saját LOB-alkalmazást épített, fel kell töltenie a licencfájlt vagy a biztonsági tanúsítványt.

    - Licencfájl: lépjen a **UniversalAppInstall**  >  **UserContextAppLicence** elemre, keresse meg és töltse fel a licenc helyét.
    - A biztonsági fájlhoz lépjen a Tanúsítványok **lapra,** és válassza ki az .appx csomag mellé telepíteni kívánt tanúsítványt.

Ügyeljen arra, hogy a projektet biztonságos helyre mentse. Ezután **exportálja** **kiépítési csomagként.**  

Lásd még: [A kiépítési](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)csomag alkalmazása a HoloLens.
