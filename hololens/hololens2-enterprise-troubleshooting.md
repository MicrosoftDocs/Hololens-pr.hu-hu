---
title: HoloLens 2. implementáció és felügyelt eszközök hibaelhárítása
description: 2 HoloLens hibaelhárítása vállalati környezetben
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: hibaelhárítás
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636877"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Megvalósítási és felügyelt eszközök hibaelhárítása 

Ez a cikk azt ismerteti, hogyan oldható meg több probléma, illetve hogyan válaszolható meg a 2. HoloLens megvalósítása és kezelése.

>[!IMPORTANT]
> A hibaelhárítási eljárás elkezdése előtt győződjön meg arról, hogy az eszköz **20–40** százalék akkumulátor-kapacitással rendelkezik, ha lehetséges. A [tápkapcsoló alatt](hololens2-setup.md#lights-that-indicate-the-battery-level) található akkumulátorjelző világítással gyorsan ellenőrizheti az akkumulátor kapacitását anélkül, hogy bejelentkezik az eszközre.


<a id="list"></a>
- [EAP-hibaelhárítás](#eap-troubleshooting)
- [Wi-Fi-hibaelhárítás](#wi-fi-troubleshooting)
- [Hálózati hibaelhárítás](#network-troubleshooting)
- [Nem lehet bejelentkezni egy korábban HoloLens eszközre](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Nem lehet bejelentkezni, miután frissített Windows Holographic 21H1-re](#cant-login-after-updating-to-windows-holographic-21h1)
- [Az Autopilot hibaelhárítása](#autopilot-troubleshooting)
- [Felügyelt HoloLens eszközök – gyakori kérdések](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>EAP-hibaelhárítás
1. Ellenőrizze, Wi-Fi profil rendelkezik-e a megfelelő beállításokkal:
    - Az EAP-típus megfelelően van konfigurálva, gyakori EAP-típusok: EAP-TLS (13), EAP-TTLS (21) és PEAP (25).
    - Wi-Fi SSID neve helyes, és hexikáns sztringre illeszkedik.
    - Az EAP-TLS-hez a TrustedRootCA tartalmazza a kiszolgáló megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványának SHA-1 kivonatát. A Windows számítógépen a "certutil.exe -dump cert_file_name" parancs egy tanúsítvány SHA-1 kivonatsringet fog mutatni.
2. Gyűjtse össze a hálózati csomagrögzítést a hozzáférési pont, a vezérlő vagy az AAA-kiszolgáló naplóiban, hogy megtudja, hol nem sikerül az EAP-munkamenet.
    - Ha az EAP-identitás nem HoloLens, ellenőrizze, hogy az identitás megfelelően lett-e Wi-Fi profilon vagy ügyfél-tanúsítványon keresztül.
    - Ha a kiszolgáló elutasítja HoloLens ügyfél-tanúsítványt, ellenőrizze, hogy a szükséges ügyfél-tanúsítvány ki lett-e építve az eszközön.
    - Ha HoloLens elutasítja a kiszolgálótanúsítványt, ellenőrizze, hogy a kiszolgáló legfelső szintű hitelesítésszolgáltatói tanúsítványa ki lett-e építve a HoloLens.
3. Ha a vállalati profil egy kiépítési Wi-Fi keresztül van kiépítve, fontolja meg a kiépítési csomag alkalmazását egy Windows 10 számítógépen. Ha a hiba a Windows 10 is sikertelen, kövesse a Windows 802.1X hitelesítési hibaelhárítási útmutatóját.
4. Küldjön visszajelzést a Visszajelzési központ.

[Vissza a listához](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi hibaelhárítás

Ha nem tud csatlakozni a HoloLens egy Wi-Fi hálózathoz, az Wi-Fi próbálkozhat:

1. Ellenőrizze, hogy Wi-Fi be van-e kapcsolva. Az ellenőrzéshez használja a Start (Indítás) kézmozdulatot, majd válassza Gépház > Network & Internet > Wi-Fi lehetőséget. Ha Wi-Fi be van kapcsolva, próbálja meg kikapcsolni, majd újra bekapcsolni.
2. Lépjen közelebb az útválasztóhoz vagy a hozzáférési ponthoz.
3. Indítsa újra a Wi-Fi útválasztót, majd indítsa újra HoloLens. Próbáljon meg újra csatlakozni.
4. Ha ezek egyike sem működik, ellenőrizze, hogy az útválasztó a legújabb belső vezérlőprogramot használja-e. Ezt az információt a gyártó webhelyén találja.

Amikor vállalati vagy szervezeti fiókba jelentkezik be az eszközön, az a Mobile Eszközkezelés (MDM) szabályzatot is alkalmazhatja, ha a házirendet a rendszergazda konfigurálta.

[Vissza a listához](#list)

## <a name="network-troubleshooting"></a>Hálózati hibaelhárítás
Ha a hálózati problémák akadályt gördülnek a HoloLens 2. üzembe helyezése és használata előtt, konfigurálja a Fiddlert és/vagy a Wiresharkot a HTTP/HTTPS-forgalom rögzítésére és elemzésére. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>A Fiddler konfigurálása HTTP-forgalom rögzítésére
A Fiddler egy webes hibakeresési proxy, amely a HTTP(S) problémák elhárítására szolgál. A számítógép által lekért http-kéréseket rögzíti, és mindent rögzít, ami hozzá van társítva. A HTTPS-alkalmazások végfelhasználói hitelesítési problémáinak feltárása jobb hatékonyságot és hatékonyságot biztosít a HoloLens két használati esetben. 

#### <a name="prerequisites"></a>Előfeltételek
 
- HoloLens 2 eszköznek és a számítógépnek ugyanazon a hálózaton kell lennie
- Jegyezze fel a számítógép IP-címét

#### <a name="install-and-configure-fiddler"></a>A Fiddler telepítése és konfigurálása

1. A számítógépen telepítse és [indítsa el](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) a Fiddlert.  
1. A számítógépen – konfigurálja a Fiddlert úgy, hogy engedélyezze a távoli számítógépek csatlakozását.
    1. Ugrás a Fiddler Gépház -> Connections (Kapcsolatok) hez
    1. Figyelje meg a Fiddler figyelőportját (az alapértelmezett érték: 8866)
    1. Jelölje be a Távoli számítógépek csatlakozásának engedélyezése jelölőnégyzetet
    1. Kattintson a Save (Mentés) gombra.
3. A 2. HoloLens konfigurálja a Fiddlert<sup>1. proxykiszolgálóként:</sup>
    1. Nyissa meg a Start menü, és válassza a Gépház
    1. Válassza a Hálózati & internet lehetőséget, majd a bal oldali menü proxybeállítását.
    1. Görgessen le a Manual proxy setup (Manuális proxybeállítás) elemre, és a Use a proxy server (Proxykiszolgáló használata) kapcsolót a On (Be) beállításra kell beállítani
    1. Adja meg annak a számítógépnek az IP-címét, ahol a Fiddler telepítve van
    1. Adja meg a fent feljegyzett portszámot (az alapértelmezett érték: 8866)
    1. Kattintson a Save (Mentés) gombra.

<sup>1</sup> A 20279.1006+ buildek (Insiders és a közelgő kiadás) esetén az alábbi lépésekkel konfigurálhatja a proxyt:
1. Nyissa meg Start menü, és nyissa meg a Wi-Fi hálózat Tulajdonságok lapját 
1. Görgessen le a Proxyhoz
1. Módosítás manuális beállításra
1. Adja meg annak a számítógépnek az IP-címét, ahol a Fiddler telepítve van
1. Adja meg a fent feljegyzett portszámot. (az alapértelmezett érték: 8866)
1. Kattintson az Alkalmaz gombra
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>A 2. HoloLens HTTPS-forgalmának visszafejtése

1. A számítógépen – exportálja a Fiddler-tanúsítványt.
    1. A Fiddler Gépház -> HTTPS-hez, és bontsa ki a Speciális Gépház
    2. Kattintson a Fiddler-tanúsítvány exportálása elemre. Ez az asztalra lesz mentve
    3. Helyezze át a tanúsítványt a 2. HoloLens mappájába

2.  A 2. HoloLens – importálja a Fiddler-tanúsítványt.
    1. Ugrás a Gépház -> Update and Security -> Certificates (Frissítési és biztonsági tanúsítványok) >.
    2. Kattintson a Tanúsítvány telepítése elemre, keresse meg a Letöltések mappát, és válassza ki a Fiddler-tanúsítványt
    3. Az Áruház helyének módosítása helyi gépre
    4. Módosítsa a tanúsítványtárolót a főtanúsítványra
    5. Válassza a Telepítés lehetőséget
    6. Győződjön meg arról, hogy a tanúsítvány megjelenik a tanúsítványok listájában. Ha nem, ismételje meg a fenti lépéseket

#### <a name="inspect-https-sessions"></a>HTTP(S) munkamenetek vizsgálata

A számítógépen a Fiddler HoloLens 2. élő HTTP-munkameneteit. A Fiddler Vizsgálók panelje különböző nézetekben képes HTTP(S) kérést/választ mutatni – például a "Nyers" nézet egyszerű szövegként jeleníti meg a nyers kérést vagy választ. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>A Wireshark konfigurálása a hálózati forgalom rögzítésére
A Wireshark egy hálózati protokollelemző, amely a 2. eszközről a HoloLens UDP-forgalmának vizsgálatához használható. Ez megkönnyíti annak azonosítását, hogy milyen forgalom halad át a HoloLens 2., mekkora része, milyen gyakran, mekkora késés van bizonyos ugrások között stb.

#### <a name="prerequisites"></a>Előfeltételek:
- A számítógépnek internet-hozzáféréssel kell rendelkezik, és támogatnia kell az internetes megosztást Wi-Fi

#### <a name="install-and-configure-wireshark"></a>A Wireshark telepítése és konfigurálása
1. A [Wireshark](https://www.wireshark.org/#download) telepítése a számítógépen 
1. A számítógépen – engedélyezze a Mobil elérési pont számára az internetkapcsolat megosztását Wi-Fi-kapcsolaton keresztül.
1. Indítsa el a Wiresharkot a számítógépén, és rögzítse a mobil elérési pont felületéről származó forgalmat. 
1. A HoloLens 2- Wi-Fi a számítógép mobil elérési útjára. HoloLens 2 IP-forgalom fog mutatni a Wiresharkban.

#### <a name="analyze-wireshark-logs"></a>Wireshark-naplók elemzése
A Wireshark szűrői segíthetnek kiszűrni az érdeklődési körök csomagját. 

Tekintse meg az eredeti [blogot.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)

[Vissza a listához](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Nem lehet bejelentkezni egy korábban HoloLens eszközre

Ha az eszközt korábban már beállította valaki más számára egy ügyfél vagy egy korábbi alkalmazott számára, és nincs jelszava az [](/intune/remote-actions/devices-wipe) eszköz feloldásához, az Intune-nal távolról is törölheti az eszközt. Az eszköz ezután újra flash eszközt használ.  
> [!IMPORTANT]
> Az eszköz összes részletének törlésével győződjön meg arról, hogy a **Regisztrációs állapot** és felhasználói fiók megtartása jelölőnégyzet nincs bejelölve.

[Vissza a listához](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Nem lehet bejelentkezni, miután frissített Windows Holographic 21H1-re

### <a name="symptoms"></a>Hibajelenségek
- A MEGFELELŐ PIN-kód megadása után a PIN-kód használata sikertelen lesz a bejelentkezéshez.
- A webes bejelentkezési módszer használata sikertelen lesz, miután sikeresen bejelentkezik a weblapra.
- Az eszköz nem szerepel az "Azure AD-hez csatlakozott" Azure Portal [-> Azure Active Directory](https://portal.azure.com/) -> eszközök között.

### <a name="cause"></a>Ok
Előfordulhat, hogy az érintett eszköz törölve lett az Azure AD-bérlőből. Ez például a következő miatt fordulhat elő:

- Egy rendszergazda vagy felhasználó törölte az eszközt a Azure Portal PowerShell használatával.
- Az eszköz inaktivitás miatt el lett távolítva az Azure AD-bérlőből. A hatékony felügyelt környezet érdekében általában azt javasoljuk a rendszergazdáknak, hogy távolítsanak el elavult, inaktív eszközöket az [Azure AD-bérlőjükből.](/azure/active-directory/devices/manage-stale-devices)

Ha egy érintett eszköz a törlés után ismét megpróbál kapcsolatba lépni az Azure AD-bérlővel, nem fog tudni hitelesítést végezni az Azure AD-val. Ez a hatás gyakran láthatatlan az eszköz felhasználója számára, mivel a gyorsítótárazott, PIN-kódot használó bejelentkezés továbbra is lehetővé teszi a felhasználó bejelentkezését.

### <a name="mitigation"></a>Kockázatcsökkentés
A törölt adatokat jelenleg nem lehet HoloLens vissza az Azure AD-be. Az érintett eszközöket az eszköz újrafedésére vonatkozó utasítások szerint kell [megtisztítani.](hololens-recovery.md#clean-reflash-the-device)

[Vissza a listához](#list)

## <a name="autopilot-troubleshooting"></a>Az Autopilot hibaelhárítása

A következő cikkek hasznos forrást hatnak az AutoPilot-problémák további információinak elsajátítása és hibaelhárítása során, azonban vegye figyelembe, hogy ezek a cikkek az Windows 10 Desktopon alapulnak, és nem minden információ vonatkozhat a HoloLens:

- [Windows Autopilot – ismert problémák](/mem/autopilot/known-issues)
- [Eszközregisztrációs Windows hibaelhárítása a Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – Szabályzatütközések](/mem/autopilot/policy-conflicts)

[Vissza a listához](#list)

## <a name="managed-hololens-devices-faqs"></a>Felügyelt HoloLens eszközök – gyakori kérdések

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Használhatom a System Center Configuration Manager (SCCM) a HoloLens kezelésére?

Nem. Az MDM-rendszert kell használnia a HoloLens kezeléséhez.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Használhatom a Active Directory Domain Services (AD DS) a HoloLens fiókok kezeléséhez?

Nem. A Azure Active Directory (Azure AD) használatával kell kezelnie a HoloLens felhasználói fiókjait.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Képes HoloLens automatikus adatrögzítési rendszerek (ADCS) automatikus regisztrálására?

Nem.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Részt HoloLens integrált Windows hitelesítésben?

Nem.

### <a name="does-hololens-support-branding"></a>Támogatja HoloLens a védjegyezést?

Nem. Ezt a problémát azonban a következő megközelítések egyikével is meg lehet közelítheti:

- Hozzon létre egy egyéni alkalmazást, majd engedélyezze a [Kioszkmódot.](hololens-kiosk.md) Az egyéni alkalmazás védjegyezést is kaphat, és más alkalmazásokat is elindíthat (például a Remote Assist alkalmazást).  
- Módosítsa az Összes felhasználói profilképet az Azure AD-ban a vállalati emblémára. Ez azonban nem minden esetben kívánatos.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Milyen naplózási képességeket kínál HoloLens 2?

A naplózás olyan nyomkövetési adatokra korlátozódik, amelyek fejlesztési vagy hibaelhárítási forgatókönyvekben, vagy az eszközök által a Microsoft-kiszolgálóknak küldött telemetriákban rögzítettek.

## <a name="questions-about-securing-hololens-devices"></a>Kérdések a HoloLens biztonságról

Lásd [a HoloLens 2 biztonsági információt.](security-overview.md)
Az HoloLens gen eszközökhöz tekintse át ezt a [gyakori kérdéseket.](hololens1-faq-security.yml)

[Vissza a listához](#list)
