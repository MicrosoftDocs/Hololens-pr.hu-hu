---
title: A HoloLens megosztása több felhasználóval
description: Konfigurálhatja úgy a HoloLens, hogy több fiókkal Azure Active Directory, vagy több, egyetlen fiókot használó felhasználóval osztják meg.
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
ms.openlocfilehash: 821ef2d17531226177e508b1428af82012c16406e9fbce3ed1a5617c767adfe8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663067"
---
# <a name="share-your-hololens-with-multiple-people"></a>A HoloLens megosztása több felhasználóval

Gyakori, hogy egy közös HoloLens sokak között, vagy sokak osztoznak egy sor HoloLens eszközön.  Ez a cikk az eszközök megosztásának különböző módjait ismerteti.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Megosztás több felhasználóval, mindegyiket a saját fiókjával

**Előfeltétel:** A HoloLens 1803-as vagy újabb Windows 10 kell futnia.  HoloLens (1. generációs) verzióra is frissíteni kell a [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

Amikor saját fiókokat Azure Active Directory (Azure AD) használ, több felhasználó is megtarthatja saját felhasználói beállításait és felhasználói adatait az eszközön.

Annak érdekében, hogy többen is használják a saját fiókjukat a HoloLens, az alábbi lépésekkel konfigurálhatja:

1. Győződjön meg arról, hogy az eszköz Windows 10 1803-as vagy újabb verzióval fut.
   > [!IMPORTANT]
   > Ha egy HoloLens (1. generációs) eszközt használ, frissítse az eszközt a [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)
1. Az eszköz beállításakor válassza a Saját munkahelyi **vagy** iskolai tulajdonú lehetőséget, és jelentkezzen be egy Azure AD-fiókkal.
1. A beállítás befejezése után győződjön meg arról, hogy a **fiókbeállítások**(a  >  **Gépház-fiókok**) tartalmazzák az **Egyéb felhasználók beállítást.**

A HoloLens felhasználó a következő lépéseket követi:

1. Ha egy másik felhasználó már használja az eszközt, tegye a következők egyikét:
   - A készenléti állapotba való visszatéréshez nyomja le egyszer a bekapcsológombot, majd a zárolási képernyőre való visszatéréshez nyomja le újra a bekapcsológombot
   - HoloLens 2 felhasználó választhatja ki a felhasználó csempéjét a Start menü az aktuális felhasználó kijelentkeztetése érdekében.

1. Jelentkezzen be az eszközre az Azure AD-fiók hitelesítő adataival.  
    Ha első alkalommal használja az eszközt, a saját szemére [kell](hololens-calibration.md) HoloLens az eszközt.

Az eszköz felhasználóinak listájáért vagy egy felhasználó eszközről való eltávolításához lásd: Gépház  >    >  **felhasználók.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Megosztás több felhasználóval, mind ugyanazt a fiókot használva

Több felhasználó is megoszthat egy HoloLens eszközt egyetlen felhasználói fiók használatával.

**A HoloLens 2.** időpontban, amikor egy új felhasználó először helyezi a fejére az eszközt (miközben ugyanazt a fiókot tartja bejelentkezve), az eszköz arra kéri az új felhasználót, hogy gyorsan állítsa be és szabja személyre a megtekintési élményt. Az eszköz tárolhatja a berendezés adatait, így a jövőben automatikusan optimalizálhatja az egyes felhasználók megtekintési élményének minőségét és kényelmi élményét. A felhasználóknak nem kell újra bekalkenni az eszközt.

**A HoloLens (1. generációs)** felhasználóktól a fiókot megosztó felhasználóknak újra kell kérniük az újraszámítást a Gépház alkalmazásban.  További információ a [beszibrációról.](hololens-calibration.md)
