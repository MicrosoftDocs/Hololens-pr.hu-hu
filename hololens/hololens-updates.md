---
title: A HoloLens kezelése
description: Megtudhatja, hogyan kezelhetik a rendszergazdák a mobileszköz-kezelés segítségével a HoloLens frissítéseit.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 635e2cc274101fcf08fd05f2b3b54ce6c2f79182011d76409a51c722ea47ecc7
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662788"
---
# <a name="manage-hololens-updates"></a>A HoloLens kezelése

HoloLens a Windows frissítés ugyanúgy használható, mint más Windows 10 eszközök. Amikor egy frissítés elérhetővé válik, a rendszer automatikusan letölti és telepíti, amikor az eszköz legközelebb csatlakozik az internethez. Ez a cikk a frissítések vállalati vagy más felügyelt környezetben való kezelését ismerteti. Az egyes eszközök frissítésének kezelésével kapcsolatos HoloLens lásd: [Frissítés HoloLens.](hololens-update-hololens.md)

## <a name="manage-updates-automatically"></a>Frissítések automatikus kezelése

### <a name="managing-updates-by-using-windows-update-for-business"></a>Frissítések kezelése az Windows Update for Business használatával

Windows Holographic for Business frissítések kezeléséhez [Windows Frissítés vállalati verzióval.](/windows/deployment/update/waas-manage-updates-wufb) Mind HoloLens 2 eszköz használhatja a Windows Holographic for Business. Győződjön meg arról, hogy a Windows Holographic for Business 10.0.18362.1042-es vagy újabb buildet használják. Ha már HoloLens (1. generációs) eszközökkel, frissítenie [](hololens1-upgrade-enterprise.md) kell őket Windows Holographic for Business frissítésük kezeléséhez.

Windows Az Update for Business HoloLens az eszközöket közvetlenül a Windows Update szolgáltatáshoz. Az Windows Update for Business használatával a frissítési folyamat több aspektusát is szabályozhatja, vagyis hogy mely eszközök mely frissítéseket &mdash; kapják meg. Például az eszközök egy részéhez is kiadhatja a frissítéseket tesztelésre, majd később a többi eszközre is. De különböző frissítési ütemezéseket is meghatározhat a különböző típusú frissítésekhez.

> [!NOTE]  
> A HoloLens automatikusan kezelheti a funkciófrissítéseket (évente kétszer jelent meg) és a minőségi frissítéseket (havonta vagy szükség szerint kiadva, beleértve a kritikus fontosságú biztonsági frissítéseket). További információ a frissítéstípusokról: Az Windows Update for Business által kezelt [frissítések típusai.](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)

A Vállalati verzió Windows frissítésének beállításai HoloLens mobil-Eszközkezelés (MDM) megoldásban, például a Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Vállalati Windows frissítésének kezelése a Microsoft Intune

