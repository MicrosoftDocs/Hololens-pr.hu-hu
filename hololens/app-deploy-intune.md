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
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427630"
---
# <a name="intune--company-portal"></a>Intune & Céges portál

A Mobile Eszközkezelés (MDM) segítségével a saját egyéni alkalmazásait az [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) használatával telepítheti közvetlenül a saját HoloLens eszközeire. Microsoft Intune egy felhőalapú szolgáltatás, amely a mobileszköz-felügyeletre (MDM) és a mobilalkalmazás-felügyeletre (MAM) összpontosít. Az Intune része a Microsoft Enterprise Mobility + Security [(EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)csomagnak, és lehetővé teszi, hogy a felhasználók hatékonyan dolgozhatnak, miközben a szervezeti adatok védelme is biztosított. További információ az Intune-nal kapcsolatban: [Mi az Intune?](/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>Telepítés

1. Feltölthet egy alkalmazást egy üzletági alkalmazásba, vagy feltölthet egy egyéni alkalmazást az Intune-bérlőjébe. Lásd még: [Vállalati alkalmazáskezelés.](/windows/client-management/mdm/enterprise-app-management)

2. [Rendelje hozzá az alkalmazást egy csoporthoz.](/mem/intune/apps/apps-deploy) A kiválasztott hozzárendelési típustól függően az alkalmazás automatikusan kézbesíthető vagy azonnal lekérhetők, ha van néhány alkalmazás.

> [!NOTE]
> Az appx csomag létrehozásakor ügyeljen arra, hogy figyelembe veszi az üzembe helyező eszköz(nek) architektúráját. HoloLens 2. az ARM64, HoloLens (1. generációs) pedig x86. Ha vegyes eszközkörnyezetet tervez, mindkettőt egyetlen appx csomagba foglalhatja.

## <a name="assignment-types"></a>Hozzárendelés-típusok

Ahhoz, hogy az alkalmazás a regisztrációt követően automatikusan telepítve legyen az eszközön, válassza a **Kötelező** lehetőséget az egyes csoportokhoz.
Ahhoz, hogy az alkalmazás letölthető legyen a vállalati portálon regisztrált eszközökre, válassza az **Elérhető a regisztrált eszközökhöz lehetőséget.**

## <a name="end-user-experience"></a>End-User felhasználói élmény

Miután beállította a konfigurációt az Intune-ban, készen áll arra, hogy a végfelhasználók megkapják a kiválasztott alkalmazásokat.

Az alábbi lépéseket követve automatikusan lekért alkalmazás(ak)t:

1. Regisztrálja eszközét a bérlővel.
2. Miután az eszköz regisztrációja befejeződött, meg kell kapnia az alkalmazást az eszközön.
3. Ha nem látja azonnal az alkalmazást, Gépház fiók munkahelyi vagy iskolai fiókjának adatai között, és görgessen le a telepített alkalmazás  >    >    >  állapotával kapcsolatos információkért.

Alkalmazások a következő Céges portál:

1. Nyissa meg **a Start menüt,** és válassza a **Microsoft Store.**
2. Keressen rá **a Céges portál,** és töltse le az alkalmazást.
3. Jelentkezzen be a fiókjába.
4. Válassza ki a megkapni kívánt alkalmazást, és töltse le.

> [!Tip]
> További információ az [alkalmazások automatikus telepítéséről és Céges portál](/mem/intune/apps/company-portal-app) telepítéséről és felügyeletéről az [Intune-ban.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
