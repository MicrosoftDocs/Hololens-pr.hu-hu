---
title: Windows Autopilot HoloLens 2-höz
description: Ismerje meg, hogyan állíthatja be, konfigurálhatja és háríthatja el az Autopilotot HoloLens 2 eszközön.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Robotpilóta
manager: jarrettr
ms.openlocfilehash: cc73f5cbb438119f4c626ae76db9c91373e19aff
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635364"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot HoloLens 2-höz

A Windows Holographic 2004-es verziójától kezdődően a HoloLens 2. [](/mem/autopilot/self-deploying) verziója támogatja az Windows Autopilot önkiszolgáló üzembe helyezési módját az Microsoft Intune-val (a harmadik féltől származó MDM-ek nem támogatottak). A rendszergazdák konfigurálhatják a használatra készült felhasználói élményt (OOBE) a Microsoft Endpoint Manager és lehetővé tehetik a végfelhasználók számára, hogy kis vagy semmilyen interakcióval előkészítsék az eszközöket az üzleti használatra. Ez csökkenti a leltárkezeléshez szükséges többletterhelést, az eszközök gyakorlati előkészítésének költségeit és az alkalmazottak támogatási hívásait a beállítási folyamat során. További információért olvassa el [Windows Autopilot dokumentációját.](/mem/autopilot/windows-autopilot)

