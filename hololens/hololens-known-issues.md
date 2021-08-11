---
title: A HoloLens (1. generációs) ismert problémái
description: Maradjon naprakész az ismert problémák és megkerülő megoldások listájával, amelyek hatással lehetnek HoloLens Unityt és a Windows Eszközportál.
keywords: hibaelhárítás, ismert probléma, súgó
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: d2a8ae420a0c1d646625fe81b166e2daae07e44652b70f2e4a1b19ccba240cfb
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663938"
---
# <a name="known-issues-for-hololens-1st-gen"></a>A HoloLens (1. generációs) ismert problémái

Az alábbi lista az összes eszköz ismert HoloLens sorolja fel. Először ellenőrizze, hogy szokatlan viselkedést lát-e. A lista az új problémák felderített vagy jelentett, illetve a szoftverfrissítések későbbi HoloLens során folyamatosan frissül.

>[!NOTE]
> - Ha olyan problémát tapasztal, amely nem akadályozza, jelentse azt a HoloLens eszközén a [Visszajelzési központ.](hololens-feedback.md)
> - Ha a problémája blokkolja, a visszajelzés küldése mellett kérjük, nyújtsa be [a támogatási kérést.](https://aka.ms/hlsupport)


- [Az összes HoloLens ismert problémái](#known-issues-for-all-hololens-generations)
- [A HoloLens (1. generációs) ismert problémái](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>Az összes HoloLens ismert problémái

### <a name="unity"></a>Unity

- Lásd: [Install the tools](/windows/mixed-reality/install-the-tools) for the most-to-date version of Unity recommended for HoloLens development (A Unity legújabb verziójának telepítése a HoloLens érdekében.
- A Unity és a Technical Preview HoloLens ismert problémáit az HoloLens [Unity fórumain találhatja.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Windows Eszközportál

- A Rögzítés funkció Live Preview Mixed Reality néhány másodpercnyi késést is mutathat.

- A Virtuális bemenet lapon a Virtuális kézmozdulatok szakasz Kézmozdulatok és Görgetés vezérlői nem működnek. A használatuknak nincs hatása. A virtuális beviteli oldalon található virtuális billentyűzet megfelelően működik.

- A fejlesztői mód Gépház után néhány másodpercet is igénybe vehet, amíg a kapcsoló bekapcsolja a Eszközportál beállítást.

### <a name="onedrive-camera-upload"></a>OneDrive feltöltése

A OneDrive alkalmazás HoloLens támogatja a munkahelyi vagy iskolai fiókok automatikus kamerafeltöltését.

Workarounds:

- Ha a vállalata számára is elérhető, a fogyasztói Microsoft-fiókok támogatják az automatikus kamerafeltöltést. A munkahelyi vagy iskolai Microsoft-fiók (a OneDrive alkalmazás támogatja a kettős bejelentkezést) mellett a fiókba is bejelentkezhet. Az alkalmazás Microsoft-fiók profilból OneDrive automatikus, háttérkamerás kameratekercs-feltöltést is engedélyezhet.

- Ha nem tud biztonságosan használni fogyasztói Microsoft-fiók a fényképek automatikus feltöltéséhez, manuálisan feltölthet fényképeket a munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásból. Győződjön meg arról, hogy be van jelentkezve munkahelyi vagy iskolai fiókjába a OneDrive alkalmazásban. Kattintson a **+** gombra, majd válassza a **Feltöltés lehetőséget.** Keresse meg a feltölteni kívánt fényképeket vagy videókat a **Pictures (Képek) > Camera Roll (Kameragörgetés) kiválasztásával.** Válassza ki a feltölteni kívánt fényképeket vagy videókat, majd kattintson a **Megnyitás gombra.**

## <a name="known-issues-for-hololens-1st-gen"></a>A HoloLens (1. generációs) ismert problémái

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Nem lehet csatlakozni és üzembe helyezni HoloLens Visual Studio

> [!NOTE]
> Utolsó frissítés: 2019. 08. 08. 11: 17:11 – Visual Studio megjelent a VS 2019 16.2-es verziója, amely tartalmaz egy javítást a problémára. Javasoljuk, hogy a hiba elkerülése érdekében frissítsen erre a legújabb verzióra.

Visual Studio VS 2019 16.2-es verziója jelent meg, amely a probléma megoldását is tartalmazza. Javasoljuk, hogy a hiba elkerülése érdekében frissítsen erre a legújabb verzióra.

A probléma kiváltó oka: Azok a felhasználók, akik Visual Studio 2015 vagy a 2017-es Visual Studio korai verzióit használták alkalmazások telepítésére és hibakeresésére a HoloLens-Visual Studio 2017-es vagy Visual Studio 2019-es verziójának legújabb verzióiban, ugyanazokkal az HoloLens-val. A Visual Studio újabb verziói egy összetevő új verzióját telepítik, de a régebbi verzió fájljai az eszközön maradnak, ami az újabb verzió meghiúsulását okozza.  Ez a következő hibaüzenetet váltja ki: DEP0100: Győződjön meg arról, hogy a céleszközön engedélyezve van a fejlesztői mód. Hiba miatt nem sikerült fejlesztői licencet beszerezni a \<ip\> 80004005.

#### <a name="workaround"></a>Áthidaló megoldás

Csapatunk jelenleg dolgozik a javításon. Addig is a következő lépésekkel megoldhatja a problémát, és feloldhatja az üzembe helyezés és a hibakeresés blokkolását:  

1. Nyissa meg a Visual Studiót.

1. Válassza **a File** New  >    >  **Project** lehetőséget.

1. Válassza **a Visual C#**  >  **Windows Asztali**  >  **konzolalkalmazás (.NET-keretrendszer) lehetőséget.**

1. Nevezze el a projektet (például "HoloLensDeploymentFix"), és győződjön meg arról, hogy a keretrendszer legalább .NET-keretrendszer 4.5-ös, majd kattintson az **OK gombra.**

1. Kattintson a jobb gombbal a hivatkozások **csomópontra** a Megoldáskezelő és adja hozzá a következő hivatkozásokat (válassza a Tallózás **szakaszt,** majd válassza a Tallózás **lehetőséget):**

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Ha nincs telepítve a 10.0.18362.0, használja a legújabb verziót.

1. Kattintson a jobb gombbal a projektre a Megoldáskezelő válassza a **Meglévő elem** hozzáadása  >  **lehetőséget.**

1. Keresse meg a C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 fájlt, és módosítsa a szűrőt a **Következőre: Minden fájl ( \* . \* ).**

1. Jelölje ki a SirepClient.dll és a SshClient.dll, majd válassza a **Hozzáadás lehetőséget.**

1. Keresse meg és válassza ki a Megoldáskezelő mindkét fájlt (a fájlok listájának  alján kell lennie), és módosítsa a Másolás kimeneti könyvtárba a **Tulajdonságok** ablakban a Mindig másolás **lehetőségre.**

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

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problémák a Microsoft Store és alkalmazások a HoloLens

> [!NOTE]
> Utolsó frissítés: 04/2 @ 10:00 – A probléma megoldva.

Problémákat tapasztalhat, amikor megpróbálja elindítani a Microsoft Store és alkalmazásokat a HoloLens. Megállapítottuk, hogy a probléma akkor fordul elő, ha a háttéralkalmazás frissítései a keretrendszercsomagok újabb verzióját telepítik adott sorrendben, miközben egy vagy több függő alkalmazásuk még mindig fut. Ebben az esetben az automatikus alkalmazásfrissítés a .NET Native Framework új verzióját (10.0.25531–10.0.27413) hozta létre, ami miatt a futó alkalmazások nem frissülnek megfelelően a keretrendszer korábbi verzióját fogyasztó összes futó alkalmazás esetében.  A keretrendszer frissítésének folyamata a következő:

1. A rendszer letölti az új keretrendszercsomagot az áruházból, és telepíti.

1. Minden alkalmazás régebbi keretrendszer "frissítve" lett az újabb verzió használatára.

Ha a 2. lépés megszakad a befejezés előtt, akkor azok az alkalmazások, amelyekhez az újabb keretrendszer nincs regisztrálva, nem fognak elindulni a Start menüből.  Úgy véljük, hogy a HoloLens bármelyik alkalmazást érintheti ez a probléma.

Egyes felhasználók arról jelentették, hogy a lefagyott alkalmazások bezárása és más alkalmazások ( például Visszajelzési központ, 3D-megjelenítő vagy Photos) indítása megoldja a problémát számukra – ez azonban az idő 100%-ában nem működik.

Kiváltó okunk az, hogy a problémát nem maga a frissítés okozta, hanem az operációs rendszer egy olyan problémája, amely miatt a .NET Native-keretrendszer frissítése helytelenül lett kezelve. Örömmel jelentjük be, hogy azonosítottunk egy javítást, és közzétettük a javítást tartalmazó frissítést (az operációs rendszer 17763.380-as verziója).  

Annak megnézni, hogy az eszköz képes-e a frissítésre:

1. Nyissa meg a Gépház alkalmazást, és nyissa meg **az Update & Security alkalmazást.**

1. Válassza **a Frissítések keresése lehetőséget.**

1. Ha elérhető a 17763.380-as verzióra való frissítés, frissítsen erre a buildre, hogy megkapja az alkalmazás lefagyó hibajavítását.

1. Az operációs rendszer ezen verziójára való frissítéskor az alkalmazásoknak a várt módon kell működnie.

Továbbá, ahogy az operációs rendszer minden kiadásával HoloLens, az FFU-rendszerképet is közzétettük a [Microsoft letöltőközpontjában.](https://aka.ms/hololensdownload/10.0.17763.380)

Ha nem szeretné frissíteni a frissítést, a 3/29-es Microsoft Store az UWP-alkalmazás új verzióját adták ki. Miután frissítette az Áruház frissített verzióját:

1. Nyissa meg az Áruházat, és ellenőrizze, hogy betöltődik-e.
1. A bloom kézmozdulattal nyissa meg a menüt.
1. Próbálja meg megnyitni a korábban hibás alkalmazásokat.
1. Ha továbbra sem indítható el, koppintson és tartsa lenyomva a hibás alkalmazás ikonját, és válassza az eltávolítás lehetőséget.
1. Telepítse újra ezeket az alkalmazásokat az áruházból.

Ha az eszköz továbbra sem tud alkalmazásokat betölteni, a letöltőközponton keresztül a következő lépésekkel töltheti be a .NET Native Framework és a Runtime egy verzióját:

1. Töltse le [ezt a zip-fájlt](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) a Microsoft letöltőközpontból. A kicsomagolás két fájlt hoz létre.  Microsoft .NET.Native.Runtime.1.7.appx és Microsoft .NET.Native.Framework.1.7.appx.

1. Ellenőrizze, hogy az eszköz fel van-e oldva a fejlesztéshez.  Ha ezt még nem tette meg, tekintse meg a Using the Windows Eszközportál for instructions [(A](/windows/mixed-reality/using-the-windows-device-portal) Windows Eszközportál használata) útmutatót.

1. Ezután a következőbe szeretne Windows Eszközportál. Javasoljuk, hogy ezt USB-kapcsolaton keresztül tegye meg, és ezt a böngészőben http://127.0.0.1:10080 gépelje be.

1. A Windows Eszközportál után "be kell töltenie" a letöltött két fájlt. Ezt a bal oldali sávon kell megtennie, amíg el nem jut az **Alkalmazások szakaszhoz,** és válassza az Alkalmazások **lehetőséget.**

1. Ekkor az alábbihoz hasonló képernyő jelenik meg.  Lépjen az Install **App** (Alkalmazás telepítése) szakaszra, és keresse meg a két APPX-fájl kibontott helyét. Egyszerre csak egyet tud megtenni, ezért miután kiválasztotta az elsőt, kattintson az Üzembe helyezés szakasz "Ugrás" gombjára. Ezután tegye meg ezt a második APPX-fájlhoz.

   ![Windows Eszközportál alkalmazás Side-Loaded telepítése](images/20190322-DevicePortal.png)

1. Úgy véljük, hogy ezen a ponton az alkalmazásoknak újra kell kezdeniük a munkát, és hogy a Store-t is el tudja látni.

1. Bizonyos esetekben az érintett alkalmazások indítása előtt le kell futtatni a 3D-megjelenítő elindításának további lépését.

Nagyra értékeljük türelmét, mivel végigmentünk a probléma megoldásának folyamatán, és várjuk, hogy továbbra is együtt dolgozunk a közösséggel a sikeres és sikeres Mixed Reality érdekében.

### <a name="device-update"></a>Eszközfrissítés

- Egy új frissítés után 30 másodperccel a rendszerhéj egyszer eltűnik. A munkamenet **folytatásához hajtsa** végre a Bloom-kézmozdulatot.

### <a name="visual-studio"></a>Visual Studio

- Lásd: [A](/windows/mixed-reality/install-the-tools) Visual Studio legújabb verziójának eszközeinek telepítése HoloLens használata.

- Amikor alkalmazást telepít egy Visual Studio-HoloLens, a következő hibaüzenet jelenhet meg: A kért művelet nem hajtható végre olyan fájlon, amely megnyit egy felhasználó által leképezett **szakaszt. (Kivétel HRESULT-ból: 0x800704C8)**. Ha ez történik, próbálkozzon újra, és az üzembe helyezés általában sikeres lesz.

### <a name="api"></a>API

- Ha az alkalmazás [](/windows/mixed-reality/focus-point-in-unity) beállítja a fókuszpontot a felhasználó mögött, vagy a szokásos kamera-továbbítást, a hologramok nem jelennek meg Vegyes valóság rögzítése fényképeken vagy videókban. Amíg ez a hiba nincs kijavítva a Windows, ha az alkalmazások aktívan beállítják a fókuszpontot, meg kell győződni arról, hogy a sík normál értéke a kamera ellenkező irányában van beállítva (például normal = -camera.forward). [](/windows/mixed-reality/focus-point-in-unity)

### <a name="xbox-wireless-controller"></a>Xbox vezeték nélküli vezérlő

- Az Xbox Vezeték nélküli vezérlő S eszközét frissíteni kell, mielőtt a HoloLens. Győződjön meg arról, [hogy naprakész,](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) mielőtt a vezérlőt egy új vezérlővel HoloLens.

- Ha az Xbox vezeték nélküli HoloLens közben újraindítja a rendszert, a vezérlő nem fog automatikusan újracsatlakozni a HoloLens. Az Útmutató gomb fénye lassan villog, amíg a vezérlő 3 perc után ki nem indul. Ha azonnal újra csatlakoztatnia kell a vezérlőt, kikapcsolja a vezérlőt úgy, hogy az Útmutató gombot addig tartja, amíg a világítás ki nem vált. Amikor újra bekapcsolja a vezérlőt, az újracsatlakozik a HoloLens.

- Ha a HoloLens készenléti állapotba lép, miközben az Xbox vezeték nélküli vezérlő csatlakoztatva van, a vezérlő minden bemenete felébreszti a HoloLens. Ezt úgy előzheti meg, ha kikapcsolja a vezérlőt, amikor már nem használja.

