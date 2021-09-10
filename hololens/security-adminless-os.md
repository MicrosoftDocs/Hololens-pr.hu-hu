---
title: Rendszergazdai jogosultsággal nem kapcsolatos operációsrendszer-biztonság
description: Ismerje meg a rendszergazda nélküli operációs rendszereket, az eszköztulajdonosokat és a biztonságot HoloLens vegyes valóságú eszközökön.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, adminless, admin-less, operating system, admin-less operating system, admin os, admin-less os, hololens 2, hololens2 security,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427471"
---
# <a name="admin-less-operating-system"></a>Rendszergazdai jogosultságokkal nem működő operációs rendszer

HoloLens 2. beállítás minimálisra csökkenti a jogosultságok eszkalálásának felületét azáltal, hogy letiltja a Rendszergazdák csoport támogatását, és úgy korlátozza az összes külső UWP-alkalmazáskódot, hogy az alkalmazás csak általános jogú felhasználóként legyen végrehajtva az AppContainer-védőfalon belül. Ez a kód csak az összes AppContainers számára elérhető erőforrásokon kívül csak olyan képességek által védett erőforrásokhoz kap hozzáférést, amelyek explicit módon az alkalmazásban egy nem védett felhasználó számára vannak megszabadulva.
Ezek az alkalmazásképességek továbbra is a háromszintű besorolási modellel rendelkeznek:
  * Általános kérdések
  * Korlátozott hozzáférésű
  * Windows

Windows összetevők az AppContainer-védőfalat is kihasználják a rendszer UWPs-ekkel. A Universal Windows Platformról (UWP) az [UWP dokumentációjában talál további információt.](/windows/uwp/) Emellett a nagyobb jogosultságcsökkentési igényekkel rendelkező Windows-összetevők (például a böngésző tartalomoldalai vagy elemzői) a Less Privileged AppContainer (LPAC) védőfalat használják, amely csökkenti az összes AppContainers számára elérhető erőforráskészlethez való hozzáférést.

## <a name="device-owner"></a>Az eszköz tulajdonosa

Végezetül, az eszközre vonatkozó adott műveletek végrehajtása, például az eszköz bérlőhöz vagy felhasználókezeléshez való csatlakozása csak az "eszköztulajdonosok" számára engedélyezett. Ezt a csoportot az eszközön található felhasználók töltik ki az alábbi lépések egyikével:
  * Az eszköz első felhasználója mindig Tulajdonosként van ki jelölni. 
> [!IMPORTANT]
>Az Azure AD-felhasználók kivételt képeznek ez alól a szabály alól, ha az eszköz Autopilot- vagy tömeges Azure AD-regisztráción keresztül csatlakozik az Azure AD-hez, amely nem valós felhasználót használ. Ebben az esetben előfordulhat, hogy az eszközre való első AAD-felhasználó nem lesz automatikusan az eszköz tulajdonosa, kivéve, ha a felhasználóhoz hozzá van rendelve a "globális rendszergazda" vagy az "Azure Portal. További információért tekintse meg az alábbi megjegyzést.  

  * Ha egy felhasználót tulajdonosként léptetnek elő a felhasználói Gépház egy másik tulajdonossal az eszközön.
  * Ha az eszköz tulajdonosa már nem érhető el (elhagyja a vállalatot), és az eszköz Csatlakozik az Azure AD-hez, a bérlői rendszergazda új felhasználóra módosíthatja az eszköz tulajdonosát a Azure Portal. Az Azure AD-bérlő globális rendszergazdái és eszköz-rendszergazdái implicit módon tulajdonosokként jelentkeznek be az eszközön anélkül, hogy az előző lépések valamelyikére szükség volna.  

 A rendszergazdák adatvédelmi szabályzatokkal kezelhetik, hogy mely alkalmazások [férhetnek](/windows/client-management/mdm/policy-csp-privacy) hozzá. 

> [!NOTE]
> Ha többet szeretne tudni arról, hogy ki lett eszköztulajdonos egy Azure AD-hez csatlakozott eszközön, tekintse meg a ["Helyi](/azure/active-directory/devices/assign-local-admin) rendszergazda hozzárendelése" dokumentációt (de olvassa el a "helyi rendszergazda" adatokat eszköztulajdonosként, mivel a rendszergazda nem létezik a HoloLens).