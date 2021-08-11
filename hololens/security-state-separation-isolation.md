---
title: Állapotok elkülönítése és elkülönítése
description: Ismerje meg az állapotelválasztást, az elkülönítést, a kódalá aláírást és a defender alkalmazásokat a HoloLens 2 vegyes valóságú eszközön.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: biztonság, hololens, állapotelválasztás, állapotelválasztás és elkülönítés, hololens 2, hololens2 biztonság, biztonsági áttekintés, biztonsági architektúra, architektúra, hololens 2 architektúra
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 18c30b4edd649c088f71e479a401c8b286ddfd592f57a5659c3c15b3ec9c854f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665369"
---
# <a name="state-separation-and-isolation"></a>Állapotok elkülönítése és elkülönítése

Az állapotok elkülönítése és elkülönítése megvédi a Hololens 2 operációs rendszer kritikus fontosságú részeit a változásoktól, például azokat, amelyek az operációs rendszer megbízható állapotba való rendszerindításához szükségesek. Az elkülönítési technológiával a nem megbízható alkalmazások áthelyezhetőek egy elkülönített sandbox-környezetbe, így biztosítva, hogy azok ne befolyásolják a rendszer biztonságát.

## <a name="state-separation"></a>Állapotok elkülönítése

A 2. HoloLens állapotok elkülönítése jelentősen javítja a biztonságot és a javíthatóságot (frissítés), és segít megvédeni az alkalmazásadatokat.  Az állapotok elkülönítése a következőképpen működik:
  * Az alapvető operációs rendszer tárolása az operációs rendszer központi kötetében (megbízható vagy ellenőrzött Microsoft operációs rendszer az operációs rendszer frissítésével).
  * Az operációs rendszer futásidőben módosítható részei (például letölthető illesztőprogramok és konfigurációk), az adatok particionálása és biztonságos, különálló tárolási helyeken való tárolása további állapotok elkülönítésével.
  * Minden biztonságos tárolóhelyhez különböző biztonsági szabályzatok vannak társítva, amelyek a következő szakaszban részletezett különböző biztonsági előnyöket kínálnak.

## <a name="state-separation-benefits"></a>Az állapotok elkülönítésének előnyei

  * Biztonság: A 2. HoloLens kiemelt állapot-elkülönítés jelentősen javítja a platform integritását, a kártevők elleni védelmet és a felhasználói adatvédelmet. Ha elkülöníti az operációs rendszer nem elterjedő részét, és írásra vagy integritásvédelemre teszi, az állapotelválasztás rendkívül megnehezíti a kártevők számára a hideg újraindítások során való megőrzését. 
  * Frissítések: HoloLens 2. frissítéssel, miután az alapvető operációs rendszer nem módosítható, és egyértelműen el lett választva az eszközön található többi adattól, a frissítések egyszerűvé és megbízhatóvá válnak.  Emellett az állapotok elkülönítése lefekteti a jelentősen gyorsabb frissítések alapvető fontosságú alaprendszerét, amely lehetővé teszi az operációs rendszer egyetlen lépésben (atomi egységben) való cseréjét.
  * Eszköz alaphelyzetbe állítása: HoloLens 2. alaphelyzetbe állítása törli a felhasználó által létrehozott adatokat és felhasználói alkalmazásadatokat az eszközön – beleértve a belső és külső tárolási helyeket is. Megőrzi a jelenlegi operációsrendszer-alkalmazásokat és a biztonsági szempontjából kritikus alkalmazásokat, valamint a Microsoft és az OEM által testre szabott (előre telepített) alkalmazásokat. Ezek az előre telepített alkalmazások rehidratálhatóak az eszközön az alaphelyzetbe állítás befejezése után

### <a name="state-separation-states"></a>Állapotok elkülönítési állapotai

Az állapotok elkülönítése biztosítja, hogy az operációs rendszert csak a Microsoft megbízható eszközösszetevői változtatják meg, és csak a nagy értékű állapot marad meg az újraindítások között; más rendszerállapot csak a rendszerindítási munkamenet időtartamára létezik, és a rendszer egy újraindítás után elveti. Az állapotok elkülönítése gyorsan visszaállítja az eszközt a gyári állapotba. Windows Holographic for Business az alábbi kategóriákba sorolhatók:
  * Alapvető operációs rendszer – Nem elterjedő állapot
  * Operációs rendszer adatai – Változtatható állapot 
  * Felhasználói adatok – Módosítható állapot

A következő HoloLens két operációs rendszert ismertet.

#### <a name="core-operating-system"></a>Alapvető operációs rendszer

A nem módosítható állapot olyan végrehajtható fájlokból és adatokból áll, amelyek nem módosíthatók, és a Microsoft csak a frissítések telepítése során módosítható. Az alapvető operációs rendszer ilyen frissítése során a rendszer engedélyezi a legújabb kívánt működési állapotot tartalmazó új lemezképet.
A nem elterjedő állapot csak olvashatóként van megjelölve (vagy egyéb módon integritásvédelem alatt áll), ami megakadályozza az emelt szintű jogosultságokkal rendelkező kártevők megőrzését. A következő végrehajtható fájlok és adatok nem módosítható állapotban vannak védve:
  * Windows Holografikus postaládák illesztőprogramjai
  * Operációs rendszer bináris fájlok
  * Windows-illesztőprogramok
  * A Windows struktúra (HKLM) Windows holografikus beállításai
    * Példa: A HKLM a gépre telepített alkalmazások konfigurációs adatait tárolja. A hardverek és a hozzájuk tartozó illesztőprogramok észleléséhez szükséges adatokat is tárolja.
