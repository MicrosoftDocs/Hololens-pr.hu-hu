---
title: Állapotok elkülönítése és elkülönítése
description: Megismeri az állapotelválasztást, az elkülönítést, a kódalá aláírást és a defender alkalmazásokat a HoloLens 2 vegyes valóságú eszközön.
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
ms.openlocfilehash: 0487ea49c706c753f4dfca7da7daa499d1715e9f
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036228"
---
# <a name="state-separation-and-isolation"></a>Állapotok elkülönítése és elkülönítése

Az állapotok elkülönítése és elkülönítése megvédi a Hololens 2 operációs rendszer kritikus részeit a változásoktól, például azokat, amelyek az operációs rendszer megbízható állapotba való rendszerindításához szükségesek. Az elkülönítési technológiával a nem megbízható alkalmazásokat áthelyezi egy elkülönített környezetbe, hogy azok ne befolyásolják a rendszer biztonságát.

## <a name="state-separation"></a>Állapotok elkülönítése

A 2. HoloLens állapot-elkülönítés jelentősen javítja a biztonságot és a javíthatóságot (frissítés), és segít megvédeni az alkalmazásadatokat.  Az állapotok elkülönítése a következőképpen működik:
  * Az alapvető operációs rendszer az operációs rendszer központi kötetében van tárolva (megbízható vagy ellenőrzött Microsoft operációs rendszer frissíti az operációs rendszert).
  * Az operációs rendszer futásidőben módosítható részei (például letölthető illesztőprogramok és konfigurációk), az adatok particionálása és biztonságos, különálló tárolási helyeken való tárolása további állapot-elkülönítést biztosít.
  * Minden biztonságos tárolóhelyhez különböző biztonsági szabályzatok vannak társítva, amelyek különböző biztonsági előnyöket kínálnak, amint azt a következő szakasz részletezi.

## <a name="state-separation-benefits"></a>Az állapotok elkülönítésének előnyei

  * Biztonság: A 2. HoloLens kiemelt állapot-elkülönítés jelentősen javítja a platform integritását, a kártevők elleni védelmet és a felhasználói adatvédelmet. Az operációs rendszer nem elterjedhető részének elkülönítésével és írási vagy integritásvédelemre való biztosításával az állapotelválasztás rendkívül megnehezíti a kártevők számára a ritka megőrzésű újraindítások során való megőrzését. 
  * Frissítések: HoloLens 2. frissítéssel, miután az alapvető operációs rendszer nem módosítható, és az eszközön található többi adattól tisztán el lett választva, a frissítések egyszerűvé és megbízhatóvá válnak.  Emellett az állapotok elkülönítése lefekteti a jelentősen gyorsabb frissítések alapvető alaprendszerét, amely lehetővé teszi az operációs rendszer egyetlen lépésben (atomi egységben) való cseréjét.
  * Eszköz alaphelyzetbe állítása: HoloLens 2. alaphelyzetbe állítása törli a felhasználó által létrehozott adatokat és felhasználói alkalmazásadatokat az eszközön – beleértve a belső és külső tárolási helyeket is. Megőrzi a jelenlegi operációsrendszer-alkalmazásokat és a biztonsági kritikus fontosságú alkalmazásokat, valamint a Microsoft és az OEM által testre szabott (előre telepített) alkalmazásokat. Ezek az előre telepített alkalmazások rehidratálhatóak az eszközön az alaphelyzetbe állítás befejezése után

### <a name="state-separation-states"></a>Állapotok elkülönítési állapotai

Az állapotok elkülönítése biztosítja, hogy az operációs rendszert csak a Microsoft megbízható eszközösszetevői változtatják meg, és csak a nagy értékű állapot marad meg az újraindítások között; más rendszerállapot csak a rendszerindítási munkamenet időtartamára létezik, és az újraindítás után törlődik. Az állapotok elkülönítése gyorsan visszaállítja az eszközt a gyári állapotba. Windows Holographic for Business államok a következő kategóriákba sorolhatók:
  * Alapvető operációs rendszer – Nem érhető el állapot
  * Operációsrendszer-adatok – Módosítható állapot 
  * Felhasználói adatok – Módosítható állapot

A következő HoloLens két operációs rendszert ismertet.

#### <a name="core-operating-system"></a>Alapvető operációs rendszer

A nem módosítható állapot olyan végrehajtható fájlokból és adatokból áll, amelyek nem módosíthatók, és a Microsoft csak a frissítések telepítése során módosítható. Az alapvető operációs rendszer ilyen frissítése során egy új lemezkép lesz engedélyezve, amely a legújabb kívánt működési állapotot tartalmazza.
A nem állítható állapot csak olvashatóként van megjelölve (vagy egyéb módon integritásvédelem alatt áll), ami megakadályozza az emelt szintű jogosultságokkal rendelkező kártevők megőrzését. A következő végrehajtható fájlok és adatok nem módosítható állapotban vannak védve:
  * Windows Holografikus beérkezett üzenetek illesztőprogramjai
  * Operációs rendszer bináris fájlok
  * Windows-illesztőprogramok
  * Statikus Windows beállításjegyzék-Windows (HKLM) tárolt Holographic-beállítások
    * Példa: A HKLM a gépre telepített alkalmazások konfigurációs adatait tárolja. A hardverek és a hozzájuk tartozó illesztőprogramok észleléséhez szükséges információkat is tárolja.
