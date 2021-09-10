---
title: Alkalmazások megkeresheti, telepítheti és eltávolíthatja őket
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
ms.openlocfilehash: 3442da500e7554d7f97db2178cbaceeecad143ac
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427053"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Alkalmazások megkeresheti, telepítheti és eltávolíthatja őket a Microsoft Store

A Microsoft Store az alkalmazásokkal és játékokkal HoloLens. Amikor a saját üzletében az Áruházat HoloLens, minden ott látható alkalmazás futni fog rajta.

A HoloLens 2D nézetet vagy holografikus nézetet használhatnak. A 2D nézetet használó alkalmazások windowsosak, és az Ön köré is el lehet őket különülni. A holografikus nézetet használó alkalmazások körülveszi, és ön lesz az egyetlen alkalmazás, amit lát.

HoloLens számos meglévő alkalmazást támogat a Microsoft Store, valamint a kifejezetten a HoloLens.  Ez a cikk a Microsoft Store.

További információ az egyéni alkalmazások telepítéséről és futtatásáról: [Egyéni holografikus alkalmazások.](holographic-custom-apps.md)

## <a name="find-apps"></a>Alkalmazások megkerese

Nyissa meg a Microsoft Store a **Start menüből.** Ezután keresse meg az alkalmazásokat és játékokat. Hangparancsok [](hololens-cortana.md) használatával a kereséshez mondja ki a "Search" (Keresés) üzenetet, a keresőablak megnyitása után a "Start dictating" (Diktálás megkezdése) üzenet jelenik meg, majd amikor a rendszer kéri, kezdje el kiadni a keresési kifejezéseket.

> [!NOTE]
> A HoloLens rendszerkövetelményei az alkalmazás build architektúrája alapján vannak megszabadulva. Ha az HoloLens-hoz készült alkalmazás buildje (1. generációs) nem lett frissítve az áruházban egy újabb UWP-re, hogy tartalmazza az ARM architektúracsomagot, akkor a 2. generációs HoloLens nem lesz elérhető. Hasonlóképpen, ha egy HoloLens 2-es alkalmazás nem tartalmazza az x86 architektúracsomagot, az nem lesz elérhető HoloLens (1. generációs) eszközökön. HoloLens eszközarchitektúrák:
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

Az alkalmazások letöltéséhez be kell jelentkeznünk egy Microsoft-fiók. Egyes alkalmazások ingyenesek, és azonnal letölthetők. A vásárlást igénylő alkalmazások esetében be kell jelentkeznie az Áruházba a Microsoft-fiók és érvényes fizetési módgal kell lennie.

> [!NOTE]
> A fióknak, Microsoft Store kell lennie a bejelentkezett fiókkal. Ha munkahelyi vagy iskolai fiókot használ a HoloLens akkor előfordulhat, hogy be kell jelentkeznie személyes fiókjával az Áruházbeli alkalmazásban a vásárláshoz.

