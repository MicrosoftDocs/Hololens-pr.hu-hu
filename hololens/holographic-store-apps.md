---
title: Alkalmazások megkerese, telepítése és eltávolítása
description: A Microsoft Store a forrás az olyan alkalmazásokhoz és játékokhoz, amelyek a HoloLens.  További információ a holografikus alkalmazások kereséséről, telepítéséről és eltávolításáról.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
manager: jarrettr
keywords: hololens, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4705112ee41ce6de0598358b9c81775f261bb2fa
ms.sourcegitcommit: 8a3f925d2bda13c095b35f14d80afdd876aa859c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/12/2021
ms.locfileid: "129800555"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Alkalmazások megkeresheti, telepítheti és eltávolíthatja őket a Microsoft Store

A Microsoft Store az alkalmazásokkal és játékokkal használt alkalmazások és játékok HoloLens. Amikor a saját alkalmazásában az Áruházat HoloLens, minden ott látható alkalmazás futni fog rajta.

A HoloLens 2D nézetet vagy holografikus nézetet használhatnak. A 2D nézetet használó alkalmazások windowsosak, és az Ön köré is el lehet őket tetsszen. A holografikus nézetet használó alkalmazások körülveszi, és ön lesz az egyetlen alkalmazás, amit lát.

HoloLens számos meglévő alkalmazást támogat a Microsoft Store, valamint a kifejezetten a HoloLens.  Ez a cikk a világ különböző oldalának holografikus Microsoft Store.

További információ az egyéni alkalmazások telepítéséről és futtatásáról: [Egyéni holografikus alkalmazások.](holographic-custom-apps.md)

## <a name="find-apps"></a>Alkalmazások megkerese

Nyissa meg a Microsoft Store a **Start menüből.** Ezután keresse meg az alkalmazásokat és játékokat. A hangparancsokkal a "Keresés" kifejezéssel kereshet, a keresési ablak megnyitása után a "Start dictating" (Diktálás megkezdése) üzenet jelenik meg, majd amikor a rendszer kéri, kezdje el kiadni a keresési kifejezéseket. [](hololens-cortana.md)

> [!NOTE]
> A HoloLens rendszerkövetelményei az alkalmazás build architektúrája alapján vannak felépítve. Ha az HoloLens (1. generációs) alkalmazás buildje nem lett frissítve az áruházban egy újabb UWP-re az ARM-architektúracsomag beépítéséhez, akkor az arm-architektúracsomag nem lesz elérhető HoloLens 2. eszközön. Hasonlóképpen, ha egy HoloLens 2-es alkalmazás nem tartalmazza az x86 architektúracsomagot, az nem lesz elérhető HoloLens (1. generációs) eszközökön. HoloLens eszközarchitektúrák:
>
> - x86 = HoloLens (1. generációs)
> - ARM = HoloLens 2

> [!NOTE]
> 2021. január 12-én a következő alkalmazások érik el a Támogatás vége a HoloLens eszközökön. Javasoljuk, hogy használja az alábbi hivatkozást az eszközén az alkalmazás webes verziójának használatára.

| Alkalmazás        | Hivatkozás                                          |
|------------|-----------------------------------------------|
| Excel mobil      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Word Mobile       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint mobil | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> Az OneDrive alkalmazás jelenleg nem támogatott az Azure AD-fiókokhoz a HoloLens. Javasoljuk, hogy töltse le Microsoft OneDrive PWA alkalmazást. [Kövesse az alábbi lépéseket az alkalmazás letöltéséhez.]

## <a name="install-apps"></a>Alkalmazások telepítése

Az alkalmazások letöltéséhez egy új fiókkal kell Microsoft-fiók. Egyes alkalmazások ingyenesek, és azonnal letölthetők. A vásárlást igénylő alkalmazásokhoz be kell jelentkeznie az Áruházba a Microsoft-fiók és érvényes fizetési módgal kell lennie.

> [!NOTE]
> A fióknak, Microsoft Store kell lennie a bejelentkezett fiókkal. Ha munkahelyi vagy iskolai fiókot használ a HoloLens akkor előfordulhat, hogy be kell jelentkeznie személyes fiókjával az Áruházbeli alkalmazásban a vásárláshoz.

