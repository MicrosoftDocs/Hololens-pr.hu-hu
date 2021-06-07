---
title: Rendszergazdai jogosultsággal nem kapcsolatos operációsrendszer-biztonság
description: További információ a rendszergazda nélküli operációs rendszerekről, az eszköztulajdonosokról és a biztonságról a HoloLens vegyes valóságú eszközökön.
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
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379557"
---
# <a name="admin-less-operating-system"></a>Rendszergazdai jogosultságokkal nem működő operációs rendszer

A HoloLens 2 minimálisra csökkenti a jogosultságok eszkalálásának felületét azáltal, hogy letiltja a Rendszergazdák csoport támogatását, és korlátozza az összes külső UWP-alkalmazáskód végrehajtását, hogy csak általános jogú felhasználókként futtason az AppContainer-védőfalon belül. Ez a kód csak olyan képességek által védett erőforrásokhoz kap hozzáférést, amelyek explicit módon az alkalmazásban egy nem védett felhasználó számára vannak megszabadulva az összes AppContainers számára elérhető erőforrások mellett.
Ezek az alkalmazásképességek továbbra is a háromszintű besorolási modellel rendelkeznek:
  * Általános kérdések
  * Korlátozott hozzáférésű
  * Windows

A Windows-összetevők az AppContainer-védőfalat is kihasználják a rendszer UWPs-ekkel. A (UWP Univerzális Windows-platform (UWP) alkalmazásokkal kapcsolatos további információkért lásd az [UWP dokumentációját.](https://docs.microsoft.com/windows/uwp/) Emellett a nagyobb jogosultságcsökkentési igényekkel rendelkező Windows-összetevők (például a böngészőtartalom oldalai vagy elemzői) a Less Privileged AppContainer (LPAC) védőfalat használják, amely az összes AppContainers számára elérhető erőforráskészlethez való hozzáférést csökkenti.

## <a name="device-owner"></a>Az eszköz tulajdonosa

Végezetül, az eszközre vonatkozó adott műveletek végrehajtása, például az eszköz bérlőhöz vagy felhasználókezeléshez való csatlakozása csak az "eszköztulajdonosok" számára engedélyezett. Ezt a csoportot az eszközön található felhasználók töltik ki az alábbi lépések egyikével:
  * Az eszköz első felhasználója mindig Tulajdonosként van ki jelölni. 
> [!IMPORTANT]
>Az Azure AD-felhasználók kivételt képeznek ez alól a szabály alól, ha az eszköz Autopilot- vagy tömeges Azure AD-regisztráción keresztül csatlakozik az Azure AD-hez, amely nem valós felhasználót használ. Ebben az esetben előfordulhat, hogy az első AAD-felhasználó, aki bejelentkezik az eszközre, nem lesz automatikusan eszköztulajdonos, kivéve, ha a felhasználó rendelkezik hozzárendelt "globális rendszergazda" vagy "eszköz-rendszergazda" Azure Portal. További információért tekintse meg az alábbi megjegyzést.  

  * Ha egy felhasználót tulajdonosként léptet elő a Beállítások felhasználói felületről egy másik tulajdonos az eszközön.
  * Ha az eszköz tulajdonosa már nem érhető el (elhagyja a vállalatot), és az eszköz Csatlakozik az Azure AD-hez, a bérlői rendszergazda új felhasználóra módosíthatja az eszköz tulajdonosát a Azure Portal. Az Azure AD-bérlő globális rendszergazdái és eszköz-rendszergazdái implicit módon tulajdonosokként jelentkeznek be az eszközön anélkül, hogy az előző lépések valamelyikére szükség volna.  

 A rendszergazdák az adatvédelmi szabályzatok segítségével kezelhetik, hogy mely alkalmazások [férhetnek](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) hozzá. 

> [!NOTE]
> Ha többet szeretne tudni arról, hogy ki lett eszköztulajdonos egy Azure AD-hez csatlakozott eszközön, tekintse meg a "Helyi rendszergazda [hozzárendelése"](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) dokumentációt (de olvassa el a "helyi rendszergazda" adatokat eszköztulajdonosként, mivel a rendszergazda nem létezik a HoloLensben).