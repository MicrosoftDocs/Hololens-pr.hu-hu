---
title: A HoloLens 2 beállítása
description: Megtudhatja, hogyan állíthatja be első alkalommal Wi-Fi a HoloLens 2-t egy Microsoft- (MSA-) vagy Azure Active Directory-fiókkal egy hálózaton keresztül.
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: d46deaf4048e6a649345dc1676a7f8b94d3ad2fc
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379610"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="0d738-104">A HoloLens 2 beállítása</span><span class="sxs-lookup"><span data-stu-id="0d738-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="0d738-105">Az első alkalommal, amikor bekapcsolja a HoloLenst, a rendszer végigvezeti az eszköz beállításán, a felhasználói fiókkal való bejelentkezésen és a HoloLens saját szemének kinyerésén.</span><span class="sxs-lookup"><span data-stu-id="0d738-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="0d738-106">Ez a szakasz végigvezeti a HoloLens 2 kezdeti beállítási folyamatán.</span><span class="sxs-lookup"><span data-stu-id="0d738-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="0d738-107">A következő szakaszban megtudhatja, hogyan dolgozhat a HoloLens-sel, és hogyan kommunikálhat hologramokkal.</span><span class="sxs-lookup"><span data-stu-id="0d738-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="0d738-108">A cikkre való ugráshoz lásd: [Get started with HoloLens 2 (A HoloLens 2 első lépései).](hololens2-basic-usage.md)</span><span class="sxs-lookup"><span data-stu-id="0d738-108">To skip ahead to that article, see [Get started with HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="0d738-109">Előkészületek</span><span class="sxs-lookup"><span data-stu-id="0d738-109">Before you start</span></span>

<span data-ttu-id="0d738-110">Mielőtt hozzá kezd, győződjön meg arról, hogy a következők állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="0d738-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="0d738-111">**Egy hálózati kapcsolat.**</span><span class="sxs-lookup"><span data-stu-id="0d738-111">**A network connection**.</span></span> <span data-ttu-id="0d738-112">A beállításhoz csatlakoztatnia kell a HoloLenst egy hálózathoz.</span><span class="sxs-lookup"><span data-stu-id="0d738-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="0d738-113">A HoloLens 2-vel csatlakozhat Wi-Fi vagy Ethernet használatával (USB-C-to-Ethernet adapter szükséges).</span><span class="sxs-lookup"><span data-stu-id="0d738-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="0d738-114">Az első csatlakozáskor szüksége lesz egy nyílt vagy jelszóval védett hálózatra, amely nem igényel webhely megnyitását vagy tanúsítványokkal való csatlakozást.</span><span class="sxs-lookup"><span data-stu-id="0d738-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="0d738-115">[További információ a HoloLens](hololens-offline.md)által használt webhelyekről.</span><span class="sxs-lookup"><span data-stu-id="0d738-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="0d738-116">**Egy Microsoft-fiók.**</span><span class="sxs-lookup"><span data-stu-id="0d738-116">**A Microsoft account**.</span></span> <span data-ttu-id="0d738-117">A HoloLensbe is be kell jelentkeznie egy Microsoft-fiók -fiókkal (vagy a munkahelyi fiókjával, ha az eszköz a vállalat tulajdonában van).</span><span class="sxs-lookup"><span data-stu-id="0d738-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="0d738-118">Ha még nincs saját Microsoft-fiók, account.microsoft.com [és](https://account.microsoft.com) állítson be egyet ingyenesen.</span><span class="sxs-lookup"><span data-stu-id="0d738-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="0d738-119">**Biztonságos, jól világított tér, amely nem jár veszélyekkel.**</span><span class="sxs-lookup"><span data-stu-id="0d738-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="0d738-120">[Egészségügyi és biztonsági információk.](https://go.microsoft.com/fwlink/p/?LinkId=746661)</span><span class="sxs-lookup"><span data-stu-id="0d738-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="0d738-121">**A** HoloLenshez választható kényelmi kiegészítők a legkényelmesebb illeszkedés érdekében.</span><span class="sxs-lookup"><span data-stu-id="0d738-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="0d738-122">[További információ a illeszkedésről és a kényelemről.](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="0d738-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="0d738-123">A Windows beállítása</span><span class="sxs-lookup"><span data-stu-id="0d738-123">Set up Windows</span></span>

<span data-ttu-id="0d738-124">Amikor először indítja el a HoloLens 2-t, az első feladata a Windows Holographic beállítása.</span><span class="sxs-lookup"><span data-stu-id="0d738-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="0d738-125">Amikor elindítja a HoloLenst, a zene hallatán egy Windows-embléma látható.</span><span class="sxs-lookup"><span data-stu-id="0d738-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Az első rendszerindítás első képernyője](images/01-magic-moment.png)

<span data-ttu-id="0d738-127">A HoloLens 2 a következő lépéseket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="0d738-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="0d738-128">Válassza ki a nyelvet.</span><span class="sxs-lookup"><span data-stu-id="0d738-128">Select your language.</span></span>

    ![Nyelv kiválasztása](images/04-language.png)

