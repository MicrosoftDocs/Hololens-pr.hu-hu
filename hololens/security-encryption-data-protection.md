---
title: Titkosítás és adatvédelem
description: Tudnivalók a HoloLens 2-eszközökön való titkosításról és adatvédelemről, beleértve a BitLockert és az Azure-integrációt.
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
ms.openlocfilehash: ebe1d072f36cdf4ad9b3543882e61fa2ed4a0300
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379542"
---
# <a name="encryption-and-data-protection"></a>Titkosítás és adatvédelem

A titkosítás és az adatvédelem megvédi az adatokat az eszköz ellopása vagy ellopása esetén, és megakadályozza, hogy jogosulatlan alkalmazások hozzáférjenek a bizalmas adatokhoz.

## <a name="bitlocker-device-encryption"></a>BitLocker-eszköztitkosítás

A BitLocker egy teljes kötetre vonatkozó titkosítási szolgáltatás, amely a csak olvasási (RO) adathordozók és az írható adathordozók adatvédelmi védelmét védi.  A kezdetektől hatékony védelmet biztosít az adatokhoz való jogosulatlan hozzáférés ellen offline támadások során. A HoloLens 2 alapértelmezés szerint engedélyezi a Bitlocker Eszköztitkosítás (BDE) számára az adatok védelmét az eszközhöz való jogosulatlan fizikai hozzáférés ellen. A Microsoft folyamatosan a jövő igényeinek megfelelően fejleszt, és folyamatosan fejleszti ezt a technológiát.

A BDE egy adatvédelmi funkció, amely AES-XTS-256 titkosítást alkalmaz az eszköz állapotokkal elválasztott elrendezésében található összes köteten. A BDE eszközszintű titkosítást biztosít az állapottól elválasztott elrendezésben. A BitLocker Eszköztitkosítás automatikusan engedélyezve van az operációs rendszeren és rögzített adatköteten, és még a rendszergazdák sem tudják kikapcsolni, hogy az eszköz mindig védve legyen.

A BDE titkosítási kulcsok ezután a bináris fájlok és az eszköz rendszerindításához szükséges adatok transzparens visszafejtéséhez használhatók. Az operációs rendszer kötetének zárolásának feloldása és a rendszerindítás közben más kötetek az automatikus zárolás-feloldó védő kötetspecifikus verziójával válnak elérhetővé. A felhasználói adatok védelme érdekében más védők nem érhetők el, és a meghajtó csak ugyanazon az eszközön oldható fel. A rendszer az első rendszerindítástól kezdve azonnal alkalmazza és érvényesíti a csak olvasási (RO) kényszerítéseket a szükséges kötetek esetén. A Bitlocker helyreállítási kulcsra nincs szükség a HoloLens 2 életciklusában.

## <a name="azure-integration"></a>Azure-integráció 

A HoloLens 2 lehetővé teszi, hogy az ügyfelek integrálják eszközeiket az Azure-szolgáltatásokkal. A HoloLens 2-eszközök és az Azure közötti kommunikáció TLS (Transport Layer Security) protokollt használ az közötte és a felhőszolgáltatások között áthaladó adatok védelmére, ami erős hitelesítést, üzenet-adatvédelmet és integritást biztosít. Minden Azure-szolgáltatás teljes mértékben támogatja a TLS 1.2-t, és minden olyan szolgáltatást, ahol az ügyfelek csak a TLS 1.2-t használják, csak tLS 1.2-forgalmat fogadnak el. Az átvitel közbeni adatok azure-beli titkosítási szabványait az [Azure-titkosítás áttekintésében olvashatja el.](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview) Az Azure-beli adatbiztonsággal és -titkosítással kapcsolatos ajánlott eljárásokról az [Azure dokumentációjában talál további információt.](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices) 

A OneDrive, amely a HoloLens 2-höz való felhőintegráció egyik példája, automatikus feltöltési funkcióval rendelkezik, amelyben a fájlok és dokumentumok automatikusan feltölthetők a felhőbe, amikor csatlakoznak az internethez. A fájlok automatikus szinkronizálásának szüneteltetés nem állítható ki szabályzaton keresztül, de közvetlenül konfigurálható a felhasználói felületről. 
