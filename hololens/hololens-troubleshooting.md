---
title: HoloLens Eszköz hibaelhárítása
description: Maradjon naprakész az eszközök problémáinak és hibaelhárítási HoloLens leggyakoribb megoldásaival kapcsolatban.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problémák, hiba, hibaelhárítás, javítás, súgó, támogatás, HoloLens, emulátor
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635449"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="2ba66-104">Eszköz hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="2ba66-104">Device Troubleshooting</span></span>

<span data-ttu-id="2ba66-105">Ez a cikk több gyakori probléma megoldását HoloLens ismerteti.</span><span class="sxs-lookup"><span data-stu-id="2ba66-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="2ba66-106">A hibaelhárítási eljárás elkezdése előtt győződjön meg arról, hogy az eszköz **20–40** százalék akkumulátor-kapacitással rendelkezik, ha lehetséges.</span><span class="sxs-lookup"><span data-stu-id="2ba66-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="2ba66-107">A [tápkapcsoló alatt](hololens2-setup.md#lights-that-indicate-the-battery-level) található akkumulátorjelző világítással gyorsan ellenőrizheti az akkumulátor kapacitását anélkül, hogy bejelentkezik az eszközre.</span><span class="sxs-lookup"><span data-stu-id="2ba66-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="2ba66-108">**Ismert problémák**</span><span class="sxs-lookup"><span data-stu-id="2ba66-108">**Known Issues**</span></span>
- [<span data-ttu-id="2ba66-109">A Remote Assist videó 20 perc után lefagy</span><span class="sxs-lookup"><span data-stu-id="2ba66-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="2ba66-110">Az automatikus bejelentkezés bejelentkezést kér</span><span class="sxs-lookup"><span data-stu-id="2ba66-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="2ba66-111">Microsoft Edge nem indul el</span><span class="sxs-lookup"><span data-stu-id="2ba66-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="2ba66-112">A billentyűzet nem vált át speciális karakterekre</span><span class="sxs-lookup"><span data-stu-id="2ba66-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="2ba66-113">A zárolt fájlok letöltésekor nem jelenik meg hiba</span><span class="sxs-lookup"><span data-stu-id="2ba66-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="2ba66-114">Eszközportál feltöltési/letöltési időkorrekta</span><span class="sxs-lookup"><span data-stu-id="2ba66-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="2ba66-115">Kék képernyő, miután az Insider előzetes verzióból való igénylést egy Insider buildeléses flash() módban megjelenő eszközön</span><span class="sxs-lookup"><span data-stu-id="2ba66-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="2ba66-116">OneDrive nem tölt fel automatikusan képeket</span><span class="sxs-lookup"><span data-stu-id="2ba66-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="2ba66-117">**Általános**</span><span class="sxs-lookup"><span data-stu-id="2ba66-117">**General**</span></span>
- [<span data-ttu-id="2ba66-118">HoloLens nem válaszol vagy nem indul el</span><span class="sxs-lookup"><span data-stu-id="2ba66-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="2ba66-119">"Kevés lemezterület" hiba</span><span class="sxs-lookup"><span data-stu-id="2ba66-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="2ba66-120">Nem sikerül a beeső hiba</span><span class="sxs-lookup"><span data-stu-id="2ba66-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="2ba66-121">Nem tudok bejelentkezni, mert a HoloLens korábban valaki más számára lett beállítva</span><span class="sxs-lookup"><span data-stu-id="2ba66-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="2ba66-122">A Unity nem működik</span><span class="sxs-lookup"><span data-stu-id="2ba66-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="2ba66-123">Windows Eszközportál nem működik megfelelően</span><span class="sxs-lookup"><span data-stu-id="2ba66-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="2ba66-124">A HoloLens Emulator nem működik</span><span class="sxs-lookup"><span data-stu-id="2ba66-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="2ba66-125">**Bevitel**</span><span class="sxs-lookup"><span data-stu-id="2ba66-125">**Input**</span></span>
- [<span data-ttu-id="2ba66-126">A hangparancsok nem működnek</span><span class="sxs-lookup"><span data-stu-id="2ba66-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="2ba66-127">A kézi bevitel nem működik</span><span class="sxs-lookup"><span data-stu-id="2ba66-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="2ba66-128">**Kapcsolódás**</span><span class="sxs-lookup"><span data-stu-id="2ba66-128">**Connectivity**</span></span>
- [<span data-ttu-id="2ba66-129">Nem lehet csatlakozni a Wi-Fi-hez</span><span class="sxs-lookup"><span data-stu-id="2ba66-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="2ba66-130">**Külső eszközök**</span><span class="sxs-lookup"><span data-stu-id="2ba66-130">**External Devices**</span></span> 
- [<span data-ttu-id="2ba66-131">Bluetooth eszközök nem párosodnak</span><span class="sxs-lookup"><span data-stu-id="2ba66-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="2ba66-132">Az USB-C mikrofon nem működik</span><span class="sxs-lookup"><span data-stu-id="2ba66-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="2ba66-133">A Gépház felsorolt eszközök nem működnek</span><span class="sxs-lookup"><span data-stu-id="2ba66-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="2ba66-134">A Remote Assist videó 20 perc után lefagy</span><span class="sxs-lookup"><span data-stu-id="2ba66-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="2ba66-135">A Remote Assistnek van egy újabb verziója, amely ki lett javítva a problémára.</span><span class="sxs-lookup"><span data-stu-id="2ba66-135">There is a newer version of Remote Assist which has a fix for this issue.</span></span> <span data-ttu-id="2ba66-136">A probléma elkerülése érdekében frissítse a [Remote Assistet](holographic-store-apps.md#update-apps) a legújabb verzióra.</span><span class="sxs-lookup"><span data-stu-id="2ba66-136">Please [update Remote Assist](holographic-store-apps.md#update-apps) to the latest version to avoid this issue.</span></span>

> [!NOTE]
> <span data-ttu-id="2ba66-137">Az ismert probléma súlyossága miatt ideiglenesen szüneteltettünk egy Windows Holographic 21H1-es verziójának elérhetőségét.</span><span class="sxs-lookup"><span data-stu-id="2ba66-137">Due to this Known Issue's severity we had temporarily paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="2ba66-138">A 21H1 build ismét elérhető, így az eszközök ismét frissíthetők a legújabb 21H1 buildre.</span><span class="sxs-lookup"><span data-stu-id="2ba66-138">The 21H1 build is now available again, so devices may once again be updated to the latest 21H1 build.</span></span>

<span data-ttu-id="2ba66-139">Az Windows [Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójának legújabb kiadásában a Remote Assist néhány felhasználója a hívások során több mint 20 perc alatt fagypontot tapasztalt.</span><span class="sxs-lookup"><span data-stu-id="2ba66-139">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="2ba66-140">Ez egy **ismert probléma.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-140">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="2ba66-141">Kerülő megoldások</span><span class="sxs-lookup"><span data-stu-id="2ba66-141">Workarounds</span></span>

<span data-ttu-id="2ba66-142">Ha nem tudja újabb buildre frissíteni a Remote Assistet, próbálkozzon a következővel.</span><span class="sxs-lookup"><span data-stu-id="2ba66-142">If you are unable to update Remote Assist to a newer build try the following work around.</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="2ba66-143">Újraindítás hívások között</span><span class="sxs-lookup"><span data-stu-id="2ba66-143">Restart in between calls</span></span>

<span data-ttu-id="2ba66-144">Ha a hívások hossza 20 percnél hosszabb, és ezt a problémát tapasztalja, próbálja meg újraindítani az eszközt.</span><span class="sxs-lookup"><span data-stu-id="2ba66-144">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="2ba66-145">Ha újraindítja az eszközt a Remote Assist-hívások között, az eszköz frissül, és jó állapotba kerül.</span><span class="sxs-lookup"><span data-stu-id="2ba66-145">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="2ba66-146">Ha gyorsan újraindít egy eszközt a [Holographic Windows 21H1-es verziójában,](hololens-release-notes.md#windows-holographic-version-21h1) nyissa meg a Start menüt, válassza a felhasználó ikont, majd válassza az **Újraindítás lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-146">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

[<span data-ttu-id="2ba66-147">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-147">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="2ba66-148">Az automatikus bejelentkezés bejelentkezést kér</span><span class="sxs-lookup"><span data-stu-id="2ba66-148">Auto-login asks for log-in</span></span>

<span data-ttu-id="2ba66-149">A HoloLens 2-es eszközök konfigurálhatóak úgy, hogy automatikusan bejelentkeznek az **Gépház**  ->  **Accounts**  ->  **Sign-in Options** ->  és a Required (Kötelező) beállításnál állítsa be a Never (Soha) **értéket.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-149">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="2ba66-150">Előfordulhat, hogy egyes felhasználóknak újra be kell jelentkezniük az eszközre, amikor egy jelentős frissítéssel( például funkciófrissítéssel) frissítik az eszközt.</span><span class="sxs-lookup"><span data-stu-id="2ba66-150">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="2ba66-151">Ez egy **ismert probléma.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-151">This is a **known issue**.</span></span>

<span data-ttu-id="2ba66-152">Példa arra, hogy mikor fordulhat elő ez:</span><span class="sxs-lookup"><span data-stu-id="2ba66-152">Example of when this could occur:</span></span>

- <span data-ttu-id="2ba66-153">Eszköz frissítése Windows Holographic 2004-es verziójáról (19041.xxxx build) a Windows Holographic 21H1-es verziójára (Build 20346.xxxx)</span><span class="sxs-lookup"><span data-stu-id="2ba66-153">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="2ba66-154">Egy eszköz frissítése ugyanannak a főverziónak a nagy frissítésére , például a Windows Holographic 2004-es verziójáról a Windows Holographic 20H2-es verziójára</span><span class="sxs-lookup"><span data-stu-id="2ba66-154">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="2ba66-155">Eszköz frissítése gyári rendszerképről a legújabb rendszerképre</span><span class="sxs-lookup"><span data-stu-id="2ba66-155">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="2ba66-156">Ez nem fordulhat elő a következő időszakban:</span><span class="sxs-lookup"><span data-stu-id="2ba66-156">This should not occur during:</span></span>

- <span data-ttu-id="2ba66-157">Havi karbantartási frissítést frissítő eszközök</span><span class="sxs-lookup"><span data-stu-id="2ba66-157">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="2ba66-158">Módszerek használata:</span><span class="sxs-lookup"><span data-stu-id="2ba66-158">Work around methods:</span></span>

- <span data-ttu-id="2ba66-159">Bejelentkezési módszerek, például PIN-kód, jelszó, írisz, webes hitelesítés vagy FIDO2-kulcsok.</span><span class="sxs-lookup"><span data-stu-id="2ba66-159">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="2ba66-160">Ha az eszköz PIN-kódját nem lehet megöröklni, és más hitelesítési módszerek nem érhetők el, akkor a felhasználó használhat manuális [perjeles módot.](hololens-recovery.md#manual-procedure)</span><span class="sxs-lookup"><span data-stu-id="2ba66-160">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="2ba66-161">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-161">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="2ba66-162">Microsoft Edge nem indul el</span><span class="sxs-lookup"><span data-stu-id="2ba66-162">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="2ba66-163">Ezt a problémát eredetileg a csomag szállítási verziójával hozták Microsoft Edge szem előtt tartva.</span><span class="sxs-lookup"><span data-stu-id="2ba66-163">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="2ba66-164">Ez a probléma megoldható az [új](hololens-new-edge.md)Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="2ba66-164">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="2ba66-165">Ha nem, kérjük, visszajelzést írjon.</span><span class="sxs-lookup"><span data-stu-id="2ba66-165">If it is not, please file feedback.</span></span>

<span data-ttu-id="2ba66-166">Néhány ügyfél olyan problémát jelentett, Microsoft Edge nem indul el.</span><span class="sxs-lookup"><span data-stu-id="2ba66-166">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="2ba66-167">Ezen ügyfelek esetében a probléma újraindítással továbbra is fennáll, és nem oldódik meg a Windows vagy alkalmazásfrissítésekkel.</span><span class="sxs-lookup"><span data-stu-id="2ba66-167">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="2ba66-168">Ha ezt a problémát tapasztalja, és megerősítette, hogy [Windows](hololens-updates.md#manually-check-for-updates)naprakész, jelentsen be egy hibát a Visszajelzési központ-alkalmazásból [a](hololens-feedback.md) következő kategóriával és alkategóriával: Install and Update > Downloading, installing, and configuring Windows Update ..</span><span class="sxs-lookup"><span data-stu-id="2ba66-168">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="2ba66-169">Nincsenek ismert megkerülő megoldások, mivel eddig nem sikerült megoldani a problémát.</span><span class="sxs-lookup"><span data-stu-id="2ba66-169">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="2ba66-170">Hiba bejelentése a Visszajelzési központ segít a vizsgálatban!</span><span class="sxs-lookup"><span data-stu-id="2ba66-170">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="2ba66-171">Ez egy **ismert probléma.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-171">This is a **known issue**.</span></span>

[<span data-ttu-id="2ba66-172">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-172">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="2ba66-173">A billentyűzet nem vált át speciális karakterekre</span><span class="sxs-lookup"><span data-stu-id="2ba66-173">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="2ba66-174">Az OOBE során probléma lép fel, amely miatt ha a felhasználó kiválasztott egy munkahelyi vagy iskolai fiókot, és megadta a jelszavát, a billentyűzeten lévő speciális karakterekre próbál átváltani az &123 gombra koppintva, nem változik különleges karakterekre.</span><span class="sxs-lookup"><span data-stu-id="2ba66-174">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="2ba66-175">Ez egy **ismert probléma.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-175">This is a **known issue**.</span></span>

<span data-ttu-id="2ba66-176">A következőt kell körül kell dolgozni:</span><span class="sxs-lookup"><span data-stu-id="2ba66-176">Work-arounds:</span></span>
-   <span data-ttu-id="2ba66-177">Zárja be a billentyűzetet, és nyissa meg újra a szövegmezőre koppintva.</span><span class="sxs-lookup"><span data-stu-id="2ba66-177">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="2ba66-178">Helytelenül adja meg a jelszót.</span><span class="sxs-lookup"><span data-stu-id="2ba66-178">Incorrectly enter your password.</span></span> <span data-ttu-id="2ba66-179">Ha a billentyűzetet a következő alkalommal újraindítják, az a várt módon fog működni.</span><span class="sxs-lookup"><span data-stu-id="2ba66-179">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="2ba66-180">Webes hitelesítés, zárja be a billentyűzetet, és válassza **a Bejelentkezés másik eszközről lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-180">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="2ba66-181">Ha csak számokat ad meg, a felhasználó megnyomhat és lenyomva tarthat bizonyos kulcsokat egy kibontott menü megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="2ba66-181">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="2ba66-182">USB-billentyűzet használata.</span><span class="sxs-lookup"><span data-stu-id="2ba66-182">Using a USB keyboard.</span></span>

<span data-ttu-id="2ba66-183">Ez nincs hatással a következőre:</span><span class="sxs-lookup"><span data-stu-id="2ba66-183">This does not affect:</span></span>
- <span data-ttu-id="2ba66-184">Azok a felhasználók, akik személyes fiókot választanának.</span><span class="sxs-lookup"><span data-stu-id="2ba66-184">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="2ba66-185">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-185">Back to list</span></span>](#list)

## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="2ba66-186">A zárolt fájlok letöltése nem hibás</span><span class="sxs-lookup"><span data-stu-id="2ba66-186">Downloading locked files doesn't error</span></span>

> [!NOTE]
> <span data-ttu-id="2ba66-187">Ez egy **ismert probléma,** amely a Windows Insider build 20348.1403-as verziójában javítva.</span><span class="sxs-lookup"><span data-stu-id="2ba66-187">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>

<span data-ttu-id="2ba66-188">A Holographic Windows korábbi buildje során zárolt fájl letöltésekor az eredmény egy HTTP-hibalap lesz.</span><span class="sxs-lookup"><span data-stu-id="2ba66-188">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="2ba66-189">A Windows Holographic 21H1-es verziójának frissítésében a zárolt fájl letöltésének a kipróbálása azt jelenti, hogy semmi sem látható– a fájl nem tölt le, és nem jelenik meg hiba.</span><span class="sxs-lookup"><span data-stu-id="2ba66-189">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span>

[<span data-ttu-id="2ba66-190">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-190">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="2ba66-191">Eszközportál feltöltési/letöltési időkorrekta</span><span class="sxs-lookup"><span data-stu-id="2ba66-191">Device Portal file upload/download times out</span></span>
> [!NOTE]
> <span data-ttu-id="2ba66-192">Ez egy **ismert probléma,** amely a Windows Insider build 20348.1403-as verziójában javítva.</span><span class="sxs-lookup"><span data-stu-id="2ba66-192">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="2ba66-193">Ha az áthidaló megoldás részeként korábban letiltotta az SSL-kapcsolatot, erősen ajánlott újra engedélyezni.</span><span class="sxs-lookup"><span data-stu-id="2ba66-193">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="2ba66-194">Egyes ügyfelek azt találták, hogy amikor fájlokat próbálnak feltölteni vagy letölteni, előfordulhat, hogy a művelet lefagy, majd időkorrekciót vagy soha nem fejeződik be.</span><span class="sxs-lookup"><span data-stu-id="2ba66-194">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="2ba66-195">Ez elkülönül a " fájl[zárolt"](#downloading-locked-files-doesnt-error) ismert problémától – ez a Windows Holographic 2004-es, 20H2-es és 21H1-es piaci buildeket érinti.</span><span class="sxs-lookup"><span data-stu-id="2ba66-195">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="2ba66-196">A problémát az okozza, hogy a Eszközportál bizonyos kéréseket kezel, és a https használata esetén a leg konzisztensen ad vissza találatot, amely az alapértelmezett beállítás.</span><span class="sxs-lookup"><span data-stu-id="2ba66-196">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="2ba66-197">Áthidaló megoldás</span><span class="sxs-lookup"><span data-stu-id="2ba66-197">Workaround</span></span>

<span data-ttu-id="2ba66-198">Ez az áthidaló megoldás, amely ugyanúgy vonatkozik a Wi-Fi az UsbNcm-re, a "kötelező" beállítás letiltása az "SSL-kapcsolat" alatt.</span><span class="sxs-lookup"><span data-stu-id="2ba66-198">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="2ba66-199">Lépjen a következő oldalra: **Eszközportál, System**( Rendszer) és válassza a **Preferences (Beállítások)** lapot.</span><span class="sxs-lookup"><span data-stu-id="2ba66-199">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="2ba66-200">Az **Eszközbiztonság szakaszban** keresse meg az **SSL-kapcsolatot,** és törölje a jelölését a **Kötelező letiltásához.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-200">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="2ba66-201">A felhasználónak ekkor az http:// kell lennie, https:// (IP-cím) és olyan szolgáltatások, mint a fájlok feltöltése és letöltése működni fog.</span><span class="sxs-lookup"><span data-stu-id="2ba66-201">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="2ba66-202">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-202">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="2ba66-203">Kék képernyő, miután az Insider előzetes verzióból való igénylést egy Insider buildeléses flash() módban megjelenő eszközön</span><span class="sxs-lookup"><span data-stu-id="2ba66-203">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="2ba66-204">Ez a probléma olyan felhasználókra van hatással, akik egy Insider előzetes verziójú builden voltak, új belső előzetes verziójú buildelték újra az HoloLens 2-es verziójukat, majd nem regisztrálták őket az Insider programból.</span><span class="sxs-lookup"><span data-stu-id="2ba66-204">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="2ba66-205">Ez egy **ismert probléma.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-205">This is a **known issue**.</span></span>

<span data-ttu-id="2ba66-206">Ez nincs hatással a következőre:</span><span class="sxs-lookup"><span data-stu-id="2ba66-206">This does not affect:</span></span>
- <span data-ttu-id="2ba66-207">A Windows Insiderben nem regisztrált felhasználók</span><span class="sxs-lookup"><span data-stu-id="2ba66-207">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="2ba66-208">Bennfentesek:</span><span class="sxs-lookup"><span data-stu-id="2ba66-208">Insiders:</span></span>
    - <span data-ttu-id="2ba66-209">Ha egy eszköz az Insider buildek óta regisztrálva lett, az 18362.x verziójú volt</span><span class="sxs-lookup"><span data-stu-id="2ba66-209">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="2ba66-210">Ha egy Insider 19041.x buildet írt alá, és regisztrálva kell maradnia az Insider programban</span><span class="sxs-lookup"><span data-stu-id="2ba66-210">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="2ba66-211">Időző:</span><span class="sxs-lookup"><span data-stu-id="2ba66-211">Work-around:</span></span> 
- <span data-ttu-id="2ba66-212">A probléma elkerülése</span><span class="sxs-lookup"><span data-stu-id="2ba66-212">Avoid the issue</span></span> 
    - <span data-ttu-id="2ba66-213">Flash egy nem belső build.</span><span class="sxs-lookup"><span data-stu-id="2ba66-213">Flash a non-insider build.</span></span> <span data-ttu-id="2ba66-214">A rendszeres havi frissítések egyike.</span><span class="sxs-lookup"><span data-stu-id="2ba66-214">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="2ba66-215">Maradjon az Insider előzetes kiadásában</span><span class="sxs-lookup"><span data-stu-id="2ba66-215">Stay on Insider Preview</span></span>
- <span data-ttu-id="2ba66-216">Az eszköz perjelének átfedő perjele</span><span class="sxs-lookup"><span data-stu-id="2ba66-216">Reflash the device</span></span>

    1. <span data-ttu-id="2ba66-217">Helyezze [a HoloLens 2- et flash (flash)](hololens-recovery.md) módba manuálisan úgy, hogy teljesen lekapcsolód, miközben nem csatlakozik.</span><span class="sxs-lookup"><span data-stu-id="2ba66-217">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="2ba66-218">Ezután a Kötet lenyomva tartási gombra koppintva koppintson a Bekapcsoló gombra.</span><span class="sxs-lookup"><span data-stu-id="2ba66-218">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="2ba66-219">Csatlakozás nyissa meg a számítógépet, és nyissa meg az Advanced Recovery Companiont.</span><span class="sxs-lookup"><span data-stu-id="2ba66-219">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="2ba66-220">A 2. HoloLens az alapértelmezett buildhez.</span><span class="sxs-lookup"><span data-stu-id="2ba66-220">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="2ba66-221">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-221">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="2ba66-222">OneDrive nem tölt fel automatikusan képeket</span><span class="sxs-lookup"><span data-stu-id="2ba66-222">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="2ba66-223">A OneDrive alkalmazás HoloLens támogatja a munkahelyi vagy iskolai fiókok automatikus kamerafeltöltését.</span><span class="sxs-lookup"><span data-stu-id="2ba66-223">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="2ba66-224">Ez egy **ismert probléma.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-224">This is a **known issue**.</span></span>

<span data-ttu-id="2ba66-225">Workarounds:</span><span class="sxs-lookup"><span data-stu-id="2ba66-225">Workarounds:</span></span>

- <span data-ttu-id="2ba66-226">Ha a vállalata számára is elérhető, a fogyasztói Microsoft-fiókok támogatják az automatikus kamerafeltöltést.</span><span class="sxs-lookup"><span data-stu-id="2ba66-226">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="2ba66-227">Munkahelyi vagy iskolai fiókján kívül Microsoft-fiók is bejelentkezhet a fiókba (a OneDrive alkalmazás támogatja a kettős bejelentkezést).</span><span class="sxs-lookup"><span data-stu-id="2ba66-227">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="2ba66-228">A profilban Microsoft-fiók profilból OneDrive automatikus, háttérkamerás kameratekercs-feltöltést is engedélyezhet.</span><span class="sxs-lookup"><span data-stu-id="2ba66-228">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="2ba66-229">Ha nem tud biztonságosan használni fogyasztói Microsoft-fiók a fényképek automatikus feltöltéséhez, manuálisan feltölthet fényképeket a munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="2ba66-229">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="2ba66-230">Győződjön meg arról, hogy be van jelentkezve munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="2ba66-230">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="2ba66-231">Kattintson a **+** gombra, majd válassza a **Feltöltés lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-231">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="2ba66-232">Keresse meg a feltölteni kívánt fényképeket vagy videókat a **Pictures (Képek) > Camera Roll (Kameragörgetés) kiválasztásával.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-232">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="2ba66-233">Válassza ki a feltölteni kívánt fényképeket vagy videókat, majd kattintson a **Megnyitás gombra.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-233">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="2ba66-234">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-234">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="2ba66-235">HoloLens nem válaszol vagy nem indul el</span><span class="sxs-lookup"><span data-stu-id="2ba66-235">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="2ba66-236">Ha a HoloLens nem indul el:</span><span class="sxs-lookup"><span data-stu-id="2ba66-236">If your HoloLens won't start:</span></span>

- <span data-ttu-id="2ba66-237">Ha a bekapcsológomb melletti LED-ek nem világadnak meg, vagy csak egy LED villog rövid időre, előfordulhat, hogy fel kell töltenie a [HoloLens.](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="2ba66-237">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="2ba66-238">Ha a LED-ek bekapcsolódnak, amikor megnyomja a bekapcsológombot, de nem lát semmit a kijelzőkön, állítsa alaphelyzetbe [az eszközt.](hololens-recovery.md#hard-reset-procedure)</span><span class="sxs-lookup"><span data-stu-id="2ba66-238">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="2ba66-239">Ha a HoloLens lefagy vagy nem válaszol:</span><span class="sxs-lookup"><span data-stu-id="2ba66-239">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="2ba66-240">Kapcsolja ki a HoloLens a bekapcsológombbal, amíg mind az öt LED ki nem kapcsolja magát, vagy 15 másodpercig, ha a LED-ek nem válaszolnak.</span><span class="sxs-lookup"><span data-stu-id="2ba66-240">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="2ba66-241">A hálózati HoloLens nyomja meg újra a bekapcsológombot.</span><span class="sxs-lookup"><span data-stu-id="2ba66-241">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="2ba66-242">Ha ezek a lépések nem működnek, megpróbálhatja helyreállítani [HoloLens 2-es](hololens-recovery.md) vagy HoloLens [(1. generációs) eszközt.](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="2ba66-242">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="2ba66-243">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-243">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="2ba66-244">"Kevés lemezterület" hiba</span><span class="sxs-lookup"><span data-stu-id="2ba66-244">"Low Disk Space" error</span></span>

<span data-ttu-id="2ba66-245">Az alábbiak közül egyet vagy többet is el kell szabadítanunk egy vagy több tárolóhelyen:</span><span class="sxs-lookup"><span data-stu-id="2ba66-245">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="2ba66-246">Töröljön néhány nem használt szóközt.</span><span class="sxs-lookup"><span data-stu-id="2ba66-246">Delete some unused spaces.</span></span> <span data-ttu-id="2ba66-247">A Rendszer **Gépház**  >    >  **gombra,** válasszon ki egy olyan helyet, amelyre már nincs szüksége, majd válassza az **Eltávolítás lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-247">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="2ba66-248">Távolítsa el a elhelyezett hologramokat.</span><span class="sxs-lookup"><span data-stu-id="2ba66-248">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="2ba66-249">Töröljön néhány képet és videót a Photos alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="2ba66-249">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="2ba66-250">Távolítsa el az alkalmazásokat a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2ba66-250">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="2ba66-251">A **Minden alkalmazás** koppintson és tartsa lenyomva az eltávolítani kívánt alkalmazást, majd válassza az **Eltávolítás lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-251">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="2ba66-252">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-252">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="2ba66-253">A meghiúsulás</span><span class="sxs-lookup"><span data-stu-id="2ba66-253">Calibration fails</span></span>

<span data-ttu-id="2ba66-254">A legtöbb ember számára működnie kell, de vannak olyan esetek, amikor a beszibrálás sikertelen.</span><span class="sxs-lookup"><span data-stu-id="2ba66-254">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="2ba66-255">Néhány lehetséges ok a meghibásodásra:</span><span class="sxs-lookup"><span data-stu-id="2ba66-255">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="2ba66-256">Elvonja a figyelmet, és nem követi a célokat</span><span class="sxs-lookup"><span data-stu-id="2ba66-256">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="2ba66-257">Nem megfelelően el van állítva a trágár vagy karcolt eszköz vagy az eszköz vizora</span><span class="sxs-lookup"><span data-stu-id="2ba66-257">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="2ba66-258">Trágár vagy karcolt szemüveg</span><span class="sxs-lookup"><span data-stu-id="2ba66-258">Dirty or scratched glasses</span></span>
- <span data-ttu-id="2ba66-259">Bizonyos típusú kapcsolattartási objektívek és szemüveg (színes kapcsolattartó objektívek, néhány toric contact lenses, IR-blokkoló szemüveg, néhány magas szemüveg, napszemüveg vagy hasonló)</span><span class="sxs-lookup"><span data-stu-id="2ba66-259">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="2ba66-260">Jobban kiejtve és perjeles mellékekkel</span><span class="sxs-lookup"><span data-stu-id="2ba66-260">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="2ba66-261">Haj vagy vastag szemüveg, ha blokkolja az eszközt a tekintete előtt</span><span class="sxs-lookup"><span data-stu-id="2ba66-261">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="2ba66-262">Bizonyos szemfizikai, szemkörülmények vagy szemműveletek, például keskeny szem, hosszú szempillák, amblyadás, nystagmus, a LASIK vagy más szemműveletek bizonyos esetekben</span><span class="sxs-lookup"><span data-stu-id="2ba66-262">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="2ba66-263">Sikertelen kísérlet esetén próbálkozzon a következővel:</span><span class="sxs-lookup"><span data-stu-id="2ba66-263">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="2ba66-264">Az eszköz vizorának tisztítása</span><span class="sxs-lookup"><span data-stu-id="2ba66-264">Cleaning your device visor</span></span>
- <span data-ttu-id="2ba66-265">Szemüveg tisztítása</span><span class="sxs-lookup"><span data-stu-id="2ba66-265">Cleaning your glasses</span></span>
- <span data-ttu-id="2ba66-266">Az eszköz vizorának a lehető legnagyobb közelében való eltolás</span><span class="sxs-lookup"><span data-stu-id="2ba66-266">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="2ba66-267">Objektumok mozgatása a vizorban az útból (például haj)</span><span class="sxs-lookup"><span data-stu-id="2ba66-267">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="2ba66-268">Világítás bekapcsolása a helyiségben, vagy a közvetlen világításból való eltálás</span><span class="sxs-lookup"><span data-stu-id="2ba66-268">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="2ba66-269">Ha minden útmutatót követte, és a beszkennálás továbbra is sikertelen, letilthatja a figyelmeztetést a Gépház.</span><span class="sxs-lookup"><span data-stu-id="2ba66-269">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="2ba66-270">Visszajelzést is küldhet a következő [Visszajelzési központ.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="2ba66-270">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="2ba66-271">A képszínekkel vagy a fényerejével kapcsolatos [hibaelhárítással kapcsolatos információkat is itt láthatja.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span><span class="sxs-lookup"><span data-stu-id="2ba66-271">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="2ba66-272">Az IPD beállítása a 2. HoloLens esetén nem alkalmazható, mivel a szempozíciót a rendszer számítja ki.</span><span class="sxs-lookup"><span data-stu-id="2ba66-272">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="2ba66-273">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-273">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="2ba66-274">Nem tudok bejelentkezni, mert a HoloLens korábban valaki más számára lett beállítva</span><span class="sxs-lookup"><span data-stu-id="2ba66-274">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="2ba66-275">Az eszközt [flash **(Flashing)**](hololens-recovery.md#clean-reflash-the-device) módba használhatja, és az Advanced Recovery Companion használatával helyreállíthatja az eszközt.</span><span class="sxs-lookup"><span data-stu-id="2ba66-275">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="2ba66-276">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-276">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="2ba66-277">A Unity nem működik</span><span class="sxs-lookup"><span data-stu-id="2ba66-277">Unity isn't working</span></span>

- <span data-ttu-id="2ba66-278">Lásd: [Install the tools](/windows/mixed-reality/install-the-tools) for the most-to-date version of Unity recommended for HoloLens development (A Unity legújabb verziójának telepítése a HoloLens érdekében.</span><span class="sxs-lookup"><span data-stu-id="2ba66-278">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="2ba66-279">A Unity és a Technical Preview HoloLens ismert problémáit az HoloLens [Unity fórumain találhatja.](https://forum.unity3d.com/threads/known-issues.394627/)</span><span class="sxs-lookup"><span data-stu-id="2ba66-279">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="2ba66-280">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-280">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="2ba66-281">Windows Eszközportál nem működik megfelelően</span><span class="sxs-lookup"><span data-stu-id="2ba66-281">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="2ba66-282">A Rögzítés funkció Live Preview Mixed Reality néhány másodpercnyi késést is mutathat.</span><span class="sxs-lookup"><span data-stu-id="2ba66-282">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="2ba66-283">A Virtuális bemenet lapon a Virtuális kézmozdulatok szakasz Kézmozdulatok és Görgetés vezérlői nem működnek.</span><span class="sxs-lookup"><span data-stu-id="2ba66-283">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="2ba66-284">A használatuknak nincs hatása.</span><span class="sxs-lookup"><span data-stu-id="2ba66-284">Using them will have no effect.</span></span> <span data-ttu-id="2ba66-285">A virtuális beviteli oldalon található virtuális billentyűzet megfelelően működik.</span><span class="sxs-lookup"><span data-stu-id="2ba66-285">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="2ba66-286">A fejlesztői mód Gépház után néhány másodpercet is igénybe vehet, amíg a kapcsoló bekapcsolja a Eszközportál beállítást.</span><span class="sxs-lookup"><span data-stu-id="2ba66-286">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="2ba66-287">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-287">Back to list</span></span>](#list)

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="2ba66-288">A HoloLens Emulator nem működik</span><span class="sxs-lookup"><span data-stu-id="2ba66-288">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="2ba66-289">A HoloLens emulátorról a fejlesztői dokumentációnkban tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="2ba66-289">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="2ba66-290">További információ [a HoloLens emulátor hibaelhárításáról.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="2ba66-290">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="2ba66-291">Nem minden alkalmazás kompatibilis Microsoft Store az emulátorsal.</span><span class="sxs-lookup"><span data-stu-id="2ba66-291">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="2ba66-292">A Young Conker és a Fragments például nem lejátszható az emulátoron.</span><span class="sxs-lookup"><span data-stu-id="2ba66-292">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="2ba66-293">A számítógép webkameráját nem használhatja a Emulator.</span><span class="sxs-lookup"><span data-stu-id="2ba66-293">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="2ba66-294">A szolgáltatás Live Preview Windows Eszközportál nem működik az emulátorral.</span><span class="sxs-lookup"><span data-stu-id="2ba66-294">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="2ba66-295">Továbbra is rögzíthet Mixed Reality és képeket.</span><span class="sxs-lookup"><span data-stu-id="2ba66-295">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="2ba66-296">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-296">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="2ba66-297">A hangparancsok nem működnek</span><span class="sxs-lookup"><span data-stu-id="2ba66-297">Voice commands aren't working</span></span>

<span data-ttu-id="2ba66-298">Ha Cortana nem válaszol a hangparancsra, győződjön meg arról, hogy Cortana be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2ba66-298">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="2ba66-299">A módosítások Minden alkalmazás kattintson a Cortana  >    >  **Notebook**  >  **Gépház** elemre.</span><span class="sxs-lookup"><span data-stu-id="2ba66-299">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="2ba66-300">További információ a beszédről: [Use your voice with HoloLens](hololens-cortana.md).</span><span class="sxs-lookup"><span data-stu-id="2ba66-300">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="2ba66-301">A HoloLens (1. generációs) rendszerében a beépített beszédfelismerés nem konfigurálható.</span><span class="sxs-lookup"><span data-stu-id="2ba66-301">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="2ba66-302">Mindig be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2ba66-302">It is always turned on.</span></span> <span data-ttu-id="2ba66-303">A HoloLens 2-ben eldöntheti, hogy bekapcsolja-e a beszédfelismerést és a Cortana az eszköz beállítása során.</span><span class="sxs-lookup"><span data-stu-id="2ba66-303">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="2ba66-304">Ha a HoloLens 2. nem válaszol a hangjára, győződjön meg arról, hogy a Beszédfelismerés be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2ba66-304">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="2ba66-305">A **Start Gépház** Privacy Speech  >    >  **(Adatvédelmi**  >  **beszéd) menüben** kapcsolja be a **Beszédfelismerést.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-305">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="2ba66-306">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-306">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="2ba66-307">A kézi bevitel nem működik</span><span class="sxs-lookup"><span data-stu-id="2ba66-307">Hand input isn't working</span></span>

<span data-ttu-id="2ba66-308">Ahhoz, hogy HoloLens a kézmozdulatokat, kézmozdulatok keretében kell tartania azokat.</span><span class="sxs-lookup"><span data-stu-id="2ba66-308">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="2ba66-309">A Mixed Reality Kezdőlap visszajelzést küld, amely tudatja, mikor követik nyomon a kézzel kapcsolatos információkat.</span><span class="sxs-lookup"><span data-stu-id="2ba66-309">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="2ba66-310">A visszajelzések eltérőek a HoloLens:</span><span class="sxs-lookup"><span data-stu-id="2ba66-310">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="2ba66-311">A HoloLens (1. generációs) esetében a tekintet kurzora pontról gyűrűre változik</span><span class="sxs-lookup"><span data-stu-id="2ba66-311">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="2ba66-312">A 2. HoloLens kurzor akkor jelenik meg, ha a kéz egy lappal közel van, és egy kéz sugár jelenik meg, ha a belátsok közelebb vannak</span><span class="sxs-lookup"><span data-stu-id="2ba66-312">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="2ba66-313">Számos modern alkalmazás a Kezdőlaphoz hasonló bemeneti mintákat Mixed Reality követ.</span><span class="sxs-lookup"><span data-stu-id="2ba66-313">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="2ba66-314">További információ a kézi bevitelről [a HoloLens (1. generációs)](hololens1-basic-usage.md#use-hololens-with-your-hands) és [a 2. HoloLens használatával](hololens2-basic-usage.md#the-hand-tracking-frame)kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="2ba66-314">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="2ba66-315">Ha a kézkövetést jól viseli, vegye figyelembe, hogy egyes típusú kézkövetési funkció nem működik.</span><span class="sxs-lookup"><span data-stu-id="2ba66-315">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="2ba66-316">Gyakori példa a fekete védőkesztyűk, amelyek általában befogadják a világítást, és nem a mélységi kamera érzékeli őket.</span><span class="sxs-lookup"><span data-stu-id="2ba66-316">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="2ba66-317">Ha a munkája során védőkesztyűt is magában foglal, javasoljuk, hogy egy világosabb színt( például kék vagy szürke) próbáljon ki.</span><span class="sxs-lookup"><span data-stu-id="2ba66-317">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="2ba66-318">Egy másik példa a nagy méretű, zacskós kézkesztyű, amely általában elfedi a kéz formáját.</span><span class="sxs-lookup"><span data-stu-id="2ba66-318">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="2ba66-319">Javasoljuk, hogy a legjobb eredmény érdekében a lehető legjobban illeszkedő, formában illeszkedő védőkét használja.</span><span class="sxs-lookup"><span data-stu-id="2ba66-319">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="2ba66-320">Ha a vizor ujjlenyomattal vagy elmosott lenyomattal rendelkezik, használja a vizorhoz érkezett mikrofiberos tisztítási HoloLens a vizorok tisztítására.</span><span class="sxs-lookup"><span data-stu-id="2ba66-320">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="2ba66-321">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-321">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="2ba66-322">Nem lehet csatlakozni a Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="2ba66-322">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="2ba66-323">Ha nem tud csatlakozni a HoloLens egy Wi-Fi hálózathoz, az Wi-Fi próbálkozhat:</span><span class="sxs-lookup"><span data-stu-id="2ba66-323">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="2ba66-324">Ellenőrizze, hogy Wi-Fi be van-e kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2ba66-324">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="2ba66-325">Az ellenőrzéshez használja a Start kézmozdulatot, majd válassza Gépház  >  **Hálózati &amp; internet**  >  **Wi-Fi lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-325">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="2ba66-326">Ha Wi-Fi be van kapcsolva, próbálja meg kikapcsolni, majd újra bekapcsolni.</span><span class="sxs-lookup"><span data-stu-id="2ba66-326">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="2ba66-327">Lépjen közelebb az útválasztóhoz vagy a hozzáférési ponthoz.</span><span class="sxs-lookup"><span data-stu-id="2ba66-327">Move closer to the router or access point.</span></span>
- <span data-ttu-id="2ba66-328">Indítsa újra a Wi-Fi útválasztót, majd [indítsa újra a HoloLens.](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="2ba66-328">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="2ba66-329">Próbáljon meg újra csatlakozni.</span><span class="sxs-lookup"><span data-stu-id="2ba66-329">Try connecting again.</span></span>
- <span data-ttu-id="2ba66-330">Ha ezek egyike sem működik, ellenőrizze, hogy az útválasztó a legújabb belső vezérlőprogramot használja-e.</span><span class="sxs-lookup"><span data-stu-id="2ba66-330">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="2ba66-331">Ezt az információt a gyártó webhelyén találja.</span><span class="sxs-lookup"><span data-stu-id="2ba66-331">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="2ba66-332">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-332">Back to list</span></span>](#list)

## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="2ba66-333">Bluetooth eszközök nem párosodnak</span><span class="sxs-lookup"><span data-stu-id="2ba66-333">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="2ba66-334">Ha problémába merült fel [a Bluetooth párosítása,](hololens-connect-devices.md)próbálkozzon a következővel:</span><span class="sxs-lookup"><span data-stu-id="2ba66-334">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="2ba66-335">Az Eszközök **Gépház,** és győződjön meg arról, hogy Bluetooth  >  be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2ba66-335">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="2ba66-336">Ha igen, kapcsolja ki és be újra.</span><span class="sxs-lookup"><span data-stu-id="2ba66-336">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="2ba66-337">Győződjön meg arról, Bluetooth az eszköz teljesen fel van töltve, vagy friss akkumulátorokkal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="2ba66-337">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="2ba66-338">Ha továbbra sem tud csatlakozni, indítsa [újra a HoloLens.](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="2ba66-338">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="2ba66-339">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-339">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="2ba66-340">Az USB-C mikrofon nem működik</span><span class="sxs-lookup"><span data-stu-id="2ba66-340">USB-C Microphone isn't working</span></span>
<span data-ttu-id="2ba66-341">Vegye figyelembe, hogy egyes USB-C-mikrofonok helytelenül, mikrofonként és *beszélőként is* jelentik magukat.</span><span class="sxs-lookup"><span data-stu-id="2ba66-341">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="2ba66-342">Ez a mikrofonnal, és nem a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2ba66-342">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="2ba66-343">Ha az egyik mikrofont a HoloLens csatlakoztatja, előfordulhat, hogy a hang elveszett.</span><span class="sxs-lookup"><span data-stu-id="2ba66-343">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="2ba66-344">Szerencsére van egy egyszerű javítás.</span><span class="sxs-lookup"><span data-stu-id="2ba66-344">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="2ba66-345">A **Gépház** System Soundban explicit módon állítsa be a beépített beszélők  ->    ->   **(Analog Feature Audio Driver)** alapértelmezett eszközként való **beállítását.**</span><span class="sxs-lookup"><span data-stu-id="2ba66-345">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="2ba66-346">HoloLens akkor is meg kell jegyezni ezt a beállítást, ha a mikrofont eltávolítják, majd később újracsatlakoztatják.</span><span class="sxs-lookup"><span data-stu-id="2ba66-346">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C mikrofonok hibaelhárítása](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="2ba66-348">A Gépház felsorolt eszközök nem működnek</span><span class="sxs-lookup"><span data-stu-id="2ba66-348">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="2ba66-349">HoloLens (1. generációs) nem támogatja a Bluetooth hangprofilokat.</span><span class="sxs-lookup"><span data-stu-id="2ba66-349">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="2ba66-350">Bluetooth hangeszközök, például a beszélők és a headsetek elérhetőként jelennek meg HoloLens beállításokban, de nem támogatottak.</span><span class="sxs-lookup"><span data-stu-id="2ba66-350">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="2ba66-351">HoloLens 2. pont a Bluetooth A2DP hangprofilt támogatja a lejátszáshoz.</span><span class="sxs-lookup"><span data-stu-id="2ba66-351">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="2ba66-352">A Bluetooth nélküli kéz profil, amely lehetővé teszi a mikrofon rögzítését egy Bluetooth periféria nem támogatott a 2. HoloLens támogatja.</span><span class="sxs-lookup"><span data-stu-id="2ba66-352">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="2ba66-353">Ha problémája van egy Bluetooth eszköz használatával, győződjön meg arról, hogy az támogatott eszköz.</span><span class="sxs-lookup"><span data-stu-id="2ba66-353">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="2ba66-354">A támogatott eszközök a következők:</span><span class="sxs-lookup"><span data-stu-id="2ba66-354">Supported devices include the following:</span></span>

- <span data-ttu-id="2ba66-355">Angol nyelvű QWERTY Bluetooth billentyűzettel (ezeket bárhol használhatja, ahol a holografikus billentyűzetet használja).</span><span class="sxs-lookup"><span data-stu-id="2ba66-355">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="2ba66-356">Bluetooth mice.</span><span class="sxs-lookup"><span data-stu-id="2ba66-356">Bluetooth mice.</span></span>
- <span data-ttu-id="2ba66-357">A [HoloLens gombra.](hololens1-clicker.md)</span><span class="sxs-lookup"><span data-stu-id="2ba66-357">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="2ba66-358">Más HID és BLUETOOTH ESZKÖZÖKET is párosíthat a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2ba66-358">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="2ba66-359">Előfordulhat azonban, hogy telepítenie kell a megfelelő társalkalmazásokat a Microsoft Store az eszközök ténylegesen való használatához.</span><span class="sxs-lookup"><span data-stu-id="2ba66-359">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="2ba66-360">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="2ba66-360">Back to list</span></span>](#list)
