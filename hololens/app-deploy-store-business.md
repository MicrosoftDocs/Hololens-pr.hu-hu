---
title: Vállalati Microsoft Áruház
description: Megtudhatja, hogyan munkához Microsoft Store Vállalatoknak vegyes valóságú alkalmazások üzleti közzétételéhez.
keywords: Microsoft Store Vállalatoknak, msfb, alkalmazástelepítés, áruház
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
ms.openlocfilehash: 5bc719539aaa254b8aacb05e24554152231f7e5a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924327"
---
# <a name="microsoft-store-for-business"></a>Vállalati Microsoft Áruház

A [Microsoft Store Vállalatoknak](/microsoft-store/microsoft-store-for-business-overview) elsősorban vállalatok vagy szervezetek informatikai döntéshozói és rendszergazdái számára készült, amelyek rugalmasan megkeresik, megvásárolják, kezelik és terjesztik az ingyenes és fizetős alkalmazásokat egyes piacokon, és nagy mennyiségben Windows 10 eszközökhöz. 

Egy leltárban Microsoft Store alkalmazásokat és privát üzletági alkalmazásokat kezelhet, és szükség szerint hozzárendelheti és újra felhasználhatja a licenceket. A legjobb terjesztési módszert is kiválaszthatja a szervezet számára: közvetlenül rendelhet alkalmazásokat egyénekhez és csapatokhoz, alkalmazásokat tehet közzé privát oldalakon az Microsoft Store-ban, vagy csatlakozhat felügyeleti megoldásokkal további lehetőségekért.

Ha Microsoft Store Vállalatoknak felhasználó használja, elindítja a Microsoft Store alkalmazást. Az elindítása után a felhasználó kiválaszthatja a szervezet nevével egy lapot, majd jelennek meg a számára vagy az eszköz számára elérhető alkalmazások.

> [!Note]
> Microsoft Store Vállalatoknak nem tölt le (le) automatikusan alkalmazásokat az eszközökre. Az alkalmazásokat azonban Microsoft Store Vállalatoknak társíthatja az eszközkezelési (MDM) kiszolgálóhoz az alkalmazások megcélzához és az eszközökkel való szinkronizálásához.

A következő oldalakon további információkat olvashat a Microsoft Store Vállalatoknak:

* [Az alkalmazások telepítéséhez használt engedélyszintek](/mem/intune/configuration/device-restrictions-windows-holographic#app-store)
* [Alkalmazás hozzáadása a Vállalati Áruházhoz](/mem/intune/apps/store-apps-windows)
* [Alkalmazások hozzárendelése alkalmazottak csoportjaihoz](/mem/intune/apps/windows-store-for-business)

Az alkalmazás társításával kapcsolatban Microsoft Store Vállalatoknak a Associate your Microsoft Store Vállalatoknak with Intune (A saját Microsoft Store Vállalatoknak [társítása az Intune-nal) webhelyet.](/mem/intune/apps/windows-store-for-business#associate-your-microsoft-store-for-business-account-with-intune)

> [!Tip]
> További információ az [offline alkalmazások terjesztéséről](/microsoft-store/distribute-offline-apps) olyan alkalmazások használata esetén, mint az Advanced Recovery Companion (ARC) és Windows Configuration Designer (WCD).

## <a name="use-only-private-store-apps-for-microsoft-store"></a>Csak privát áruházbeli alkalmazások használata Microsoft Store

- A [Holographic Windows 21H2 verzióban vezettük be.](hololens-release-notes.md#windows-holographic-version-21h2)

A RequirePrivateStoreOnly szabályzat engedélyezve van a HoloLens. Ez a szabályzat lehetővé Microsoft Store, hogy az alkalmazás úgy legyen konfigurálva, hogy csak a szervezet számára konfigurált privát tárolót mutassa. A hozzáférés korlátozása csak az Ön által elérhetővé tett alkalmazásokra.

További információ az [ApplicationManagement/RequirePrivateStoreOnly-ről](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

## <a name="smart-retry-for-app-updates"></a>Intelligens újrapróbálkozás alkalmazásfrissítésekkor

- A [Holographic Windows 21H2 verzióban vezettük be.](hololens-release-notes.md#windows-holographic-version-21h2)

A HoloLens egy új szabályzat, amely lehetővé teszi a rendszergazdák számára, hogy ismétlődő vagy egyszeri időpontot állítsanak be az olyan alkalmazások újraindításához, amelyek frissítése az alkalmazás használatának engedélyezése miatt meghiúsult. Ezek több különböző eseményindító, például ütemezett időpont vagy bejelentkezés alapján is beállíthatók. A szabályzat használatával kapcsolatos további információkért tekintse meg az [ApplicationManagement/ScheduleForceRestartForUpdateFailures et.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)