A Vállalati verzió frissítésének Intune-Windows nal való konfigurálásával kapcsolatos részletes információkért lásd: Windows 10 frissítései [az Intune-ban.](/intune/protect/windows-update-for-business-configure) További információ az Intune által támogatott HoloLens az Intune frissítéskezelési funkcióiról, amelyek HoloLens [támogatottak.](#intune-update-management-functions-that-hololens-supports)

> [!IMPORTANT]  
> Az Intune két szabályzattípust biztosít a frissítések kezeléséhez: Windows 10 *frissítési kör* és *Windows 10 funkciófrissítés.* Az Windows 10 funkciófrissítési szabályzattípus jelenleg nyilvános előzetes verzióban érhető el, és nem támogatott a HoloLens.
>  
> A frissítési Windows 10 szabályzatokkal 2 frissítés HoloLens kezelheti.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Frissítési szabályzatok konfigurálása HoloLens 2. vagy HoloLens (1. generációs) verzióhoz

Ez a szakasz azokat a szabályzatokat ismerteti, amelyek a 2. HoloLens frissítések (1. generációs) HoloLens kezelésére használhatók. További információ a 2. HoloLens elérhető funkciókról: A [2.](#plan-and-configure-update-rollouts-for-hololens-2)HoloLens frissítésének megterve és konfigurálása.

[Szabályzat CSP – A frissítés](/windows/client-management/mdm/policy-csp-update) határozza meg a vállalati frissítés Windows konfiguráló szabályzatokat.

> [!NOTE]  
> A szabályzatkonfigurációs szolgáltatók (CSP-k) listájáért, amelyet a HoloLens adott kiadásai támogatnak, lásd: A házirend-konfigurációs szolgáltatók által támogatott HoloLens [eszközök.](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)

#### <a name="configure-automatic-checks-for-updates"></a>Frissítések automatikus ellenőrzései

Az **Update/AllowAutoUpdate** szabályzat segítségével kezelheti az automatikus frissítési viselkedést, például a frissítések keresését, letöltését és telepítését. A szabályzathoz elérhető beállításokkal kapcsolatos további információkért lásd: [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> A Microsoft Intune automatikus frissítési **viselkedéssel** módosíthatja ezt a szabályzatot. További információ: [Manage Windows 10 software updates in Intune](/intune/windows-update-for-business-configure)..

#### <a name="configure-an-update-schedule"></a>Frissítési ütemezés konfigurálása

A frissítések alkalmazásának miként és mikor való konfiguráláskor használja a következő szabályzatokat:

- [Update/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Értékek: **0**–**7** (0 = naponta, 1 = vasárnap, 7 = szombat)
  - Alapértelmezett érték: **0** (naponta)
- [Update/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Értékek: 0–23 (0 = éjfél, 23 = 11 PM)
  - Alapértelmezett érték: 3:00

#### <a name="configure-active-hours"></a>Aktív órák konfigurálása
A [Holographic Windows 20H2-es](hololens-release-notes.md#windows-holographic-version-20h2) verziójától kezdve a rendszergazdák megadhatják az aktív órák tartományát HoloLens 2 eszköz számára.

Az aktív órák azt az időszakot azonosítják, amikor az eszköz várhatóan használatban lesz. Automatikus újraindítás, ha a frissítés az aktív órákon kívülre fog lekövetkezni. A megadott tartomány az aktív órák kezdési időpontból lesz megszámadva. Az MDM-et az Aktív órák konfigurálása az MDM-hez leírás [szerint használhatja.](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) Az MDM a Házirend CSP Update/ActiveHoursStart és Update/ActiveHoursEnd és Update/ActiveHoursMaxRange beállítását használja az aktív órák konfigurálhoz.

-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) – Ez az érték határozza meg a záró időt. A kezdési időponttól legfeljebb 12 órás lehet.
    -   Támogatott értékek: 0–23, ahol a 0 12:00, 1:00 stb.
    -   Az alapértelmezett érték 17 (17 óra).
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) – Ez az érték a kezdési időponttól való aktív órák maximális számát állítja be.
    -   A támogatott értékek: 8–18.
    -   Az alapértelmezett érték 18 (óra).
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) – Ez az érték határozza meg a kezdési időt. A záró időpont legfeljebb 12 órás lehet.
    -   Támogatott értékek: 0–23, ahol a 0 12:00, 1:00 stb.
    -   Az alapértelmezett érték 8 (8 AM).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Csak az 1607 Windows 10 verziót futtató eszközök esetén

A következő frissítési szabályzatok segítségével konfigurálhatja az eszközöket úgy, hogy az Windows Server Update Service (WSUS) szolgáltatásból kapják meg a frissítéseket az Windows Update helyett:

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>A 2. HoloLens frissítésének megterve és konfigurálása

HoloLens 2. verzió több frissítésautomatizálási funkciót támogat HoloLens mint az HoloLens (1. generációs) támogatja. Ez különösen akkor igaz, ha Microsoft Intune az Windows Update for Business szabályzatok kezeléséhez. Ezekkel a funkciókkal könnyebben tervezheti meg és valósíthatja meg a frissítés-bevezetéseket a szervezeten belül.

#### <a name="plan-the-update-strategy"></a>A frissítési stratégia megterve

Windows A Vállalati verzió frissítései támogatják a halasztó szabályzatokat. Miután a Microsoft közzétett egy frissítést, egy halasztó szabályzattal meghatározhatja, hogy mennyi ideig várjon a frissítés telepítése előtt az eszközökön. Az eszközök részkészleteinek (más néven frissítési *köröknek)* különböző halasztó szabályzatokkal való társításával koordinálhatja a szervezet frissítésének bevezetési stratégiáját.

Tegyük fel például, hogy egy szervezet 1000 eszközzel rendelkezik, és öt hullámban kell frissítenie az eszközöket. A szervezet öt frissítési köröket hozhat létre, az alábbi táblázatban látható módon.

|Group |Eszközök száma |Halasztás (nap) |
| ---| :---: | :---: |
|Grp 1 (it-alkalmazottak) |5 |0 |
|Grp 2 (korai befogadók) |50 |60 |
|Grp 3 (fő 1) |250 |120 |
|Grp 4 (fő 2) |300 |150 |
|Grp 5 (fő 3) |395 |180 |

Így halad a bevezetés az idő előrehaladtában a teljes szervezet számára.

![Frissítések telepítésének ütemterve](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Frissítés-halasztó szabályzat konfigurálása

A halasztó szabályzatok a frissítés elérhetővé válásának dátuma és a frissítés eszköz számára való felkínálásának dátuma között megadott napok számát ják meg.

Különböző halasztásokat konfigurálhat a szolgáltatásfrissítések és a minőségi frissítések számára. Az alábbi táblázat az egyes típusokkal használható házirendeket és azok maximális halasztását sorolja fel.

|Kategória |Szabályzat |Maximális halasztás |
| --- | --- | --- |
|Funkciófrissítések |DeferFeatureUpdatesPeriodInDays |365 nap |
|Minőségi frissítések |DeferQualityUpdatesPeriodInDays |30 nap |

#### <a name="pause-updates-via-device"></a>Frissítések felfüggesztése eszközön keresztül

Ha a felhasználó nem rendelkezik hozzáféréssel az MDM-hez, egyenként szüneteltetheti a frissítéseket 35 napig manuálisan egy HoloLens 2-es buildelésű eszközön Windows [Holographic 2004-es](hololens-release-notes.md#windows-holographic-version-2004) vagy újabb verzióban. A felhasználók úgy érik el ezt a beállítást, hogy megnyitják a **Gépház > Update & Security > Speciális beállításokat,** görgessen le a **Frissítések** felfüggesztése lehetőséghez, és válassza ki azt a dátumot, amely előtt szüneteltetik a frissítéseket. Miután egy felhasználó elérte a szüneteltetési korlátot, az eszköznek új frissítéseket kell kapnia, mielőtt újra szüneteltetheti. 

A [Holographic Windows 20H2](hololens-release-notes.md#windows-holographic-version-20h2)verziótól kezdve ez a szünetfrissítési függvény 2 HoloLens kezelhető. 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (alapértelmezett) – Engedélyezve
    - 1 – Letiltva

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Az Intune frissítéskezelési funkciói, HoloLens támogatottak

Az Intune következő frissítéskezelési funkcióival kezelheti a frissítéseket a HoloLens.

- **Létrehozás** és **hozzárendelés:** Ezek a függvények Windows 10 egy frissítési köröket a frissítési körök listájához. További információ: [Frissítési körök létrehozása és hozzárendelése.](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)

- **Szüneteltetés:** Ha problémába ütközik egy funkció- vagy minőségi frissítés telepítésekor, 35 napig szüneteltetheti a frissítést (a megadott dátumtól kezdődően). Ez a szünet megakadályozza, hogy más eszközök telepítsék a frissítést, amíg meg nem oldja vagy nem oldja meg a problémát. Ha szüneteltet egy funkciófrissítést, a minőségi frissítések továbbra is elérhetőek maradnak az eszközök számára a biztonságuk biztosítása érdekében. Ha egy frissítési típus fel van függesztve, a kör Áttekintés panelje megjeleníti, hogy hány nap van még a frissítési típus folytatása előtt. A megadott idő letelése után a szüneteltetés automatikusan lejár, és a frissítési folyamat folytatódik.

  Amíg a frissítési kör fel van függesztve, a következő lehetőségek közül választhat:

  - **Kiterjesztés:** A frissítési típus szüneteltetési időszakának meghosszabbítása 35 napra.
  - **Folytatás:** Állítsa vissza a kör frissítéseit az aktív művelethez. Szükség esetén ismét szüneteltetheti a frissítési kört.

  > [!NOTE]  
  > A **frissítési** körök eltávolítási művelete 2 HoloLens nem támogatott.

### <a name="delivery-optimization-preview"></a>Kézbesítésoptimalizálás előzetes verzió

[Windows Holographic 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) verziója lehetővé tette a kézbesítésoptimalizálási beállítások korai előzetes verzióját, így csökkentve a sávszélesség-használatot több HoloLens eszközről való letöltések esetén. A funkció teljesebb leírása és az ajánlott hálózati konfiguráció itt érhető el: Kézbesítésoptimalizálás [a Windows 10 frissítéséhez.](/windows/deployment/update/waas-delivery-optimization)

Az alábbi beállítások a felügyeleti felület részeként vannak engedélyezve, [és az Intune-ból konfigurálhatóak:](/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Az előzetes verzióval kapcsolatos néhány figyelmeztetés:

- HoloLens előzetes verzió csak az operációs rendszer frissítéseit támogatja.
- Windows Holographic for Business a HTTP-letöltési módokat és a Microsoft-végpontról [Csatlakoztatott gyorsítótár támogatja;](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) A társközi letöltési módok és csoport-hozzárendelések jelenleg nem támogatottak HoloLens eszközök esetében.
- HoloLens nem támogatja az üzembe helyezést vagy a kézbesítés optimalizálását Windows Server Update Services végpontok esetén.
- A hibaelhárításhoz vagy diagnosztikára van szükség a Csatlakoztatott gyorsítótár-kiszolgálón, vagy nyomkövetést kell gyűjteni a HoloLens-on HoloLens-n Gépház Update & Security Troubleshooting Windows Update (Frissítés &  >  **biztonsági**  >   **hibaelhárítása)**  >   **Windows keresztül.**

## <a name="manually-check-for-updates"></a>Frissítések manuális ellenőrzése

Bár HoloLens rendszeresen ellenőrzi a rendszerfrissítéseket, előfordulhatnak olyan körülmények, amelyeket manuálisan szeretne ellenőrizni.

A frissítések manuális ellenőrzéséhez Gépház  >  **frissítés & frissítések biztonsági**  >  **ellenőrzéséhez.** Ha a Gépház azt jelzi, hogy az eszköz naprakész, akkor az összes jelenleg elérhető frissítés elérhető.

## <a name="manually-roll-back-an-update"></a>Frissítés manuális visszaállítás

Bizonyos esetekben érdemes lehet a szoftver korábbi verziójára HoloLens vissza. Ennek folyamata attól függ, hogy 2-es vagy HoloLens (1. generációs) HoloLens-e.

### <a name="revert-to-a-previous-version-hololens-2"></a>Visszaállítás egy korábbi verzióra (2. HoloLens)

Visszaállíthatja a frissítéseket, és visszatérhet a 2. HoloLens korábbi verziójára az [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) használatával, hogy visszaállítsa a HoloLens korábbi verzióra.

> [!NOTE]
> A korábbi verzióra való visszaállítás törli a személyes fájlokat és beállításokat.

A 2. HoloLens előző verziójára való visszaállításhoz kövesse az alábbi lépéseket:

1. Győződjön meg arról, hogy nincs telefonja vagy Windows a számítógéphez csatlakoztatva.
1. A számítógépen töltse le az [Advanced Recovery Companiont a](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) Microsoft Store.
1. Töltse le [a 2 HoloLens kiadás legújabb kiadását.](https://aka.ms/hololens2download)
1. A letöltések befejezése után nyissa meg a **Fájlkezelő** Letöltések parancsát, kattintson a jobb gombbal az előbb letöltött tömörített (.zip) mappára, majd válassza a Extract all Extract all Extract (Összes kibontása) lehetőséget a fájl  >     >   kibontásához.
1. Usb-A–USB-C kábellel csatlakoztassa HoloLens eszközét a számítógéphez. Akkor is ez a kábel működik a legjobban, ha más kábelekkel csatlakoztatta HoloLens a kábeleket.
1. Az Advanced Recovery Companion automatikusan észleli a HoloLens eszközét. Válassza a **Microsoft HoloLens** csempét.
1. A következő képernyőn válassza a **Manuális csomagválasztás** lehetőséget, majd nyissa meg a korábban kibontott mappát.
1. Válassza ki a telepítőfájlt (.ffu).
1. Válassza **a Szoftver telepítése** lehetőséget, majd kövesse az utasításokat.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Visszaállítás korábbi verzióra (HoloLens (1. generáció))

Visszaállíthatja a frissítéseket, és visszatérhet az HoloLens (1. generációs) egy korábbi verziójára az [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) használatával a HoloLens korábbi verzióra való visszaállításához.

> [!NOTE]
> A korábbi verzióra való HoloLens törli a személyes fájlokat és beállításokat.

A (1. generációs) HoloLens korábbi verziójára való visszaállításhoz kövesse az alábbi lépéseket:

1. Győződjön meg arról, hogy nincs telefonja vagy Windows a számítógéphez csatlakoztatva.
1. A számítógépen töltse le a [Windows Device Recovery Tool (WDRT) eszközt.](https://support.microsoft.com/help/12379)
1. Töltse le [HoloLens évfordulós frissítés helyreállítási csomagját.](https://aka.ms/hololensrecovery)
1. A letöltések befejezése után nyissa meg a **Fájlkezelő** Letöltések parancsát, kattintson a jobb gombbal az előbb letöltött tömörített (.zip) mappára, majd válassza a Extract all Extract all Extract (Összes kibontása) lehetőséget a fájl  >     >   kibontásához.
1. Az eszközhöz a saját eszközével együtt biztosított mikro-USB HoloLens csatlakoztathatja a HoloLens eszközt a számítógépéhez. Ez akkor is működik a legjobban, ha más kábelekkel csatlakoztatta HoloLens eszközét.
1. A WDRT automatikusan észleli a HoloLens eszközt. Válassza a **Microsoft HoloLens** csempét.
1. A következő képernyőn válassza a **Manuális csomagválasztás** lehetőséget, majd nyissa meg a korábban kibontott mappát.
1. Válassza ki a telepítőfájlt (.ffu).
1. Válassza **a Szoftver telepítése** lehetőséget, majd kövesse az utasításokat.

**Ha a WDRT nem észleli az eszközt**

Ha a WDRT nem észleli a HoloLens eszközt, indítsa újra a számítógépet. Ha ez nem működik, válassza a Saját eszköz nem észlelhető **lehetőséget,** válassza a **Microsoft HoloLens** lehetőséget, majd kövesse az utasításokat.

## <a name="related-articles"></a>Kapcsolódó cikkek

- [HoloLens 2. kiadási megjegyzések](hololens-release-notes.md)
- [Mi az Windows Update for Business?](/windows/deployment/update/waas-manage-updates-wufb)
- [Eszközök hozzárendelése karbantartási csatornákhoz a Windows 10 frissítésekhez](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Windows 10-szoftverfrissítések kezelése az Intune-ban](/mem/intune/protect/windows-update-for-business-configure)
