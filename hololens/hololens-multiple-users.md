---
title: A HoloLens megosztása több felhasználóval
description: A HoloLenst konfigurálhatja úgy, hogy több fiókkal Azure Active Directory, vagy több, egyetlen fiókot használó felhasználóval osztva.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378120"
---
# <a name="share-your-hololens-with-multiple-people"></a>A HoloLens megosztása több felhasználóval

Gyakori, hogy egy HoloLenst sokak között osztunk meg, vagy sokak osztoznak HoloLens-eszközökön.  Ez a cikk az eszközök megosztásának különböző módjait ismerteti.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Megosztás több felhasználóval, mindegyiket a saját fiókjával

**Előfeltétel:** A HoloLens-eszköznek Windows 10 1803-as vagy újabb verziójú verziójának kell futnia.  A HoloLenst (1. generációs) is frissíteni kell a [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

Amikor saját fiókokat Azure Active Directory (Azure AD) használ, egyszerre több felhasználó is megtarthatja saját felhasználói beállításait és felhasználói adatait az eszközön.

Annak érdekében, hogy többen is használják a saját fiókjukat a HoloLensben, az alábbi lépésekkel konfigurálhatja:

1. Győződjön meg arról, hogy az eszköz Windows 10 1803-as vagy újabb verzióját használja.
   > [!IMPORTANT]
   > Ha HoloLens-eszközt (1. generációs) használ, frissítse az eszközt a [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)
1. Az eszköz beállításakor válassza a Saját munkahelyi **vagy** iskolai tulajdonú lehetőséget, és jelentkezzen be egy Azure AD-fiókkal.
1. A beállítás befejezése után győződjön megarról, hogy a fiókbeállítások  >  **(Beállításfiókok)** tartalmazzák az **Egyéb felhasználók beállítást.**

A HoloLens használata érdekében minden felhasználó az alábbi lépéseket követi:

1. Ha egy másik felhasználó már használja az eszközt, tegye a következők egyikét:
   - A készenléti állapotba való visszatéréshez nyomja le egyszer a bekapcsológombot, majd a zárolási képernyőre való visszatéréshez nyomja le újra a bekapcsológombot
   - A HoloLens 2-felhasználók a felhasználó csempéjét Start menü aktuális felhasználó kijelentkeztetése érdekében.

1. Jelentkezzen be az eszközre az Azure AD-fiók hitelesítő adataival.  
    Ha első alkalommal használja az eszközt, a [saját](hololens-calibration.md) szemére kell állítania a HoloLenst.

Az eszköz felhasználóinak listáját úgy láthatja, hogy eltávolít egy felhasználót az eszközről, ha a Beállítások fiókok  >    >  **– Egyéb felhasználók lehetőséget használja.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Megosztás több felhasználóval, mind ugyanazt a fiókot használva

Egy HoloLens-eszközt több felhasználó is megoszthat egyetlen felhasználói fiók használatával.

**A HoloLens 2-ben,** amikor egy új felhasználó először helyezi a fejére az eszközt (miközben ugyanazt a fiókot tartja bejelentkezve), az eszköz arra kéri az új felhasználót, hogy gyorsan állítsa be és szabja személyre a megtekintési élményt. Az eszköz tárolhatja a hőmérsékleti információkat, így a jövőben automatikusan optimalizálhatja az egyes felhasználók megtekintési élményének minőségét és kényelmi élményét. A felhasználóknak nem kell újra bekalkenni az eszközt.

A fiókot megosztó **HoloLens- (1. generációs)** felhasználóknak újra kell kérniük az újraszámítást a Beállítások alkalmazásban.  További információ a [beszibrálásról.](hololens-calibration.md)
