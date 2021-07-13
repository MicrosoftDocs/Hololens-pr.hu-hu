---
title: Lap Gépház láthatósága
description: Maradjon naprakész a PageVisibilityList által támogatott URI-k listájával és a vegyes valóságú eszközökön HoloLens útmutatóval.
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
ms.openlocfilehash: 5ac3ff27085fd2f7c5bc1de0e461079a673bbb23
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637166"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="646bf-104">Lap Gépház láthatósága</span><span class="sxs-lookup"><span data-stu-id="646bf-104">Page Settings Visibility</span></span>

<span data-ttu-id="646bf-105">A HoloLens egyik felügyelhető szolgáltatása a [Gépház/PageVisibilityList szabályzat](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) használatával korlátozza a Gépház belüli oldalakat.</span><span class="sxs-lookup"><span data-stu-id="646bf-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="646bf-106">A PageVisibilityList egy olyan szabályzat, amely lehetővé teszi a rendszergazdák számára, hogy megakadályozzák a System Gépház alkalmazás adott lapjainak láthatóságát vagy akadálymentességét, vagy a megadottak kivételével minden oldal esetén ezt teszik.</span><span class="sxs-lookup"><span data-stu-id="646bf-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="646bf-107">Ez a funkció csak a [Holographic Windows 20H2-es](hololens-release-notes.md#windows-holographic-version-20h2) vagy újabb verziójában használható 2 HoloLens eszközök esetében.</span><span class="sxs-lookup"><span data-stu-id="646bf-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="646bf-108">Győződjön meg arról, hogy a használni kívánt eszközök frissítve vannak.</span><span class="sxs-lookup"><span data-stu-id="646bf-108">Please ensure devices you intend to use this for are updated.</span></span>


## <a name="examples"></a><span data-ttu-id="646bf-109">Példák</span><span class="sxs-lookup"><span data-stu-id="646bf-109">Examples</span></span>
<span data-ttu-id="646bf-110">A lapokat a közzétett URI-k rövid verziója azonosítja, amely az URI és az "ms-settings:" előtag.</span><span class="sxs-lookup"><span data-stu-id="646bf-110">Pages are identified by a shortened version of the published URIs, which is the URI minus the "ms-settings:" prefix.</span></span>

<span data-ttu-id="646bf-111">Az alábbi példa egy olyan szabályzatot mutat be, amely csak a "network-wifi" és "bluetooth" URI-vel rendelkezik, amely csak az about és a Bluetooth-oldalakhoz engedélyezi a hozzáférést:</span><span class="sxs-lookup"><span data-stu-id="646bf-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "network-wifi" and "bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="646bf-112">Az alábbi példa egy olyan szabályzatot mutat be, amely elrejti az Operációs rendszer alaphelyzetbe állítása oldalt:</span><span class="sxs-lookup"><span data-stu-id="646bf-112">The following example illustrates a policy that would hide the OS Reset page:</span></span>
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a><span data-ttu-id="646bf-113">A szabályzat telepítése az Intune-nal</span><span class="sxs-lookup"><span data-stu-id="646bf-113">Deploying this policy via Intune</span></span>

<span data-ttu-id="646bf-114">Az Intune a következő konfigurációs értékeket fogja szolgáltatni:</span><span class="sxs-lookup"><span data-stu-id="646bf-114">These are the configuration values that will be supplied to Intune:</span></span>

- <span data-ttu-id="646bf-115">**Név:** A profil rendszergazda által előnyben részesített megjelenítendő neve.</span><span class="sxs-lookup"><span data-stu-id="646bf-115">**Name:** An admin preferred display name for the profile.</span></span>
- <span data-ttu-id="646bf-116">**OMA-URI:** A beállítási oldal teljes URI-ját, beleértve a [hatókörét is.](/windows/client-management/mdm/policy-configuration-service-provider)</span><span class="sxs-lookup"><span data-stu-id="646bf-116">**OMA-URI:** The fully qualified URI of the setting page including its [scope](/windows/client-management/mdm/policy-configuration-service-provider).</span></span> <span data-ttu-id="646bf-117">Az ezen az oldalon található példák a hatókört `./Device` használják.</span><span class="sxs-lookup"><span data-stu-id="646bf-117">This examples on this page are using the `./Device` scope.</span></span>
- <span data-ttu-id="646bf-118">**Érték:** Sztringérték, amely azt jelzi, hogy csak a megadott oldalakat rejtse el vagy *mutassa.*</span><span class="sxs-lookup"><span data-stu-id="646bf-118">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="646bf-119">Lehetséges értékek: `hide:<pagename>` és `showonly:<pagename>` .</span><span class="sxs-lookup"><span data-stu-id="646bf-119">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> 
 
<span data-ttu-id="646bf-120">Több oldal is meg lehet adni pontosvesszővel elválasztva, és a gyakori oldalak listája alább található.</span><span class="sxs-lookup"><span data-stu-id="646bf-120">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>

1. <span data-ttu-id="646bf-121">Hozzon létre **egy egyéni szabályzatot.**</span><span class="sxs-lookup"><span data-stu-id="646bf-121">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="646bf-122">Az **OMA-URI beállításakor adja** meg a teljes hatókörű URI-t.</span><span class="sxs-lookup"><span data-stu-id="646bf-122">When setting the **OMA-URI** enter the fully scoped URI.</span></span> <span data-ttu-id="646bf-123">Például: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="646bf-123">For example: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="646bf-124">Az adat kiválasztásakor válassza a Sztring **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="646bf-124">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="646bf-125">Az Érték **megadásakor** használja a fenti útmutatást.</span><span class="sxs-lookup"><span data-stu-id="646bf-125">When specifying **Value** use the guidance above.</span></span> <span data-ttu-id="646bf-126">Például: **`showonly:network-wifi;network-proxy;bluetooth`** vagy **`hide:reset`**</span><span class="sxs-lookup"><span data-stu-id="646bf-126">For example: **`showonly:network-wifi;network-proxy;bluetooth`** or **`hide:reset`**</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="646bf-127">Ügyeljen arra, hogy az egyéni eszközkonfigurációt olyan csoporthoz rendelje, amelybe az eszköznek szánták.</span><span class="sxs-lookup"><span data-stu-id="646bf-127">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span> <span data-ttu-id="646bf-128">Ha ezt a lépést nem végzi el, a rendszer lekedi a szabályzatot, de nem alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="646bf-128">If this step is not performed, the policy will be pushed but won't be applied.</span></span>

<span data-ttu-id="646bf-129">Az [Intune HoloLens és](hololens-mdm-configure.md) eszközkonfigurációkról további információt az MDM-konfigurációk és -konfigurációk konfigurálása oldalon található.</span><span class="sxs-lookup"><span data-stu-id="646bf-129">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>


## <a name="deploying-this-policy-via-a-provisioning-package"></a><span data-ttu-id="646bf-130">A szabályzat üzembe helyezése kiépítési csomagon keresztül</span><span class="sxs-lookup"><span data-stu-id="646bf-130">Deploying this policy via a Provisioning Package</span></span>

<span data-ttu-id="646bf-131">A Configuration Designerben a következő konfigurációs értékeket Windows meg:</span><span class="sxs-lookup"><span data-stu-id="646bf-131">These are the configuration values that will be specified in Windows Configuration Designer:</span></span>

<span data-ttu-id="646bf-132">**Érték:** Sztringérték, amely azt jelzi, hogy csak a megadott oldalakat rejtse el vagy *mutassa.*</span><span class="sxs-lookup"><span data-stu-id="646bf-132">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="646bf-133">Lehetséges értékek: `hide:<pagename>` és `showonly:<pagename>` .</span><span class="sxs-lookup"><span data-stu-id="646bf-133">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> <span data-ttu-id="646bf-134">Több oldal is meg lehet adni pontosvesszővel elválasztva, és a gyakori oldalak listája alább található.</span><span class="sxs-lookup"><span data-stu-id="646bf-134">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>


1. <span data-ttu-id="646bf-135">Amikor a csomagot a Configuration Designerben Windows, lépjen a **Szabályzatok és > Gépház > PageVisibilityList listára.**</span><span class="sxs-lookup"><span data-stu-id="646bf-135">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="646bf-136">Adja meg a sztringet: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="646bf-136">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="646bf-137">Exportálja a kiépítési csomagot.</span><span class="sxs-lookup"><span data-stu-id="646bf-137">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="646bf-138">Alkalmazza a csomagot az eszközre.</span><span class="sxs-lookup"><span data-stu-id="646bf-138">Apply the package to your device.</span></span>
<span data-ttu-id="646bf-139">A kiépítési csomagok létrehozásáról és alkalmazásról további részleteket a [HoloLens oldalon talál.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="646bf-139">For full details on how to create and apply a provisioning package visit [the HoloLens provisioning page](hololens-provisioning.md).</span></span>


<span data-ttu-id="646bf-140">A kiválasztott módszertől függetlenül az eszköznek most már meg kell kapnia a módosításokat, és a felhasználók számára az alábbi Gépház alkalmazás.</span><span class="sxs-lookup"><span data-stu-id="646bf-140">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Képernyőkép a módosított aktív órákról az Gépház alkalmazásban](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="646bf-142">Ha úgy Gépház, hogy az alkalmazásoldalak saját oldalakat mutassanak vagy rejtsen el, nézze meg a Gépház elérhető URI-HoloLens.</span><span class="sxs-lookup"><span data-stu-id="646bf-142">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="646bf-143">Gépház Uri</span><span class="sxs-lookup"><span data-stu-id="646bf-143">Settings URIs</span></span>

<span data-ttu-id="646bf-144">HoloLens eszközök és Windows 10 eszközök különböző oldalakat tartalmaznak a Gépház alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="646bf-144">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="646bf-145">Ezen a lapon csak a meglévő beállításokat fogja HoloLens.</span><span class="sxs-lookup"><span data-stu-id="646bf-145">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="646bf-146">Fiókok</span><span class="sxs-lookup"><span data-stu-id="646bf-146">Accounts</span></span>
| <span data-ttu-id="646bf-147">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="646bf-147">Settings page</span></span>           | <span data-ttu-id="646bf-148">URI</span><span class="sxs-lookup"><span data-stu-id="646bf-148">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="646bf-149">Hozzáférés munkahelyi vagy iskolai rendszerhez</span><span class="sxs-lookup"><span data-stu-id="646bf-149">Access work or school</span></span> | `workplace`                         |
| <span data-ttu-id="646bf-150">Íriszregisztrálás</span><span class="sxs-lookup"><span data-stu-id="646bf-150">Iris Enrollment</span></span>       | `signinoptions-launchirisenrollment` |
| <span data-ttu-id="646bf-151">Bejelentkezési beállítások</span><span class="sxs-lookup"><span data-stu-id="646bf-151">Sign In Options</span></span>         | ` signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="646bf-152">Alkalmazások</span><span class="sxs-lookup"><span data-stu-id="646bf-152">Apps</span></span>
| <span data-ttu-id="646bf-153">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="646bf-153">Settings page</span></span> | <span data-ttu-id="646bf-154">URI</span><span class="sxs-lookup"><span data-stu-id="646bf-154">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="646bf-155">Alkalmazások & <sup>funkciók 2</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-155">Apps & features <sup>2</sup></span></span>     | `appsfeatures` <br> |
| <span data-ttu-id="646bf-156">Alkalmazások & szolgáltatások > <sup>2.</sup> speciális beállításai</span><span class="sxs-lookup"><span data-stu-id="646bf-156">Apps & features > Advanced Options <sup>2</sup></span></span>     | `appsfeatures-app` <br> |
| <span data-ttu-id="646bf-157">Offline & <sup>2> alkalmazások Térképek funkciók</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-157">Apps & features > Offline Maps <sup>2</sup></span></span>     | `maps-maps` <br> |
| <span data-ttu-id="646bf-158">Az offline & és > alkalmazások Térképek > Maps <sup>2 letöltése</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-158">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="646bf-159">Eszközök</span><span class="sxs-lookup"><span data-stu-id="646bf-159">Devices</span></span>
| <span data-ttu-id="646bf-160">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="646bf-160">Settings page</span></span> | <span data-ttu-id="646bf-161">URI</span><span class="sxs-lookup"><span data-stu-id="646bf-161">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="646bf-162">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="646bf-162">Bluetooth</span></span>     | `bluetooth` <br> `connecteddevices` |
| <span data-ttu-id="646bf-163"><sup>2. egér</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-163">Mouse <sup>2</sup></span></span>      | `mouse` <br>  |
| <span data-ttu-id="646bf-164">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-164">USB <sup>2</sup></span></span>      | `usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="646bf-165">Adatvédelem</span><span class="sxs-lookup"><span data-stu-id="646bf-165">Privacy</span></span>
| <span data-ttu-id="646bf-166">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="646bf-166">Settings page</span></span>            | <span data-ttu-id="646bf-167">URI</span><span class="sxs-lookup"><span data-stu-id="646bf-167">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="646bf-168">Fiókadatok</span><span class="sxs-lookup"><span data-stu-id="646bf-168">Account Info</span></span>             | `privacy-accountinfo`              |
| <span data-ttu-id="646bf-169">Alkalmazásdiagnosztika</span><span class="sxs-lookup"><span data-stu-id="646bf-169">App Diagnostics</span></span>        | `privacy-appdiagnostics`              |
| <span data-ttu-id="646bf-170">Háttérben futó alkalmazások</span><span class="sxs-lookup"><span data-stu-id="646bf-170">Background Apps</span></span>        | `privacy-backgroundapps`              |
| <span data-ttu-id="646bf-171">Naptár</span><span class="sxs-lookup"><span data-stu-id="646bf-171">Calendar</span></span>                 | `privacy-calendar`                    |
| <span data-ttu-id="646bf-172">Híváselőzmények</span><span class="sxs-lookup"><span data-stu-id="646bf-172">Call History</span></span>             | `privacy-callhistory`                 |
| <span data-ttu-id="646bf-173">Kamera</span><span class="sxs-lookup"><span data-stu-id="646bf-173">Camera</span></span>                   | `privacy-webcam`                      |
| <span data-ttu-id="646bf-174">Kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="646bf-174">Contacts</span></span>                 | `privacy-contacts`                    |
| <span data-ttu-id="646bf-175">Diagnosztikai & visszajelzés</span><span class="sxs-lookup"><span data-stu-id="646bf-175">Diagnostics & Feedback</span></span> | `privacy-feedback`                    |
| <span data-ttu-id="646bf-176">Dokumentumok</span><span class="sxs-lookup"><span data-stu-id="646bf-176">Documents</span></span>                | `privacy-documents`                   |
| <span data-ttu-id="646bf-177">E-mail</span><span class="sxs-lookup"><span data-stu-id="646bf-177">Email</span></span>                    | `privacy-email`                       |
| <span data-ttu-id="646bf-178">Fájlrendszer</span><span class="sxs-lookup"><span data-stu-id="646bf-178">File system</span></span>              | `privacy-broadfilesystemaccess`       |
| <span data-ttu-id="646bf-179"><sup>Általános 2</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-179">General <sup>2</sup></span></span>             | `privacy-general`       |
| <span data-ttu-id="646bf-180">Ink & személyre szabás <sup>2 gépelése</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-180">Ink & typing personalization <sup>2</sup></span></span>             | `privacy-speechtyping`       |
| <span data-ttu-id="646bf-181">Hely</span><span class="sxs-lookup"><span data-stu-id="646bf-181">Location</span></span>                 | `privacy-location`                    |
| <span data-ttu-id="646bf-182">Üzenetkezelés</span><span class="sxs-lookup"><span data-stu-id="646bf-182">Messaging</span></span>                | `privacy-messaging`                   |
| <span data-ttu-id="646bf-183">Mikrofon</span><span class="sxs-lookup"><span data-stu-id="646bf-183">Microphone</span></span>               | `privacy-microphone`                  |
| <span data-ttu-id="646bf-184"><sup>2. mozgás</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-184">Motion <sup>2</sup></span></span>               | `privacy-motion`                  |
| <span data-ttu-id="646bf-185">Értesítések</span><span class="sxs-lookup"><span data-stu-id="646bf-185">Notifications</span></span>            | `privacy-notifications`               |
| <span data-ttu-id="646bf-186">Egyéb eszközök</span><span class="sxs-lookup"><span data-stu-id="646bf-186">Other devices</span></span>            | `privacy-customdevices`               |
| <span data-ttu-id="646bf-187">Képek</span><span class="sxs-lookup"><span data-stu-id="646bf-187">Pictures</span></span>                 | `privacy-pictures`                    |
| <span data-ttu-id="646bf-188">Rádiók</span><span class="sxs-lookup"><span data-stu-id="646bf-188">Radios</span></span>                   | `privacy-radios`                      |
| <span data-ttu-id="646bf-189">Képernyőkép a <sup>2. szegélyről</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-189">Screenshot borders <sup>2</sup></span></span>             | `privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="646bf-190">Képernyőképek és alkalmazások <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-190">Screenshots and apps <sup>2</sup></span></span>             | `privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="646bf-191">Speech</span><span class="sxs-lookup"><span data-stu-id="646bf-191">Speech</span></span>                   | `privacy-speech`                      |
| <span data-ttu-id="646bf-192">Feladatok</span><span class="sxs-lookup"><span data-stu-id="646bf-192">Tasks</span></span>                    | `privacy-tasks`                       |
| <span data-ttu-id="646bf-193">Felhasználói mozgások</span><span class="sxs-lookup"><span data-stu-id="646bf-193">User movements</span></span>           | `privacy-backgroundspatialperception` |
| <span data-ttu-id="646bf-194">Videók</span><span class="sxs-lookup"><span data-stu-id="646bf-194">Videos</span></span>                   | `privacy-videos`                      |
| <span data-ttu-id="646bf-195">Hangaktiválás</span><span class="sxs-lookup"><span data-stu-id="646bf-195">Voice Activation</span></span>       | `privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="646bf-196">Hálózat és internet</span><span class="sxs-lookup"><span data-stu-id="646bf-196">Network & Internet</span></span>
| <span data-ttu-id="646bf-197">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="646bf-197">Settings page</span></span> | <span data-ttu-id="646bf-198">URI</span><span class="sxs-lookup"><span data-stu-id="646bf-198">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="646bf-199"><sup>2.</sup> repülőgép üzemmód</span><span class="sxs-lookup"><span data-stu-id="646bf-199">Airplane Mode <sup>2</sup></span></span> | `network-airplanemode`        |
| <span data-ttu-id="646bf-200">Proxy</span><span class="sxs-lookup"><span data-stu-id="646bf-200">Proxy</span></span> | `network-proxy`        |
| <span data-ttu-id="646bf-201">VPN</span><span class="sxs-lookup"><span data-stu-id="646bf-201">VPN</span></span>   | `network-vpn`          |
| <span data-ttu-id="646bf-202">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="646bf-202">Wi-Fi</span></span>  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="646bf-203">Rendszer</span><span class="sxs-lookup"><span data-stu-id="646bf-203">System</span></span>
| <span data-ttu-id="646bf-204">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="646bf-204">Settings page</span></span>      | <span data-ttu-id="646bf-205">URI</span><span class="sxs-lookup"><span data-stu-id="646bf-205">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="646bf-206"><sup>2. akkumulátor</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-206">Battery <sup>2</sup></span></span>           | `batterysaver`<br>|
| <span data-ttu-id="646bf-207"><sup>2. akkumulátor</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-207">Battery <sup>2</sup></span></span>           | `batterysaver-settings`<br>|
| <span data-ttu-id="646bf-208">Színek</span><span class="sxs-lookup"><span data-stu-id="646bf-208">Colors</span></span>             | `colors`<br>`personalization-colors` |
| <span data-ttu-id="646bf-209">Hologramok <sup>2.</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-209">Holograms <sup>2</sup></span></span>  |  `holograms`  |
| <span data-ttu-id="646bf-210"><sup>2. hiba</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-210">Calibration <sup>2</sup></span></span> |  `calibration` |
| <span data-ttu-id="646bf-211">Értesítési & műveletek</span><span class="sxs-lookup"><span data-stu-id="646bf-211">Notifications & actions</span></span>  | `notifications`          |
| <span data-ttu-id="646bf-212">Megosztott élmények</span><span class="sxs-lookup"><span data-stu-id="646bf-212">Shared Experiences</span></span> | `crossdevice` 
| <span data-ttu-id="646bf-213"><sup>2. hang</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-213">Sound <sup>2</sup></span></span>           | `sound`<br>|
| <span data-ttu-id="646bf-214">Hang > alkalmazáskötet és eszköz preferencia <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-214">Sound > App volume and device preference <sup>2</sup></span></span>           | `apps-volume`<br>|
| <span data-ttu-id="646bf-215">Hang > Hangeszközök kezelése <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-215">Sound > Manage sound devices <sup>2</sup></span></span>           | `sound-devices`<br>|
| <span data-ttu-id="646bf-216">Tárolás</span><span class="sxs-lookup"><span data-stu-id="646bf-216">Storage</span></span>            | `storagesense`           |
| <span data-ttu-id="646bf-217">Storage > Sense <sup>2</sup> Storage konfigurálása</span><span class="sxs-lookup"><span data-stu-id="646bf-217">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="646bf-218">Time & Language</span><span class="sxs-lookup"><span data-stu-id="646bf-218">Time & Language</span></span>
| <span data-ttu-id="646bf-219">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="646bf-219">Settings page</span></span> | <span data-ttu-id="646bf-220">URI</span><span class="sxs-lookup"><span data-stu-id="646bf-220">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="646bf-221">Dátum & <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-221">Date & time <sup>2</sup></span></span> | `dateandtime`                  |
| <span data-ttu-id="646bf-222"><sup>2.</sup> billentyűzet</span><span class="sxs-lookup"><span data-stu-id="646bf-222">Keyboard <sup>2</sup></span></span> | `keyboard`                  |
| <span data-ttu-id="646bf-223"><sup>2. nyelv</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-223">Language <sup>2</sup></span></span> | `language`                  |
| <span data-ttu-id="646bf-224"><sup>2. nyelv</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-224">Language <sup>2</sup></span></span> | `regionlanguage-languageoptions`                  |
| <span data-ttu-id="646bf-225">Nyelv</span><span class="sxs-lookup"><span data-stu-id="646bf-225">Language</span></span>      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="646bf-226">Region</span><span class="sxs-lookup"><span data-stu-id="646bf-226">Region</span></span>        | `regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="646bf-227">Biztonsági & frissítése</span><span class="sxs-lookup"><span data-stu-id="646bf-227">Update & Security</span></span>
| <span data-ttu-id="646bf-228">Beállítások lap</span><span class="sxs-lookup"><span data-stu-id="646bf-228">Settings page</span></span>                         | <span data-ttu-id="646bf-229">URI</span><span class="sxs-lookup"><span data-stu-id="646bf-229">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="646bf-230">Speciális beállítások</span><span class="sxs-lookup"><span data-stu-id="646bf-230">Advanced Options</span></span>                    | `windowsupdate-options`         |
| <span data-ttu-id="646bf-231">Visszaállítás & <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="646bf-231">Reset & Recovery <sup>2</sup></span></span>      | `reset`         |
| <span data-ttu-id="646bf-232">Windows Insider Program</span><span class="sxs-lookup"><span data-stu-id="646bf-232">Windows Insider Program</span></span>               | `windowsinsider` <br>`windowsinsider-optin`          |
| <span data-ttu-id="646bf-233">Windows Update</span><span class="sxs-lookup"><span data-stu-id="646bf-233">Windows Update</span></span>                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><span data-ttu-id="646bf-234"><sup>1</sup>`windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="646bf-234"><sup>1</sup>`windowsupdate-options`</span></span><br><span data-ttu-id="646bf-235"><sup>1</sup>`windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="646bf-235"><sup>1</sup>`windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="646bf-236">Windows Frissítés – Frissítések keresése</span><span class="sxs-lookup"><span data-stu-id="646bf-236">Windows Update - Checks for updates</span></span> | `windowsupdate-action`          |


- <span data-ttu-id="646bf-237"><sup>1</sup> – Az Windows Holographic 21H1-es verziójánál korábbi verziók esetén a következő  két URI valójában nem a Speciális beállítások vagy beállítások **oldalra** lép; csak a Frissítés oldal fő Windows vagy fognak jelenni.</span><span class="sxs-lookup"><span data-stu-id="646bf-237"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="646bf-238">windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="646bf-238">windowsupdate-options</span></span>
  -  <span data-ttu-id="646bf-239">windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="646bf-239">windowsupdate-restartoptions</span></span>

- <span data-ttu-id="646bf-240"><sup>2</sup> – Elérhető Windows Holographic 21H1 vagy újabb verzióban.</span><span class="sxs-lookup"><span data-stu-id="646bf-240"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="646bf-241">Az URI-k teljes Windows 10 Gépház tekintse meg az indítási beállítások [dokumentációját.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)</span><span class="sxs-lookup"><span data-stu-id="646bf-241">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
