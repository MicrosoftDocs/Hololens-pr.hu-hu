---
title: HoloLens-eszközök nagyvállalati regisztrálása KORLÁTOZOTT MAC-Wi-Fi környezetben
description: Hálózat MAC-címének kezelése HoloLens 2-eszközökön
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
ms.openlocfilehash: a577eace62040e2d48de5d3e4cc99ef108bd006c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379547"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="314e4-103">HoloLens-eszközök nagyvállalati regisztrálása KORLÁTOZOTT MAC-Wi-Fi környezetben</span><span class="sxs-lookup"><span data-stu-id="314e4-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="314e4-104">Ez a dokumentum egy gyakori forgatókönyvet ismertet az ügyfélkörnyezetekben, ahol a Wi-Fi MAC-címek korlátozzák, vagy a vezeték nélküli hálózatokhoz való csatlakozáshoz tanúsítványokra van szükség.</span><span class="sxs-lookup"><span data-stu-id="314e4-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="314e4-105">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="314e4-105">Example Scenario</span></span>

<span data-ttu-id="314e4-106">Számos biztonságos környezetben számos ügyfél korlátozza a vezeték nélküli vagy vezetékes hálózatait, amelyek csak a jóváhagyott eszközök (MAC-címek alapján) számára engedélyezik a sikeres csatlakozást.</span><span class="sxs-lookup"><span data-stu-id="314e4-106">Many customers in secure environments have restrictions on their Wireless or wired networks that will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="314e4-107">Ezt a mac-címek szűrésével kényszerítheti ki egy vezeték nélküli hozzáférési ponton vagy egy DHCP-kiszolgálón.</span><span class="sxs-lookup"><span data-stu-id="314e4-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="314e4-108">Emellett egyes vezeték nélküli hálózatok PEAP-védelem alatt áll, amihez tanúsítványt kell alkalmazni az eszközre a vezeték nélküli hálózat hitelesítése előtt.</span><span class="sxs-lookup"><span data-stu-id="314e4-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="314e4-109">Ebben a forgatókönyvben két fő követelmény okozhat késést, vagy manuális beavatkozást igényel, amikor HoloLens-eszközöket csatlakozik a hálózathoz:</span><span class="sxs-lookup"><span data-stu-id="314e4-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="314e4-110">A vezeték nélküli PEAP-tanúsítványt alkalmazni kell az eszközre, mielőtt az eszköz sikeresen csatlakozna a vezeték nélküli hálózathoz.</span><span class="sxs-lookup"><span data-stu-id="314e4-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="314e4-111">A HoloLens-adapter MACWi-Fi címét regisztrálni kell.</span><span class="sxs-lookup"><span data-stu-id="314e4-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="314e4-112">A fenti követelményekkel kapcsolatos fő kihívások a következőek:</span><span class="sxs-lookup"><span data-stu-id="314e4-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="314e4-113">A MAC-cím jelenleg csak az eszköz Beállítások alkalmazásában vagy a sikeres regisztrációt követően az Intune-ban azonosítható.</span><span class="sxs-lookup"><span data-stu-id="314e4-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>

2. <span data-ttu-id="314e4-114">A MAC-cím nélkül az eszköz nem csatlakozhat a Wi-Fi hálózathoz a regisztráció megkezdéséhez.</span><span class="sxs-lookup"><span data-stu-id="314e4-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>

3. <span data-ttu-id="314e4-115">Ezeknek a kihívásoknak a manuális megkerülő megoldásához egy technikusnak kell kapcsolatba lépnie az eszközzel.</span><span class="sxs-lookup"><span data-stu-id="314e4-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="314e4-116">Megoldások</span><span class="sxs-lookup"><span data-stu-id="314e4-116">Solutions</span></span>

