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
# <a name="connect-to-cellular-and-5g"></a>Csatlakozás mobilhálózathoz és 5G-hez

A HoloLens 2 két módszert támogat a mobilhálózathoz és az 5G-hálózatokhoz való csatlakozáshoz:

- A mobilhálózat által biztosított alkalmi Wi-Fi-hálózat, amelyet gyakran "elérési pontnak" is nevezik
- Usb-C-csatlakoztatott eszközök korlátozott támogatása

## <a name="hotspot-wifi"></a>Elérési pont (Wi-Fi)

A legtöbb mobilkapcsolati igény egy elérési ponttal is kielégítható. A HoloLens 2 Wi-Fi támogatja a 802.11ac-t, amely a leggyakoribb esetekben szükséges sávszélességre és késésre vonatkozó követelményeket biztosít. A Wi-Fi kábel nélküli, és a legtöbb mobilhálózati eszközzel kompatibilis.

### <a name="connecting-to-a-hotspot"></a>Kapcsolódás elérési ponthoz

1. A hozzáférési pont módjának engedélyezéséről az eszköz használati útmutatója alapján tájékozódjon.
1. Engedélyezze a elérési pont módot, és nevezze el a hálózatot, valamint egy ismert jelszót.
1. A HoloLens 2 Hálózati beállítások között keresse meg a 2. lépésben létrehozott Wi-Fi-hálózatot, és csatlakozzon hozzá.

## <a name="usb-c-tethering"></a>USB-C Tethering

Az USB-C-tethering alacsonyabb késést biztosít az olyan speciális számítási feladatok esetében, amelyekre szükség van. [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)például kihasználhatja a internetezést. Vegye figyelembe, hogy a internetezéshez kábelre van szükség a mobileszközök és a HoloLens között, és a tetheringet korlátozott számú eszköz támogatja.

### <a name="usb-c-compatibility"></a>USB-C-kompatibilitás

A Windows Holographic 2004-es és újabb verzióiban korlátozott számú olyan eszköz használható, amely Ethernet-adapterként működik.

Az ethernet-adapterként nem jelenítő eszközöknek támogatniuk kell az általános Microsoft [RNDIS-illesztőprogramot.](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) De csak korlátozott számú eszköz kompatibilis a HoloLens 2-nal. Az általános Microsoft RNDIS-illesztőprogram támogatásával kapcsolatos részletekért forduljon az eszköz gyártójához.

Azok az eszközök, amelyek nem kompatibilisek az RNDIS-rel, vagy illesztőprogram vagy alkalmazás telepítését igénylik, nem támogatottak.

Bár a Microsoft nem tartja fenn a kompatibilis eszközök listáját, a témáról itt is folyik közösségi [vitafórum.](https://aka.ms/HLCommunityCell)

### <a name="connecting-to-a-tethered-device"></a>Csatlakozás egy összekapcsolt eszközhöz

1. Az USB-kapcsolaton keresztüli adatmegosztás engedélyezésével kapcsolatos információkért tekintse meg az eszköz kézikönyvét. Ezt a beállítást gyakran "USB Tethering", "Adatmegosztás" vagy "USB Modem" néven is nevezik.
1. Adatmegosztás engedélyezése USB-kapcsolaton keresztül.
1. Csatlakoztassa az eszközt a HoloLens USB-C portjához.
1. A HoloLens 2 hálózati beállításaiban az eszköz automatikusan Ethernet-kapcsolatként jelenik meg.
