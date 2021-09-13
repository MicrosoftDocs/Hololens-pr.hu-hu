---
title: HoloLens kioszkra vonatkozó referenciainformációk
description: Információk és minták a kioszkeszközökről HoloLens eszközökön.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032567"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens Kioszk referenciainformációk

Ez az oldal hasznos információkat tartalmaz a HoloLens eszköz kioszkmódja beállításával kapcsolatban. A hivatkozások között találhatók a beérkezett üzenetekhez és a saját alkalmazásokhoz használható AUMID-k, valamint a Kioszk módhoz használható XML-minták, amelyek csupán néhány módosításra vannak attól, hogy készen állnak a használatra számos különböző forgatókönyvhöz. A kioszk beállításával kapcsolatos információkért olvassa el [a Kioszk](hololens-kiosk.md) beállítása oldalt.

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens Alkalmazásfelhasználói modell azonosítói (AUMID-k)  

A kioszkalkalmazások kiválasztásával kapcsolatos általános információkért lásd: [Guidelines for choose an app for assigned access (kioszkmód)](/windows/configuration/guidelines-for-assigned-access-app).

Ha Mobile Eszközkezelés (MDM) vagy kiépítési csomag használatával konfigurálja a kioszkmódot, az [AssignedAccess configuration Service Provider (CSP)](/windows/client-management/mdm/assignedaccess-csp) segítségével adhatja meg az alkalmazásokat. A CSP [alkalmazásfelhasználói modellben használt azonosítókat (AUMID) használ](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) az alkalmazások azonosításához. Az alábbi táblázat néhány, többalkalmazásos kioszkban használható, használatra használt alkalmazás AUMID-ját sorolja fel.

<a id="aumids"></a>

|Alkalmazásnév |AUMID (AUMID) |
| --- | --- |
|3D-megjelenítő |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Naptár |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|<sup>1., 2. kamera</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3.</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! alkalmazás |
|Eszközválasztó a HoloLens (1. generációs) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Eszközválasztó a 2. HoloLens oldalon |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Dynamics 365-útmutatók |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|Visszajelzési &nbsp; központ |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! App |
|Fájlkezelő |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Régi Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Új Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4.</sup> | &nbsp; |
|Filmek & TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! Alkalmazás |
|Fotók |Microsoft. Windows. Photos \_ 8wekyb3d8bbwe \! App |
|Régi Gépház |HolographicSystemSettings_cw5n1h2txyewy! App |
|Új Gépház |BAEAEF15-9CAF-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Tippek |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> A fénykép- vagy videórögzítés engedélyezéséhez kioszkalkalmazásként engedélyeznie kell a Kamera alkalmazást.  
> <sup>2</sup> A Kamera alkalmazás engedélyezésekor vegye figyelembe a következő feltételeket:
> - A Gyorsműveletek menüben található a Fénykép és a Videó gomb.
> - Emellett engedélyeznie kell egy olyan alkalmazást (például Fényképek, Mail vagy OneDrive), amely képes képeket használni vagy lekérni.  
>  
> <sup>3</sup> Még ha nem is engedélyezi a Cortana kioszkalkalmazásként, a beépített hangparancsok is engedélyezve vannak. A letiltott funkciókhoz kapcsolódó parancsok azonban hatás nélkül használhatók.  
> <sup>4</sup> Közvetlenül nem engedélyezhető Miracast engedélyezése. A kioszkalkalmazásként való Miracast engedélyezéséhez engedélyezze a Kamera alkalmazást és az Eszközválasztó alkalmazást.

Emellett a Mixed Reality kezdőlapja nem beállítható kioszkalkalmazásként.

Térjen vissza [a Támogatott forgatókönyvek kioszkmódhoz identitástípus alapján](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>Kioszk XML-kódminták

1. [Több alkalmazás globális hozzárendelt hozzáférési profilja](#multiple-app-global-assigned-access-profile)
1. [Több alkalmazás globális hozzárendelt hozzáférési profilja az eszköztulajdonosok kivételével](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [Több alkalmazáshoz rendelt hozzáférési profil egy helyi fiókhoz vagy AAD-felhasználói fiókhoz](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [Több alkalmazáshoz rendelt hozzáférési profil két vagy több AAD-felhasználóhoz](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [Több alkalmazáshoz rendelt hozzáférési profil egy AAD-csoporthoz](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [Több alkalmazáshoz rendelt hozzáférési profil két vagy több AAD-csoporthoz](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [Több alkalmazáshoz rendelt hozzáférési profil egy AAD-fiókhoz és egy AAD-csoporthoz](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [Több alkalmazáshoz rendelt hozzáférési profil a látogatók számára](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> Cserélje le a TODO műveleteket a követelményeknek megfelelően.

### <a name="multiple-app-global-assigned-access-profile"></a>Több alkalmazás globális hozzárendelt hozzáférési profilja

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[Vissza a listához](#kiosk-xml-code-samples) <br>
Térjen vissza [a Támogatott forgatókönyvek kioszkmódhoz identitástípus alapján](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>Több alkalmazás globális hozzárendelt hozzáférési profilja az eszköztulajdonosok kivételével

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[Vissza a listához](#kiosk-xml-code-samples) <br>
Térjen vissza [a Támogatott forgatókönyvek kioszkmódhoz identitástípus alapján](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>Több alkalmazáshoz rendelt hozzáférési profil egy helyi fiókhoz vagy AAD-felhasználói fiókhoz

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[Vissza a listához](#kiosk-xml-code-samples) <br>
Térjen vissza [a Támogatott forgatókönyvek kioszkmódhoz identitástípus alapján](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>Több alkalmazáshoz rendelt hozzáférési profil két vagy több AAD-felhasználóhoz

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[Vissza a listához](#kiosk-xml-code-samples) <br>
Térjen vissza [a Támogatott forgatókönyvek kioszkmódhoz identitástípus alapján](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>Több alkalmazáshoz rendelt hozzáférési profil egy AAD-csoporthoz

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[Vissza a listához](#kiosk-xml-code-samples) <br>
Térjen vissza [a Támogatott forgatókönyvek kioszkmódhoz identitástípus alapján](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>Több alkalmazáshoz rendelt hozzáférési profil két vagy több AAD-csoporthoz

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[Vissza a listához](#kiosk-xml-code-samples) <br>
Térjen vissza [a Támogatott forgatókönyvek kioszkmódhoz identitástípus alapján](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>Több alkalmazáshoz rendelt hozzáférési profil egy AAD-fiókhoz és egy AAD-csoporthoz

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[Vissza a listához](#kiosk-xml-code-samples) <br>
Térjen vissza [a Támogatott forgatókönyvek kioszkmódhoz identitástípus alapján](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>Több alkalmazáshoz rendelt hozzáférési profil a látogatók számára

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[Vissza a listához](#kiosk-xml-code-samples) <br>
Térjen vissza [a Támogatott forgatókönyvek kioszkmódhoz identitástípus alapján](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)
