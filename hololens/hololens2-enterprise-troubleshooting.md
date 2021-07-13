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
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="52ae0-104">Megvalósítási és felügyelt eszközök hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="52ae0-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="52ae0-105">Ez a cikk azt ismerteti, hogyan oldható meg több probléma, illetve hogyan válaszolható meg a 2. HoloLens megvalósítása és kezelése.</span><span class="sxs-lookup"><span data-stu-id="52ae0-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="52ae0-106">A hibaelhárítási eljárás elkezdése előtt győződjön meg arról, hogy az eszköz **20–40** százalék akkumulátor-kapacitással rendelkezik, ha lehetséges.</span><span class="sxs-lookup"><span data-stu-id="52ae0-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="52ae0-107">A [tápkapcsoló alatt](hololens2-setup.md#lights-that-indicate-the-battery-level) található akkumulátorjelző világítással gyorsan ellenőrizheti az akkumulátor kapacitását anélkül, hogy bejelentkezik az eszközre.</span><span class="sxs-lookup"><span data-stu-id="52ae0-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="52ae0-108">EAP-hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="52ae0-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="52ae0-109">Wi-Fi-hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="52ae0-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="52ae0-110">Hálózati hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="52ae0-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="52ae0-111">Nem lehet bejelentkezni egy korábban HoloLens eszközre</span><span class="sxs-lookup"><span data-stu-id="52ae0-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="52ae0-112">Nem lehet bejelentkezni, miután frissített Windows Holographic 21H1-re</span><span class="sxs-lookup"><span data-stu-id="52ae0-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="52ae0-113">Az Autopilot hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="52ae0-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="52ae0-114">Felügyelt HoloLens eszközök – gyakori kérdések</span><span class="sxs-lookup"><span data-stu-id="52ae0-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="52ae0-115">EAP-hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="52ae0-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="52ae0-116">Ellenőrizze, Wi-Fi profil rendelkezik-e a megfelelő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="52ae0-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="52ae0-117">Az EAP-típus megfelelően van konfigurálva, gyakori EAP-típusok: EAP-TLS (13), EAP-TTLS (21) és PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="52ae0-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="52ae0-118">Wi-Fi SSID neve helyes, és hexikáns sztringre illeszkedik.</span><span class="sxs-lookup"><span data-stu-id="52ae0-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="52ae0-119">Az EAP-TLS-hez a TrustedRootCA tartalmazza a kiszolgáló megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványának SHA-1 kivonatát.</span><span class="sxs-lookup"><span data-stu-id="52ae0-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="52ae0-120">A Windows számítógépen a "certutil.exe -dump cert_file_name" parancs egy tanúsítvány SHA-1 kivonatsringet fog mutatni.</span><span class="sxs-lookup"><span data-stu-id="52ae0-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="52ae0-121">Gyűjtse össze a hálózati csomagrögzítést a hozzáférési pont, a vezérlő vagy az AAA-kiszolgáló naplóiban, hogy megtudja, hol nem sikerül az EAP-munkamenet.</span><span class="sxs-lookup"><span data-stu-id="52ae0-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="52ae0-122">Ha az EAP-identitás nem HoloLens, ellenőrizze, hogy az identitás megfelelően lett-e Wi-Fi profilon vagy ügyfél-tanúsítványon keresztül.</span><span class="sxs-lookup"><span data-stu-id="52ae0-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="52ae0-123">Ha a kiszolgáló elutasítja HoloLens ügyfél-tanúsítványt, ellenőrizze, hogy a szükséges ügyfél-tanúsítvány ki lett-e építve az eszközön.</span><span class="sxs-lookup"><span data-stu-id="52ae0-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="52ae0-124">Ha HoloLens elutasítja a kiszolgálótanúsítványt, ellenőrizze, hogy a kiszolgáló legfelső szintű hitelesítésszolgáltatói tanúsítványa ki lett-e építve a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="52ae0-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="52ae0-125">Ha a vállalati profil egy kiépítési Wi-Fi keresztül van kiépítve, fontolja meg a kiépítési csomag alkalmazását egy Windows 10 számítógépen.</span><span class="sxs-lookup"><span data-stu-id="52ae0-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="52ae0-126">Ha a hiba a Windows 10 is sikertelen, kövesse a Windows 802.1X hitelesítési hibaelhárítási útmutatóját.</span><span class="sxs-lookup"><span data-stu-id="52ae0-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="52ae0-127">Küldjön visszajelzést a Visszajelzési központ.</span><span class="sxs-lookup"><span data-stu-id="52ae0-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="52ae0-128">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="52ae0-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="52ae0-129">Wi-Fi hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="52ae0-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="52ae0-130">Ha nem tud csatlakozni a HoloLens egy Wi-Fi hálózathoz, az Wi-Fi próbálkozhat:</span><span class="sxs-lookup"><span data-stu-id="52ae0-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="52ae0-131">Ellenőrizze, hogy Wi-Fi be van-e kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="52ae0-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="52ae0-132">Az ellenőrzéshez használja a Start (Indítás) kézmozdulatot, majd válassza Gépház > Network & Internet > Wi-Fi lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="52ae0-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="52ae0-133">Ha Wi-Fi be van kapcsolva, próbálja meg kikapcsolni, majd újra bekapcsolni.</span><span class="sxs-lookup"><span data-stu-id="52ae0-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="52ae0-134">Lépjen közelebb az útválasztóhoz vagy a hozzáférési ponthoz.</span><span class="sxs-lookup"><span data-stu-id="52ae0-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="52ae0-135">Indítsa újra a Wi-Fi útválasztót, majd indítsa újra HoloLens.</span><span class="sxs-lookup"><span data-stu-id="52ae0-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="52ae0-136">Próbáljon meg újra csatlakozni.</span><span class="sxs-lookup"><span data-stu-id="52ae0-136">Try connecting again.</span></span>
4. <span data-ttu-id="52ae0-137">Ha ezek egyike sem működik, ellenőrizze, hogy az útválasztó a legújabb belső vezérlőprogramot használja-e.</span><span class="sxs-lookup"><span data-stu-id="52ae0-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="52ae0-138">Ezt az információt a gyártó webhelyén találja.</span><span class="sxs-lookup"><span data-stu-id="52ae0-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="52ae0-139">Amikor vállalati vagy szervezeti fiókba jelentkezik be az eszközön, az a Mobile Eszközkezelés (MDM) szabályzatot is alkalmazhatja, ha a házirendet a rendszergazda konfigurálta.</span><span class="sxs-lookup"><span data-stu-id="52ae0-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

