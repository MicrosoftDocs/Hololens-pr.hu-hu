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
ms.date: 10/12/2021
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
ms.openlocfilehash: 854e867238de6c87732970fba75abdc8e1fb2c64
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924346"
---
# <a name="manage-hololens-updates"></a>A HoloLens kezelése

HoloLens frissítés Windows, ugyanúgy, mint a többi Windows 10. Amikor egy frissítés elérhetővé válik, a rendszer automatikusan letölti és telepíti, amikor az eszköz legközelebb csatlakozik az internethez. Ez a cikk a frissítések vállalati vagy más felügyelt környezetben való kezelését ismerteti. Az egyes eszközök frissítésének kezelésével kapcsolatos HoloLens lásd: [Frissítés HoloLens.](hololens-update-hololens.md)

## <a name="manage-updates-automatically"></a>Frissítések automatikus kezelése

### <a name="managing-updates-by-using-windows-update-for-business"></a>Frissítések kezelése az Windows Update for Business használatával

Windows Holographic for Business frissítés Windows [frissítéssel kezelheti](/windows/deployment/update/waas-manage-updates-wufb) a frissítéseket. Mind HoloLens 2 eszköz használhatja a Windows Holographic for Business. Győződjön meg arról, hogy Windows Holographic for Business 10.0.18362.1042 vagy újabb buildet használ. Ha már HoloLens (1. generációs) eszközökkel, frissítenie [](hololens1-upgrade-enterprise.md) kell őket a Windows Holographic for Business frissítésük kezeléséhez.

Windows Az Update for Business HoloLens az eszközöket közvetlenül az Windows Update szolgáltatáshoz. Az Windows Update for Business használatával a frissítési folyamat több aspektusát is szabályozhatja, vagyis hogy mely eszközök mely frissítéseket &mdash; kapják meg. Például az eszközök egy részéhez is kiadhatja a frissítéseket tesztelésre, majd később a többi eszközre is. De különböző frissítési ütemezéseket is meghatározhat a különböző típusú frissítésekhez.

> [!NOTE]  
> A HoloLens automatikusan kezelheti a funkciófrissítéseket (évente kétszer jelent meg) és a minőségi frissítéseket (havonta vagy szükség szerint, beleértve a kritikus fontosságú biztonsági frissítéseket is). További információ a frissítéstípusokról: Az Windows Update for Business által kezelt [frissítések típusai.](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)

A Vállalati verzió Windows beállításokat a HoloLens konfigurálhatja egy Mobile Eszközkezelés-megoldás (MDM) szabályzatával, például a Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Vállalati Windows frissítésének kezelése a Microsoft Intune

