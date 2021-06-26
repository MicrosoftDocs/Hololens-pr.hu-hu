---
title: Alkalmazások oldalbetöltése és telepítése a HoloLens 2 Alkalmazástelepítő
description: Megtudhatja, hogyan telepíthet és háríthatja el az alkalmazások hibáit az alkalmazástelepítővel, illetve hogyan telepíthet alkalmazásokat a felhasználói felületen keresztül.
keywords: alkalmazáskezelés, alkalmazás, hololens, alkalmazástelepítő
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8be5c2ed7fba38b6710aba9c122557a36073a79
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924128"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="79b16-104">Alkalmazások telepítése a HoloLens 2-re a Alkalmazástelepítő</span><span class="sxs-lookup"><span data-stu-id="79b16-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="79b16-105">Ez a funkció a [Windows Holographic 20H2 – 2020.](hololens-release-notes.md)decemberi frissítésében érhető el.</span><span class="sxs-lookup"><span data-stu-id="79b16-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="79b16-106">Ellenőrizze, hogy az eszköz [frissítve van-e](hololens-update-hololens.md) a funkció használatához.</span><span class="sxs-lookup"><span data-stu-id="79b16-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="79b16-107">Új **képességet (Alkalmazástelepítő)** adtunk hozzá, amely lehetővé teszi az alkalmazások zökkenőmentesebb telepítését a HoloLens 2-eszközökön.</span><span class="sxs-lookup"><span data-stu-id="79b16-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="79b16-108">Ez a funkció alapértelmezés szerint be lesz kapcsolva a nem **engedélyezett eszközökön.**</span><span class="sxs-lookup"><span data-stu-id="79b16-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="79b16-109">A vállalatok kimaradásának elkerülése érdekében az alkalmazástelepítő jelenleg nem lesz elérhető **a felügyelt** eszközökhöz.</span><span class="sxs-lookup"><span data-stu-id="79b16-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="79b16-110">Az eszközök akkor minősülnek  "felügyeltnek", ha az alábbiak bármelyike igaz:</span><span class="sxs-lookup"><span data-stu-id="79b16-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="79b16-111">MDM [regisztrálva](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="79b16-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="79b16-112">Kiépítési [csomaggal konfigurálva](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="79b16-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="79b16-113">A felhasználói [identitás](hololens-identity.md) az Azure AD</span><span class="sxs-lookup"><span data-stu-id="79b16-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="79b16-114">Most már anélkül telepíthet alkalmazásokat, hogy engedélyeznie kellene a fejlesztői módot, vagy engedélyeznie kellene a Eszközportál.</span><span class="sxs-lookup"><span data-stu-id="79b16-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="79b16-115">Töltse le (USB-n vagy Microsoft Edge) az Appx-csomagot az eszközre, és navigáljon az Appx-csomaghoz a Fájlkezelő-ban, hogy a rendszer a telepítést elindító kérést kapjon.</span><span class="sxs-lookup"><span data-stu-id="79b16-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="79b16-116">Másik lehetőségként [kezdeményezzen telepítést a weblapról.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)</span><span class="sxs-lookup"><span data-stu-id="79b16-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="79b16-117">Az Microsoft Store-ból telepített alkalmazásokhoz vagy az MDM LOB App Deployment funkcióját használó alkalmazásokhoz hasonló [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) módon az [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) alkalmazásoknak digitálisan alá kell írniuk az aláírási eszközzel, és az aláíráshoz használt tanúsítványnak megbízhatónak kell lennie a HoloLens-eszközben az alkalmazás üzembe helyezése előtt.</span><span class="sxs-lookup"><span data-stu-id="79b16-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="79b16-118">Követelmények</span><span class="sxs-lookup"><span data-stu-id="79b16-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="79b16-119">Az eszközök esetében:</span><span class="sxs-lookup"><span data-stu-id="79b16-119">For your devices:</span></span>

<span data-ttu-id="79b16-120">Ez a funkció jelenleg a HoloLens 2-eszközökhöz használható Windows Holographic 20H2-buildek esetében érhető el.</span><span class="sxs-lookup"><span data-stu-id="79b16-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="79b16-121">Győződjön meg arról, hogy a metódust használó összes [eszköz frissült.](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="79b16-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="79b16-122">Az alkalmazásokhoz:</span><span class="sxs-lookup"><span data-stu-id="79b16-122">For your apps:</span></span>

<span data-ttu-id="79b16-123">Az alkalmazás Megoldáskonfigurációjának  fő  vagy kiadási konfigurációnak kell lennie, mivel a Alkalmazástelepítő az áruház függőségeit fogja használni.</span><span class="sxs-lookup"><span data-stu-id="79b16-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="79b16-124">További információ az [alkalmazáscsomagok létrehozásáról:](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="79b16-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="79b16-125">Az ezzel a módszerrel telepített alkalmazásokat digitális aláírással kell aláírni.</span><span class="sxs-lookup"><span data-stu-id="79b16-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="79b16-126">Az alkalmazás aláíráshoz tanúsítványt kell használnia.</span><span class="sxs-lookup"><span data-stu-id="79b16-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="79b16-127">A tanúsítványt az [MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)megbízható hitelesítésszolgáltatói listájából is lekérheti, ebben az esetben nem kell további műveletet eszközbe vennie.</span><span class="sxs-lookup"><span data-stu-id="79b16-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="79b16-128">Vagy aláírhatja a saját tanúsítványát, de a tanúsítványt le kell majd olni az eszközre.</span><span class="sxs-lookup"><span data-stu-id="79b16-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="79b16-129">Alkalmazások aláírása [az aláíró eszközzel.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="79b16-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="79b16-130">**Tanúsítványbeállítások:**</span><span class="sxs-lookup"><span data-stu-id="79b16-130">**Certificate options:**</span></span>

- [<span data-ttu-id="79b16-131">Ms megbízható hitelesítésszolgáltatói listája</span><span class="sxs-lookup"><span data-stu-id="79b16-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="79b16-132">**Válasszon tanúsítványtelepítési módszert.**</span><span class="sxs-lookup"><span data-stu-id="79b16-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="79b16-133">[A kiépítési](hololens-provisioning.md) csomagok helyi eszközökre alkalmazhatók.</span><span class="sxs-lookup"><span data-stu-id="79b16-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="79b16-134">Az MDM segítségével [tanúsítványokat alkalmazhat az eszközkonfigurációkra.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="79b16-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="79b16-135">Használja a eszközt a [Tanúsítványkezelőben.](certificate-manager.md)</span><span class="sxs-lookup"><span data-stu-id="79b16-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="79b16-136">Telepítési módszer</span><span class="sxs-lookup"><span data-stu-id="79b16-136">Installation method</span></span>

1. <span data-ttu-id="79b16-137">Ellenőrizze, hogy az eszköz nem felügyeltnek minősül-e.</span><span class="sxs-lookup"><span data-stu-id="79b16-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="79b16-138">Ellenőrizze, hogy a HoloLens 2-eszköz be van-e kapcsolva, és hogy be van-e jelentkezve.</span><span class="sxs-lookup"><span data-stu-id="79b16-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="79b16-139">A számítógépen navigáljon az egyéni alkalmazáshoz, és másolja a yourapp.appxbundle et a yourdevicename\Internal Storage\Downloads mappába.</span><span class="sxs-lookup"><span data-stu-id="79b16-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="79b16-140">Miután befejezte a fájl másolását, leválaszthatja az eszközt, és később befejezheti a telepítést.</span><span class="sxs-lookup"><span data-stu-id="79b16-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="79b16-141">A HoloLens 2-eszközön nyissa meg a **Start** menüt, válassza **a** Minden alkalmazás lehetőséget, és indítsa el **Fájlkezelő** alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="79b16-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="79b16-142">Lépjen a Letöltések mappára.</span><span class="sxs-lookup"><span data-stu-id="79b16-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="79b16-143">Előfordulhat, hogy az alkalmazás bal oldali  panelén először az Ez az eszköz lehetőséget kell választania, majd a Letöltések lapra kell navigálnia.</span><span class="sxs-lookup"><span data-stu-id="79b16-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="79b16-144">Válassza ki a yourapp.appxbundle fájlt.</span><span class="sxs-lookup"><span data-stu-id="79b16-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="79b16-145">A Alkalmazástelepítő meg fog indulni.</span><span class="sxs-lookup"><span data-stu-id="79b16-145">The App Installer will launch.</span></span> <span data-ttu-id="79b16-146">Az alkalmazás **telepítéséhez** kattintson a Telepítés gombra.</span><span class="sxs-lookup"><span data-stu-id="79b16-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="79b16-147">A telepített alkalmazás a telepítés befejezésekor automatikusan elindul.</span><span class="sxs-lookup"><span data-stu-id="79b16-147">The installed app will automatically launch upon the completion of installing.</span></span>

![MRTK-példák telepítése Alkalmazástelepítő](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="79b16-149">Telepítésekkel kapcsolatos hibák elhárítása</span><span class="sxs-lookup"><span data-stu-id="79b16-149">Troubleshooting Installs</span></span>

<span data-ttu-id="79b16-150">Ha az alkalmazás telepítése nem sikerült, ellenőrizze a következőket a hibaelhárításhoz:</span><span class="sxs-lookup"><span data-stu-id="79b16-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="79b16-151">Az alkalmazás fő vagy kiadási build.</span><span class="sxs-lookup"><span data-stu-id="79b16-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="79b16-152">Az eszköz egy olyan buildre frissül, amelyen ez a funkció elérhető.</span><span class="sxs-lookup"><span data-stu-id="79b16-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="79b16-153">Csatlakozik [az internethez.](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="79b16-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="79b16-154">A [végpontok megfelelően Microsoft Store](hololens-offline.md) konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="79b16-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="79b16-155">Webes telepítő</span><span class="sxs-lookup"><span data-stu-id="79b16-155">Web Installer</span></span>

<span data-ttu-id="79b16-156">A felhasználók közvetlenül egy webkiszolgálóról telepíthet alkalmazásokat.</span><span class="sxs-lookup"><span data-stu-id="79b16-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="79b16-157">Ez a folyamat az alkalmazást használja Alkalmazástelepítő egyszerű letöltési és telepítési terjesztési módszerrel kombinálva.</span><span class="sxs-lookup"><span data-stu-id="79b16-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="79b16-158">Webes telepítés beállítása:</span><span class="sxs-lookup"><span data-stu-id="79b16-158">How to set up web install:</span></span>

1. <span data-ttu-id="79b16-159">Győződjön meg arról, hogy az alkalmazás megfelelően van konfigurálva a telepítéshez.</span><span class="sxs-lookup"><span data-stu-id="79b16-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="79b16-160">Kövesse az [alábbi lépéseket a weblapról való telepítés engedélyezéséhez.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)</span><span class="sxs-lookup"><span data-stu-id="79b16-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="79b16-161">Végfelhasználói élmény:</span><span class="sxs-lookup"><span data-stu-id="79b16-161">End user experience:</span></span>

1. <span data-ttu-id="79b16-162">A felhasználó a fent kiválasztott módszerrel kap és telepít tanúsítványt az eszközre.</span><span class="sxs-lookup"><span data-stu-id="79b16-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="79b16-163">A felhasználó felkeresi a fenti lépésben létrehozott URL-címet.</span><span class="sxs-lookup"><span data-stu-id="79b16-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="79b16-164">Az alkalmazás most már telepítve lesz az eszközön.</span><span class="sxs-lookup"><span data-stu-id="79b16-164">The app will now install to the device.</span></span> <span data-ttu-id="79b16-165">Az alkalmazás megkereséhez nyissa meg a **Start menü,** és válassza Minden alkalmazás **gombot** az alkalmazás megkereséhez.</span><span class="sxs-lookup"><span data-stu-id="79b16-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="79b16-166">Az alkalmazástelepítő telepítési módszerének hibaelhárításával kapcsolatos további segítségért látogasson el az [alkalmazástelepítő hibáinak elhárításához.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="79b16-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="79b16-167">A felhasználói felület a frissítési folyamat során nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="79b16-167">UI during the update process is not supported.</span></span> <span data-ttu-id="79b16-168">Így a ShowPrompt beállítás ezen [az oldalon és](https://docs.microsoft.com/windows/msix/app-installer/update-settings) a kapcsolódó beállítások nem támogatottak.</span><span class="sxs-lookup"><span data-stu-id="79b16-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="79b16-169">Mintaalkalmazások</span><span class="sxs-lookup"><span data-stu-id="79b16-169">Sample Apps</span></span>

<span data-ttu-id="79b16-170">Próbálja ki a Alkalmazástelepítő az elérhető mintaalkalmazásaink egyikével.</span><span class="sxs-lookup"><span data-stu-id="79b16-170">Try out the App Installer with one of our available sample apps.</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="79b16-171">Mintaalkalmazások</span><span class="sxs-lookup"><span data-stu-id="79b16-171">Sample apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/features-and-samples?tabs=unity#sample-apps)
