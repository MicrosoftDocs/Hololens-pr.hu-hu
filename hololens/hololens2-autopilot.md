---
title: Windows Autopilot HoloLens 2-höz
description: Ismerje meg, hogyan állíthatja be, konfigurálhatja és háríthatja el az Autopilotot HoloLens 2 eszközön.
author: qianw211
ms.author: v-qianwen
ms.date: 9/8/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Robotpilóta
manager: sekerawa
ms.openlocfilehash: 28793b385bad58d44c6592a800c4f56b18d152ce
ms.sourcegitcommit: 20ea1ed37772655504ccb11a7e185ed19d85f336
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/16/2021
ms.locfileid: "127833573"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot HoloLens 2-höz

## <a name="overview"></a>Áttekintés

Nagy léptékű üzembe helyezéshez javasoljuk, hogy ismerkedés az Windows Autopilottal. Ez "kevés érintésnek" tekinthető, mert jelentősen leegyszerűsíti az it-HoloLens és a végfelhasználók számára való beállítását. 

Magas szinten a rendszergazda általában üzleti használatra kész konfigurációkat hoz létre, és HoloLens 2 eszközt regisztrál az MDM-portálon. Ha HoloLens 2 eszköz használatra kész felülettel (OOBE) indul el, és csatlakozik az internethez, a rendszer automatikusan letölti és alkalmazza a regisztrált HoloLens 2 eszköz üzleti használatra kész konfigurációit, hogy az eszköz felhasználói beavatkozás nélkül használható legyen.

További információ: [Az Autopilot-Windows áttekintése | Microsoft Docs](/mem/autopilot/windows-autopilot) cikk.

## <a name="supported-autopilot-scenario-on-hololens-2"></a>A 2. HoloLens támogatott Autopilot-forgatókönyv

> [!NOTE]
> A szolgáltatásban HoloLens Autopilot Microsoft Endpoint Manager konfiguráció nyilvános  előzetes verzióról általánosan **elérhetőre áll át.** Minden bérlő be tudja majd állítva az Autopilotot a MEM felügyeleti központban.

A Windows Holographic 2004-es verziójától kezdődően a HoloLens 2., támogatja az Windows Autopilot [self-Deploying Mode-t az Microsoft Intune-val](/mem/autopilot/self-deploying) (a harmadik féltől származó MDM-ek nem támogatottak). Ez a konfiguráció csökkenti a készletkezelési többletterhelést, az eszközök gyakorlati előkészítésének költségeit és az alkalmazottak támogatási hívásait a beállítási folyamat során. További információt a Windows [Autopilot dokumentációjában](/mem/autopilot/windows-autopilot) talál.

