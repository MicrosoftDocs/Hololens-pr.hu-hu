---
title: HoloLens 2 Megfelelőség és GDPR
description: A GDPR dokumentációja
keywords: HoloLens, GDPR, adatvédelem, PII
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b795513d83c9d23f70b8dd8365e703d1fc43a51
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378194"
---
# <a name="hololens-2-privacy-statement"></a>HoloLens 2 adatvédelmi nyilatkozat

A GDPR egyik alapvető eleme az "adatvédelem terv szerint". Ez a fogalom különösen a mobileszközökre, például a HoloLens 2-re vonatkozik a hordozhatóság, a korlátlan internetkapcsolat és a nyílt kommunikációs csatornák miatt. Ennek eredményeképpen a HoloLens 2 biztonsága úgy lett újratervezve, hogy fejlett, innovatív biztonsági és adatvédelmi védelmet nyújtson teljes a Microsoft adatvédelmi és [GDPR-szabályozásaiba](https://privacy.microsoft.com/)is. [](https://docs.microsoft.com/hololens/security-architecture)

 >[!NOTE]
> Ez a dokumentum nem vonatkozik a HoloLensre (1. generációs).

## <a name="privacy-overview"></a>Adatvédelem áttekintése

A HoloLens 2 egy windowsos önálló számítógép, amely Windows Holographic rendszert futtat, és modern vegyes valóságú környezetben futtat alkalmazásokat és megoldásokat. Használható biztonságos offline eszközként, vagy telepíthető felügyelt [eszközként](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) a szervezeten belül. Az alábbi hivatkozásokon keresztül értheti meg, hogyan használja és védi a HoloLens 2 és a Microsoft az adatokat:
1. [Microsoft adatvédelmi nyilatkozat – HoloLens – bontsa](https://privacy.microsoft.com/privacystatement) ki a vállalati és fejlesztői szakaszt a bal oldali navigációs menüben, és válassza a Vállalati és **fejlesztői szoftverek és berendezések lehetőséget.**  Ugrás a **HoloLens szakaszra.**
2.  [Windows 10 és a online szolgáltatások](https://privacy.microsoft.com/windows10privacy)
3.  [Windows 10 & adatvédelmi megfelelőségi útmutató](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Adatvédelem és személyes adatok az Intune-ban](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Hálózati biztonság
A HoloLens [2](https://docs.microsoft.com/hololens/common-scenarios)gyakori üzembe helyezési forgatókönyvei alapján az [adatokat](https://docs.microsoft.com/azure/compliance/) az Azure világosztályú megfelelősége, valamint a jogi/szabályozási szabványok integrációja védi. Ha még csak most használja az Azure AD-t és a Dynamics 365 Remote Assistet, tekintse meg az Azure és a Dynamics 365 elszámoltathatósági készenlétére vonatkozó [ellenőrzőlistát a GDPR-ben.](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics)

Emellett a Windows Defender tűzfal kritikus fontosságú funkciókat is biztosít az eszközkapcsolatok biztonságának biztosítása érdekében. A HoloLens 2-ben a tűzfal mindig engedélyezve van, és nem lehet programozott módon vagy a felhasználói felületen keresztül letiltani. Ha a HoloLens 2-t felügyelt eszközként telepíti az Intune-nal, további megfelelőségi funkciók érhetők el az Endpoint és a [Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) Mobile Threat Defense megoldással való integrációjához. [](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started) 

További információ a HoloLens 2 [biztonságról és architektúráról.](https://docs.microsoft.com/hololens/security-architecture)

## <a name="os-security"></a>Operációs rendszer biztonsága
A frissítések automatikusan (alapértelmezés szerint) vannak megtörténik, így a HoloLens 2 mindig naprakész a Windows Holographic legújabb kiadásával és az összes telepített alkalmazással. Az operációs rendszer biztonságos tervezésével kapcsolatos további információkért tekintse meg a következőt:
1. [Állapotok elkülönítése és elkülönítése](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [Rendszergazdai jogosultságokkal nem működő operációs rendszer](https://docs.microsoft.com/hololens/security-adminless-os)
1. [A jelszóhasználat korlátozása](https://docs.microsoft.com/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Fizikai biztonság
A HoloLens 2 rendelkezik BitLocker-titkosítással védett flash [memóriával.](https://docs.microsoft.com/hololens/security-encryption-data-protection) Az eszköz és annak helyi adatai az [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) használatával offline is flash() állapotban is flash (flash) adatokat, illetve felügyelt eszközként üzembe helyezett MDM-en keresztül távolról is törölhetőek.

## <a name="data-protection"></a>Adatvédelem
A Windows-frissítések automatikusan futnak (alapértelmezés szerint), és az [Azure-integráció](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) megvédi az ön és a felhő között áthaladó adatokat. 

Amikor a HoloLens 2-t külső ügyfelekre telepíti, a [Dynamics 365 Remote Assist](https://docs.microsoft.com/hololens/hololens2-deployment-guide) gondoskodik arról, hogy a bizalmas vállalati adatok és erőforrások elkülönítve és biztonságban legyenek. 

A diagnosztikai adatok Microsofttal való megosztása manuálisan konfigurálható az MDM vagy a felhasználó által az OOBE során. Két lehetőség közül választhat: Választható diagnosztikai adatok és Szükséges diagnosztikai adatok. Ha az eredeti diagnosztikai beállítást később módosítani kell hibaelhárítási célokból, a felhasználó a Beállítások **-> Adatvédelem -> Diagnostics & Visszajelzés** vagy felügyelt eszköz esetén a rendszergazda (MDM) segítségével módosítható. A diagnosztikát, [visszajelzést és adatvédelmet a](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)következő Windows 10.

> [!Important]
> Az eszközdiagnosztikai naplók személyazonosításra alkalmas adatokat (PII-ket) tartalmaznak, például azt, hogy a felhasználó milyen folyamatokat vagy alkalmazásokat kezd el a tipikus műveletek során. Ha egy HoloLens-eszközön több felhasználó is osztozik (például a felhasználók különböző Microsoft Azure Active Directory- (Azure AD-) fiókokkal jelentkeznek be ugyanannak az eszköznek a felhasználói, a diagnosztikai naplók több felhasználóra vonatkozó PII-adatokat tartalmazhatnak.

 

A [](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) HoloLens 2-ről többféle gyűjtési módszer és adatmegőrzési szabályzat is rendelkezésre áll a diagnosztikai adatok gyűjtéséhez.  További információ arról, hogy a Microsoft hogyan gyűjti és használja fel a diagnosztikai adatokat: [Microsoft Adatvédelmi nyilatkozat – Diagnosztika – Bontsa](https://privacy.microsoft.com/privacystatement) ki a **Windows** elemet a bal oldali navigációs menüben, és válassza a **Diagnosztika lehetőséget.** Ugrás a **Diagnosztika szakaszra.**
