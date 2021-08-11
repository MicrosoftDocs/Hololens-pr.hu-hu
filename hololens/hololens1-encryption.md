---
title: HoloLens BitLocker-titkosítás
description: Megtudhatja, hogyan engedélyezheti a BitLocker eszköztitkosítást a vegyes valóságú eszközökön tárolt HoloLens védelméhez.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4b07bb87b34ec966472bcbde000106590570fd7e7063ab503724884fa266bb34
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662726"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>HoloLens (1. generációs) BitLocker-titkosítás

HoloLens (1. generációs) és HoloLens 2. HoloLens egyaránt támogatja az eszköztitkosítást a BitLocker használatával, a BitLocker azonban mindig engedélyezve van a 2. HoloLens-ben.

Ez a cikk segít a BitLocker engedélyezésében és HoloLens (1. generációs) rendszerében.

A HoloLens (1. generációs) eszközön manuálisan vagy mobileszköz-felügyelet (MDM) használatával engedélyezheti a BitLocker-eszköz titkosítását. Kövesse ezeket az utasításokat a [BitLocker](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) eszköztitkosítás engedélyezéséhez az eszközön tárolt fájlok és információk HoloLens. Az eszköztitkosítás az AES-CBC 128 titkosítási módszerrel segíti az adatok védelmét, amely egyenértékű a BitLocker konfigurációszolgáltató (CSP) [3. titkosítási módszerével.](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) A megfelelő titkosítási kulccsal (például jelszóval) dolgozó személyzet visszafejtheti vagy helyreállíthatja az adatokat.

## <a name="enable-device-encryption-using-mdm"></a>Eszköz titkosításának engedélyezése MDM használatával

A Mobile Eszközkezelés (MDM) szolgáltatójával eszköztitkosítást igénylő szabályzatot alkalmazhat. A használni szükséges szabályzat a Házirend CSP [Security/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) beállítása.

