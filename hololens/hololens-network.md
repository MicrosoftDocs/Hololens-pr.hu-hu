---
title: Csatlakozás HoloLens hálózatra
description: Megtudhatja, hogyan lehet beállítani az internetet és csatlakozni az internethez HoloLens és az eszköz IP-címének azonosítását.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wi-fi, vezeték nélküli, internet, ip, IP-cím
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: c2a2fe1a20a4e9baa194b1037ccb6649d324b990
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640219"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="a7954-104">Csatlakozás HoloLens hálózatra</span><span class="sxs-lookup"><span data-stu-id="a7954-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="a7954-105">Ahhoz, hogy a legtöbb dolgot HoloLens, egy hálózathoz kell csatlakozva lennie.</span><span class="sxs-lookup"><span data-stu-id="a7954-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="a7954-106">HoloLens 802.11ac-kompatibilis, 2x2 Wi-Fi-választógombot tartalmaz, és ahhoz hasonlít, mintha egy Windows 10 Desktop- vagy mobileszközt csatlakoztat egy Wi-Fi-hálózathoz.</span><span class="sxs-lookup"><span data-stu-id="a7954-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="a7954-107">Ez az útmutató a következőben segít:</span><span class="sxs-lookup"><span data-stu-id="a7954-107">This guide will help you:</span></span>

- <span data-ttu-id="a7954-108">Csatlakozás Wi-Fi-vel, vagy csak HoloLens 2-es Wi-Fi Usb-C-kapcsolaton keresztüli közvetlen vagy Ethernet-kapcsolaton keresztüli csatlakozáshoz</span><span class="sxs-lookup"><span data-stu-id="a7954-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="a7954-109">Az Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a7954-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="a7954-110">További információ az [offline HoloLens való használatról.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="a7954-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="a7954-111">Csatlakozás első alkalommal</span><span class="sxs-lookup"><span data-stu-id="a7954-111">Connecting for the first time</span></span>

