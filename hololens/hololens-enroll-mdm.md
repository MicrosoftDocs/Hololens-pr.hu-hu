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
ms.openlocfilehash: a368c622c137374ea9cc544490d3492fa9d3f8c1
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428510"
---
# <a name="enroll-hololens-in-mdm"></a>Regisztráció HoloLens MDM-be

Egyidejűleg több Microsoft HoloLens is felügyelhet olyan megoldásokkal, mint a [Microsoft Intune.](/intune/windows-holographic-for-business) Kezelheti a beállításokat, kiválaszthatja a telepíteni kívánt alkalmazásokat, és beállíthatja a szervezet igényeihez igazított biztonsági konfigurációkat. Lásd: A [Holographic Windows-t](/intune/windows-holographic-for-business)futtató eszközök kezelése a Microsoft Intune segítségével, a Windows Holographic által támogatott konfigurációs szolgáltatókkal [(CSP-kkal),](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)valamint a [Windows Holographic for Business.](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)

> [!NOTE]
> A mobileszköz-kezelés (MDM), beleértve a VPN, a Bitlocker és a [](hololens1-upgrade-enterprise.md)kioszkmód funkciókat is, csak akkor érhető el, ha a(Windows Holographic for Business.

## <a name="requirements"></a>Követelmények

 A szervezetnek be kell állítania a Mobile Eszközkezelés (MDM) eszközt a mobileszközök HoloLens kezeléséhez. Az MDM-szolgáltató lehet Microsoft Intune microsoftos MDM API-kat használó külső szolgáltató.

## <a name="different-ways-to-enroll"></a>A regisztrálás különböző módjai

Az OOBE [vagy](hololens-identity.md) a bejelentkezés után választott identitás típusától függően különböző regisztrációs módszerek állnak a létezik.

- Ha az Identity az Azure AD, akkor az OOBE vagy Gépház **alkalmazás-hozzáférés** munkahelyi vagy iskolai Csatlakozás  ->    ->   gombra.
    - Az Azure AD esetén az [automatikus MDM-regisztráció](hololens-enroll-mdm.md#auto-enrollment-in-mdm) csak akkor történik meg, ha az Azure AD-t regisztrációs URL-címekkel konfigurálták.

- Ha az Identity az Azure AD, és az eszköz előre regisztrálva van az Intune MDM-kiszolgálón, és hozzá van rendelve egy adott konfigurációs profil, akkor az Azure AD-Join és az automatikus [MDM-regisztráció](hololens-enroll-mdm.md#auto-enrollment-in-mdm) az OOBE során történik.
    - Más néven [Autopilot-folyamat](hololens2-autopilot.md) Az [19041.1103+-buildben érhető el.](hololens-release-notes.md#windows-holographic-version-2004)


- Ha az Identity az MSA, akkor használja **Gépház Alkalmazás-hozzáférés** munkahelyi vagy iskolai  ->    ->  **Csatlakozás** gombot.
    - Más néven Munkahelyi fiók hozzáadása (AWA) folyamat.
- Ha az Identitás helyi felhasználó, akkor Gépház **alkalmazás-hozzáférés** munkahelyi vagy iskolai  ->    ->  **regisztrációja csak az eszközkezelési hivatkozáson keresztül.**
    - Más néven tiszta MDM-regisztrációs folyamat.

Miután regisztrálta az eszközt az MDM-kiszolgálóval, az Gépház azt fogja tükrözni, hogy az eszköz regisztrálva van az eszközkezelésben.

## <a name="auto-enrollment-in-mdm"></a>Automatikus regisztráció az MDM-be

Ha a szervezet [](https://azure.microsoft.com/overview/)azure Prémium-előfizetéssel rendelkezik, az Azure Active Directory (Azure AD) és egy MDM-megoldást használ, amely elfogad egy Azure AD-jogkivonatot a hitelesítéshez (jelenleg csak az Microsoft Intune-ban és az AirWatchban támogatott), a rendszergazda konfigurálhatja az Azure AD-t úgy, hogy automatikusan engedélyezze az MDM-regisztrációt, miután a felhasználó bejelentkezett az Azure AD-fiókjával. [Megtudhatja, hogyan konfigurálhatja az Azure AD-regisztrációt.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Ha az automatikus regisztráció engedélyezve van, nincs szükség további manuális regisztrációra. Amikor a felhasználó Azure AD-fiókkal jelentkezik be, az eszköz az első futtatási folyamat befejezése után regisztrálva lesz az MDM-be.

Ha egy eszköz Csatlakozik az Azure AD-hez, az hatással lehet arra, hogy ki tekinthető [az eszköz tulajdonosának.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>A HoloLens Intune-ból való HoloLens-

A regisztrációs módszertől függően előfordulhat, hogy az eszköz regisztrációja nem lesz elérhető.

Ha az eszköz Azure AD-fiókkal vagy Autopilot-fiókkal lett regisztrálva, nem lehet azt az Intune-ból regisztrálni. Ha szeretne lecsatlakozni a HoloLens Azure AD-ről, vagy újracsatlakozni az Azure AD-bérlőhöz, alaphelyzetbe kell [állítania/újra](hololens-recovery.md#reset-the-device) kell perjelesre állítania az eszközt.

Ha az eszköz munkahelyi fiókot hozzáadott MSA-fiókkal lett regisztrálva, vagy egy helyi fiókkal, amely csak eszközkezelésre lett regisztrálva, akkor lehet, hogy az eszköz regisztrációját már nem kell regisztrálnia. Nyissa meg a Start menü, majd válassza Gépház **Alkalmazás-hozzáférés** munkahelyi vagy iskolai  ->    ->  *fiókok leválasztása*  ->  **gomb** lehetőséget.

## <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Győződjön meg arról, hogy az MDM-regisztráció nincs letiltva a Windows eszközökön

Ahhoz, hogy a regisztráció sikeres legyen, meg kell győződni arról, hogy a HoloLens eszközök regisztrálva legyenek. Mivel HoloLens eszköz Windows eszköznek minősül, nincs szükség regisztrációs korlátozásokra, amelyek blokkolni tudnák az üzembe helyezést. [Tekintse át ezt a korlátozáslistát,](/mem/intune/enrollment/enrollment-restrictions-set) és ellenőrizze, hogy regisztrálhatja-e az eszközeit.