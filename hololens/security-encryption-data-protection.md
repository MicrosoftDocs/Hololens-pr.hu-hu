---
title: Titkosítás és adatvédelem
description: További információ a titkosításról és az adatvédelemről HoloLens 2 eszközön, beleértve a BitLocker és az Azure-integrációt.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: biztonság, hololens, titkosítás, adatvédelem, BitLocker eszköz, BitLocker, bitlocker, bitlocker titkosítás, azure-integráció,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e156fc21bfd1541dd8718a7349e7ba82b45576be
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428310"
---
# <a name="encryption-and-data-protection"></a>Titkosítás és adatvédelem

A titkosítás és az adatvédelem megvédi az adatokat az eszköz ellopása vagy ellopása esetén, és megakadályozza, hogy jogosulatlan alkalmazások hozzáférjenek a bizalmas adatokhoz.

## <a name="bitlocker-device-encryption"></a>BitLocker-eszköztitkosítás

A BitLocker egy teljes kötetetitkosítási szolgáltatás, amely a csak olvasható (RO) adathordozók integritásának és az írható adathordozók adatvédelmének védelmét teszi lehetővé.  A kezdetektől hatékony védelmet biztosít az adatokhoz való jogosulatlan hozzáférés ellen offline támadások esetén. HoloLens 2. beállítás alapértelmezés szerint engedélyezi a Bitlocker Eszköztitkosítás (BDE) számára az adatok védelmét az eszközhöz való jogosulatlan fizikai hozzáféréssel ellen. A Microsoft folyamatosan fejleszti a jövő igényeit, és folyamatosan fejleszti ezt a technológiát.

A BDE egy adatvédelmi funkció, amely AES-XTS-256 titkosítást alkalmaz az eszköz állapotokkal elválasztott elrendezésében található összes köteten. A BDE eszközszintű titkosítást biztosít az állapottól elválasztott elrendezésben. A BitLocker Eszköztitkosítás automatikusan engedélyezve van az operációs rendszeren és a rögzített adatköteten, és még a rendszergazdák sem tudják kikapcsolni, hogy az eszköz mindig védve legyen.

A BDE titkosítási kulcsok ezután a bináris fájlok és az eszköz rendszerindításához szükséges adatok transzparens visszafejtéséhez használhatók. Az operációs rendszer kötetének zárolásának feloldása és a rendszerindítás közben más kötetek az automatikus zárolás-feloldó védő kötetspecifikus verziójával válnak elérhetővé. A felhasználói adatok védelme érdekében más védők nem érhetők el, és a meghajtó csak ugyanazon az eszközön oldható fel. A csak olvasási (RO) kényszerítés a szükséges kötetek esetén azonnal érvényesül, az első rendszerindítástól kezdve. A Bitlocker helyreállítási kulcsra a 2. HoloLens van szükség.

## <a name="azure-integration"></a>Azure-integráció 

HoloLens 2. módszer lehetővé teszi, hogy az ügyfelek integrálják eszközeiket az Azure-szolgáltatásokkal. A 2. HoloLens-eszközök és az Azure közötti kommunikáció TLS (Transport Layer Security) protokollt használ a közöttük és a felhőszolgáltatások között áthaladó adatok védelmére, ami erős hitelesítést, üzenet-adatvédelmet és integritást biztosít. Minden Azure-szolgáltatás teljes mértékben támogatja a TLS 1.2-t, és minden olyan szolgáltatást, amelyben az ügyfelek csak a TLS 1.2-t használják, csak a TLS 1.2-forgalmat fogadják el. Az Azure átvitel közbeni adattitkosítási szabványait az [Azure-titkosítás áttekintésében olvashatja el.](/azure/security/fundamentals/encryption-overview) Az Azure adatbiztonsággal és -titkosítással kapcsolatos ajánlott eljárásait az [Azure dokumentációjában találhatja](/azure/security/fundamentals/data-encryption-best-practices)meg. 

OneDrive a HoloLens 2-es megoldással való felhőintegráció egyik példája, amely automatikus feltöltési funkcióval rendelkezik, amelyben a fájlok és dokumentumok automatikusan feltölthetők a felhőbe, amikor csatlakoznak az internethez. A fájlok automatikus szinkronizálásának szüneteltetés nem állítható ki szabályzaton keresztül, de közvetlenül konfigurálható a felhasználói felületről. 
