---
title: Windows Defender Alkalmazásvezérlés – WDAC
description: Az alkalmazásvezérlés Windows Defender és használatának áttekintése a vegyes valóságú HoloLens kezeléséhez.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639930"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="1197f-103">Windows Defender Alkalmazásvezérlés – WDAC</span><span class="sxs-lookup"><span data-stu-id="1197f-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="1197f-104">A WDAC lehetővé teszi, hogy a rendszergazda úgy konfigurálja az eszközeit, hogy letiltsa az alkalmazások elindítását az eszközökön.</span><span class="sxs-lookup"><span data-stu-id="1197f-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="1197f-105">Ez eltér az eszközkorlátozási módszerektől, például a Kioszk módtól, ahol a felhasználó számára egy olyan felhasználói felület van meg, amely elrejti az eszközön található alkalmazásokat, de továbbra is elindítható.</span><span class="sxs-lookup"><span data-stu-id="1197f-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="1197f-106">A WDAC megvalósítása közben az alkalmazások továbbra is láthatók a Minden alkalmazás listában, de a WDAC megakadályozza, hogy ezeket az alkalmazásokat és folyamatokat az eszköz felhasználója elindítsa.</span><span class="sxs-lookup"><span data-stu-id="1197f-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="1197f-107">Egy eszközhöz több WDAC-szabályzat is hozzárendelhető.</span><span class="sxs-lookup"><span data-stu-id="1197f-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="1197f-108">Ha több WDAC-házirend van beállítva egy rendszeren, a legszigorúbb házirendek lépnek életbe.</span><span class="sxs-lookup"><span data-stu-id="1197f-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="1197f-109">Amikor a végfelhasználók olyan alkalmazást próbálnak meg elindítani, amelyet a WDAC blokkol, HoloLens nem kapnak értesítést arról, hogy nem tudják elindítani az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="1197f-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="1197f-110">Az alábbi útmutató segítségével a felhasználók megtudhatják, hogyan engedélyezheti vagy tilthatja le az alkalmazásokat [a WDAC](/mem/intune/configuration/custom-profile-hololens)és a Windows PowerShell használatával HoloLens 2 eszközön a Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="1197f-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="1197f-111">Amikor a felhasználók az első példalépéssel rákeresnek a Windows 10 telepített alkalmazásokra, előfordulhat, hogy néhány kísérletet kell tenniük az eredmények szűkítésére.</span><span class="sxs-lookup"><span data-stu-id="1197f-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="1197f-112">Ha nem tudja a csomag teljes nevét, előfordulhat, hogy néhányszor futtatnia kell a Get-AppxPackage -name \* YourBestGuess \* nevét, hogy megtalálja.</span><span class="sxs-lookup"><span data-stu-id="1197f-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="1197f-113">A név után futtassa a következőt: "$package 1 = Get-AppxPackage -name Actual.PackageName"</span><span class="sxs-lookup"><span data-stu-id="1197f-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="1197f-114">Ha például a következőt futtatja Microsoft Edge több eredményt ad vissza, de ebből a listából megállapíthatja, hogy a teljes név, amire szüksége van, a Microsoft.MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="1197f-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="1197f-115">Csomag családneveket a HoloLens</span><span class="sxs-lookup"><span data-stu-id="1197f-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="1197f-116">A fent hivatkozott útmutatóban manuálisan szerkesztheti az alkalmazásokat, és newPolicy.xml adhat hozzá szabályokat az olyan alkalmazásokhoz, amelyek csak HoloLens a csomagjuk családnevekkel.</span><span class="sxs-lookup"><span data-stu-id="1197f-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="1197f-117">Előfordulhat, hogy olyan alkalmazásokat használ, amelyek nem az asztali számítógépen vannak, és ezeket hozzá szeretné adni a szabályzathoz.</span><span class="sxs-lookup"><span data-stu-id="1197f-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="1197f-118">Az alábbi lista a 2 eszköz In-Box használt és HoloLens alkalmazások listáját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="1197f-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="1197f-119">Alkalmazásnév</span><span class="sxs-lookup"><span data-stu-id="1197f-119">App Name</span></span>                   | <span data-ttu-id="1197f-120">Csomag családneve</span><span class="sxs-lookup"><span data-stu-id="1197f-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="1197f-121">3D-megjelenítő</span><span class="sxs-lookup"><span data-stu-id="1197f-121">3D Viewer</span></span>                  | <span data-ttu-id="1197f-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1197f-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="1197f-123">Alkalmazástelepítő</span><span class="sxs-lookup"><span data-stu-id="1197f-123">App Installer</span></span>              | <span data-ttu-id="1197f-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1197f-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="1197f-125">Naptár</span><span class="sxs-lookup"><span data-stu-id="1197f-125">Calendar</span></span>                   | <span data-ttu-id="1197f-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1197f-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="1197f-127">Kamera</span><span class="sxs-lookup"><span data-stu-id="1197f-127">Camera</span></span>                     | <span data-ttu-id="1197f-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="1197f-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="1197f-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="1197f-129">Cortana</span></span>                    | <span data-ttu-id="1197f-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1197f-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="1197f-131">Dynamics 365-útmutatók</span><span class="sxs-lookup"><span data-stu-id="1197f-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="1197f-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1197f-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="1197f-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="1197f-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="1197f-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1197f-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="1197f-135">Visszajelzési központ</span><span class="sxs-lookup"><span data-stu-id="1197f-135">Feedback Hub</span></span>               | <span data-ttu-id="1197f-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1197f-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="1197f-137">Fájlkezelő</span><span class="sxs-lookup"><span data-stu-id="1197f-137">File Explorer</span></span>              | <span data-ttu-id="1197f-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="1197f-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="1197f-139">Mail</span><span class="sxs-lookup"><span data-stu-id="1197f-139">Mail</span></span>                       | <span data-ttu-id="1197f-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1197f-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="1197f-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="1197f-141">Microsoft Store</span></span>            | <span data-ttu-id="1197f-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1197f-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="1197f-143">Filmek & TV</span><span class="sxs-lookup"><span data-stu-id="1197f-143">Movies & TV</span></span>                | <span data-ttu-id="1197f-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1197f-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="1197f-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="1197f-145">OneDrive</span></span>                   | <span data-ttu-id="1197f-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1197f-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="1197f-147">Fotók</span><span class="sxs-lookup"><span data-stu-id="1197f-147">Photos</span></span>                     | <span data-ttu-id="1197f-148">Microsoft. Windows. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1197f-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="1197f-149">Beállítások</span><span class="sxs-lookup"><span data-stu-id="1197f-149">Settings</span></span>                   | <span data-ttu-id="1197f-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="1197f-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="1197f-151">Tippek</span><span class="sxs-lookup"><span data-stu-id="1197f-151">Tips</span></span>                       | <span data-ttu-id="1197f-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1197f-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="1197f-153">1 – A Alkalmazástelepítő blokkolás csak a Alkalmazástelepítő alkalmazást blokkolja, más forrásokból, például a Microsoft Store vagy az MDM-megoldásból telepített alkalmazásokat nem.</span><span class="sxs-lookup"><span data-stu-id="1197f-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="1197f-154">Csomag családnevének megkeresés</span><span class="sxs-lookup"><span data-stu-id="1197f-154">How to find a Package Family Name</span></span>

