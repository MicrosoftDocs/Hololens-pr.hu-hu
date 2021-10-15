---
title: Regisztráció HoloLens MDM-be
description: Megtudhatja, hogyan regisztrálhat HoloLens mobileszköz-felügyeletben (MDM) több eszköz egyszerűbb kezelése érdekében.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/15/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: fa114633afe70a11a180c67fedbd40eb423ece99
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034178"
---
# <a name="enroll-hololens-in-mdm"></a>Regisztráció HoloLens MDM-be

Egyszerre több Microsoft HoloLens is felügyelhet olyan megoldásokkal, mint a [Microsoft Intune.](/intune/windows-holographic-for-business) Kezelheti a beállításokat, kiválaszthatja a telepíteni kívánt alkalmazásokat, és beállíthatja a szervezet igényeihez igazított biztonsági konfigurációkat. Lásd: A [Holographic Windows-t](/intune/windows-holographic-for-business)futtató eszközök kezelése a Microsoft Intune-val, a Windows Holographic által támogatott konfigurációszolgáltatók [(CSP-k)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)és a [Windows Holographic for Business.](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)

> [!NOTE]
> A mobileszköz-kezelés (MDM), beleértve a VPN, a Bitlocker és a kioszkmód funkcióit is, csak akkor érhető el, ha az -ra [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

## <a name="requirements"></a>Követelmények

 A szervezetnek be kell állítania a Mobile Eszközkezelés (MDM) eszközt a mobileszközök HoloLens kezeléséhez. Az MDM-szolgáltató lehet Microsoft Intune microsoftos MDM API-kat használó külső szolgáltató.

## <a name="different-ways-to-enroll"></a>A regisztráció különböző módjai

Az OOBE vagy a bejelentkezés után [kiválasztott](hololens-identity.md) identitás típusától függően különböző regisztrációs módszerek állnak a létezik.

- Ha az Identity az Azure AD, akkor az OOBE vagy Gépház **Alkalmazás-hozzáférés** munkahelyi vagy iskolai Csatlakozás  ->    ->  **gombra.**
    - Az Azure AD esetén az [automatikus MDM-regisztráció](hololens-enroll-mdm.md#auto-enrollment-in-mdm) csak akkor történik meg, ha az Azure AD-t regisztrációs URL-címekkel konfigurálták.

- Ha az Identity az Azure AD, és az eszköz előre regisztrálva van az Intune MDM-kiszolgálón, és hozzá van rendelve egy adott konfigurációs profil, akkor az Azure AD-Join és az automatikus [MDM-regisztráció](hololens-enroll-mdm.md#auto-enrollment-in-mdm) az OOBE során történik.
    - Más néven [AutoPilot-folyamat](hololens2-autopilot.md) Az [19041.1103+-buildek érhetők el.](hololens-release-notes.md#windows-holographic-version-2004)


- Ha az Identity az MSA, Gépház **az Alkalmazás-hozzáférés** munkahelyi vagy iskolai  ->    ->  **Csatlakozás** gombra.
    - Más néven Munkahelyi fiók hozzáadása (AWA) folyamat.
- Ha az Identitás helyi felhasználó, akkor Gépház **alkalmazás-hozzáférés** munkahelyi vagy iskolai regisztrációja csak az  ->    ->  **eszközkezelési hivatkozáson** keresztül.
    - Más néven tiszta MDM-regisztrációs folyamat.

Miután az eszköz regisztrálva van az MDM-kiszolgálón, a Gépház alkalmazás azt fogja tükrözni, hogy az eszköz regisztrálva van az eszközkezelésben.

## <a name="auto-enrollment-in-mdm"></a>Automatikus regisztráció az MDM-be

Ha a szervezet [](https://azure.microsoft.com/overview/)azure Prémium-előfizetéssel rendelkezik, Azure Active Directory (Azure AD) és egy MDM-megoldást használ, amely Azure AD-jogkivonatot fogad el hitelesítéshez (jelenleg csak az Microsoft Intune és az AirWatch támogatja), a rendszergazda konfigurálhatja az Azure AD-t úgy, hogy automatikusan engedélyezze az MDM-regisztrációt, miután a felhasználó bejelentkezett az Azure AD-be Számla. [Megtudhatja, hogyan konfigurálhatja az Azure AD-regisztrációt.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Ha az automatikus regisztráció engedélyezve van, nincs szükség további manuális regisztrációra. Amikor a felhasználó Egy Azure AD-fiókkal jelentkezik be, az eszköz az első futtatás befejezése után regisztrálva lesz az MDM-be.

Ha egy eszköz Azure AD-hez csatlakozik, az hatással lehet arra, hogy ki tekinthető [az eszköz tulajdonosának.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>A HoloLens Intune-ból

A regisztrációs módszertől függően előfordulhat, hogy az eszköz regisztrációja nem lesz elérhető.

Ha az eszköz Azure AD-fiókkal vagy Autopilot-fiókkal lett regisztrálva, nem lehet azt az Intune-ból regisztrálni. Ha szeretne lecsatlakozni HoloLens Azure AD-ről, vagy újracsatlakozni az Azure AD-bérlőhöz, alaphelyzetbe kell [állítania/újra](hololens-recovery.md#restart-the-device) kell perjelet állítania az eszközt.

Ha az eszköz munkahelyi fiókot hozzáadott MSA-fiókból vagy egy csak eszközkezelésben regisztrált helyi fiókból lett regisztrálva, akkor az eszköz regisztrációját is megszűkítheti. Nyissa meg a Start menü, majd válassza Gépház **alkalmazás-hozzáférés** munkahelyi vagy iskolai  ->    ->  *fiókok leválasztása*  ->  **gombot.**

## <a name="enrollment-troubleshooting"></a>Regisztrációs hibaelhárítás

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>Ellenőrizze, hogy érvényes licenc van-e hozzárendelve a felhasználóhoz

Tekintse meg az Windows regisztrálási problémák elhárítása szakaszt [Microsoft Intune](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors) következő szakaszokban, például: [Eszköztípus-korlátozások](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions) ellenőrzése és Érvényes licenc [hozzárendelése a felhasználóhoz.](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user)

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Győződjön meg arról, hogy az MDM-regisztráció nincs letiltva a Windows eszközökön

Ahhoz, hogy a regisztráció sikeres legyen, meg kell győződni arról, hogy a HoloLens regisztrálhat. Mivel HoloLens eszköz Windows eszköznek minősül, nincs szükség regisztrációs korlátozásokra, amelyek blokkolni tudnák az üzembe helyezést. [Tekintse át ezt a korlátozási listát,](/mem/intune/enrollment/enrollment-restrictions-set) és ellenőrizze, hogy tudja-e regisztrálni az eszközeit.