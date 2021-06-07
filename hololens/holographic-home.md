---
title: A Start menü vegyes valóság kezdőlapja
description: Ismerje meg, hogyan használhatja a Start menüt, hogyan kezelheti és férhet hozzá az alkalmazásokhoz, és hogyan navigálhat a Vegyes valóság kezdőlapján a HoloLens-eszközökön.
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
ms.openlocfilehash: 66271911a4692dea89b6338cc8c77a05dfcaae1d
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379534"
---
# <a name="use-the-start-menu-and-mixed-reality-home"></a>A Start menü vegyes valóság kezdőlapja

A Windows rendszerű számítógépek asztali környezetben való indításakor a Windows Holographic is a vegyes valóság kezdőlapját használja.  A Start menü alkalmazásablakokat, modern alkalmazásindítókat és 3D-tartalmakat nyithat meg és helyezzen el a vegyes valóság kezdőlapján, és a fizikai térben való elhelyezésük is meg lesz öröklesztve.

## <a name="use-the-start-menu"></a>A Start menü

A Start menü holoLensben nyithatja meg az alkalmazásokat, láthatja a fontos állapotinformációkat, és elérheti az olyan eszközöket, mint a kamera.

Bárhol is van a HoloLensben, mindig megnyithatja a Start menü a **Start kézmozdulattal.**  HoloLensen (1. generációs) a Start kézmozdulat a [bloom](https://support.microsoft.com/help/12644/hololens-use-gestures). A HoloLens 2-ben a [Start](hololens2-basic-usage.md#start-gesture) kézmozdulatra koppintva koppintson a menetben megjelenő Start ikonra.  A hangjával is Start menü a "Go to Start" (Ugrás az indításhoz) üzenetre.

> [!TIP]
> Ha a Start menü meg van nyitva, zárja be a Start kézmozdulattal, vagy nézze meg a Start menü és mondja a "Bezárás" szót.

A képernyő tetején Start menü a Wi-Fi, az akkumulátor, a kötet és az óra állapotjelzői. A HoloLens 2-ben egy figyelő jelző is látható, amely azt mutatja, hogy az eszköz engedélyezett-e a beszéd, és figyel-e hangparancsokat. Alul található a Fénykép  és  a Videó gomb, amellyel fényképeket és videofelvételeket készíthet.  Egy Csatlakozás gomb **is** rendelkezésre áll, amely lehetővé teszi, hogy a látható adatokat kivetítje egy másik eszközre a Miracast használatával.

### <a name="find-apps-on-start-menu"></a>Alkalmazások megkeres Start menü

A Start menü rendelkezik egy **Rögzített alkalmazások és** egy Minden alkalmazás listával. 

- A **Rögzített alkalmazások lista** a rögzített alkalmazásokat jeleníti meg. A Rögzített alkalmazások listából  alkalmazásokat adhat hozzá és távolíthat  el az alkalmazáscsempék kiválasztásakor és a rajta található helyi menü segítségével.

- A **Minden alkalmazás** az eszközön telepített összes alkalmazást megjeleníti.  A **Minden alkalmazás** a **Start** menü jobb oldalán található Bal oldali gomb használatával megjelenik a lista.

Mindkét alkalmazáslistán használja az  Oldal **felfelé** és a Lap lefelé gombokat a képernyő jobb oldalán Start menü lapra a listában lévő összes alkalmazás között.  Mindkét alkalmazáslista automatikusan megnyílik az eszköz-munkamenet során utoljára használt oldalra.

> [!TIP]
> A HoloLens 2-ben közvetlenül görgetheti az alkalmazáslistákat az indexavacsával. Csak érintse meg a listát az ujjlenyomat-tippjével, és húzza felfelé vagy lefelé.

### <a name="open-apps-from-start-menu"></a>Alkalmazások megnyitása Start menü

Az alkalmazás megnyitásához a Start menü válasszon **ki egy** **alkalmazáscsempét.** A megnyitáshoz meg is használhatja az alkalmazás nevét.

Amikor megnyit egy alkalmazást a Start menü, a következők egyike történik az alkalmazás tervezésétől függően:

- Egy **alkalmazásablak** lesz elhelyezve. Az alkalmazás ezután betöltődik az ablakban, és érintőképernyőként használható.
- A **rendszer elhelyez egy 3D-s alkalmazásindítót** egy modern alkalmazáshoz. Ezután ki kell **választania a** indítót a modern alkalmazás megnyitásához.
- A rendszer egy alkalmazásablakot helyez el, amely **egy** modern alkalmazás indítójaként működik. A modern alkalmazás automatikusan elindul.

A vegyes valóságú kezdőlapon elhelyezett alkalmazásablakok és alkalmazásindítók addig maradnak, amíg el nem távolítja őket.  Kényelmes parancsikont kínálnak a világ számára az alkalmazásablakok használatára vagy a modern alkalmazások elindítására anélkül, hogy újra meg kell nyitni őket a Start menü. 

> [!NOTE]
>A telefonon való alkalmazáshoz hasonló a rendszererőforrások kezelése is automatikusan történik a HoloLensben.  Egy új modern alkalmazás megnyitásakor például az összes többi futó alkalmazás azonnal inaktívvá válik. A rendszererőforrások felszabadítása érdekében nincs szükség az alkalmazásablakok és -indítók eltávolítására a vegyes valóságban. 

## <a name="using-apps-on-hololens"></a>Alkalmazások használata a HoloLensen

A HoloLens-alkalmazások alkalmazásablak-nézetet vagy modern nézetet használhatnak. Az alkalmazásablak nézetben az alkalmazás egyszerűen megjeleníti annak tartalmát egy ablakban. A modern nézetben az alkalmazások távolodnak a vegyes valóságú otthontól, ahol a tartalmai a fizikai környezetben is megjeleníthetőek. Az alkalmazások mindkét nézetet is választhatják.

### <a name="use-app-windows"></a>Alkalmazásablakok használata

A HoloLens(1st gen) alkalmazásablakai a Vegyes valóság kezdőlapján helyezhetők el és használhatók, ahol a kívánt helyen [mozgathatja,](hololens1-basic-usage.md#move-resize-and-rotate-apps) átméretezheti és elforgathatja őket. Az alkalmazásablakok tekintetsel és kézmozdulattal való használata mellett Bluetooth-csatlakozóval csatlakoztatott egérrel és billentyűzettel is használhatók.

A HoloLens 2-ben az alkalmazásablakok vegyes valóságú kezdőlapon való használata mellett egyszerre egy alkalmazásablakot is használhat egy modern alkalmazásban. Az alkalmazásablakokat a  Követés módba is be lehet tenni, ahol az Ön előtt marad, miközben jár. Amikor megnyit egy alkalmazásablakot egy modern alkalmazáson belül, az automatikusan Követés **módban** nyílik meg. Az [alkalmazásablakokat](hololens2-basic-usage.md#move-resize-and-rotate-holograms) közvetlenül mozgathatja, átméretezheti és elforgathatja a vegyes valóság otthonában és egy modern alkalmazásban.

> [!NOTE]
>
> - Egyszerre legfeljebb három alkalmazásablak lehet aktív a vegyes valóságú otthonban. Többet is megnyithat, de csak három marad aktív.
> - Ha egy alkalmazásablak nem aktív, akkor az aktív ablakhoz képest sötétül jelenik meg.  Néhány tartalom helyett csak az alkalmazás ikonja jelenik meg.  Inaktív ablak aktiválásához egyszerűen **jelölje ki.**
> - Minden megnyitott alkalmazásnak egyszerre egy aktív ablaka lehet, kivéve Microsoft Edge, amely legfeljebb három lehet.

### <a name="close-apps"></a>Alkalmazások bezárása

Ha egy alkalmazásablakot használó alkalmazást be kell zárnia, egyszerűen zárja be az alkalmazásablakot a címsor **Bezárás** gombjával.  Az ablakra megjelenik a "Bezárás" szó is.

A modern nézetet használó alkalmazásokból a Start kézmozdulattal lépjen ki a **Start menü,** majd válassza a **Mixed reality kezdőlap gombját.**

Ha egy modern alkalmazás hibás állapotban van, és újra kell indítania, akkor biztos lehet benne, hogy az alkalmazás először teljesen leáll, ha bezárja a vegyes valóságú kezdőlapon a indítóját, majd elindítja azt a Start menü.

### <a name="default-app-picker"></a>Alapértelmezett alkalmazásválasztó

A [Windows Holographic 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1)verziója esetén, amikor aktivál egy hivatkozást, vagy megnyit egy fájltípust több telepített alkalmazással, amely támogatja azt, egy új ablak nyílik meg, amely felszólítja, hogy válassza ki, melyik telepített alkalmazás kezelje a fájlt vagy a hivatkozástípust. Ebben az ablakban azt is kiválaszthatja, hogy a kiválasztott alkalmazás kezelje-e az "Egyszer" vagy "Mindig" típusú fájlt vagy hivatkozástípust.

![Alkalmazásválasztó ablak](images/default-app-picker.png)

Ha az "Always" (Mindig) lehetőséget választja, de később módosítani szeretné, hogy melyik alkalmazás kezeljen egy adott fájlt vagy hivatkozástípust, visszaállíthatja a mentett alapértelmezett beállításokat a **Beállítások > Alkalmazások lapon.** Görgessen az oldal aljára, és válassza a Clear (Ürítés) gombot az "Alapértelmezett alkalmazások fájltípusokhoz" és/vagy "Default apps for link types" (Alapértelmezett alkalmazások hivatkozástípusokhoz) alatt.  Az asztali számítógépek hasonló beállításával ellentétben az egyes fájltípusokat nem lehet alaphelyzetbe állítani.

### <a name="per-app-volume-control"></a>Alkalmazásonkénti kötetvezérlés

A [Windows Holographic 21H1 verziójával](hololens-release-notes.md#windows-holographic-version-21h1)a felhasználók manuálisan módosíthatjak az egyes alkalmazások kötetszintjéhez. Így a felhasználók jobban azokra az alkalmazásokra koncentrálnak, amelyekre szükségük van, vagy jobban hallanak több alkalmazás használata esetén. Például le kell kapcsolni egy alkalmazás mennyiségét, miközben egy másik személyt hív meg távsegítségért egy másikban.

Egy adott alkalmazás kötetének beállításhoz lépjen a **Beállítások**  ->  **Rendszerhang** elemre, majd a Speciális hangbeállítások alatt válassza az Alkalmazáskötet és az  ->   **Eszközbeállítások lehetőséget.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

## <a name="related-info"></a>Kapcsolódó információ

[Alkalmazások megkerese, telepítése és eltávolítása a Microsoft Store](holographic-store-apps.md)