1. <span data-ttu-id="0d738-130">Válassza ki a régiót.</span><span class="sxs-lookup"><span data-stu-id="0d738-130">Select your region.</span></span>

    ![Régió kiválasztása](images/05-region.png)

1. <span data-ttu-id="0d738-132">A HoloLens berakni a saját szemének.</span><span class="sxs-lookup"><span data-stu-id="0d738-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="0d738-133">Ha úgy dönt, hogy kihagyja a hitelesítést, a rendszer a következő bejelentkezéskor kérni fogja.</span><span class="sxs-lookup"><span data-stu-id="0d738-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span>

    <span data-ttu-id="0d738-134">A besziratáláshoz több célt is meg kell néznie (ezt gemnek nevezzük).</span><span class="sxs-lookup"><span data-stu-id="0d738-134">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="0d738-135">Nem gond, ha villog vagy bezárja a tekintetét a bepillantás közben, de nem próbál meg más objektumokat nézni a helyiségben vagy a fizikai térben.</span><span class="sxs-lookup"><span data-stu-id="0d738-135">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="0d738-136">A HoloLens ezzel a folyamattal tanulja meg a szem pozícióját, hogy jobban renderelje a holografikus világát.</span><span class="sxs-lookup"><span data-stu-id="0d738-136">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> <span data-ttu-id="0d738-137">A besziratás után a hologramok akkor is helyesen jelennek meg, ha a vizor a fejében eltolást vált.</span><span class="sxs-lookup"><span data-stu-id="0d738-137">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

    <span data-ttu-id="0d738-138">A helyileg tárolt információk az eszközön tárolódnak, és nem kapcsolódnak fiókinformációkhoz.</span><span class="sxs-lookup"><span data-stu-id="0d738-138">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="0d738-139">További információkért [lásd: Az adatok és a biztonsággal kapcsolatos tudnivalók.](hololens-calibration.md#calibration-data-and-security)</span><span class="sxs-lookup"><span data-stu-id="0d738-139">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

    ![A kijelölés képernyője](images/06-et-corners.png)

1. <span data-ttu-id="0d738-141">Csatlakozzon az internethez (válassza a Wi-Fi ethernet-kapcsolatot).</span><span class="sxs-lookup"><span data-stu-id="0d738-141">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="0d738-142">A HoloLens automatikusan beállítja az időzónát a hálózati Wi-Fi alapján.</span><span class="sxs-lookup"><span data-stu-id="0d738-142">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="0d738-143">A telepítés befejezése után a Beállítások alkalmazással módosíthatja az időzónát.</span><span class="sxs-lookup"><span data-stu-id="0d738-143">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Csatlakozás Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="0d738-145">Ha túlhalad az Wi-Fi lépésen, és később másik hálózatra kell váltania, miközben még be van állítva, egyidejűleg nyomja le a Volume **Down** és a **Power** (Lekötve) gombot, hogy visszatérjen erre a lépésre, ha 2019 októberében vagy később futtatja az operációs rendszer verzióját.</span><span class="sxs-lookup"><span data-stu-id="0d738-145">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="0d738-146">Korábbi verziók esetén előfordulhat, [](hololens-recovery.md) hogy alaphelyzetbe kell állítania az eszközt, vagy újra kell indítania egy olyan helyen, ahol a Wi-Fi-hálózat nem érhető el, hogy megakadályozza az automatikus csatlakozást.</span><span class="sxs-lookup"><span data-stu-id="0d738-146">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="0d738-147">Azt is vegye figyelembe, hogy a HoloLens telepítése során a hitelesítő adatok időkorlátja két perc.</span><span class="sxs-lookup"><span data-stu-id="0d738-147">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="0d738-148">A felhasználónevet/jelszót két percen belül meg kell adni, különben a rendszer automatikusan törli a felhasználónév mezőt.</span><span class="sxs-lookup"><span data-stu-id="0d738-148">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="0d738-149">Jelentkezzen be a felhasználói fiókjába.</span><span class="sxs-lookup"><span data-stu-id="0d738-149">Sign in to your user account.</span></span> <span data-ttu-id="0d738-150">Választhat, hogy a saját munkahelyi **vagy** iskolai tulajdonom, és **az én tulajdonom.**</span><span class="sxs-lookup"><span data-stu-id="0d738-150">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    - <span data-ttu-id="0d738-151">Ha a Saját munkahelyi vagy iskolai tulajdonú lehetőséget **választja,** egy Azure AD-fiókkal jelentkezik be.</span><span class="sxs-lookup"><span data-stu-id="0d738-151">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="0d738-152">Ha a szervezet prémium szintű Azure AD és konfigurálta az automatikus MDM-regisztrációt, a HoloLens automatikusan regisztrál az MDM-be.</span><span class="sxs-lookup"><span data-stu-id="0d738-152">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="0d738-153">Ha a szervezet nem használ prémium szintű Azure AD, az automatikus MDM-regisztráció nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="0d738-153">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="0d738-154">Ebben az esetben manuálisan kell regisztrálnia [a HoloLenst az eszközkezelésben.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="0d738-154">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="0d738-155">Adja meg a szervezeti fiók adatait.</span><span class="sxs-lookup"><span data-stu-id="0d738-155">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="0d738-156">Fogadja el az adatvédelmi nyilatkozatot és a végfelhasználói licencszerződést.</span><span class="sxs-lookup"><span data-stu-id="0d738-156">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="0d738-157">Jelentkezzen be Azure AD-beli hitelesítő adataival.</span><span class="sxs-lookup"><span data-stu-id="0d738-157">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="0d738-158">Ez átirányítható a szervezet bejelentkezési oldalára.</span><span class="sxs-lookup"><span data-stu-id="0d738-158">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="0d738-159">Folytassa az eszköz beállítását.</span><span class="sxs-lookup"><span data-stu-id="0d738-159">Continue setting up the device.</span></span>

    - <span data-ttu-id="0d738-160">Ha a Saját **tulajdonom lehetőséget választja,** egy új Microsoft-fiók.</span><span class="sxs-lookup"><span data-stu-id="0d738-160">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="0d738-161">A telepítés befejezése után manuálisan regisztrálhatja [a HoloLenst az eszközkezelésben.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="0d738-161">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="0d738-162">Adja meg Microsoft-fiók adatait.</span><span class="sxs-lookup"><span data-stu-id="0d738-162">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="0d738-163">Írja be a jelszót.</span><span class="sxs-lookup"><span data-stu-id="0d738-163">Enter your password.</span></span> <span data-ttu-id="0d738-164">Ha a Microsoft-fiók [kétlépéses ellenőrzést (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)igényel, akkor teljes körű ellenőrzési folyamatot kell végrehajtania.</span><span class="sxs-lookup"><span data-stu-id="0d738-164">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Felhasználó beállítása](images/13-device-owner.png)

1. <span data-ttu-id="0d738-166">Válassza ki, hogy engedélyezi-e a beszédfelismerést a HoloLens 2-ben, és hogy küld-e diagnosztikai telemetriát.</span><span class="sxs-lookup"><span data-stu-id="0d738-166">Select whether to enable speech on HoloLens 2, and whether to send diagnostic telemetry.</span></span>

    ![Cortana engedélyezése](images/22-do-more-with-voice.png)

1. <span data-ttu-id="0d738-168">Válassza ki a telemetria szintjét.</span><span class="sxs-lookup"><span data-stu-id="0d738-168">Select your telemetry level.</span></span> <span data-ttu-id="0d738-169">Ha lehet, engedélyezze a teljes telemetriát.</span><span class="sxs-lookup"><span data-stu-id="0d738-169">If you can, please enable Full telemetry.</span></span> <span data-ttu-id="0d738-170">Ez az információ igazán segít a HoloLens mérnöki csapatának.</span><span class="sxs-lookup"><span data-stu-id="0d738-170">This information really helps the HoloLens engineering team.</span></span>

     ![Telemetriaszint](images/24-telemetry.png)

1. <span data-ttu-id="0d738-172">Ismerje meg, hogyan használható az indítási kézmozdulat a HoloLens 2-ben.</span><span class="sxs-lookup"><span data-stu-id="0d738-172">Learn how to use the start gesture on HoloLens 2.</span></span>

     <span data-ttu-id="0d738-173">![Az indítási kézmozdulat használatának elsajátítása, 1. kép Az indítási kézmozdulat használatának ](images/26-01-startmenu-learning.png) ![ elsajátítása, 2. kép](images/26-02-startmenu-learning.png)</span><span class="sxs-lookup"><span data-stu-id="0d738-173">![Learn how to use the start gesture, image 1](images/26-01-startmenu-learning.png) ![Learn how to use the start gesture, image 2](images/26-02-startmenu-learning.png)</span></span>

<span data-ttu-id="0d738-174">Gratulálunk!</span><span class="sxs-lookup"><span data-stu-id="0d738-174">Congratulations!</span></span>  <span data-ttu-id="0d738-175">A telepítés befejeződött, és készen áll a HoloLens használatára!</span><span class="sxs-lookup"><span data-stu-id="0d738-175">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="0d738-176">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="0d738-176">Next steps</span></span>

1. <span data-ttu-id="0d738-177">Azonnal elkezdhet interakcióba lépni a Mixed Reality és navigálhat Windows 10 HoloLensen – tekintse meg a **Tippek** alkalmazást, amely gyakorlati oktatóanyagokat ad a kézi interakciókhoz.</span><span class="sxs-lookup"><span data-stu-id="0d738-177">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="0d738-178">Az indítási kézmozdulattal a Start menüre vagy a "Go to Start" (Ugrás az indításra) szövegre, és válassza a Tippek lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0d738-178">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="0d738-179">Az alábbi gombra kattintva tovább olvashat a HoloLens 2-es ki- és beolvasásról.</span><span class="sxs-lookup"><span data-stu-id="0d738-179">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0d738-180">A HoloLens 2 első lépések</span><span class="sxs-lookup"><span data-stu-id="0d738-180">Get started with HoloLens 2</span></span>](hololens2-basic-usage.md)
