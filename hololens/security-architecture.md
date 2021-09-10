---
title: HoloLens architektúra
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428970"
---
# <a name="security-overview-and-architecture"></a>Biztonsági áttekintés és architektúra

A HoloLens 2. biztonsági architektúrát úgy tervezték és alakítottuk ki, hogy az az egész világra vonatkozó biztonsági problémáktól mentes legyen, és minimális támadási felületet hozzon létre. Ez az új, innovatív architektúra biztonságos tárolási helyeket és fejlett biztonsági elemeket kínál olyan mechanizmusokkal, amelyek képesek védeni az operációs rendszereket a lehetséges fenyegetésekkel és biztonsági résekkel szemben.

HoloLens 2. megoldás hardvereket, szoftvereket, hálózatokat és szolgáltatásokat kombinál a teljes biztonság biztosításához, miközben optimális felhasználói élményt nyújt a felhasználónak. A 2. HoloLens a biztonsági funkciók nagy része automatikusan bekapcsol, így minimálisra van szükség az operációs rendszer helyes beállításához és konfigurálásához.

Windows HoloLens 2. architektúra és az operációs rendszer architektúrája a következő innovatív biztonsági funkciókat kínálja:

  * **Állapotok elkülönítése** és elkülönítése: Ez az új architektúra az HoloLens 2 operációs rendszer kritikus fontosságú részeit védi a változásoktól, például az alapvető operációs rendszer megbízható állapotba való rendszerindításához szükségeseket. Az elkülönítési technológia arra használható, hogy a nem megbízható alkalmazásokat a védőfalon belül korlátozzák, így azok ne tudják befolyásolni a rendszer biztonságát. A teljes operációs rendszer biztonságos szakaszokra van szegmentálva, amelyek mindegyikét különböző biztonsági technológiák kombinációja védi.
  
  * **Adatvédelem:** Ha egy felhasználó eszköze elveszett vagy ellopták, a HoloLens 2 a BitLocker adattitkosítással megakadályozza, hogy jogosulatlan alkalmazások bizalmas adatokat olvassanak be. 
  
  * **Jelszóval** nem rendelkező operációs rendszer: A régebbi, jelszóalapú operációs rendszerek akaratlanul is adathalászati fenyegetéseknek tehetnek ki felhasználókat, és gyakran felelősek a feltört fiókokért. Windows Holographic for Business megszünteti a jelszavak használatát az MSA- és Az Azure AD-bejelentkezéshez, és megerősíti a felhasználói identitások védelmét az Windows Hello™ FIDO2-bejelentkezéssel. 
  
    > [!NOTE]
    > A FIDO2 támogatásához az eszköznek az 19041-es vagy újabb builden kell lennie. 

  * **Hálózati biztonság:** HoloLens 2. frissítés továbbfejlesztett protokollok és alapértelmezett beállítások révén növeli a hálózati biztonságot a felhasználók számára.
