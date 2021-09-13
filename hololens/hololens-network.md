---
title: Csatlakozás HoloLens hálózatra
description: Megtudhatja, hogyan lehet beállítani az internetet, és csatlakozni az internethez HoloLens és az eszköz IP-címének azonosítását.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wi-fi, vezeték nélküli, internet, ip, IP-cím
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: fe1c47de48e413a6f45921ba1e247016873ca996
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036192"
---
# <a name="connect-hololens-to-a-network"></a>Csatlakozás HoloLens hálózatra

Ha a legtöbb dolgot el HoloLens, egy hálózathoz kell csatlakoztatnia. HoloLens egy 802.11ac-kompatibilis, 2x2 Wi-Fi-választógombot tartalmaz, és ahhoz hasonlóan csatlakoztatja azt egy hálózathoz, mint egy Windows 10 Desktop- vagy mobileszközt egy Wi-Fi-hálózathoz. Ez az útmutató a következőben segít:

- Csatlakozás Wi-Fi-t használó hálózathoz, vagy csak HoloLens 2- Wi-Fi Usb-C-n keresztüli közvetlen vagy Ethernet-kapcsolathoz
- Az Wi-Fi

További információ az [offline HoloLens való használatról.](hololens-offline.md)

## <a name="connecting-for-the-first-time"></a>Csatlakozás első alkalommal

Amikor először használja a HoloLens, a rendszer végigvezeti a hálózati Wi-Fi lépésen. Ha a telepítés során problémába Wi-Fi, győződjön meg arról, hogy a hálózat egy nyílt, jelszóval védett hálózat vagy egy portálhálózat. Győződjön meg arról is, hogy a hálózat nem követeli meg tanúsítvány használatát a csatlakozáshoz. A beállítás után más típusú virtuális hálózatokhoz is Wi-Fi csatlakozhat.

