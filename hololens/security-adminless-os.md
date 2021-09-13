---
title: Rendszergazdai jogosultsággal nem kapcsolatos operációsrendszer-biztonság
description: Ismerje meg a rendszergazda nélküli operációs rendszereket, az eszköztulajdonosokat és a biztonságot HoloLens vegyes valóságú eszközökön.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: biztonság, hololens, adminless, admin-less, operating system, admin-less operating system, admin os, admin-less os, hololens 2, hololens2 security,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036247"
---
# <a name="admin-less-operating-system"></a>Rendszergazdai jogosultságokkal nem működő operációs rendszer

HoloLens 2. beállítás minimálisra csökkenti a jogosultságok eszkalálására vonatkozó felületet azáltal, hogy letiltja a Rendszergazdák csoport támogatását, és korlátozza az összes külső UWP-alkalmazáskód végrehajtását, hogy csak általános jogú felhasználókként futnak az AppContainer-védőfalon belül. Ez a kód csak olyan képességek által védett erőforrásokhoz kap hozzáférést, amelyek explicit módon az alkalmazásban egy nem védett felhasználó számára vannak megszabadulva, valamint az összes AppContainers számára elérhető erőforrásokhoz.
Ezek az alkalmazásképességek továbbra is a háromszintű besorolási modellel rendelkeznek:
  * Általános kérdések
  * Korlátozott hozzáférésű
  * Windows

Windows összetevők az AppContainer-védőfalat is kihasználják a rendszer UWPs-ekkel. A Universal Windows Platformról (UWP) az [UWP dokumentációjában talál további információt.](/windows/uwp/) Emellett a nagyobb jogosultságcsökkentési igényekkel rendelkező Windows-összetevők (például a böngészőtartalom oldalai vagy elemzői) a Less Privileged AppContainer (LPAC) védőkészletet használják, amely csökkenti az összes AppContainers számára elérhető erőforráskészlethez való hozzáférést.

## <a name="device-owner"></a>Az eszköz tulajdonosa

Végezetül, az eszközre vonatkozó adott műveletek végrehajtása, például az eszköz bérlőhöz vagy felhasználókezeléshez való csatlakozása csak az "eszköztulajdonosok" számára engedélyezett. Ezt a csoportot az eszköz felhasználói töltik ki az alábbi lépések egyikével:
  * Az eszköz első felhasználója mindig Tulajdonosként van ki jelölni. 
> [!IMPORTANT]
>Az Azure AD-felhasználók kivételt képeznek ez alól a szabály alól, ha az eszköz Autopilot- vagy tömeges Azure AD-regisztráción keresztül csatlakozik az Azure AD-hez, amely nem valódi felhasználót használ. Ebben az esetben előfordulhat, hogy az első AAD-felhasználó, aki bejelentkezik az eszközre, nem lesz automatikusan eszköztulajdonos, kivéve, ha a felhasználóhoz hozzá van rendelve a "globális rendszergazda" vagy az "eszköz-rendszergazda" Azure Portal. További információért tekintse meg az alábbi megjegyzést.  

  * Ha egy felhasználó tulajdonosi előléptetve lesz a Gépház a felhasználói felületről az eszköz egy másik tulajdonosa.
  * Ha az eszköz tulajdonosa már nem érhető el (elhagyja a vállalatot), és az eszköz csatlakozik az Azure AD-hez, a bérlői rendszergazda új felhasználóra módosíthatja az eszköz tulajdonosát a Azure Portal. Az Azure AD-bérlő globális rendszergazdái és eszköz-rendszergazdái tulajdonosként vannak implicit módon bejelentkezve az eszközön anélkül, hogy az előző lépések valamelyikére szükség volna.  

 A rendszergazdák adatvédelmi szabályzatokkal kezelhetik, hogy mely alkalmazások [férhetnek](/windows/client-management/mdm/policy-csp-privacy) hozzá. 

> [!NOTE]
> Ha többet szeretne tudni arról, hogy ki lett eszköztulajdonos egy Azure AD-hez csatlakozott eszközön, tekintse meg a ["Helyi](/azure/active-directory/devices/assign-local-admin) rendszergazda hozzárendelése" dokumentációt (de olvassa el a "helyi rendszergazda" adatokat eszköztulajdonosként, mivel a rendszergazda nem létezik a HoloLens).