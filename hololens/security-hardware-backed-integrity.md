---
title: Hardveres integritás és futásidejű igazolás
description: Hardveres integritás és futásidejű igazolás
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: biztonság, hololens, hardveres integritás, futásidejű igazolás, UEFI, UEFI biztonságos rendszerindítás, biztonságos rendszerindítás, TPM, fenyegetésvédelem, Windows Adatmegőrzés-védelem, kódintegritás, kódvédelem,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0a89fa5e61e560f629444efd2728f6dd41db60d3
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379574"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Hardveres integritás- és futásidejű igazolás

A hardveres integritás- és futásidejű igazolás védelmet nyújt az operációs rendszer indítása előtt, futásidőben, amikor az eszköz hardveres és távoli igazolási szolgáltatásokat használ az integritás fenntartása érdekében indításkor és futásidő alatt.

## <a name="uefi-secure-boot"></a>UEFI biztonságos rendszerindítás

A HoloLens 2 a Unified Extensible Firmware Interface (UEFI) biztonságos rendszerindítást mindig kényszeríti, és az UEFI csak a Windows Holographic for Business.
A biztonságos rendszerindítás biztosítja, hogy a teljes rendszerindítási lánc integritása ellenőrizve legyen, és hogy a Windows mindig a megfelelő biztonsági házirendekkel induljon el. További információ a [biztonságos rendszerindításról.](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

## <a name="tpm"></a>TPM

A platformmegbízhatósági modul (TPM) egy speciális lapka egy végponteszközön. A HoloLens 2 A TPM 2.0-t használja, amely hardver által kényszerített kulcselszigetelést biztosít. További információ a [TPM alapjairól.](https://docs.microsoft.com/windows/security/information-protection/tpm/tpm-fundamentals)

## <a name="persistence-access-threat-protection"></a>Adatmegőrzési hozzáférés fenyegetésvédelemhez

A legtöbb kibertámadás célja az eszköz állandó hozzáférésének fenntartása. A kiberbűnözés esetén az adatmegőrzés fenntartása lehetővé teszi, hogy egy feltört Windows-eszköz csatlakozzon egy botnethez, hozzáférést adjon az eszközhöz vagy más visszaeső felhasználókhoz, vagy lehetővé tegye az ismételt adatlopásokat. A célzott támadások világában az adatmegőrzés elengedhetetlen a sikeres kibertámadások számára – akár egy eszközön, akár (gyakrabban) egy teljes hálózaton.  

Valójában a célzott támadásokat "fejlett állandó fenyegetéseknek" tekintjük, mivel stratégiai szükség van a céleszközhöz vagy hálózathoz való hozzáférés fenntartására. Ezért a Windows Holographic for Business rendkívül fontosnak tartja a kitartás elleni védekezést, és anti-persistence technológiával hoz egy kitalló ügyfélbiztonsági ígéretet.

### <a name="secure-boot"></a>Biztonságos rendszerindítás

A HoloLens 2 az operációs rendszer összes Extensible Firmware Interface (UEFI) biztonságos rendszerindítását kényszeríti. Az UEFI csak a Microsoft megbízható platformokat indítja el, ami biztosítja, hogy a teljes rendszerindítási lánc integritása ellenőrizve van, és hogy a Windows mindig a megfelelő biztonsági házirendekkel indul el. A HoloLens 2 nem kikapcsolja a biztonságos rendszerindítást, és nem engedélyezi a harmadik féltől származó rendszertöltőket.

> [!Tip]
> További információ a [biztonságos rendszerindításról.](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

### <a name="windows-anti-persistence-assurance"></a>A Windows adatmegőrzés-gátló garanciája

A HoloLens 2 anti-persistence garantálja a felhasználók számára, hogy még abban a ritka esetben is, amikor a rendszer futásidejű biztonsági rése (például egy távoli biztonsági rés) bekövetkezik, az ilyen eseményeket az eszköz egyszerű kikapcsolása révén eltávolítják a rendszerből eltávolított rosszindulatú kódokkal. Az adatmegőrzés további megerősítése érdekében a HoloLens 2 hatékony integritásvédelmet biztosít, és csak olvasható védelmet biztosít.

Az operációs rendszer adatainak adatok formájában való megőrzésére akkor is lehetőség van, ha a felhasználó nem végzi el az eszköz Leküldéses gomb alaphelyzetbe állítása (PBR) műveletét, amely törli az összes átformált partíciót. Bár a nem módosítható partíciókban való adatmegőrzés sokkal nehezebb, a felhasználónak a HoloLens 2 PBR-nek kell lennie, hogy eltávolítsa az esetleges fenyegetésmegőrzést a módosítható részekből.

## <a name="code-integrity-protection"></a>Kódintegritás-védelem

A kódintegritás (CI) a modern operációs rendszerek kulcsfontosságú biztonsági tulajdonsága. A CI kikényolása megbízható biztonsági döntéseket tesz lehetővé, mivel garantálja, hogy a kód forrásának átláthatónak kell lennie a felhasználó és az operációs rendszer számára is. A teljes kódintegritásnak ki kell terjesztenie a korábbi bináris rendszerkép-aláírást, és tartalmaznia kell a futásidejű kényszerítési érvényt, például a folyamintegritás szabályozását és a dinamikus kódkorlátozásokat. A CI kritikus fontosságú a támadások több osztályának megelőzéséhez, beleértve a társadalmilag megtervezett kártevőket, például a zsarolóprogramokat, a távoli kódvégrehajtási támadásokat és más támadási osztályokat.
