---
title: HoloLens 2. implementáció és felügyelt eszközök hibaelhárítása
description: 2 HoloLens hibaelhárítása vállalati környezetben
author: beelia
ms.author: v-beehanson
ms.date: 6/22/2021
ms.topic: article
keywords: hibaelhárítás
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 2e997514be5d067ce5e9bd7f3611b464d19a6fad
ms.sourcegitcommit: b9cd7ed5edb98249c609b547b90587863ea1cb9e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/01/2021
ms.locfileid: "129364587"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Implementáció és felügyelt eszközök hibaelhárítása

Ez a cikk azt ismerteti, hogyan oldható meg több probléma, illetve hogyan válaszolható meg a 2. HoloLens kezelése.

>[!IMPORTANT]
> A hibaelhárítási eljárás elkezdése előtt győződjön meg arról, hogy az eszköz **20–40%-os** akkumulátor-kapacitással rendelkezik, ha lehetséges. A [tápkapcsoló alatt](hololens2-setup.md#lights-that-indicate-the-battery-level) található akkumulátorjelző világítással gyorsan ellenőrizheti az akkumulátor kapacitását anélkül, hogy bejelentkezik az eszközre.


<a id="list"></a>
- [EAP-hibaelhárítás](#eap-troubleshooting)
- [Wi-Fi-hibaelhárítás](#wi-fi-troubleshooting)
- [Hálózati hibaelhárítás](#network-troubleshooting)
- [Nem lehet bejelentkezni egy korábban HoloLens eszközre](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Nem lehet bejelentkezni a Holographic 21H1 Windows frissítése után](#cant-login-after-updating-to-windows-holographic-21h1)
- [Az Autopilot hibaelhárítása](#autopilot-troubleshooting)
- [Felügyelt HoloLens eszközök – gyakori kérdések](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>EAP-hibaelhárítás
1. Ellenőrizze, hogy Wi-Fi profil rendelkezik-e a megfelelő beállításokkal:
    - Konfigurálja megfelelően az EAP-típust. Gyakori EAP-típusok: EAP-TLS (13), EAP-TTLS (21) és PEAP (25).
    - Ellenőrizze a Wi-Fi SSID nevét, és ellenőrizze, hogy egyezik-e a HEX-sztring nevével.
    - Győződjön meg arról, hogy az EAP-TLS-hez a TrustedRootCA tartalmazza a kiszolgáló megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványának SHA-1 kivonatát. A Windows számítógépen a "certutil.exe -dump cert_file_name" parancs egy tanúsítvány SHA-1 kivonatsringet fog mutatni.
2. Gyűjtse össze a hálózati csomagok rögzítését a hozzáférési pont, a vezérlő vagy az AAA-kiszolgáló naplóiban, hogy megtudja, hol nem sikerül az EAP-munkamenet.
    - Ha az EAP-identitás HoloLens, ellenőrizze, hogy az identitás megfelelően lett-e kiépítve egy Wi-Fi-tanúsítványon keresztül.
    - Ha a kiszolgáló elutasítja a HoloLens ügyfél-tanúsítványát, ellenőrizze, hogy a szükséges ügyfél-tanúsítvány ki lett-e építve az eszközön.
    - Ha HoloLens elutasítja a kiszolgálótanúsítványt, ellenőrizze, hogy a kiszolgáló legfelső szintű hitelesítésszolgáltatói tanúsítványa ki lett-e építve a HoloLens.
3. Ha a vállalati profil egy Wi-Fi csomaggal van kiépítve, fontolja meg a kiépítési csomag alkalmazását egy Windows 10 számítógépen. Ha a számítógép Windows 10 is meghibásodik, kövesse a Windows 802.1X hitelesítési hibaelhárítási útmutatóját.
4. Küldjön visszajelzést a Visszajelzési központ.

[Vissza a listához](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi hibaelhárítás

Ha nem tud csatlakozni a HoloLens egy Wi-Fi hálózathoz, az Wi-Fi próbálkozhat:

1. Győződjön meg arról, hogy a Wi-Fi be van kapcsolva. Ezt a Start kézmozdulattal ellenőrizheti, majd válassza Gépház > a & Internet > Wi-Fi lehetőséget. Ha Wi-Fi be van kapcsolva, próbálja meg újra bekapcsolni.
2. Lépjen közelebb az útválasztóhoz vagy a hozzáférési ponthoz.
3. Indítsa újra Wi-Fi útválasztót, majd indítsa újra HoloLens. Próbáljon meg újból csatlakozni.
4. Ha ezek egyike sem működik, ellenőrizze, hogy az útválasztó a legújabb belső vezérlőprogramot használja-e. Ezt az információt a gyártó webhelyén találja.

Amikor vállalati vagy szervezeti fiókba jelentkezik be az eszközön, az a Mobile Eszközkezelés (MDM) szabályzatot is alkalmazhatja, ha a házirendet a rendszergazda konfigurálta.

[Vissza a listához](#list)

## <a name="network-troubleshooting"></a>Hálózati hibaelhárítás
Ha a hálózati problémák akadályt gördülnek a HoloLens 2. kód sikeres üzembe helyezése és használata előtt, konfigurálja a Fiddlert és/vagy a Wiresharkot a HTTP/HTTPS-forgalom rögzítésére és elemzésére. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>A Fiddler konfigurálása HTTP-forgalom rögzítésére
A Fiddler egy webes hibakeresési proxy, amely a HTTP(S) problémák elhárítására szolgál. A számítógép által lekért http-kéréseket rögzíti, és mindent rögzít, ami hozzá van társítva. A HTTPS-alkalmazások végfelhasználói hitelesítési problémáinak feltárása jobb hatékonyságot és hatékonyságot biztosít a HoloLens két használati esetben. 

#### <a name="prerequisites"></a>Előfeltételek
 
- HoloLens 2 eszköznek és a számítógépnek ugyanazon a hálózaton kell lennie
- Jegyezze fel a számítógép IP-címét

#### <a name="install-and-configure-fiddler"></a>A Fiddler telepítése és konfigurálása

1. A számítógépen telepítse és [indítsa el](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) a Fiddlert.  
1. A számítógépen – konfigurálja a Fiddlert úgy, hogy engedélyezze a távoli számítógépek csatlakozását.
    1. A Fiddler Gépház -> kapcsolatokhoz.
    1. Figyelje meg a Fiddler figyelőportját (az alapértelmezett érték: 8866).
    1. Jelölje be A távoli számítógépek csatlakozásának engedélyezése jelölőnégyzetet.
    1. Kattintson a Mentés gombra.
3. A 2. HoloLens konfigurálja a Fiddlert<sup>1. proxykiszolgálóként:</sup>
    1. Nyissa meg a Start menü, és válassza a Gépház.
    1. Válassza a Network & internet, majd a proxy lehetőséget a bal oldali menüben.
    1. Görgessen le a Manual proxy setup (Manuális proxybeállítás) elemre, és a Use a proxy server (Proxykiszolgáló használata) kapcsolót a On (Be) beállításra.
    1. Adja meg annak a számítógépnek az IP-címét, ahol a Fiddler telepítve van.
    1. Adja meg a fent feljegyzett portszámot (az alapértelmezett érték a 8866).
    1. Kattintson a Mentés gombra.

<sup>1</sup> A 20279.1006+ buildek (insiders és a következő kiadás) esetén a következő lépésekkel konfigurálhatja a proxyt:
1. Nyissa meg Start menü, és nyissa meg Wi-Fi hálózat Tulajdonságok lapját. 
1. Görgessen le a Proxyhoz.
1. Váltsa át manuális telepítésre.
1. Adja meg annak a számítógépnek az IP-címét, ahol a Fiddler telepítve van.
1. Adja meg a fent feljegyzett portszámot (az alapértelmezett érték a 8866).
1. Kattintson az Alkalmaz gombra.
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>A 2. HoloLens HTTPS-forgalmának visszafejtése

1. A számítógépen – exportálja a Fiddler-tanúsítványt.
    1. A Fiddler Gépház -> HTTPS-hez, és bontsa ki a Speciális Gépház.
    2. Kattintson a Fiddler-tanúsítvány exportálása elemre. Ez az asztalra lesz mentve.
    3. Helyezze át a tanúsítványt a 2. HoloLens mappájába.

2.  A 2. HoloLens – importálja a Fiddler-tanúsítványt.
    1. A -Gépház -> -Security -> Certificates (Frissítés és biztonság – tanúsítványok) > meg.
    2. Kattintson a Tanúsítvány telepítése elemre, keresse meg a Letöltések mappát, és válassza ki a Fiddler-tanúsítványt.
    3. Módosítsa a Store Location (Áruház helye) helyére a Local Machine (Helyi gép) adatokat.
    4. Módosítsa a tanúsítványtárolót a főtanúsítványra.
    5. Válassza a Telepítés gombot.
    6. Győződjön meg arról, hogy a tanúsítvány megjelenik a tanúsítványok listájában. Ha nem, ismételje meg ezeket a lépéseket.

#### <a name="inspect-https-sessions"></a>HTTP(S) munkamenetek vizsgálata

A számítógépen a Fiddler HoloLens 2. élő HTTP-munkameneteit. A Fiddler Vizsgálók panelje különböző nézetekben képes HTTP(S) kérést/választ mutatni. A "Nyers" nézet például egyszerű szövegként jeleníti meg a nyers kérést vagy választ. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>A Wireshark konfigurálása a hálózati forgalom rögzítésére
A Wireshark egy hálózati protokollelemző, amely a 2. eszköz tcp/UDP-forgalmának HoloLens vizsgálja. Így könnyen azonosítható a hálózat és a HoloLens 2 közötti forgalom , azaz hogy mekkora a forgalom, milyen gyakorisággal, mekkora késés van bizonyos ugrások között, és így tovább.

#### <a name="prerequisites"></a>Előfeltételek:
- A számítógépnek internet-hozzáféréssel kell rendelkezik, és támogatnia kell az internet-megosztást Wi-Fi-n keresztül.

#### <a name="install-and-configure-wireshark"></a>A Wireshark telepítése és konfigurálása
1. A számítógépen telepítse a [Wiresharkot.](https://www.wireshark.org/#download)
1. A számítógépen – engedélyezze a Mobil elérési pont számára az internetkapcsolat megosztását a Wi-Fi-ről.
1. A számítógépén indítsa el a Wiresharkot, és rögzítse a mobil elérési pont felületéről származó forgalmat. 
1. A 2. HoloLens módosítsa a Wi-Fi a számítógép Mobil elérési útjára. HoloLens 2 IP-forgalmat a Wiresharkban fog mutatni.

#### <a name="analyze-wireshark-logs"></a>Wireshark-naplók elemzése
A Wireshark szűrői segíthetnek kiszűrni az érdeklődési köröket. 

Tekintse meg az eredeti [blogot.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)

[Vissza a listához](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Nem lehet bejelentkezni egy korábban HoloLens eszközre

Ha az eszközt korábban már beállította valaki más számára, akár egy ügyfél, akár egy korábbi alkalmazott számára, és nincs [](/intune/remote-actions/devices-wipe) jelszava az eszköz feloldásához, az Intune-nal távolról is törölheti az eszközt. Az eszköz ezután újra flash eszközt használ.  
> [!IMPORTANT]
> Az eszköz összes részletének törlésével győződjön meg arról, hogy a **Regisztrációs állapot** és felhasználói fiók megtartása jelölőnégyzet nincs bejelölve.

[Vissza a listához](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Nem lehet bejelentkezni, miután frissített Windows Holographic 21H1-re

### <a name="symptoms"></a>Hibajelenségek
- A PIN-kód használata a megfelelő PIN-kód megadása után sikertelen lesz.
- A webes bejelentkezési módszer használata sikertelen lesz, miután sikeresen bejelentkezik a weblapra.
- Az eszköz nem szerepel az "Azure AD-hez csatlakozott" Azure Portal [-> Azure Active Directory](https://portal.azure.com/) -> eszközök között.

### <a name="cause"></a>Ok
Előfordulhat, hogy az érintett eszköz törölve lett az Azure AD-bérlőből. Ez például a következő miatt fordulhat elő:

- Egy rendszergazda vagy felhasználó törölte az eszközt a Azure Portal PowerShell használatával.
- Az eszköz inaktivitás miatt el lett távolítva az Azure AD-bérlőből. A hatékony felügyelt környezet érdekében általában azt javasoljuk a rendszergazdáknak, hogy távolítsanak el elavult, inaktív eszközöket az [Azure AD-bérlőjükből.](/azure/active-directory/devices/manage-stale-devices)

Ha egy érintett eszköz a törlés után ismét megpróbál kapcsolatba lépni az Azure AD-bérlővel, nem fog tudni hitelesítést végezni az Azure AD-val. Ez a hatás gyakran láthatatlan az eszköz felhasználója számára, mivel a gyorsítótárazott, PIN-kódot használó bejelentkezés továbbra is lehetővé teszi a felhasználó bejelentkezését.

### <a name="mitigation"></a>Kockázatcsökkentés
A törölt adatokat jelenleg nem lehet HoloLens az Azure AD-be. Az érintett eszközöket az eszköz újrafedődésére vonatkozó utasítások szerint kell [megtisztítani.](hololens-recovery.md#clean-reflash-the-device)

[Vissza a listához](#list)

## <a name="autopilot-troubleshooting"></a>Az Autopilot hibaelhárítása

Az alábbi cikkek hasznos forrást hatnak az AutoPilot-problémák további információinak és hibaelhárításának elsajátítása érdekében. A cikkek azonban a Windows 10 Desktopra épülnek, és nem minden információ vonatkozhat a HoloLens:

- [Windows Autopilot – ismert problémák](/mem/autopilot/known-issues)
- [Az Windows kapcsolatos problémák elhárítása a Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – Szabályzatütközések](/mem/autopilot/policy-conflicts)

[Vissza a listához](#list)

## <a name="managed-hololens-devices-faqs"></a>Felügyelt HoloLens eszközök – gyakori kérdések

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Használhatom a System Center Configuration Manager (SCCM) a HoloLens kezelésére?

Nem. Az MDM-rendszert kell használnia a HoloLens kezeléséhez.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Használhatom a Active Directory Domain Services (AD DS) a HoloLens fiókok kezeléséhez?

Nem. A Azure Active Directory (Azure AD) használatával kell kezelnie a HoloLens fiókjait.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Képes HoloLens automatikus adatrögzítési rendszerek (ADCS) automatikus regisztrációja?

Nem.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Részt HoloLens az integrált Windows hitelesítésben?

Nem.

### <a name="does-hololens-support-branding"></a>Támogatja HoloLens a védjegyezést?

Nem. Ezt a problémát azonban a következő megközelítések egyikével is meg lehet közelítetni:

- Hozzon létre egy egyéni alkalmazást, majd [engedélyezze a Kioszkmódot.](hololens-kiosk.md) Az egyéni alkalmazás védjegyezést is kaphat, és más alkalmazásokat is elindíthat (például Remote Assist).  
- Módosítsa az Azure AD-beli összes felhasználói profilképet a vállalati emblémára. Ez azonban nem minden esetben kívánatos.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Milyen naplózási lehetőségeket kínál HoloLens 2?

A naplózás olyan nyomkövetési adatokra korlátozódik, amelyek fejlesztési vagy hibaelhárítási forgatókönyvekben, vagy az eszközök által a Microsoft-kiszolgálóknak küldött telemetria alapján rögzítettek.

## <a name="questions-about-securing-hololens-devices"></a>Kérdések a HoloLens biztonságról

Lásd [a HoloLens 2 biztonsági információt.](security-overview.md)
Az HoloLens gen eszközökhöz tekintse át ezt [a gyakori kérdéseket.](hololens1-faq-security.yml)

[Vissza a listához](#list)