<span data-ttu-id="1197f-155">Ha egy alkalmazás nem szerepel a listában, akkor a felhasználó használhatja a Eszközportál-t, amely egy olyan HoloLens 2-hez csatlakozik, amely le szeretné tiltani az alkalmazást, és meghatározza a PackageRelativeID azonosítót, és onnantól a PackageFamilyName megjelenik.</span><span class="sxs-lookup"><span data-stu-id="1197f-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="1197f-156">Telepítse az alkalmazást a HoloLens 2-es eszközön.</span><span class="sxs-lookup"><span data-stu-id="1197f-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="1197f-157">Nyissa meg Gépház -> Updates & Security -> For developers (Biztonsági  beállítások fejlesztőknek) és engedélyezze a Fejlesztői módot, majd az **Eszközportál gombra.**</span><span class="sxs-lookup"><span data-stu-id="1197f-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="1197f-158">További részletekért olvassa el az eszközportál beállítását és [használatát itt.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="1197f-158">More more details instructions read more about [setup and use of device portal here](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="1197f-159">Miután Eszközportál, lépjen a **Nézetek,** majd az Alkalmazások **lapra.**</span><span class="sxs-lookup"><span data-stu-id="1197f-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="1197f-160">Az Installed Apps (Telepített alkalmazások) panelen válassza ki a telepített alkalmazást a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="1197f-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="1197f-161">Keresse meg a PackageRelativeID azonosítót.</span><span class="sxs-lookup"><span data-stu-id="1197f-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="1197f-162">Másolja az alkalmazás karaktereit a ! karakter előtt, ezek lesznek a PackageFamilyName karakterei.</span><span class="sxs-lookup"><span data-stu-id="1197f-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


