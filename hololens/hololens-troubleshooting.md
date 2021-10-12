---
title: HoloLens Eszköz hibaelhárítása
description: Maradjon naprakész az eszközök problémáinak és hibaelhárítási HoloLens leggyakoribb megoldásaival kapcsolatban.
author: evmill
ms.author: v-evmill
ms.date: 10/7/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problémák, hiba, hibaelhárítás, javítás, súgó, támogatás, HoloLens, emulátor
ms.openlocfilehash: ceb6f2670b15f46d17a0cb36f6602ae3d4e3ec1d
ms.sourcegitcommit: 8a3f925d2bda13c095b35f14d80afdd876aa859c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/12/2021
ms.locfileid: "129800538"
---
# <a name="device-troubleshooting"></a>Eszköz hibaelhárítása

Ez a cikk több gyakori probléma megoldását HoloLens ismerteti.

>[!IMPORTANT]
> A hibaelhárítási eljárás elkezdése előtt győződjön meg arról, hogy az eszköz **20–40%-os** akkumulátor-kapacitással rendelkezik, ha lehetséges. A [tápkapcsoló alatt](hololens2-setup.md#lights-that-indicate-the-battery-level) található akkumulátorjelző világítással gyorsan ellenőrizheti az akkumulátor kapacitását anélkül, hogy bejelentkezik az eszközre.

<a id="list"></a>

**Ismert problémák**
- [Minden alkalommal, amikor az energia 18%-ra kapcsol, az eszköz hirtelen automatikusan leáll](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive Az UWP-alkalmazás nem működik az Azure AD-felhasználók számára](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [A Remote Assist videó 20 perc után lefagy](#remote-assist-video-freezes-after-20-minutes)
- [Az automatikus bejelentkezés bejelentkezést kér](#auto-login-asks-for-log-in)
- [Microsoft Edge nem indul el](#microsoft-edge-fails-to-launch)
- [A billentyűzet nem vált át speciális karakterekre](#keyboard-doesnt-switch-to-special-characters)
- [A zárolt fájlok letöltésekor nem jelenik meg hiba](#downloading-locked-files-doesnt-error)
- [Eszközportál feltöltés/letöltés időkorrekta](#device-portal-file-uploaddownload-times-out)
- [Kék képernyő az Insider előzetes verzióból való eltolás után egy Insider buildtel flashdolt eszközön](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive nem tölt fel automatikusan képeket](#onedrive-doesnt-automatically-upload-pictures)

**Általános**
- [HoloLens nem válaszol vagy nem indul el](#hololens-is-unresponsive-or-wont-start)
- ["Kevés lemezterület" hiba](#low-disk-space-error)
- [Nem sikerül a beeső hiba](#calibration-fails)
- [Nem tudok bejelentkezni, mert a HoloLens korábban valaki más számára lett beállítva](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [A Unity nem működik](#unity-isnt-working)
- [Windows Eszközportál nem működik megfelelően](#windows-device-portal-isnt-working-correctly)
- [A HoloLens Emulator nem működik](#the-hololens-emulator-isnt-working)

**Bevitel**
- [A hangparancsok nem működnek](#voice-commands-arent-working)
- [A kézi bevitel nem működik](#hand-input-isnt-working)

**Kapcsolódás**
- [Nem lehet csatlakozni a Wi-Fi-hez](#cant-connect-to-wi-fi)

**Külső eszközök** 
- [Bluetooth eszközök nem párosítása](#bluetooth-devices-arent-pairing)
- [Az USB-C mikrofon nem működik](#usb-c-microphone-isnt-working)
- [A nem működnek a Gépház listában szereplő eszközök](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Minden alkalommal, amikor az energia 18%-ra kapcsol, az eszköz hirtelen automatikusan leáll

Ismert probléma, hogy amikor az eszköz eléri a 18%-os akkumulátort, az váratlanul leáll. Ez szoftveres, és nem hardverrel vagy akkumulátorral kapcsolatos probléma, ezért ne cseréljen eszközöket erre a problémára. Ha nem biztos abban, hogy a probléma megfelel-e a hibának, kérjük,:

1. Győződjön meg arról, hogy a választható diagnosztika engedélyezve van az eszközön(k)
1. Reprodukálja a problémát
1. Probléma [Visszajelzési központ](hololens-feedback.md) elküldése
1. A visszajelzési probléma URL-címének megosztása
1. [Kapcsolatfelvétel az ügyfélszolgálattal](https://aka.ms/hololenssupport)

[Vissza a listához](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive Az UWP-alkalmazás nem működik az Azure AD-felhasználók számára

Ha az Azure AD OneDrive fiókkal használja a vállalati OneDrive, akkor előfordulhat, hogy hibába ütközött, amikor bejelentkezett a beérkezett OneDrive alkalmazásba. Ha nem tud bejelentkezni az alkalmazásba OneDrive nincs hatással a Kamera alkalmazás által rögzített képek és videók automatikus feltöltésére. A fájlok továbbra is menthetők és elérhetők a felhőalapú OneDrive Vállalati verzió tárolóból. A OneDrive és HoloLens csapatok dolgoznak a probléma megoldásán.

### <a name="workarounds"></a>Kerülő megoldások

Előfeltétel: Az ügyfelek a Microsoft Edge és az eszköz operációs rendszerének frissítése egy Windows Holographic, 21H1 build vagy újabb verzióra van frissítve.

Ha ezt a problémát tapasztalja, próbálkozzon a következők valamelyikével:

- A felhasználók közvetlenül hozzáférhetnek OneDrive Vállalati verzióhoz a Microsoft Edge, és a böngészőjükből használhatja a webhely fájljaikat.
- A felhasználók úgy telepítheti a OneDrive PWA alkalmazást, HoloLens letöltik a Microsoft Edge. Így a felhasználók ismét megtekinthetik és kezelhetik az eszközön lévő fájlokat. Olvassa el és kövesse ezeket az utasításokat a OneDrive PWA [alkalmazás telepítéséhez a HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Vissza a listához](#list)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>A Remote Assist videó 20 perc után lefagy

> [!NOTE]
> A Remote Assist egy újabb verziója már rendelkezik javítással a problémára. A probléma elkerülése érdekében frissítse a [Remote Assistet](holographic-store-apps.md#update-apps) a legújabb verzióra.

> [!NOTE]
> Az ismert probléma súlyossága miatt ideiglenesen szüneteltettünk egy Windows Holographic 21H1-es verziójának elérhetőségét. A 21H1 build ismét elérhető, így az eszközök ismét frissíthetők a legújabb 21H1 buildre.

Az Windows [Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójának legújabb kiadásában a Remote Assist egyes felhasználói a hívások során több mint 20 percnyi videófagyást tapasztaltak. Ez egy **ismert probléma.**

### <a name="workarounds"></a>Kerülő megoldások

Ha nem tudja újabb buildre frissíteni a Remote Assistet, próbálkozzon a következővel.

#### <a name="restart-in-between-calls"></a>Újraindítás hívások között

Ha a hívások hossza 20 percnél hosszabb, és ezt a problémát tapasztalja, próbálja meg újraindítani az eszközt. Ha újraindítja az eszközt a Remote Assist-hívások között, az frissíti az eszközt, és jó állapotba kerül.

Ha gyorsan újraindít egy eszközt a [Holographic Windows 21H1-es verziójában,](hololens-release-notes.md#windows-holographic-version-21h1) nyissa meg a Start menüt, válassza a felhasználó ikont, majd válassza az **Újraindítás lehetőséget.**

[Vissza a listához](#list)

## <a name="auto-login-asks-for-log-in"></a>Az automatikus bejelentkezés bejelentkezést kér

A HoloLens 2-es eszközök konfigurálhatóak úgy, hogy automatikusan bejelentkeznek a **Gépház**  ->  **Accounts**  ->  **Sign-in Options** ->  és a Required (Kötelező) beállításnál a **Never**(Soha) értékre. Előfordulhat, hogy egyes felhasználóknak újra be kell jelentkezniük az eszközre egy jelentős mértékben nagy frissítéssel, például funkciófrissítéssel való frissítéskor. Ez egy **ismert probléma.**

Példa arra, hogy mikor fordulhat elő ez:

- Eszköz frissítése Windows Holographic 2004-es verziójáról (Build 19041.xxxx) Windows Holographic, 21H1-es verzióra (Build 20346.xxxx)
- Egy eszköz frissítése ugyanannak a fő buildnek a jelentős frissítéséhez, például a Windows Holographic 2004-es verziójának és a Windows Holographic 20H2-es verziójának frissítéséhez
- Eszköz frissítése gyári rendszerképről a legújabb rendszerképre

Ez nem fordulhat elő a következő időszakban:

- Havi karbantartási frissítést kapó eszközök

Módszerek használata:

- Bejelentkezési módszerek, például PIN-kód, jelszó, írisz, webes hitelesítés vagy FIDO2-kulcsok.
- Ha az eszköz PIN-kódját nem lehet megöröklni, és más hitelesítési módszerek nem érhetők el, akkor a felhasználó használhat manuális [perjeles módot.](hololens-recovery.md#manual-procedure)

[Vissza a listához](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge nem indul el

> [!NOTE]
> Ezt a problémát eredetileg a csomag szállítási verziójával hozták Microsoft Edge szem előtt tartva. Ez a probléma megoldható az új [Microsoft Edge.](hololens-new-edge.md) Ha nem, kérjük, visszajelzést írjon.

Néhány ügyfél olyan problémát jelentett, Microsoft Edge nem indul el. Ezeknél az ügyfeleknél a probléma újraindítással továbbra is fennáll, és nem oldódik meg a Windows vagy alkalmazásfrissítésekkel. Ha ezt a problémát tapasztalja, és megerősítette, hogy az [Windows](hololens-updates.md#manually-check-for-updates)naprakész, jelentsen be egy hibát a Visszajelzési központ-alkalmazásból [a](hololens-feedback.md) következő kategóriával és alkategóriával: Install and Update > Downloading, installing, and configuring Windows Update (Az Windows Update telepítése és frissítése).

Nincsenek ismert megkerülő megoldások, mivel eddig nem sikerült megoldani a problémát. Hiba bejelentése a Visszajelzési központ segít a vizsgálatban! Ez egy **ismert probléma.**

[Vissza a listához](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>A billentyűzet nem vált át speciális karakterekre

Az OOBE során probléma lép fel, amikor a felhasználó kiválasztott egy munkahelyi vagy iskolai fiókot, és megadta a jelszavát, és a billentyűzeten lévő speciális karakterekre próbál átváltani az &123 gombra koppintva, nem változik különleges karakterekre. Ez egy **ismert probléma.**

A következőt kell körül kell dolgozni:

- Zárja be a billentyűzetet, és nyissa meg újra a szövegmezőre koppintva.
- Helytelenül adja meg a jelszót. Amikor a billentyűzetet a következő alkalommal újraindítják, az a várt módon fog működni.
- Webes hitelesítés, zárja be a billentyűzetet, és válassza **a Bejelentkezés másik eszközről lehetőséget.**
- Ha csak számokat ad meg, a felhasználó megnyomhat és lenyomva tarthat bizonyos kulcsokat egy kibontott menü megnyitásához.
- USB-billentyűzet használata.

Ez nincs hatással a következőre:

- Azok a felhasználók, akik személyes fiókot választanának.

[Vissza a listához](#list)

## <a name="downloading-locked-files-doesnt-error"></a>A zárolt fájlok letöltése nem hibás

> [!NOTE]
> Ez egy ismert **hiba,** amely a [Holographic Windows 21H1 - 2021. júliusi frissítésében javítva lett.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)

A Holographic Windows korábbi buildjeiben zárolt fájl letöltésekor az eredmény egy HTTP-hibalap lenne. A Windows Holographic 21H1-es verziójának frissítésében a zárolt fájl letöltésének a kipróbálása azt jelenti, hogy semmi sem látható– a fájl nem tölt le, és nem jelenik meg hiba.

[Vissza a listához](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Eszközportál feltöltése/letöltése időkorrekta
> [!NOTE]
> Ez egy ismert **hiba,** amely a [Holographic Windows 21H1 - 2021. júliusi frissítésében javítva lett.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update) Ha az áthidaló megoldás részeként korábban letiltotta az SSL-kapcsolatot, erősen ajánlott újra engedélyezni.

Egyes ügyfelek azt találták, hogy amikor fájlokat próbálnak feltölteni vagy letölteni, a művelet lefagyhat, majd időkorrekciót vagy soha nem fejeződik be. Ez elkülönül a "fájl[zárolt"](#downloading-locked-files-doesnt-error) ismert problémától – ez a Windows Holographic 2004-es, 20H2-es és 21H1-es piaci buildeket érinti. A problémát az okozza, hogy Eszközportál bizonyos kérések kezelése során hiba történt, és a https használata esetén a legnagyobb konzisztens találat, amely az alapértelmezett beállítás.

### <a name="workaround"></a>Áthidaló megoldás

Ez az áthidaló megoldás, amely ugyanúgy vonatkozik a Wi-Fi az UsbNcm-re, a "kötelező" beállítás letiltása az "SSL-kapcsolat" alatt. Lépjen a következő oldalra: **Eszközportál, System**( Rendszer) és válassza a **Preferences (Beállítások)** lapot. Az **Eszközbiztonság szakaszban** keresse meg az **SSL-kapcsolatot,** és törölje a jelölését a **Kötelező letiltásához.**

A felhasználónak ekkor az http:// kell lennie, https:// (IP-cím) és olyan funkciók, mint a fájlok feltöltése és letöltése működni fog.

[Vissza a listához](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Kék képernyő, miután az Insider előzetes verzióból való igénylést egy Insider buildeléses flash() módban megjelenő eszközön

Ez a probléma olyan felhasználókra van hatással, akik egy Insider előzetes verziójú builden voltak, új belső előzetes verziójú buildelték újra az HoloLens 2-es verziójukat, majd nem regisztrálták őket az Insider programból. Ez egy **ismert probléma.**

Ez nincs hatással a következőre:

- Az Insiderben nem regisztrált Windows
- Bennfentesek:
    - Ha egy eszköz az Insider buildek óta regisztrálva lett, az 18362.x verziójú volt
    - Ha egy Insider 19041.x buildet írt alá, és regisztrálva kell maradnia az Insider programban

Időző:

- A probléma elkerülése
    - Flash egy nem belső build. A rendszeres havi frissítések egyike.
    - Maradjon az Insider előzetes kiadásában
- Az eszköz perjelének átfedő perjele

    1. Helyezze [a HoloLens 2-](hololens-recovery.md) et flash (flash) módba manuálisan úgy, hogy teljesen lekapcsolód, miközben nem csatlakozik. Ezután a Kötet lenyomva tartási gombra koppintva koppintson a Bekapcsoló gombra.

    1. Csatlakozás nyissa meg a számítógépet, és nyissa meg az Advanced Recovery Companion gombra.

    1. A 2. HoloLens az alapértelmezett buildhez.

[Vissza a listához](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive nem tölt fel automatikusan képeket

A OneDrive alkalmazás HoloLens támogatja a munkahelyi vagy iskolai fiókok automatikus kamerafeltöltését. Ez egy **ismert probléma.**

Workarounds:

- Ha a vállalkozása számára is elérhető, a fogyasztói Microsoft-fiókok támogatják az automatikus kamerafeltöltést. A munkahelyi vagy iskolai fiók Microsoft-fiók is bejelentkezhet a fiókba (a OneDrive alkalmazás támogatja a kettős bejelentkezést). A profil Microsoft-fiók a OneDrive engedélyezheti az automatikus, háttérkamerás kameratekercs-feltöltést.

- Ha nem tudja biztonságosan használni a Microsoft-fiók a fényképek automatikus feltöltéséhez, manuálisan feltölthet fényképeket a munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásból. Ennek érdekében győződjön meg arról, hogy bejelentkezett a munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásban. Kattintson a **+** gombra, majd válassza a **Feltöltés lehetőséget.** Keresse meg a feltölteni kívánt fényképeket vagy videókat a **Pictures (Képek) és a Camera Roll (>) között.** Válassza ki a feltölteni kívánt fényképeket vagy videókat, majd kattintson a **Megnyitás gombra.**

[Vissza a listához](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens nem válaszol vagy nem indul el

Ha a HoloLens nem indul el:

- Ha a bekapcsológomb melletti LED-ek nem világadnak meg, vagy csak egy LED villog rövid időre, előfordulhat, hogy fel kell töltenie a [HoloLens.](hololens2-charging.md#charging-the-device)
- Ha a LED-ek bekapcsolódnak, amikor megnyomja a bekapcsológombot, de nem lát semmit a kijelzőkön, állítsa alaphelyzetbe [az eszközt.](hololens-recovery.md#hard-reset-procedure)

Ha a HoloLens lefagy vagy nem válaszol:

- Kapcsolja ki a HoloLens a bekapcsológombbal, amíg mind az öt LED ki nem kapcsolja magát, vagy 15 másodpercig, ha a LED-ek nem válaszolnak. A hálózati HoloLens nyomja meg újra a bekapcsológombot.

Ha ezek a lépések nem működnek, megpróbálhatja helyreállítani [HoloLens 2-es](hololens-recovery.md) vagy HoloLens [(1. generációs) eszközt.](hololens1-recovery.md)

[Vissza a listához](#list)

## <a name="low-disk-space-error"></a>"Kevés lemezterület" hiba

Az alábbiak közül egyet vagy többet is el kell szabadítanunk egy vagy több tárolóhelyen:

- Töröljön néhány nem használt szóközt. A **Gépház**  >    >  **gombra,** válasszon ki egy olyan helyet, amelyre már nincs szüksége, majd válassza az Eltávolítás **lehetőséget.**
- Távolítsa el a elhelyezett hologramokat.
- Töröljön néhány képet és videót a Photos alkalmazásból.
- Távolítsa el az alkalmazásokat a HoloLens. A **Minden alkalmazás** koppintson és tartsa lenyomva az eltávolítani kívánt alkalmazást, majd válassza az **Eltávolítás lehetőséget.**

[Vissza a listához](#list)

## <a name="calibration-fails"></a>A meghiúsulás

A legtöbb ember számára működnie kell, de vannak olyan esetek, amikor a besziratás meghiúsul.
  
Néhány lehetséges ok a meghibásodásra:

- Elvonja a figyelmet, és nem követi a célokat
- Nem megfelelően el van állítva a trágár vagy karcolt eszköz vizora vagy az eszköz vizora
- Trágár vagy karcolt szemüveg
- Bizonyos típusú kapcsolattartási objektívek és szemüveg (színes kapcsolattartó objektívek, némi toric contact lenses, IR-blokkoló szemüveg, néhány magas szemüveg, napszemüveg vagy hasonló)
- Jobban kiejtve és perjeles mellékek
- Haj vagy vastag szemüveg, ha nem látják a tekintetét az eszközön
- Bizonyos szemfiziológia, szemkörülmények vagy szemműveletek, például keskeny szem, hosszú szempillák, amblyegymáshoz hasonlók, nystagmus, a LASIK vagy más szemműveletek néhány esete

Sikertelen kísérlet esetén próbálkozzon a következővel:

- Az eszköz vizorának tisztítása
- Szemüveg tisztítása
- Az eszköz vizorának lehető legnagyobb közelében való eltolás
- Objektumok (például haj) mozgatása a vizorban
- Világítás bekapcsolása a helyiségben, vagy a közvetlen világításból való eltálás

Ha minden útmutatót követte, és a tiltása továbbra sem sikerül, a figyelmeztetést a következő Gépház. Visszajelzést is küldhet a [Visszajelzési központ.](hololens-feedback.md)

A képszínekkel vagy a fényerejével kapcsolatos [hibaelhárítással kapcsolatos információkat is itt láthatja.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

A 2. HoloLens IPD beállítása nem alkalmazható, mivel a szem pozícióit a rendszer számítja ki. 

[Vissza a listához](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Nem tudok bejelentkezni, mert a HoloLens korábban valaki más számára lett beállítva

Az eszközt [flash **(Flashing)**](hololens-recovery.md#clean-reflash-the-device) módba használhatja, és az Advanced Recovery Companion használatával helyreállíthatja az eszközt.

[Vissza a listához](#list)


## <a name="unity-isnt-working"></a>A Unity nem működik

- Lásd: [Install the tools](/windows/mixed-reality/install-the-tools) for the most-to-date version of Unity recommended for HoloLens development (A Unity legújabb verziójának telepítése a HoloLens érdekében.
- A Unityvel kapcsolatos ismert HoloLens Technical Preview-val kapcsolatban a következő Unity-fórumokon [HoloLens dokumentáljuk:](https://forum.unity3d.com/threads/known-issues.394627/).

[Vissza a listához](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Eszközportál nem működik megfelelően

- A rögzítési funkció Live Preview Mixed Reality néhány másodpercnyi késést is mutathat.

- A Virtuális bemenet lapon a Virtuális kézmozdulatok szakasz Kézmozdulatok és Görgetés vezérlői nem működnek. A használatuknak nincs hatása. A virtuális beviteli oldalon található virtuális billentyűzet megfelelően működik.

- A fejlesztői mód Gépház után néhány másodpercet is igénybe vehet, amíg a kapcsoló bekapcsolja a Eszközportál beállítást.

[Vissza a listához](#list)

## <a name="the-hololens-emulator-isnt-working"></a>A HoloLens Emulator nem működik

A HoloLens emulátorról a fejlesztői dokumentációnkban tájékozódhat.  További információ [a HoloLens emulátor hibaelhárításáról.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Nem minden alkalmazás kompatibilis Microsoft Store az emulátorsal. Young Conker és a Fragments például nem lejátszható az emulátoron.
- A számítógép webkameráját nem használhatja a Emulator.
- A szolgáltatás Live Preview Windows Eszközportál nem működik az emulátorral. Továbbra is rögzíthet Mixed Reality videókat és képeket.

[Vissza a listához](#list)

## <a name="voice-commands-arent-working"></a>A hangparancsok nem működnek

Ha Cortana nem válaszol a hangparancsra, győződjön meg arról, hogy Cortana be van kapcsolva. A Minden alkalmazás a Módosítások Cortana menü jegyzetfüzet  >    >    >  **Gépház** lehetőséget. További információ a beszédről: [Use your voice with HoloLens](hololens-cortana.md).

A HoloLens (1. generációs) beépített beszédfelismerés nem konfigurálható. Mindig be van kapcsolva. A 2. HoloLens megadhatja, hogy bekapcsolja-e a beszédfelismerést és a Cortana az eszköz beállítása során.

Ha a HoloLens 2. nem válaszol a hangjára, győződjön meg arról, hogy a Beszédfelismerés be van kapcsolva. A **Start Gépház** Privacy Speech  >    >  **(Beszédfelismerési beszéd)**  >  **menüben** kapcsolja be a **Beszédfelismerést.**

[Vissza a listához](#list)

## <a name="hand-input-isnt-working"></a>A kézi bevitel nem működik

Ahhoz, HoloLens a kézmozdulatok láthatóak, kézmozdulatok keretében kell tartania őket.  A Mixed Reality Kezdőlap visszajelzést küld, amely tudatja, mikor követik nyomon a kézzel.  A visszajelzések eltérőek a HoloLens:

- A HoloLens (1. generációs) esetében a tekintet kurzora pontról gyűrűre változik
- A 2. HoloLens kurzor akkor jelenik meg, ha a kéz egy lappal közelebb van, és egy kéz sugár jelenik meg, ha a belók távolodnak

Számos modern alkalmazás a Kezdőlaphoz hasonló bemeneti mintákat Mixed Reality követ.  További információ a kézi bevitelnek a HoloLens [(1. generációs)](hololens1-basic-usage.md#use-hololens-with-your-hands) és [a 2. HoloLens való használatával kapcsolatban.](hololens2-basic-usage.md#the-hand-tracking-frame)

Vegye figyelembe, hogy a kézkövetés bizonyos típusú kézkövetési funkcióval nem működik.  Gyakori példa a fekete védőkesztyűk, amelyek általában befogadják a világítást, és a mélységi kamera nem tudja felvenni őket.  Ha a munkája során védőkesztyűt is kell tenni, javasoljuk, hogy egy világosabb színt, például kéket vagy szürkét próbáljon ki.  Egy másik példa a nagy méretű, nagy méretű, kézbegyűség. Ez általában elfedi a kéz alakját. Javasoljuk, hogy a legjobb eredmény érdekében a lehető legjobban illeszkedő, jól illeszkedő védőkét használja.

Ha a vizor ujjlenyomattal vagy elmosott lenyomattal rendelkezik, használja a vizorhoz érkezett mikrofiberos tisztítási HoloLens a vizorok megtisztítására.

[Vissza a listához](#list)

## <a name="cant-connect-to-wi-fi"></a>Nem lehet csatlakozni a Wi-Fi

Ha nem tud csatlakozni a HoloLens egy Wi-Fi hálózathoz:

- Ellenőrizze, hogy Wi-Fi be van-e kapcsolva. Az ellenőrzéshez használja a Start kézmozdulatot, majd válassza **Gépház**  >  **Hálózati &amp; internet**  >  **Wi-Fi lehetőséget.** Ha Wi-Fi be van kapcsolva, próbálja meg kikapcsolni, majd újra bekapcsolni.
- Lépjen közelebb az útválasztóhoz vagy a hozzáférési ponthoz.
- Indítsa újra a Wi-Fi útválasztót, majd [indítsa újra HoloLens.](hololens-recovery.md) Próbáljon meg újból csatlakozni.
- Ha ezek közül egyik sem működik, ellenőrizze, hogy az útválasztó a legújabb belső vezérlőprogramot használja-e. Ezt az információt a gyártó webhelyén találja.

[Vissza a listához](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth eszközök nem párosítása

Ha problémába merült fel [a Bluetooth való párosítása,](hololens-connect-devices.md)próbálkozzon a következő megoldásokkal:

- Az Eszközök **Gépház,** és győződjön meg arról, hogy Bluetooth  >  be van kapcsolva. Ha igen, kapcsolja ki és be újra.
- Győződjön meg arról, Bluetooth az eszköz teljesen fel van töltve, vagy friss akkumulátorokkal rendelkezik.
- Ha továbbra sem tud csatlakozni, indítsa [újra a HoloLens.](hololens-recovery.md)

[Vissza a listához](#list)

## <a name="usb-c-microphone-isnt-working"></a>Az USB-C mikrofon nem működik

Vegye figyelembe, hogy egyes USB-C-mikrofonok helytelenül jelentik magukat mikrofonként és *beszélőként* is. Ez a mikrofonnal, és nem a mikrofonnal HoloLens. Ha ezen mikrofonok valamelyikét csatlakoztatja HoloLens, a hang elveszhet. Szerencsére van egy egyszerű javítás.  

A **Gépház** a System Soundban explicit módon állítsa be a beépített beszélők  ->    ->   **(Analog Feature Audio Driver)** alapértelmezett eszközként való **beállítását.** HoloLens a beállítást akkor is meg kell jegyezni, ha a mikrofont eltávolítják, majd később újracsatlakoztatják.

![USB-C-mikrofonok hibaelhárítása.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>A Gépház felsorolt eszközök nem működnek

HoloLens (1. generációs) nem támogatja a Bluetooth hangprofilokat. Bluetooth hangeszközök, például a beszélők és a headsetek elérhetőként jelennek meg a HoloLens beállításaiban, de ezek nem támogatottak.

HoloLens 2. Bluetooth A2DP hangprofilt támogatja a lejátszáshoz. A Bluetooth-profil, amely lehetővé teszi a mikrofon rögzítését egy Bluetooth periféria nem támogatott a 2. HoloLens esetén.

Ha problémába fog kerülni egy Bluetooth eszköz használata, ellenőrizze, hogy támogatott eszköz-e. A támogatott eszközök a következők:

- Az angol nyelvű QWERTY Bluetooth billentyűzeteket (ezeket bárhol használhatja, ahol a holografikus billentyűzetet használja).
- Bluetooth mice.
- A [HoloLens gombra.](hololens1-clicker.md)

Más HID és BLUETOOTH eszköz is párosíthatja a HoloLens. Előfordulhat azonban, hogy a megfelelő társalkalmazásokat a Microsoft Store kell telepítenie az eszközök ténylegesen való használatához.

[Vissza a listához](#list)
