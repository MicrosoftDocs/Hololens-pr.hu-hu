---
title: A HoloLens honosított verzióinak telepítése
description: Ismerje meg, hogyan telepítheti a HoloLens (1. generációs) honosított verzióit, beleértve a kínai és a japán verziót is.
ms.prod: hololens
ms.mktglfcycl: manage
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
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378223"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="a05e8-103">A HoloLens honosított verzióinak telepítése (1. generációs)</span><span class="sxs-lookup"><span data-stu-id="a05e8-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="a05e8-104">Ahhoz, hogy átváltson a HoloLens kínai vagy japán verziójára, a Windows Device Recovery Tool (WDRT) használatával le kell töltenie a nyelvhez szükséges buildet egy számítógépre, majd telepítenie kell a HoloLensen.</span><span class="sxs-lookup"><span data-stu-id="a05e8-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a05e8-105">A WDRT használatával a HoloLens kínai vagy japán buildje törli a meglévő adatokat, például a személyes fájlokat és beállításokat a HoloLensből.</span><span class="sxs-lookup"><span data-stu-id="a05e8-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="a05e8-106">A számítógépen töltse le és telepítse a [Windows Device Recovery Tool (WDRT) eszközt.](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="a05e8-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="a05e8-107">Töltse le a csomagot a számítógépére a kívánt nyelvhez:  [Egyszerűsített kínai vagy](https://aka.ms/hololensdownload-ch) [japán](https://aka.ms/hololensdownload-jp).</span><span class="sxs-lookup"><span data-stu-id="a05e8-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="a05e8-108">A letöltés befejezése után válassza a **Letöltések Fájlkezelő**  >  **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="a05e8-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="a05e8-109">Kattintson a jobb gombbal az előbb letöltött tömörített mappára, és válassza az Extract all Extract **(Összes** kibontás) lehetőséget a  >   kicsomagoláshoz.</span><span class="sxs-lookup"><span data-stu-id="a05e8-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="a05e8-110">Csatlakoztassa a HoloLenst a számítógépéhez a kiszállító mikro-USB-kábellel.</span><span class="sxs-lookup"><span data-stu-id="a05e8-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="a05e8-111">(Ez akkor is működik a legjobban, ha más kábelekkel csatlakoztatta a HoloLenst.)</span><span class="sxs-lookup"><span data-stu-id="a05e8-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="a05e8-112">Miután az eszköz automatikusan észleli a HoloLenst, válassza a Microsoft HoloLens csempét.</span><span class="sxs-lookup"><span data-stu-id="a05e8-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="a05e8-113">A következő képernyőn válassza a **Manuális** csomagválasztás lehetőséget, és válassza ki azt a telepítőfájlt, amely a   4. lépésben kicsomagolt mappában található.</span><span class="sxs-lookup"><span data-stu-id="a05e8-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="a05e8-114">(Keresse meg a ".ffu" kiterjesztésű fájlt.)</span><span class="sxs-lookup"><span data-stu-id="a05e8-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="a05e8-115">Válassza **a Szoftver telepítése lehetőséget,** és kövesse az utasításokat.</span><span class="sxs-lookup"><span data-stu-id="a05e8-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="a05e8-116">A build telepítése után a HoloLens telepítése automatikusan elindul.</span><span class="sxs-lookup"><span data-stu-id="a05e8-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="a05e8-117">Helyezze az eszközre, és kövesse a beállítási utasításokat.</span><span class="sxs-lookup"><span data-stu-id="a05e8-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="a05e8-118">Ha végzett a beállítással, kattintson a Beállítások frissítése & Security Windows Insider Program elemre, és ellenőrizze, hogy konfigurálva van-e a legújabb előzetes verziójú  >    >  buildek fogadására.</span><span class="sxs-lookup"><span data-stu-id="a05e8-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="a05e8-119">Az angol előzetes buildhez Windows Insider Program a HoloLens kínai és japán verziói is naprakészek maradnak a legújabb előzetes verziójú buildekkel.</span><span class="sxs-lookup"><span data-stu-id="a05e8-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="a05e8-120">A Beállítások alkalmazás nem használható a rendszer nyelvének angol, japán és kínai nyelven való módosítására.</span><span class="sxs-lookup"><span data-stu-id="a05e8-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="a05e8-121">Az eszközrendszer nyelvének kizárólag az új buildek flash (flash) használata támogatott.</span><span class="sxs-lookup"><span data-stu-id="a05e8-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="a05e8-122">Bár a képernyőn megjelenő Pinyin-billentyűzettel egyszerűsített kínai vagy japán szöveget is beírhat, az egyszerűsített kínai vagy japán szöveg Bluetooth-hardveres billentyűzettel való begépelése jelenleg nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="a05e8-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="a05e8-123">Kínai vagy japán HoloLensen azonban továbbra is használhatja a Bluetooth-billentyűzetet az angol nyelv begépelésével (a hardveres billentyűzet angol nyelvű begépelésével a ~ billentyű lenyomása után válthat).</span><span class="sxs-lookup"><span data-stu-id="a05e8-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
