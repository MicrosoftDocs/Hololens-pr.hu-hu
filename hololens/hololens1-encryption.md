---
title: HoloLens BitLocker-titkosítás
description: Ismerje meg, hogyan engedélyezheti a BitLocker eszköztitkosítást a vegyes valóságú eszközökön tárolt HoloLens védelméhez.
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
ms.openlocfilehash: d5cf7385dd0a53c6b17f79e16364e84ab6ec867d
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189936"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>HoloLens (1. generációs) BitLocker-titkosítás

HoloLens (1. generációs) és a 2. HoloLens is támogatja az eszköztitkosítást a BitLocker használatával, a BitLocker azonban mindig engedélyezve van a 2. HoloLens-on.

Ez a cikk segít a BitLocker engedélyezésében és HoloLens (1. generációs) rendszerében.

A HoloLens (1. generációs) manuálisan vagy mobileszköz-felügyelet (MDM) használatával engedélyezheti a BitLocker-eszköz titkosítását. Kövesse ezeket az utasításokat a [BitLocker eszköztitkosítás engedélyezéséhez](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) az eszközön tárolt fájlok és információk HoloLens. Az eszköztitkosítás az AES-CBC 128 titkosítási módszerrel segíti az adatok védelmét, ami egyenértékű a BitLocker konfigurációszolgáltató (CSP) [3. titkosítási módszerével.](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) A megfelelő titkosítási kulccsal (például jelszóval) dolgozó személyzet visszafejtheti vagy adat-helyreállítást hajthat végre.

## <a name="enable-device-encryption-using-mdm"></a>Eszköz titkosításának engedélyezése MDM használatával

A Mobile Eszközkezelés (MDM) szolgáltatójával eszköztitkosítást igénylő szabályzatot alkalmazhat. A használni szükséges szabályzat a Házirend CSP [Security/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) beállítása.

[Lásd az eszköz titkosításának engedélyezésére vonatkozó utasításokat Microsoft Intune.](/intune/compliance-policy-create-windows#windows-holographic-for-business)

Egyéb MDM-eszközökről az MDM-szolgáltató dokumentációjában talál útmutatást. Ha az MDM-szolgáltató egyéni URI-t igényel az eszköz titkosításához, használja a következő konfigurációt:

- **Név:** egy Ön által választott név
- **Leírás:** nem kötelező
- **OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Adattípus:** egész szám
- **Érték:**`1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Eszköz titkosításának engedélyezése kiépítési csomag használatával

A kiépítési csomagok olyan fájlok, Windows Configuration Designer eszköz által létrehozott fájlok, amelyek egy adott konfigurációt alkalmaznak egy eszközre. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Hozzon létre egy kiépítési csomagot, amely frissíti a Windows Holographic kiadást, és engedélyezi a titkosítást

1. [Hozzon létre egy kiépítési csomagot a HoloLens.](hololens-provisioning.md)
1. Válassza a **Futásidejű beállítások**  >    >  **Házirendek biztonsága lehetőséget,** majd válassza **a RequireDeviceEncryption lehetőséget.**

    ![Az igen értékhez konfigurált eszköztitkosítás megkövetelve.](images/device-encryption.png)

1. Keresse meg a kereskedelmi csomag vásárlásakor megadott XML-licencfájlt.

1. Keresse meg és válassza ki a Kereskedelmi csomag vásárlásakor megadott XML-licencfájlt.
    > [!NOTE]
    > További [beállításokat a kiépítési csomagban konfigurálhat.](hololens-provisioning.md)

1. A **File** (Fájl) menüben kattintson a **Save** (Mentés) parancsra. 

1. Olvassa el a figyelmeztetést, amely ismerteti, hogy a projektfájlok bizalmas adatokat tartalmazhatnak, majd kattintson az **OK gombra.**

    > [!IMPORTANT]
    > Kiépítési csomag létrehozása során bizalmas adatokat is tartalmazhat a projektfájlokban és a kiépítési csomagfájlban (.ppkg). Bár lehetősége van a .ppkg fájl titkosítására, a projektfájlok nincsenek titkosítva. A projektfájlokat érdemes biztonságos helyen tárolni, és törölni a projektfájlokat, ha már nincs rájuk szükség.

1. Az Exportálás **menüben** kattintson a **Kiépítési csomag elemre.**
1. Módosítsa **a Tulajdonost** **rendszergazdai** beállításra, amely magasabb prioritást ad meg ennek a kiépítési csomagnak, mint a más forrásokból az eszközre alkalmazott kiépítési csomagoknak, majd válassza a Tovább **lehetőséget.**
1. Állítsa be a Package **Version (Csomagverzió) értékét.**

    > [!TIP]
    > Módosíthatja a meglévő csomagokat, és módosíthatja a verziószámot a korábban alkalmazott csomagok frissítéséhez.

1. A **Kiépítési csomag Biztonsági részletek kiválasztása területén kattintson** a Tovább **gombra.**
1. Kattintson **a Tovább** gombra annak a kimeneti helynek a megadásához, ahová a kiépítési csomagot létre szeretné hozatni. Alapértelmezés szerint az Windows ICD a projektmappát használja kimeneti helyként.

    Másik lehetőségként a Tallózás gombra kattintva módosíthatja az alapértelmezett kimeneti helyet.

1. Kattintson a **Tovább** gombra.
1. Kattintson **a Build (Build)** gombra a csomag felépítésének elkezdésében. A projektinformációk a build oldalán jelennek meg, a folyamatjelző sáv pedig jelzi a build állapotát.
1. Amikor a build elkészült, kattintson a **Befejezés gombra.**

### <a name="apply-the-provisioning-package-to-hololens"></a>A kiépítési csomag alkalmazása a HoloLens

1. Csatlakozás csatlakoztatja az eszközt USB-kapcsolaton keresztül egy számítógéphez,  és indítsa el az eszközt, de ne haladjon tovább a kezdeti beállítási folyamat illesztésén (az első oldalon a kék mezővel).
1. Röviden nyomja le és engedje el egyszerre a **Volume Down** és **a Power** gombokat.
1. HoloLens adatokat a számítógép Fájlkezelő eszközként fogja mutatni.
1. A Fájlkezelő húzza a kiépítési csomagot (.ppkg) az eszköz tárhelyére.
1. Röviden nyomja le és  engedje el egyszerre a **Kötet** le és bekapcsoló gombokat, miközben a beférés **lapon** van.
1. Az eszköz megkérdezi, hogy megbízik-e a csomagban, és szeretné-e alkalmazni. Győződjön meg arról, hogy megbízik a csomagban.
1. Látni fogja, hogy a csomag alkalmazása sikeres volt-e. Ha nem sikerült, javíthatja a csomagot, és újra próbálkozhat. Ha sikerrel járt, folytassa az eszköz beállításával.

> [!NOTE]
> Ha az eszközt 2016 augusztusa előtt vásárolta meg, be kell jelentkeznie az eszközre egy Microsoft-fiók-val, le kell szereznie a legújabb operációsrendszer-frissítést, majd alaphelyzetbe kell állítania az operációs rendszert a kiépítési csomag alkalmazáshoz.

## <a name="verify-device-encryption"></a>Az eszköztitkosítás ellenőrzése

A titkosítás csendes a HoloLens. Az eszköz titkosítási állapotának ellenőrzése:

- A HoloLens a Rendszer **Gépház**  >    >  **oldalon.** **A BitLocker** **akkor van engedélyezve,** ha az eszköz titkosítva van. 

    ![About screen showing BitLocker enabled.](images/about-encryption.png)
