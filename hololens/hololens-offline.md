---
title: Kapcsolati végpontok kezelése a HoloLens
description: Megtudhatja, hogyan állíthat be HoloLens hálózati kapcsolati Wi-Fi kapcsolati végpontok kezelése és konfigurálása közben.
keywords: hololens, offline, OOBE
audience: ITPro
ms.date: 07/01/2019
ms.assetid: b86f603c-d25f-409b-b055-4bbc6edcd301
author: Teresa-Motiv
ms.author: v-tea
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: jarrettr
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 63c82e5b1a953ee2f69bf4c22a8442c7bca07f073cc13f1e5e573fde0ccc1976
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662941"
---
# <a name="manage-connection-endpoints-for-hololens"></a>Kapcsolati végpontok kezelése a HoloLens

Egyes HoloLens összetevők, alkalmazások és kapcsolódó szolgáltatások microsoftos hálózati végpontokra továbbítják az adatokat. Ez a cikk felsorolja azokat a különböző végpontokat és URL-címeket, amelyek a hálózati konfigurációban (pl. proxy vagy tűzfal) engedélyezve lesznek az összetevők működőképességét.    

## <a name="near-offline-setup"></a>Közel offline telepítés

HoloLens kapcsolat nélküli élmény korlátozott készletét támogatja a hálózati környezet korlátozásokkal érintett ügyfelei számára. A HoloLens azonban hálózati kapcsolatra van szükség a kezdeti eszköz beállításához, és engedélyezni kell a következő URL-címeket:

| Rendeltetés | URL-cím |
|------|------|
| IDPS | https://sdx.microsoft.com/frx/idps |
| [NCSI](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| AAD PIN-kód | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| Msa | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| MSA Pin | https://account.live.com/msangc?fl=enroll |

## <a name="endpoint-configuration"></a>Végpont konfigurálása

A fenti lista mellett a hálózati konfigurációban a HoloLens a következő végpontokat kell engedélyezni.


| Rendeltetés | URL-cím |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |
|                                                     | ris-prod-atm.trafficmanager.net                                     |
|                                                     | validation-v2.sls.trafficmanager.net                                |
| Azure AD többtényezős hitelesítés                | https://secure.aadcdn.microsoftonline-p.com                         |
| Intune- és MDM-konfigurációk                       | activation-v2.sls.microsoft.com/*                                   |
|                                                     | cdn.onenote.net                                                     |
|                                                     | client.wns.windows.com                                              |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ctldl.windowsupdate.com                                             |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | dm3p.wns.windows.com                                                |
|                                                     | *microsoft.com/pkiops/*                                             |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | r.manage.microsoft.com                                              |
|                                                     | tile-service.weather.microsoft.com                                  |
|                                                     | settings-win.data.microsoft.com                                     |
| Tanúsítványok                                        | activation-v2.sls.microsoft.com/*                                   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | https://www.microsoft.com/pkiops/*                                          |
| Cortana és keresés                                  | store-images.*microsoft.com                                         |
|                                                     | www.bing.com/client                                                 |
|                                                     | www.bing.com                                                        |
|                                                     | www.bing.com/proactive                                              |
|                                                     | www.bing.com/threshold/xls.aspx                                     |
|                                                     | exo-ring.msedge.net                                                 |
|                                                     | fp.msedge.net                                                       |
|                                                     | fp-vp.azureedge.net                                                 |
|                                                     | odinvzc.azureedge.net                                               |
|                                                     | spo-ring.msedge.net                                                 |
| Eszközhitelesítés                               | login.live.com*                                                     |
| Eszköz metaadatai                                     | dmd.metaservices.microsoft.com                                      |
| Hely                                            | inference.location.live.net                                         |
|                                                     | location-inference-westus.cloudapp.net                              |
| Diagnosztikai adatok                                     | v10.events.data.microsoft.com                                       |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |
|                                                     | https://www.microsoft.com                                                   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |
|                                                     | cs11.wpc.v0cdn.net                                                  |
|                                                     | cs1137.wpc.gammacdn.net                                             |
|                                                     | modern.watson.data.microsoft.com*                                   |
|                                                     | watson.telemetry.microsoft.com                                      |
| Licencek                                           | licensing.mp.microsoft.com                                          |
| Microsoft-fiók                                   | login.msa.akadns6.net                                               |
|                                                     | us.configsvc1.live.com.akadns.net                                   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |
| Microsoft továbbítási hivatkozásátirányítási szolgáltatás (FWLink) | go.microsoft.com                                                    |
| Microsoft Store                                     | *.wns.windows.com                                                   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |
|                                                     | img-prod-cms-rt-microsoft-com*                                      |
|                                                     | store-images.microsoft.com                                          |
|                                                     | .md.mp.microsoft.com                                                |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | pti.store.microsoft.com                                             |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |
|                                                     | markets.books.microsoft.com                                         |
|                                                     | share.microsoft.com                                                 |
| Hálózati kapcsolat állapotjelzője (NCSI)          | www.msftconnecttest.com*                                            |
| Office                                              | *.c-msedge.net                                                      |
|                                                     | *.e-msedge.net                                                      |
|                                                     | *.s-msedge.net                                                      |
|                                                     | nexusrules.officeapps.live.com                                      |
|                                                     | ocos-office365-s2s.msedge.net                                       |
|                                                     | officeclient.microsoft.com                                          |
|                                                     | outlook.office365.com                                               |
|                                                     | client-office365-tas.msedge.net                                     |
|                                                     | https://www.office.com                                                      |
|                                                     | onecollector.cloudapp.aria                                          |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |
|                                                     | self.events.data.microsoft.com                                      |
|                                                     | to-do.microsoft.com                                                 |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |
|                                                     | msagfx.live.com                                                     |
|                                                     | oneclient.sfx.ms                                                    |
| Photos alkalmazás                                          | evoke-windowsservices-tas.msedge.net                                |
| Beállítások                                            | cy2.settings.data.microsoft.com.akadns.net                          |
|                                                     | settings.data.microsoft.com                                         |
|                                                     | settings-win.data.microsoft.com                                     |
| Windows Defender                                    | wdcp.microsoft.com                                                  |
|                                                     | definitionupdates.microsoft.com                                     |
|                                                     | go.microsoft.com                                                    |
|                                                     | *smartscreen.microsoft.com                                          |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |
|                                                     | unitedstates.smartscreen-prod.microsoft.com                         |
| Windows Reflektorfény                                   | *.search.msn.com                                                    |
|                                                     | arc.msn.com                                                         |
|                                                     | g.msn.com*                                                          |
|                                                     | query.prod.cms.rt.microsoft.com                                     |
|                                                     | ris.api.iris.microsoft.com                                          |
| Windows Update                                      | *.prod.do.dsp.mp.microsoft.com                                      |
|                                                     | cs9.wac.phicdn.net                                                  |
|                                                     | emdl.ws.microsoft.com                                               |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |
|                                                     | *.windowsupdate.com                                                 |
|                                                     | *.delivery.mp.microsoft.com                                         |
|                                                     | *.update.microsoft.com                                              |



## <a name="references"></a>Hivatkozások

> [!NOTE]
> Ha a D365 Remote Assistet telepíti, engedélyeznie kell a SharePoint Online és OneDrive Vállalati verzió listában felsorolt végpontokat a Office 365 URL-címek és [IP-címtartományok](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)között.

- [Diagnosztikai Windows konfigurálása a szervezetben](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Kapcsolati végpontok kezelése a Windows 10 Enterprise, 1903-as verzió](/windows/privacy/manage-windows-1903-endpoints)
- [Az operációs rendszer Windows 10 és az operációs rendszerek közötti kapcsolatok Microsoft-szolgáltatások](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [Az operációsrendszer Windows 10 összetevők és a Microsoft-szolgáltatások közötti kapcsolatok Microsoft Intune MDM-Microsoft Intune kezelése](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Az Intune hálózati konfigurációs követelményei és sávszélessége](/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Hálózati végpontok Microsoft Intune](/intune/fundamentals/intune-endpoints)
- [Office 365 URL-címek és IP-címtartományok](/office365/enterprise/urls-and-ip-address-ranges)
- [Az Azure AD Connect előfeltételei](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## <a name="hololens-limitations"></a>HoloLens korlátozások

A HoloLens beállítását követően Wi-Fi kapcsolat nélkül is használhatja, de az internetkapcsolatot használó alkalmazások korlátozott képességekkel rendelkeznek, ha offline HoloLens használ.
