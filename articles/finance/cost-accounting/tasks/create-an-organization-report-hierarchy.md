---
title: Creación o modificación de una jerarquía de informes
description: Utilice este procedimiento para crear una jerarquía de informes para los informes de la organización.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 57203a7ddbacd631cbf800fb3a98e35a485cb74f
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976268"
---
# <a name="create-an-organization-report-hierarchy"></a><span data-ttu-id="ad2ff-103">Creación o modificación de una jerarquía de informes</span><span class="sxs-lookup"><span data-stu-id="ad2ff-103">Create an organization report hierarchy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ad2ff-104">Utilice este procedimiento para crear una jerarquía de informes para los informes de la organización.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-104">Use this procedure to create a report hierarchy for organization reporting.</span></span> <span data-ttu-id="ad2ff-105">El propósito de este registro es orientarle en la jerarquía de dimensiones de modo que pueda continuar hasta que se cree la estructura completa de informes de la organización.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-105">The purpose of this recording is to guide you through the dimension hierarchy so that you can continue until the whole organization reporting structure is created.</span></span> <span data-ttu-id="ad2ff-106">Este registro usa la empresa USP2 con los datos para demostración.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="ad2ff-107">Vaya a Contabilidad de costes > Dimensiones > Jerarquías de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-107">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="ad2ff-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-108">Click New.</span></span>
3. <span data-ttu-id="ad2ff-109">En el campo de HierarchyTypeComboBox, seleccione “Jerarquía de clasificación de dimensiones”.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-109">In the HierarchyTypeComboBox field, select 'Dimension classification hierarchy'.</span></span>
    * <span data-ttu-id="ad2ff-110">Seleccione Jerarquía de clasificación de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-110">Select Dimension classification hierarchy.</span></span> <span data-ttu-id="ad2ff-111">El tipo Jerarquía de clasificación de dimensiones se usa para definir reglas y fines de notificación.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-111">The Dimension classification hierarchy type is used to define rules and for reporting purposes.</span></span> <span data-ttu-id="ad2ff-112">Admite todas las dimensiones, como objetos de coste, elementos de coste y dimensiones estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-112">It supports all dimensions, such as cost objects, cost elements, and statistical dimensions.</span></span>  