<span data-ttu-id="314e4-117">A környezetben elérhető infrastruktúrától függően számos módon javítható ez a helyzet.</span><span class="sxs-lookup"><span data-stu-id="314e4-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="314e4-118">Megoldás</span><span class="sxs-lookup"><span data-stu-id="314e4-118">Solution</span></span> | <span data-ttu-id="314e4-119">Előnyök</span><span class="sxs-lookup"><span data-stu-id="314e4-119">Benefits</span></span> | <span data-ttu-id="314e4-120">Követelmények</span><span class="sxs-lookup"><span data-stu-id="314e4-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="314e4-121">Kiépítési csomag Ethernet-adapter használatával</span><span class="sxs-lookup"><span data-stu-id="314e4-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="314e4-122">Javítja az OOBE-élményt, és gyorsabb technikusi élményt tesz lehetővé.</span><span class="sxs-lookup"><span data-stu-id="314e4-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="314e4-123">HoloLens-kompatibilis USB-C Hub + Ethernet-adapter, és a technikusnak továbbra is kapcsolatba kell lépnie az eszközzel a MAC-rögzítéshez és az OOBE véglegesítéséhez</span><span class="sxs-lookup"><span data-stu-id="314e4-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalization</span></span> |
| <span data-ttu-id="314e4-124">Autopilot Etherneten keresztüli Intune-regisztrációval</span><span class="sxs-lookup"><span data-stu-id="314e4-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="314e4-125">Ez egy egylépéses kapcsolat és az eszköz regisztrációja az ügyfélkörnyezetben.</span><span class="sxs-lookup"><span data-stu-id="314e4-125">This is a single-step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="314e4-126">A MAC-rögzítés anélkül is befejeződhet, hogy kapcsolatba kellene lépnie az eszközzel</span><span class="sxs-lookup"><span data-stu-id="314e4-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="314e4-127">Az Intune engedélyezve van az ügyfél AAD-bérlője és egy HoloLens-kompatibilis USB-C Ethernet-adapter számára</span><span class="sxs-lookup"><span data-stu-id="314e4-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="314e4-128">MAC-címek automatikus jelentése</span><span class="sxs-lookup"><span data-stu-id="314e4-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="314e4-129">Ha az eszközök regisztrálva vannak az Intune-bérlőben, egy parancsfájl jelentheti a MAC-címet a technikusnak.</span><span class="sxs-lookup"><span data-stu-id="314e4-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="314e4-130">Intune PowerShell-parancsmagok</span><span class="sxs-lookup"><span data-stu-id="314e4-130">Intune PowerShell cmdlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="314e4-131">Kiépítési csomag Ethernet-adapter használatával</span><span class="sxs-lookup"><span data-stu-id="314e4-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="314e4-132">Ha a vezetékes hálózatra MAC-korlátozások vonatkoznak, akkor az USB-C Hub + Ethernet adapter MAC-címét is előzetesen jóvá kell hagyni.</span><span class="sxs-lookup"><span data-stu-id="314e4-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="314e4-133">Ezzel az adapterrel ügyelni kell arra, hogy más eszközökről is hozzáférjen a hálózathoz.</span><span class="sxs-lookup"><span data-stu-id="314e4-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="314e4-134">Követelmények</span><span class="sxs-lookup"><span data-stu-id="314e4-134">Requirements</span></span>

- <span data-ttu-id="314e4-135">Vezetékes hálózati port az ügyfélhálózathoz való hozzáféréssel</span><span class="sxs-lookup"><span data-stu-id="314e4-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="314e4-136">HoloLens-kompatibilis USB-C Hub Ethernet-adapterrel – Minden olyan adapternek megfelelőnek kell lennie, amely nem igényel további illesztőprogramokat vagy alkalmazástelepítéseket.</span><span class="sxs-lookup"><span data-stu-id="314e4-136">HoloLens Compatible USB-C Hub with Ethernet adaptor — Any adapter that doesn't require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="314e4-137">A kiépítési csomag a következőket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="314e4-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="314e4-138">Vezeték nélküli hálózattal kapcsolatos információkat és tanúsítványt tartalmaz</span><span class="sxs-lookup"><span data-stu-id="314e4-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="314e4-139">A szervezet Azure AD-hez való regisztrálási információinak opcionális megadása</span><span class="sxs-lookup"><span data-stu-id="314e4-139">Optionally containing enrollment information for the Organization's Azure AD</span></span>
  - <span data-ttu-id="314e4-140">Az egyéb szükséges kiépítési beállításokat tartalmazza</span><span class="sxs-lookup"><span data-stu-id="314e4-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="314e4-141">Folyamat</span><span class="sxs-lookup"><span data-stu-id="314e4-141">Process</span></span>

