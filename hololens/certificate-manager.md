---
title: Tanúsítványkezelő
description: Megtudhatja, hogyan telepíthet, kezelhet és távolíthat el tanúsítványokat manuálisan a HoloLens 2 vegyes valóságú eszközökön.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378041"
---
# <a name="certificate-manager"></a>Tanúsítványkezelő

- Továbbfejlesztett naplózási, diagnosztikai és érvényesítési eszközök az eszközbiztonság és -megfelelőség érdekében az új Tanúsítványkezelővel. Ez a képesség lehetővé teszi a tanúsítványok kereskedelmi környezetekben való nagy léptékű üzembe helyezését, hibaelhárítását és érvényesítését.

A Windows Holographic 20H2-es verziójában tanúsítványkezelőt ad hozzá a HoloLens 2 Beállítások alkalmazáshoz. A Biztonsági **tanúsítványok > frissítése & lapra > meg.** Ez a funkció egyszerű és felhasználóbarát módja a tanúsítványok megtekintésének, telepítésének és eltávolításának az eszközön. Az új Tanúsítványkezelővel a rendszergazdák és a felhasználók továbbfejlesztett naplózási, diagnosztikai és érvényesítési eszközökkel gondoskodnak az eszközök biztonságának és megfelelőségének biztosításáról. 

-   **Naplózás:** A tanúsítvány megfelelő telepítésének ellenőrzése vagy annak ellenőrzése, hogy a tanúsítvány megfelelően lett-e eltávolítva. 
-   **Diagnosztika:** Ha problémák merülnek fel, a megfelelő tanúsítványoknak az eszközön való létezik-e a hitelesítése időt takarít meg, és segít a hibaelhárításban. 
-   **Érvényesítés:** Annak ellenőrzése, hogy a tanúsítvány a kívánt célt szolgálja-e és működik-e, jelentős időt takaríthat meg, különösen kereskedelmi környezetekben, mielőtt nagyobb léptékben helyez üzembe tanúsítványokat.

Ha gyorsan meg kell találnia egy adott tanúsítványt a listában, lehetőség van név, tároló vagy lejárati dátum szerint rendezni. A felhasználók közvetlenül is kereshetnek tanúsítványt. Az egyes tanúsítványtulajdonságok megtekintéséhez jelölje ki a tanúsítványt, majd kattintson az **Információ elemre.** 

A tanúsítványtelepítés jelenleg a .cer és a .crt fájlokat támogatja. Az eszköztulajdonosok a helyi gépen és az aktuális felhasználónál telepíthet tanúsítványokat;  minden más felhasználó csak az Aktuális felhasználóra telepíthető. A felhasználók csak a beállítások felhasználói felületről távolítják el a közvetlenül telepített tanúsítványokat. Ha egy tanúsítvány más módon lett telepítve, akkor ugyanezen mechanizmussal kell eltávolítani.

## <a name="to-install-a-certificate"></a>Tanúsítvány telepítése: 

1.  Csatlakoztassa a HoloLens 2-t egy számítógéphez.
1.  Helyezze el a telepíteni kívánt tanúsítványfájlt a HoloLens 2-es helyén.
1.  Lépjen a **Settings App > Update & Security > Certificates**(Tanúsítványok frissítése) lapra, és válassza a Tanúsítvány telepítése lehetőséget.
1.  Kattintson **a Fájl importálása** elemre, és keresse meg a helyet, ahol a tanúsítványt mentette.
1.  Válassza **a Store Location (Áruház helye) lehetőséget.**
1.  Válassza **a Tanúsítványtároló lehetőséget.**
1.  Kattintson az **Install** (Telepítés) gombra.

A tanúsítványnak most már telepítve kell lennie az eszközön.

## <a name="to-remove-a-certificate"></a>Tanúsítvány eltávolítása: 
>[!WARNING]
> Bár az MDM által telepített tanúsítványokat megtekintheti a Tanúsítványkezelőben, a Tanúsítványkezelőben nem távolíthatja el őket. Ezeket az MDM-ről kell eltávolítania.
1. Lépjen a Settings App > Update and Security > Certificates (Tanúsítványok **>) elemre.**
1. Keresse meg a tanúsítványt név alapján a keresőmezőben.
1. Válassza ki a tanúsítványt.
1. Kattintson az **Eltávolítás gombra.**
1. Ha  a rendszer megerősítést kér, válassza az Igen lehetőséget.



![Tanúsítványmegjelenítő a Beállítások alkalmazásban a Tanúsítványok alatt](images/certificate-viewer-device.jpg)

![Kép arról, hogyan telepíthet tanúsítványt a Tanúsítvány felhasználói felületén a Beállítások menüben.](images/certificate-device-install.jpg)
