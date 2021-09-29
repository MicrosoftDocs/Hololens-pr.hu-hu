---
ms.openlocfilehash: 3d6b36124cd50dcc9f420227cb7787f0d787c013
ms.sourcegitcommit: c73cdefbdb4411f6a187cc38bb2570dadeb156bf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/28/2021
ms.locfileid: "129220958"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune alkalmazás kioszksablonjának létrehozása](#tab/uisak)

### <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune alkalmazás kioszksablonjának létrehozása

1. Konfigurációs profil létrehozása <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Kioszksablon kiválasztása <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Válassza ki, hogy egy vagy több alkalmazás kioszkmódja, valamint a kioszkmódhoz milyen típusú felhasználói célcsoportot válasszon <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. A kioszkmódban futtatott alkalmazás kiválasztása <br>
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. A többi lehetőséget hagyja a következőn: <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Válassza ki, hogy mely csoportokhoz/eszközökhöz vagy felhasználókhoz legyen hozzárendelve ez a konfigurációs profil <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. Konfigurációs profil mentésének áttekintése és létrehozása
8. MDM-szinkronizálás végrehajtása az eszközről vagy az Intune-ból az eszköz konfigurációjának alkalmazáshoz. [Eszközök szinkronizálása az Intune-ból](/mem/intune/remote-actions/device-sync#sync-a-device) vagy az eszközről **Gépház ->-Fiókok -> Munkahelyi** vagy iskolai ->válassza ki a csatlakoztatott fiókot **–> Info -> Sync**
9. Jelentkezzen be célfelhasználóként a kioszkélményhez.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune alkalmazás kioszksablonjának létrehozása](#tab/uimak)

### <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune többalkalmazásos kioszksablon létrehozása

1. Konfigurációs profil létrehozása <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Kioszksablon kiválasztása <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Válassza ki, hogy egy vagy több alkalmazás kioszkmódja, valamint a kioszkmódhoz milyen típusú felhasználói célcsoportot válasszon <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. A kioszkmódban futtatott alkalmazás(k) kiválasztása <br>
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. A többi lehetőséget hagyja a következőn: <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Válassza ki, hogy mely csoportokhoz/eszközökhöz vagy felhasználókhoz legyen hozzárendelve ez a konfigurációs profil <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. Konfigurációs profil mentésének áttekintése és létrehozása
8. MDM-szinkronizálás végrehajtása az eszközről vagy az Intune-ból az eszköz konfigurációjának alkalmazáshoz. [Eszközök szinkronizálása az Intune-ból](/mem/intune/remote-actions/device-sync#sync-a-device) vagy az eszközről **Gépház ->-Fiókok -> Munkahelyi** vagy iskolai ->válassza ki a csatlakoztatott fiókot **–> Info -> Sync**
9. Jelentkezzen be célfelhasználóként a kioszkélményhez.

# <a name="microsoft-intune-custom-template"></a>[Microsoft Intune sablon létrehozása](#tab/intunecustom)

### <a name="microsoft-intune-custom-template"></a>Microsoft Intune sablon létrehozása

1. Hozzon létre xml-konfigurációt a kívánt kioszkélményhez. A [kezdéshez](../hololens-kiosk-reference.md#kiosk-xml-code-samples) itt talál példákat.

1. Egyéni konfigurációs profil létrehozása <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. Adja meg az egyéni konfigurációs profil nevét, és kattintson a "Konfigurációs beállítások" szakaszban a "Hozzáadás" gombra az OMA-URI-beállítások hozzáadásához. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. Adja meg az OMA-URI beállítások nevét.

    1. Az OMA-URI szövegmezőbe írja be a **következőt: ./Device/Vendor/MSFT/AssignedAccess/Configuration**
    1. Válassza az Adattípus lehetőséget **Sztringként.**
    1. Az érték szövegmezőbe másolja és illessze be a hozzárendelt hozzáférési konfigurációs XML-t (a példahivatkozásokat a forgatókönyv alapján tekintse meg, és szükség szerint frissítse a másolás beillesztése előtt).
    1. A beállítás és a konfiguráció mentéshez kattintson a Mentés gombra.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. Válassza ki, hogy mely csoportokhoz/eszközökhöz vagy felhasználókhoz legyen hozzárendelve ez a konfigurációs profil. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. Tekintse át és hozza létre a konfigurációs profil mentését.
1. MDM-szinkronizálás végrehajtása az eszközről vagy az Intune-ból az eszköz konfigurációjának alkalmazáshoz. [Eszközök szinkronizálása az Intune-ból](/mem/intune/remote-actions/device-sync#sync-a-device) vagy az eszközről **Gépház ->-Fiókok -> Munkahelyi** vagy iskolai ->válassza ki a csatlakoztatott fiókot **–> Info -> Sync**
1. Jelentkezzen be célfelhasználóként a kioszkélményhez.

# <a name="runtime-provisioning---multi-app"></a>[Futásidejű kiépítés – Több alkalmazás](#tab/ppkgmak)

### <a name="runtime-provisioning---multi-app"></a>Futásidejű kiépítés – Több alkalmazás

1. Hozzon létre xml-konfigurációt a kívánt kioszkélményhez. A [kezdéshez](../hololens-kiosk-reference.md#kiosk-xml-code-samples) itt talál példákat.

1. Nyissa [meg Windows Configuration Designert.](https://www.microsoft.com/store/apps/9nblggh4tx22)

1. A Kezdőlapon válassza a **Kiépítés HoloLens lehetőséget.** <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. Válassza **a HoloLens 2 eszköz kiépítése, majd** a Tovább lehetőséget. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. Nevezze el a projektet. Ha szükséges, leírást is írhat. A **folytatáshoz válassza** a Befejezés lehetőséget.

6. A képernyő bal alsó részén válassza a **Váltás speciális szerkesztőre lehetőséget.** Az Igen lehetőség kiválasztásával erősítse meg a speciális szerkesztőre **váltást.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. A bal oldalon bontsa ki a Runtime settings (Futásidejű beállítások) AssignedAccess (Hozzárendeltaccess) gombra, majd válassza a **MultiAppAssignedAccess lehetőséget.** <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. Kattintson a **Tallózás** gombra a fájlkezelő megnyitásához. Válassza ki a konfigurált kioszk xml-fájlt.

9. Válassza **az Exportálás,** majd a **Kiépítési csomag lehetőséget.**

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. Módosítsa a tulajdonos típusát a **rendszergazdai típusra.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. Kattintson háromszor a **Tovább** gombra. Ezután válassza a **Build (Build) lehetőséget.**

12. A kiépítési csomag létrehozása után nyissa meg a Kimeneti hely mappát. A .ppkg fájl a kiépítési csomag. Nem kötelező lépés: Mentse a projektet.

13. Most már alkalmazhatja a kiépítési csomagot. Alkalmazhat egy [kiépítési](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) csomagot a HoloLens, vagy alkalmazhat egy kiépítési csomagot a HoloLens [után.](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)

14. Jelentkezzen be célfelhasználóként a kioszkélményhez.

# <a name="runtime-provisioning---single-app"></a>[Futásidejű üzembe állás – Egyetlen alkalmazás](#tab/ppkgsak)

### <a name="runtime-provisioning---single-app"></a>Futásidejű üzembe állás – Egyetlen alkalmazás

1. Nyissa [meg Windows Configuration Designert.](https://www.microsoft.com/store/apps/9nblggh4tx22)

1. A Kezdőlapon válassza a **Kiépítés HoloLens lehetőséget.** <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. Válassza **a HoloLens 2 eszköz kiépítése, majd** a Tovább lehetőséget. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. Nevezze el a projektet. Ha szükséges, leírást is írhat. A **folytatáshoz válassza** a Befejezés lehetőséget.

5. A képernyő bal alsó részén válassza a **Váltás speciális szerkesztőre lehetőséget.** Az Igen lehetőség kiválasztásával erősítse meg a speciális szerkesztőre **váltást.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. A bal oldalon bontsa ki a Runtime settings (Futásidejű beállítások) AssignedAccess (Hozzárendeltaccess)et, majd válassza **az AssignedAccessSettings (Hozzárendelési beállítások) lehetőséget.** <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. Definiálja a kioszkot a szövegmezőben. Az alábbiak például egyetlen alkalmazáskioszkot hoznak létre egy LocalAccount nevű helyi fiókhoz, amely a beállítási alkalmazás.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. Válassza **az Exportálás,** majd a **Kiépítési csomag lehetőséget.** <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. Módosítsa a tulajdonos típusát a **rendszergazdai típusra.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. Kattintson háromszor a **Tovább** gombra. Ezután válassza a **Build (Build) lehetőséget.**

11. A kiépítési csomag létrehozása után nyissa meg a Kimeneti hely mappát. A .ppkg fájl a kiépítési csomag. Nem kötelező lépés: Mentse a projektet.

12. Most már alkalmazhatja a kiépítési csomagot. Alkalmazhat egy [kiépítési](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) csomagot a HoloLens, vagy alkalmazhat egy kiépítési csomagot a HoloLens [után.](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)