---
title: Ossza meg HoloLens több felhasználóval
description: Konfigurálhatja úgy a HoloLens, hogy több Azure Active Directory, vagy több felhasználó osztozik egy fiókon.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3acd2665e93e44bce2c5dad467c825dc768bfed
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428845"
---
# <a name="share-your-hololens-with-multiple-people"></a>Ossza meg HoloLens több felhasználóval

## <a name="overview"></a>Áttekintés
A vállalatok gyakran fektetnek be számos megosztott HoloLens eszközbe. Az egyéni HoloLens rugalmasan használhatja a táblát. Az alábbi példa néhány többfelhasználós élményt mutat be: 

- A Dynamics 365-útmutatókat és a felhasználók által a szükséges Wi-Fi-módosításokhoz szükséges Wi-Fi-alkalmazást megnyitó, Dynamics 36 Gépház 5-útmutatókkal rendelkező eszközök esetében azonban engedélyezve van a Page Gépház Visibility szabályzat a Gépház-alkalmazásban elérhető oldal mennyiségének korlátozására.
- A Remote Assisthez és a más vállalatoknak bérelt üzletági alkalmazáshoz használható eszközök. Ezek az eszközök olyan kioszkokkal is vannak, amelyek csak az alkalmazást és a Remote Assist eszközt tartalmazzák. A WDAC használatával az alkalmazás Gépház és a Microsoft Edge nem indul el. A kölcsönzés tartalmazza az USB-C akkumulátort, amely több műszakban is teljes tékban tartja az eszközöket.
- Minden eszköz be van állítva az Autopilothoz, és letölti az összes vállalati alkalmazást. Több különböző kioszkprofilt is beállított, amelyek különböző Azure AD-csoportokat céloznak meg. Minden felhasználó FIDO2 HoloLens kulcsokkal jelentkezik be a saját Azure AD-fiókjába, és személyre szabott élményt nyújt.



## <a name="share-with-multiple-people-each-using-their-own-account"></a>Megosztás több felhasználóval, mindegyiket a saját fiókjával

**Előfeltétel:** HoloLens eszközön az 1803 Windows 10 vagy újabb verziónak kell futnia.  HoloLens (1. generációs) verzióra is frissíteni kell a [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

Ha saját fiókokat Azure Active Directory (Azure AD) használ, egyszerre több felhasználó is megtarthatja saját felhasználói beállításait és felhasználói adatait az eszközön.

Annak érdekében, hogy többen is használják a saját fiókjukat a HoloLens, az alábbi lépésekkel konfigurálhatja:

1. Győződjön meg arról, hogy az eszköz Windows 10 1803-as vagy újabb verzióját futtatja.
   > [!IMPORTANT]
   > Ha egy HoloLens (1. generációs) eszközt használ, frissítse az eszközt a [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)
1. Az eszköz beállításakor válassza  a Saját munkahelyi vagy iskolai tulajdonú lehetőséget, és jelentkezzen be egy Azure AD-fiókkal.
1. A beállítás befejezése után győződjön meg arról, hogy a **fiókbeállítások**(a  >  **Gépház-fiókok**) tartalmazzák az **Egyéb felhasználók beállítást.**

A HoloLens felhasználó a következő lépéseket követi:

1. Ha egy másik felhasználó már használja az eszközt, válasszon az alábbi lehetőségek közül:
   - A készenléti állapotba való visszatéréshez nyomja le egyszer a bekapcsológombot, majd a zárolási képernyőre való visszatéréshez nyomja le újra a bekapcsológombot
   - HoloLens 2 felhasználó választhatja ki a felhasználó csempéjét a Start menü az aktuális felhasználó kijelentkeztetése érdekében.

1. Jelentkezzen be az eszközre az Azure AD-fiók hitelesítő adataival.  
    Ha első alkalommal használja az eszközt, a saját szemére [kell](hololens-calibration.md) HoloLens az eszközt.

Az eszköz felhasználóinak listájáért vagy egy felhasználó eszközről való eltávolításához a Fiók **Gépház**  >    >  **felhasználók oldalon.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Megosztás több felhasználóval, mind ugyanazt a fiókot használva

Több felhasználó is megoszthat egy HoloLens eszközt egyetlen felhasználói fiók használatával.

**A HoloLens 2.** időpontban, amikor egy új felhasználó először helyezi a fejére az eszközt (miközben ugyanazt a fiókot tartja bejelentkezve), az eszköz arra kéri az új felhasználót, hogy gyorsan állítsa be és szabja személyre a megtekintési élményt. Az eszköz tárolhatja a hőmérsékleti információkat, így a jövőben automatikusan optimalizálhatja az egyes felhasználók megtekintési élményének minőségét és kényelmi élményét. A felhasználóknak nem kell újra bekalkenni az eszközt.

**A HoloLens (1. generációs)** felhasználóktól a fiókot megosztó felhasználóknak újra kell kérniük az újraszámítást a Gépház alkalmazásban.  További információ a [beszibrálásról.](hololens-calibration.md)