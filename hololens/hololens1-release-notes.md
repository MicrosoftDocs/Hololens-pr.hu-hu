---
title: HoloLens első (gen) kibocsátási megjegyzései
description: Ismerje meg az új verziók frissítéseit HoloLens frissítéseket.
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
ms.openlocfilehash: e332794baf20fbab8278a138ceeafb651c6fa2a06f3f41a66038e544f7a6e46b
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661830"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens első (gen) kibocsátási megjegyzései

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1. generációs) hosszú távú karbantartás
HoloLens (1. generációs) hosszú távú karbantartási (LTS) állapotba került. A jövőbeli frissítések a problémákra és a biztonsági javításokra fognak összpontosítani, miközben megőrzik a funkcióparitást a Windows 10 Holographic 1809-es kiadásával a HoloLens (1. generáció).

A fejlesztők számára ez azt jelenti, HoloLens (1. generációs) alkalmazások nem támogatják az OpenXR API-t.  Ezek a headsetek a Unity 2019 LTS-ben is támogatottak maradnak a WinRT API háttérkészlettel a Unity 2019 LTS teljes életciklusa során, 2022 közepéig.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, 1809-es verzió

> **A következőkre vonatkozik:** HoloLens (1. generációs)

| Szolgáltatás | Részletek |
|---|---|
| **Gyorsműveletek menü** | Ha egy alkalmazásban van, a Bloom-kézmozdulat megnyit egy Gyorsműveletek menüt, amely gyors hozzáférést biztosít a gyakran használt rendszer funkcióihoz anélkül, hogy el kell hagynia az alkalmazást. <br> A [Gyorsműveletek kioszkmódban](hololens-kiosk.md) való beállítását HoloLens a Gyorsműveletek menüről a Kioszk módban.<br><br> |
| **A videórögzítés leállítása a Start vagy a Gyorsműveletek menüből** | Ha a videórögzítést a Start menü vagy a gyorsműveletek menüből indítja el, akkor ugyanott leállíthatja a rögzítést. (Ne feledje, ezt hangparancsokkal is meg lehet tenni.) |
| **Project egy Miracast-kompatibilis eszközre** | Project a HoloLens egy közeli Surface-eszközre vagy TV-re/monitorra, ha Microsoft Megjelenítési adaptert használ.  A **Start menüben** válassza **Csatlakozás** lehetőséget, majd válassza ki azt az eszközt, amelybe kivetíteni szeretne. **Megjegyzés:** Üzembe helyezheti a HoloLens, és Miracast a fejlesztői mód engedélyezése nélkül. |
| **Új értesítések** | A bejelentési bejelentések megtekintése és megválaszolása a HoloLens, ahogy a számítógépeken is. Tekintet a válaszra vagy azok elvetését (vagy ha magával ragadó élményben van része, használja a Bloom-kézmozdulatot). |
| **HoloLens átfedések**<br>(fájlválasztó, billentyűzet, párbeszédpanelek stb.) | Olyan átfedéseket láthat, mint például a billentyűzet, a párbeszédpanelek, a fájlválasztó stb. a modern alkalmazások használata esetén. |
| **Vizuális visszajelzések átfedése a kötetek változásának felhasználói felületén** | A kötet fel-/le gombjainak HoloLens a kötetszint vizualizációja jelenik meg. |
| **Új felhasználói felület az eszközindításhoz** | A rendszerindítási folyamat során egy betöltési jelzőt adtunk hozzá, amely vizuális visszajelzést ad a rendszer betöltéséről. Indítsa újra az eszközt, hogy megjelenik az új betöltési jelző – ez a "Hello" üzenet és a rendszerindítási embléma Windows között van. |
| **Közeli megosztás** | Az Windows Közeli megosztási élmény része, amely lehetővé teszi, hogy a rögzítést egy közeli Windows meg. Amikor fényképet vagy videót rögzít a HoloLens (vagy használja az alkalmazás megosztás gombját, például az Microsoft Edge-t), válasszon ki egy közeli Windows eszközt, amelyvel meg fogja osztani. |
| **Megosztás Microsoft Edge** | A Megosztás gomb mostantól elérhető Microsoft Edge a HoloLens. A Microsoft Edge válassza a **Megosztás lehetőséget.** A webes HoloLens megosztásához használja a megosztásválasztót. |

#### <a name="for-international-customers"></a>Nemzetközi ügyfelek számára

| Szolgáltatás | Részletek |
| --- | --- |
| Honosított kínai és japán buildek | A HoloLens egyszerűsített kínai vagy japán nyelvhez használható honosított felhasználói felülettel, beleértve a honosított Pinyin-billentyűzetet, a diktálást és a hangparancsokat.<br>[Ismerje meg, hogyan telepítheti a kínai és a japán HoloLens.](hololens1-install-localized.md) |
| Beszédszintézis (TTS) | A beszédszintézis funkció mostantól a kínai, a japán és az angol nyelvet támogatja. |

#### <a name="for-administrators"></a>Rendszergazdáknak

