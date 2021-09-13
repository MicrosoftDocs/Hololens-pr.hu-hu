---
title: A HoloLens megosztása több felhasználóval
description: Konfigurálhatja úgy a HoloLens, hogy több fiókkal Azure Active Directory, vagy több, egyetlen fiókot használó felhasználóval osztják meg.
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032908"
---
# <a name="share-your-hololens-with-multiple-people"></a>A HoloLens megosztása több felhasználóval

## <a name="overview"></a>Áttekintés
A vállalatok gyakran fektetnek be számos megosztott HoloLens eszközbe. Az egyéni HoloLens függően rugalmasan használhatja a teljes táblát. Az alábbi példa néhány többfelhasználós élményt mutat be: 

- Azok az eszközök, amelyek díj ellenében Dynamics 365-útmutatókat tartalmaznak, és lehetővé teszik az alkalmazottak számára a Gépház-alkalmazás megnyitását az Wi-Fi szükséges módosításokhoz, de a Page Gépház Visibility szabályzat engedélyezve van a Gépház-alkalmazásban elérhető lapok mennyiségének korlátozásához.
- A Remote Assisthez és a más vállalatoknak bérelt üzletági alkalmazáshoz használható eszközök. Ezek az eszközök olyan kioszkokkal is vannak, amelyek csak az alkalmazást és a Remote Assist eszközt tartalmazzák. A WDAC használatával az alkalmazás Gépház és a Microsoft Edge nem indul el. A kölcsönzés tartalmaz egy USB-C akkumulátorcsomagot, amely több műszakban is teljes mértékben tartja az eszközöket.
- Minden eszköz be van állítva az Autopilothoz, és letölti az összes vállalati alkalmazást. Több különböző kioszkprofilt is beállított, amelyek különböző Azure AD-csoportokat céloznak meg. Minden felhasználó FIDO2 HoloLens kulcsokkal jelentkezik be a saját Azure AD-fiókjába, és személyre szabott élményt nyújt.



## <a name="share-with-multiple-people-each-using-their-own-account"></a>Megosztás több felhasználóval, mindegyik saját fiókkal

**Előfeltétel:** A HoloLens 1803-as vagy újabb Windows 10 kell futnia.  HoloLens (1. generációs) verzióra is frissíteni kell a [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

Ha saját fiókokat Azure Active Directory (Azure AD- ) használ, több felhasználó is megtarthatja a saját felhasználói beállításait és felhasználói adatait az eszközön.

Ha meg kell győződni arról, hogy többen is használhatnak saját fiókokat a HoloLens, kövesse az alábbi lépéseket a konfiguráláshoz:

1. Győződjön meg arról, hogy az eszköz Windows 10 1803-as vagy újabb verziót futtat.
   > [!IMPORTANT]
   > Ha HoloLens (1. generációs) eszközt használ, frissítse az [eszközt Windows Holographic for Business.](hololens1-upgrade-enterprise.md)
1. Az eszköz beállításakor válassza a Saját munkahelyi **vagy** iskolai tulajdonú lehetőséget, és jelentkezzen be egy Azure AD-fiókkal.
1. A beállítás befejezése után győződjön meg arról, hogy a **fiókbeállítások**(a  >  **Gépház-fiókok**) tartalmazzák az **Egyéb felhasználók beállítást.**

A felhasználók HoloLens a következő lépéseket:

1. Ha egy másik felhasználó már használja az eszközt, válasszon az alábbi lehetőségek közül:
   - A készenléti állapotba való visszatéréshez nyomja le egyszer a bekapcsológombot, majd a zárolási képernyőre való visszatéréshez nyomja le újra a bekapcsológombot
   - HoloLens 2 felhasználó kiválaszthatja a felhasználó csempéjét a Start menü az aktuális felhasználó kijelentkeztetése érdekében.

1. Jelentkezzen be az eszközre az Azure AD-fiók hitelesítő adataival.  
    Ha első alkalommal használja az eszközt, a saját [](hololens-calibration.md) szemére kell HoloLens az eszközt.

Az eszköz felhasználóinak listájáért vagy egy felhasználó eszközről való eltávolításához a Fiók **egyéb** Gépház  >    >  **meg.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Megosztás több felhasználóval, akik mind ugyanazt a fiókot használják

Több felhasználó is megoszthat egy HoloLens eszközt egyetlen felhasználói fiók használatával.

**A HoloLens 2.** időpontban, amikor egy új felhasználó először helyezi a fejére az eszközt (miközben ugyanaz a fiók van bejelentkezve), az eszköz arra kéri az új felhasználót, hogy gyorsan állítsa be és szabja személyre a megtekintési élményt. Az eszköz tárolhatja a berendezési adatokat, így a jövőben automatikusan optimalizálni tudja az egyes felhasználók megtekintési élményének minőségét és kényelmi élményét. A felhasználóknak nem kell újra bekalkenni az eszközt.

**A HoloLens (1. generációs)** felhasználóktól a fiókot megosztó felhasználóknak újra kell kérniük az újraszámítást a Gépház alkalmazásban.  További információ [](hololens-calibration.md)a beredektálásról.