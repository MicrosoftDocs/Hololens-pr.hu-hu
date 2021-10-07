---
title: A HoloLens megosztása több felhasználóval
description: Konfigurálhatja úgy a HoloLens, hogy több fiókkal Azure Active Directory vagy egyetlen fiókot használó több felhasználóval megossanak.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/23/2021
ms.reviewer: anisgup
manager: sean-kerawala
appliesto:
- HoloLens 2
ms.openlocfilehash: bbb955edaa500187ea921538291bb1c7bda05422
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600729"
---
# <a name="share-your-hololens-with-multiple-people"></a>A HoloLens megosztása több felhasználóval

## <a name="overview"></a>Áttekintés

A vállalatok gyakran fektetnek be számos megosztott HoloLens eszközbe. Az egyéni HoloLens függően rugalmasan használhatja a teljes táblát. Az alábbi példa néhány többfelhasználós élményt mutat be:

- Az HoloLens 2 eszközből Windows HoloLens 2.-hez az Windows Autopiloton keresztül állíthat be egy egységes vállalati alkalmazásportfóliót az egyes eszközökön. Több különböző kioszkprofilt is beállított, amelyek különböző Azure AD-csoportokat céloznak meg. Minden felhasználó FIDO2 HoloLens kulcsokkal jelentkezik be a saját Azure AD-fiókjába, és személyre szabott élményt nyújt.
- Egy független szoftverszállító (ISV) HoloLens 2 eszközt bérel a D365 Remote Assist és az üzletági (LOB) alkalmazással az ügyfél vállalatának. Ezek az eszközök olyan kioszkeszközökre vannak konfigurálva, amelyek csak az LOB alkalmazást és a Remote Assist alkalmazást tartalmazzák, és több végfelhasználó között vannak megosztva. A WDAC használatával az alkalmazás Gépház és a Microsoft Edge nem indul el. A kölcsönzés tartalmaz egy USB-C akkumulátorcsomagot, amely több műszakban is teljes mértékben tartja az eszközöket.
- A vállalat végfelhasználója megpróbál módosításokat végezni az Bluetooth-on az új eszköz csatlakoztatása érdekében, de a Page Gépház Visibility szabályzat engedélyezve van, hogy az Eszközök lap ne legyen megtekintve. Szükség szerint továbbra is hozzáférhetnek más oldalakhoz, például a Wi-Fi, így több helyen is használhatnak Remote Assistet ugyanazokkal a HoloLens.

## <a name="best-practices"></a>Ajánlott eljárások

Az eszközök megosztásának tervezésekor több szempontot is figyelembe kell venni az eszközkörnyezet üzleti igényeknek megfelelő optimalizálásához.

