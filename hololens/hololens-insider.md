---
title: Belső előzetes verzió a Microsoft HoloLens
description: Ismerje meg az Insider-buildek első lépéseit, és adjon értékes visszajelzést az operációs rendszer következő jelentős frissítésével kapcsolatban a HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636093"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="fbd22-103">Belső előzetes verzió a Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="fbd22-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="fbd22-104">Üdvözöljük az Insider előzetes verziójának legújabb buildjeiben HoloLens!</span><span class="sxs-lookup"><span data-stu-id="fbd22-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="fbd22-105">Az első lépések [egyszerűek,](hololens-insider.md#start-receiving-insider-builds) és értékes visszajelzést adhatunk az operációs rendszer következő jelentős frissítésével kapcsolatban a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fbd22-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="fbd22-106">Windows Belső kibocsátási megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fbd22-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="fbd22-107">Izgatottan várjuk, hogy új funkciókat Windows Insidersbe.</span><span class="sxs-lookup"><span data-stu-id="fbd22-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="fbd22-108">Az új buildek a fejlesztői és bétaverziós csatornákra lesznek felkísértve a legújabb frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="fbd22-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="fbd22-109">Ezt az oldalt folyamatosan frissítjük, ahogy további funkciókat és frissítéseket adunk hozzá a Windows Insider buildjeinkhez.</span><span class="sxs-lookup"><span data-stu-id="fbd22-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="fbd22-110">Legyen izgatott, és készen áll arra, hogy ezeket a frissítéseket a valóságba keverje.</span><span class="sxs-lookup"><span data-stu-id="fbd22-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="fbd22-111">Szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="fbd22-111">Feature</span></span>                 | <span data-ttu-id="fbd22-112">Leírás</span><span class="sxs-lookup"><span data-stu-id="fbd22-112">Description</span></span>                | <span data-ttu-id="fbd22-113">Felhasználó vagy forgatókönyv</span><span class="sxs-lookup"><span data-stu-id="fbd22-113">User or Scenario</span></span> | <span data-ttu-id="fbd22-114">Build bevezetve</span><span class="sxs-lookup"><span data-stu-id="fbd22-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| [<span data-ttu-id="fbd22-115">CSP-módosítások a jelentéskészítési HoloLens részleteihez</span><span class="sxs-lookup"><span data-stu-id="fbd22-115">CSP changes for reporting HoloLens details</span></span>](#csp-changes-for-reporting-hololens-details) | <span data-ttu-id="fbd22-116">Új CSP-k az adatok lekérdezéséhez</span><span class="sxs-lookup"><span data-stu-id="fbd22-116">New CSPs for to query data</span></span> | <span data-ttu-id="fbd22-117">It-rendszergazdák</span><span class="sxs-lookup"><span data-stu-id="fbd22-117">IT Admins</span></span>    | <span data-ttu-id="fbd22-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="fbd22-118">20348.1403</span></span>                 |
| [<span data-ttu-id="fbd22-119">CSP által vezérelt automatikus bejelentkezési szabályzat</span><span class="sxs-lookup"><span data-stu-id="fbd22-119">Auto login policy controlled by CSP</span></span>](#auto-login-policy-controlled-by-csp) | <span data-ttu-id="fbd22-120">Fiók automatikus bejelentkezéshez használatos</span><span class="sxs-lookup"><span data-stu-id="fbd22-120">Used to log in an account automatically</span></span> | <span data-ttu-id="fbd22-121">It-rendszergazdák</span><span class="sxs-lookup"><span data-stu-id="fbd22-121">IT Admins</span></span> | <span data-ttu-id="fbd22-122">20348.1405</span><span class="sxs-lookup"><span data-stu-id="fbd22-122">20348.1405</span></span> |
| [<span data-ttu-id="fbd22-123">PFX-fájl támogatása a Tanúsítványkezelőben</span><span class="sxs-lookup"><span data-stu-id="fbd22-123">PFX file support for Certificate Manager</span></span>](#pfx-file-support-for-certificate-manager) | <span data-ttu-id="fbd22-124">PFX-tanúsítványok hozzáadása Gépház felhasználói felületen</span><span class="sxs-lookup"><span data-stu-id="fbd22-124">Add PFX certs via Settings UI</span></span> | <span data-ttu-id="fbd22-125">Végfelhasználó</span><span class="sxs-lookup"><span data-stu-id="fbd22-125">End User</span></span> | <span data-ttu-id="fbd22-126">20348.1405</span><span class="sxs-lookup"><span data-stu-id="fbd22-126">20348.1405</span></span> |
| [<span data-ttu-id="fbd22-127">Speciális diagnosztikai jelentés megtekintése a Gépház a HoloLens</span><span class="sxs-lookup"><span data-stu-id="fbd22-127">View advanced diagnostic report in Settings on HoloLens</span></span>](#view-advanced-diagnostic-report-in-settings-on-hololens) | <span data-ttu-id="fbd22-128">MDM diagnosztikai naplók megtekintése az eszközön</span><span class="sxs-lookup"><span data-stu-id="fbd22-128">View MDM diagnostic logs on device</span></span> | <span data-ttu-id="fbd22-129">Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="fbd22-129">Troubleshooting</span></span> | <span data-ttu-id="fbd22-130">20348.1405</span><span class="sxs-lookup"><span data-stu-id="fbd22-130">20348.1405</span></span> |
| [<span data-ttu-id="fbd22-131">Offline diagnosztikai értesítések</span><span class="sxs-lookup"><span data-stu-id="fbd22-131">Offline Diagnostics notifications</span></span>](#offline-diagnostics-notifications) | <span data-ttu-id="fbd22-132">Visszajelzés a naplógyűjtéssel kapcsolatban</span><span class="sxs-lookup"><span data-stu-id="fbd22-132">Audiovisual feedback for log collection</span></span> | <span data-ttu-id="fbd22-133">Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="fbd22-133">Troubleshooting</span></span> | <span data-ttu-id="fbd22-134">20348.1405</span><span class="sxs-lookup"><span data-stu-id="fbd22-134">20348.1405</span></span> |


### <a name="csp-changes-for-reporting-hololens-details"></a><span data-ttu-id="fbd22-135">CSP-módosítások a jelentéskészítési HoloLens részleteihez</span><span class="sxs-lookup"><span data-stu-id="fbd22-135">CSP changes for reporting HoloLens details</span></span>

- <span data-ttu-id="fbd22-136">A Windows 20348.1403-as buildben vezettük be</span><span class="sxs-lookup"><span data-stu-id="fbd22-136">Introduced in Windows Insider build, 20348.1403</span></span>

<span data-ttu-id="fbd22-137">Az alábbi CSP-k új módszereket kínálnak a jelentések jelentésére a HoloLens eszközeiről.</span><span class="sxs-lookup"><span data-stu-id="fbd22-137">The following CSPs have been updated with new ways to report information from your HoloLens devices.</span></span>

#### <a name="devdetail-csp---free-storage"></a><span data-ttu-id="fbd22-138">DevDetail CSP – Ingyenes Storage</span><span class="sxs-lookup"><span data-stu-id="fbd22-138">DevDetail CSP - Free Storage</span></span>

<span data-ttu-id="fbd22-139">A DevDetail CSP mostantól a szabad tárterületet is jelenti HoloLens eszközön.</span><span class="sxs-lookup"><span data-stu-id="fbd22-139">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="fbd22-140">Ennek nagyjából meg kell egyeznie az alkalmazás Gépház lapján látható Storage értékkel.</span><span class="sxs-lookup"><span data-stu-id="fbd22-140">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="fbd22-141">Az alábbiakban az ezt az információt tartalmazó csomópont található.</span><span class="sxs-lookup"><span data-stu-id="fbd22-141">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="fbd22-142">./DevDetail/Ext/Microsoft/FreeStorage (csak GET művelet)</span><span class="sxs-lookup"><span data-stu-id="fbd22-142">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp---ssid-and-bssid"></a><span data-ttu-id="fbd22-143">DeviceStatus CSP – SSID és BSSID</span><span class="sxs-lookup"><span data-stu-id="fbd22-143">DeviceStatus CSP - SSID and BSSID</span></span>

<span data-ttu-id="fbd22-144">A DeviceStatus CSP mostantól azon hálózati SSID és BSSID Wi-Fi is jelenti, amelyhez a HoloLens csatlakozik.</span><span class="sxs-lookup"><span data-stu-id="fbd22-144">DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="fbd22-145">A következő csomópontok tartalmazzák ezt az információt.</span><span class="sxs-lookup"><span data-stu-id="fbd22-145">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="fbd22-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-cím* Wi-Fi /SSID</span><span class="sxs-lookup"><span data-stu-id="fbd22-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="fbd22-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span><span class="sxs-lookup"><span data-stu-id="fbd22-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="fbd22-148">Példa syncml blobra (MDM-szállítók számára) a NetworkIdentifiers lekérdezéséhez</span><span class="sxs-lookup"><span data-stu-id="fbd22-148">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a><span data-ttu-id="fbd22-149">CSP által vezérelt automatikus bejelentkezési szabályzat</span><span class="sxs-lookup"><span data-stu-id="fbd22-149">Auto login policy controlled by CSP</span></span>

<span data-ttu-id="fbd22-150">Ez az új AutoLogonUser szabályzat szabályozza, hogy a rendszer automatikusan bejelentkeztet-e egy felhasználót.</span><span class="sxs-lookup"><span data-stu-id="fbd22-150">This new AutoLogonUser policy controls whether a user will be automatically logged on.</span></span> <span data-ttu-id="fbd22-151">Egyes ügyfelek identitáshoz kötött, de bejelentkezési élményt nem kívánó eszközöket is beállítanának.</span><span class="sxs-lookup"><span data-stu-id="fbd22-151">Some customers want to set up devices that are tied to an identity but don't want any sign-in experience.</span></span> <span data-ttu-id="fbd22-152">Imagine eszköz felvétele és azonnali használata a remote assist használatával.</span><span class="sxs-lookup"><span data-stu-id="fbd22-152">Imagine picking up a device and using remote assist immediately.</span></span> <span data-ttu-id="fbd22-153">Vagy az is előnyös, ha gyorsan el tudja terjeszteni a HoloLens eszközeit, és lehetővé teszi a végfelhasználók számára a bejelentkezés gyorsítását.</span><span class="sxs-lookup"><span data-stu-id="fbd22-153">Or have a benefit of being able to rapidly  distribute HoloLens devices and enable their end users to expedite login.</span></span>

<span data-ttu-id="fbd22-154">Ha a szabályzat nem üres értékre van állítva, megadja az automatikus bejelentkezési felhasználó e-mail-címét.</span><span class="sxs-lookup"><span data-stu-id="fbd22-154">When the policy is set to a non-empty value, it specifies the email address of the auto-logon user.</span></span> <span data-ttu-id="fbd22-155">Az automatikus bejelentkezés engedélyezéséhez a megadott felhasználónak legalább egyszer be kell jelentkeznie az eszközre.</span><span class="sxs-lookup"><span data-stu-id="fbd22-155">The specified user must logon to the device at least once to enable auto-logon.</span></span>

<span data-ttu-id="fbd22-156">Az új szabályzat sztringértékének `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` OMA-URI-ját</span><span class="sxs-lookup"><span data-stu-id="fbd22-156">The OMA-URI of new policy `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` String value</span></span>

- <span data-ttu-id="fbd22-157">Az azonos e-mail-címmel rendelkező felhasználónál engedélyezve lesz az automatikus bejelentkezés.</span><span class="sxs-lookup"><span data-stu-id="fbd22-157">User with the same email address will have auto logon enabled.</span></span>

<span data-ttu-id="fbd22-158">Egy olyan eszközön, ahol ez a szabályzat konfigurálva van, a szabályzatban megadott felhasználónak legalább egyszer be kell jelentkeznie.</span><span class="sxs-lookup"><span data-stu-id="fbd22-158">On a device where this policy is configured, the user specified in the policy will need to logon at least once.</span></span> <span data-ttu-id="fbd22-159">Az eszköz az első bejelentkezést követő újraindítása után automatikusan bejelentkezik a megadott felhasználóra.</span><span class="sxs-lookup"><span data-stu-id="fbd22-159">Subsequent reboots of the device after the first logon will have the specified user automatically logged on.</span></span> <span data-ttu-id="fbd22-160">Csak egyetlen automatikus bejelentkezési felhasználó támogatott.</span><span class="sxs-lookup"><span data-stu-id="fbd22-160">Only a single auto-logon user is supported.</span></span> <span data-ttu-id="fbd22-161">Ha engedélyezve van, az automatikusan bejelentkezett felhasználó nem fog tudni manuálisan kijelentkezni.</span><span class="sxs-lookup"><span data-stu-id="fbd22-161">Once enabled, the automatically logged on user will not be able to log out manually.</span></span> <span data-ttu-id="fbd22-162">Ha egy másik felhasználóval jelentkezik be, először le kell tiltani a szabályzatot.</span><span class="sxs-lookup"><span data-stu-id="fbd22-162">To logon as a different user, the policy must first be disabled.</span></span>

> [!NOTE]
> - <span data-ttu-id="fbd22-163">Egyes események, például a fő operációsrendszer-frissítések miatt előfordulhat, hogy a megadott felhasználónak újra be kell jelentkeznie az eszközre az automatikus bejelentkezés folytatásához.</span><span class="sxs-lookup"><span data-stu-id="fbd22-163">Some events such as major OS updates may require the specified user to logon to the device again to resume auto-logon behavior.</span></span> 
> - <span data-ttu-id="fbd22-164">Az automatikus bejelentkezés csak MSA- és AAD-felhasználók számára támogatott.</span><span class="sxs-lookup"><span data-stu-id="fbd22-164">Auto-logon is only supported for MSA and AAD users.</span></span>

### <a name="pfx-file-support-for-certificate-manager"></a><span data-ttu-id="fbd22-165">PFX-fájl támogatása a Tanúsítványkezelőben</span><span class="sxs-lookup"><span data-stu-id="fbd22-165">PFX file support for Certificate Manager</span></span>

<span data-ttu-id="fbd22-166">Az Insider Windows 20348.1405-ös buildben vezettük be.</span><span class="sxs-lookup"><span data-stu-id="fbd22-166">Introduced in Windows Insider build 20348.1405.</span></span> <span data-ttu-id="fbd22-167">Mostantól támogatott a Tanúsítványkezelő a .pfx-tanúsítványok használatára. [](certificate-manager.md)</span><span class="sxs-lookup"><span data-stu-id="fbd22-167">We’ve added support to the [Certificate Manager](certificate-manager.md) to now use .pfx certificates.</span></span> <span data-ttu-id="fbd22-168">Amikor a felhasználók a **Biztonsági tanúsítványok frissítése Gépház** lapra &, és kiválasztják a Tanúsítvány telepítése lehetőséget, a felhasználói felület már támogatja  >    >   **a** .pfx tanúsítványfájlt.</span><span class="sxs-lookup"><span data-stu-id="fbd22-168">When users navigate to **Settings** > **Update & Security** > **Certificates**, and select **Install a certificate** the UI now supports .pfx certificate file.</span></span>
<span data-ttu-id="fbd22-169">A felhasználók titkos kulccsal .pfx-tanúsítványt importálnak a felhasználói tárolóba vagy a számítógép tárolóba.</span><span class="sxs-lookup"><span data-stu-id="fbd22-169">Users can import .pfx certificate, with private key, to user store or machine store.</span></span>

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a><span data-ttu-id="fbd22-170">Speciális diagnosztikai jelentés megtekintése a Gépház a HoloLens</span><span class="sxs-lookup"><span data-stu-id="fbd22-170">View advanced diagnostic report in Settings on HoloLens</span></span>

<span data-ttu-id="fbd22-171">A felügyelt eszközök esetében a viselkedés hibaelhárítása során fontos lépés annak ellenőrzése, hogy a várt házirend-konfiguráció van-e alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="fbd22-171">For managed devices when troubleshooting behavior, confirming that an expected policy configuration is applied is an important step.</span></span> <span data-ttu-id="fbd22-172">Korábban ezt az új funkciót az MDM-en keresztül vagy az eszköz közelében, az **Gépház** Accounts Access munkahelyi vagy iskolai fiókkal összegyűjtött diagnosztikai naplók exportálása után kellett eszközről eltenni, majd a Felügyeleti naplók exportálása és megtekintése egy közeli számítógépen lehetőség  ->    >  **kiválasztásával.** </span><span class="sxs-lookup"><span data-stu-id="fbd22-172">Previously to this new feature, this had to be done off device via MDM or near the device after exporting MDM diagnostic logs gathered via **Settings** -> **Accounts** > **Access work or school**, and select **Export your management logs** and viewed on a nearby PC.</span></span>

<span data-ttu-id="fbd22-173">Az MDM-diagnosztika mostantól megtekinthető az eszközön az Edge böngésző használatával.</span><span class="sxs-lookup"><span data-stu-id="fbd22-173">Now the MDM Diagnostics can be viewed on device using the Edge browser.</span></span> <span data-ttu-id="fbd22-174">Ha könnyebben meg szeretne tekinteni egy MDM diagnosztikai jelentést, lépjen a Hozzáférés munkahelyi vagy iskolai alkalmazáshoz lapra, és válassza a Speciális diagnosztikai **jelentés megtekintése lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="fbd22-174">To more easily view the MDM Diagnostic report navigate to the Access work or school page, and select **View advanced diagnostic report**.</span></span> <span data-ttu-id="fbd22-175">Ez létrehozza és megnyitja a jelentést egy új Edge-ablakban.</span><span class="sxs-lookup"><span data-stu-id="fbd22-175">This will generate and open the report in a new Edge window.</span></span>

![Tekintse meg a speciális diagnosztikai jelentést Gépház alkalmazásban.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a><span data-ttu-id="fbd22-177">Offline diagnosztikai értesítések</span><span class="sxs-lookup"><span data-stu-id="fbd22-177">Offline Diagnostics notifications</span></span>

<span data-ttu-id="fbd22-178">Ez egy offline diagnosztika nevű meglévő [szolgáltatás frissítése.](hololens-diagnostic-logs.md#offline-diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fbd22-178">This an update for an existing feature called [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> <span data-ttu-id="fbd22-179">Korábban nem volt egyértelmű jelzés a felhasználók számára a diagnosztikai gyűjtés aktiválására vagy befejezésére.</span><span class="sxs-lookup"><span data-stu-id="fbd22-179">Previously, there was no clear indicator to users that they had triggered diagnostic collection or it had completed.</span></span>
<span data-ttu-id="fbd22-180">Az Insider Windows buildek két módon adhatnak visszajelzést az offline diagnosztikához.</span><span class="sxs-lookup"><span data-stu-id="fbd22-180">Now added in Windows Insider builds, there are two forms of audiovisual feedback for Offline Diagnostics.</span></span> <span data-ttu-id="fbd22-181">Az első a bejelentések értesítései, amelyek a gyűjtemény indításakor és befejezésekor is megjelennek.</span><span class="sxs-lookup"><span data-stu-id="fbd22-181">The first being toasts notifications displayed for both when collection starts and completes.</span></span> <span data-ttu-id="fbd22-182">Ezek akkor jelennek meg, ha a felhasználó bejelentkezett, és rendelkezik vizualizációval.</span><span class="sxs-lookup"><span data-stu-id="fbd22-182">These will be displayed when the user is logged in and has visuals.</span></span>

![Bejelentés a naplók gyűjtéséhez.](./images/logcollection1.jpg)

![Bejelentés a naplógyűjtés befejezésekor.](./images/logcollection2.jpg)
 
<span data-ttu-id="fbd22-185">Mivel a felhasználók gyakran használják tartalék naplógyűjtési mechanizmusként az Offline diagnosztikát, amikor nem férnek hozzá a kijelzőkhez, nem tudnak bejelentkezni vagy még mindig az OOBE-ban vannak, a naplók gyűjtésekor hangjel is megjelenik.</span><span class="sxs-lookup"><span data-stu-id="fbd22-185">Because users often use Offline Diagnostics as a fallback log gathering mechanism for when they don’t have access to a display, can’t log-in or are still in OOBE there will also be an audio cue played when logs are gathered.</span></span> <span data-ttu-id="fbd22-186">A bejelentési értesítés mellett ez a hang is megjelenik.</span><span class="sxs-lookup"><span data-stu-id="fbd22-186">This sound will be played in addition to the toast notification.</span></span>

<span data-ttu-id="fbd22-187">Ez az új funkció az eszköz frissítésekekor lesz engedélyezve, és nem szükséges engedélyezni vagy kezelni.</span><span class="sxs-lookup"><span data-stu-id="fbd22-187">This new feature will be enabled when your device updates, and doesn’t need to be enabled or managed.</span></span> <span data-ttu-id="fbd22-188">Ha az új visszajelzés nem jelenik meg vagy nem hallható, az Offline diagnosztika továbbra is létrejön.</span><span class="sxs-lookup"><span data-stu-id="fbd22-188">In any event that this new feedback cannot be displayed or heard, Offline Diagnostics will still be generated.</span></span>

<span data-ttu-id="fbd22-189">Reméljük, hogy a visszajelzések újabb kiegészítésével könnyebb diagnosztikai adatokat gyűjteni, és gyorsabban elhárítani a problémákat.</span><span class="sxs-lookup"><span data-stu-id="fbd22-189">We hope with this newer addition of audiovisual feedback it is easier to gather diagnostic data, and more quickly be able to troubleshoot your problems.</span></span>



### <a name="fixes-and-improvements"></a><span data-ttu-id="fbd22-190">Javítások és fejlesztések:</span><span class="sxs-lookup"><span data-stu-id="fbd22-190">Fixes and improvements:</span></span>

- <span data-ttu-id="fbd22-191">Kijavítottunk egy ismert hibát, Eszközportál amikor nem volt [rákérdezés zárolt fájlok letöltésére.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="fbd22-191">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="fbd22-192">Kijavítottunk egy ismert hibát, amely Eszközportál és letöltés időkorrekta [miatt ki volt javítva.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="fbd22-192">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>


## <a name="start-receiving-insider-builds"></a><span data-ttu-id="fbd22-193">Insider-buildek fogadásának elkezde</span><span class="sxs-lookup"><span data-stu-id="fbd22-193">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="fbd22-194">Ha a közelmúltban nem frissített, indítsa újra az eszközt az állapot frissítéséhez, és szerezze be a legújabb buildet.</span><span class="sxs-lookup"><span data-stu-id="fbd22-194">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="fbd22-195">Az "Eszköz újraindítása" hangparancs jól működik.</span><span class="sxs-lookup"><span data-stu-id="fbd22-195">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="fbd22-196">Az újraindítási gombot is választhatja a Gépház/Windows Insider Program.</span><span class="sxs-lookup"><span data-stu-id="fbd22-196">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="fbd22-197">Előfordulhat, hogy egy hiba történt a háttéren, amely miatt ön is találkozhatott, így újra a útjára fog menni.</span><span class="sxs-lookup"><span data-stu-id="fbd22-197">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="fbd22-198">A 2. HoloLens eszközön válassza az **Update** Gépház Security & Windows Insider Program get started (Első  >    >   **lépések) lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="fbd22-198">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="fbd22-199">Csatolja a regisztrációhoz használt fiókot Windows Insiderben.</span><span class="sxs-lookup"><span data-stu-id="fbd22-199">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="fbd22-200">Windows belsős már áttért a Csatornákra.</span><span class="sxs-lookup"><span data-stu-id="fbd22-200">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="fbd22-201">A **Gyors** kör lesz a **fejlesztői** csatorna, a **Lassú** kör lesz a **Béta csatorna,** a kiadási **előnézeti** kör pedig a kiadási **előnézeti csatorna** lesz.</span><span class="sxs-lookup"><span data-stu-id="fbd22-201">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="fbd22-202">A leképezés így néz ki:</span><span class="sxs-lookup"><span data-stu-id="fbd22-202">Here is what that mapping looks like:</span></span>

![Windows A belső csatornák magyarázata](images/WindowsInsiderChannels.png)

<span data-ttu-id="fbd22-204">További információ: [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (A belső csatornák Windows blogok).</span><span class="sxs-lookup"><span data-stu-id="fbd22-204">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="fbd22-205">Ezután válassza az **Active development of Windows of Windows**( Aktív fejlesztés) lehetőséget, válassza ki, hogy szeretné-e megkapni a Dev **Channelt** vagy Béta csatorna **buildeket,** és tekintse át a program feltételeit.</span><span class="sxs-lookup"><span data-stu-id="fbd22-205">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="fbd22-206">A **befejezéshez válassza > Újraindítás most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fbd22-206">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="fbd22-207">Miután az eszköz újraindult, a **Gépház > Update & Security > Frissítések** keresése ás a legújabb buildhez lapra.</span><span class="sxs-lookup"><span data-stu-id="fbd22-207">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="fbd22-208">Hiba 0x80070490 hiba a hibakódok között</span><span class="sxs-lookup"><span data-stu-id="fbd22-208">Update error 0x80070490 work-around</span></span>

<span data-ttu-id="fbd22-209">Ha frissítési hibát 0x80070490 a fejlesztői vagy a bétaverziós csatornán való frissítéskor, próbálkozzon a következő rövid távú munkával.</span><span class="sxs-lookup"><span data-stu-id="fbd22-209">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="fbd22-210">Ez magában foglalja a belső csatorna áthelyezését, a frissítés be- és vissza mozgatát.</span><span class="sxs-lookup"><span data-stu-id="fbd22-210">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="fbd22-211">Első fázis – Előzetes verzió</span><span class="sxs-lookup"><span data-stu-id="fbd22-211">Stage one - Release Preview</span></span>

1.  <span data-ttu-id="fbd22-212">Gépház a Frissítés & security (Biztonsági frissítés) Windows Insider Program válassza a Release Preview Channel (Előzetes **verziójú csatorna) lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="fbd22-212">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>

2.  <span data-ttu-id="fbd22-213">Gépház, Update & Security, Windows Update, **Frissítések keresése.**</span><span class="sxs-lookup"><span data-stu-id="fbd22-213">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="fbd22-214">A frissítés után folytassa a második fázisra.</span><span class="sxs-lookup"><span data-stu-id="fbd22-214">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="fbd22-215">Második fázis – Fejlesztői csatorna</span><span class="sxs-lookup"><span data-stu-id="fbd22-215">Stage two - Dev Channel</span></span>

1. <span data-ttu-id="fbd22-216">Gépház Update & Security (Biztonsági frissítés) lehetőséget, Windows Insider Program válassza a **Dev Channel (Fejlesztői csatorna) lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="fbd22-216">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>

2. <span data-ttu-id="fbd22-217">Gépház, Update & Security, Windows Update, **Frissítések keresése.**</span><span class="sxs-lookup"><span data-stu-id="fbd22-217">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="fbd22-218">FFU letöltési és flash utasítások</span><span class="sxs-lookup"><span data-stu-id="fbd22-218">FFU download and flash directions</span></span>

<span data-ttu-id="fbd22-219">Az aláírt ffu repülőjárattal való teszteléshez először fel kell oldania az eszköz zárolását, mielőtt a repülőjárat aláírt ffu-ját felrakná.</span><span class="sxs-lookup"><span data-stu-id="fbd22-219">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>

1. <span data-ttu-id="fbd22-220">Pc-n:</span><span class="sxs-lookup"><span data-stu-id="fbd22-220">On PC:</span></span>
    1. <span data-ttu-id="fbd22-221">Töltse le a ffu-t a számítógépére a [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) ről.</span><span class="sxs-lookup"><span data-stu-id="fbd22-221">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="fbd22-222">Telepítse az ARC-t (Speciális helyreállítási társ) a következő Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="fbd22-222">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="fbd22-223">On HoloLens - Flight Unlock: Open **Gépház**  >  **Update & Security**  >  **Windows Insider Program** majd regisztráljon, indítsa újra az eszközt.</span><span class="sxs-lookup"><span data-stu-id="fbd22-223">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="fbd22-224">Flash FFU – Most már az ARC használatával is flashlheti a repülőjárat aláírt FFU-ját.</span><span class="sxs-lookup"><span data-stu-id="fbd22-224">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="fbd22-225">Visszajelzés küldése és problémák jelentése</span><span class="sxs-lookup"><span data-stu-id="fbd22-225">Provide feedback and report issues</span></span>

<span data-ttu-id="fbd22-226">A [visszajelzések Visszajelzési központ és a](hololens-feedback.md) jelentésekkel kapcsolatos problémák HoloLens a saját alkalmazásában.</span><span class="sxs-lookup"><span data-stu-id="fbd22-226">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="fbd22-227">A Visszajelzési központ biztosítja, hogy minden szükséges diagnosztikai információt tartalmaz, hogy a mérnökök gyorsan hibakeresést és megoldást tudjanak biztosítani a problémára.</span><span class="sxs-lookup"><span data-stu-id="fbd22-227">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="fbd22-228">A kínai és a japán nyelvű HoloLens ugyanúgy kell jelenteni.</span><span class="sxs-lookup"><span data-stu-id="fbd22-228">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="fbd22-229">Mindenképpen fogadja el azt a kérdést, amely rákérdez, hogy szeretné Visszajelzési központ szeretné-e elérni a Dokumentumok mappát (válassza az **Igen** lehetőséget, amikor a rendszer kéri).</span><span class="sxs-lookup"><span data-stu-id="fbd22-229">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="fbd22-230">Megjegyzés fejlesztőknek</span><span class="sxs-lookup"><span data-stu-id="fbd22-230">Note for developers</span></span>

<span data-ttu-id="fbd22-231">Nyugodtan fejleszthet alkalmazásokat belső fejlesztésű belső HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fbd22-231">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="fbd22-232">Az első [lépésekhez HoloLens tekintse meg az](https://developer.microsoft.com/windows/mixed-reality/development) HoloLens fejlesztői dokumentációját.</span><span class="sxs-lookup"><span data-stu-id="fbd22-232">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="fbd22-233">Ugyanezek az utasítások a kód insider buildje HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fbd22-233">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="fbd22-234">Használhatja a Unity ugyanazon buildeket és Visual Studio, mint a fejlesztéshez HoloLens használ.</span><span class="sxs-lookup"><span data-stu-id="fbd22-234">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="fbd22-235">Insider-buildek fogadásának leállítása</span><span class="sxs-lookup"><span data-stu-id="fbd22-235">Stop receiving Insider builds</span></span>

<span data-ttu-id="fbd22-236">Ha már nem szeretné megkapni az Windows Holographic Insider-buildjét, kikapcsolhatja, ha az HoloLens éles buildet futtat, vagy az Advanced Recovery Companion használatával helyreállíthatja az eszközt az Windows Holographic nem insider verziójára. [](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="fbd22-236">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="fbd22-237">Megjelenik egy ismert probléma, amely miatt az Insider Preview-ból való regisztrációt manuálisan újratelepítő felhasználók kék képernyőt tapasztalnak.</span><span class="sxs-lookup"><span data-stu-id="fbd22-237">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="fbd22-238">Ezt követően manuálisan kell helyreállítania az eszközt.</span><span class="sxs-lookup"><span data-stu-id="fbd22-238">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="fbd22-239">Ha szeretné részletesen ismerni, hogy ez hatással lenne-e a problémára, tekintse meg az ismert [problémát.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="fbd22-239">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>

<span data-ttu-id="fbd22-240">Annak ellenőrzése, hogy a HoloLens futtat-e éles buildet:</span><span class="sxs-lookup"><span data-stu-id="fbd22-240">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="fbd22-241">Keresse meg **Gépház > System > About (Rendszer > about ) et,** és keresse meg a build számát.</span><span class="sxs-lookup"><span data-stu-id="fbd22-241">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="fbd22-242">[Az éles buildszámok kibocsátási megjegyzései.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="fbd22-242">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="fbd22-243">Az Insider-buildek lemondása:</span><span class="sxs-lookup"><span data-stu-id="fbd22-243">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="fbd22-244">Éles buildet HoloLens futtató környezetben válassza az Update Gépház > Security & ( Frissítés **&)** lehetőséget, > Windows Insider Program **Stop Insider builds (Belső** buildek leállítása) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fbd22-244">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="fbd22-245">Az eszköz lemondáshoz kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="fbd22-245">Follow the instructions to opt out your device.</span></span>
