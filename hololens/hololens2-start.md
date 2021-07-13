---
title: A 2. HoloLens beállítása
description: Ismerje meg, hogyan állíthatja be HoloLens 2. Wi-Fi-fiókot első alkalommal egy Microsoft- (MSA-) vagy Azure Active Directory- (AAD-) fiókkal.
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: a5c0e28eff9bb71135309ec5e484fc5b88f02d08
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636675"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="6293b-104">A 2. HoloLens beállítása</span><span class="sxs-lookup"><span data-stu-id="6293b-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="6293b-105">Az első alkalommal, amikor bekapcsolja a HoloLens, a rendszer végigvezeti az eszköz beállításán, a felhasználói fiókkal való bejelentkezésen és a HoloLens a szemére.</span><span class="sxs-lookup"><span data-stu-id="6293b-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="6293b-106">Ez a szakasz végigvezeti a HoloLens 2. kezdeti beállítási folyamatán.</span><span class="sxs-lookup"><span data-stu-id="6293b-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="6293b-107">A következő szakaszban megtudhatja, hogyan dolgozhat a hologramokkal HoloLens és hogyan kommunikálhat a hologramokkal.</span><span class="sxs-lookup"><span data-stu-id="6293b-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="6293b-108">A cikkre való ugráshoz tekintse meg a következőt: [Getting around HoloLens 2](hololens2-basic-usage.md).</span><span class="sxs-lookup"><span data-stu-id="6293b-108">To skip ahead to that article, see [Getting around HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="6293b-109">Előkészületek</span><span class="sxs-lookup"><span data-stu-id="6293b-109">Before you start</span></span>

