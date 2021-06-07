---
title: A HoloLens 1 újraindítása, alaphelyzetbe állítása vagy helyreállítása
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Hogyan használható a Windows Eszköz-helyreállítási eszköz egy kép a HoloLens 1st Gen-ben való flash eleméhez.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, Windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f855aa84a347edc85e5b9f02458721778eb2515a
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378082"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>A HoloLens újraindítása, alaphelyzetbe állítása vagy helyreállítása (1. generációs)

Ha problémákat tapasztal a HoloLens-sel kapcsolatban, megpróbálhatja újraindítani vagy alaphelyzetbe állítani az eszközt, vagy akár újra is perelheti az eszközt az eszköz helyreállításával. Ez a cikk végigvezeti a javasolt helyreállítási lépések sorrendjén.

Ha helyre kell állítania egy HoloLens 2-t, tekintse meg [a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery)helyreállítását, mivel ez a folyamat eltér.

> [!NOTE]
> Ez a cikk a HoloLens-eszközre és -szoftverre összpontosít. Ha a hologramok nem jól néznek ki, a **[HoloLens-környezet](hololens-environment-considerations.md)** szempontjait és a hologramminőséget javítására irányuló tényezőkkel kapcsolatos információkért tekintse meg.

## <a name="restart"></a>Újraindítás

### <a name="do-a-safe-restart-by-using-cortana"></a>Biztonságos újraindítás Cortana használatával

A HoloLens újraindításának legbiztonságosabb módja a Cortana használata, amely általában az első lépés, amikor problémát tapasztal a HoloLensben.

> [!NOTE] 
> A Cortana nem minden eszközön érhető el.
> - Cortana minden HoloLens- (1. generációs) eszközön elérhető. 
> - Cortana a Windows Holograpic 2004-es verziójának frissítése előtti builden érhető el a HoloLens 2-eszközökön.

1. Kapcsolja be a HoloLenst.
1. Győződjön meg arról, hogy a felhasználó be van jelentkezve, és az eszköz nem vár jelszóra a zárolás feloldásához.
2. Mondja ki a "Hey Cortana, restart" vagy a "Hey Cortana, restart" (Cortana, újraindítás) parancsot.
3. Cortana válaszolni fog, és megerősítést kér. Várjon, amíg egy hang lejátszásra vár a kérdés után, majd mondja ki az "Igen" választ. Az eszköz újraindul.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Biztonságos újraindítás a bekapcsoló gombbal

Ha továbbra sem tudja újraindítani az eszközt, próbálja meg újraindítani a **bekapcsológombbal:**

1. Nyomja le és tartsa lenyomva a **bekapcsológombot** 5 másodpercig. 1 másodperc múlva mind az öt LED-et el fogja látni, majd lassan kikapcsolja őket 1-ről 1-re jobbról balra. 5 másodperc elteltével az összes LED ki lesz kapcsolva, ami a sikeres leállítást jelzi.
      
   > [!IMPORTANT]
   > Ne nyomja le azonnal a gombot, miután az összes LED ki van kapcsolva.
1. Várjon 1 percet, amíg a leállítás befejeződik. Előfordulhat, hogy a leállítás még a kijelzők kikapcsolása után is folyamatban van.
2. Kapcsolja be újra az eszközt  a bekapcsológomb 1 gombra való lenyomásával.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Biztonságos újraindítás a Windows eszközportál

> [!NOTE]
> Ehhez a folyamathoz a HoloLenst fejlesztői eszközként kell konfigurálni. További információ: [Windows eszközportál.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)

Ha az előző eljárás nem működött, próbálja meg újraindítani az eszközt a [Windows eszközportál.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) A jobb felső sarokban keresse meg az eszköz újraindítási vagy leállítható beállítását.

### <a name="do-an-unsafe-forced-restart"></a>Nem biztonságos kényszerített újraindítás

Ha az előző metódusok nem indítani a HoloLenst, kényszerítsen újraindítást. Ez a módszer egyenértékű az akkumulátor eltávolításával és újratelepítésével. Ez azért veszélyes, mert az eszközt sérült állapotban hagyhatja. Ha ez történik, akkor a HoloLenst is fel kell flashmenten.  

> [!WARNING]
> Ez egy potenciálisan káros metódus, és csak akkor szabad használni, ha a korábban hivatkozott metódusok nem működtek.

1. Tartsa lenyomva a **bekapcsológombot** legalább 10 másodpercig.
   - A gomb 10 másodpercnél hosszabb ideig is tartható.
   - A LED-tevékenységeket biztonságosan figyelmen kívül hagyhatja.
