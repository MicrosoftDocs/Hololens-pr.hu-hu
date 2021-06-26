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
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="47c90-104">Implementáció és felügyelt eszközök hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="47c90-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="47c90-105">Ez a cikk több probléma megoldását, illetve a HoloLens 2 implementációval és felügyeletével kapcsolatos kérdések megoldását ismerteti.</span><span class="sxs-lookup"><span data-stu-id="47c90-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="47c90-106">A hibaelhárítási eljárás elkezdése előtt győződjön meg arról, hogy az eszköz **20–40%-os** akkumulátor-kapacitással rendelkezik, ha lehetséges.</span><span class="sxs-lookup"><span data-stu-id="47c90-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="47c90-107">A [tápkapcsoló alatt](hololens2-setup.md#lights-that-indicate-the-battery-level) található akkumulátorjelző világítással gyorsan ellenőrizheti az akkumulátor kapacitását anélkül, hogy bejelentkezik az eszközre.</span><span class="sxs-lookup"><span data-stu-id="47c90-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="47c90-108">EAP-hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="47c90-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="47c90-109">Wi-Fi-hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="47c90-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="47c90-110">Hálózati hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="47c90-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="47c90-111">Nem lehet bejelentkezni egy korábban telepített HoloLens-eszközbe</span><span class="sxs-lookup"><span data-stu-id="47c90-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="47c90-112">Nem lehet bejelentkezni a Windows Holographic 21H1-re való frissítés után</span><span class="sxs-lookup"><span data-stu-id="47c90-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="47c90-113">Az Autopilot hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="47c90-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="47c90-114">Felügyelt HoloLens-eszközök – gyakori kérdések</span><span class="sxs-lookup"><span data-stu-id="47c90-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="47c90-115">EAP-hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="47c90-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="47c90-116">Ellenőrizze, hogy Wi-Fi profil rendelkezik-e a megfelelő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="47c90-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="47c90-117">Az EAP-típus megfelelően van konfigurálva, gyakori EAP-típusok: EAP-TLS (13), EAP-TTLS (21) és PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="47c90-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="47c90-118">Wi-Fi SSID neve helyes, és HEX-sztringre illeszkedik.</span><span class="sxs-lookup"><span data-stu-id="47c90-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="47c90-119">Az EAP-TLS-hez a TrustedRootCA tartalmazza a kiszolgáló megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványának SHA-1 kivonatát.</span><span class="sxs-lookup"><span data-stu-id="47c90-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="47c90-120">Windows rendszerű számítógépen certutil.exe -dump cert_file_name parancs a tanúsítvány SHA-1 kivonatsringet fogja mutatni.</span><span class="sxs-lookup"><span data-stu-id="47c90-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="47c90-121">Gyűjtse össze a hálózati csomagok rögzítését a hozzáférési pont, a vezérlő vagy az AAA-kiszolgáló naplóiban, hogy megtudja, hol nem sikerül az EAP-munkamenet.</span><span class="sxs-lookup"><span data-stu-id="47c90-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="47c90-122">Ha a HoloLens által biztosított EAP-identitás nem várható, ellenőrizze, hogy az identitás megfelelően lettWi-Fi-profillal vagy ügyfél-tanúsítvánnyal lett-e kiépítve.</span><span class="sxs-lookup"><span data-stu-id="47c90-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="47c90-123">Ha a kiszolgáló elutasítja a HoloLens-ügyfél tanúsítványát, ellenőrizze, hogy a szükséges ügyfél-tanúsítvány ki lett-e építve az eszközön.</span><span class="sxs-lookup"><span data-stu-id="47c90-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="47c90-124">Ha a HoloLens elutasítja a kiszolgálótanúsítványt, ellenőrizze, hogy a kiszolgáló legfelső szintű hitelesítésszolgáltatói tanúsítványa ki lett-e építve a HoloLensen.</span><span class="sxs-lookup"><span data-stu-id="47c90-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="47c90-125">Ha a vállalati profil egy Wi-Fi csomaggal van kiépítve, fontolja meg a kiépítési csomag alkalmazását egy Windows 10 számítógépen.</span><span class="sxs-lookup"><span data-stu-id="47c90-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="47c90-126">Ha a hiba a számítógépen Windows 10, kövesse a Windows-ügyfél 802.1X hitelesítési hibaelhárítási útmutatóját.</span><span class="sxs-lookup"><span data-stu-id="47c90-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="47c90-127">Küldjön visszajelzést a Visszajelzési központ.</span><span class="sxs-lookup"><span data-stu-id="47c90-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="47c90-128">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="47c90-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="47c90-129">Wi-Fi hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="47c90-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="47c90-130">Ha nem tudja csatlakoztatni a HoloLenst egy Wi-Fi hálózathoz:</span><span class="sxs-lookup"><span data-stu-id="47c90-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="47c90-131">Ellenőrizze, hogy Wi-Fi be van-e kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="47c90-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="47c90-132">Az ellenőrzéshez használja a Start (Indítás) kézmozdulatot, majd válassza a Settings > Network & Internet > Wi-Fi lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="47c90-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="47c90-133">Ha Wi-Fi be van kapcsolva, próbálja meg kikapcsolni, majd újra bekapcsolni.</span><span class="sxs-lookup"><span data-stu-id="47c90-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="47c90-134">Lépjen közelebb az útválasztóhoz vagy a hozzáférési ponthoz.</span><span class="sxs-lookup"><span data-stu-id="47c90-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="47c90-135">Indítsa újra a Wi-Fi útválasztót, majd indítsa újra a HoloLenst.</span><span class="sxs-lookup"><span data-stu-id="47c90-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="47c90-136">Próbáljon meg újra csatlakozni.</span><span class="sxs-lookup"><span data-stu-id="47c90-136">Try connecting again.</span></span>
4. <span data-ttu-id="47c90-137">Ha ezek közül egyik sem működik, ellenőrizze, hogy az útválasztó a legújabb belső vezérlőprogramot használja-e.</span><span class="sxs-lookup"><span data-stu-id="47c90-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="47c90-138">Ezt az információt a gyártó webhelyén találja.</span><span class="sxs-lookup"><span data-stu-id="47c90-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="47c90-139">Amikor vállalati vagy szervezeti fiókba jelentkezik be az eszközön, az a Mobile Eszközkezelés (MDM) szabályzatot is alkalmazhatja, ha a házirendet a rendszergazda konfigurálta.</span><span class="sxs-lookup"><span data-stu-id="47c90-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="47c90-140">Hálózati hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="47c90-140">Network Troubleshooting</span></span>
<span data-ttu-id="47c90-141">Ha a hálózati problémák akadályt gördülnek a HoloLens 2 sikeres üzembe helyezése és használata előtt, megtudhatja, hogyan segíthet két jól ismert hálózati diagnosztikai eszköz, a Fiddler és a Wireshark a problémák vizsgálatában, diagnosztizálásában és azonosításában.</span><span class="sxs-lookup"><span data-stu-id="47c90-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="47c90-142">További részletekért tekintse meg ezt a [blogot.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)</span><span class="sxs-lookup"><span data-stu-id="47c90-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="47c90-143">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="47c90-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="47c90-144">Nem lehet bejelentkezni egy korábban telepített HoloLens-eszközbe</span><span class="sxs-lookup"><span data-stu-id="47c90-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="47c90-145">Ha az eszközt korábban már beállította valaki más számára egy ügyfél vagy egy korábbi alkalmazott számára, és nincs jelszava az [](https://docs.microsoft.com/intune/remote-actions/devices-wipe) eszköz feloldásához, az Intune-nal távolról is törölheti az eszközt.</span><span class="sxs-lookup"><span data-stu-id="47c90-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="47c90-146">Az eszköz ezután újra flash eszközt használ.</span><span class="sxs-lookup"><span data-stu-id="47c90-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="47c90-147">Az eszköz összes részletének törlésével győződjön meg arról, hogy a **Regisztrációs állapot** és felhasználói fiók megtartása jelölőnégyzet nincs bejelölve.</span><span class="sxs-lookup"><span data-stu-id="47c90-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="47c90-148">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="47c90-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="47c90-149">Nem lehet bejelentkezni a Windows Holographic 21H1-re való frissítés után</span><span class="sxs-lookup"><span data-stu-id="47c90-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="47c90-150">Hibajelenségek</span><span class="sxs-lookup"><span data-stu-id="47c90-150">Symptoms</span></span>
- <span data-ttu-id="47c90-151">A MEGFELELŐ PIN-kód megadása után a PIN-kód használata sikertelen lesz a bejelentkezéshez.</span><span class="sxs-lookup"><span data-stu-id="47c90-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="47c90-152">A webes bejelentkezési módszer használata sikertelen lesz, miután sikeresen bejelentkezik a weblapra.</span><span class="sxs-lookup"><span data-stu-id="47c90-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="47c90-153">Az eszköz nem szerepel az "Azure AD-hez csatlakozott" Azure Portal [-> Azure Active Directory](https://portal.azure.com/) -> eszközök listában.</span><span class="sxs-lookup"><span data-stu-id="47c90-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="47c90-154">Ok</span><span class="sxs-lookup"><span data-stu-id="47c90-154">Cause</span></span>
<span data-ttu-id="47c90-155">Előfordulhat, hogy az érintett eszköz törölve lett az Azure AD-bérlőből.</span><span class="sxs-lookup"><span data-stu-id="47c90-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="47c90-156">Ez például a következő miatt fordulhat elő:</span><span class="sxs-lookup"><span data-stu-id="47c90-156">For example, this may happen because:</span></span>

- <span data-ttu-id="47c90-157">Egy rendszergazda vagy felhasználó törölte az eszközt a Azure Portal PowerShell használatával.</span><span class="sxs-lookup"><span data-stu-id="47c90-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="47c90-158">Az eszköz inaktivitás miatt el lett távolítva az Azure AD-bérlőből.</span><span class="sxs-lookup"><span data-stu-id="47c90-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="47c90-159">A hatékony felügyelt környezet érdekében általában azt javasoljuk a rendszergazdáknak, hogy távolítsanak el elavult, inaktív eszközöket az [Azure AD-bérlőjükből.](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)</span><span class="sxs-lookup"><span data-stu-id="47c90-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="47c90-160">Ha egy érintett eszköz a törlés után ismét megpróbál kapcsolatba lépni az Azure AD-bérlővel, nem fog tudni hitelesítést végezni az Azure AD-val.</span><span class="sxs-lookup"><span data-stu-id="47c90-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="47c90-161">Ez a hatás gyakran láthatatlan az eszköz felhasználója számára, mivel a gyorsítótárazott, PIN-kódot használó bejelentkezés továbbra is lehetővé teszi a felhasználó bejelentkezését.</span><span class="sxs-lookup"><span data-stu-id="47c90-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="47c90-162">Kockázatcsökkentés</span><span class="sxs-lookup"><span data-stu-id="47c90-162">Mitigation</span></span>
<span data-ttu-id="47c90-163">Törölt HoloLens-eszközt jelenleg nem lehet újra hozzáadni az Azure AD-hez.</span><span class="sxs-lookup"><span data-stu-id="47c90-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="47c90-164">Az érintett eszközöket az eszköz újrafedésére vonatkozó utasítások szerint kell [megtisztítani.](hololens-recovery.md#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="47c90-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="47c90-165">Az Autopilot hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="47c90-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="47c90-166">Az alábbi cikkek hasznos forrást hatnak az AutoPilot-problémák további információinak elsajátítása és hibaelhárítása során, azonban vegye figyelembe, hogy ezek a cikkek az Windows 10 Desktopra épülnek, és nem minden információ vonatkozhat a HoloLensre:</span><span class="sxs-lookup"><span data-stu-id="47c90-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="47c90-167">Windows Autopilot – ismert problémák</span><span class="sxs-lookup"><span data-stu-id="47c90-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="47c90-168">Windows-eszközök regisztrálási problémáinak elhárítása a Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="47c90-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="47c90-169">Windows Autopilot – Szabályzatütközések</span><span class="sxs-lookup"><span data-stu-id="47c90-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="47c90-170">Felügyelt HoloLens-eszközök – gyakori kérdések</span><span class="sxs-lookup"><span data-stu-id="47c90-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="47c90-171">Használhatom a System Center Konfigurációkezelő (SCCM) a HoloLens-eszközök kezelésére?</span><span class="sxs-lookup"><span data-stu-id="47c90-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="47c90-172">Nem.</span><span class="sxs-lookup"><span data-stu-id="47c90-172">No.</span></span> <span data-ttu-id="47c90-173">A HoloLens-eszközök kezeléséhez MDM-rendszert kell használnia.</span><span class="sxs-lookup"><span data-stu-id="47c90-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="47c90-174">Használhatom a Active Directory Domain Services (AD DS) a HoloLens-felhasználói fiókok kezelésére?</span><span class="sxs-lookup"><span data-stu-id="47c90-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="47c90-175">Nem.</span><span class="sxs-lookup"><span data-stu-id="47c90-175">No.</span></span> <span data-ttu-id="47c90-176">A HoloLens-eszközök Azure Active Directory (Azure AD) használatával kell kezelnie a felhasználói fiókokat.</span><span class="sxs-lookup"><span data-stu-id="47c90-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="47c90-177">Képes a HoloLens automatikus adatrögzítési rendszerek (ADCS) automatikus regisztrációra?</span><span class="sxs-lookup"><span data-stu-id="47c90-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="47c90-178">Nem.</span><span class="sxs-lookup"><span data-stu-id="47c90-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="47c90-179">Részt vehet a HoloLens a integrált Windows-hitelesítés?</span><span class="sxs-lookup"><span data-stu-id="47c90-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="47c90-180">Nem.</span><span class="sxs-lookup"><span data-stu-id="47c90-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="47c90-181">Támogatja a HoloLens a védjegyezést?</span><span class="sxs-lookup"><span data-stu-id="47c90-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="47c90-182">Nem.</span><span class="sxs-lookup"><span data-stu-id="47c90-182">No.</span></span> <span data-ttu-id="47c90-183">Ezt a problémát azonban a következő megközelítések egyikével is meg lehet közelítheti:</span><span class="sxs-lookup"><span data-stu-id="47c90-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="47c90-184">Hozzon létre egy egyéni alkalmazást, majd engedélyezze a [Kioszkmódot.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="47c90-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="47c90-185">Az egyéni alkalmazás védjegyezést is kaphat, és más alkalmazásokat is elindíthat (például a Remote Assist alkalmazást).</span><span class="sxs-lookup"><span data-stu-id="47c90-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="47c90-186">Módosítsa az Összes felhasználói profilképet az Azure AD-ban a vállalati emblémára.</span><span class="sxs-lookup"><span data-stu-id="47c90-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="47c90-187">Ez azonban nem minden esetben kívánatos.</span><span class="sxs-lookup"><span data-stu-id="47c90-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="47c90-188">Milyen naplózási képességeket kínál a HoloLens 2?</span><span class="sxs-lookup"><span data-stu-id="47c90-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="47c90-189">A naplózás olyan nyomkövetési adatokra korlátozódik, amelyek fejlesztési vagy hibaelhárítási forgatókönyvekben, illetve az eszközök által a Microsoft-kiszolgálóknak küldött telemetriákban rögzítettek.</span><span class="sxs-lookup"><span data-stu-id="47c90-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="47c90-190">Kérdések a HoloLens-eszközök biztonságának biztosításáról</span><span class="sxs-lookup"><span data-stu-id="47c90-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="47c90-191">Lásd [a HoloLens 2 biztonsági információit.](security-overview.md)</span><span class="sxs-lookup"><span data-stu-id="47c90-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="47c90-192">HoloLens 1. generációs eszközök esetén tekintse át ezt [a gyakori kérdéseket.](hololens1-faq-security.md)</span><span class="sxs-lookup"><span data-stu-id="47c90-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="47c90-193">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="47c90-193">Back to list</span></span>](#list)