A Surface-eszközökhöz hasonló ajánlott, hogy az ügyfelek a Microsoft [Felhőszolgáltató](https://partner.microsoft.com/cloud-solution-provider) (viszonteladó vagy terjesztő) segítségével regisztrálják az eszközöket az Autopilot szolgáltatásban a Partnerközpont.

Amikor egy felhasználó elindítja az AutoPilot önkiszolgáló üzembe helyezési folyamatát, az Autopilot a következő lépéseket teszi:

1. Az eszköz csatlakozása Azure Active Directory (Azure AD) szolgáltatáshoz. Az Autopilot for HoloLens nem támogatja a Active Directory és a hibrid Azure AD-csatlakozást.

1. Az Azure AD használatával regisztrálja az eszközt Microsoft Endpoint Manager (vagy egy másik MDM-szolgáltatásban).

1. Eszközre vonatkozó szabályzatok, tanúsítványok, hálózati profilok és alkalmazások letöltése és alkalmazása.

1. A bejelentkezési képernyőt mutatja be a felhasználónak.

## <a name="configuring-autopilot-for-hololens-2"></a>Az AutoPilot konfigurálása HoloLens 2-

A környezet beállításhoz kövesse az alábbi lépéseket:

1. [Tekintse át az Autopilot Windows 2- HoloLens követelményeit.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Automatikus MDM-regisztráció engedélyezése](#2-enable-automatic-mdm-enrollment)

1. (Csak az Intune esetén) Győződjön meg arról, hogy az [MDM-regisztráció nincs Windows eszközökön.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [Eszközök regisztrálása Windows Autopilotban.](#4-register-devices-in-windows-autopilot)

1. [Eszközcsoport létrehozása.](#5-create-a-device-group)

1. [AutoPilot-profil létrehozása és hozzárendelése az eszközcsoporthoz.](#6-create-autopilot-profile-and-assign-it-to-the-device-group)

1. [Hozza létre a Regisztrációs állapotlap (ESP) konfigurációját, és rendelje hozzá az eszközcsoporthoz.](#7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group)

1. [Ellenőrizze a profil állapotát a HoloLens eszközein.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Az Autopilot 2 Windows re vonatkozó követelményeinek HoloLens áttekintése

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Tekintse át a következő szakaszokat a Windows Autopilot-követelményekkel kapcsolatos cikkben:

- [A hálózatra vonatkozó követelmények](/mem/autopilot/networking-requirements)  
- [Licenckövetelmények](/mem/autopilot/licensing-requirements)  
- [Konfigurációs követelmények](/mem/autopilot/configuration-requirements)

**Tekintse át [a](/windows/deployment/windows-autopilot/self-deploying#requirements)Windows Autopilot Self-Deploying móddal kapcsolatos cikk "Követelmények" szakaszát.** A környezetnek meg kell felelnie ezeknek a követelményeknek és a szabványos Windows Autopilot követelményeinek. Nem kell áttekintenünk a cikk "Lépésről lépésre" és "Ellenőrzés" szakaszát. A cikk későbbi lépései a megfelelő lépéseket biztosítanak a HoloLens.

Győződjön meg arról, hogy az eszközök még nem tagjai az Azure AD-nek, és nincsenek regisztrálva az Intune-ban (vagy más MDM-rendszerben). Az Autopilot önkiszolgáló üzembe helyezési folyamata ezeket a lépéseket ad vissza. Ha meg kell győződni arról, hogy az eszközhöz kapcsolódó összes információ el van különülve, ellenőrizze az Eszközök lapot az Azure AD-portálon és az Intune-portálon is.  Az összes megcélzott eszköz Autopilotra konvertálása" funkció jelenleg nem HoloLens támogatott az egyes eszközökön. 

#### <a name="review-hololens-os-requirements"></a>Tekintse át HoloLens operációs rendszer követelményeit:

Az eszközön található buildverzió megerősítéséhez vagy a legújabb operációs rendszerre való átfedéshez használja az [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) eszközt és az eszköz perjeles [utasításait.](hololens-recovery.md) A 2020. szeptember végéig kézbesített eszközökre Windows Holographic 1903-as verziója van előre telepítve. Lépjen kapcsolatba a viszonteladóval, és győződjön meg arról, hogy az Autopilot-kompatibilis eszközök ki vannak szállítva.

 Az operációs rendszer minimális verziószáma | Támogatott funkció | Megjegyzések 
 ------ | ------ | ------  
 [Windows Holographic, 2004-es](hololens-release-notes.md#windows-holographic-version-2004) verzió (19041.1103-as build) vagy újabb | 1. Az AutoPilot önkiszolgáló üzembe helyezési forgatókönyve a 2. HoloLens 2. | Az Autopilot-profilok letöltése csak Etherneten keresztül támogatott. A bekapcsolása HoloLens az "USB-C–Ethernet" adapterrel győződjön meg arról, hogy a hálózati adapter csatlakoztatva van az **Ethernethez.**  Ha egy Autopilot-bevezetést tervez számos HoloLens-eszközön, javasoljuk, hogy tervezze meg az adapter-infrastruktúrát. Az USB Hubok nem ajánlottak, mivel gyakran külső gyártótól származó illesztőprogramokat kell telepíteni, amelyek nem támogatottak a HoloLens.
 [Windows Holographic, 20H2-es](hololens-release-notes.md#windows-holographic-version-20h2) verzió (19041.1128-as build) vagy újabb | 1. Autopilot-profil letöltése Wi-Fi-n keresztül. <br> 2. [Bérlői lezárási CSP és Autopilot az AutoPilot](#tenant-lockdown-csp-and-autopilot) által megadott bérlővel zárolt eszközök zárolásához. | Szükség esetén továbbra is használhat Ethernet-adaptereket. A Wi-Fi-n keresztül csatlakoztatott eszközök esetében a felhasználónak csak a következőt kell: <ul> <li> Végig kell mennie a jeleneten. </li> <li> Válassza ki a nyelvet és a területi beállításokat. </li> <li> Futtatassa a szemkontrasztot. </li> <li> Sikeresen csatlakozott a kívánt Wi-Fi-hálózathoz. </li> </ul>

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Az automatikus MDM-regisztráció engedélyezése:

Ahhoz, hogy az Autopilot sikeres legyen, engedélyeznie kell az automatikus MDM-regisztrációt a Azure Portal. Ez lehetővé teszi, hogy az eszköz felhasználó nélkül regisztráljon.

Az automatikus [MDM-regisztráció](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) engedélyezéséről az [](/mem/intune/enrollment/quickstart-setup-auto-enrollment) alábbi rövid útmutatóban vagy az automatikus regisztráció rövid útmutatója alapján további információt is be lehet állítani.

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. Győződjön meg arról, hogy az MDM-regisztráció nincs letiltva a Windows eszközökön.

Ahhoz, hogy az Autopilot sikeres legyen, meg kell győződni arról, hogy a HoloLens eszközök regisztrálva legyenek. Mivel HoloLens eszköz Windows, nem kell regisztrációs korlátozásokat alkalmaznunk, amelyek blokkolni tudnák az üzembe helyezést. [Tekintse át ezt a korlátozáslistát,](/mem/intune/enrollment/enrollment-restrictions-set) és ellenőrizze, hogy regisztrálhatja-e az eszközeit.

### <a name="4-register-devices-in-windows-autopilot"></a>4. Eszközök regisztrálása Windows Autopilotban

Az első telepítés előtt az eszközöket regisztrálni kell Windows Autopilotban. 

Az eszközök regisztrálásának három elsődleges HoloLens módja van:

 - **A viszonteladó regisztrálhat eszközöket a Partnerközpont rendeléskor.**

   > [!NOTE]  
   > Ez az eszközök Autopilot-szolgáltatáshoz való hozzáadásának ajánlott útvonala. [További információ](/mem/autopilot/partner-registration).  

 - **Támogatási [kérést küldhet közvetlenül a](hololens2-autopilot-registration-support.md) Microsoftnak.**
 - **Olvassa be a hardver kivonatát (más** néven hardverazonosítóját), és regisztrálja manuálisan az eszközt a MEM felügyeleti központban.

#### <a name="obtain-hardware-hash"></a>Hardver-kivonat beszerzése

A hardver kivonatát lekérheti az eszközről. Az eszköz rögzíti a hardver kivonatát egy CSV-fájlban az OOBE folyamat során, vagy később, amikor az eszköz tulajdonosa elindítja a diagnosztikai naplók gyűjtésének folyamatát (lásd az alábbi eljárást). Általában az eszköz tulajdonosa az első felhasználó, aki bejelentkezik az eszközre.

> [!WARNING]
> A 20H2 előtti buildek esetén, ha már végigment az OOBE-ban, és a telemetria Kötelezőre lett állítva, ezzel a módszerrel nem gyűjthető össze az Autopilot hardver-kivonata. Ha ezzel a módszerrel gyűjti össze a hardver-kivonatot, állítsa a Telemetria beállítást Teljesre a Gépház alkalmazáson keresztül, majd válassza az **Adatvédelmi**  >  **diagnosztika lehetőséget.**

1. Indítsa el HoloLens 2-es eszközt.

1. Az eszközön egyszerre nyomja le a **Power** és **Volume Down** gombokat, majd engedje el őket. Az eszköz összegyűjti a diagnosztikai naplókat és a hardver kivonatát, és egy .zip tárolja őket.

1. Részletes információkért és egy oktató videóért ennek elvégzéséről olvassa el az [Offline diagnosztika szakaszt.](hololens-diagnostic-logs.md#offline-diagnostics)

1. Usb-C kábellel csatlakoztassa az eszközt egy számítógéphez.

1. A számítógépen nyissa meg a Fájlkezelő. Nyissa <b>meg \\ ezt</b>a < *HoloLens belső eszköznevet* a Dokumentumok > <b> \\ \\ Storage,</b>és keresse meg a AutopilotDiagnostics.zip fájlt.  

   > [!NOTE]  
   > Előfordulhat.zip hogy a fájl nem érhető el azonnal. Ha a fájl még nem áll készen, egy HoloLensDiagnostics.temp fájlt láthat a Dokumentumok mappában. A fájlok listájának frissítéséhez frissítse az ablakot.
    
1. Bontsa ki a AutopilotDiagnostics.zip tartalmát.

1. A kibontott fájlokban keresse meg azt a CSV-fájlt, amely a "DeviceHash" fájlnév-előtaggal rendelkezik. Másolja a fájlt a számítógép egyik meghajtójére, ahol később hozzáférhet.  

   > [!IMPORTANT]  
   > A CSV-fájlban található adatoknak a következő fejléc- és sorformátumot kell használniuk:
   >
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### <a name="register-device-through-mem"></a>Eszköz regisztrálása MEM-en keresztül

1. A [Microsoft Endpoint Manager központban](https://endpoint.microsoft.com)válassza az **Eszközök Windows** Windows lehetőséget, majd a Program Windows Autopilot Deployment eszközök  >    >     >   **importálása lehetőséget.**

1. Az **Autopilot Windows hozzáadása** alatt válassza ki a DeviceHash CSV-fájlt, válassza a **Megnyitás** lehetőséget, majd az Importálás **lehetőséget.**  

   > [!div class="mx-imgBorder"]
   > ![Az Import paranccsal importálja a hardver kivonatát.](./images/hololens-ap-hash-import.png)

1. Az importálás befejezése után válassza az **Eszközök Windows**  >    >  **Windows eszközök**  >    >  **szinkronizálása lehetőséget.** A folyamat eltarthat néhány percig, attól függően, hogy hány eszköz szinkronizálása van folyamatban. A regisztrált eszköz kiválasztásához válassza a Frissítés **lehetőséget.**  

   > [!div class="mx-imgBorder"]
   > ![Az eszközlista megtekintéséhez használja a Szinkronizálás és frissítés parancsot.](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. Eszközcsoport létrehozása

1. A [Microsoft Endpoint Manager központban válassza](https://endpoint.microsoft.com)a Csoportok **Új** csoport  >  **lehetőséget.**

1. A **Csoport típusa mezőben** válassza a **Biztonság** lehetőséget, majd adja meg a csoport nevét és leírását.

1. A Tagság **típusa mezőben** válassza a **Hozzárendelt vagy** a **Dinamikus eszköz lehetőséget.**

1. Tegye a következők egyikét:  

   - Ha az **előző** lépésben a Hozzárendelt lehetőséget választotta a Tagság típusa beállításnál, válassza a Tagok lehetőséget, majd adja hozzá az AutoPilot-eszközöket a csoporthoz.  A még nem regisztrált Autopilot-eszközök az eszköz sorozatszámát használják eszköznévként a listában.
   - Ha az **előző** lépésben a Dinamikus eszközök lehetőséget választotta a Tagság típusa  beállításnál, válassza a Dinamikus eszköztagok lehetőséget, majd írja be a következőhöz hasonló kódot a Speciális szabály mezőbe: 
     - Ha az összes Autopilot-eszközét tartalmazó csoportot szeretne létrehozni, írja be a következőt: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Az Intune csoportcímke mezője az Azure AD-eszközökön az **OrderID** attribútumra van leképezve. Ha létre szeretne hozni egy csoportot, amely tartalmazza az összes olyan Autopilot-eszközt, amely egy adott csoportcímkével (az Azure AD-eszköz rendelésazonosítóját) tartalmazza, írja be a következőt: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Ha létre szeretne hozni egy csoportot, amely tartalmazza az összes olyan AutoPilot-eszközt, amely adott rendelésazonosítóval van megrendelve, írja be a következőt: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Ezek a szabályok az AutoPilot-eszközökre jellemző egyedi attribútumokat céloznak meg.
1. Válassza **a Mentés,** majd a Létrehozás **lehetőséget.**

### <a name="6-create-autopilot-profile-and-assign-it-to-the-device-group"></a>6. AutoPilot-profil létrehozása és hozzárendelése az eszközcsoporthoz

1. A [Microsoft Endpoint Manager központban](https://endpoint.microsoft.com)válassza az   >    >  Autopilot Windows Windows regisztrációs  >    >    >  profilokkal Windows Eszközök Profil létrehozása HoloLens lehetőséget.
   ![A Profil létrehozása legördülő menü tartalmaz egy HoloLens elemet.](./images/hololens-ap-enrollment-profiles.png)

1. Adja meg a profil nevét és leírását, majd válassza a Tovább **lehetőséget.**  
   Megjelenik egy lista, amely a **következőt HoloLens.** Ha ez a lehetőség nem áll rendelkezésre, a Visszajelzési lehetőségek [egyikével](hololens2-autopilot.md#feedback-and-support-for-autopilot) lépjen kapcsolatba velünk.

   > [!div class="mx-imgBorder"]
   > ![Adja meg a profil nevét és leírását.](./images/hololens-ap-profile-name.png)

1. A **OOBE (Out-of-box experience, OOBE)** oldalon a legtöbb beállítás előre konfigurálva van, hogy leegyszerűsítse az OOBE-t a kiértékelés során. Igény szerint a következő beállításokat is konfigurálhatja:  

   - **Nyelv (Régió):** Válassza ki az OOBE nyelvét. Javasoljuk, hogy válasszon nyelvet a 2. HoloLens támogatott nyelvek [listájából.](hololens2-language-support.md)
   - **Billentyűzet automatikus konfigurálása:** Ha meg kell győződni arról, hogy a billentyűzet megegyezik a kiválasztott nyelvvel, válassza az **Igen lehetőséget.**
   - **Eszköznév-sablon alkalmazása:** Az eszköz nevének automatikus  beállítását az OOBE során válassza az Igen lehetőséget, majd írja be a sablon kifejezését és helyőrzőit **a** Név beírása: Például adjon meg egy előtagot és egy helyőrzőt egy négyjegyű véletlenszerű `%RAND:4%` &mdash; számhoz.
     > [!NOTE]  
     > Ha eszköznév-sablont használ, az OOBE-folyamat egyszer újraindítja az eszközt az eszköznév alkalmazása után, és mielőtt az eszközt az Azure AD-hez csatlakozna. Ez az újraindítás teszi lehetővé az új név érvénybe léptét.  

   > [!div class="mx-imgBorder"]
   > ![OOBE-beállítások konfigurálása.](./images/hololens-ap-profile-oobe.png)

1. A beállítások konfigurálása után válassza a Tovább **lehetőséget.**
1. A **Hatókörcímkék lapon** igény szerint hozzáadhatja a profilra alkalmazni kívánt hatókörcímkéket. További információ a hatókörcímkékről: Szerepköralapú hozzáférés-vezérlés és hatókörcímkék használata [elosztott IT-hez.](/mem/intune/fundamentals/scope-tags.md) Ha elkészült, válassza a **Tovább lehetőséget.**
1. A **Hozzárendelések lapon** a Hozzárendelés elemhez **válassza** a Kijelölt csoportok **lehetőséget.**
1. A **SELECTED GROUPS (KIVÁLASZTOTT CSOPORTOK) alatt** válassza a + Select groups to include **(Csoportok kiválasztása) lehetőséget.**
1. A **Bevezetni kívánt** csoportok kiválasztása listában válassza ki az Autopilot-eszközhöz létrehozott eszközcsoportot, HoloLens kattintson a Tovább **gombra.**  
  
   Ha ki szeretne zárni egy csoportot, válassza a **Kizárni** kívánt csoportok kijelölése lehetőséget, majd válassza ki a kizárni kívánt csoportokat.

   > [!div class="mx-imgBorder"]
   > ![Eszközcsoport hozzárendelése a profilhoz.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Az Áttekintés **+ létrehozás lapon** tekintse át a beállításokat, majd válassza a Létrehozás lehetőséget a profil létrehozásához.   

   > [!div class="mx-imgBorder"]
   > ![Áttekintés és létrehozás.](./images/hololens-ap-profile-summ.png)

### <a name="7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group"></a>7. Regisztrációs állapotlap (ESP) konfigurációjának létrehozása és hozzárendelése az eszközcsoporthoz

A Regisztrációs állapotlap (ESP) megjeleníti a teljes eszközkonfigurációs folyamat állapotát, amely akkor fut, amikor egy MDM által felügyelt felhasználó először jelentkezik be egy eszközre. Győződjön meg arról, hogy az ESP-konfiguráció az alábbihoz hasonló, és ellenőrizze, hogy a hozzárendelések helyesek-e.  

> [!div class="mx-imgBorder"]
> ![ESP-konfiguráció.](./images/hololens-ap-profile-settings.png)

További információ az ESP-ről: Regisztrációs állapotlap beállítása [– Microsoft Intune | Microsoft Docs](/mem/intune/enrollment/windows-enrollment-status)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. A HoloLens állapotának ellenőrzése

1. A Microsoft Endpoint Manager központban válassza az **Eszközök Windows**  >    >  **Windows eszközök**  >  **lehetőséget.**

1. Ellenőrizze, hogy a HoloLens megjelenik-e, és hogy a profiljuk állapota **Hozzárendelve.**  

   > [!NOTE]  
   > Eltarthat néhány percig, hogy a profil hozzá legyen rendelve az eszközhöz.  

   > [!div class="mx-imgBorder"]
   > ![Eszköz- és profil-hozzárendelések.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Autopilot for HoloLens 2 Felhasználói élmény

A fenti utasítások befejezése után a HoloLens 2 felhasználó a következő folyamaton megy keresztül a saját HoloLens kiépítése érdekében:  

1. Az Autopilot használatához internet-hozzáférés szükséges. Internet-hozzáférést az alábbi lehetőségek egyikével biztosít:

    - Csatlakozás az eszközt egy Wi-Fi OOBE-ban, majd hagyja, hogy automatikusan észlelje az Autopilot-élményt. Ez az egyetlen alkalom, amikor OOBE-val kell interakcióba lépnie, amíg az Autopilot-élmény egyedül be nem fejeződik. Alapértelmezés szerint HoloLens 2 várakozást az Autopilot észlelésére 10 másodpercig az internet észlelése után. Ha a rendszer 10 másodpercen belül nem észlel AutoPilot-profilt, az OOBE bemutatja a EULA-t. Ha ezzel a forgatókönyvvel találkozik, indítsa újra az eszközt, hogy újra megkísérelje észlelni az AutoPilotot. Azt is vegye figyelembe, hogy az OOBE csak akkor tud határozatlan ideig várni az Autopilotra, ha a TenantLockdown-szabályzat be van állítva az eszközön.

    - Csatlakozás "USB-C–Ethernet" adapterek használatával csatlakoztathatja az eszközt Ethernet-kapcsolattal a vezetékes internetkapcsolat érdekében, és HoloLens 2 teljes Autopilot-élményt biztosít automatikusan.

    - Csatlakozás "USB-C–Wi-Fi" adapterekkel támogatja a vezeték nélküli internetkapcsolatot, és HoloLens 2 teljes Autopilot-élményt biztosít automatikusan.

        > [!IMPORTANT]  
       > Az Autopilothoz Wi-Fi OOBE-ban a virtuális hálózatokat használni próbáló eszközöknek a [Holographic 20H2-es](hololens-release-notes.md#windows-holographic-version-20h2)verzióján Windows kell lennie.
       >
       > Ethernet-adaptereket használó eszközök esetén az eszközt csatlakoztatni kell a hálózathoz a OOBE indítása előtt. Az eszköz az első OOBE képernyőn határozza meg, hogy AutoPilot-eszközként van-e kiépítve. Ha az eszköz nem tud csatlakozni a hálózathoz, vagy ha úgy dönt, hogy nem autopilot-eszközként létesíti az eszközt, később nem válthat AutoPilot-kiépítésre. Ehelyett újra kellene kezdenie ezt az eljárást ahhoz, hogy AutoPilot-eszközként kiépítse az eszközt.

1. Az eszköz automatikusan elindítja az OOBE-t. Ne használja az OOBE-t.

    > [!IMPORTANT]
    > Ne használja az OOBE-t, és ne nyomja le a bekapcsológombot a rendszer készenléti/leállítási állapotba hozása érdekében, amíg az Autopilot folyamatban van. Ez azt okozhatja, hogy az AutoPilot-folyamat nem fejeződik be.

   Hagyja HoloLens, hogy a 2. gép észlelje a hálózati kapcsolatot, és engedélyezze a teljes OOBE automatikus befejezését. Az eszköz újraindulhat az OOBE során. Az OOBE-képernyőknek az alábbihoz hasonlónak kell lennie.

   ![OOBE 1. lépés. ](./images/autopilot-welcome.jpg)
    ![ OOBE 2. lépés. ](./images/autopilot-step-complete.jpg)
    ![ OOBE 3. lépés.](./images/autopilot-device-setup.jpg)

1. Az OOBE végén bejelentkezhet az eszközre a felhasználónevével és jelszavával.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>Bérlő zárolt CSP és Autopilot

HoloLens 2 eszköz támogatja a TenantLockdown CSP-t Windows Holographic 20H2-es verziójától. Ez a CSP úgy tartja meg az eszközöket a szervezet bérlőjében, hogy az eszköz alaphelyzetbe állításán vagy perjelen keresztül zárolja őket a bérlőhöz.

[TenantLockdown (Bérlői zárolás)](/windows/client-management/mdm/tenantlockdown-csp) A CSP lehetővé HoloLens 2. tanúsítvány MDM-regisztrációhoz való kötődését kizárólag autopilot használatával. Miután a TenantLockdown CSP RequireNetworkInOOBE csomópontja true (igaz) vagy false (kezdetben beállított) értékre van állítva HoloLens 2-es verzióban, ez az érték megmarad az eszközön az újrafésulás, az operációs rendszer frissítése stb. ellenére is.

Ha HoloLens 2. HoloLens-n a TenantLockdown CSP-k RequireNetworkInOOBE csomópontja igazra van állítva, az OOBE határozatlan ideig vár az Autopilot-profil sikeres letöltésére és alkalmazásra a hálózati kapcsolat után.

Miután a TenantLockdown CSP-k RequireNetworkInOOBE csomópontja igazra van állítva HoloLens 2. HoloLens OOBE-ban a következő műveletek nem engedélyezettek:

- Helyi felhasználó létrehozása futásidejű kiépítéssel 
- Azure AD-csatlakozási művelet végrehajtása futásidejű üzembe építéssel 
- Annak kiválasztása, hogy ki az eszköz a OOBE-felhasználói élményben a tulajdonában 

#### <a name="how-to-set-this-using-intune"></a>Hogyan állíthatja be ezt az Intune-nal? 
1. Hozzon létre egy egyéni OMA URI eszközkonfigurációs profilt, és adja meg a true értéket a RequireNetworkInOOBE csomóponthoz az alább látható módon.
Az OMA-URI értékének ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE kell lennie

   > [!div class="mx-imgBorder"]
   > ![Tennant zárolás beállítása OMA-URI-n keresztül.](images/hololens-tenant-lockdown.png)

1. Hozzon létre egy csoportot, és rendelje hozzá az eszközkonfigurációs profilt.

1. A HoloLens az előző lépésben létrehozott csoport 2. eszköztagját, és indítsa el a szinkronizálást.  

Ellenőrizze az Intune-portálon, hogy sikeresen megtörtént-e az eszközkonfiguráció alkalmazása. Miután ez az eszközkonfiguráció sikeresen alkalmazva lett HoloLens 2. eszközön, a TenantLockdown hatása aktív lesz.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>A TenantLockdown RequireNetworkInOOBE szolgáltatásának be- és HoloLens a 2. intune-nal?

1. Távolítsa el HoloLens 2. adatokat arról az eszközcsoportról, amelyhez korábban hozzárendelték a fent létrehozott eszközkonfigurációt.

1. Hozzon létre egy egyéni OMA URI-alapú eszközkonfigurációs profilt, és adja meg a false (hamis) értéket a RequireNetworkInOOBE mezőben, ahogy az alább látható.
Az OMA-URI értékének ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE kell lennie

   > [!div class="mx-imgBorder"]
   > ![Képernyőkép a RequireNetworkInOOBE hamisra állításával az Intune OMA URI-ján keresztül.](images/hololens-tenant-lockdown-false.png)

1. Hozzon létre egy csoportot, és rendelje hozzá az eszközkonfigurációs profilt. 

1. A HoloLens az előző lépésben létrehozott csoport 2. eszköztagját, és indítsa el a szinkronizálást.

Ellenőrizze az Intune-portálon, hogy sikeresen megtörtént-e az eszközkonfiguráció alkalmazása. Miután ez az eszközkonfiguráció sikeresen alkalmazva lett HoloLens 2. eszközön, a TenantLockdown hatása inaktív lesz.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Mi történne az OOBE során, ha az Autopilot-profil nincs hozzárendelve egy HoloLens miután a TenantLockdown igazra lett állítva? 
Az OOBE határozatlan ideig vár az Autopilot-profil letöltésére, és megjelenik a következő párbeszédpanel. A TenantLockdown hatásainak eltávolításához az eszközt először az autopilot használatával kell regisztrálni az eredeti bérlővel, és a RequireNetworkInOOBE-t az előző lépésben leírtak szerint meg kell szüntetni a TenantLockdown CSP által bevezetett korlátozások eltávolítása előtt.

![Eszközről nézetre, ha a szabályzat érvényben van az eszközön.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Ismert problémák & korlátozásai

- Egy olyan problémát vizsgálunk, amely miatt a MEM-alkalmazásban konfigurált eszközkörnyezet-alapú alkalmazástelepítés nem vonatkozik a HoloLens. [További információ az eszközkörnyezetről és a felhasználói környezet telepítéséről.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Az Autopilot Wi-Fi-n keresztüli beállításakor előfordulhat, hogy az AutoPilot-profil nem lesz letöltve az internetkapcsolat első létesítéskor. Ebben az esetben végfelhasználói licencszerződés (EULA) lesz bemutatva, és a felhasználó folytathatja a nem Autopilot-beállítási élményt. Az Autopilot beállításának újrapróbálkozáshoz helyezze alvó üzemmódba az eszközt, majd bekapcsolja vagy indítsa újra az eszközt, és hagyja, hogy újrapróbálkozjon.

### <a name="troubleshooting"></a>Hibaelhárítás

A következő cikkek hasznos forrást hatnak az AutoPilot-problémák további információinak elsajátítása és hibaelhárítása során, azonban ezek a cikkek az Windows 10 Desktopon alapulnak, és nem minden információ vonatkozhat a HoloLens:

- [Windows Autopilot – ismert problémák](/mem/autopilot/known-issues)
- [Eszközregisztrációs Windows hibaelhárítása a Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – Szabályzatütközések](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Visszajelzés és támogatás az AutoPilothoz

Ha visszajelzést szeretne küldeni vagy problémákat szeretne jelenteni, használja az alábbi módszerek egyikét:

- Az eszközregisztrációval kapcsolatban forduljon a viszonteladóhoz vagy a terjesztőhöz.
- Az Autopilot használatával Windows kapcsolatos általános támogatási kérdésekért, illetve a profil-hozzárendeléssel, csoport létrehozásával vagy a MEM-portál vezérlőivel kapcsolatos Microsoft Endpoint Manager [forduljon](/mem/get-support)  
- Ha az eszköze regisztrálva van az Autopilot szolgáltatásban, és a profil hozzá van rendelve a MEM portálon, lépjen kapcsolatba a HoloLens [támogatási](/hololens/) szolgálatával (lásd a "Támogatás" kártyát). Nyisson meg egy támogatási jegyet, és ha lehetséges, csatolja a képernyőképeket és naplókat az [offline](hololens-diagnostic-logs.md#offline-diagnostics) diagnosztikai naplóknak a használatra (OOBE) való rögzítésével.
- A probléma eszközről való bejelentéséhez használja a Visszajelzési központ alkalmazást a HoloLens. A Visszajelzési központ válassza a **Vállalati felügyeleti**  >  **eszköz kategóriát.**
- Ha általános visszajelzést szeretne küldeni az Autopilot for HoloLens, elküldheti ezt a [felmérést](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>AutoPilot-eszközök törlése

Előfordulhat, hogy már nem szeretne eszközt használni az Autopilothoz, vagy egy másik bérlőben szeretné regisztrálni az eszközeit. Ha ezt szeretné tenni, olvassa el, hogyan törölheti az [AutoPilot-eszközöket.](/mem/autopilot/add-devices#delete-autopilot-devices)