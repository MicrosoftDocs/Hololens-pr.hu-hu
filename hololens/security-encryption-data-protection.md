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
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639369"
---
# <a name="encryption-and-data-protection"></a>Titkosítás és adatvédelem

A titkosítás és az adatvédelem megvédi az adatokat az eszköz ellopása vagy ellopása esetén, és megakadályozza, hogy jogosulatlan alkalmazások hozzáférjenek a bizalmas adatokhoz.

## <a name="bitlocker-device-encryption"></a>BitLocker-eszköztitkosítás

A BitLocker egy teljes kötetre vonatkozó titkosítási szolgáltatás, amely a csak olvasási (RO) adathordozók és az írható adathordozók adatvédelmének védelmét védi.  A kezdetektől hatékony védelmet biztosít az adatokhoz való jogosulatlan hozzáférés ellen offline támadások során. HoloLens 2. beállítás alapértelmezés szerint engedélyezi a Bitlocker Eszköztitkosítás (BDE) számára az adatok védelmét az eszközhöz való jogosulatlan fizikai hozzáférés ellen. A Microsoft folyamatosan fejleszt a jövő igényeinek megfelelően, és folyamatosan fejleszti ezt a technológiát.

A BDE egy adatvédelmi funkció, amely AES-XTS-256 titkosítást alkalmaz az eszköz állapotokkal elválasztott elrendezésében található összes köteten. A BDE eszközszintű titkosítást biztosít az állapottól elkülönülő elrendezésben. A BitLocker Eszköztitkosítás automatikusan engedélyezve van az operációs rendszeren és rögzített adatköteten, és még a rendszergazdák sem tudják kikapcsolni, hogy az eszköz mindig védve legyen.

A BDE titkosítási kulcsok ezután a bináris fájlok és az eszköz rendszerindításához szükséges adatok transzparens visszafejtéséhez használhatók. Az operációs rendszer kötetének zárolásának feloldása és a rendszer rendszerindítása közben más kötetek is elérhetővé válnak az automatikus feloldási védő kötetspecifikus verziójával. A felhasználói adatok védelme érdekében más védők nem érhetők el, és a meghajtó csak ugyanazon az eszközön oldható fel. A rendszer az első rendszerindítástól kezdve azonnal alkalmazza és érvényesíti a csak olvasási (RO) kényszerítéseket a szükséges kötetek esetén. A 2. HoloLens időszakban nincs szükség a Bitlocker helyreállítási kulcsára.

## <a name="azure-integration"></a>Azure-integráció 

HoloLens 2. lehetőség az ügyfelek eszközeik Azure-szolgáltatásokkal való integrálására. A HoloLens 2 eszköz és az Azure közötti kommunikáció TLS (Transport Layer Security) protokollt használ az közötte és a felhőszolgáltatások között áthaladó adatok védelmére, ami erős hitelesítést, üzenet-adatvédelmet és integritást biztosít. Minden Azure-szolgáltatás teljes mértékben támogatja a TLS 1.2-t, és minden olyan szolgáltatást, ahol az ügyfelek csak a TLS 1.2-t használják, csak tLS 1.2-forgalmat fogadnak el. Az átvitel közbeni adatok azure-beli titkosítási szabványait az [Azure-titkosítás áttekintésében olvashatja el.](/azure/security/fundamentals/encryption-overview) Az Azure-beli adatbiztonsággal és -titkosítással kapcsolatos ajánlott eljárásokról az [Azure dokumentációjában talál további információt.](/azure/security/fundamentals/data-encryption-best-practices) 

OneDrive a HoloLens 2.-essel való felhőintegráció egyik példája, amely automatikus feltöltési funkcióval rendelkezik, amelyben a fájlok és dokumentumok automatikusan feltölthetők a felhőbe, amikor csatlakoznak az internethez. A fájlok automatikus szinkronizálásának szüneteltetés nem állítható ki szabályzaton keresztül, de közvetlenül konfigurálható a felhasználói felületről. 
