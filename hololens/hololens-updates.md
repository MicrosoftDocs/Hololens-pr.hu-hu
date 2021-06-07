---
title: HoloLens-frissítések kezelése
description: Megtudhatja, hogyan kezelhetik a rendszergazdák a holoLens-eszközök frissítéseit mobileszköz-felügyelet használatával.
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
ms.openlocfilehash: 6c9d1551b2a3348a6ff9962180c2d5552eb100f1
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379577"
---
# <a name="manage-hololens-updates"></a>HoloLens-frissítések kezelése

A HoloLens ugyanúgy Windows Update, mint a többi Windows 10. Amikor elérhetővé válik egy frissítés, a rendszer automatikusan letölti és telepíti, amikor az eszköz legközelebb csatlakozik és csatlakozik az internethez. Ez a cikk a frissítések vállalati vagy más felügyelt környezetben való kezelését ismerteti. További információ az egyes HoloLens-eszközök frissítésének kezelésével kapcsolatban: [A HoloLens frissítése.](hololens-update-hololens.md)

## <a name="manage-updates-automatically"></a>Frissítések automatikus kezelése

### <a name="managing-updates-by-using-windows-update-for-business"></a>Frissítések kezelése a Windows Update Vállalatoknak

Windows Holographic for Business a [Windows Update Vállalatoknak](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) kezelheti a frissítéseket. Minden HoloLens 2-eszköz használhatja a Windows Holographic for Business. Győződjön meg arról, hogy Windows Holographic for Business 10.0.18362.1042 vagy újabb buildet használ. Ha HoloLens -eszközökkel (1. generációs) is [](hololens1-upgrade-enterprise.md) van, frissítenie kell őket Windows Holographic for Business-re a frissítések kezeléséhez.

Windows Update Vállalatoknak a HoloLens-eszközöket közvetlenül a Windows Update csatlakoztatja. A Windows Update Vállalatoknak a frissítési folyamat több aspektusát is szabályozhatja, vagyis hogy mely eszközök mely frissítéseket &mdash; kapják meg. Például az eszközök egy részéhez is kiadhatja a frissítéseket tesztelésre, majd később a többi eszközre is. De különböző frissítési ütemezéseket is meghatározhat a különböző típusú frissítésekhez.

> [!NOTE]  
> HoloLens-eszközök esetén automatikusan felügyelheti a funkciófrissítéseket (évente kétszer jelent meg) és a minőségi frissítéseket (havonta vagy szükség szerint kiadva, beleértve a kritikus fontosságú biztonsági frissítéseket is). A frissítéstípusokkal kapcsolatos további információkért lásd: [Az](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)Windows Update Vállalatoknak.

