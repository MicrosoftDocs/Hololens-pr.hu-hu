---
title: Belső előzetes verzió a Microsoft HoloLens
description: Ismerje meg az Insider-buildek első lépéseit, és adjon értékes visszajelzést az operációs rendszer következő jelentős frissítésével kapcsolatban a HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: e8adb2f796299c99a9152a5b245e8bdd0b768f05
ms.sourcegitcommit: 78e5f26014e55c13fee9c2b75a80810fd2e77877
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/31/2021
ms.locfileid: "115009340"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Belső előzetes verzió a Microsoft HoloLens

Üdvözöljük az Insider előzetes verziójának legújabb buildjeiben HoloLens! Az első lépések [egyszerűek,](hololens-insider.md#start-receiving-insider-builds) és értékes visszajelzést adhatunk az operációs rendszer következő jelentős frissítésével kapcsolatban a HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Belső kibocsátási megjegyzések

Izgatottan várjuk, hogy új funkciókat Windows Insidersbe. Az új buildek a fejlesztői és a bétaverziós csatornákon lesznek elérhetőek a legújabb frissítésekért. Ezt az oldalt folyamatosan frissítjük, ahogy további funkciókat és frissítéseket adunk hozzá a Windows Insider buildjeinkhez. Legyen izgatott, és készen áll arra, hogy ezeket a frissítéseket a valóságba keverje.

| Szolgáltatás                 | Leírás                | Felhasználó vagy forgatókönyv | Build bevezetve |
|-------------------------|----------------------------|--------------|------------------|
| [CSP-módosítások a jelentéskészítési HoloLens részleteihez](#csp-changes-for-reporting-hololens-details) | Új CSP-k az adatok lekérdezéséhez | It-rendszergazdák    | 20348.1403                 |
| [CSP által vezérelt automatikus bejelentkezési szabályzat](#auto-login-policy-controlled-by-csp) | Fiók automatikus bejelentkezéshez használatos | It-rendszergazdák | 20348.1405 |
| [PFX-fájltámogatás a Tanúsítványkezelőhöz](#pfx-file-support-for-certificate-manager) | PFX-tanúsítványok hozzáadása Gépház felhasználói felületen | Végfelhasználó | 20348.1405 |
| [Speciális diagnosztikai jelentés megtekintése a Gépház a HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | MDM diagnosztikai naplók megtekintése az eszközön | Hibaelhárítás | 20348.1405 |
| [Offline diagnosztikai értesítések](#offline-diagnostics-notifications) | Visszajelzés a naplógyűjtéssel kapcsolatban | Hibaelhárítás | 20348.1405 |
| [Csak privát áruházbeli alkalmazásokat használjon csak Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Az áruházbeli alkalmazás konfigurálása úgy, hogy csak a szervezettől származó alkalmazásokat mutassa | Rendszergazdai | 20348.1408 |
| [Az alacsony tárterületű naplógyűjtés fejlesztései](#low-storage-log-collection-improvements) | A naplógyűjtési forgatókönyvek fejlesztései alacsony tárolási helyzetekben. | Rendszergazdai | 20348.1412 |
| [Javítások és fejlesztések](hololens-insider.md#fixes-and-improvements) | Javítások és fejlesztések a HoloLens. | Mind | 20348.1411 |

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-módosítások a jelentéskészítési HoloLens részleteihez

- A Windows 20348.1403-as buildben vezettük be

Az alábbi CSP-k új módszereket kínálnak a jelentések jelentésére a HoloLens eszközeiről.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP – Ingyenes Storage

A DevDetail CSP mostantól a szabad tárterületet is jelenti HoloLens eszközön. Ennek nagyjából meg kell egyeznie az alkalmazás Gépház lapján látható Storage értékkel. Az alábbiakban az ezt az információt tartalmazó csomópont található.

- ./DevDetail/Ext/Microsoft/FreeStorage (csak GET művelet)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP – SSID és BSSID

A DeviceStatus CSP mostantól azon hálózati SSID és BSSID Wi-Fi is jelenti, amelyhez a HoloLens csatlakozik. A következő csomópontok tartalmazzák ezt az információt.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-cím* Wi-Fi /SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID

Példa syncml blobra (MDM-szállítók számára) a NetworkIdentifiers lekérdezéséhez

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>CSP által vezérelt automatikus bejelentkezési szabályzat

Ez az új AutoLogonUser szabályzat szabályozza, hogy a rendszer automatikusan bejelentkeztet-e egy felhasználót. Egyes ügyfelek olyan eszközöket is beállítanának, amelyek egy identitáshoz kötődnek, de nem szeretnék, ha bármilyen bejelentkezési élményre lenne lehetőség. Imagine eszköz felvétele és azonnali használata a remote assist használatával. Vagy az is előnyös, ha gyorsan el tudja terjeszteni a HoloLens, és lehetővé teszi a végfelhasználók számára a bejelentkezés gyorsítását.

Ha a szabályzat nem üres értékre van állítva, megadja az automatikus bejelentkezési felhasználó e-mail-címét. Az automatikus bejelentkezés engedélyezéséhez a megadott felhasználónak legalább egyszer be kell jelentkeznie az eszközre.

Az új szabályzat sztringértékének `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` OMA-URI-ját

- Az azonos e-mail-címmel rendelkező felhasználónál engedélyezve lesz az automatikus bejelentkezés.

Egy olyan eszközön, ahol ez a szabályzat konfigurálva van, a szabályzatban megadott felhasználónak legalább egyszer be kell jelentkeznie. Az eszköz az első bejelentkezést követő újraindítása után automatikusan bejelentkezik a megadott felhasználóra. Csak egyetlen automatikus bejelentkezési felhasználó támogatott. Ha engedélyezve van, az automatikusan bejelentkezett felhasználó nem fog tudni manuálisan kijelentkezni. Ha egy másik felhasználóval jelentkezik be, először le kell tiltani a szabályzatot.

> [!NOTE]
> - Egyes események, például a fő operációsrendszer-frissítések miatt előfordulhat, hogy a megadott felhasználónak újra be kell jelentkeznie az eszközre az automatikus bejelentkezés folytatásához. 
> - Az automatikus bejelentkezés csak MSA- és AAD-felhasználók számára támogatott.

### <a name="pfx-file-support-for-certificate-manager"></a>PFX-fájltámogatás a Tanúsítványkezelőhöz

Az Insider Windows 20348.1405-ös buildben vezettük be. Mostantól támogatott a Tanúsítványkezelő a .pfx-tanúsítványok használatára. [](certificate-manager.md) Amikor a felhasználók a **Biztonsági tanúsítványok frissítése Gépház** lapra &, és kiválasztják a Tanúsítvány telepítése lehetőséget, a felhasználói felület mostantól támogatja  >    >   **a** .pfx tanúsítványfájlt.
A felhasználók titkos kulccsal .pfx-tanúsítványt importálnak a felhasználói tárolóba vagy a számítógép tárolóba.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Speciális diagnosztikai jelentés megtekintése a Gépház a HoloLens

A felügyelt eszközök esetében a viselkedés hibaelhárítása során fontos lépés annak ellenőrzése, hogy a várt házirend-konfiguráció van-e alkalmazva. Korábban ezt az új funkciót az MDM-en keresztül vagy az eszköz közelében kellett volna, az **Gépház** Accounts Access munkahelyi vagy iskolai fiókkal összegyűjtött diagnosztikai naplók exportálása után, majd a Felügyeleti naplók exportálása és megtekintése egy közeli számítógépen lehetőség  ->    >  kiválasztásával. 

Az MDM-diagnosztika mostantól megtekinthető az eszközön az Edge böngésző használatával. Ha könnyebben meg szeretne tekinteni egy MDM diagnosztikai jelentést, lépjen a Hozzáférés munkahelyi vagy iskolai alkalmazáshoz lapra, és válassza a **Speciális diagnosztikai jelentés megtekintése lehetőséget.** Ez létrehozza és megnyitja a jelentést egy új Edge-ablakban.

![Tekintse meg a speciális diagnosztikai jelentést Gépház alkalmazásban.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Offline diagnosztikai értesítések

Ez egy offline diagnosztika nevű meglévő [szolgáltatás frissítése.](hololens-diagnostic-logs.md#offline-diagnostics) Korábban nem volt egyértelmű jelzés a felhasználók számára a diagnosztikai gyűjtés aktiválására vagy befejezésére.
Az Insider Windows buildek két módon adhatják hozzá a visszajelzéseket az Offline Diagnosticshoz. Az első a bejelentések értesítései, amelyek a gyűjtemény indításakor és befejezésekor is megjelennek. Ezek akkor jelennek meg, ha a felhasználó bejelentkezett, és rendelkezik vizualizációval.

![Bejelentés a naplók gyűjtéséhez.](./images/logcollection1.jpg)

![Bejelentés a naplógyűjtés befejezésekor.](./images/logcollection2.jpg)
 
Mivel a felhasználók gyakran használják tartalék naplógyűjtési mechanizmusként az Offline diagnosztikát, amikor nem férnek hozzá a kijelzőkhez, nem tudnak bejelentkezni vagy még mindig az OOBE-ban vannak, a naplók gyűjtésekor hangjel is megjelenik. A bejelentési értesítés mellett ez a hang is megjelenik.

Ez az új funkció az eszköz frissítésekekor lesz engedélyezve, és nem szükséges engedélyezni vagy kezelni. Ha az új visszajelzés nem jelenik meg vagy nem hallható, az Offline diagnosztika továbbra is létrejön.

Reméljük, hogy a visszajelzések újabb kiegészítésével könnyebb diagnosztikai adatokat gyűjteni, és gyorsabban elhárítani a problémákat.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Csak privát áruházbeli alkalmazások használata Microsoft Store

A RequirePrivateStoreOnly szabályzat engedélyezve van a HoloLens. Ez a szabályzat lehetővé Microsoft Store, hogy az alkalmazás úgy legyen konfigurálva, hogy csak a szervezet számára konfigurált privát tárolót mutassa. A hozzáférés korlátozása csak az Ön által elérhetővé tett alkalmazásokra.

További információ az [ApplicationManagement/RequirePrivateStoreOnly-ről](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="low-storage-log-collection-improvements"></a>Az alacsony tárterületű naplógyűjtés fejlesztései

Az olyan forgatókönyvekben, ahol az eszköz a diagnosztikai naplók gyűjtésekor  kevés a lemezterület, létrejön egyStorageDiagnostics.zipnevű jelentés. Az alacsony tárterület küszöbértékét a rendszer Windows [határozza meg.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

### <a name="fixes-and-improvements"></a>Javítások és fejlesztések

- Kijavítottunk egy ismert hibát, Eszközportál amikor nem volt [rákérdezés zárolt fájlok letöltésére.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Kijavítottunk egy ismert hibát, amely Eszközportál és letöltés időkorrekta [miatt ki volt javítva.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- A megfelelőségi tulajdonságok jelentésével kapcsolatos problémák elhárítása HoloLens eszközökről; Előfordulhat, hogy újraindításra van szükség ahhoz, hogy a megfelelő jelentéskészítés aktiválódjon az Insider-buildek esetén.  
- Frissítettük a Remote Assist új flashre telepített beépített verzióját.

## <a name="start-receiving-insider-builds"></a>Insider-buildek fogadásának elkezde

> [!NOTE]
> Ha a közelmúltban nem frissített, indítsa újra az eszközt az állapot frissítéséhez, és szerezze be a legújabb buildet.
> - Az "Eszköz újraindítása" hangparancs jól működik. 
> - Az újraindítási gombot is választhatja a Gépház/Windows Insider Program.
>
> Előfordulhat, hogy egy hiba történt a háttéren, amely miatt ön is találkozhatott, így újra a útjára fog menni.

A 2. HoloLens eszközön válassza az **Update** Gépház Security &  >  **Windows Insider Program** get  >   started (Első **lépések) lehetőséget.** Csatolja a regisztrációhoz használt fiókot Windows Insiderben.

Windows belsős már áttért a Csatornákra. A **Gyors** kör lesz a **Fejlesztői** csatorna, a **Lassú** kör lesz a **Béta csatorna,** a Kiadási **előnézeti** kör pedig a Kiadás **előnézete csatorna** lesz. A leképezés így néz ki:

![Windows Belső csatornák magyarázata](images/WindowsInsiderChannels.png)

További információ: [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (A belső csatornák Windows blogok).
Ezután válassza az **Active development of Windows of Windows**( Aktív fejlesztés) lehetőséget, válassza ki, hogy szeretné-e fogadni a Dev **Channelt** vagy Béta csatorna **buildeket,** és tekintse át a program feltételeit.
A **befejezéshez válassza > Újraindítás most lehetőséget.** Miután az eszköz újraindult, Gépház > **Update & Security > Frissítések** keresése a legújabb build lehozáshoz lapra.

### <a name="update-error-0x80070490-work-around"></a>Hiba 0x80070490 hiba

Ha frissítési hibát 0x80070490 a Dev vagy a Beta csatornán való frissítéskor, próbálkozzon a következő rövid távú munkával. Ez magában foglalja a belső csatorna áthelyezését, a frissítés be- és áthelyezését, majd az Insider-csatorna vissza mozgatát.

#### <a name="stage-one---release-preview"></a>Első fázis – Előzetes kiadás

1.  Gépház a Biztonsági & frissítése, majd Windows Insider Program a Kiadási előzetes **csatorna lehetőséget.**

2.  Gépház, Update & Security, Windows Update, **Check for updates**. A frissítés után folytassa a második fázisra.

#### <a name="stage-two---dev-channel"></a>Második fázis – Fejlesztői csatorna

1. Gépház Update & Security (Biztonsági frissítés) Windows Insider Program, majd a **Dev Channel (Fejlesztői csatorna) lehetőséget.**

2. Gépház, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>FFU letöltési és flash utasítások

A flight signed ffu (FFU) teszteléséhez először fel kell oldania az eszköz zárolását, mielőtt felrakná a repülőjárat aláírt ffu-ját.

1. Pc-n:
    1. Töltse le a ffu-t a számítógépére a [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) ről.
    
    1. Telepítse az ARC-t (Advanced Recovery Companion) a Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. On HoloLens - Flight Unlock: **Open Gépház** Update & Security Windows Insider Program majd  >    >   regisztráljon, indítsa újra az eszközt.

1. Flash FFU – Most már az ARC használatával is meg flashlheti a repülőjárat aláírt FFU-ját.

### <a name="provide-feedback-and-report-issues"></a>Visszajelzés küldése és problémák jelentése

A [visszajelzések Visszajelzési központ és a](hololens-feedback.md) jelentésekkel kapcsolatos problémák HoloLens a saját alkalmazásában. A Visszajelzési központ biztosítja, hogy minden szükséges diagnosztikai információ bekerül a hibakeresésbe és a probléma megoldásához.  A kínai és a japán nyelvű HoloLens ugyanúgy kell jelenteni.

> [!NOTE]
> Mindenképpen fogadja el azt a kérdést, amely megkérdezi, hogy szeretné Visszajelzési központ szeretné-e elérni a Dokumentumok mappát (válassza az **Igen** lehetőséget, amikor a rendszer kéri).

## <a name="note-for-developers"></a>Megjegyzés fejlesztőknek

Nyugodtan kipróbálhatja az alkalmazások fejlesztését belső fejlesztésű belső HoloLens.  Az első [lépésekhez tekintse](https://developer.microsoft.com/windows/mixed-reality/development) HoloLens fejlesztői dokumentációját. Ugyanezek az utasítások az Insider-buildekkel is HoloLens.  Használhatja a Unity ugyanazon buildeket, Visual Studio a fejlesztéshez már HoloLens is.

## <a name="stop-receiving-insider-builds"></a>Insider-buildek fogadásának leállítása

Ha már nem szeretné megkapni az Windows Holographic Insider-buildjét, kikapcsolhatja, ha az HoloLens éles buildet futtat, vagy az Advanced Recovery Companion segítségével helyreállíthatja az eszközt az Windows Holographic nem insider verziójára. [](hololens-recovery.md)

> [!CAUTION]
> Megjelenik egy ismert probléma, amely miatt az Insider Preview buildre való regisztrációt manuálisan újratelepítő felhasználók kék képernyőt tapasztalnak. Ezt követően manuálisan kell helyreállítania az eszközt. Ha szeretne többet tudni arról, hogy ez hatással lenne-e az Ön számára, tekintse meg ezt az ismert [problémát.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Annak ellenőrzése, hogy a HoloLens futtat-e éles buildet:

1. Keresse meg **Gépház > System > About (Rendszer > about )** et, és keresse meg a build számát.

1. [Az éles buildszámokat a kibocsátási megjegyzésekben láthatja.](hololens-release-notes.md)

Az Insider-buildek lemondása:

1. Éles buildet HoloLens futtató környezetben válassza az Update **Gépház > Security &**(Frissítés & biztonsági > Windows Insider Program) lehetőséget, és válassza a Stop Insider builds (Belső buildek **leállítása) lehetőséget.**

1. Az eszköz lemondáshoz kövesse az utasításokat.
