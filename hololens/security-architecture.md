---
title: HoloLens biztonsági architektúra
description: Biztonsági architektúra
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: biztonság, hololens, hololens 2, hololens2 biztonság, biztonsági áttekintés, biztonsági architektúra, architektúra, hololens 2 architektúra
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379543"
---
# <a name="security-overview-and-architecture"></a>Biztonsági áttekintés és architektúra

A HoloLens 2 biztonsági architektúrát az egész világból úgy tervezték meg és alakítottuk ki, hogy ne legyen régebbi biztonsági probléma, és minimális támadási felületet hozzon létre. Ez az új, innovatív architektúra biztonságos tárolási helyeket és fejlett biztonsági elemeket kínál olyan mechanizmusokkal, amelyek képesek védeni az operációs rendszereket a potenciális fenyegetésektől és biztonsági résektől.

A HoloLens 2 a hardver, a szoftver, a hálózat és a szolgáltatások kombinálása által biztosítja a teljes biztonságot, miközben optimális felhasználói élményt nyújt a felhasználónak. A HoloLens 2-ben a biztonsági funkciók nagy része automatikusan bekapcsol, így minimálisra van szükség az operációs rendszer helyes beállításához és konfigurálásához.

A Windows HoloLens 2 és az operációs rendszer architektúrája az alábbi innovatív biztonsági funkciókat kínálja:

  * **Állapotok elkülönítése** és elkülönítése: Ez az új architektúra megvédi a HoloLens 2 operációs rendszer kritikus részeit a változásoktól, például az alapvető operációs rendszer megbízható állapotba való rendszerindításához szükségeseket. Az elkülönítési technológia arra használható, hogy a nem megbízható alkalmazásokat a védőfalon belül korlátozzák, így azok ne tudják befolyásolni a rendszer biztonságát. A teljes operációs rendszer biztonságos szakaszokra van osztva, amelyek mindegyikét különböző biztonsági technológiák kombinációja védi.
  
  * **Adatvédelem:** Ha egy felhasználó eszköze elveszett vagy ellopták, a HoloLens 2 megakadályozza, hogy jogosulatlan alkalmazások bizalmas adatokat olvassanak be az adatok BitLocker-titkosításának használatával. 
  
  * **Jelszóval** nem rendelkező operációs rendszer: A régebbi, jelszóalapú operációs rendszerek akaratlanul is adathalászati fenyegetéseknek tehetnek ki felhasználókat, és gyakran felelősek a feltört fiókokért. Windows Holographic for Business megszünteti a jelszavak használatát az MSA- és Az Azure AD-bejelentkezéshez, és megerősíti a felhasználói identitások védelmét Windows Hello™ FIDO2-bejelentkezéssel. 
  
    > [!NOTE]
    > A FIDO2 támogatásához az eszköznek az 19041-es vagy újabb builden kell lennie. 

  * **Hálózati biztonság:** A HoloLens 2 továbbfejlesztett protokollok és alapértelmezett beállítások révén növeli a felhasználók hálózati biztonságát.
