---
title: Diagnosztikai adatok gyűjtése és használata HoloLens eszközökről
description: Megtudhatja, hogyan gyűjti, használhatja és őrizze meg a diagnosztikai adatokat a HoloLens eszközökről.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 9/12/2021
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4f62a70430d78087157b3adcdf76af53183db708
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924404"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Diagnosztikai adatok gyűjtése és használata HoloLens eszközökről

HoloLens felhasználók és rendszergazdák négy különböző módszer közül választhatnak, hogy diagnosztikai adatokat gyűjtsenek a HoloLens:

- Visszajelzési központ alkalmazás
- DiagnosticLog CSP
- Gépház alkalmazás
- Offline diagnosztika

> [!IMPORTANT]  
> Az eszközdiagnosztikai naplók személyes azonosításra alkalmas adatokat (PII-ket) tartalmaznak, például azt, hogy a felhasználó milyen folyamatokat vagy alkalmazásokat kezd el a tipikus műveletek során. Ha egy HoloLens-eszközön több felhasználó is osztozik (például a felhasználók különböző Microsoft Azure Active Directory- (Azure AD-) fiókkal jelentkeznek be ugyanannak az eszköznek), a diagnosztikai naplók több felhasználóra vonatkozó, PII-adatokat tartalmazhatnak. További információ: [Microsoft Adatvédelmi nyilatkozat.](https://privacy.microsoft.com/privacystatement)

Az alábbi táblázat a különböző gyűjtési módszereket hasonlítja össze. A metódusnevek a táblázatot követő szakaszok részletesebb információira hivatkoznak.

|Metódus |Előfeltételek |Adatok helye |Adatelérés és -használat |Adatmegőrzés |
| --- | --- | --- | --- | --- |
|[Visszajelzési központ](#feedback-hub) |Hálózat és internetkapcsolat<br /><br />Visszajelzési központ alkalmazás<br /><br />Engedély fájlok microsoftos felhőbe való feltöltéséhez |Microsoft Cloud<br /><br />HoloLens eszköz (nem kötelező) |A felhasználó segítséget kér, elfogadja a használati feltételeket, és feltölti az adatokat<br /><br />A Microsoft-alkalmazottak a használati feltételeknek megfelelő módon pillantják meg az adatokat |A felhőben az adatok a következő generációs adatvédelem (NEXT Generation Privacy, NGP) által meghatározott időtartamra maradnak meg. Ezután a rendszer automatikusan törli az adatokat.<br /><br />Az eszközön található adatokat bármikor törölheti egy  eszköztulajdonosi vagy rendszergazdai engedéllyel **rendelkező** felhasználó. |
|[Gépház Hibaelhárító](#settings-troubleshooter) |Gépház alkalmazás |HoloLens eszköz<br /><br />Csatlakoztatott számítógép (nem kötelező) |A felhasználó tárolja az adatokat, és csak a felhasználó fér hozzá az adatokhoz (kivéve, ha a felhasználó kifejezetten megosztja az adatokat egy másik felhasználóval). |Az adatok addig maradnak az eszközön, amíg a felhasználó nem törli azokat.* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |Hálózati kapcsolat<br /><br />A DiagnosticLog CSP-t támogató MDM-környezet |A rendszergazda konfigurálja a tárolási helyeket |A felügyelt környezetben a felhasználó implicit módon hozzájárul az adatok rendszergazdai hozzáféréséhez.<br /><br />A rendszergazda konfigurálja a hozzáférési szerepköröket és engedélyeket. | Az adatok a felhőalapú tárolóban maradnak, és a rendszergazda konfigurálja az adatmegőrzési szabályzatot. |
|[Offline diagnosztika](#offline-diagnostics) |Eszközkonfiguráció:<ul><li>Bekapcsolva és csatlakoztatva a számítógéphez</li><li>A Power és a Volume gomb működik</li></ul> |HoloLens eszköz<br /><br />Csatlakoztatott számítógép |A felhasználó tárolja az adatokat, és csak a felhasználó fér hozzá az adatokhoz (kivéve, ha a felhasználó kifejezetten megosztja az adatokat egy másik felhasználóval). |Az adatok addig maradnak az eszközön, amíg a felhasználó nem törli azokat. |

* A végfelhasználó felelős azért, hogy felelősségteljesen megossa a naplókat valaki másval. Ezek a fájlok elsősorban az ügyfélszolgálattal és az ügyfélszolgálattal való kapcsolatfelvételkor hasznosak.  

## <a name="feedback-hub"></a>Visszajelzési központ

A HoloLens felhasználók a Microsoft Visszajelzési központ asztali alkalmazással diagnosztikai adatokat küldhetnek a Microsoft ügyfélszolgálata. A részletekért és a teljes útmutatásért lásd: [Visszajelzés küldése.](hololens-feedback.md)  

> [!NOTE]  
> **Kereskedelmi vagy vállalati felhasználók:** Ha a Visszajelzési központ alkalmazással jelenti az MDM-hez, a kiépítéshez vagy bármely más eszközkezelési aspektushoz kapcsolódó problémát, módosítsa az alkalmazáskategóriát Enterprise **Management** Device (Vállalati felügyeleti eszköz)  >  **kategóriára.**

>[!IMPORTANT]
> Annak érdekében, hogy a lehető legjobb adatokat biztosítsa a problémák megoldásához, javasoljuk, hogy az eszköztelemetelemetiát választhatóra **állítsa.** Ezt az értéket a használaton belüli használatra (OOBE) vagy a Gépház **állíthatja** be. Ha ezt a következővel Gépház meg, válassza a **Start > Gépház > Privacy > App Diagnostics > on lehetőséget.**

### <a name="prerequisites"></a>Előfeltételek

- Az eszköz hálózathoz csatlakozik.
- A Visszajelzési központ alkalmazás elérhető a felhasználó asztali számítógépén, és a felhasználó fájlokat tölthet fel a Microsoft-felhőbe.

### <a name="data-locations-access-and-retention"></a>Adathelyek, hozzáférés és megőrzés

A használati feltételek Visszajelzési központ a felhasználó kifejezetten beleegyezik az adatok tárolásába és használatára (a szerződés által meghatározottak szerint).

A Visszajelzési központ két helyet biztosít a felhasználó számára a diagnosztikai adatok tárolására:

- **A Microsoft-felhő.** A felhasználó által a Visszajelzési központ alkalmazással feltöltött adatokat a rendszer a következő generációs adatvédelmi (NGP) követelményeknek megfelelő napokig tárolja. A Microsoft-alkalmazottak NGP-kompatibilis megjelenítővel férhetnek hozzá az információkhoz ebben az időszakban.

   > [!NOTE]  
   > Ezek a követelmények az összes kategória összes Visszajelzési központ vonatkoznak.

- **A HoloLens eszköz.** Amikor jelentést küld a Visszajelzési központ, a felhasználó kiválaszthatja a Visszajelzés küldésekor létrehozott diagnosztikai és mellékletek helyi **másolatának mentése lehetőséget.** Ha a felhasználó ezt a lehetőséget választja, a Visszajelzési központ tárolja a diagnosztikai adatok másolatát a HoloLens eszközön. Ezek az információk továbbra is elérhetők maradnak a felhasználó (vagy bárki számára, aki ezt a fiókot használja a HoloLens). Az adatok törléséhez a  felhasználónak  Eszköztulajdonos vagy Rendszergazda jogosultsággal kell rendelkeznie az eszközön. A megfelelő engedélyekkel rendelkező felhasználók bejelentkeznek a Visszajelzési központ, kiválasztják **Gépház** Diagnosztikai naplók megtekintése lehetőséget, és  >  törölhetik az adatokat.

## <a name="settings-troubleshooter"></a>Gépház Hibaelhárító

A HoloLens felhasználó az eszközön **Gépház** alkalmazással elháríthatja a problémákat, és diagnosztikai adatokat gyűjthet. Ehhez kövesse az alábbi lépéseket:

1. Nyissa meg a Gépház alkalmazást, és válassza az **Update & Security Troubleshoot**(Biztonsági &  >  **frissítése)** lapot.
1. Válassza ki a megfelelő területet, majd válassza az **Indítás lehetőséget.**
1. Reprodukálja a problémát.
1. Miután reprodukálta a problémát, térjen vissza a Gépház, majd válassza a **Leállítás lehetőséget.**

A felhasználók a tartalék diagnosztika viselkedését  is konfigurálhatja a Gépház alkalmazásból. A beállítás **konfiguráláshoz lépjen > Adatvédelem -> lapra.**
> [!NOTE]
> Ha az eszközhöz MDM-szabályzat van konfigurálva, a felhasználó nem tudja felülbírálni ezt a viselkedést.

### <a name="os-update-troubleshooter"></a>Operációsrendszer-frissítés hibaelhárítója

A [Holographic Windows, 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) és újabb verziókban:
- A Gépház alkalmazás korábbi hibaelhárítói mellett egy új hibaelhárítót is hozzáadtunk az új Gépház operációsrendszer-frissítésekhez. Lépjen a **Gépház -> Update & Security -> Troubleshoot -> Windows Update** (Frissítés hibaelhárítása) lapra, és válassza az Indítás **lehetőséget.** Ez lehetővé teszi a nyomkövetések gyűjtését az operációsrendszer-frissítésekkel kapcsolatos probléma reprodukálása során, így jobb hibaelhárítást tud nyújtani az IT-hez vagy a támogatáshoz.

### <a name="prerequisites"></a>Előfeltételek

- A **Gépház** alkalmazás telepítve van az eszközön, és elérhető a felhasználó számára.

### <a name="data-locations-access-and-retention"></a>Adathelyek, hozzáférés és megőrzés

Mivel a felhasználó elindítja az adatgyűjtést, implicit módon hozzájárul a diagnosztikai adatok tárolásához. Csak a felhasználó, vagy bárki, akivel a felhasználó megosztja az adatokat, hozzáférhet az adatokhoz.

A diagnosztikai adatok az eszközön tárolódnak. Ha az eszköz csatlakozik a felhasználó számítógépéhez, az adatok a számítógépen is a következő fájlban találhatók:

> Ez a számítógép \\ \<*HoloLens device name*> \\ belső Storage \\ Dokumentumok \\ \<*ddmmyyhhmmss*> nyomkövetése .etl

> [!NOTE]  
> Ebben a fájl elérési útjának és nevének neve a HoloLens nevét jelöli, valamint a fájl létrehozási \<*HoloLens device name*> \<*ddmmyyhhmmss*> dátumát és időpontját.

A diagnosztikai adatok ezeken a helyeken maradnak, amíg a felhasználó nem törli azokat.

### <a name="view-diagnostic-report"></a>Diagnosztikai jelentés megtekintése

Az MDM Diagnostics 2. HoloLens-n való megtekintéséhez válassza a Wi-Fi ikont, majd lépjen a **Gépház** Accounts Access work or school (Munkahelyi vagy iskolai Gépház-fiókok elérése) pontra, és válassza a Felügyeleti naplók  ->    >   **exportálása lehetőséget.** HoloLens elküldi a naplófájlokat a fiókjába, és megjeleníti azok helyét az asztali számítógépen.

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

A Mobile Eszközkezelés (MDM) környezetben a rendszergazda a DiagnosticLog konfigurációs szolgáltató [(CSP)](/windows/client-management/mdm/diagnosticlog-csp) használatával konfigurálhatja a regisztrált HoloLens diagnosztikai beállításokat. A rendszergazda konfigurálhatja ezeket a beállításokat, hogy naplókat gyűjtsön a regisztrált eszközökről.

További információ:
- [Diagnosztika gyűjtése egy Windows eszközről](/mem/intune/remote-actions/collect-diagnostics)
- [Intune nyilvános előzetes verzió – Windows 10 eszközdiagnosztika](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Előfeltételek

- Az eszköz hálózathoz csatlakozik.
- Az eszköz olyan MDM-környezetben van regisztrálva, amely támogatja a DiagnosticLog CSP-t.

### <a name="data-locations-access-and-retention"></a>Adathelyek, hozzáférés és megőrzés

Mivel az eszköz a felügyelt környezet része, a felhasználó implicit módon hozzájárul a diagnosztikai információkhoz való rendszergazdai hozzáféréshez.

A rendszergazda a DiagnosticLog CSP segítségével konfigurálja az adattárolási, megőrzési és hozzáférési szabályzatokat, beleértve a következőket szabályozó szabályzatokat:

- A diagnosztikai adatokat tároló felhőalapú infrastruktúra.
- A diagnosztikai adatok megőrzési ideje.
- A diagnosztikai adatokhoz való hozzáférést vezérlő engedélyek.

## <a name="offline-diagnostics"></a>Offline diagnosztika

Olyan esetekben, amikor az eszköz nem képes diagnosztikai adatokat gyűjteni a Visszajelzési központ vagy a Gépház hibaelhárító segítségével, manuálisan is gyűjtheti a diagnosztikát. Erre akkor van szükség, ha az eszköz nem tud csatlakozni Wi-Fi vagy nem fér hozzá a fent említett egyéb módszerekhez. A diagnosztika összeomlási memóriaképeket és naplókat gyűjt az eszközről, amelyek segítségével a Microsoft támogatási szakemberei elkülönítik a problémákat.

Ez akkor működik, amikor az eszköz megjelenik a Fájlkezelő miután USB-kábelen keresztül csatlakoztatta a számítógéphez.

> [!NOTE]
> Az offline diagnosztika létrehozása és kezelése az operációs rendszer verziójától függően eltérő módon történik. Korábban a telemetriabeállítás vezérelte, de most már közvetlenül az MDM-szabályzat vezérli. Ha a beállítás vagy az MDM-szabályzat letiltja, akkor a diagnosztikai naplók nem gyűjthetőek ezzel a mechanizmussal.

Viselkedés a [Holographic Windows 20H2-es verziója előtt:](hololens-release-notes.md#windows-holographic-version-20h2)
 - Az offline diagnosztika csak akkor engedélyezett, ha a felhasználó az OOBE vagy a [System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) szabályzat értéke Full (Teljes) értékre van állítva (az alapszintű érték a HoloLens). 
- Az offline diagnosztika letiltásához válassza az Gépház **App > Adatvédelmi lapját,** és válassza az **Alapszintű** lehetőséget a **Diagnosztikai adatok lapon.** Olyan buildek esetén, ahol az offline diagnosztika a telemetriai beállításoktól függ, csak azt befolyásolja, hogy a rendszer gyűjt-e naplókat. Ez nincs hatással a begyűjtött fájlokra.
- Ha az eszköz zárolva van, a naplók nem jelennek meg.

A [Holographic Windows 20H2](hololens-release-notes.md#windows-holographic-version-20h2) és újabb verziókban:
- Ha a Fallback Diagnostics engedélyezve van, egy adott MDM-szabályzat vezérli, a [MixedReality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics) megfelelő beállításával
- Ha az eszköz zárolva van, a naplók nem jelennek meg.

További információért tekintse meg ezt a videót.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

A diagnosztika gyűjtéséhez kövesse az alábbi lépéseket:

1.  Csatlakozás az eszközt egy USB-kábellel a számítógéphez.

2.  A Fájlkezelő nyissa meg az "Ez a számítógép **\<hololens-device> \Belső számítógép" Storage.**

3.  Ha a **Belső Storage** mappa nem jelent meg, az eszköz arra vár, hogy a felhasználó bejelentkeztetsen. Az eszközbe való bejelentkezéshez vagy az energiaciklushoz tartsa lenyomva a POWER gombot 10 másodpercig.

4.  Nyomja le és azonnal engedje el a **Power + Volume Down** gombokat.

5.  Várjon egy percet, amíg az eszköz előkészíti a zip-archívumokat. (Előfordulhat, hogy egy HololensDiagnostics.temp nevű ideiglenes fájl láthatóvá válik, miközben az eszköz létrehozza a zip-archívumokat. Ne fér hozzá a fájlhoz, és ne mentse azt. Ha a folyamat befejeződik, a zip-archívumok felülírják.)

6.  Frissítse a fájlkezelőt, és keresse meg a **\Documents mappát.**

7.  Másolja ki a diagnosztikai ZIP-fájlokat, és ossza meg őket a Microsoft támogatási csapatával.

> [!NOTE]
> Egyes diagnosztikai ZIP-fájlok piI-adatokat tartalmazhatnak.

### <a name="offline-diagnostics-notifications"></a>Offline diagnosztikai értesítések

- A [Holographic Windows 21H2 verzióban vezettük be.](hololens-release-notes.md#windows-holographic-version-21h2)

Ez egy offline diagnosztika nevű meglévő [szolgáltatás frissítése.](hololens-diagnostic-logs.md#offline-diagnostics) Korábban nem volt egyértelmű jelzés a felhasználók számára a diagnosztikai gyűjtés aktiválására vagy befejezésére.
Az Insider Windows buildek két módon adhatják hozzá a visszajelzéseket az offline diagnosztikához. Az első a bejelentések értesítései, amelyek a gyűjtemény indításakor és befejezésekor is megjelennek. Ezek akkor jelennek meg, ha a felhasználó bejelentkezett, és rendelkezik vizualizációval.

![Bejelentés a naplók gyűjtéséhez.](./images/logcollection1.jpg)

![Bejelentés a naplógyűjtés befejezésekor.](./images/logcollection2.jpg)

Mivel a felhasználók gyakran használják az offline diagnosztikát tartalék naplógyűjtési mechanizmusként, amikor nem férnek hozzá a kijelzőkhez, nem tudnak bejelentkezni, vagy még mindig az OOBE-ban vannak, a naplók gyűjtésekor hangszavak is le fognak játszani. A bejelentési értesítés mellett ez a hang is megjelenik.

Ez az új funkció az eszköz frissítésekekor lesz engedélyezve, és nem szükséges engedélyezni vagy kezelni. Ha az új visszajelzés nem jelenik meg vagy nem hallható, az offline diagnosztika továbbra is létrejön.

Reméljük, hogy a visszajelzések újabb kiegészítésével könnyebb diagnosztikai adatokat gyűjteni, és gyorsabban elhárítani a problémákat.

### <a name="low-storage-log-collection-improvements"></a>Az alacsony tárterületű naplógyűjtés fejlesztései

- A [Holographic Windows 21H2 verzióban vezettük be.](hololens-release-notes.md#windows-holographic-version-21h2)

Olyan esetekben, amikor úgy tűnik, hogy az eszköznek kevés a lemezterülete a diagnosztikai naplók gyűjtésekor, a rendszer létrehoz egyStorageDiagnostics.zipnevű jelentést.  Az alacsony tárterület küszöbértékét a rendszer Windows [határozza meg.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

## <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Speciális diagnosztikai jelentés megtekintése a Gépház a HoloLens

- A [Holographic Windows 21H2 verzióban vezettük be.](hololens-release-notes.md#windows-holographic-version-21h2)

A felügyelt eszközök viselkedésének hibaelhárítása során fontos lépés annak ellenőrzése, hogy a rendszer a várt szabályzatkonfigurációt alkalmazza-e. Korábban ezt az új funkciót az MDM-en keresztül vagy az eszköz közelében kellett eszközről, az **Gépház** Accounts Access munkahelyi vagy iskolai fiókokkal gyűjtött diagnosztikai naplók exportálása után, majd a Felügyeleti naplók exportálása és megtekintése egy közeli számítógépen lehetőség  ->    >  **kiválasztásával.** 

Az MDM-diagnosztika mostantól megtekinthető az eszközön az Edge böngésző használatával. Ha könnyebben meg szeretne tekinteni egy MDM diagnosztikai jelentést, lépjen a Hozzáférés munkahelyi vagy iskolai alkalmazáshoz lapra, és válassza a **Speciális diagnosztikai jelentés megtekintése lehetőséget.** Ez létrehozza és megnyitja a jelentést egy új Edge-ablakban.

![Speciális diagnosztikai jelentés megtekintése az Gépház alkalmazásban.](./images/view-advanced-diagnostic-report.jpg)
