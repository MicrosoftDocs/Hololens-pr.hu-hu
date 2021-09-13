---
title: A HoloLens beállítása (1. generációs)
description: Megtudhatja, hogyan állíthatja be HoloLens -t (1. generációs) első alkalommal egy Microsoft- (MSA-Wi-Fi) vagy Azure Active Directory-fiókkal (AAD) egy hálózaton keresztül.
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 06b7142be471d0db3f45812654288a33425abd60
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032780"
---
# <a name="set-up-your-hololens-1st-gen"></a>A HoloLens beállítása (1. generációs)

Az első alkalommal, amikor bekapcsolja a HoloLens, a rendszer végigvezeti az eszköz rendszerén, az eszköz beállításán és a bejelentkezésen.  Ez a cikk végigvezeti az HoloLens (1. generációs) első indítási és beállítási folyamatán.

A következő szakaszban megtudhatja, hogyan dolgozhat a hologramokkal HoloLens és hogyan kommunikálhat a hologramokkal. A cikkre való ugráshoz lásd: Első lépések a HoloLens [(1. generációs)](hololens1-basic-usage.md).

## <a name="before-you-start"></a>Előkészületek

Mielőtt hozzá kezd, győződjön meg arról, hogy a következők állnak rendelkezésre:

**Egy Wi-Fi kapcsolat.** A beállításhoz csatlakoztatnia HoloLens egy Wi-Fi hálózathoz. Az első csatlakozáskor szüksége lesz egy nyílt vagy jelszóval védett hálózatra, amely nem igényel webhely megnyitását vagy tanúsítványokkal való csatlakozást. [További információ a által HoloLens webhelyekről.](hololens-offline.md)

**Egy Microsoft-fiók munkahelyi fiók.** A munkahelyi Microsoft-fiók (vagy munkahelyi fiókkal, ha az eszköz a vállalat tulajdonában van) is HoloLens. Ha még nincs saját Microsoft-fiók, account.microsoft.com és [](https://account.microsoft.com) állítson be egyet ingyenesen.

**Biztonságos, jól világított tér, amely nem jár veszélyekkel.** [Egészségügyi és biztonsági információk.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**Az opcionális kényelmi kiegészítők,** amelyek a HoloLens, segítenek a legkényelmesebb választásban. [További információ a illeszkedésről és a kényelemről.](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - Az első alkalommal, amikor a HoloLens használja, [Cortana](hololens-cortana.md) már be van állítva, és készen áll az Ön útmutatóira (bár addig nem tud válaszolni a kérdéseire, amíg be nem beállította az eszközt). A Cortana bármikor kikapcsolhatja a Cortana beállításaiban.
> - A HoloLens kínai vagy japán verziójára való váltáshoz le kell töltenie a nyelvhez szükséges buildet egy számítógépre, majd telepítenie kell a HoloLens. További információ: [Install localized versions of HoloLens (1st gen)](hololens1-install-localized.md).

## <a name="start-your-hololens-and-set-up-windows"></a>Indítsa el a Hololenst, és állítsa be Windows

Az első alkalommal, amikor elindítja a HoloLens, az első feladat a Holographic Windows beállítása az eszközön.

1. Csatlakozás az internetre (HoloLens végigvezeti a hálózat Wi-Fi kiválasztásán).

1. Jelentkezzen be a felhasználói fiókjába. Válasszon a **Saját munkahelyi vagy iskolai tulajdonom és** az én **tulajdonom közül.**
    - Ha a Saját munkahelyi vagy iskolai tulajdonú lehetőséget **választja,** egy Azure AD-fiókkal jelentkezik be. Ha a szervezet prémium szintű Azure AD és konfigurálta az automatikus MDM-regisztrációt, a HoloLens regisztrál az MDM-be. Ha a szervezet nem használ prémium szintű Azure AD, az automatikus MDM-regisztráció nem érhető el, ezért manuálisan kell regisztrálnia HoloLens [eszközkezelésben.](hololens-enroll-mdm.md#different-ways-to-enroll) Az eszközre a következő lépésekkel lehet először bejelentkezni munkahelyi vagy iskolai fiókkal:
        1. Adja meg a szervezeti fiók adatait.
        1. Fogadja el az adatvédelmi nyilatkozatot.
        1. Jelentkezzen be Azure AD-beli hitelesítő adataival. Ez átirányítható a szervezet bejelentkezési oldalára.
        1. Folytassa az eszköz beállítását.
    - Ha a Saját **tulajdonom lehetőséget választja,** egy új alkalmazás használatával Microsoft-fiók. A telepítés befejezése után manuálisan regisztrálhatja a HoloLens [eszközkezelésben.](hololens-enroll-mdm.md#different-ways-to-enroll)
        1. Adja meg Microsoft-fiók adatait.
        1. Írja be a jelszót. Ha a Microsoft-fiók [kétlépéses ellenőrzést (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)igényel, akkor teljes körű ellenőrzési folyamatot kell végrehajtania.

1. Az eszköz az időzónát a hálózatról lekért információk alapján állítja Wi-Fi alapján.

## <a name="calibration"></a>Kalibrációs

Miután Cortana bemutatja magát, a következő beállítási lépés az átkattatás. A legjobb HoloLens érdekében a beállítás során el kell készítenie a vizsgálat folyamatát.

HoloLens (1. generációs) a távolság a pupillák (IPD vagy [interpupillary distance)](https://en.wikipedia.org/wiki/Interpupillary_distance)távolságát használja a hologramok egyértelművé és könnyen kezelhetővé válta érdekében. Ha az IPD helytelen, a hologramok instabilnak vagy helytelen távolságnak hatnak.

A HoloLens során a rendszer arra kéri, hogy igazítsa az ujjlenyomatát egy szemenkénti hat célsorozattal. HoloLens ezzel a folyamattal állíthatja be a helyes IPD-t a szemének. Ha egy új felhasználó számára frissíteni vagy módosítani kell a színreszibrációt, az új felhasználó a beállításon kívül is futtathatja a Hibakezelő alkalmazást.

![AZ IPD-ujjlenyomat igazítása a második lépésben.](./images/ipd-finger-alignment-300px.jpg)

*AZ IPD-ujjlenyomat igazítása a második lépésben*

Gratulálunk! A telepítés befejeződött, és megkezdheti a HoloLens.

## <a name="next-steps"></a>Következő lépések

> [!div class="nextstepaction"]
> [Első lépések a HoloLens (1. generációs)](hololens1-basic-usage.md)
