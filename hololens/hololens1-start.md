---
title: A HoloLens (1. generációs) beállítása
description: Megtudhatja, hogyan állíthatja be első alkalommal Wi-Fi a HoloLens -t (1. generációs) egy Microsoft- (MSA-) vagy Azure Active Directory-fiókkal (AAD) egy hálózaton keresztül.
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
ms.openlocfilehash: f0ec62e55f15fda6d5a8304ea2bb77039d644b9e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378075"
---
# <a name="set-up-your-hololens-1st-gen"></a>A HoloLens beállítása (1. generációs)

Az első alkalommal, amikor bekapcsolja a HoloLenst, a rendszer végigvezeti az eszköz calibibálásán, az eszköz beállításán és a bejelentkezésen.  Ez a cikk végigvezeti a HoloLens (1. generációs) első indítási és beállítási folyamatán.

A következő szakaszban megtudhatja, hogyan dolgozhat a HoloLens-sel, és hogyan kommunikálhat hologramokkal. A cikkre való ugráshoz lásd: [Get started with HoloLens (1st gen) (A HoloLens első lépései (1. generációs)](hololens1-basic-usage.md)).

## <a name="before-you-start"></a>Előkészületek

Mielőtt hozzá kezd, győződjön meg arról, hogy a következők állnak rendelkezésre:

**Egy Wi-Fi kapcsolat.** A beállításhoz csatlakoztatnia kell a HoloLenst egy Wi-Fi hálózathoz. Az első csatlakozáskor szüksége lesz egy nyílt vagy jelszóval védett hálózatra, amely nem igényel webhely megnyitását vagy tanúsítványokkal való csatlakozást. [További információ a HoloLens](hololens-offline.md)által használt webhelyekről.

**Egy Microsoft-fiók munkahelyi fiók.** A HoloLensbe való bejelentkezéshez szükség lesz egy Microsoft-fiók -fiókra (vagy egy munkahelyi fiókra, ha az eszköz a szervezet tulajdonában van). Ha még nincs saját Microsoft-fiók, account.microsoft.com [és](https://account.microsoft.com) állítson be egyet ingyenesen.

**Biztonságos, jól világított tér, amely nem jár veszélyekkel.** [Egészségügyi és biztonsági információk.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**A** HoloLenshez választható kényelmi kiegészítők a legkényelmesebb illeszkedés érdekében. [További információ a illeszkedésről és a kényelemről.](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - Amikor első alkalommal használja a HoloLenst, [Cortana](hololens-cortana.md) már be van kapcsolva és készen áll az Ön útmutatóira (bár az eszköz beállítását követően nem tud válaszolni a kérdéseire). Cortana beállításait bármikor kikapcsolhatja.
> - A HoloLens kínai vagy japán verziójára való váltáshoz le kell töltenie a nyelvhez szükséges buildet egy számítógépre, majd telepítenie kell a HoloLensen. További információ: [Install localized versions of HoloLens (1st gen) (A HoloLens (1. generációs)](hololens1-install-localized.md)honosított verzióinak telepítése).

## <a name="start-your-hololens-and-set-up-windows"></a>Indítsa el a Hololenst, és állítsa be a Windowst

Amikor először indítja el a HoloLenst, az első feladata a Windows Holographic beállítása az eszközön.

1. Csatlakozás az internethez (a HoloLens végigvezeti a hálózat Wi-Fi kiválasztásán).

1. Jelentkezzen be a felhasználói fiókjába. Válasszon a **saját munkahelyi vagy iskolai tulajdonom és** az én **tulajdonom közül.**
    - Ha a Saját munkahelyi vagy iskolai tulajdonú lehetőséget **választja,** egy Azure AD-fiókkal jelentkezik be. Ha a szervezet prémium szintű Azure AD és konfigurálta az automatikus MDM-regisztrációt, a HoloLens automatikusan regisztrál az MDM-be. Ha a szervezet nem használ prémium szintű Azure AD, az automatikus MDM-regisztráció nem érhető el, ezért manuálisan kell regisztrálnia a [HoloLenst az eszközkezelésben.](hololens-enroll-mdm.md#different-ways-to-enroll) Az eszközre a következő lépésekkel lehet először bejelentkezni munkahelyi vagy iskolai fiókkal:
        1. Adja meg a szervezeti fiók adatait.
        1. Fogadja el az adatvédelmi nyilatkozatot.
        1. Jelentkezzen be Azure AD-beli hitelesítő adataival. Ez átirányítható a szervezet bejelentkezési oldalára.
        1. Folytassa az eszköz beállítását.
    - Ha a Saját **tulajdonom lehetőséget választja,** egy új alkalmazás használatával Microsoft-fiók. A telepítés befejezése után manuálisan regisztrálhatja [a HoloLenst az eszközkezelésben.](hololens-enroll-mdm.md#different-ways-to-enroll)
        1. Adja meg Microsoft-fiók adatait.
        1. Írja be a jelszót. Ha a Microsoft-fiók [kétlépéses ellenőrzést (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)igényel, akkor teljes körű ellenőrzési folyamatot kell végrehajtania.

1. Az eszköz az időzónát a hálózati hálózatról Wi-Fi alapján állítja be.

## <a name="calibration"></a>Kalibrációs

Miután Cortana bemutatkozik, a következő beállítási lépés az lesz. A legjobb HoloLens-élmény érdekében a beállítás során el kell készítenie a hitelesítési folyamatot.

A HoloLens (1. generációs) a pupillák távolságát (IPD vagy [interpupillary distance)](https://en.wikipedia.org/wiki/Interpupillary_distance)használja a hologramok egyértelművé és könnyen kezelhetővé vált érdekében. Ha az IPD helytelen, a hologramok instabilnak vagy helytelen távolságnak hatnak.

A hitelesítés során HoloLens arra kéri, hogy igazítsa az ujjlenyomatát egy szemenkénti hat célsorozattal. HoloLens ezzel a folyamattal adja meg a helyes IPD-t a szemének. Ha egy új felhasználó számára frissíteni vagy módosítani kell a színreszibrációt, az új felhasználó a beállításon kívül is futtathatja az Újalkalmazást.

![AZ IPD-ujjlenyomat igazítása a második lépésben](./images/ipd-finger-alignment-300px.jpg)

*AZ IPD-ujjlenyomat igazítása a második lépésben*

Gratulálunk! A telepítés befejeződött, és megkezdheti a HoloLens használatának megkezdését.

## <a name="next-steps"></a>Következő lépések

> [!div class="nextstepaction"]
> [A HoloLens (1. generációs) első lépések](hololens1-basic-usage.md)
