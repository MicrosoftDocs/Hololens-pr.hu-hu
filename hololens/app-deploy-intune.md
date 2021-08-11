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
ms.openlocfilehash: f1c178c940224ed3cd07c58b886b176108614caf7a8463af089e2f2357f45553
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665250"
---
# <a name="intune--company-portal"></a>Intune & Céges portál

A Mobile Eszközkezelés (MDM) segítségével saját egyéni alkalmazásait használhatja az [Microsoft Endpoint Manager -ban (Intune)](/intune/windows-holographic-for-business) annak közvetlen telepítéséhez a HoloLens eszközein. Microsoft Intune egy felhőalapú szolgáltatás, amely a mobileszköz-felügyeletre (MDM) és mobilalkalmazás-felügyeletre (MAM) összpontosít. Az Intune része a Microsoft Enterprise Mobility + Security [(EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)csomagnak, és lehetővé teszi, hogy a felhasználók hatékonyan és a szervezeti adatok védelmével is hatékonyan védve legyenek. Az Intune-nal kapcsolatos további információkért olvassa el [a Mi az az Intune?](/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>Telepítés

1. Töltsön fel egy alkalmazást egy üzletági alkalmazásba, vagy töltsön fel egy egyéni alkalmazást az Intune-bérlőjébe. Lásd még: [Vállalati alkalmazáskezelés.](/windows/client-management/mdm/enterprise-app-management)

2. [Rendelje hozzá az alkalmazást egy csoporthoz.](/mem/intune/apps/apps-deploy) A kiválasztott hozzárendelési típustól függően az alkalmazás automatikusan vagy bármikor lekérhetők, ha vannak alkalmazások.

> [!NOTE]
> Az appx csomag létrehozásakor ügyeljen arra, hogy figyelembe veszi az üzembe helyező eszköz(ék) architektúráját. HoloLens 2. az ARM64, HoloLens (1. generációs) pedig x86. Ha vegyes eszközkörnyezetet tervez, mindkettőt egyetlen appx csomagba foglalhatja.

## <a name="assignment-types"></a>Hozzárendelés-típusok

Ahhoz, hogy az alkalmazás a regisztrációt követően automatikusan telepítve legyen az eszközön, válassza a **Kötelező** lehetőséget az egyes csoportokhoz.
Ahhoz, hogy az alkalmazás letölthető legyen a vállalati portálon keresztül regisztrált eszközökre, válassza a Regisztrált eszközökhöz **elérhető lehetőséget.**

## <a name="end-user-experience"></a>End-User felhasználói élmény

Miután beállította a konfigurációt az Intune-ban, készen áll arra, hogy a végfelhasználók megkapják a kiválasztott alkalmazásokat.

Az alábbi lépéseket követve automatikusan lekért alkalmazás(ak)t:

1. Regisztrálja az eszközt a bérlővel.
2. Miután az eszköz regisztrációja befejeződött, meg kell kapnia az alkalmazást az eszközön.
3. Ha nem látja azonnal az alkalmazást, a Gépház-fiókok munkahelyi vagy iskolai fiókjának adatai lapon görgessen le a telepített alkalmazás állapotára  >    >    >   vonatkozó információkért.

Alkalmazások letöltése a Céges portál:

1. Nyissa meg **a Start menüt,** és válassza a **Microsoft Store.**
2. Keressen rá **a Céges portál,** és töltse le az alkalmazást.
3. Jelentkezzen be a fiókjába.
4. Válassza ki és töltse le a megkapni kívánt alkalmazást.

> [!Tip]
> További információ az [alkalmazások automatikus telepítéséről és Céges portál](/mem/intune/apps/company-portal-app) telepítéséről és felügyeletéről az [Intune-ban.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
