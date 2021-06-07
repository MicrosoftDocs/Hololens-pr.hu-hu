---
title: A HoloLens 1st (gen) kibocsátási megjegyzései
description: Ismerje meg az új HoloLens-kiadások frissítéseit.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: 0fb6c9ed1cd8d3ecc23975052eed54512a465bfb
ms.sourcegitcommit: 35e180e09e3938c25e4cac8e99885d7e57fa4dad
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "111377997"
---
# <a name="hololens-1st-gen-release-notes"></a>A HoloLens 1st (gen) kibocsátási megjegyzései

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1. generációs) hosszú távú karbantartás
A HoloLens (1. generációs) hosszú távú karbantartási (LTS) állapotba került. A jövőbeli frissítések a problémákra és a biztonsági javításokra koncentrálnak, miközben megőrzik a funkcióparitást a Windows 10 Holographic HoloLens 1809-es (1. generációs) kiadásával.

A fejlesztők számára ez azt jelenti, hogy a HoloLens (1. generációs) alkalmazások nem támogatják az OpenXR API-t.  Ezek a headsetek a Unity 2019 LTS-ben is támogatottak maradnak a WinRT API háttérkészlettel a Unity 2019 LTS teljes életciklusa során, 2022 közepéig.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, 1809-es verzió

> **A következőkre vonatkozik:** HoloLens (1. generációs)

| Szolgáltatás | Részletek |
|---|---|
| **Gyorsműveletek menü** | Ha egy alkalmazásban van, a Bloom-kézmozdulat most megnyit egy Gyorsműveletek menüt, hogy gyors hozzáférést biztosít a gyakran használt rendszer funkcióihoz anélkül, hogy el kell hagynia az alkalmazást. <br> A [Gyorsműveletek menü kioszkmódban](hololens-kiosk.md) való beállítását lásd: HoloLens beállítása kioszkmódban.<br><br> |
| **A videórögzítés leállítása a Start vagy a Gyorsműveletek menüből** | Ha a videórögzítést a Start menü vagy a gyorsműveletek menüből indítja el, akkor ugyanott leállíthatja a rögzítést. (Ne feledje, ezt hangparancsokkal is meg lehet tenni.) |
| **Projekt miracast-kompatibilis eszközre** | Ha Microsoft Megjelenítési adaptert használ, a HoloLens-tartalmakat egy közeli Surface-eszközre vagy TV-re/monitorra is kivetítheti.  A **Start menüben** válassza **a Csatlakozás** lehetőséget, majd válassza ki azt az eszközt, amelybe kivetíteni szeretne. **Megjegyzés:** A HoloLens üzembe helyezéssel a Miracast leképezéseket a fejlesztői mód engedélyezése nélkül is használhatja. |
| **Új értesítések** | Tekintse meg az értesítési bejelentéseket a HoloLensen, és reagáljon ezekre, ahogy a PC-n is. Tekintet a válaszra vagy az elvetésükre (vagy ha magával ragadó élményben van része, használja a Bloom-kézmozdulatot). |
| **HoloLens-átfedések**<br>(fájlválasztó, billentyűzet, párbeszédpanelek stb.) | Olyan átfedéseket láthat, mint például a billentyűzet, a párbeszédpanelek, a fájlválasztó stb. a modern alkalmazások használata esetén. |
| **Vizuális visszajelzések átfedése a kötetek változásának felhasználói felületén** | A HoloLens fel-/le gombjainak használata esetén a kötetszint vizualizációja jelenik meg. |
| **Új felhasználói felület az eszközindításhoz** | A rendszerindítási folyamat során egy betöltési jelzőt adtunk hozzá, amely vizuális visszajelzést ad a rendszer betöltéséről. Indítsa újra az eszközt, hogy megjelenik az új betöltési jelző – ez a "Hello" üzenet és a Windows rendszerindítási emblémája között található. |
| **Közeli megosztás** | A Windows Nearby megosztási élményének köszönhetően egy közeli Windows-eszközzel is megoszthatja a rögzítést. Amikor fényképet vagy videót rögzít a HoloLensen (vagy használja a megosztás gombot egy alkalmazásból, például Microsoft Edge), válasszon ki egy közeli Windows-eszközt, amelyvel meg fogja osztani. |
| **Megosztás Microsoft Edge** | A Megosztás gomb mostantól elérhető Microsoft Edge HoloLensen. A Microsoft Edge válassza a **Megosztás lehetőséget.** Használja a HoloLens-megosztásválasztót a webes tartalmak megosztásához. |

#### <a name="for-international-customers"></a>Nemzetközi ügyfelek számára

| Szolgáltatás | Részletek |
| --- | --- |
| Honosított kínai és japán buildek | A HoloLens használata a honosított felhasználói felülettel egyszerűsített kínai vagy japán nyelvhez, beleértve a honosított Pinyin-billentyűzetet, a diktálást és a hangparancsokat.<br>[Ismerje meg, hogyan telepítheti a HoloLens kínai és japán verzióit.](hololens1-install-localized.md) |
| Beszédszintézis (TTS) | A beszédszintézis funkció mostantól a kínai, a japán és az angol nyelvet is támogatja. |

#### <a name="for-administrators"></a>Rendszergazdáknak