> [!TIP]
> A fizetési mód beállításához [](https://account.microsoft.com/) válassza a Fizetési account.microsoft.com **lehetőséget& fizetési** lehetőség Fizetési  >    >  **lehetőség hozzáadása lehetőséget.**

1. A [ **Start menü megnyitásához**](holographic-home.md)hajtson végre egy [Indítás](/hololens/hololens2-basic-usage#start-gesture) kézmozdulatot vagy [bloom](hololens1-basic-usage.md) kézmozdulatot a HoloLens (1. gen).

1. Válassza ki Microsoft Store alkalmazást. Az Áruházbeli alkalmazás megnyitása után:
   1. Az alkalmazások kereséséhez használja a keresősávot.
   1. Válassza ki a kifejezetten a HoloLens alkalmazásokra készült alapvető alkalmazásokat a kiválasztott kategóriák egyikében.
   1. Az Áruház alkalmazás jobb felső részen válassza a  **"..."** gombot, majd a Saját könyvtár lehetőséget a korábban megvásárolt alkalmazások megtekintéséhez.

1. Válassza **a Lekért** **vagy** Telepítés lehetőséget az alkalmazás oldalán (előfordulhat, hogy vásárlásra van szükség).

### <a name="install-microsoft-onedrive-pwa-app"></a>Az Microsoft OneDrive PWA telepítése

Előfeltételek: A felhasználó már csatlakozott HoloLens 2. eszközhöz a munkahelyi bérlőhöz.

1. Nyissa meg a Start menüt, és indítsa el az Edge böngészőt.

    ![Start menü](images/office-pwa-1.jpg)

1. A saját HoloLens a oldalon, [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) és adja meg a munkahelyi fiók hitelesítő adatait

    ![Munkahelyi bejelentkezés](images/office-pwa-2.jpg)

1. Miután sikeresen bejelentkezett az OneDrive webportálra, várjon 30–60 másodpercet, amíg PWA gombra.

    ![PWA telepítés gomb](images/office-pwa-3.jpg)

1. Kattintson a PWA gombra, és telepítse az alkalmazást

    ![Telepítési kérés](images/office-pwa-4.jpg)

1. Zárja be az Edge böngészőt, és a Start menü kattintson a **Minden** alkalmazás  gombra, és indítsa el a OneDrive PWA címkével Microsoft OneDrive

    ![Minden alkalmazás mindkét alkalmazást.](images/office-pwa-5.jpg)

> [!NOTE]
> A "Microsoft OneDrive" az a PWA, ahol "OneDrive" a régebbi UWP.

1. Ezután láthatja a saját OneDrive fájlokat.

    ![OneDrive PWA](images/office-pwa-6.jpg)

Lásd még: [Az OneDrive feltöltésének engedélyezése](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>Alkalmazások frissítése

Ha frissítenie kell egy, a Microsoft Store telepített alkalmazást, frissítheti az alkalmazást a Microsoft Store alkalmazásból. Az alkalmazáshoz telepített Microsoft Store Vállalatoknak frissítheti ezeket az alkalmazásokat a Microsoft Store Vállalatoknak.

1. A [ **Start menü megnyitásához**](holographic-home.md)hajtson végre egy [Indítás](/hololens/hololens2-basic-usage#start-gesture) kézmozdulatot vagy [bloom](hololens1-basic-usage.md) kézmozdulatot a HoloLens (1. gen).

1. Válassza ki az Áruház alkalmazást.

1. Keresse meg az Áruház alkalmazás jobb felső sarokban.

1. Válassza a **"..."** vagy a "További részletek" gombot.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store alkalmazás képernyőképe.](images/store-update-1.png)

1. Válassza **a Letöltések és frissítések lehetőséget.**
    1. Ha az eszköz korábban frissítéseket azonosított, előfordulhat, hogy egy lefelé mutató nyíl és egy szám jelöli a függőben lévő frissítéseket.

1. Válassza a **Frissítések lekérte lehetőséget.** Az eszköz most frissítéseket keres, és letölti és telepíti őket.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store képernyőképe a frissítések lekért alkalmazásról.](images/store-update-2.png.jpg)

> [!NOTE]
> Ha az eszközön található alkalmazásokat a szervezet terjesztette, ugyanezekkel a kereskedelmi alkalmazáskezelési módszerekkel frissíthetők. Ha ez az Ön helyzetére vonatkozik, további információt a kereskedelmi alkalmazások üzembe helyezésének [áttekintésében talál.](app-deploy-overview.md)
>
> Ha egy saját telepítésű vagy üzembe helyezett egyéni alkalmazást szeretne frissíteni, ugyanezt a módszert kell használnia az alkalmazás frissített verziójával is. Az egyéni alkalmazások telepítésével és futtatásával kapcsolatos további információkért olvassa el az [egyéni holografikus alkalmazásokat.](holographic-custom-apps.md)

## <a name="uninstall-apps"></a>Alkalmazások eltávolítása

Az alkalmazások háromféleképpen távolíthatók el. Az alkalmazásokat eltávolíthatja a Microsoft Store, Start menü vagy a Gépház.

> [!WARNING]
> Nem távolíthat el rendszeralkalmazást vagy a Microsoft Store magát.

> [!IMPORTANT]
> Ha a HoloLens 2 felhasználója több felhasználóval rendelkezik, az alkalmazás eltávolításához be kell jelentkeznie az alkalmazást telepítő felhasználóként.

### <a name="uninstall-from-the-microsoft-store"></a>Eltávolítás a Microsoft Store

Nyissa meg Microsoft Store a **Start menüben,** majd keresse meg az eltávolítani kívánt alkalmazást.  Az Áruház lapon minden telepített alkalmazás rendelkezik egy **Eltávolítás gombbal.**

### <a name="uninstall-from-the-start-menu"></a>Eltávolítás a Start menü

A **Start menüben** vagy a **Minden alkalmazás** nyissa meg az alkalmazást. Válassza ki és tartsa lenyomva, amíg meg nem jelenik a menü, majd válassza az **Eltávolítás lehetőséget.**

### <a name="uninstall-from-settings"></a>Eltávolítás a Gépház

A **Start menüben** válassza az Alkalmazások **Gépház > lehetőséget.** Keresse meg az alkalmazást a listában, jelölje ki, majd kattintson az **Eltávolítás gombra.**

Ha nem sikerül eltávolítania egy alkalmazást, [visszajelzést](/hololens/hololens-feedback) küldhet a Visszajelzési központ.
