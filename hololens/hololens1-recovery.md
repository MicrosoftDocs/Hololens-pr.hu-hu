---
title: Újraindítás, visszaállítás vagy helyreállítás HoloLens 1.
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: A Windows Eszköz-helyreállítási eszköz használata egy kép flash-HoloLens 1. generációs rendszerképhez.
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
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428644"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Újraindítás, visszaállítás vagy helyreállítás HoloLens (1. generációs)

Ha problémákat tapasztal a HoloLens, megpróbálkozás az újraindítással, az alaphelyzetbe állítással, vagy akár az eszköz újrafedésével az eszköz helyreállításával. Ez a cikk végigvezeti a javasolt helyreállítási lépéseken.

Ha a [2.](hololens-recovery.md)HoloLens helyre kell állítania, HoloLens a folyamat eltér.

> [!NOTE]
> Ez a cikk az eszköz HoloLens szoftverekkel foglalkozik. Ha a hologramok nem megfelelőek, a HoloLens a hologram minőségét javítására javítására vonatkozó környezeti szempontokat. **[](hololens-environment-considerations.md)**

## <a name="restart"></a>Újraindítás

### <a name="do-a-safe-restart-by-using-cortana"></a>Biztonságos újraindítás a Cortana

A HoloLens újraindításának legbiztonságosabb módja a Cortana használata, amely általában az első lépés, amikor problémát tapasztal a HoloLens.

> [!NOTE] 
> Cortana nem minden eszközön érhető el.
> - Cortana az összes HoloLens (1. generációs) eszközön elérhető. 
> - Cortana a HoloLens Holograpic 2004-es verziójának frissítése előtt Windows 2 eszközön érhető el.

1. Kapcsolja be a HoloLens.
1. Győződjön meg arról, hogy a felhasználó be van jelentkezve, és az eszköz nem vár jelszóra a zárolás feloldásához.
2. Mondja ki a "Hey Cortana, restart" vagy a "Hey Cortana, restart" (Helló, újraindítás) vagy "Hey Cortana.
3. Cortana válaszol, és megerősítést kér. Várjon, amíg a kérdés után egy hang lejátszása meg fog zajni, majd mondja ki az "Igen" választ. Az eszköz újraindul.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Biztonságos újraindítás a bekapcsoló gombbal

Ha továbbra sem tudja újraindítani az eszközt, próbálja meg újraindítani a **bekapcsológombbal:**

1. Nyomja le és tartsa lenyomva a **bekapcsológombot** 5 másodpercig. 1 másodperc múlva mind az öt LED-et el fogja látni, majd lassan kikapcsolja őket 1-ről jobbra. 5 másodperc elteltével az összes LED ki lesz kapcsolva, ami a sikeres leállítást jelzi.
      
   > [!IMPORTANT]
   > Ne nyomja le azonnal a gombot, miután az összes LED ki van kapcsolva.
1. Várjon 1 percet, amíg a leállítás befejeződik. Előfordulhat, hogy a leállítás még a kijelzők kikapcsolása után is folyamatban van.
2. Kapcsolja be újra az eszközt  úgy, hogy 1 gombra lenyomva tartja a bekapcsológombot.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Biztonságos újraindítás a Windows Eszközportál

> [!NOTE]
> Ehhez a HoloLens fejlesztői eszközként kell konfigurálni. További információ: [Windows Eszközportál.](/windows/mixed-reality/using-the-windows-device-portal)

Ha az előző eljárás nem működött, próbálja meg újraindítani az eszközt a [következő Windows Eszközportál.](/windows/mixed-reality/using-the-windows-device-portal) A jobb felső sarokban keresse meg az eszköz újraindítási vagy leállítható beállítását.

### <a name="do-an-unsafe-forced-restart"></a>Nem biztonságos kényszerített újraindítás

Ha az előző metódusok nem újraindítják a HoloLens, kényszerítsen újraindítást. Ez a módszer egyenértékű az akkumulátor eltávolításával és újratelepítésével. Ez azért veszélyes, mert az eszközt sérült állapotban hagyhatja. Ha ez történik, akkor flash-HoloLens.  

> [!WARNING]
> Ez egy potenciálisan káros metódus, és csak akkor szabad használni, ha a korábban hivatkozott metódusok nem működtek.

1. Tartsa lenyomva a **bekapcsológombot** legalább 10 másodpercig.
   - A gomb 10 másodpercnél hosszabb ideig is tartható.
   - A LED-tevékenységeket biztonságosan figyelmen kívül hagyhatja.
1. Engedje el a gombot, és várjon 2–3 másodpercet.
1. Nyomja le és tartsa lenyomva a **bekapcsológombot** 1 gombra.
1. Ha továbbra is problémákat  tapasztal, nyomja meg a bekapcsológombot 4 másodpercig, amíg az akkumulátor kijelzői el nem halványulnak, és a képernyő nem jelenít meg hologramokat. Várjon 1 percet,  majd nyomja le újra a bekapcsológombot az eszköz bekapcsoláshoz.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Vissza verzióra való átkértség – HoloLens (1. generáció)

Bizonyos esetekben érdemes lehet a szoftver korábbi verziójára HoloLens vissza. Ezt a Windows Eszköz-helyreállítási eszköz használatával állíthatja vissza HoloLens korábbi verzióra.

> [!NOTE]
> A korábbi verzióra való visszaút törli a személyes fájlokat és beállításokat.

Az 1. HoloLens előző verziójára való visszaúthoz kövesse az alábbi lépéseket:

