---
title: Egyéni alkalmazások kezelése a HoloLens 2-hez
description: Megtudhatja, hogyan telepíthet, távolíthat el és telepíthet egyéni holografikus alkalmazásokat a HoloLens 2-eszközökön a Eszközportál és a Visual Studio.
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
ms.openlocfilehash: e3ae180697c889a426108992ba345dc23b96505c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378057"
---
# <a name="manage-custom-apps-for-hololens-2"></a><span data-ttu-id="a40d7-104">Egyéni alkalmazások kezelése a HoloLens 2-hez</span><span class="sxs-lookup"><span data-stu-id="a40d7-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="a40d7-105">A HoloLens számos meglévő alkalmazást támogat a Microsoft Store, valamint a Kifejezetten a HoloLenshez készült új alkalmazásokat.</span><span class="sxs-lookup"><span data-stu-id="a40d7-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="a40d7-106">További információ az áruházbeli alkalmazásokról: [Alkalmazások kezelése az áruházban.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="a40d7-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a40d7-107">Vállalati üzemelő példányok esetén nem javasoljuk a Fejlesztői mód engedélyezését, amelyet mindkét módszer használ.</span><span class="sxs-lookup"><span data-stu-id="a40d7-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="a40d7-108">Ha egy biztonságos alkalmazástelepítési módszer érdekli, tekintse át az [Alkalmazáskezelés: Áttekintés témakört.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a40d7-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="a40d7-109">Ha a HoloLens 2-eszközök alkalmazástelepítési fejlesztői módszerét keresi, tekintse meg a következőt:</span><span class="sxs-lookup"><span data-stu-id="a40d7-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>
- [<span data-ttu-id="a40d7-110">Eszközportál: Alkalmazás telepítése</span><span class="sxs-lookup"><span data-stu-id="a40d7-110">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="a40d7-111">Alkalmazások Visual Studio és hibakeresése a Visual Studio használatával</span><span class="sxs-lookup"><span data-stu-id="a40d7-111">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="a40d7-112">Tekintse meg [útmutatónkat,](holographic-custom-apps.md) ha egyéni alkalmazásokat szeretne üzembe helyezni a HoloLensben (1. generációs).</span><span class="sxs-lookup"><span data-stu-id="a40d7-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>