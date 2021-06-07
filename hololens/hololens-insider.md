---
title: Belső előzetes verzió a Microsoft HoloLens
description: Ismerje meg az Insider-buildek első lépéseit, és adjon értékes visszajelzést a HoloLens következő fő operációsrendszer-frissítésével kapcsolatban.
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
ms.openlocfilehash: 8545b5f23dc81c194b68ea8b40feb83e525dfdf7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378132"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Belső előzetes verzió a Microsoft HoloLens

Üdvözöljük a HoloLenshez elérhető insider preview buildek legújabb verziójában! Az első lépések [egyszerűek,](hololens-insider.md#start-receiving-insider-builds) és értékes visszajelzést adhatunk a HoloLens következő jelentős operációsrendszer-frissítésével kapcsolatban.

## <a name="windows-insider-release-notes"></a>Windows Insider kibocsátási megjegyzések

Izgatottan várjuk, hogy ismét új funkciókkal kezdhetjük el a Windows Insiderst. Az új buildek a fejlesztői és a bétaverziós csatornákon lesznek elérhetőek a legújabb frissítésekért. Ezt az oldalt folyamatosan frissítjük, ahogy további funkciókat és frissítéseket adunk hozzá a Windows Insider buildhez. Legyen izgatott, és készen áll arra, hogy ezeket a frissítéseket a valóságba keverje. 

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive munkahelyi vagy iskolai kameratekercs feltöltése

*A 20346.1402-es buildben bevezetett*

Új funkciót adtunk hozzá a HoloLens 2 Beállítások alkalmazáshoz, amely lehetővé teszi az ügyfelek számára, hogy automatikusan feltöltsön vegyes valóságú fényképeket és videókat az eszköz Pictures > Camera Roll mappájában a megfelelő OneDrive munkahelyi vagy iskolai mappába. Ez a funkció a HoloLens 2 [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) alkalmazásában található szolgáltatásbeli hézagokat teszi lehetővé, amely csak az ügyfél személyes tárhelyére (és a munkahelyi vagy iskolai fiókjukba) való automatikus kameratekercs-feltöltést Microsoft-fiók támogatja.

**Működés**

- A **"Kamera feltöltése> funkció** engedélyezéséhez látogasson el > System > Mixed Reality Camera (Kamera feltöltése) lapra.
- Ennek a funkciónak  a Be állásba való beállításával az eszközön rögzített vegyes valóságú fényképek és videók automatikusan várólistára kerülnek a OneDrive munkahelyi vagy iskolai fiókjának Pictures > Camera Roll mappájába való feltöltéshez.
    >[!NOTE]
    >A funkció engedélyezése előtt rögzített  fényképek és videók nem kerülnek a várakozási sorba a feltöltéshez, így manuálisan kell feltölteni őket.
- A Beállítások lapon megjelenő állapotüzenet megjeleníti a függőben lévő fájlok számát (vagy elolvassa a "OneDrive naprakész" állapotot, ha az összes függőben lévő fájl fel lett töltve).
- Ha aggódik a sávszélesség miatt, vagy bármilyen okból "szüneteltetni" szeretné  a feltöltést, a funkciót kikapcsolhatja. A funkció ideiglenes letiltása biztosítja, hogy a feltöltési üzenetsor tovább nő, miközben új fájlokat ad hozzá a Camera Roll mappához, de a fájlok feltöltése addig nem folytatódik, amíg újra nem engedélyezi a funkciót.
- A rendszer először a legújabb fájlokat tölti fel (utolsóként, elsőként ki).
- Ha a OneDrive-fiókjában problémák vannak (például a jelszó módosítása után), megjelenik a Javítás **most** gomb a Beállítások lapon.
- Nincs maximális fájlméret, de vegye figyelembe, hogy a nagy fájlok feltöltése hosszabb időt fog igénybe venni (különösen akkor, ha a feltöltési sávszélesség korlátozott). Ha egy nagy méretű fájl feltöltése közben szünetelteti vagy kikapcsolja a feltöltést, az azonnal megszakítja a feltöltést. A feltöltés a funkció újraindításakor újraindul; A rendszer nem veszíti el a fájlokat, de a részleges feltöltést a rendszer elveti.

**Ismert problémák és kikötések**

- Ez a beállítás nem rendelkezik beépített szabályozással az aktuális sávszélesség-használat alapján. Ha a sávszélességet maximalizálni kell egy másik forgatókönyvhöz, kapcsolja ki manuálisan a beállítást. A feltöltés fel lesz függesztve, de a funkció továbbra is figyeli a Camera Roll újonnan hozzáadott fájljait. Engedélyezze újra a feltöltést, ha készen áll a folytatásra.
- Ezt a funkciót engedélyezni kell az eszközön lévő összes felhasználói fiókhoz, és csak az eszközre jelenleg bejelentkezett felhasználó fájljait tudja aktívan feltölteni.
- Ha valós időben készít fényképeket vagy videókat, miközben a Beállítások lapon figyeli a feltöltések számát, vegye figyelembe, hogy a függőben lévő fájlok száma nem változik, amíg az aktuális fájl feltöltése be nem fejeződik.
- A feltöltés szünetel, ha az eszköz elalszik vagy ki van kapcsolva. A függőben lévő feltöltések befejezéséhez aktívan használja az eszközt, amíg a Beállítások lap el nem olvassa a "OneDrive naprakész" adatokat, vagy módosítsa a **Power & beállításait.**

## <a name="start-receiving-insider-builds"></a>Insider-buildek fogadásának kezdete
> [!NOTE]
> Ha a közelmúltban nem frissített, indítsa újra az eszközt az állapot frissítéséhez, és szerezze be a legújabb buildet.
> - Az "Eszköz újraindítása" hangparancs jól működik. 
> - Az újraindítás gombot a Beállítások/beállítások/beállítások Windows Insider Program.
>
> Előfordulhat, hogy egy hiba történt a háttérben, amely miatt ön is találkozhatott, így újra a útjára fog menni.

HoloLens 2-eszközön válassza a Beállítások  >  **frissítése & Security**  >  **Windows Insider Program** **az Első lépések lehetőséget.** Csatolja a regisztrációhoz használt fiókot a Windows Insider.
A Windows Insider mostantól a Csatornákra költözik. A **Gyors** kör lesz a **fejlesztői** csatorna, a **Lassú** kör lesz a **Béta csatorna,** a kiadási **előnézeti** kör pedig a kiadási **előnézeti csatorna** lesz. A leképezés a következő: Windows Insider magyarázata További információ: Introducing Windows Insider Channels on Windows Blogs (A Windows blogok Windows Insider ![ ](images/WindowsInsiderChannels.png) [csatornái).](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)
Ezután válassza a **Windows** aktív fejlesztése lehetőséget, válassza ki, hogy szeretné-e megkapni a **Dev Channelt** vagy Béta csatorna **buildeket,** és tekintse át a program feltételeit.
A **befejezéshez válassza > Újraindítás most** lehetőséget. Miután az eszköz újraindult, a Beállítások > **Update & Security > Frissítések** keresése lapon lekért legújabb buildet.
### <a name="update-error-0x80070490-work-around"></a>Hiba 0x80070490 hiba a hibakódok között
Ha frissítési hibát 0x80070490 a fejlesztői vagy a bétaverziós csatornán való frissítéskor, próbálkozzon a következő rövid távú munkával. Ez magában foglalja a belső csatorna áthelyezését, a frissítés be- és vissza mozgatát.
#### <a name="stage-one---release-preview"></a>Első fázis – Előzetes verzió
1.  Beállítások, Biztonsági & frissítése, majd Windows Insider Program a Kiadási **előnézeti csatorna lehetőséget.**
2.  Beállítások, Biztonsági & frissítése, Windows Update, **Frissítések keresése.** A frissítés után folytassa a második fázisra.
#### <a name="stage-two---dev-channel"></a>Második fázis – Fejlesztői csatorna
1. Beállítások, Biztonsági & frissítése, majd Windows Insider Program Dev **Channel lehetőséget.**
2. Beállítások, Biztonsági & frissítése, Windows Update, **Frissítések keresése.**
## <a name="ffu-download-and-flash-directions"></a>FFU letöltési és flash utasítások
Az aláírt ffu repülőjárattal való teszteléshez először fel kell oldania az eszköz zárolását, mielőtt a repülőjárat aláírt ffu-ját felrakná.
1. Pc-n:
    1. Töltse le a ffu-t a számítógépére a [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) ről.
    
    1. Telepítse az ARC -t (Speciális helyreállítási társ) a következő Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. A HoloLensben – Flight Unlock: Nyissa meg a **Beállítások** frissítése &  >  **Security**  >  **Windows Insider Program** majd regisztráljon, indítsa újra az eszközt.
1. Flash FFU – Most már az ARC használatával is flashlheti a repülőjárat aláírt FFU-ját.
### <a name="provide-feedback-and-report-issues"></a>Visszajelzés küldése és problémák jelentése
A HoloLensben [Visszajelzési központ](hololens-feedback.md) alkalmazással visszajelzést küldhet, és jelentést küldhet a problémákról. A Visszajelzési központ biztosítja, hogy minden szükséges diagnosztikai információ megtalálható, hogy a mérnökök gyorsan hibakeresést és megoldást tudjanak biztosítani a problémára.  A HoloLens kínai és japán verziójával kapcsolatos problémákat ugyanúgy kell jelenteni.
> [!NOTE]
> Mindenképpen fogadja el azt a kérdést, amely rákérdez, hogy szeretné Visszajelzési központ szeretné-e elérni a Dokumentumok mappát (válassza az **Igen** lehetőséget, amikor a rendszer kéri).
## <a name="note-for-developers"></a>Megjegyzés fejlesztőknek
Nyugodtan fejleszthet alkalmazásokat a HoloLens Insider buildjéhez.  Az első lépésekhez tekintse meg a [HoloLens fejlesztői](https://developer.microsoft.com/windows/mixed-reality/development) dokumentációját. Ugyanezek az utasítások működnek a HoloLens Insider-buildjén is.  Használhatja a Unity és a Visual Studio a HoloLens-fejlesztéshez már használt buildeket.
## <a name="stop-receiving-insider-builds"></a>Insider-buildek fogadásának leállítása
Ha már nem szeretné megkapni a Windows Holographic Insider-buildjét, kikapcsolhatja, ha a HoloLens éles buildet futtat, vagy az Advanced Recovery Companion használatával helyreállíthatja az eszközt a Windows Holographic nem belső verziójára. [](hololens-recovery.md)
> [!CAUTION]
> Megjelenik egy ismert probléma, amely miatt az Insider Preview-ból való regisztrációt manuálisan újratelepítő felhasználók kék képernyőt tapasztalnak. Ezt követően manuálisan kell helyreállítania az eszközt. Ha szeretné részletesen ismerni, hogy ez hatással lenne-e a problémára, tekintse meg ezt az ismert [problémát.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)
Annak ellenőrzése, hogy a HoloLens éles buildet futtat-e:
1. A Settings **(Beállítások) > System (Rendszer) > About (A** rendszerről) lapon keresse meg a build számát.
1. [Az éles buildszámok kibocsátási megjegyzései.](hololens-release-notes.md)
Az Insider-buildek lemondása:
1. Éles buildet futtató HoloLensen válassza a Beállítások > **Update & Security > Windows Insider Program** lehetőséget, és válassza a Stop **Insider builds** lehetőséget.
1. Az eszköz lemondáshoz kövesse az utasításokat.