[<span data-ttu-id="52ae0-140">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="52ae0-140">Back to list</span></span>](#list)

## <a name="network-troubleshooting"></a><span data-ttu-id="52ae0-141">Hálózati hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="52ae0-141">Network Troubleshooting</span></span>
<span data-ttu-id="52ae0-142">Ha a hálózati problémák akadályt gördülnek a HoloLens 2. üzembe helyezése és használata előtt, konfigurálja a Fiddlert és/vagy a Wiresharkot a HTTP/HTTPS-forgalom rögzítésére és elemzésére.</span><span class="sxs-lookup"><span data-stu-id="52ae0-142">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, configure Fiddler and/or Wireshark to capture and analyze HTTP/HTTPS traffic.</span></span> 

### <a name="configure-fiddler-to-capture-http-traffic"></a><span data-ttu-id="52ae0-143">A Fiddler konfigurálása HTTP-forgalom rögzítésére</span><span class="sxs-lookup"><span data-stu-id="52ae0-143">Configure Fiddler to capture HTTP traffic</span></span>
<span data-ttu-id="52ae0-144">A Fiddler egy webes hibakeresési proxy, amely a HTTP(S) problémák elhárítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="52ae0-144">Fiddler is a web debugging proxy and is used to troubleshoot HTTP(S) issues.</span></span> <span data-ttu-id="52ae0-145">A számítógép által lekért http-kéréseket rögzíti, és mindent rögzít, ami hozzá van társítva.</span><span class="sxs-lookup"><span data-stu-id="52ae0-145">It captures every HTTP request the computer makes and records everything associated with it.</span></span> <span data-ttu-id="52ae0-146">A HTTPS-alkalmazások végfelhasználói hitelesítési problémáinak feltárása jobb hatékonyságot és hatékonyságot biztosít a HoloLens két használati esetben.</span><span class="sxs-lookup"><span data-stu-id="52ae0-146">Uncovering end-user authentication issues for your HTTPS apps drives better productivity and efficiency for your target HoloLens 2 use cases.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="52ae0-147">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="52ae0-147">Prerequisites</span></span>
 
- <span data-ttu-id="52ae0-148">HoloLens 2 eszköznek és a számítógépnek ugyanazon a hálózaton kell lennie</span><span class="sxs-lookup"><span data-stu-id="52ae0-148">HoloLens 2 devices and your PC must be on the same network</span></span>
- <span data-ttu-id="52ae0-149">Jegyezze fel a számítógép IP-címét</span><span class="sxs-lookup"><span data-stu-id="52ae0-149">Note the IP address of your PC</span></span>

#### <a name="install-and-configure-fiddler"></a><span data-ttu-id="52ae0-150">A Fiddler telepítése és konfigurálása</span><span class="sxs-lookup"><span data-stu-id="52ae0-150">Install and Configure Fiddler</span></span>

1. <span data-ttu-id="52ae0-151">A számítógépen telepítse és [indítsa el](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) a Fiddlert.</span><span class="sxs-lookup"><span data-stu-id="52ae0-151">On your PC - [install](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) and start Fiddler.</span></span>  
1. <span data-ttu-id="52ae0-152">A számítógépen – konfigurálja a Fiddlert úgy, hogy engedélyezze a távoli számítógépek csatlakozását.</span><span class="sxs-lookup"><span data-stu-id="52ae0-152">On your PC - configure Fiddler to allow remote computers to connect.</span></span>
    1. <span data-ttu-id="52ae0-153">Ugrás a Fiddler Gépház -> Connections (Kapcsolatok) hez</span><span class="sxs-lookup"><span data-stu-id="52ae0-153">Go to Fiddler Settings -> Connections</span></span>
    1. <span data-ttu-id="52ae0-154">Figyelje meg a Fiddler figyelőportját (az alapértelmezett érték: 8866)</span><span class="sxs-lookup"><span data-stu-id="52ae0-154">Note the listening port for Fiddler (default is 8866)</span></span>
    1. <span data-ttu-id="52ae0-155">Jelölje be a Távoli számítógépek csatlakozásának engedélyezése jelölőnégyzetet</span><span class="sxs-lookup"><span data-stu-id="52ae0-155">Check Allow remote computers to connect</span></span>
    1. <span data-ttu-id="52ae0-156">Kattintson a Save (Mentés) gombra.</span><span class="sxs-lookup"><span data-stu-id="52ae0-156">Click Save</span></span>
3. <span data-ttu-id="52ae0-157">A 2. HoloLens konfigurálja a Fiddlert<sup>1. proxykiszolgálóként:</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-157">On your HoloLens 2 – configure Fiddler as the proxy server<sup>1</sup>:</span></span>
    1. <span data-ttu-id="52ae0-158">Nyissa meg a Start menü, és válassza a Gépház</span><span class="sxs-lookup"><span data-stu-id="52ae0-158">Open the Start menu and select Settings</span></span>
    1. <span data-ttu-id="52ae0-159">Válassza a Hálózati & internet lehetőséget, majd a bal oldali menü proxybeállítását.</span><span class="sxs-lookup"><span data-stu-id="52ae0-159">Select Network & Internet and then Proxy on the left menu</span></span>
    1. <span data-ttu-id="52ae0-160">Görgessen le a Manual proxy setup (Manuális proxybeállítás) elemre, és a Use a proxy server (Proxykiszolgáló használata) kapcsolót a On (Be) beállításra kell beállítani</span><span class="sxs-lookup"><span data-stu-id="52ae0-160">Scroll down to Manual proxy setup and toggle Use a proxy server to On</span></span>
    1. <span data-ttu-id="52ae0-161">Adja meg annak a számítógépnek az IP-címét, ahol a Fiddler telepítve van</span><span class="sxs-lookup"><span data-stu-id="52ae0-161">Enter the IP address of the PC where Fiddler is installed</span></span>
    1. <span data-ttu-id="52ae0-162">Adja meg a fent feljegyzett portszámot (az alapértelmezett érték: 8866)</span><span class="sxs-lookup"><span data-stu-id="52ae0-162">Enter the port number noted above (default is 8866)</span></span>
    1. <span data-ttu-id="52ae0-163">Kattintson a Save (Mentés) gombra.</span><span class="sxs-lookup"><span data-stu-id="52ae0-163">Click Save</span></span>

<span data-ttu-id="52ae0-164"><sup>1</sup> A 20279.1006+ buildek (Insiders és a közelgő kiadás) esetén az alábbi lépésekkel konfigurálhatja a proxyt:</span><span class="sxs-lookup"><span data-stu-id="52ae0-164"><sup>1</sup> For builds 20279.1006+ (Insiders and the upcoming release), use the following steps to configure proxy:</span></span>
1. <span data-ttu-id="52ae0-165">Nyissa meg Start menü, és nyissa meg a Wi-Fi hálózat Tulajdonságok lapját</span><span class="sxs-lookup"><span data-stu-id="52ae0-165">Open the Start menu and go to your Wi-Fi Network’s Properties page</span></span> 
1. <span data-ttu-id="52ae0-166">Görgessen le a Proxyhoz</span><span class="sxs-lookup"><span data-stu-id="52ae0-166">Scroll down to Proxy</span></span>
1. <span data-ttu-id="52ae0-167">Módosítás manuális beállításra</span><span class="sxs-lookup"><span data-stu-id="52ae0-167">Change to Manual Setup</span></span>
1. <span data-ttu-id="52ae0-168">Adja meg annak a számítógépnek az IP-címét, ahol a Fiddler telepítve van</span><span class="sxs-lookup"><span data-stu-id="52ae0-168">Enter the IP address of the PC where Fiddler is installed</span></span>
1. <span data-ttu-id="52ae0-169">Adja meg a fent feljegyzett portszámot.</span><span class="sxs-lookup"><span data-stu-id="52ae0-169">Enter the port number noted above.</span></span> <span data-ttu-id="52ae0-170">(az alapértelmezett érték: 8866)</span><span class="sxs-lookup"><span data-stu-id="52ae0-170">(default is 8866)</span></span>
1. <span data-ttu-id="52ae0-171">Kattintson az Alkalmaz gombra</span><span class="sxs-lookup"><span data-stu-id="52ae0-171">Click Apply</span></span>
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a><span data-ttu-id="52ae0-172">A 2. HoloLens HTTPS-forgalmának visszafejtése</span><span class="sxs-lookup"><span data-stu-id="52ae0-172">Decrypt HTTPS traffic from HoloLens 2</span></span>

1. <span data-ttu-id="52ae0-173">A számítógépen – exportálja a Fiddler-tanúsítványt.</span><span class="sxs-lookup"><span data-stu-id="52ae0-173">On your PC – export the Fiddler certificate.</span></span>
    1. <span data-ttu-id="52ae0-174">A Fiddler Gépház -> HTTPS-hez, és bontsa ki a Speciális Gépház</span><span class="sxs-lookup"><span data-stu-id="52ae0-174">Go to Fiddler Settings -> HTTPS and expand Advanced Settings</span></span>
    2. <span data-ttu-id="52ae0-175">Kattintson a Fiddler-tanúsítvány exportálása elemre.</span><span class="sxs-lookup"><span data-stu-id="52ae0-175">Click Export Fiddler certificate.</span></span> <span data-ttu-id="52ae0-176">Ez az asztalra lesz mentve</span><span class="sxs-lookup"><span data-stu-id="52ae0-176">It will save to your desktop</span></span>
    3. <span data-ttu-id="52ae0-177">Helyezze át a tanúsítványt a 2. HoloLens mappájába</span><span class="sxs-lookup"><span data-stu-id="52ae0-177">Move the certificate over to the Downloads folder on your HoloLens 2</span></span>

2.  <span data-ttu-id="52ae0-178">A 2. HoloLens – importálja a Fiddler-tanúsítványt.</span><span class="sxs-lookup"><span data-stu-id="52ae0-178">On your HoloLens 2 - import the Fiddler certificate.</span></span>
    1. <span data-ttu-id="52ae0-179">Ugrás a Gépház -> Update and Security -> Certificates (Frissítési és biztonsági tanúsítványok) >.</span><span class="sxs-lookup"><span data-stu-id="52ae0-179">Go to Settings -> Update and Security -> Certificates</span></span>
    2. <span data-ttu-id="52ae0-180">Kattintson a Tanúsítvány telepítése elemre, keresse meg a Letöltések mappát, és válassza ki a Fiddler-tanúsítványt</span><span class="sxs-lookup"><span data-stu-id="52ae0-180">Click Install Certificate, browse to the Downloads folder and select the Fiddler certificate</span></span>
    3. <span data-ttu-id="52ae0-181">Az Áruház helyének módosítása helyi gépre</span><span class="sxs-lookup"><span data-stu-id="52ae0-181">Change Store Location to Local Machine</span></span>
    4. <span data-ttu-id="52ae0-182">Módosítsa a tanúsítványtárolót a főtanúsítványra</span><span class="sxs-lookup"><span data-stu-id="52ae0-182">Change Certificate Store to root</span></span>
    5. <span data-ttu-id="52ae0-183">Válassza a Telepítés lehetőséget</span><span class="sxs-lookup"><span data-stu-id="52ae0-183">Select Install</span></span>
    6. <span data-ttu-id="52ae0-184">Győződjön meg arról, hogy a tanúsítvány megjelenik a tanúsítványok listájában.</span><span class="sxs-lookup"><span data-stu-id="52ae0-184">Confirm the certificate is showing in the list of certificates.</span></span> <span data-ttu-id="52ae0-185">Ha nem, ismételje meg a fenti lépéseket</span><span class="sxs-lookup"><span data-stu-id="52ae0-185">If not, repeat the above steps</span></span>

#### <a name="inspect-https-sessions"></a><span data-ttu-id="52ae0-186">HTTP(S) munkamenetek vizsgálata</span><span class="sxs-lookup"><span data-stu-id="52ae0-186">Inspect HTTP(S) sessions</span></span>

<span data-ttu-id="52ae0-187">A számítógépen a Fiddler HoloLens 2. élő HTTP-munkameneteit.</span><span class="sxs-lookup"><span data-stu-id="52ae0-187">On your PC, Fiddler will show the HoloLens 2’s live HTTP(S) sessions.</span></span> <span data-ttu-id="52ae0-188">A Fiddler Vizsgálók panelje különböző nézetekben képes HTTP(S) kérést/választ mutatni – például a "Nyers" nézet egyszerű szövegként jeleníti meg a nyers kérést vagy választ.</span><span class="sxs-lookup"><span data-stu-id="52ae0-188">The Inspectors panel in Fiddler can show HTTP(S) request/response in different views - for example, the “Raw” view shows the raw request or response in plain text.</span></span> 

### <a name="configure-wireshark-to-capture-network-traffic"></a><span data-ttu-id="52ae0-189">A Wireshark konfigurálása a hálózati forgalom rögzítésére</span><span class="sxs-lookup"><span data-stu-id="52ae0-189">Configure Wireshark to capture network traffic</span></span>
<span data-ttu-id="52ae0-190">A Wireshark egy hálózati protokollelemző, amely a 2. eszközről a HoloLens UDP-forgalmának vizsgálatához használható.</span><span class="sxs-lookup"><span data-stu-id="52ae0-190">Wireshark is a network protocol analyzer and is used to inspect TCP/UDP traffic from and to your HoloLens 2 devices.</span></span> <span data-ttu-id="52ae0-191">Ez megkönnyíti annak azonosítását, hogy milyen forgalom halad át a HoloLens 2., mekkora része, milyen gyakran, mekkora késés van bizonyos ugrások között stb.</span><span class="sxs-lookup"><span data-stu-id="52ae0-191">This makes it easy to identify what traffic is crossing your network to your HoloLens 2, how much of it, how frequently, how much latency there is between certain hops, and so forth.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="52ae0-192">Előfeltételek:</span><span class="sxs-lookup"><span data-stu-id="52ae0-192">Prerequisites:</span></span>
- <span data-ttu-id="52ae0-193">A számítógépnek internet-hozzáféréssel kell rendelkezik, és támogatnia kell az internetes megosztást Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="52ae0-193">PC must have internet access and support Internet sharing over Wi-Fi</span></span>

#### <a name="install-and-configure-wireshark"></a><span data-ttu-id="52ae0-194">A Wireshark telepítése és konfigurálása</span><span class="sxs-lookup"><span data-stu-id="52ae0-194">Install and Configure Wireshark</span></span>
1. <span data-ttu-id="52ae0-195">A [Wireshark](https://www.wireshark.org/#download) telepítése a számítógépen</span><span class="sxs-lookup"><span data-stu-id="52ae0-195">On your PC - install [Wireshark](https://www.wireshark.org/#download)</span></span> 
1. <span data-ttu-id="52ae0-196">A számítógépen – engedélyezze a Mobil elérési pont számára az internetkapcsolat megosztását Wi-Fi-kapcsolaton keresztül.</span><span class="sxs-lookup"><span data-stu-id="52ae0-196">On your PC - enable Mobile hotspot to share your Internet connection from Wi-Fi.</span></span>
1. <span data-ttu-id="52ae0-197">Indítsa el a Wiresharkot a számítógépén, és rögzítse a mobil elérési pont felületéről származó forgalmat.</span><span class="sxs-lookup"><span data-stu-id="52ae0-197">On your PC - start Wireshark and capture traffic from the Mobile hotspot interface.</span></span> 
1. <span data-ttu-id="52ae0-198">A HoloLens 2- Wi-Fi a számítógép mobil elérési útjára.</span><span class="sxs-lookup"><span data-stu-id="52ae0-198">On your HoloLens 2 – change its Wi-Fi network to the PC’s Mobile hotspot.</span></span> <span data-ttu-id="52ae0-199">HoloLens 2 IP-forgalom fog mutatni a Wiresharkban.</span><span class="sxs-lookup"><span data-stu-id="52ae0-199">HoloLens 2 IP traffic will show up in Wireshark.</span></span>

#### <a name="analyze-wireshark-logs"></a><span data-ttu-id="52ae0-200">Wireshark-naplók elemzése</span><span class="sxs-lookup"><span data-stu-id="52ae0-200">Analyze Wireshark logs</span></span>
<span data-ttu-id="52ae0-201">A Wireshark szűrői segíthetnek kiszűrni az érdeklődési körök csomagját.</span><span class="sxs-lookup"><span data-stu-id="52ae0-201">Wireshark filters can help filtering out the packets of interests.</span></span> 

<span data-ttu-id="52ae0-202">Tekintse meg az eredeti [blogot.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)</span><span class="sxs-lookup"><span data-stu-id="52ae0-202">Check out the original [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).</span></span>

[<span data-ttu-id="52ae0-203">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="52ae0-203">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="52ae0-204">Nem lehet bejelentkezni egy korábban HoloLens eszközre</span><span class="sxs-lookup"><span data-stu-id="52ae0-204">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="52ae0-205">Ha az eszközt korábban már beállította valaki más számára egy ügyfél vagy egy korábbi alkalmazott számára, és nincs jelszava az [](/intune/remote-actions/devices-wipe) eszköz feloldásához, az Intune-nal távolról is törölheti az eszközt.</span><span class="sxs-lookup"><span data-stu-id="52ae0-205">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="52ae0-206">Az eszköz ezután újra flash eszközt használ.</span><span class="sxs-lookup"><span data-stu-id="52ae0-206">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="52ae0-207">Az eszköz összes részletének törlésével győződjön meg arról, hogy a **Regisztrációs állapot** és felhasználói fiók megtartása jelölőnégyzet nincs bejelölve.</span><span class="sxs-lookup"><span data-stu-id="52ae0-207">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>

[<span data-ttu-id="52ae0-208">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="52ae0-208">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="52ae0-209">Nem lehet bejelentkezni, miután frissített Windows Holographic 21H1-re</span><span class="sxs-lookup"><span data-stu-id="52ae0-209">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="52ae0-210">Hibajelenségek</span><span class="sxs-lookup"><span data-stu-id="52ae0-210">Symptoms</span></span>
- <span data-ttu-id="52ae0-211">A MEGFELELŐ PIN-kód megadása után a PIN-kód használata sikertelen lesz a bejelentkezéshez.</span><span class="sxs-lookup"><span data-stu-id="52ae0-211">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="52ae0-212">A webes bejelentkezési módszer használata sikertelen lesz, miután sikeresen bejelentkezik a weblapra.</span><span class="sxs-lookup"><span data-stu-id="52ae0-212">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="52ae0-213">Az eszköz nem szerepel az "Azure AD-hez csatlakozott" Azure Portal [-> Azure Active Directory](https://portal.azure.com/) -> eszközök között.</span><span class="sxs-lookup"><span data-stu-id="52ae0-213">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="52ae0-214">Ok</span><span class="sxs-lookup"><span data-stu-id="52ae0-214">Cause</span></span>
<span data-ttu-id="52ae0-215">Előfordulhat, hogy az érintett eszköz törölve lett az Azure AD-bérlőből.</span><span class="sxs-lookup"><span data-stu-id="52ae0-215">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="52ae0-216">Ez például a következő miatt fordulhat elő:</span><span class="sxs-lookup"><span data-stu-id="52ae0-216">For example, this may happen because:</span></span>

- <span data-ttu-id="52ae0-217">Egy rendszergazda vagy felhasználó törölte az eszközt a Azure Portal PowerShell használatával.</span><span class="sxs-lookup"><span data-stu-id="52ae0-217">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="52ae0-218">Az eszköz inaktivitás miatt el lett távolítva az Azure AD-bérlőből.</span><span class="sxs-lookup"><span data-stu-id="52ae0-218">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="52ae0-219">A hatékony felügyelt környezet érdekében általában azt javasoljuk a rendszergazdáknak, hogy távolítsanak el elavult, inaktív eszközöket az [Azure AD-bérlőjükből.](/azure/active-directory/devices/manage-stale-devices)</span><span class="sxs-lookup"><span data-stu-id="52ae0-219">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="52ae0-220">Ha egy érintett eszköz a törlés után ismét megpróbál kapcsolatba lépni az Azure AD-bérlővel, nem fog tudni hitelesítést végezni az Azure AD-val.</span><span class="sxs-lookup"><span data-stu-id="52ae0-220">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="52ae0-221">Ez a hatás gyakran láthatatlan az eszköz felhasználója számára, mivel a gyorsítótárazott, PIN-kódot használó bejelentkezés továbbra is lehetővé teszi a felhasználó bejelentkezését.</span><span class="sxs-lookup"><span data-stu-id="52ae0-221">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="52ae0-222">Kockázatcsökkentés</span><span class="sxs-lookup"><span data-stu-id="52ae0-222">Mitigation</span></span>
<span data-ttu-id="52ae0-223">A törölt adatokat jelenleg nem lehet HoloLens vissza az Azure AD-be.</span><span class="sxs-lookup"><span data-stu-id="52ae0-223">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="52ae0-224">Az érintett eszközöket az eszköz újrafedésére vonatkozó utasítások szerint kell [megtisztítani.](hololens-recovery.md#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="52ae0-224">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

[<span data-ttu-id="52ae0-225">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="52ae0-225">Back to list</span></span>](#list)

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="52ae0-226">Az Autopilot hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="52ae0-226">Autopilot Troubleshooting</span></span>

<span data-ttu-id="52ae0-227">A következő cikkek hasznos forrást hatnak az AutoPilot-problémák további információinak elsajátítása és hibaelhárítása során, azonban vegye figyelembe, hogy ezek a cikkek az Windows 10 Desktopon alapulnak, és nem minden információ vonatkozhat a HoloLens:</span><span class="sxs-lookup"><span data-stu-id="52ae0-227">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="52ae0-228">Windows Autopilot – ismert problémák</span><span class="sxs-lookup"><span data-stu-id="52ae0-228">Windows Autopilot - known issues</span></span>](/mem/autopilot/known-issues)
- [<span data-ttu-id="52ae0-229">Eszközregisztrációs Windows hibaelhárítása a Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="52ae0-229">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="52ae0-230">Windows Autopilot – Szabályzatütközések</span><span class="sxs-lookup"><span data-stu-id="52ae0-230">Windows Autopilot - Policy Conflicts</span></span>](/mem/autopilot/policy-conflicts)

[<span data-ttu-id="52ae0-231">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="52ae0-231">Back to list</span></span>](#list)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="52ae0-232">Felügyelt HoloLens eszközök – gyakori kérdések</span><span class="sxs-lookup"><span data-stu-id="52ae0-232">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="52ae0-233">Használhatom a System Center Configuration Manager (SCCM) a HoloLens kezelésére?</span><span class="sxs-lookup"><span data-stu-id="52ae0-233">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="52ae0-234">Nem.</span><span class="sxs-lookup"><span data-stu-id="52ae0-234">No.</span></span> <span data-ttu-id="52ae0-235">Az MDM-rendszert kell használnia a HoloLens kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="52ae0-235">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="52ae0-236">Használhatom a Active Directory Domain Services (AD DS) a HoloLens fiókok kezeléséhez?</span><span class="sxs-lookup"><span data-stu-id="52ae0-236">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="52ae0-237">Nem.</span><span class="sxs-lookup"><span data-stu-id="52ae0-237">No.</span></span> <span data-ttu-id="52ae0-238">A Azure Active Directory (Azure AD) használatával kell kezelnie a HoloLens felhasználói fiókjait.</span><span class="sxs-lookup"><span data-stu-id="52ae0-238">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="52ae0-239">Képes HoloLens automatikus adatrögzítési rendszerek (ADCS) automatikus regisztrálására?</span><span class="sxs-lookup"><span data-stu-id="52ae0-239">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="52ae0-240">Nem.</span><span class="sxs-lookup"><span data-stu-id="52ae0-240">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="52ae0-241">Részt HoloLens integrált Windows hitelesítésben?</span><span class="sxs-lookup"><span data-stu-id="52ae0-241">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="52ae0-242">Nem.</span><span class="sxs-lookup"><span data-stu-id="52ae0-242">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="52ae0-243">Támogatja HoloLens a védjegyezést?</span><span class="sxs-lookup"><span data-stu-id="52ae0-243">Does HoloLens support branding?</span></span>

<span data-ttu-id="52ae0-244">Nem.</span><span class="sxs-lookup"><span data-stu-id="52ae0-244">No.</span></span> <span data-ttu-id="52ae0-245">Ezt a problémát azonban a következő megközelítések egyikével is meg lehet közelítheti:</span><span class="sxs-lookup"><span data-stu-id="52ae0-245">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="52ae0-246">Hozzon létre egy egyéni alkalmazást, majd engedélyezze a [Kioszkmódot.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="52ae0-246">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="52ae0-247">Az egyéni alkalmazás védjegyezést is kaphat, és más alkalmazásokat is elindíthat (például a Remote Assist alkalmazást).</span><span class="sxs-lookup"><span data-stu-id="52ae0-247">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="52ae0-248">Módosítsa az Összes felhasználói profilképet az Azure AD-ban a vállalati emblémára.</span><span class="sxs-lookup"><span data-stu-id="52ae0-248">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="52ae0-249">Ez azonban nem minden esetben kívánatos.</span><span class="sxs-lookup"><span data-stu-id="52ae0-249">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="52ae0-250">Milyen naplózási képességeket kínál HoloLens 2?</span><span class="sxs-lookup"><span data-stu-id="52ae0-250">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="52ae0-251">A naplózás olyan nyomkövetési adatokra korlátozódik, amelyek fejlesztési vagy hibaelhárítási forgatókönyvekben, vagy az eszközök által a Microsoft-kiszolgálóknak küldött telemetriákban rögzítettek.</span><span class="sxs-lookup"><span data-stu-id="52ae0-251">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="52ae0-252">Kérdések a HoloLens biztonságról</span><span class="sxs-lookup"><span data-stu-id="52ae0-252">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="52ae0-253">Lásd [a HoloLens 2 biztonsági információt.](security-overview.md)</span><span class="sxs-lookup"><span data-stu-id="52ae0-253">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="52ae0-254">Az HoloLens gen eszközökhöz tekintse át ezt a [gyakori kérdéseket.](hololens1-faq-security.yml)</span><span class="sxs-lookup"><span data-stu-id="52ae0-254">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.yml).</span></span>

[<span data-ttu-id="52ae0-255">Vissza a listához</span><span class="sxs-lookup"><span data-stu-id="52ae0-255">Back to list</span></span>](#list)