<span data-ttu-id="314e4-142">A folyamat az eszköz szoftverszintjétől függően változhat.</span><span class="sxs-lookup"><span data-stu-id="314e4-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="314e4-143">Ha az eszköz [2004.](hololens-release-notes.md#windows-holographic-version-2004)májusi frissítéssel rendelkezik, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="314e4-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="314e4-144">Helyezze a kiépítési csomagot egy USB-meghajtó gyökerére, és csatlakoztassa a hubhoz.</span><span class="sxs-lookup"><span data-stu-id="314e4-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="314e4-145">Csatlakoztassa az Ethernet-kábelt a Hub + Ethernet adapterhez.</span><span class="sxs-lookup"><span data-stu-id="314e4-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="314e4-146">Csatlakoztassa az USB-C Hubot a HoloLens-eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="314e4-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="314e4-147">Kapcsolja be a HoloLenst, és helyezze az eszközre.</span><span class="sxs-lookup"><span data-stu-id="314e4-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="314e4-148">A **kiépítési csomag alkalmazáshoz** nyomja le a Kötet le és a Bekapcsoló gombot.</span><span class="sxs-lookup"><span data-stu-id="314e4-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="314e4-149">A technikus most már tudja követni az OOBE-t, és amikor elkészült, nyissa meg a Beállítások alkalmazást az eszköz MAC-címének lekéréséhez.</span><span class="sxs-lookup"><span data-stu-id="314e4-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="314e4-150">Ha az eszköz a [2004.](hololens-release-notes.md#windows-holographic-version-2004)májusi frissítés előtt rendelkezik operációsrendszer-buildtel, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="314e4-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="314e4-151">Kapcsolja be a HoloLenst, és csatlakoztassa az eszközt egy számítógéphez.</span><span class="sxs-lookup"><span data-stu-id="314e4-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="314e4-152">Az eszköznek fájltároló eszközként kell lennie a számítógépen.</span><span class="sxs-lookup"><span data-stu-id="314e4-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="314e4-153">A kiépítési csomag másolása az eszközre</span><span class="sxs-lookup"><span data-stu-id="314e4-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="314e4-154">Csatlakoztassa az Ethernet-kábelt a hubhoz.</span><span class="sxs-lookup"><span data-stu-id="314e4-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="314e4-155">Csatlakoztassa az USB-C Hubot a HoloLens-eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="314e4-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="314e4-156">Put on the HoloLens</span><span class="sxs-lookup"><span data-stu-id="314e4-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="314e4-157">A **kiépítési csomag alkalmazáshoz** nyomja le a Kötet le és a Bekapcsoló gombot.</span><span class="sxs-lookup"><span data-stu-id="314e4-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="314e4-158">A technikus most már tudja követni az OOBE-t, és amikor elkészült, nyissa meg a Beállítások alkalmazást az eszköz MAC-címének lekéréséhez.</span><span class="sxs-lookup"><span data-stu-id="314e4-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="314e4-159">Előnyök</span><span class="sxs-lookup"><span data-stu-id="314e4-159">Benefits</span></span>

<span data-ttu-id="314e4-160">Ez lehetővé teszi, hogy az eszköz egyetlen érintéssel alkalmazza a megfelelő kiépítési csomagot, és összegyűjtse az eszköz MAC-címét.</span><span class="sxs-lookup"><span data-stu-id="314e4-160">This will allow a "Single touch" of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="314e4-161">A kiépítési csomagokat az itt elérhető útmutatás szerint lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="314e4-161">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="314e4-162">Autopilot Intune-regisztrációval</span><span class="sxs-lookup"><span data-stu-id="314e4-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="314e4-163">Követelmények</span><span class="sxs-lookup"><span data-stu-id="314e4-163">Requirements</span></span>

- <span data-ttu-id="314e4-164">Vezetékes hálózati port az ügyfélhálózathoz való hozzáféréssel</span><span class="sxs-lookup"><span data-stu-id="314e4-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="314e4-165">Windows Holographic 2004 rendszert futtató HoloLens-eszközök</span><span class="sxs-lookup"><span data-stu-id="314e4-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="314e4-166">HoloLens-kompatibilis USB-C Ethernet-adapter</span><span class="sxs-lookup"><span data-stu-id="314e4-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="314e4-167">Az Intune beállítása és engedélyezése az ügyfélbérlő számára</span><span class="sxs-lookup"><span data-stu-id="314e4-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="314e4-168">Az AutoPilothoz regisztrált és az ügyfélbérlőbe importált eszköz</span><span class="sxs-lookup"><span data-stu-id="314e4-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="314e4-169">Az eszközhöz definiált Intune-szabályzatok:</span><span class="sxs-lookup"><span data-stu-id="314e4-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="314e4-170">Vezeték nélküli hálózattal kapcsolatos információkat és tanúsítványt tartalmaz</span><span class="sxs-lookup"><span data-stu-id="314e4-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="314e4-171">Az egyéb szükséges kiépítési beállításokat tartalmazza</span><span class="sxs-lookup"><span data-stu-id="314e4-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="314e4-172">Ez lehetővé teszi, hogy a speciális hálózatépítési követelményekkel dolgozó ügyfelek kézből, skálázható módszerként regisztrálják az eszközöket</span><span class="sxs-lookup"><span data-stu-id="314e4-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="314e4-173">További előfeltételekre lesz szükség az alábbiak szerint:</span><span class="sxs-lookup"><span data-stu-id="314e4-173">Additional pre-requisites will be needed as below:</span></span>
1. <span data-ttu-id="314e4-174">[Engedélyezze a bérlőt az Autopilot előzetes verziója számára.](https://docs.microsoft.com/hololens/hololens2-autopilot)</span><span class="sxs-lookup"><span data-stu-id="314e4-174">[Enable the Tenant for the Autopilot preview](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
1. <span data-ttu-id="314e4-175">Hozza létre a HoloLens-szabályzatokat a kiépítési csomag cseréjéhez az Intune-ban.</span><span class="sxs-lookup"><span data-stu-id="314e4-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="314e4-176">Hozza létre a HoloLens Intune-szabályzatokat.</span><span class="sxs-lookup"><span data-stu-id="314e4-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="314e4-177">Rendelje hozzá az eszközöket a megfelelő csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="314e4-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="314e4-178">Folyamat</span><span class="sxs-lookup"><span data-stu-id="314e4-178">Process</span></span>

1. <span data-ttu-id="314e4-179">Csatlakoztassa az Ethernet-kábelt az adapterhez, és csatlakoztassa az adaptert a HoloLens 2 eszköz USB-C portjához.</span><span class="sxs-lookup"><span data-stu-id="314e4-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>

2. <span data-ttu-id="314e4-180">Kapcsolja be a HoloLenst.</span><span class="sxs-lookup"><span data-stu-id="314e4-180">Turn on the HoloLens.</span></span>

3. <span data-ttu-id="314e4-181">Az eszköznek automatikusan csatlakoznia kell az internethez az OOBE során az Ethernet-adapteren keresztül.</span><span class="sxs-lookup"><span data-stu-id="314e4-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="314e4-182">Észlelnie kell az Autopilot konfigurációját, és automatikusan regisztrálnia kell az Azure AD-be és az Intune-ba.</span><span class="sxs-lookup"><span data-stu-id="314e4-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune.</span></span>

4. <span data-ttu-id="314e4-183">Az eszköz az Intune-Wi-Fi szükséges tanúsítványokat és egyéb konfigurációkat alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="314e4-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune.</span></span>

5. <span data-ttu-id="314e4-184">Ha elkészült, a technikus betöltheti az Intune (Endpoint Manager) portált, és részletezheti az eszköztulajdonságok oldalát a **Kezdőlap -> Eszközök -> DeviceName -> Hardware** lapon.</span><span class="sxs-lookup"><span data-stu-id="314e4-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**.</span></span>

6. <span data-ttu-id="314e4-185">A Wi-Fi MAC-cím látható lesz az Intune-portálon.</span><span class="sxs-lookup"><span data-stu-id="314e4-185">The Wi-Fi MAC address will be visible within the Intune Portal.</span></span>

   ![MAC-cím az Intune-on keresztül](images/mac-address-intune.jpg)

7. <span data-ttu-id="314e4-187">A technikus ezt a MAC-címet fogja hozzáadni engedélyezett eszközként.</span><span class="sxs-lookup"><span data-stu-id="314e4-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="314e4-188">Előnyök</span><span class="sxs-lookup"><span data-stu-id="314e4-188">Benefits</span></span>

<span data-ttu-id="314e4-189">Ez lehetővé teszi a "Fejből" üzembe helyezési élményt a technikus számára, így az eszköz anélkül léphet a dobozból az Azure AD-be és az Intune-ba való regisztrációhoz, hogy a technikusnak el kellenehasználnia az eszközt, vagy manuálisan kapcsolatba kellene lépnie a HoloLens-környezettel.</span><span class="sxs-lookup"><span data-stu-id="314e4-189">This will allow a "Heads off" deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="314e4-190">MAC-címek jelentése a technikusnak</span><span class="sxs-lookup"><span data-stu-id="314e4-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="314e4-191">Követelmények</span><span class="sxs-lookup"><span data-stu-id="314e4-191">Requirements</span></span>

- <span data-ttu-id="314e4-192">Az "Intune Graph PowerShell" engedélyezése az ügyfélbérlőn</span><span class="sxs-lookup"><span data-stu-id="314e4-192">Authorization of the "Intune Graph PowerShell" against the customer Tenant</span></span>
- <span data-ttu-id="314e4-193">Az Intune Graph PowerShell telepítése a technikusok gépére.</span><span class="sxs-lookup"><span data-stu-id="314e4-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="314e4-194">Olvasási hozzáférés az Intune "Felügyelt eszközök" elemeihez.</span><span class="sxs-lookup"><span data-stu-id="314e4-194">Read access to the "Managed Devices" elements of Intune.</span></span> <span data-ttu-id="314e4-195">(Ügyfélszolgálati operátor vagy magasabb, vagy egyéni szerepkör)</span><span class="sxs-lookup"><span data-stu-id="314e4-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="314e4-196">Jelenleg nincs "egyszerű" mód automatizálási parancs aktiválására egy új eszköz Intune-nal való regisztrálása alapján.</span><span class="sxs-lookup"><span data-stu-id="314e4-196">At present, there is no "simple" way to trigger an automation command based on the enrollment of a new device within Intune.</span></span> <span data-ttu-id="314e4-197">Ezért ez a parancs egyszerű lehetőséget biztosít a technikusnak a MAC-cím lekérésére anélkül, hogy be kellene jelentkeznie a portálra, és manuálisan kellene lekérni.</span><span class="sxs-lookup"><span data-stu-id="314e4-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="314e4-198">Ez visszaadja az elmúlt 30 napban regisztrált HoloLens-eszközök nevét és MAC-címét.</span><span class="sxs-lookup"><span data-stu-id="314e4-198">This will return the name and MAC address of any HoloLens devices that have been enrolled in the last 30 days.</span></span>

![MAC-cím a PowerShellen keresztül](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="314e4-200">Folyamat</span><span class="sxs-lookup"><span data-stu-id="314e4-200">Process</span></span>

<span data-ttu-id="314e4-201">Az Intune-regisztráció befejezése után a technikus a fenti szkript futtatásával lekéri a MAC-címet.</span><span class="sxs-lookup"><span data-stu-id="314e4-201">After the Intune enrollment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
