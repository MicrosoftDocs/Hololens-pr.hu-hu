---
title: A HoloLens ismert problémái
description: Maradjon naprakész az ismert problémák és megkerülő megoldások listájával, amelyek hatással lehetnek a Unityt és a Windows eszközportál.
keywords: hibaelhárítás, ismert probléma, súgó
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: bc1d399a07a6a0622c953178cad7be1b8a018fdb
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378123"
---
# <a name="known-issues-for-hololens"></a>A HoloLens ismert problémái

Itt található a HoloLens-eszközök ismert problémáinak aktuális listája. Először ellenőrizze, hogy szokatlan viselkedést lát-e. A lista az új problémák felderített vagy jelentett, illetve a jövőbeli HoloLens-szoftverfrissítések során megoldott problémák esetén folyamatosan frissül.

>[!NOTE]
> - Ha olyan problémát tapasztal, amely nem akadályozza, jelentse a HoloLens-eszközön a [Visszajelzési központ.](hololens-feedback.md)
> - Ha a probléma, amely a visszajelzések küldése mellett blokkolja, nyújtsa be [a támogatási kérést.](https://aka.ms/hlsupport)

- [Az összes HoloLens-generáció ismert problémái](#known-issues-for-all-hololens-generations)
- [HoloLens 2-eszközök ismert problémái](#known-issues-for-hololens-2-devices)
- [A HoloLens ismert problémái (1. generációs)](#known-issues-for-hololens-1st-gen)
- [A HoloLens Emulator ismert problémái](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a>Az összes HoloLens-generáció ismert problémái

### <a name="unity"></a>Unity

- Lásd: [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most-to-date version of Unity recommended for HoloLens development (A Unity HoloLens-fejlesztéshez ajánlott legfrissebb verziójának telepítése).
- A Unity HoloLens Technical Preview ismert problémáit a [HoloLens Unity fórumain találhatja meg.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Windows eszközportál

- A Rögzítés funkció Live Preview Mixed Reality néhány másodpercnyi késést is mutathat.

- A Virtuális bemenet lapon a Virtuális kézmozdulatok szakasz Kézmozdulatok és Görgetés vezérlői nem működnek. A használatuknak nincs hatása. A virtuális beviteli oldalon található virtuális billentyűzet megfelelően működik.

- Miután engedélyezte a Fejlesztői módot a Beállításokban, a beállítás bekapcsolása néhány másodpercet is igénybe Eszközportál előtt.

### <a name="onedrive-camera-upload"></a>OneDrive-kamera feltöltése

A HoloLenshez való OneDrive alkalmazás nem támogatja a munkahelyi vagy iskolai fiókok automatikus kamerafeltöltését.

Workarounds:

- Ha a vállalkozása számára is elérhető, a fogyasztói Microsoft-fiókok támogatják az automatikus kamerafeltöltést. Munkahelyi vagy iskolai fiókján kívül Microsoft-fiók is bejelentkezhet az alkalmazásba (a OneDrive alkalmazás támogatja a kettős bejelentkezést). A OneDrive Microsoft-fiók profilból engedélyezheti az automatikus, háttérkamerás felvételeket.

- Ha nem tud biztonságosan használni fogyasztói Microsoft-fiók a fényképek automatikus feltöltéséhez, manuálisan feltölthet fényképeket munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásból. Győződjön meg arról, hogy be van jelentkezve munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásban. Kattintson a **+** gombra, majd válassza a Feltöltés **lehetőséget.** Keresse meg a feltölteni kívánt fényképeket vagy videókat a **Pictures (Képek) > Camera Roll (Kameratekercs) kiválasztásával.** Válassza ki a feltölteni kívánt fényképeket vagy videókat, majd kattintson a **Megnyitás gombra.**

## <a name="known-issues-for-hololens-2-devices"></a>HoloLens 2-eszközök ismert problémái

### <a name="device-using-auto-login-asks-for-log-in"></a>Az automatikus bejelentkezést használó eszköz bejelentkezést kér

A HoloLens 2-eszközök konfigurálhatóak úgy, hogy automatikusan bejelentkeznek a Settings   ->  **Accounts**  ->  **Sign-in Options** ->  és a Required setting the value to Never (Soha) értékre vannak **beállítva.** Előfordulhat, hogy egyes felhasználóknak újra be kell jelentkezniük az eszközre, amikor egy jelentős frissítéssel( például funkciófrissítéssel) frissítik az eszközt.

Példa arra, hogy mikor fordulhat elő ez:

- Eszköz frissítése a Windows Holographic 2004-es verziójáról (19041.xxxx build) a Windows Holographic 21H1-es verziójára (Build 20346.xxxx)
- Egy eszköz frissítése ugyanannak a fő buildnek a nagy frissítéséhez , például a Windows Holographic 2004-es verziójáról a Windows Holographic 20H2-es verziójára
- Eszköz frissítése gyári rendszerképről a legújabb rendszerképre

Ez nem fordulhat elő a következő időszakban:

- Havi karbantartási frissítést frissítő eszközök

Módszerek használata:

- Bejelentkezési módszerek, például PIN-kód, jelszó, írisz, webes hitelesítés vagy FIDO2-kulcsok.
- Ha az eszköz PIN-kódját nem lehet megöröklni, és más hitelesítési módszerek nem érhetők el, akkor a felhasználó használhat manuális [perjeles módot.](hololens-recovery.md#manual-procedure)

### <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge nem indul el

> [!NOTE]
> Ezt a problémát eredetileg a Microsoft Edge szállítási verziójával hozták létre. Ez a probléma megoldható az [új](hololens-new-edge.md)Microsoft Edge. Ha nem, kérjük, visszajelzést írjon.

Néhány ügyfél olyan problémát jelentett, Microsoft Edge nem indul el. Ezen ügyfelek esetében a probléma újraindítással továbbra is fennáll, és a Windows- vagy alkalmazásfrissítésekkel nem oldódik meg. Ha ezt a problémát tapasztalja, és megerősítette, hogy a [Windows](hololens-updates.md#manually-check-for-updates)naprakész, jelentsen be egy hibát a [Visszajelzési központ-alkalmazásból](hololens-feedback.md) a következő kategóriával és alkategóriával: Install and Update > Downloading, installing, and configuring Windows Update.

Nincsenek ismert megkerülő megoldások, mivel eddig nem sikerült megoldani a problémát. Hiba bejelentése a Visszajelzési központ segít a vizsgálatban!

### <a name="keyboard-does-not-switch-to-special-characters"></a>A billentyűzet nem vált át speciális karakterekre

Az OOBE során probléma lép fel, amikor a felhasználó kiválasztott egy munkahelyi vagy iskolai fiókot, és megadta a jelszavát, és a billentyűzeten lévő speciális karakterekre próbál átváltani az &123 gombra koppintva, nem változik különleges karakterekre.

A következőt kell körül kell dolgozni:
-   Zárja be a billentyűzetet, és nyissa meg újra a szövegmezőre koppintva.
-   Helytelenül adja meg a jelszót. Ha a billentyűzetet a következő alkalommal újraindítják, az a várt módon fog működni.
- Webes hitelesítés, zárja be a billentyűzetet, és válassza **a Bejelentkezés másik eszközről lehetőséget.**
-   Ha csak számokat ad meg, a felhasználó megnyomhat és lenyomva tarthat bizonyos kulcsokat egy kibontott menü megnyitásához.
-   USB-billentyűzet használata.

Ez nincs hatással a következőre:
- Azok a felhasználók, akik személyes fiókot választanának.

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-an-insider-build"></a>A kék képernyő akkor jelenik meg, ha az Insider előzetes verziójú buildjéről való leépítés után egy Insider buildel újra van építve egy eszközön

Ez olyan problémát jelent, amely hatással van az Insider előzetes verziójú buildet használó felhasználókra, új belső előzetes verziójú buildekkel új HoloLens 2-buildet hoz létre, majd nem regisztrálta őket az Insider programból.

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

    1. Helyezze a [HoloLens 2-t flashing (flash)](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) módba manuálisan úgy, hogy teljesen lekapcsolód, miközben nem csatlakozik. Ezután a Kötet lenyomva tartási gombra koppintva koppintson a Bekapcsoló gombra.
    
    1. Csatlakozzon a számítógéphez, és nyissa meg az Advanced Recovery Companiont.
    
    1. Flash the HoloLens 2 to the default build.

## <a name="known-issues-for-hololens-1st-gen"></a>A HoloLens ismert problémái (1. generációs)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Nem lehet csatlakozni a HoloLenshez, és üzembe helyezni a Visual Studio

> [!NOTE]
> Utolsó frissítés: 8/8 @ 17:11 – Visual Studio megjelent a VS 2019 16.2-es verziója, amely tartalmaz egy javítást a problémára. Javasoljuk, hogy a hiba elkerülése érdekében frissítsen erre a legújabb verzióra.

Visual Studio VS 2019 16.2-es verziója jelent meg, amely a probléma megoldását is tartalmazza. Javasoljuk, hogy a hiba elkerülése érdekében frissítsen erre a legújabb verzióra.

A probléma kiváltó oka: Azok a felhasználók, akik Visual Studio 201 Visual Studio 5-ös vagy korai kiadását használták alkalmazások telepítésére és hibakeresésére a HoloLensen, majd ezt követően az Visual Studio 2017 vagy Visual Studio 2019 legújabb verzióit használták ugyanazokkal a HoloLens-ekkel. A Visual Studio újabb verziói egy összetevő új verzióját telepítik, de a régebbi verzió fájljai az eszközön maradnak, ami az újabb verzió meghiúsulását okozza.  Ez a következő hibaüzenetet váltja ki: DEP0100: Győződjön meg arról, hogy a céleszközön engedélyezve van a fejlesztői mód. Nem sikerült fejlesztői licencet beszerezni a \<ip\> következőn: 80004005-ös hiba.

#### <a name="workaround"></a>Áthidaló megoldás

Csapatunk jelenleg dolgozik a javításon. Addig is az alábbi lépésekkel megoldhatja a problémát, és feloldhatja az üzembe helyezés és a hibakeresés blokkolását:  

1. Nyissa meg a Visual Studiót.

1. Válassza **a Fájl Új**  >  **projekt**  >  **lehetőséget.**

1. Válassza a **Visual C#**  >  **Windows asztali**  >  **konzolalkalmazás (.NET-keretrendszer) lehetőséget.**

1. Nevezze el a projektet (például "HoloLensDeploymentFix"), és győződjön meg arról, hogy a keretrendszer legalább .NET-keretrendszer 4.5-ös, majd kattintson az **OK gombra.**

1. Kattintson a jobb gombbal a hivatkozások **csomópontra** a Megoldáskezelő és adja hozzá a következő hivatkozásokat (válassza a Tallózás **szakaszt,** majd válassza a Tallózás **lehetőséget):**

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Ha nincs telepítve a 10.0.18362.0, használja a legújabb verziót. 

1. Kattintson a jobb gombbal a projektre a Megoldáskezelő **válassza a Meglévő elem** hozzáadása  >  **lehetőséget.**

1. Keresse meg a C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 fájlt, és módosítsa a szűrőt a **Következőre: Minden fájl ( \* . \* ).**.

1. Jelölje ki a SirepClient.dll és a SshClient.dll, majd válassza a **Hozzáadás lehetőséget.**

1. Keresse meg és válassza ki a Megoldáskezelő mindkét fájlt (a fájlok listájának  alján kell lennie), és módosítsa a Másolás kimeneti könyvtárba lehetőséget a **Tulajdonságok** ablakban a Mindig másolás **lehetőségre.**

1. A fájl tetején adja hozzá a következőt a meglévő utasítások `using` listájához:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. A `static void Main(...)` alkalmazáson belül adja hozzá a következő kódot:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Válassza **a Build** Solution  >  **(Megoldás összeállítása) lehetőséget.**

1. Nyisson meg egy parancssori ablakot, és cd-vel nyissa meg a lefordított .exe-fájlt tartalmazó mappát (például C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Futtassa a végrehajtható fájlt, és adja meg az eszköz IP-címét parancssori argumentumként. (Ha USB-kapcsolattal csatlakozik, használhatja a 127.0.0.1-es portot, ellenkező esetben pedig az eszköz Wi-Fi IP-címét.)  Például: "HoloLensDeploymentFix 127.0.0.1".

1. Miután az eszköz üzenetek nélkül kilépt (ez csak néhány másodpercet fog igénybe venni), a 2017-es vagy újabb Visual Studio üzembe helyezheti és hibakeresést végezni.  Az eszköz további használata nem szükséges.

Amint elérhetővé válnak, további frissítéseket is biztosítanak.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problémák a Microsoft Store és alkalmazások HoloLensen való elindításával kapcsolatban

> [!NOTE]
> Utolsó frissítés: 04/2 @ 10:00 – A probléma megoldva.

Problémákat tapasztalhat, amikor megpróbálja elindítani a Microsoft Store és alkalmazásokat a HoloLensen. Megállapítottuk, hogy a probléma akkor fordul elő, ha a háttéralkalmazás frissítései a keretrendszercsomagok újabb verzióját telepítik adott sorrendben, miközben egy vagy több függő alkalmazásuk még mindig fut. Ebben az esetben az automatikus alkalmazásfrissítés a .NET Native Framework új verzióját (10.0.25531-es verzió 10.0.27413-as verzió) miatt a futó alkalmazások nem megfelelően frissülnek a keretrendszer korábbi verzióját fogyasztó összes futó alkalmazás esetében.  A keretrendszer frissítésének folyamata a következő:

1. A rendszer letölti az új keretrendszercsomagot az áruházból, és telepíti.

1. Minden alkalmazás régebbi keretrendszer "frissítve" lett az újabb verzió használatára.

Ha a 2. lépés megszakad a befejezés előtt, akkor azok az alkalmazások, amelyekhez az újabb keretrendszer nincs regisztrálva, nem fognak elindulni a Start menüből.  Úgy véljük, hogy a Probléma bármelyik HoloLens-alkalmazást érintheti.

Egyes felhasználók arról jelentették, hogy a lefagyott alkalmazások bezárása és más alkalmazások ( például Visszajelzési központ, 3D-megjelenítő vagy Photos) indítása megoldja a problémát számukra – ez azonban az idő 100%-ában nem működik.

Kiváltó okunk az, hogy a problémát nem maga a frissítés okozta, hanem az operációs rendszer egy olyan problémája, amely miatt a .NET Native-keretrendszer frissítése helytelenül lett kezelve. Örömmel jelentjük be, hogy azonosítottunk egy javítást, és közzétettük a javítást tartalmazó frissítést (az operációs rendszer 17763.380-as verziója).  

Annak megnézni, hogy az eszköz képes-e a frissítésre:

1. Nyissa meg a Beállítások alkalmazást, és nyissa meg **az Update & Security alkalmazást.**

1. Válassza **a Frissítések keresése lehetőséget.**

1. Ha elérhető a 17763.380-as verzióra való frissítés, frissítsen erre a buildre, hogy megkapja az alkalmazás lefagyó hibajavítását.

1. Az operációs rendszer ezen verziójára való frissítéskor az alkalmazásoknak a várt módon kell működnie.

Emellett, ahogy minden HoloLens operációsrendszer-kiadás esetén, az FFU-rendszerképet is közzétettük a [Microsoft letöltőközpontjában.](https://aka.ms/hololensdownload/10.0.17763.380)

Ha nem szeretné frissíteni a frissítést, az UWP-alkalmazás 3/29-es Microsoft Store új verzióját adták ki. Miután frissítette az Áruház frissített verzióját:

1. Nyissa meg az Áruházat, és ellenőrizze, hogy betöltődik-e.
1. A bloom kézmozdulattal nyissa meg a menüt.
1. Próbálja meg megnyitni a korábban hibás alkalmazásokat.
1. Ha továbbra sem indítható el, koppintson és tartsa lenyomva a hibás alkalmazás ikonját, és válassza az eltávolítás lehetőséget.
1. Telepítse újra ezeket az alkalmazásokat az áruházból.

Ha az eszköz továbbra sem tud alkalmazásokat betölteni, a letöltőközponton keresztül a következő lépésekkel töltheti be a .NET Native Framework és a Runtime egy verzióját:

1. Töltse le [ezt a zip-fájlt](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) a Microsoft letöltőközpontból. A kicsomagolás két fájlt hoz létre.  Microsoft .NET.Native.Runtime.1.7.appx és Microsoft .NET.Native.Framework.1.7.appx.

1. Ellenőrizze, hogy az eszköz fel van-e oldva a fejlesztéshez.  Ha ezt még nem tette meg, tekintse meg a Using the Windows eszközportál for instructions [(A](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) Windows eszközportál használata) útmutatót.

1. Ezután be szeretne szerezni a Windows eszközportál. Javasoljuk, hogy ezt USB-kapcsolaton keresztül tegye meg, és ezt a böngészőben http://127.0.0.1:10080 gépelje be.

1. A Windows eszközportál után "be kell töltenie" a letöltött két fájlt. Ezt a bal oldali sávon kell megtennie, amíg el nem jut az **Alkalmazások szakaszhoz,** és válassza az **Alkalmazások lehetőséget.**

1. Ekkor az alábbihoz hasonló képernyő jelenik meg.  Lépjen az Install **App** (Alkalmazás telepítése) szakaszra, és keresse meg a két APPX-fájl kibontott helyét. Egyszerre csak egyet tud megtenni, ezért miután kiválasztotta az elsőt, kattintson az "Ugrás" gombra az Üzembe helyezés szakaszban. Ezután tegye ezt a második APPX-fájlhoz.

   ![Windows eszközportál telepítése Side-Loaded alkalmazásba](images/20190322-DevicePortal.png)
   
1. Ezen a ponton úgy véljük, hogy az alkalmazásoknak újra kell kezdeniük a munkát, és hogy az Áruházat is el tudja látni.

1. Bizonyos esetekben az érintett alkalmazások indítása előtt futtatni kell a 3D-megjelenítő elindításának további lépését. 

Nagyra értékeljük türelmét, mivel végigmentünk a probléma megoldásának folyamatán, és várjuk, hogy továbbra is együtt dolgozunk a közösséggel a sikeres Mixed Reality érdekében.

### <a name="device-update"></a>Eszközfrissítés

- 30 másodperccel az új frissítés után a rendszerhéj egyszer eltűnik. A munkamenet **folytatásához hajtsa** végre a Bloom-kézmozdulatot.

### <a name="visual-studio"></a>Visual Studio

- Lásd: Install [the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most-to-date version of Visual Studio that is recommended for HoloLens development (A holoLens-fejlesztéshez ajánlott eszközök telepítése).

- Amikor alkalmazást helyez üzembe a Visual Studio HoloLensben, a következő hibaüzenet jelenhet meg: A kért művelet nem hajtható végre olyan fájlon, amely megnyitja a felhasználó által leképezett **szakaszt. (Kivétel HRESULT-ból: 0x800704C8)**. Ha ez történik, próbálkozzon újra, és az üzembe helyezés általában sikeres lesz.

### <a name="api"></a>API

- Ha az alkalmazás [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) a felhasználó mögött állítja be a fókuszpontot vagy a camera.forward normál módon, a hologramok nem jelennek meg a Vegyes valóság rögzítése vagy videókban. Amíg ez a hiba nincs kijavítva [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) a Windowsban, ha az alkalmazások aktívan beállítják a fókuszpontot, meg kell győződni arról, hogy a sík normál értéke a kamera ellentétes irányában van beállítva (például normal = -camera.forward).

### <a name="xbox-wireless-controller"></a>Xbox vezeték nélküli vezérlő

- Az S Xbox vezeték nélküli vezérlőt frissíteni kell, mielőtt a HoloLens-sel használható lenne. Győződjön meg [arról, hogy naprakész,](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) mielőtt a vezérlőt egy HoloLens-sel próbál párosítani.

- Ha az Xbox vezeték nélküli vezérlő csatlakoztatva van, amikor újraindítja a HoloLenst, a vezérlő nem fog automatikusan újracsatlakozni a HoloLenshez. Az Útmutató gomb fénye lassan villog, amíg a vezérlő 3 perc után kikapcsol. Ha azonnal újra csatlakoztatnia kell a vezérlőt, a világítás kikapcsolásáig tartsa lenyomva az Útmutató gombot. Amikor újra bekapcsolja a vezérlőt, az újrakapcsolódik a HoloLenshez.

- Ha a HoloLens készenléti állapotba lép az Xbox vezeték nélküli vezérlő csatlakoztatva van, a vezérlő minden bemenete felébreszti a HoloLenst. Ezt úgy előzheti meg, ha kikapcsolja a vezérlőt, amikor már nem használja.

## <a name="known-issues-for-hololens-emulator"></a>A HoloLens Emulator ismert problémái

- Nem minden alkalmazás kompatibilis Microsoft Store az emulátorral. A Young Conker és a Fragments például nem lejátszható az emulátoron.
- Az emulátorban nem használhatja a PC-s webkamerát.
- A szolgáltatás Live Preview Windows eszközportál nem működik az emulátorral. Továbbra is rögzíthet Mixed Reality és képeket.
