---
title: Alkalmazások oldalsó betöltése és telepítése HoloLens 2 Alkalmazástelepítő
description: Megtudhatja, hogyan telepíthet és háríthatja el az alkalmazások hibáit az alkalmazástelepítővel, illetve hogyan telepíthet alkalmazásokat a felhasználói felületen keresztül.
keywords: alkalmazáskezelés, alkalmazás, hololens, alkalmazástelepítő
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 071dfb3b211928c561fc84754dd7ed4d64886f61
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428504"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Alkalmazások telepítése a 2. HoloLens a Alkalmazástelepítő

> [!NOTE]
> Ez a funkció a [Holographic Windows 20H2 – 2020.](hololens-release-notes.md)decemberi frissítésében érhető el. Ellenőrizze, hogy az eszköz [frissítve van-e](hololens-update-hololens.md) a funkció használatához.

Új **képességet (Alkalmazástelepítő)** adtunk hozzá, amely lehetővé teszi az alkalmazások zökkenőmentesebb telepítését a HoloLens 2 eszközön. A szolgáltatás alapértelmezés szerint be lesz kapcsolva a nem nem **engedélyezett eszközökön.** A vállalatok kimaradásának elkerülése érdekében az alkalmazástelepítő jelenleg nem lesz elérhető **a felügyelt** eszközökhöz.  

Az eszközök akkor minősülnek  "felügyeltnek", ha az alábbiak bármelyike igaz:

- MDM [regisztrálva](hololens-enroll-mdm.md)
- Kiépítési [csomaggal konfigurálva](hololens-provisioning.md)
- A felhasználói [identitás](hololens-identity.md) az Azure AD

Most már anélkül telepíthet alkalmazásokat, hogy engedélyeznie kellene a fejlesztői módot, vagy engedélyeznie kellene a Eszközportál.  Töltse le (USB-n vagy Microsoft Edge-n keresztül) az Appx-csomagot az eszközre, és navigáljon a Fájlkezelő Appx-csomaghoz, hogy a rendszer a telepítést elindító kérést kapjon.  Másik lehetőségként [kezdeményezzen telepítést a weblapról.](/windows/msix/app-installer/installing-windows10-apps-web) Az Microsoft Store-ból telepített alkalmazásokhoz vagy az MDM LOB App Deployment funkcióját használó alkalmazásokhoz hasonló [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) módon az [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) alkalmazásoknak digitálisan alá kell írniuk az aláírási eszközt, és az HoloLens-eszköznek megbízhatónak kell lennie az aláíráshoz használt tanúsítványban az alkalmazás üzembe helyezése előtt.

## <a name="requirements"></a>Követelmények

### <a name="for-your-devices"></a>Az eszközökhöz:

Ez a funkció jelenleg 2 Windows holographic 20H2 HoloLens érhető el. Győződjön meg arról, hogy a metódust használó összes [eszköz frissült.](hololens-update-hololens.md)

### <a name="for-your-apps"></a>Az alkalmazásokhoz:

Az alkalmazás Megoldáskonfigurációjának  masternek vagy kiadásnak kell lennie, mivel a Alkalmazástelepítő az áruház függőségeit fogja használni.  További információ az [alkalmazáscsomagok létrehozásáról:](/windows/msix/app-installer/create-appinstallerfile-vs).

Az ezzel a módszerrel telepített alkalmazásokat digitális aláírással kell aláírni. Az alkalmazás aláíráshoz tanúsítványt kell használnia. A tanúsítványt az [MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)megbízható hitelesítésszolgáltatói listájából is lekérheti, ebben az esetben nem kell további műveletet eszközbe vennie. Vagy aláírhatja a saját tanúsítványát, de a tanúsítványt le kell majd olni az eszközre.

