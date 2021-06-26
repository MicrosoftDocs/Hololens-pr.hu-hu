---
title: A HoloLens 2 implementációja és a felügyelt eszközök hibaelhárítása
description: HoloLens 2-eszközök hibaelhárítása vállalati környezetben
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
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961638"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Implementáció és felügyelt eszközök hibaelhárítása 

Ez a cikk több probléma megoldását, illetve a HoloLens 2 implementációval és felügyeletével kapcsolatos kérdések megoldását ismerteti.

>[!IMPORTANT]
> A hibaelhárítási eljárás elkezdése előtt győződjön meg arról, hogy az eszköz **20–40%-os** akkumulátor-kapacitással rendelkezik, ha lehetséges. A [tápkapcsoló alatt](hololens2-setup.md#lights-that-indicate-the-battery-level) található akkumulátorjelző világítással gyorsan ellenőrizheti az akkumulátor kapacitását anélkül, hogy bejelentkezik az eszközre.


<a id="list"></a>
- [EAP-hibaelhárítás](#eap-troubleshooting)
- [Wi-Fi-hibaelhárítás](#wi-fi-troubleshooting)
- [Hálózati hibaelhárítás](#network-troubleshooting)
- [Nem lehet bejelentkezni egy korábban telepített HoloLens-eszközbe](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Nem lehet bejelentkezni a Windows Holographic 21H1-re való frissítés után](#cant-login-after-updating-to-windows-holographic-21h1)
- [Az Autopilot hibaelhárítása](#autopilot-troubleshooting)
- [Felügyelt HoloLens-eszközök – gyakori kérdések](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>EAP-hibaelhárítás
1. Ellenőrizze, hogy Wi-Fi profil rendelkezik-e a megfelelő beállításokkal:
    - Az EAP-típus megfelelően van konfigurálva, gyakori EAP-típusok: EAP-TLS (13), EAP-TTLS (21) és PEAP (25).
    - Wi-Fi SSID neve helyes, és HEX-sztringre illeszkedik.
    - Az EAP-TLS-hez a TrustedRootCA tartalmazza a kiszolgáló megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványának SHA-1 kivonatát. Windows rendszerű számítógépen certutil.exe -dump cert_file_name parancs a tanúsítvány SHA-1 kivonatsringet fogja mutatni.
2. Gyűjtse össze a hálózati csomagok rögzítését a hozzáférési pont, a vezérlő vagy az AAA-kiszolgáló naplóiban, hogy megtudja, hol nem sikerül az EAP-munkamenet.
    - Ha a HoloLens által biztosított EAP-identitás nem várható, ellenőrizze, hogy az identitás megfelelően lettWi-Fi-profillal vagy ügyfél-tanúsítvánnyal lett-e kiépítve.
    - Ha a kiszolgáló elutasítja a HoloLens-ügyfél tanúsítványát, ellenőrizze, hogy a szükséges ügyfél-tanúsítvány ki lett-e építve az eszközön.
    - Ha a HoloLens elutasítja a kiszolgálótanúsítványt, ellenőrizze, hogy a kiszolgáló legfelső szintű hitelesítésszolgáltatói tanúsítványa ki lett-e építve a HoloLensen.
3. Ha a vállalati profil egy Wi-Fi csomaggal van kiépítve, fontolja meg a kiépítési csomag alkalmazását egy Windows 10 számítógépen. Ha a hiba a számítógépen Windows 10, kövesse a Windows-ügyfél 802.1X hitelesítési hibaelhárítási útmutatóját.
4. Küldjön visszajelzést a Visszajelzési központ.

[Vissza a listához](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi hibaelhárítás

Ha nem tudja csatlakoztatni a HoloLenst egy Wi-Fi hálózathoz:

1. Ellenőrizze, hogy Wi-Fi be van-e kapcsolva. Az ellenőrzéshez használja a Start (Indítás) kézmozdulatot, majd válassza a Settings > Network & Internet > Wi-Fi lehetőséget. Ha Wi-Fi be van kapcsolva, próbálja meg kikapcsolni, majd újra bekapcsolni.
2. Lépjen közelebb az útválasztóhoz vagy a hozzáférési ponthoz.
3. Indítsa újra a Wi-Fi útválasztót, majd indítsa újra a HoloLenst. Próbáljon meg újra csatlakozni.
4. Ha ezek közül egyik sem működik, ellenőrizze, hogy az útválasztó a legújabb belső vezérlőprogramot használja-e. Ezt az információt a gyártó webhelyén találja.

Amikor vállalati vagy szervezeti fiókba jelentkezik be az eszközön, az a Mobile Eszközkezelés (MDM) szabályzatot is alkalmazhatja, ha a házirendet a rendszergazda konfigurálta.

## <a name="network-troubleshooting"></a>Hálózati hibaelhárítás
Ha a hálózati problémák akadályt gördülnek a HoloLens 2 sikeres üzembe helyezése és használata előtt, megtudhatja, hogyan segíthet két jól ismert hálózati diagnosztikai eszköz, a Fiddler és a Wireshark a problémák vizsgálatában, diagnosztizálásában és azonosításában. További részletekért tekintse meg ezt a [blogot.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)

[Vissza a listához](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Nem lehet bejelentkezni egy korábban telepített HoloLens-eszközbe

Ha az eszközt korábban már beállította valaki más számára egy ügyfél vagy egy korábbi alkalmazott számára, és nincs jelszava az [](https://docs.microsoft.com/intune/remote-actions/devices-wipe) eszköz feloldásához, az Intune-nal távolról is törölheti az eszközt. Az eszköz ezután újra flash eszközt használ.  
> [!IMPORTANT]
> Az eszköz összes részletének törlésével győződjön meg arról, hogy a **Regisztrációs állapot** és felhasználói fiók megtartása jelölőnégyzet nincs bejelölve.
[Vissza a listához](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Nem lehet bejelentkezni a Windows Holographic 21H1-re való frissítés után

### <a name="symptoms"></a>Hibajelenségek
- A MEGFELELŐ PIN-kód megadása után a PIN-kód használata sikertelen lesz a bejelentkezéshez.
- A webes bejelentkezési módszer használata sikertelen lesz, miután sikeresen bejelentkezik a weblapra.
- Az eszköz nem szerepel az "Azure AD-hez csatlakozott" Azure Portal [-> Azure Active Directory](https://portal.azure.com/) -> eszközök listában.

### <a name="cause"></a>Ok
Előfordulhat, hogy az érintett eszköz törölve lett az Azure AD-bérlőből. Ez például a következő miatt fordulhat elő:

- Egy rendszergazda vagy felhasználó törölte az eszközt a Azure Portal PowerShell használatával.
- Az eszköz inaktivitás miatt el lett távolítva az Azure AD-bérlőből. A hatékony felügyelt környezet érdekében általában azt javasoljuk a rendszergazdáknak, hogy távolítsanak el elavult, inaktív eszközöket az [Azure AD-bérlőjükből.](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)

Ha egy érintett eszköz a törlés után ismét megpróbál kapcsolatba lépni az Azure AD-bérlővel, nem fog tudni hitelesítést végezni az Azure AD-val. Ez a hatás gyakran láthatatlan az eszköz felhasználója számára, mivel a gyorsítótárazott, PIN-kódot használó bejelentkezés továbbra is lehetővé teszi a felhasználó bejelentkezését.

### <a name="mitigation"></a>Kockázatcsökkentés
Törölt HoloLens-eszközt jelenleg nem lehet újra hozzáadni az Azure AD-hez. Az érintett eszközöket az eszköz újrafedésére vonatkozó utasítások szerint kell [megtisztítani.](hololens-recovery.md#clean-reflash-the-device)

## <a name="autopilot-troubleshooting"></a>Az Autopilot hibaelhárítása

Az alábbi cikkek hasznos forrást hatnak az AutoPilot-problémák további információinak elsajátítása és hibaelhárítása során, azonban vegye figyelembe, hogy ezek a cikkek az Windows 10 Desktopra épülnek, és nem minden információ vonatkozhat a HoloLensre:

- [Windows Autopilot – ismert problémák](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Windows-eszközök regisztrálási problémáinak elhárítása a Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – Szabályzatütközések](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a>Felügyelt HoloLens-eszközök – gyakori kérdések

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Használhatom a System Center Konfigurációkezelő (SCCM) a HoloLens-eszközök kezelésére?

Nem. A HoloLens-eszközök kezeléséhez MDM-rendszert kell használnia.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Használhatom a Active Directory Domain Services (AD DS) a HoloLens-felhasználói fiókok kezelésére?

Nem. A HoloLens-eszközök Azure Active Directory (Azure AD) használatával kell kezelnie a felhasználói fiókokat.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Képes a HoloLens automatikus adatrögzítési rendszerek (ADCS) automatikus regisztrációra?

Nem.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Részt vehet a HoloLens a integrált Windows-hitelesítés?

Nem.

### <a name="does-hololens-support-branding"></a>Támogatja a HoloLens a védjegyezést?

Nem. Ezt a problémát azonban a következő megközelítések egyikével is meg lehet közelítheti:

- Hozzon létre egy egyéni alkalmazást, majd engedélyezze a [Kioszkmódot.](hololens-kiosk.md) Az egyéni alkalmazás védjegyezést is kaphat, és más alkalmazásokat is elindíthat (például a Remote Assist alkalmazást).  
- Módosítsa az Összes felhasználói profilképet az Azure AD-ban a vállalati emblémára. Ez azonban nem minden esetben kívánatos.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Milyen naplózási képességeket kínál a HoloLens 2?

A naplózás olyan nyomkövetési adatokra korlátozódik, amelyek fejlesztési vagy hibaelhárítási forgatókönyvekben, illetve az eszközök által a Microsoft-kiszolgálóknak küldött telemetriákban rögzítettek.

## <a name="questions-about-securing-hololens-devices"></a>Kérdések a HoloLens-eszközök biztonságának biztosításáról

Lásd [a HoloLens 2 biztonsági információit.](security-overview.md)
HoloLens 1. generációs eszközök esetén tekintse át ezt [a gyakori kérdéseket.](hololens1-faq-security.md)

[Vissza a listához](#list)
