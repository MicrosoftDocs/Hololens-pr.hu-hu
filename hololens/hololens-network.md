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
# <a name="connect-hololens-to-a-network"></a>A HoloLens csatlakoztatása hálózathoz

A HoloLensen a legtöbb dologhoz egy hálózathoz kell csatlakozva lennie. A HoloLens egy 802.11ac-kompatibilis, 2x2 Wi-Fi-választógombot tartalmaz, és ahhoz hasonlít, mintha egy Windows 10 Desktop- vagy mobileszközt csatlakoztat egy Wi-Fi-hálózathoz. Ez az útmutató a következőben segít:

- Csatlakozás hálózathoz Wi-Fi használatával, vagy csak a HoloLens 2 esetén közvetlen Wi-Fi Ethernet usb-C-kapcsolaton keresztül
- Az Wi-Fi

További információ a [HoloLens offline módban való használatával kapcsolatban.](hololens-offline.md)

## <a name="connecting-for-the-first-time"></a>Csatlakozás első alkalommal

Amikor először használja a HoloLenst, a rendszer végigvezeti egy Wi-Fi csatlakoztatásán. Ha a telepítés során problémába Wi-Fi, győződjön meg arról, hogy a hálózat egy nyílt, jelszóval védett hálózat vagy egy portálhálózat. Azt is ellenőrizze, hogy a hálózat nem igényel-e tanúsítványt a csatlakozáshoz. A beállítás után más típusú hálózati Wi-Fi is csatlakozhat.

