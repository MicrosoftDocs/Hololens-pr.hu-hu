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
ms.openlocfilehash: afbbc1ab0e018f668381137849738ec7d274fe37
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924383"
---
# <a name="device-troubleshooting"></a>Eszköz hibaelhárítása

Ez a cikk több gyakori probléma megoldását HoloLens ismerteti.

>[!IMPORTANT]
> A hibaelhárítási eljárás elkezdése előtt győződjön meg arról, hogy az eszköz **20–40%-os** akkumulátor-kapacitással rendelkezik, ha lehetséges. A [tápkapcsoló alatt](hololens2-setup.md#lights-that-indicate-the-battery-level) található akkumulátorjelző világítással gyorsan ellenőrizheti az akkumulátor kapacitását anélkül, hogy bejelentkezik az eszközre.

<a id="list"></a>

**Ismert problémák**
- [Minden alkalommal, amikor az energia 18%-ra kapcsol, az eszköz hirtelen automatikusan leáll](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive Az UWP-alkalmazás nem működik az Azure AD-felhasználók számára](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Miért látom a 0x80180014 Autopilot alatt?](#why-do-i-see-0x80180014-during-autopilot)
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
- [A Gépház felsorolt eszközök nem működnek](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Minden alkalommal, amikor az energia 18%-ra kapcsol, az eszköz hirtelen automatikusan leáll

Ismert probléma, hogy amikor az eszköz eléri a 18%-os akkumulátort, az váratlanul leáll. Ez szoftveres, és nem hardverrel vagy akkumulátorral kapcsolatos probléma, ezért ne cseréljen eszközöket erre a problémára. Ha nem biztos abban, hogy a probléma megfelel-e a hibának, kérjük,:

1. Győződjön meg arról, hogy a választható diagnosztika engedélyezve van az eszközön(k)
1. Reprodukálja a problémát
1. Probléma [Visszajelzési központ](hololens-feedback.md) elküldése
1. A visszajelzési probléma URL-címének megosztása
1. [Kapcsolatfelvétel az ügyfélszolgálattal](https://aka.ms/hololenssupport)

[Vissza a listához](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive Az UWP-alkalmazás nem működik az Azure AD-felhasználók számára

Ha a vállalati OneDrive használja az Azure AD-fiókját, előfordulhat, hogy hibába ütközött, amikor bejelentkezett OneDrive alkalmazásba. Ha nem tud bejelentkezni az alkalmazásba OneDrive nincs hatással a Kamera alkalmazás által rögzített képek és videók automatikus feltöltésére. A fájlok továbbra is menthetők és elérhetők a felhőalapú OneDrive Vállalati verzió tárolóból. A OneDrive és HoloLens csapatok dolgoznak a probléma megoldásán.

### <a name="workarounds"></a>Kerülő megoldások

Előfeltétel: Az ügyfelek használhatnak Microsoft Edge és az eszköz operációs rendszerének frissítése egy Windows Holographic, 21H1 build vagy újabb verzióra van frissítve.

Ha ezt a problémát tapasztalja, próbálkozzon a következők valamelyikével:

- A felhasználók közvetlenül hozzáférhetnek OneDrive Vállalati verzióhoz a Microsoft Edge, és a böngészőjükből férhetnek hozzá a webhely fájljaikhoz.
- A felhasználók úgy telepítheti a OneDrive PWA alkalmazást, HoloLens letöltik a Microsoft Edge. Így a felhasználók ismét megtekinthetik és kezelhetik az eszközön lévő fájlokat. Olvassa el és kövesse ezeket az utasításokat a OneDrive PWA [alkalmazás telepítéséhez a HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Vissza a listához](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Miért látom a 0x80180014 Autopilot alatt?

Ez a hiba általában az eszköz alaphelyzetbe állítása és a folyamatok újrahasználata során merül fel, amikor egy HoloLens eszköz legalább egyszer végigment az Autopiloton. A probléma megoldásához törölje az eszközt a Microsoft Intune [majd](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) állítsa vissza az AutoPilot-folyamat befejezéséhez.

További információért tekintse meg az [AutoPilot oldalán található hibaelhárítási lépéseket.](hololens2-autopilot.md#why-do-i-see-0x80180014-during-autopilot)

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

A következőt kell körülveszenni:

- Zárja be a billentyűzetet, és nyissa meg újra a szövegmezőre koppintva.
- Helytelenül adja meg a jelszót. Ha a billentyűzetet legközelebb újraindítják, az a várt módon fog működni.
- Webes hitelesítés, zárja be a billentyűzetet, és válassza **a Bejelentkezés másik eszközről lehetőséget.**
- Ha csak számokat ad meg, a felhasználó megnyomhat és lenyomva tarthat bizonyos kulcsokat egy kibontott menü megnyitásához.
- USB-billentyűzet használata.

Ez nincs hatással a következőre:

- Azok a felhasználók, akik személyes fiókot választanának.

[Vissza a listához](#list)

## <a name="downloading-locked-files-doesnt-error"></a>A zárolt fájlok letöltése nem hibás

> [!NOTE]
> Ez egy ismert **probléma,** amely ki lett javítva [Windows Holographic 21H1 - 2021.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)júliusi frissítésében.

A Holographic Windows korábbi buildje során egy zárolt fájl letöltésekor az eredmény egy HTTP-hibalap lesz. A Windows Holographic 21H1-es verziójának frissítésében a zárolt fájl letöltésével semmi nem látható – a fájl nem tölt le és nem jelenik meg hiba.

[Vissza a listához](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Eszközportál feltöltés/letöltés időkorrekta
> [!NOTE]
> Ez egy ismert **probléma,** amely ki lett javítva [Windows Holographic 21H1 - 2021.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)júliusi frissítésében. Ha az áthidaló megoldás részeként korábban letiltotta az SSL-kapcsolatot, javasoljuk, hogy engedélyezze újra.

Egyes ügyfelek azt találták, hogy amikor fájlokat próbálnak feltölteni vagy letölteni, a művelet lefagyhat, majd időkorrekciót vagy soha nem fejeződik be. Ez elkülönül a "fájl[zárolt"](#downloading-locked-files-doesnt-error) ismert problémától – ez a Windows Holographic 2004-es, 20H2-es és 21H1-es piaci buildeket érinti. A problémát egy olyan hiba okozza, Eszközportál bizonyos kérések kezelése során, és https használata esetén a legnagyobb konzisztensen ad vissza találatot, amely az alapértelmezett beállítás.

### <a name="workaround"></a>Áthidaló megoldás

Ez az áthidaló megoldás, amely ugyanúgy vonatkozik a Wi-Fi és az UsbNcm protokollra, a "kötelező" beállítás letiltása az SSL-kapcsolat alatt. Navigáljon a Eszközportál, a System (Rendszer) **lapra,** és válassza a **Preferences (Beállítások)** lapot. Az **Eszközbiztonság szakaszban** keresse meg az **SSL-kapcsolatot,** és törölje a jelölését a Kötelező **letiltásához.**

A felhasználónak ekkor az http:// kell lennie, nem https:// (IP-cím), és az olyan funkciók, mint a fájlfeltöltés és a letöltés működni fognak.

[Vissza a listához](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Kék képernyő az Insider előzetes verzióból való eltolás után egy Insider buildtel flashdolt eszközön

Ez olyan problémát jelent, amely olyan felhasználókat érint, akik egy Insider előzetes verziójú builden voltak, új belső előzetes verziójú buildelték újra a HoloLens 2-es verziójukat, majd nem regisztrálták őket az Insider programból. Ez egy **ismert probléma.**

Ez nincs hatással a következőre:

- A Windows Insiderben nem regisztrált felhasználók
- Bennfentesek:
    - Ha az insider buildek óta regisztrált egy eszközt, az 18362.x verziójú volt
    - Ha egy Insider által aláírt 19041.x buildet flashltek, és regisztrálva kell maradnia az Insider programban

Körül kell dolgozni:

- A probléma elkerülése
    - Flash egy nem belső build. Az egyik rendszeres havi frissítés.
    - Maradjon az Insider előzetes kiadásában
- Az eszköz átfedő perjele

    1. Helyezze [a HoloLens 2- et flash (flash)](hololens-recovery.md) módba manuálisan úgy, hogy teljesen leáll, miközben nem csatlakozik. Ezután a Kötet lenyomva tartási gombra koppintva koppintson a Bekapcsoló gombra.

    1. Csatlakozás nyissa meg a számítógépet, és nyissa meg az Advanced Recovery Companiont.

    1. A 2. HoloLens az alapértelmezett buildre.

[Vissza a listához](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive nem tölt fel automatikusan képeket

A OneDrive alkalmazás nem HoloLens támogatja a munkahelyi vagy iskolai fiókok automatikus kamerafeltöltését. Ez egy **ismert probléma.**

Workarounds:

- Ha ez a vállalkozása számára is elérhető, a fogyasztói Microsoft-fiókok támogatják az automatikus kamerafeltöltést. Munkahelyi vagy iskolai fiókján kívül Microsoft-fiók is bejelentkezhet a munkahelyi vagy iskolai fiókjába (a OneDrive az alkalmazás támogatja a kettős bejelentkezést). A profil Microsoft-fiók a OneDrive engedélyezheti az automatikus, háttérkamerás kameratekercs-feltöltést.

- Ha nem tud biztonságosan használni egy fogyasztói Microsoft-fiók a fényképek automatikus feltöltéséhez, manuálisan feltölthet fényképeket a munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásból. Győződjön meg arról, hogy be van jelentkezve munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásban. Kattintson a **+** gombra, majd válassza a **Feltöltés lehetőséget.** Keresse meg a feltölteni kívánt fényképeket vagy videókat a **Pictures (Képek) és a Camera Roll (>) között.** Válassza ki a feltölteni kívánt fényképeket vagy videókat, majd kattintson a **Megnyitás gombra.**

[Vissza a listához](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens nem válaszol vagy nem indul el

Ha a HoloLens nem indul el:

- Ha a bekapcsológomb melletti LED-ek nem világadnak meg, vagy csak egy LED villog rövid időre, előfordulhat, hogy fel kell töltenie a [HoloLens.](hololens2-charging.md#charging-the-device)
- Ha a bekapcsológomb megnyomása után a LED-ek kigyűjnek, de nem lát semmit a kijelzőkön, állítsa alaphelyzetbe [az eszközt.](hololens-recovery.md#hard-reset-procedure)

Ha a HoloLens lefagy vagy nem válaszol:

- Kapcsolja ki a HoloLens a bekapcsológombbal, amíg mind az öt LED ki nem kapcsolja magát, vagy 15 másodpercig, ha a LED-ek nem válaszolnak. A hálózati HoloLens nyomja meg újra a bekapcsológombot.

Ha ezek a lépések nem működnek, megpróbálhatja helyreállítani [HoloLens 2-es](hololens-recovery.md) vagy HoloLens [(1. generációs) eszközt.](hololens1-recovery.md)

[Vissza a listához](#list)

## <a name="low-disk-space-error"></a>"Kevés lemezterület" hiba

Az alábbiak közül egy vagy több megoldással szabadíthat fel tárhelyet:

- Töröljön néhány nem használt szóközt. Válassza a **Gépház** lehetőséget, válasszon ki egy olyan területet, amelyre már nincs  >    >  szüksége, majd válassza az **Eltávolítás lehetőséget.**
- Távolítsa el a elhelyezett hologramokat.
- Töröljön néhány képet és videót a Photos alkalmazásból.
- Távolítsa el az alkalmazásokat a HoloLens. A **Minden alkalmazás** koppintson és tartsa lenyomva az eltávolítani kívánt alkalmazást, majd válassza az **Eltávolítás lehetőséget.**

[Vissza a listához](#list)

## <a name="calibration-fails"></a>A meghiúsulás

A legtöbb ember számára működnie kell, de vannak olyan esetek, amikor a hiba nem sikerül.
  
Néhány lehetséges ok a meghibásodásra:

- Elvonják a figyelmet, és nem követik a célokat
- Nem megfelelően el van állítva a trágár vagy karcolt eszköz- vagy eszköz-vizor
- Trágár vagy karcolt szemüveg
- Bizonyos típusú névjegy objektívek és szemüveg (színes kapcsolattartó objektívek, néhány toric contact lenses, IR-blokkoló szemüveg, néhány magas szemüveg, napszemüveg vagy hasonló)
- Pontosabban kiejtve és perjeles bővítmények
- Haj vagy vastag szemüveg, ha blokkolja az eszközt a szemének
- Bizonyos szemfizika, szemkörülmények vagy szemműveletek, például keskeny szem, hosszú perjel, amblyphy, nystagmus, a LASIK vagy más szemműveletek bizonyos esetekben

Sikertelen kísérlet esetén próbálkozzon a következővel:

- Az eszköz vizorának tisztítása
- Szemüveg tisztítása
- Az eszköz vizorának a lehető legnagyobb egymáshoz zárásával
- Objektumok (például haj) mozgatása a vizorban
- Világítás bekapcsolása a helyiségben, vagy a közvetlen világításból való eltálás

Ha követte az összes útmutatót, és a tiltás továbbra sem sikerül, a figyelmeztetést a következő Gépház. Visszajelzést is küldhet a [Visszajelzési központ.](hololens-feedback.md)

A képszínekkel vagy a fényerejével kapcsolatos [hibaelhárítással kapcsolatos információkat is itt láthatja.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Az IPD beállítása a 2. HoloLens nem alkalmazható, mivel a szem pozícióit a rendszer számítja ki. 

[Vissza a listához](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Nem tudok bejelentkezni, mert a HoloLens korábban valaki más számára lett beállítva

Az eszközt [flash **(Flashing)**](hololens-recovery.md#clean-reflash-the-device) módba használhatja, és az Advanced Recovery Companion használatával helyreállíthatja az eszközt.

[Vissza a listához](#list)


## <a name="unity-isnt-working"></a>A Unity nem működik

- Lásd: [Install the tools](/windows/mixed-reality/install-the-tools) for the most-to-date version of Unity recommended for HoloLens development (A Unity legújabb verziójának telepítése a HoloLens érdekében.
- A Unity és a Technical Preview HoloLens ismert problémáit az [HoloLens Unity fórumain találhatja.](https://forum.unity3d.com/threads/known-issues.394627/)

[Vissza a listához](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Eszközportál nem működik megfelelően

- A Rögzítés funkció Live Preview Mixed Reality néhány másodpercnyi késést is mutathat.

- A Virtuális bemenet lapon a Virtuális kézmozdulatok szakasz Kézmozdulatok és Görgetés vezérlői nem működnek. A használatuknak nincs hatása. A virtuális beviteli oldalon található virtuális billentyűzet megfelelően működik.

- Miután engedélyezte a fejlesztői módot Gépház módban, a kapcsoló bekapcsolása néhány másodpercet is igénybe Eszközportál előtt.

[Vissza a listához](#list)

## <a name="the-hololens-emulator-isnt-working"></a>A HoloLens Emulator nem működik

A HoloLens emulátorról a fejlesztői dokumentációnkban tájékozódhat.  További információ [a HoloLens emulátor hibaelhárításáról.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Nem minden alkalmazás kompatibilis Microsoft Store az emulátorral. A Young Conker és a Fragments például nem lejátszható az emulátoron.
- A számítógép webkameráját nem használhatja a Emulator.
- A szolgáltatás Live Preview Windows Eszközportál nem működik az emulátorral. Továbbra is rögzíthet Mixed Reality videókat és képeket.

[Vissza a listához](#list)

## <a name="voice-commands-arent-working"></a>A hangparancsok nem működnek

Ha Cortana nem válaszol a hangparancsra, győződjön meg arról, hogy Cortana be van kapcsolva. A Minden alkalmazás a Módosítások Cortana   >  **menü**  >    >  **jegyzetfüzet-Gépház** lehetőséget. További információ a beszédről: A hang használata a [HoloLens.](hololens-cortana.md)

A HoloLens (1. generációs) beépített beszédfelismerés nem konfigurálható. Mindig be van kapcsolva. A HoloLens 2-es Cortana megadhatja, hogy bekapcsolja-e a beszédfelismerést és a Cortana az eszköz beállítása során.

Ha a HoloLens 2 nem válaszol a hangjára, győződjön meg arról, hogy a Beszédfelismerés be van kapcsolva. A **Start Gépház** Privacy Speech  >    >  **(Beszédfelismerési szolgáltatás)**  >  **menüben** kapcsolja be a **Beszédfelismerést.**

[Vissza a listához](#list)

## <a name="hand-input-isnt-working"></a>A kézi bevitel nem működik

Ahhoz, hogy HoloLens a kézmozdulatokat, kézmozdulatok keretében kell tartania azokat.  A Mixed Reality Kezdőlap visszajelzést ad, amely tudatja, mikor követik nyomon a kézzel kapcsolatos információkat.  A visszajelzések eltérőek a következő HoloLens:

- A HoloLens (1. generációs) esetében a tekintet kurzora pontról gyűrűre változik
- A 2. HoloLens kurzor akkor jelenik meg, ha a kéz egy laphoz közel van, és egy kéz sugár jelenik meg, ha a belátsó oldal távol van

Számos modern alkalmazás a Kezdőlaphoz hasonló bemeneti mintákat Mixed Reality követ.  További információ a kézi bevitelről a [HoloLens (1. gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) és [a 2. HoloLens használatával](hololens2-basic-usage.md#the-hand-tracking-frame)kapcsolatban.

Vegye figyelembe, hogy a kézkövetés bizonyos típusú kézkövetéssel nem működik.  Gyakori példa a fekete védőkesztyűk, amelyek általában befogadják a világítást, és nem a mélységi kamera érzékeli őket.  Ha a munkája során védőkesztyűt is bevet, javasoljuk, hogy egy világosabb színt( például kék vagy szürke) próbáljon ki.  Egy másik példa a nagy méretű, zacskós kézkesztyű, amely általában elfedi a kéz formáját. Javasoljuk, hogy a legjobb eredmény érdekében a lehető legjobban illeszkedő, formában illeszkedő védőkét használja.

Ha a vizor ujjlenyomattal vagy elmosott lenyomattal rendelkezik, használja a vizorhoz készült mikrofiberos tisztítási HoloLens a vizorok tisztítására.

[Vissza a listához](#list)

## <a name="cant-connect-to-wi-fi"></a>Nem lehet csatlakozni a Wi-Fi

Ha nem tud csatlakozni a HoloLens egy Wi-Fi hálózathoz, az Wi-Fi próbálkozhat:

- Győződjön meg arról, Wi-Fi be van kapcsolva. Az ellenőrzéshez használja a Start (Indítás) kézmozdulatot, majd válassza Gépház  >  **Network &amp; Internet**  >  **Wi-Fi (Hálózati internet Wi-Fi) lehetőséget.** Ha Wi-Fi be van kapcsolva, próbálja meg kikapcsolni, majd újra bekapcsolni.
- Lépjen közelebb az útválasztóhoz vagy a hozzáférési ponthoz.
- Indítsa újra a Wi-Fi útválasztót, majd [indítsa újra a HoloLens.](hololens-recovery.md) Próbáljon meg újból csatlakozni.
- Ha ezek egyike sem működik, ellenőrizze, hogy az útválasztó a legújabb belső vezérlőprogramot használja-e. Ezt az információt a gyártó webhelyén találja.

[Vissza a listához](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth eszközök nem párosítása

Ha problémába merült fel [a Bluetooth párosítása,](hololens-connect-devices.md)próbálkozzon a következővel:

- Az Eszközök **Gépház,** és győződjön meg arról, Bluetooth be  >  van kapcsolva. Ha igen, kapcsolja ki és be újra.
- Ellenőrizze, hogy a Bluetooth teljesen fel van-e töltve vagy friss akkumulátorokkal rendelkezik-e.
- Ha továbbra sem tud csatlakozni, indítsa [újra a HoloLens.](hololens-recovery.md)

[Vissza a listához](#list)

## <a name="usb-c-microphone-isnt-working"></a>Az USB-C mikrofon nem működik

Vegye figyelembe, hogy egyes USB-C-mikrofonok helytelenül, mikrofonként és *beszélőként is* jelentik magukat. Ez a mikrofonnal, és nem a HoloLens. Ha ezen mikrofonok valamelyikét csatlakoztatja HoloLens, előfordulhat, hogy a hang elveszett. Szerencsére van egy egyszerű javítás.  

A **Gépház** a System Soundban explicit módon állítsa be a beépített beszélők  ->    ->   **(Analog Feature Audio Driver)** alapértelmezett eszközként való **beállítását.** HoloLens a beállítást akkor is meg kell jegyezni, ha a mikrofont eltávolítják, majd később újracsatlakoztatják.

![USB-C mikrofonok hibaelhárítása.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Nem működnek a Gépház-ban elérhetőként felsorolt eszközök

HoloLens (1. generációs) nem támogatja a Bluetooth hangprofilokat. Bluetooth hangeszközök, például a beszélők és a headsetek elérhetőként jelennek meg HoloLens beállításokban, de nem támogatottak.

HoloLens 2. Bluetooth támogatja a Bluetooth A2DP hangprofilt a audio lejátszáshoz. A Bluetooth-kéz nélküli profil, amely lehetővé teszi a mikrofon rögzítését egy Bluetooth periféria nem támogatott a 2. HoloLens támogatja.

Ha problémája van egy Bluetooth eszköz használatával, győződjön meg arról, hogy az támogatott eszköz. A támogatott eszközök a következők:

- Az angol nyelvű QWERTY Bluetooth billentyűzeteket (ezeket bárhol használhatja, ahol a holografikus billentyűzetet használja).
- Bluetooth mice.
- A [HoloLens gombra.](hololens1-clicker.md)

Más HID és BLUETOOTH eszközöket is párosíthat a HoloLens. Előfordulhat azonban, hogy a megfelelő társalkalmazásokat a Microsoft Store kell telepítenie az eszközök ténylegesen való használatához.

[Vissza a listához](#list)