A HoloLens Windows Update Vállalatoknak konfigurálható szabályzatokkal egy Mobile Eszközkezelés-megoldásban (például az Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>A Windows Update Vállalatoknak kezelése a Microsoft Intune

Az Intune Windows Update Vállalatoknak-nal való konfigurálás részletes leírását lásd: Windows 10 kezelése [az Intune-ban.](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure) A HoloLens által támogatott intune-funkciókkal kapcsolatos további információkért lásd a HoloLens által támogatott [Intune frissítéskezelési funkciókat.](#intune-update-management-functions-that-hololens-supports)

> [!IMPORTANT]  
> Az Intune két szabályzattípust biztosít a frissítések kezeléséhez: Windows 10 *frissítési kör* és *Windows 10 funkciófrissítés.* A Windows 10 funkciófrissítési szabályzattípus jelenleg nyilvános előzetes verzióban érhető el, és a HoloLens nem támogatja.
>  
> A Frissítési kör Windows 10 a HoloLens 2 frissítéseinek kezeléséhez.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Frissítési szabályzatok konfigurálása HoloLens 2-hez vagy HoloLenshez (1. generációs)

Ez a szakasz azokat a szabályzatokat ismerteti, amelyek a HoloLens 2 vagy a HoloLens (1. generációs) frissítéseinek kezeléséhez használhatók. A HoloLens 2-hez elérhető funkciókkal kapcsolatos további információkért lásd: A [HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2)frissítésének megtervezője és konfigurálása.

[Házirend CSP – A frissítés](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) határozza meg a házirendeket, amelyek Windows Update Vállalatoknak.

> [!NOTE]  
> A HoloLens adott kiadásai által támogatott szabályzatkonfigurációs szolgáltatók (CSP-k) listáját lásd: [A HoloLens-eszközök](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)által támogatott szabályzatkonfigurációs szolgáltatók.

#### <a name="configure-automatic-checks-for-updates"></a>Frissítések automatikus ellenőrzésének konfigurálása

Az **Update/AllowAutoUpdate** szabályzat segítségével kezelheti az automatikus frissítés viselkedését, például a frissítések keresését, letöltését és telepítését. A szabályzathoz elérhető beállításokkal kapcsolatos további információkért lásd: [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> A Microsoft Intune automatikus frissítési **viselkedéssel** módosíthatja ezt a szabályzatot. További információkért lásd: Manage Windows 10 software updates in Intune (Szoftverfrissítések [kezelése az Intune-ban).](https://docs.microsoft.com/intune/windows-update-for-business-configure)

#### <a name="configure-an-update-schedule"></a>Frissítési ütemezés konfigurálása

A frissítések alkalmazásának és az alkalmazásának konfiguráláskor használja a következő szabályzatokat:

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Értékek: **0**–**7** (0 = naponta, 1 = vasárnap, 7 = szombat)
  - Alapértelmezett érték: **0** (minden nap)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Értékek: 0–23 (0 = éjfél, 23 = 11 PM)
  - Alapértelmezett érték: 15:00

#### <a name="configure-active-hours"></a>Aktív órák konfigurálása
A [Windows Holographic rendszertől kezdve a 20H2-es](hololens-release-notes.md#windows-holographic-version-20h2) verziótól kezdve a rendszergazda megadhatja a HoloLens 2-eszközök aktív munkaidő-tartományát.

Az aktív órák azt az időszakot meghatározzák, amikor az eszköz várhatóan használatban lesz. Automatikus újraindítás, ha a frissítés az aktív órán kívül történik. A megadott tartomány beleszámál az aktív órák kezdési időpontba. Az MDM-et az Aktív órák konfigurálása az [MDM-hez dokumentumban leírtak szerint használhatja.](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) Az MDM a Házirend CSP Update/ActiveHoursStart és Update/ActiveHoursEnd és Update/ActiveHoursMaxRange beállítását használja az aktív órák konfigurálhoz.

-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) – Ez az érték határozza meg a záró időt. A kezdési időponttól legfeljebb 12 óra van.
    -   A támogatott értékek a 0-23, ahol a 0 az 12 AM, az 1 pedig az 1 AM stb.
    -   Az alapértelmezett érték 17 (17 óra).
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) – Ez az érték a kezdési időponttól való aktív órák maximális számát állítja be.
    -   A támogatott értékek: 8–18.
    -   Az alapértelmezett érték 18 (óra).
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) – Ez az érték határozza meg a kezdési időt. A záró időponttól legfeljebb 12 óra van.
    -   A támogatott értékek a 0-23, ahol a 0 az 12 AM, az 1 pedig az 1 AM stb.
    -   Az alapértelmezett érték 8 (08:00).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Csak az 1607 Windows 10 verziót futtató eszközök esetén

Az alábbi frissítési szabályzatok segítségével konfigurálhatja az eszközöket a Windows Server Update Service (WSUS) frissítéseinek lekért használatára az Windows Update:

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>A HoloLens 2 frissítésének megtervezője és konfigurálása

A HoloLens 2 több frissítésautomatizálási funkciót támogat, mint a HoloLens (1. generációs) Ez különösen akkor igaz, ha Microsoft Intune szabályzatok kezeléséhez Windows Update Vállalatoknak használ. Ezekkel a funkciókkal könnyebben tervezheti meg és valósíthatja meg a frissítés-bevezetéseket a szervezeten belül.

#### <a name="plan-the-update-strategy"></a>A frissítési stratégia megterve

A Vállalati Windows-frissítések támogatja a halasztó házirendeket. Miután a Microsoft közzétett egy frissítést, egy halasztó szabályzattal meghatározhatja, hogy mennyi ideig várjon a frissítés telepítése előtt az eszközökön. Az eszközök részkészleteinek (más néven frissítési *köröknek)* különböző halasztó szabályzatokkal való társításával koordinálhatja a szervezet frissítésbe való bevezetési stratégiáját.

Tegyük fel például, hogy egy szervezet 1000 eszközzel rendelkezik, és öt hullámban kell frissítenie az eszközöket. A szervezet öt frissítési köröket hozhat létre, az alábbi táblázatban látható módon.

|Group |Eszközök száma |Halasztás (nap) |
| ---| :---: | :---: |
|Grp 1 (it-csapat) |5 |0 |
|Grp 2 (korai befogadók) |50 |60 |
|Grp 3 (fő 1) |250 |120 |
|Grp 4 (fő 2) |300 |150 |
|Grp 5 (fő 3) |395 |180 |

Így halad a bevezetés az idő előrehaladtát a teljes szervezet számára.

![Frissítések telepítésének ütemterve](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Frissítés-halasztó szabályzat konfigurálása

A halasztó szabályzat a frissítés elérhetővé válásának dátuma és a frissítés eszköz számára való felkínálásának dátuma között megadott napok számát határozza meg.

Különböző halasztásokat konfigurálhat a szolgáltatásfrissítések és a minőségi frissítések számára. Az alábbi táblázat az egyes típusokkal használható házirendeket és azok maximális halasztását sorolja fel.

|Kategória |Szabályzat |Maximális halasztás |
| --- | --- | --- |
|Funkciófrissítések |DeferFeatureUpdatesPeriodInDays |365 nap |
|Minőségi frissítések |DeferQualityUpdatesPeriodInDays |30 nap |

#### <a name="pause-updates-via-device"></a>Frissítések felfüggesztése eszközön keresztül

Ha a felhasználó nem fér hozzá az MDM-hez, külön-külön szüneteltetheti a frissítéseket 35 napig manuálisan egy HoloLens 2 rendszerű eszközön a [Windows Holographic 2004-es](hololens-release-notes.md#windows-holographic-version-2004) vagy újabb buildelési verzióján. A felhasználók úgy érik el ezt a beállítást, hogy megnyitják a **Beállítások -> Update & Security -> Speciális beállításokat,** görgessen le a **Frissítések** felfüggesztése lehetőséghez, és válassza ki azt a dátumot, amely előtt szüneteltetik a frissítéseket. Ha egy felhasználó elérte a szüneteltetési korlátot, az eszköznek új frissítéseket kell kapnia, mert újra szüneteltetheti azt. 

A [Windows Holographic 20H2](hololens-release-notes.md#windows-holographic-version-20h2)verziójától kezdve ez a szünetfrissítési funkció a HoloLens 2 rendszerű eszközökhöz is kezelhető. 
- [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (alapértelmezett) – Engedélyezve
    - 1 – Letiltva

#### <a name="intune-update-management-functions-that-hololens-supports"></a>A HoloLens által támogatott Intune frissítéskezelési funkciók

A HoloLens frissítéseit a következő Intune frissítéskezelési funkciókkal kezelheti.

- **Létrehozás** és **hozzárendelés:** Ezek a függvények Windows 10 egy frissítési köröket a frissítési körök listájához. További információ: [Frissítési körök létrehozása és hozzárendelése.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)

- **Szüneteltetés:** Ha problémába ütközik egy funkció- vagy minőségi frissítés telepítésekor, 35 napig szüneteltetheti a frissítést (a megadott dátumtól kezdődően). Ez a szünet megakadályozza, hogy más eszközök telepítsék a frissítést, amíg meg nem oldja vagy nem oldja meg a problémát. Ha szüneteltet egy funkciófrissítést, a minőségi frissítések továbbra is elérhetőek maradnak az eszközök számára a biztonságuk biztosítása érdekében. Ha egy frissítési típus fel van függesztve, a kör Áttekintés panelje megjeleníti, hogy hány nap van még a frissítési típus folytatása előtt. A megadott idő letelése után a szüneteltetés automatikusan lejár, és a frissítési folyamat folytatódik.

  Amíg a frissítési kör fel van függesztve, a következő lehetőségek közül választhat:

  - **Kiterjesztés:** A frissítési típus szüneteltetési időszakának meghosszabbítása 35 napra.
  - **Folytatás:** Állítsa vissza a kör frissítéseit az aktív művelethez. Szükség esetén ismét szüneteltetheti a frissítési kört.

  > [!NOTE]  
  > A **frissítési** körök eltávolítási művelete a HoloLens 2-eszközökön nem támogatott.

### <a name="delivery-optimization-preview"></a>Kézbesítésoptimalizálás előzetes verzió

[A Windows Holographic 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) verziója lehetővé tette a kézbesítésoptimalizálási beállítások korai előzetes verzióját, így csökkentve a sávszélesség-felhasználást több HoloLens-eszközről történő letöltések esetén. A funkció teljesebb leírása és az ajánlott hálózati konfiguráció itt érhető el: Kézbesítésoptimalizálás [a Windows 10 frissítéséhez.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

Az alábbi beállítások a felügyeleti felület részeként vannak engedélyezve, [és az Intune-ból konfigurálhatóak:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Az előzetes verzióval kapcsolatos néhány figyelmeztetés:

- A HoloLens támogatása ebben az előzetes verzióban csak az operációs rendszer frissítéseit támogatja.
- Windows Holographic for Business a HTTP letöltési módokat és a Microsoft-végpontról [való Csatlakoztatott gyorsítótár letöltéseket támogatja;](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) A holoLens-eszközök jelenleg nem támogatják a társközi letöltési módokat és csoport-hozzárendeléseket.
- A HoloLens nem támogatja a végpontok üzembe helyezését Windows Server Update Services optimalizálását.
- A hibaelhárításhoz vagy diagnosztikára van szükség a Csatlakoztatott gyorsítótár-kiszolgálón, vagy nyomkövetést kell gyűjteni a HoloLensen a HoloLensen a Settings  >  **Update & Security**  >   **Troubleshooting**  >   **Windows Update**.

## <a name="manually-check-for-updates"></a>Frissítések manuális ellenőrzése

Bár a HoloLens rendszeresen keres rendszerfrissítéseket, előfordulhatnak olyan körülmények, amelyekben manuálisan szeretné ellenőrizni.

A frissítések manuális ellenőrzéséhez kattintson a Beállítások frissítése és  >  **& frissítések biztonsági** ellenőrzése  >  **elemre.** Ha a Beállítások alkalmazás azt jelzi, hogy az eszköz naprakész, akkor az összes jelenleg elérhető frissítés elérhető.

## <a name="manually-roll-back-an-update"></a>Frissítés manuális visszaállítási lehetőség

Bizonyos esetekben érdemes lehet visszaállni a HoloLens szoftver egy korábbi verziójára. Ennek folyamata attól függ, hogy a HoloLens 2-t vagy a HoloLenst (1. generációs) használja-e.

### <a name="revert-to-a-previous-version-hololens-2"></a>Visszaállítás korábbi verzióra (HoloLens 2)

Visszaállíthatja a frissítéseket, és visszatérhet a HoloLens 2 egy korábbi verziójára az [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) használatával, hogy visszaállítsa a HoloLenst a korábbi verzióra.

> [!NOTE]
> A korábbi verzióra való visszaállítás törli a személyes fájlokat és beállításokat.

A HoloLens 2 korábbi verziójára való visszaállításhoz kövesse az alábbi lépéseket:

1. Győződjön meg arról, hogy nincs csatlakoztatva telefon vagy Windows-eszköz a számítógéphez.
1. A számítógépen töltse le az [Advanced Recovery Companiont](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) a Microsoft Store.
1. Töltse le [a Legújabb HoloLens 2-kiadást.](https://aka.ms/hololens2download)
1. A letöltések befejezése után nyissa meg a **Fájlkezelő** Letöltések parancsát, kattintson a jobb gombbal az előbb letöltött tömörített (.zip) mappára, majd válassza a Extract all Extract all Extract (Összes kinyerés kibontása) lehetőséget a fájl  >     >   kibontásához.
1. A HoloLens-eszközt USB-A–USB-C kábellel csatlakoztassa a számítógépéhez. Az ilyen kábelek akkor is a legjobban működnek, ha más kábeleket használt a HoloLens csatlakoztatására.
1. Az Advanced Recovery Companion automatikusan észleli a HoloLens-eszközt. Válassza a **Microsoft HoloLens** csempét.
1. A következő képernyőn válassza a **Manuális csomagválasztás** lehetőséget, majd nyissa meg a korábban kibontott mappát.
1. Válassza ki a telepítőfájlt (.ffu).
1. Válassza **a Szoftver telepítése** lehetőséget, majd kövesse az utasításokat.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Visszaállítás korábbi verzióra (HoloLens (1. generáció))

Visszaállíthatja a frissítéseket, és visszatérhet a HoloLens (1. generációs) korábbi verziójára a [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) használatával a HoloLens korábbi verziójára való visszaállításához.

> [!NOTE]
> Egy korábbi HoloLens-verzióra való visszaállítás törli a személyes fájlokat és beállításokat.

A HoloLens (1. generációs) korábbi verziójára való visszaállításhoz kövesse az alábbi lépéseket:

1. Győződjön meg arról, hogy nincs csatlakoztatva telefon vagy Windows-eszköz a számítógéphez.
1. A számítógépen töltse le a [Windows Device Recovery Tool (WDRT) eszközt.](https://support.microsoft.com/help/12379)
1. Töltse le [a HoloLens évfordulós frissítés helyreállítási csomagját.](https://aka.ms/hololensrecovery)
1. A letöltések befejezése után nyissa meg a **Fájlkezelő** Letöltések parancsát, kattintson a jobb gombbal az előbb letöltött tömörített (.zip) mappára, majd válassza a Extract all Extract all Extract (Összes kibontása) lehetőséget a fájl  >     >   kibontásához.
1. A HoloLens-eszközzel együtt biztosított mikro USB-kábellel csatlakoztassa a HoloLens-eszközt a számítógépéhez. Ez akkor is működik a legjobban, ha más kábelekkel csatlakoztatta a HoloLens-eszközt.
1. A WDRT automatikusan észleli a HoloLens-eszközt. Válassza a **Microsoft HoloLens** csempét.
1. A következő képernyőn válassza a **Manuális csomagválasztás** lehetőséget, majd nyissa meg a korábban kibontott mappát.
1. Válassza ki a telepítőfájlt (.ffu).
1. Válassza **a Szoftver telepítése** lehetőséget, majd kövesse az utasításokat.

**Ha a WDRT nem észleli az eszközt**

Ha a WDRT nem észleli a HoloLens-eszközt, próbálja meg újraindítani a számítógépet. Ha ez nem működik, válassza a Saját eszköz nem észlelhető **lehetőséget,** válassza a **Microsoft HoloLens** lehetőséget, majd kövesse az utasításokat.

## <a name="related-articles"></a>Kapcsolódó cikkek

- [A HoloLens 2 kibocsátási megjegyzései](https://docs.microsoft.com/hololens/hololens-release-notes)
- [Mi az Windows Update Vállalatoknak?](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Eszközök hozzárendelése karbantartási csatornákhoz a Windows 10 frissítésekhez](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Windows 10-szoftverfrissítések kezelése az Intune-ban](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
