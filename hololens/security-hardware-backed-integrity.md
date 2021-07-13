---
title: Hardveres integritás és futásidejű igazolás
description: Hardveres integritás és futásidejű igazolás
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: biztonság, hololens, hardveres biztonsági integritás, futásidejű igazolás, UEFI, UEFI biztonságos rendszerindítás, biztonságos rendszerindítás, TPM, fenyegetésvédelem, Windows anti-persistence Assurance, kódintegritás, kódvédelem,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 037f9325555244314518c81d7814bf983c345af6
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639335"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Hardveres integritás- és futásidejű igazolás

A hardveres integritás- és futásidejű igazolás védelmet nyújt az operációs rendszer indítása előtt, futásidőben, amikor az eszköz hardvert és távoli igazolási szolgáltatásokat használ az integritás fenntartásához indításkor és futásidőben.

## <a name="uefi-secure-boot"></a>UEFI biztonságos rendszerindítás

HoloLens 2. Extensible Firmware Interface UEFI mindig kényszeríti a biztonságos rendszerindítást, és az UEFI csak az Windows Holographic for Business.
A biztonságos rendszerindítás biztosítja, hogy a teljes rendszerindítási lánc integritása ellenőrizve legyen, és Windows a rendszer mindig a megfelelő biztonsági házirendekkel induljon el. További információ a [biztonságos rendszerindításról.](/windows-hardware/design/device-experiences/oem-secure-boot)

## <a name="tpm"></a>TPM

A platformmegbízhatósági modul (TPM) egy speciális lapka egy végponteszközön. HoloLens 2. lépés TPM 2.0-t használ, amely hardver által kényszerített kulcselszigetelést biztosít. További információ a [TPM alapjairól.](/windows/security/information-protection/tpm/tpm-fundamentals)

## <a name="persistence-access-threat-protection"></a>Adatmegőrzési hozzáférés fenyegetésvédelem

A legtöbb kibertámadás célja az eszköz állandó hozzáférésének fenntartása. A kiberbűnözés esetén az adatmegőrzés fenntartása lehetővé teszi, hogy egy feltört Windows-eszköz csatlakozzon egy botnethez, hozzáférést adjon el az eszközhöz vagy más visszaeső felhasználókhoz, vagy lehetővé tegye az adatok ismételt ellopását. A célzott támadások világában az állandóság elengedhetetlen a sikeres kibertámadások során – akár egy eszközön, akár (gyakrabban) egy teljes hálózaton.  

Valójában a célzott támadások "fejlett állandó fenyegetéseknek" minősülnek, mivel stratégiai szükség van a céleszközhöz vagy hálózathoz való hozzáférés fenntartására. Ezért a Windows Holographic for Business nélkülözhetetlennek tartja az adatmegőrzés elleni védelmet, és a perzisztencia-megőrzési technológiával egy ironc önatikus ügyfélbiztonsági ígéretet hoz.

### <a name="secure-boot"></a>Biztonságos rendszerindítás

HoloLens 2. Extensible Firmware Interface (UEFI) biztonságos rendszerindítást kényszerít az operációs rendszer összes központi állapotában. Az UEFI csak a Microsoft megbízható platformokat indítja el, ami biztosítja, hogy a teljes rendszerindítási lánc integritása ellenőrizve legyen, és hogy a Windows mindig a megfelelő biztonsági szabályzatokkal indul el. HoloLens 2. helyen nem lehet kikapcsolni a biztonságos rendszerindítást, és nem engedélyezi a harmadik féltől származó rendszertöltőket sem.

> [!Tip]
> További információ a [biztonságos rendszerindításról.](/windows-hardware/design/device-experiences/oem-secure-boot)

### <a name="windows-anti-persistence-assurance"></a>Windows Anti-Persistence Assurance

HoloLens 2. típusú adatmegőrzés garantálja a felhasználók számára, hogy még abban a ritka helyzetben is, amikor a rendszer futásidejű biztonsága bármikor előfordulna (például egy távoli biztonsági rést kihasználva) az ilyen eseményeket a rendszerről eltávolított kártékony kódok egyszerűen az eszköz kikapcsolása révén enyhítenék. Az adatmegőrzés további megerősítéséhez a 2. HoloLens nagy teljesítményű integritásvédelmet és írási védelemmel bővült.

Az operációs rendszer adatainak adatok formájában való megőrzésére továbbra is van lehetőség, kivéve, ha a felhasználó olyan leküldéses gomb alaphelyzetbe állítást (PBR) hajt végre az eszközön, amely törli az összes formázható partíciót. Bár a nem módosítható partíciókra való adatmegőrzés sokkal nehezebb, a felhasználónak a HoloLens 2. PBR-nek kell lennie, hogy eltávolítsa a lehetséges fenyegetésmegőrzést a módosítható részekből.

## <a name="code-integrity-protection"></a>Kódintegritás-védelem

A kódintegritás (CI) a modern operációs rendszerek kulcsfontosságú biztonsági tulajdonsága. A CI kikényolása megbízható biztonsági döntéseket tesz lehetővé, mivel garantálja, hogy a kód forrását a felhasználó és az operációs rendszer is átláthatóvá teszi. A teljes kódintegritásnak ki kell terjesztenie a bináris rendszerkép-aláírást, és tartalmaznia kell a futásidő kényszerítését, például a folyam integritásának szabályozását és a dinamikus kódkorlátozásokat. A CI kritikus fontosságú a támadások több osztályának megakadályozásához, beleértve a társadalmilag megtervezett kártevőket, például a zsarolóprogramokat, a távoli kódvégrehajtási támadásokat és számos más támadási osztályt.