1. Engedje el a gombot, és várjon 2–3 másodpercet.
1. Nyomja le és tartsa lenyomva a **bekapcsológombot** 1 gombra.
1. Ha továbbra is problémákat  tapasztal, nyomja meg a bekapcsológombot 4 másodpercig, amíg el nem halványulnak az akkumulátor kijelzői, és a képernyő nem jelenít meg hologramokat. Várjon 1 percet, majd nyomja meg ismét a **bekapcsológombot** az eszköz bekapcsoláshoz.

## <a name="reset-to-factory-settings"></a>Visszaállítás a gyári beállításokra

> [!NOTE]
> Az akkumulátor alaphelyzetbe állításhoz legalább 40%-os töltöttség szükséges.

Ha a HoloLensben továbbra is probléma van, próbálja meg visszaállítani a gyári állapotra. Ez a lépés megtartja a rajta telepített Windows Holographic szoftver verzióját, és minden mást visszaad a gyári beállításoknak.

>[!WARNING]
> Ha alaphelyzetbe állítja az eszközt, az összes személyes adata, alkalmazása és beállítása törlődik, beleértve a TPM alaphelyzetbe állítási adatait is. Az alaphelyzetbe állítás csak a Windows Holographic legújabb telepített verzióját telepíti. Minden inicializálási lépést újra végre kell majd hoznia (be kell állítania, csatlakoznia kell a Wi-Fi-hez, létre kell hoznia egy felhasználói fiókot, le kell töltenie az alkalmazásokat stb.).

1. Nyissa meg a Beállítások alkalmazást, majd válassza az **Update**  >  **Recovery lehetőséget.**
1. Válassza az **Eszköz alaphelyzetbe állítása** lehetőséget, és olvassa el a megerősítő üzenetet.
1. Erősítse meg az alaphelyzetbe állítást. Az eszköz újraindul, és megjeleníti a forgó fogaskerékkészletet és a folyamatjelző sávot.
1. Várjon körülbelül 30 percet, amíg a folyamat befejeződik. Amikor végzett, az eszköz újraindul a "kész" felhasználói élményben.

## <a name="reinstall-the-operating-system"></a>Az operációs rendszer újratelepítése

Ha az eszköz újraindítása és alaphelyzetbe állítása után is probléma lép fel, egy helyreállítási eszközzel újratelepítheti a HoloLens operációs rendszert és a belső vezérlőprogramot.  

A HoloLensnek az alaphelyzetbe állításhoz szükséges adatai egy teljes flash frissítésbe (FFU) vannak csomagolva, amely egy .iso-, .wim- vagy .vhd-fájlhoz hasonlít. [Tudnivalók az FFU képfájlformátumokról.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

A Windows Eszköz-helyreállítási eszközzel új operációs rendszert telepíthet a HoloLens (1. generációs) eszközére. Az eszköz használata előtt nézze meg, hogy a HoloLens újraindítása vagy alaphelyzetbe állítása megoldja-e a problémát.

A helyreállítási folyamat egy ideig tart. Ha ez megtörtént, a Windows Holographic szoftver legújabb verziója lesz telepítve.

Az eszköz csak akkor használható, ha Windows 10 vagy újabb, legalább 4 GB szabad tárhellyel. Ez az eszköz nem futtatható virtuális gépen.

### <a name="recover-your-hololens"></a>A HoloLens helyreállítása

1. Töltse le és telepítse a [Windows Eszköz-helyreállítási eszközt](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) a számítógépre.
1. Csatlakoztassa a HoloLenst (1. generációs) a számítógéphez a HoloLenshez csatlakoztatott Micro USB-kábellel.
1. Nyissa meg a Windows Eszköz-helyreállítási eszközt, és kövesse az utasításokat.

Ha a HoloLens (1. generációs) nem észlelhető automatikusan, válassza a **Saját eszköz nem észlelhető lehetőséget.** Ezután kövesse az utasításokat az eszköz helyreállítási módba való beállításhoz.

### <a name="manual-flashing-mode"></a>Manuális flash mód

Ha a rendszer nem észleli az eszközt, kövesse az alábbi lépéseket a flash (flash) módba való beállításhoz:

1. Válassza le az eszközt bármely áramforrásról.
1. Ha az eszköz be van kapcsolva, tartsa lenyomva a **bekapcsológombot,** amíg teljesen ki nem vált.
2. Tartsa lenyomva **a hangerőt gombot,** és koppintson röviden a **bekapcsoló gombra.** Az eszköznek el kell indulni, és csak a középső LED-et kell megjelenítenie.
3. Csatlakoztassa az eszközt a számítógéphez.
4. Nyissa meg a Windows Eszköz-helyreállítási eszközt.
5. Válassza **a Nem észlelhető az eszközöm lehetőséget,** majd a **HoloLens lehetőséget.** 
6. Az eszköz helyreállításához kövesse az utasításokat.
