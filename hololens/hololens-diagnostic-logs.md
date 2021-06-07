---
title: Diagnosztikai adatok gyűjtése és használata HoloLens-eszközökről
description: Megtudhatja, hogyan gyűjthetőek, használhatók és őrizhetőek meg a HoloLens-eszközök diagnosztikai adatai.
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
ms.openlocfilehash: c1d5205d4faa4384600c489167c9581de8e4b62c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378156"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Diagnosztikai adatok gyűjtése és használata HoloLens-eszközökről

A HoloLens-felhasználók és -rendszergazdák négy különböző módszer közül választhatnak a HoloLens diagnosztikai információinak gyűjtéséhez:

- Visszajelzési központ alkalmazás
- DiagnosticLog CSP
- Beállítások alkalmazás
- Offline diagnosztika

> [!IMPORTANT]  
> Az eszközdiagnosztikai naplók személyazonosításra alkalmas adatokat (PII-ket) tartalmaznak, például azt, hogy a felhasználó milyen folyamatokat vagy alkalmazásokat kezd el a tipikus műveletek során. Ha egy HoloLens-eszközön több felhasználó is osztozik (például a felhasználók különböző Microsoft Azure Active Directory- (Azure AD-) fiókokkal jelentkeznek be ugyanannak az eszköznek a felhasználói, a diagnosztikai naplók több felhasználóra vonatkozó PII-adatokat tartalmazhatnak. További információ: [A Microsoft adatvédelmi nyilatkozata.](https://privacy.microsoft.com/privacystatement)

Az alábbi táblázat a különböző gyűjtési módszereket hasonlítja össze. A metódusok nevei részletesebb információkra hivatkoznak a táblázatot követő szakaszokban.

|Metódus |Előfeltételek |Adatok helye |Adatelérés és -használat |Adatmegőrzés |
| --- | --- | --- | --- | --- |
|[Visszajelzési központ](#feedback-hub) |Hálózati és internetkapcsolat<br /><br />Visszajelzési központ alkalmazás<br /><br />Engedély fájlok microsoftos felhőbe való feltöltéséhez |Microsoft Cloud<br /><br />HoloLens-eszköz (nem kötelező) |A felhasználó segítséget kér, elfogadja a használati feltételeket, és feltölti az adatokat<br /><br />A Microsoft alkalmazottai az adatokat a használati feltételeknek megfelelő módon tekinteni |A felhőben az adatok a következő generációs adatvédelem (NGP) által meghatározott időtartamra maradnak meg. Ezt követően a rendszer automatikusan törli az adatokat.<br /><br />Az eszközön található adatokat bármikor törölheti egy  eszköztulajdonosi vagy rendszergazdai engedéllyel **rendelkező** felhasználó. |
|[Beállítások hibaelhárítója](#settings-troubleshooter) |Beállítások alkalmazás |HoloLens-eszköz<br /><br />Csatlakoztatott számítógép (nem kötelező) |A felhasználó tárolja az adatokat, és csak a felhasználó fér hozzá az adatokhoz (kivéve, ha a felhasználó kifejezetten megosztja az adatokat egy másik felhasználóval). |Az adatok addig maradnak az eszközön, amíg a felhasználó nem törli őket.* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |Hálózati kapcsolat<br /><br />A DiagnosticLog CSP-t támogató MDM-környezet |A rendszergazda konfigurálja a tárolóhelyeket |A felügyelt környezetben a felhasználó implicit módon hozzájárul az adatok rendszergazdai hozzáféréséhez.<br /><br />A rendszergazda konfigurálja a hozzáférési szerepköröket és engedélyeket. | Az adatok a felhőtárhelyben maradnak, és a rendszergazda konfigurálja az adatmegőrzési szabályzatot. |
|[Offline diagnosztika](#offline-diagnostics) |Eszközkonfiguráció:<ul><li>Bekapcsolva és csatlakoztatva a számítógéphez</li><li>A Tápkapcsoló és a Kötet gomb működése</li></ul> |HoloLens-eszköz<br /><br />Csatlakoztatott számítógép |A felhasználó tárolja az adatokat, és csak a felhasználó fér hozzá az adatokhoz (kivéve, ha a felhasználó kifejezetten megosztja az adatokat egy másik felhasználóval). |Az adatok addig maradnak az eszközön, amíg a felhasználó nem törli azokat. |

* A végfelhasználó felelőssége, hogy felelősségteljesen megossa a naplókat valaki másval. Ezek a fájlok elsősorban az ügyfélszolgálattal és az ügyfélszolgálattal való kapcsolatfelvételkor hasznosak.  

## <a name="feedback-hub"></a>Visszajelzési központ

A HoloLens-felhasználók a Microsoft Visszajelzési központ asztali alkalmazással diagnosztikai adatokat küldhetnek a Microsoft ügyfélszolgálata. A részletekért és a teljes útmutatásért lásd: [Visszajelzés küldése.](hololens-feedback.md)  

> [!NOTE]  
> **Kereskedelmi vagy vállalati felhasználók:** Ha a Visszajelzési központ alkalmazást használja az MDM-hez, a kiépítéshez vagy bármely más eszközkezelési aspektushoz kapcsolódó probléma jelentéséhez, módosítsa az alkalmazáskategóriát Vállalati felügyeleti eszköz  >  **kategóriára.**

>[!IMPORTANT]
> Annak érdekében, hogy a lehető legjobb adatokat biztosítsa a problémák megoldásához, javasoljuk, hogy az eszköz telemetriai adatait opcionálisra **állítsa.** Ezt az értéket a Használatra való használatra (OOBE) vagy a Beállítások alkalmazással **állíthatja** be. Ehhez a Beállítások használatával válassza a **Start > Settings > Privacy > App Diagnostics > on lehetőséget.**
### <a name="prerequisites"></a>Előfeltételek

- Az eszköz hálózathoz csatlakozik.
- A Visszajelzési központ alkalmazás elérhető a felhasználó asztali számítógépén, és a felhasználó fájlokat tölthet fel a Microsoft-felhőbe.

### <a name="data-locations-access-and-retention"></a>Adathelyek, hozzáférés és megőrzés

A használati feltételek Visszajelzési központ a felhasználó kifejezetten beleegyezik az adatok tárolásába és használatára (a szerződés által meghatározottak szerint).

A Visszajelzési központ két helyet biztosít a felhasználó számára a diagnosztikai adatok tárolására:

- **A Microsoft-felhő.** A felhasználó által az Visszajelzési központ alkalmazással feltöltött adatokat a rendszer a következő generációs adatvédelmi (NGP)-követelményeknek megfelelő napokig tárolja. A Microsoft-alkalmazottak NGP-kompatibilis megjelenítővel férhetnek hozzá az adatokhoz ebben az időszakban.

   > [!NOTE]  
   > Ezek a követelmények az összes kategória adatainak Visszajelzési központ vonatkoznak.

- **A HoloLens-eszköz.** Amikor jelentést készít a Visszajelzési központ, a felhasználó kiválaszthatja a Visszajelzés küldésekor létrehozott diagnosztikai és mellékletek helyi **másolatának mentése lehetőséget.** Ha a felhasználó ezt a lehetőséget választja, a Visszajelzési központ a diagnosztikai adatok másolatát a HoloLens-eszközön tárolja. Ezek az információk továbbra is elérhetők maradnak a felhasználó (vagy bárki számára, aki ezt a fiókot használja a HoloLensbe való bejelentkezéshez). Ezen adatok törléséhez a  felhasználónak  eszköztulajdonosi vagy rendszergazdai engedélyekkel kell rendelkeznie az eszközön. A megfelelő engedélyekkel rendelkező felhasználók bejelentkeznek a Visszajelzési központ, a Beállítások Diagnosztikai naplók megtekintése lehetőséget választva  >  törölhetik az adatokat.

## <a name="settings-troubleshooter"></a>Beállítások hibaelhárítója

A HoloLens-felhasználók az eszközön található **Beállítások** alkalmazással elháríthatja a problémákat, és diagnosztikai adatokat gyűjthet. Ehhez kövesse az alábbi lépéseket:

1. Nyissa meg a Beállítások alkalmazást, és **válassza a Frissítés & Biztonsági hibaelhárítás**  >  **lapra.**
1. Válassza ki a megfelelő területet, majd válassza az **Indítás lehetőséget.**
1. Reprodukálja a problémát.
1. Miután reprodukálta a problémát, térjen vissza a Beállítások lapra, majd válassza a **Leállítás lehetőséget.**

A felhasználó a Tartalék diagnosztika viselkedését is konfigurálhatja a **Beállítások alkalmazásban.** A beállítás **konfiguráláshoz lépjen** > -> lapra.
> [!NOTE]
> Ha az eszközhöz MDM-szabályzat van konfigurálva, a felhasználó nem tudja felülbírálni ezt a viselkedést.

### <a name="os-update-troubleshooter"></a>Operációs rendszer frissítésének hibaelhárítója
Builden [a Windows Holographic 21H1-es ](hololens-release-notes.md#windows-holographic-version-21h1) és újabb verziói:
- A Beállítások alkalmazás korábbi hibaelhárítói mellett egy új hibaelhárítót is hozzáadtunk az új, operációsrendszer-frissítésekhez elérhető Settings alkalmazással. Lépjen a **Beállítások -> Update & Security -> Troubleshoot -> Windows Update** ( Hibaelhárítás ) elemre, és válassza az **Indítás lehetőséget.** Ez lehetővé teszi a nyomkövetések gyűjtését az operációsrendszer-frissítésekkel kapcsolatos probléma reprodukálása során, hogy az it-it és a támogatással kapcsolatos hibaelhárítást támaszon ki.
### <a name="prerequisites"></a>Előfeltételek

- A **Beállítások** alkalmazás telepítve van az eszközön, és elérhető a felhasználó számára.

### <a name="data-locations-access-and-retention"></a>Adathelyek, hozzáférés és megőrzés

Mivel a felhasználó elindítja az adatgyűjtést, implicit módon hozzájárul a diagnosztikai adatok tárolásához. Csak a felhasználó, vagy bárki, akivel a felhasználó megosztja az adatokat, hozzáférhet az adatokhoz.

A diagnosztikai adatok az eszközön tárolódnak. Ha az eszköz csatlakozik a felhasználó számítógépéhez, az adatok a számítógépen is találhatók a következő fájlban:

> A számítógép \\ \<*HoloLens device name*> \\ belső \\ tárolódokumentumai \\ \<*ddmmyyhhmmss*> nyomkövetési .etl

> [!NOTE]  
> Ebben a fájl elérési útjának és nevének része a HoloLens-eszköz neve, valamint a fájl létrehozási dátuma és \<*HoloLens device name*> \<*ddmmyyhhmmss*> időpontja.

A diagnosztikai adatok ezeken a helyeken maradnak, amíg a felhasználó nem törli azokat.

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

A Mobile Eszközkezelés (MDM) környezetben a rendszergazda a [DiagnosticLog konfigurációs szolgáltatóval (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) konfigurálhatja a regisztrált HoloLens-eszközökön a diagnosztikai beállításokat. A rendszergazda konfigurálhatja ezeket a beállításokat, hogy naplókat gyűjtsön a regisztrált eszközökről.

További információ:
- [Diagnosztika gyűjtése Windows-eszközről](https://docs.microsoft.com/mem/intune/remote-actions/collect-diagnostics)
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
Olyan esetekben, amikor az eszköz nem tud diagnosztikai adatokat gyűjteni a Visszajelzési központ vagy a Beállítások hibaelhárítója segítségével, manuálisan is gyűjtheti a diagnosztikát. Erre akkor van szükség, ha az eszköz nem tud csatlakozni Wi-Fi vagy nem fér hozzá a fent említett egyéb módszerekhez. A diagnosztika összeomlási memóriaképeket és naplókat gyűjt az eszközről, amelyek segítségével a Microsoft támogatási szakemberei elkülönítik a problémákat.

Ez akkor működik, amikor az eszköz megjelenik a Fájlkezelő miután USB-kábelen keresztül csatlakoztatta a számítógéphez.

> [!NOTE]
> Az offline diagnosztika létrehozása és kezelése az operációs rendszer verziójától függően eltérő módon történik. Korábban a telemetriabeállítás vezérelte, de most már közvetlenül az MDM-szabályzat vezérli. Ha a beállítás vagy az MDM-szabályzat letiltja, akkor a diagnosztikai naplók nem gyűjthetőek ezzel a mechanizmussal.

Viselkedés a [Windows Holographic előtti 20H2-es verziónál:](hololens-release-notes.md#windows-holographic-version-20h2)
 - Az offline diagnosztika csak akkor engedélyezett, ha a felhasználó az OOBE vagy a [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) szabályzat teljes értékre van állítva (a HoloLensen az alapszintű érték). 
- Az offline diagnosztika letiltásához válassza a Beállítások alkalmazás > **Adatvédelmi lapját,** és válassza az **Alapszintű** lehetőséget a **Diagnosztikai adatok lapon.** Olyan buildek esetén, ahol az offline diagnosztika a telemetriai beállításoktól függ, csak azt befolyásolja, hogy a rendszer gyűjt-e naplókat. Ez nincs hatással a begyűjtött fájlokra.
- Ha az eszköz zárolva van, a naplók nem jelennek meg.

A Windows [Holographic 20H2](hololens-release-notes.md#windows-holographic-version-20h2) és újabb verziójú buildek esetén:
- Ha a Fallback Diagnostics engedélyezve van, a rendszer meghatározott MDM-szabályzattal fogja vezérelni a [MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics) megfelelő beállításával
- Ha az eszköz zárolva van, a naplók nem jelennek meg.

További információért tekintse meg ezt a videót.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

A diagnosztika gyűjtéséhez kövesse az alábbi lépéseket:
1.  Csatlakoztassa az eszközt egy USB-kábellel a számítógéphez.
2.  A Fájlkezelő nyissa meg a **"This PC \Internal Storage" (Ez a számítógép \<hololens-device> \Belső tárhely) et.**
3.  Ha a **Belső tároló mappa** nem jelent meg, az eszköz arra vár, hogy egy felhasználó bejelentkeztetsen. Jelentkezzen be vagy tápellátást az eszközön úgy, hogy 10 másodpercig lenyomva tartja a POWER gombot.
4.  Nyomja le és azonnal engedje el a **Power + Volume Down** gombokat.
5.  Várjon egy percet, amíg az eszköz előkészíti a zip-archívumokat. (Előfordulhat, hogy egy HololensDiagnostics.temp nevű ideiglenes fájl láthatóvá válik, miközben az eszköz létrehozza a zip-archívumokat. Ne fér hozzá a fájlhoz, és ne mentse azt. Amikor a folyamat befejeződik, a zip-archívumok felülírják.)
6.  Frissítse a fájlkezelőt, és keresse meg a **\Documents mappát.**
7.  Másolja ki a diagnosztikai ZIP-fájlokat, és ossza meg őket a Microsoft támogatási csapatával.

> [!NOTE]
> Egyes diagnosztikai ZIP-fájlok piI-adatokat tartalmazhatnak.
