---
title: Az új Beállítások alkalmazás bevezetése
description: Tudnivalók az új Beállítások alkalmazásról
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, beállítások, alkalmazásválasztó, kötet
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bf1a2080c15346843b9ea9b2d0dc93154e185107
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379658"
---
# <a name="new-settings-app"></a><span data-ttu-id="c328b-104">Új beállítások alkalmazás</span><span class="sxs-lookup"><span data-stu-id="c328b-104">New Settings app</span></span>

<span data-ttu-id="c328b-105">A [Windows Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójával bevezetjük a Settings alkalmazás új verzióját.</span><span class="sxs-lookup"><span data-stu-id="c328b-105">With [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="c328b-106">Az új Beállítások alkalmazás új funkciókat és kibővített beállításokat tartalmaz a HoloLens 2-hez a következő területeken: Hang, Power & sleep, Network & Internet, Alkalmazások, Fiókok, Könnyű kezelés stb.</span><span class="sxs-lookup"><span data-stu-id="c328b-106">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="c328b-107">Mivel az új Beállítások alkalmazás különbözik az örökölt Beállítások alkalmazástól, a környezetben korábban elhelyezett beállítások ablakai frissítéskor el lesznek távolítva.</span><span class="sxs-lookup"><span data-stu-id="c328b-107">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![Új beállítások alkalmazás kezdőlapja](images/new-settings-app.png)

<span data-ttu-id="c328b-109">**Új funkciók és beállítások**</span><span class="sxs-lookup"><span data-stu-id="c328b-109">**New features and settings**</span></span>
- <span data-ttu-id="c328b-110">Beállítások keresése: a beállításokat a Beállítások kezdőlapon kulcsszavak vagy a beállítás nevének használatával keresheti meg.</span><span class="sxs-lookup"><span data-stu-id="c328b-110">Settings search: search for settings from the Settings homepage using keywords or the setting's name.</span></span>
- <span data-ttu-id="c328b-111">A rendszer > [színezése](hololens2-display.md#how-to-use-display-color-calibration)</span><span class="sxs-lookup"><span data-stu-id="c328b-111">System > [Color calibration](hololens2-display.md#how-to-use-display-color-calibration)</span></span>
    - <span data-ttu-id="c328b-112">Válasszon egy alternatív színprofilt a HoloLens 2-es megjelenítéshez.</span><span class="sxs-lookup"><span data-stu-id="c328b-112">Select an alternative color profile for your HoloLens 2 display.</span></span>
- <span data-ttu-id="c328b-113">System > Sound:</span><span class="sxs-lookup"><span data-stu-id="c328b-113">System > Sound:</span></span>
  - <span data-ttu-id="c328b-114">Bemeneti és kimeneti hangeszközök: egymástól függetlenül válassza ki a bemeneti és kimeneti hangeszközöket (például Bluetooth-kábelen keresztüli hanglejátszást, vagy USB-C mikrofont használjon a hangbemenethez).</span><span class="sxs-lookup"><span data-stu-id="c328b-114">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span>
    > [!NOTE]
    > <span data-ttu-id="c328b-115">A HoloLens 2 nem támogatja a Bluetooth-mikrofonokat.</span><span class="sxs-lookup"><span data-stu-id="c328b-115">Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="c328b-116">Alkalmazáskötet: az egyes alkalmazások kötetét egymástól függetlenül módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="c328b-116">App volume: independently adjust the volume of each app.</span></span> <span data-ttu-id="c328b-117">Lásd: [alkalmazásonkénti kötetvezérlés.](holographic-home.md#per-app-volume-control)</span><span class="sxs-lookup"><span data-stu-id="c328b-117">See [per app volume control](holographic-home.md#per-app-volume-control).</span></span>
- <span data-ttu-id="c328b-118">A > Power &: megadhatja, hogy az eszköz mikor legyen alvó üzemmódban egy bizonyos tétlenség után.</span><span class="sxs-lookup"><span data-stu-id="c328b-118">System > Power & sleep: choose when the device should go to sleep after a period of inactivity.</span></span>
- <span data-ttu-id="c328b-119">Rendszer > akkumulátor: manuálisan engedélyezheti az takarékos üzemmód üzemmódot, vagy beállíthatja az akkumulátor töltöttségi küszöbértékét, amely takarékos üzemmód bekapcsolja automatikusan.</span><span class="sxs-lookup"><span data-stu-id="c328b-119">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically.</span></span>
- <span data-ttu-id="c328b-120">USB> eszközök: alapértelmezés szerint letilthatja az USB-kapcsolatokat.</span><span class="sxs-lookup"><span data-stu-id="c328b-120">Devices > USB: you can disable USB connections by default.</span></span>
- <span data-ttu-id="c328b-121">Hálózati & internet:</span><span class="sxs-lookup"><span data-stu-id="c328b-121">Network & Internet:</span></span>
  - <span data-ttu-id="c328b-122">Az USB-C Ethernet-adapterek mostantól a Hálózati adapterek & jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="c328b-122">USB-C Ethernet adapters will now appear in Network & Internet.</span></span>
  - <span data-ttu-id="c328b-123">Elérhetőek az USB-C Ethernet-adapter beállításai, beleértve annak IP-címét is.</span><span class="sxs-lookup"><span data-stu-id="c328b-123">USB-C Ethernet adapter settings are now available, including its IP address.</span></span>
  - <span data-ttu-id="c328b-124">Mostantól engedélyezheti a repülőgép üzemmódot a HoloLens 2-ben.</span><span class="sxs-lookup"><span data-stu-id="c328b-124">You can now enable airplane mode on HoloLens 2.</span></span>
- <span data-ttu-id="c328b-125">Alkalmazások: alaphelyzetbe állíthatja a fájl- és hivatkozástípusokhoz használt alapértelmezett alkalmazásokat.</span><span class="sxs-lookup"><span data-stu-id="c328b-125">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="c328b-126">További információ: [Alapértelmezett alkalmazásválasztó.](holographic-home.md#default-app-picker)</span><span class="sxs-lookup"><span data-stu-id="c328b-126">For more information see [Default app picker](holographic-home.md#default-app-picker).</span></span>
- <span data-ttu-id="c328b-127">Fiókok > Egyéb felhasználók: az eszköztulajdonosok felhasználókat adhatnak hozzá, frissítheti a normál felhasználókat az eszköztulajdonosokra, visszaminősítheti az eszköztulajdonosokat a normál felhasználókra, és eltávolíthat felhasználókat.</span><span class="sxs-lookup"><span data-stu-id="c328b-127">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="c328b-128">Könnyű kezelés: szövegméret és néhány vizuális hatás módosítása.</span><span class="sxs-lookup"><span data-stu-id="c328b-128">Ease of Access: change text size and some visual effects.</span></span>

<span data-ttu-id="c328b-129">**Ismert problémák**</span><span class="sxs-lookup"><span data-stu-id="c328b-129">**Known issues**</span></span>
- <span data-ttu-id="c328b-130">A korábban elhelyezett Beállítások ablakokat a rendszer eltávolítja (lásd a fenti megjegyzést).</span><span class="sxs-lookup"><span data-stu-id="c328b-130">Previously placed Settings windows will be removed (see note above).</span></span>
- <span data-ttu-id="c328b-131">A Továbbiakban nem nevezheti át az eszközt a Beállítások alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="c328b-131">You can no longer rename your device with the Settings app.</span></span> <span data-ttu-id="c328b-132">A rendszergazdák a [Windows Autopilot for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) eszköznévsablon vagy az MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName csomópont használatával nevezheti át az eszközöket.</span><span class="sxs-lookup"><span data-stu-id="c328b-132">IT admins can rename devices by using the [Windows Autopilot for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) device name template or the MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName node.</span></span>
- <span data-ttu-id="c328b-133">Az Ethernet-oldal mindig egy virtuális Ethernet-eszközt ("UsbNcm") mutat.</span><span class="sxs-lookup"><span data-stu-id="c328b-133">The Ethernet page shows a virtual Ethernet device ("UsbNcm") at all times.</span></span>
- <span data-ttu-id="c328b-134">Előfordulhat, hogy az új Microsoft Edge akkumulátor-használata nem pontos, mivel az UWP-adapterréteg által támogatott Win32 asztali alkalmazás (hamarosan nem várható javítás).</span><span class="sxs-lookup"><span data-stu-id="c328b-134">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon).</span></span>

