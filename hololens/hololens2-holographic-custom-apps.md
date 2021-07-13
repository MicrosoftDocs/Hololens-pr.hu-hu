---
title: Egyéni alkalmazások kezelése a 2. HoloLens esetén
description: Megtudhatja, hogyan telepíthet, távolíthat el és telepíthet egyéni holografikus alkalmazásokat HoloLens 2 eszközön a Eszközportál és Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 01/21/2021
manager: yannisle
keywords: hololens, hololens 2, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: joyjaz
ms.author: v-jjaswinski
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens 2
ms.openlocfilehash: d2280a794455090c61a7bf30bc5dc5b8faf5adbe
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636401"
---
# <a name="manage-custom-apps-for-hololens-2"></a><span data-ttu-id="bf2fc-104">Egyéni alkalmazások kezelése a 2. HoloLens esetén</span><span class="sxs-lookup"><span data-stu-id="bf2fc-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="bf2fc-105">HoloLens számos meglévő alkalmazást támogat a Microsoft Store, valamint a kifejezetten a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bf2fc-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="bf2fc-106">További információ az áruházbeli alkalmazásokról: [Alkalmazások kezelése az áruházban.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="bf2fc-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf2fc-107">Vállalati üzemelő példányok esetén nem javasoljuk a Fejlesztői mód engedélyezését, amelyet mindkét módszer használ.</span><span class="sxs-lookup"><span data-stu-id="bf2fc-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="bf2fc-108">Ha biztonságos alkalmazástelepítési módszer érdekli, tekintse át az [Alkalmazáskezelés: Áttekintés témakört.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bf2fc-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="bf2fc-109">Ha az alkalmazástelepítés fejlesztői módszerét keresi HoloLens 2 eszközön, tekintse meg a következőt:</span><span class="sxs-lookup"><span data-stu-id="bf2fc-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>

- [<span data-ttu-id="bf2fc-110">Eszközportál: Alkalmazás telepítése</span><span class="sxs-lookup"><span data-stu-id="bf2fc-110">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="bf2fc-111">Alkalmazások Visual Studio és hibakeresése a Visual Studio használatával</span><span class="sxs-lookup"><span data-stu-id="bf2fc-111">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="bf2fc-112">Tekintse meg [az útmutatót,](holographic-custom-apps.md) ha egyéni alkalmazásokat szeretne üzembe helyezni a HoloLens (1. generációs) virtuális gépre.</span><span class="sxs-lookup"><span data-stu-id="bf2fc-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>
