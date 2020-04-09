---
title: 'ER Usar dimensiones financieras como origen de datos (Parte 3: Diseño del informe)'
description: En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7bbbc81eaf8c13e8d13e30a0276e38453e07ead9
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142533"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="7d88a-103">ER Usar dimensiones financieras como origen de datos (Parte 3: Diseño del informe)</span><span class="sxs-lookup"><span data-stu-id="7d88a-103">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7d88a-104">En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER.</span><span class="sxs-lookup"><span data-stu-id="7d88a-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="7d88a-105">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="7d88a-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="7d88a-106">Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Usar dimensiones financieras como origen de datos (Parte 2: Asignación de modelo)".</span><span class="sxs-lookup"><span data-stu-id="7d88a-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="7d88a-107">Diseñar un informe para mostrar las dimensiones financieras</span><span class="sxs-lookup"><span data-stu-id="7d88a-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="7d88a-108">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="7d88a-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="7d88a-109">En el árbol, seleccione "Modelo de ejemplo de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="7d88a-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="7d88a-110">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="7d88a-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="7d88a-111">En el campo Nuevo, especifique "Formato basado en modelo de datos Modelo de ejemplo de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="7d88a-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="7d88a-112">Usar el modelo que se ha creado por adelantado como origen de datos para su nuevo informe.</span><span class="sxs-lookup"><span data-stu-id="7d88a-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="7d88a-113">En el campo Nombre, escriba "Informe del diario contable".</span><span class="sxs-lookup"><span data-stu-id="7d88a-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="7d88a-114">En el campo Definición del modelo de datos, seleccione Entrada.</span><span class="sxs-lookup"><span data-stu-id="7d88a-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="7d88a-115">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="7d88a-115">Click Create configuration.</span></span>
8. <span data-ttu-id="7d88a-116">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="7d88a-116">Click Designer.</span></span>
9. <span data-ttu-id="7d88a-117">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="7d88a-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="7d88a-118">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="7d88a-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="7d88a-119">Escriba "Raíz" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="7d88a-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="7d88a-120">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7d88a-120">Click OK.</span></span>
13. <span data-ttu-id="7d88a-121">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="7d88a-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="7d88a-122">En el árbol, seleccione XML\Atributo.</span><span class="sxs-lookup"><span data-stu-id="7d88a-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="7d88a-123">Escriba "Empresa" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="7d88a-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="7d88a-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7d88a-124">Click OK.</span></span>
17. <span data-ttu-id="7d88a-125">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="7d88a-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="7d88a-126">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="7d88a-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="7d88a-127">En el campo Nombre, escriba "Diario".</span><span class="sxs-lookup"><span data-stu-id="7d88a-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="7d88a-128">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7d88a-128">Click OK.</span></span>
21. <span data-ttu-id="7d88a-129">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="7d88a-130">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="7d88a-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="7d88a-131">En el árbol, seleccione XML\Atributo.</span><span class="sxs-lookup"><span data-stu-id="7d88a-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="7d88a-132">En el campo Nombre, escriba "Lote".</span><span class="sxs-lookup"><span data-stu-id="7d88a-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="7d88a-133">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7d88a-133">Click OK.</span></span>
26. <span data-ttu-id="7d88a-134">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="7d88a-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="7d88a-135">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="7d88a-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="7d88a-136">En el campo Nombre, escriba "Transacción".</span><span class="sxs-lookup"><span data-stu-id="7d88a-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="7d88a-137">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7d88a-137">Click OK.</span></span>
30. <span data-ttu-id="7d88a-138">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="7d88a-139">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="7d88a-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="7d88a-140">En el árbol, seleccione XML\Atributo.</span><span class="sxs-lookup"><span data-stu-id="7d88a-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="7d88a-141">En el campo Nombre, escriba "Asiento".</span><span class="sxs-lookup"><span data-stu-id="7d88a-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="7d88a-142">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7d88a-142">Click OK.</span></span>
35. <span data-ttu-id="7d88a-143">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="7d88a-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="7d88a-144">En el campo Nombre, escriba "Fecha".</span><span class="sxs-lookup"><span data-stu-id="7d88a-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="7d88a-145">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7d88a-145">Click OK.</span></span>
38. <span data-ttu-id="7d88a-146">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="7d88a-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="7d88a-147">En el campo Nombre, escriba "Divisa".</span><span class="sxs-lookup"><span data-stu-id="7d88a-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="7d88a-148">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7d88a-148">Click OK.</span></span>
41. <span data-ttu-id="7d88a-149">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="7d88a-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="7d88a-150">En el campo Nombre, escriba "Dt".</span><span class="sxs-lookup"><span data-stu-id="7d88a-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="7d88a-151">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7d88a-151">Click OK.</span></span>
44. <span data-ttu-id="7d88a-152">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="7d88a-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="7d88a-153">En el campo Nombre, escriba "Ct".</span><span class="sxs-lookup"><span data-stu-id="7d88a-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="7d88a-154">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7d88a-154">Click OK.</span></span>
47. <span data-ttu-id="7d88a-155">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="7d88a-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="7d88a-156">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="7d88a-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="7d88a-157">En el campo Nombre, escriba "Dimensiones".</span><span class="sxs-lookup"><span data-stu-id="7d88a-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="7d88a-158">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7d88a-158">Click OK.</span></span>
51. <span data-ttu-id="7d88a-159">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dimensiones: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="7d88a-160">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="7d88a-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="7d88a-161">En el árbol, seleccione XML\Atributo.</span><span class="sxs-lookup"><span data-stu-id="7d88a-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="7d88a-162">En el campo Nombre, escriba "Código".</span><span class="sxs-lookup"><span data-stu-id="7d88a-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="7d88a-163">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7d88a-163">Click OK.</span></span>
56. <span data-ttu-id="7d88a-164">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="7d88a-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="7d88a-165">En el campo Nombre, escriba "Valor".</span><span class="sxs-lookup"><span data-stu-id="7d88a-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="7d88a-166">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7d88a-166">Click OK.</span></span>
59. <span data-ttu-id="7d88a-167">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="7d88a-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="7d88a-168">En el campo Nombre, escriba "Desc".</span><span class="sxs-lookup"><span data-stu-id="7d88a-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="7d88a-169">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7d88a-169">Click OK.</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="7d88a-170">Asignar elementos del informe a orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="7d88a-170">Map report elements to data sources</span></span>
1. <span data-ttu-id="7d88a-171">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="7d88a-171">Click the Mapping tab.</span></span>
2. <span data-ttu-id="7d88a-172">En el árbol, expanda "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="7d88a-172">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="7d88a-173">En el árbol, expanda "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="7d88a-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="7d88a-174">En el árbol, expanda "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="7d88a-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="7d88a-175">En el árbol, expanda "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Datos de dimensiones: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="7d88a-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="7d88a-176">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dimensiones: Elemento XML\Desc: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-176">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="7d88a-177">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Datos de dimensiones: Lista de registros\Descripción: Cadena".</span><span class="sxs-lookup"><span data-stu-id="7d88a-177">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="7d88a-178">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="7d88a-178">Click Bind.</span></span>
9. <span data-ttu-id="7d88a-179">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dimensiones: Elemento XML\Valor: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-179">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="7d88a-180">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Datos de dimensiones: Lista de registros\Código: Cadena".</span><span class="sxs-lookup"><span data-stu-id="7d88a-180">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="7d88a-181">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="7d88a-181">Click Bind.</span></span>
12. <span data-ttu-id="7d88a-182">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dimensiones: Elemento XML\Código: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-182">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="7d88a-183">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Datos de dimensiones: Lista de registros\Nombre: Cadena".</span><span class="sxs-lookup"><span data-stu-id="7d88a-183">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="7d88a-184">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="7d88a-184">Click Bind.</span></span>
15. <span data-ttu-id="7d88a-185">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Datos de dimensiones: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="7d88a-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="7d88a-186">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dimensiones: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-186">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="7d88a-187">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="7d88a-187">Click Bind.</span></span>
18. <span data-ttu-id="7d88a-188">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Ct: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="7d88a-189">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Crédito: Real".</span><span class="sxs-lookup"><span data-stu-id="7d88a-189">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="7d88a-190">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="7d88a-190">Click Bind.</span></span>
21. <span data-ttu-id="7d88a-191">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dt: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-191">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="7d88a-192">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Débito: Real".</span><span class="sxs-lookup"><span data-stu-id="7d88a-192">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="7d88a-193">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="7d88a-193">Click Bind.</span></span>
24. <span data-ttu-id="7d88a-194">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Divisa: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-194">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="7d88a-195">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Divisa: Cadena".</span><span class="sxs-lookup"><span data-stu-id="7d88a-195">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="7d88a-196">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="7d88a-196">Click Bind.</span></span>
27. <span data-ttu-id="7d88a-197">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Fecha: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-197">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="7d88a-198">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Fecha: Fecha".</span><span class="sxs-lookup"><span data-stu-id="7d88a-198">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="7d88a-199">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="7d88a-199">Click Bind.</span></span>
30. <span data-ttu-id="7d88a-200">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Asiento: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-200">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="7d88a-201">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Asiento: Cadena".</span><span class="sxs-lookup"><span data-stu-id="7d88a-201">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="7d88a-202">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="7d88a-202">Click Bind.</span></span>
33. <span data-ttu-id="7d88a-203">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-203">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="7d88a-204">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="7d88a-204">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="7d88a-205">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="7d88a-205">Click Bind.</span></span>
36. <span data-ttu-id="7d88a-206">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Lote: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-206">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="7d88a-207">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Lote: Cadena".</span><span class="sxs-lookup"><span data-stu-id="7d88a-207">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="7d88a-208">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="7d88a-208">Click Bind.</span></span>
39. <span data-ttu-id="7d88a-209">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-209">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="7d88a-210">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="7d88a-210">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="7d88a-211">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="7d88a-211">Click Bind.</span></span>
42. <span data-ttu-id="7d88a-212">En el árbol, seleccione "Raíz: Elemento XML\Empresa: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="7d88a-212">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="7d88a-213">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Empresa: Cadena".</span><span class="sxs-lookup"><span data-stu-id="7d88a-213">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="7d88a-214">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="7d88a-214">Click Bind.</span></span>
45. <span data-ttu-id="7d88a-215">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="7d88a-215">Click Save.</span></span>
46. <span data-ttu-id="7d88a-216">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7d88a-216">Close the page.</span></span>

