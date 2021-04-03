---
title: 'ER Usar dimensiones financieras como origen de datos (Parte 1: Modelo de datos de diseño)'
description: Este tema describe cómo configurar un modelo de informes electrónicos (ER) para usar dimensiones financieras como origen de datos para informes ER. (Parte 1)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b5ecae444d80698c03ac050b49894daa1b090f74
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570201"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a><span data-ttu-id="22ea3-104">ER Usar dimensiones financieras como origen de datos (Parte 1: Modelo de datos de diseño)</span><span class="sxs-lookup"><span data-stu-id="22ea3-104">ER Use financial dimensions as a data source (Part 1 - Design data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="22ea3-105">En los pasos siguientes se explica cómo un administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER.</span><span class="sxs-lookup"><span data-stu-id="22ea3-105">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="22ea3-106">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="22ea3-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="22ea3-107">Para completar estos pasos, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".</span><span class="sxs-lookup"><span data-stu-id="22ea3-107">To complete these steps, you must first complete the steps in the procedure, "Create a configuration provider and mark it as active".</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="22ea3-108">Crear un nuevo modelo de datos</span><span class="sxs-lookup"><span data-stu-id="22ea3-108">Create a new data model</span></span>
1. <span data-ttu-id="22ea3-109">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="22ea3-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="22ea3-110">Asegúrese de que “Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="22ea3-110">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="22ea3-111">está disponible y marcado como activo.</span><span class="sxs-lookup"><span data-stu-id="22ea3-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="22ea3-112">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="22ea3-112">Click Reporting configurations.</span></span>
3. <span data-ttu-id="22ea3-113">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-113">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="22ea3-114">En el campo Nombre, escriba "Modelo de ejemplo de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="22ea3-114">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="22ea3-115">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="22ea3-115">Click Create configuration.</span></span>
6. <span data-ttu-id="22ea3-116">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="22ea3-116">Click Designer.</span></span>
7. <span data-ttu-id="22ea3-117">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="22ea3-118">En el campo Nombre, escriba "Entrada".</span><span class="sxs-lookup"><span data-stu-id="22ea3-118">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="22ea3-119">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-119">Click Add.</span></span>
10. <span data-ttu-id="22ea3-120">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-120">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="22ea3-121">Escriba "Empresa" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="22ea3-121">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="22ea3-122">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-122">Click Add.</span></span>
    * <span data-ttu-id="22ea3-123">Agregaremos nuestro modelo a una lista de registro nuevo.</span><span class="sxs-lookup"><span data-stu-id="22ea3-123">We will add to our model a new record list.</span></span> <span data-ttu-id="22ea3-124">Esta lista expondrá (para cualquier informe ER que utilice este modelo como origen de datos) los valores de dimensiones financieras seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="22ea3-124">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="22ea3-125">Cada dimensión financiera se mostrará en esta lista como registro con los campos adecuados que representan el valor de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="22ea3-125">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's setting.</span></span>  