HoloLens 2-eszközökön a felhasználók [USB-C–Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) adapterrel is csatlakozhatnak közvetlenül az Wi-Fi-hoz, hogy segítsenek az eszköz beállításában. Az eszköz beállítása után a felhasználó továbbra is használhatja az adaptert, vagy leválaszthatja az eszközt az adapterről, és a beállítás után csatlakozhat a [Wi-Fi-hez.](hololens-network.md#connecting-to-wi-fi-after-setup) 

## <a name="connecting-to-wi-fi-after-setup"></a>Csatlakozás Wi-Fi telepítés után

1. Formázhatja előre a **Start kézmozdulatot,** és válassza a **Beállítások lehetőséget.** A Beállítások alkalmazás automatikusan az Ön elé kerül.
1. Válassza **a Hálózati &**  >  **Wi-Fi lehetőséget.** Győződjön meg arról, hogy a Wi-Fi be van kapcsolva. Ha nem látja a hálózatot, görgessen lefelé a listán.
1. Válasszon ki egy hálózatot, majd válassza a **Csatlakozás lehetőséget.**
1. Ha a rendszer hálózati jelszót kér, írja be, majd válassza a Tovább **lehetőséget.**

![HoloLens-Wi-Fi beállításai](./images/hololens-2-wifi-settings.jpg)

Annak megerősítéséhez, hogy csatlakozott egy Wi-Fi hálózathoz, ellenőrizze a Wi-Fi állapotát a **Start menüben:**

1. Nyissa meg **a Start menüt.**
1. A Start menü bal felső **menüjében** keresse meg Wi-Fi állapotát. Megjelenik a Wi-Fi hálózat SSID-ének állapota.

> [!TIP]
> Ha Wi-Fi nem érhető el, mobilhálózati és [5G-hálózatokhoz is csatlakozhat.](https://docs.microsoft.com/hololens/hololens-cellular)

> [!IMPORTANT]
> A felhasználók a kialakításuk szerint nem tudják finomhangolni a HoloLens 2 Wi-Fi roaming viselkedését – az Wi-Fi-lista frissítésének egyetlen módja az Wi-Fi ki- és **bekapcsolása.** Ez számos problémát meggátol, például azt, hogy egy eszköz "elakadhat" egy AP-hez, ha a tartományon kívül van.

## <a name="troubleshooting-your-connection-to-wi-fi"></a>A hálózati kapcsolat hibaelhárítása Wi-Fi

Ha problémákat tapasztal a Wi-Fi-hez való csatlakozáskor, tekintse meg a Nem tudok csatlakozni a [Wi-Fi-hez való csatlakozást.](./hololens-faq.md#i-cant-connect-to-wi-fi)

Amikor vállalati vagy szervezeti fiókba jelentkezik be az eszközön, az a Mobile Eszközkezelés (MDM) szabályzatot is alkalmazhatja, ha a házirendet a rendszergazda konfigurálta.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>A HoloLens csatlakoztatása az Enterprise Wi-Fi Network szolgáltatáshoz

A Wi-Fi profiljai az EAP protokollt (Extensible Authentication Protocol) használják a Wi-Fi hitelesítéséhez. A HoloLens Enterprise Wi-Fi profil a Windows Configuration Designer által létrehozott MDM vagy kiépítési csomag [segítségével konfigurálható.](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)

A Microsoft Intune eszköz konfigurálási utasításait az [Intune-ban](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) használhatja.

Ha Wi-Fi csomagot a WCD-ben, egy előre konfigurált Wi-Fi profilra és .xml fájlra van szükség. Az EAP-TLSWi-Fi hitelesítéssel WPA2-Enterprise mintaprofil:

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


Az EAP típusától függően előfordulhat, hogy a kiszolgáló legfelső szintű hitelesítésszolgáltatói tanúsítványát és az ügyféltanúsítványt kell kiépítenünk az eszközön.

További források:

- WLANv1Profile séma: [[MS-GPWL]: Vezeték nélküli LAN-profil v1 séma | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS-séma: [[MS-GPWL]: Microsoft EAP TLS-séma | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

## <a name="eap-troubleshooting"></a>EAP-hibaelhárítás
> [!TIP]
> A hálózati problémák többségét az eredményezi, hogy az alábbi 3 beállítás valamelyike helytelen a Wi-FI-profilban. 
1. Ellenőrizze, Wi-Fi profil rendelkezik-e a megfelelő beállításokkal:
   1. Az EAP-típus megfelelően van konfigurálva, gyakori EAP-típusok: EAP-TLS (13), EAP-TTLS (21) és PEAP (25).
   1. Wi-Fi SSID neve helyes, és HEX-sztringre illeszkedik.
   1. EAP-TLS-hez a TrustedRootCA tartalmazza a megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványának&#39;SHA-1 kivonatát. Windows rendszerű számítógépekencertutil.exe -dump cert fájlnév parancs egy tanúsítványt fog&#39;&quot; \_ \_ &quot; SHA-1 kivonatsringhez.

2. Gyűjtse össze a hálózati csomagrögzítést a hozzáférési pont, a vezérlő vagy az AAA-kiszolgáló naplóiban, hogy megtudja, hol nem sikerül az EAP-munkamenet.
   1. Ha a HoloLens által biztosított EAP-identitás nem várható, ellenőrizze, hogy az identitás megfelelően lett-e Wi-Fi-profilon vagy ügyfél-tanúsítványon keresztül.
   1. Ha a kiszolgáló elutasítja a HoloLens-ügyfél tanúsítványát, ellenőrizze, hogy a szükséges ügyfél-tanúsítvány ki lett-e építve az eszközön.
   1. Ha a HoloLens elutasítja a kiszolgálótanúsítványt, ellenőrizze, hogy a kiszolgáló legfelső szintű hitelesítésszolgáltatói tanúsítványa ki lett-e építve a HoloLensen.
1. Ha a vállalati profil egy kiépítési Wi-Fi keresztül van kiépítve, fontolja meg a kiépítési csomag alkalmazását egy Windows 10 számítógépen. Ha a hiba a Windows 10 is sikertelen, kövesse a [Windows-ügyfél 802.1X hitelesítési hibaelhárítási útmutatóját.](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication)
1. Állítsa a telemetriát Teljes vagy Választható (a buildtől függően) beállításra, majd küldjön visszajelzést a [Visszajelzési központ.](https://docs.microsoft.com/hololens/hololens-feedback)

### <a name="additional-resources"></a>További források:
- [Wi-Fi beállítások exportálása windowsos eszközről](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="configure-network-proxy"></a>Hálózati proxy konfigurálása

Ez a szakasz a HoloLens operációs rendszer és a Windows HTTP-vermét használó Univerzális Windows-platform (UWP) alkalmazások hálózati proxyját tartalmazza. A nem Windows HTTP-vermeket használó alkalmazások saját proxykonfigurációval és -kezeléssel is használhatók. 

### <a name="proxy-configurations"></a>Proxykonfigurációk 

- Pac-proxy automatikus konfigurációs parancsfájl: a [PAC-fájl](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (amely nem Microsoft webhelyet nyit meg) tartalmaz egy FindProxyForURL(url, host) JavaScript-függvényt. 
- Statikus proxy: Kiszolgáló:Port alakban.  
- Webproxy automatikus felderítési protokollja (WPAD): ADJA meg a proxykonfigurációs fájl URL-címét DHCP-en vagy DNS-en keresztül. 

### <a name="proxy-provisioning-methods"></a>Proxy-kiépítési módszerek 
A proxyk kiépítése háromféleképpen lehetséges:

 

1.  **Beállítások felhasználói felülete:** 
    1. Felhasználónkénti proxy (20H2 vagy korábbi):
        1. Nyissa meg a Start menü, és válassza a Beállítások lehetőséget.
        2. Válassza a Network & internet, majd a proxy lehetőséget a bal oldali menüben.
        3. Görgessen le a Manual proxy setup (Manuális proxybeállítás) elemre, és a Use a proxy server (Proxykiszolgáló használata) beállítást pedig a On (Be) beállításra.
        4. Adja meg a proxykiszolgáló IP-címét.
        5. Adja meg a portszámot.
        6. Kattintson a Mentés gombra.
      1. Wi-Fi-proxy (21H1 vagy újabb):
          1. Nyissa meg Start menü, és nyissa meg Wi-Fi hálózat Tulajdonságok lapját.
          1. Görgessen le a Proxyhoz
          1. Módosítás manuális beállításra
          1. Adja meg a proxykiszolgáló IP-címét.
          1. Adja meg a portszámot.
          1. Kattintson az Alkalmaz gombra.
        
 2. **MDM** 
     1. Intune – Ezekkel a [lépésekkel konfigurálhatja](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) a proxyt az Intune-ban. A szakasz aljára kell görgetnie.
     1. Egyéb, harmadik féltől származó MDM-megoldások – [Wi-Fi CSP használata.](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)

3. **PPKG** 
    1. A Windows Configuration Designer megnyitása
    1. Kattintson a Speciális kiépítés elemre, adja meg az új projekt nevét, majd kattintson a Tovább gombra.
    1. Válassza a Windows Holographic (HoloLens 2) lehetőséget, majd kattintson a Tovább gombra.
    1. Importálja a PPKG-t (nem kötelező), majd kattintson a Befejezés gombra.
    1. Bontsa ki a Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy (WLAN-proxy) gombra.
    1. Adja meg a hálózati Wi-Fi SSID-ját, majd kattintson a Hozzáadás gombra.
    1. Válassza ki a Wi-Fi a bal oldali ablakban, és adja meg a kívánt testreszabásokat. Az engedélyezett testreszabások félkövérrel jelennek meg a bal oldali menüben.
    1. Kattintson a Mentés és kilépés gombra.
    1. [Alkalmazza a](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) kiépítési csomagot a HoloLensre.

[A felhőszolgáltatók](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) számos felügyeleti feladat és házirend mögött állnak a Windows 10, mind a Microsoft Intune, mind a nem Microsoft MDM-szolgáltatóknál. A Windows [Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) használatával is létrehozhat egy kiépítési csomagot, és alkalmazhatja azt [a](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) HoloLens 2-re.
A HoloLens 2-re leginkább a következő CSP-k lesznek alkalmazva:

- [Wi-Fi CSP:](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)profilonkénti Wi-Fi proxy 

[A HoloLens-eszközökön támogatott egyéb CSP-k](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
A VPN-kapcsolat biztonságosabb kapcsolatot és hozzáférést biztosít a vállalat hálózatához és az internethez. A HoloLens 2 támogatja a beépített VPN-ügyfelet és Univerzális Windows-platform (UWP) VPN beépülő modult. 

Támogatott beépített VPN-protokollok:
- IKEv2
- L2TP
- PPTP

Ha a beépített VPN-ügyfél hitelesítéséhez tanúsítványt használ, a szükséges ügyfél-tanúsítványt hozzá kell adni a felhasználói tanúsítványtárolóhoz. Annak ellenőrzéséhez, hogy egy harmadik féltől származó VPN beépülő modul támogatja-e a HoloLens 2-t, az Áruházban keresse meg a VPN-alkalmazást, és ellenőrizze, hogy a HoloLens támogatott eszközként szerepel-e, és a Rendszerkövetelmények oldalon az alkalmazás támogatja-e az ARM- vagy ARM64-architektúrát. A HoloLens csak a Univerzális Windows-platform VPN-hez támogatja az alkalmazásokat.

 A VPN-t MDM-en keresztül lehet kezelni [a Beállítások/AllowVPN segítségével,](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)és [a vpnv2-csp szabályzattal lehet beállítani.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)

A VPN [konfigurálásról az alábbi](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) [útmutatókban olvashat bővebben.](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)  

### <a name="vpn-via-ui"></a>VPN felhasználói felületen keresztül

A VPN alapértelmezés szerint nincs engedélyezve,  de manuálisan is engedélyezhető a Beállítások alkalmazás megnyitásával és a Network **& Internet -> VPN elemre navigálva.**
1. Válasszon ki egy VPN-szolgáltatót.
1. Hozzon létre egy kapcsolatnevet. 
1. Adja meg a kiszolgáló nevét vagy címét.
1. Válassza ki a VPN típusát.
1. Válassza ki a bejelentkezési adatok típusát. 
1. Ha szükséges, adjon meg egy felhasználónevet és egy jelszót.
1. Alkalmazza a VPN-beállításokat. 

![HoloLens VPN-beállítások](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>VPN beállítása kiépítési csomagon keresztül

> [!TIP] 
> A Windows Holographic 20H2-es verziójában kijavítottunk egy proxykonfigurációs hibát a VPN-kapcsolathoz. Ha ezt a folyamatot szeretné használni, fontolja meg az eszközök frissítését erre a buildre.

1. Indítsa el a Windows Configuration Designert.
1. Kattintson **a Provision HoloLens devices (HoloLens-eszközök kiépítése)** elemre, majd válassza ki a céleszközt, és kattintson **a Next (Tovább) gombra.**
1. Adja meg a csomag nevét és elérési útját.
1. Kattintson **a Váltás speciális szerkesztőre lehetőségre.**
1. Nyissa **meg a KapcsolatProfilok** VPN  ->    ->    ->  **VPN-beállításokat.**
1. A VPNProfileName konfigurálása
1. Válassza a ProfileType: **Natív vagy** **külső lehetőséget.**
    1. A Natív profil beállításnál válassza a **NativeProtocolType** lehetőséget, majd konfigurálja a kiszolgálót, az útválasztási házirendet, a hitelesítési típust és az egyéb beállításokat.
    1. A "Külső gyártótól származó" profilhoz konfigurálja a kiszolgáló URL-címét, a VPN beépülő modul alkalmazáscsomagjának családnevét (csak 3 előre definiált) és egyéni konfigurációkat.
1. Exportálja a csomagot.
1. Csatlakoztassa a HoloLenst, és másolja a .ppkg fájlt az eszközre. 
1. A HoloLensen alkalmazza a VPN .ppkg-t a Start menü megnyitásával és a Beállítások fiókelérés munkahelyi vagy iskolai fiókjához Való hozzáférés Munkahelyi vagy iskolai fiók hozzáadása vagy eltávolítása -> VÁLASSZA ki a  ->    ->    ->   VPN-csomagot lehetőséget.


### <a name="setting-up-vpn-via-intune"></a>VPN beállítása az Intune-on keresztül
Az első lépésekhez kövesse az Intune-dokumentumokat. Ha követi ezeket a lépéseket, tartsa szem előtt a HoloLens-eszközök által támogatott beépített VPN-protokollokat. 

[VPN-profilok létrehozása VPN-kiszolgálókhoz való csatlakozáshoz az Intune-ban.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)

[Windows 10 és Windows Holographic eszközbeállításokkal VPN-kapcsolatokat adhat hozzá az Intune-nal.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)

Ha végzett, ne felejtse el [hozzárendelni a profilt.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)

### <a name="vpn-via-3rd-party-mdm-solutions"></a>VPN külső MDM-megoldásokon keresztül
Példa külső VPN-kapcsolatra:
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

Példa natív IKEv2 VPN-re:
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>A Wi-Fi letiltása a HoloLensben (1. generációs)

### <a name="using-the-settings-app-on-hololens"></a>A Settings alkalmazás használata a HoloLensben

1. Nyissa meg **a Start menüt.**
1. Válassza a **Beállítások** alkalmazást a **Start menüből** vagy a **Start** menü jobb oldalon található Minden alkalmazás **listából.** A **Beállítások** alkalmazás automatikusan el lesz helyezve Ön előtt.
1. Válassza **a Hálózati & lehetőséget.**
1. A csúszka Wi-Fi a csúszkakapcsolót a **Ki állásba való áthelyezéshez.** Ezzel kikapcsolja az eszköz RF összetevőitWi-Fi és letiltja az összes Wi-Fi Funkciót a HoloLensen.

    > [!WARNING]
    > Ha a Wi-Fi le van tiltva, a HoloLens nem fogja tudni automatikusan betölteni a [szóközöket.](hololens-spaces.md)

1. Húzza a csúszkakapcsolót **a** Be állásba, hogy be tudja kapcsolni Wi-Fi választógombot, és visszaállítsa Wi-Fi funkcióját a Microsoft HoloLens. A kiválasztott Wi-Fi választógomb állapota (**Be** vagy **Ki**) megmarad az újraindítások között.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>HoloLens IP-címének azonosítása a Wi-Fi hálózaton

### <a name="by-using-the-settings-app"></a>A Beállítások alkalmazás használatával

1. Nyissa meg **a Start menüt.**
1. Válassza a **Beállítások** alkalmazást a **Start menüből** vagy a **Start** menü jobb oldalon található Minden alkalmazás **listából.** A **Beállítások** alkalmazás automatikusan el lesz helyezve Ön előtt.
1. Válassza **a Hálózati & lehetőséget.**
1. Görgessen le az elérhető hálózati Wi-Fi, és válassza a **Hardvertulajdonságok lehetőséget.**

    ![Hardvertulajdonságok a Wi-Fi beállításaiban](./images/wifi-hololens-hwdetails.jpg)

   Az IP-cím a következő **IPv4-cím mellett jelenik meg:**.

### <a name="by-using-voice-commands"></a>Hangparancsok használatával

Az eszközök felépítésétől függően beépített hangparancsokat vagy Cortanát is használhat az IP-cím megjelenítéséhez. Az [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) utáni buildek a "Mi az IP-címem?" és megjelenik. A korábbi buildek vagy a HoloLens (1. generációs) számára a "Hé, Cortana, mi az IP-címem?" És Cortana megjeleníti és kiolvassa az IP-címét.

### <a name="by-using-windows-device-portal"></a>Az Windows eszközportál

1. A számítógépen egy webböngészőben nyissa meg az [eszközportálját.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)
1. Lépjen a **Hálózat szakaszra.**  
   Ez a szakasz az IP-címet és egyéb hálózati információkat jeleníti meg. Ezzel a módszerrel másolhatja és beillesztheti az IP-címet a fejlesztői számítógépen.

## <a name="change-ip-address-to-static-address"></a>IP-cím statikus címre módosítása
### <a name="by-using-settings"></a>A Beállítások használatával
 
1. Nyissa meg **a Start menüt.**
1. Válassza a **Beállítások** alkalmazást a **Start menüből** vagy a **Start** menü jobb oldalon található Minden alkalmazás **listából.** A **Beállítások** alkalmazás automatikusan el lesz helyezve Ön előtt.
1. Válassza **a Hálózati & lehetőséget.**
1. Görgessen le az elérhető hálózati Wi-Fi, és válassza a **Hardvertulajdonságok lehetőséget.**
1. Az **IP-beállítások szerkesztése ablakban** módosítsa az első mezőt **Manuálisra.**
1. A többi mezőben adja meg a kívánt IP-konfigurációt, majd kattintson a **Mentés gombra.**

### <a name="by-using-windows-device-portal"></a>Az Windows eszközportál

1. A számítógépen egy webböngészőben nyissa meg az [eszközportálját.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)
1. Lépjen a **Hálózat szakaszra.**
1. Válassza az **IPv4-konfiguráció** gombot.
1. Válassza **a Következő IP-cím használata lehetőséget,** és adja meg a kívánt TCP/IP-konfigurációt.
1. Válassza a Use the following DNS server addresses (A következő **DNS-kiszolgálócímek** használata) lehetőséget, és szükség esetén adja meg az előnyben részesített és másodlagos DNS-kiszolgálócímeket.
1. Kattintson a **Mentés** gombra. 