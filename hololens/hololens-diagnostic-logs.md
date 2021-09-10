---
title: Diagnosztikai adatok gyűjtése és használata HoloLens eszközökről
description: Megtudhatja, hogyan gyűjti, használhatja és őrizze meg a diagnosztikai adatokat a HoloLens eszközökről.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
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
ms.openlocfilehash: 082a263bdd7eba694c13124abf40763644c83dfa
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427944"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Diagnosztikai adatok gyűjtése és használata HoloLens eszközökről

HoloLens felhasználók és rendszergazdák négy különböző módszer közül választhatnak, hogy diagnosztikai adatokat gyűjtsenek a HoloLens:

- Visszajelzési központ alkalmazás
- DiagnosticLog CSP
- Gépház alkalmazás
- Offline diagnosztika

> [!IMPORTANT]  
> Az eszközdiagnosztikai naplók személyes azonosításra alkalmas adatokat (PII-ket) tartalmaznak, például azt, hogy a felhasználó milyen folyamatokat vagy alkalmazásokat kezd el a tipikus műveletek során. Ha egy HoloLens-eszközön több felhasználó is osztozik (például a felhasználók különböző Microsoft Azure Active Directory- (Azure AD-) fiókkal jelentkeznek be ugyanannak az eszköznek a felhasználásával, a diagnosztikai naplók több felhasználóra vonatkozó PII-adatokat tartalmazhatnak. További információ: [A Microsoft adatvédelmi nyilatkozata.](https://privacy.microsoft.com/privacystatement)

Az alábbi táblázat a különböző gyűjteményi metódusokat hasonlítja össze. A metódusok nevei részletesebb információkra hivatkoznak a táblázatot követő szakaszokban.

|Metódus |Előfeltételek |Adatok helye |Adatelérés és -használat |Adatmegőrzés |
| --- | --- | --- | --- | --- |
|[Visszajelzési központ](#feedback-hub) |Hálózati és internetkapcsolat<br /><br />Visszajelzési központ alkalmazás<br /><br />Engedély fájlok microsoftos felhőbe való feltöltéséhez |Microsoft Cloud<br /><br />HoloLens eszköz (nem kötelező) |A felhasználó segítséget kér, elfogadja a használati feltételeket, és feltölti az adatokat<br /><br />A Microsoft alkalmazottai az adatokat a használati feltételeknek megfelelő módon tekinteni |A felhőben az adatok a következő generációs adatvédelem (NGP) által meghatározott időtartamra maradnak meg. Ezután a rendszer automatikusan törli az adatokat.<br /><br />Az eszközön található adatokat bármikor törölheti egy  eszköztulajdonosi vagy rendszergazdai engedéllyel **rendelkező** felhasználó. |
|[Gépház Hibaelhárító](#settings-troubleshooter) |Gépház alkalmazás |HoloLens eszköz<br /><br />Csatlakoztatott számítógép (nem kötelező) |A felhasználó tárolja az adatokat, és csak a felhasználó fér hozzá az adatokhoz (kivéve, ha a felhasználó kifejezetten megosztja az adatokat egy másik felhasználóval). |Az adatok addig maradnak az eszközön, amíg a felhasználó nem törli őket.* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |Hálózati kapcsolat<br /><br />A DiagnosticLog CSP-t támogató MDM-környezet |A rendszergazda konfigurálja a tárolóhelyeket |A felügyelt környezetben a felhasználó implicit módon hozzájárul az adatok rendszergazdai hozzáféréséhez.<br /><br />A rendszergazda konfigurálja a hozzáférési szerepköröket és engedélyeket. | Az adatok a felhőalapú tárolóban maradnak, és a rendszergazda konfigurálja az adatmegőrzési szabályzatot. |
|[Offline diagnosztika](#offline-diagnostics) |Eszközkonfiguráció:<ul><li>Bekapcsolva és csatlakoztatva a számítógéphez</li><li>A Tápkapcsoló és a Kötet gomb működése</li></ul> |HoloLens eszköz<br /><br />Csatlakoztatott számítógép |A felhasználó tárolja az adatokat, és csak a felhasználó fér hozzá az adatokhoz (kivéve, ha a felhasználó kifejezetten megosztja az adatokat egy másik felhasználóval). |Az adatok addig maradnak az eszközön, amíg a felhasználó nem törli azokat. |

* A végfelhasználó felelőssége, hogy felelősségteljesen megossa a naplókat valaki másval. Ezek a fájlok elsősorban az ügyfélszolgálattal és az ügyfélszolgálattal való kapcsolatfelvételkor hasznosak.  

## <a name="feedback-hub"></a>Visszajelzési központ

A HoloLens felhasználók a Microsoft Visszajelzési központ asztali alkalmazással diagnosztikai adatokat küldhetnek a Microsoft ügyfélszolgálata. A részletekért és a teljes útmutatásért lásd: [Visszajelzés küldése.](hololens-feedback.md)  

> [!NOTE]  
> **Kereskedelmi vagy vállalati felhasználók:** Ha a Visszajelzési központ alkalmazást használja az MDM-hez, a kiépítéshez vagy bármely más eszközkezelési aspektushoz kapcsolódó probléma jelentéséhez, módosítsa az alkalmazáskategóriát Vállalati felügyeleti eszköz   >  **kategóriára.**

>[!IMPORTANT]
> Annak érdekében, hogy a lehető legjobb adatokat biztosítsa a problémák megoldásához, javasoljuk, hogy az eszköz telemetriát opcionálisra **állítsa.** Ezt az értéket a OOBE (Out-of-Box-Experience) vagy a Gépház is **beállíthatja.** Ha ezt az alkalmazással Gépház meg, válassza a Start > Gépház > Privacy > App Diagnostics (Alkalmazásdiagnosztikai adatok **>) lehetőséget.**
### <a name="prerequisites"></a>Előfeltételek

- Az eszköz hálózathoz csatlakozik.
- A Visszajelzési központ alkalmazás elérhető a felhasználó asztali számítógépén, és a felhasználó fájlokat tölthet fel a Microsoft-felhőbe.

### <a name="data-locations-access-and-retention"></a>Adathelyek, hozzáférés és megőrzés

A használati feltételek Visszajelzési központ a felhasználó kifejezetten beleegyezik az adatok tárolásába és használatára (a szerződés által meghatározottak szerint).

A Visszajelzési központ két helyet biztosít a felhasználó számára a diagnosztikai adatok tárolására:

- **A Microsoft-felhő.** A felhasználó által az Visszajelzési központ alkalmazással feltöltött adatokat a rendszer a következő generációs adatvédelmi (NGP)-követelményeknek megfelelő napokig tárolja. A Microsoft-alkalmazottak NGP-kompatibilis megjelenítővel férhetnek hozzá az adatokhoz ebben az időszakban.

   > [!NOTE]  
   > Ezek a követelmények az összes kategória összes Visszajelzési központ vonatkoznak.

- **A HoloLens eszköz.** Amikor jelentést készít a Visszajelzési központ, a felhasználó kiválaszthatja a Visszajelzés küldésekor létrehozott diagnosztikai és mellékletek helyi **másolatának mentése lehetőséget.** Ha a felhasználó ezt a lehetőséget választja, a Visszajelzési központ másolatot fog a diagnosztikai adatokról a HoloLens eszközön. Ezek az információk továbbra is elérhetők maradnak a felhasználó (vagy bárki számára, aki ezt a fiókot használja a HoloLens). Ezen adatok törléséhez a  felhasználónak  eszköztulajdonosi vagy rendszergazdai engedélyekkel kell rendelkeznie az eszközön. A megfelelő engedélyekkel rendelkező felhasználók bejelentkeznek a Visszajelzési központ, kiválasztják **Gépház** Diagnosztikai naplók megtekintése lehetőséget, és  >  törölhetik az információkat.

## <a name="settings-troubleshooter"></a>Gépház Hibaelhárító

A HoloLens felhasználó a Gépház **segítségével** elháríthatja a problémákat, és diagnosztikai adatokat gyűjthet. Ehhez kövesse az alábbi lépéseket:

1. Nyissa meg a Gépház alkalmazást, és válassza **az Update & Security Troubleshoot (Biztonsági &**  >  **frissítése)** lapot.
1. Válassza ki a megfelelő területet, majd válassza az **Indítás lehetőséget.**
1. Reprodukálja a problémát.
1. Miután reprodukálta a problémát, térjen vissza a Gépház, majd válassza a **Leállítás lehetőséget.**

A felhasználó a tartalék diagnosztika viselkedését  is konfigurálhatja a Gépház alkalmazásból. A beállítás **konfiguráláshoz lépjen > Adatvédelem –> lapra.**
> [!NOTE]
> Ha az eszközhöz MDM-szabályzat van konfigurálva, a felhasználó nem tudja felülbírálni ezt a viselkedést.

### <a name="os-update-troubleshooter"></a>Operációs rendszer frissítésének hibaelhárítója
A [Holographic Windows 21H1-es](hololens-release-notes.md#windows-holographic-version-21h1) és újabb verziókban:
- A Gépház alkalmazás korábbi hibaelhárítói mellett egy új hibaelhárítót is hozzáadtunk az operációsrendszer-frissítésekhez Gépház új hibaelhárítóval. Lépjen a **Gépház -> Update & Security -> Troubleshoot -> Windows Update (Frissítés** hibaelhárítása ) lapra, és válassza az Indítás **lehetőséget.** Ez lehetővé teszi a nyomkövetések gyűjtését az operációsrendszer-frissítésekkel kapcsolatos probléma reprodukálása során, hogy az it-it és a támogatással kapcsolatos hibaelhárítást támaszon ki.
### <a name="prerequisites"></a>Előfeltételek

- A **Gépház** alkalmazás telepítve van az eszközön, és elérhető a felhasználó számára.

### <a name="data-locations-access-and-retention"></a>Adathelyek, hozzáférés és megőrzés

Mivel a felhasználó elindítja az adatgyűjtést, implicit módon hozzájárul a diagnosztikai adatok tárolásához. Csak a felhasználó, vagy bárki, akivel a felhasználó megosztja az adatokat, hozzáférhet az adatokhoz.

A diagnosztikai adatok az eszközön tárolódnak. Ha az eszköz csatlakozik a felhasználó számítógépéhez, az adatok a számítógépen is találhatók a következő fájlban:

> Ez a számítógép \\ \<*HoloLens device name*> \\ belső Storage Documents \\ Trace \\ \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> Ebben a fájl elérési útjának és nevének része a HoloLens neve, valamint a fájl létrehozási \<*HoloLens device name*> \<*ddmmyyhhmmss*> dátumát és időpontját jelöli.

A diagnosztikai adatok ezeken a helyeken maradnak, amíg a felhasználó nem törli azokat.

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

A Mobile Eszközkezelés (MDM) környezetben a rendszergazda a DiagnosticLog konfigurációs szolgáltató [(CSP)](/windows/client-management/mdm/diagnosticlog-csp) segítségével konfigurálhatja a regisztrált HoloLens diagnosztikai beállításokat. A rendszergazda konfigurálhatja ezeket a beállításokat, hogy naplókat gyűjtsön a regisztrált eszközökről.

További információ:
- [Diagnosztika gyűjtése egy Windows eszközről](/mem/intune/remote-actions/collect-diagnostics)
- [Intune nyilvános előzetes verzió – Windows 10 eszközdiagnosztika](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Előfeltételek

- Az eszköz hálózathoz csatlakozik.
- Az eszköz olyan MDM-környezetben van regisztrálva, amely támogatja a DiagnosticLog CSP-t.

### <a name="data-locations-access-and-retention"></a>Adathelyek, hozzáférés és megőrzés

Mivel az eszköz a felügyelt környezet része, a felhasználó implicit módon hozzájárul a diagnosztikai információkhoz való rendszergazdai hozzáféréshez.

A rendszergazda a DiagnosticLog CSP segítségével konfigurálja az adattárolási, -megőrzési és -hozzáférési házirendeket, beleértve a következő házirendeket:

- A diagnosztikai adatokat tároló felhőalapú infrastruktúra.
- A diagnosztikai adatok megőrzési ideje.
- A diagnosztikai adatokhoz való hozzáférést vezérlő engedélyek.

## <a name="offline-diagnostics"></a>Offline diagnosztika
Olyan esetekben, amikor az eszköz nem tud diagnosztikai adatokat gyűjteni a Visszajelzési központ vagy a Gépház hibaelhárító segítségével, manuálisan is gyűjtheti a diagnosztikát. Erre akkor van szükség, ha az eszköz nem tud csatlakozni Wi-Fi vagy nem fér hozzá a fent említett egyéb módszerekhez. A diagnosztika összeomlási memóriaképeket és naplókat gyűjt az eszközről, amelyek segítségével a Microsoft támogatási szakemberei elkülönítik a problémákat.

Ez akkor működik, amikor az eszköz megjelenik a Fájlkezelő miután USB-kábelen keresztül csatlakoztatta a számítógéphez.

> [!NOTE]
> Az offline diagnosztika létrehozása és kezelése az operációs rendszer verziójától függően eltérő módon történik. Korábban a telemetriabeállítás vezérelte, de most már közvetlenül MDM-szabályzaton keresztül vezérelték. Ha a beállítás vagy az MDM-szabályzat letiltja, akkor a diagnosztikai naplók nem gyűjthetőek ezzel a mechanizmussal.

Viselkedés a [Holographic Windows 20H2-es verziója előtt:](hololens-release-notes.md#windows-holographic-version-20h2)
 - Az offline diagnosztika csak akkor engedélyezett, ha a felhasználó az OOBE vagy a [System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) szabályzat értéke Full (Teljes) értékre van állítva (az alapszintű érték a HoloLens). 
- Az offline diagnosztika letiltásához válassza az Gépház **App > Adatvédelmi lapját,** és válassza az **Alapszintű** lehetőséget a **Diagnosztikai adatok lapon.** Olyan buildek esetén, ahol az offline diagnosztika a telemetriai beállításoktól függ, csak azt befolyásolja, hogy a rendszer gyűjt-e naplókat. Ez nincs hatással a begyűjtött fájlokra.
- Ha az eszköz zárolva van, a naplók nem jelennek meg.

A [Holographic Windows 20H2](hololens-release-notes.md#windows-holographic-version-20h2) és újabb verziók buildjén:
- Ha a Fallback Diagnostics engedélyezve van, egy adott MDM-szabályzat vezérli, a [MixedReality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics) megfelelő beállításával
- Ha az eszköz zárolva van, a naplók nem jelennek meg.

További információért tekintse meg ezt a videót.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

A diagnosztika gyűjtéséhez kövesse az alábbi lépéseket:
1.  Csatlakozás csatlakoztatja az eszközt egy USB-kábellel a számítógéphez.
2.  A Fájlkezelő számítógépen keresse meg a **"This PC \Internal Storage" (Ez a számítógép \<hololens-device> \Belső Storage) et.**
3.  Ha a **Belső Storage** mappa nem jelent meg, az eszköz arra vár, hogy a felhasználó bejelentkeztetsen. Az eszközbe való bejelentkezéshez vagy az energiaciklushoz tartsa lenyomva a POWER gombot 10 másodpercig.
4.  Nyomja le és azonnal engedje el a **Power + Volume Down** gombokat.
5.  Várjon egy percet, amíg az eszköz előkészíti a zip-archívumokat. (Előfordulhat, hogy egy HololensDiagnostics.temp nevű ideiglenes fájl láthatóvá válik, miközben az eszköz létrehozza a zip-archívumokat. Ne fér hozzá a fájlhoz, és ne mentse azt. Amikor a folyamat befejeződik, a zip-archívumok felülírják.)
6.  Frissítse a fájlkezelőt, és keresse meg a **\Documents mappát.**
7.  Másolja ki a diagnosztikai ZIP-fájlokat, és ossza meg őket a Microsoft támogatási csapatával.

> [!NOTE]
> Egyes diagnosztikai ZIP-fájlok piI-adatokat tartalmazhatnak.
