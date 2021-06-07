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
ms.openlocfilehash: 60d6d7c0e281395957ce9158144a5f3d60927682
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379618"
---
# <a name="state-separation-and-isolation"></a>Állapotok elkülönítése és elkülönítése

Az állapotok elkülönítése és elkülönítése megvédi a Hololens 2 operációs rendszer kritikus fontosságú részeit a változásoktól, például azokat, amelyek az operációs rendszer megbízható állapotba való rendszerindításához szükségesek. Az elkülönítési technológiával a nem megbízható alkalmazásokat áthelyezi egy elkülönített védőkörnyezetbe, így biztosítva, hogy azok ne befolyásolják a rendszer biztonságát.

## <a name="state-separation"></a>Állapotok elkülönítése

A HoloLens 2-ben az állapotok elkülönítése jelentősen javítja a biztonságot és a szervizelhetőséget (frissítés), és segít megvédeni az alkalmazásadatokat.  Az állapotok elkülönítése a következőképpen működik:
  * Az alapvető operációs rendszer tárolása az operációs rendszer központi kötetében (megbízható vagy ellenőrzött Microsoft operációs rendszer az operációs rendszer frissítésével).
  * Az operációs rendszer futásidőben módosítható részei (például letölthető illesztőprogramok és konfigurációk), az adatok particionálása és biztonságos, különálló tárolási helyeken való tárolása további állapotok elkülönítésével.
  * Minden biztonságos tárolóhelyhez különböző biztonsági szabályzatok vannak társítva, amelyek a következő szakaszban részletezett különböző biztonsági előnyöket kínálnak.

## <a name="state-separation-benefits"></a>Az állapotok elkülönítésének előnyei

  * Biztonság: A HoloLens 2-ben kiemelt állapotelválasztás jelentősen javítja a platform integritását, a kártevők elleni védelmet és a felhasználói adatvédelmet. Az operációs rendszer nem elterjedő részének elkülönítésével és írási vagy integritásvédelemre való biztosításával az állapotelválasztás rendkívül megnehezíti a kártevők számára a hideg újraindítások során való megőrzését. 
  * Frissítések: A HoloLens 2-ben, miután az alapvető operációs rendszer nem módosítható, és egyértelműen el lett választva az eszközön található többi adattól, a frissítések egyszerűvé és megbízhatóvá válnak.  Emellett az állapotok elkülönítése lefekteti a jelentősen gyorsabb frissítések alapvető alaprendszerét, amely lehetővé teszi az operációs rendszer egyetlen lépésben (atomi egységben) való cseréjét.
  * Eszköz alaphelyzetbe állítása: A HoloLens 2 alaphelyzetbe állítása törli a felhasználó által létrehozott adatokat és felhasználói alkalmazásadatokat az eszközön – beleértve a belső és külső tárolási helyeket is. Megőrzi a jelenlegi operációsrendszer-alkalmazásokat és a biztonsági szempontjából kritikus alkalmazásokat, valamint a microsoftos és oem által testre szabott (előre telepített) alkalmazásokat. Ezek az előre telepített alkalmazások rehidratálhatóak az eszközön az alaphelyzetbe állítás befejezése után

### <a name="state-separation-states"></a>Állapotok elkülönítési állapotai

Az állapotok elkülönítése biztosítja, hogy az operációs rendszert csak a Microsoft megbízható eszközösszetevői változtatják meg, és csak a nagy értékű állapot marad meg az újraindítások között; más rendszerállapot csak a rendszerindítási munkamenet időtartamára létezik, és az újraindítás után törlődik. Az állapotok elkülönítése gyorsan visszaállítja az eszközt a gyári állapotba. Windows Holographic for Business az alábbi kategóriákba sorolhatók:
  * Alapvető operációs rendszer – Nem elterjedő állapot
  * Operációs rendszer adatai – Módosítható állapot 
  * Felhasználói adatok – Módosítható állapot

A holoLens 2 operációs rendszerek mindegyikét a következő szakaszban ismertetjük.

#### <a name="core-operating-system"></a>Alapvető operációs rendszer

A nem módosítható állapot olyan végrehajtható fájlokból és adatokból áll, amelyek nem módosíthatók, és a Microsoft csak a frissítések telepítése során módosítható. Az alapvető operációs rendszer ilyen frissítése során a rendszer engedélyezi a legújabb kívánt működési állapotot tartalmazó új lemezképet.
A nem elterjedő állapot csak olvashatóként van megjelölve (vagy egyéb módon integritásvédelem alatt áll), ami megakadályozza az emelt szintű jogosultságokkal rendelkező kártevők megőrzését. A következő végrehajtható fájlok és adatok nem módosítható állapotban vannak védve:
  * Windows Holographic inbox illesztőprogramok
  * Operációs rendszer bináris fájlok
  * Windows beérkezett üzenetek illesztőprogramjai
  * A Windows beállításjegyzék-struktúra (HKLM) által tárolt statikus Windows Holographic-beállítások
    * Példa: A HKLM a gépre telepített alkalmazások konfigurációs adatait tárolja. A hardverek és a hozzájuk tartozó illesztőprogramok észleléséhez szükséges adatokat is tárolja.