> [!TIP]
> A fizetési mód beállításához [](https://account.microsoft.com/) válassza a Fizetési account.microsoft.com **lehetőséget& fizetési** lehetőség Fizetési  >    >  **lehetőség hozzáadása lehetőséget.**

1. A [ **Start menü megnyitásához**](holographic-home.md)hajtson végre egy [Indítás](/hololens/hololens2-basic-usage#start-gesture) kézmozdulatot vagy [bloom](hololens1-basic-usage.md) kézmozdulatot a HoloLens (1. gen).

1. Válassza ki a Microsoft Store alkalmazást. Az Áruház alkalmazás megnyitása után:
   1. A keresősáv használatával alkalmazásokat kereshet.
   1. Válassza ki a kifejezetten a HoloLens alkalmazásokra készült alapvető alkalmazásokat a kiválasztott kategóriák egyikében.
   1. Az Áruház alkalmazás jobb felső részen válassza a  **"..."** gombot, majd a Saját könyvtár lehetőséget a korábban megvásárolt alkalmazások megtekintéséhez.

1. Válassza **a Lekért** **vagy** Telepítés lehetőséget az alkalmazás oldalán (előfordulhat, hogy vásárlásra van szükség).

### <a name="install-microsoft-onedrive-pwa-app"></a>Az Microsoft OneDrive PWA telepítése

> [!NOTE]
> PWA nem kezelhetők és nem helyezhetők üzembe Microsoft Intune/MDM-en keresztül.

Előfeltételek: A felhasználó már csatlakozott a HoloLens 2-es eszközhöz a munkahelyi bérlőhöz.

1. Nyissa meg a Start menüt, és indítsa el az Edge böngészőt.

    ![Start menü](images/office-pwa-1.jpg)

1. A saját HoloLens a oldalon, [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) és adja meg munkahelyi fiókja hitelesítő adatait

    ![Munkahelyi bejelentkezés](images/office-pwa-2.jpg)

1. Miután sikeresen bejelentkezett az OneDrive webportálra, várjon 30–60 másodpercet, amíg PWA gombra kattintva

    ![PWA telepítés gomb](images/office-pwa-3.jpg)

1. Válassza a PWA letöltés gombot, és telepítse az alkalmazást

    ![Telepítési kérés](images/office-pwa-4.jpg)

1. Zárja be az Edge böngészőt, és a Start menü válassza a **Minden** alkalmazás gombot, és indítsa el a OneDrive PWA címkével Microsoft OneDrive 

    ![Minden alkalmazás alkalmazásokat mutatja.](images/office-pwa-5.jpg)

    > [!NOTE]
    > A "Microsoft OneDrive" az a PWA alkalmazás, ahol "OneDrive" a régebbi UWP.

1. Ezután láthatja a saját OneDrive fájlokat.

    ![OneDrive PWA](images/office-pwa-6.jpg)

Lásd még: A vállalati OneDrive automatikus [feltöltésének engedélyezése](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>Alkalmazások frissítése

### <a name="manual-updates"></a>Manuális frissítések

Ha frissítenie kell egy, a Microsoft Store telepített alkalmazást, az alkalmazást a Microsoft Store frissítheti. Az alkalmazáshoz telepített Microsoft Store Vállalatoknak frissítheti is az alkalmazásokat a Microsoft Store Vállalatoknak.

1. A [ **Start menü megnyitásához**](holographic-home.md)hajtson végre egy [Indítás](/hololens/hololens2-basic-usage#start-gesture) kézmozdulatot vagy [bloom](hololens1-basic-usage.md) kézmozdulatot a HoloLens (1. gen).

1. Válassza ki az Áruház alkalmazást.

1. Keresse meg az Áruház alkalmazás jobb felső sarokban.

1. Válassza a **"..."** vagy a "További információ" gombot.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store képernyőképe.](images/store-update-1.png)

1. Válassza **a Letöltések és frissítések lehetőséget.**
    1. Ha az eszköz korábban már azonosított frissítéseket, előfordulhat, hogy egy lefelé mutató nyíl és egy szám jelöli a függőben lévő frissítéseket.

1. Válassza a **Frissítések lekérte lehetőséget.** Az eszköz most frissítéseket keres, és be fogja állítani őket letöltésre és telepítésre.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store képernyőképe a frissítések lekért alkalmazásról.](images/store-update-2.png.jpg)

> [!NOTE]
> Ha az eszközön található alkalmazásokat a szervezet terjesztette, ugyanezekkel a kereskedelmi alkalmazáskezelési módszerekkel frissíthetők. Ha ez az Ön helyzetére vonatkozik, további információt a kereskedelmi alkalmazások üzembe [helyezésének áttekintésében talál.](app-deploy-overview.md)
>
> Ha egy saját telepítésű vagy üzembe helyezett egyéni alkalmazást szeretne frissíteni, ugyanezt a módszert kell használnia az alkalmazás frissített verziójával. Ha többet szeretne megtudni az egyéni alkalmazások telepítéséről és futtatásáról, olvassa el az [egyéni holografikus alkalmazásokat.](holographic-custom-apps.md)

### <a name="automatic-app-updates"></a>Automatikus alkalmazásfrissítések

Az automatikus frissítések Microsoft Store alkalmazásokra Microsoft Store Vállalatoknak, és csak akkor frissíthetők automatikusan, ha közvetlenül az Áruházból telepítették őket. Ha az Intune-ból telepíti, az it-csoport leküldheti a frissítéseket az MDM-ről úgy, hogy Microsoft Store Vállalatoknak az alkalmazás legújabb elérhető verziójának frissítéseit.

> [!NOTE]
> A Microsoft Store Vállalatoknak származó alkalmazások esetében be kell jelentkeznie az Áruházba, és ugyanazokkal a bérlővel kell hitelesítenie, mint amely az eszközön használt Microsoft Store Vállalatoknak katalógushoz van társítva.

#### <a name="how-automatic-updates-work"></a>Az automatikus frissítések működnek

Az automatikus alkalmazásfrissítések napi (körülbelül 24 óránkénti) frissítésre vannak ütemezve, a hálózati rendelkezésre állás függvényében. A frissítések fogadása érdekében tartsa az eszközt aktívnak vagy áramforrás-hez csatlakoztatva. Még ha az alkalmazásfrissítéseket az aktív napi használat során is letölti, azok csak akkor lesznek alkalmazva, ha a frissíthető alkalmazás már nincs használatban.

> [!TIP]
> Ha lehetséges, töltse fel az eszközt egyik napról a másikra, amíg az a vállalati hálózathoz csatlakozik. Ha a frissítések egyik napról a másikra tölthetők le és telepíthetők, kevésbé valószínű, hogy megszakítják az aktív eszközhasználatot.

#### <a name="how-it-administrators-can-control-automatic-updates"></a>Hogyan szabályozhatják a rendszergazdák az automatikus frissítéseket?

A rendszergazdák az [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) szabályzat segítségével szabályozhatják az automatikus alkalmazásfrissítéseket. Ez a szabályzat lehetővé teszi az automatikus alkalmazásfrissítések teljes engedélyezését vagy letiltását, de nem szabályozhatja a frissítések bekövetkeztét.

A [21H2](hololens-release-notes.md#windows-holographic-version-21h1)időponttól a rendszergazdák a [ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures) szabályzattal is szabályozhatják, hogy a korábbi kísérletekben nem frissíthető alkalmazások mikor indulnak újra kényszerített módon.

## <a name="uninstall-apps"></a>Alkalmazások eltávolítása

Az alkalmazások háromféleképpen távolíthatók el. Az alkalmazásokat a Microsoft Store, Start menü vagy a Gépház.

> [!WARNING]
> Nem távolíthat el rendszeralkalmazást vagy a Microsoft Store magát.

> [!IMPORTANT]
> Ha a 2. HoloLens felhasználó több felhasználóval rendelkezik, az alkalmazás eltávolításához az alkalmazást telepítő felhasználóként kell bejelentkeznie.

### <a name="uninstall-from-the-microsoft-store"></a>Eltávolítás a Microsoft Store

Nyissa meg Microsoft Store a **Start menüben,** majd keresse meg az eltávolítani kívánt alkalmazást.  Az Áruház lapon minden telepített alkalmazás rendelkezik egy **Eltávolítás gombbal.**

### <a name="uninstall-from-the-start-menu"></a>Eltávolítás a Start menü

A **Start menüben** vagy a **Minden alkalmazás** nyissa meg az alkalmazást. Válassza ki és tartsa lenyomva, amíg meg nem jelenik a menü, majd válassza az **Eltávolítás lehetőséget.**

### <a name="uninstall-from-settings"></a>Eltávolítás a Gépház

A **Start menüben** válassza az Alkalmazások **Gépház > lehetőséget.** Keresse meg az alkalmazást a listában, jelölje ki, majd kattintson az **Eltávolítás gombra.**

Ha nem sikerül eltávolítania egy alkalmazást, kérjük, [visszajelzést](/hololens/hololens-feedback) a Visszajelzési központ.
