---
title: CsP-k és Eszközkezelés konfigurálása – áttekintés
description: Megtudhatja, hogyan konfigurálhatja a CSP-eket, a szabályzatokat és az eszközkezelést Eszközkezelés és kiépítési csomagokkal.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640457"
---
# <a name="configure-csps-and-device-management-overview"></a>CsP-k és Eszközkezelés konfigurálása – áttekintés

A rendszergazdák a 2. HoloLens házirend-beállításokat határozhatják meg és valósíthatják meg. A használt konfigurációs beállítások a telepítési forgatókönyvtől függően különböznek, és a vállalati eszközök a legszélesebb körű vezérlést kínálják az it-itának. A Windows 10 konfigurációszolgáltatók (CSP-k) az eszköz konfigurációs beállításainak olvasására, beállítására, módosítására vagy törlésére való felületek. Ezek a beállítások beállításkulcsra vagy fájlokra vannak leképezve. Egyes konfigurációs szolgáltatók támogatják a WAP formátumot, némelyik támogatja a SyncML-t, néhány pedig mindkettőt.

Az eszközkezelési CSP-Windows 10 Holographic kapcsolatos további információkért tekintse meg az eszközök által támogatott [CSP-k HoloLens listáját.](/windows/client-management/mdm/configuration-service-provider-reference#hololens)
A rendszergazdák az eszközökön is kezelhetik a házirendek CSP-ját. Lásd a 2. HoloLens által támogatott [házirend-CSP-k teljes listáját.](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="configuration-methods"></a>Konfigurációs módszerek

### <a name="configure-with-mdm"></a>Konfigurálás MDM-sel

A CSP-k és szabályzatok egyszerűen kezelhetők az MDM-rendszerekben regisztrált személyes vagy vállalati eszközök bármelyikén. Miután regisztrált egy eszközt az MDM-megoldásban, kezelheti az eszközt vagy eszközkonfigurációkat használó eszközöket. További információ a [mobileszközök MDM HoloLens keresztüli kezelésről.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Konfigurálás kiépítési csomagokkal

HoloLens 2., támogatja a CSP-konfigurációk korlátozott készletének beállítását HoloLens 2 eszköz számára egyéni kiépítési csomagokon keresztül. A kiépítési csomagokat általában nem MDM által felügyelt eszközökhöz használják, és manuálisan kell alkalmazni őket az egyes eszközökre. Olvassa el az egyéni [kiépítési csomagok létrehozásáról HoloLens.](hololens-provisioning.md)

## <a name="configurations"></a>Konfigurációk

### <a name="common-device-restrictions"></a>Gyakori eszközkorlátozások

Bizonyos eszközkorlátozások egyszerűek, és letiltják a funkciókat vagy az eszközhöz való kapcsolódást. További információért olvassa el a gyakori [eszközkorlátozásokkal kapcsolatos további tudnivalókat.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Kioszkmódok

A Kioszkmód használatával szabályozhatja, hogy mely identitások férhetnek hozzá alapértelmezés szerint az alkalmazásokhoz. A kioszkok egyetlen alkalmazáshoz vagy több alkalmazás felhasználói felületéhez is használhatók. A kioszkkonfigurációk az eszköz minden használója számára egyetlen alkalmazástól a különböző csoportok alkalmazásválasztásaitól is függnek. A kioszkmód nem teszi lehetővé, hogy az "engedélyezett alkalmazások" más alkalmazásokat indítsanak el, és soha nem volt rendeltetése. További információ: [Kioszkmódok és azok használata.](hololens-kiosk.md)

### <a name="settings-page-visibility"></a>Gépház Oldal láthatósága

Az Gépház szabályzat használatával szabályozhatja, hogy mely identitások férhetnek hozzá alapértelmezés szerint a beállításokhoz. Ezzel a szabályzatkal Gépház alkalmazás konfigurálható úgy, hogy csak a kijelölt oldalakat mutassa, vagy elrejtse az összes kijelölt oldalt. [Olvassa el, hogyan konfigurálhatja az elérhető oldalakat.](settings-uri-list.md)

Ez a funkció jelenleg csak az [Insider Windows buildek esetén érhető el.](hololens-insider.md) Győződjön meg arról, hogy a szolgáltatáshoz használni kívánt eszközök az 19041.1349-es vagy további buildben vannak.

### <a name="wdac"></a>WDAC

A WDAC-konfigurációval szabályozhatja, hogy mely alkalmazások/folyamatok indíthatóak el/nem engedélyezettek attól függetlenül, hogy a rendszer kioszkmódban van-e vagy sem.
[Tekintse meg a WDAC áttekintését.](windows-defender-application-control-wdac.md)