[Lásd az eszköz titkosításának engedélyezésére vonatkozó utasításokat Microsoft Intune.](/intune/compliance-policy-create-windows#windows-holographic-for-business)

További MDM-eszközökért tekintse meg az MDM-szolgáltató dokumentációját. Ha az MDM-szolgáltató egyéni URI-t igényel az eszköz titkosításához, használja a következő konfigurációt:

- **Név:** egy ön által választott név
- **Leírás:** nem kötelező
- **OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Adattípus:** egész szám
- **Érték:**`1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Eszköz titkosításának engedélyezése kiépítési csomag használatával

A kiépítési csomagok olyan fájlok, Windows Configuration Designer eszköz által létrehozott fájlok, amelyek egy adott konfigurációt alkalmaznak egy eszközre. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Hozzon létre egy kiépítési csomagot, amely frissíti Windows Holographic kiadást, és engedélyezi a titkosítást

1. [Hozzon létre egy kiépítési csomagot a HoloLens.](hololens-provisioning.md)
1. Válassza a **Runtime settings** Policies Security (Biztonsági szabályzatok) lehetőséget, majd válassza  >    >   **a RequireDeviceEncryption lehetőséget.**

    ![Az igen beállításra konfigurált eszköztitkosítás megkövetelve](images/device-encryption.png)

1. Keresse meg a Kereskedelmi csomag vásárlásakor megadott XML-licencfájlt.

1. Keresse meg és válassza ki a Commercial Suite vásárlásakor megadott XML-licencfájlt.
    > [!NOTE]
    > További [beállításokat a kiépítési csomagban konfigurálhat.](hololens-provisioning.md)

1. A **File** (Fájl) menüben kattintson a **Save** (Mentés) parancsra. 

1. Olvassa el a figyelmeztetést, amely szerint a projektfájlok bizalmas adatokat tartalmazhatnak, majd kattintson az **OK gombra.**

    > [!IMPORTANT]
    > A kiépítési csomag létrehozása során bizalmas adatokat is tartalmazhat a projektfájlokban és a kiépítési csomagfájlban (.ppkg). Bár lehetősége van a .ppkg fájl titkosítására, a projektfájlok nincsenek titkosítva. A projektfájlokat biztonságos helyen tárolja, és törölje a projektfájlokat, ha már nincs rájuk szükség.

1. Az Exportálás **menüben** kattintson a **Kiépítési csomag elemre.**
1. Módosítsa **a Tulajdonost** **rendszergazdai** beállításra, amely magasabb prioritást ad meg ennek a kiépítési csomagnak, mint a más forrásokból az eszközre alkalmazott kiépítési csomagoknak, majd válassza a Tovább **lehetőséget.**
1. Állítsa be a Package **Version (Csomagverzió) értékét.**

    > [!TIP]
    > Módosíthatja a meglévő csomagokat, és módosíthatja a verziószámot a korábban alkalmazott csomagok frissítéséhez.

1. A Select security details for the provisioning package (A **kiépítési csomag biztonsági részleteinek kiválasztása) területén kattintson** a Next **(Tovább) gombra.**
1. Kattintson **a Tovább** gombra annak a kimeneti helynek a megadásához, ahová a kiépítési csomagot létre szeretné hozatni. Alapértelmezés szerint Windows ICD a projektmappát használja kimeneti helyként.

    Ha szeretne, a Tallózás gombra kattintva módosíthatja az alapértelmezett kimeneti helyet.

1. Kattintson a **Tovább** gombra.
1. Kattintson **a Build (Build)** gombra a csomag felépítésének elkezdéshez. A projektinformációk a build oldalán jelennek meg, a folyamatjelző sáv pedig a build állapotát jelzi.
1. Amikor a build elkészült, kattintson a **Befejezés gombra.**

### <a name="apply-the-provisioning-package-to-hololens"></a>A kiépítési csomag alkalmazása a HoloLens

1. Csatlakozás usb-kapcsolaton keresztül csatlakoztatja az eszközt egy számítógéphez,  és indítsa el az eszközt, de ne haladjon tovább a kezdeti beállítási folyamat illesztésén (az első oldalon a kék mezővel).
1. Röviden nyomja le és engedje el egyszerre a **Volume Down** és a Power (Le- és **bekapcsolás)** gombot.
1. HoloLens adatokat a számítógép Fájlkezelő eszközként fogja mutatni.
1. A Fájlkezelő húzza a kiépítési csomagot (.ppkg) az eszköz tárhelyére.
1. Röviden nyomja le és engedje el egyszerre a Kötet le **és** a **Bekapcsológombot** az **illesztés lapon.**
1. Az eszköz rá fog kérdezni, hogy megbízik-e a csomagban, és szeretné-e alkalmazni. Győződjön meg arról, hogy megbízik a csomagban.
1. Látni fogja, hogy a csomag alkalmazása sikeres volt-e. Ha nem sikerült, javíthatja a csomagot, és újra próbálkozhat. Ha sikeres volt, folytassa az eszköz beállításával.

> [!NOTE]
> Ha az eszközt 2016 augusztusa előtt vásárolta meg, be kell jelentkeznie az eszközre egy Microsoft-fiók-val, be kell szereznie a legújabb operációsrendszer-frissítést, majd alaphelyzetbe kell állítania az operációs rendszert a kiépítési csomag alkalmazáshoz.

## <a name="verify-device-encryption"></a>Az eszköztitkosítás ellenőrzése

A titkosítás csendes a HoloLens. Az eszköz titkosítási állapotának ellenőrzése:

- A HoloLens a System About **(Rendszer**  >  **Gépház)**  >  **oldalon.** **A BitLocker** **akkor van engedélyezve,** ha az eszköz titkosítva van. 

    ![About screen showing BitLocker enabled (A BitLocker engedélyezése) képernyő](images/about-encryption.png)
