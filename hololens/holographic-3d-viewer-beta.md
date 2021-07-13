---
title: A 3D-megjelenítő bétaverzió használata HoloLens (1. generációs)
description: Ismerteti a 3D-megjelenítő (1. generációs) HoloLens bétaverziója által támogatott fájlokat és szolgáltatásokat, valamint az alkalmazás használatát és hibaelhárítását.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 00e99d3f67e9e4371da12612b9b01c3ce58e71bd
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635483"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a><span data-ttu-id="7af33-103">A 3D-megjelenítő bétaverzió használata HoloLens (1. generációs)</span><span class="sxs-lookup"><span data-stu-id="7af33-103">Using 3D Viewer Beta on HoloLens (1st gen)</span></span>

<span data-ttu-id="7af33-104">3D-megjelenítő Bétaverzió lehetővé teszi a 3D modellek megtekintését HoloLens (1. generációs) verzióban.</span><span class="sxs-lookup"><span data-stu-id="7af33-104">3D Viewer Beta lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="7af33-105">A támogatott  .fbx fájlokat megnyithatja és megtekintheti Microsoft Edge, OneDrive és más alkalmazásokból.</span><span class="sxs-lookup"><span data-stu-id="7af33-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="7af33-106">Ez a cikk a modern Unity **3D-megjelenítő Beta** alkalmazásra vonatkozik, amely támogatja az .fbx fájlokat, és csak HoloLens (1. generációs) verzióban érhető el.</span><span class="sxs-lookup"><span data-stu-id="7af33-106">This article applies to the immersive Unity **3D Viewer Beta** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="7af33-107">Az 3D-megjelenítő  2. HoloLens-ben előre telepített alkalmazás támogatja az egyéni .glb 3D [](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) modellek megnyitását a vegyes valóság kezdőlapon (további részletekért lásd az eszközkövetelmények áttekintését.</span><span class="sxs-lookup"><span data-stu-id="7af33-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

>[!IMPORTANT]
><span data-ttu-id="7af33-108">Bár 3D-megjelenítő bétaverzió elérhető maradhat a Microsoft Store for HoloLens (1. generációs) verzióban, már nem aktív fejlesztés alatt áll, és már nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="7af33-108">While 3D Viewer Beta may remain available in the Microsoft Store for HoloLens (1st gen), it is no longer in active development and is no longer supported.</span></span>