<span data-ttu-id="6293b-110">Mielőtt hozzá kezd, győződjön meg arról, hogy a következők állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="6293b-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="6293b-111">**Egy hálózati kapcsolat.**</span><span class="sxs-lookup"><span data-stu-id="6293b-111">**A network connection**.</span></span> <span data-ttu-id="6293b-112">A beállításhoz csatlakoztatnia HoloLens egy hálózathoz.</span><span class="sxs-lookup"><span data-stu-id="6293b-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="6293b-113">A HoloLens 2-vel csatlakozhat Wi-Fi vagy Ethernet használatával (USB-C-to-Ethernet adapter szükséges).</span><span class="sxs-lookup"><span data-stu-id="6293b-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="6293b-114">Az első csatlakozáskor szüksége lesz egy nyílt vagy jelszóval védett hálózatra, amely nem igényel webhely megnyitását vagy tanúsítványokkal való csatlakozást.</span><span class="sxs-lookup"><span data-stu-id="6293b-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="6293b-115">[További információ a által HoloLens webhelyekről.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="6293b-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="6293b-116">**Egy Microsoft-fiók.**</span><span class="sxs-lookup"><span data-stu-id="6293b-116">**A Microsoft account**.</span></span> <span data-ttu-id="6293b-117">Be kell jelentkeznie a HoloLens egy Microsoft-fiók -fiókkal (vagy a munkahelyi fiókjával, ha az eszköz a vállalat tulajdonában van).</span><span class="sxs-lookup"><span data-stu-id="6293b-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="6293b-118">Ha még nincs saját Microsoft-fiók, account.microsoft.com és [](https://account.microsoft.com) állítson be egyet ingyenesen.</span><span class="sxs-lookup"><span data-stu-id="6293b-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="6293b-119">**Biztonságos, jól világított tér, amely nem jár veszélyekkel.**</span><span class="sxs-lookup"><span data-stu-id="6293b-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="6293b-120">[Egészségügyi és biztonsági információk.](https://go.microsoft.com/fwlink/p/?LinkId=746661)</span><span class="sxs-lookup"><span data-stu-id="6293b-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="6293b-121">**Az opcionális kényelmi kiegészítők,** amelyek a HoloLens, a legkényelmesebb illeszkedés érdekében.</span><span class="sxs-lookup"><span data-stu-id="6293b-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="6293b-122">[További információ a illeszkedésről és a kényelemről.](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="6293b-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="6293b-123">A Windows beállítása</span><span class="sxs-lookup"><span data-stu-id="6293b-123">Set up Windows</span></span>

<span data-ttu-id="6293b-124">A 2. HoloLens első végrehajtásához először be kell állítania Windows Holographict.</span><span class="sxs-lookup"><span data-stu-id="6293b-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="6293b-125">Amikor elkezdi a HoloLens, a zene hallatán egy Windows embléma látható.</span><span class="sxs-lookup"><span data-stu-id="6293b-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Az első rendszerindítás első képernyője](images/01-magic-moment.png)

<span data-ttu-id="6293b-127">Látni fogja, hogy egy madár van a közelben.</span><span class="sxs-lookup"><span data-stu-id="6293b-127">You will see a hummingbird flying around.</span></span>

![Fogmingica-repülőút](images/hummingbird-1.png)

<span data-ttu-id="6293b-129">Kövesse a saját kezében.</span><span class="sxs-lookup"><span data-stu-id="6293b-129">Follow it with your hand.</span></span>

![Közelről a Fogmingbird-höz](images/hummingbird-2.png)

<span data-ttu-id="6293b-131">HoloLens 2. lépés az alábbi lépéseket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="6293b-131">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="6293b-132">Válassza ki a nyelvet.</span><span class="sxs-lookup"><span data-stu-id="6293b-132">Select your language.</span></span>

    ![Nyelv kiválasztása](images/04-language.png)

1. <span data-ttu-id="6293b-134">Válassza ki a régiót.</span><span class="sxs-lookup"><span data-stu-id="6293b-134">Select your region.</span></span>

    ![Régió kiválasztása](images/05-region.png)

1. <span data-ttu-id="6293b-136">A HoloLens be a szemének.</span><span class="sxs-lookup"><span data-stu-id="6293b-136">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="6293b-137">Ha úgy dönt, hogy kihagyja a hitelesítést, a rendszer a következő bejelentkezéskor kérni fogja.</span><span class="sxs-lookup"><span data-stu-id="6293b-137">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span> 

    1. <span data-ttu-id="6293b-138">Először módosítania kell a vizort.</span><span class="sxs-lookup"><span data-stu-id="6293b-138">First, you'll adjust your visor.</span></span>
    
        ![A kijelölés képernyője](images/06-et-corners.png)

    2. <span data-ttu-id="6293b-140">A besziratáláshoz célokat (más néven gemeket) kell látnia.</span><span class="sxs-lookup"><span data-stu-id="6293b-140">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="6293b-141">Nem gond, ha villog vagy bezárja a tekintetét a bepillantás közben, de nem próbál más objektumokra nézni a helyiségben vagy a fizikai térben.</span><span class="sxs-lookup"><span data-stu-id="6293b-141">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="6293b-142">HoloLens a folyamat segítségével megismeri a szem pozícióját, hogy jobban renderelje a holografikus világát.</span><span class="sxs-lookup"><span data-stu-id="6293b-142">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> 

        ![Igazítja a tekintetét](images/07-adjust-eyes.png)

        <span data-ttu-id="6293b-144">A besziranáció után a hologramok akkor is helyesen jelennek meg, ha a vizor a fejében eltolást vált.</span><span class="sxs-lookup"><span data-stu-id="6293b-144">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span> <span data-ttu-id="6293b-145">A rendszer helyben tárolja a helyi eszközön található adatokat, és nem társítja őket fiókinformációkhoz.</span><span class="sxs-lookup"><span data-stu-id="6293b-145">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="6293b-146">További információ: [Az adatok és a biztonság.](hololens-calibration.md#calibration-data-and-security)</span><span class="sxs-lookup"><span data-stu-id="6293b-146">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

        ![A megszabadult](images/calibration-complete.png)

1. <span data-ttu-id="6293b-148">Csatlakozás az internetre (válassza az Wi-Fi ethernet-kapcsolat lehetőséget).</span><span class="sxs-lookup"><span data-stu-id="6293b-148">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="6293b-149">HoloLens automatikusan beállítja az időzónát a hálózati Wi-Fi alapján.</span><span class="sxs-lookup"><span data-stu-id="6293b-149">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="6293b-150">A telepítés befejezése után az időzónát a Gépház módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="6293b-150">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Csatlakozás a Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="6293b-152">Ha az Wi-Fi lépésen túlhalad, és később másik hálózatra kell váltania, miközben még be van állítva, akkor egyidejűleg nyomja le a Volume **Down** és a **Power** (Lekötve) gombot, hogy visszatérjen erre a lépésre, ha 2019 októberében vagy később futtatja az operációs rendszer verzióját.</span><span class="sxs-lookup"><span data-stu-id="6293b-152">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="6293b-153">Korábbi verziók esetén előfordulhat, [](hololens-recovery.md) hogy alaphelyzetbe kell állítania az eszközt, vagy újra kell indítania egy olyan helyen, ahol a Wi-Fi-hálózat nem érhető el, hogy megakadályozza az automatikus csatlakozást.</span><span class="sxs-lookup"><span data-stu-id="6293b-153">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="6293b-154">Azt is vegye figyelembe, HoloLens a hitelesítő adatok két perces időkorlátja van.</span><span class="sxs-lookup"><span data-stu-id="6293b-154">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="6293b-155">A felhasználónevet/jelszót két percen belül meg kell adni, különben a rendszer automatikusan törli a felhasználónév mezőt.</span><span class="sxs-lookup"><span data-stu-id="6293b-155">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="6293b-156">HoloLens 2. példa AutoPilot-profilt keres és alkalmaz, ha van ilyen.</span><span class="sxs-lookup"><span data-stu-id="6293b-156">HoloLens 2 will search and apply an Autopilot profile if one exists.</span></span> <span data-ttu-id="6293b-157">Ezen a képernyőn nincs szükség műveletre.</span><span class="sxs-lookup"><span data-stu-id="6293b-157">No action is needed on this screen.</span></span>
 
    ![Autopilot-profilkeresés](images/autopilot-profile-search.png) 

1. <span data-ttu-id="6293b-159">Kattintson **az Elfogadás** gombra a licencelési képernyőn.</span><span class="sxs-lookup"><span data-stu-id="6293b-159">Click **Accept** on the licensing screen.</span></span>

    ![Windows licencszerződés](images/windows-license-agreement.png)

1. <span data-ttu-id="6293b-161">Jelentkezzen be a felhasználói fiókjába.</span><span class="sxs-lookup"><span data-stu-id="6293b-161">Sign in to your user account.</span></span> <span data-ttu-id="6293b-162">Választhat, hogy a saját munkahelyi **vagy** iskolai tulajdonom, és **az én tulajdonom.**</span><span class="sxs-lookup"><span data-stu-id="6293b-162">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    ![Felhasználó beállítása](images/13-device-owner.png)
    - <span data-ttu-id="6293b-164">Ha a Saját munkahelyi vagy iskolai tulajdonú lehetőséget **választja,** egy Azure AD-fiókkal jelentkezik be.</span><span class="sxs-lookup"><span data-stu-id="6293b-164">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="6293b-165">Ha a szervezet prémium szintű Azure AD és beállította az automatikus MDM-regisztrációt, a HoloLens regisztrál az MDM-be.</span><span class="sxs-lookup"><span data-stu-id="6293b-165">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="6293b-166">Ha a szervezet nem használ prémium szintű Azure AD, az automatikus MDM-regisztráció nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="6293b-166">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="6293b-167">Ebben az esetben manuálisan kell regisztrálnia a HoloLens [eszközkezelésben.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="6293b-167">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="6293b-168">Adja meg a szervezeti fiók adatait.</span><span class="sxs-lookup"><span data-stu-id="6293b-168">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="6293b-169">Fogadja el az adatvédelmi nyilatkozatot és a végfelhasználói licencszerződést.</span><span class="sxs-lookup"><span data-stu-id="6293b-169">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="6293b-170">Jelentkezzen be Azure AD-beli hitelesítő adataival.</span><span class="sxs-lookup"><span data-stu-id="6293b-170">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="6293b-171">Ez átirányítható a szervezet bejelentkezési oldalára.</span><span class="sxs-lookup"><span data-stu-id="6293b-171">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="6293b-172">Folytassa az eszköz beállítását.</span><span class="sxs-lookup"><span data-stu-id="6293b-172">Continue setting up the device.</span></span>

    - <span data-ttu-id="6293b-173">Ha a Saját **tulajdonom lehetőséget választja,** egy új Microsoft-fiók.</span><span class="sxs-lookup"><span data-stu-id="6293b-173">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="6293b-174">A telepítés befejezése után manuálisan regisztrálhatja a HoloLens [eszközkezelésben.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="6293b-174">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="6293b-175">Adja meg Microsoft-fiók adatait.</span><span class="sxs-lookup"><span data-stu-id="6293b-175">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="6293b-176">Írja be a jelszót.</span><span class="sxs-lookup"><span data-stu-id="6293b-176">Enter your password.</span></span> <span data-ttu-id="6293b-177">Ha a Microsoft-fiók [kétlépéses ellenőrzést (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)igényel, akkor teljes körű ellenőrzési folyamatot kell végrehajtania.</span><span class="sxs-lookup"><span data-stu-id="6293b-177">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

        
1. <span data-ttu-id="6293b-178">Az Iris-bejelentkezés beállításához válassza a **Tovább lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="6293b-178">Setup Iris sign-in by selecting **Next**.</span></span> <span data-ttu-id="6293b-179">Hasonló élményt fog tapasztalni, mint a szemkontraszt.</span><span class="sxs-lookup"><span data-stu-id="6293b-179">You will go through a similar experience to the eye calibration.</span></span> <span data-ttu-id="6293b-180">Amikor **a vizsgálat** befejeződött, válassza a Kész lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6293b-180">Select **Done** when the scan is complete.</span></span> <span data-ttu-id="6293b-181">Választhatja a **Kihagyás lehetőséget is** a lépés kihagyása előtt.</span><span class="sxs-lookup"><span data-stu-id="6293b-181">You may also select **Skip** to bypass this step.</span></span>
    
    <span data-ttu-id="6293b-182">![Az írisz ](images/setup-iris.png) ![ beállításának befejezése az írisz beállításához](images/iris-setup-complete.png)</span><span class="sxs-lookup"><span data-stu-id="6293b-182">![Iris setup](images/setup-iris.png) ![Iris setup completion](images/iris-setup-complete.png)</span></span> 
     
  
1. <span data-ttu-id="6293b-183">Pin-kódot fog beállítani az eszközre való bejelentkezéshez.</span><span class="sxs-lookup"><span data-stu-id="6293b-183">You'll setup a PIN to log into the device.</span></span> <span data-ttu-id="6293b-184">Ez a PIN-kód eszközspecifikus.</span><span class="sxs-lookup"><span data-stu-id="6293b-184">This PIN is device specific.</span></span> 

    ![Telepítési Windows Hello](images/setup-windows-hello.png)

    ![Pin Windows Hello pin-kód beállítása](images/windows-hello-pin.png)

    ![Windows Hello A telepítés sikeres](images/windows-hello-successful.png) 
    
1. <span data-ttu-id="6293b-188">Válassza ki, hogy a 2. HoloLens szeretné-e engedélyezni a beszédet.</span><span class="sxs-lookup"><span data-stu-id="6293b-188">Select whether to enable speech on HoloLens 2.</span></span>

    ![A Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="6293b-190">Válassza ki, hogy a 2. HoloLens szeretné-e engedélyezni a helyet.</span><span class="sxs-lookup"><span data-stu-id="6293b-190">Select whether to enable location on HoloLens 2.</span></span>
    
    ![Helyszolgáltatások engedélyezése](images/setup-location-services.png)

1. <span data-ttu-id="6293b-192">Válassza ki a telemetria szintjét.</span><span class="sxs-lookup"><span data-stu-id="6293b-192">Select your telemetry level.</span></span> <span data-ttu-id="6293b-193">Ha lehetséges, engedélyezze a választható telemetriát.</span><span class="sxs-lookup"><span data-stu-id="6293b-193">If you can, please enable Optional telemetry.</span></span> <span data-ttu-id="6293b-194">Ezek az információk nagy segítséget HoloLens mérnöki csapatnak.</span><span class="sxs-lookup"><span data-stu-id="6293b-194">This information really helps the HoloLens engineering team.</span></span>

     ![Telemetriaszint](images/24-telemetry.png)

1. <span data-ttu-id="6293b-196">Ismerje meg, hogyan használhatja az indítási kézmozdulatot HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="6293b-196">Learn how to use the start gesture on HoloLens 2.</span></span>

     ![Az 1. kép kezdő kézmozdulat használatának elsajátítása](images/26-01-startmenu-learning.png)

     ![A 2. kép kezdő kézmozdulat használatának elsajátítása](images/26-02-startmenu-learning.png)

<span data-ttu-id="6293b-199">Gratulálunk!</span><span class="sxs-lookup"><span data-stu-id="6293b-199">Congratulations!</span></span>  <span data-ttu-id="6293b-200">A telepítés befejeződött, és készen áll a HoloLens!</span><span class="sxs-lookup"><span data-stu-id="6293b-200">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="6293b-201">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="6293b-201">Next steps</span></span>

1. <span data-ttu-id="6293b-202">Azonnal elkezdhet interakcióba lépni Mixed Reality és Windows 10 a HoloLens-on – tekintse meg az **Tippek** alkalmazást, amely gyakorlati oktatóanyagokat is elérhető a kéz-interakciókhoz.</span><span class="sxs-lookup"><span data-stu-id="6293b-202">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="6293b-203">Az indítási kézmozdulattal a Start menüre vagy a "Ugrás az indításhoz" szövegre használhatja, majd válassza a Tippek.</span><span class="sxs-lookup"><span data-stu-id="6293b-203">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="6293b-204">Az alábbi gombra kattintva tovább olvashat a 2. HoloLens való ismerkedésről.</span><span class="sxs-lookup"><span data-stu-id="6293b-204">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6293b-205">Tájékozódás a HoloLens 2-ben</span><span class="sxs-lookup"><span data-stu-id="6293b-205">Getting around HoloLens 2</span></span>](hololens2-basic-usage.md)
