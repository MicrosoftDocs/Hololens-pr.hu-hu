---
title: A HoloLens újraindítása, alaphelyzetbe állítása vagy helyreállítása
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: How to use Advanced Recovery Companion to flash an image to HoloLens 2 (Az Advanced Recovery Companion használata kép a HoloLens 2-ben való flashhez).
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: be33eb5d06ee7d63f1f598792ff75605b0eb4424
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923635"
---
# <a name="restart-reset-or-recover-hololens-2"></a>A HoloLens 2 újraindítása, alaphelyzetbe állítása vagy helyreállítása

>[!IMPORTANT]
> A hibaelhárítási eljárás elkezdése előtt győződjön meg arról, hogy az eszköz **20–40%-os** akkumulátor-kapacitással rendelkezik, ha lehetséges. A [tápkapcsoló alatt](hololens2-setup.md#lights-that-indicate-the-battery-level) található akkumulátorjelző világítással gyorsan ellenőrizheti az akkumulátor kapacitását anélkül, hogy bejelentkezik az eszközre.

Használja a HoloLens 2-höz csatlakoztatott usb [type-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) kábelt, mivel ez a legjobb módszer az eszköz feltöltésére. A akkumulátor 18W energiát ad (9V at 2A). A mellékelt fali akkumulátor használatával a HoloLens 2-eszközök az akkumulátort kevesebb mint 65 perc alatt megtelik, amikor az eszköz készenléti állapotban van. Ha ezek a kiegészítők nem érhetők el, győződjön meg arról, hogy a rendelkezésre álló tápegység legalább 15W energiát képes támogatni.

> [!NOTE]
> Ha lehetséges, kerülje a számítógép usb-kapcsolaton keresztüli feltöltését, ami lassú.

Ha az eszköz megfelelően elindult és fut, az akkumulátor töltöttségi szintjét háromféleképpen ellenőrizheti:

- A HoloLens eszköz felhasználói felületének főmenüjéről.
- Tekintse meg a LED-et a bekapcsológomb közelében (40%-os díjért legalább két folytonos LED-et kell látnia).
    - Ha az eszköz töltődik, az akkumulátor kijelzője felgyúsodik, és jelzi az aktuális töltöttségi szintet.  Az utolsó világítás elhalványul, és kihalványul, ami aktív díjszabást jelez.
    - Ha a HoloLens be van stb., az akkumulátor kijelzője öt lépéssel jeleníti meg az akkumulátor töltöttségi szintjét.
    - Ha az öt világítás közül csak az egyik van bekapcsolva, az akkumulátor töltöttségi szintje 20% alatt van.
    - Ha az akkumulátor töltöttségi szintje kritikusan alacsony, és megpróbálja bekapcsolni az eszközt, az egyik világítás rövid időre villog, majd kiússik.
- A gazdagépen nyissa meg a **Fájlkezelő,** és keresse meg a HoloLens 2 eszközt a bal oldalon az Ez a **számítógép alatt.** Kattintson a jobb gombbal az eszközre, majd válassza a **Tulajdonságok lehetőséget.** Egy párbeszédpanelen megjelenik az akkumulátor töltöttségi szintje.

   ![A HoloLens 2 tulajdonságokat bemutató képernyője az akkumulátor töltöttségi szintjét jeleníti meg](images/ResetRecovery2.png)

Ha az eszköz nem indítható el az indítási menüben, jegyezze fel a LED megjelenését és az eszköz enumerálását a gazdagépen. Ezután kövesse [a hibaelhárítási útmutatót.](hololens-troubleshooting.md) Ha az eszköz állapota nem egyezik a hibaelhárítási útmutatóban felsorolt állapotokkal, hajtsa végre a merevlemez-visszaállítási eljárást úgy, hogy az eszköz a tápellátáshoz, nem pedig a gazdagéphez csatlakozik. [](hololens-recovery.md#hard-reset-procedure) Várjon legalább egy órát, amíg az eszköz díjat számít fel.

## <a name="reset-the-device"></a>Az eszköz alaphelyzetbe állítása

Bizonyos körülmények között előfordulhat, hogy manuálisan kell alaphelyzetbe állítania az eszközt a szoftver felhasználói felületének használata nélkül.

### <a name="standard-procedure"></a>Szabványos eljárás

1. A Type-C kábel leválasztása az eszköz tápellátásról vagy a gazdaszámítógépről való leválasztása érdekében.

2. Nyomja le és tartsa lenyomva a **bekapcsológombot** 15 másodpercig. Minden LED-nek kikapcsolva kell lennie.

3. Várjon 2–3 másodpercet, majd nyomja le röviden a **bekapcsológombot.** A bekapcsológombhoz közeli LED-ek kigyűjnek, és az eszköz elindul.

4. Csatlakoztassa az eszközt a gazdagéphez, majd nyissa meg Eszközkezelő. (A Windows 10 nyomja le a **Windows** billentyűt, majd az **X** billentyűt, és válassza a **Eszközkezelő** lehetőséget.) Győződjön meg arról, hogy az eszköz helyesen számba veszi *Microsoft HoloLens* az alábbi képen látható módon:

   ![HoloLens 2 MicrosoftHoloLensRecovery devive manager](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Visszaállítási eljárás

Ha a normál alaphelyzetbe állítási eljárás nem működött, használja a visszaállítható visszaállítási eljárást:

1. A Type-C kábel leválasztása az eszköz tápellátásról vagy a gazdaszámítógépről való leválasztása érdekében.

2. Tartsa lenyomva a **hangerőt**  +   15 másodpercig. Az eszköz automatikusan újraindul.

4. Csatlakoztassa az eszközt a gazdaszámítógéphez.

5. Nyissa Eszközkezelő a Windows 10 (a windowsos billentyűvel, majd az **X** billentyűvel, majd válassza a **Eszközkezelő)** lehetőséget.  Győződjön meg arról, hogy az eszköz helyesen számba veszi *Microsoft HoloLens* az alábbi képen látható módon:

   ![HoloLens 2 MicrosoftHoloLensRecovery eszköz maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Az eszköz perjelének tisztítása

Rendkívüli helyzetekben előfordulhat, hogy a HoloLens 2-t "tiszta flash"-re kell "felrakni". Vegye figyelembe, hogy a perjeles perjel várhatóan nem érinti a következő problémákat:
- [Szín egységességének megjelenítése](hololens2-display.md)
- Rendszerindítás hanggal, de nem jelenik meg a kimenet
- [1-3-5 LED minta](hololens2-setup.md#lights-to-indicate-problems)
- [Túlmelegedés](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Operációsrendszer-összeomlások (amelyek eltérnek az alkalmazás-összeomlástól)

Az eszközt két módon lehet újrafedni. Mindkét esetben először telepítenie kell az [Advanced Recovery Companiont a Windows Áruházból.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)

>[!WARNING]
>Ha újrafésedi az eszközt, az összes személyes adata, alkalmazása és beállítása törlődik, beleértve a TPM alaphelyzetbe állítási információit is.

Alapértelmezés szerint az Advanced Recovery Companion a legújabb funkció kiadási build [](hololens-release-notes.md#) letöltésére van beállítva. Itt elolvashatja a kibocsátási megjegyzéseket a legújabb funkció kiadásának megismerése érdekében. Ha a legújabb HoloLens 2 Full Flash Update -csomagot (FFU) le kell töltenie az eszköz reflash eleméhez az Advanced Recovery Companion segítségével, kattintson ide a legújabb havi [HoloLens 2](https://aka.ms/hololens2download)rendszerkép letöltéséhez. Ez a verzió a legújabb általánosan elérhető build.

A perjeles eljárás előtt győződjön meg arról, hogy az alkalmazás telepítve van és fut a Windows 10 számítógépen, és készen áll az eszköz észlelésére. Arról is győződjön meg, hogy a HoloLensért legalább 40%-os díjat kell fizetnie.

![HoloLens 2 – tiszta perjel képernyőfelvétel](images/ARC1.png)

### <a name="normal-procedure"></a>Normál eljárás

1. Amíg a HoloLens-eszköz fut, csatlakoztassa a Windows 10 számítógéphez, ahol korábban megnyitotta az Advanced Recovery-társalkalmazást.
 
   A rendszer automatikusan észleli az eszközt, és a Speciális helyreállítást kísérő alkalmazás felhasználói felülete elindítja a frissítési folyamatot:

   ![A HoloLens 2 tiszta perjeles kezdőképernyője](images/ARC2.png)

3. Válassza ki a HoloLens 2 eszközt az Advanced Recovery Companion alkalmazás felhasználói felületén, és kövesse az utasításokat a perjel befejezéséhez.

### <a name="manual-procedure"></a>Manuális eljárás

Ha a HoloLens 2 nem indul el megfelelően, vagy ha az Advanced Recovery Companion nem tudja észlelni az eszközt, előfordulhat, hogy helyreállítási módba kell tennie az eszközt:

1. A Type-C kábel leválasztása az eszköz tápellátásról vagy a gazdaszámítógépről való leválasztása érdekében.

2. Nyomja le és tartsa lenyomva a **bekapcsológombot** 15 másodpercig. Minden LED-nek ki kell kapcsolnia.

3. A hangerőszabályzó **gomb megnyomása** közben nyomja le és engedje el a **bekapcsológombot** az eszköz elindítani. Várjon 15 másodpercet, majd engedje fel **a kötet fel gombját.** Csak az öt LED középső LED-e lesz begyűjteve.

4. Csatlakoztassa az eszközt a gazdagéphez, és nyissa meg Eszközkezelő. (A Windows 10 nyomja le a **Windows** billentyűt, majd az **X** billentyűt, majd válassza a Eszközkezelő **lehetőséget.)** Győződjön meg arról, hogy az eszköz helyesen számba veszi Microsoft HoloLens az alábbi képen látható módon:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   A rendszer automatikusan észleli az eszközt, és a Speciális helyreállítást kísérő alkalmazás felhasználói felülete elindítja a frissítési folyamatot:

   ![A HoloLens 2 tiszta perjeles képernyője](images/ARC2.png)

6. Válassza ki a HoloLens 2 eszközt az Advanced Recovery Companion alkalmazás felhasználói felületén, majd kövesse az utasításokat a perjel befejezéséhez.

## <a name="troubleshoot-advanced-recovery-companion"></a>Az Advanced Recovery Companion hibaelhárítása

1. Mielőtt megpróbálkozás a flash eszközzel, győződjön meg arról, hogy az eszköz 40%-os vagy annál nagyobb díjat számít fel.

2. Ellenőrizze, hogy az eszköz zárolása fel van-e oldva.

3. Ha az ARC nem észleli az eszközt, ellenőrizze, hogy tud-e csatlakozni az eszközhöz Fájlkezelő számítógépen található kapcsolaton keresztül. Ha nem tudja;

    1.  Előfordulhat, hogy az eszközön USB-szabályzatok tiltják le ezt a kapcsolatot. Ha igen, próbálja ki [a Manual Flashing mode (Manuális flash mód) módot.](hololens-recovery.md#manual-procedure)
    2.  Ha nincsenek házirendek, próbálkozzon egy másik USB-kábellel.

1. Ellenőrizze, hogy az eszköz nem [1-3-5 LED-es mintát jelenít-e meg.](hololens2-setup.md#lights-to-indicate-problems)

## <a name="download-arc-without-using-the-app-store"></a>AZ ARC letöltése az alkalmazás-áruház használata nélkül

Ha az it-környezet megakadályozza a Windows Áruházbeli alkalmazás használatát, vagy korlátozza a kiskereskedelmi áruházhoz való hozzáférést, a rendszergazda "offline" telepítési útvonalon keresztül elérhetővé tudja tenni az alkalmazást.

 >[!NOTE]
 > - A rendszergazdák az alkalmazást a System Center Konfigurációkezelő (SCCM) vagy az Intune használatával is terjesztheti.
 > - Ez az útmutató az Advanced Recovery Companion funkcióval foglalkozik, de a folyamat más "offline" alkalmazásokhoz is használható.

Az üzembe helyezési útvonal engedélyezéséhez kövesse az alábbi lépéseket:

1. A Microsoft Store Vállalatoknak [jelentkezzen](https://businessstore.microsoft.com) be egy Azure Active Directory identitással.

1. Kattintson a **Kezelés – Beállítások elemre.** A Vásárlási **élmény alatt kapcsolja** be az Offline alkalmazások megjelenítése **et.**

1. Keresse fel **a csoportomért való vásárlást,** és keressen rá az [**_Advanced Recovery Companion kifejezésre._**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)

1. Módosítsa a **Licenc típusa beállítását** **_offline _,_*majd válassza a _ Kezelés* lehetőséget.**

1. A **Csomag letöltése offline használatra alatt válassza** a második kék Letöltés **gombot.** Győződjön meg arról, hogy a *fájlkiterjesztés .appxbundle.*

    - Ha az asztali számítógép jelenleg rendelkezik internet-hozzáféréssel, kattintson duplán a csomagra az alkalmazás telepítéséhez.

    - Ha a célszámítógépen nincs internetkapcsolat, kövesse az alábbi lépéseket:
       1. Válassza ki a nem kódolatlan licencet, majd válassza a **Licenc létrehozása lehetőséget.**
       2. A **Szükséges keretrendszerek alatt válassza** a Letöltés **lehetőséget.**
       3. A DISM használatával alkalmazza a csomagot a függőséggel és a licenccel. Futtassa a következő parancsot egy rendszergazdai parancssorból:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > Előfordulhat, hogy a jelen példakódban lévő verziószám nem egyezik a jelenleg elérhető verzióval. Előfordulhat, hogy más letöltési helyet választott, mint a példában. Szükség szerint módosítja a parancsot.

> [!TIP]
> Ha az FFU offline telepítéséhez az Advanced Recovery Companiont tervezi használni, hasznos lehet a flash lemezkép letöltése. [**Töltse le a HoloLens 2 aktuális rendszerképét.**](https://aka.ms/hololens2download)


Egyéb erőforrások:
- [Offline alkalmazások terjesztése](/microsoft-store/distribute-offline-apps) 
- [DISM alkalmazáscsomag (.appx vagy .appxbundle) – karbantartási parancssori beállítások](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
