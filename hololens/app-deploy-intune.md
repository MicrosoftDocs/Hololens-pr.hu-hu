---
title: Intune és Céges portál
description: Megtudhatja, hogyan hozhat létre, rendelhet hozzá és hozhat létre kényelmes felhasználói élményt az Intune, a mobileszköz-kezelés és a vállalati portál használatával.
keywords: intune, alkalmazáskezelés, alkalmazás, vállalati portál, portál, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378157"
---
# <a name="intune--company-portal"></a>Intune & Céges portál

A Mobile Eszközkezelés (MDM) segítségével saját egyéni alkalmazásait használhatja a [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) szolgáltatáson keresztül, hogy közvetlenül a HoloLens-eszközökön telepítse őket. Microsoft Intune egy felhőalapú szolgáltatás, amely a mobileszköz-felügyeletre (MDM) és mobilalkalmazás-felügyeletre (MAM) összpontosít. Az Intune része a Microsoft Enterprise Mobility + Security [(EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)csomagnak, és lehetővé teszi, hogy a felhasználók hatékonyan és a szervezeti adatok védelmével is hatékonyan védve legyenek. Az Intune-nal kapcsolatos további információkért olvassa el [a Mi az Az Intune?](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>Telepítés

1. Töltsön fel egy alkalmazást egy üzletági alkalmazásba, vagy töltsön fel egy egyéni alkalmazást az Intune-bérlőjébe. Lásd még: [Vállalati alkalmazáskezelés.](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)

2. [Rendelje hozzá az alkalmazást egy csoporthoz.](https://docs.microsoft.com/mem/intune/apps/apps-deploy) A kiválasztott hozzárendelési típustól függően az alkalmazás automatikusan kézbesíthető vagy azonnal lekérhetők, ha van néhány alkalmazása.

> [!NOTE]
> Az appx csomag létrehozásakor ügyeljen arra, hogy figyelembe veszi az üzembe helyező eszköz(ék) architektúráját. A HoloLens 2 az ARM64, a HoloLens (1. generációs) pedig x86. Ha vegyes eszközkörnyezetet tervez, mindkettőt egyetlen appx-csomagba foglalhatja.

## <a name="assignment-types"></a>Hozzárendelés-típusok

Ahhoz, hogy az alkalmazás a regisztrációt követően automatikusan telepítve legyen az eszközön, válassza a **Kötelező** lehetőséget az egyes csoportokhoz.
Ahhoz, hogy az alkalmazás letölthető legyen a vállalati portálon keresztül regisztrált eszközökre, válassza a Regisztrált eszközökhöz **elérhető lehetőséget.**

## <a name="end-user-experience"></a>End-User felhasználói élmény

Miután beállította a konfigurációt az Intune-ban, készen áll arra, hogy a végfelhasználók megkapják a kiválasztott alkalmazásokat.

Az alábbi lépéseket követve automatikusan lekért alkalmazás(ak)t:

1. Regisztrálja az eszközt a bérlővel.
2. Miután az eszköz regisztrációja befejeződött, meg kell kapnia az alkalmazást az eszközön.
3. Ha nem látja azonnal az alkalmazást, a Beállítások fiókok munkahelyi vagy iskolai fiókjának adatai között görgessen le a telepített alkalmazás   >    >    >   állapotával kapcsolatos információkért.

Alkalmazások letöltése a Céges portál:

1. Nyissa meg **a Start menüt,** és válassza a **Microsoft Store.**
2. Keressen rá **a Céges portál,** és töltse le az alkalmazást.
3. Jelentkezzen be a fiókjába.
4. Válassza ki és töltse le a megkapni kívánt alkalmazást.

> [!Tip]
> További információ az [alkalmazások automatikus telepítéséről és Céges portál](https://docs.microsoft.com/mem/intune/apps/company-portal-app) és felügyeletéről az [Intune-ban.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
