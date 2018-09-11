--- 
title: "Definir directivas de auditoría para documentos de origen"
description: "En este procedimiento se muestra cómo configurar y ejecutar las reglas de directivas de auditoría."
author: ryansandness
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 10a3823e6d444b20c756890389400b58c080a01f
ms.contentlocale: es-es
ms.lasthandoff: 09/11/2018

---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="b6a79-103">Definir directivas de auditoría para documentos de origen</span><span class="sxs-lookup"><span data-stu-id="b6a79-103">Define audit policies for source documents</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b6a79-104">En este procedimiento se muestra cómo configurar y ejecutar las reglas de directivas de auditoría.</span><span class="sxs-lookup"><span data-stu-id="b6a79-104">This procedure shows how to set up and run audit policy rules.</span></span> <span data-ttu-id="b6a79-105">En el ejemplo se usan informes de gastos con el tipo de gastos de hotel.</span><span class="sxs-lookup"><span data-stu-id="b6a79-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="b6a79-106">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="b6a79-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="b6a79-107">El rol de auditor contiene los permisos correctos para llevar a cabo estas tareas.</span><span class="sxs-lookup"><span data-stu-id="b6a79-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="b6a79-108">Vaya a Área de trabajo de auditoría > Configuración > Tipo de regla de directivas.</span><span class="sxs-lookup"><span data-stu-id="b6a79-108">Go to Audit workbench > Setup > Policy rule type.</span></span>
2. <span data-ttu-id="b6a79-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="b6a79-109">Click New.</span></span>
3. <span data-ttu-id="b6a79-110">En el campo Nombre de regla, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="b6a79-110">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="b6a79-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="b6a79-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="b6a79-112">En el campo Nombre de la consulta, seleccione la línea Informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="b6a79-112">In the Query name field, select Expense report line</span></span>
6. <span data-ttu-id="b6a79-113">En el campo Tipo de consulta, seleccione Agregado.</span><span class="sxs-lookup"><span data-stu-id="b6a79-113">In the query type field, select Aggregate</span></span>
7. <span data-ttu-id="b6a79-114">En el campo Entidad jurídica, seleccione una entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="b6a79-114">In the Legal entity field, select Legal entity</span></span>
8. <span data-ttu-id="b6a79-115">En el campo Referencia de fecha de documento, seleccione la fecha y la hora de modificación.</span><span class="sxs-lookup"><span data-stu-id="b6a79-115">In the Document date reference field, select Modified date and time</span></span>
9. <span data-ttu-id="b6a79-116">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b6a79-116">Click Save.</span></span>
10. <span data-ttu-id="b6a79-117">Vaya a Área de trabajo de auditoría > Configuración > Directivas de auditoría.</span><span class="sxs-lookup"><span data-stu-id="b6a79-117">Go to Audit workbench > Setup > Audit policies.</span></span>
11. <span data-ttu-id="b6a79-118">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="b6a79-118">Click New.</span></span>
12. <span data-ttu-id="b6a79-119">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="b6a79-119">In the Name field, type a value.</span></span>
13. <span data-ttu-id="b6a79-120">Expanda la sección Organizaciones de directivas.</span><span class="sxs-lookup"><span data-stu-id="b6a79-120">Expand the Policy organizations section.</span></span>
14. <span data-ttu-id="b6a79-121">En el árbol, seleccione "Contoso Entertainment System USA".</span><span class="sxs-lookup"><span data-stu-id="b6a79-121">In the tree, select 'Contoso Entertainment System USA'.</span></span>
15. <span data-ttu-id="b6a79-122">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="b6a79-122">Click Add.</span></span>
16. <span data-ttu-id="b6a79-123">En el árbol, seleccione "Contoso Consulting USA".</span><span class="sxs-lookup"><span data-stu-id="b6a79-123">In the tree, select 'Contoso Consulting USA'.</span></span>
17. <span data-ttu-id="b6a79-124">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="b6a79-124">Click Add.</span></span>
18. <span data-ttu-id="b6a79-125">En el árbol, seleccione "Contoso Retail USA".</span><span class="sxs-lookup"><span data-stu-id="b6a79-125">In the tree, select 'Contoso Retail USA'.</span></span>
19. <span data-ttu-id="b6a79-126">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="b6a79-126">Click Add.</span></span>
20. <span data-ttu-id="b6a79-127">Contraiga la sección Organizaciones de directivas.</span><span class="sxs-lookup"><span data-stu-id="b6a79-127">Collapse the Policy organizations section.</span></span>
21. <span data-ttu-id="b6a79-128">Expanda la sección Reglas de directivas.</span><span class="sxs-lookup"><span data-stu-id="b6a79-128">Expand the Policy rules section.</span></span>
22. <span data-ttu-id="b6a79-129">En la lista, busque y seleccione la regla de directivas que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b6a79-129">In the list, find and select the Policy Rule that was created previously.</span></span>
23. <span data-ttu-id="b6a79-130">Haga clic en Crear regla de directivas.</span><span class="sxs-lookup"><span data-stu-id="b6a79-130">Click Create policy rule.</span></span>
24. <span data-ttu-id="b6a79-131">En el campo Fecha de vigencia, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="b6a79-131">In the Effective date field, enter a date and time.</span></span>
25. <span data-ttu-id="b6a79-132">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="b6a79-132">Click Filter.</span></span>
26. <span data-ttu-id="b6a79-133">En la lista, seleccione la fila de la categoría Gastos y defina los detalles de Hotel.</span><span class="sxs-lookup"><span data-stu-id="b6a79-133">In the list, select the row for Expense category, and set the details to Hotel</span></span>
27. <span data-ttu-id="b6a79-134">En el campo Criterios, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b6a79-134">In the Criteria field, enter or select a value.</span></span>
28. <span data-ttu-id="b6a79-135">Haga clic en la ficha Agregado.</span><span class="sxs-lookup"><span data-stu-id="b6a79-135">Click the Aggregate tab.</span></span>
29. <span data-ttu-id="b6a79-136">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="b6a79-136">Click Add.</span></span>
30. <span data-ttu-id="b6a79-137">En la lista, seleccione un valor de campo del importe de la transacción.</span><span class="sxs-lookup"><span data-stu-id="b6a79-137">In the list, select a field value of Transaction amount</span></span>
31. <span data-ttu-id="b6a79-138">En el campo Campo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b6a79-138">In the Field field, enter or select a value.</span></span>
32. <span data-ttu-id="b6a79-139">En el campo de AggregateFunction, seleccione “Suma”.</span><span class="sxs-lookup"><span data-stu-id="b6a79-139">In the AggregateFunction field, select 'Sum'.</span></span>
33. <span data-ttu-id="b6a79-140">Haga clic en la ficha Agrupar por.</span><span class="sxs-lookup"><span data-stu-id="b6a79-140">Click the Group by tab.</span></span>
34. <span data-ttu-id="b6a79-141">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="b6a79-141">Click Add.</span></span>
35. <span data-ttu-id="b6a79-142">En la lista, seleccione un valor de Empleado. </span><span class="sxs-lookup"><span data-stu-id="b6a79-142">In the list, select a value of Employee</span></span> 
36. <span data-ttu-id="b6a79-143">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="b6a79-143">Click Add.</span></span>
37. <span data-ttu-id="b6a79-144">En la lista, seleccione un valor de Categoría de gastos.</span><span class="sxs-lookup"><span data-stu-id="b6a79-144">In the list, select a value of Expense category</span></span>
38. <span data-ttu-id="b6a79-145">En el campo Campo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b6a79-145">In the Field field, enter or select a value.</span></span>
39. <span data-ttu-id="b6a79-146">Haga clic en la ficha Tiene.</span><span class="sxs-lookup"><span data-stu-id="b6a79-146">Click the Having tab.</span></span>
40. <span data-ttu-id="b6a79-147">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="b6a79-147">Click Add.</span></span>
41. <span data-ttu-id="b6a79-148">Seleccionar el importe de transacción</span><span class="sxs-lookup"><span data-stu-id="b6a79-148">Select Transaction amount</span></span>
42. <span data-ttu-id="b6a79-149">En el campo Campo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b6a79-149">In the Field field, enter or select a value.</span></span>
43. <span data-ttu-id="b6a79-150">En el campo de AggregateFunction, seleccione “Suma”.</span><span class="sxs-lookup"><span data-stu-id="b6a79-150">In the AggregateFunction field, select 'Sum'.</span></span>
44. <span data-ttu-id="b6a79-151">En el campo Criterios, escriba >2000".</span><span class="sxs-lookup"><span data-stu-id="b6a79-151">In the Criteria field, type '>2000'.</span></span>
45. <span data-ttu-id="b6a79-152">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="b6a79-152">Click OK.</span></span>
46. <span data-ttu-id="b6a79-153">Haga clic en Probar.</span><span class="sxs-lookup"><span data-stu-id="b6a79-153">Click Test.</span></span>
47. <span data-ttu-id="b6a79-154">En el campo Fecha inicial de selección de documentos, especifique una fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="b6a79-154">In the Document selection starting date field, enter a date and time.</span></span>
48. <span data-ttu-id="b6a79-155">En el campo Fecha final de selección de documentos, especifique una fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="b6a79-155">In the Document selection ending date field, enter a date and time.</span></span>
49. <span data-ttu-id="b6a79-156">Haga clic en Ejecutar prueba.</span><span class="sxs-lookup"><span data-stu-id="b6a79-156">Click Run test.</span></span>
50. <span data-ttu-id="b6a79-157">En el panel de acciones, haga clic en Directiva de auditoría.</span><span class="sxs-lookup"><span data-stu-id="b6a79-157">On the Action Pane, click Audit policy.</span></span>
51. <span data-ttu-id="b6a79-158">Haga clic en Opciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="b6a79-158">Click Additional options.</span></span>
52. <span data-ttu-id="b6a79-159">En el campo Fecha inicial, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="b6a79-159">In the Starting date field, enter a date and time.</span></span>
53. <span data-ttu-id="b6a79-160">En el campo Fecha de finalización, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="b6a79-160">In the Ending date field, enter a date and time.</span></span>
54. <span data-ttu-id="b6a79-161">Haga clic en Lote.</span><span class="sxs-lookup"><span data-stu-id="b6a79-161">Click Batch.</span></span>
55. <span data-ttu-id="b6a79-162">Expanda la sección Ejecutar en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b6a79-162">Expand the Run in the background section.</span></span>
56. <span data-ttu-id="b6a79-163">Seleccione Sí en el campo Procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="b6a79-163">Select Yes in the Batch processing field.</span></span>
57. <span data-ttu-id="b6a79-164">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="b6a79-164">Click OK.</span></span>
58. <span data-ttu-id="b6a79-165">Vaya a Área de trabajo de auditoría '>Casos de auditoría.</span><span class="sxs-lookup"><span data-stu-id="b6a79-165">Go to Audit workbench > Audit cases.</span></span>
59. <span data-ttu-id="b6a79-166">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b6a79-166">In the list, find and select the desired record.</span></span>
60. <span data-ttu-id="b6a79-167">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b6a79-167">In the list, click the link in the selected row.</span></span>
61. <span data-ttu-id="b6a79-168">Expanda la sección Asociación.</span><span class="sxs-lookup"><span data-stu-id="b6a79-168">Expand the Associations section.</span></span>
62. <span data-ttu-id="b6a79-169">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b6a79-169">In the list, find and select the desired record.</span></span>
63. <span data-ttu-id="b6a79-170">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b6a79-170">In the list, click the link in the selected row.</span></span>