A Surface-eszközökhöz hasonló ajánlott, hogy az ügyfelek a Microsoft [Felhőszolgáltató](https://partner.microsoft.com/cloud-solution-provider) (viszonteladó vagy terjesztő) segítségével regisztrálják az eszközöket az Autopilot szolgáltatásban a Partnerközpont. Az eszközregisztráció egyéb módjai az Eszköz hozzáadása dokumentációban vannak ismertetve, bár a Microsoft csatornapartnerei biztosítják a leghatékonyabb teljes útvonalat. [](/mem/autopilot/add-devices)

> [!NOTE]
> A 2020. 01. 20-án a HoloLens-ben az AutoPilot Microsoft Endpoint Manager nyilvános előzetes verzióra **áll át.** Az ügyfeleknek már nem kell regisztrálni a privát előzetes verzióra, és minden bérlő be tudja majd állítva az Autopilotot a MEM felügyeleti központban.

Amikor egy felhasználó elindítja az AutoPilot önkiszolgáló üzembe helyezési folyamatát, az Autopilot a következő lépéseket teszi:

1. Az eszköz Azure Active Directory (Azure AD). Vegye figyelembe, hogy az Autopilot for HoloLens nem támogatja a Active Directory és a hibrid Azure AD-csatlakozást.

1. Az Azure AD használatával regisztrálja az eszközt a Microsoft Endpoint Manager (vagy egy másik MDM-szolgáltatásban).

1. Eszközre vonatkozó szabályzatok, tanúsítványok, hálózati profilok és alkalmazások letöltése és alkalmazása.

1. Az eszköz kiépítése.

1. A bejelentkezési képernyőt mutatja be a felhasználónak.

## <a name="configuring-autopilot-for-hololens-2"></a>Az Autopilot konfigurálása a 2. HoloLens számára

A környezet beállításhoz kövesse az alábbi lépéseket:

1. [Tekintse át az Autopilot Windows 2-es HoloLens követelményeit.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Automatikus MDM-regisztráció engedélyezése](#2-enable-automatic-mdm-enrollment)

1. [Eszközök regisztrálása Windows Autopilotban.](#3-register-devices-in-windows-autopilot)

1. [Eszközcsoport létrehozása.](#4-create-a-device-group)

1. [Hozzon létre egy telepítési profilt.](#5-create-a-deployment-profile)

1. [Ellenőrizze a Regisztrációs állapotlap (ESP) konfigurációját.](#6-verify-the-esp-configuration)

1. [Ellenőrizze a profil állapotát a HoloLens eszközökön.](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. A 2. Windows Autopilot követelményei HoloLens nek áttekintése

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Tekintse át a Windows Autopilot követelményeit ismertető cikk alábbi szakaszait:

- [A hálózatra vonatkozó követelmények](/mem/autopilot/networking-requirements)  
- [Licenckövetelmények](/mem/autopilot/licensing-requirements)  
- [Konfigurációs követelmények](/mem/autopilot/configuration-requirements)

**Tekintse át [a](/windows/deployment/windows-autopilot/self-deploying#requirements)Windows Autopilot Self-Deploying móddal kapcsolatos cikk "Követelmények" szakaszát.** A környezetnek meg kell felelnie ezeknek a követelményeknek, valamint a szabványos Windows Autopilot követelményeinek. Nem kell áttekintenünk a cikk "Lépésről lépésre" és "Ellenőrzés" szakaszát. A cikk későbbi cikkei a megfelelő lépéseket biztosítanak, amelyek a HoloLens.

További információ az eszközök regisztrálásának és a profilok konfigurálásának mikéntről: [2. Eszközök regisztrálása Windows Autopilotban](#3-register-devices-in-windows-autopilot) [és 4. Ebben a cikkben üzembe helyezési profilt](#5-create-a-deployment-profile) hozhat létre. Az Autopilot önkiszolgáló üzembe helyezési módú profiljainak konfigurálása és kezelése érdekében győződjön meg arról, hogy rendelkezik [hozzáféréssel Microsoft Endpoint Manager felügyeleti központhoz.](https://endpoint.microsoft.com)

#### <a name="review-hololens-os-requirements"></a>Tekintse át HoloLens operációs rendszer követelményeit:

- Az eszközöknek a [Holographic Windows 2004-es](hololens-release-notes.md#windows-holographic-version-2004) (19041.1103-as buildszám) vagy újabb verziójával kell lennie. Az eszközön található buildverzió megerősítéséhez vagy a legújabb operációs rendszer flash verziójának frissítéséhez használja az [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) eszközt és az eszköz újra flash [funkcióját.](/hololens/hololens-recovery#clean-reflash-the-device) Vegye figyelembe, hogy a 2020. szeptember végéig kézbesített eszközökre Windows Holographic 1903-as verziója van előre telepítve. Lépjen kapcsolatba a viszonteladóval, és győződjön meg arról, hogy az Autopilot-kompatibilis eszközöket ki szállítják Önnek.

- Windows A Holographic 2004-es verziója csak az Ethernet-kapcsolaton keresztüli Autopilotot támogatja. Mielőtt bekapcsolja HoloLens, győződjön meg arról, hogy a hálózati adapter csatlakoztatva van az Ethernethez egy "USB-C–Ethernet" **adapterrel.** Az eszköz rendszerindítása esetén nincs szükség felhasználói beavatkozásra. Ha egy Autopilot-bevezetést tervez számos HoloLens eszközön, javasoljuk, hogy tervezze meg az adapter-infrastruktúrát. Az USB Hubok nem ajánlottak, mivel gyakran további, külső gyártótól származó illesztőprogramok telepítését igénylik, amelyek nem támogatottak a HoloLens.

- [Windows Holographic 20H2](hololens-release-notes.md#windows-holographic-version-20h2) -es (19041.1128-as build) vagy újabb verziója támogatja az Autopilotot Wi-Fi-n keresztül, bár ethernet-adaptereket továbbra is használhat. A Wi-Fi-n keresztül csatlakoztatott eszközök esetében a felhasználónak csak a következőre van engedélye:

     - Végig kell mennie a jeleneten
     - Nyelv és területi beállítások kiválasztása
     - Szemkontraszt futtatása
     - Hálózati kapcsolat létrehozása

- Windows A Holographic 20H2-es verziója támogatja a [Tenantlockdown CSP-t](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)és az Autopilotot, amely zárolja az eszközt egy bérlőhöz, és biztosítja, hogy az eszköz a véletlen vagy szándékos alaphelyzetbe állítások vagy törlések esetén is az adott bérlőhöz kötődik.  

- Győződjön meg arról, hogy az eszközök még nem tagjai az Azure AD-nek, és nincsenek regisztrálva az Intune-ban (vagy más MDM-rendszerben). Az Autopilot önkiszolgáló üzembe helyezési folyamata ezeket a lépéseket is végreveszi. Annak érdekében, hogy az eszközzel kapcsolatos összes információ  el legyen ásva, tekintse meg az Eszközök lapot az Azure AD-portálon és az Intune-portálon is. Vegye figyelembe, hogy a "Minden megcélzott eszköz Autopilot-eszközre konvertálása" funkció jelenleg HoloLens nem támogatott.  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Az automatikus MDM-regisztráció engedélyezése:

Ahhoz, hogy az Autopilot sikeres legyen, engedélyeznie kell az automatikus MDM-regisztrációt a Azure Portal. Ez lehetővé teszi, hogy az eszköz felhasználó nélkül regisztráljon.

A [Azure Portal](https://portal.azure.com/#home) **válassza** Azure Active Directory  ->  **(MDM és MAM) Microsoft Intune.**  ->   Ezután konfigurálja az **MDM-felhasználói hatókört,** és válassza az Összes **lehetőséget.**

Tekintse át az alábbi rövid útmutatót az automatikus [](/mem/intune/enrollment/quickstart-setup-auto-enrollment) [MDM-regisztráció](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) engedélyezéséről vagy az automatikus regisztráció gyorsútműveleti útmutatóját, amely további információt tartalmaz a beállításról.

### <a name="3-register-devices-in-windows-autopilot"></a>3. Eszközök regisztrálása Windows Autopilotban

Az első telepítés előtt az eszközöket regisztrálni kell Windows Autopilotban. Az eszközregisztráció MEM-dokumentációját lásd: [Eszközök hozzáadása az Autopilothoz.](/mem/autopilot/add-devices)  

Az eszközök regisztrálásának három elsődleges HoloLens módja van:

 - **A viszonteladó regisztrálhat eszközöket a Partnerközpont rendeléskor.**

   > [!NOTE]  
   > Ez az ajánlott elérési út az eszközök AutoPilot-szolgáltatáshoz való hozzáadásához. [További információk](/mem/autopilot/partner-registration).  

 - **Támogatási [kérést küldhet közvetlenül a](hololens2-autopilot-registration-support.md) Microsoftnak.**
 - **Olvassa be a hardver kivonatát (más** néven hardverazonosítóját), és regisztrálja manuálisan az eszközt a MEM felügyeleti központban.

#### <a name="obtain-hardware-hash"></a>Hardver-kivonat beszerzése
A hardver-kivonat lekérésének két módja van.
1. Támogatási [kérést küldhet közvetlenül a](hololens2-autopilot-registration-support.md) Microsoftnak.
2. Lekérheti az eszközről. Az eszköz rögzíti a hardver kivonatát egy CSV-fájlban az OOBE folyamat során, vagy később, amikor az eszköz tulajdonosa elindítja a diagnosztikai naplók gyűjtésének folyamatát (lásd az alábbi eljárást). Általában az eszköz tulajdonosa az első felhasználó, aki bejelentkezik az eszközre.
     > [!WARNING]
     > A 20H2 előtti buildek esetén, ha már végigment az OOBE-ban, és a telemetria Kötelezőre lett állítva, ezzel a módszerrel nem gyűjthet hardver-kivonatot az Autopilothoz. Ha ezzel a módszerrel gyűjti össze a hardver-kivonatot, állítsa a Telemetria beállítást Teljesre a Gépház-alkalmazáson keresztül, majd válassza az Adatvédelmi -> diagnosztika lehetőséget.

    1. Indítsa el HoloLens 2-es eszközt.

    1. Az eszközön egyszerre nyomja le a **Power** and **Volume Down** (Bekapcsolás és lekötve) gombot, majd engedje el őket. Az eszköz összegyűjti a diagnosztikai naplókat és a hardver kivonatát, és egy .zip tárolja őket.

   1. Részletes információkért és egy tájékoztató videóért az előzetes formázásról olvassa el az [Offline diagnosztika szakaszt.](hololens-diagnostic-logs.md#offline-diagnostics)

    1. Usb-C kábellel csatlakoztassa az eszközt egy számítógéphez.

    1. A számítógépen nyissa meg a Fájlkezelő. Nyissa **meg a This PC Internal Storage Documents \\ \<*HoloLens device name*> \\ \\ (Dokumentumok)** fájlt, és keresse meg AutopilotDiagnostics.zip fájlt.  

       > [!NOTE]  
       > Előfordulhat.zip hogy a .zip fájl nem lesz azonnal elérhető. Ha a fájl még nem áll készen, egy HoloLensDiagnostics.temp fájlt láthat a Dokumentumok mappában. A fájlok listájának frissítéséhez frissítse az ablakot.
    
    1. Bontsa ki a AutopilotDiagnostics.zip tartalmát.

    1. A kibontott fájlokban keresse meg azt a CSV-fájlt, amely a "DeviceHash" fájlnév-előtaggal rendelkezik. Másolja a fájlt a számítógép egyik meghajtójére, ahol később hozzáférhet.  

       > [!IMPORTANT]  
       > A CSV-fájlban található adatoknak a következő fejléc- és sorformátumot kell használniuk:
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a>Eszköz regisztrálása MEM-en keresztül

1. A [Microsoft Endpoint Manager központban](https://endpoint.microsoft.com)válassza az **Eszközök Windows** Windows lehetőséget, majd a Program Windows Autopilot Deployment eszközök  >    >     >   **importálása lehetőséget.**

1. Az **Autopilot Windows hozzáadása alatt** válassza ki a DeviceHash CSV-fájlt, válassza a **Megnyitás** lehetőséget, majd az Importálás **lehetőséget.**  

   > [!div class="mx-imgBorder"]
   > ![Az Import paranccsal importálja a hardver kivonatát.](./images/hololens-ap-hash-import.png)

1. Az importálás befejezése után válassza az **Eszközök Windows**  >    >  **Windows eszközök**  >    >  **szinkronizálása lehetőséget.** A folyamat eltarthat néhány percig, attól függően, hogy hány eszköz szinkronizálása van folyamatban. A regisztrált eszköz kiválasztásához válassza a Frissítés **lehetőséget.**  

   > [!div class="mx-imgBorder"]
   > ![Az eszközlista megtekintéséhez használja a Szinkronizálás és frissítés parancsot.](./images/hololens-ap-devices-sync.png)  

### <a name="4-create-a-device-group"></a>4. Eszközcsoport létrehozása

1. A [Microsoft Endpoint Manager központban válassza a](https://endpoint.microsoft.com)Csoportok **Új** csoport  >  **lehetőséget.**

1. A **Csoport típusa mezőben** válassza a **Biztonság** lehetőséget, majd adja meg a csoport nevét és leírását.

1. A Tagság **típusa mezőben** válassza a **Hozzárendelt vagy** a **Dinamikus eszköz lehetőséget.**

1. Tegye a következők egyikét:  

   - Ha az **előző** lépésben a Hozzárendelt lehetőséget választotta a Tagság típusa beállításnál, válassza a Tagok lehetőséget, majd adja hozzá az AutoPilot-eszközöket a csoporthoz.  A még nem regisztrált Autopilot-eszközök az eszköz sorozatszámát használják eszköznévként a listában.
   - Ha az **előző** lépésben a Dinamikus eszközök lehetőséget választotta a Tagság típusa  beállításnál, válassza a Dinamikus eszköztagok lehetőséget, majd írja be a következőhöz hasonló kódot a Speciális szabály mezőbe: 
     - Ha az összes Autopilot-eszközét tartalmazó csoportot szeretne létrehozni, írja be a következőt: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Az Intune csoportcímke mezője az Azure AD-eszközökön az **OrderID** attribútumra van leképezve. Ha létre szeretne hozni egy csoportot, amely tartalmazza az összes olyan Autopilot-eszközt, amely egy adott csoportcímkével (az Azure AD-eszköz rendelésazonosítóját) tartalmazza, írja be a következőt: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Ha létre szeretne hozni egy csoportot, amely tartalmazza az összes olyan AutoPilot-eszközt, amely adott rendelésazonosítóval van meg, írja be a következőt: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Ezek a szabályok az AutoPilot-eszközökre jellemző egyedi attribútumokat céloznak meg.
1. Válassza **a Mentés,** majd a Létrehozás **lehetőséget.**

### <a name="5-create-a-deployment-profile"></a>5. Üzembe helyezési profil létrehozása

1. A [Microsoft Endpoint Manager központban](https://endpoint.microsoft.com)válassza az   >    >  **Autopilot Windows Windows regisztrációs**  >    >    >  Windows Profil létrehozása HoloLens lehetőséget.
   ![A Profil létrehozása legördülő menü tartalmaz egy HoloLens elemet.](./images/hololens-ap-enrollment-profiles.png)

1. Adja meg a profil nevét és leírását, majd válassza a Tovább **lehetőséget.**  
   Megjelenik egy lista, amely a **következőt HoloLens.** Ha ez a lehetőség nem áll rendelkezésre, a Visszajelzési lehetőségek [egyikével](hololens2-autopilot.md#feedback-and-support-for-autopilot) lépjen kapcsolatba velünk.

   > [!div class="mx-imgBorder"]
   > ![Profilnév és -leírás hozzáadása](./images/hololens-ap-profile-name.png)

1. A **OOBE (Out-of-box experience, OOBE)** oldalon a legtöbb beállítás előre konfigurálva van, hogy leegyszerűsítse az OOBE-t a kiértékelés során. Igény szerint a következő beállításokat is konfigurálhatja:  

   - **Nyelv (Régió):** Válassza ki az OOBE nyelvét. Javasoljuk, hogy válasszon nyelvet a 2. HoloLens támogatott nyelvek [listájából.](hololens2-language-support.md)
   - **Billentyűzet automatikus konfigurálása:** Ha meg kell győződni arról, hogy a billentyűzet megegyezik a kiválasztott nyelvvel, válassza az **Igen lehetőséget.**
   - **Eszköznév-sablon alkalmazása:** Az eszköz nevének automatikus  beállítását az OOBE során válassza az Igen lehetőséget, majd írja be a sablon kifejezését és helyőrzőit **a** Név beírása mezőben Például adjon meg egy előtagot és egy helyőrzőt egy négyjegyű véletlenszerű `%RAND:4%` &mdash; számhoz.
     > [!NOTE]  
     > Ha eszköznév-sablont használ, az OOBE folyamat még egyszer újraindítja az eszközt az eszköznév alkalmazása után, és mielőtt az eszközt az Azure AD-hez csatlakozna. Ez az újraindítás teszi lehetővé az új név érvénybe léptét.  

   > [!div class="mx-imgBorder"]
   > ![OOBE-beállítások konfigurálása](./images/hololens-ap-profile-oobe.png)

1. A beállítások konfigurálása után válassza a Tovább **lehetőséget.**
1. A **Hatókörcímkék lapon** igény szerint hozzáadhatja a profilra alkalmazni kívánt hatókörcímkéket. További információ a hatókörcímkékről: Szerepköralapú hozzáférés-vezérlés és hatókörcímkék használata [elosztott it-hez.](/mem/intune/fundamentals/scope-tags.md) Ha elkészült, válassza a **Tovább lehetőséget.**
1. A **Hozzárendelések lapon** a Hozzárendelés elemhez **válassza** a Kijelölt csoportok **lehetőséget.**
1. A **SELECTED GROUPS (KIVÁLASZTOTT CSOPORTOK) alatt** válassza a + Select groups to include **(Csoportok kiválasztása) lehetőséget.**
1. A **Bevezetni kívánt** csoportok kiválasztása listában válassza ki az Autopilot-eszközhöz létrehozott eszközcsoportot, HoloLens válassza a Tovább **lehetőséget.**  
  
   Ha ki szeretne zárni egy csoportot, válassza a **Kizárni** kívánt csoportok kijelölése lehetőséget, majd válassza ki a kizárni kívánt csoportokat.

   > [!div class="mx-imgBorder"]
   > ![Eszközcsoport hozzárendelése a profilhoz.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Az Áttekintés **+ létrehozás lapon** tekintse át a beállításokat, majd válassza a Létrehozás lehetőséget a profil létrehozásához.   

   > [!div class="mx-imgBorder"]
   > ![Ellenőrzés és létrehozás](./images/hololens-ap-profile-summ.png)

### <a name="6-verify-the-esp-configuration"></a>6. Az ESP konfigurációjának ellenőrzése

A Regisztrációs állapotlap (ESP) megjeleníti a teljes eszközkonfigurációs folyamat állapotát, amely akkor fut le, amikor egy MDM által felügyelt felhasználó először jelentkezik be egy eszközre. Győződjön meg arról, hogy az ESP-konfiguráció az alábbihoz hasonló, és ellenőrizze, hogy a hozzárendelések helyesek-e.  

> [!div class="mx-imgBorder"]
> ![ESP-konfiguráció](./images/hololens-ap-profile-settings.png)

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a>7. A profil állapotának ellenőrzése HoloLens eszközökön

1. A Microsoft Endpoint Manager központban válassza az **Eszközök Windows**  >    >  **Windows eszközök**  >  **lehetőséget.**

1. Ellenőrizze, hogy a HoloLens megjelenik-e a listában, és hogy a profiljuk állapota **Hozzárendelve.**  

   > [!NOTE]  
   > A profil az eszközhöz való hozzárendelése eltarthat néhány percig.  

   > [!div class="mx-imgBorder"]
   > ![Eszköz- és profil-hozzárendelések.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Autopilot for HoloLens 2 Felhasználói élmény

A fenti utasítások befejezése után a HoloLens 2 felhasználó a következő folyamaton megy keresztül a saját HoloLens üzembe:  

1. Az Autopilot használatához internet-hozzáférés szükséges. Az internet-hozzáféréshez használja az alábbi lehetőségek egyikét:

    - Csatlakozás az eszközt egy Wi-Fi OOBE-ban, majd hagyja, hogy automatikusan észlelje az Autopilot-élményt. Ez az egyetlen alkalom, amikor OOBE-val kell interakcióba lépnie, amíg az Autopilot-élmény egyedül be nem fejeződik. Vegye figyelembe, hogy HoloLens 2 várakozás 10 másodpercig az Autopilot észlelésére az internet észlelése után. Ha a rendszer 10 másodpercen belül nem észlel AutoPilot-profilt, az OOBE bemutatja a EULA-t. Ha ezzel a forgatókönyvvel találkozik, indítsa újra az eszközt, hogy újra megkísérelje észlelni az AutoPilotot. Vegye figyelembe azt is, hogy az OOBE csak akkor tud határozatlan ideig várni az Autopilotra, ha a TenantLockdown-szabályzat be van állítva az eszközön.

    - Csatlakozás "USB-C–Ethernet" adapterek használatával csatlakoztathatja az eszközt Ethernet-kapcsolattal a vezetékes internetkapcsolat érdekében, és HoloLens 2 teljes Autopilot-élményt biztosít automatikusan.

    - Csatlakozás az "USB-C–Wi-Fi" adaptereket a vezeték nélküli internetkapcsolat érdekében, és HoloLens 2 teljes Autopilot-élményt biztosít automatikusan.

        > [!IMPORTANT]  
       > Az Autopilothoz Wi-Fi OOBE-ban az új hálózatokat használni próbáló eszközöknek a [Holographic Windows 20H2](hololens-release-notes.md#windows-holographic-version-20h2)verziójú verziójának kell lennie.
       >
       > Ethernet-adaptereket használó eszközök esetén az eszközt a hálózatra kell csatlakoztatnia a OOBE (Out-of-the-Box-Experience) indítása előtt. Az eszköz az első OOBE képernyőn határozza meg, hogy AutoPilot-eszközként van-e kiépítve. Ha az eszköz nem tud csatlakozni a hálózathoz, vagy ha úgy dönt, hogy nem autopilot-eszközként létesíti az eszközt, később nem válthat AutoPilot-kiépítésre. Ehelyett újra kellene kezdenie ezt az eljárást ahhoz, hogy AutoPilot-eszközként kiépítse az eszközt.

1. Az eszköz automatikusan elindítja az OOBE-t. Ne használja az OOBE-t. Ehelyett dőlj hátra, és dőlj hátra! Hagyja, HoloLens 2. észlelje a hálózati kapcsolatot, és engedélyezze a OOBE automatikus befejezését. Az eszköz újraindulhat az OOBE során. Az OOBE-képernyőknek az alábbihoz hasonlónak kell lennie.

   ![OOBE 1. lépés ](./images/autopilot-welcome.jpg)
    ![ OOBE, ](./images/autopilot-step-complete.jpg)
    ![ 2. lépés: OOBE 3. lépés](./images/autopilot-device-setup.jpg)

1. Az OOBE végén bejelentkezhet az eszközre a felhasználónevével és jelszavával.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP és Autopilot

HoloLens 2 eszköz támogatja a TenantLockdown CSP-t Windows Holographic 20H2-es verziójától. Ez a CSP úgy tartja meg az eszközöket a szervezet bérlőjében, hogy az eszköz alaphelyzetbe állításán vagy perjelen keresztül zárolja őket a bérlőhöz.

[TenantLockdown (Bérlői zárolás)](/windows/client-management/mdm/tenantlockdown-csp) A CSP lehetővé HoloLens, hogy a 2., csak autopilotot használó MDM-regisztrációhoz legyen kötve. Miután a TenantLockdown CSP RequireNetworkInOOBE csomópontja true (igaz) vagy false (kezdetben beállított) értékre van állítva HoloLens 2-es verzióban, ez az érték megmarad az eszközön az újra flash() vagy operációsrendszer-frissítések stb. ellenére is.

Ha HoloLens 2. HoloLens TenantLockdown CSP-k RequireNetworkInOOBE csomópontja true (igaz) értékre van állítva, az OOBE határozatlan ideig vár az Autopilot-profil sikeres letöltésére és alkalmazásra a hálózati kapcsolat után.

Miután a TenantLockdown CSP-k RequireNetworkInOOBE csomópontja igazra van állítva HoloLens 2. HoloLens esetén a következő műveletek nem engedélyezettek az OOBE-ban:

- Helyi felhasználó létrehozása futásidejű kiépítéssel 
- Azure AD-beléptetés végrehajtása futásidejű üzembe építéssel 
- Annak kiválasztása, hogy ki az eszköz a tulajdonában az OOBE felhasználói élményben 

#### <a name="how-to-set-this-using-intune"></a>Hogyan állíthatja be ezt az Intune-nal? 
1. Hozzon létre egy egyéni OMA URI eszközkonfigurációs profilt, és adja meg a true értéket a RequireNetworkInOOBE csomóponthoz az alább látható módon.
Az OMA-URI értékének ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE kell lennie

   > [!div class="mx-imgBorder"]
   > ![Tennant zárolásának beállítása OMA-URI-n keresztül](images/hololens-tenant-lockdown.png)

1. Hozzon létre egy csoportot, és rendelje hozzá az eszközkonfigurációs profilt.

1. A HoloLens az előző lépésben létrehozott csoport 2. eszköztagját, és indítsa el a szinkronizálást.  

Ellenőrizze az Intune-portálon, hogy sikeresen megtörtént-e az eszközkonfiguráció alkalmazása. Miután ez az eszközkonfiguráció sikeresen alkalmazva lett HoloLens 2. eszközön, a TenantLockdown hatása aktív lesz.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>A TenantLockdown RequireNetworkInOOBE szolgáltatásának a 2. HoloLens az Intune-nal való használatának a megszürkítését?

1. Távolítsa el HoloLens 2. adatokat arról az eszközcsoportról, amelyhez korábban hozzárendelték a fent létrehozott eszközkonfigurációt.

1. Hozzon létre egy egyéni OMA URI-alapú eszközkonfigurációs profilt, és adja meg a false (hamis) értéket a RequireNetworkInOOBE mezőben, az alább látható módon.
Az OMA-URI értékének ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE kell lennie

   > [!div class="mx-imgBorder"]
   > ![Képernyőkép a RequireNetworkInOOBE hamisra állításával az OMA URI-n keresztül az Intune-ban](images/hololens-tenant-lockdown-false.png)

1. Hozzon létre egy csoportot, és rendelje hozzá az eszközkonfigurációs profilt. 

1. A HoloLens az előző lépésben létrehozott csoport 2. eszköztagját, és indítsa el a szinkronizálást.

Ellenőrizze az Intune-portálon, hogy sikeresen megtörtént-e az eszközkonfiguráció alkalmazása. Miután ez az eszközkonfiguráció sikeresen alkalmazva lett HoloLens 2. eszközön, a TenantLockdown hatása inaktív lesz.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Mi történne az OOBE során, ha az Autopilot-profil nincs hozzárendelve egy HoloLens miután a TenantLockdown igazra lett állítva? 
Az OOBE határozatlan ideig vár az Autopilot-profil letöltésére, és megjelenik a következő párbeszédpanel. A TenantLockdown hatásainak eltávolításához az eszközt először az autopilot használatával kell regisztrálni az eredeti bérlővel, és a RequireNetworkInOOBE-t az előző lépésben leírtak szerint meg kell szüntetni a TenantLockdown CSP által bevezetett korlátozások eltávolítása előtt.

![Eszközről nézetre, ha a szabályzat érvényben van az eszközön.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Ismert problémák & korlátozásai

- Egy olyan problémát vizsgálunk, amely miatt a MEM-alkalmazásban konfigurált eszközkörnyezet-alapú alkalmazástelepítés nem vonatkozik a HoloLens. [További információ az eszközkörnyezetről és a felhasználói környezet telepítéséről.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Az AutoPilot Wi-Fi-n keresztüli beállításakor előfordulhat, hogy az AutoPilot-profil nem lesz letöltve az internetkapcsolat első létesítéskor. Ebben az esetben végfelhasználói licencszerződés (EULA) lesz bemutatva, és a felhasználó folytathatja a nem Autopilot-beállítási élményt. Az Autopilot beállításának újrapróbálkozáshoz helyezze alvó üzemmódba az eszközt, majd bekapcsolja vagy indítsa újra az eszközt, és hagyja, hogy újrapróbálkozjon.
- A "Minden megcélzott eszköz Autopilot-eszközre konvertálása" funkció jelenleg HoloLens támogatott.  

### <a name="troubleshooting"></a>Hibaelhárítás

A következő cikkek hasznos forrást hatnak az AutoPilot-problémák további információinak elsajátítása és hibaelhárítása során, azonban vegye figyelembe, hogy ezek a cikkek az Windows 10 Desktopon alapulnak, és nem minden információ vonatkozhat a HoloLens:

- [Windows Autopilot – ismert problémák](/mem/autopilot/known-issues)
- [Eszközregisztrációs Windows hibaelhárítása a Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – Szabályzatütközések](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Visszajelzés és támogatás az AutoPilothoz

Ha visszajelzést szeretne küldeni vagy problémákat szeretne jelenteni, használja az alábbi módszerek egyikét:

- Az eszközregisztrációval kapcsolatban forduljon a viszonteladóhoz vagy a terjesztőhöz.
- Az Autopilot Windows kapcsolatos általános támogatási kérdésekért, illetve a profil-hozzárendeléssel, csoport létrehozásával vagy a MEM-portál vezérlőivel kapcsolatos problémákért forduljon a [Microsoft Endpoint Manager támogatási szolgálatához](/mem/get-support)  
- Ha az eszköze regisztrálva van az Autopilot szolgáltatásban, és a profil hozzá van rendelve a MEM portálon, lépjen kapcsolatba a HoloLens [támogatási](/hololens/) szolgálatával (lásd a "Támogatás" kártyát). Nyisson meg egy támogatási jegyet, és ha lehetséges, csatolja a képernyőképeket és naplókat az [offline](hololens-diagnostic-logs.md#offline-diagnostics) diagnosztikai naplók a használatra (OOBE) való rögzítésével.
- A probléma eszközről való bejelentéséhez használja a Visszajelzési központ alkalmazást a HoloLens. A Visszajelzési központ válassza a **Vállalati felügyeleti**  >  **eszköz kategóriát.**
- Ha általános visszajelzést szeretne küldeni az Autopilot for HoloLens, elküldheti ezt a [felmérést](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)
