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
# <a name="network-security"></a>Hálózati biztonság

## <a name="network-protocols"></a>Hálózati protokollok

Az elavult NetBIOS-t (alapszintű hálózati bemeneti/kimeneti rendszert) széles körben használták a múltban LAN-forgatókönyvekben – gyakran a számítógép és a megosztott mappák névfeloldásához. Idővel azonban a NetBIOS ki volt téve a többszörös támadásoknak, és a relevanciája a többi biztonságosabb protokollt is támogatja. A biztonsági rés megszüntetéséhez a HoloLens 2 kiiktatta a NetBIOS-hez kapcsolódó kódot az operációs rendszerből.

A TLS (Transport Layer Security) protokollok folyamatosan fejlődnek. Annak érdekében, hogy lépést tartsunk az ezen a területen feltárt különböző biztonsági résekkel, a számítástechnikai iparág egyre újabb és hatékonyabb verziókra is kihat. Mivel az összes kiszolgálótelepítésnek szüksége van az új TLS protokollverziók alkalmazásához, olyan tartalék mechanizmus is használhatja, amely lehetővé teszi, hogy az ügyfél és a különböző alapértelmezett protokollverziók kiszolgálói továbbra is kommunikáljanak az átváltási időszak alatt.

## <a name="secure-connectivity"></a>Biztonságos kapcsolat 

A Windows Defender tűzfal kritikus fontosságú funkciókat biztosít az eszközkapcsolatok biztonságossá teéhez. A HoloLens 2-ben a tűzfal mindig engedélyezve van, és nem lehet programozott módon vagy a felhasználói felületen keresztül letiltani.

A mobil ügyfelek távelérési és kapcsolati adatvédelme az [UWP VPN beépülő modul platformján keresztül biztosítható.](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041) A külső VPN-szolgáltatók saját beépülő modulokat hozhatnak létre a WinRT API-k használatával, amelyek az AppContainer-sandboxban fognak futni, így kiküszöbölve a rendszerszintű illesztőprogramok írásával gyakran járó összetettséget és problémákat.
