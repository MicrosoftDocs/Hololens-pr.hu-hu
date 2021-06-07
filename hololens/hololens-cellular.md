---
title: Csatlakozás mobilhálózathoz és 5G-hez
description: Csatlakozás mobilhálózathoz HoloLens vegyes valóságú eszközeiről.
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 8318d011d6a593c1036b6bcf6f7973870b0dc294
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379519"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="8b249-103">Csatlakozás mobilhálózathoz és 5G-hez</span><span class="sxs-lookup"><span data-stu-id="8b249-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="8b249-104">A HoloLens 2 két módszert támogat a mobilhálózathoz és az 5G-hálózatokhoz való csatlakozáshoz:</span><span class="sxs-lookup"><span data-stu-id="8b249-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="8b249-105">A mobilhálózat által biztosított alkalmi Wi-Fi-hálózat, amelyet gyakran "elérési pontnak" is nevezik</span><span class="sxs-lookup"><span data-stu-id="8b249-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="8b249-106">Usb-C-csatlakoztatott eszközök korlátozott támogatása</span><span class="sxs-lookup"><span data-stu-id="8b249-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="8b249-107">Elérési pont (Wi-Fi)</span><span class="sxs-lookup"><span data-stu-id="8b249-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="8b249-108">A legtöbb mobilkapcsolati igény egy elérési ponttal is kielégítható.</span><span class="sxs-lookup"><span data-stu-id="8b249-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="8b249-109">A HoloLens 2 Wi-Fi támogatja a 802.11ac-t, amely a leggyakoribb esetekben szükséges sávszélességre és késésre vonatkozó követelményeket biztosít.</span><span class="sxs-lookup"><span data-stu-id="8b249-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="8b249-110">A Wi-Fi kábel nélküli, és a legtöbb mobilhálózati eszközzel kompatibilis.</span><span class="sxs-lookup"><span data-stu-id="8b249-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="8b249-111">Kapcsolódás elérési ponthoz</span><span class="sxs-lookup"><span data-stu-id="8b249-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="8b249-112">A hozzáférési pont módjának engedélyezéséről az eszköz használati útmutatója alapján tájékozódjon.</span><span class="sxs-lookup"><span data-stu-id="8b249-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="8b249-113">Engedélyezze a elérési pont módot, és nevezze el a hálózatot, valamint egy ismert jelszót.</span><span class="sxs-lookup"><span data-stu-id="8b249-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="8b249-114">A HoloLens 2 Hálózati beállítások között keresse meg a 2. lépésben létrehozott Wi-Fi-hálózatot, és csatlakozzon hozzá.</span><span class="sxs-lookup"><span data-stu-id="8b249-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="8b249-115">USB-C Tethering</span><span class="sxs-lookup"><span data-stu-id="8b249-115">USB-C Tethering</span></span>

<span data-ttu-id="8b249-116">Az USB-C-tethering alacsonyabb késést biztosít az olyan speciális számítási feladatok esetében, amelyekre szükség van.</span><span class="sxs-lookup"><span data-stu-id="8b249-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="8b249-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)például kihasználhatja a internetezést.</span><span class="sxs-lookup"><span data-stu-id="8b249-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="8b249-118">Vegye figyelembe, hogy a internetezéshez kábelre van szükség a mobileszközök és a HoloLens között, és a tetheringet korlátozott számú eszköz támogatja.</span><span class="sxs-lookup"><span data-stu-id="8b249-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="8b249-119">USB-C-kompatibilitás</span><span class="sxs-lookup"><span data-stu-id="8b249-119">USB-C compatibility</span></span>

<span data-ttu-id="8b249-120">A Windows Holographic 2004-es és újabb verzióiban korlátozott számú olyan eszköz használható, amely Ethernet-adapterként működik.</span><span class="sxs-lookup"><span data-stu-id="8b249-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="8b249-121">Az ethernet-adapterként nem jelenítő eszközöknek támogatniuk kell az általános Microsoft [RNDIS-illesztőprogramot.](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-)</span><span class="sxs-lookup"><span data-stu-id="8b249-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="8b249-122">De csak korlátozott számú eszköz kompatibilis a HoloLens 2-nal.</span><span class="sxs-lookup"><span data-stu-id="8b249-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="8b249-123">Az általános Microsoft RNDIS-illesztőprogram támogatásával kapcsolatos részletekért forduljon az eszköz gyártójához.</span><span class="sxs-lookup"><span data-stu-id="8b249-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="8b249-124">Azok az eszközök, amelyek nem kompatibilisek az RNDIS-rel, vagy illesztőprogram vagy alkalmazás telepítését igénylik, nem támogatottak.</span><span class="sxs-lookup"><span data-stu-id="8b249-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="8b249-125">Bár a Microsoft nem tartja fenn a kompatibilis eszközök listáját, a témáról itt is folyik közösségi [vitafórum.](https://aka.ms/HLCommunityCell)</span><span class="sxs-lookup"><span data-stu-id="8b249-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="8b249-126">Csatlakozás egy összekapcsolt eszközhöz</span><span class="sxs-lookup"><span data-stu-id="8b249-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="8b249-127">Az USB-kapcsolaton keresztüli adatmegosztás engedélyezésével kapcsolatos információkért tekintse meg az eszköz kézikönyvét.</span><span class="sxs-lookup"><span data-stu-id="8b249-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="8b249-128">Ezt a beállítást gyakran "USB Tethering", "Adatmegosztás" vagy "USB Modem" néven is nevezik.</span><span class="sxs-lookup"><span data-stu-id="8b249-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="8b249-129">Adatmegosztás engedélyezése USB-kapcsolaton keresztül.</span><span class="sxs-lookup"><span data-stu-id="8b249-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="8b249-130">Csatlakoztassa az eszközt a HoloLens USB-C portjához.</span><span class="sxs-lookup"><span data-stu-id="8b249-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="8b249-131">A HoloLens 2 hálózati beállításaiban az eszköz automatikusan Ethernet-kapcsolatként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="8b249-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
