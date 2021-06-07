---
title: A Windows Holographic for Business funkcióinak feloldása
description: Az új Windows Holographic for Business a HoloLens további, üzleti használatra tervezett funkciókat biztosít.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378104"
---
# <a name="unlock-windows-holographic-for-business-features"></a>A Windows Holographic for Business funkcióinak feloldása

> [!IMPORTANT]
> Ez a lap csak a HoloLens 1st Gen-re vonatkozik.

Microsoft HoloLens a Development *Edition* kiadásban érhető el, amely a Windows Holographic (a holoLenshez tervezett Windows 10 egy kiadása) és a [Commercial Suite-ban](hololens-commercial-features.md)érhető el, amely további üzleti funkciókat biztosít.

A kereskedelmi csomag megvásárlásakor kap egy licencet, amely frissíti a Windows Holographic rendszert a Windows Holographic for Business. Ezt a licencet a szervezet mobileszköz-kezelési [(MDM)](#edition-upgrade-by-using-mdm) szolgáltatójával vagy egy kiépítési csomaggal [alkalmazhatja az eszközre.](#edition-upgrade-by-using-a-provisioning-package)

> [!TIP]
> A Windows 10 1803-as verziójában a Beállításrendszer lehetőség kiválasztásával ellenőrizheti, hogy a HoloLens frissítve lett-e az üzleti  >  **kiadásra.**

## <a name="edition-upgrade-by-using-mdm"></a>Kiadásfrissítés MDM használatával

A vállalati licencet bármely olyan MDM-szolgáltató használhatja, amely támogatja a [WindowsLicensing konfigurációs szolgáltatót (CSP).](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) A Microsoft MDM API legújabb verziója támogatja a WindowsLicensing CSP-t.

A HoloLens frissítésének részletes útmutatója a Microsoft Intune használatával: [Upgrade devices running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).

 Más MDM-szolgáltatók esetében a házirend beállításának és telepítésének konkrét lépései eltérőek lehetnek.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Kiadásfrissítés kiépítési csomag használatával

A kiépítési csomagok a Windows Configuration Designer eszköz által létrehozott fájlok, amelyek egy adott konfigurációt alkalmaznak egy eszközre.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>A Windows Holographic kiadását frissítő kiépítési csomag létrehozása

1. [Hozzon létre egy kiépítési csomagot a HoloLenshez.](hololens-provisioning.md)
1. Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.

    ![Kiadás frissítése a kiválasztott licencbeállítással](images/icd1.png)

1. Keresse meg a kereskedelmi csomag vásárlásakor megadott XML-licencfájlt.

    > [!NOTE]
    > További [beállításokat a kiépítési csomagban konfigurálhat.](hololens-provisioning.md)

1. A **Fájl** menüben válassza a **Mentés** elemet. 

1. Olvassa el a figyelmeztetést, amely szerint a projektfájlok bizalmas adatokat tartalmazhatnak, majd kattintson az **OK gombra.**

    > [!IMPORTANT]
    > Kiépítési csomag létrehozása során bizalmas adatokat is tartalmazhat a projektfájlokban és a kiépítési csomagfájlban (.ppkg). Bár lehetősége van a .ppkg fájl titkosítására, a projektfájlok nincsenek titkosítva. A projektfájlokat érdemes biztonságos helyen tárolni, és törölni a projektfájlokat, ha már nincs rájuk szükség.

1. Az Exportálás **menüben** válassza a **Kiépítési csomag lehetőséget.**

1. Módosítsa **a Tulajdonost** **rendszergazdai** beállításra, amely a kiépítési csomag prioritását magasabbra állítja, mint a különböző forrásokból származó eszközökre alkalmazott többi eszköz, majd válassza a Tovább **lehetőséget.**

1. Állítsa be a Package **Version (Csomagverzió) értékét.**

    > [!TIP]
    > Módosíthatja a meglévő csomagokat, és módosíthatja a verziószámot a korábban alkalmazott csomagok frissítéséhez.

1. A **Kiépítési csomag Biztonsági részletek kiválasztása területén válassza** a Tovább **lehetőséget.**

1. Válassza **a Tovább** lehetőséget annak a kimeneti helynek a megadásához, ahová a kiépítési csomagot létre szeretné hozatni. Alapértelmezés szerint a Windows ICD a projektmappát használja kimeneti helyként.

    A Tallózás gombra  kattintva módosíthatja az alapértelmezett kimeneti helyet.

1. Kattintson a **Tovább** gombra.

1. Válassza **a Build (Build)** lehetőséget a csomag felépítésének elkezdődjön. A build oldal megjeleníti a projektinformációkat, a folyamatjelző sáv pedig a build állapotát jelzi.

1. Ha a build elkészült, válassza a **Befejezés lehetőséget.**

### <a name="apply-the-provisioning-package-to-hololens"></a>A kiépítési csomag alkalmazása a HoloLensre

1. Az USB-kábellel csatlakoztassa az eszközt egy számítógéphez. Indítsa el az eszközt, de  ne haladjon tovább a kezdeti beállítási folyamat illesztésoldalán (az első oldalon a kék mezővel). A számítógépen a HoloLens eszközként jelenik meg a Fájlkezelő.

    > [!NOTE]
    > Ha a HoloLens-eszköz az Windows 10 1607-es vagy korábbi verzióját futtatja, nyissa meg az Fájlkezelő-t úgy, hogy rövid időre lenyomja és egyszerre kiadja a **Volume Down** és a **Power** gombokat az eszközön.

1. A Fájlkezelő húzza a kiépítési csomagot (.ppkg) az eszköz tárhelyére.

1. Bár a HoloLens továbbra is az illesztés oldalon **van,** röviden nyomja le és engedje el egyszerre a **Volume Down** és **a Power** gombokat.

1. HoloLens megkérdezi, hogy megbízik-e a csomagban, és szeretné-e alkalmazni. Győződjön meg arról, hogy megbízik a csomagban.

1. Látni fogja, hogy a csomag alkalmazása sikeres volt-e. Ha nem sikerült alkalmazni, javíthatja a csomagot, és újra megpróbálhatja. Ha ez sikeres, folytassa az eszköz beállításával.
