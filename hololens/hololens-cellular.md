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
# <a name="connect-to-cellular-and-5g"></a>Csatlakozás mobilhálózathoz és 5G-hez

HoloLens 2. kapcsolat két módszert támogat a mobilhálózathoz és az 5G-hálózatokhoz való csatlakozáshoz:

- A mobilhálózat által biztosított alkalmi Wi-Fi-hálózat, amelyet gyakran "elérési pontnak" is nevezik
- Korlátozott támogatás USB-C-hez csatlakoztatott eszközökhöz

## <a name="hotspot-wifi"></a>Elérési pont (Wi-Fi)

A legtöbb mobilkapcsolati igény egy elérési ponttal is kielégítható. HoloLens 2. Wi-Fi támogatja a 802.11ac-et, amely a leggyakoribb esetekben szükséges sávszélesség- és késési követelményeket biztosítja. A Wi-Fi kábel nélküli, és a legtöbb mobilhálózati eszközzel kompatibilis.

### <a name="connecting-to-a-hotspot"></a>Kapcsolódás elérési ponthoz

1. Tekintse meg az eszköz használati útmutatóját a elérési pont módjának engedélyezéséről.
1. Engedélyezze a elérési pont módot, és nevezze el a hálózatot, valamint egy ismert jelszót.
1. A HoloLens 2. lépésben található Hálózati beállítások között keresse meg a 2. lépésben létrehozott Wi-Fi-hálózatot, és csatlakozzon hozzá.

## <a name="usb-c-tethering"></a>USB-C Tethering

Az USB-C-internetezés alacsonyabb késést biztosít az olyan speciális számítási feladatoknál, amelyekhez szükség van rá. [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)például előnyös lehet a tethering. Vegye figyelembe, hogy a internetezéshez kábelre van szükség a mobileszközök és a HoloLens között, és a internetezést korlátozott számú eszköz támogatja.

### <a name="usb-c-compatibility"></a>USB-C-kompatibilitás

A Holographic 2004-es és újabb verzióiban korlátozott számú, Ethernet-adapterként Windows eszköz használható.

Az Ethernet-adapterként nem jelenítő eszközöknek támogatniuk kell az általános Microsoft [RNDIS-illesztőprogramot.](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Ezen eszközök közül azonban csak korlátozott számú kompatibilis a HoloLens 2-es verzióval. Az általános Microsoft RNDIS-illesztőprogram támogatásával kapcsolatos részletekért forduljon az eszköz gyártójához.

Azok az eszközök, amelyek nem kompatibilisek RNDIS-rel, vagy illesztőprogram vagy alkalmazás telepítését igénylik, nem támogatottak.

Bár a Microsoft nem tartja fenn a kompatibilis eszközök listáját, a témáról itt tartunk közösségi [vitafórumot.](https://aka.ms/HLCommunityCell)

### <a name="connecting-to-a-tethered-device"></a>Csatlakozás egy összekapcsolt eszközhöz

1. Az USB-adatmegosztás engedélyezésével kapcsolatos információkért tekintse meg az eszköz használati útmutatóját. Ezt a beállítást gyakran "USB Tetheringnek", "Adatmegosztásnak" vagy "USB modemnek" is nevezik.
1. Adatmegosztás engedélyezése USB-n keresztül.
1. Csatlakozás az eszközt a HoloLens USB-C-portra.
1. A HoloLens 2. hálózati beállításnál az eszköz automatikusan Ethernet-kapcsolatként jelenik meg.
