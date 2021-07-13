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
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640491"
---
# <a name="network-security"></a>Hálózati biztonság

## <a name="network-protocols"></a>Hálózati protokollok

Az elavult NetBIOS-t (alapszintű hálózati bemeneti/kimeneti rendszert) széles körben használták a múltban LAN-forgatókönyvekben – gyakran a számítógép és a megosztott mappák névfeloldásához. Idővel azonban a NetBIOS ki volt téve a többszörös támadásoknak, és a relevancia más biztonságosabb protokollok mellett csökkent. A biztonsági rés megszüntetéséhez a 2. HoloLens eltávolítja a NetBIOS-hez kapcsolódó kódot az operációs rendszerből.

A TLS(Transport Layer Security) protokollok folyamatosan fejlődnek. Annak érdekében, hogy lépést tartsunk az ezen a területen feltárt különböző biztonsági résekkel, a számítástechnikai iparág újabb és hatékonyabb verziókra is kihat. Mivel az összes kiszolgálótelepítésnek szüksége van az új TLS protokollverziók elfogadására, olyan tartalék mechanizmust valósíthat meg, amely lehetővé teszi, hogy az ügyfél és a különböző alapértelmezett protokollverziók kiszolgálói továbbra is kommunikáljanak az átváltási időszak alatt.

## <a name="secure-connectivity"></a>Biztonságos kapcsolat 

A Windows Defender tűzfal kritikus fontosságú funkciókat biztosít az eszközkapcsolatok biztonságának biztosítása érdekében. A 2. HoloLens a tűzfal mindig engedélyezve van, és nem lehet programozott módon vagy a felhasználói felületen keresztül letiltani.

A mobil ügyfelek távelérési és kapcsolati adatvédelme az [UWP VPN beépülő modul platformján keresztül biztosítható.](/uwp/api/Windows.Networking.Vpn?view=winrt-19041) A külső VPN-szolgáltatók saját beépülő modulokat hozhatnak létre a WinRT API-k használatával, amelyek az AppContainer-védőfalon belül fognak futni, így kiküszöbölve a rendszerszintű illesztőprogramok írásával gyakran járó összetettséget és problémákat.