Azáltal, hogy ezek nem módosítható (integritás és csak olvasható védelem) állapotban vannak védve, biztosítjuk, hogy az alapvető operációs rendszer mindig megbízható állapotban elindul. Emellett az eszköz alaphelyzetbe állításakor gondoskodhat róla, hogy az eszköz csak az ebben a nem módosítható szakaszban található összetevőkben elindul. 

#### <a name="operating-system-data"></a>Operációs rendszer adatai 

Fontos megjegyezni, hogy a végrehajtható fájlok és adatok, amelyek futásidőben változtathatók (és nem kritikus fontosságúak az operációs rendszer működése szempontjából), elvethetők és újra létre is állíthatók, ha az adatok sérültek vagy sérültek. A nagy értékű, változtatható állapot vagy funkcionálisan szükséges ahhoz, hogy az operációs rendszer megmaradjon, vagy az operációs rendszer leállításakor és/vagy a támogatott Windows operációs rendszerek és eszközforgatókönyvek által történő újraindítások során is megmaradjon. Példák nagy értékű, testreszabható állapotra:
  * A rendszergazda által konfigurált globális eszközbeállítások, például a hely letiltása minden felhasználó számára.
  * A Wi-Fi hálózati kapcsolat adateszköz által meg nem ett hálózatokhoz és a kapcsolódó kapcsolati jelszavakhoz fér hozzá.
  * Összeomlási memóriakép, beleértve a beállításokat és a naplókat.
  * Az újonnan felderített eszközökről igény szerint letöltött illesztőprogramok.
A HoloLens 2-ben a nagy értékű, módosítható állapot az operációs rendszer adatbiztonsági helye, amely lehet egy lemezen mentett fájl vagy egy megőrzött beállításjegyzék-struktúra.

#### <a name="user-data"></a>Felhasználói adatok

Az utolsó állapotkategória az UWP-alkalmazások vagy az operációs rendszer által előállított vagy megőrzött felhasználói adatokat jelöli. Az összes ismert felhasználói mappa, például a Letöltések, Dokumentumok, Videók, felhasználói profilok és HKEY_CURRENT_USER is ezen a helyen tárolódnak. Ezek az adatok nem bonthatóak ki megfelelő hitelesítő adatok nélkül; További információ az adatok védelméről: Titkosítás [és adatvédelem.](security-encryption-data-protection.md)

##  <a name="isolation"></a>Elkülönítés

Ennek az egyensúlynak az eléréséhez a HoloLens 2 egy alapvető operációs rendszerrel rendelkezik, amely olyan elsődleges funkciókhoz használható, mint a rendszerindítás, a hardvervezérlés, a bejelentkezés stb. Az alapvető operációs rendszeren csak két alkalmazáskészlet fut – előre telepített alkalmazások és UWP-alkalmazások.

## <a name="code-signing"></a>Kódalá aláírása

A digitális aláírási kód lehetővé teszi annak alárendeltségét, hogy a végrehajtható fájlok és szkriptek nem módosultak, mivel megbízható forrás írta alá őket, így hitelességet és integritást biztosítva. A HoloLens 2 alapértelmezés szerint a Microsoft és az Microsoft Store. A rendszergazdák a [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) és [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) CSP-k segítségével adhatnak hozzá új tanúsítványokat az eszközhöz. Emellett az [AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) házirend használatával megbíznak a további, saját használatú vagy üzletági [alkalmazásokban.](https://docs.microsoft.com/intune/apps/lob-apps-windows) A tanúsítványok a helyi számítógép tanúsítványtárolójában találhatók, amelyet "Eszköz" használata esetén a HKLM/Root, "Felhasználó" használata esetén pedig a HKCU tárol.

## <a name="defender-protections"></a>Defender-védelem
A HoloLens 2 Microsoft-szolgáltatások segítségével magas szintű biztonságot ad a felhasználóknak:

* [A Defender SmartScreent](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) az operációs rendszer automatikusan engedélyezi a Windows Holographic rendszeren, és védelmet nyújt az adathalászat és a kártevők ellen, valamint a potenciálisan kártékony fájlok letöltésével szemben az Edge-ben. A felhasználó nem tudja kikapcsolni, de a szabályzat segítségével letilthatja.

* [A Defender tűzfal](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) blokkolja az eszközre és az eszközről be- és visszaáramló jogosulatlan hálózati forgalmat. Alapértelmezés szerint engedélyezve van, és az ügyfél nem konfigurálható helyi műveletekkel vagy szabályzattal. 

* [Windows Defender alkalmazásvezérlés:](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview)A HoloLens 2 támogatja a WDAC-t, amely lehetővé teszi a rendszergazda számára az alkalmazásvezérlési szabályzatok leküldését az eszközre. További információ: [WDAC használata HoloLens 2-eszközökön az MSFT Intune-nal.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) 

A rendszergazdák az [AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) és a böngésző viselkedésével kezelhetik a SmartScreen viselkedését a [következő szabályzatokkal:](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2). 

