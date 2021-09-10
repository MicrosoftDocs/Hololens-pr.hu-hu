---
title: HoloLens Eszköz hibaelhárítása
description: Naprakész maradhat az eszközök problémáinak és hibaelhárítási HoloLens leggyakoribb megoldásaival kapcsolatban.
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
ms.openlocfilehash: 6ac86acf85e8e4fc1b97473732ea358d3d612d12
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428667"
---
# <a name="device-troubleshooting"></a>Eszköz hibaelhárítása

Ez a cikk több gyakori probléma megoldását HoloLens ismerteti.

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

## <a name="remote-assist-video-freezes-after-20-minutes"></a>A Remote Assist videó 20 perc után lefagy

> [!NOTE]
> A Remote Assistnek van egy újabb verziója, amely ki lett javítva a problémára. A probléma elkerülése érdekében frissítse a [Remote Assistt](holographic-store-apps.md#update-apps) a legújabb verzióra.

> [!NOTE]
> Az ismert probléma súlyossága miatt ideiglenesen szüneteltette a holografikus Windows 21H1-es verziójának elérhetőségét. A 21H1 build ismét elérhető, így az eszközök ismét frissíthetők a legújabb 21H1 buildre.

A [Holographic Windows 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójának legújabb verziójában a Remote Assist néhány felhasználója a hívások során 20 percnél is fagypontot tapasztalt. Ez egy **ismert probléma.**

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
- Egy eszköz frissítése ugyanannak a fő buildnek a nagy frissítéséhez, például a Windows Holographic 2004-es verziójának a holographic Windows, 20H2-es verzióra való frissítése
- Eszköz frissítése gyári rendszerképről a legújabb rendszerképre

Ez nem fordulhat elő a következő időszakban:

- Havi karbantartási frissítést frissítő eszközök

Módszerek használata:

- Bejelentkezési módszerek, például PIN-kód, jelszó, írisz, webes hitelesítés vagy FIDO2-kulcsok.
- Ha az eszköz PIN-kódját nem lehet megöröklni, és más hitelesítési módszerek nem érhetők el, akkor a felhasználó használhat manuális [perjeles módot.](hololens-recovery.md#manual-procedure)

[Vissza a listához](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge nem indul el

> [!NOTE]
> Ezt a problémát eredetileg a szolgáltatás szállítási verziójával hozták Microsoft Edge szem előtt tartva. Ez a probléma megoldható az új [Microsoft Edge.](hololens-new-edge.md) Ha nem, kérjük, visszajelzést írjon.

Néhány ügyfél olyan problémát jelentett, Microsoft Edge nem indul el. Ezen ügyfelek esetében a probléma újraindítással továbbra is fennáll, és nem oldódik meg a Windows vagy alkalmazásfrissítésekkel. Ha ezt a problémát tapasztalja, és megerősítette, hogy [az Windows](hololens-updates.md#manually-check-for-updates)naprakész, jelentsen be egy hibát a Visszajelzési központ-alkalmazásból [a](hololens-feedback.md) következő kategóriával és alkategóriával: Install and Update > Downloading, installing, and configuring Windows Update ..

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
> Ez egy ismert **probléma,** amely a [holografikus Windows 21H1-es és 2021. júliusi frissítésében lett kijavítva.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)

A Holographic Windows korábbi buildje során zárolt fájl letöltésekor az eredmény egy HTTP-hibalap lenne. A Windows Holographic 21H1-es verziójának frissítésével a zárolt fájlok letöltésének próbálkozáskor semmi sem látható – a fájl nem tölt le, és nem jelenik meg hiba.

[Vissza a listához](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Eszközportál feltöltési/letöltési időkorrekta
> [!NOTE]
> Ez egy ismert **probléma,** amely a [holografikus Windows 21H1-es és 2021. júliusi frissítésében lett kijavítva.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update) Ha az áthidaló megoldás részeként korábban letiltotta az SSL-kapcsolatot, erősen ajánlott újra engedélyezni.

Egyes ügyfelek azt találták, hogy amikor fájlokat próbálnak feltölteni vagy letölteni, a művelet lefagyhat, majd időkorrekciót vagy soha nem fejeződik be. Ez elkülönül a "fájl[zárolt"](#downloading-locked-files-doesnt-error) ismert problémától – ez a Windows Holographic 2004-es, 20H2-es és 21H1-es piaci buildeket érinti. A problémát az okozza, hogy a Eszközportál bizonyos kéréseket kezel, és a https használata esetén a legnagyobb konzisztens találat, amely az alapértelmezett beállítás.

### <a name="workaround"></a>Áthidaló megoldás

Ez az áthidaló megoldás, amely ugyanúgy vonatkozik a Wi-Fi az UsbNcm-re, a "kötelező" beállítás letiltása az SSL-kapcsolat alatt. Lépjen a következő oldalra: **Eszközportál, System**( Rendszer) és válassza a **Preferences (Beállítások)** lapot. Az **Eszközbiztonság szakaszban** keresse meg az **SSL-kapcsolatot,** és törölje a jelölését a **Kötelező letiltásához.**

A felhasználónak ekkor az http:// kell https:// (IP-cím) és olyan funkciókkal, mint a fájlfeltöltés és -letöltés.

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

- Ha ez a vállalkozása számára is elérhető, a fogyasztói Microsoft-fiókok támogatják az automatikus kamerafeltöltést. A munkahelyi vagy iskolai Microsoft-fiók (a OneDrive alkalmazás támogatja a kettős bejelentkezést) mellett a fiókba is bejelentkezhet. Az alkalmazás Microsoft-fiók profilból OneDrive automatikus, háttérkamerás kameratekercs-feltöltést engedélyezhet.

- Ha nem tud biztonságosan használni fogyasztói Microsoft-fiók a fényképek automatikus feltöltéséhez, manuálisan feltölthet fényképeket a munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásból. Győződjön meg arról, hogy be van jelentkezve a munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásban. Kattintson a **+** gombra, majd válassza a **Feltöltés lehetőséget.** Keresse meg a feltölteni kívánt fényképeket vagy videókat a Képek és > **kiválasztásával.** Válassza ki a feltölteni kívánt fényképeket vagy videókat, majd kattintson a **Megnyitás gombra.**

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

Az alábbi lépések közül egy vagy több megoldással szabadíthat fel tárhelyet:

- Töröljön néhány nem használt szóközt. Válassza a **Gépház**  >    >  **lehetőséget,** válasszon ki egy szóközt, amire már nincs szüksége, majd válassza az Eltávolítás **lehetőséget.**
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
- Bizonyos szemfizika, szemkörülmények vagy szemműveletek, például keskeny szem, hosszú szempillák, amblyológus, nystagmus, a LASIK vagy más szemműveletek bizonyos esetekben

Sikertelen kísérlet esetén próbálkozzon a következővel:

- Az eszköz vizorának tisztítása
- Szemüveg tisztítása
- Az eszköz vizorának a lehető legnagyobb egymáshoz zárásával
- Objektumok (például haj) mozgatása a vizorban
- Világítás bekapcsolása a helyiségben, vagy a közvetlen világításból való eltálás

Ha követte az összes útmutatót, és a tiltás továbbra is sikertelen, a figyelmeztetést a következő Gépház. Visszajelzést is küldhet a [Visszajelzési központ.](hololens-feedback.md)

Lásd még a képszínekkel vagy a [fényerejével kapcsolatos hibaelhárítással kapcsolatos információkat.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Az IPD beállítása nem alkalmazható a 2. HoloLens, mivel a szem pozícióit a rendszer számítja ki. 

[Vissza a listához](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Nem tudok bejelentkezni, mert a HoloLens korábban valaki más számára lett beállítva

Az eszközt [Flashing (Flashing) módba **használhatja,**](hololens-recovery.md#clean-reflash-the-device) és az Advanced Recovery Companion használatával helyreállíthatja az eszközt.

[Vissza a listához](#list)


## <a name="unity-isnt-working"></a>A Unity nem működik

- Lásd: [Install the tools](/windows/mixed-reality/install-the-tools) for the most-to-date version of Unity recommended for HoloLens development (A Unity legújabb verziójának telepítése a HoloLens érdekében.
- A Unityvel kapcsolatos ismert HoloLens Technical Preview-val kapcsolatban a következő Unity-fórumokon [HoloLens dokumentáljuk:](https://forum.unity3d.com/threads/known-issues.394627/).

[Vissza a listához](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Eszközportál nem működik megfelelően

- A Rögzítés funkció Live Preview Mixed Reality néhány másodpercnyi késést is mutathat.

- A Virtuális bemenet lapon a Virtuális kézmozdulatok szakasz Kézmozdulatok és Görgetés vezérlői nem működnek. A használatuknak nincs hatása. A virtuális beviteli oldalon található virtuális billentyűzet megfelelően működik.

- A fejlesztői mód Gépház után néhány másodpercet is igénybe vehet, amíg a kapcsoló bekapcsolja a Eszközportál beállítást.

[Vissza a listához](#list)

## <a name="the-hololens-emulator-isnt-working"></a>A HoloLens Emulator nem működik

A HoloLens emulátorról a fejlesztői dokumentációnkban tájékozódhat.  További információ [a HoloLens emulátor hibaelhárításáról.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Nem minden alkalmazás kompatibilis Microsoft Store az emulátorral. Young Conker és a Fragments például nem lejátszható az emulátoron.
- A számítógép webkameráját nem használhatja a Emulator.
- Az élő előzetes verziójú Windows Eszközportál nem működik az emulátorral. Továbbra is rögzíthet Mixed Reality videókat és képeket.

[Vissza a listához](#list)

## <a name="voice-commands-arent-working"></a>A hangparancsok nem működnek

Ha Cortana nem válaszol a hangparancsra, győződjön meg arról, hogy Cortana be van kapcsolva. A módosítások Minden alkalmazás a Cortana   >    >  **notebook**  >  **Gépház** elemet. További információ a beszédről: [Use your voice with HoloLens](hololens-cortana.md).

A HoloLens (1. generációs) beépített beszédfelismerés nem konfigurálható. Mindig be van kapcsolva. A 2. HoloLens megadhatja, hogy bekapcsolja-e a beszédfelismerést és a Cortana az eszköz beállítása során.

Ha a HoloLens 2., nem válaszol a hangjára, győződjön meg arról, hogy a Beszédfelismerés be van kapcsolva. Kattintson a **Start**  >  **Gépház** Privacy Speech  >  **(Beszédfelismerési szolgáltatás)**  >  **menüre,** és kapcsolja be a **Beszédfelismerést.**

[Vissza a listához](#list)

## <a name="hand-input-isnt-working"></a>A kézi bevitel nem működik

Ahhoz, HoloLens a kézmozdulatok láthatóak, kézmozdulatok keretében kell tartania őket.  A Mixed Reality Kezdőlap visszajelzést ad, amely tudatja, mikor követik nyomon a kézzel.  A visszajelzések eltérőek a következő verziók HoloLens:
- A HoloLens (1. generációs) esetében a tekintet kurzora pontról gyűrűre változik
- A 2. HoloLens kurzor megjelenik, ha a kéz egy lappal közelebb van, és egy kéz sugár jelenik meg, ha a belók távolodnak

Számos modern alkalmazás a Kezdőlaphoz hasonló bemeneti mintákat Mixed Reality követ.  További információ a kézi bevitelnek a HoloLens [(1. generációs)](hololens1-basic-usage.md#use-hololens-with-your-hands) és [a 2. HoloLens való használatával kapcsolatban.](hololens2-basic-usage.md#the-hand-tracking-frame)

Vegye figyelembe, hogy a kézkövetés bizonyos típusú kézkövetési funkcióval nem működik.  Gyakori példa a fekete védőkesztyűk, amelyek általában befogadják a világítást, és a mélységi kamera nem tudja felvenni őket.  Ha a munkája során védőkesztyűt is kell tenni, javasoljuk, hogy egy világosabb színt, például kéket vagy szürkét próbáljon ki.  Egy másik példa a nagy méretű, nagy méretű, kézbegyűkösség, amely általában elfedi a kéz alakját. Javasoljuk, hogy a legjobb eredmény érdekében a lehető legjobban illeszkedő, jól illeszkedő védőkét használja.

Ha a vizor ujjlenyomattal vagy elmosott lenyomattal rendelkezik, használja a vizorhoz HoloLens tisztításhoz használt mikrofiberos tisztítást.

[Vissza a listához](#list)

## <a name="cant-connect-to-wi-fi"></a>Nem lehet csatlakozni a Wi-Fi

Ha nem tud csatlakozni a HoloLens egy Wi-Fi hálózathoz:

- Ellenőrizze, hogy Wi-Fi be van-e kapcsolva. Az ellenőrzéshez használja a Start (Indítás) kézmozdulatot, majd válassza **Gépház**  >  **Network &amp; Internet**  >  **Wi-Fi** lehetőséget. Ha Wi-Fi be van kapcsolva, próbálja meg kikapcsolni, majd újra bekapcsolni.
- Lépjen közelebb az útválasztóhoz vagy a hozzáférési ponthoz.
- Indítsa újra a Wi-Fi útválasztót, majd [indítsa újra HoloLens.](hololens-recovery.md) Próbáljon meg újra csatlakozni.
- Ha ezek közül egyik sem működik, ellenőrizze, hogy az útválasztó a legújabb belső vezérlőprogramot használja-e. Ezt az információt a gyártó webhelyén találja.

[Vissza a listához](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth eszközök nem párosítása

Ha problémákat tapasztal egy Bluetooth [eszközhöz](hololens-connect-devices.md)való párosítása esetén, próbálkozzon a következő megoldásokkal:

- Az Eszközök **Gépház,** és győződjön meg arról, hogy Bluetooth  >  be van kapcsolva. Ha igen, kapcsolja ki és be újra.
- Győződjön meg arról, Bluetooth eszköz teljesen fel van töltve, vagy friss akkumulátorokkal rendelkezik.
- Ha továbbra sem tud csatlakozni, indítsa [újra a HoloLens.](hololens-recovery.md)

[Vissza a listához](#list)

## <a name="usb-c-microphone-isnt-working"></a>Az USB-C mikrofon nem működik
Vegye figyelembe, hogy egyes USB-C-mikrofonok helytelenül jelentik magukat mikrofonként és *beszélőként* is. Ez a mikrofonnal, és nem a mikrofonnal HoloLens. Ha ezen mikrofonok valamelyikét csatlakoztatja HoloLens, a hang elveszhet. Szerencsére van egy egyszerű javítás.  

A **Gépház** System Sound eszközben explicit módon állítsa be a beépített beszélők  ->    ->   **(Analog Feature Audio Driver)** alapértelmezett eszközként való **beállítását.** HoloLens a beállítást akkor is meg kell jegyezni, ha a mikrofont eltávolítják, majd később újracsatlakoztatják.

![USB-C-mikrofonok hibaelhárítása.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>A következőben elérhetőként felsorolt Gépház nem működnek

HoloLens (1. generációs) nem támogatja a Bluetooth hangprofilokat. Bluetooth hangeszközök, például a beszélők és a headsetek elérhetőként jelennek meg a HoloLens beállításaiban, de ezek nem támogatottak.

HoloLens 2. Bluetooth A2DP hangprofilt támogatja a lejátszási lejátszáshoz. A Bluetooth-profil, amely lehetővé teszi a mikrofon rögzítését egy Bluetooth periféria nem támogatott a 2. HoloLens esetén.

Ha nem tudja használni a Bluetooth, ellenőrizze, hogy támogatott eszköz-e. A támogatott eszközök a következők:

- Az angol nyelvű QWERTY Bluetooth billentyűzeteket (ezeket bárhol használhatja, ahol a holografikus billentyűzetet használja).
- Bluetooth mice.
- A [HoloLens gombra.](hololens1-clicker.md)

Más HID- és BLUETOOTH-eszközöket is párosíthat a HoloLens. Előfordulhat azonban, hogy telepítenie kell a megfelelő társalkalmazásokat a Microsoft Store az eszközök ténylegesen való használatához.

[Vissza a listához](#list)
