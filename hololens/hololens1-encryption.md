---
title: HoloLens BitLocker-titkosítás
description: Megtudhatja, hogyan engedélyezheti a BitLocker-eszköztitkosítást a vegyes valóságú eszközökön tárolt HoloLens védelméhez.
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
ms.openlocfilehash: 37efab3ef3d68a9641320e144619008612f6efa2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635245"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="4fddb-103">HoloLens (1. generációs) BitLocker-titkosítás</span><span class="sxs-lookup"><span data-stu-id="4fddb-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="4fddb-104">HoloLens (1. generációs) és a 2. HoloLens egyaránt támogatja az eszköztitkosítást a BitLocker használatával, a BitLocker azonban mindig engedélyezve van a 2. HoloLens-ben.</span><span class="sxs-lookup"><span data-stu-id="4fddb-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="4fddb-105">Ez a cikk segít a BitLocker engedélyezésében és HoloLens (1. generációs) rendszerében.</span><span class="sxs-lookup"><span data-stu-id="4fddb-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="4fddb-106">A HoloLens (1. generációs) manuálisan vagy mobileszköz-felügyelet (MDM) használatával engedélyezheti a BitLocker-eszköz titkosítását.</span><span class="sxs-lookup"><span data-stu-id="4fddb-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="4fddb-107">Kövesse ezeket az utasításokat a [BitLocker eszköztitkosítás engedélyezéséhez](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) a tárolóban tárolt fájlok és információk HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4fddb-107">Follow these instructions to enable [BitLocker device encryption](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="4fddb-108">Az eszköztitkosítás az AES-CBC 128 titkosítási módszerrel segíti az adatok védelmét, amely egyenértékű a BitLocker konfigurációszolgáltató (CSP) [3. titkosítási módszerével.](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype)</span><span class="sxs-lookup"><span data-stu-id="4fddb-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="4fddb-109">A megfelelő titkosítási kulccsal (például jelszóval) dolgozó személyzet visszafejtheti vagy helyreállíthatja az adatokat.</span><span class="sxs-lookup"><span data-stu-id="4fddb-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="4fddb-110">Eszköz titkosításának engedélyezése MDM használatával</span><span class="sxs-lookup"><span data-stu-id="4fddb-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="4fddb-111">A Mobile Eszközkezelés (MDM) szolgáltatóval eszköztitkosítást igénylő szabályzatot alkalmazhat.</span><span class="sxs-lookup"><span data-stu-id="4fddb-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="4fddb-112">A használni szükséges szabályzat a Házirend CSP [Security/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) beállítása.</span><span class="sxs-lookup"><span data-stu-id="4fddb-112">The policy to use is the [Security/RequireDeviceEncryption setting](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="4fddb-113">Lásd az eszköz titkosításának engedélyezésére vonatkozó utasításokat Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="4fddb-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="4fddb-114">Egyéb MDM-eszközökről az MDM-szolgáltató dokumentációjában talál útmutatást.</span><span class="sxs-lookup"><span data-stu-id="4fddb-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="4fddb-115">Ha az MDM-szolgáltató egyéni URI-t igényel az eszköz titkosításához, használja a következő konfigurációt:</span><span class="sxs-lookup"><span data-stu-id="4fddb-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="4fddb-116">**Név:** egy Ön által választott név</span><span class="sxs-lookup"><span data-stu-id="4fddb-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="4fddb-117">**Leírás:** nem kötelező</span><span class="sxs-lookup"><span data-stu-id="4fddb-117">**Description**: optional</span></span>
- <span data-ttu-id="4fddb-118">**OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="4fddb-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="4fddb-119">**Adattípus:** egész szám</span><span class="sxs-lookup"><span data-stu-id="4fddb-119">**Data type**: integer</span></span>
- <span data-ttu-id="4fddb-120">**Érték:**`1`</span><span class="sxs-lookup"><span data-stu-id="4fddb-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="4fddb-121">Eszköz titkosításának engedélyezése kiépítési csomag használatával</span><span class="sxs-lookup"><span data-stu-id="4fddb-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="4fddb-122">A kiépítési csomagok olyan fájlok, Windows Configuration Designer eszköz által létrehozott fájlok, amelyek egy adott konfigurációt alkalmaznak egy eszközre.</span><span class="sxs-lookup"><span data-stu-id="4fddb-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="4fddb-123">Hozzon létre egy kiépítési csomagot, amely frissíti a Windows Holographic kiadást, és engedélyezi a titkosítást</span><span class="sxs-lookup"><span data-stu-id="4fddb-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="4fddb-124">Hozzon létre egy kiépítési csomagot a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4fddb-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="4fddb-125">Válassza a **Futásidejű beállítások**  >    >  **Házirendek biztonsága lehetőséget,** majd válassza **a RequireDeviceEncryption lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="4fddb-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Igen értékkel konfigurált eszköztitkosítás megkövetelve](images/device-encryption.png)

1. <span data-ttu-id="4fddb-127">Keresse meg a kereskedelmi csomag vásárlásakor megadott XML-licencfájlt.</span><span class="sxs-lookup"><span data-stu-id="4fddb-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="4fddb-128">Keresse meg és válassza ki a Kereskedelmi csomag vásárlásakor megadott XML-licencfájlt.</span><span class="sxs-lookup"><span data-stu-id="4fddb-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="4fddb-129">További [beállításokat a kiépítési csomagban konfigurálhat.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="4fddb-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="4fddb-130">A **File** (Fájl) menüben kattintson a **Save** (Mentés) parancsra.</span><span class="sxs-lookup"><span data-stu-id="4fddb-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="4fddb-131">Olvassa el a figyelmeztetést, amely ismerteti, hogy a projektfájlok bizalmas adatokat tartalmazhatnak, majd kattintson az **OK gombra.**</span><span class="sxs-lookup"><span data-stu-id="4fddb-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4fddb-132">Kiépítési csomag létrehozása során bizalmas adatokat is tartalmazhat a projektfájlokban és a kiépítési csomagfájlban (.ppkg).</span><span class="sxs-lookup"><span data-stu-id="4fddb-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="4fddb-133">Bár lehetősége van a .ppkg fájl titkosítására, a projektfájlok nincsenek titkosítva.</span><span class="sxs-lookup"><span data-stu-id="4fddb-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="4fddb-134">A projektfájlokat érdemes biztonságos helyen tárolni, és törölni a projektfájlokat, ha már nincs rájuk szükség.</span><span class="sxs-lookup"><span data-stu-id="4fddb-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="4fddb-135">Az Exportálás **menüben** kattintson a **Kiépítési csomag elemre.**</span><span class="sxs-lookup"><span data-stu-id="4fddb-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="4fddb-136">Módosítsa **a Tulajdonost** **rendszergazdai** beállításra, amely magasabb prioritást ad meg ennek a kiépítési csomagnak, mint a más forrásokból az eszközre alkalmazott kiépítési csomagoknak, majd válassza a Tovább **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="4fddb-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="4fddb-137">Állítsa be a Package **Version (Csomagverzió) értékét.**</span><span class="sxs-lookup"><span data-stu-id="4fddb-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="4fddb-138">Módosíthatja a meglévő csomagokat, és módosíthatja a verziószámot a korábban alkalmazott csomagok frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="4fddb-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="4fddb-139">A **Kiépítési csomag Biztonsági részletek kiválasztása területén kattintson** a Tovább **gombra.**</span><span class="sxs-lookup"><span data-stu-id="4fddb-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="4fddb-140">Kattintson **a Tovább** gombra annak a kimeneti helynek a megadásához, ahová a kiépítési csomagot létre szeretné hozatni.</span><span class="sxs-lookup"><span data-stu-id="4fddb-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="4fddb-141">Alapértelmezés szerint az Windows ICD a projektmappát használja kimeneti helyként.</span><span class="sxs-lookup"><span data-stu-id="4fddb-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="4fddb-142">Másik lehetőségként a Tallózás gombra kattintva módosíthatja az alapértelmezett kimeneti helyet.</span><span class="sxs-lookup"><span data-stu-id="4fddb-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="4fddb-143">Kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="4fddb-143">Click **Next**.</span></span>
1. <span data-ttu-id="4fddb-144">Kattintson **a Build (Build)** gombra a csomag felépítésének elkezdésében.</span><span class="sxs-lookup"><span data-stu-id="4fddb-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="4fddb-145">A projektinformációk a build oldalán jelennek meg, a folyamatjelző sáv pedig jelzi a build állapotát.</span><span class="sxs-lookup"><span data-stu-id="4fddb-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="4fddb-146">Amikor a build elkészült, kattintson a **Befejezés gombra.**</span><span class="sxs-lookup"><span data-stu-id="4fddb-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="4fddb-147">A kiépítési csomag alkalmazása a HoloLens</span><span class="sxs-lookup"><span data-stu-id="4fddb-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="4fddb-148">Csatlakozás csatlakoztatja az eszközt USB-kapcsolaton keresztül egy számítógéphez,  és indítsa el az eszközt, de ne haladjon tovább a kezdeti beállítási folyamat illesztésén (az első oldalon a kék mezővel).</span><span class="sxs-lookup"><span data-stu-id="4fddb-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="4fddb-149">Röviden nyomja le és engedje el egyszerre a **Volume Down** és **a Power** gombot.</span><span class="sxs-lookup"><span data-stu-id="4fddb-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="4fddb-150">HoloLens adatokat a számítógép Fájlkezelő eszközként fogja mutatni.</span><span class="sxs-lookup"><span data-stu-id="4fddb-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="4fddb-151">A Fájlkezelő húzza a kiépítési csomagot (.ppkg) az eszköz tárhelyére.</span><span class="sxs-lookup"><span data-stu-id="4fddb-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="4fddb-152">Röviden nyomja le és  engedje el egyszerre a **Kötet** le és bekapcsoló gombokat, miközben a beférés **lapon** van.</span><span class="sxs-lookup"><span data-stu-id="4fddb-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="4fddb-153">Az eszköz megkérdezi, hogy megbízik-e a csomagban, és szeretné-e alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="4fddb-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="4fddb-154">Győződjön meg arról, hogy megbízik a csomagban.</span><span class="sxs-lookup"><span data-stu-id="4fddb-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="4fddb-155">Látni fogja, hogy a csomag alkalmazása sikeres volt-e.</span><span class="sxs-lookup"><span data-stu-id="4fddb-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="4fddb-156">Ha nem sikerült, javíthatja a csomagot, és újra próbálkozhat.</span><span class="sxs-lookup"><span data-stu-id="4fddb-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="4fddb-157">Ha sikerrel járt, folytassa az eszköz beállításával.</span><span class="sxs-lookup"><span data-stu-id="4fddb-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="4fddb-158">Ha az eszközt 2016 augusztusa előtt vásárolta meg, be kell jelentkeznie az eszközre egy Microsoft-fiók-val, le kell szereznie a legújabb operációsrendszer-frissítést, majd alaphelyzetbe kell állítania az operációs rendszert a kiépítési csomag alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="4fddb-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="4fddb-159">Az eszköztitkosítás ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="4fddb-159">Verify device encryption</span></span>

<span data-ttu-id="4fddb-160">A titkosítás nem HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4fddb-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="4fddb-161">Az eszköz titkosítási állapotának ellenőrzése:</span><span class="sxs-lookup"><span data-stu-id="4fddb-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="4fddb-162">A HoloLens a Rendszer **Gépház**  >  **oldalon.**  >  </span><span class="sxs-lookup"><span data-stu-id="4fddb-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="4fddb-163">**A BitLocker** **akkor van engedélyezve,** ha az eszköz titkosítva van.</span><span class="sxs-lookup"><span data-stu-id="4fddb-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![A BitLocker használatát bemutató képernyő](images/about-encryption.png)
