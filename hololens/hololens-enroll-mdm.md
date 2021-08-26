---
title: Regisztráció HoloLens MDM-be
description: Megtudhatja, hogyan regisztrálhat HoloLens mobileszköz-felügyeletben (MDM) több eszköz egyszerűbb kezelése érdekében.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5ded375d88740b9367eec87e4e902c423f131689
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/25/2021
ms.locfileid: "122858983"
---
# <a name="enroll-hololens-in-mdm"></a>Regisztráció HoloLens MDM-be

Egyszerre több Microsoft HoloLens is felügyelhet olyan megoldásokkal, mint a [Microsoft Intune.](/intune/windows-holographic-for-business) Kezelheti a beállításokat, kiválaszthatja az alkalmazásokat a szervezet igényeihez igazított biztonsági konfigurációk telepítéséhez és beállításhoz. Lásd: A [Holographic Windows-t](/intune/windows-holographic-for-business)futtató eszközök kezelése a Microsoft Intune segítségével, a Windows Holographic által támogatott konfigurációszolgáltatók [(CSP-k)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)és a [Windows Holographic for Business.](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)

> [!NOTE]
> A mobileszköz-kezelés (MDM), beleértve a VPN-t, a Bitlockert és a kioszkmódot is, csak akkor érhető el, ha az -ra [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

## <a name="requirements"></a>Követelmények

 A szervezetnek be kell állítania a Mobile Eszközkezelés (MDM) eszközt a mobileszközök HoloLens kezeléséhez. Az MDM-szolgáltató lehet Microsoft Intune microsoftos MDM API-kat használó külső szolgáltató.

## <a name="different-ways-to-enroll"></a>A regisztráció különböző módjai

Az OOBE vagy a bejelentkezés után [kiválasztott](hololens-identity.md) identitás típusától függően különböző regisztrációs módszerek állnak a létezik.

- Ha az Identity az Azure AD, akkor az OOBE vagy Gépház **alkalmazás-hozzáférés** munkahelyi vagy iskolai Csatlakozás  ->    ->   gombra.
    - Az Azure AD esetén az [automatikus MDM-regisztráció](hololens-enroll-mdm.md#auto-enrollment-in-mdm) csak akkor történik meg, ha az Azure AD-t regisztrációs URL-címekkel konfigurálták.

- Ha az Identity az Azure AD, és az eszköz előre regisztrálva van az Intune MDM-kiszolgálón, és hozzá van rendelve egy adott konfigurációs profil, akkor az Azure AD-Join és az automatikus [MDM-regisztráció](hololens-enroll-mdm.md#auto-enrollment-in-mdm) az OOBE során történik.
    - Más néven [AutoPilot-folyamat](hololens2-autopilot.md) Az [19041.1103+-buildek érhetők el.](hololens-release-notes.md#windows-holographic-version-2004)


- Ha az Identity az MSA, akkor használja **Gépház Alkalmazás-hozzáférés** munkahelyi vagy iskolai  ->    ->  **Csatlakozás** gombot.
    - Más néven Munkahelyi fiók hozzáadása (AWA) folyamat.
- Ha az Identitás helyi felhasználó, akkor Gépház **alkalmazás-hozzáférés** munkahelyi vagy iskolai  ->    ->  **regisztrációja csak az eszközkezelési hivatkozáson** keresztül.
    - Más néven tiszta MDM-regisztrációs folyamat.

Miután az eszköz regisztrálva van az MDM-kiszolgálón, az Gépház az eszköznek az eszközkezelésben való regisztrálását fogja tükrözni.

## <a name="auto-enrollment-in-mdm"></a>Automatikus regisztráció az MDM-be

Ha a szervezet [](https://azure.microsoft.com/overview/)azure Prémium-előfizetéssel rendelkezik, Azure Active Directory (Azure AD) és egy MDM-megoldást használ, amely Azure AD-tokent fogad el hitelesítéshez (jelenleg csak az Microsoft Intune és az AirWatch támogatja), a rendszergazda konfigurálhatja az Azure AD-t úgy, hogy automatikusan engedélyezze az MDM-regisztrációt, miután a felhasználó bejelentkezett az Azure AD-fiókjával. [Megtudhatja, hogyan konfigurálhatja az Azure AD-regisztrációt.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Ha az automatikus regisztráció engedélyezve van, nincs szükség további manuális regisztrációra. Amikor a felhasználó Azure AD-fiókkal jelentkezik be, az eszköz az első futtatás befejezése után regisztrálva lesz az MDM-be.

Ha egy eszköz Azure AD-hez csatlakozik, az hatással lehet arra, hogy ki tekinthető [az eszköz tulajdonosának.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>A HoloLens Intune-ból

A regisztrációs módszertől függően előfordulhat, hogy az eszköz regisztrációja nem lesz elérhető.

Ha az eszköz Azure AD-fiókkal vagy Autopilot-fiókkal lett regisztrálva, nem lehet azt az Intune-ból regisztrálni. Ha le szeretné állítani a HoloLens Azure AD-ről, vagy egy másik Azure AD-bérlőhöz szeretne újracsatlakozni, alaphelyzetbe kell [állítania/újra](hololens-recovery.md#reset-the-device) kell perjelet állítania az eszközt.

Ha az eszköz munkahelyi fiókot hozzáadott MSA-fiókból vagy egy helyi fiókból lett regisztrálva, amely csak eszközkezelésre lett regisztrálva, akkor az eszköz regisztrációját is megszűkítheti. Nyissa meg Start menü, majd válassza Gépház **alkalmazás-hozzáférés** munkahelyi vagy iskolai  ->    ->  *fiókok leválasztása*  ->  **gombot.**

## <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Győződjön meg arról, hogy az MDM-regisztráció nincs letiltva a Windows eszközökön

Ahhoz, hogy az Autopilot sikeres legyen, meg kell győződni arról, hogy a HoloLens eszközök regisztrálva legyenek. Mivel HoloLens eszköz Windows eszköznek minősül, nem kell regisztrációs korlátozásokat alkalmaznunk, amelyek blokkolni tudnák az üzembe helyezést. [Tekintse át ezt a korlátozási listát,](/mem/intune/enrollment/enrollment-restrictions-set) és ellenőrizze, hogy tudja-e regisztrálni az eszközeit.