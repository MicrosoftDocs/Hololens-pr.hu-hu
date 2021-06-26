---
title: HoloLens-eszköz hibaelhárítása
description: Naprakész maradhat a HoloLens-eszközök leggyakoribb megoldásaival és hibaelhárítási módszereivel kapcsolatban.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problémák, hiba, hibaelhárítás, javítás, súgó, támogatás, HoloLens, emulátor
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924621"
---
# <a name="device-troubleshooting"></a>Eszköz hibaelhárítása

Ez a cikk több gyakori HoloLens-probléma megoldását ismerteti.

>[!IMPORTANT]
> A hibaelhárítási eljárás elkezdése előtt győződjön meg arról, hogy az eszköz **20–40** százalék akkumulátor-kapacitással rendelkezik, ha lehetséges. A [tápkapcsoló alatt](hololens2-setup.md#lights-that-indicate-the-battery-level) található akkumulátorjelző világítással gyorsan ellenőrizheti az akkumulátor kapacitását anélkül, hogy bejelentkezik az eszközre.

<a id="list"></a>

**Ismert problémák**
- [A Remote Assist videó 20 perc után lefagy](#remote-assist-video-freezes-after-20-minutes)
- [Az automatikus bejelentkezés bejelentkezést kér](#auto-login-asks-for-log-in)
- [Microsoft Edge nem indul el](#microsoft-edge-fails-to-launch)
- [A billentyűzet nem vált át speciális karakterekre](#keyboard-doesnt-switch-to-special-characters)
- [A zárolt fájlok letöltésekor nem jelenik meg hiba](#downloading-locked-files-doesnt-error)
- [Eszközportál feltöltési/letöltési időkorrekta](#device-portal-file-uploaddownload-times-out)
- [Kék képernyő, miután az Insider előzetes verzióból való igénylést egy Insider buildeléses flash() módban megjelenő eszközön](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [A OneDrive nem tölt fel automatikusan képeket](#onedrive-doesnt-automatically-upload-pictures)

**Általános**
- [A HoloLens nem válaszol vagy nem indul el](#hololens-is-unresponsive-or-wont-start)
- ["Kevés lemezterület" hiba](#low-disk-space-error)
- [Nem sikerül a beeső hiba](#calibration-fails)
- [Nem tudok bejelentkezni, mert a HoloLensem korábban valaki más számára lett beállítva](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [A Unity nem működik](#unity-isnt-working)
- [Windows eszközportál nem működik megfelelően](#windows-device-portal-isnt-working-correctly)
- [A HoloLens Emulator nem működik](#the-hololens-emulator-isnt-working)

**Bevitel**
- [A hangparancsok nem működnek](#voice-commands-arent-working)
- [A kézi bevitel nem működik](#hand-input-isnt-working)

**Kapcsolódás**
- [Nem lehet csatlakozni a Wi-Fi-hez](#cant-connect-to-wi-fi)

**Külső eszközök** 
- [A Bluetooth-eszközök nem párosodnak](#bluetooth-devices-arent-pairing)
- [Az USB-C mikrofon nem működik](#usb-c-microphone-isnt-working)
- [A Beállítások között elérhetőként felsorolt eszközök nem működnek](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>A Remote Assist videó 20 perc után lefagy

> [!NOTE]
> Az ismert probléma súlyossága miatt jelenleg szüneteltetjük a Windows Holographic 21H1-es verziójának rendelkezésre állását. Ha továbbra is a 21H1-es verzióra szeretné frissíteni az eszközeit, tekintse meg az oldal tetején található kibocsátási [megjegyzéseinkben található utasításokat.](hololens-release-notes.md)

A [Windows Holographic legújabb, 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1)verziójában a Remote Assist egyes felhasználói a hívások során 20 percnél régebbi videófagyást tapasztaltak. Ez egy **ismert probléma.**

### <a name="workarounds"></a>Kerülő megoldások

#### <a name="restart-in-between-calls"></a>Újraindítás hívások között

Ha a hívások hossza 20 percnél hosszabb, és ezt a problémát tapasztalja, próbálja meg újraindítani az eszközt. Ha újraindítja az eszközt a Remote Assist-hívások között, az eszköz frissül, és jó állapotba kerül.

Ha gyorsan újraindít egy eszközt a [Windows Holographic 21H1-es verziójában,](hololens-release-notes.md#windows-holographic-version-21h1) nyissa meg a Start menüt, válassza a felhasználó ikont, majd válassza az **Újraindítás lehetőséget.**

#### <a name="revert-to-an-older-build"></a>Visszaállítás régebbi buildre

Egyes ügyfelek azt tapasztalják, hogy az operációs rendszer korábbi verziójára való visszatéréskor már nem tapasztalják ezt a problémát. Ha azt tapasztalja, hogy az eszközein ez a probléma áll be, próbálkozzon az alábbi lépésekkel:


Workarounds:

- Ha a vállalata számára is elérhető, a fogyasztói Microsoft-fiókok támogatják az automatikus kamerafeltöltést. Munkahelyi vagy iskolai fiókján kívül Microsoft-fiók is bejelentkezhet az alkalmazásba (a OneDrive alkalmazás támogatja a kettős bejelentkezést). A OneDrive Microsoft-fiók profilból engedélyezheti az automatikus, háttérkamerás felvételeket.

- Ha nem tud biztonságosan használni fogyasztói Microsoft-fiók a fényképek automatikus feltöltéséhez, manuálisan feltölthet fényképeket munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásból. Győződjön meg arról, hogy be van jelentkezve munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásban. Kattintson a **+** gombra, majd válassza a **Feltöltés lehetőséget.** Keresse meg a feltölteni kívánt fényképeket vagy videókat a **Pictures (Képek) > Camera Roll (Kameragörgetés) kiválasztásával.** Válassza ki a feltölteni kívánt fényképeket vagy videókat, majd kattintson a **Megnyitás gombra.**


1. [A Windows Holographic 20H2 – May 2021 Update build letöltése](https://aka.ms/hololens2download/10.0.19041.1146)
1. Kövesse az [utasításokat az operációs rendszer korábbi verziójához való visszatéréshez](hololens-update-hololens.md#go-back-to-a-previous-version)
1. Az [eszköz operációsrendszer-frissítéseit manuálisan](hololens-updates.md#pause-updates-via-device) szüneteltetheti, vagy sok eszköz esetén az [MDM-ben keresztüli halasztás használható.](hololens-updates.md#configure-an-update-deferral-policy)

[Vissza a listához](#list)

## <a name="auto-login-asks-for-log-in"></a>Az automatikus bejelentkezés bejelentkezést kér

A HoloLens 2-eszközök konfigurálhatóak úgy, hogy automatikusan bejelentkeznek a Beállításfiókok bejelentkezési beállításai -> és a Kötelező beállításnál a Never (Soha) értéket adja   ->    ->   **meg.**  Előfordulhat, hogy egyes felhasználóknak újra be kell jelentkezniük az eszközre, amikor egy jelentős frissítéssel( például funkciófrissítéssel) frissítik az eszközt. Ez egy **ismert probléma.**

Példa arra, hogy mikor fordulhat elő ez:

- Eszköz frissítése a Windows Holographic 2004-es verziójáról (19041.xxxx build) a 21H1-es verziójú Windows Holographicra (Build 20346.xxxx)
- Egy eszköz frissítése ugyanannak a fő buildnek a nagy frissítéséhez , például a Windows Holographic 2004-es verziójáról a Windows Holographic 20H2-es verziójára
- Eszköz frissítése gyári rendszerképről a legújabb rendszerképre

Ez nem fordulhat elő a következő időszakban:

- Havi karbantartási frissítést frissítő eszközök

Módszerek használata:

- Bejelentkezési módszerek, például PIN-kód, jelszó, írisz, webes hitelesítés vagy FIDO2-kulcsok.
- Ha az eszköz PIN-kódját nem lehet megöröklni, és más hitelesítési módszerek nem érhetők el, akkor a felhasználó használhat manuális [perjeles módot.](hololens-recovery.md#manual-procedure)

[Vissza a listához](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge nem indul el

> [!NOTE]
> Ezt a problémát eredetileg a Microsoft Edge szállítási verziójával hozták létre. Ez a probléma megoldható az [új](hololens-new-edge.md)Microsoft Edge. Ha nem, kérjük, visszajelzést írjon.

Néhány ügyfél olyan problémát jelentett, Microsoft Edge nem indul el. Ezen ügyfelek esetében a probléma újraindítással továbbra is fennáll, és a Windows- vagy alkalmazásfrissítésekkel nem oldódik meg. Ha ezt a problémát tapasztalja, és megerősítette, hogy a [Windows](hololens-updates.md#manually-check-for-updates)naprakész, jelentsen be egy hibát a [Visszajelzési központ-alkalmazásból](hololens-feedback.md) a következő kategóriával és alkategóriával: Install and Update > Downloading, installing, and configuring Windows Update.

Nincsenek ismert megkerülő megoldások, mivel eddig nem sikerült megoldani a problémát. Hiba bejelentése a Visszajelzési központ segít a vizsgálatban! Ez egy **ismert probléma.**

[Vissza a listához](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>A billentyűzet nem vált át speciális karakterekre

Az OOBE során probléma lép fel, amely miatt ha a felhasználó kiválasztott egy munkahelyi vagy iskolai fiókot, és megadta a jelszavát, a billentyűzeten lévő speciális karakterekre próbál átváltani az &123 gombra koppintva, nem változik különleges karakterekre. Ez egy **ismert probléma.**

A következőt kell körül kell dolgozni:
-   Zárja be a billentyűzetet, és nyissa meg újra a szövegmezőre koppintva.
-   Helytelenül adja meg a jelszót. Ha a billentyűzetet a következő alkalommal újraindítják, az a várt módon fog működni.
- Webes hitelesítés, zárja be a billentyűzetet, és válassza **a Bejelentkezés másik eszközről lehetőséget.**
-   Ha csak számokat ad meg, a felhasználó megnyomhat és lenyomva tarthat bizonyos kulcsokat egy kibontott menü megnyitásához.
-   USB-billentyűzet használata.

Ez nincs hatással a következőre:
- Azok a felhasználók, akik személyes fiókot választanának.

[Vissza a listához](#list)


## <a name="downloading-locked-files-doesnt-error"></a>A zárolt fájlok letöltése nem hibás
> ! MEGJEGYZÉS Ez egy ismert **probléma,** amely a 20348.1403 Windows Insider buildben kijavítva.


A Windows Holographic korábbi buildjeiben zárolt fájl letöltésekor az eredmény egy HTTP-hibalap lesz. A Windows Holographic 21H1-es verziójának frissítésében a zárolt fájlok letöltésének a kipróbálása azt jelenti, hogy semmi sem látható– a fájl nem tölt le és nem jelenik meg hiba. 

[Vissza a listához](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Eszközportál feltöltési/letöltési időkorrekta
> ! MEGJEGYZÉS Ez egy ismert **probléma,** amely a 20348.1403 Windows Insider buildben kijavítva. Ha az áthidaló megoldás részeként korábban letiltotta az SSL-kapcsolatot, erősen ajánlott újra engedélyezni.


Egyes ügyfelek azt találták, hogy amikor fájlokat próbálnak feltölteni vagy letölteni, előfordulhat, hogy a művelet lefagy, majd időkorrekciót vagy soha nem fejeződik be. Ez elkülönül a "fájl[zárolva"](#downloading-locked-files-doesnt-error) ismert problémától – ez a Windows Holographic 2004-es, 20H2-es és 21H1-es piaci buildeket érinti. A problémát az okozza, hogy a Eszközportál bizonyos kéréseket kezel, és a https használata esetén a leg konzisztensen ad vissza találatot, amely az alapértelmezett beállítás. 

### <a name="workaround"></a>Áthidaló megoldás

Ez az áthidaló megoldás, amely ugyanúgy vonatkozik a Wi-Fi az UsbNcm-re, a "kötelező" beállítás letiltása az "SSL-kapcsolat" alatt. Lépjen a következő oldalra: **Eszközportál, System**( Rendszer) és válassza a **Preferences (Beállítások)** lapot. Az **Eszközbiztonság szakaszban** keresse meg az **SSL-kapcsolatot,** és törölje a jelölését a **Kötelező letiltásához.**

A felhasználónak ekkor az http:// kell lennie, https:// (IP-cím) és olyan szolgáltatások, mint a fájlok feltöltése és letöltése működni fog.

[Vissza a listához](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Kék képernyő, miután az Insider előzetes verzióból való igénylést egy Insider buildeléses flash() módban megjelenő eszközön

Ez olyan problémát jelent, amely hatással van az Insider előzetes verziójú buildet használó felhasználókra, új belső előzetes verziójú buildekkel új HoloLens 2-buildet hoz létre, majd nem regisztrálta őket az Insider programból. Ez egy **ismert probléma.**

Ez nincs hatással a következőre:
- Felhasználók, akik nincsenek regisztrálva a Windows Insider 
- Bennfentesek:
    - Ha egy eszköz az Insider buildek óta regisztrálva lett, az 18362.x verziójú volt
    - Ha egy Insider 19041.x buildet írt alá, és regisztrálva kell maradnia az Insider programban

Időző: 
- A probléma elkerülése 
    - Flash egy nem belső build. A rendszeres havi frissítések egyike.
    - Maradjon az Insider előzetes kiadásában
- Az eszköz perjelének átfedő perjele

    1. Helyezze a [HoloLens 2-t flashing (flash)](hololens-recovery.md) módba manuálisan úgy, hogy teljesen lekapcsolód, miközben nem csatlakozik. Ezután a Kötet lenyomva tartási gombra koppintva koppintson a Bekapcsoló gombra.
    
    1. Csatlakozzon a számítógéphez, és nyissa meg az Advanced Recovery Companiont.
    
    1. Flash the HoloLens 2 to the default build.

[Vissza a listához](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>A OneDrive nem tölt fel automatikusan képeket

A HoloLenshez való OneDrive alkalmazás nem támogatja a munkahelyi vagy iskolai fiókok automatikus kamerafeltöltését. Ez egy **ismert probléma.**

Workarounds:

- Ha a vállalata számára is elérhető, a fogyasztói Microsoft-fiókok támogatják az automatikus kamerafeltöltést. Munkahelyi vagy iskolai fiókján kívül Microsoft-fiók is bejelentkezhet az alkalmazásba (a OneDrive alkalmazás támogatja a kettős bejelentkezést). A OneDrive Microsoft-fiók profilból engedélyezheti az automatikus, háttérkamerás felvételeket.

- Ha nem tud biztonságosan használni fogyasztói Microsoft-fiók a fényképek automatikus feltöltéséhez, manuálisan feltölthet fényképeket munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásból. Győződjön meg arról, hogy be van jelentkezve munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásban. Kattintson a **+** gombra, majd válassza a **Feltöltés lehetőséget.** Keresse meg a feltölteni kívánt fényképeket vagy videókat a **Pictures (Képek) > Camera Roll (Kameragörgetés) kiválasztásával.** Válassza ki a feltölteni kívánt fényképeket vagy videókat, majd kattintson a **Megnyitás gombra.**

[Vissza a listához](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>A HoloLens nem válaszol vagy nem indul el

Ha a HoloLens nem indul el:

- Ha a bekapcsológomb melletti LED-ek nem világadnak meg, vagy csak egy LED villog rövid időre, előfordulhat, hogy fel kell töltenie a [HoloLenst.](hololens2-charging.md#charging-the-device)
- Ha a LED-ek bekapcsolódnak, amikor megnyomja a bekapcsológombot, de nem lát semmit a kijelzőkön, állítsa alaphelyzetbe [az eszközt.](hololens-recovery.md#hard-reset-procedure)

Ha a HoloLens lefagy vagy nem válaszol:

- Kapcsolja ki a HoloLenst úgy, hogy megnyomja a bekapcsológombot, amíg mind az öt LED ki nem kapcsolja magát, vagy 15 másodpercig, ha a LED-ek nem válaszolnak. A HoloLens-hez nyomja le újra a bekapcsológombot.

Ha ezek a lépések nem működnek, megpróbálhatja helyreállítani [HoloLens 2-es](hololens-recovery.md) vagy [HoloLens- (1. generációs) eszközét.](hololens1-recovery.md)

[Vissza a listához](#list)

## <a name="low-disk-space-error"></a>"Kevés lemezterület" hiba

Az alábbiak közül egyet vagy többet is el kell szabadítanunk egy vagy több tárolóhelyen:

- Töröljön néhány nem használt szóközt. Válassza a **Beállítások**  >  **Rendszerterek** lehetőséget, válasszon ki egy olyan helyet, amelyre már nincs  >  szüksége, majd válassza az Eltávolítás **lehetőséget.**
- Távolítsa el a elhelyezett hologramokat.
- Töröljön néhány képet és videót a Photos alkalmazásból.
- Néhány alkalmazás eltávolítása a HoloLensből. A **Minden alkalmazás** koppintson és tartsa lenyomva az eltávolítani kívánt alkalmazást, majd válassza az **Eltávolítás lehetőséget.**

[Vissza a listához](#list)

## <a name="calibration-fails"></a>A meghiúsulás

A legtöbb ember számára működnie kell, de vannak olyan esetek, amikor a beszibrálás sikertelen.
  
Néhány lehetséges ok a meghibásodásra:

- Elvonja a figyelmet, és nem követi a célokat
- Nem megfelelően el van állítva a trágár vagy karcolt eszköz vagy az eszköz vizora
- Trágár vagy karcolt szemüveg
- Bizonyos típusú kapcsolattartási objektívek és szemüveg (színes kapcsolattartó objektívek, néhány toric contact lenses, IR-blokkoló szemüveg, néhány magas szemüveg, napszemüveg vagy hasonló)
- Jobban kiejtve és perjeles mellékekkel
- Haj vagy vastag szemüveg, ha blokkolja az eszközt a tekintete előtt
- Bizonyos szemfizikai, szemkörülmények vagy szemműveletek, például keskeny szem, hosszú szempillák, amblyadás, nystagmus, a LASIK vagy más szemműveletek bizonyos esetekben

Sikertelen kísérlet esetén próbálkozzon a következővel:

- Az eszköz vizorának tisztítása
- Szemüveg tisztítása
- Az eszköz vizorának a lehető legnagyobb közelében való eltolás
- Objektumok mozgatása a vizorban az útból (például haj)
- Világítás bekapcsolása a helyiségben, vagy a közvetlen világításból való eltálás

Ha minden útmutatót követte, és a tiltása továbbra sem sikerül, letilthatja a figyelmeztetést a Beállításokban. Visszajelzést is küldhet a következő [Visszajelzési központ.](hololens-feedback.md)

A képszínekkel vagy a fényerejével kapcsolatos [hibaelhárítással kapcsolatos információkat is itt láthatja.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Az IPD beállítása nem alkalmazható a HoloLens 2-re, mivel a szempozíciókat a rendszer számítja ki. 

[Vissza a listához](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Nem tudok bejelentkezni, mert a HoloLensem korábban valaki más számára lett beállítva

Az eszközt [flash **(Flashing)**](hololens-recovery.md#clean-reflash-the-device) módba használhatja, és az Advanced Recovery Companion használatával helyreállíthatja az eszközt.

[Vissza a listához](#list)


## <a name="unity-isnt-working"></a>A Unity nem működik

- Lásd: [Install the tools](/windows/mixed-reality/install-the-tools) for the most-to-date version of Unity recommended for HoloLens development (A Unity HoloLens-fejlesztéshez ajánlott legfrissebb verziójának telepítése).
- A Unity HoloLens Technical Preview ismert problémáit a [HoloLens Unity fórumain találhatja meg.](https://forum.unity3d.com/threads/known-issues.394627/)

[Vissza a listához](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows eszközportál nem működik megfelelően

- A Rögzítés funkció Live Preview Mixed Reality néhány másodpercnyi késést is mutathat.

- A Virtuális bemenet lapon a Virtuális kézmozdulatok szakasz Kézmozdulatok és Görgetés vezérlői nem működnek. A használatuknak nincs hatása. A virtuális beviteli oldalon található virtuális billentyűzet megfelelően működik.

- Miután engedélyezte a Fejlesztői módot a Beállításokban, a beállítás bekapcsolása néhány másodpercet is igénybe Eszközportál előtt.

[Vissza a listához](#list)

## <a name="emulator"></a>Emulátor
### <a name="the-hololens-emulator-isnt-working"></a>A HoloLens Emulator nem működik

A HoloLens Emulatorról a fejlesztői dokumentációnkban tájékozódhat.  További információ [a HoloLens emulátor hibaelhárításáról.](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)


- Nem minden alkalmazás kompatibilis Microsoft Store az emulátorral. A Young Conker és a Fragments például nem lejátszható az emulátoron.
- Az emulátorban nem használhatja a PC-s webkamerát.
- A szolgáltatás Live Preview Windows eszközportál nem működik az emulátorral. Továbbra is rögzíthet Mixed Reality és képeket.

[Vissza a listához](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>Nem találom vagy nem tudom használni a billentyűzetet a HoloLens 2 Emulator begépelésével

*Hamarosan érkezik*

[Vissza a listához](#list)

## <a name="voice-commands-arent-working"></a>A hangparancsok nem működnek

Ha Cortana nem válaszol a hangparancsra, győződjön meg arról, hogy Cortana be van kapcsolva. A Minden alkalmazás a **Cortana**  >  **menü** Jegyzetfüzet-beállítások menüpontját a  >    >   módosítások gombra. További információ a beszédről: Use your voice with HoloLens (A hang használata [a HoloLens-sel).](hololens-cortana.md)

A HoloLensben (1. generációs) a beépített beszédfelismerés nem konfigurálható. Mindig be van kapcsolva. A HoloLens 2-ben eldöntheti, hogy a beszédfelismerést és a Cortanát is bekapcsolja-e az eszköz beállítása során.

Ha a HoloLens 2 nem válaszol a hangjára, győződjön meg arról, hogy a Beszédfelismerés be van kapcsolva. A Start **Settings**  >  **Privacy** Speech  >    >  **oldalon** kapcsolja be a **Beszédfelismerést.**

[Vissza a listához](#list)

## <a name="hand-input-isnt-working"></a>A kézi bevitel nem működik

Ahhoz, hogy a HoloLens lássa a kézmozdulatokat, kézmozdulatkeretben kell tartania őket.  A Mixed Reality Kezdőlap visszajelzést küld, amely tudatja, mikor követik nyomon a kézzel kapcsolatos információkat.  A Visszajelzések eltérnek a HoloLens különböző verzióiról:
- A HoloLensben (1. generációs) a tekintet kurzora pontról gyűrűre változik
- A HoloLens 2-ben egy egérmutató jelenik meg, ha a kéz egy lappal közel van, és egy kézre mutató sugár jelenik meg, ha a beúszó oldal távol van

Számos modern alkalmazás a Kezdőlaphoz hasonló bemeneti mintákat Mixed Reality követ.  További információ a [holoLens (1. generációs)](hololens1-basic-usage.md#use-hololens-with-your-hands) és a [HoloLens 2 kézzel megadott bemenetének használatával kapcsolatban.](hololens2-basic-usage.md#the-hand-tracking-frame)

Ha a kézkövetést jól viseli, vegye figyelembe, hogy egyes típusú kézkövetési funkció nem működik.  Gyakori példa a fekete védőkesztyűk, amelyek általában befogadják a világítást, és nem a mélységi kamera érzékeli őket.  Ha a munkája során védőkesztyűt is magában foglal, javasoljuk, hogy egy világosabb színt( például kék vagy szürke) próbáljon ki.  Egy másik példa a nagy méretű, zacskós kézkesztyű, amely általában elfedi a kéz formáját. Javasoljuk, hogy a legjobb eredmény érdekében a lehető legjobban illeszkedő, formában illeszkedő védőkét használja.

Ha a vizor ujjlenyomattal vagy elmosott lenyomattal rendelkezik, a HoloLenshez készült mikrofiberos tisztítási tisztítással megtisztítja a vizort.

[Vissza a listához](#list)

## <a name="cant-connect-to-wi-fi"></a>Nem lehet csatlakozni a Wi-Fi

Ha nem tudja csatlakoztatni a HoloLenst egy Wi-Fi hálózathoz:

- Ellenőrizze, hogy Wi-Fi be van-e kapcsolva. Az ellenőrzéshez használja a Start kézmozdulatot, majd válassza a **Beállítások**  >  **Hálózati &amp; internet**  >  **Wi-Fi lehetőséget.** Ha Wi-Fi be van kapcsolva, próbálja meg kikapcsolni, majd újra bekapcsolni.
- Lépjen közelebb az útválasztóhoz vagy a hozzáférési ponthoz.
- Indítsa újra a Wi-Fi útválasztót, majd [indítsa újra a HoloLenst.](hololens-recovery.md) Próbáljon meg újra csatlakozni.
- Ha ezek egyike sem működik, ellenőrizze, hogy az útválasztó a legújabb belső vezérlőprogramot használja-e. Ezt az információt a gyártó webhelyén találja.

[Vissza a listához](#list)
## <a name="bluetooth-devices-arent-pairing"></a>A Bluetooth-eszközök nem párosodnak

Ha problémákat tapasztal egy [Bluetooth-eszköz párosítása esetén,](hololens-connect-devices.md)próbálkozzon a következő megoldásokkal:

- A Beállítások **eszközök**  >  **lapon** ellenőrizze, hogy a Bluetooth be van-e kapcsolva. Ha igen, kapcsolja ki és be újra.
- Győződjön meg arról, hogy a Bluetooth-eszköz teljesen fel van töltve vagy friss akkumulátorokkal rendelkezik.
- Ha továbbra sem tud csatlakozni, indítsa [újra a HoloLenst.](hololens-recovery.md)

[Vissza a listához](#list)

## <a name="usb-c-microphone-isnt-working"></a>Az USB-C mikrofon nem működik
Vegye figyelembe, hogy egyes USB-C-mikrofonok helytelenül, mikrofonként és *beszélőként is* jelentik magukat. Ez a mikrofonnal, és nem a HoloLens-sel van probléma. Ha ezen mikrofonok valamelyikét a HoloLensbe csatlakoztatja, előfordulhat, hogy a hang elveszett. Szerencsére van egy egyszerű javítás.  

A **Settings** System Sound  ->  **(Beállítások rendszerhangja)** lapon explicit módon állítsa be a beépített beszélők  ->   **(Analog Feature Audio Driver)** alapértelmezett **eszközként való beállítását.** A HoloLensnek akkor is meg kell emlékeznie erre a beállításra, ha a mikrofont eltávolítják, majd később újracsatlakoztatják.

![USB-C mikrofonok hibaelhárítása](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>A Beállítások között elérhetőként felsorolt eszközök nem működnek

A HoloLens (1. generációs) nem támogatja a Bluetooth-hangprofilokat. Előfordulhat, hogy a Bluetooth-hangeszközök, például a beszélők és a headsetek elérhetőként jelennek meg a HoloLens beállításaiban, de nem támogatottak.

A HoloLens 2 a Bluetooth A2DP hangprofilt támogatja a lejátszó lejátszásához. A HoloLens 2 nem támogatja az ingyenes Bluetooth-kéz profilt, amely lehetővé teszi a Bluetooth-periféria mikrofonnal való rögzítését.

Ha nem tudja használni a Bluetooth-eszközt, ellenőrizze, hogy támogatott eszköz-e. A támogatott eszközök a következők:

- Angol nyelvű QWERTY Bluetooth-billentyűzetek (ezeket bárhol használhatja, ahol a holografikus billentyűzetet használja).
- Bluetooth-egér.
- A [HoloLens-gombra.](hololens1-clicker.md)

A HoloLens-sel más Bluetooth HID- és EGYRED-eszközöket is párosíthat. Előfordulhat azonban, hogy telepítenie kell a megfelelő társalkalmazásokat a Microsoft Store az eszközök ténylegesen való használatához.

[Vissza a listához](#list)