4. <span data-ttu-id="ad2ff-113">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-113">Click Create.</span></span>
5. <span data-ttu-id="ad2ff-114">En el campo Nombre de jerarquía de dimensiones, escriba "Organización USP2".</span><span class="sxs-lookup"><span data-stu-id="ad2ff-114">In the Dimension hierarchy name field, type 'Oganization USP2'.</span></span>
6. <span data-ttu-id="ad2ff-115">En el campo Dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-115">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="ad2ff-116">Seleccione Centros de coste.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-116">Select Cost centers.</span></span>  
7. <span data-ttu-id="ad2ff-117">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-117">Click Save.</span></span>
8. <span data-ttu-id="ad2ff-118">Haga clic en Ver jerarquía.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-118">Click View hierarchy.</span></span>
9. <span data-ttu-id="ad2ff-119">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-119">Click New.</span></span>
10. <span data-ttu-id="ad2ff-120">En el campo Nombre de nodo, escriba "Director general".</span><span class="sxs-lookup"><span data-stu-id="ad2ff-120">In the Node name field, type 'CEO'.</span></span>
11. <span data-ttu-id="ad2ff-121">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-121">Click Save.</span></span>
12. <span data-ttu-id="ad2ff-122">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-122">Click New.</span></span>
13. <span data-ttu-id="ad2ff-123">En el campo Nombre de nodo, escriba "Centros de coste de director general".</span><span class="sxs-lookup"><span data-stu-id="ad2ff-123">In the Node name field, type 'CEO cost centers'.</span></span>
14. <span data-ttu-id="ad2ff-124">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-124">Click Save.</span></span>
15. <span data-ttu-id="ad2ff-125">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-125">Click New.</span></span>
16. <span data-ttu-id="ad2ff-126">En el campo Nombre de nodo, escriba "Región este".</span><span class="sxs-lookup"><span data-stu-id="ad2ff-126">In the Node name field, type 'Region East'.</span></span>
17. <span data-ttu-id="ad2ff-127">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-127">Click Save.</span></span>
18. <span data-ttu-id="ad2ff-128">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-128">Click New.</span></span>
19. <span data-ttu-id="ad2ff-129">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-129">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="ad2ff-130">En el campo Desde miembro de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-130">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="ad2ff-131">Seleccione el miembro de dimensión que se corresponde con el nodo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-131">Select the dimension member that corresponds to the node.</span></span>  
21. <span data-ttu-id="ad2ff-132">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-132">Click Save.</span></span>
22. <span data-ttu-id="ad2ff-133">En el árbol, seleccione “Organización USP2\Director general\Director general centros de coste".</span><span class="sxs-lookup"><span data-stu-id="ad2ff-133">In the tree, select 'Oganization USP2\CEO\CEO cost centers'.</span></span>
23. <span data-ttu-id="ad2ff-134">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-134">Click New.</span></span>
24. <span data-ttu-id="ad2ff-135">En el campo Nombre de nodo, escriba "Región oeste".</span><span class="sxs-lookup"><span data-stu-id="ad2ff-135">In the Node name field, type 'Region West'.</span></span>
25. <span data-ttu-id="ad2ff-136">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-136">Click Save.</span></span>
26. <span data-ttu-id="ad2ff-137">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-137">Click New.</span></span>
27. <span data-ttu-id="ad2ff-138">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-138">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="ad2ff-139">En el campo Desde miembro de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-139">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="ad2ff-140">Seleccione el miembro de dimensión que se corresponde con el nodo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-140">Select the dimension member that corresponds to the node.</span></span>  
29. <span data-ttu-id="ad2ff-141">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-141">Click Save.</span></span>
30. <span data-ttu-id="ad2ff-142">En el árbol, seleccione "Organización USP2\Director general".</span><span class="sxs-lookup"><span data-stu-id="ad2ff-142">In the tree, select 'Oganization USP2\CEO'.</span></span>
31. <span data-ttu-id="ad2ff-143">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-143">Click New.</span></span>
32. <span data-ttu-id="ad2ff-144">En el campo Nombre de nodo, escriba "Centros de coste de director financiero“.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-144">In the Node name field, type 'CFO cost centers'.</span></span>
33. <span data-ttu-id="ad2ff-145">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-145">Click Save.</span></span>
34. <span data-ttu-id="ad2ff-146">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-146">Click New.</span></span>
35. <span data-ttu-id="ad2ff-147">En el campo Nombre de nodo, escriba "Campaña de marketing".</span><span class="sxs-lookup"><span data-stu-id="ad2ff-147">In the Node name field, type 'Marketing campa'.</span></span>
36. <span data-ttu-id="ad2ff-148">En el campo Nombre de nodo, escriba "Campaña de marketing".</span><span class="sxs-lookup"><span data-stu-id="ad2ff-148">In the Node name field, type 'Marketing campaign'.</span></span>
37. <span data-ttu-id="ad2ff-149">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-149">Click Save.</span></span>
38. <span data-ttu-id="ad2ff-150">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-150">Click New.</span></span>
39. <span data-ttu-id="ad2ff-151">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-151">In the list, mark the selected row.</span></span>
40. <span data-ttu-id="ad2ff-152">En el campo Desde miembro de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-152">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="ad2ff-153">Seleccione el miembro de dimensión que se corresponde con el nodo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-153">Select the dimension member that corresponds to the node.</span></span>  
41. <span data-ttu-id="ad2ff-154">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-154">Click Save.</span></span>
42. <span data-ttu-id="ad2ff-155">En el árbol, seleccione 'Organización USP2\Director general\Director general centros de coste'.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-155">In the tree, select 'Organization USP2\CEO\CFO cost centers'.</span></span>
43. <span data-ttu-id="ad2ff-156">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-156">Click New.</span></span>
44. <span data-ttu-id="ad2ff-157">En el campo Nombre de nodo, escriba "Ferias de muestras".</span><span class="sxs-lookup"><span data-stu-id="ad2ff-157">In the Node name field, type 'Trade shows'.</span></span>
45. <span data-ttu-id="ad2ff-158">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-158">Click Save.</span></span>
46. <span data-ttu-id="ad2ff-159">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-159">Click New.</span></span>
47. <span data-ttu-id="ad2ff-160">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-160">In the list, mark the selected row.</span></span>
48. <span data-ttu-id="ad2ff-161">En el campo Desde miembro de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-161">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="ad2ff-162">Seleccione el miembro de dimensión que se corresponde con el nodo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-162">Select the dimension member that corresponds to the node.</span></span>  
49. <span data-ttu-id="ad2ff-163">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-163">Click Save.</span></span>
50. <span data-ttu-id="ad2ff-164">En el árbol, seleccione "Organización USP2\Director general".</span><span class="sxs-lookup"><span data-stu-id="ad2ff-164">In the tree, select 'Oganization USP2\CEO'.</span></span>
51. <span data-ttu-id="ad2ff-165">En el campo Nombre de nodo, escriba "Centros de coste de director de información".</span><span class="sxs-lookup"><span data-stu-id="ad2ff-165">In the Node name field, type 'CIO cost centers'.</span></span>
52. <span data-ttu-id="ad2ff-166">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-166">Click Save.</span></span>
53. <span data-ttu-id="ad2ff-167">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-167">Click New.</span></span>
54. <span data-ttu-id="ad2ff-168">En el campo Nombre de nodo, escriba "Centros de llamadas".</span><span class="sxs-lookup"><span data-stu-id="ad2ff-168">In the Node name field, type 'Call centers'.</span></span>
55. <span data-ttu-id="ad2ff-169">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-169">Click Save.</span></span>
56. <span data-ttu-id="ad2ff-170">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-170">Click New.</span></span>
57. <span data-ttu-id="ad2ff-171">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-171">In the list, mark the selected row.</span></span>
58. <span data-ttu-id="ad2ff-172">En el campo Desde miembro de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-172">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="ad2ff-173">Seleccione el miembro de dimensión que se corresponde con el nodo.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-173">Select the dimension member that corresponds to the node.</span></span>  
59. <span data-ttu-id="ad2ff-174">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-174">Click Save.</span></span>