13. <span data-ttu-id="22ea3-126">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-126">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="22ea3-127">En el campo Nombre, escriba "Configuración de dimensiones".</span><span class="sxs-lookup"><span data-stu-id="22ea3-127">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="22ea3-128">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="22ea3-128">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="22ea3-129">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-129">Click Add.</span></span>
17. <span data-ttu-id="22ea3-130">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-130">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="22ea3-131">En el campo Nombre, escriba "Código".</span><span class="sxs-lookup"><span data-stu-id="22ea3-131">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="22ea3-132">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="22ea3-132">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="22ea3-133">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-133">Click Add.</span></span>
21. <span data-ttu-id="22ea3-134">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-134">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="22ea3-135">En el campo Nombre, escriba "Nombre".</span><span class="sxs-lookup"><span data-stu-id="22ea3-135">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="22ea3-136">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-136">Click Add.</span></span>
24. <span data-ttu-id="22ea3-137">En el árbol, seleccione "Entrada".</span><span class="sxs-lookup"><span data-stu-id="22ea3-137">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="22ea3-138">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-138">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="22ea3-139">En el campo Nombre, escriba "Diario".</span><span class="sxs-lookup"><span data-stu-id="22ea3-139">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="22ea3-140">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="22ea3-140">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="22ea3-141">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-141">Click Add.</span></span>
29. <span data-ttu-id="22ea3-142">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-142">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="22ea3-143">En el campo Nombre, escriba "Lote".</span><span class="sxs-lookup"><span data-stu-id="22ea3-143">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="22ea3-144">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="22ea3-144">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="22ea3-145">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-145">Click Add.</span></span>
33. <span data-ttu-id="22ea3-146">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-146">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="22ea3-147">En el campo Nombre, escriba "Transacción".</span><span class="sxs-lookup"><span data-stu-id="22ea3-147">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="22ea3-148">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="22ea3-148">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="22ea3-149">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-149">Click Add.</span></span>
37. <span data-ttu-id="22ea3-150">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-150">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="22ea3-151">En el campo Nombre, escriba "Fecha".</span><span class="sxs-lookup"><span data-stu-id="22ea3-151">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="22ea3-152">En el campo Tipo de artículo, seleccione Fecha.</span><span class="sxs-lookup"><span data-stu-id="22ea3-152">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="22ea3-153">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-153">Click Add.</span></span>
41. <span data-ttu-id="22ea3-154">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-154">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="22ea3-155">En el campo Nombre, escriba "Débito".</span><span class="sxs-lookup"><span data-stu-id="22ea3-155">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="22ea3-156">En el campo Tipo de artículo, seleccione Real.</span><span class="sxs-lookup"><span data-stu-id="22ea3-156">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="22ea3-157">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-157">Click Add.</span></span>
45. <span data-ttu-id="22ea3-158">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-158">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="22ea3-159">En el campo Nombre, escriba "Crédito".</span><span class="sxs-lookup"><span data-stu-id="22ea3-159">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="22ea3-160">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-160">Click Add.</span></span>
48. <span data-ttu-id="22ea3-161">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-161">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="22ea3-162">En el campo Nombre, escriba "Divisa".</span><span class="sxs-lookup"><span data-stu-id="22ea3-162">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="22ea3-163">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="22ea3-163">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="22ea3-164">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-164">Click Add.</span></span>
52. <span data-ttu-id="22ea3-165">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-165">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="22ea3-166">En el campo Nombre, escriba "Asiento".</span><span class="sxs-lookup"><span data-stu-id="22ea3-166">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="22ea3-167">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-167">Click Add.</span></span>
55. <span data-ttu-id="22ea3-168">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-168">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="22ea3-169">En el campo Nombre, escriba "Datos de dimensiones".</span><span class="sxs-lookup"><span data-stu-id="22ea3-169">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="22ea3-170">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="22ea3-170">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="22ea3-171">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-171">Click Add.</span></span>
    * <span data-ttu-id="22ea3-172">Agregaremos a nuestro modelo a una lista de registro nuevo.</span><span class="sxs-lookup"><span data-stu-id="22ea3-172">We added to our model a new record list.</span></span> <span data-ttu-id="22ea3-173">Esta lista expondrá (para cualquier informe ER que utilice este modelo como origen de datos) los valores de las dimensiones financieras seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="22ea3-173">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="22ea3-174">Cada dimensión financiera se mostrará en esta lista como registro con los campos adecuados que representan los valores de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="22ea3-174">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's values.</span></span> <span data-ttu-id="22ea3-175">El nombre de la dimensión también se mostrará en este registro como campo que se utilizará, si procede, para fines de selección.</span><span class="sxs-lookup"><span data-stu-id="22ea3-175">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="22ea3-176">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-176">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="22ea3-177">En el campo Nombre, escriba "Código".</span><span class="sxs-lookup"><span data-stu-id="22ea3-177">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="22ea3-178">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="22ea3-178">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="22ea3-179">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-179">Click Add.</span></span>
63. <span data-ttu-id="22ea3-180">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-180">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="22ea3-181">En el campo Nombre, escriba "Descripción".</span><span class="sxs-lookup"><span data-stu-id="22ea3-181">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="22ea3-182">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-182">Click Add.</span></span>
66. <span data-ttu-id="22ea3-183">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="22ea3-183">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="22ea3-184">En el campo Nombre, escriba "Nombre".</span><span class="sxs-lookup"><span data-stu-id="22ea3-184">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="22ea3-185">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-185">Click Add.</span></span>
69. <span data-ttu-id="22ea3-186">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="22ea3-186">Click Save.</span></span>
70. <span data-ttu-id="22ea3-187">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="22ea3-187">Close the page.</span></span>

![Página de diseñador del modelo de datos de ER](../media/er-financial-dimensions-guides-data-model.png)



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]