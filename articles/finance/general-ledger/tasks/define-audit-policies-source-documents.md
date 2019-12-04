---
title: Definir directivas de auditoría para documentos de origen
description: En este tema se explica cómo configurar y ejecutar las reglas de directivas de auditoría.
author: ryansandness
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6b0fa28d778a4d9fa1f718b1d50bf1dce00be00
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186127"
---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="c1cc2-103">Definir directivas de auditoría para documentos de origen</span><span class="sxs-lookup"><span data-stu-id="c1cc2-103">Define audit policies for source documents</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c1cc2-104">En este tema se explica cómo configurar y ejecutar las reglas de directivas de auditoría.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-104">This topic explains how to set up and run audit policy rules.</span></span> <span data-ttu-id="c1cc2-105">En el ejemplo se usan informes de gastos con el tipo de gastos de hotel.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="c1cc2-106">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="c1cc2-107">El rol de auditor contiene los permisos correctos para llevar a cabo estas tareas.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="c1cc2-108">En el panel de exploración, vaya a **Módulos > Área de trabajo de auditoría > Configuración > Tipo de regla de directivas**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-108">In the navigation pane, go to **Modules > Audit workbench > Setup > Policy rule type**.</span></span>
2. <span data-ttu-id="c1cc2-109">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-109">Select **New**.</span></span>
3. <span data-ttu-id="c1cc2-110">En el campo **Nombre de regla**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-110">In the **Rule name** field, type a value.</span></span>
4. <span data-ttu-id="c1cc2-111">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="c1cc2-112">En el campo **Nombre de la consulta**, seleccione **Línea de informe de gastos**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-112">In the **Query name** field, select **Expense report line**</span></span>
6. <span data-ttu-id="c1cc2-113">En el campo **Tipo de consulta**, seleccione **Agregado**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-113">In the **query type** field, select **Aggregate**</span></span>
7. <span data-ttu-id="c1cc2-114">En el campo **Entidad jurídica**, seleccione **Entidad jurídica**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-114">In the **Legal entity** field, select **Legal entity**</span></span>
8. <span data-ttu-id="c1cc2-115">En el campo **Referencia de fecha de documento**, seleccione **Fecha y hora de modificación**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-115">In the **Document date reference** field, select **Modified date and time**</span></span>
9. <span data-ttu-id="c1cc2-116">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-116">Select **Save**.</span></span>
10. <span data-ttu-id="c1cc2-117">En el panel de exploración, vaya a **Módulos > Área de trabajo de auditoría > Configuración > Directivas de auditoría**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-117">In the navigation pane, go to **Modules > Audit workbench > Setup > Audit policies**.</span></span>
11. <span data-ttu-id="c1cc2-118">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-118">Select **New**.</span></span>
12. <span data-ttu-id="c1cc2-119">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-119">In the **Name** field, type a value.</span></span>
13. <span data-ttu-id="c1cc2-120">Expanda la sección **Organizaciones de directivas**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-120">Expand the **Policy organizations** section.</span></span>
14. <span data-ttu-id="c1cc2-121">En el árbol, seleccione **Contoso Entertainment System USA** y, después, **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-121">In the tree, select **Contoso Entertainment System USA**, then select **Add**.</span></span>
15. <span data-ttu-id="c1cc2-122">En el árbol, seleccione **Contoso Consulting USA** y, después, **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-122">In the tree, select **Contoso Consulting USA**, then select **Add**.</span></span>
16. <span data-ttu-id="c1cc2-123">En el árbol, seleccione **Contoso Retail USA** y, después, **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-123">In the tree, select **Contoso Retail USA**, then select **Add**.</span></span>
17. <span data-ttu-id="c1cc2-124">Contraiga la sección **Organizaciones de directivas**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-124">Collapse the **Policy organizations** section.</span></span>
18. <span data-ttu-id="c1cc2-125">Expanda la sección **Reglas de directivas**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-125">Expand the **Policy rules** section.</span></span>
19. <span data-ttu-id="c1cc2-126">En la lista, busque y seleccione la regla de directivas que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-126">In the list, find and select the Policy Rule that was created previously.</span></span>
20. <span data-ttu-id="c1cc2-127">Seleccione **Crear regla de directivas**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-127">Select **Create policy rule**.</span></span>
21. <span data-ttu-id="c1cc2-128">En el campo **Fecha de vigencia**, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-128">In the **Effective date** field, enter a date and time.</span></span>
22. <span data-ttu-id="c1cc2-129">Seleccione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-129">Select **Filter**.</span></span>
23. <span data-ttu-id="c1cc2-130">En la lista, seleccione la fila para **Categoría de gastos** y establezca los detalles en **Hotel**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-130">In the list, select the row for **Expense category**, and set the details to **Hotel**.</span></span>
24. <span data-ttu-id="c1cc2-131">En el campo **Criterios**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-131">In the **Criteria** field, enter or select a value.</span></span>
25. <span data-ttu-id="c1cc2-132">Seleccione la pestaña **Agregado**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-132">Select the **Aggregate** tab.</span></span>
26. <span data-ttu-id="c1cc2-133">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-133">Select **Add**.</span></span>
27. <span data-ttu-id="c1cc2-134">En la lista, seleccione un valor de campo de **Importe de la transacción**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-134">In the list, select a field value of **Transaction amount**.</span></span>
28. <span data-ttu-id="c1cc2-135">En el campo **Campo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-135">In the **Field** field, enter or select a value.</span></span>
29. <span data-ttu-id="c1cc2-136">En el campo de **AggregateFunction**, seleccione **Suma**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-136">In the **AggregateFunction** field, select **Sum**.</span></span>
30. <span data-ttu-id="c1cc2-137">Seleccione la ficha **Agrupar por**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-137">Select the **Group by** tab.</span></span>
31. <span data-ttu-id="c1cc2-138">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-138">Select **Add**.</span></span>
32. <span data-ttu-id="c1cc2-139">En la lista, seleccione un valor de **Empleado**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-139">In the list, select a value of **Employee** .</span></span>
33. <span data-ttu-id="c1cc2-140">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-140">Select **Add**.</span></span>
34. <span data-ttu-id="c1cc2-141">En la lista, seleccione un valor de **Categoría de gastos**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-141">In the list, select a value of **Expense category**.</span></span>
35. <span data-ttu-id="c1cc2-142">En el campo **Campo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-142">In the **Field** field, enter or select a value.</span></span>
36. <span data-ttu-id="c1cc2-143">Seleccione la pestaña **Tiene**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-143">Select the **Having** tab.</span></span>
37. <span data-ttu-id="c1cc2-144">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-144">Select **Add**.</span></span>
38. <span data-ttu-id="c1cc2-145">Seleccione **Importe de transacción**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-145">Select **Transaction amount**.</span></span>
39. <span data-ttu-id="c1cc2-146">En el campo **Campo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-146">In the **Field** field, enter or select a value.</span></span>
40. <span data-ttu-id="c1cc2-147">En el campo de **AggregateFunction**, seleccione **Suma**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-147">In the **AggregateFunction** field, select **Sum**.</span></span>
41. <span data-ttu-id="c1cc2-148">En el campo **Criterios**, escriba `>2000`.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-148">In the **Criteria** field, type `>2000`.</span></span>
42. <span data-ttu-id="c1cc2-149">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-149">Select **OK**.</span></span>
43. <span data-ttu-id="c1cc2-150">Seleccione **Prueba**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-150">Select **Test**.</span></span>
44. <span data-ttu-id="c1cc2-151">En el campo **Fecha inicial de selección de documentos**, especifique una fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-151">In the **Document selection starting date** field, enter a date and time.</span></span>
45. <span data-ttu-id="c1cc2-152">En el campo **Fecha final de selección de documentos**, especifique una fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-152">In the **Document selection ending date** field, enter a date and time.</span></span>
46. <span data-ttu-id="c1cc2-153">Seleccione **Ejecutar prueba**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-153">Select **Run test**.</span></span>
47. <span data-ttu-id="c1cc2-154">En el panel de acciones, seleccione **Directiva de auditoría**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-154">On the Action Pane, select **Audit policy**.</span></span>
48. <span data-ttu-id="c1cc2-155">Seleccione **Opciones adicionales**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-155">Select **Additional options**.</span></span>
49. <span data-ttu-id="c1cc2-156">En el campo **Fecha inicial**, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-156">In the **Starting date** field, enter a date and time.</span></span>
50. <span data-ttu-id="c1cc2-157">En el campo **Fecha de finalización**, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-157">In the **Ending date** field, enter a date and time.</span></span>
51. <span data-ttu-id="c1cc2-158">Seleccione **Lote**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-158">Select **Batch**.</span></span>
52. <span data-ttu-id="c1cc2-159">Expanda la sección **Ejecutar en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-159">Expand the **Run in the background** section.</span></span>
53. <span data-ttu-id="c1cc2-160">Seleccione **Sí** en el campo **Procesamiento por lotes**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-160">Select **Yes** in the **Batch processing** field.</span></span>
54. <span data-ttu-id="c1cc2-161">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-161">Select **OK**.</span></span>
55. <span data-ttu-id="c1cc2-162">En el panel de exploración, vaya a **Módulos > Área de trabajo de auditoría > Configuración > Casos de auditoría**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-162">In the navigation pane, go to **Modules > Audit workbench > Audit cases**.</span></span>
56. <span data-ttu-id="c1cc2-163">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-163">In the list, find and select the desired record.</span></span>
57. <span data-ttu-id="c1cc2-164">Expanda la sección **Asociaciones**.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-164">Expand the **Associations** section.</span></span>
58. <span data-ttu-id="c1cc2-165">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c1cc2-165">In the list, find and select the desired record.</span></span>