- Alkalmazások aláírása [az aláíró eszközzel.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Tanúsítványbeállítások:**

- [Ms megbízható hitelesítésszolgáltatói listája](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Válasszon tanúsítványtelepítési módszert.**

- [A kiépítési](hololens-provisioning.md) csomagok helyi eszközökre alkalmazhatók.
- Az MDM segítségével [tanúsítványokat alkalmazhat az eszközkonfigurációkra.](/mem/intune/protect/certificates-configure)
- Használja a eszközt a [Tanúsítványkezelőben.](certificate-manager.md)

## <a name="installation-method"></a>Telepítési módszer

1. Ellenőrizze, hogy az eszköz nem felügyeltnek minősül-e.
1. Ellenőrizze, hogy HoloLens 2-es eszköz be van-e kapcsolva, és hogy be van-e jelentkezve.
1. A számítógépen navigáljon az egyéni alkalmazáshoz, és másolja a yourapp.appxbundle et a yourdevicename\Internal Storage\Downloads mappába.
    Miután befejezte a fájl másolását, leválaszthatja az eszközt, és később befejezheti a telepítést.
1. A 2. HoloLens nyissa meg a **Start** menüt, válassza **a** Minden alkalmazás lehetőséget, és indítsa el **Fájlkezelő** alkalmazást.
1. Lépjen a Letöltések mappára. Előfordulhat, hogy az alkalmazás bal oldali  panelén először az Ez az eszköz lehetőséget kell választania, majd a Letöltések lapra kell navigálnia.
1. Válassza ki a yourapp.appxbundle fájlt.
1. A Alkalmazástelepítő elindul. Az alkalmazás **telepítéséhez** kattintson a Telepítés gombra.

A telepített alkalmazás a telepítés befejezésekor automatikusan elindul.

![MRTK-példák telepítése Alkalmazástelepítő.](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Telepítésekkel kapcsolatos hibák elhárítása

Ha az alkalmazás telepítése sikertelen volt, ellenőrizze a következőket a hibaelhárításhoz:

- Az alkalmazás fő vagy kiadási build.
- Az eszköz egy olyan buildre frissül, amelyen ez a funkció elérhető.
- Csatlakozik [az internethez.](hololens-network.md)
- A [végpontok megfelelően Microsoft Store](hololens-offline.md) konfigurálva.  

## <a name="web-installer"></a>Webes telepítő

A felhasználók közvetlenül egy webkiszolgálóról telepíthet alkalmazásokat. Ez a folyamat a Alkalmazástelepítő egyszerű letöltési és telepítési elosztási módszerrel kombinálva használja.

### <a name="how-to-set-up-web-install"></a>Webes telepítés beállítása:

1. Győződjön meg arról, hogy az alkalmazás megfelelően van konfigurálva a telepítéshez.
1. Kövesse az [alábbi lépéseket a weblapról való telepítés engedélyezéséhez.](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)

### <a name="end-user-experience"></a>Végfelhasználói élmény:

1. A felhasználó a fent kiválasztott módszerrel kap és telepít tanúsítványt az eszközre.
1. A felhasználó felkeresi a fenti lépésben létrehozott URL-címet.

Az alkalmazás most már telepítve lesz az eszközön. Az alkalmazás megkereséhez nyissa meg a **Start menü,** és válassza Minden alkalmazás **gombot** az alkalmazás megkereséhez.

- Az alkalmazástelepítő telepítési módszerének hibaelhárításával kapcsolatos további segítségért látogasson el az [alkalmazástelepítő hibáinak elhárításához.](/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> A felhasználói felület a frissítési folyamat során nem támogatott. Így a ShowPrompt beállítás ezen [az oldalon és](/windows/msix/app-installer/update-settings) a kapcsolódó beállítások nem támogatottak.

## <a name="sample-apps"></a>Mintaalkalmazások

Próbálja ki a Alkalmazástelepítő az elérhető mintaalkalmazásaink egyikével. 
> [!div class="nextstepaction"]
> [Mintaalkalmazások](/windows/mixed-reality/develop/features-and-samples)
