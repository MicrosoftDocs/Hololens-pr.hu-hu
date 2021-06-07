---
title: Oldalbeállítások láthatósága
description: Maradjon naprakész a PageVisibilityList által támogatott URI-k listájával és a HoloLens vegyes valóságú eszközökön elérhető útmutatóval.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, hozzárendelt hozzáférés, kioszk, beállítások oldal
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5779ffa1de1700b4fcd17fc17b8ae3a82a45c22
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379573"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="77654-104">Oldalbeállítások láthatósága</span><span class="sxs-lookup"><span data-stu-id="77654-104">Page Settings Visibility</span></span>

<span data-ttu-id="77654-105">A HoloLens-eszközök egyik felügyelhető szolgáltatása a [Settings/PageVisibilityList szabályzat](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) használatával korlátozza a Beállítások alkalmazásban látható oldalakat.</span><span class="sxs-lookup"><span data-stu-id="77654-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="77654-106">A PageVisibilityList egy olyan szabályzat, amely lehetővé teszi a rendszergazdák számára, hogy megakadályozzák a Rendszerbeállítások alkalmazás adott lapjainak láthatóságát vagy akadálymentességét, vagy hogy ezt a megadott oldalak kivételével az összes oldalon meg tudjanak jelenni.</span><span class="sxs-lookup"><span data-stu-id="77654-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="77654-107">Ez a funkció csak a [Windows Holographic 20H2-es](hololens-release-notes.md#windows-holographic-version-20h2) vagy újabb verziójában használható a HoloLens 2-es eszközökön.</span><span class="sxs-lookup"><span data-stu-id="77654-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="77654-108">Győződjön meg arról, hogy a használni kívánt eszközök frissítve vannak.</span><span class="sxs-lookup"><span data-stu-id="77654-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="77654-109">Az alábbi példa egy olyan szabályzatot mutat be, amely csak az About és a Bluetooth-oldalakhoz biztosít hozzáférést, amelyek URI-ja "ms-settings:network-wifi" és "ms-settings:bluetooth" lehet:</span><span class="sxs-lookup"><span data-stu-id="77654-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="77654-110">Ennek beállítása kiépítési csomaggal:</span><span class="sxs-lookup"><span data-stu-id="77654-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="77654-111">Amikor a Windows Configuration Designerben létrehozza a csomagot, lépjen a Házirendek és > **beállítások > Lap láthatóságaLista elemre.**</span><span class="sxs-lookup"><span data-stu-id="77654-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="77654-112">Adja meg a sztringet: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="77654-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="77654-113">Exportálja a kiépítési csomagot.</span><span class="sxs-lookup"><span data-stu-id="77654-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="77654-114">Alkalmazza a csomagot az eszközre.</span><span class="sxs-lookup"><span data-stu-id="77654-114">Apply the package to your device.</span></span>
<span data-ttu-id="77654-115">A kiépítési csomagok létrehozására és alkalmazására vonatkozó részletes információkért látogasson el erre [az oldalra.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="77654-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="77654-116">Ezt az Intune-on keresztül, az OMA-URI használatával lehet tenni:</span><span class="sxs-lookup"><span data-stu-id="77654-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="77654-117">Hozzon létre **egy egyéni szabályzatot.**</span><span class="sxs-lookup"><span data-stu-id="77654-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="77654-118">Az OMA-URI beállításakor használja a következő sztringet: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="77654-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="77654-119">Az adat kiválasztásakor válassza a Sztring **lehetőséget**</span><span class="sxs-lookup"><span data-stu-id="77654-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="77654-120">Az érték beírásakor használja a következőt: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="77654-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="77654-121">Ügyeljen arra, hogy az egyéni eszközkonfigurációt olyan csoporthoz rendelje, amelybe az eszköznek szánták.</span><span class="sxs-lookup"><span data-stu-id="77654-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="77654-122">További információ az Intune-csoportokról és az eszközkonfigurációkról: [HoloLens MDM-konfiguráció.](hololens-mdm-configure.md)</span><span class="sxs-lookup"><span data-stu-id="77654-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="77654-123">Az eszköznek a választott módszertől függetlenül meg kell kapnia a módosításokat, és a felhasználók számára a következő Beállítások alkalmazás fog jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="77654-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Képernyőkép a Beállítások alkalmazásban módosított aktív órákról](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="77654-125">Ha a Beállítások alkalmazásoldalait úgy konfigurálja, hogy saját oldalakat mutassanak vagy rejtsen el, nézze meg a HoloLensben elérhető Beállítás URI-ket.</span><span class="sxs-lookup"><span data-stu-id="77654-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="77654-126">Beállítási URI-k</span><span class="sxs-lookup"><span data-stu-id="77654-126">Settings URIs</span></span>

<span data-ttu-id="77654-127">A HoloLens- és Windows 10-eszközök különböző oldalakat tartalmaznak a Beállítások alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="77654-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="77654-128">Ezen az oldalon csak a HoloLensben meglévő beállításokat találja meg.</span><span class="sxs-lookup"><span data-stu-id="77654-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="77654-129">Fiókok</span><span class="sxs-lookup"><span data-stu-id="77654-129">Accounts</span></span>
| <span data-ttu-id="77654-130">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="77654-130">Settings page</span></span>           | <span data-ttu-id="77654-131">URI</span><span class="sxs-lookup"><span data-stu-id="77654-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="77654-132">Hozzáférés munkahelyi vagy iskolai rendszerhez</span><span class="sxs-lookup"><span data-stu-id="77654-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="77654-133">Íriszregisztrálás</span><span class="sxs-lookup"><span data-stu-id="77654-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="77654-134">Bejelentkezési lehetőségek</span><span class="sxs-lookup"><span data-stu-id="77654-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="77654-135">Alkalmazások</span><span class="sxs-lookup"><span data-stu-id="77654-135">Apps</span></span>
| <span data-ttu-id="77654-136">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="77654-136">Settings page</span></span> | <span data-ttu-id="77654-137">URI</span><span class="sxs-lookup"><span data-stu-id="77654-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="77654-138">Alkalmazások &<sup>funkciók 2</sup></span><span class="sxs-lookup"><span data-stu-id="77654-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="77654-139">Alkalmazások & funkciókkal > <sup>2.</sup> speciális beállításokkal</span><span class="sxs-lookup"><span data-stu-id="77654-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="77654-140">Az offline & <sup>2</sup> > alkalmazások</span><span class="sxs-lookup"><span data-stu-id="77654-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="77654-141">Az offline térképek & elérhető > alkalmazások > Maps <sup>2 letöltése</sup></span><span class="sxs-lookup"><span data-stu-id="77654-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="77654-142">Eszközök</span><span class="sxs-lookup"><span data-stu-id="77654-142">Devices</span></span>
| <span data-ttu-id="77654-143">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="77654-143">Settings page</span></span> | <span data-ttu-id="77654-144">URI</span><span class="sxs-lookup"><span data-stu-id="77654-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="77654-145">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="77654-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="77654-146"><sup>2. egér</sup></span><span class="sxs-lookup"><span data-stu-id="77654-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="77654-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="77654-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="77654-148">Adatvédelem</span><span class="sxs-lookup"><span data-stu-id="77654-148">Privacy</span></span>
| <span data-ttu-id="77654-149">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="77654-149">Settings page</span></span>            | <span data-ttu-id="77654-150">URI</span><span class="sxs-lookup"><span data-stu-id="77654-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="77654-151">Fiókadatok</span><span class="sxs-lookup"><span data-stu-id="77654-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="77654-152">Alkalmazásdiagnosztika</span><span class="sxs-lookup"><span data-stu-id="77654-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="77654-153">Háttérben futó alkalmazások</span><span class="sxs-lookup"><span data-stu-id="77654-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="77654-154">Naptár</span><span class="sxs-lookup"><span data-stu-id="77654-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="77654-155">Híváselőzmények</span><span class="sxs-lookup"><span data-stu-id="77654-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="77654-156">Kamera</span><span class="sxs-lookup"><span data-stu-id="77654-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="77654-157">Kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="77654-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="77654-158">Diagnosztikai és & visszajelzés</span><span class="sxs-lookup"><span data-stu-id="77654-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="77654-159">Dokumentumok</span><span class="sxs-lookup"><span data-stu-id="77654-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="77654-160">E-mail</span><span class="sxs-lookup"><span data-stu-id="77654-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="77654-161">Fájlrendszer</span><span class="sxs-lookup"><span data-stu-id="77654-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="77654-162"><sup>2. általános</sup></span><span class="sxs-lookup"><span data-stu-id="77654-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="77654-163">Ink & személyre szabás <sup>begépelése 2</sup></span><span class="sxs-lookup"><span data-stu-id="77654-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="77654-164">Hely</span><span class="sxs-lookup"><span data-stu-id="77654-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="77654-165">Üzenetkezelés</span><span class="sxs-lookup"><span data-stu-id="77654-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="77654-166">Mikrofon</span><span class="sxs-lookup"><span data-stu-id="77654-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="77654-167"><sup>2. mozgás</sup></span><span class="sxs-lookup"><span data-stu-id="77654-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="77654-168">Értesítések</span><span class="sxs-lookup"><span data-stu-id="77654-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="77654-169">Egyéb eszközök</span><span class="sxs-lookup"><span data-stu-id="77654-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="77654-170">Képek</span><span class="sxs-lookup"><span data-stu-id="77654-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="77654-171">Rádiók</span><span class="sxs-lookup"><span data-stu-id="77654-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="77654-172">Képernyőkép a <sup>szegélyek 2-ről</sup></span><span class="sxs-lookup"><span data-stu-id="77654-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="77654-173">Képernyőképek és alkalmazások <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="77654-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="77654-174">Speech</span><span class="sxs-lookup"><span data-stu-id="77654-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="77654-175">Feladatok</span><span class="sxs-lookup"><span data-stu-id="77654-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="77654-176">Felhasználói mozgások</span><span class="sxs-lookup"><span data-stu-id="77654-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="77654-177">Videók</span><span class="sxs-lookup"><span data-stu-id="77654-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="77654-178">Hangaktiválás</span><span class="sxs-lookup"><span data-stu-id="77654-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="77654-179">Hálózat és internet</span><span class="sxs-lookup"><span data-stu-id="77654-179">Network & Internet</span></span>
| <span data-ttu-id="77654-180">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="77654-180">Settings page</span></span> | <span data-ttu-id="77654-181">URI</span><span class="sxs-lookup"><span data-stu-id="77654-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="77654-182"><sup>2.</sup> repülőgép üzemmód</span><span class="sxs-lookup"><span data-stu-id="77654-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="77654-183">Proxy</span><span class="sxs-lookup"><span data-stu-id="77654-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="77654-184">VPN</span><span class="sxs-lookup"><span data-stu-id="77654-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="77654-185">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="77654-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="77654-186">Rendszer</span><span class="sxs-lookup"><span data-stu-id="77654-186">System</span></span>
| <span data-ttu-id="77654-187">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="77654-187">Settings page</span></span>      | <span data-ttu-id="77654-188">URI</span><span class="sxs-lookup"><span data-stu-id="77654-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="77654-189"><sup>2. akkumulátor</sup></span><span class="sxs-lookup"><span data-stu-id="77654-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="77654-190"><sup>2. akkumulátor</sup></span><span class="sxs-lookup"><span data-stu-id="77654-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="77654-191">Színek</span><span class="sxs-lookup"><span data-stu-id="77654-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="77654-192">Hologramok <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="77654-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="77654-193"><sup>2. hiba</sup></span><span class="sxs-lookup"><span data-stu-id="77654-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="77654-194">Értesítési & műveletek</span><span class="sxs-lookup"><span data-stu-id="77654-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="77654-195">Megosztott élmények</span><span class="sxs-lookup"><span data-stu-id="77654-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="77654-196"><sup>2. hang</sup></span><span class="sxs-lookup"><span data-stu-id="77654-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="77654-197">Hang > alkalmazáskötet és eszköz preferencia <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="77654-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="77654-198">Hang > Hangeszközök kezelése <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="77654-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="77654-199">Tárolás</span><span class="sxs-lookup"><span data-stu-id="77654-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="77654-200">Storage > Configue Tárterületsegéd <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="77654-200">Storage > Configue Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="77654-201">Time & Language</span><span class="sxs-lookup"><span data-stu-id="77654-201">Time & Language</span></span>
| <span data-ttu-id="77654-202">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="77654-202">Settings page</span></span> | <span data-ttu-id="77654-203">URI</span><span class="sxs-lookup"><span data-stu-id="77654-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="77654-204">Dátum & <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="77654-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="77654-205"><sup>2. billentyűzet</sup></span><span class="sxs-lookup"><span data-stu-id="77654-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="77654-206"><sup>2. nyelv</sup></span><span class="sxs-lookup"><span data-stu-id="77654-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="77654-207"><sup>2. nyelv</sup></span><span class="sxs-lookup"><span data-stu-id="77654-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="77654-208">Nyelv</span><span class="sxs-lookup"><span data-stu-id="77654-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="77654-209">Region</span><span class="sxs-lookup"><span data-stu-id="77654-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="77654-210">Biztonsági & frissítése</span><span class="sxs-lookup"><span data-stu-id="77654-210">Update & Security</span></span>
| <span data-ttu-id="77654-211">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="77654-211">Settings page</span></span>                         | <span data-ttu-id="77654-212">URI</span><span class="sxs-lookup"><span data-stu-id="77654-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="77654-213">Speciális beállítások</span><span class="sxs-lookup"><span data-stu-id="77654-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="77654-214">Visszaállítás & <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="77654-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="77654-215">Windows Insider Program</span><span class="sxs-lookup"><span data-stu-id="77654-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="77654-216">Windows Update</span><span class="sxs-lookup"><span data-stu-id="77654-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="77654-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="77654-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="77654-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="77654-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="77654-219">Windows Update – Frissítések keresése</span><span class="sxs-lookup"><span data-stu-id="77654-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


>  <span data-ttu-id="77654-220"><sup>1</sup> A Windows Holographic előtti, 21H1-es verziónál korábbi verziók esetén  a következő két URI valójában nem a Speciális beállítások vagy Beállítások **oldalra** lép; csak a főoldalt blokkolják vagy Windows Update meg.</span><span class="sxs-lookup"><span data-stu-id="77654-220"><sup>1</sup> For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
> - <span data-ttu-id="77654-221">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="77654-221">ms-settings:windowsupdate-options</span></span>
> - <span data-ttu-id="77654-222">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="77654-222">ms-settings:windowsupdate-restartoptions</span></span>
 
> <span data-ttu-id="77654-223"><sup>2</sup> – Windows Holographic 21H1 vagy újabb rendszeren érhető el.</span><span class="sxs-lookup"><span data-stu-id="77654-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="77654-224">A beállítások URI Windows 10 teljes listáját az indítási beállítások [dokumentációjában](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) találhatja meg.</span><span class="sxs-lookup"><span data-stu-id="77654-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
