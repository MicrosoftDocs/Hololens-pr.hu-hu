---
title: Áttekintés – Alkalmazáskezelés
description: 'Első lépések: a vegyes valóságú alkalmazáskezelés áttekintése mobileszköz-felügyelet, Vállalati Microsoft Áruház és kiépítési csomagok használatával.'
keywords: HoloLens, felhasználó, fiók, alkalmazás, alkalmazáskezelés,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635551"
---
# <a name="app-management-overview"></a>Alkalmazáskezelés: Áttekintés

Az alkalmazásokat négy különböző útvonalon telepítheti: **Mobile Eszközkezelés (MDM),** **Microsoft Store Vállalatoknak**, **Microsoft Store**, vagy telepítésükön **keresztül.**

## <a name="mobile-device-management-mdm"></a>Mobileszköz-felügyelet (MDM)

Az MDM-megoldások lehetővé teszik az informatikai döntéshozók és a rendszergazdák számára, hogy privát módon automatikusan telepítik (leküldik) a házon belüli, üzletági alkalmazásokat, vagy alkalmazásokat vásárolnak az áruházon keresztül a felhasználók egy csoportja számára. HoloLens eszközök az alkalmazáskezeléshez Microsoft Endpoint Manager (Intune) [működnek a legjobban.](app-deploy-intune.md) Az Intune emellett lehetővé teszi a felhasználók számára az IT által felügyelt alkalmazások finomhangolt vezérlését a Céges portál használatával.

> [!NOTE]
> Az alábbi utasításokat azok a felhasználók számára ismertetjük, akik az Intune-nal szeretnék kezelni az alkalmazásokat. A Microsoft az Intune használatát javasolja az alkalmazás- és eszközkezeléshez.

A Eszközkezelés (MDM) a következőre vonatkozik:

* Telepített MDM + Céges portál
* Üzletági (nem nyilvános) alkalmazások
* Az elérhető alkalmazások manuális telepítése a Céges portál
* Rendszergazdai leküldés MDM-szabályzaton keresztül
* Automatikus frissítés MDM-en keresztül

## <a name="microsoft-store-for-business"></a>Vállalati Microsoft Áruház

A [Microsoft Store Vállalatoknak](app-deploy-store-business.md) az informatikai döntéshozók és a vállalatok rendszergazdái számára ingyenes és fizetős alkalmazások keresését, megszerzését, kezelését és terjesztését teszi lehetővé. A rendszergazdák egyetlen Microsoft Store kezelhetik az alkalmazásokat és a privát üzletági alkalmazásokat, valamint szükség szerint rendelhetnek hozzá és újra felhasználhatnak licenceket. További információ: [Prerequisites for using the Microsoft Store Vállalatoknak.](/microsoft-store/prerequisites-microsoft-store-for-business)

A Microsoft Store Vállalatoknak a következőre vonatkozik:

* Nyilvános vagy üzletági alkalmazások
* A szükséges alkalmazások automatikus telepítése MDM-társításon keresztül
* A felhasználó manuálisan tölt le alkalmazásokat
* Automatikus frissítés

## <a name="microsoft-store-apps"></a>Microsoft Áruházbeli alkalmazások

A Microsoft Store a vállalatok informatikai döntéshozói és rendszergazdái számára nyilvános alkalmazások keresését, megszerzését, kezelését és terjesztését teszi lehetővé.

Ez Microsoft Store a következőre vonatkozik:

* Csak nyilvános alkalmazások
* A felhasználó manuálisan tölt le alkalmazásokat
* Automatikus frissítés, ha csatlakozik az internethez

További információkért látogasson el a [Holographic Store Apps webhelyre.](/hololens/holographic-store-apps)

## <a name="install-via-provisioning-packages"></a>Telepítés kiépítési csomagokkal

[A kiépítési](app-deploy-provisioning-package.md) csomagok segítségével egyéni vagy üzletági alkalmazásokat telepíthet, így az informatikai szakemberek és a rendszergazdák gyorsan telepíthet alkalmazásokat egy helyi eszköz(ére) USB-kapcsolaton keresztül. Ez a telepítés internetkapcsolat nélkül és bármilyen identitástípus esetén használhatja.

A kiépítési csomagokkal történő telepítés a következőre vonatkozik:

* Üzletági / saját fejlesztésű (nem nyilvános) alkalmazások
* Nyilvános alkalmazások (ha elérhető offline telepítő)
* Csak USB-meghajtóról történő oldalbetöltés
* Nincs automatikus frissítés (manuális frissítéseket igényel a kiépítési csomagon keresztül)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Alkalmazások telepítése a 2. HoloLens a Alkalmazástelepítő

A [Alkalmazástelepítő](app-deploy-app-installer.md) a felhasználók egyszerűen telepíthet alkalmazásokat helyi eszközökre, vagy megoszthatnak egy alkalmazást egy olyan felhasználóval, aki nem ismeri a többi alkalmazástelepítési módszert a HoloLens. Ez a Fejlesztői mód engedélyezése vagy az alkalmazás használata nélkül Eszközportál. Ez egy egyszerű módszer egy teljesen felépített alkalmazás terjesztésére. Függetlenül attól, hogy az alkalmazást egyszerűen egy másik felhasználónak szeretné HoloLens, vagy egyszerűen üzembe szeretné helyezni az alkalmazást.

A telepítés Alkalmazástelepítő a következőre vonatkozik:

* Üzletági / saját fejlesztésű (nem nyilvános) alkalmazások
* Csak oldalbetöltés
* Nincs szükség fejlesztői módra vagy eszközportálra
* A végfelhasználók könnyen telepíthetők