Két HoloLens eszközön a felhasználók [USB-C–Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) adapterrel is csatlakozhatnak közvetlenül az Wi-Fi-hoz, hogy segítsenek az eszköz beállításában. Az eszköz beállítása után a felhasználó továbbra is használhatja az adaptert, vagy leválaszthatja az eszközt az adapterről, és a beállítás után csatlakozhat a [Wi-Fi-hez.](hololens-network.md#connecting-to-wi-fi-after-setup) 

## <a name="connecting-to-wi-fi-after-setup"></a>Csatlakozás Wi-Fi után

1. Formázsa előre a **Start kézmozdulatot,** és válassza **a Gépház.** A Gépház alkalmazás automatikusan el lesz helyezve Az Ön előtt.
1. Válassza **a Hálózati &**  >  **Wi-Fi lehetőséget.** Győződjön meg arról, hogy a Wi-Fi be van kapcsolva. Ha nem látja a hálózatot, görgessen lefelé a listán.
1. Válasszon ki egy hálózatot, majd válassza a **Csatlakozás.**
1. Ha a rendszer hálózati jelszót kér, írja be, majd válassza a **Tovább lehetőséget.**

![HoloLens Wi-Fi beállításokat.](./images/hololens-2-wifi-settings.jpg)

Annak megerősítéséhez, hogy csatlakozott egy Wi-Fi hálózathoz, ellenőrizze a Wi-Fi állapotát a **Start menüben:**

1. Nyissa meg **a Start menüt.**
1. A Start menü bal felső **részen** keresse meg a Wi-Fi állapotát. Megjelenik a Wi-Fi hálózat SSID-ének állapota.

> [!TIP]
> Ha Wi-Fi nem érhető el, mobilhálózati és [5G-hálózatokhoz is csatlakozhat.](hololens-cellular.md)

> [!IMPORTANT]
> A felhasználók a HoloLens 2 központi Wi-Fi viselkedését úgy tudják finomhangolni, hogy az Wi-Fi-lista frissítésének egyetlen módja az Wi-Fi ki- és **bekapcsolása.** Ez számos problémát meggátol, például azt, hogy egy eszköz "elakadhat" egy AP-hez, ha az a tartományon kívül esik.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Csatlakozás HoloLens enterprise Wi-Fi Networkre

A Wi-Fi profilok az EAP protokollt (Extensible Authentication Protocol) használják a Wi-Fi hitelesítéséhez. HoloLens A vállalati Wi-Fi profil A Configuration Designer által létrehozott MDM- vagy [kiépítési csomaggal Windows konfigurálható.](/windows/configuration/provisioning-packages/provisioning-packages)

A Microsoft Intune eszközről a konfigurációs [utasításokért tekintse](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) meg az Intune-t.

Ha Wi-Fi kiépítési csomagot a WCD-ben, egy előre konfigurált Wi-Fi profilra és .xml fájlra van szükség. Itt egy EAP-TLSWi-Fi hitelesítést WPA2-Enterprise profilminta:

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


Az EAP-típustól függően előfordulhat, hogy a kiszolgáló legfelső szintű hitelesítésszolgáltatói tanúsítványát és az ügyféltanúsítványt ki kell kiépítenünk az eszközön.

További források:

- WLANv1Profile séma: [[MS-GPWL]: Vezeték nélküli LAN-profil v1 séma | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS-séma: [[MS-GPWL]: Microsoft EAP TLS-séma | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

Ha problémái [vannak](hololens2-enterprise-troubleshooting.md#) a Wi-Fi-hez való csatlakozással, tekintse meg a hibaelhárítási oldalt.

## <a name="configure-network-proxy"></a>Hálózati proxy konfigurálása

Ez a szakasz a http HoloLens címet használó Windows és univerzális Windows platform- (UWP-) alkalmazások Windows hálózati proxyját tartalmazza. A nem Windows HTTP-vermet használó alkalmazások saját proxykonfigurációval és -kezeléssel is használhatók. 

### <a name="proxy-configurations"></a>Proxykonfigurációk 

- Proxy auto-config (PAC) szkript: a [PAC-fájl](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (egy nem Microsoft-webhelyet nyit meg) tartalmaz egy FindProxyForURL(url, host) JavaScript-függvényt. 
- Statikus proxy: Kiszolgáló:Port formában.  
- Webproxy automatikus felderítési protokollja (WPAD): adja meg a proxykonfigurációs fájl URL-címét DHCP-en vagy DNS-en keresztül. 

### <a name="proxy-provisioning-methods"></a>Proxy-kiépítési módszerek 
A proxyk üzembe építésének három módja van:

 

1.  **Gépház UI:** 
    1. Felhasználónkénti proxy (20H2 vagy korábbi):
        1. Nyissa meg a Start menü, és válassza a Gépház.
        2. Válassza a Network & internet, majd a proxy lehetőséget a bal oldali menüben.
        3. Görgessen le a Manual proxy setup (Manuális proxybeállítás) elemre, és a Use a proxy server (Proxykiszolgáló használata) kapcsolót a On (Be) beállításra.
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
     1. Intune – Ezekkel a [lépésekkel konfigurálhatja](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) a proxyt az Intune-ban. A szakasz aljára kell görgetnie.
     1. Egyéb külső MDM-megoldások – [Wi-Fi CSP használata.](/windows/client-management/mdm/wifi-csp)

3. **PPKG** 
    1. A Windows Configuration Designer megnyitása
    1. Kattintson a Speciális kiépítés elemre, adja meg az új Project majd kattintson a Tovább gombra.
    1. Válassza Windows Holographic (HoloLens 2) lehetőséget, majd kattintson a Tovább gombra.
    1. Importálja a PPKG-t (nem kötelező), majd kattintson a Befejezés gombra.
    1. Bontsa ki a Runtime Gépház -> Connectivity Profiles -> WLAN -> WLAN Proxy (WLAN-kapcsolati profilok -> WLAN-proxy) lehetőséget.
    1. Adja meg a hálózati Wi-Fi SSID-ját, majd kattintson a Hozzáadás gombra.
    1. Válassza ki a Wi-Fi a bal oldali ablakban, és adja meg a kívánt testreszabásokat. Az engedélyezett testreszabások félkövérrel jelennek meg a bal oldali menüben.
    1. Kattintson a Mentés és kilépés gombra.
    1. [Alkalmazza a](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) kiépítési csomagot a HoloLens.

[A csP-k](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) számos felügyeleti feladat és házirend mögött állnak a Windows 10, mind a Microsoft Intune, mind a nem Microsoft MDM-szolgáltatóknál. A Configuration [Designer Windows](/windows/configuration/provisioning-packages/provisioning-install-icd) is használhatja [egy](/windows/configuration/provisioning-packages/provisioning-packages) kiépítési csomag létrehozásához és a 2. HoloLens alkalmazáshoz.
A 2. HoloLens következő CSP-k lesznek alkalmazva:

- [Wi-Fi CSP:](/windows/client-management/mdm/wifi-csp)profilonkénti Wi-Fi proxy 

[Az egyéb támogatott CSP-k a HoloLens támogatottak](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
A VPN-kapcsolat biztonságosabb kapcsolatot és hozzáférést biztosít a vállalat hálózatához és az internethez. HoloLens 2. modul támogatja a beépített VPN-ügyfelet és a Universal Windows Platform (UWP) VPN beépülő modult. 

Támogatott beépített VPN-protokollok:
- IKEv2
- L2TP
- PPTP

Ha tanúsítványt használ a beépített VPN-ügyfél hitelesítéséhez, a szükséges ügyfél-tanúsítványt hozzá kell adni a felhasználói tanúsítványtárolóhoz. Annak ellenőrzéséhez, hogy egy harmadik féltől származó VPN beépülő modul támogatja-e a HoloLens 2- es verzió működését, az Áruházban keresse meg a VPN-alkalmazást, és ellenőrizze, hogy a HoloLens támogatott eszközként szerepel-e, és a Rendszerkövetelmények lapon az alkalmazás támogatja-e az ARM- vagy ARM64-architektúrát. HoloLens a Universal Windows Platform alkalmazásokat támogatja külső VPN-hez.

 A VPN-t MDM-en keresztül lehet [kezelni Gépház/AllowVPN-en](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)keresztül, és [vpnv2-csp szabályzattal lehet beállítani.](/windows/client-management/mdm/vpnv2-csp)

A VPN [konfigurálásával kapcsolatos további információkért](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) olvassa [el ezeket az útmutatókat.](/windows/security/identity-protection/vpn/vpn-guide)  

### <a name="vpn-via-ui"></a>VPN felhasználói felületen keresztül

A VPN alapértelmezés szerint nincs engedélyezve, de manuálisan engedélyezhető egy alkalmazás megnyitásával és **Gépház** **Network & Internet -> VPN -hez.**
1. Válasszon ki egy VPN-szolgáltatót.
1. Hozzon létre egy kapcsolatnevet. 
1. Adja meg a kiszolgáló nevét vagy címét.
1. Válassza ki a VPN típusát.
1. Válassza ki a bejelentkezési adatok típusát. 
1. Ha szükséges, adjon meg egy felhasználónevet és egy jelszót.
1. Alkalmazza a VPN-beállításokat. 

![HoloLens VPN-beállítások.](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>VPN beállítása kiépítési csomagon keresztül

> [!TIP] 
> A holografikus Windows 20H2 verzióban kijavítottunk egy proxykonfigurációs hibát a VPN-kapcsolathoz. Ha ezt a folyamatot szeretné használni, fontolja meg az eszközök frissítését erre a buildre.

1. Indítsa el Windows Configuration Designert.
1. Kattintson **a Provision HoloLens devices**(Eszközök kiépítése) elemre, majd válassza ki a céleszközt, és kattintson a Next **(Tovább) gombra.**
1. Adja meg a csomag nevét és elérési útját.
1. Kattintson **a Váltás speciális szerkesztőre lehetőségre.**
1. Nyissa **meg a Runtime settings**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings (Futtatás** futásidejű beállításai) Beállítást.
1. A VPNProfileName konfigurálása
1. Válassza a ProfileType: **Native (Natív) vagy** **a Third Party (Harmadik fél) lehetőséget.**
    1. A Natív profil beállításnál válassza a **NativeProtocolType** lehetőséget, majd konfigurálja a kiszolgálót, az útválasztási házirendet, a hitelesítési típust és az egyéb beállításokat.
    1. A "Külső gyártótól származó" profilhoz konfigurálja a kiszolgáló URL-címét, a VPN beépülő modul alkalmazáscsomagjának családnevét (csak 3 előre definiált) és egyéni konfigurációkat.
1. Exportálja a csomagot.
1. Csatlakozás a HoloLens, és másolja a .ppkg fájlt az eszközre. 
1. A HoloLens vpn .ppkg fájlban a Start menü megnyitásával és Gépház Munkahelyi vagy iskolai fiókelérési csomag hozzáadása vagy eltávolítása -> VÁLASSZA ki **a**  ->    ->    ->   VPN-csomagot lehetőséget.


### <a name="setting-up-vpn-via-intune"></a>VPN beállítása az Intune-on keresztül
Az első lépésekhez kövesse az Intune-dokumentumokat. A lépések lépéseikor tartsa szem előtt az eszközök által támogatott beépített VPN HoloLens protokollokat. 

[VPN-profilok létrehozása VPN-kiszolgálókhoz való csatlakozáshoz az Intune-ban.](/mem/intune/configuration/vpn-settings-configure)

[Windows 10 és Windows Holographic eszközbeállításokkal VPN-kapcsolatokat adhat hozzá az Intune használatával.](/mem/intune/configuration/vpn-settings-windows-10)

Ha végzett, ne felejtse el [hozzárendelni a profilt.](/mem/intune/configuration/device-profile-assign)

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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>A Wi-Fi letiltása HoloLens (1. generációs)

### <a name="using-the-settings-app-on-hololens"></a>A Gépház alkalmazás használata a HoloLens

1. Nyissa meg **a Start menüt.**
1. Válassza ki **Gépház** alkalmazást a **Start** menüből vagy a **Start** menü jobb oldalon található Minden alkalmazás **listájából.** A **Gépház** alkalmazás automatikusan el lesz helyezve Az Ön előtt.
1. Válassza **a Hálózati & lehetőséget.**
1. A csúszka Wi-Fi a csúszkakapcsolót a Ki **állásba való áthelyezéshez.** Ezzel kikapcsolja az eszköz RF összetevőitWi-Fi és letiltja az összes Wi-Fi funkciót a HoloLens.

    > [!WARNING]
    > Ha a Wi-Fi választógomb le van tiltva, HoloLens nem tudja automatikusan betölteni a [szóközöket.](hololens-spaces.md)

1. Húzza a csúszkakapcsolót **a** Be állásba, hogy be tudja kapcsolni a Wi-Fi választógombot, és visszaállítsa Wi-Fi funkcióját a Microsoft HoloLens. A kiválasztott Wi-Fi választógomb állapota (**Be** vagy **Ki**) megmarad az újraindítások között.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>A hálózati HoloLens IP-címének Wi-Fi azonosítása

### <a name="by-using-the-settings-app"></a>A Gépház alkalmazással

1. Nyissa meg **a Start menüt.**
1. Válassza ki **Gépház** alkalmazást a **Start** menüből vagy a **Start** menü jobb oldalon található Minden alkalmazás **listájából.** A **Gépház** alkalmazás automatikusan el lesz helyezve Az Ön előtt.
1. Válassza **a Hálózati & lehetőséget.**
1. Görgessen le az elérhető hálózati Wi-Fi, és válassza a **Hardvertulajdonságok lehetőséget.**

    ![A hardvertulajdonságok a Wi-Fi beállításaiban.](./images/wifi-hololens-hwdetails.jpg)

   Az IP-cím a következő **IPv4-cím mellett jelenik meg:**.

### <a name="by-using-voice-commands"></a>Hangparancsok használatával

Az eszközök felépítésétől függően használhatja a beépített hangparancsokat, vagy Cortana az IP-cím megjelenítéséhez. Az [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) utáni buildek a "Mi az IP-címem?" és megjelenik. Korábbi buildek vagy HoloLens (1. generációs) kérdésre: "Hey Cortana, What's my IP address?" A Cortana megjelenik és kiolvassa az IP-címét.

### <a name="by-using-windows-device-portal"></a>Az Windows Eszközportál

1. A számítógépen egy webböngészőben nyissa meg az [eszközportálját.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)
1. Lépjen a **Hálózat szakaszra.**  
   Ez a szakasz az IP-címet és egyéb hálózati információkat jeleníti meg. Ezzel a módszerrel másolhatja és beillesztheti az IP-címet a fejlesztői számítógépen.

## <a name="change-ip-address-to-static-address"></a>IP-cím statikus címre módosítása
### <a name="by-using-settings"></a>Az Gépház
 
1. Nyissa meg **a Start menüt.**
1. Válassza ki **Gépház** alkalmazást a **Start** menüből vagy a **Start** menü jobb oldalon található Minden alkalmazás **listájából.** A **Gépház** alkalmazás automatikusan el lesz helyezve Az Ön előtt.
1. Válassza **a Hálózati & lehetőséget.**
1. Görgessen le az elérhető hálózati Wi-Fi, és válassza a **Hardvertulajdonságok lehetőséget.**
1. Az **IP-beállítások szerkesztése ablakban** módosítsa az első mezőt **Manuálisra.**
1. A többi mezőben adja meg a kívánt IP-konfigurációt, majd kattintson a **Mentés gombra.**

### <a name="by-using-windows-device-portal"></a>Az Windows Eszközportál

1. A számítógépen egy webböngészőben nyissa meg az [eszközportálját.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)
1. Lépjen a **Hálózat szakaszra.**
1. Válassza az **IPv4-konfiguráció gombot.**
1. Válassza **a Következő IP-cím használata lehetőséget,** és adja meg a kívánt TCP/IP-konfigurációt.
1. Válassza a Use the following DNS server addresses (A következő **DNS-kiszolgálócímek** használata) lehetőséget, és szükség esetén adja meg az előnyben részesített és másodlagos DNS-kiszolgálócímeket.
1. Kattintson a **Mentés** gombra. 
