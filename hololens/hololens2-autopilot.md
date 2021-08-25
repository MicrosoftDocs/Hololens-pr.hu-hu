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
ms.openlocfilehash: 7dbe77c8c5999d5be1a61ca9deaa8071d152c87a
ms.sourcegitcommit: d0c7bf5b055fa1fa8ac5562eef904583a655da99
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/24/2021
ms.locfileid: "122782807"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot HoloLens 2-höz

> [!NOTE]
> A szolgáltatásban HoloLens Autopilot Microsoft Endpoint Manager konfiguráció  nyilvános előzetes verzióról **általánosan elérhetőre áll át.** Minden bérlő be tudja majd állítva az Autopilotot a MEM felügyeleti központban.

A Windows Holographic 2004-es verziójától kezdődően a HoloLens 2., támogatja az Windows Autopilot [self-Deploying Mode-t az Microsoft Intune-val](/mem/autopilot/self-deploying) (a harmadik féltől származó MDM-ek nem támogatottak). A rendszergazdák konfigurálhatják a használatra készült felhasználói élményt (OOBE) a Microsoft Endpoint Manager és lehetővé tehetik a végfelhasználók számára, hogy kis vagy semmilyen interakcióval előkészítsék az eszközöket az üzleti használatra. Ennek konfigurálásával csökkenti a készletkezelési többletterhelést, az eszközök gyakorlati előkészítésének költségét és az alkalmazottak támogatási hívásait a beállítási folyamat során. További információt a Windows [Autopilot dokumentációjában](/mem/autopilot/windows-autopilot) talál.