<span data-ttu-id="7af33-109">Ha nem tudja megnyitni a 3D-s modellt a 3D-megjelenítő Beta kiadásban, vagy a 3D-modell bizonyos funkciói nem támogatottak, tekintse meg alább a támogatott tartalomsokajátságokat. [](#supported-content-specifications)</span><span class="sxs-lookup"><span data-stu-id="7af33-109">If you're having trouble opening a 3D model in 3D Viewer Beta, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications) below.</span></span>

<span data-ttu-id="7af33-110">A 3D-modellek a bétaverzióval való használatra való 3D-megjelenítő vagy optimalizálásáról lásd az alábbi [3D-s](#optimizing-3d-models-for-3d-viewer-beta) modellek 3D-megjelenítő bétaverzióhoz való optimalizálását.</span><span class="sxs-lookup"><span data-stu-id="7af33-110">To build or optimize 3D models for use with 3D Viewer Beta, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) below.</span></span>

<span data-ttu-id="7af33-111">A 3D-s modelleket kétféleképpen nyithatja meg a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7af33-111">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="7af33-112">További információért lásd az [FBX-fájlok HoloLens](#viewing-fbx-files-on-hololens) az alábbi táblázatot.</span><span class="sxs-lookup"><span data-stu-id="7af33-112">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.</span></span>

<span data-ttu-id="7af33-113">Ha a témakörök elolvasása után problémába fog kerülni, tekintse meg a [hibaelhárítással kapcsolatos alábbi](#troubleshooting) témakört.</span><span class="sxs-lookup"><span data-stu-id="7af33-113">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting) below.</span></span>

## <a name="supported-content-specifications"></a><span data-ttu-id="7af33-114">Támogatott tartalomsokajátok</span><span class="sxs-lookup"><span data-stu-id="7af33-114">Supported content specifications</span></span>

### <a name="file-format"></a><span data-ttu-id="7af33-115">Fájlformátum</span><span class="sxs-lookup"><span data-stu-id="7af33-115">File format</span></span>

- <span data-ttu-id="7af33-116">FBX formátum</span><span class="sxs-lookup"><span data-stu-id="7af33-116">FBX format</span></span>
- <span data-ttu-id="7af33-117">FBX-kiadás maximuma, 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="7af33-117">Maximum FBX release 2015.1.0</span></span>

### <a name="file-size"></a><span data-ttu-id="7af33-118">Fájlméret</span><span class="sxs-lookup"><span data-stu-id="7af33-118">File size</span></span>

- <span data-ttu-id="7af33-119">Minimum 5 KB</span><span class="sxs-lookup"><span data-stu-id="7af33-119">Minimum 5 KB</span></span>
- <span data-ttu-id="7af33-120">Legfeljebb 500 MB</span><span class="sxs-lookup"><span data-stu-id="7af33-120">Maximum 500 MB</span></span>

### <a name="geometry"></a><span data-ttu-id="7af33-121">Geometria</span><span class="sxs-lookup"><span data-stu-id="7af33-121">Geometry</span></span>

- <span data-ttu-id="7af33-122">Csak sokszögmodellek.</span><span class="sxs-lookup"><span data-stu-id="7af33-122">Polygonal models only.</span></span> <span data-ttu-id="7af33-123">Nincs alhálózati felület vagy NURB</span><span class="sxs-lookup"><span data-stu-id="7af33-123">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="7af33-124">Jobbos koordinátarendszer</span><span class="sxs-lookup"><span data-stu-id="7af33-124">Right-handed coordinate system</span></span>
- <span data-ttu-id="7af33-125">Az átalakítási mátrixok shearok nem támogatottak</span><span class="sxs-lookup"><span data-stu-id="7af33-125">Shear in transformation matrices is not supported</span></span>

### <a name="textures"></a><span data-ttu-id="7af33-126">Textúrák</span><span class="sxs-lookup"><span data-stu-id="7af33-126">Textures</span></span>

- <span data-ttu-id="7af33-127">A textúratérképeket be kell ágyazni az FBX-fájlba</span><span class="sxs-lookup"><span data-stu-id="7af33-127">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="7af33-128">Támogatott képformátumok</span><span class="sxs-lookup"><span data-stu-id="7af33-128">Supported image formats</span></span>
  - <span data-ttu-id="7af33-129">JPEG- és PNG-képek</span><span class="sxs-lookup"><span data-stu-id="7af33-129">JPEG and PNG images</span></span>
  - <span data-ttu-id="7af33-130">BMP-képek (24 bites RGB valódi szín)</span><span class="sxs-lookup"><span data-stu-id="7af33-130">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="7af33-131">TGA-képek (24 bites RGB és 32 bites RGBQ valódi szín)</span><span class="sxs-lookup"><span data-stu-id="7af33-131">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="7af33-132">A textúra maximális felbontása 2048x2048</span><span class="sxs-lookup"><span data-stu-id="7af33-132">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="7af33-133">Hálónként legfeljebb egy leképezés, egy normál térkép és egy tükrözési kockatérkép</span><span class="sxs-lookup"><span data-stu-id="7af33-133">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="7af33-134">A sima mintázatok alfa csatornája esetén a képpontok el lesznek vetve, ha az 50% alatti</span><span class="sxs-lookup"><span data-stu-id="7af33-134">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <a name="animation"></a><span data-ttu-id="7af33-135">Animáció</span><span class="sxs-lookup"><span data-stu-id="7af33-135">Animation</span></span>

- <span data-ttu-id="7af33-136">Méretezési/rotációs/fordítási animáció az egyes objektumokon</span><span class="sxs-lookup"><span data-stu-id="7af33-136">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="7af33-137">Skeletal (rigged) animáció lekicsinyítve</span><span class="sxs-lookup"><span data-stu-id="7af33-137">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="7af33-138">Csúcsonként legfeljebb 4 befolyásoló tényező</span><span class="sxs-lookup"><span data-stu-id="7af33-138">Maximum of 4 influences per vertex</span></span>

### <a name="materials"></a><span data-ttu-id="7af33-139">Anyagok</span><span class="sxs-lookup"><span data-stu-id="7af33-139">Materials</span></span>

- <span data-ttu-id="7af33-140">A Rendszer és a Pése anyagok támogatottak, amelyek módosítható paraméterekkel vannak támogatva</span><span class="sxs-lookup"><span data-stu-id="7af33-140">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="7af33-141">Támogatott anyagtulajdonságok a:</span><span class="sxs-lookup"><span data-stu-id="7af33-141">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="7af33-142">Fő textúra (RGB + Alfa teszt)</span><span class="sxs-lookup"><span data-stu-id="7af33-142">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="7af33-143">Color (RGB)</span><span class="sxs-lookup"><span data-stu-id="7af33-143">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="7af33-144">Környezeti szín (RGB)</span><span class="sxs-lookup"><span data-stu-id="7af33-144">Ambient Color (RGB)</span></span>
- <span data-ttu-id="7af33-145">A Pemet támogató anyagtulajdonságok</span><span class="sxs-lookup"><span data-stu-id="7af33-145">Supported material properties for Phong</span></span>
  - <span data-ttu-id="7af33-146">Fő textúra (RGB + Alfa teszt)</span><span class="sxs-lookup"><span data-stu-id="7af33-146">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="7af33-147">Color (RGB)</span><span class="sxs-lookup"><span data-stu-id="7af33-147">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="7af33-148">Környezeti szín (RGB)</span><span class="sxs-lookup"><span data-stu-id="7af33-148">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="7af33-149">Spekulatív szín (RGB)</span><span class="sxs-lookup"><span data-stu-id="7af33-149">Specular Color (RGB)</span></span>
  - <span data-ttu-id="7af33-150">Készség</span><span class="sxs-lookup"><span data-stu-id="7af33-150">Shininess</span></span>
  - <span data-ttu-id="7af33-151">Tükrözés</span><span class="sxs-lookup"><span data-stu-id="7af33-151">Reflectivity</span></span>
- <span data-ttu-id="7af33-152">Az egyéni anyagok nem támogatottak</span><span class="sxs-lookup"><span data-stu-id="7af33-152">Custom materials are not supported</span></span>
- <span data-ttu-id="7af33-153">Hálónként legfeljebb egy anyag</span><span class="sxs-lookup"><span data-stu-id="7af33-153">Maximum of one material per mesh</span></span>
- <span data-ttu-id="7af33-154">Legfeljebb egy anyagréteg</span><span class="sxs-lookup"><span data-stu-id="7af33-154">Maximum of one material layer</span></span>
- <span data-ttu-id="7af33-155">Fájlonként legfeljebb 8 anyag</span><span class="sxs-lookup"><span data-stu-id="7af33-155">Maximum of 8 materials per file</span></span>

### <a name="file-and-model-limitations"></a><span data-ttu-id="7af33-156">Fájl- és modellkorlátozások</span><span class="sxs-lookup"><span data-stu-id="7af33-156">File and model limitations</span></span>

<span data-ttu-id="7af33-157">A bétaverzióban egyidejűleg megnyitható modellek, csúcsok és hálók száma erősen korlátozza a fájlok méretét, valamint 3D-megjelenítő számát:</span><span class="sxs-lookup"><span data-stu-id="7af33-157">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta:</span></span>

- <span data-ttu-id="7af33-158">Modellenként 500 MB maximális fájlméret</span><span class="sxs-lookup"><span data-stu-id="7af33-158">500 MB maximum file size per model</span></span>
- <span data-ttu-id="7af33-159">Csúcsok: 600 000 az összes nyitott modellen kombinálva</span><span class="sxs-lookup"><span data-stu-id="7af33-159">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="7af33-160">Hálók: 1600 az összes nyitott modellen kombinálva</span><span class="sxs-lookup"><span data-stu-id="7af33-160">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="7af33-161">Egyszerre legfeljebb 40 nyitott modell</span><span class="sxs-lookup"><span data-stu-id="7af33-161">Maximum of 40 models open at one time</span></span>

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a><span data-ttu-id="7af33-162">3D modellek optimalizálása 3D-megjelenítő bétaverzióhoz</span><span class="sxs-lookup"><span data-stu-id="7af33-162">Optimizing 3D models for 3D Viewer Beta</span></span>

### <a name="special-considerations"></a><span data-ttu-id="7af33-163">Különleges szempontok</span><span class="sxs-lookup"><span data-stu-id="7af33-163">Special considerations</span></span>

- <span data-ttu-id="7af33-164">Kerülje a fekete anyagokat vagy a fekete területeket a textúratérképek között.</span><span class="sxs-lookup"><span data-stu-id="7af33-164">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="7af33-165">Hologramok fényből készült, így a HoloLens (a fény hiánya) átlátszóként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="7af33-165">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="7af33-166">Az FBX-be a létrehozási eszközből való exportálás előtt győződjön meg arról, hogy minden geometria látható és fel van oldva, és a geometriát tartalmazó rétegek nincsenek kikapcsolva vagy sablonosak.</span><span class="sxs-lookup"><span data-stu-id="7af33-166">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="7af33-167">A láthatóság nem teljesül.</span><span class="sxs-lookup"><span data-stu-id="7af33-167">Visibility is not respected.</span></span>
- <span data-ttu-id="7af33-168">Kerülje a csomópontok közötti nagyon nagy fordítási eltolásokat (például 100 000 egység).</span><span class="sxs-lookup"><span data-stu-id="7af33-168">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="7af33-169">Ez azt okozhatja, hogy a modell jittert vált ki, miközben áthelyezik, skálázják vagy elforgatják.</span><span class="sxs-lookup"><span data-stu-id="7af33-169">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <a name="performance-optimization"></a><span data-ttu-id="7af33-170">Teljesítményoptimalizálás</span><span class="sxs-lookup"><span data-stu-id="7af33-170">Performance optimization</span></span>

<span data-ttu-id="7af33-171">A legjobb eredmények elérése érdekében tartsa szem előtt a teljesítményt, amikor tartalmat hoz 3D-megjelenítő és érvényesít a HoloLens bétaverziós alkalmazásában.</span><span class="sxs-lookup"><span data-stu-id="7af33-171">Keep performance in mind while authoring content and validate in the 3D Viewer Beta app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="7af33-172">3D-megjelenítő bétaverzió valós időben renderel tartalmakat, és a teljesítményre HoloLens hardverképességek vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="7af33-172">3D Viewer Beta renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="7af33-173">A 3D-s modellekben számos olyan változó van, amely hatással lehet a teljesítményre.</span><span class="sxs-lookup"><span data-stu-id="7af33-173">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="7af33-174">3D-megjelenítő bétaverzió egy terhelésre vonatkozó figyelmeztetést fog mutatni, ha több mint 150 000 csúcspont vagy több mint 400 háló van.</span><span class="sxs-lookup"><span data-stu-id="7af33-174">3D Viewer Beta will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="7af33-175">Az animációk hatással lehetnek más nyitott modellek teljesítményére.</span><span class="sxs-lookup"><span data-stu-id="7af33-175">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="7af33-176">A bétaverzióban egyidejűleg megnyitható összes számmodell 3D-megjelenítő re, csúcspontra és hálóra is korlátozások vonatkoznak (lásd: Fájl- és [modellkorlátozások).](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="7af33-176">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="7af33-177">Ha a 3D modell a modell összetettsége miatt nem fut jól, fontolja meg a következőt:</span><span class="sxs-lookup"><span data-stu-id="7af33-177">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="7af33-178">Sokszögszám csökkentése</span><span class="sxs-lookup"><span data-stu-id="7af33-178">Reducing polygon count</span></span>
- <span data-ttu-id="7af33-179">A gombóék számának csökkentése a megjelölt animációban</span><span class="sxs-lookup"><span data-stu-id="7af33-179">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="7af33-180">Az önelzáródás elkerülése</span><span class="sxs-lookup"><span data-stu-id="7af33-180">Avoiding self-occlusion</span></span>

<span data-ttu-id="7af33-181">A bétaverzió támogatja a kétoldalas 3D-megjelenítő renderelést, bár teljesítménybeli okokból alapértelmezés szerint ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="7af33-181">Double-sided rendering is supported in 3D Viewer Beta, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="7af33-182">Ezt a Részletek oldal **Kétoldalas** gombjával **lehet bekapcsolni.**</span><span class="sxs-lookup"><span data-stu-id="7af33-182">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="7af33-183">A legjobb teljesítmény érdekében ne legyen szükség kétoldalas renderelésre a tartalomban.</span><span class="sxs-lookup"><span data-stu-id="7af33-183">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <a name="validating-your-3d-model"></a><span data-ttu-id="7af33-184">A 3D-modell érvényességének igazolása</span><span class="sxs-lookup"><span data-stu-id="7af33-184">Validating your 3D model</span></span>

<span data-ttu-id="7af33-185">Ellenőrizze a modellt úgy, hogy megnyitja 3D-megjelenítő bétaverzióban a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7af33-185">Validate your model by opening it in 3D Viewer Beta on HoloLens.</span></span> <span data-ttu-id="7af33-186">A Részletek **gombra** kattintva megtekintheti a modell jellemzőit és a nem támogatott tartalmakra vonatkozó figyelmeztetéseket (ha van ilyen).</span><span class="sxs-lookup"><span data-stu-id="7af33-186">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a><span data-ttu-id="7af33-187">3D-s modellek renderelése valós életből való dimenziókkal</span><span class="sxs-lookup"><span data-stu-id="7af33-187">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="7af33-188">Alapértelmezés szerint a 3D-megjelenítő Bétaverzió a felhasználóhoz képest kényelmes méretben és pozícióban jeleníti meg a 3D-modelleket.</span><span class="sxs-lookup"><span data-stu-id="7af33-188">By default, 3D Viewer Beta displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="7af33-189">Ha azonban egy 3D-s modell valós életből való méréssel való renderelése fontos (például amikor egy helyiségben értékeli a berendezésmodelleket), a tartalom létrehozója beállíthat egy jelzőt a fájl metaadataiban, hogy megakadályozza a modell átméretezését az alkalmazás és a felhasználó számára is.</span><span class="sxs-lookup"><span data-stu-id="7af33-189">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="7af33-190">A modell méretezésének megakadályozásához adjon hozzá egy logikai egyéni attribútumot a jelenet bármely objektumához, Microsoft_DisableScale állítsa true (igaz) értékre.</span><span class="sxs-lookup"><span data-stu-id="7af33-190">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="7af33-191">3D-megjelenítő Beta figyelembe veszi az FBX-fájlba be van ékelve az FbxSystemUnit adatokat.</span><span class="sxs-lookup"><span data-stu-id="7af33-191">3D Viewer Beta will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="7af33-192">A bétaverziós 3D-megjelenítő 1 méter FBX egységenként.</span><span class="sxs-lookup"><span data-stu-id="7af33-192">Scale in 3D Viewer Beta is 1 meter per FBX unit.</span></span>

## <a name="viewing-fbx-files-on-hololens"></a><span data-ttu-id="7af33-193">FBX-fájlok megtekintése a HoloLens</span><span class="sxs-lookup"><span data-stu-id="7af33-193">Viewing FBX files on HoloLens</span></span>

### <a name="open-an-fbx-file-from-microsoft-edge"></a><span data-ttu-id="7af33-194">Nyisson meg egy FBX-fájlt a Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7af33-194">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="7af33-195">Az FBX-fájlok közvetlenül egy webhelyről nyithatók meg a Microsoft Edge a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7af33-195">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="7af33-196">A Microsoft Edge keresse meg a megtekinteni kívánt FBX-fájlt tartalmazó weblapot.</span><span class="sxs-lookup"><span data-stu-id="7af33-196">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="7af33-197">Válassza ki a fájlt a letöltéshez.</span><span class="sxs-lookup"><span data-stu-id="7af33-197">Select the file to download it.</span></span>
1. <span data-ttu-id="7af33-198">Ha a letöltés befejeződött,  kattintson a Megnyitás gombra a Microsoft Edge a fájl bétaverzióban 3D-megjelenítő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7af33-198">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer Beta.</span></span>

<span data-ttu-id="7af33-199">A letöltött fájl később a Letöltések használatával érhető el és nyitható meg Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="7af33-199">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="7af33-200">A 3D-modell mentéséhez és a folyamatos hozzáférés biztosításához töltse le a fájlt a számítógépre, és mentse a saját OneDrive fiókjába.</span><span class="sxs-lookup"><span data-stu-id="7af33-200">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="7af33-201">A fájl ezután a OneDrive a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7af33-201">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="7af33-202">Egyes letölthető FBX-modellekkel elérhető webhelyek tömörített ZIP formátumban biztosítják őket.</span><span class="sxs-lookup"><span data-stu-id="7af33-202">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="7af33-203">3D-megjelenítő bétaverzió nem tudja közvetlenül megnyitni a ZIP-fájlokat.</span><span class="sxs-lookup"><span data-stu-id="7af33-203">3D Viewer Beta cannot open ZIP files directly.</span></span> <span data-ttu-id="7af33-204">Ehelyett a számítógépével bontsa ki az FBX-fájlt, és mentse a OneDrive fiókjába.</span><span class="sxs-lookup"><span data-stu-id="7af33-204">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="7af33-205">A fájl ezután a OneDrive a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7af33-205">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <a name="open-an-fbx-file-from-onedrive"></a><span data-ttu-id="7af33-206">FBX-fájl megnyitása a OneDrive</span><span class="sxs-lookup"><span data-stu-id="7af33-206">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="7af33-207">Az FBX-fájlok a OneDrive a OneDrive alkalmazással HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7af33-207">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="7af33-208">Győződjön meg arról, hogy OneDrive telepítette az Microsoft Store-alkalmazást a HoloLens-n, és hogy már feltöltötte az FBX-fájlt a OneDrive gépére.</span><span class="sxs-lookup"><span data-stu-id="7af33-208">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="7af33-209">A OneDrive az FBX-fájlok a HoloLens a 3D-megjelenítő Beta használatával kétféleképpen nyithatók meg:</span><span class="sxs-lookup"><span data-stu-id="7af33-209">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer Beta in one of two ways:</span></span>

- <span data-ttu-id="7af33-210">Indítsa OneDrive a HoloLens, és válassza ki az FBX-fájlt, hogy a bétaverzióban 3D-megjelenítő meg.</span><span class="sxs-lookup"><span data-stu-id="7af33-210">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer Beta.</span></span>
- <span data-ttu-id="7af33-211">Indítsa 3D-megjelenítő bétaverziót, koppintson a légi koppintással az eszköztár megjelenítéséhez, majd válassza a **Fájl megnyitása lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="7af33-211">Launch 3D Viewer Beta, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="7af33-212">OneDrive elindul, így kiválaszthatja az FBX-fájlt.</span><span class="sxs-lookup"><span data-stu-id="7af33-212">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7af33-213">Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="7af33-213">Troubleshooting</span></span>

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a><span data-ttu-id="7af33-214">3D-s modell megnyitásakor figyelmeztetés jelenik meg</span><span class="sxs-lookup"><span data-stu-id="7af33-214">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="7af33-215">Figyelmeztetés jelenik meg, ha olyan 3D modellt próbál megnyitni, amely a 3D-megjelenítő Beta által nem támogatott funkciókat tartalmaz, vagy ha a modell túl összetett, és ez hatással lehet a teljesítményre.</span><span class="sxs-lookup"><span data-stu-id="7af33-215">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer Beta, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="7af33-216">3D-megjelenítő bétaverzió továbbra is betölti a 3D modellt, de a teljesítmény vagy a vizualizációk hűsége sérülhet.</span><span class="sxs-lookup"><span data-stu-id="7af33-216">3D Viewer Beta will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="7af33-217">További információ: [Supported content specifications (Támogatott](#supported-content-specifications) tartalomsifikációk) és [Optimizing 3D models for 3D-megjelenítő Beta (3D-modellek optimalizálása 3D-megjelenítő bétaverzióhoz).](#optimizing-3d-models-for-3d-viewer-beta)</span><span class="sxs-lookup"><span data-stu-id="7af33-217">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a><span data-ttu-id="7af33-218">Egy figyelmeztetés jelenik meg, és a 3D-modell nem töltődik be</span><span class="sxs-lookup"><span data-stu-id="7af33-218">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="7af33-219">Hibaüzenet jelenik meg, ha 3D-megjelenítő Beta nem tud 3D-modellt betölteni összetettség vagy fájlméret miatt, vagy ha az FBX-fájl sérült vagy érvénytelen.</span><span class="sxs-lookup"><span data-stu-id="7af33-219">You will see an error message when 3D Viewer Beta cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="7af33-220">Akkor is megjelenik egy hibaüzenet, ha elérte az egyidejűleg megnyitható modellek, csúcsok vagy hálók teljes számára vonatkozó korlátot.</span><span class="sxs-lookup"><span data-stu-id="7af33-220">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="7af33-221">További információ: [Támogatott tartalomsifikációk](#supported-content-specifications) és [Fájl- és modellkorlátozások.](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="7af33-221">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a><span data-ttu-id="7af33-222">Betöltődik a 3D-modellem, de nem a várt módon jelenik meg</span><span class="sxs-lookup"><span data-stu-id="7af33-222">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="7af33-223">Ha a 3D-modell nem a várt módon jelenik meg 3D-megjelenítő bétaverzióban, koppintson a légi koppintással az eszköztár megjelenítéséhez, majd válassza a **Részletek lehetőséget.**</span><span class="sxs-lookup"><span data-stu-id="7af33-223">If your 3D model does not look as expected in 3D Viewer Beta, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="7af33-224">A bétaverzió által nem támogatott 3D-megjelenítő figyelmeztetésekként lesznek kiemelve.</span><span class="sxs-lookup"><span data-stu-id="7af33-224">Aspects of the file which are not supported by 3D Viewer Beta will be highlighted as warnings.</span></span>

<span data-ttu-id="7af33-225">A leggyakoribb probléma a hiányzó textúra, valószínűleg azért, mert nincsenek beágyazva az FBX-fájlba.</span><span class="sxs-lookup"><span data-stu-id="7af33-225">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="7af33-226">Ebben az esetben a modell fehéren jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="7af33-226">In this case, the model will appear white.</span></span> <span data-ttu-id="7af33-227">Ez a probléma a létrehozási folyamat során úgy hárítható el, ha a létrehozási eszközből az FBX-be exportál, és be van jelölve a beágyazási mintázatok beállítás.</span><span class="sxs-lookup"><span data-stu-id="7af33-227">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="7af33-228">További információ: [Supported content specifications (Támogatott](#supported-content-specifications) tartalomsifikációk) és [Optimizing 3D models for 3D-megjelenítő Beta (3D-modellek optimalizálása 3D-megjelenítő bétaverzióhoz).](#optimizing-3d-models-for-3d-viewer-beta)</span><span class="sxs-lookup"><span data-stu-id="7af33-228">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a><span data-ttu-id="7af33-229">Teljesítmény csökken a 3D-s modell megtekintése közben</span><span class="sxs-lookup"><span data-stu-id="7af33-229">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="7af33-230">A 3D-s modellek betöltésekor és megtekintésekor a teljesítményt befolyásolhatja a modell összetettsége, az egyidejűleg megnyitott modellek száma vagy az aktív animációkat bemutató modellek száma.</span><span class="sxs-lookup"><span data-stu-id="7af33-230">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="7af33-231">További információ: [3D-s](#optimizing-3d-models-for-3d-viewer-beta) modellek optimalizálása a 3D-megjelenítő és a fájl- [és modellkorlátozások alapján.](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="7af33-231">For more info, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a><span data-ttu-id="7af33-232">Amikor megnyitok egy FBX-fájlt a HoloLens, az nem nyílik meg a 3D-megjelenítő Bétaverzióban</span><span class="sxs-lookup"><span data-stu-id="7af33-232">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer Beta</span></span>

<span data-ttu-id="7af33-233">3D-megjelenítő bétaverzió telepítésekor a rendszer automatikusan társítja a .fbx fájlkiterjesztést.</span><span class="sxs-lookup"><span data-stu-id="7af33-233">3D Viewer Beta is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="7af33-234">Ha FBX-fájlt próbál megnyitni, és megjelenik egy párbeszédpanel, amely a Microsoft Store-hoz irányítja, akkor jelenleg nincs .fbx fájlkiterjesztéssel társított alkalmazás a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7af33-234">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="7af33-235">Ellenőrizze, hogy 3D-megjelenítő bétaverzió telepítve van-e.</span><span class="sxs-lookup"><span data-stu-id="7af33-235">Verify that 3D Viewer Beta is installed.</span></span> <span data-ttu-id="7af33-236">Ha nincs telepítve, töltse le a Microsoft Store a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7af33-236">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="7af33-237">Ha 3D-megjelenítő bétaverzió már telepítve van, indítsa el 3D-megjelenítő Bétaverziót, majd próbálja meg újra megnyitni a fájlt.</span><span class="sxs-lookup"><span data-stu-id="7af33-237">If 3D Viewer Beta is already installed, launch 3D Viewer Beta, then try opening the file again.</span></span> <span data-ttu-id="7af33-238">Ha a probléma továbbra is fennáll, távolítsa el és telepítse újra 3D-megjelenítő Bétaverziót.</span><span class="sxs-lookup"><span data-stu-id="7af33-238">If the issue persists, uninstall and reinstall 3D Viewer Beta.</span></span> <span data-ttu-id="7af33-239">Ez újra társítja az .fbx fájlkiterjesztést a 3D-megjelenítő Bétaverzióval.</span><span class="sxs-lookup"><span data-stu-id="7af33-239">This will re-associate the .fbx file extension with 3D Viewer Beta.</span></span>

<span data-ttu-id="7af33-240">Ha egy FBX-fájl megnyitásakor a 3D-megjelenítő Beta helyett egy másik alkalmazást nyit meg, az alkalmazás valószínűleg az 3D-megjelenítő Beta után lett telepítve, és átveszi a társítást az .fbx fájlkiterjesztéssel.</span><span class="sxs-lookup"><span data-stu-id="7af33-240">If attempting to open an FBX file opens an app other than 3D Viewer Beta, that app was likely installed after 3D Viewer Beta and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="7af33-241">Ha azt 3D-megjelenítő, hogy a bétaverzió .fbx fájlkiterjesztéssel legyen társítva, távolítsa el és telepítse újra 3D-megjelenítő Bétaverziót.</span><span class="sxs-lookup"><span data-stu-id="7af33-241">If you prefer 3D Viewer Beta to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer Beta.</span></span>

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a><span data-ttu-id="7af33-242">A Bétaverzió Fájl megnyitása 3D-megjelenítő gombja nem indít el alkalmazást</span><span class="sxs-lookup"><span data-stu-id="7af33-242">The Open File button in 3D Viewer Beta doesn't launch an app</span></span>

<span data-ttu-id="7af33-243">A **Fájl megnyitása gomb** megnyitja a fájlválasztó függvényhez társított alkalmazást a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7af33-243">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="7af33-244">Ha OneDrive van telepítve, a Fájl megnyitása **gombnak** OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7af33-244">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="7af33-245">Ha azonban jelenleg nincs alkalmazás társítva a HoloLens-on telepített fájlválasztó függvénnyel, a rendszer a Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="7af33-245">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="7af33-246">Ha a **Fájl megnyitása gomb** nem a OneDrive indít el, akkor az alkalmazás valószínűleg a OneDrive után lett telepítve, és átveszi a fájlválasztó függvény társítását.</span><span class="sxs-lookup"><span data-stu-id="7af33-246">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="7af33-247">Ha inkább a OneDrive szeretné indítani,  amikor a bétaverzióban a Fájl megnyitása 3D-megjelenítő gombra kattint, távolítsa el és telepítse újra a OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7af33-247">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer Beta, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="7af33-248">Ha a **Fájl megnyitása** gomb nem aktív, akkor lehetséges, hogy egyszerre elérte a bétaverzióban 3D-megjelenítő a modellek számára vonatkozó korlátot.</span><span class="sxs-lookup"><span data-stu-id="7af33-248">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer Beta at one time.</span></span> <span data-ttu-id="7af33-249">Ha a bétaverzióban 40 modell van 3D-megjelenítő, néhányat be kell zárnia, mielőtt további modelleket nyit meg.</span><span class="sxs-lookup"><span data-stu-id="7af33-249">If you have 40 models open in 3D Viewer Beta, you will need to close some before you will be able to open additional models.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7af33-250">További források</span><span class="sxs-lookup"><span data-stu-id="7af33-250">Additional resources</span></span>

- <span data-ttu-id="7af33-251">[Támogatási fórumok](http://forums.hololens.com/categories/3d-viewer-beta) – Csak archiválási célokra.</span><span class="sxs-lookup"><span data-stu-id="7af33-251">[Support forums](http://forums.hololens.com/categories/3d-viewer-beta) - For archival purposes only.</span></span> <span data-ttu-id="7af33-252">Ez a fórum már nem aktív.</span><span class="sxs-lookup"><span data-stu-id="7af33-252">This forum is no longer active.</span></span>
- [<span data-ttu-id="7af33-253">Harmadik féltől származó közlemények</span><span class="sxs-lookup"><span data-stu-id="7af33-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
