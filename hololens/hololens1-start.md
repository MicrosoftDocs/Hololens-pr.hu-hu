---
title: A HoloLens beállítása (1. generációs)
description: Megtudhatja, hogyan állíthatja be HoloLens (1. generációs) első alkalommal egy Microsoft- (MSA-) vagy Azure Active Directory- (AAD-) fiókkal az Wi-Fi-hálózaton keresztül.
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
ms.openlocfilehash: 9e09ba1a022428b098392464e5cd2abf84911bd6a86d8e699036b8fc4f91470a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661857"
---
# <a name="set-up-your-hololens-1st-gen"></a>A HoloLens beállítása (1. generációs)

Az első alkalommal, amikor bekapcsolja a HoloLens, a rendszer végigvezeti az eszköz rendszerén, az eszköz beállításán és a bejelentkezésen.  Ez a cikk végigvezeti az HoloLens (1. generációs) első indítási és beállítási folyamatán.

A következő szakaszban megtudhatja, hogyan dolgozhat a HoloLens és hogyan kommunikálhat a hologramokkal. A cikkre való ugráshoz lásd: Első lépések a HoloLens [(1. generációs)](hololens1-basic-usage.md).

## <a name="before-you-start"></a>Előkészületek

Mielőtt hozzá is kezd, győződjön meg arról, hogy az alábbiak elérhetők:

**Egy Wi-Fi kapcsolat.** A beállításhoz a HoloLens egy Wi-Fi kell csatlakoztatnia. Az első csatlakozáskor szüksége lesz egy nyílt vagy jelszóval védett hálózatra, amely nem igényel webhelyre való navigálást vagy tanúsítványokat a csatlakozáshoz. [További információ a által HoloLens webhelyekről.](hololens-offline.md)

**Egy Microsoft-fiók munkahelyi fiók.** A fiókba való bejelentkezéshez egy Microsoft-fiók (vagy egy munkahelyi fiókot, ha az eszköz a vállalat tulajdonában van) is HoloLens. Ha még nem Microsoft-fiók, account.microsoft.com ingyenes beállítását. [](https://account.microsoft.com)

**Biztonságos, jól meggyújtott hely, amely nem jár veszélyekkel.** [Egészségügyi és biztonsági információk.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**Az opcionális kényelmi kiegészítők,** amelyek a HoloLens, a legkényelmesebb illeszkedés érdekében. [További információ a illeszkedésről és a kényelemről.](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - Az első alkalommal, amikor a HoloLens [használja, Cortana](hololens-cortana.md) már be van állítva, és készen áll arra, hogy útmutatást adjon Önnek (bár csak az eszköz beállítása után tud válaszolni a kérdéseire). A Cortana bármikor kikapcsolhatja a Cortana beállításaiban.
> - A HoloLens kínai vagy japán verziójára való váltáshoz le kell töltenie a nyelvhez szükséges buildet a számítógépre, majd telepítenie kell a HoloLens. További információkért lásd: [Install localized versions of HoloLens (1st gen)](hololens1-install-localized.md)..

## <a name="start-your-hololens-and-set-up-windows"></a>Indítsa el a Hololenst, és állítsa be Windows

Az első alkalommal, amikor elindítja a HoloLens, az első feladata a Holographic Windows beállítása az eszközön.

1. Csatlakozás az internetre (HoloLens segítségével kiválaszthatja a Wi-Fi hálózatot).

1. Jelentkezzen be a felhasználói fiókjába. Válasszon a **Saját munkahelyi vagy iskolai tulajdona és** az én **tulajdonom közül.**
    - Ha a Saját munkahelyi vagy iskolai tulajdonú lehetőséget **választja,** egy Azure AD-fiókkal jelentkezik be. Ha a szervezet prémium szintű Azure AD és konfigurálta az automatikus MDM-regisztrációt, a HoloLens is regisztrál az MDM-be. Ha a szervezet nem használ prémium szintű Azure AD, az automatikus MDM-regisztráció nem érhető el, ezért manuálisan kell regisztrálnia HoloLens [eszközkezelésben.](hololens-enroll-mdm.md#different-ways-to-enroll) Az eszközre való első bejelentkezéshez munkahelyi vagy iskolai fiókkal kövesse az alábbi lépéseket:
        1. Adja meg a szervezeti fiók adatait.
        1. Fogadja el az adatvédelmi nyilatkozatot.
        1. Jelentkezzen be az Azure AD-beli hitelesítő adataival. Ez átirányíthatja a szervezet bejelentkezési oldalára.
        1. Folytassa az eszköz beállítását.
    - Ha a **Saját tulajdonom lehetőséget választja,** egy új alkalmazás használatával Microsoft-fiók. A telepítés befejezése után manuálisan regisztrálhatja a HoloLens [eszközkezelésben.](hololens-enroll-mdm.md#different-ways-to-enroll)
        1. Adja meg Microsoft-fiók adatait.
        1. Írja be a jelszót. Ha a Microsoft-fiók [kétlépéses ellenőrzést (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)igényel, akkor teljes körű ellenőrzési folyamatot kell végrehajtania.

1. Az eszköz az időzónát az alapján állítja be, hogy az a hálózati Wi-Fi-e.

## <a name="calibration"></a>Kalibrációs

Miután Cortana bemutatja magát, a következő beállítási lépés a hiba. A legjobb HoloLens érdekében a beállítás során el kell készítenie a hitelesítési folyamatot.

HoloLens (1. generációs) a tanulók távolságát (IPD vagy [interpupillary distance)](https://en.wikipedia.org/wiki/Interpupillary_distance)használja a hologramok egyértelművé és könnyen kezelhetővé vált érdekében. Ha az IPD helytelen, a hologramok instabilnak vagy helytelen távolságnak hatnak.

A terhesség alatt HoloLens, hogy az ujjlenyomatát egy szemenként hat célsorozattal igazítsa. HoloLens ezzel a folyamattal állíthatja be a helyes IPD-t a szemének. Ha egy új felhasználónál frissíteni vagy módosítani kell a tudatot, az új felhasználó a beállításon kívül is futtathatja a Felhasználóbarát alkalmazást.

![AZ IPD-ujjlenyomat igazítása képernyő a második lépésben](./images/ipd-finger-alignment-300px.jpg)

*AZ IPD-ujjlenyomat igazítása képernyő a második lépésben*

Gratulálunk! A telepítés befejeződött, és megkezdheti a HoloLens.

## <a name="next-steps"></a>Következő lépések

> [!div class="nextstepaction"]
> [Első lépések a HoloLens (1. generációs)](hololens1-basic-usage.md)