A Surface-eszközökhöz hasonló ajánlott, hogy az ügyfelek a Microsoft [Felhőszolgáltató](https://partner.microsoft.com/cloud-solution-provider) (viszonteladó vagy terjesztő) segítségével regisztrálják az eszközöket az Autopilot szolgáltatásban a Partnerközpont. Az eszközregisztráció egyéb módjai az eszköz hozzáadásának dokumentációjában vannak ismertetve, bár a Microsoft csatornapartnereivel biztosítható a leghatékonyabb végpontok között útvonal. [](/mem/autopilot/add-devices)



Amikor egy felhasználó elindítja az AutoPilot önkiszolgáló üzembe helyezési folyamatát, az Autopilot a következő lépéseket teszi:

1. Az eszköz csatlakozása a Azure Active Directory (Azure AD) szolgáltatáshoz. Vegye figyelembe, hogy az Autopilot for HoloLens nem támogatja a Active Directory a hibrid Azure AD-csatlakozást.

1. Az Azure AD használatával regisztrálja az eszközt Microsoft Endpoint Manager (vagy egy másik MDM-szolgáltatásban).

1. Eszközre vonatkozó szabályzatok, tanúsítványok, hálózati profilok és alkalmazások letöltése és alkalmazása.

1. Az eszköz kiépítése.

1. A bejelentkezési képernyőt mutatja be a felhasználónak.

## <a name="configuring-autopilot-for-hololens-2"></a>Az AutoPilot konfigurálása HoloLens 2.

A környezet beállításhoz kövesse az alábbi lépéseket:

1. [Tekintse át az Autopilot Windows 2-es HoloLens követelményeit.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Automatikus MDM-regisztráció engedélyezése](#2-enable-automatic-mdm-enrollment)

1. (Csak az Intune esetén) [Győződjön meg arról, hogy az MDM-regisztráció nincs](/mem/intune/enrollment/enrollment-restrictions-set) letiltva a Windows eszközökön.

1. [Eszközök regisztrálása Windows Autopilotban.](#4-register-devices-in-windows-autopilot)

1. [Eszközcsoport létrehozása.](#5-create-a-device-group)

1. [Hozzon létre egy üzembe helyezési profilt.](#6-create-a-deployment-profile)

1. [Ellenőrizze a Regisztrációs állapotlap (ESP) konfigurációját.](#7-verify-the-esp-configuration)

1. [Ellenőrizze a profil állapotát a HoloLens eszközein.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. A 2. Windows Autopil HoloLens ot követelményeinek áttekintése

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Tekintse át a következő szakaszokat a Windows Autopilot-követelményekkel kapcsolatos cikkben:

- [A hálózatra vonatkozó követelmények](/mem/autopilot/networking-requirements)  
- [Licenckövetelmények](/mem/autopilot/licensing-requirements)  
- [Konfigurációs követelmények](/mem/autopilot/configuration-requirements)

**Tekintse át [a](/windows/deployment/windows-autopilot/self-deploying#requirements)Windows Autopilot Self-Deploying móddal kapcsolatos cikk "Követelmények" szakaszát.** A környezetnek meg kell felelnie ezeknek a követelményeknek, valamint a standard Windows Autopilot követelményeinek. Nem kell áttekintenünk a cikk "Lépésről lépésre" és "Ellenőrzés" szakaszát. A cikk későbbi lépései a megfelelő lépéseket biztosítanak a HoloLens.

További információ az eszközök regisztrálásának és a profilok konfigurálásának mikéntről: [4. Eszközök regisztrálása az Windows Autopilotban](#4-register-devices-in-windows-autopilot) [és a 6. Ebben a cikkben hozzon létre egy üzembe](#6-create-a-deployment-profile) helyezési profilt. Az Autopilot önkiszolgáló módú profilok konfigurálása és kezelése érdekében győződjön meg arról, hogy rendelkezik [hozzáféréssel Microsoft Endpoint Manager felügyeleti központhoz.](https://endpoint.microsoft.com)

#### <a name="review-hololens-os-requirements"></a>Tekintse át HoloLens operációs rendszer követelményeit:

- Az eszközöknek a [Holographic Windows 2004-es](hololens-release-notes.md#windows-holographic-version-2004) (19041.1103-as build) vagy újabb verziójával kell lennie. Az eszközön található buildverzió megerősítéséhez vagy a legújabb operációs rendszerre való átfedéshez használja az [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) eszközt és az eszköz perjeles [utasításait.](/hololens/hololens-recovery#clean-reflash-the-device) Vegye figyelembe, hogy a 2020. szeptember végéig Windows Holographic 1903-as verziójának telepítése már előre telepítve van. Lépjen kapcsolatba a viszonteladóval, és győződjön meg arról, hogy az Autopilot-kompatibilis eszközök ki vannak szállítva.

- Windows A Holographic 2004-es verziója csak az Autopilot over Ethernet-kapcsolatot támogatja. A bekapcsolása HoloLens az "USB-C–Ethernet" adapterrel győződjön meg arról, hogy a hálózati adapter csatlakoztatva van az **Ethernethez.** Az eszköz rendszerindításakor nincs szükség felhasználói beavatkozásra. Ha egy Autopilot-bevezetést tervez számos HoloLens eszközön, javasoljuk, hogy tervezze meg az adapter infrastruktúráját. Nem javasoljuk az USB Hubok használatát, mivel gyakran további külső gyártótól származó illesztőprogramok telepítését igénylik, amelyek nem támogatottak a HoloLens.

- [Windows Holographic 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) vagy újabb verziója támogatja az Autopilotot Wi-Fi-n keresztül, bár ethernet-adaptereket továbbra is használhat. A Wi-Fi-n keresztül csatlakoztatott eszközök esetében a felhasználónak csak a következőt kell:

     - Végig kell mennie a jeleneten
     - Nyelv és területi beállítások kiválasztása
     - Szemredúsztás
     - Hálózati kapcsolat létrehozása

- Windows A Holographic 20H2-es verziója támogatja a [Tenantlockdown CSP-t](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)és az Autopilotot, amely zárolja az eszközt a bérlőhöz, és biztosítja, hogy az eszköz véletlen vagy szándékos alaphelyzetbe állítások vagy törlések esetén is az adott bérlőhöz kötődik.  

- Győződjön meg arról, hogy az eszközök még nem tagjai az Azure AD-nek, és nincsenek regisztrálva az Intune-ban (vagy más MDM-rendszerben). Az Autopilot önkiszolgáló üzembe helyezési folyamata ezeket a lépéseket ad vissza. Ha meg kell győződni arról, hogy az eszközhöz kapcsolódó összes információ el van különülve, ellenőrizze az Eszközök lapot az Azure AD-portálon és az Intune-portálon is.  Vegye figyelembe, hogy a "Minden megcélzott eszköz Autopilot-eszközre konvertálása" funkció jelenleg nem támogatott HoloLens-eszközökön.  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Az automatikus MDM-regisztráció engedélyezése:

Ahhoz, hogy az Autopilot sikeres legyen, engedélyeznie kell az automatikus MDM-regisztrációt a Azure Portal. Ez lehetővé teszi, hogy az eszköz felhasználó nélkül regisztráljon.

A [Azure Portal](https://portal.azure.com/#home) válassza **Azure Active Directory**  ->  **(MDM és MAM)**  ->  **Microsoft Intune.** Ezután konfigurálja az **MDM-felhasználói hatókört,** és válassza az Összes **lehetőséget.**

Tekintse át az [MDM](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) automatikus regisztráció engedélyezésével kapcsolatos rövid útmutatót vagy az automatikus regisztráció gyors útmutatóját, amely további információt tartalmaz a beállításról. [](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. Győződjön meg arról, hogy az MDM-regisztráció nincs letiltva a Windows eszközökön.

Ahhoz, hogy az Autopilot sikeres legyen, meg kell győződni arról, hogy a HoloLens eszközök regisztrálva legyenek. Mivel HoloLens eszköz Windows eszköznek minősül, nincsenek regisztrációs korlátozások, amelyek blokkolni tudnák az üzembe helyezést. [Tekintse át ezt a korlátozáslistát,](/mem/intune/enrollment/enrollment-restrictions-set) és ellenőrizze, hogy regisztrálhatja-e az eszközeit.

### <a name="4-register-devices-in-windows-autopilot"></a>4. Eszközök regisztrálása Windows Autopilotban

Az első telepítés előtt az eszközöket regisztrálni kell Windows Autopilotban. Az eszközregisztrációval kapcsolatos MEM-dokumentációért lásd: Eszközök hozzáadása az [Autopilothoz.](/mem/autopilot/add-devices)  

Az eszközök regisztrálásának három elsődleges HoloLens módja van:

 - **A viszonteladó regisztrálhat eszközöket a Partnerközpont amikor ön megrendelést ad vissza.**

   > [!NOTE]  
   > Ez az eszközök Autopilot-szolgáltatáshoz való hozzáadásának ajánlott útvonala. [További információ](/mem/autopilot/partner-registration).  

 - **Támogatási [kérést küldhet közvetlenül a](hololens2-autopilot-registration-support.md) Microsoftnak.**
 - **Olvassa be a hardver kivonatát (más** néven hardverazonosítóját), és regisztrálja manuálisan az eszközt a MEM felügyeleti központban.

#### <a name="obtain-hardware-hash"></a>Hardver-kivonat beszerzése
A hardver kivonatát kétféleképpen lehet lekérni.
1. Támogatási [kérést küldhet közvetlenül a](hololens2-autopilot-registration-support.md) Microsoftnak.
2. Az eszközről lekérhető. Az eszköz rögzíti a hardver kivonatát egy CSV-fájlban az OOBE folyamat során, vagy később, amikor az eszköz tulajdonosa elindítja a diagnosztikai naplók gyűjtésének folyamatát (lásd az alábbi eljárást). Általában az eszköz tulajdonosa az első felhasználó, aki bejelentkezik az eszközre.
     > [!WARNING]
     > A 20H2 előtti buildek esetén, ha már végigment az OOBE-ban, és a telemetria Kötelezőre lett állítva, ezzel a módszerrel nem gyűjthető össze az Autopilot hardver-kivonata. Ha ezzel a módszerrel gyűjti össze a hardver-kivonatot, állítsa a Telemetria beállítást Teljesre az Gépház-alkalmazáson keresztül, majd válassza az Adatvédelem -> diagnosztika lehetőséget.

    1. Indítsa el a HoloLens 2-es eszközt.

    1. Az eszközön egyszerre nyomja le a **Power** és **Volume Down** gombokat, majd engedje el őket. Az eszköz összegyűjti a diagnosztikai naplókat és a hardver kivonatát, és egy .zip tárolja őket.

   1. Részletes információkért és egy oktató videóért, amely bemutatja, hogyan lehet ezt előre formázni, olvassa el az [Offline diagnosztika szakaszt.](hololens-diagnostic-logs.md#offline-diagnostics)

    1. Usb-C kábellel csatlakoztassa az eszközt egy számítógéphez.

    1. A számítógépen nyissa meg a Fájlkezelő. Nyissa **meg a This PC Internal Storage Documents \\ \<*HoloLens device name*> \\ \\ (Dokumentumok)** fájlt, és keresse meg AutopilotDiagnostics.zip fájlt.  

       > [!NOTE]  
       > Előfordulhat.zip hogy a fájl nem érhető el azonnal. Ha a fájl még nem áll készen, egy HoloLensDiagnostics.temp fájlt láthat a Dokumentumok mappában. A fájlok listájának frissítéséhez frissítse az ablakot.
    
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

1. Az importálás befejezése után válassza az **Eszközök Windows**  >    >  **Windows**  >  **eszközök**  >  **szinkronizálása lehetőséget.** A folyamat eltarthat néhány percig, attól függően, hogy hány eszköz van szinkronizálva. A regisztrált eszköz a Frissítés lehetőséget **választva látható.**  

   > [!div class="mx-imgBorder"]
   > ![Az eszközlista megtekintéséhez használja a Szinkronizálás és frissítés parancsot.](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. Eszközcsoport létrehozása

1. A [Microsoft Endpoint Manager központban válassza](https://endpoint.microsoft.com)a Csoportok **Új** csoport  >  **lehetőséget.**

1. A **Csoport típusa mezőben** válassza a **Biztonság** lehetőséget, majd adja meg a csoport nevét és leírását.

1. A **Tagság típusa mezőben** válassza a **Hozzárendelt vagy** a Dinamikus eszköz **lehetőséget.**

1. Tegye a következők egyikét:  

   - Ha az **előző** lépésben a **Hozzárendelt** lehetőséget választotta a Tagság típusa beállításnál, válassza a Tagok lehetőséget, majd adja hozzá az Autopilot-eszközöket a csoporthoz. A még nem regisztrált Autopilot-eszközök az eszköz sorozatszámát használva vannak listázva eszköznévként.
   - Ha az előző  **lépésben** a Dinamikus eszközök lehetőséget választotta a Tagság típusa  beállításnál, válassza a Dinamikus eszköztagok lehetőséget, majd írja be a következőhöz hasonló kódot a Speciális szabály mezőbe:
     - Ha létre szeretne hozni egy csoportot, amely az összes Autopilot-eszközt tartalmazza, írja be a következőt: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Az Intune csoportcímke-mezője az Azure AD-eszközökön az **OrderID** attribútumra van leképezve. Ha olyan csoportot szeretne létrehozni, amely tartalmazza az összes olyan Autopilot-eszközt, amely egy adott csoportcímkével (az Azure AD-eszköz rendelésazonosítóját) tartalmazza, írja be a következőt: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Ha létre szeretne hozni egy csoportot, amely tartalmazza az összes olyan AutoPilot-eszközt, amely adott rendelésazonosítóval van meg, írja be a következőt: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Ezek a szabályok az AutoPilot-eszközökre jellemző egyedi attribútumokat céloznak meg.
1. Válassza **a Mentés,** majd a Létrehozás **lehetőséget.**

### <a name="6-create-a-deployment-profile"></a>6. Telepítési profil létrehozása

1. A [Microsoft Endpoint Manager központban](https://endpoint.microsoft.com)válassza az **Eszközök Windows**  >    >  **Windows**  >  **autopilot Windows telepítési**  >    >  profilok Profil létrehozása HoloLens.
   ![A Profil létrehozása legördülő menü tartalmaz egy HoloLens elemet.](./images/hololens-ap-enrollment-profiles.png)

1. Adja meg a profil nevét és leírását, majd válassza a Tovább **lehetőséget.**  
   Megjelenik egy lista, amely a **következőt HoloLens:**. Ha ez a lehetőség nem áll rendelkezésre, a Visszajelzési lehetőségek [egyikével](hololens2-autopilot.md#feedback-and-support-for-autopilot) lépjen kapcsolatba velünk.

   > [!div class="mx-imgBorder"]
   > ![Profilnév és -leírás hozzáadása](./images/hololens-ap-profile-name.png)

1. A **OOBE (Out-of-box experience, OOBE)** oldalon a legtöbb beállítás előre konfigurálva van, hogy leegyszerűsítse az OOBE-t a kiértékeléshez. Igény szerint a következő beállításokat is konfigurálhatja:  

   - **Nyelv (Régió)**: Válassza ki az OOBE nyelvét. Javasoljuk, hogy válasszon egy nyelvet a [2. HoloLens nyelvek listájából.](hololens2-language-support.md)
   - **Billentyűzet automatikus konfigurálása:** Ha meg kell győződni arról, hogy a billentyűzet megfelel a kiválasztott nyelvnek, válassza az **Igen lehetőséget.**
   - **Eszköznév-sablon alkalmazása:** Az eszköz nevének automatikus  beállítását az OOBE során válassza az Igen lehetőséget, majd írja be a sablon kifejezését és helyőrzőit **a Név** beírása: Például adjon meg egy előtagot és egy helyőrzőt egy négyjegyű véletlenszerű `%RAND:4%` &mdash; számhoz.
     > [!NOTE]  
     > Ha eszköznév-sablont használ, az OOBE-folyamat még egyszer újraindítja az eszközt az eszköznév alkalmazása után, és mielőtt az eszközt az Azure AD-hez csatlakozta volna. Az újraindítás lehetővé teszi, hogy az új név érvénybe lép.  

   > [!div class="mx-imgBorder"]
   > ![OOBE-beállítások konfigurálása](./images/hololens-ap-profile-oobe.png)

1. A beállítások konfigurálása után válassza a Tovább **lehetőséget.**
1. A **Hatókörcímkék lapon** igény szerint hozzáadhatja a profilra alkalmazni kívánt hatókörcímkéket. További információ a hatókörcímkékről: Szerepköralapú hozzáférés-vezérlés és hatókörcímkék használata [elosztott it-hez.](/mem/intune/fundamentals/scope-tags.md) Ha elkészült, válassza a **Tovább lehetőséget.**
1. A **Hozzárendelések lapon** válassza a Kijelölt **csoportok lehetőséget a** Hozzárendelés **elemhez.**
1. A **SELECTED GROUPS (KIVÁLASZTOTT CSOPORTOK) alatt** válassza a + Select groups to include **(Csoportok kiválasztása) lehetőséget.**
1. A **Beveszni kívánt** csoportok kiválasztása listában válassza ki az Autopilot-eszközhöz létrehozott eszközcsoportot, HoloLens kattintson a Tovább **gombra.**  
  
   Ha ki szeretne zárni csoportokat, válassza a **Kizárni** kívánt csoportok kiválasztása lehetőséget, majd válassza ki a kizárni kívánt csoportokat.

   > [!div class="mx-imgBorder"]
   > ![Eszközcsoport hozzárendelése a profilhoz.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Az Áttekintés **+ létrehozás lapon** tekintse át a beállításokat, majd válassza a **Létrehozás** lehetőséget a profil létrehozásához.  

   > [!div class="mx-imgBorder"]
   > ![Ellenőrzés és létrehozás](./images/hololens-ap-profile-summ.png)

### <a name="7-verify-the-esp-configuration"></a>7. Az ESP konfigurációjának ellenőrzése

A Regisztrációs állapot lap (ESP) megjeleníti a teljes eszközkonfigurációs folyamat állapotát, amely akkor fut, amikor egy MDM által felügyelt felhasználó először jelentkezik be egy eszközre. Győződjön meg arról, hogy az ESP-konfiguráció az alábbihoz hasonló, és ellenőrizze, hogy a hozzárendelések helyesek-e.  

> [!div class="mx-imgBorder"]
> ![ESP-konfiguráció](./images/hololens-ap-profile-settings.png)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. A HoloLens állapotának ellenőrzése

1. A Microsoft Endpoint Manager központban válassza az **Eszközök Windows**  >    >  **Windows eszközök**  >  **lehetőséget.**

1. Ellenőrizze, hogy a HoloLens eszközök fel vannak-e sorolva, és hogy a profiljuk állapota **Hozzárendelve.**  

   > [!NOTE]  
   > A profil az eszközhöz való hozzárendelése eltarthat néhány percig.  

   > [!div class="mx-imgBorder"]
   > ![Eszköz- és profil-hozzárendelések.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Autopilot for HoloLens 2 Felhasználói élmény

A fenti utasítások befejezése után a HoloLens 2 felhasználó a következő folyamaton keresztül fogja üzembe HoloLens eszközeit:  

1. Az Autopilot használatához internet-hozzáférés szükséges. Az internet-hozzáféréshez a következő lehetőségek egyikét használhatja:

    - Csatlakozás az eszközt egy Wi-Fi OOBE-hálózatra, majd hagyja, hogy automatikusan észlelje az Autopilot-élményt. Ez az egyetlen alkalom, amikor az OOBE-val kell interakcióba lépnie, amíg az Autopilot-élmény egyedül be nem fejeződik. Vegye figyelembe, hogy alapértelmezés szerint HoloLens 2 várakozás 10 másodpercig az Autopilot észlelésére az internet észlelése után. Ha a rendszer 10 másodpercen belül nem észlel AutoPilot-profilt, az OOBE bemutatja a EULA-t. Ha ezzel a forgatókönyvvel találkozik, indítsa újra az eszközt, hogy újra megkísérelje észlelni az AutoPilotot. Azt is vegye figyelembe, hogy az OOBE csak akkor tud határozatlan ideig várni az AutoPilotra, ha a TenantLockdown-szabályzat be van állítva az eszközön.

    - Csatlakozás "USB-C–Ethernet" adapterek használatával csatlakoztathatja az eszközt Ethernet-kapcsolattal a vezetékes internetkapcsolat érdekében, és HoloLens 2 teljes Autopilot-élményt biztosít automatikusan.

    - Csatlakozás "USB-C–Wi-Fi" adapterekkel támogatja a vezeték nélküli internetkapcsolatot, és HoloLens 2 teljes Autopilot-élményt biztosít automatikusan.

        > [!IMPORTANT]  
       > Az Autopilothoz Wi-Fi OOBE-ban a virtuális hálózatokat használni próbáló eszközöknek a [Holographic 20H2](hololens-release-notes.md#windows-holographic-version-20h2)Windows kell lennie.
       >
       > Ethernet-adaptereket használó eszközök esetén az eszközt a box-of-box-experience (OOBE) indítása előtt kell csatlakoztatnia a hálózathoz. Az eszköz az első OOBE képernyőn határozza meg, hogy Autopilot-eszközként van-e kiépítve. Ha az eszköz nem tud csatlakozni a hálózathoz, vagy ha úgy dönt, hogy nem autopilot-eszközként létesíti az eszközt, később nem válthat AutoPilot-kiépítésre. Ehelyett újra kellene kezdenie ezt az eljárást ahhoz, hogy autopilot-eszközként kiépítse az eszközt.

1. Az eszköz automatikusan elindítja az OOBE-t. Ne használja az OOBE-t.

    > [!IMPORTANT]
    > Ne használja az OOBE-t, és ne nyomja le a bekapcsológombot a rendszer készenléti/leállítási állapotba hozása érdekében, amíg az AutoPilot folyamatban van. Ez azt okozhatja, hogy az AutoPilot-folyamat nem fejeződik be.

   Hagyja, HoloLens 2. észlelje a hálózati kapcsolatot, és engedélyezze a OOBE automatikus befejezését. Az eszköz újraindulhat az OOBE során. Az OOBE-képernyőknek az alábbihoz hasonlóknak kell lennie.

   ![OOBE ](./images/autopilot-welcome.jpg)
    ![ 1. lépés OOBE 2. lépés ](./images/autopilot-step-complete.jpg)
    ![ OOBE 3. lépés](./images/autopilot-device-setup.jpg)

1. Az OOBE végén bejelentkezhet az eszközre a felhasználónevével és jelszavával.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>TenantLockdown CSP és Autopilot

HoloLens 2 eszköz támogatja a TenantLockdown CSP-t Windows Holographic 20H2-es verziójától. Ez a CSP úgy tartja meg az eszközöket a szervezet bérlőjében, hogy az eszköz alaphelyzetbe állításán vagy perjelen keresztül is ehhez a bérlőhöz zárolja őket.

[TenantLockdown (Bérlői zárolás)](/windows/client-management/mdm/tenantlockdown-csp) A CSP lehetővé HoloLens, hogy a 2. tanúsítvány kizárólag az Autopilot használatával kötődik az MDM-regisztrációhoz. Ha a TenantLockdown CSP RequireNetworkInOOBE csomópontja true (igaz) vagy false (kezdetben beállított) értékre van állítva HoloLens 2-ben, ez az érték az újra perjelezés, az operációs rendszer frissítése stb. ellenére is az eszközön marad.

Miután HoloLens 2., a TenantLockdown CSP-k RequireNetworkInOOBE csomópontja true (igaz) értékre van állítva, az OOBE határozatlan ideig vár az Autopilot-profil sikeres letöltésére és alkalmazásra a hálózati kapcsolat után.

Miután a TenantLockdown CSP-k RequireNetworkInOOBE csomópontja true (igaz) értékre van állítva HoloLens 2. HoloLens esetében, az OOBE a következő műveleteket nem engedélyezett:

- Helyi felhasználó létrehozása futásidejű kiépítéssel 
- Azure AD-csatlakozás végrehajtása futásidejű üzembe építéssel 
- Annak kiválasztása, hogy ki az eszköz a tulajdonában az OOBE-élményben 

#### <a name="how-to-set-this-using-intune"></a>Hogyan állíthatja be ezt az Intune-nal? 
1. Hozzon létre egy egyéni OMA URI eszközkonfigurációs profilt, és az alább látható módon adja meg a true értéket a RequireNetworkInOOBE csomóponthoz.
Az OMA-URI értékének ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE kell lennie

   > [!div class="mx-imgBorder"]
   > ![Tennant zárolásának beállítása OMA-URI-n keresztül](images/hololens-tenant-lockdown.png)

1. Hozzon létre egy csoportot, és rendelje hozzá az eszközkonfigurációs profilt az eszközcsoporthoz.

1. A szinkronizálás HoloLens az előző lépésben létrehozott csoport 2. eszköztagját.  

Ellenőrizze az Intune-portálon, hogy az eszközkonfiguráció alkalmazása sikeres volt-e. Miután ez az eszközkonfiguráció sikeresen alkalmazva lett HoloLens 2. eszközön, a TenantLockdown hatása aktív lesz.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>A TenantLockdown RequireNetworkInOOBE szolgáltatásának e-HoloLens a 2. intune-nal?

1. Távolítsa el HoloLens 2. adatokat arról az eszközcsoportról, amelyhez korábban hozzárendelték a fent létrehozott eszközkonfigurációt.

1. Hozzon létre egy egyéni OMA URI-alapú eszközkonfigurációs profilt, és az alább látható módon adja meg a false értéket a RequireNetworkInOOBE beállításhoz.
Az OMA-URI értékének ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE kell lennie

   > [!div class="mx-imgBorder"]
   > ![Képernyőkép a RequireNetworkInOOBE hamisra állításával az Intune OMA URI-ján keresztül](images/hololens-tenant-lockdown-false.png)

1. Hozzon létre egy csoportot, és rendelje hozzá az eszközkonfigurációs profilt az eszközcsoporthoz. 

1. A szinkronizálás HoloLens az előző lépésben létrehozott csoport 2. eszköztagját.

Ellenőrizze az Intune-portálon, hogy az eszközkonfiguráció alkalmazása sikeres volt-e. Miután ez az eszközkonfiguráció sikeresen alkalmazva lett HoloLens 2. eszközön, a TenantLockdown hatásai inaktívak lesznek.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Mi történne az OOBE során, ha az Autopilot-profil nincs hozzárendelve egy HoloLens a TenantLockdown true (igaz) beállítása után? 
Az OOBE határozatlan ideig vár az Autopilot-profil letöltésére, és megjelenik a következő párbeszédpanel. A TenantLockdown hatásainak eltávolításához az eszközt először az eredeti bérlővel kell regisztrálni az AutoPilot használatával, és a RequireNetworkInOOBE-t az előző lépésben leírtak szerint meg kell szüntetni a TenantLockdown CSP által bevezetett korlátozások eltávolítása előtt.

![Az eszköz nézetében megtekintheti, hogy mikor van kikényszeríteni a szabályzatot az eszközön.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Ismert problémák & korlátozásai

- Egy olyan problémát vizsgálunk, amely miatt a MEM-alkalmazásban konfigurált eszközkörnyezet-alapú alkalmazástelepítés nem vonatkozik a HoloLens. [További információ az eszközkörnyezetről és a felhasználói környezet telepítéséről.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Az AutoPilot Wi-Fi-n keresztüli beállításakor előfordulhat, hogy az AutoPilot-profil nem lesz letöltve az internetkapcsolat első létesítéskor. Ebben az esetben végfelhasználói licencszerződés (EULA) lesz bemutatva, és a felhasználó folytathatja a nem Autopilot-telepítési folyamattal. Az Autopilot beállításának újrapróbálkozáshoz helyezze alvó üzemmódba az eszközt, majd indítsa el, vagy indítsa újra az eszközt, és próbálkozzon újra.
- A "Minden megcélzott eszköz Autopilot-eszközre konvertálása" funkció jelenleg HoloLens támogatott.  

### <a name="troubleshooting"></a>Hibaelhárítás

Az alábbi cikkek hasznos forrást hatnak az AutoPilot-problémák további információinak és hibaelhárításának elsajátítása érdekében, azonban vegye figyelembe, hogy ezek a cikkek az Windows 10 Desktopon alapulnak, és nem minden információ vonatkozhat a HoloLens:

- [Windows Autopilot – ismert problémák](/mem/autopilot/known-issues)
- [Eszközregisztrációs Windows hibaelhárítása a Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – Szabályzatütközések](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Visszajelzés és támogatás az AutoPilothoz

Ha visszajelzést szeretne küldeni vagy problémákat szeretne jelenteni, használja az alábbi módszerek egyikét:

- Az eszközregisztrációval kapcsolatban forduljon a viszonteladóhoz vagy a terjesztőhöz.
- Az Autopilot használatával kapcsolatos általános támogatási Windows, illetve a profil-hozzárendeléssel, csoport létrehozásával vagy a MEM-portál vezérlőivel kapcsolatos problémák esetén forduljon a Microsoft Endpoint Manager [ügyfélszolgálatához](/mem/get-support)  
- Ha az eszköze regisztrálva van az Autopilot szolgáltatásban, és a profil hozzá van rendelve a MEM-portálon, lépjen kapcsolatba HoloLens [ügyfélszolgálatával](/hololens/) (lásd a "Támogatás" kártyát). Nyisson meg egy támogatási jegyet, és ha lehetséges, az [offline](hololens-diagnostic-logs.md#offline-diagnostics) diagnosztikai naplóknak a használaton kívül (OOBE) való rögzítésével adjon meg képernyőképeket és naplókat.
- A probléma eszközről való bejelentéséhez használja a Visszajelzési központ alkalmazást a HoloLens. A Visszajelzési központ válassza a **Vállalati felügyeleti**  >  **eszköz kategóriát.**
- Ha általános visszajelzést szeretne küldeni az Autopilot for HoloLens, elküldheti ezt a [felmérést](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>AutoPilot-eszközök törlése

Előfordulhat, hogy már nem szeretne eszközt használni az AutoPilothoz, vagy egy másik bérlőhöz szeretné regisztrálni az eszközeit. Ha ezt szeretné tenni, olvassa el a h ow parancsot az[AutoPilot-eszközök törléséhez.](/mem/autopilot/add-devices#delete-autopilot-devices)