<span data-ttu-id="a7954-112">Amikor először használja a HoloLens, a rendszer végigvezeti egy hálózati Wi-Fi csatlakozásán.</span><span class="sxs-lookup"><span data-stu-id="a7954-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="a7954-113">Ha a telepítés során problémába Wi-Fi, győződjön meg arról, hogy a hálózat egy nyílt, jelszóval védett hálózat vagy egy portálhálózat.</span><span class="sxs-lookup"><span data-stu-id="a7954-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="a7954-114">Győződjön meg arról is, hogy a hálózat nem igényel tanúsítványt a csatlakozáshoz.</span><span class="sxs-lookup"><span data-stu-id="a7954-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="a7954-115">A beállítás után más típusú hálózati Wi-Fi is csatlakozhat.</span><span class="sxs-lookup"><span data-stu-id="a7954-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="a7954-116">2 HoloLens eszközön a felhasználó [USB-C–Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) adaptert is használhat az Wi-Fi-hoz való közvetlen csatlakozáshoz, hogy segítsen az eszköz beállításában.</span><span class="sxs-lookup"><span data-stu-id="a7954-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="a7954-117">Az eszköz beállítása után a felhasználó továbbra is használhatja az adaptert, vagy leválaszthatja az eszközt az adapterről, és a beállítás után csatlakozhat a [Wi-Fi-hez.](hololens-network.md#connecting-to-wi-fi-after-setup)</span><span class="sxs-lookup"><span data-stu-id="a7954-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="a7954-118">Csatlakozás Wi-Fi telepítés után</span><span class="sxs-lookup"><span data-stu-id="a7954-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="a7954-119">Formázsa előre a **Start kézmozdulatot,** és válassza a **Gépház.**</span><span class="sxs-lookup"><span data-stu-id="a7954-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="a7954-120">A Gépház alkalmazás automatikusan el lesz helyezve Az Ön előtt.</span><span class="sxs-lookup"><span data-stu-id="a7954-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="a7954-121">Válassza **a Hálózati &**  >  **Wi-Fi lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="a7954-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="a7954-122">Győződjön meg arról, hogy a Wi-Fi be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="a7954-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="a7954-123">Ha nem látja a hálózatot, görgessen lefelé a listán.</span><span class="sxs-lookup"><span data-stu-id="a7954-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="a7954-124">Válasszon ki egy hálózatot, majd válassza a **Csatlakozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7954-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="a7954-125">Ha a rendszer hálózati jelszót kér, írja be, majd válassza a Tovább **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="a7954-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens Wi-Fi beállítások](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="a7954-127">Annak megerősítéséhez, hogy csatlakozott egy Wi-Fi hálózathoz, ellenőrizze a Wi-Fi állapotát a **Start menüben:**</span><span class="sxs-lookup"><span data-stu-id="a7954-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="a7954-128">Nyissa meg **a Start menüt.**</span><span class="sxs-lookup"><span data-stu-id="a7954-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="a7954-129">A Start menü bal felső **menüjében** keresse meg Wi-Fi állapotát.</span><span class="sxs-lookup"><span data-stu-id="a7954-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="a7954-130">Megjelenik a Wi-Fi hálózat SSID-ének állapota.</span><span class="sxs-lookup"><span data-stu-id="a7954-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="a7954-131">Ha Wi-Fi nem érhető el, mobilhálózati és [5G-hálózatokhoz is csatlakozhat.](hololens-cellular.md)</span><span class="sxs-lookup"><span data-stu-id="a7954-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7954-132">A felhasználók kialakításuk szerint nem tudják finomhangolni Wi-Fi HoloLens 2 barangolási viselkedését – az Wi-Fi-lista frissítésének egyetlen módja az Wi-Fi ki és **be kapcsolása.**</span><span class="sxs-lookup"><span data-stu-id="a7954-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="a7954-133">Ez számos problémát meggátol, például azt, hogy egy eszköz "elakadhat" egy AP-hez, ha a tartományon kívül van.</span><span class="sxs-lookup"><span data-stu-id="a7954-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="a7954-134">Csatlakozás HoloLens enterprise Wi-Fi Networkre</span><span class="sxs-lookup"><span data-stu-id="a7954-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="a7954-135">A Wi-Fi profiljai az EAP protokollt (Extensible Authentication Protocol) használják a Wi-Fi hitelesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="a7954-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="a7954-136">HoloLens A vállalati Wi-Fi profil az MDM vagy a Configuration Designer által létrehozott [kiépítési Windows konfigurálható.](/windows/configuration/provisioning-packages/provisioning-packages)</span><span class="sxs-lookup"><span data-stu-id="a7954-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="a7954-137">A Microsoft Intune eszközről a konfigurációs [utasításokért tekintse](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) meg az Intune-t.</span><span class="sxs-lookup"><span data-stu-id="a7954-137">For Microsoft Intune managed device, refer to [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="a7954-138">A Wi-Fi kiépítési csomag WCD-ben való létrehozásához egy előre konfigurált Wi-Fi profilra és .xml fájlra van szükség.</span><span class="sxs-lookup"><span data-stu-id="a7954-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="a7954-139">Az EAP-TLSWi-Fi hitelesítéssel WPA2-Enterprise mintaprofil:</span><span class="sxs-lookup"><span data-stu-id="a7954-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="a7954-140">Az EAP típusától függően előfordulhat, hogy a kiszolgáló legfelső szintű hitelesítésszolgáltatói tanúsítványát és az ügyféltanúsítványt kell kiépítenünk az eszközön.</span><span class="sxs-lookup"><span data-stu-id="a7954-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="a7954-141">További források:</span><span class="sxs-lookup"><span data-stu-id="a7954-141">Additional resources:</span></span>

- <span data-ttu-id="a7954-142">WLANv1Profile séma: [[MS-GPWL]: Vezeték nélküli LAN-profil v1 séma | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="a7954-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="a7954-143">EAP-TLS-séma: [[MS-GPWL]: Microsoft EAP TLS-séma | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="a7954-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="a7954-144">Ha [problémákat tapasztal](hololens2-enterprise-troubleshooting.md#) a Wi-Fi-hez való csatlakozáskor, tekintse meg a Hibaelhárítás oldalt.</span><span class="sxs-lookup"><span data-stu-id="a7954-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="a7954-145">Hálózati proxy konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a7954-145">Configure Network Proxy</span></span>

<span data-ttu-id="a7954-146">Ez a szakasz a HTTP-verem HoloLens és a Universal Windows Platform (UWP) alkalmazások hálózati proxyját Windows be.</span><span class="sxs-lookup"><span data-stu-id="a7954-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="a7954-147">A nem Windows HTTP-vermet használó alkalmazások saját proxykonfigurációval és -kezeléssel is használhatók.</span><span class="sxs-lookup"><span data-stu-id="a7954-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="a7954-148">Proxykonfigurációk</span><span class="sxs-lookup"><span data-stu-id="a7954-148">Proxy Configurations</span></span> 

- <span data-ttu-id="a7954-149">Pac-proxy automatikus konfigurációs parancsfájl: a [PAC-fájl](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (amely nem Microsoft webhelyet nyit meg) tartalmaz egy FindProxyForURL(url, host) JavaScript-függvényt.</span><span class="sxs-lookup"><span data-stu-id="a7954-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="a7954-150">Statikus proxy: Kiszolgáló:Port alakban.</span><span class="sxs-lookup"><span data-stu-id="a7954-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="a7954-151">Webproxy automatikus felderítési protokoll (WPAD): adja meg a proxykonfigurációs fájl URL-címét DHCP-en vagy DNS-en keresztül.</span><span class="sxs-lookup"><span data-stu-id="a7954-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="a7954-152">Proxy-kiépítési módszerek</span><span class="sxs-lookup"><span data-stu-id="a7954-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="a7954-153">A proxyk üzembe építésének három módja van:</span><span class="sxs-lookup"><span data-stu-id="a7954-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="a7954-154">**Gépház Ui:**</span><span class="sxs-lookup"><span data-stu-id="a7954-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="a7954-155">Felhasználónkénti proxy (20H2 vagy korábbi):</span><span class="sxs-lookup"><span data-stu-id="a7954-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="a7954-156">Nyissa meg a Start menü, és válassza a Gépház.</span><span class="sxs-lookup"><span data-stu-id="a7954-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="a7954-157">Válassza a Network & internet, majd a proxy lehetőséget a bal oldali menüben.</span><span class="sxs-lookup"><span data-stu-id="a7954-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="a7954-158">Görgessen le a Manual proxy setup (Manuális proxybeállítás) elemre, és a Use a proxy server (Proxykiszolgáló használata) beállítást pedig a On (Be) beállításra.</span><span class="sxs-lookup"><span data-stu-id="a7954-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="a7954-159">Adja meg a proxykiszolgáló IP-címét.</span><span class="sxs-lookup"><span data-stu-id="a7954-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="a7954-160">Adja meg a portszámot.</span><span class="sxs-lookup"><span data-stu-id="a7954-160">Enter the port number.</span></span>
        6. <span data-ttu-id="a7954-161">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a7954-161">Click Save.</span></span>
      1. <span data-ttu-id="a7954-162">Wi-Fi-proxy (21H1 vagy újabb):</span><span class="sxs-lookup"><span data-stu-id="a7954-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="a7954-163">Nyissa meg Start menü, és nyissa meg a Wi-Fi hálózat Tulajdonságok lapját.</span><span class="sxs-lookup"><span data-stu-id="a7954-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="a7954-164">Görgessen le a Proxyhoz</span><span class="sxs-lookup"><span data-stu-id="a7954-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="a7954-165">Módosítás manuális beállításra</span><span class="sxs-lookup"><span data-stu-id="a7954-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="a7954-166">Adja meg a proxykiszolgáló IP-címét.</span><span class="sxs-lookup"><span data-stu-id="a7954-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="a7954-167">Adja meg a portszámot.</span><span class="sxs-lookup"><span data-stu-id="a7954-167">Enter the port number.</span></span>
          1. <span data-ttu-id="a7954-168">Kattintson az Alkalmaz gombra.</span><span class="sxs-lookup"><span data-stu-id="a7954-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="a7954-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="a7954-169">**MDM**</span></span> 
     1. <span data-ttu-id="a7954-170">Intune – Ezekkel a [lépésekkel konfigurálhatja](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) a proxyt az Intune-ban.</span><span class="sxs-lookup"><span data-stu-id="a7954-170">Intune - Use these [steps](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="a7954-171">A szakasz aljára kell görgetnie.</span><span class="sxs-lookup"><span data-stu-id="a7954-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="a7954-172">Egyéb, harmadik féltől származó MDM-megoldások – [Wi-Fi CSP használata.](/windows/client-management/mdm/wifi-csp)</span><span class="sxs-lookup"><span data-stu-id="a7954-172">Other 3rd party MDM solutions - Use a [WiFi CSP](/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="a7954-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="a7954-173">**PPKG**</span></span> 
    1. <span data-ttu-id="a7954-174">A Windows Configuration Designer megnyitása</span><span class="sxs-lookup"><span data-stu-id="a7954-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="a7954-175">Kattintson a Speciális kiépítés elemre, adja meg az új Project majd kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="a7954-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="a7954-176">Válassza Windows Holographic (HoloLens 2) lehetőséget, majd kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="a7954-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="a7954-177">Importálja a PPKG-t (nem kötelező), majd kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="a7954-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="a7954-178">Bontsa ki a Runtime Gépház -> Connectivity Profiles -> WLAN -> WLAN Proxy (WLAN -> kapcsolati profilok ->- és WLAN-proxy) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7954-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="a7954-179">Adja meg a hálózati Wi-Fi SSID-ját, majd kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="a7954-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="a7954-180">Válassza ki a Wi-Fi a bal oldali ablakban, és adja meg a kívánt testreszabásokat.</span><span class="sxs-lookup"><span data-stu-id="a7954-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="a7954-181">Az engedélyezett testreszabások félkövérrel jelennek meg a bal oldali menüben.</span><span class="sxs-lookup"><span data-stu-id="a7954-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="a7954-182">Kattintson a Mentés és kilépés gombra.</span><span class="sxs-lookup"><span data-stu-id="a7954-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="a7954-183">[Alkalmazza a](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) kiépítési csomagot a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a7954-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="a7954-184">[A felhőszolgáltatók](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) számos felügyeleti feladat és szabályzat mögött állnak a Windows 10, mind a Microsoft Intune, mind a nem Microsoft MDM-szolgáltatóknál.</span><span class="sxs-lookup"><span data-stu-id="a7954-184">[CSPs](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="a7954-185">A Configuration [Designer Windows](/windows/configuration/provisioning-packages/provisioning-install-icd) is használhatja [egy](/windows/configuration/provisioning-packages/provisioning-packages) kiépítési csomag létrehozásához és a 2. HoloLens alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="a7954-185">You can also use [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="a7954-186">A 2. HoloLens CSP-k a legvalószínűbbek:</span><span class="sxs-lookup"><span data-stu-id="a7954-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="a7954-187">[WiFi CSP:](/windows/client-management/mdm/wifi-csp)profilonkénti Wi-Fi proxy</span><span class="sxs-lookup"><span data-stu-id="a7954-187">[WiFi CSP](/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="a7954-188">A mobileszközökön támogatott HoloLens CSP-k</span><span class="sxs-lookup"><span data-stu-id="a7954-188">Other CSPs supported in HoloLens devices</span></span>](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="a7954-189">VPN</span><span class="sxs-lookup"><span data-stu-id="a7954-189">VPN</span></span>
<span data-ttu-id="a7954-190">A VPN-kapcsolat biztonságosabb kapcsolatot és hozzáférést biztosít a vállalat hálózatához és az internethez.</span><span class="sxs-lookup"><span data-stu-id="a7954-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="a7954-191">HoloLens 2. modul támogatja a beépített VPN-ügyfelet és a Universal Windows Platform (UWP) VPN beépülő modult.</span><span class="sxs-lookup"><span data-stu-id="a7954-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="a7954-192">Támogatott beépített VPN-protokollok:</span><span class="sxs-lookup"><span data-stu-id="a7954-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="a7954-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="a7954-193">IKEv2</span></span>
- <span data-ttu-id="a7954-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="a7954-194">L2TP</span></span>
- <span data-ttu-id="a7954-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="a7954-195">PPTP</span></span>

<span data-ttu-id="a7954-196">Ha a beépített VPN-ügyfél hitelesítéséhez tanúsítványt használ, a szükséges ügyfél-tanúsítványt hozzá kell adni a felhasználói tanúsítványtárolóhoz.</span><span class="sxs-lookup"><span data-stu-id="a7954-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="a7954-197">Annak ellenőrzéséhez, hogy egy harmadik féltől származó VPN beépülő modul támogatja-e a HoloLens 2-es verzió működését, az Áruházban keresse meg a VPN-alkalmazást, és ellenőrizze, hogy az HoloLens támogatott eszközként szerepel-e a listán, és a Rendszerkövetelmények lapon az alkalmazás támogatja-e az ARM- vagy ARM64-architektúrát.</span><span class="sxs-lookup"><span data-stu-id="a7954-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="a7954-198">HoloLens a Universal Windows Platform alkalmazásokat csak külső VPN-hez támogatja.</span><span class="sxs-lookup"><span data-stu-id="a7954-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="a7954-199">A VPN-t MDM-en keresztül lehet [Gépház/AllowVPN-en](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)keresztül kezelni, és [vpnv2-csp szabályzattal lehet beállítani.](/windows/client-management/mdm/vpnv2-csp)</span><span class="sxs-lookup"><span data-stu-id="a7954-199">VPN can be managed by MDM via [Settings/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="a7954-200">A VPN [konfigurálásról az alábbi](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) [útmutatókban olvashat bővebben.](/windows/security/identity-protection/vpn/vpn-guide)</span><span class="sxs-lookup"><span data-stu-id="a7954-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="a7954-201">VPN felhasználói felületen keresztül</span><span class="sxs-lookup"><span data-stu-id="a7954-201">VPN via UI</span></span>

<span data-ttu-id="a7954-202">A VPN alapértelmezés szerint nincs engedélyezve,  de manuálisan is engedélyezhető egy Gépház megnyitásával és a **Network & Internet -> VPN megnyitásával.**</span><span class="sxs-lookup"><span data-stu-id="a7954-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="a7954-203">Válasszon ki egy VPN-szolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="a7954-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="a7954-204">Hozzon létre egy kapcsolatnevet.</span><span class="sxs-lookup"><span data-stu-id="a7954-204">Create a connection name.</span></span> 
1. <span data-ttu-id="a7954-205">Adja meg a kiszolgáló nevét vagy címét.</span><span class="sxs-lookup"><span data-stu-id="a7954-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="a7954-206">Válassza ki a VPN típusát.</span><span class="sxs-lookup"><span data-stu-id="a7954-206">Select the VPN type.</span></span>
1. <span data-ttu-id="a7954-207">Válassza ki a bejelentkezési adatok típusát.</span><span class="sxs-lookup"><span data-stu-id="a7954-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="a7954-208">Ha szükséges, adjon meg egy felhasználónevet és egy jelszót.</span><span class="sxs-lookup"><span data-stu-id="a7954-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="a7954-209">Alkalmazza a VPN-beállításokat.</span><span class="sxs-lookup"><span data-stu-id="a7954-209">Apply the VPN settings.</span></span> 

![HoloLens VPN-beállítások](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="a7954-211">VPN beállítása kiépítési csomagon keresztül</span><span class="sxs-lookup"><span data-stu-id="a7954-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="a7954-212">A holografikus Windows 20H2-es verziójában kijavítottunk egy proxykonfigurációs hibát a VPN-kapcsolathoz.</span><span class="sxs-lookup"><span data-stu-id="a7954-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="a7954-213">Ha ezt a folyamatot szeretné használni, fontolja meg az eszközök frissítését erre a buildre.</span><span class="sxs-lookup"><span data-stu-id="a7954-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="a7954-214">Indítsa el Windows Configuration Designert.</span><span class="sxs-lookup"><span data-stu-id="a7954-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="a7954-215">Kattintson a Provision HoloLens devices (Eszközök **kiépítése)** elemre, majd válassza ki a céleszközt, és kattintson a **Next (Tovább) gombra.**</span><span class="sxs-lookup"><span data-stu-id="a7954-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="a7954-216">Adja meg a csomag nevét és elérési útját.</span><span class="sxs-lookup"><span data-stu-id="a7954-216">Enter package name and path.</span></span>
1. <span data-ttu-id="a7954-217">Kattintson **a Váltás speciális szerkesztőre lehetőségre.**</span><span class="sxs-lookup"><span data-stu-id="a7954-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="a7954-218">Nyissa **meg a Runtime settings**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings (Futtatás** futásidejű beállításai) Beállítást.</span><span class="sxs-lookup"><span data-stu-id="a7954-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="a7954-219">A VPNProfileName konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a7954-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="a7954-220">Válassza a ProfileType: **Native (Natív) vagy** **a Third Party (Harmadik fél) lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="a7954-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="a7954-221">A Natív profil beállításnál válassza a **NativeProtocolType** lehetőséget, majd konfigurálja a kiszolgálót, az útválasztási házirendet, a hitelesítési típust és az egyéb beállításokat.</span><span class="sxs-lookup"><span data-stu-id="a7954-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="a7954-222">A "Külső gyártótól származó" profilhoz konfigurálja a kiszolgáló URL-címét, a VPN beépülő modul alkalmazáscsomagjának családnevét (csak 3 előre definiált) és egyéni konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="a7954-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="a7954-223">Exportálja a csomagot.</span><span class="sxs-lookup"><span data-stu-id="a7954-223">Export your package.</span></span>
1. <span data-ttu-id="a7954-224">Csatlakozás a HoloLens, és másolja a .ppkg fájlt az eszközre.</span><span class="sxs-lookup"><span data-stu-id="a7954-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="a7954-225">A HoloLens a VPN .ppkg fájlban a Start menü megnyitásával és Gépház Munkahelyi vagy iskolai fiókelérésI csomag hozzáadása vagy eltávolítása -> VÁLASSZA ki **a**  ->    ->    ->   VPN-csomagot lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7954-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="a7954-226">VPN beállítása az Intune-on keresztül</span><span class="sxs-lookup"><span data-stu-id="a7954-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="a7954-227">Az első lépésekhez kövesse az Intune-dokumentumokat.</span><span class="sxs-lookup"><span data-stu-id="a7954-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="a7954-228">A lépések lépéseikor tartsa szem előtt az eszközök által támogatott HoloLens VPN-protokollokat.</span><span class="sxs-lookup"><span data-stu-id="a7954-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="a7954-229">[VPN-profilok létrehozása VPN-kiszolgálókhoz való csatlakozáshoz az Intune-ban.](/mem/intune/configuration/vpn-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="a7954-229">[Create VPN profiles to connect to VPN servers in Intune](/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="a7954-230">[Windows 10 és Windows Holographic eszközbeállításokkal VPN-kapcsolatokat adhat hozzá az Intune-nal.](/mem/intune/configuration/vpn-settings-windows-10)</span><span class="sxs-lookup"><span data-stu-id="a7954-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="a7954-231">Ha végzett, ne felejtse el [hozzárendelni a profilt.](/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="a7954-231">When done please remember to [assign the profile](/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="a7954-232">VPN külső MDM-megoldásokon keresztül</span><span class="sxs-lookup"><span data-stu-id="a7954-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="a7954-233">Példa külső VPN-kapcsolatra:</span><span class="sxs-lookup"><span data-stu-id="a7954-233">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="a7954-234">Példa natív IKEv2 VPN-re:</span><span class="sxs-lookup"><span data-stu-id="a7954-234">Native IKEv2 VPN example:</span></span>
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="a7954-235">A Wi-Fi letiltása HoloLens (1. generációs)</span><span class="sxs-lookup"><span data-stu-id="a7954-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="a7954-236">A Gépház alkalmazás használata a HoloLens</span><span class="sxs-lookup"><span data-stu-id="a7954-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="a7954-237">Nyissa meg **a Start menüt.**</span><span class="sxs-lookup"><span data-stu-id="a7954-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="a7954-238">Válassza ki **Gépház** alkalmazást a **Start** menüből vagy a **Start** menü jobb oldalon található Minden alkalmazás **listájából.**</span><span class="sxs-lookup"><span data-stu-id="a7954-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="a7954-239">A **Gépház** alkalmazás automatikusan el lesz helyezve Ön előtt.</span><span class="sxs-lookup"><span data-stu-id="a7954-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="a7954-240">Válassza **a Hálózati & lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="a7954-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="a7954-241">A csúszka Wi-Fi a csúszkakapcsolót, hogy a Ki **állásba helyezze.**</span><span class="sxs-lookup"><span data-stu-id="a7954-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="a7954-242">Ezzel kikapcsolja az rf-Wi-Fi választógombot, és letiltja Wi-Fi összes HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a7954-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="a7954-243">Ha a Wi-Fi választógomb le van tiltva, HoloLens nem tudja automatikusan betölteni a [szóközöket.](hololens-spaces.md)</span><span class="sxs-lookup"><span data-stu-id="a7954-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="a7954-244">Húzza a csúszkakapcsolót **a** Be állásba, hogy be tudja kapcsolni a Wi-Fi választógombot, és állítsa Wi-Fi a Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a7954-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="a7954-245">A kiválasztott Wi-Fi választógomb állapota (**Be** vagy **Ki**) megmarad az újraindítások között.</span><span class="sxs-lookup"><span data-stu-id="a7954-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="a7954-246">A hálózati HoloLens IP-Wi-Fi azonosítása</span><span class="sxs-lookup"><span data-stu-id="a7954-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="a7954-247">A Gépház alkalmazással</span><span class="sxs-lookup"><span data-stu-id="a7954-247">By using the Settings app</span></span>

1. <span data-ttu-id="a7954-248">Nyissa meg **a Start menüt.**</span><span class="sxs-lookup"><span data-stu-id="a7954-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="a7954-249">Válassza ki **Gépház** alkalmazást a **Start** menüből vagy a **Start** menü jobb oldalon található Minden alkalmazás **listájából.**</span><span class="sxs-lookup"><span data-stu-id="a7954-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="a7954-250">A **Gépház** alkalmazás automatikusan el lesz helyezve Ön előtt.</span><span class="sxs-lookup"><span data-stu-id="a7954-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="a7954-251">Válassza **a Hálózati & lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="a7954-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="a7954-252">Görgessen le az elérhető hálózati Wi-Fi, és válassza a **Hardvertulajdonságok lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="a7954-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Hardvertulajdonságok a Wi-Fi beállításaiban](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="a7954-254">Az IP-cím a következő **IPv4-cím mellett jelenik meg:**.</span><span class="sxs-lookup"><span data-stu-id="a7954-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="a7954-255">Hangparancsok használatával</span><span class="sxs-lookup"><span data-stu-id="a7954-255">By using voice commands</span></span>

<span data-ttu-id="a7954-256">Az eszközök felépítésétől függően használhatja a beépített hangparancsokat, vagy Cortana az IP-cím megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="a7954-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="a7954-257">Az [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) utáni buildek a "Mi az IP-címem?"</span><span class="sxs-lookup"><span data-stu-id="a7954-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="a7954-258">és megjelenik.</span><span class="sxs-lookup"><span data-stu-id="a7954-258">and it will be displayed.</span></span> <span data-ttu-id="a7954-259">Korábbi buildek vagy HoloLens (1. generációs) kérdésre: "Hey Cortana, What's my IP address?"</span><span class="sxs-lookup"><span data-stu-id="a7954-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="a7954-260">A Cortana megjelenik és kiolvassa az IP-címét.</span><span class="sxs-lookup"><span data-stu-id="a7954-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="a7954-261">Az Windows Eszközportál</span><span class="sxs-lookup"><span data-stu-id="a7954-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="a7954-262">A számítógépen egy webböngészőben nyissa meg az [eszközportálját.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="a7954-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="a7954-263">Lépjen a **Hálózat szakaszra.**</span><span class="sxs-lookup"><span data-stu-id="a7954-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="a7954-264">Ez a szakasz az IP-címet és egyéb hálózati információkat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="a7954-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="a7954-265">Ezzel a módszerrel másolhatja és beillesztheti az IP-címet a fejlesztői számítógépen.</span><span class="sxs-lookup"><span data-stu-id="a7954-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="a7954-266">IP-cím statikus címre módosítása</span><span class="sxs-lookup"><span data-stu-id="a7954-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="a7954-267">Az Gépház</span><span class="sxs-lookup"><span data-stu-id="a7954-267">By using Settings</span></span>
 
1. <span data-ttu-id="a7954-268">Nyissa meg **a Start menüt.**</span><span class="sxs-lookup"><span data-stu-id="a7954-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="a7954-269">Válassza ki **Gépház** alkalmazást a **Start** menüből vagy a **Start** menü jobb oldalon található Minden alkalmazás **listájából.**</span><span class="sxs-lookup"><span data-stu-id="a7954-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="a7954-270">A **Gépház** alkalmazás automatikusan el lesz helyezve Ön előtt.</span><span class="sxs-lookup"><span data-stu-id="a7954-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="a7954-271">Válassza **a Hálózati & lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="a7954-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="a7954-272">Görgessen le az elérhető hálózati Wi-Fi, és válassza a **Hardvertulajdonságok lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="a7954-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="a7954-273">Az **IP-beállítások szerkesztése ablakban** módosítsa az első mezőt **Manuálisra.**</span><span class="sxs-lookup"><span data-stu-id="a7954-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="a7954-274">A többi mezőben adja meg a kívánt IP-konfigurációt, majd kattintson a **Mentés gombra.**</span><span class="sxs-lookup"><span data-stu-id="a7954-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="a7954-275">Az Windows Eszközportál</span><span class="sxs-lookup"><span data-stu-id="a7954-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="a7954-276">A számítógépen egy webböngészőben nyissa meg az [eszközportálját.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="a7954-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="a7954-277">Lépjen a **Hálózat szakaszra.**</span><span class="sxs-lookup"><span data-stu-id="a7954-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="a7954-278">Válassza az **IPv4-konfiguráció** gombot.</span><span class="sxs-lookup"><span data-stu-id="a7954-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="a7954-279">Válassza **a Következő IP-cím használata lehetőséget,** és adja meg a kívánt TCP/IP-konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="a7954-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="a7954-280">Válassza a Use the following DNS server addresses (A következő **DNS-kiszolgálócímek** használata) lehetőséget, és szükség esetén adja meg az előnyben részesített és másodlagos DNS-kiszolgálócímeket.</span><span class="sxs-lookup"><span data-stu-id="a7954-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="a7954-281">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="a7954-281">Click **Save**.</span></span> 