Azáltal, hogy ezek nem módosítható (integritás és csak olvasható védelem) állapotban vannak védve, biztosítjuk, hogy az alapvető operációs rendszer mindig megbízható állapotban elindul. Emellett az eszköz alaphelyzetbe állításakor biztosíthatja, hogy az eszköz csak az ebben a nem módosítható szakaszban található összetevőkben elindul. 

#### <a name="operating-system-data"></a>Operációs rendszer adatai 

Fontos megjegyezni, hogy a végrehajtható fájlok és adatok, amelyek futásidőben változtathatók (és nem kritikus fontosságúak az operációs rendszer működése szempontjából), elvethetők és újra létre is állíthatók, ha az adatok sérültek vagy sérültek. A nagy értékű, változtatható állapot vagy funkcionálisan szükséges ahhoz, hogy az operációs rendszer megőrzendő legyen, vagy az operációs rendszer leállításakor és/vagy a támogatott Windows és eszközforgatókönyvek által támogatott újraindítások során is megmaradjon. Példák a nagy értékű, testreszabható állapotra:
  * A rendszergazda által konfigurált globális eszközbeállítások, például a hely letiltása az összes felhasználó számára.
  * A Wi-Fi-hálózati kapcsolat hozzáfér az adateszköz által meg nem ett hálózatokhoz és a társított kapcsolati jelszavakhoz.
  * Összeomlási memóriakép, beleértve a beállításokat és a naplókat.
  * Az újonnan felderített eszközökről igény szerint letöltött illesztőprogramok.
A 2. HoloLens nagy értékű, módosítható állapota az operációs rendszer Adatbiztonsági helye, amely lehet egy lemezen mentett fájl vagy egy megőrzött beállításjegyzék-struktúra.

#### <a name="user-data"></a>Felhasználói adatok

Az utolsó állapotkategória az UWP-alkalmazások vagy az operációs rendszer által előállított vagy megőrzött felhasználói adatokat jelöli. Az összes ismert felhasználói mappa, például a Letöltések, Dokumentumok, Videók, felhasználói profilok és HKEY_CURRENT_USER is ezen a helyen tárolódnak. Ezek az adatok nem bonthatóak ki a megfelelő hitelesítő adatok nélkül; További információ az adatok védelméről: Titkosítás [és adatvédelem.](security-encryption-data-protection.md)

##  <a name="isolation"></a>Elkülönítés

Az egyensúly eléréséhez a 2. HoloLens rendelkezik egy alapvető operációs rendszerrel, amely olyan elsődleges funkciókhoz használható, mint a rendszerindítás, a hardvervezérlés, a bejelentkezés stb. Az alapvető operációs rendszeren csak két alkalmazáskészlet fut – előre telepített alkalmazások és UWP-alkalmazások.

## <a name="code-signing"></a>Kódalá aláírás

A digitális aláírási kód lehetővé teszi annak pótlását, hogy a végrehajtható fájlok és a parancsfájlok nem módosultak, mivel egy megbízható forrás írta alá őket, így hitelességet és integritást biztosítva. Alapértelmezés szerint a Microsoft HoloLens 2 megbízhatósági kapcsolattal rendelkező Microsoft Store. A rendszergazdák a [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) és [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp) CSP-k segítségével adhatnak hozzá új tanúsítványokat az eszközhöz. Emellett az [AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) szabályzat használatával megbíznak a további, saját használatra telepített vagy üzletági [alkalmazásokban.](/intune/apps/lob-apps-windows) A tanúsítványok a helyi gép tanúsítványtárolójában találhatók, amelyet "Eszköz" vagy "Felhasználó" használata esetén a HKLM/Root tárol.

## <a name="defender-protections"></a>Defender-védelem
HoloLens 2. Microsoft-szolgáltatások magas szintű biztonságot ad a felhasználóknak:

* Az operációs rendszer automatikusan engedélyezi a [Defender SmartScreent](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) Windows Holographicban, és védelmet nyújt az adathalászat és a kártevők ellen, valamint a potenciálisan rosszindulatú fájlok letöltésével szemben az Edge-ben. A felhasználó nem tudja kikapcsolni, de szabályzaton keresztül letilthatja.

* [A Defender tűzfal](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) blokkolja az eszközre és az eszközről be- és vissza áramló jogosulatlan hálózati forgalmat. Alapértelmezés szerint engedélyezve van, és az ügyfél nem konfigurálható helyi műveletek vagy szabályzatok segítségével. 

* [Windows Defender alkalmazásvezérlés:](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview)a 2. HoloLens támogatja a WDAC-t, amely lehetővé teszi, hogy a rendszergazda alkalmazásvezérlési szabályzatokat lekulljon az eszközre. További információ: [WDAC használata HoloLens 2 eszközön az MSFT Intune-nal.](/mem/intune/configuration/custom-profile-hololens) 

A rendszergazdák az [AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) és a böngésző viselkedésével kezelhetik a SmartScreen viselkedését a [következő szabályzatokkal:](/windows/client-management/mdm/policy-csps-supported-by-hololens2). 

