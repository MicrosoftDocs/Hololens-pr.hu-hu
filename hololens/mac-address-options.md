---
title: Mac-címben HoloLens eszközök vállalati regisztrációja korlátozott Wi-Fi környezetben
description: Mac-cím hálózati címének kezelése 2 HoloLens eszközön
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d21a63aae94f5ea5269f61fe319a9036626de1b4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036229"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Mac-címben HoloLens eszközök vállalati regisztrációja korlátozott Wi-Fi környezetben

Ez a dokumentum egy gyakori forgatókönyvet ismertet az ügyfélkörnyezetekben, ahol a Wi-Fi MAC-címek korlátozzák, vagy a vezeték nélküli hálózatokhoz való csatlakozáshoz tanúsítványokra van szükség.

## <a name="example-scenario"></a>Példaforgatókönyv

Számos biztonságos környezetben számos ügyfél korlátozza a vezeték nélküli vagy vezetékes hálózatokat, amelyek csak a jóváhagyott (MAC-címeken alapuló) eszközök számára engedélyezik a sikeres csatlakozást. Ez a vezeték nélküli hozzáférési pont MAC-címszűrésével vagy EGY DHCP-kiszolgálón keresztül kényszeríthető ki. Emellett egyes vezeték nélküli hálózatok PEAP-védelem alatt áll, amihez tanúsítványt kell alkalmazni az eszközre a vezeték nélküli hálózat hitelesítése előtt.

Ebben a forgatókönyvben két fő követelmény késéseket okozhat, vagy manuális beavatkozást követelhet meg, amikor HoloLens eszközöket a hálózathoz:

- A vezeték nélküli PEAP-tanúsítványt alkalmazni kell az eszközre, mielőtt az eszköz sikeresen csatlakozna a vezeték nélküli hálózathoz.
- Regisztrálni kell a HoloLens Wi-Fi adapter MAC-címét.

A fenti követelményekkel kapcsolatos fő kihívások a következőek:

1. A MAC-cím jelenleg csak az eszköz Gépház alkalmazásból vagy az Intune-ból azonosítható a sikeres regisztráció után.

2. A MAC-cím nélkül az eszköz nem csatlakozhat a Wi-Fi hálózathoz a regisztráció megkezdéséhez.

3. Az ilyen kihívások manuális megkerülő megoldásához egy technikusnak kell kapcsolatba lépnie az eszközzel.

## <a name="solutions"></a>Megoldások

A helyzet számos módon javítható a környezetben elérhető infrastruktúrától függően.

| Megoldás | Előnyök | Követelmények |
| --- | --- | --- |
| Kiépítési csomag Ethernet-adapter használatával | Javítja az OOBE-élményt, és gyorsabb technikusi élményt tesz lehetővé. | HoloLens USB-C Hub + Ethernet adapter, és a technikusnak továbbra is kapcsolatba kell lépnie az eszközzel a MAC-rögzítéshez és az OOBE-véglegesítéshez |
| Autopilot Etherneten keresztüli Intune-regisztrációval | Ez egy egylépéses kapcsolat és az eszköz regisztrációja az ügyfélkörnyezetben. A MAC-rögzítés az eszközzel való kommunikáció nélkül is be lehet fejeződni | Az Intune engedélyezve van az ügyfél AAD-bérlője és egy HoloLens USB-C Ethernet-adapter számára |
| MAC-címek automatikus jelentése | Ha az eszközök regisztrálva vannak az Intune-bérlőben, egy parancsfájl jelentheti a MAC-címet a technikusnak. | Intune PowerShell-parancsmagok |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Kiépítési csomag Ethernet-adapter használatával

> [!NOTE] 
> Ha a vezetékes hálózatra MAC-korlátozások vonatkoznak, akkor az USB-C Hub + Ethernet adapter MAC-címét is előzetesen jóvá kell hagyni. Ezzel az adapterrel ügyelni kell arra, hogy más eszközökről is hozzáférjen a hálózathoz.

### <a name="requirements"></a>Követelmények

- Vezetékes hálózati port az ügyfélhálózathoz való hozzáféréssel
- HoloLens Kompatibilis USB-C hub Ethernet-adapterrel – Minden olyan adapternek, amely nem igényel további illesztőprogramokat vagy alkalmazástelepítéseket, megfelelőnek kell lennie.
- A kiépítési csomag a következőket tartalmazza:
  - Vezeték nélküli hálózattal kapcsolatos információkat és tanúsítványt tartalmaz
  - A szervezet Azure AD-hez való regisztrálási információinak opcionális megadása
  - Az egyéb szükséges kiépítési beállításokat tartalmazza

### <a name="process"></a>Folyamat

