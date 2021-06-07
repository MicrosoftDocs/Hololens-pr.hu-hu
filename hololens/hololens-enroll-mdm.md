---
title: HoloLens regisztrálása az MDM-be
description: Megtudhatja, hogyan regisztrálhat HoloLenst a mobileszköz-felügyeletben (MDM) több eszköz egyszerűbb kezelése érdekében.
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378154"
---
# <a name="enroll-hololens-in-mdm"></a>HoloLens regisztrálása az MDM-be

Egyidejűleg több Microsoft HoloLens is felügyelhet olyan megoldásokkal, mint a [Microsoft Intune.](https://docs.microsoft.com/intune/windows-holographic-for-business) Kezelheti a beállításokat, kiválaszthatja az alkalmazásokat a szervezet igényeihez igazított biztonsági konfigurációk telepítéséhez és beállításhoz. Lásd: [A Windows Holographic](https://docs.microsoft.com/intune/windows-holographic-for-business)rendszert futtató eszközök kezelése a Microsoft Intune segítségével, a Windows Holographic által támogatott konfigurációszolgáltatók [(CSP-k)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)és a [Windows Holographic for Business.](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)

> [!NOTE]
> A mobileszköz-felügyelet (MDM), beleértve a VPN-t, a Bitlockert és a kioszkmódot is, csak akkor érhető el, ha az -ra [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

## <a name="requirements"></a>Követelmények

 A holoLens-eszközök kezeléséhez Eszközkezelés mobile Eszközkezelés (MDM) kell beállítania a szervezetének. Az MDM-szolgáltató lehet Microsoft Intune microsoftos MDM API-kat használó külső szolgáltató.
 
## <a name="different-ways-to-enroll"></a>A regisztráció különböző módjai

Az OOBE vagy a bejelentkezés után [kiválasztott](hololens-identity.md) identitás típusától függően különböző regisztrációs módszerek állnak a létezik.

- Ha az Identity az Azure AD, akkor az OOBE vagy a **Beállítások** alkalmazás-hozzáférés  ->  **munkahelyi vagy iskolai csatlakozás**  ->  **gombja során.**
    - Az Azure AD esetén az [automatikus MDM-regisztráció](hololens-enroll-mdm.md#auto-enrollment-in-mdm) csak akkor történik meg, ha az Azure AD-t regisztrációs URL-címekkel konfigurálták.
     
- Ha az Identity az Azure AD, és az eszköz előre regisztrálva van az Intune MDM-kiszolgálón, és hozzá van rendelve egy adott konfigurációs profil, akkor az Azure AD-Join és az automatikus [MDM-regisztráció](hololens-enroll-mdm.md#auto-enrollment-in-mdm) az OOBE során történik.
    - Más néven [AutoPilot-folyamat](hololens2-autopilot.md) Az [19041.1103+-buildek érhetők el.](hololens-release-notes.md#windows-holographic-version-2004)
    

- Ha az Identity az MSA, használja a **Settings App** Access Work  ->  **vagy School**  ->  **Connect** gombot.
    - Más néven Munkahelyi fiók hozzáadása (AWA) folyamat.
- Ha az Identitás helyi felhasználó, akkor a **Beállítások alkalmazás-hozzáférés** munkahelyi vagy iskolai regisztráció  ->    ->  **csak az eszközkezelési hivatkozáson keresztül.**
    - Más néven tiszta MDM-regisztrációs folyamat.

Miután regisztrálta az eszközt az MDM-kiszolgálón, a Beállítások alkalmazás azt fogja tükrözni, hogy az eszköz regisztrálva van az eszközkezelésben.

## <a name="auto-enrollment-in-mdm"></a>Automatikus regisztráció az MDM-be

Ha a szervezet rendelkezik Azure Premium-előfizetéssel, a Azure Active Directory (Azure AD) és egy MDM-megoldást használ, amely Azure AD-jogkivonatot fogad el a hitelesítéshez (jelenleg csak az Microsoft Intune és az AirWatch támogatja), a rendszergazda konfigurálhatja az Azure AD-t úgy, hogy automatikusan engedélyezze az MDM-regisztrációt, miután a felhasználó bejelentkezett Azure AD-fiókjával. [](https://azure.microsoft.com/overview/) [Megtudhatja, hogyan konfigurálhatja az Azure AD-regisztrációt.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Ha az automatikus regisztráció engedélyezve van, nincs szükség további manuális regisztrációra. Amikor a felhasználó Azure AD-fiókkal jelentkezik be, az eszköz az első futtatás befejezése után regisztrálva lesz az MDM-be.

Ha egy eszköz Azure AD-hez csatlakozik, az hatással lehet arra, hogy ki tekinthető [az eszköz tulajdonosának.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>HoloLens intune-nal való intune-igénylésének igénylése

A regisztrációs módszertől függően előfordulhat, hogy az eszköz regisztrációja nem lesz elérhető.

Ha az eszköz Azure AD-fiókkal vagy Autopilot-fiókkal lett regisztrálva, nem lehet azt az Intune-ból regisztrálni. Ha le szeretné állítani a HoloLenst az Azure AD-ről, vagy egy másik Azure AD-bérlőhöz szeretné újracsatlakozni, alaphelyzetbe kell [állítania/újra](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) kell perjelesre állítania az eszközt.

Ha az eszköz munkahelyi fiókot hozzáadott MSA-fiókból vagy egy helyi fiókból lett regisztrálva, amely csak eszközkezelésre lett regisztrálva, akkor az eszköz regisztrációját is megszűkítheti. Nyissa meg a Start menü, majd válassza a **Settings App** Access Work or School YourAccount Disconnect (Alkalmazás-hozzáférés munkahelyi vagy iskolai fiók  ->    ->  *leválasztása)*  ->  **gombot.**