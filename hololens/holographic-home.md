---
title: A Start menü vegyes valóság kezdőlapja
description: Megtudhatja, hogyan használhatja a Start menüt, hogyan kezelheti és férhet hozzá az alkalmazásokhoz, és hogyan navigálhat a vegyes valóság kezdőlapon HoloLens eszközökön.
ms.assetid: 742bc126-7996-4f3a-abb2-cf345dff730c
ms.date: 08/07/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f9a6f1692df05e5fd8faec3da07cc85f7c6a32c7
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189171"
---
# <a name="use-the-start-menu-and-mixed-reality-home"></a>A Start menü vegyes valóság kezdőlapja

A Windows asztali környezethez hasonló, Windows Holographic a vegyes valóság kezdőlapját használja.  A Start menü alkalmazásablakokat, modern alkalmazásindítókat és 3D-s tartalmakat nyithat meg és helyezzen el a vegyes valóság kezdőlapján, és a fizikai tárhelyen való elhelyezésük is meg lesz öröklesztve.

## <a name="use-the-start-menu"></a>A Start menü

A Start menü a HoloLens megnyithatja az alkalmazásokat, láthatja a fontos állapotinformációkat, és elérheti az olyan eszközöket, mint a kamera.

Bárhol is van a HoloLens, mindig megnyithatja a Start menü a **Start kézmozdulattal.**  A HoloLens (1. generációs) indítási kézmozdulat a [bloom](https://support.microsoft.com/help/12644/hololens-use-gestures). A HoloLens 2. oldalon a [Start](hololens2-basic-usage.md#start-gesture) kézmozdulatra koppintva koppintson a menetben megjelenő Start ikonra.  A hangjával is Start menü a "Go to Start" (Ugrás az indításhoz) üzenetre.

> [!TIP]
> Ha a Start menü meg van nyitva, zárja be a Start kézmozdulattal, vagy nézze meg a Start menü és mondja a "Bezárás" szót.

A képernyő tetején Start menü Wi-Fi, akkumulátor, kötet és óra állapotjelzőit láthatja. A HoloLens 2. oldalon egy figyelő jelző is látható, amely azt mutatja, hogy az eszköz engedélyezett-e a beszéd, és figyel-e hangparancsokat. Alul található a Fénykép  és  a Videó gomb, amellyel fényképeket és videofelvételeket készíthet.  Van egy Csatlakozás **gomb** is, amely lehetővé teszi, hogy a látható adatokat kivetítje egy másik eszközre a Miracast.

### <a name="find-apps-on-start-menu"></a>Alkalmazások megkeres Start menü

A Start menü rendelkezik egy **Rögzített** alkalmazások és egy Minden alkalmazás **listával.**

- A **Rögzített alkalmazások lista** a rögzített alkalmazásokat jeleníti meg. A Rögzített alkalmazások listából  az alkalmazáscsempék kiválasztásakor megjelenő  helyi menüvel adhat hozzá és távolíthat el alkalmazásokat.

- A **Minden alkalmazás** az eszközön telepített összes alkalmazást megjeleníti.  A **Minden alkalmazás** a **Start** menü jobb oldalán található Bal gombot választva megjelenik a lista.

Mindkét alkalmazáslistán használja az  Oldal **felfelé** és a Lap lefelé gombokat a képernyő jobb oldalán Start menü lapra a listában lévő összes alkalmazás között.  Mindkét alkalmazáslista automatikusan megnyílik az eszköz-munkamenet során utoljára használt oldalra.

> [!TIP]
> A HoloLens 2. oldalon közvetlenül görgetheti az alkalmazáslistákat az indexavacsával. Csak érintse meg a listát az ujjlenyomat-tippjével, és húzza felfelé vagy lefelé.

### <a name="open-apps-from-start-menu"></a>Alkalmazások megnyitása Start menü

Az alkalmazás megnyitásához a Start menü válasszon **ki egy** **alkalmazáscsempét.** A megnyitáshoz meg is használhatja az alkalmazás nevét.

Amikor megnyit egy alkalmazást a Start menü, a következők egyike történik az alkalmazás tervezésétől függően:

- A **alkalmazás ablaka** el lesz helyezve. Az alkalmazás ezután betöltődik az ablakban, és érintőképernyőként is használható.
- A **rendszer elhelyez egy 3D-s alkalmazásindítót** egy modern alkalmazáshoz. Ezután ki kell **választania a** indítót a modern alkalmazás megnyitásához.
- A rendszer egy alkalmazásablakot helyez el, amely **egy** modern alkalmazás indítójaként működik. A modern alkalmazás automatikusan elindul.

A vegyes valóságú kezdőlapon elhelyezett alkalmazásablakok és alkalmazásindítók addig maradnak, amíg el nem távolítja őket.  Kényelmes parancsikont kínálnak a világ számára az alkalmazásablakok használatára vagy a modern alkalmazások elindítására anélkül, hogy újra meg kell nyitni őket a Start menü. 

> [!NOTE]
>A telefonon való alkalmazáshoz hasonló a rendszererőforrások kezelése automatikusan történik a HoloLens.  Egy új modern alkalmazás megnyitásakor például az összes többi futó alkalmazás azonnal inaktívvá válik. A rendszererőforrások felszabadítása érdekében nincs szükség az alkalmazásablakok és -indítók eltávolítására a vegyes valóságban. 

## <a name="using-apps-on-hololens"></a>Alkalmazások használata HoloLens

A HoloLens alkalmazás ablaknézetet vagy modern nézetet használhat. Az alkalmazásablak nézetben az alkalmazás egyszerűen megjeleníti annak tartalmát egy ablakban. A modern nézetben az alkalmazások távolodnak a vegyes valóságú otthontól, ahol a tartalmai a fizikai környezetben is megjeleníthetőek. Az alkalmazások mindkét nézetet is választhatják.

### <a name="use-app-windows"></a>Alkalmazásablakok használata

A HoloLens (1. generációs) alkalmazásablakok a Vegyes valóság kezdőlapon vannak elhelyezve és használva, ahol a saját tükre lehet [áthelyezni,](hololens1-basic-usage.md#move-resize-and-rotate-apps) átméretezni és elforgatni őket. Az alkalmazásablakok tekintetsel és kézmozdulattal való használata mellett a csatlakoztatott egérrel és billentyűzettel Bluetooth is használhatók.

A HoloLens 2. oldalon az alkalmazásablakok vegyes valóságú kezdőlapon való használata mellett egyszerre egy alkalmazásablakot is használhat egy modern alkalmazásban. Az alkalmazásablakokat a  Követés módba is be lehet tenni, ahol az Ön előtt marad, miközben jár. Amikor megnyit egy alkalmazásablakot egy modern alkalmazáson belül, az automatikusan Követés **módban** nyílik meg. Az [alkalmazásablakokat](hololens2-basic-usage.md#move-resize-and-rotate-holograms) közvetlenül mozgathatja, átméretezheti és elforgathatja a vegyes valóság otthonában és egy modern alkalmazásban.

> [!NOTE]
>
> - Egyszerre legfeljebb három alkalmazásablak lehet aktív a vegyes valóságú otthonban. Többet is megnyithat, de csak három marad aktív.
> - Ha egy alkalmazásablak nem aktív, akkor az aktív ablakhoz képest sötétül jelenik meg.  Néhány tartalom helyett csak az alkalmazás ikonja jelenik meg.  Inaktív ablak aktiválásához egyszerűen **jelölje ki.**
> - Minden megnyitott alkalmazás egyszerre egy aktív ablakkal is Microsoft Edge, amely legfeljebb három lehet.

### <a name="close-apps"></a>Alkalmazások bezárása

Ha egy alkalmazásablakot használó alkalmazást be kell zárnia, egyszerűen zárja be az alkalmazásablakot a címsor **Bezárás** gombjával.  Az ablakra megjelenik a "Bezárás" szó is.

A modern nézetet használó alkalmazásokból való kilépéshez használja a Start kézmozdulatot a **Start menü,** majd válassza a **Mixed reality kezdőlap gombját.**

Ha egy modern alkalmazás hibás állapotban van, és újra kell indítania, akkor az alkalmazást először teljesen leállíthatja úgy, hogy bezárja a vegyes valóságú kezdőlapon a indítóját, majd elindítja azt a Start menü.

### <a name="default-app-picker"></a>Alapértelmezett alkalmazásválasztó

Az [Windows Holographic 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1)verziója esetén, amikor aktivál egy hivatkozást, vagy egynél több telepített alkalmazással nyit meg egy fájltípust, amely támogatja azt, egy új ablak nyílik meg, amely arra kéri, hogy válassza ki, melyik telepített alkalmazás kezelje a fájlt vagy a hivatkozástípust. Ebben az ablakban azt is kiválaszthatja, hogy a kiválasztott alkalmazás kezelje-e az "Egyszer" vagy "Mindig" hivatkozástípust.

![Alkalmazásválasztó ablak.](images/default-app-picker.png)

Ha az "Always" (Mindig) lehetőséget választja, de később módosítani szeretné, hogy melyik alkalmazás kezeljen egy adott fájlt vagy hivatkozástípust, visszaállíthatja a mentett alapértelmezett beállításokat a **Gépház > alkalmazásokban.** Görgessen az oldal aljára, és válassza a Clear (Ürítés) gombot az "Alapértelmezett alkalmazások fájltípusokhoz" és/vagy "Default apps for link types" (Alapértelmezett alkalmazások hivatkozástípusokhoz) alatt.  Az asztali számítógépek hasonló beállításával ellentétben az egyes fájltípusokat nem lehet alaphelyzetbe állítani.

### <a name="per-app-volume-control"></a>Alkalmazásonkénti kötetvezérlés

A [Windows Holographic 21H1](hololens-release-notes.md#windows-holographic-version-21h1)verziójával a felhasználók manuálisan módosíthatja az egyes alkalmazások kötetszintjeiket. Így a felhasználók jobban azokra az alkalmazásokra összpontosítanak, amelyekre szükségük van, vagy jobban hallanak több alkalmazás használata esetén. Például le kell kapcsolni egy alkalmazás mennyiségét, miközben egy másik személyt hív meg távsegítségért egy másikban.

Egy adott alkalmazás kötetének beállításhoz lépjen a **Gépház** System Sound elemre, majd a Speciális hangbeállítások alatt válassza az Alkalmazáskötet és az  ->    ->   **eszközbeállítások lehetőséget.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

## <a name="related-info"></a>Kapcsolódó információ

[Alkalmazások megkerese, telepítése és eltávolítása a Microsoft Store](holographic-store-apps.md)
