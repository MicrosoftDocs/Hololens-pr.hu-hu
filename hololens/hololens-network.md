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
ms.openlocfilehash: d68c75dcb2249a67f2e07c77cb1b69997eb0ae72
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379588"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="fdfe8-104">A HoloLens csatlakoztatása hálózathoz</span><span class="sxs-lookup"><span data-stu-id="fdfe8-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="fdfe8-105">A HoloLensen a legtöbb dologhoz egy hálózathoz kell csatlakozva lennie.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="fdfe8-106">A HoloLens egy 802.11ac-kompatibilis, 2x2 Wi-Fi-választógombot tartalmaz, és ahhoz hasonlít, mintha egy Windows 10 Desktop- vagy mobileszközt csatlakoztat egy Wi-Fi-hálózathoz.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="fdfe8-107">Ez az útmutató a következőben segít:</span><span class="sxs-lookup"><span data-stu-id="fdfe8-107">This guide will help you:</span></span>

- <span data-ttu-id="fdfe8-108">Csatlakozás hálózathoz Wi-Fi használatával, vagy csak a HoloLens 2 esetén közvetlen Wi-Fi Ethernet usb-C-kapcsolaton keresztül</span><span class="sxs-lookup"><span data-stu-id="fdfe8-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="fdfe8-109">Az Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="fdfe8-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="fdfe8-110">További információ a [HoloLens offline módban való használatával kapcsolatban.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="fdfe8-111">Csatlakozás első alkalommal</span><span class="sxs-lookup"><span data-stu-id="fdfe8-111">Connecting for the first time</span></span>

<span data-ttu-id="fdfe8-112">Amikor először használja a HoloLenst, a rendszer végigvezeti egy Wi-Fi csatlakoztatásán.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="fdfe8-113">Ha a telepítés során problémába Wi-Fi, győződjön meg arról, hogy a hálózat egy nyílt, jelszóval védett hálózat vagy egy portálhálózat.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="fdfe8-114">Azt is ellenőrizze, hogy a hálózat nem igényel-e tanúsítványt a csatlakozáshoz.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="fdfe8-115">A beállítás után más típusú hálózati Wi-Fi is csatlakozhat.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="fdfe8-116">HoloLens 2-eszközökön a felhasználók [USB-C–Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) adapterrel is csatlakozhatnak közvetlenül az Wi-Fi-hoz, hogy segítsenek az eszköz beállításában.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="fdfe8-117">Az eszköz beállítása után a felhasználó továbbra is használhatja az adaptert, vagy leválaszthatja az eszközt az adapterről, és a beállítás után csatlakozhat a [Wi-Fi-hez.](hololens-network.md#connecting-to-wi-fi-after-setup)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="fdfe8-118">Csatlakozás Wi-Fi telepítés után</span><span class="sxs-lookup"><span data-stu-id="fdfe8-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="fdfe8-119">Formázhatja előre a **Start kézmozdulatot,** és válassza a **Beállítások lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="fdfe8-120">A Beállítások alkalmazás automatikusan az Ön elé kerül.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="fdfe8-121">Válassza **a Hálózati &**  >  **Wi-Fi lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="fdfe8-122">Győződjön meg arról, hogy a Wi-Fi be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="fdfe8-123">Ha nem látja a hálózatot, görgessen lefelé a listán.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="fdfe8-124">Válasszon ki egy hálózatot, majd válassza a **Csatlakozás lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="fdfe8-125">Ha a rendszer hálózati jelszót kér, írja be, majd válassza a Tovább **lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens-Wi-Fi beállításai](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="fdfe8-127">Annak megerősítéséhez, hogy csatlakozott egy Wi-Fi hálózathoz, ellenőrizze a Wi-Fi állapotát a **Start menüben:**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="fdfe8-128">Nyissa meg **a Start menüt.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="fdfe8-129">A Start menü bal felső **menüjében** keresse meg Wi-Fi állapotát.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="fdfe8-130">Megjelenik a Wi-Fi hálózat SSID-ének állapota.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="fdfe8-131">Ha Wi-Fi nem érhető el, mobilhálózati és [5G-hálózatokhoz is csatlakozhat.](https://docs.microsoft.com/hololens/hololens-cellular)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](https://docs.microsoft.com/hololens/hololens-cellular).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fdfe8-132">A felhasználók a kialakításuk szerint nem tudják finomhangolni a HoloLens 2 Wi-Fi roaming viselkedését – az Wi-Fi-lista frissítésének egyetlen módja az Wi-Fi ki- és **bekapcsolása.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="fdfe8-133">Ez számos problémát meggátol, például azt, hogy egy eszköz "elakadhat" egy AP-hez, ha a tartományon kívül van.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="troubleshooting-your-connection-to-wi-fi"></a><span data-ttu-id="fdfe8-134">A hálózati kapcsolat hibaelhárítása Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="fdfe8-134">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="fdfe8-135">Ha problémákat tapasztal a Wi-Fi-hez való csatlakozáskor, tekintse meg a Nem tudok csatlakozni a [Wi-Fi-hez való csatlakozást.](./hololens-faq.md#i-cant-connect-to-wi-fi)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-135">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="fdfe8-136">Amikor vállalati vagy szervezeti fiókba jelentkezik be az eszközön, az a Mobile Eszközkezelés (MDM) szabályzatot is alkalmazhatja, ha a házirendet a rendszergazda konfigurálta.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-136">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="fdfe8-137">A HoloLens csatlakoztatása az Enterprise Wi-Fi Network szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="fdfe8-137">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="fdfe8-138">A Wi-Fi profiljai az EAP protokollt (Extensible Authentication Protocol) használják a Wi-Fi hitelesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-138">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="fdfe8-139">A HoloLens Enterprise Wi-Fi profil a Windows Configuration Designer által létrehozott MDM vagy kiépítési csomag [segítségével konfigurálható.](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-139">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="fdfe8-140">A Microsoft Intune eszköz konfigurálási utasításait az [Intune-ban](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) használhatja.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-140">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="fdfe8-141">Ha Wi-Fi csomagot a WCD-ben, egy előre konfigurált Wi-Fi profilra és .xml fájlra van szükség.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-141">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="fdfe8-142">Az EAP-TLSWi-Fi hitelesítéssel WPA2-Enterprise mintaprofil:</span><span class="sxs-lookup"><span data-stu-id="fdfe8-142">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="fdfe8-143">Az EAP típusától függően előfordulhat, hogy a kiszolgáló legfelső szintű hitelesítésszolgáltatói tanúsítványát és az ügyféltanúsítványt kell kiépítenünk az eszközön.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-143">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="fdfe8-144">További források:</span><span class="sxs-lookup"><span data-stu-id="fdfe8-144">Additional resources:</span></span>

- <span data-ttu-id="fdfe8-145">WLANv1Profile séma: [[MS-GPWL]: Vezeték nélküli LAN-profil v1 séma | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-145">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="fdfe8-146">EAP-TLS-séma: [[MS-GPWL]: Microsoft EAP TLS-séma | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-146">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

## <a name="eap-troubleshooting"></a><span data-ttu-id="fdfe8-147">EAP-hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="fdfe8-147">EAP Troubleshooting</span></span>
> [!TIP]
> <span data-ttu-id="fdfe8-148">A hálózati problémák többségét az eredményezi, hogy az alábbi 3 beállítás valamelyike helytelen a Wi-FI-profilban.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-148">A majority of network issues are the result of one of the below 3 settings being incorrect in the Wi-FI profile.</span></span> 
1. <span data-ttu-id="fdfe8-149">Ellenőrizze, Wi-Fi profil rendelkezik-e a megfelelő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="fdfe8-149">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="fdfe8-150">Az EAP-típus megfelelően van konfigurálva, gyakori EAP-típusok: EAP-TLS (13), EAP-TTLS (21) és PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="fdfe8-150">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="fdfe8-151">Wi-Fi SSID neve helyes, és HEX-sztringre illeszkedik.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-151">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="fdfe8-152">EAP-TLS-hez a TrustedRootCA tartalmazza a megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványának&#39;SHA-1 kivonatát.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-152">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="fdfe8-153">Windows rendszerű számítógépekencertutil.exe -dump cert fájlnév parancs egy tanúsítványt fog&#39;&quot; \_ \_ &quot; SHA-1 kivonatsringhez.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-153">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>

2. <span data-ttu-id="fdfe8-154">Gyűjtse össze a hálózati csomagrögzítést a hozzáférési pont, a vezérlő vagy az AAA-kiszolgáló naplóiban, hogy megtudja, hol nem sikerül az EAP-munkamenet.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-154">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="fdfe8-155">Ha a HoloLens által biztosított EAP-identitás nem várható, ellenőrizze, hogy az identitás megfelelően lett-e Wi-Fi-profilon vagy ügyfél-tanúsítványon keresztül.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-155">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="fdfe8-156">Ha a kiszolgáló elutasítja a HoloLens-ügyfél tanúsítványát, ellenőrizze, hogy a szükséges ügyfél-tanúsítvány ki lett-e építve az eszközön.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-156">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="fdfe8-157">Ha a HoloLens elutasítja a kiszolgálótanúsítványt, ellenőrizze, hogy a kiszolgáló legfelső szintű hitelesítésszolgáltatói tanúsítványa ki lett-e építve a HoloLensen.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-157">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="fdfe8-158">Ha a vállalati profil egy kiépítési Wi-Fi keresztül van kiépítve, fontolja meg a kiépítési csomag alkalmazását egy Windows 10 számítógépen.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-158">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="fdfe8-159">Ha a hiba a Windows 10 is sikertelen, kövesse a [Windows-ügyfél 802.1X hitelesítési hibaelhárítási útmutatóját.](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-159">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="fdfe8-160">Állítsa a telemetriát Teljes vagy Választható (a buildtől függően) beállításra, majd küldjön visszajelzést a [Visszajelzési központ.](https://docs.microsoft.com/hololens/hololens-feedback)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-160">Set your telemetry to Full or Optional (depending on your build) and then send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="fdfe8-161">További források:</span><span class="sxs-lookup"><span data-stu-id="fdfe8-161">Additional resources:</span></span>
- [<span data-ttu-id="fdfe8-162">Wi-Fi beállítások exportálása windowsos eszközről</span><span class="sxs-lookup"><span data-stu-id="fdfe8-162">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="configure-network-proxy"></a><span data-ttu-id="fdfe8-163">Hálózati proxy konfigurálása</span><span class="sxs-lookup"><span data-stu-id="fdfe8-163">Configure Network Proxy</span></span>

<span data-ttu-id="fdfe8-164">Ez a szakasz a HoloLens operációs rendszer és a Windows HTTP-vermét használó Univerzális Windows-platform (UWP) alkalmazások hálózati proxyját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-164">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="fdfe8-165">A nem Windows HTTP-vermeket használó alkalmazások saját proxykonfigurációval és -kezeléssel is használhatók.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-165">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="fdfe8-166">Proxykonfigurációk</span><span class="sxs-lookup"><span data-stu-id="fdfe8-166">Proxy Configurations</span></span> 

- <span data-ttu-id="fdfe8-167">Pac-proxy automatikus konfigurációs parancsfájl: a [PAC-fájl](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (amely nem Microsoft webhelyet nyit meg) tartalmaz egy FindProxyForURL(url, host) JavaScript-függvényt.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-167">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="fdfe8-168">Statikus proxy: Kiszolgáló:Port alakban.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-168">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="fdfe8-169">Webproxy automatikus felderítési protokollja (WPAD): ADJA meg a proxykonfigurációs fájl URL-címét DHCP-en vagy DNS-en keresztül.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-169">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="fdfe8-170">Proxy-kiépítési módszerek</span><span class="sxs-lookup"><span data-stu-id="fdfe8-170">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="fdfe8-171">A proxyk kiépítése háromféleképpen lehetséges:</span><span class="sxs-lookup"><span data-stu-id="fdfe8-171">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="fdfe8-172">**Beállítások felhasználói felülete:**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-172">**Settings UI:**</span></span> 
    1. <span data-ttu-id="fdfe8-173">Felhasználónkénti proxy (20H2 vagy korábbi):</span><span class="sxs-lookup"><span data-stu-id="fdfe8-173">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="fdfe8-174">Nyissa meg a Start menü, és válassza a Beállítások lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-174">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="fdfe8-175">Válassza a Network & internet, majd a proxy lehetőséget a bal oldali menüben.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-175">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="fdfe8-176">Görgessen le a Manual proxy setup (Manuális proxybeállítás) elemre, és a Use a proxy server (Proxykiszolgáló használata) beállítást pedig a On (Be) beállításra.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-176">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="fdfe8-177">Adja meg a proxykiszolgáló IP-címét.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-177">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="fdfe8-178">Adja meg a portszámot.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-178">Enter the port number.</span></span>
        6. <span data-ttu-id="fdfe8-179">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-179">Click Save.</span></span>
      1. <span data-ttu-id="fdfe8-180">Wi-Fi-proxy (21H1 vagy újabb):</span><span class="sxs-lookup"><span data-stu-id="fdfe8-180">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="fdfe8-181">Nyissa meg Start menü, és nyissa meg Wi-Fi hálózat Tulajdonságok lapját.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-181">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="fdfe8-182">Görgessen le a Proxyhoz</span><span class="sxs-lookup"><span data-stu-id="fdfe8-182">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="fdfe8-183">Módosítás manuális beállításra</span><span class="sxs-lookup"><span data-stu-id="fdfe8-183">Change to Manual Setup</span></span>
          1. <span data-ttu-id="fdfe8-184">Adja meg a proxykiszolgáló IP-címét.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-184">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="fdfe8-185">Adja meg a portszámot.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-185">Enter the port number.</span></span>
          1. <span data-ttu-id="fdfe8-186">Kattintson az Alkalmaz gombra.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-186">Click Apply.</span></span>
        
 2. <span data-ttu-id="fdfe8-187">**MDM**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-187">**MDM**</span></span> 
     1. <span data-ttu-id="fdfe8-188">Intune – Ezekkel a [lépésekkel konfigurálhatja](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) a proxyt az Intune-ban.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-188">Intune - Use these [steps](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="fdfe8-189">A szakasz aljára kell görgetnie.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-189">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="fdfe8-190">Egyéb, harmadik féltől származó MDM-megoldások – [Wi-Fi CSP használata.](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-190">Other 3rd party MDM solutions - Use a [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="fdfe8-191">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-191">**PPKG**</span></span> 
    1. <span data-ttu-id="fdfe8-192">A Windows Configuration Designer megnyitása</span><span class="sxs-lookup"><span data-stu-id="fdfe8-192">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="fdfe8-193">Kattintson a Speciális kiépítés elemre, adja meg az új projekt nevét, majd kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-193">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="fdfe8-194">Válassza a Windows Holographic (HoloLens 2) lehetőséget, majd kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-194">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="fdfe8-195">Importálja a PPKG-t (nem kötelező), majd kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-195">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="fdfe8-196">Bontsa ki a Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy (WLAN-proxy) gombra.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-196">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="fdfe8-197">Adja meg a hálózati Wi-Fi SSID-ját, majd kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-197">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="fdfe8-198">Válassza ki a Wi-Fi a bal oldali ablakban, és adja meg a kívánt testreszabásokat.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-198">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="fdfe8-199">Az engedélyezett testreszabások félkövérrel jelennek meg a bal oldali menüben.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-199">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="fdfe8-200">Kattintson a Mentés és kilépés gombra.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-200">Click Save and Exit.</span></span>
    1. <span data-ttu-id="fdfe8-201">[Alkalmazza a](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) kiépítési csomagot a HoloLensre.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-201">[Apply](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="fdfe8-202">[A felhőszolgáltatók](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) számos felügyeleti feladat és házirend mögött állnak a Windows 10, mind a Microsoft Intune, mind a nem Microsoft MDM-szolgáltatóknál.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-202">[CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="fdfe8-203">A Windows [Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) használatával is létrehozhat egy kiépítési csomagot, és alkalmazhatja azt [a](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) HoloLens 2-re.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-203">You can also use [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="fdfe8-204">A HoloLens 2-re leginkább a következő CSP-k lesznek alkalmazva:</span><span class="sxs-lookup"><span data-stu-id="fdfe8-204">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="fdfe8-205">[Wi-Fi CSP:](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)profilonkénti Wi-Fi proxy</span><span class="sxs-lookup"><span data-stu-id="fdfe8-205">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="fdfe8-206">A HoloLens-eszközökön támogatott egyéb CSP-k</span><span class="sxs-lookup"><span data-stu-id="fdfe8-206">Other CSPs supported in HoloLens devices</span></span>](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="fdfe8-207">VPN</span><span class="sxs-lookup"><span data-stu-id="fdfe8-207">VPN</span></span>
<span data-ttu-id="fdfe8-208">A VPN-kapcsolat biztonságosabb kapcsolatot és hozzáférést biztosít a vállalat hálózatához és az internethez.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-208">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="fdfe8-209">A HoloLens 2 támogatja a beépített VPN-ügyfelet és Univerzális Windows-platform (UWP) VPN beépülő modult.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-209">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="fdfe8-210">Támogatott beépített VPN-protokollok:</span><span class="sxs-lookup"><span data-stu-id="fdfe8-210">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="fdfe8-211">IKEv2</span><span class="sxs-lookup"><span data-stu-id="fdfe8-211">IKEv2</span></span>
- <span data-ttu-id="fdfe8-212">L2TP</span><span class="sxs-lookup"><span data-stu-id="fdfe8-212">L2TP</span></span>
- <span data-ttu-id="fdfe8-213">PPTP</span><span class="sxs-lookup"><span data-stu-id="fdfe8-213">PPTP</span></span>

<span data-ttu-id="fdfe8-214">Ha a beépített VPN-ügyfél hitelesítéséhez tanúsítványt használ, a szükséges ügyfél-tanúsítványt hozzá kell adni a felhasználói tanúsítványtárolóhoz.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-214">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="fdfe8-215">Annak ellenőrzéséhez, hogy egy harmadik féltől származó VPN beépülő modul támogatja-e a HoloLens 2-t, az Áruházban keresse meg a VPN-alkalmazást, és ellenőrizze, hogy a HoloLens támogatott eszközként szerepel-e, és a Rendszerkövetelmények oldalon az alkalmazás támogatja-e az ARM- vagy ARM64-architektúrát.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-215">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="fdfe8-216">A HoloLens csak a Univerzális Windows-platform VPN-hez támogatja az alkalmazásokat.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-216">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="fdfe8-217">A VPN-t MDM-en keresztül lehet kezelni [a Beállítások/AllowVPN segítségével,](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)és [a vpnv2-csp szabályzattal lehet beállítani.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-217">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="fdfe8-218">A VPN [konfigurálásról az alábbi](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) [útmutatókban olvashat bővebben.](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-218">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="fdfe8-219">VPN felhasználói felületen keresztül</span><span class="sxs-lookup"><span data-stu-id="fdfe8-219">VPN via UI</span></span>

<span data-ttu-id="fdfe8-220">A VPN alapértelmezés szerint nincs engedélyezve,  de manuálisan is engedélyezhető a Beállítások alkalmazás megnyitásával és a Network **& Internet -> VPN elemre navigálva.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-220">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="fdfe8-221">Válasszon ki egy VPN-szolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-221">Select a VPN provider.</span></span>
1. <span data-ttu-id="fdfe8-222">Hozzon létre egy kapcsolatnevet.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-222">Create a connection name.</span></span> 
1. <span data-ttu-id="fdfe8-223">Adja meg a kiszolgáló nevét vagy címét.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-223">Enter your server name or address.</span></span>
1. <span data-ttu-id="fdfe8-224">Válassza ki a VPN típusát.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-224">Select the VPN type.</span></span>
1. <span data-ttu-id="fdfe8-225">Válassza ki a bejelentkezési adatok típusát.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-225">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="fdfe8-226">Ha szükséges, adjon meg egy felhasználónevet és egy jelszót.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-226">Optionally add user name and password.</span></span>
1. <span data-ttu-id="fdfe8-227">Alkalmazza a VPN-beállításokat.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-227">Apply the VPN settings.</span></span> 

![HoloLens VPN-beállítások](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="fdfe8-229">VPN beállítása kiépítési csomagon keresztül</span><span class="sxs-lookup"><span data-stu-id="fdfe8-229">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="fdfe8-230">A Windows Holographic 20H2-es verziójában kijavítottunk egy proxykonfigurációs hibát a VPN-kapcsolathoz.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-230">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="fdfe8-231">Ha ezt a folyamatot szeretné használni, fontolja meg az eszközök frissítését erre a buildre.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-231">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="fdfe8-232">Indítsa el a Windows Configuration Designert.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-232">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="fdfe8-233">Kattintson **a Provision HoloLens devices (HoloLens-eszközök kiépítése)** elemre, majd válassza ki a céleszközt, és kattintson **a Next (Tovább) gombra.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-233">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="fdfe8-234">Adja meg a csomag nevét és elérési útját.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-234">Enter package name and path.</span></span>
1. <span data-ttu-id="fdfe8-235">Kattintson **a Váltás speciális szerkesztőre lehetőségre.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-235">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="fdfe8-236">Nyissa **meg a KapcsolatProfilok** VPN  ->    ->    ->  **VPN-beállításokat.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-236">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="fdfe8-237">A VPNProfileName konfigurálása</span><span class="sxs-lookup"><span data-stu-id="fdfe8-237">Configure VPNProfileName</span></span>
1. <span data-ttu-id="fdfe8-238">Válassza a ProfileType: **Natív vagy** **külső lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-238">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="fdfe8-239">A Natív profil beállításnál válassza a **NativeProtocolType** lehetőséget, majd konfigurálja a kiszolgálót, az útválasztási házirendet, a hitelesítési típust és az egyéb beállításokat.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-239">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="fdfe8-240">A "Külső gyártótól származó" profilhoz konfigurálja a kiszolgáló URL-címét, a VPN beépülő modul alkalmazáscsomagjának családnevét (csak 3 előre definiált) és egyéni konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-240">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="fdfe8-241">Exportálja a csomagot.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-241">Export your package.</span></span>
1. <span data-ttu-id="fdfe8-242">Csatlakoztassa a HoloLenst, és másolja a .ppkg fájlt az eszközre.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-242">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="fdfe8-243">A HoloLensen alkalmazza a VPN .ppkg-t a Start menü megnyitásával és a Beállítások fiókelérés munkahelyi vagy iskolai fiókjához Való hozzáférés Munkahelyi vagy iskolai fiók hozzáadása vagy eltávolítása -> VÁLASSZA ki a  ->    ->    ->   VPN-csomagot lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-243">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="fdfe8-244">VPN beállítása az Intune-on keresztül</span><span class="sxs-lookup"><span data-stu-id="fdfe8-244">Setting up VPN via Intune</span></span>
<span data-ttu-id="fdfe8-245">Az első lépésekhez kövesse az Intune-dokumentumokat.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-245">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="fdfe8-246">Ha követi ezeket a lépéseket, tartsa szem előtt a HoloLens-eszközök által támogatott beépített VPN-protokollokat.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-246">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="fdfe8-247">[VPN-profilok létrehozása VPN-kiszolgálókhoz való csatlakozáshoz az Intune-ban.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-247">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="fdfe8-248">[Windows 10 és Windows Holographic eszközbeállításokkal VPN-kapcsolatokat adhat hozzá az Intune-nal.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-248">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="fdfe8-249">Ha végzett, ne felejtse el [hozzárendelni a profilt.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-249">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="fdfe8-250">VPN külső MDM-megoldásokon keresztül</span><span class="sxs-lookup"><span data-stu-id="fdfe8-250">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="fdfe8-251">Példa külső VPN-kapcsolatra:</span><span class="sxs-lookup"><span data-stu-id="fdfe8-251">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="fdfe8-252">Példa natív IKEv2 VPN-re:</span><span class="sxs-lookup"><span data-stu-id="fdfe8-252">Native IKEv2 VPN example:</span></span>
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="fdfe8-253">A Wi-Fi letiltása a HoloLensben (1. generációs)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-253">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="fdfe8-254">A Settings alkalmazás használata a HoloLensben</span><span class="sxs-lookup"><span data-stu-id="fdfe8-254">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="fdfe8-255">Nyissa meg **a Start menüt.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-255">Open the **Start** menu.</span></span>
1. <span data-ttu-id="fdfe8-256">Válassza a **Beállítások** alkalmazást a **Start menüből** vagy a **Start** menü jobb oldalon található Minden alkalmazás **listából.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-256">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="fdfe8-257">A **Beállítások** alkalmazás automatikusan el lesz helyezve Ön előtt.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-257">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="fdfe8-258">Válassza **a Hálózati & lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-258">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="fdfe8-259">A csúszka Wi-Fi a csúszkakapcsolót a **Ki állásba való áthelyezéshez.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-259">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="fdfe8-260">Ezzel kikapcsolja az eszköz RF összetevőitWi-Fi és letiltja az összes Wi-Fi Funkciót a HoloLensen.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-260">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="fdfe8-261">Ha a Wi-Fi le van tiltva, a HoloLens nem fogja tudni automatikusan betölteni a [szóközöket.](hololens-spaces.md)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-261">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="fdfe8-262">Húzza a csúszkakapcsolót **a** Be állásba, hogy be tudja kapcsolni Wi-Fi választógombot, és visszaállítsa Wi-Fi funkcióját a Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-262">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="fdfe8-263">A kiválasztott Wi-Fi választógomb állapota (**Be** vagy **Ki**) megmarad az újraindítások között.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-263">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="fdfe8-264">HoloLens IP-címének azonosítása a Wi-Fi hálózaton</span><span class="sxs-lookup"><span data-stu-id="fdfe8-264">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="fdfe8-265">A Beállítások alkalmazás használatával</span><span class="sxs-lookup"><span data-stu-id="fdfe8-265">By using the Settings app</span></span>

1. <span data-ttu-id="fdfe8-266">Nyissa meg **a Start menüt.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-266">Open the **Start** menu.</span></span>
1. <span data-ttu-id="fdfe8-267">Válassza a **Beállítások** alkalmazást a **Start menüből** vagy a **Start** menü jobb oldalon található Minden alkalmazás **listából.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-267">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="fdfe8-268">A **Beállítások** alkalmazás automatikusan el lesz helyezve Ön előtt.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-268">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="fdfe8-269">Válassza **a Hálózati & lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-269">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="fdfe8-270">Görgessen le az elérhető hálózati Wi-Fi, és válassza a **Hardvertulajdonságok lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-270">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Hardvertulajdonságok a Wi-Fi beállításaiban](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="fdfe8-272">Az IP-cím a következő **IPv4-cím mellett jelenik meg:**.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-272">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="fdfe8-273">Hangparancsok használatával</span><span class="sxs-lookup"><span data-stu-id="fdfe8-273">By using voice commands</span></span>

<span data-ttu-id="fdfe8-274">Az eszközök felépítésétől függően beépített hangparancsokat vagy Cortanát is használhat az IP-cím megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-274">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="fdfe8-275">Az [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) utáni buildek a "Mi az IP-címem?"</span><span class="sxs-lookup"><span data-stu-id="fdfe8-275">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="fdfe8-276">és megjelenik.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-276">and it will be displayed.</span></span> <span data-ttu-id="fdfe8-277">A korábbi buildek vagy a HoloLens (1. generációs) számára a "Hé, Cortana, mi az IP-címem?"</span><span class="sxs-lookup"><span data-stu-id="fdfe8-277">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="fdfe8-278">És Cortana megjeleníti és kiolvassa az IP-címét.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-278">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="fdfe8-279">Az Windows eszközportál</span><span class="sxs-lookup"><span data-stu-id="fdfe8-279">By using Windows Device Portal</span></span>

1. <span data-ttu-id="fdfe8-280">A számítógépen egy webböngészőben nyissa meg az [eszközportálját.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-280">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="fdfe8-281">Lépjen a **Hálózat szakaszra.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-281">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="fdfe8-282">Ez a szakasz az IP-címet és egyéb hálózati információkat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-282">This section displays your IP address and other network information.</span></span> <span data-ttu-id="fdfe8-283">Ezzel a módszerrel másolhatja és beillesztheti az IP-címet a fejlesztői számítógépen.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-283">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="fdfe8-284">IP-cím statikus címre módosítása</span><span class="sxs-lookup"><span data-stu-id="fdfe8-284">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="fdfe8-285">A Beállítások használatával</span><span class="sxs-lookup"><span data-stu-id="fdfe8-285">By using Settings</span></span>
 
1. <span data-ttu-id="fdfe8-286">Nyissa meg **a Start menüt.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-286">Open the **Start** menu.</span></span>
1. <span data-ttu-id="fdfe8-287">Válassza a **Beállítások** alkalmazást a **Start menüből** vagy a **Start** menü jobb oldalon található Minden alkalmazás **listából.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-287">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="fdfe8-288">A **Beállítások** alkalmazás automatikusan el lesz helyezve Ön előtt.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-288">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="fdfe8-289">Válassza **a Hálózati & lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-289">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="fdfe8-290">Görgessen le az elérhető hálózati Wi-Fi, és válassza a **Hardvertulajdonságok lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-290">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="fdfe8-291">Az **IP-beállítások szerkesztése ablakban** módosítsa az első mezőt **Manuálisra.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-291">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="fdfe8-292">A többi mezőben adja meg a kívánt IP-konfigurációt, majd kattintson a **Mentés gombra.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-292">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="fdfe8-293">Az Windows eszközportál</span><span class="sxs-lookup"><span data-stu-id="fdfe8-293">By using Windows Device Portal</span></span>

1. <span data-ttu-id="fdfe8-294">A számítógépen egy webböngészőben nyissa meg az [eszközportálját.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="fdfe8-294">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="fdfe8-295">Lépjen a **Hálózat szakaszra.**</span><span class="sxs-lookup"><span data-stu-id="fdfe8-295">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="fdfe8-296">Válassza az **IPv4-konfiguráció** gombot.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-296">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="fdfe8-297">Válassza **a Következő IP-cím használata lehetőséget,** és adja meg a kívánt TCP/IP-konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-297">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="fdfe8-298">Válassza a Use the following DNS server addresses (A következő **DNS-kiszolgálócímek** használata) lehetőséget, és szükség esetén adja meg az előnyben részesített és másodlagos DNS-kiszolgálócímeket.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-298">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="fdfe8-299">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="fdfe8-299">Click **Save**.</span></span> 