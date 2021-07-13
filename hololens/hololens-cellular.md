---
title: Csatlakozás mobilhálózathoz és 5G-hez
description: Csatlakozás mobilhálózathoz a HoloLens vegyes valóságú eszközökről.
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
ms.openlocfilehash: 6f7da0263e8637486f0151fd2b9da55da8feccc1
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635840"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="45091-103">Csatlakozás mobilhálózathoz és 5G-hez</span><span class="sxs-lookup"><span data-stu-id="45091-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="45091-104">HoloLens 2. kapcsolat két módszert támogat a mobilhálózathoz és az 5G-hálózatokhoz való csatlakozáshoz:</span><span class="sxs-lookup"><span data-stu-id="45091-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="45091-105">A mobilhálózat által biztosított alkalmi Wi-Fi-hálózat, amelyet gyakran "elérési pontnak" is nevezik</span><span class="sxs-lookup"><span data-stu-id="45091-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="45091-106">Korlátozott támogatás USB-C-hez csatlakoztatott eszközökhöz</span><span class="sxs-lookup"><span data-stu-id="45091-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="45091-107">Elérési pont (Wi-Fi)</span><span class="sxs-lookup"><span data-stu-id="45091-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="45091-108">A legtöbb mobilkapcsolati igény egy elérési ponttal is kielégítható.</span><span class="sxs-lookup"><span data-stu-id="45091-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="45091-109">HoloLens 2. Wi-Fi támogatja a 802.11ac-et, amely a leggyakoribb esetekben szükséges sávszélesség- és késési követelményeket biztosítja.</span><span class="sxs-lookup"><span data-stu-id="45091-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="45091-110">A Wi-Fi kábel nélküli, és a legtöbb mobilhálózati eszközzel kompatibilis.</span><span class="sxs-lookup"><span data-stu-id="45091-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="45091-111">Kapcsolódás elérési ponthoz</span><span class="sxs-lookup"><span data-stu-id="45091-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="45091-112">Tekintse meg az eszköz használati útmutatóját a elérési pont módjának engedélyezéséről.</span><span class="sxs-lookup"><span data-stu-id="45091-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="45091-113">Engedélyezze a elérési pont módot, és nevezze el a hálózatot, valamint egy ismert jelszót.</span><span class="sxs-lookup"><span data-stu-id="45091-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="45091-114">A HoloLens 2. lépésben található Hálózati beállítások között keresse meg a 2. lépésben létrehozott Wi-Fi-hálózatot, és csatlakozzon hozzá.</span><span class="sxs-lookup"><span data-stu-id="45091-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="45091-115">USB-C Tethering</span><span class="sxs-lookup"><span data-stu-id="45091-115">USB-C Tethering</span></span>

<span data-ttu-id="45091-116">Az USB-C-internetezés alacsonyabb késést biztosít az olyan speciális számítási feladatoknál, amelyekhez szükség van rá.</span><span class="sxs-lookup"><span data-stu-id="45091-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="45091-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)például előnyös lehet a tethering.</span><span class="sxs-lookup"><span data-stu-id="45091-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="45091-118">Vegye figyelembe, hogy a internetezéshez kábelre van szükség a mobileszközök és a HoloLens között, és a internetezést korlátozott számú eszköz támogatja.</span><span class="sxs-lookup"><span data-stu-id="45091-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="45091-119">USB-C-kompatibilitás</span><span class="sxs-lookup"><span data-stu-id="45091-119">USB-C compatibility</span></span>

<span data-ttu-id="45091-120">A Holographic 2004-es és újabb verzióiban korlátozott számú, Ethernet-adapterként Windows eszköz használható.</span><span class="sxs-lookup"><span data-stu-id="45091-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="45091-121">Az Ethernet-adapterként nem jelenítő eszközöknek támogatniuk kell az általános Microsoft [RNDIS-illesztőprogramot.](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-)</span><span class="sxs-lookup"><span data-stu-id="45091-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="45091-122">Ezen eszközök közül azonban csak korlátozott számú kompatibilis a HoloLens 2-es verzióval.</span><span class="sxs-lookup"><span data-stu-id="45091-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="45091-123">Az általános Microsoft RNDIS-illesztőprogram támogatásával kapcsolatos részletekért forduljon az eszköz gyártójához.</span><span class="sxs-lookup"><span data-stu-id="45091-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="45091-124">Azok az eszközök, amelyek nem kompatibilisek RNDIS-rel, vagy illesztőprogram vagy alkalmazás telepítését igénylik, nem támogatottak.</span><span class="sxs-lookup"><span data-stu-id="45091-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="45091-125">Bár a Microsoft nem tartja fenn a kompatibilis eszközök listáját, a témáról itt tartunk közösségi [vitafórumot.](https://aka.ms/HLCommunityCell)</span><span class="sxs-lookup"><span data-stu-id="45091-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="45091-126">Csatlakozás egy összekapcsolt eszközhöz</span><span class="sxs-lookup"><span data-stu-id="45091-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="45091-127">Az USB-adatmegosztás engedélyezésével kapcsolatos információkért tekintse meg az eszköz használati útmutatóját.</span><span class="sxs-lookup"><span data-stu-id="45091-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="45091-128">Ezt a beállítást gyakran "USB Tetheringnek", "Adatmegosztásnak" vagy "USB modemnek" is nevezik.</span><span class="sxs-lookup"><span data-stu-id="45091-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="45091-129">Adatmegosztás engedélyezése USB-n keresztül.</span><span class="sxs-lookup"><span data-stu-id="45091-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="45091-130">Csatlakozás az eszközt a HoloLens USB-C-portra.</span><span class="sxs-lookup"><span data-stu-id="45091-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="45091-131">A HoloLens 2. hálózati beállításnál az eszköz automatikusan Ethernet-kapcsolatként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="45091-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
