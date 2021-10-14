---
title: HoloLens Eszköz hibaelhárítása
description: Naprakész maradhat az eszközök problémáinak és hibaelhárítási HoloLens leggyakoribb megoldásaival kapcsolatban.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problémák, hiba, hibaelhárítás, javítás, súgó, támogatás, HoloLens, emulátor
ms.openlocfilehash: 247cf9d34da723e587f6796178ad9a917b93ac08
ms.sourcegitcommit: 39accbc8e35728969c500da052035af4fd317a65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2021
ms.locfileid: "129964564"
---
# <a name="device-troubleshooting"></a>Eszköz hibaelhárítása

Ez a cikk több gyakori probléma megoldását HoloLens ismerteti.

>[!IMPORTANT]
> A hibaelhárítási eljárás elkezdése előtt győződjön meg arról, hogy az eszköz **20–40** százalék akkumulátor-kapacitással rendelkezik, ha lehetséges. A [tápkapcsoló alatt](hololens2-setup.md#lights-that-indicate-the-battery-level) található akkumulátorjelző világítással gyorsan ellenőrizheti az akkumulátor kapacitását anélkül, hogy bejelentkezik az eszközre.

<a id="list"></a>

**Ismert problémák**
- [Minden alkalommal, amikor az energiaellátás 18%-ra csökkent, az eszköz hirtelen automatikusan leáll](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive Az UWP-alkalmazás nem működik az Azure AD-felhasználók számára](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Miért látom a 0x80180014 Autopilot alatt?](#why-do-i-see-0x80180014-during-autopilot)
- [Microsoft Store hibakód 0x80131500](#microsoft-store-error-code-0x80131500)
- [Microsoft Edge nem tudja elindítani a mikrofont](#microsoft-edge-fails-to-start-the-microphone)
- [**Kijavítva** – A Remote Assist videó 20 perc után lefagy](#remote-assist-video-freezes-after-20-minutes)
- [Az automatikus bejelentkezés bejelentkezést kér](#auto-login-asks-for-log-in)
- [Microsoft Edge nem indul el](#microsoft-edge-fails-to-launch)
- [A billentyűzet nem vált át speciális karakterekre](#keyboard-doesnt-switch-to-special-characters)
- [**Kijavítva** – A zárolt fájlok letöltésekor nem jelenik meg hiba](#downloading-locked-files-doesnt-error)
- [**Kijavítva** – Eszközportál feltöltés/letöltés időkorrekta](#device-portal-file-uploaddownload-times-out)
- [Kék képernyő, miután az Insider előzetes verzióból való igénylést egy Insider buildeléses flash() módú eszközön](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
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
- [Bluetooth eszközök nem párosodnak](#bluetooth-devices-arent-pairing)
- [Az USB-C mikrofon nem működik](#usb-c-microphone-isnt-working)
- [A Gépház felsorolt eszközök nem működnek](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Minden alkalommal, amikor az energiaellátás 18%-ra csökkent, az eszköz hirtelen automatikusan leáll

Van egy ismert probléma, amelyben amikor az eszköz eléri a 18%-os akkumulátort, az váratlanul leáll. Ez szoftveres, és nem hardverrel vagy akkumulátorral kapcsolatos probléma, ezért erre ne cserélje ki az eszközöket. Ha nem biztos abban, hogy a probléma megfelel-e ennek a hibának, kérjük:

1. Győződjön meg arról, hogy a választható diagnosztika engedélyezve van az eszközön vagy az eszközön
1. Reprodukálja a problémát
1. Probléma [Visszajelzési központ](hololens-feedback.md) elküldése
1. A visszajelzési probléma URL-címének megosztása
1. [Kapcsolatfelvétel az ügyfélszolgálattal](https://aka.ms/hololenssupport)

[Vissza a listához](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive Az UWP-alkalmazás nem működik az Azure AD-felhasználók számára

Ha a vállalati OneDrive használja az Azure AD-fiókját, előfordulhat, hogy hibába ütközött, amikor bejelentkezett a OneDrive alkalmazásba. Ha nem tud bejelentkezni a OneDrive a Kamera alkalmazás által rögzített képek és videók automatikus feltöltésére nincs hatással. A fájlok továbbra is menthetők és elérhetők a felhőalapú OneDrive Vállalati verzió tárolóból. A OneDrive és HoloLens csapat már dolgozik a probléma megoldásán.

### <a name="workarounds"></a>Kerülő megoldások

Előfeltétel: Az ügyfelek a Microsoft Edge és az eszköz operációs rendszerének frissítése egy Windows Holographic, 21H1 build vagy újabb verzióra van frissítve.

Ha ezt a problémát tapasztalja, próbálkozzon a következők valamelyikével:

- A felhasználók közvetlenül hozzáférhetnek OneDrive Vállalati verzióhoz a Microsoft Edge webhelyről, és a böngészőjükből használhatja a webhely fájljaikat.
- A felhasználók a OneDrive PWA alkalmazásból HoloLens alkalmazást a Microsoft Edge. Így a felhasználók ismét megtekinthetik és kezelhetik az eszközön lévő fájlokat. Olvassa el és kövesse ezeket az utasításokat a OneDrive PWA [telepítéséhez a HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Vissza a listához](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Miért látom a 0x80180014 Autopilot alatt?

Ez a hiba általában az eszköz alaphelyzetbe állítása és a folyamatok újrahasználata során merül fel, amikor HoloLens eszköz legalább egyszer végigment az Autopiloton. A probléma megoldásához törölje az eszközt a Microsoft Intune [és](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) állítsa vissza az AutoPilot-folyamat befejezéséhez.

További információért tekintse meg az [AutoPilot-oldalon](hololens2-autopilot.md#why-do-i-see-0x80180014-during-autopilot) található hibaelhárítási lépéseket.

## <a name="microsoft-store-error-code-0x80131500"></a>Microsoft Store hibakód 0x80131500

Előfordulhat, hogy egyes felhasználók Microsoft Store nem a várt módon működnek, és a hibakódot 0x80131500. Ezt a problémát az okozza, hogy a HoloLens beállított régió nem érhető el a Microsoft Store alkalmazásban a HoloLens. Ha hibakódokat 0x80131500, megkerülő megoldásként:

1. Állítsa Gépház > Az & Nyelv > régió > ország vagy régió beállítását a következők egyikére:
    - Egyesült Államok, Japán, Kína, Németország, Kanada, Egyesült Királyság, Írország, Franciaország, Ausztrália, Új-Zéland.
1. Indítsa újra az Áruház alkalmazást.
1. Ahhoz, hogy a teljes eszköz tükrözze a változást, az eszközt újra kell indítani.

A HoloLens csapat további régiók támogatásán dolgozik.

Itt [láthatja, hogy az országoknak 2-es HoloLens kell vásárolnia.](hololens2-purchase.md)

## <a name="microsoft-edge-fails-to-start-the-microphone"></a>Microsoft Edge nem tudja elindítani a mikrofont

Ha a felhasználók Microsoft Edge a mikrofon nem indul el, így nem használhatók az Edge-hez a HoloLens. Ez az ismert probléma a Microsoft Edge-alkalmazás verziójához kapcsolódik. Ne írjon át perjelet az eszköz egy korábbi verziójára, mivel ez nem oldja meg a problémát.

### <a name="who-is-affected"></a>Who érintett?

A 93 Microsoft Edge 94-es vagy 95-ös verzióval nem Microsoft Edge felhasználók.
A Microsoft Store alkalmazással ellenőrizheti, hogy a Microsoft Edge melyik verzióját használja, majd válassza a **...,** majd a Letöltések és frissítések lehetőséget.

### <a name="work-around"></a>A munka során

A jelenlegi javítás a 96-os verzióban érhető el az Insidersben regisztrált Microsoft Edge számára. Ez eltér az eszköz Belső eszközként Windows regisztrációtól. Olvassa el ezeket az utasításokat az Edge belső programjában való [regisztrációval kapcsolatos részletekért.](hololens-new-edge.md#microsoft-edge-insider-channels)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>A Remote Assist videó 20 perc után lefagy

> [!NOTE]
> A Remote Assist egy újabb verziója is elérhető, amely ki lett javítva a problémára. A probléma elkerülése érdekében frissítse a [Remote Assistt](holographic-store-apps.md#update-apps) a legújabb verzióra.

> [!NOTE]
> Az ismert probléma súlyossága miatt ideiglenesen szüneteltette a Windows Holographic 21H1-es verziójának elérhetőségét. A 21H1 build ismét elérhető, így az eszközök ismét frissíthetők a legújabb 21H1 buildre.

Az Windows [Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójának legújabb kiadásában a Remote Assist néhány felhasználója a hívások során 20 percnél is fagypontot tapasztalt. Ez egy **ismert probléma.**

### <a name="workarounds"></a>Kerülő megoldások

Ha nem tudja újabb buildre frissíteni a Remote Assistet, próbálkozzon a következővel.

#### <a name="restart-in-between-calls"></a>Újraindítás hívások között

Ha a hívások hossza 20 percnél hosszabb, és ezt a problémát tapasztalja, próbálja meg újraindítani az eszközt. Ha újraindítja az eszközt a Remote Assist-hívások között, az eszköz frissül, és jó állapotba kerül.

Ha gyorsan újraindít egy eszközt a [Holographic Windows 21H1-es verziójában,](hololens-release-notes.md#windows-holographic-version-21h1) nyissa meg a Start menüt, válassza a felhasználó ikont, majd válassza az **Újraindítás lehetőséget.**

[Vissza a listához](#list)

## <a name="auto-login-asks-for-log-in"></a>Az automatikus bejelentkezés bejelentkezést kér

A HoloLens 2-es eszközök konfigurálhatóak úgy, hogy automatikusan bejelentkeznek az **Gépház**  ->  **Accounts**  ->  **Sign-in Options** ->  és a Required (Kötelező) beállításnál a **Never**(Soha) értékre. Előfordulhat, hogy egyes felhasználóknak újra be kell jelentkezniük az eszközre, amikor egy jelentős frissítéssel( például funkciófrissítéssel) frissítik az eszközt. Ez egy **ismert probléma.**

Példa arra, hogy mikor fordulhat elő ez:

- Eszköz frissítése Windows Holographic 2004-es verziójáról (Build 19041.xxxx) a Windows Holographic 21H1-es verziójára (Build 20346.xxxx)
- Egy eszköz frissítése ugyanannak a fő buildnek a nagy frissítéséhez, például a Windows Holographic 2004-es verziójának a holographic Windows 20H2-es verziójára
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

Néhány ügyfél olyan problémát jelentett, Microsoft Edge nem indul el. Ezen ügyfelek esetében a probléma újraindítással továbbra is fennáll, és nem oldódik meg a Windows vagy alkalmazásfrissítésekkel. Ha ezt a problémát tapasztalja, és megerősítette, hogy [az Windows](hololens-updates.md#manually-check-for-updates)naprakész, jelentsen be egy hibát a Visszajelzési központ-alkalmazásból [a](hololens-feedback.md) következő kategóriával és alkategóriával: Install and Update > Downloading, installing, and configuring Windows Update ..

Nincsenek ismert megkerülő megoldások, mivel eddig nem sikerült megoldani a problémát. Hiba bejelentése a Visszajelzési központ segít a vizsgálatban! Ez egy **ismert probléma.**

[Vissza a listához](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>A billentyűzet nem vált át speciális karakterekre

Az OOBE során probléma lép fel, amely során, amikor a felhasználó kiválasztott egy munkahelyi vagy iskolai fiókot, és megadta a jelszavát, a billentyűzeten lévő speciális karakterekre próbál átváltani az &123 gombra koppintva, nem változik különleges karakterekre. Ez egy **ismert probléma.**

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

A Holographic Windows korábbi buildje során zárolt fájl letöltésekor az eredmény egy HTTP-hibalap lesz. A Windows Holographic 21H1-es verziójának frissítésében a zárolt fájl letöltésének a kipróbálása azt jelenti, hogy semmi sem látható– a fájl nem tölt le, és nem jelenik meg hiba.

[Vissza a listához](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Eszközportál feltöltési/letöltési időkorrekta
> [!NOTE]
> Ez egy ismert **hiba,** amely a [Holographic Windows 21H1 - 2021. júliusi frissítésében javítva lett.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update) Ha az áthidaló megoldás részeként korábban letiltotta az SSL-kapcsolatot, erősen ajánlott újra engedélyezni.

Egyes ügyfelek azt találták, hogy amikor fájlokat próbálnak feltölteni vagy letölteni, a művelet lefagyhat, majd időkorrekciót vagy soha nem fejeződik be. Ez elkülönül a "fájl[zárolt"](#downloading-locked-files-doesnt-error) ismert problémától – ez a Windows Holographic 2004-es, 20H2-es és 21H1-es piaci buildeket érinti. A problémát az okozza, hogy a Eszközportál bizonyos kéréseket kezel, és a https használata esetén a legnagyobb konzisztens találat, amely az alapértelmezett beállítás.

### <a name="workaround"></a>Áthidaló megoldás

Ez az áthidaló megoldás, amely ugyanúgy vonatkozik a Wi-Fi az UsbNcm-re, a "kötelező" beállítás letiltása az "SSL-kapcsolat" alatt. Lépjen a következő oldalra: **Eszközportál, System**( Rendszer) és válassza a **Preferences (Beállítások)** lapot. Az **Eszközbiztonság szakaszban** keresse meg az **SSL-kapcsolatot,** és törölje a jelölését a **Kötelező letiltásához.**

A felhasználónak ekkor az http:// kell lennie, https:// (IP-cím) és az olyan funkciók, mint a fájlfeltöltés és -letöltés működni fognak.

[Vissza a listához](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Kék képernyő, miután az Insider előzetes verzióból való igénylést egy Insider buildeléses flash() módú eszközön

Ez olyan problémát jelent, amely hatással van az Insider előzetes verziójú buildet használó felhasználókra, egy új belső előzetes verziójú buildel új belsős buildel új HoloLens 2-es verzióra, majd az Insider programból való regisztrálta őket. Ez egy **ismert probléma.**

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

    1. Helyezze [a 2. HoloLens flash()](hololens-recovery.md) módba manuálisan úgy, hogy teljesen lekapcsolód, miközben nem csatlakozik. Ezután a Kötet lenyomva tartási gombra koppintva koppintson a Bekapcsoló gombra.

    1. Csatlakozás nyissa meg a számítógépet, és nyissa meg az Advanced Recovery Companiont.

    1. A 2. HoloLens az alapértelmezett buildhez.

[Vissza a listához](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive nem tölt fel automatikusan képeket

A OneDrive alkalmazás nem HoloLens támogatja a munkahelyi vagy iskolai fiókok automatikus kamerafeltöltését. Ez egy **ismert probléma.**

Workarounds:

- Ha a vállalkozása számára is elérhető, a fogyasztói Microsoft-fiókok támogatják az automatikus kamerafeltöltést. Munkahelyi vagy iskolai fiókján kívül Microsoft-fiók is bejelentkezhet a OneDrive (a OneDrive a kettős bejelentkezést támogatja). A profilban Microsoft-fiók profilban OneDrive automatikus, háttérkamerás kameratekercs-feltöltést engedélyezhet.

- Ha nem tud biztonságosan használni egy fogyasztói Microsoft-fiók a fényképek automatikus feltöltéséhez, manuálisan feltölthet fényképeket a munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásból. Ennek érdekében győződjön meg arról, hogy bejelentkezett a munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásban. Kattintson a **+** gombra, majd válassza a **Feltöltés lehetőséget.** Keresse meg a feltölteni kívánt fényképeket vagy videókat a **Pictures (Képek) és a Camera Roll (>) között.** Válassza ki a feltölteni kívánt fényképeket vagy videókat, majd kattintson a **Megnyitás gombra.**

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

Az alábbiak közül egyet vagy többet is el kell szabadítanunk a tárterületen:

- Töröljön néhány nem használt szóközt. A Rendszer **Gépház**  >    >  **gombra,** válasszon ki egy olyan helyet, amelyre már nincs szüksége, majd válassza az **Eltávolítás lehetőséget.**
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

Lásd még a képszínekkel vagy a [fényerejével kapcsolatos hibaelhárítással kapcsolatos információkat.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Az IPD beállítása nem alkalmazható a 2. HoloLens esetén, mivel a szem pozícióit a rendszer számítja ki. 

[Vissza a listához](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Nem tudok bejelentkezni, mert a HoloLens korábban valaki más számára lett beállítva

Az eszközt [Flashing (Flashing) módba **használhatja,**](hololens-recovery.md#clean-reflash-the-device) és az Advanced Recovery Companion használatával helyreállíthatja az eszközt.

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


- Nem minden alkalmazás kompatibilis Microsoft Store az emulátorral. Young Conker és a Fragments például nem lejátszható az emulátoron.
- A számítógép webkamerája nem használható a Emulator.
- A szolgáltatás Live Preview Windows Eszközportál nem működik az emulátorral. Továbbra is rögzíthet Mixed Reality videókat és képeket.

[Vissza a listához](#list)

## <a name="voice-commands-arent-working"></a>A hangparancsok nem működnek

Ha Cortana nem válaszol a hangparancsra, győződjön meg arról, hogy Cortana be van kapcsolva. A Minden alkalmazás a módosításokhoz válassza **Cortana**  >  notebook Gépház  >    >   menüt. További információ a beszédről: [Use your voice with HoloLens](hololens-cortana.md).

A HoloLens (1. generációs) beépített beszédfelismerés nem konfigurálható. Mindig be van kapcsolva. A HoloLens 2. beállításban eldöntheti, hogy bekapcsolja-e a beszédfelismerést és a Cortana az eszköz beállítása során.

Ha a HoloLens 2. nem válaszol a hangjára, győződjön meg arról, hogy a Beszédfelismerés be van kapcsolva. A Start **Gépház** Privacy Speech  >    >  **(Beszédfelismerési beszéd)**  >  **menüben** kapcsolja be a **Beszédfelismerést.**

[Vissza a listához](#list)

## <a name="hand-input-isnt-working"></a>A kézi bevitel nem működik

Ahhoz, HoloLens a kézmozdulatok láthatóak, kézmozdulatok keretében kell tartania őket.  A Mixed Reality Kezdőlap visszajelzést ad, amely tudatja, mikor követik nyomon a kézzel.  A visszajelzések eltérőek a következő verziók HoloLens:

- A HoloLens (1. generációs) esetében a tekintet kurzora pontról gyűrűre változik
- A 2. HoloLens kurzor akkor jelenik meg, ha a kéz egy lappal közelebb van, és egy kéz sugár jelenik meg, ha a belók távolodnak

Számos modern alkalmazás a Kezdőlaphoz hasonló bemeneti mintákat Mixed Reality követ.  További információ a kézi bevitelnek a HoloLens [(1. generációs)](hololens1-basic-usage.md#use-hololens-with-your-hands) és [a 2. HoloLens való használatával kapcsolatban.](hololens2-basic-usage.md#the-hand-tracking-frame)

Vegye figyelembe, hogy a kézkövetés bizonyos típusú kézkövetési funkcióval nem működik.  Gyakori példa a fekete védőkesztyűk, amelyek általában befogadják a világítást, és a mélységi kamera nem tudja felvenni őket.  Ha a munkája során védőkesztyűt is kell tenni, javasoljuk, hogy egy világosabb színt, például kéket vagy szürkét próbáljon ki.  Egy másik példa a nagy méretű, nagy méretű, kézbegyűség. Ez általában elfedi a kéz alakját. Javasoljuk, hogy a legjobb eredmény érdekében a lehető legjobban illeszkedő, jól illeszkedő védőkét használja.

Ha a vizor ujjlenyomattal vagy elmosott lenyomattal rendelkezik, használja a vizorhoz HoloLens tisztításhoz használt mikrofiberos tisztítást.

[Vissza a listához](#list)

## <a name="cant-connect-to-wi-fi"></a>Nem lehet csatlakozni a Wi-Fi

Ha nem tud csatlakozni a HoloLens egy Wi-Fi hálózathoz:

- Ellenőrizze, hogy Wi-Fi be van-e kapcsolva. Az ellenőrzéshez használja a Start kézmozdulatot, majd válassza **Gépház**  >  **Hálózati &amp; internet**  >  **Wi-Fi lehetőséget.** Ha Wi-Fi be van kapcsolva, próbálja meg kikapcsolni, majd újra bekapcsolni.
- Lépjen közelebb az útválasztóhoz vagy a hozzáférési ponthoz.
- Indítsa újra a Wi-Fi útválasztót, majd [indítsa újra HoloLens.](hololens-recovery.md) Próbáljon meg újból csatlakozni.
- Ha ezek közül egyik sem működik, ellenőrizze, hogy az útválasztó a legújabb belső vezérlőprogramot használja-e. Ezt az információt a gyártó webhelyén találja.

[Vissza a listához](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth eszközök nem párosítása

Ha problémába merült fel egy Bluetooth [eszközhöz](hololens-connect-devices.md)való párosítása, próbálkozzon a következővel:

- Az Eszközök **Gépház,** és győződjön meg arról, hogy az  >  Bluetooth be van kapcsolva. Ha igen, kapcsolja ki és be újra.
- Győződjön meg arról, Bluetooth az eszköz teljes mértékben fel van töltve, vagy friss akkumulátorokkal rendelkezik.
- Ha továbbra sem tud csatlakozni, indítsa [újra a HoloLens.](hololens-recovery.md)

[Vissza a listához](#list)

## <a name="usb-c-microphone-isnt-working"></a>Az USB-C mikrofon nem működik

Vegye figyelembe, hogy egyes USB-C-mikrofonok helytelenül jelentik magukat mikrofonként és *beszélőként* is. Ez a mikrofonnal, és nem a HoloLens. Ha ezen mikrofonok valamelyikét csatlakoztatja HoloLens, előfordulhat, hogy a hang elveszett. Szerencsére van egy egyszerű javítás.  

A **Gépház** System Sound eszközben explicit módon állítsa be a beépített beszélők  ->    ->   **(Analog Feature Audio Driver)** alapértelmezett eszközként való **beállítását.** HoloLens a beállítást akkor is meg kell jegyezni, ha a mikrofont eltávolítják, majd később újracsatlakoztatják.

![USB-C-mikrofonok hibaelhárítása.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>A következőben elérhetőként felsorolt Gépház nem működnek

HoloLens (1. generációs) nem támogatja a Bluetooth hangprofilokat. Bluetooth hangeszközök, például a beszélők és a headsetek elérhetőként jelennek meg HoloLens beállításokban, de nem támogatottak.

HoloLens 2. Bluetooth támogatja a Bluetooth A2DP hangprofilt a audio lejátszáshoz. A Bluetooth-kéz nélküli profil, amely lehetővé teszi a mikrofon rögzítését egy Bluetooth periféria nem támogatott a 2. HoloLens támogatja.

Ha problémája van egy Bluetooth eszköz használatával, győződjön meg arról, hogy az támogatott eszköz. A támogatott eszközök a következők:

- Az angol nyelvű QWERTY Bluetooth billentyűzeteket (ezeket bárhol használhatja, ahol a holografikus billentyűzetet használja).
- Bluetooth mice.
- A [HoloLens gombra.](hololens1-clicker.md)

Más HID és BLUETOOTH ESZKÖZeket is párosíthat a HoloLens. Előfordulhat azonban, hogy telepítenie kell a megfelelő társalkalmazásokat a Microsoft Store az eszközök ténylegesen való használatához.

[Vissza a listához](#list)