Azáltal, hogy ezek nem módosítható (integritás és csak olvasható védelem) állapotban vannak védve, biztosítjuk, hogy az alapvető operációs rendszer mindig megbízható állapotban elindul. Emellett az eszköz alaphelyzetbe állításakor gondoskodhat róla, hogy az eszköz csak az ebben a nem módosítható szakaszban található összetevőkben elindul. 

#### <a name="operating-system-data"></a>Operációs rendszer adatai 

Fontos megjegyezni, hogy a végrehajtható fájlok és adatok, amelyek futásidőben változtathatók (és nem kritikus fontosságúak az operációs rendszer működése szempontjából), elvethetők és újra létre is állíthatók, ha az adatok sérültek vagy sérültek. A nagy értékű, változtatható állapot vagy funkcionálisan szükséges ahhoz, hogy az operációs rendszer megmaradjon, vagy az operációs rendszer leállításakor és Windows/vagy a támogatott operációsrendszer- és eszközforgatókönyvek által támogatott újraindítások során is megmaradjon. Példák nagy értékű, testreszabható állapotra:
  * A rendszergazda által konfigurált globális eszközbeállítások, például a hely letiltása minden felhasználó számára.
  * A Wi-Fi hálózati kapcsolat adateszköz által meg nem ett hálózatokhoz és a kapcsolódó kapcsolati jelszavakhoz fér hozzá.
  * Összeomlási memóriakép, beleértve a beállításokat és a naplókat.
  * Az újonnan felderített eszközökről igény szerint letöltött illesztőprogramok.
A 2. HoloLens nagy értékű, módosítható állapota az operációs rendszer adatbiztonsági helyén található, mentett fájlként a lemezen vagy egy megőrzött beállításjegyzék-struktúrában.

#### <a name="user-data"></a>Felhasználói adatok

Az utolsó állapotkategória az UWP-alkalmazások vagy az operációs rendszer által előállított vagy megőrzött felhasználói adatokat jelöli. Az összes ismert felhasználói mappa, például a Letöltések, Dokumentumok, Videók, felhasználói profilok és HKEY_CURRENT_USER is ezen a helyen tárolódnak. Ezek az adatok nem bonthatóak ki megfelelő hitelesítő adatok nélkül; További információ az adatok védelméről: Titkosítás [és adatvédelem.](security-encryption-data-protection.md)

##  <a name="isolation"></a>Elkülönítés

Ennek az egyensúlynak az eléréséhez a 2. HoloLens rendelkezik egy alapvető operációs rendszerrel, amely olyan elsődleges funkciókhoz használható, mint a rendszerindítás, a hardvervezérlés, a bejelentkezés stb. Az alapvető operációs rendszeren csak két alkalmazáskészlet fut – előre telepített alkalmazások és UWP-alkalmazások.

## <a name="code-signing"></a>Kódalá aláírása

A digitális aláírási kód lehetővé teszi annak alárendeltségét, hogy a végrehajtható fájlok és szkriptek nem módosultak, mivel megbízható forrás írta alá őket, így hitelességet és integritást biztosítva. Alapértelmezés szerint a Microsoft HoloLens 2 megbízhatósági kapcsolattal rendelkező Microsoft Store. A rendszergazdák a [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) és [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp) CSP-k segítségével adhatnak hozzá új tanúsítványokat az eszközhöz. Emellett az [AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) házirend használatával megbíznak a további, saját használatú vagy üzletági [alkalmazásokban.](/intune/apps/lob-apps-windows) A tanúsítványok a helyi számítógép tanúsítványtárolójában találhatók, amelyet "Eszköz" használata esetén a HKLM/Root, "Felhasználó" használata esetén pedig a HKCU tárol.

## <a name="defender-protections"></a>Defender-védelem
HoloLens 2. Microsoft-szolgáltatások magas szintű biztonságot ad a felhasználóknak:

* [A Defender SmartScreent](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) az operációs Windows automatikusan engedélyezi a Windows Holographicon, és védelmet nyújt az adathalászat és a kártevők ellen, valamint a potenciálisan kártékony fájlok letöltésével szemben az Edge-ben. A felhasználó nem tudja kikapcsolni, de a szabályzat segítségével letilthatja.

* [A Defender tűzfal](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) blokkolja az eszközre és az eszközről be- és visszaáramló jogosulatlan hálózati forgalmat. Alapértelmezés szerint engedélyezve van, és az ügyfél nem konfigurálható helyi műveletekkel vagy szabályzattal. 

* [Windows Defender alkalmazásvezérlés:](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview)HoloLens 2. HoloLens támogatja a WDAC-t, amely lehetővé teszi, hogy a rendszergazda alkalmazásvezérlési szabályzatokat toljon le az eszközre. További információ: [WDAC használata HoloLens 2 eszközön az MSFT Intune-nal.](/mem/intune/configuration/custom-profile-hololens) 

A rendszergazdák az [AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) és a böngésző viselkedésével kezelhetik a SmartScreen viselkedését a [következő szabályzatokkal:](/windows/client-management/mdm/policy-csps-supported-by-hololens2). 

