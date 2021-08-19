---
title: HoloLens 2. adatvédelmi és adatvédelmi szabályzat
description: Adatvédelmi dokumentáció
keywords: HoloLens, GDPR, adatvédelem, személyes adatok, adatvédelem
author: golish
ms.author: marcingo
ms.reviewer: sekerawa, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 74f74645a3fc1282f48cb7ce0f6f722979c91b04
ms.sourcegitcommit: 548550f309010fa95f674a7ff688166a31cf1963
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/18/2021
ms.locfileid: "122336742"
---
# <a name="hololens-2-privacy-and-data-protection"></a>HoloLens 2. adatvédelmi és adatvédelmi szabályzat

A GDPR egyik fő eleme az "adatvédelem terv szerint". Ez a fogalom különösen a mobileszközökre, például a HoloLens 2-re vonatkozik a hordozhatóság, a korlátlan internetkapcsolat és a nyílt kommunikációs csatornák miatt. Ennek eredményeképpen a HoloLens 2 biztonsága [](/hololens/security-architecture) úgy lett újratervezve, hogy fejlett, innovatív biztonsági és adatvédelmi védelmet nyújtson teljes a Microsoft adatvédelmi és [GDPR-szabályozásaiba](https://privacy.microsoft.com/)is.

 >[!NOTE]
> Ez a dokumentum nem vonatkozik a HoloLens (1. generációs) alkalmazásra.

## <a name="privacy-overview"></a>Adatvédelem áttekintése

HoloLens 2. egy önálló Windows számítógép, amely Windows Holographicot futtat, és modern vegyes valóságú környezetben futtat alkalmazásokat és megoldásokat. Használható biztonságos offline eszközként, vagy telepíthető felügyelt [eszközként](/mem/intune/fundamentals/windows-holographic-for-business) a szervezeten belül. Az alábbi hivatkozásokon keresztül értheti meg, hogy a HoloLens 2 és a Microsoft hogyan használja és védi az adatokat:

1. [Microsoft adatvédelmi nyilatkozat – HoloLens](https://privacy.microsoft.com/privacystatement)  a bal oldali navigációs menüben bontsa ki a Nagyvállalati és fejlesztői szakaszt, és válassza a Vállalati és fejlesztői szoftverek és **berendezések lehetőséget.** Ugrás a **HoloLens** szakaszra.
2. [Windows 10 és a online szolgáltatások](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & adatvédelmi megfelelőségi útmutató](/windows/privacy/windows-10-and-privacy-compliance)
4. [Adatvédelem és személyes adatok az Intune-ban](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Hálózati biztonság
A HoloLens [2.](/hololens/common-scenarios)gyakori üzembe helyezési forgatókönyv szerint az adatait az [Azure](/azure/compliance/) világosztályú megfelelősége, valamint a jogi/szabályozási szabványok integrációja védi. Ha még csak most használja az Azure AD-t és a Dynamics 365 Remote Assistet, tekintse meg az Azure és a Dynamics 365 elszámoltathatósági készenlétére vonatkozó [ellenőrzőlistát a GDPR-ben.](/compliance/regulatory/gdpr-arc-azure-dynamics)

Emellett a Windows Defender tűzfal kritikus fontosságú funkciókat biztosít az eszközkapcsolatok biztonságának biztosítása érdekében. A HoloLens 2 esetén a tűzfal mindig engedélyezve van, és nem lehet programozott módon vagy a felhasználói felületen keresztül letiltani. Ha a HoloLens 2., az [Intune-nal](/mem/intune/protect/device-compliance-get-started)felügyelt eszközként van telepítve, további megfelelőségi funkciók érhetők el a Mobile Threat Defense-megoldásként Microsoft Intune végpont integrációja révén. [](/mem/intune/protect/advanced-threat-protection)

További információ a HoloLens 2 [biztonságról és architektúráról.](/hololens/security-architecture)

## <a name="os-security"></a>Operációs rendszer biztonsága
A frissítések automatikusan (alapértelmezés szerint) vannak megtörténik, így a HoloLens 2. verzió mindig naprakész a Windows Holographic legújabb kiadásával és az összes telepített alkalmazással. Az operációs rendszer biztonságos tervezésével kapcsolatos további információkért tekintse meg a következőt:

1. [Állapotok elkülönítése és elkülönítése](/hololens/security-state-separation-isolation)
1. [Rendszergazdai jogosultságokkal nem működő operációs rendszer](/hololens/security-adminless-os)
1. [A jelszóhasználat korlátozása](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Fizikai biztonság
HoloLens 2. meghajtó bitLocker-titkosítással védett flash [memóriával rendelkezik.](/hololens/security-encryption-data-protection) Az eszköz és annak helyi adatai az [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) használatával offline is flash() állapotban is flash (flash) adatokat, illetve felügyelt eszközként üzembe helyezett MDM-en keresztül távolról is törölhetőek.

## <a name="data-protection"></a>Adatvédelem
Windows frissítések automatikusan futnak (alapértelmezés szerint), és az [Azure-integráció](/hololens/security-encryption-data-protection#Azure-integration) megvédi az ön és a felhő között áthaladó adatokat.

A 2. HoloLens telepítésekor a [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide) gondoskodik arról, hogy a bizalmas vállalati adatok és erőforrások elkülönülnek és biztonságban legyenek.

A diagnosztikai adatok Microsofttal való megosztása manuálisan konfigurálható az MDM-ben vagy a felhasználó által az OOBE során. Két lehetőség közül választhat: Választható diagnosztikai adatok és Szükséges diagnosztikai adatok. Ha az eredeti diagnosztikai beállítást később módosítani kell hibaelhárítási célokból, a felhasználó a **Gépház -> Privacy -> Diagnostics & Feedback** (Adatvédelmi szabályzat –> Diagnostics & Visszajelzés) vagy felügyelt eszköz esetén a rendszergazda (MDM) segítségével módosítható. A diagnosztikát, [visszajelzést és adatvédelmet a](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)következő Windows 10.

> [!Important]
> Az eszközdiagnosztikai naplók személyes azonosításra alkalmas adatokat (PII-ket) tartalmaznak, például azt, hogy a felhasználó milyen folyamatokat vagy alkalmazásokat kezd el a tipikus műveletek során. Ha egy HoloLens-eszközön több felhasználó is osztozik (például a felhasználók különböző Microsoft Azure Active Directory- (Azure AD-) fiókkal jelentkeznek be ugyanannak az eszköznek), a diagnosztikai naplók több felhasználóra vonatkozó PII-adatokat tartalmazhatnak.

A diagnosztikai [adatoknak a](/hololens/hololens-diagnostic-logs) 2. HoloLens gyűjtési módszerei és adatmegőrzési szabályzata is létezik.  További információ arról, hogy a Microsoft hogyan gyűjti és használja fel a diagnosztikai adatokat: [Microsoft Privacy Statement - Diagnostics](https://privacy.microsoft.com/privacystatement) - expand **Windows** a bal oldali navigációs menüben, és válassza a **Diagnosztika lehetőséget.** Ugrás a **Diagnosztika szakaszra.**
