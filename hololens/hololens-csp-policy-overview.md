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
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378155"
---
# <a name="configure-csps-and-device-management-overview"></a>CsP-k és Eszközkezelés konfigurálása – áttekintés

A rendszergazdák szabályzatbeállításokat határozhatnak meg és valósítanak meg a HoloLens 2-ben. A használt konfigurációs beállítások a telepítési forgatókönyvtől függően eltérnek, és a vállalati eszközök a legszélesebb körű vezérlést kínálják az it-csoport számára. A Windows 10 konfigurációszolgáltatók (CSP-k) az eszköz konfigurációs beállításainak olvasására, beállítására, módosítására vagy törlésére való felületek. Ezek a beállítások beállításkulcsra vagy fájlokra vannak leképezve. Egyes konfigurációs szolgáltatók támogatják a WAP formátumot, némelyik támogatja a SyncML-t, néhány pedig mindkettőt.

További információ a Windows 10 Holographic csP-kről: A [HoloLens-eszközök](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)által támogatott CSP-k teljes listája.
A rendszergazdák az eszközökön is kezelhetik a házirendek CSP-ját. Lásd a [HoloLens 2 által támogatott házirend-CSP-k teljes listáját.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="configuration-methods"></a>Konfigurációs módszerek

### <a name="configure-with-mdm"></a>Konfigurálás MDM-sel

A CSP-k és szabályzatok egyszerűen kezelhetők az MDM-rendszerekben regisztrált bármely személyes vagy vállalati eszközön. Miután regisztrált egy eszközt az MDM-megoldásban, kezelheti az eszközt vagy eszközkonfigurációkat használó eszközöket. További információ a [HoloLens-eszközök MDM-en keresztüli kezeléséhez.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Konfigurálás kiépítési csomagokkal

A HoloLens 2 támogatja a CSP-konfigurációk korlátozott készletének beállítását a HoloLens 2-eszközökhöz egyéni kiépítési csomagokon keresztül. A kiépítési csomagokat általában nem MDM által felügyelt eszközökhöz használják, és manuálisan kell alkalmazni őket az egyes eszközökre. További információ a [HoloLens egyéni kiépítési csomagjainak létrehozásáról.](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="configurations"></a>Konfigurációk

### <a name="common-device-restrictions"></a>Gyakori eszközkorlátozások

Bizonyos eszközkorlátozások egyszerűek, és letiltják a funkciókat vagy az eszközhöz való kapcsolódást. További információért olvassa el a gyakori [eszközkorlátozásokkal kapcsolatos további tudnivalókat.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Kioszkmódok

A Kioszkmód használatával szabályozhatja, hogy alapértelmezés szerint mely identitások mely alkalmazásokhoz férnek hozzá. A kioszkok egyetlen alkalmazáshoz vagy több alkalmazás felhasználói felületéhez is használhatók. A kioszkkonfigurációk az eszköz minden használója számára egyetlen alkalmazástól a különböző csoportokhoz kiválasztott alkalmazásokon át adhatók át. A kioszkmód nem hagyja abba, hogy az "engedélyezett alkalmazások" más alkalmazásokat indítsanak el, és soha nem volt rendeltetése. További információ: [Kioszkmódok](hololens-kiosk.md)és azok használata.

### <a name="settings-page-visibility"></a>Beállítások oldal láthatósága

A Beállítások alkalmazás-szabályzat használatával szabályozhatja, hogy alapértelmezés szerint mely identitások férhetnek hozzá a beállításokhoz. Ezzel a szabályzatkal a Beállítások alkalmazás konfigurálható úgy, hogy csak a kijelölt oldalakat mutassa, vagy elrejtse az összes kiválasztott oldalt. [Olvassa el, hogyan konfigurálhatja az elérhető oldalakat.](settings-uri-list.md)

Ez a funkció jelenleg csak a [buildek Windows Insider érhető el.](hololens-insider.md) Győződjön meg arról, hogy a használni kívánt eszközök az 19041.1349+-es builden vannak.

### <a name="wdac"></a>WDAC

A WDAC-konfigurációval szabályozhatja, hogy mely alkalmazások/folyamatok indíthatóak el/nem engedélyezettek attól függetlenül, hogy a rendszer kioszkmódban van-e vagy sem.
[Tekintse meg a WDAC áttekintését.](windows-defender-application-control-wdac.md)
