---
title: A HoloLens csatlakoztatása hálózathoz
description: Ismerje meg, hogyan lehet beállítani az internetet és csatlakozni az internethez a HoloLens segítségével, és hogyan lehet azonosítani az eszköz IP-címét.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wi-fi, vezeték nélküli, internet, ip, IP-cím
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 8564fb0483226a16722ada345de325577cda77d6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923601"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="311b0-104">A HoloLens csatlakoztatása hálózathoz</span><span class="sxs-lookup"><span data-stu-id="311b0-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="311b0-105">A HoloLensen a legtöbb dologhoz egy hálózathoz kell csatlakozva lennie.</span><span class="sxs-lookup"><span data-stu-id="311b0-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="311b0-106">A HoloLens egy 802.11ac-kompatibilis, 2x2 Wi-Fi-választógombot tartalmaz, és ahhoz hasonlít, mintha egy Windows 10 Desktop- vagy mobileszközt csatlakoztat egy Wi-Fi-hálózathoz.</span><span class="sxs-lookup"><span data-stu-id="311b0-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="311b0-107">Ez az útmutató a következőben segít:</span><span class="sxs-lookup"><span data-stu-id="311b0-107">This guide will help you:</span></span>

- <span data-ttu-id="311b0-108">Csatlakozás hálózathoz Wi-Fi használatával, vagy csak a HoloLens 2 esetén közvetlen Wi-Fi Ethernet usb-C-kapcsolaton keresztül</span><span class="sxs-lookup"><span data-stu-id="311b0-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="311b0-109">Az Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="311b0-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="311b0-110">További információ a [HoloLens offline használatával kapcsolatban.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="311b0-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="311b0-111">Csatlakozás első alkalommal</span><span class="sxs-lookup"><span data-stu-id="311b0-111">Connecting for the first time</span></span>

<span data-ttu-id="311b0-112">Amikor először használja a HoloLenst, a rendszer végigvezeti egy Wi-Fi hálózatához való csatlakozáson.</span><span class="sxs-lookup"><span data-stu-id="311b0-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="311b0-113">Ha a telepítés során problémába Wi-Fi, győződjön meg arról, hogy a hálózat egy nyílt, jelszóval védett hálózat vagy egy portálhálózat.</span><span class="sxs-lookup"><span data-stu-id="311b0-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="311b0-114">Győződjön meg arról is, hogy a hálózat nem követeli meg tanúsítvány használatát a csatlakozáshoz.</span><span class="sxs-lookup"><span data-stu-id="311b0-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="311b0-115">A beállítás után más típusú virtuális hálózatokhoz Wi-Fi csatlakozhat.</span><span class="sxs-lookup"><span data-stu-id="311b0-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="311b0-116">HoloLens 2-eszközökön a felhasználók [USB-C–Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) adapterrel is csatlakozhatnak közvetlenül az Wi-Fi-hoz, hogy segítsenek az eszköz beállításában.</span><span class="sxs-lookup"><span data-stu-id="311b0-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="311b0-117">Az eszköz beállítása után a felhasználó továbbra is használhatja az adaptert, vagy leválaszthatja az eszközt az adapterről, és a beállítás után csatlakozhat a [Wi-Fi-hez.](hololens-network.md#connecting-to-wi-fi-after-setup)</span><span class="sxs-lookup"><span data-stu-id="311b0-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="311b0-118">Csatlakozás Wi-Fi után</span><span class="sxs-lookup"><span data-stu-id="311b0-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="311b0-119">Formázhatja előre a **Start kézmozdulatot,** és válassza a **Beállítások lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="311b0-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="311b0-120">A Beállítások alkalmazás automatikusan el lesz helyezve Ön előtt.</span><span class="sxs-lookup"><span data-stu-id="311b0-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="311b0-121">Válassza **a Hálózati &**  >  **Wi-Fi lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="311b0-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="311b0-122">Győződjön meg arról, hogy a Wi-Fi be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="311b0-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="311b0-123">Ha nem látja a hálózatot, görgessen lefelé a listán.</span><span class="sxs-lookup"><span data-stu-id="311b0-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="311b0-124">Válasszon ki egy hálózatot, majd válassza a **Csatlakozás lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="311b0-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="311b0-125">Ha a rendszer hálózati jelszót kér, írja be, majd válassza a **Tovább lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="311b0-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens Wi-Fi beállításai](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="311b0-127">Annak megerősítéséhez, hogy csatlakozott egy Wi-Fi hálózathoz, ellenőrizze a Wi-Fi állapotát a **Start menüben:**</span><span class="sxs-lookup"><span data-stu-id="311b0-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="311b0-128">Nyissa meg **a Start menüt.**</span><span class="sxs-lookup"><span data-stu-id="311b0-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="311b0-129">A Start menü bal felső **részen** keresse meg a Wi-Fi állapotát.</span><span class="sxs-lookup"><span data-stu-id="311b0-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="311b0-130">Megjelenik a Wi-Fi hálózat SSID-ének állapota.</span><span class="sxs-lookup"><span data-stu-id="311b0-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="311b0-131">Ha Wi-Fi nem érhető el, mobilhálózati és [5G-hálózatokhoz is csatlakozhat.](hololens-cellular.md)</span><span class="sxs-lookup"><span data-stu-id="311b0-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="311b0-132">A felhasználók a Tervezés szerint nem tudják finomhangolni a HoloLens 2 Wi-Fi roaming viselkedését – az Wi-Fi-lista frissítésének egyetlen módja a Wi-Fi ki- és **bekapcsolása.**</span><span class="sxs-lookup"><span data-stu-id="311b0-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="311b0-133">Ez számos problémát meggátol, például azt, hogy egy eszköz "elakadhat" egy AP-hez, ha az a tartományon kívül esik.</span><span class="sxs-lookup"><span data-stu-id="311b0-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="311b0-134">A HoloLens csatlakoztatása az Enterprise Wi-Fi Network szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="311b0-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="311b0-135">A Wi-Fi profilok az EAP protokollt (Extensible Authentication Protocol) használják a Wi-Fi hitelesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="311b0-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="311b0-136">A HoloLens Enterprise Wi-Fi-profil a Windows Configuration Designer által létrehozott MDM vagy kiépítési csomag [segítségével konfigurálható.](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)</span><span class="sxs-lookup"><span data-stu-id="311b0-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="311b0-137">A Microsoft Intune eszközről a konfigurációs [utasításokért tekintse](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) meg az Intune-t.</span><span class="sxs-lookup"><span data-stu-id="311b0-137">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="311b0-138">Ha Wi-Fi kiépítési csomagot a WCD-ben, előre konfigurált Wi-Fi profilra és .xml fájlra van szükség.</span><span class="sxs-lookup"><span data-stu-id="311b0-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="311b0-139">Az EAP-TLSWi-Fi hitelesítéssel WPA2-Enterprise mintaprofil:</span><span class="sxs-lookup"><span data-stu-id="311b0-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="311b0-140">Az EAP-típustól függően előfordulhat, hogy a kiszolgáló legfelső szintű hitelesítésszolgáltatói tanúsítványát és az ügyféltanúsítványt ki kell kiépítenünk az eszközön.</span><span class="sxs-lookup"><span data-stu-id="311b0-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="311b0-141">További források:</span><span class="sxs-lookup"><span data-stu-id="311b0-141">Additional resources:</span></span>

- <span data-ttu-id="311b0-142">WLANv1Profile séma: [[MS-GPWL]: Vezeték nélküli LAN-profil v1 séma | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="311b0-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="311b0-143">EAP-TLS-séma: [[MS-GPWL]: Microsoft EAP TLS-séma | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="311b0-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="311b0-144">Ha problémái [vannak](hololens2-enterprise-troubleshooting.md#) a Wi-Fi-hez való csatlakozással, tekintse meg a hibaelhárítási oldalt.</span><span class="sxs-lookup"><span data-stu-id="311b0-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="311b0-145">Hálózati proxy konfigurálása</span><span class="sxs-lookup"><span data-stu-id="311b0-145">Configure Network Proxy</span></span>

<span data-ttu-id="311b0-146">Ez a szakasz a HoloLens operációs rendszer hálózati proxyját és Univerzális Windows-platform (UWP) Windows HTTP-vermeket használó alkalmazásokkal foglalkozik.</span><span class="sxs-lookup"><span data-stu-id="311b0-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="311b0-147">A nem Windows HTTP-vermeket használó alkalmazások saját proxykonfigurációval és -kezeléssel is használhatók.</span><span class="sxs-lookup"><span data-stu-id="311b0-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="311b0-148">Proxykonfigurációk</span><span class="sxs-lookup"><span data-stu-id="311b0-148">Proxy Configurations</span></span> 

- <span data-ttu-id="311b0-149">Proxy auto-config (PAC) szkript: a [PAC-fájl](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (nem a Microsofttól származó webhely megnyitása) tartalmaz egy FindProxyForURL(url, host) JavaScript-függvényt.</span><span class="sxs-lookup"><span data-stu-id="311b0-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="311b0-150">Statikus proxy: Kiszolgáló:Port formában.</span><span class="sxs-lookup"><span data-stu-id="311b0-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="311b0-151">Webproxy automatikus felderítési protokollja (WPAD): adja meg a proxykonfigurációs fájl URL-címét DHCP-en vagy DNS-en keresztül.</span><span class="sxs-lookup"><span data-stu-id="311b0-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="311b0-152">Proxy-kiépítési módszerek</span><span class="sxs-lookup"><span data-stu-id="311b0-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="311b0-153">A proxyk üzembe építésének három módja van:</span><span class="sxs-lookup"><span data-stu-id="311b0-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="311b0-154">**Beállítások felhasználói felülete:**</span><span class="sxs-lookup"><span data-stu-id="311b0-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="311b0-155">Felhasználónkénti proxy (20H2 vagy korábbi):</span><span class="sxs-lookup"><span data-stu-id="311b0-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="311b0-156">Nyissa meg a Start menü, és válassza a Beállítások lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="311b0-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="311b0-157">Válassza a Network & internet, majd a proxy lehetőséget a bal oldali menüben.</span><span class="sxs-lookup"><span data-stu-id="311b0-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="311b0-158">Görgessen le a Manual proxy setup (Manuális proxybeállítás) elemre, és a Use a proxy server (Proxykiszolgáló használata) kapcsolót a On (Be) beállításra.</span><span class="sxs-lookup"><span data-stu-id="311b0-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="311b0-159">Adja meg a proxykiszolgáló IP-címét.</span><span class="sxs-lookup"><span data-stu-id="311b0-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="311b0-160">Adja meg a portszámot.</span><span class="sxs-lookup"><span data-stu-id="311b0-160">Enter the port number.</span></span>
        6. <span data-ttu-id="311b0-161">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="311b0-161">Click Save.</span></span>
      1. <span data-ttu-id="311b0-162">Wi-Fi-proxy (21H1 vagy újabb):</span><span class="sxs-lookup"><span data-stu-id="311b0-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="311b0-163">Nyissa meg Start menü, és nyissa meg Wi-Fi hálózat Tulajdonságok lapját.</span><span class="sxs-lookup"><span data-stu-id="311b0-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="311b0-164">Görgessen le a Proxyhoz</span><span class="sxs-lookup"><span data-stu-id="311b0-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="311b0-165">Módosítás manuális beállításra</span><span class="sxs-lookup"><span data-stu-id="311b0-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="311b0-166">Adja meg a proxykiszolgáló IP-címét.</span><span class="sxs-lookup"><span data-stu-id="311b0-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="311b0-167">Adja meg a portszámot.</span><span class="sxs-lookup"><span data-stu-id="311b0-167">Enter the port number.</span></span>
          1. <span data-ttu-id="311b0-168">Kattintson az Alkalmaz gombra.</span><span class="sxs-lookup"><span data-stu-id="311b0-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="311b0-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="311b0-169">**MDM**</span></span> 
     1. <span data-ttu-id="311b0-170">Intune – Ezekkel a [lépésekkel konfigurálhatja](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) a proxyt az Intune-ban.</span><span class="sxs-lookup"><span data-stu-id="311b0-170">Intune - Use these [steps](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="311b0-171">A szakasz aljára kell görgetnie.</span><span class="sxs-lookup"><span data-stu-id="311b0-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="311b0-172">Egyéb külső MDM-megoldások – [Wi-Fi CSP használata.](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)</span><span class="sxs-lookup"><span data-stu-id="311b0-172">Other 3rd party MDM solutions - Use a [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="311b0-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="311b0-173">**PPKG**</span></span> 
    1. <span data-ttu-id="311b0-174">A Windows Configuration Designer megnyitása</span><span class="sxs-lookup"><span data-stu-id="311b0-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="311b0-175">Kattintson a Speciális kiépítés elemre, adja meg az új projekt nevét, majd kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="311b0-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="311b0-176">Válassza a Windows Holographic (HoloLens 2) lehetőséget, majd kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="311b0-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="311b0-177">Importálja a PPKG-t (nem kötelező), majd kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="311b0-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="311b0-178">Bontsa ki a Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy (WLAN-kapcsolati profilok -> WLAN-proxy) gombra.</span><span class="sxs-lookup"><span data-stu-id="311b0-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="311b0-179">Adja meg a hálózati Wi-Fi SSID-ját, és kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="311b0-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="311b0-180">Válassza ki a Wi-Fi a bal oldali ablakban, és adja meg a kívánt testreszabásokat.</span><span class="sxs-lookup"><span data-stu-id="311b0-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="311b0-181">Az engedélyezett testreszabások félkövérrel jelennek meg a bal oldali menüben.</span><span class="sxs-lookup"><span data-stu-id="311b0-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="311b0-182">Kattintson a Mentés és kilépés gombra.</span><span class="sxs-lookup"><span data-stu-id="311b0-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="311b0-183">[Alkalmazza a](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) kiépítési csomagot a HoloLensre.</span><span class="sxs-lookup"><span data-stu-id="311b0-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="311b0-184">[A csP-k](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) számos felügyeleti feladat és házirend mögött állnak a Windows 10, mind a Microsoft Intune, mind a nem Microsoft MDM-szolgáltatóknál.</span><span class="sxs-lookup"><span data-stu-id="311b0-184">[CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="311b0-185">A Windows [Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) használatával is létrehozhat egy kiépítési csomagot, és alkalmazhatja azt [a](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) HoloLens 2-re.</span><span class="sxs-lookup"><span data-stu-id="311b0-185">You can also use [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="311b0-186">A HoloLens 2-re leginkább a következő CSP-k lesznek alkalmazva:</span><span class="sxs-lookup"><span data-stu-id="311b0-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="311b0-187">[Wi-Fi CSP:](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)profilonkénti Wi-Fi proxy</span><span class="sxs-lookup"><span data-stu-id="311b0-187">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="311b0-188">A HoloLens-eszközökön támogatott egyéb CSP-k</span><span class="sxs-lookup"><span data-stu-id="311b0-188">Other CSPs supported in HoloLens devices</span></span>](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="311b0-189">VPN</span><span class="sxs-lookup"><span data-stu-id="311b0-189">VPN</span></span>
<span data-ttu-id="311b0-190">A VPN-kapcsolat biztonságosabb kapcsolatot és hozzáférést biztosít a vállalat hálózatához és az internethez.</span><span class="sxs-lookup"><span data-stu-id="311b0-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="311b0-191">A HoloLens 2 támogatja a beépített VPN-ügyfelet és Univerzális Windows-platform (UWP) VPN beépülő modult.</span><span class="sxs-lookup"><span data-stu-id="311b0-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="311b0-192">Támogatott beépített VPN-protokollok:</span><span class="sxs-lookup"><span data-stu-id="311b0-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="311b0-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="311b0-193">IKEv2</span></span>
- <span data-ttu-id="311b0-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="311b0-194">L2TP</span></span>
- <span data-ttu-id="311b0-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="311b0-195">PPTP</span></span>

<span data-ttu-id="311b0-196">Ha tanúsítványt használ a beépített VPN-ügyfél hitelesítéséhez, a szükséges ügyfél-tanúsítványt hozzá kell adni a felhasználói tanúsítványtárolóhoz.</span><span class="sxs-lookup"><span data-stu-id="311b0-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="311b0-197">Annak ellenőrzéséhez, hogy egy harmadik féltől származó VPN beépülő modul támogatja-e a HoloLens 2-t, az Áruházban keresse meg a VPN-alkalmazást, és ellenőrizze, hogy a HoloLens támogatott eszközként szerepel-e, és a Rendszerkövetelmények lapon az alkalmazás támogatja-e az ARM- vagy ARM64-architektúrát.</span><span class="sxs-lookup"><span data-stu-id="311b0-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="311b0-198">A HoloLens csak a Univerzális Windows-platform VPN-hez támogatja az alkalmazásokat.</span><span class="sxs-lookup"><span data-stu-id="311b0-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="311b0-199">A VPN-t MDM-en keresztül lehet kezelni [a Beállítások/AllowVPN segítségével,](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)és [a vpnv2-csp szabályzattal lehet beállítani.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)</span><span class="sxs-lookup"><span data-stu-id="311b0-199">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="311b0-200">A VPN [konfigurálásról az alábbi](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) [útmutatókban olvashat bővebben.](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)</span><span class="sxs-lookup"><span data-stu-id="311b0-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="311b0-201">VPN felhasználói felületen keresztül</span><span class="sxs-lookup"><span data-stu-id="311b0-201">VPN via UI</span></span>

<span data-ttu-id="311b0-202">A VPN alapértelmezés szerint nincs engedélyezve,  de manuálisan is engedélyezhető a Beállítások alkalmazás megnyitásával és a **Network & Internet -> VPN elemre navigálva.**</span><span class="sxs-lookup"><span data-stu-id="311b0-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="311b0-203">Válasszon ki egy VPN-szolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="311b0-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="311b0-204">Hozzon létre egy kapcsolatnevet.</span><span class="sxs-lookup"><span data-stu-id="311b0-204">Create a connection name.</span></span> 
1. <span data-ttu-id="311b0-205">Adja meg a kiszolgáló nevét vagy címét.</span><span class="sxs-lookup"><span data-stu-id="311b0-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="311b0-206">Válassza ki a VPN típusát.</span><span class="sxs-lookup"><span data-stu-id="311b0-206">Select the VPN type.</span></span>
1. <span data-ttu-id="311b0-207">Válassza ki a bejelentkezési adatok típusát.</span><span class="sxs-lookup"><span data-stu-id="311b0-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="311b0-208">Ha szükséges, adjon meg egy felhasználónevet és egy jelszót.</span><span class="sxs-lookup"><span data-stu-id="311b0-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="311b0-209">Alkalmazza a VPN-beállításokat.</span><span class="sxs-lookup"><span data-stu-id="311b0-209">Apply the VPN settings.</span></span> 

![HoloLens VPN-beállítások](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="311b0-211">VPN beállítása kiépítési csomagon keresztül</span><span class="sxs-lookup"><span data-stu-id="311b0-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="311b0-212">A Windows Holographic 20H2-es verziójában kijavítottunk egy proxykonfigurációs hibát a VPN-kapcsolathoz.</span><span class="sxs-lookup"><span data-stu-id="311b0-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="311b0-213">Ha ezt a folyamatot szeretné használni, fontolja meg az eszközök frissítését erre a buildre.</span><span class="sxs-lookup"><span data-stu-id="311b0-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="311b0-214">Indítsa el a Windows Configuration Designert.</span><span class="sxs-lookup"><span data-stu-id="311b0-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="311b0-215">Kattintson **a Provision HoloLens devices (HoloLens-eszközök kiépítése)** elemre, majd válassza ki a céleszközt, és kattintson **a Next (Tovább) gombra.**</span><span class="sxs-lookup"><span data-stu-id="311b0-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="311b0-216">Adja meg a csomag nevét és elérési útját.</span><span class="sxs-lookup"><span data-stu-id="311b0-216">Enter package name and path.</span></span>
1. <span data-ttu-id="311b0-217">Kattintson **a Váltás speciális szerkesztőre lehetőségre.**</span><span class="sxs-lookup"><span data-stu-id="311b0-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="311b0-218">Nyissa **meg a Runtime settings**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings (Futtatás** futásidejű beállításai) Beállítást.</span><span class="sxs-lookup"><span data-stu-id="311b0-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="311b0-219">A VPNProfileName konfigurálása</span><span class="sxs-lookup"><span data-stu-id="311b0-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="311b0-220">Válassza a ProfileType: **Native (Natív) vagy** **a Third Party (Harmadik fél) lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="311b0-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="311b0-221">A Natív profil beállításnál válassza a **NativeProtocolType** lehetőséget, majd konfigurálja a kiszolgálót, az útválasztási házirendet, a hitelesítési típust és az egyéb beállításokat.</span><span class="sxs-lookup"><span data-stu-id="311b0-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="311b0-222">A "Külső gyártótól származó" profilhoz konfigurálja a kiszolgáló URL-címét, a VPN beépülő modul alkalmazáscsomagjának családnevét (csak 3 előre definiált) és egyéni konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="311b0-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="311b0-223">Exportálja a csomagot.</span><span class="sxs-lookup"><span data-stu-id="311b0-223">Export your package.</span></span>
1. <span data-ttu-id="311b0-224">Csatlakoztassa a HoloLenst, és másolja a .ppkg fájlt az eszközre.</span><span class="sxs-lookup"><span data-stu-id="311b0-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="311b0-225">A HoloLensen alkalmazza a VPN .ppkg-t a Start menü megnyitásával és a Beállítások fiókelérés munkahelyi vagy iskolai fiókjához Való hozzáférés Munkahelyi vagy iskolai fiók hozzáadása vagy eltávolítása -> VÁLASSZA ki a  ->    ->    ->   VPN-csomagot lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="311b0-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="311b0-226">VPN beállítása az Intune-on keresztül</span><span class="sxs-lookup"><span data-stu-id="311b0-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="311b0-227">Az első lépésekhez kövesse az Intune-dokumentumokat.</span><span class="sxs-lookup"><span data-stu-id="311b0-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="311b0-228">Ha követi ezeket a lépéseket, tartsa szem előtt a HoloLens-eszközök által támogatott beépített VPN-protokollokat.</span><span class="sxs-lookup"><span data-stu-id="311b0-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="311b0-229">[VPN-profilok létrehozása VPN-kiszolgálókhoz való csatlakozáshoz az Intune-ban.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="311b0-229">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="311b0-230">[Windows 10 és Windows Holographic eszközbeállításokkal VPN-kapcsolatokat adhat hozzá az Intune-nal.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)</span><span class="sxs-lookup"><span data-stu-id="311b0-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="311b0-231">Ha végzett, ne felejtse el [hozzárendelni a profilt.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="311b0-231">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="311b0-232">VPN külső MDM-megoldásokon keresztül</span><span class="sxs-lookup"><span data-stu-id="311b0-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="311b0-233">Példa külső VPN-kapcsolatra:</span><span class="sxs-lookup"><span data-stu-id="311b0-233">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="311b0-234">Példa natív IKEv2 VPN-re:</span><span class="sxs-lookup"><span data-stu-id="311b0-234">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="311b0-235">A Wi-Fi letiltása a HoloLensben (1. generációs)</span><span class="sxs-lookup"><span data-stu-id="311b0-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="311b0-236">A Settings alkalmazás használata a HoloLensben</span><span class="sxs-lookup"><span data-stu-id="311b0-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="311b0-237">Nyissa meg **a Start menüt.**</span><span class="sxs-lookup"><span data-stu-id="311b0-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="311b0-238">Válassza a **Beállítások** alkalmazást a **Start menüből** vagy a **Start** menü jobb oldalon található Minden alkalmazás **listából.**</span><span class="sxs-lookup"><span data-stu-id="311b0-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="311b0-239">A **Beállítások** alkalmazás automatikusan el lesz helyezve Ön előtt.</span><span class="sxs-lookup"><span data-stu-id="311b0-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="311b0-240">Válassza **a Hálózati & lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="311b0-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="311b0-241">A csúszka Wi-Fi a csúszkakapcsolót, hogy a Ki **állásba helyezze.**</span><span class="sxs-lookup"><span data-stu-id="311b0-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="311b0-242">Ezzel kikapcsolja az eszköz RF összetevőitWi-Fi és letiltja az összes Wi-Fi Funkciót a HoloLensen.</span><span class="sxs-lookup"><span data-stu-id="311b0-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="311b0-243">Ha a Wi-Fi le van tiltva, a HoloLens nem fogja tudni automatikusan betölteni a [szóközöket.](hololens-spaces.md)</span><span class="sxs-lookup"><span data-stu-id="311b0-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="311b0-244">Húzza a csúszkakapcsolót **a** Be állásba, hogy be tudja kapcsolni Wi-Fi választógombot, és visszaállítsa Wi-Fi funkcióját a Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="311b0-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="311b0-245">A kiválasztott Wi-Fi választógomb állapota (**Be** vagy **Ki**) megmarad az újraindítások között.</span><span class="sxs-lookup"><span data-stu-id="311b0-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="311b0-246">HoloLens IP-címének azonosítása a Wi-Fi hálózaton</span><span class="sxs-lookup"><span data-stu-id="311b0-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="311b0-247">A Beállítások alkalmazás használatával</span><span class="sxs-lookup"><span data-stu-id="311b0-247">By using the Settings app</span></span>

1. <span data-ttu-id="311b0-248">Nyissa meg **a Start menüt.**</span><span class="sxs-lookup"><span data-stu-id="311b0-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="311b0-249">Válassza a **Beállítások** alkalmazást a **Start menüből** vagy a **Start** menü jobb oldalon található Minden alkalmazás **listából.**</span><span class="sxs-lookup"><span data-stu-id="311b0-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="311b0-250">A **Beállítások** alkalmazás automatikusan el lesz helyezve Ön előtt.</span><span class="sxs-lookup"><span data-stu-id="311b0-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="311b0-251">Válassza **a Hálózati & lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="311b0-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="311b0-252">Görgessen le az elérhető hálózati Wi-Fi, és válassza a **Hardvertulajdonságok lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="311b0-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Hardvertulajdonságok a Wi-Fi beállításaiban](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="311b0-254">Az IP-cím a következő **IPv4-cím mellett jelenik meg:**.</span><span class="sxs-lookup"><span data-stu-id="311b0-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="311b0-255">Hangparancsok használatával</span><span class="sxs-lookup"><span data-stu-id="311b0-255">By using voice commands</span></span>

<span data-ttu-id="311b0-256">Az eszközök felépítésétől függően beépített hangparancsokat vagy Cortanát is használhat az IP-cím megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="311b0-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="311b0-257">Az [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) utáni buildek a "Mi az IP-címem?"</span><span class="sxs-lookup"><span data-stu-id="311b0-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="311b0-258">és megjelenik.</span><span class="sxs-lookup"><span data-stu-id="311b0-258">and it will be displayed.</span></span> <span data-ttu-id="311b0-259">A korábbi buildek vagy a HoloLens (1. generációs) számára a "Hé, Cortana, mi az IP-címem?"</span><span class="sxs-lookup"><span data-stu-id="311b0-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="311b0-260">És Cortana megjeleníti és kiolvassa az IP-címét.</span><span class="sxs-lookup"><span data-stu-id="311b0-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="311b0-261">Az Windows eszközportál</span><span class="sxs-lookup"><span data-stu-id="311b0-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="311b0-262">A számítógépen egy webböngészőben nyissa meg az [eszközportálját.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="311b0-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="311b0-263">Lépjen a **Hálózat szakaszra.**</span><span class="sxs-lookup"><span data-stu-id="311b0-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="311b0-264">Ez a szakasz az IP-címet és egyéb hálózati információkat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="311b0-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="311b0-265">Ezzel a módszerrel másolhatja és beillesztheti az IP-címet a fejlesztői számítógépen.</span><span class="sxs-lookup"><span data-stu-id="311b0-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="311b0-266">IP-cím statikus címre módosítása</span><span class="sxs-lookup"><span data-stu-id="311b0-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="311b0-267">A Beállítások használatával</span><span class="sxs-lookup"><span data-stu-id="311b0-267">By using Settings</span></span>
 
1. <span data-ttu-id="311b0-268">Nyissa meg **a Start menüt.**</span><span class="sxs-lookup"><span data-stu-id="311b0-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="311b0-269">Válassza a **Beállítások** alkalmazást a **Start menüből** vagy a **Start** menü jobb oldalon található Minden alkalmazás **listából.**</span><span class="sxs-lookup"><span data-stu-id="311b0-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="311b0-270">A **Beállítások** alkalmazás automatikusan el lesz helyezve Ön előtt.</span><span class="sxs-lookup"><span data-stu-id="311b0-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="311b0-271">Válassza **a Hálózati & lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="311b0-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="311b0-272">Görgessen le az elérhető hálózati Wi-Fi, és válassza a **Hardvertulajdonságok lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="311b0-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="311b0-273">Az **IP-beállítások szerkesztése ablakban** módosítsa az első mezőt **Manuálisra.**</span><span class="sxs-lookup"><span data-stu-id="311b0-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="311b0-274">A többi mezőben adja meg a kívánt IP-konfigurációt, majd kattintson a **Mentés gombra.**</span><span class="sxs-lookup"><span data-stu-id="311b0-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="311b0-275">Az Windows eszközportál</span><span class="sxs-lookup"><span data-stu-id="311b0-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="311b0-276">A számítógépen egy webböngészőben nyissa meg az [eszközportálját.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="311b0-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="311b0-277">Lépjen a **Hálózat szakaszra.**</span><span class="sxs-lookup"><span data-stu-id="311b0-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="311b0-278">Válassza az **IPv4-konfiguráció** gombot.</span><span class="sxs-lookup"><span data-stu-id="311b0-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="311b0-279">Válassza **a Következő IP-cím használata lehetőséget,** és adja meg a kívánt TCP/IP-konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="311b0-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="311b0-280">Válassza a Use the following DNS server addresses (A következő **DNS-kiszolgálócímek** használata) lehetőséget, és szükség esetén adja meg az előnyben részesített és másodlagos DNS-kiszolgálócímeket.</span><span class="sxs-lookup"><span data-stu-id="311b0-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="311b0-281">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="311b0-281">Click **Save**.</span></span> 
