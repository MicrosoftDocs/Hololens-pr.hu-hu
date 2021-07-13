---
title: HoloLens 2. megfelelőség és GDPR
description: A GDPR dokumentációja
keywords: HoloLens, GDPR, adatvédelem, személyes adatok
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
ms.openlocfilehash: 684a97a4fcdc3aaf830f164c54fb3079e296c78c
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637115"
---
# <a name="hololens-2-privacy-statement"></a>HoloLens 2. adatvédelmi nyilatkozat

A GDPR egyik fő eleme az "adatvédelem a tervezés alapján". Ez a fogalom különösen a mobileszközökre, például a HoloLens 2-re vonatkozik a hordozhatóság, a korlátlan internetkapcsolat és a nyílt kommunikációs csatornák miatt. Ennek eredményeképpen a HoloLens 2 biztonsága [](/hololens/security-architecture) úgy lett újratervezve, hogy fejlett, innovatív biztonsági és adatvédelmi védelmet nyújtson teljes végpontok között, és a Microsoft adatvédelmi és GDPR-szabályozásaiba is [beépítve](https://privacy.microsoft.com/)legyen.

 >[!NOTE]
> Ez a dokumentum nem vonatkozik a HoloLens (1. generációs) alkalmazásra.

## <a name="privacy-overview"></a>Adatvédelem áttekintése

HoloLens 2 egy önálló Windows számítógép, amely Windows Holographict futtat, és egy modern vegyes valóságú környezetben futtat alkalmazásokat és megoldásokat. Használható biztonságos offline eszközként, vagy telepíthető felügyelt [eszközként](/mem/intune/fundamentals/windows-holographic-for-business) a szervezeten belül. Az alábbi hivatkozásokon keresztül értheti meg, hogy a HoloLens 2 és a Microsoft hogyan használja és védi az adatokat:

1. [Microsoft adatvédelmi nyilatkozat – HoloLens](https://privacy.microsoft.com/privacystatement)  a bal oldali navigációs menüben bontsa ki a Vállalati és fejlesztői szakaszt, és válassza a Vállalati és fejlesztői szoftverek és **berendezések lehetőséget.** Ugrás a **HoloLens** szakaszra.
2. [Windows 10 és a online szolgáltatások](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & adatvédelmi megfelelőségi útmutató](/windows/privacy/windows-10-and-privacy-compliance)
4. [Adatvédelem és személyes adatok az Intune-ban](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Hálózati biztonság
A HoloLens [2.](/hololens/common-scenarios)gyakori üzembe helyezési forgatókönyvet követi. Az [adatokat](/azure/compliance/) az Azure világosztályú megfelelősége, valamint a jogi/szabályozási szabványok integrációja védi. Ha még nem használja az Azure AD-t és a Dynamics 365 Remote Assistet, tekintse meg az Azure és a Dynamics 365 elszámoltathatósági készenlétének ellenőrzőlistáját a [GDPR-ben.](/compliance/regulatory/gdpr-arc-azure-dynamics)

Emellett a Windows Defender tűzfal kritikus fontosságú funkciókat biztosít az eszközkapcsolatok biztonságának biztosítása érdekében. A 2 HoloLens esetén a tűzfal mindig engedélyezve van, és nem lehet programozott módon vagy a felhasználói felületen keresztül letiltani. Ha a HoloLens 2., az [Intune-nal](/mem/intune/protect/device-compliance-get-started)felügyelt eszközként van telepítve, további megfelelőségi funkciók érhetők el a Mobile Threat Defense-megoldásként Microsoft Intune végponttal való integrációhoz. [](/mem/intune/protect/advanced-threat-protection)

További információ a HoloLens 2 [biztonságról és architektúráról.](/hololens/security-architecture)

## <a name="os-security"></a>Operációs rendszer biztonsága
A frissítések automatikusan (alapértelmezés szerint) vannak telepítve, így a HoloLens 2-es verzió mindig naprakész a Windows Holographic legújabb kiadásával és az összes telepített alkalmazással. Az operációs rendszer biztonságos tervezésével kapcsolatos további információkért tekintse meg a következőt:

1. [Állapotok elkülönítése és elkülönítése](/hololens/security-state-separation-isolation)
1. [Rendszergazdai jogosultságokkal nem működő operációs rendszer](/hololens/security-adminless-os)
1. [A jelszóhasználat korlátozása](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Fizikai biztonság
HoloLens 2., bitLocker-titkosítással védett flash [memóriával rendelkezik.](/hololens/security-encryption-data-protection) Az eszköz és a helyi adatok offline is flash() flash (ily módon) az [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) használatával, vagy távolról is törölhetőek az MDM-en keresztül, ha felügyelt eszközként lett telepítve.

## <a name="data-protection"></a>Adatvédelem
Windows frissítések automatikusan futnak (alapértelmezés szerint), és az [Azure-integráció](/hololens/security-encryption-data-protection#Azure-integration) megvédi a közöttük és a felhőben áthaladó adatokat.

A 2 HoloLens telepítésekor a [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide) gondoskodik arról, hogy a bizalmas vállalati adatok és erőforrások elkülönítve és biztonságosan legyenek elkülönítve és biztonságosan.

A diagnosztikai adatok Microsofttal való megosztását az MDM vagy a felhasználó manuálisan konfigurálhatja az OOBE során. Két lehetőség közül választhat: Választható diagnosztikai adatok és Szükséges diagnosztikai adatok. Ha az eredeti diagnosztikai beállítást később módosítani kell hibaelhárítási célokból, a felhasználó a **Gépház -> Privacy -> Diagnostics & Feedback** (Adatvédelmi szabályzat – &-visszajelzés) vagy a rendszergazda (MDM) segítségével módosítható, ha az egy felügyelt eszköz. A diagnosztikát, visszajelzést és [adatvédelmet a](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)következő Windows 10.

> [!Important]
> Az eszközdiagnosztikai naplók személyes azonosításra alkalmas adatokat (PII-ket) tartalmaznak, például azt, hogy a felhasználó milyen folyamatokat vagy alkalmazásokat kezd el a tipikus műveletek során. Ha több felhasználó osztozik egy HoloLens-eszközön (például a felhasználók különböző Microsoft Azure Active Directory- (Azure AD-) fiókkal jelentkeznek be ugyanannak az eszköznek), a diagnosztikai naplók több felhasználóra vonatkozó, PII-adatokat tartalmazhatnak.

A diagnosztikai [adatok a](/hololens/hololens-diagnostic-logs) 2. évtől való gyűjtésére többféle gyűjtési módszer és adatmegőrzési szabályzat HoloLens létezik.  További információ arról, hogyan gyűjti és használja a Microsoft a diagnosztikai adatokat: [Microsoft Privacy Statement - Diagnostics](https://privacy.microsoft.com/privacystatement) - expand **Windows** a bal oldali navigációs menüben, és válassza a **Diagnosztika lehetőséget.** Ugrás a **Diagnosztika szakaszra.**
