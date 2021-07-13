---
title: A HoloLens (1. generációs) ismert problémái
description: Maradjon naprakész az ismert problémák és megkerülő megoldások listájával, amelyek hatással lehetnek HoloLens Unityt és a Windows Eszközportál.
keywords: hibaelhárítás, ismert probléma, súgó
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 36991d62da91011b807dfb9ff52ab16eadac8bc7
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640304"
---
# <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="74f64-104">A HoloLens (1. generációs) ismert problémái</span><span class="sxs-lookup"><span data-stu-id="74f64-104">Known issues for HoloLens (1st Gen)</span></span>

<span data-ttu-id="74f64-105">Az alábbi lista a meglévő eszközök ismert HoloLens sorolja fel.</span><span class="sxs-lookup"><span data-stu-id="74f64-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="74f64-106">Először ellenőrizze, hogy szokatlan viselkedést lát-e.</span><span class="sxs-lookup"><span data-stu-id="74f64-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="74f64-107">A lista az új problémák felderített vagy jelentett frissítésekor, illetve a szoftverfrissítések későbbi megoldása során HoloLens frissül.</span><span class="sxs-lookup"><span data-stu-id="74f64-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="74f64-108">Ha olyan problémát tapasztal, amely nem blokkolja, jelentse azt HoloLens eszközén a [Visszajelzési központ.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="74f64-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="74f64-109">Ha a problémája blokkolja a problémát, a visszajelzések küldése mellett kérjük, nyújtsa [be a támogatási kérést.](https://aka.ms/hlsupport)</span><span class="sxs-lookup"><span data-stu-id="74f64-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>


- [<span data-ttu-id="74f64-110">Az összes HoloLens ismert problémái</span><span class="sxs-lookup"><span data-stu-id="74f64-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="74f64-111">A HoloLens (1. generációs) ismert problémái</span><span class="sxs-lookup"><span data-stu-id="74f64-111">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="74f64-112">Az összes HoloLens ismert problémái</span><span class="sxs-lookup"><span data-stu-id="74f64-112">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="74f64-113">Unity</span><span class="sxs-lookup"><span data-stu-id="74f64-113">Unity</span></span>

- <span data-ttu-id="74f64-114">Lásd: [Install the tools](/windows/mixed-reality/install-the-tools) for the most-to-date version of Unity recommended for HoloLens development (A Unity legújabb verziójának telepítése a HoloLens érdekében.</span><span class="sxs-lookup"><span data-stu-id="74f64-114">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="74f64-115">A Unityvel kapcsolatos ismert HoloLens Technical Preview-val kapcsolatos dokumentáció a [HoloLens Unity-fórumokon érhető el.](https://forum.unity3d.com/threads/known-issues.394627/)</span><span class="sxs-lookup"><span data-stu-id="74f64-115">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="74f64-116">Windows Eszközportál</span><span class="sxs-lookup"><span data-stu-id="74f64-116">Windows Device Portal</span></span>

- <span data-ttu-id="74f64-117">A valós idejű Mixed Reality funkció néhány másodpercnyi késést is mutathat.</span><span class="sxs-lookup"><span data-stu-id="74f64-117">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="74f64-118">A Virtuális bemenet lapon a Virtuális kézmozdulatok szakasz Kézmozdulatok és Görgetés vezérlői nem működnek.</span><span class="sxs-lookup"><span data-stu-id="74f64-118">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="74f64-119">A használatuknak nincs hatása.</span><span class="sxs-lookup"><span data-stu-id="74f64-119">Using them will have no effect.</span></span> <span data-ttu-id="74f64-120">A virtuális beviteli oldalon található virtuális billentyűzet megfelelően működik.</span><span class="sxs-lookup"><span data-stu-id="74f64-120">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="74f64-121">A fejlesztői mód Gépház után néhány másodpercet is igénybe vehet, amíg a kapcsoló bekapcsolja a Eszközportál beállítást.</span><span class="sxs-lookup"><span data-stu-id="74f64-121">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="74f64-122">OneDrive feltöltése</span><span class="sxs-lookup"><span data-stu-id="74f64-122">OneDrive camera upload</span></span>

<span data-ttu-id="74f64-123">A OneDrive alkalmazás HoloLens nem támogatja a munkahelyi vagy iskolai fiókok automatikus kamerafeltöltését.</span><span class="sxs-lookup"><span data-stu-id="74f64-123">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="74f64-124">Workarounds:</span><span class="sxs-lookup"><span data-stu-id="74f64-124">Workarounds:</span></span>

- <span data-ttu-id="74f64-125">Ha ez a vállalkozása számára is elérhető, a fogyasztói Microsoft-fiókok támogatják az automatikus kamerafeltöltést.</span><span class="sxs-lookup"><span data-stu-id="74f64-125">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="74f64-126">Munkahelyi vagy iskolai fiókján Microsoft-fiók (a OneDrive alkalmazás támogatja a kettős bejelentkezést).</span><span class="sxs-lookup"><span data-stu-id="74f64-126">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="74f64-127">A profil Microsoft-fiók a OneDrive engedélyezheti az automatikus, háttérkamerás kameratekercs-feltöltést.</span><span class="sxs-lookup"><span data-stu-id="74f64-127">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="74f64-128">Ha nem tud biztonságosan használni fogyasztói Microsoft-fiók a fényképek automatikus feltöltéséhez, manuálisan feltölthet fényképeket a munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="74f64-128">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="74f64-129">Győződjön meg arról, hogy be van jelentkezve munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="74f64-129">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="74f64-130">Kattintson a **+** gombra, majd válassza a **Feltöltés lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="74f64-130">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="74f64-131">Keresse meg a feltölteni kívánt fényképeket vagy videókat a **Pictures (Képek) és a Camera Roll (Kamera >) között.**</span><span class="sxs-lookup"><span data-stu-id="74f64-131">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="74f64-132">Válassza ki a feltölteni kívánt fényképeket vagy videókat, majd kattintson a **Megnyitás gombra.**</span><span class="sxs-lookup"><span data-stu-id="74f64-132">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="74f64-133">A HoloLens (1. generációs) ismert problémái</span><span class="sxs-lookup"><span data-stu-id="74f64-133">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="74f64-134">Nem lehet csatlakozni a virtuális géphez, és HoloLens üzembe Visual Studio</span><span class="sxs-lookup"><span data-stu-id="74f64-134">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="74f64-135">Utolsó frissítés: 8/8 @ 17:11 – Visual Studio megjelent a VS 2019 16.2-es verziója, amely tartalmaz egy javítást a problémára.</span><span class="sxs-lookup"><span data-stu-id="74f64-135">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="74f64-136">Javasoljuk, hogy a hiba elkerülése érdekében frissítsen erre a legújabb verzióra.</span><span class="sxs-lookup"><span data-stu-id="74f64-136">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="74f64-137">Visual Studio MEGJELENT A VS 2019 16.2-es verziója, amely tartalmazza a probléma megoldását.</span><span class="sxs-lookup"><span data-stu-id="74f64-137">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="74f64-138">Javasoljuk, hogy a hiba elkerülése érdekében frissítsen erre a legújabb verzióra.</span><span class="sxs-lookup"><span data-stu-id="74f64-138">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="74f64-139">Probléma kiváltó oka: A probléma kihat az Visual Studio 2015-ös vagy a 2017-es Visual Studio korai verzióit az alkalmazások HoloLens-ban való üzembe helyezésére és hibakeresésére, majd ezt követően az Visual Studio 2017-es vagy 2019-es Visual Studio 2019 HoloLens legújabb verzióit fogja érinteni.</span><span class="sxs-lookup"><span data-stu-id="74f64-139">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="74f64-140">A Visual Studio újabb verziói egy összetevő új verzióját telepítik, de a régebbi verzió fájljai az eszközön maradnak, ami az újabb verzió meghiúsulását okozza.</span><span class="sxs-lookup"><span data-stu-id="74f64-140">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="74f64-141">Ez a következő hibaüzenetet okozza: DEP0100: Győződjön meg arról, hogy a céleszközön engedélyezve van a fejlesztői mód.</span><span class="sxs-lookup"><span data-stu-id="74f64-141">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="74f64-142">Nem sikerült beszerezni a fejlesztői licencét a következő hiba miatt: \<ip\> 80004005.</span><span class="sxs-lookup"><span data-stu-id="74f64-142">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="74f64-143">Áthidaló megoldás</span><span class="sxs-lookup"><span data-stu-id="74f64-143">Workaround</span></span>

<span data-ttu-id="74f64-144">Csapatunk jelenleg a javításon dolgozik.</span><span class="sxs-lookup"><span data-stu-id="74f64-144">Our team is currently working on a fix.</span></span> <span data-ttu-id="74f64-145">Addig is a következő lépésekkel megoldhatja a problémát, és feloldhatja az üzembe helyezés és a hibakeresés blokkolását:</span><span class="sxs-lookup"><span data-stu-id="74f64-145">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="74f64-146">Nyissa meg a Visual Studiót.</span><span class="sxs-lookup"><span data-stu-id="74f64-146">Open Visual Studio.</span></span>

1. <span data-ttu-id="74f64-147">Válassza **a Fájl Új**  >    >  **Project** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="74f64-147">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="74f64-148">Válassza **a Visual C#**  >  **Windows Desktop** Console App  >  **(.NET-keretrendszer)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="74f64-148">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="74f64-149">Nevezze el a projektet (például "HoloLensDeploymentFix"), és győződjön meg arról, hogy a keretrendszer legalább .NET-keretrendszer 4.5-ös, majd kattintson az **OK gombra.**</span><span class="sxs-lookup"><span data-stu-id="74f64-149">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="74f64-150">Kattintson a jobb gombbal a hivatkozások **csomópontra** a Megoldáskezelő és adja hozzá a következő hivatkozásokat (válassza a Tallózás **szakaszt,** majd válassza a Tallózás **lehetőséget):**</span><span class="sxs-lookup"><span data-stu-id="74f64-150">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="74f64-151">Ha nincs telepítve a 10.0.18362.0-s verzió, használja a legújabb verziót.</span><span class="sxs-lookup"><span data-stu-id="74f64-151">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span>

1. <span data-ttu-id="74f64-152">Kattintson a jobb gombbal a projektre a Megoldáskezelő válassza a **Meglévő elem** hozzáadása  >  **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="74f64-152">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="74f64-153">Keresse meg a C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 fájlt, és módosítsa a szűrőt a **következőre: Minden fájl ( . \* \* ).**.</span><span class="sxs-lookup"><span data-stu-id="74f64-153">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="74f64-154">Jelölje ki a SirepClient.dll és a SshClient.dll, majd válassza a **Hozzáadás lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="74f64-154">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="74f64-155">Keresse meg és válassza ki a Megoldáskezelő mindkét fájlt (a fájlok listájának  alján kell lennie), és módosítsa a Másolás a kimeneti könyvtárba a **Tulajdonságok** ablakban a Copy always (Mindig másolás) **beállításra.**</span><span class="sxs-lookup"><span data-stu-id="74f64-155">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="74f64-156">A fájl tetején adja hozzá a következőt a meglévő utasítások `using` listájához:</span><span class="sxs-lookup"><span data-stu-id="74f64-156">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="74f64-157">A `static void Main(...)` alkalmazáson belül adja hozzá a következő kódot:</span><span class="sxs-lookup"><span data-stu-id="74f64-157">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="74f64-158">Válassza a **Build**  >  **Solution (Megoldás összeállítása) lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="74f64-158">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="74f64-159">Nyisson meg egy parancssori ablakot, és cd-vel nyissa meg a lefordított .exe-fájlt tartalmazó mappát (például C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span><span class="sxs-lookup"><span data-stu-id="74f64-159">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="74f64-160">Futtassa a végrehajtható fájlt, és adja meg az eszköz IP-címét parancssori argumentumként.</span><span class="sxs-lookup"><span data-stu-id="74f64-160">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="74f64-161">(Ha USB-kapcsolattal csatlakozik, használhatja a 127.0.0.1-es portot, ellenkező esetben pedig az eszköz Wi-Fi IP-címét.)  Például: "HoloLensDeploymentFix 127.0.0.1".</span><span class="sxs-lookup"><span data-stu-id="74f64-161">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="74f64-162">Miután az eszköz üzenetek nélkül kilépt (ez csak néhány másodpercet vegyen igénybe), üzembe helyezheti az eszközt, és hibakeresést Visual Studio 2017-es vagy újabb Visual Studio után.</span><span class="sxs-lookup"><span data-stu-id="74f64-162">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="74f64-163">Az eszköz további használata nem szükséges.</span><span class="sxs-lookup"><span data-stu-id="74f64-163">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="74f64-164">Amint elérhetővé válnak, további frissítéseket is biztosítanak.</span><span class="sxs-lookup"><span data-stu-id="74f64-164">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="74f64-165">Problémák a Microsoft Store alkalmazások a HoloLens</span><span class="sxs-lookup"><span data-stu-id="74f64-165">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="74f64-166">Utolsó frissítés: 4/2 @ 10:00 – A probléma megoldva.</span><span class="sxs-lookup"><span data-stu-id="74f64-166">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="74f64-167">Problémákat tapasztalhat, amikor megpróbálja elindítani a Microsoft Store alkalmazást a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="74f64-167">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="74f64-168">Megállapítottuk, hogy a probléma akkor fordul elő, ha a háttéralkalmazás frissítései adott sorrendben telepítik a keretrendszer-csomagok újabb verzióját, miközben egy vagy több függő alkalmazás továbbra is fut.</span><span class="sxs-lookup"><span data-stu-id="74f64-168">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="74f64-169">Ebben az esetben egy automatikus alkalmazásfrissítés a .NET Native Framework új verzióját (10.0.25531–10.0.27413) hozta létre, ami miatt a futó alkalmazások nem megfelelően frissülnek a keretrendszer korábbi verzióját fogyasztó összes futó alkalmazás esetében.</span><span class="sxs-lookup"><span data-stu-id="74f64-169">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="74f64-170">A keretrendszer frissítésének folyamata a következő:</span><span class="sxs-lookup"><span data-stu-id="74f64-170">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="74f64-171">A rendszer letölti az új keretrendszercsomagot az áruházból, és telepíti.</span><span class="sxs-lookup"><span data-stu-id="74f64-171">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="74f64-172">Minden alkalmazás régebbi keretrendszer "frissítve" lett az újabb verzió használatára.</span><span class="sxs-lookup"><span data-stu-id="74f64-172">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="74f64-173">Ha a 2. lépés megszakad a befejezés előtt, akkor az újabb keretrendszert nem regisztráló alkalmazások nem indulnak el a Start menüből.</span><span class="sxs-lookup"><span data-stu-id="74f64-173">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="74f64-174">Úgy véljük, hogy a HoloLens bármelyik alkalmazást érintheti ez a probléma.</span><span class="sxs-lookup"><span data-stu-id="74f64-174">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="74f64-175">Egyes felhasználók jelentése szerint a lefagyott alkalmazások bezárása és más alkalmazások ( például Visszajelzési központ, 3D-megjelenítő vagy Photos) bezárása megoldja a problémát számukra – ez azonban az idő 100%-ában nem működik.</span><span class="sxs-lookup"><span data-stu-id="74f64-175">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="74f64-176">Kiváltó okunk az, hogy a problémát nem maga a frissítés okozta, hanem az operációs rendszer egy olyan problémája, amely miatt a .NET Native-keretrendszer frissítése helytelenül lett kezelve.</span><span class="sxs-lookup"><span data-stu-id="74f64-176">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="74f64-177">Örömmel jelentjük be, hogy azonosítottunk egy javítást, és közzétettünk egy, a javítást tartalmazó frissítést (az operációs rendszer 17763.380-as verzióját).</span><span class="sxs-lookup"><span data-stu-id="74f64-177">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="74f64-178">Annak megnézni, hogy az eszköz képes-e a frissítésre:</span><span class="sxs-lookup"><span data-stu-id="74f64-178">To see if your device can take the update:</span></span>

1. <span data-ttu-id="74f64-179">Nyissa meg a Gépház alkalmazást, és nyissa meg **az Update & Security alkalmazást.**</span><span class="sxs-lookup"><span data-stu-id="74f64-179">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="74f64-180">Válassza **a Frissítések keresése lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="74f64-180">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="74f64-181">Ha az 17763.380-as verzióra való frissítés elérhető, frissítsen erre a buildre, hogy megkapja az Alkalmazás lefagy hibajavítását.</span><span class="sxs-lookup"><span data-stu-id="74f64-181">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="74f64-182">Az operációs rendszer ezen verziójára való frissítéskor az Alkalmazásoknak a várt módon kell működnie.</span><span class="sxs-lookup"><span data-stu-id="74f64-182">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="74f64-183">Emellett, ahogy az operációs rendszer minden kiadásával HoloLens, az FFU-rendszerképet is közzétettük a [Microsoft letöltőközpontjában.](https://aka.ms/hololensdownload/10.0.17763.380)</span><span class="sxs-lookup"><span data-stu-id="74f64-183">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="74f64-184">Ha nem szeretné frissíteni a frissítést, 2019. augusztus 29-től a Microsoft Store UWP-alkalmazás új verzióját adták ki.</span><span class="sxs-lookup"><span data-stu-id="74f64-184">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="74f64-185">Miután frissítette az Áruház frissített verzióját:</span><span class="sxs-lookup"><span data-stu-id="74f64-185">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="74f64-186">Nyissa meg az Áruházat, és ellenőrizze, hogy betöltődik-e.</span><span class="sxs-lookup"><span data-stu-id="74f64-186">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="74f64-187">A bloom kézmozdulattal nyissa meg a menüt.</span><span class="sxs-lookup"><span data-stu-id="74f64-187">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="74f64-188">Próbálja meg megnyitni a korábban hibás alkalmazásokat.</span><span class="sxs-lookup"><span data-stu-id="74f64-188">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="74f64-189">Ha továbbra sem indítható el, koppintson és tartsa lenyomva a hibás alkalmazás ikonját, és válassza az eltávolítás lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="74f64-189">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="74f64-190">Telepítse újra ezeket az alkalmazásokat az áruházból.</span><span class="sxs-lookup"><span data-stu-id="74f64-190">Reinstall these apps from the store.</span></span>

<span data-ttu-id="74f64-191">Ha az eszköz továbbra sem tud alkalmazásokat betölteni, a letöltőközponton keresztül a következő lépésekkel töltheti be a .NET Native Framework és a Runtime egy verzióját:</span><span class="sxs-lookup"><span data-stu-id="74f64-191">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="74f64-192">Töltse le [ezt a zip-fájlt](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) a Microsoft letöltőközpontból.</span><span class="sxs-lookup"><span data-stu-id="74f64-192">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="74f64-193">A kicsomagolás két fájlt hoz létre.</span><span class="sxs-lookup"><span data-stu-id="74f64-193">Unzipping will produce two files.</span></span>  <span data-ttu-id="74f64-194">Microsoft .NET.Native.Runtime.1.7.appx és Microsoft .NET.Native.Framework.1.7.appx.</span><span class="sxs-lookup"><span data-stu-id="74f64-194">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="74f64-195">Ellenőrizze, hogy az eszköz fel van-e oldva az eszközön.</span><span class="sxs-lookup"><span data-stu-id="74f64-195">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="74f64-196">Ha ezt még nem tette meg, tekintse meg [a Using the Windows Eszközportál](/windows/mixed-reality/using-the-windows-device-portal) for instructions (A Windows Eszközportál használata) útmutatót.</span><span class="sxs-lookup"><span data-stu-id="74f64-196">If you haven't done that before, see [Using the Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="74f64-197">Ezután be szeretne szerezni a Windows Eszközportál.</span><span class="sxs-lookup"><span data-stu-id="74f64-197">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="74f64-198">Javasoljuk, hogy ezt USB-kapcsolaton keresztül tegye meg, és ehhez gépelje be a http://127.0.0.1:10080 szöveget a böngészőbe.</span><span class="sxs-lookup"><span data-stu-id="74f64-198">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="74f64-199">A Windows Eszközportál után "be kell töltenie" a letöltött két fájlt.</span><span class="sxs-lookup"><span data-stu-id="74f64-199">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="74f64-200">Ezt a bal oldali sávon kell megtennie, amíg el nem jut az **Alkalmazások szakaszhoz,** és válassza az **Alkalmazások lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="74f64-200">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="74f64-201">Ekkor az alábbihoz hasonló képernyő jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="74f64-201">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="74f64-202">Lépjen az Install **App** (Alkalmazás telepítése) szakaszra, és keresse meg a két APPX-fájl kibontott helyét.</span><span class="sxs-lookup"><span data-stu-id="74f64-202">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="74f64-203">Egyszerre csak egyet tud megtenni, ezért miután kiválasztotta az elsőt, kattintson az Üzembe helyezés szakasz "Ugrás" gombjára.</span><span class="sxs-lookup"><span data-stu-id="74f64-203">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="74f64-204">Ezután tegye meg ezt a második APPX-fájlhoz.</span><span class="sxs-lookup"><span data-stu-id="74f64-204">Then do this for the second APPX file.</span></span>

   ![Windows Eszközportál alkalmazás Side-Loaded telepítése](images/20190322-DevicePortal.png)

1. <span data-ttu-id="74f64-206">Úgy véljük, hogy ezen a ponton az alkalmazásoknak újra kell kezdeniük a munkát, és hogy a Store-t is el tudja látni.</span><span class="sxs-lookup"><span data-stu-id="74f64-206">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="74f64-207">Bizonyos esetekben az érintett alkalmazások indítása előtt le kell futtatni a 3D-megjelenítő elindításának további lépését.</span><span class="sxs-lookup"><span data-stu-id="74f64-207">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span>

<span data-ttu-id="74f64-208">Nagyra értékeljük türelmét, mivel végigmentünk a probléma megoldásának folyamatán, és várjuk, hogy továbbra is együtt dolgozunk a közösséggel a sikeres és sikeres Mixed Reality érdekében.</span><span class="sxs-lookup"><span data-stu-id="74f64-208">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="74f64-209">Eszközfrissítés</span><span class="sxs-lookup"><span data-stu-id="74f64-209">Device Update</span></span>

- <span data-ttu-id="74f64-210">Egy új frissítés után 30 másodperccel a rendszerhéj egyszer eltűnik.</span><span class="sxs-lookup"><span data-stu-id="74f64-210">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="74f64-211">A munkamenet **folytatásához hajtsa** végre a Bloom-kézmozdulatot.</span><span class="sxs-lookup"><span data-stu-id="74f64-211">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="74f64-212">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="74f64-212">Visual Studio</span></span>

- <span data-ttu-id="74f64-213">Lásd: [A](/windows/mixed-reality/install-the-tools) Visual Studio legújabb verziójának eszközeinek telepítése HoloLens használata.</span><span class="sxs-lookup"><span data-stu-id="74f64-213">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="74f64-214">Amikor alkalmazást telepít egy Visual Studio-HoloLens, a következő hibaüzenet jelenhet meg: A kért művelet nem hajtható végre olyan fájlon, amely megnyit egy felhasználó által leképezett **szakaszt. (Kivétel HRESULT-ból: 0x800704C8)**.</span><span class="sxs-lookup"><span data-stu-id="74f64-214">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="74f64-215">Ha ez történik, próbálkozzon újra, és az üzembe helyezés általában sikeres lesz.</span><span class="sxs-lookup"><span data-stu-id="74f64-215">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="74f64-216">API</span><span class="sxs-lookup"><span data-stu-id="74f64-216">API</span></span>

- <span data-ttu-id="74f64-217">Ha az alkalmazás [](/windows/mixed-reality/focus-point-in-unity) beállítja a fókuszpontot a felhasználó mögött, vagy a szokásos kamera-továbbítást, a hologramok nem jelennek meg Vegyes valóság rögzítése fényképeken vagy videókban.</span><span class="sxs-lookup"><span data-stu-id="74f64-217">If the application sets the [focus point](/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="74f64-218">Amíg ez a hiba nincs kijavítva a Windows, ha az alkalmazások aktívan beállítják a fókuszpontot, meg kell győződni arról, hogy a sík normál értéke a kamera ellenkező irányában van beállítva (például normal = -camera.forward). [](/windows/mixed-reality/focus-point-in-unity)</span><span class="sxs-lookup"><span data-stu-id="74f64-218">Until this bug is fixed in Windows, if applications actively set the [focus point](/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="74f64-219">Xbox vezeték nélküli vezérlő</span><span class="sxs-lookup"><span data-stu-id="74f64-219">Xbox Wireless Controller</span></span>

- <span data-ttu-id="74f64-220">Az Xbox Vezeték nélküli vezérlő S eszközét frissíteni kell, mielőtt a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="74f64-220">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="74f64-221">Győződjön meg arról, [hogy naprakész,](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) mielőtt a vezérlőt egy új vezérlővel HoloLens.</span><span class="sxs-lookup"><span data-stu-id="74f64-221">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="74f64-222">Ha az Xbox vezeték nélküli HoloLens közben újraindítja a rendszert, a vezérlő nem fog automatikusan újracsatlakozni a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="74f64-222">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="74f64-223">Az Útmutató gomb fénye lassan villog, amíg a vezérlő 3 perc után ki nem indul.</span><span class="sxs-lookup"><span data-stu-id="74f64-223">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="74f64-224">Ha azonnal újra csatlakoztatnia kell a vezérlőt, kikapcsolja a vezérlőt úgy, hogy az Útmutató gombot addig tartja, amíg a világítás ki nem vált.</span><span class="sxs-lookup"><span data-stu-id="74f64-224">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="74f64-225">Amikor újra bekapcsolja a vezérlőt, az újracsatlakozik a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="74f64-225">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="74f64-226">Ha a HoloLens készenléti állapotba lép, miközben az Xbox vezeték nélküli vezérlő csatlakoztatva van, a vezérlő minden bemenete felébreszti a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="74f64-226">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="74f64-227">Ezt úgy előzheti meg, ha kikapcsolja a vezérlőt, amikor már nem használja.</span><span class="sxs-lookup"><span data-stu-id="74f64-227">You can prevent this by powering off your controller when you are done using it.</span></span>