- [Identitás és hitelesítés](#identity-and-authentication)
- [Eszközkezelés](#device-management)
- [Speciális eszközkezelés – Kioszk és WDAC](#advanced-device-management---kiosk-and-wdac)
- [Fizikai felügyelet](#physical-management)

### <a name="identity-and-authentication"></a>[Identitás és hitelesítés](hololens-identity.md)

Ha azt tervezi, hogy több fiókot is használ egy eszközön, akkor azure AD-fiókjai vannak, amelyek minden hitelesítési móddal használhatók. Ezek a hitelesítési módszerek a következő [kulcsokon alapulnak Windows Hello](/windows-hardware/design/device-experiences/windows-hello)Iris és FIDO2 kulcsok.

- A FIDO 2 biztonsági kulcsok akkor kiválóak, ha több eszközzel, sok felhasználóval vagy folyamatosan új eszközöket használ.
- Ha 10 vagy kevesebb felhasználója van, az Iris egy gyors megoldás az ugyanazon eszközre korábban bejelentkezett felhasználók bejelentkezésére.

### <a name="device-management"></a>[Eszközkezelés](hololens-csp-policy-overview.md)

Ha az eszközök felhasználók között vannak megosztva, akkor valószínűleg eszközkorlátozásokat szeretne használni. Az eszközkezelés használatával olyan szabályzatokat állíthat be, amelyek lehetővé teszik a felhasználók számára az eszköz használatát, a frissítések kezelését vagy az eszköz által elérhető szolgáltatások korlátozását. Javasoljuk, hogy tekintse át a gyakori [eszközkorlátozásainkat,](hololens-common-device-restrictions.md)és ellenőrizze, hogy ezek a javaslatok illeszkednek-e a szervezetéhez. Ha már tudja, hogy milyen szabályzatokat szeretne használni, alkalmazhatja azokat a Microsoft Endpoint Manager [(MDM)](hololens-mdm-configure.md) vagy kiépítési csomagjaival.

### <a name="advanced-device-management---kiosk-and-wdac"></a>Speciális eszközkezelés – [Kioszk](hololens-kiosk.md) [és WDAC](windows-defender-application-control-wdac.md)

Bizonyos esetekben előfordulhat, hogy korlátozni szeretné, hogy a végfelhasználók milyen alkalmazásokhoz férnek hozzá. A Kioszk mód használatával korlátozhatja, hogy a felhasználók milyen alkalmazásokat jelennek meg a [Start menüben.](hololens-kiosk.md) A kioszk konfigurálható úgy, hogy különböző start menüket kínál fel a felhasználó, az Azure-csoportok vagy a speciális felhasználótípusok alapján; ilyen látogató, vagy az eszköztulajdonosok kizárása. Több alkalmazást is választhat, de akár egyetlen alkalmazást is. A többalkalmazásos kioszkok nem akadályoznak meg egy alkalmazást a másik elindításában, így ha az áruház vagy egy másik alkalmazás elérhető, a felhasználók továbbra is elindíthatnak egy másik alkalmazást.

Azt is előfordulhat, hogy teljesen le szeretné állítani az alkalmazások vagy szolgáltatások elindítását az Windows Defender alkalmazásvezérlés [(WDAC)](windows-defender-application-control-wdac.md) használatával az alkalmazások korlátozásához. A WDAC más, mint a Kioszk, mivel nem módosítja a felhasználói felületet HoloLens hanem nem engedélyezi a letiltott alkalmazások indítását.

[Az Gépház láthatósága](settings-uri-list.md) egy másik módja annak, hogy korlátozásokat adjon hozzá egy eszközhöz. Abban az esetben, ha hozzáférést kell adnunk a felhasználóknak a Gépház-alkalmazás egyes lapjaihoz, de nem Gépház a hozzáférés korlátozására. Ez például akkor hasznos, ha a felhasználóknak módosítaniuk kell a Wi-Fi-t, de nem szeretné, hogy hozzáférjenek a Fiókok laphoz.

### <a name="physical-management"></a>Fizikai felügyelet

Az eszköz több felhasználó közötti megosztásakor fizikai szempontokat is figyelembe kell venni.

- Győződjön meg arról, hogy az eszközök két műszak között kell díjszabást kivetni.
- Ha egy eszközre szükség van egy váltáshoz, és több műszakot is ki kell töltenie, fontolja meg egy külső akkumulátor használatának a elemet a váltás elején, miközben az eszköz továbbra is jelentős díjat számít fel a hőkezelés [irányának megfelelően.](hololens2-charging.md#managing-heat)
- Az eszközök tárolásakor tartsa őket csatlakoztatva és csatlakoztatva a hálózathoz. Ez a legjobb módszer az operációs rendszer és az alkalmazás frissítésének biztosítására.
- Gondolja át, hogyan tervezi megtisztítani [az eszközt a](hololens2-maintenance.md) felhasználók között.
- Ha egy megosztott PIN-kódot/jelszót használ egyetlen felhasználóhoz egy megosztott felhasználóval, ne helyezze a PIN-kódot/jelszót az eszköz oldalára.
- Több, egyetlen felhasználóval rendelkező eszköz esetén használjon különböző PIN-eket/jelszavakat.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Megosztás több felhasználóval, mindegyik a saját fiókjával

2 Azure Active Directory előnyben részesített és legbiztonságosabb identitáshasználati eset az egyéni HoloLens (Azure AD-fiók). Saját Azure AD-fiókok használata esetén több felhasználó is megtarthatja saját felhasználói beállításait és felhasználói adatait az eszközön. Egyszerre csak egy felhasználó lehet bejelentkezve. Amikor egy felhasználó bejelentkezik, HoloLens az előző felhasználót.

Ha meg kell győződni arról, hogy többen is használhatnak saját fiókokat a HoloLens, kövesse az alábbi lépéseket a konfiguráláshoz:

1. Az eszköz [beállításakor válassza](hololens2-start.md)a Saját **munkahelyi vagy** iskolai tulajdonú lehetőséget, és jelentkezzen be egy Azure AD-fiókkal.
1. A beállítás befejezése után győződjön meg arról, hogy a fiókbeállítások (Gépház >-fiókok) tartalmazzák az **Egyéb felhasználók beállítást.**

> [!NOTE]
> Ha az eszköz nincs Azure AD-fiókkal beállítva, akkor azt vagy alaphelyzetbe kell állítani, vagy újra kell állítani és megfelelően be kell állítani. [](hololens-recovery.md)

A felhasználók HoloLens a következő lépéseket:

1. Ha egy másik felhasználó már használja az eszközt, válasszon az alábbi lehetőségek közül:
   - A készenléti állapotba való visszatéréshez nyomja le egyszer a bekapcsológombot, majd a zárolási képernyőre való visszatéréshez nyomja le újra a bekapcsológombot
   - Válassza ki a felhasználói csempét a **Start menü, vagy** válassza a Kijelentkezás lehetőséget a **Power menüből** az aktuális felhasználó kijelentkeztetése.

1. Jelentkezzen be az eszközre az Azure AD-fiók hitelesítő adataival.  
    - Ha első alkalommal használja az eszközt, a rendszer megkéri, hogy a saját szemére HoloLens az eszközt. [](hololens-calibration.md)
    - Ha korábban már használta az eszközt:
        - [Windows Holographic 20H2-es verziója, 19041.1128-as](hololens-release-notes.md#windows-holographic-version-20h2) vagy újabb buildszámmal rendelkezik, a kijelző zökkenőmentesen igazodik a minőséghez és a kényelmes megtekintéshez.
        - A korábbi buildek manuális beavatkozást fognak, hogy alkalmazkodni fogjanak a szeméhez.

> [!TIP]
> Ha a felhasználó még nem jelentkezett be egy eszközre, próbálja ki a következő két módszer egyikét a gyorsabb bejelentkezéshez:
>
> - **FIDO 2 biztonsági** kulcs: A RENDSZER automatikusan felismeri a FIDO2 biztonsági kulcsot, és a felhasználónak nem kell megadnia a felhasználói hitelesítő adatait vagy MFA-t használnia. Ez az új eszközön való bejelentkezés leggyorsabb módja.
> - **Webes** hitelesítés: Amikor új eszközre jelentkezik be, kiválaszthatja a Bejelentkezés másik eszközről hivatkozást, amely létrehoz egy 9 karakterből származó kódot, amellyel az [aka.ms/devicelogin-ban](https://login.microsoftonline.com/common/oauth2/deviceauth) bejelentkezhet felhasználóként az eszközön, vagy begépelheti a felhasználónevét és jelszavát a billentyűzettel a kényelmes használat érdekében. 

Az eszköz felhasználóinak listájáért vagy a felhasználó eszközről való eltávolításához a Fiók **egyéb** Gépház  >    >  **meg.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Megosztás több felhasználóval, akik mind ugyanazt a fiókot használják

Több felhasználó is megoszthat egy HoloLens eszközt egyetlen felhasználói fiók használatával. Bár az ajánlott HoloLens, hogy a felhasználók egyéni identitásokkal (Azure AD-fiókokkal) jelentkezzenek be az eszközre, ez egyes szervezetekben nem lehetséges.

Két megosztotteszköz-módszer érhető el:

- **Több végfelhasználó osztozik az 1** eszközön – HoloLens eszköz egy kijelölt térhez van rendelve, ahol bármely alkalmazott használhatja az eszközt. Ilyen lehet például egy tiszta szoba vagy egy orvosi csomag.

- **Több eszközt megosztó** végfelhasználók – HoloLens eszközök megosztott tárolóhelyen vannak, ahol az alkalmazottak bármilyen eszközt használhatnak. Ilyenek például az olajfúró vagy az autókereskedések/-szervizek.

Amikor egy új felhasználó először helyezi el az eszközt, miközben ugyanaz a fiók van bejelentkezve, az eszköz arra kéri a felhasználót, hogy gyorsan állítsa be és szabja személyre a megtekintési élményt. Az eszköz tárolja a hőmérsékleti információkat, hogy automatikusan optimalizálja az egyes felhasználók megtekintési élményének minőségét és kényelmi élményét. A felhasználóknak nem kell újra bekalkenni az eszközt.
