---
title: A Windows Holographic for Business funkcióinak feloldása
description: A vállalati verzióra Windows Holographic for Business HoloLens funkciókat kínálnak, amelyek üzleti használatra vannak tervezve.
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
ms.openlocfilehash: c6d1225dc6da1c039a34fc2782f23330ae40f280
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428498"
---
# <a name="unlock-windows-holographic-for-business-features"></a>A Windows Holographic for Business funkcióinak feloldása

> [!IMPORTANT]
> Ez az oldal csak az első HoloLens vonatkozik.

Microsoft HoloLens a Development *Edition* kiadásban érhető el, amely a Windows Holographic (a HoloLens-hez tervezett Windows 10-kiadás) [](hololens-commercial-features.md)és a Kereskedelmi csomag kiadásában érhető el, amely további üzleti funkciókat biztosít.

A kereskedelmi csomag megvásárlásakor kap egy licencet, amely a Holographic Windows frissít a Windows Holographic for Business. Ezt a licencet a szervezet mobileszköz-kezelési [(MDM)](#edition-upgrade-by-using-mdm) szolgáltatójával vagy egy kiépítési csomaggal [alkalmazhatja az eszközre.](#edition-upgrade-by-using-a-provisioning-package)

> [!TIP]
> A Windows 10 1803-as verziójában a Rendszer Gépház ellenőrizheti, hogy a HoloLens frissítve **lett-e az üzleti**  >  **kiadásra.**

## <a name="edition-upgrade-by-using-mdm"></a>Kiadásfrissítés MDM használatával

A vállalati licencet bármely olyan MDM-szolgáltató használhatja, amely támogatja a [WindowsLicensing konfigurációs szolgáltatót (CSP).](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) A Microsoft MDM API legújabb verziója támogatja a WindowsLicensing CSP-t.

A HoloLens a Microsoft Intune használatával történő frissítésére vonatkozó részletes útmutatásért lásd: [A Holographic](/intune/holographic-upgrade)Windows-t futtató eszközök Windows Holographic for Business.

 Más MDM-szolgáltatók esetében a házirend beállításának és telepítésének konkrét lépései eltérőek lehetnek.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Kiadásfrissítés kiépítési csomag használatával

A kiépítési csomagok olyan fájlok, Windows Configuration Designer eszköz által létrehozott fájlok, amelyek egy adott konfigurációt alkalmaznak egy eszközre.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Hozzon létre egy kiépítési csomagot, amely frissíti a Windows Holographic kiadást

1. [Hozzon létre egy kiépítési csomagot a HoloLens.](hololens-provisioning.md)
1. Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.

    ![Frissítse a kiadást a kiválasztott licencbeállítással.](images/icd1.png)

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

1. Válassza **a Tovább** lehetőséget annak a kimeneti helynek a megadásához, ahová a kiépítési csomagot létre szeretné hozatni. Alapértelmezés szerint az Windows ICD a projektmappát használja kimeneti helyként.

    A Tallózás gombra  kattintva módosíthatja az alapértelmezett kimeneti helyet.

1. Kattintson a **Tovább** gombra.

1. Válassza **a Build (Build)** lehetőséget a csomag felépítésének elkezdődjön. A build oldal megjeleníti a projektinformációkat, a folyamatjelző sáv pedig a build állapotát jelzi.

1. Ha a build elkészült, válassza a **Befejezés lehetőséget.**

### <a name="apply-the-provisioning-package-to-hololens"></a>A kiépítési csomag alkalmazása a HoloLens

1. Az USB-kábellel csatlakoztassa az eszközt egy számítógéphez. Indítsa el az eszközt, de  ne haladjon tovább a kezdeti beállítási folyamat illesztésoldalán (az első oldalon a kék mezővel). A számítógépen a HoloLens eszközként jelenik meg a Fájlkezelő.

    > [!NOTE]
    > Ha a HoloLens eszközön Windows 10 1607-es vagy korábbi verzió fut, nyissa meg az Fájlkezelő-t úgy, hogy rövid időre lenyomja és egyszerre kiadja a **Volume Down** és a **Power** gombok egyidejűleg az eszközön.

1. A Fájlkezelő húzza a kiépítési csomagot (.ppkg) az eszköz tárhelyére.

1. Bár HoloLens még mindig az  illesztés lapon van, röviden  nyomja le és engedje el egyszerre a **Kötet** le- és bekapcsolása gombot.

1. HoloLens rákérdez, hogy megbízik-e a csomagban, és szeretné-e alkalmazni. Győződjön meg arról, hogy megbízik a csomagban.

1. Látni fogja, hogy a csomag alkalmazása sikeres volt-e. Ha nem sikerült alkalmazni, javíthatja a csomagot, és újra megpróbálhatja. Ha ez sikeres, folytassa az eszköz beállításával.