1. Győződjön meg arról, hogy nincs telefonja vagy Windows a számítógéphez csatlakoztatva.
1. A számítógépen töltse le a [Windows Device Recovery Tool (WDRT) eszközt.](https://support.microsoft.com/help/12379)
1. Töltse le [a HoloLens évfordulós frissítés helyreállítási csomagját.](https://aka.ms/hololensrecovery)
1. Ha a letöltések befejeződnek, nyissa meg a **Fájlkezelő**  >  **Letöltések gombra.** Kattintson a jobb gombbal az előbb letöltött tömörített mappára, és válassza a Extract all Extract **(Összes** kibontás) lehetőséget a  >   kicsomagoláshoz.
1. Csatlakozás a HoloLens a számítógépére a hozzá csatlakoztatott mikro-USB-kábellel. (Ez akkor is működik a legjobban, ha más kábeleket használt a HoloLens csatlakoztatáshoz.)
1. A WDRT automatikusan észleli a HoloLens. Válassza a **Microsoft HoloLens** csempét.
1. A következő képernyőn válassza a **Manuális** csomagválasztás lehetőséget, és válassza ki a 4. lépésben kicsomagolt mappában található telepítőfájlt. (Keress egy .ffu kiterjesztésű fájlt.)
1. Válassza **a Szoftver telepítése lehetőséget,** és kövesse az utasításokat.

> [!NOTE]
> Ha a WDRT nem észleli a HoloLens, indítsa újra a számítógépet. Ha ez nem működik, válassza a Saját eszköz nem észlelhető **lehetőséget,** válassza a **Microsoft HoloLens** lehetőséget, majd kövesse az utasításokat.

## <a name="reset-to-factory-settings"></a>Visszaállítás gyári beállításokra

> [!NOTE]
> Az akkumulátor alaphelyzetbe állításhoz legalább 40%-os díjat kell fizetni.

Ha a HoloLens továbbra is probléma van, próbálja meg gyári állapotba állítani. Ez a lépés megtartja a Windows holographic szoftver telepített verzióját, és minden mást visszaad a gyári beállításoknak.

>[!WARNING]
> Ha alaphelyzetbe állítja az eszközt, az összes személyes adata, alkalmazása és beállítása törlődik, beleértve a TPM alaphelyzetbe állítási adatait is. Az alaphelyzetbe állítás csak a holographic rendszer legújabb telepített Windows telepíti. Az inicializálás összes lépését újra el kell majd látnia (be kell állítania, csatlakoznia kell a Wi-Fi-hez, létre kell hoznia egy felhasználói fiókot, le kell töltenie az alkalmazásokat stb.).

1. Nyissa meg a Gépház alkalmazást, majd válassza az **Update**  >  **Recovery lehetőséget.**
1. Válassza az **Eszköz alaphelyzetbe állítása** lehetőséget, és olvassa el a megerősítő üzenetet.
1. Erősítse meg az alaphelyzetbe állítást. Az eszköz újraindul, és megjeleníti a forgó fogaskerékkészletet és egy folyamatjelző sávot.
1. Várjon körülbelül 30 percet, amíg a folyamat befejeződik. Amikor végzett, az eszköz újraindul a "kész" felhasználói élményben.

## <a name="reinstall-the-operating-system"></a>Az operációs rendszer újratelepítése

Ha az eszköz újraindítása és alaphelyzetbe állítása után is probléma lép fel, egy helyreállítási eszközzel újratelepítheti a HoloLens operációs rendszert és a belső vezérlőprogramot.  

A visszaállításhoz HoloLens szükséges adatok egy teljes flash frissítésbe (FFU) vannak csomagolva, amely egy .iso-, .wim- vagy .vhd-fájlhoz hasonlít. [Tudnivalók az FFU képfájlformátumokról.](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Az új operációs rendszert a HoloLens (1. generációs) az Windows Eszköz-helyreállítási eszközzel telepítheti. Az eszköz használata előtt nézze meg, hogy az újraindítás vagy a visszaállítás HoloLens megoldja a problémát.

A helyreállítási folyamat egy kis ideig is elthet. Ha ez megtörtént, a rendszer telepíti a Windows Holographic szoftver legújabb verzióját.

Az eszköz csak akkor használható, ha legalább Windows 10 legalább 4 GB szabad tárhellyel rendelkező számítógépet futtat. Ez az eszköz nem futtatható virtuális gépen.

### <a name="recover-your-hololens"></a>A HoloLens

1. Töltse le és telepítse [Windows eszköz-helyreállítási eszközét](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) a számítógépre.
1. Csatlakozás a HoloLens (1. generációs) csatlakoztatását a számítógéphez a számítógéphez HoloLens.
1. Nyissa meg Windows Eszköz-helyreállítási eszközt, és kövesse az utasításokat.

Ha a HoloLens (1. generációs) nem észlelhető automatikusan, válassza a Saját **eszköz nem észlelhető lehetőséget.** Ezután kövesse az utasításokat az eszköz helyreállítási módba való beállításhoz.

### <a name="manual-flashing-mode"></a>Manuális flash() mód

Ha a rendszer nem észleli az eszközt, kövesse az alábbi lépéseket, hogy flash (flash) módba váltsa:

1. Válassza le az eszközt bármely áramforrásról.
1. Ha az eszköz be van  kapcsolva, tartsa lenyomva a bekapcsológombot, amíg teljesen ki nem vált.
2. Tartsa lenyomva **a kötetet fel** gomb, és koppintson röviden a **bekapcsoló gombra.** Az eszköznek csak a középső LED-et szabad elindulni és megjelenítenie.
3. Csatlakoztassa az eszközt a számítógéphez.
4. Nyissa meg Windows Eszköz-helyreállítási eszközt.
5. Válassza **a Saját eszköz nem észlelhető lehetőséget,** majd válassza a **HoloLens.** 
6. Az eszköz helyreállításához kövesse az utasításokat.
