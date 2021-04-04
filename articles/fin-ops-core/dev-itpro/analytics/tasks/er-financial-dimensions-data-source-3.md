---
title: 'ER Usar dimensiones financieras como origen de datos (Parte 3: Diseño del informe)'
description: Este tema describe cómo configurar un modelo de informes electrónicos (ER) para usar dimensiones financieras como origen de datos para informes ER. (Parte 3)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a9594a12c28109d80c6ee07a9ee38f4923963dca
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565247"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="72709-104">ER Usar dimensiones financieras como origen de datos (Parte 3: Diseño del informe)</span><span class="sxs-lookup"><span data-stu-id="72709-104">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="72709-105">En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER.</span><span class="sxs-lookup"><span data-stu-id="72709-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="72709-106">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="72709-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="72709-107">Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Usar dimensiones financieras como origen de datos (Parte 2: Asignación de modelo)".</span><span class="sxs-lookup"><span data-stu-id="72709-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="72709-108">Diseñar un informe para mostrar las dimensiones financieras</span><span class="sxs-lookup"><span data-stu-id="72709-108">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="72709-109">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="72709-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="72709-110">En el árbol, seleccione "Modelo de ejemplo de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="72709-110">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="72709-111">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="72709-111">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="72709-112">En el campo Nuevo, especifique "Formato basado en modelo de datos Modelo de ejemplo de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="72709-112">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="72709-113">Usar el modelo que se ha creado por adelantado como origen de datos para su nuevo informe.</span><span class="sxs-lookup"><span data-stu-id="72709-113">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="72709-114">En el campo Nombre, escriba "Informe del diario contable".</span><span class="sxs-lookup"><span data-stu-id="72709-114">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="72709-115">En el campo Definición del modelo de datos, seleccione Entrada.</span><span class="sxs-lookup"><span data-stu-id="72709-115">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="72709-116">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="72709-116">Click Create configuration.</span></span>
8. <span data-ttu-id="72709-117">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="72709-117">Click Designer.</span></span>
9. <span data-ttu-id="72709-118">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="72709-118">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="72709-119">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="72709-119">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="72709-120">Escriba "Raíz" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="72709-120">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="72709-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="72709-121">Click OK.</span></span>
13. <span data-ttu-id="72709-122">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="72709-122">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="72709-123">En el árbol, seleccione XML\Atributo.</span><span class="sxs-lookup"><span data-stu-id="72709-123">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="72709-124">Escriba "Empresa" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="72709-124">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="72709-125">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="72709-125">Click OK.</span></span>
17. <span data-ttu-id="72709-126">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="72709-126">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="72709-127">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="72709-127">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="72709-128">En el campo Nombre, escriba "Diario".</span><span class="sxs-lookup"><span data-stu-id="72709-128">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="72709-129">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="72709-129">Click OK.</span></span>
21. <span data-ttu-id="72709-130">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="72709-130">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="72709-131">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="72709-131">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="72709-132">En el árbol, seleccione XML\Atributo.</span><span class="sxs-lookup"><span data-stu-id="72709-132">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="72709-133">En el campo Nombre, escriba "Lote".</span><span class="sxs-lookup"><span data-stu-id="72709-133">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="72709-134">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="72709-134">Click OK.</span></span>
26. <span data-ttu-id="72709-135">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="72709-135">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="72709-136">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="72709-136">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="72709-137">En el campo Nombre, escriba "Transacción".</span><span class="sxs-lookup"><span data-stu-id="72709-137">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="72709-138">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="72709-138">Click OK.</span></span>
30. <span data-ttu-id="72709-139">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="72709-139">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="72709-140">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="72709-140">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="72709-141">En el árbol, seleccione XML\Atributo.</span><span class="sxs-lookup"><span data-stu-id="72709-141">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="72709-142">En el campo Nombre, escriba "Asiento".</span><span class="sxs-lookup"><span data-stu-id="72709-142">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="72709-143">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="72709-143">Click OK.</span></span>
35. <span data-ttu-id="72709-144">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="72709-144">Click Add Attribute.</span></span>
36. <span data-ttu-id="72709-145">En el campo Nombre, escriba "Fecha".</span><span class="sxs-lookup"><span data-stu-id="72709-145">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="72709-146">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="72709-146">Click OK.</span></span>
38. <span data-ttu-id="72709-147">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="72709-147">Click Add Attribute.</span></span>
39. <span data-ttu-id="72709-148">En el campo Nombre, escriba "Divisa".</span><span class="sxs-lookup"><span data-stu-id="72709-148">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="72709-149">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="72709-149">Click OK.</span></span>
41. <span data-ttu-id="72709-150">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="72709-150">Click Add Attribute.</span></span>
42. <span data-ttu-id="72709-151">En el campo Nombre, escriba "Dt".</span><span class="sxs-lookup"><span data-stu-id="72709-151">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="72709-152">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="72709-152">Click OK.</span></span>
44. <span data-ttu-id="72709-153">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="72709-153">Click Add Attribute.</span></span>
45. <span data-ttu-id="72709-154">En el campo Nombre, escriba "Ct".</span><span class="sxs-lookup"><span data-stu-id="72709-154">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="72709-155">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="72709-155">Click OK.</span></span>
47. <span data-ttu-id="72709-156">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="72709-156">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="72709-157">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="72709-157">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="72709-158">En el campo Nombre, escriba "Dimensiones".</span><span class="sxs-lookup"><span data-stu-id="72709-158">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="72709-159">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="72709-159">Click OK.</span></span>
51. <span data-ttu-id="72709-160">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dimensiones: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="72709-160">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="72709-161">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="72709-161">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="72709-162">En el árbol, seleccione XML\Atributo.</span><span class="sxs-lookup"><span data-stu-id="72709-162">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="72709-163">En el campo Nombre, escriba "Código".</span><span class="sxs-lookup"><span data-stu-id="72709-163">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="72709-164">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="72709-164">Click OK.</span></span>
56. <span data-ttu-id="72709-165">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="72709-165">Click Add Attribute.</span></span>
57. <span data-ttu-id="72709-166">En el campo Nombre, escriba "Valor".</span><span class="sxs-lookup"><span data-stu-id="72709-166">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="72709-167">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="72709-167">Click OK.</span></span>
59. <span data-ttu-id="72709-168">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="72709-168">Click Add Attribute.</span></span>
60. <span data-ttu-id="72709-169">En el campo Nombre, escriba "Desc".</span><span class="sxs-lookup"><span data-stu-id="72709-169">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="72709-170">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="72709-170">Click OK.</span></span>
<span data-ttu-id="72709-171">![Página de diseñador de operaciones de ER](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="72709-171">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="72709-172">Asignar elementos del informe a orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="72709-172">Map report elements to data sources</span></span>
1. <span data-ttu-id="72709-173">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="72709-173">Click the Mapping tab.</span></span>
2. <span data-ttu-id="72709-174">En el árbol, expanda "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="72709-174">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="72709-175">En el árbol, expanda "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="72709-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="72709-176">En el árbol, expanda "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="72709-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="72709-177">En el árbol, expanda "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Datos de dimensiones: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="72709-177">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="72709-178">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dimensiones: Elemento XML\Desc: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="72709-178">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="72709-179">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Datos de dimensiones: Lista de registros\Descripción: Cadena".</span><span class="sxs-lookup"><span data-stu-id="72709-179">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="72709-180">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="72709-180">Click Bind.</span></span>
9. <span data-ttu-id="72709-181">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dimensiones: Elemento XML\Valor: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="72709-181">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="72709-182">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Datos de dimensiones: Lista de registros\Código: Cadena".</span><span class="sxs-lookup"><span data-stu-id="72709-182">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="72709-183">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="72709-183">Click Bind.</span></span>
12. <span data-ttu-id="72709-184">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dimensiones: Elemento XML\Código: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="72709-184">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="72709-185">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Datos de dimensiones: Lista de registros\Nombre: Cadena".</span><span class="sxs-lookup"><span data-stu-id="72709-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="72709-186">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="72709-186">Click Bind.</span></span>
15. <span data-ttu-id="72709-187">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Datos de dimensiones: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="72709-187">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="72709-188">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dimensiones: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="72709-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="72709-189">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="72709-189">Click Bind.</span></span>
18. <span data-ttu-id="72709-190">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Ct: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="72709-190">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="72709-191">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Crédito: Real".</span><span class="sxs-lookup"><span data-stu-id="72709-191">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="72709-192">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="72709-192">Click Bind.</span></span>
21. <span data-ttu-id="72709-193">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dt: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="72709-193">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="72709-194">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Débito: Real".</span><span class="sxs-lookup"><span data-stu-id="72709-194">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="72709-195">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="72709-195">Click Bind.</span></span>
24. <span data-ttu-id="72709-196">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Divisa: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="72709-196">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="72709-197">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Divisa: Cadena".</span><span class="sxs-lookup"><span data-stu-id="72709-197">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="72709-198">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="72709-198">Click Bind.</span></span>
27. <span data-ttu-id="72709-199">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Fecha: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="72709-199">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="72709-200">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Fecha: Fecha".</span><span class="sxs-lookup"><span data-stu-id="72709-200">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="72709-201">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="72709-201">Click Bind.</span></span>
30. <span data-ttu-id="72709-202">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Asiento: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="72709-202">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="72709-203">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Asiento: Cadena".</span><span class="sxs-lookup"><span data-stu-id="72709-203">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="72709-204">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="72709-204">Click Bind.</span></span>
33. <span data-ttu-id="72709-205">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="72709-205">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="72709-206">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="72709-206">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="72709-207">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="72709-207">Click Bind.</span></span>
36. <span data-ttu-id="72709-208">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Lote: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="72709-208">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="72709-209">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Lote: Cadena".</span><span class="sxs-lookup"><span data-stu-id="72709-209">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="72709-210">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="72709-210">Click Bind.</span></span>
39. <span data-ttu-id="72709-211">En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="72709-211">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="72709-212">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="72709-212">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="72709-213">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="72709-213">Click Bind.</span></span>
42. <span data-ttu-id="72709-214">En el árbol, seleccione "Raíz: Elemento XML\Empresa: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="72709-214">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="72709-215">En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Empresa: Cadena".</span><span class="sxs-lookup"><span data-stu-id="72709-215">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="72709-216">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="72709-216">Click Bind.</span></span>
45. <span data-ttu-id="72709-217">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="72709-217">Click Save.</span></span>
46. <span data-ttu-id="72709-218">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="72709-218">Close the page.</span></span>
<span data-ttu-id="72709-219">![Página de diseñador de operaciones de ER](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="72709-219">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]