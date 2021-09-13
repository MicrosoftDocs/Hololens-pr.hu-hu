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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036235"
---
# <a name="network-security"></a>Hálózati biztonság

## <a name="network-protocols"></a>Hálózati protokollok

Az elavult NetBIOS-t (alapszintű hálózati bemeneti/kimeneti rendszert) széles körben használták a múltban LAN-forgatókönyvekben – gyakran a számítógép és a megosztott mappák névfeloldásához. Idővel azonban a NetBIOS ki volt téve a többszörös támadásoknak, és a relevanciája más biztonságosabb protokollok miatt csökkent. A biztonsági rés megszüntetéséhez a 2. HoloLens eltávolítja a NetBIOS-hez kapcsolódó kódot az operációs rendszerből.

A TLS (Transport Layer Security) protokollok folyamatosan fejlődnek. Annak érdekében, hogy lépést tartsunk az ezen a területen feltárt különböző biztonsági résekkel, a számítástechnikai iparág egyre újabb és hatékonyabb verziókban is elérhető. Mivel az összes kiszolgálótelepítésnek szüksége van az új TLS protokollverziók alkalmazásához, egy tartalék mechanizmus valósítható meg, amely lehetővé teszi, hogy az ügyfél és a különböző alapértelmezett protokollverziók kiszolgálói továbbra is kommunikáljanak az átmeneti időszak alatt.

## <a name="secure-connectivity"></a>Biztonságos kapcsolat 

A Windows Defender tűzfal kritikus fontosságú funkciókat biztosít az eszközkapcsolatok biztonságának biztosítása érdekében. A HoloLens 2 esetén a tűzfal mindig engedélyezve van, és nem lehet programozott módon vagy a felhasználói felületen keresztül letiltani.

A távoli hozzáférés és a mobil ügyfelek kapcsolati adatvédelme az [UWP VPN beépülő modul platformján keresztül biztosítható.](/uwp/api/Windows.Networking.Vpn?view=winrt-19041) A külső VPN-szolgáltatók saját beépülő modulokat hozhatnak létre a WinRT API-k használatával, amelyek az AppContainer-védőfalon belül fognak futni, így kiküszöbölve a rendszerszintű illesztőprogramok írásával kapcsolatos összetettséget és problémákat.
