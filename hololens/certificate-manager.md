---
title: Tanúsítványkezelő
description: Megtudhatja, hogyan telepíthet, kezelhet és távolíthat el tanúsítványokat manuálisan HoloLens 2 vegyes valóságú eszközön.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/12/2021
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: af9c6634ddbb40acace9a2abf8dd933ec05704de
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924390"
---
# <a name="certificate-manager"></a>Tanúsítványkezelő

- Továbbfejlesztett naplózási, diagnosztikai és érvényesítési eszközök az eszközbiztonság és -megfelelőség érdekében az új Tanúsítványkezelővel. Ez a képesség lehetővé teszi a tanúsítványok kereskedelmi környezetekben való nagy léptékű üzembe helyezését, hibaelhárítását és érvényesítését.

A Windows Holographic 20H2 verziójában hozzáadunk egy tanúsítványkezelőt a HoloLens 2 Gépház alkalmazáshoz. Az Update **Gépház > Security & és tanúsítványok > meg.** Ez a szolgáltatás egyszerű és felhasználóbarát módja a tanúsítványok megtekintésének, telepítésének és eltávolításának az eszközön. Az új Tanúsítványkezelővel a rendszergazdák és a felhasználók továbbfejlesztett naplózási, diagnosztikai és érvényesítési eszközökkel gondoskodnak az eszközök biztonságának és megfelelőségének biztosításáról.

-   **Naplózás:** A tanúsítvány megfelelő telepítésének ellenőrzése vagy annak ellenőrzése, hogy a tanúsítvány megfelelően lett-e eltávolítva.
-   **Diagnosztika:** Problémák esetén a megfelelő tanúsítványoknak az eszközön való létezik-e a hitelesítése időt takarít meg, és segít a hibaelhárításban.
-   **Érvényesítés:** Annak ellenőrzése, hogy egy tanúsítvány a kívánt célt szolgálja-e és működik-e, jelentős időt takaríthat meg, különösen kereskedelmi környezetekben, mielőtt nagyobb léptékben helyez üzembe tanúsítványokat.

Ha gyorsan meg kell találnia egy adott tanúsítványt a listában, név, tároló vagy lejárati dátum szerint rendezhet. A felhasználók közvetlenül is kereshetnek tanúsítványt. Az egyes tanúsítványtulajdonságok megtekintéséhez válassza ki a tanúsítványt, majd kattintson az **Információ elemre.**

A tanúsítványtelepítés jelenleg .cer és .crt fájlokat támogat. Az eszköztulajdonosok a helyi gépen és az aktuális felhasználón telepíthet tanúsítványokat;  minden más felhasználó csak az Aktuális felhasználóba telepíthető.

## <a name="to-install-a-certificate"></a>Tanúsítvány telepítése:

1.  Csatlakozás 2. HoloLens számítógépére.
1.  Helyezze a telepíteni kívánt tanúsítványfájlt a 2. HoloLens helyére.
1.  Lépjen a Gépház App > Update & Security > Certificates (Tanúsítványok) **lapra,** és válassza a Tanúsítvány telepítése lehetőséget.
1.  Kattintson **a Fájl importálása** elemre, és keresse meg a helyet, ahol a tanúsítványt mentette.
1.  Válassza **a Store Location (Áruház helye) lehetőséget.**
1.  Válassza **a Tanúsítványtároló lehetőséget.**
1.  Kattintson az **Install** (Telepítés) gombra.

A tanúsítványnak most már telepítve kell lennie az eszközön.

![Az alkalmazás tanúsítványmegjelenítője Gépház a Tanúsítványok alatt.](images/certificate-viewer-device.jpg)

![Kép arról, hogyan telepíthet tanúsítványt a tanúsítvány felhasználói felületén a Gépház.](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>Tanúsítvány eltávolítása:

> [!WARNING]
> A Tanúsítványkezelő használatával a felhasználók csak a közvetlenül a felhasználói felületről Gépház tanúsítványokat. Ha egy tanúsítvány más módon lett telepítve, akkor azt is el kell távolítani ugyanaz a mechanizmus, és nem távolítható el a Tanúsítványkezelőből. Bár az MDM által telepített tanúsítványokat megtekintheti a Tanúsítványkezelőben, a Tanúsítványkezelőben nem távolíthatja el őket. Ezeket el kell távolítania az MDM-ről.

1. Lépjen a **Gépház App > Update and Security > Certificates (Alkalmazás frissítése és > tanúsítványok) lapra.**
1. Keresse meg a tanúsítványt név alapján a keresőmezőben.
1. Válassza ki a tanúsítványt.
1. Kattintson az **Eltávolítás gombra**
1. Ha a **rendszer** megerősítést kér, válassza az Igen lehetőséget.

## <a name="pfx-file-support-for-certificate-manager"></a>PFX-fájltámogatás a Tanúsítványkezelőhöz

- A [holografikus Windows 21H2-es verziójában vezettük be.](hololens-release-notes.md#windows-holographic-version-21h2)

 Mostantól támogatott a Tanúsítványkezelő a .pfx-tanúsítványok használatára. Amikor a felhasználók a **Gépház** update & security certificates (Biztonsági tanúsítványok frissítése) lapra navigálnak, és kiválasztják a Tanúsítvány telepítése lehetőséget, a felhasználói felület mostantól támogatja  >    >   **a** .pfx tanúsítványfájlt.
A felhasználók .pfx-tanúsítványt importálnak titkos kulccsal a felhasználói tárolóba vagy számítógéptárolóba.