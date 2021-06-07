---
title: Hálózati biztonság
description: hálózati biztonság
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: biztonság, hololens, hálózat, hálózati biztonság
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f1e5304408a9a9543eb0703ad7321725484eef01
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379551"
---
# <a name="network-security"></a><span data-ttu-id="32784-104">Hálózati biztonság</span><span class="sxs-lookup"><span data-stu-id="32784-104">Network security</span></span>

## <a name="network-protocols"></a><span data-ttu-id="32784-105">Hálózati protokollok</span><span class="sxs-lookup"><span data-stu-id="32784-105">Network protocols</span></span>

<span data-ttu-id="32784-106">Az elavult NetBIOS-t (alapszintű hálózati bemeneti/kimeneti rendszert) széles körben használták a múltban LAN-forgatókönyvekben – gyakran a számítógép és a megosztott mappák névfeloldásához.</span><span class="sxs-lookup"><span data-stu-id="32784-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="32784-107">Idővel azonban a NetBIOS ki volt téve a többszörös támadásoknak, és a relevanciája a többi biztonságosabb protokollt is támogatja.</span><span class="sxs-lookup"><span data-stu-id="32784-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="32784-108">A biztonsági rés megszüntetéséhez a HoloLens 2 kiiktatta a NetBIOS-hez kapcsolódó kódot az operációs rendszerből.</span><span class="sxs-lookup"><span data-stu-id="32784-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="32784-109">A TLS (Transport Layer Security) protokollok folyamatosan fejlődnek.</span><span class="sxs-lookup"><span data-stu-id="32784-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="32784-110">Annak érdekében, hogy lépést tartsunk az ezen a területen feltárt különböző biztonsági résekkel, a számítástechnikai iparág egyre újabb és hatékonyabb verziókra is kihat.</span><span class="sxs-lookup"><span data-stu-id="32784-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="32784-111">Mivel az összes kiszolgálótelepítésnek szüksége van az új TLS protokollverziók alkalmazásához, olyan tartalék mechanizmus is használhatja, amely lehetővé teszi, hogy az ügyfél és a különböző alapértelmezett protokollverziók kiszolgálói továbbra is kommunikáljanak az átváltási időszak alatt.</span><span class="sxs-lookup"><span data-stu-id="32784-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <a name="secure-connectivity"></a><span data-ttu-id="32784-112">Biztonságos kapcsolat</span><span class="sxs-lookup"><span data-stu-id="32784-112">Secure connectivity</span></span> 

<span data-ttu-id="32784-113">A Windows Defender tűzfal kritikus fontosságú funkciókat biztosít az eszközkapcsolatok biztonságossá teéhez.</span><span class="sxs-lookup"><span data-stu-id="32784-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="32784-114">A HoloLens 2-ben a tűzfal mindig engedélyezve van, és nem lehet programozott módon vagy a felhasználói felületen keresztül letiltani.</span><span class="sxs-lookup"><span data-stu-id="32784-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="32784-115">A mobil ügyfelek távelérési és kapcsolati adatvédelme az [UWP VPN beépülő modul platformján keresztül biztosítható.](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041)</span><span class="sxs-lookup"><span data-stu-id="32784-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="32784-116">A külső VPN-szolgáltatók saját beépülő modulokat hozhatnak létre a WinRT API-k használatával, amelyek az AppContainer-sandboxban fognak futni, így kiküszöbölve a rendszerszintű illesztőprogramok írásával gyakran járó összetettséget és problémákat.</span><span class="sxs-lookup"><span data-stu-id="32784-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