A Vállalati verziófrissítések Intune-nal való konfigurálásának Windows részletes leírását lásd: Windows 10 frissítései [az Intune-ban.](/intune/protect/windows-update-for-business-configure) A támogatott Intune-funkciókkal kapcsolatos további HoloLens az Intune frissítéskezelési funkcióit, amelyek a [HoloLens támogatják.](#intune-update-management-functions-that-hololens-supports)

> [!IMPORTANT]  
> Az Intune két szabályzattípust biztosít a frissítések kezeléséhez: Windows 10 *frissítési kör és* Windows 10 *funkciófrissítés.* Az Windows 10 funkciófrissítési szabályzattípus jelenleg nyilvános előzetes verzióban érhető el, és nem támogatott a HoloLens.
>  
> A frissítési Windows 10 szabályzatokkal 2 frissítés HoloLens kezelheti.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Frissítési szabályzatok konfigurálása HoloLens 2. vagy HoloLens (1. generációs) verzióhoz

Ez a szakasz azokat a szabályzatokat ismerteti, amelyek a 2. vagy HoloLens (1. generációs) frissítések HoloLens kezelésére használhatók. További információ a 2. HoloLens elérhető funkciókról: A [2.](#plan-and-configure-update-rollouts-for-hololens-2)HoloLens frissítésének megterve és konfigurálása.

[Szabályzat CSP – A](/windows/client-management/mdm/policy-csp-update) frissítés határozza meg az üzleti Windows frissítését konfiguráló szabályzatokat.

> [!NOTE]  
> A szabályzatkonfigurációs szolgáltatók (CSP-k) listájáért, amelyet a HoloLens adott kiadásai támogatnak, lásd a házirend-konfigurációs szolgáltatók által támogatott HoloLens [listában.](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)

#### <a name="configure-automatic-checks-for-updates"></a>Frissítések automatikus ellenőrzései

Az **Update/AllowAutoUpdate** szabályzat segítségével kezelheti az automatikus frissítési viselkedést, például a frissítések keresését, letöltését és telepítését. A szabályzathoz elérhető beállításokkal kapcsolatos további információkért lásd: [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> A Microsoft Intune automatikus frissítési viselkedéssel módosíthatja ezt a szabályzatot.  További információ: [Az Intune Windows 10 kezelése.](/intune/windows-update-for-business-configure)

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

Az aktív órák azt az időszakot azonosítják, amikor az eszköz várhatóan használatban lesz. Automatikus újraindítások, ha a frissítés az aktív órákon kívülre esik. A megadott tartomány az aktív órák kezdési időpontból lesz megszámadva. Az MDM-et az Aktív órák konfigurálása az [MDM-hez leírás szerint használhatja.](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) Az MDM a Házirend CSP Update/ActiveHoursStart és Update/ActiveHoursEnd és Update/ActiveHoursMaxRange beállítását használja az aktív órák konfigurálhoz.

-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) – Ez az érték határozza meg a záró időt. A kezdési időponttól legfeljebb 12 órás lehet.
    -   Támogatott értékek: 0–23, ahol a 0 12:00, 1 00 stb.
    -   Az alapértelmezett érték 17 (17 óra).
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) – Ez az érték a kezdési időponttól való aktív órák maximális számát állítja be.
    -   A támogatott értékek: 8–18.
    -   Az alapértelmezett érték 18 (óra).
-   [Update/ActiveHoursStart –](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) Ez az érték határozza meg a kezdési időt. A záró időpont legfeljebb 12 órás lehet.
    -   Támogatott értékek: 0–23, ahol a 0 12:00, 1 00 stb.
    -   Az alapértelmezett érték 8 (8 AM).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Csak a Windows 10 1607-es verziójú eszközök esetén

Az alábbi frissítési szabályzatokkal konfigurálhatja az eszközöket úgy, hogy az Windows Server Update Service (WSUS) szolgáltatásból kapják meg a frissítéseket a Windows helyett:

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

#### <a name="improved-update-restart-detection-and-notifications"></a>Továbbfejlesztett frissítés-újraindítás észlelése és értesítések

- A [Holographic Windows 21H2 verzióban vezettük be.](hololens-release-notes.md#windows-holographic-version-21h2)

Az aktív órák és a telepítési idő házirendek között lehetőség van arra, hogy ne kelljen újraindítani HoloLens eszközöket, amikor használatban vannak. Ha azonban nem történik újraindítás a szükséges frissítések telepítésének befejezéséhez, az is késleltetné a frissítések telepítését. Most olyan szabályzatokat adtunk hozzá, amelyek lehetővé teszik az it-ita számára a határidők és a szükséges újraindítások kényszerítése, valamint a frissítések időbeni telepítésének befejezését. A felhasználók értesítést kaphatnak az újraindítás kezdeményezése előtt, és az it-szabályzatnak megfelelően késleltetni tudják az újraindítást.

A következő frissítési szabályzatok bővültek:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>A 2. HoloLens frissítésének megterve és konfigurálása

HoloLens 2. verzió több frissítésautomatizálási funkciót támogat HoloLens mint a HoloLens (1. generációs) támogatja. Ez különösen akkor igaz, ha Microsoft Intune az Windows Update for Business szabályzatok kezeléséhez. Ezekkel a funkciókkal könnyebben tervezheti meg és valósíthatja meg a frissítés-bevezetéseket a szervezeten belül.

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

![A frissítések telepítésének ütemterve.](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Frissítés-halasztó szabályzat konfigurálása

A halasztó szabályzatok a frissítés elérhetővé válásának dátuma és a frissítés eszköz számára való felkínálásának dátuma között megadott napok számát ják meg.

Különböző halasztásokat konfigurálhat a szolgáltatásfrissítések és a minőségi frissítések számára. Az alábbi táblázat felsorolja az egyes típusonként használható házirendeket, valamint az egyes típusonkénti maximális halasztásokat.

|Kategória |Szabályzat |Maximális halasztás |
| --- | --- | --- |
|Funkciófrissítések |DeferFeatureUpdatesPeriodInDays |365 nap |
|Minőségi frissítések |DeferQualityUpdatesPeriodInDays |30 nap |

#### <a name="pause-updates-via-device"></a>Frissítések felfüggesztése eszközön keresztül

Ha a felhasználó nem rendelkezik hozzáféréssel az MDM-hez, egyenként szüneteltetheti a frissítéseket 35 napig manuálisan egy HoloLens 2-es buildelésű eszközön Windows [Holographic 2004-es](hololens-release-notes.md#windows-holographic-version-2004) vagy újabb verzióban. A felhasználók úgy érik el ezt a beállítást, hogy megnyitják a **Gépház > Update & Security > Speciális** beállításokat, majd a **Frissítések** felfüggesztése lehetőségig megnyitják azt a dátumot, amely előtt szüneteltetik a frissítéseket. Ha egy felhasználó elérte a szüneteltetési korlátot, az eszköznek új frissítéseket kell kapnia, mielőtt újra szüneteltetheti. 

A [Holographic Windows 20H2](hololens-release-notes.md#windows-holographic-version-20h2)verziótól kezdve ez a felfüggesztési frissítés funkció 2 HoloLens kezelhető. 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (alapértelmezett) – Engedélyezve
    - 1 – Letiltva

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Az Intune frissítéskezelési funkciói, HoloLens támogatottak

Az Intune következő frissítéskezelési funkcióival kezelheti a frissítéseket a HoloLens.

- **Létrehozás** és **hozzárendelés:** Ezek a függvények egy Windows 10 a frissítési körök listájához. További információ: [Frissítési körök létrehozása és hozzárendelése.](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)

- **Szüneteltetés:** Ha problémába ütközik egy szolgáltatás vagy minőségi frissítés telepítésekor, a frissítést 35 napig szüneteltetheti (a megadott dátumtól kezdve). Ez a szünet megakadályozza, hogy más eszközök telepítsék a frissítést, amíg el nem hárítja a problémát. Ha felfüggeszt egy funkciófrissítést, a minőségi frissítések továbbra is elérhetőek maradnak az eszközök számára a biztonságuk biztosítása érdekében. Ha egy frissítési típus fel van függesztve, a kör Áttekintés panelje megjeleníti, hogy hány nap van még a frissítési típus folytatása előtt. A megadott idő letelése után a szüneteltetés automatikusan lejár, és a frissítési folyamat folytatódik.

  Amíg a frissítési kör fel van függesztve, az alábbi lehetőségek közül választhat:

  - **Kiterjesztés:** 35 nappal hosszabbítsa meg a frissítési típus szünetelési időszakát.
  - **Folytatás:** Állítsa vissza a kör frissítéseit az aktív műveletre. Szükség esetén ismét szüneteltetheti a frissítési kört.

  > [!NOTE]  
  > A **frissítési** körök eltávolítási művelete 2 HoloLens nem támogatott.

### <a name="delivery-optimization-preview"></a>Kézbesítésoptimalizálás előzetes verzió

[Windows Holographic 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) verziója lehetővé tette a kézbesítésoptimalizálási beállítások korai előzetes verzióját, így csökkentve a sávszélesség-használatot több HoloLens eszközről. A funkció és az ajánlott hálózati konfiguráció teljesebb leírása itt érhető el: Kézbesítésoptimalizálás [a Windows 10 frissítéséhez.](/windows/deployment/update/waas-delivery-optimization)

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
- Windows Holographic for Business a HTTP letöltési módokat és a Microsoft-végpontról [való Csatlakoztatott gyorsítótár letöltéseket támogatja;](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) A társközi letöltési módok és csoport-hozzárendelések jelenleg nem támogatottak HoloLens eszközök esetében.
- HoloLens nem támogatja az üzembe helyezést vagy a kézbesítés optimalizálását Windows Server Update Services végpontok esetén.
- A hibaelhárításhoz diagnosztikára van szükség a Csatlakoztatott gyorsítótár-kiszolgálón, vagy nyomkövetést kell gyűjteni a HoloLens HoloLens-on az **Gépház** Update & Security Troubleshooting Windows Update (Frissítés &  >  **biztonsági**  >     >   **hibaelhárítása) Windows keresztül.**

## <a name="manually-check-for-updates"></a>Frissítések manuális ellenőrzése

Bár HoloLens rendszeresen ellenőrzi a rendszerfrissítéseket, előfordulhatnak olyan körülmények, amelyekben manuálisan szeretné ellenőrizni.

A frissítések manuális ellenőrzéséhez tekintse meg a Gépház  >  **Frissítés & biztonsági** frissítések keresése  >  **adatokat.** Ha a Gépház alkalmazás azt jelzi, hogy az eszköz naprakész, akkor az összes jelenleg elérhető frissítés elérhető.

## <a name="manually-roll-back-an-update"></a>Frissítés manuális visszaállítása

Bizonyos esetekben érdemes lehet a szoftver korábbi verziójára HoloLens vissza. Ennek folyamata attól függ, hogy 2-es vagy HoloLens (1. generációs) HoloLens-e.

### <a name="revert-to-a-previous-version-hololens-2"></a>Visszaállítás korábbi verzióra (2. HoloLens)

A frissítések visszaállításához és a 2. HoloLens korábbi verziójára való visszatéréshez használja az [Advanced Recovery Companiont](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) a HoloLens korábbi verzióra való visszaállításához.

> [!NOTE]
> A korábbi verzióra való visszaállítás törli a személyes fájlokat és beállításokat.

A 2. HoloLens korábbi verziójára való visszaállításhoz kövesse az alábbi lépéseket:

1. Győződjön meg arról, hogy nincs telefonja vagy Windows a számítógéphez csatlakoztatva.
1. A számítógépen töltse le az [Advanced Recovery Companiont](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) a Microsoft Store.
1. Töltse le [a 2 HoloLens kiadás legújabb kiadását.](https://aka.ms/hololens2download)
1. A letöltések befejezése után nyissa meg a **Fájlkezelő** Letöltések ablakát, kattintson a jobb gombbal az előbb letöltött tömörített (.zip) mappára, majd válassza az Extract all Extract (Összes kibontása) lehetőséget a fájl  >     >   kibontásához.
1. Usb-A–USB-C kábellel csatlakoztassa HoloLens eszközét a számítógéphez. Akkor is ez a kábel működik a legjobban, ha más kábelekkel csatlakoztatta HoloLens-
1. Az Advanced Recovery Companion automatikusan észleli a HoloLens eszközét. Válassza a **Microsoft HoloLens** csempét.
1. A következő képernyőn válassza a **Manuális csomagválasztás** lehetőséget, majd nyissa meg a korábban kibontott mappát.
1. Válassza ki a telepítőfájlt (.ffu).
1. Válassza **a Szoftver telepítése** lehetőséget, majd kövesse az utasításokat.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Visszaállítás korábbi verzióra (HoloLens (1. generáció))

Visszaállíthatja a frissítéseket, és visszatérhet az HoloLens (1. generációs) korábbi verziójára az [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) használatával a HoloLens korábbi verzióra való visszaállításához.

> [!NOTE]
> A korábbi verzióra való HoloLens törli a személyes fájlokat és beállításokat.

A korábbi verzióra való HoloLens (1. generációs) kövesse az alábbi lépéseket:

1. Győződjön meg arról, hogy nincs telefonja vagy Windows a számítógéphez csatlakoztatva.
1. A számítógépen töltse le a [Windows Device Recovery Tool (WDRT) eszközt.](https://support.microsoft.com/help/12379)
1. Töltse le [a HoloLens évfordulós frissítés helyreállítási csomagját.](https://aka.ms/hololensrecovery)
1. A letöltések befejezése után nyissa meg a **Fájlkezelő** Letöltések ablakát, kattintson a jobb gombbal az előbb letöltött tömörített (.zip) mappára, majd válassza az Extract all Extract (Összes kibontása) lehetőséget a fájl  >     >   kibontásához.
1. A hálózati eszközzel együtt biztosított mikro-USB-kábellel HoloLens a HoloLens eszközét a számítógéphez. Ez akkor is működik a legjobban, ha más kábelekkel csatlakoztatta HoloLens eszközét.
1. A WDRT automatikusan észleli a HoloLens eszközt. Válassza a **Microsoft HoloLens** csempét.
1. A következő képernyőn válassza a **Manuális csomagválasztás** lehetőséget, majd nyissa meg a korábban kibontott mappát.
1. Válassza ki a telepítőfájlt (.ffu).
1. Válassza **a Szoftver telepítése** lehetőséget, majd kövesse az utasításokat.

**Ha a WDRT nem észleli az eszközt**

Ha a WDRT nem észleli a HoloLens eszközt, indítsa újra a számítógépet. Ha ez nem működik, válassza a Saját eszköz **nem** észlelhető lehetőséget, válassza a **Microsoft HoloLens** lehetőséget, majd kövesse az utasításokat.

## <a name="related-articles"></a>Kapcsolódó cikkek

- [HoloLens 2. kiadási megjegyzések](hololens-release-notes.md)
- [Mi az Windows Update for Business?](/windows/deployment/update/waas-manage-updates-wufb)
- [Eszközök hozzárendelése karbantartási csatornákhoz a frissítések Windows 10 érdekében](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Windows 10-szoftverfrissítések kezelése az Intune-ban](/mem/intune/protect/windows-update-for-business-configure)
