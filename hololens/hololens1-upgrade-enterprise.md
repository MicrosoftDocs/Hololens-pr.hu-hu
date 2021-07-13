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
ms.openlocfilehash: b5ae9b0d6859c0f916b5b906e2e9ec54cad6cbd9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635194"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="1cffd-103">A Windows Holographic for Business funkcióinak feloldása</span><span class="sxs-lookup"><span data-stu-id="1cffd-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cffd-104">Ez a lap csak az 1. HoloLens 1. generációsakra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="1cffd-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="1cffd-105">Microsoft HoloLens a Development *Edition* kiadásban érhető el, amely Windows Holographic (a Windows 10 HoloLens-hez tervezett kiadása) és a Commercial [Suite](hololens-commercial-features.md)kiadásában érhető el, amely további üzleti funkciókat biztosít.</span><span class="sxs-lookup"><span data-stu-id="1cffd-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="1cffd-106">A kereskedelmi csomag megvásárlásakor olyan licencet kap, amely a Holographic Windows frissít a Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="1cffd-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="1cffd-107">Ezt a licencet a szervezet mobileszköz-kezelési [(MDM)](#edition-upgrade-by-using-mdm) szolgáltatójával vagy egy kiépítési csomaggal [alkalmazhatja az eszközre.](#edition-upgrade-by-using-a-provisioning-package)</span><span class="sxs-lookup"><span data-stu-id="1cffd-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="1cffd-108">A Windows 10 1803-as verziójában a HoloLens rendszer kiválasztásával ellenőrizheti, hogy a Gépház frissítve **lett-e az üzleti**  >  **kiadásra.**</span><span class="sxs-lookup"><span data-stu-id="1cffd-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="1cffd-109">Kiadásfrissítés MDM használatával</span><span class="sxs-lookup"><span data-stu-id="1cffd-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="1cffd-110">A vállalati licencet bármely olyan MDM-szolgáltató használhatja, amely támogatja a [WindowsLicensing konfigurációs szolgáltatót (CSP).](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx)</span><span class="sxs-lookup"><span data-stu-id="1cffd-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="1cffd-111">A Microsoft MDM API legújabb verziója támogatja a WindowsLicensing CSP-t.</span><span class="sxs-lookup"><span data-stu-id="1cffd-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="1cffd-112">Részletes útmutatás a HoloLens a Microsoft Intune használatával történő frissítéséhez: [A Holographic](/intune/holographic-upgrade)Windows-t futtató eszközök frissítése Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="1cffd-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="1cffd-113">Más MDM-szolgáltatók esetében a házirend beállításának és telepítésének konkrét lépései eltérőek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="1cffd-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="1cffd-114">Kiadásfrissítés kiépítési csomag használatával</span><span class="sxs-lookup"><span data-stu-id="1cffd-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="1cffd-115">A kiépítési csomagok olyan fájlok, Windows Configuration Designer eszköz által létrehozott fájlok, amelyek egy adott konfigurációt alkalmaznak egy eszközre.</span><span class="sxs-lookup"><span data-stu-id="1cffd-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="1cffd-116">Hozzon létre egy kiépítési csomagot, amely frissíti a Windows Holographic kiadást</span><span class="sxs-lookup"><span data-stu-id="1cffd-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="1cffd-117">Hozzon létre egy kiépítési csomagot a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1cffd-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="1cffd-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span><span class="sxs-lookup"><span data-stu-id="1cffd-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Kiadás frissítése a kiválasztott licencbeállítással](images/icd1.png)

1. <span data-ttu-id="1cffd-120">Keresse meg a kereskedelmi csomag vásárlásakor megadott XML-licencfájlt.</span><span class="sxs-lookup"><span data-stu-id="1cffd-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1cffd-121">További [beállításokat a kiépítési csomagban konfigurálhat.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="1cffd-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="1cffd-122">A **Fájl** menüben válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="1cffd-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="1cffd-123">Olvassa el a figyelmeztetést, amely szerint a projektfájlok bizalmas adatokat tartalmazhatnak, majd kattintson az **OK gombra.**</span><span class="sxs-lookup"><span data-stu-id="1cffd-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1cffd-124">Kiépítési csomag létrehozása során bizalmas adatokat is tartalmazhat a projektfájlokban és a kiépítési csomagfájlban (.ppkg).</span><span class="sxs-lookup"><span data-stu-id="1cffd-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="1cffd-125">Bár lehetősége van a .ppkg fájl titkosítására, a projektfájlok nincsenek titkosítva.</span><span class="sxs-lookup"><span data-stu-id="1cffd-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="1cffd-126">A projektfájlokat érdemes biztonságos helyen tárolni, és törölni a projektfájlokat, ha már nincs rájuk szükség.</span><span class="sxs-lookup"><span data-stu-id="1cffd-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="1cffd-127">Az Exportálás **menüben** válassza a **Kiépítési csomag lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="1cffd-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="1cffd-128">Módosítsa **a Tulajdonost** **rendszergazdai** beállításra, amely a kiépítési csomag prioritását magasabbra állítja, mint a különböző forrásokból származó eszközökre alkalmazott többi eszköz, majd válassza a Tovább **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="1cffd-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="1cffd-129">Állítsa be a Package **Version (Csomagverzió) értékét.**</span><span class="sxs-lookup"><span data-stu-id="1cffd-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="1cffd-130">Módosíthatja a meglévő csomagokat, és módosíthatja a verziószámot a korábban alkalmazott csomagok frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="1cffd-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="1cffd-131">A **Kiépítési csomag Biztonsági részletek kiválasztása területén válassza** a Tovább **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="1cffd-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="1cffd-132">Válassza **a Tovább** lehetőséget annak a kimeneti helynek a megadásához, ahová a kiépítési csomagot létre szeretné hozatni.</span><span class="sxs-lookup"><span data-stu-id="1cffd-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="1cffd-133">Alapértelmezés szerint az Windows ICD a projektmappát használja kimeneti helyként.</span><span class="sxs-lookup"><span data-stu-id="1cffd-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="1cffd-134">A Tallózás gombra  kattintva módosíthatja az alapértelmezett kimeneti helyet.</span><span class="sxs-lookup"><span data-stu-id="1cffd-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="1cffd-135">Kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="1cffd-135">Select **Next**.</span></span>

1. <span data-ttu-id="1cffd-136">Válassza **a Build (Build)** lehetőséget a csomag felépítésének elkezdődjön.</span><span class="sxs-lookup"><span data-stu-id="1cffd-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="1cffd-137">A build oldal megjeleníti a projektinformációkat, a folyamatjelző sáv pedig a build állapotát jelzi.</span><span class="sxs-lookup"><span data-stu-id="1cffd-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="1cffd-138">Ha a build elkészült, válassza a **Befejezés lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="1cffd-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="1cffd-139">A kiépítési csomag alkalmazása a HoloLens</span><span class="sxs-lookup"><span data-stu-id="1cffd-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="1cffd-140">Az USB-kábellel csatlakoztassa az eszközt egy számítógéphez.</span><span class="sxs-lookup"><span data-stu-id="1cffd-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="1cffd-141">Indítsa el az eszközt, de  ne haladjon tovább a kezdeti beállítási folyamat illesztésoldalán (az első oldalon a kék mezővel).</span><span class="sxs-lookup"><span data-stu-id="1cffd-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="1cffd-142">A számítógépen a HoloLens eszközként jelenik meg a Fájlkezelő.</span><span class="sxs-lookup"><span data-stu-id="1cffd-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1cffd-143">Ha az HoloLens-eszközön Windows 10 1607-es vagy korábbi verzió fut, nyissa meg az Fájlkezelő-t úgy, hogy rövid időre lenyomja és egyszerre kiadja a **Volume Down** és a **Power** gombokat az eszközön.</span><span class="sxs-lookup"><span data-stu-id="1cffd-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="1cffd-144">A Fájlkezelő húzza a kiépítési csomagot (.ppkg) az eszköz tárhelyére.</span><span class="sxs-lookup"><span data-stu-id="1cffd-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="1cffd-145">Bár HoloLens még mindig az  illesztés lapon van, röviden  nyomja le és engedje el egyszerre a **Kötet** le- és bekapcsolása gombot.</span><span class="sxs-lookup"><span data-stu-id="1cffd-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="1cffd-146">HoloLens rákérdez, hogy megbízik-e a csomagban, és szeretné-e alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="1cffd-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="1cffd-147">Győződjön meg arról, hogy megbízik a csomagban.</span><span class="sxs-lookup"><span data-stu-id="1cffd-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="1cffd-148">Látni fogja, hogy a csomag alkalmazása sikeres volt-e.</span><span class="sxs-lookup"><span data-stu-id="1cffd-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="1cffd-149">Ha nem sikerült alkalmazni, javíthatja a csomagot, és újra megpróbálhatja.</span><span class="sxs-lookup"><span data-stu-id="1cffd-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="1cffd-150">Ha ez sikeres, folytassa az eszköz beállításával.</span><span class="sxs-lookup"><span data-stu-id="1cffd-150">If successful, proceed with device setup.</span></span>