| Szolgáltatás |  Részletek  |
|---|----|
| [Telepítés utáni kiépítés engedélyezése](hololens-provisioning.md) | Most már bármikor alkalmazhat egy futásidejű kiépítési csomagot a **Beállítások használatával.** |
| Hozzárendelt hozzáférés Azure AD-csoportokkal | Mostantól Azure AD-csoportokkal konfigurálhatja a Windowshoz hozzárendelt hozzáférést az egy- vagy többalkalmazásos kioszkkonfiguráció beállítására. |
| PIN-kódos bejelentkezés profilváltás a bejelentkezési képernyőről | Mostantól elérhető a PIN-kódos bejelentkezés az **Egyéb felhasználó számára.** |
| Bejelentkezés webalkalmazással Hitelesítőadat-szolgáltató jelszóval | Most már kiválaszthatja a Globe bejelentkezési lehetőséget, hogy elindítsa a webes bejelentkezést a jelszavával. A bejelentkezési képernyőn válassza  a Bejelentkezési lehetőségek lehetőséget, majd a Földgömb lehetőséget a webes bejelentkezés indításához. Szükség esetén adja meg a felhasználónevét, majd a jelszavát. <br>**Megjegyzés:** Ha a rendszer a webes bejelentkezés során kéri, kihagyhatja a PIN-kód/intelligens kártya beállításait. |
| Az eszköz hardverinformációinak beolvassa az MDM-et, hogy az eszközök nyomon követhetők legyen sorozatszám alapján | A rendszergazdák az MDM-konzolon az eszköz sorozatszáma alapján láthatják és követhetik nyomon a HoloLenst. A funkciók rendelkezésre állását és utasításait az MDM-dokumentációban találhatja meg. |
| HoloLens-eszköz nevének beállítása MDM-en keresztül (átnevezés) | A rendszergazdák az MDM-konzoljukon láthatják és átnevezik a HoloLens-eszközöket. A funkciók rendelkezésre állását és utasításait az MDM-dokumentációban találhatja meg. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10 1803-as verziója a Microsoft HoloLens

> **A következőkre vonatkozik:** HoloLens (1. generációs)

Windows 10 1803-as verzió az első funkciófrissítés, Windows Holographic for Business az 1607-es Windows 10 kiadás óta. Ez a frissítés a következő módosításokat vezet be:

- Korábban csak azt lehetett ellenőrizni, hogy a Commercial Suite frissítési licence alkalmazva lett-e a HoloLens-eszközre, ha ellenőrizte, hogy a VPN elérhető-e az eszközön. A frissítési **licenc** alkalmazása után  >  **Windows Holographic for Business** Beállítások rendszer jelenik meg.  [Ismerje meg, hogyan oldhatja fel a Windows Holographic for Business funkcióit.](hololens1-upgrade-enterprise.md)

- Az operációs rendszer buildszámát az eszköztulajdonságok között a Fájlkezelő alkalmazásban és a [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)eszközben tudja megtekinteni.
- A HoloLens-eszközök kiépítése mostantól egyszerűbb a Windows Configuration Designer eszköz **Új HoloLens-eszközök** kiépítése varázslójával. A varázslóban konfigurálhatja a telepítési élményt és a hálózati kapcsolatokat, beállíthatja a fejlesztői módot, és tömeges Azure AD-jogkivonatokat szerezhet be. [Ismerje meg, hogyan használhatja a HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard)egyszerű kiépítési varázslóját.

- Amikor helyi fiókot hoz létre egy kiépítési csomagban, a jelszó már nem jár le 42 naponta.

- A [HoloLens konfigurálható egyalkalmazásos vagy többalkalmazásos kioszkként.](hololens-kiosk.md) A többalkalmazásos kioszkmód lehetővé teszi, hogy úgy állítson be egy HoloLenst, hogy csak a megadott alkalmazásokat futtassa, és megakadályozza a felhasználókat a módosításokban.

- A Media Transfer Protocol (MTP) engedélyezve van, így a HoloLens-eszközt USB-kapcsolaton keresztül csatlakoztathatja a számítógépekhez, és fájlokat továbbíthat a HoloLens és a számítógép között. A Fájlkezelő is használhatja fájlok áthelyezésére és törlésére a HoloLensen belül.

- Korábban, miután bejelentkezett az eszközre egy Azure Active Directory- (Azure AD-)  fiókkal,  munkahelyi hozzáférést kellett hozzáadnia a Beállításokban a vállalati erőforrásokhoz való hozzáféréshez. Most jelentkezzen be egy Azure AD-fiókkal, és a regisztráció automatikusan megtörténik.

- Bejelentkezés előtt a jelszó mező alatti hálózat ikont választva választhat egy másik hálózati Wi-Fi, amelyhez csatlakozni szeretne. Vendéghálózathoz is csatlakozhat, például egy szállodai, konferenciaközpontban vagy vállalatnál.

- Mostantól egyszerűen megoszthatja [a HoloLenst több,](hololens-multiple-users.md) Azure AD-fiókot használó felhasználóval.

- Ha a beállítás vagy a bejelentkezés sikertelen, válassza az új **Adatok gyűjtése** lehetőséget a diagnosztikai naplók lekért hibaelhárításához.

- Az egyéni felhasználók az eszköz mobileszköz-felügyeletben (MDM) való regisztrálása nélkül szinkronizálják a vállalati e-maileket. Az eszközt Microsoft-fiókkal is használhatja, letöltheti és telepítheti a Mail alkalmazást, és közvetlenül hozzáadhat egy e-mail fiókot.

- Az eszköz MDM-szinkronizálási állapotát a **Beállítások** fiókok hozzáférése munkahelyi vagy iskolai  >    >  **adatokhoz** lapon  >  **ellenőrizheti.** Az **Eszközszinkronizálás állapota** szakaszban elindíthatja a szinkronizálást, láthatja az MDM által kezelt területeket, és speciális diagnosztikai jelentést hozhat létre és exportálhat.
