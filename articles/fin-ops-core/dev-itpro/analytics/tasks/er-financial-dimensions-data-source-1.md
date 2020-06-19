---
title: 'ER Usar dimensiones financieras como origen de datos (Parte 1: Modelo de datos de diseño)'
description: En los pasos siguientes se explica cómo un administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER.
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b951c9074c68a9f7592c17e0688498880397b223
ms.sourcegitcommit: d9125c20b21459076e4fd92fd9ebfe2e53a0431b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "3406552"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a><span data-ttu-id="9afc2-103">ER Usar dimensiones financieras como origen de datos (Parte 1: Modelo de datos de diseño)</span><span class="sxs-lookup"><span data-stu-id="9afc2-103">ER Use financial dimensions as a data source (Part 1 - Design data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9afc2-104">En los pasos siguientes se explica cómo un administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER.</span><span class="sxs-lookup"><span data-stu-id="9afc2-104">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="9afc2-105">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="9afc2-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="9afc2-106">Para completar estos pasos, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".</span><span class="sxs-lookup"><span data-stu-id="9afc2-106">To complete these steps, you must first complete the steps in the procedure, "Create a configuration provider and mark it as active".</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="9afc2-107">Crear un nuevo modelo de datos</span><span class="sxs-lookup"><span data-stu-id="9afc2-107">Create a new data model</span></span>
1. <span data-ttu-id="9afc2-108">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="9afc2-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="9afc2-109">Asegúrese de que “Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="9afc2-109">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="9afc2-110">está disponible y marcado como activo.</span><span class="sxs-lookup"><span data-stu-id="9afc2-110">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="9afc2-111">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="9afc2-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="9afc2-112">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-112">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="9afc2-113">En el campo Nombre, escriba "Modelo de ejemplo de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="9afc2-113">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="9afc2-114">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="9afc2-114">Click Create configuration.</span></span>
6. <span data-ttu-id="9afc2-115">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="9afc2-115">Click Designer.</span></span>
7. <span data-ttu-id="9afc2-116">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="9afc2-117">En el campo Nombre, escriba "Entrada".</span><span class="sxs-lookup"><span data-stu-id="9afc2-117">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="9afc2-118">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-118">Click Add.</span></span>
10. <span data-ttu-id="9afc2-119">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-119">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="9afc2-120">Escriba "Empresa" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="9afc2-120">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="9afc2-121">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-121">Click Add.</span></span>
    * <span data-ttu-id="9afc2-122">Agregaremos nuestro modelo a una lista de registro nuevo.</span><span class="sxs-lookup"><span data-stu-id="9afc2-122">We will add to our model a new record list.</span></span> <span data-ttu-id="9afc2-123">Esta lista expondrá (para cualquier informe ER que utilice este modelo como origen de datos) los valores de dimensiones financieras seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="9afc2-123">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="9afc2-124">Cada dimensión financiera se mostrará en esta lista como registro con los campos adecuados que representan el valor de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="9afc2-124">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's setting.</span></span>  
13. <span data-ttu-id="9afc2-125">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-125">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="9afc2-126">En el campo Nombre, escriba "Configuración de dimensiones".</span><span class="sxs-lookup"><span data-stu-id="9afc2-126">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="9afc2-127">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="9afc2-127">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="9afc2-128">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-128">Click Add.</span></span>
17. <span data-ttu-id="9afc2-129">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-129">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="9afc2-130">En el campo Nombre, escriba "Código".</span><span class="sxs-lookup"><span data-stu-id="9afc2-130">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="9afc2-131">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="9afc2-131">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="9afc2-132">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-132">Click Add.</span></span>
21. <span data-ttu-id="9afc2-133">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-133">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="9afc2-134">En el campo Nombre, escriba "Nombre".</span><span class="sxs-lookup"><span data-stu-id="9afc2-134">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="9afc2-135">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-135">Click Add.</span></span>
24. <span data-ttu-id="9afc2-136">En el árbol, seleccione "Entrada".</span><span class="sxs-lookup"><span data-stu-id="9afc2-136">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="9afc2-137">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-137">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="9afc2-138">En el campo Nombre, escriba "Diario".</span><span class="sxs-lookup"><span data-stu-id="9afc2-138">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="9afc2-139">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="9afc2-139">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="9afc2-140">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-140">Click Add.</span></span>
29. <span data-ttu-id="9afc2-141">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-141">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="9afc2-142">En el campo Nombre, escriba "Lote".</span><span class="sxs-lookup"><span data-stu-id="9afc2-142">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="9afc2-143">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="9afc2-143">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="9afc2-144">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-144">Click Add.</span></span>
33. <span data-ttu-id="9afc2-145">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-145">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="9afc2-146">En el campo Nombre, escriba "Transacción".</span><span class="sxs-lookup"><span data-stu-id="9afc2-146">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="9afc2-147">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="9afc2-147">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="9afc2-148">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-148">Click Add.</span></span>
37. <span data-ttu-id="9afc2-149">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-149">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="9afc2-150">En el campo Nombre, escriba "Fecha".</span><span class="sxs-lookup"><span data-stu-id="9afc2-150">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="9afc2-151">En el campo Tipo de artículo, seleccione Fecha.</span><span class="sxs-lookup"><span data-stu-id="9afc2-151">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="9afc2-152">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-152">Click Add.</span></span>
41. <span data-ttu-id="9afc2-153">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-153">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="9afc2-154">En el campo Nombre, escriba "Débito".</span><span class="sxs-lookup"><span data-stu-id="9afc2-154">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="9afc2-155">En el campo Tipo de artículo, seleccione Real.</span><span class="sxs-lookup"><span data-stu-id="9afc2-155">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="9afc2-156">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-156">Click Add.</span></span>
45. <span data-ttu-id="9afc2-157">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-157">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="9afc2-158">En el campo Nombre, escriba "Crédito".</span><span class="sxs-lookup"><span data-stu-id="9afc2-158">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="9afc2-159">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-159">Click Add.</span></span>
48. <span data-ttu-id="9afc2-160">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-160">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="9afc2-161">En el campo Nombre, escriba "Divisa".</span><span class="sxs-lookup"><span data-stu-id="9afc2-161">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="9afc2-162">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="9afc2-162">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="9afc2-163">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-163">Click Add.</span></span>
52. <span data-ttu-id="9afc2-164">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-164">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="9afc2-165">En el campo Nombre, escriba "Asiento".</span><span class="sxs-lookup"><span data-stu-id="9afc2-165">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="9afc2-166">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-166">Click Add.</span></span>
55. <span data-ttu-id="9afc2-167">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-167">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="9afc2-168">En el campo Nombre, escriba "Datos de dimensiones".</span><span class="sxs-lookup"><span data-stu-id="9afc2-168">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="9afc2-169">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="9afc2-169">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="9afc2-170">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-170">Click Add.</span></span>
    * <span data-ttu-id="9afc2-171">Agregaremos a nuestro modelo a una lista de registro nuevo.</span><span class="sxs-lookup"><span data-stu-id="9afc2-171">We added to our model a new record list.</span></span> <span data-ttu-id="9afc2-172">Esta lista expondrá (para cualquier informe ER que utilice este modelo como origen de datos) los valores de las dimensiones financieras seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="9afc2-172">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="9afc2-173">Cada dimensión financiera se mostrará en esta lista como registro con los campos adecuados que representan los valores de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="9afc2-173">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's values.</span></span> <span data-ttu-id="9afc2-174">El nombre de la dimensión también se mostrará en este registro como campo que se utilizará, si procede, para fines de selección.</span><span class="sxs-lookup"><span data-stu-id="9afc2-174">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="9afc2-175">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-175">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="9afc2-176">En el campo Nombre, escriba "Código".</span><span class="sxs-lookup"><span data-stu-id="9afc2-176">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="9afc2-177">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="9afc2-177">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="9afc2-178">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-178">Click Add.</span></span>
63. <span data-ttu-id="9afc2-179">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-179">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="9afc2-180">En el campo Nombre, escriba "Descripción".</span><span class="sxs-lookup"><span data-stu-id="9afc2-180">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="9afc2-181">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-181">Click Add.</span></span>
66. <span data-ttu-id="9afc2-182">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9afc2-182">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="9afc2-183">En el campo Nombre, escriba "Nombre".</span><span class="sxs-lookup"><span data-stu-id="9afc2-183">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="9afc2-184">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-184">Click Add.</span></span>
69. <span data-ttu-id="9afc2-185">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9afc2-185">Click Save.</span></span>
70. <span data-ttu-id="9afc2-186">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9afc2-186">Close the page.</span></span>

![Página de diseñador del modelo de datos de ER](../media/er-financial-dimensions-guides-data-model.png)