A folyamat az eszköz szoftverszintjétől függően változhat. Ha az eszköz [2004.](hololens-release-notes.md#windows-holographic-version-2004)májusi frissítéssel rendelkezik, kövesse az alábbi lépéseket.

1. Helyezze a kiépítési csomagot egy USB-meghajtó gyökerére, és csatlakoztassa a hubhoz.
2. Csatlakozás Ethernet-kábel a Hub + Ethernet adapterhez.
3. Csatlakozás USB-C hub HoloLens eszközhöz.
4. Kapcsolja be a HoloLens, és helyezze az eszközre.
5. A **Kiépítési csomag alkalmazáshoz** nyomja le a Kötet le és a Bekapcsoló gombot.
6. A technikus most már tudja követni az OOBE-t, és amikor elkészült, nyissa meg a Gépház alkalmazást az eszköz MAC-címének lekéréséhez.

Ha az eszköz operációsrendszer-buildtel rendelkezik a [2004.](hololens-release-notes.md#windows-holographic-version-2004)májusi frissítés előtt, kövesse az alábbi lépéseket.

1. Kapcsolja be a HoloLens, és csatlakoztassa az eszközt egy számítógéphez.
2. Az eszköznek fájltároló eszközként kell lennie a számítógépen.
3. A kiépítési csomag másolása az eszközre
4. Csatlakozás Ethernet-kábel a hubhoz.
5. Csatlakozás USB-C hub HoloLens eszközhöz.
6. Helyezze a HoloLens
7. A **Kiépítési csomag alkalmazáshoz** nyomja le a Kötet le és a Bekapcsoló gombot.
8. A technikus most már tudja követni az OOBE-t, és amikor elkészült, nyissa meg a Gépház alkalmazást az eszköz MAC-címének lekéréséhez.

### <a name="benefits"></a>Előnyök

Ez lehetővé teszi, hogy az eszköz egyetlen érintéssel alkalmazza a megfelelő kiépítési csomagot, és összegyűjtse az eszköz MAC-címét. [A kiépítési csomagokat az itt elérhető útmutatás szerint lehet létrehozni.](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>Autopilot Intune-regisztrációval

### <a name="requirements"></a>Követelmények

- Vezetékes hálózati port az ügyfélhálózathoz való hozzáféréssel
- HoloLens Holographic 2004 Windows futtató eszközök
- HoloLens Kompatibilis USB-C Ethernet-adapter
- Az Intune beállítása és engedélyezése az ügyfélbérlő számára
- Az AutoPilothoz regisztrált és az ügyfélbérlőbe importált eszköz
- Az eszközhöz definiált Intune-szabályzatok:
   - Vezeték nélküli hálózattal kapcsolatos információkat és tanúsítványt tartalmaz
   - Az egyéb szükséges kiépítési beállításokat tartalmazza

Ez lehetővé teszi, hogy a speciális hálózatépítési követelményekkel dolgozó ügyfelek kézből, skálázható módszer szerint regisztrálják az eszközöket

További előfeltételekre lesz szükség az alábbiak szerint:
1. [Engedélyezze a bérlőt az Autopilot előzetes verziója számára.](hololens2-autopilot.md)
1. Hozza létre HoloLens szabályzatokat a kiépítési csomag cseréjéhez az Intune-ban.
1. Hozza létre a HoloLens Intune-szabályzatokat.
1. Rendelje hozzá az eszközöket a megfelelő csoporthoz.

### <a name="process"></a>Folyamat

1. Csatlakozás csatlakoztassa az Ethernet-kábelt az adapterhez, és csatlakoztassa az adaptert a 2 HoloLens USB-C-porthoz.

2. Kapcsolja be a HoloLens.

3. Az eszköznek automatikusan csatlakoznia kell az internethez az OOBE során az Ethernet-adapteren keresztül. Észlelni kell az Autopilot-konfigurációt, és automatikusan regisztrálnia kell az Azure AD-be és az Intune-ba.

4. Az eszköz az Intune-Wi-Fi és egyéb konfigurációkhoz szükséges tanúsítványokat alkalmazza.

5. Ha elkészült, a technikus betöltheti az Intune (Endpoint Manager) portált, és részletezheti az eszköztulajdonságok oldalát a **Kezdőlap -> Eszközök -> DeviceName -> Hardware** lapon.

6. A Wi-Fi MAC-cím látható lesz az Intune-portálon.

   ![MAC-cím az Intune-on keresztül.](images/mac-address-intune.jpg)

7. A technikus hozzáadja ezt a MAC-címet engedélyezett eszközként.

### <a name="benefits"></a>Előnyök

Ez lehetővé teszi a "Fejből" üzembe helyezési élményt a technikus számára, így az eszköz anélkül léphet a dobozból az Azure AD-be és az Intune-ba, hogy a technikusnak el kellenehasználnia az eszközt, vagy manuálisan kapcsolatba kellene lépnie a HoloLens környezettel.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>MAC-címek jelentése a technikusnak

### <a name="requirements"></a>Követelmények

- Az "Intune Graph PowerShell" engedélyezése az ügyfélbérlőn
- Az Intune és Graph PowerShell telepítése a technikusok gépére.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Olvasási hozzáférés az Intune "Felügyelt eszközök" elemeihez. (Ügyfélszolgálati operátor vagy magasabb, vagy egyéni szerepkör)

Jelenleg nincs "egyszerű" mód automatizálási parancs aktiválására egy új eszköz Intune-nal való regisztrálása alapján. Ezért ez a parancs egyszerű lehetőséget biztosít a technikusnak a MAC-cím lekérésére anélkül, hogy be kellene jelentkeznie a portálra, és manuálisan lekérni.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Ez visszaadja az elmúlt 30 napban regisztrált HoloLens összes regisztrált eszköz nevét és MAC-címét.

![MAC-cím a PowerShellen keresztül.](images/mac-address-powershell.jpg)

### <a name="process"></a>Folyamat

Az Intune-regisztráció befejezése után a technikus a fenti szkript futtatásával lekéri a MAC-címet.
