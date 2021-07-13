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
ms.openlocfilehash: 6c279664fa6051fab2f5e2e8f61e70b55704ae7c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640406"
---
# <a name="enroll-hololens-in-mdm"></a>Regisztráció HoloLens MDM-be

Egyidejűleg több Microsoft HoloLens is felügyelhet olyan megoldásokkal, mint a [Microsoft Intune.](/intune/windows-holographic-for-business) Kezelheti a beállításokat, kiválaszthatja a telepíteni kívánt alkalmazásokat, és beállíthatja a szervezet igényeihez igazított biztonsági konfigurációkat. Lásd: A [Holographic Windows-t](/intune/windows-holographic-for-business)futtató eszközök kezelése a Microsoft Intune segítségével, a Windows Holographic által támogatott konfigurációszolgáltatók [(CSP-k)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)és a [Windows Holographic for Business.](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)

> [!NOTE]
> A mobileszköz-kezelés (MDM), beleértve a VPN- és BitLocker- és kioszkmódú funkciókat is, csak akkor érhető el, ha az [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

## <a name="requirements"></a>Követelmények

 A cégének be kell állítania a Mobile Eszközkezelés (MDM) eszközt a mobileszközök HoloLens kezeléséhez. Az MDM-szolgáltató lehet Microsoft Intune microsoftos MDM API-kat használó külső szolgáltató.
 
## <a name="different-ways-to-enroll"></a>A regisztrálás különböző módjai

Az OOBE [vagy](hololens-identity.md) a bejelentkezés után választott identitás típusától függően különböző regisztrációs módszerek állnak a létezik.

- Ha az Identity az Azure AD, akkor az OOBE vagy Gépház **alkalmazás-hozzáférés** munkahelyi vagy iskolai Csatlakozás  ->    ->   gombra.
    - Az Azure AD esetén az [automatikus MDM-regisztráció](hololens-enroll-mdm.md#auto-enrollment-in-mdm) csak akkor történik meg, ha az Azure AD-t regisztrációs URL-címekkel konfigurálták.
     
- Ha az Identity az Azure AD, és az eszköz előre regisztrálva van az Intune MDM-kiszolgálón, és hozzá van rendelve egy adott konfigurációs profil, akkor az Azure AD-Join és az automatikus [MDM-regisztráció](hololens-enroll-mdm.md#auto-enrollment-in-mdm) az OOBE során történik.
    - Más néven [Autopilot-folyamat](hololens2-autopilot.md) Az [19041.1103-](hololens-release-notes.md#windows-holographic-version-2004)buildek alatt érhető el.
    

- Ha az Identity az MSA, akkor használja **Gépház Alkalmazás-hozzáférés** munkahelyi vagy iskolai  ->    ->  **Csatlakozás** gombot.
    - Más néven Munkahelyi fiók hozzáadása (AWA) folyamat.
- Ha az Identitás helyi felhasználó, akkor Gépház **alkalmazás-hozzáférés** munkahelyi vagy iskolai regisztrációja csak az  ->    ->  **eszközkezelési hivatkozáson keresztül.**
    - Más néven tiszta MDM-regisztrációs folyamat.

Miután regisztrálta az eszközt az MDM-kiszolgálón, az Gépház azt fogja tükrözni, hogy az eszköz regisztrálva van az eszközkezelésben.

## <a name="auto-enrollment-in-mdm"></a>Automatikus regisztráció az MDM-be

Ha a szervezet azure Prémium-előfizetéssel rendelkezik, akkor az Azure Active Directory (Azure AD) és egy MDM-megoldást használ, amely elfogad egy [Azure](https://azure.microsoft.com/overview/)AD-jogkivonatot a hitelesítéshez (jelenleg csak az Microsoft Intune és az AirWatch támogatja), a rendszergazda konfigurálhatja az Azure AD-t úgy, hogy automatikusan engedélyezze az MDM-regisztrációt, miután a felhasználó bejelentkezett az Azure AD-fiókjával. [Megtudhatja, hogyan konfigurálhatja az Azure AD-regisztrációt.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Ha az automatikus regisztráció engedélyezve van, nincs szükség további manuális regisztrációra. Amikor a felhasználó Azure AD-fiókkal jelentkezik be, az eszköz az első futtatási folyamat befejezése után regisztrálva lesz az MDM-be.

Ha egy eszköz Csatlakozik az Azure AD-hez, az hatással lehet arra, hogy ki tekinthető [az eszköz tulajdonosának.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>A HoloLens Intune-ból való HoloLens-

A regisztrációs módszertől függően előfordulhat, hogy az eszköz regisztrációja nem lesz elérhető.

Ha az eszköz Azure AD-fiókkal vagy Autopilot-fiókkal lett regisztrálva, nem lehet azt az Intune-ból regisztrálni. Ha szeretne lecsatlakozni a HoloLens Azure AD-ről, vagy újracsatlakozni az Azure AD-bérlőhöz, alaphelyzetbe kell [állítania/újra](hololens-recovery.md#reset-the-device) kell perjelesre állítania az eszközt.

Ha az eszköz munkahelyi fiókot hozzáadott MSA-fiókkal lett regisztrálva, vagy egy helyi fiókkal, amely csak eszközkezelésre lett regisztrálva, akkor lehet, hogy az eszköz regisztrációját már nem kell regisztrálnia. Nyissa meg a Start menü, majd válassza Gépház **alkalmazás-hozzáférés** munkahelyi vagy iskolai  ->    ->  *fiókok leválasztása*  ->  **gombját.**