| Szolgáltatás |  Részletek  |
|---|----|
| [Telepítés utáni kiépítés engedélyezése](hololens-provisioning.md) | Most már bármikor alkalmazhat egy futásidejű kiépítési csomagot a **Gépház.** |
| Hozzárendelt hozzáférés Azure AD-csoportokkal | Mostantól használhatja az Azure AD-csoportokat a hozzárendelt Windows konfigurálhatók egy- vagy többalkalmazásos kioszkkonfiguráció beállítására. |
| PIN-kódos bejelentkezés profilváltás a bejelentkezési képernyőről | Mostantól elérhető a PIN-kódos bejelentkezés az **Egyéb felhasználó számára.** |
| Bejelentkezés webalkalmazással Hitelesítőadat-szolgáltató jelszóval | Most már kiválaszthatja a Globe bejelentkezési lehetőséget, hogy elindítsa a webes bejelentkezést a jelszavával. A bejelentkezési képernyőn válassza  a Bejelentkezési lehetőségek lehetőséget, majd a Földgömb lehetőséget a webes bejelentkezés indításához. Szükség esetén adja meg a felhasználónevét, majd a jelszavát. <br>**Megjegyzés:** Ha a rendszer a webes bejelentkezés során kéri, kihagyhatja a PIN-kód/intelligens kártya beállításait. |
| Az eszköz hardverinformációinak beolvassa az MDM-et, hogy az eszközök nyomon követhetők legyen sorozatszám alapján | A rendszergazdák az MDM-HoloLens láthatják és nyomon követhetik az eszköz sorozatszáma alapján. A funkciók rendelkezésre állását és utasításait az MDM-dokumentációban találhatja meg. |
| Eszköznév HoloLens MDM-en keresztül (átnevezés) | A rendszergazdák az MDM-HoloLens láthatják és átnevezik az eszközöket. A funkciók rendelkezésre állását és utasításait az MDM-dokumentációban találhatja meg. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10 1803-as verziója a Microsoft HoloLens

> **A következőkre vonatkozik:** HoloLens (1. generációs)

Windows 10 1803-as verzió az első funkciófrissítés, Windows Holographic for Business az 1607-es Windows 10 kiadás óta. Ez a frissítés a következő módosításokat vezet be:

- Korábban csak azt lehetett ellenőrizni, hogy a Commercial Suite frissítési licence alkalmazva lett-e a HoloLens-eszközre, ha ellenőrizte, hogy a VPN elérhető-e az eszközön. A **Gépház** rendszer a Windows Holographic for Business alkalmazása után  >   megjelenik.  [Ismerje meg, hogyan oldhatja fel a Windows Holographic for Business funkcióit.](hololens1-upgrade-enterprise.md)

- Az operációs rendszer buildszámát a Fájlkezelő alkalmazásban és a [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)eszköztulajdonságában tudja megtekinteni.
- A HoloLens eszköz üzembe HoloLens Configuration Designer eszköz új **Provision HoloLens devices** (Eszköz kiépítése Windows) varázslója megkönnyíti a Windows kiépítése. A varázslóban konfigurálhatja a telepítési élményt és a hálózati kapcsolatokat, beállíthatja a fejlesztői módot, és tömeges Azure AD-jogkivonatokat szerezhet be. [Ismerje meg, hogyan használhatja az egyszerű kiépítési varázslót a HoloLens.](hololens-provisioning.md#provisioning-package-hololens-wizard)

- Amikor létrehoz egy helyi fiókot egy kiépítési csomagban, a jelszó 42 naponta lejár.

- Az [alkalmazásokat HoloLens egyalkalmazásos vagy többalkalmazásos kioszkként konfigurálhatja.](hololens-kiosk.md) A többalkalmazásos kioszkmód lehetővé teszi egy olyan HoloLens, amely csak a megadott alkalmazásokat futtatja, és megakadályozza a felhasználókat a módosításokban.

- A Media Transfer Protocol (MTP) engedélyezve van, így csatlakoztathatja az HoloLens-eszközt a számítógéphez USB-kapcsolaton keresztül, és fájlokat HoloLens és a számítógép között. A Fájlkezelő is használhatja fájlok áthelyezésére és törlésére a HoloLens.

- Korábban, miután bejelentkezett az eszközre egy Azure Active Directory- (Azure AD-)  fiókkal,  munkahelyi hozzáférést kellett hozzáadnia a Gépház-ban a vállalati erőforrásokhoz való hozzáféréshez. Most jelentkezzen be egy Azure AD-fiókkal, és a regisztráció automatikusan megtörténik.

- Bejelentkezés előtt a jelszó mező alatti hálózat ikont választva választhat egy másik hálózati Wi-Fi, amelyhez csatlakozni szeretne. Vendéghálózathoz is csatlakozhat, például egy szállodai, konferenciaközpontban vagy üzletben.

- Mostantól egyszerűen [megoszthat](hololens-multiple-users.md) több HoloLens Azure AD-fiókkal.

- Ha a beállítás vagy a bejelentkezés sikertelen, válassza az új **Adatok gyűjtése** lehetőséget a diagnosztikai naplók lekért hibaelhárításához.

- Az egyéni felhasználók anélkül szinkronizálják a vállalati e-maileket, hogy regisztrálják eszközüket a mobileszköz-felügyeletben (MDM). Az eszközt Microsoft-fiókkal is használhatja, letöltheti és telepítheti a Mail alkalmazást, és közvetlenül hozzáadhat egy e-mail fiókot.

- Az eszköz MDM-szinkronizálási állapotát az Gépház hozzáférés munkahelyi vagy iskolai  >    >  **adatokhoz** lapon  >  **ellenőrizheti.** Az **Eszközszinkronizálás állapota** szakaszban elindíthatja a szinkronizálást, láthatja az MDM által kezelt területeket, és speciális diagnosztikai jelentést hozhat létre és exportálhat.
