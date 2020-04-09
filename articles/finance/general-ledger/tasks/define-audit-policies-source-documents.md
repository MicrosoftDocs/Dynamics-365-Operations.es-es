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
ms.openlocfilehash: ba720fd1bbbbf8b4f3b936d65d9d7840432f291a
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145038"
---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="4f8f8-103">Definir directivas de auditoría para documentos de origen</span><span class="sxs-lookup"><span data-stu-id="4f8f8-103">Define audit policies for source documents</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4f8f8-104">En este tema se explica cómo configurar y ejecutar las reglas de directivas de auditoría.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-104">This topic explains how to set up and run audit policy rules.</span></span> <span data-ttu-id="4f8f8-105">En el ejemplo se usan informes de gastos con el tipo de gastos de hotel.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="4f8f8-106">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="4f8f8-107">El rol de auditor contiene los permisos correctos para llevar a cabo estas tareas.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="4f8f8-108">En el panel de exploración, vaya a **Módulos > Área de trabajo de auditoría > Configuración > Tipo de regla de directivas**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-108">In the navigation pane, go to **Modules > Audit workbench > Setup > Policy rule type**.</span></span>
2. <span data-ttu-id="4f8f8-109">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-109">Select **New**.</span></span>
3. <span data-ttu-id="4f8f8-110">En el campo **Nombre de regla**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-110">In the **Rule name** field, type a value.</span></span>
4. <span data-ttu-id="4f8f8-111">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="4f8f8-112">En el campo **Nombre de la consulta**, seleccione **Línea de informe de gastos**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-112">In the **Query name** field, select **Expense report line**</span></span>
6. <span data-ttu-id="4f8f8-113">En el campo **Tipo de consulta**, seleccione **Agregado**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-113">In the **query type** field, select **Aggregate**</span></span>
7. <span data-ttu-id="4f8f8-114">En el campo **Entidad jurídica**, seleccione **Entidad jurídica**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-114">In the **Legal entity** field, select **Legal entity**</span></span>
8. <span data-ttu-id="4f8f8-115">En el campo **Referencia de fecha de documento**, seleccione **Fecha y hora de modificación**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-115">In the **Document date reference** field, select **Modified date and time**</span></span>
9. <span data-ttu-id="4f8f8-116">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-116">Select **Save**.</span></span>
10. <span data-ttu-id="4f8f8-117">En el panel de exploración, vaya a **Módulos > Área de trabajo de auditoría > Configuración > Directivas de auditoría**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-117">In the navigation pane, go to **Modules > Audit workbench > Setup > Audit policies**.</span></span>
11. <span data-ttu-id="4f8f8-118">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-118">Select **New**.</span></span>
12. <span data-ttu-id="4f8f8-119">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-119">In the **Name** field, type a value.</span></span>
13. <span data-ttu-id="4f8f8-120">Expanda la sección **Organizaciones de directivas**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-120">Expand the **Policy organizations** section.</span></span>
14. <span data-ttu-id="4f8f8-121">En el árbol, seleccione **Contoso Entertainment System USA** y, después, **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-121">In the tree, select **Contoso Entertainment System USA**, then select **Add**.</span></span>
15. <span data-ttu-id="4f8f8-122">En el árbol, seleccione **Contoso Consulting USA** y, después, **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-122">In the tree, select **Contoso Consulting USA**, then select **Add**.</span></span>
16. <span data-ttu-id="4f8f8-123">En el árbol, seleccione **Contoso Retail USA** y, después, **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-123">In the tree, select **Contoso Retail USA**, then select **Add**.</span></span>
17. <span data-ttu-id="4f8f8-124">Contraiga la sección **Organizaciones de directivas**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-124">Collapse the **Policy organizations** section.</span></span>
18. <span data-ttu-id="4f8f8-125">Expanda la sección **Reglas de directivas**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-125">Expand the **Policy rules** section.</span></span>
19. <span data-ttu-id="4f8f8-126">En la lista, busque y seleccione la regla de directivas que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-126">In the list, find and select the Policy Rule that was created previously.</span></span>
20. <span data-ttu-id="4f8f8-127">Seleccione **Crear regla de directivas**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-127">Select **Create policy rule**.</span></span>
21. <span data-ttu-id="4f8f8-128">En el campo **Fecha de vigencia**, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-128">In the **Effective date** field, enter a date and time.</span></span>
22. <span data-ttu-id="4f8f8-129">Seleccione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-129">Select **Filter**.</span></span>
23. <span data-ttu-id="4f8f8-130">En la lista, seleccione la fila para **Categoría de gastos** y establezca los detalles en **Hotel**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-130">In the list, select the row for **Expense category**, and set the details to **Hotel**.</span></span>
24. <span data-ttu-id="4f8f8-131">En el campo **Criterios**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-131">In the **Criteria** field, enter or select a value.</span></span>
25. <span data-ttu-id="4f8f8-132">Seleccione la pestaña **Agregado**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-132">Select the **Aggregate** tab.</span></span>
26. <span data-ttu-id="4f8f8-133">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-133">Select **Add**.</span></span>
27. <span data-ttu-id="4f8f8-134">En la lista, seleccione un valor de campo de **Importe de la transacción**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-134">In the list, select a field value of **Transaction amount**.</span></span>
28. <span data-ttu-id="4f8f8-135">En el campo **Campo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-135">In the **Field** field, enter or select a value.</span></span>
29. <span data-ttu-id="4f8f8-136">En el campo de **AggregateFunction**, seleccione **Suma**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-136">In the **AggregateFunction** field, select **Sum**.</span></span>
30. <span data-ttu-id="4f8f8-137">Seleccione la ficha **Agrupar por**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-137">Select the **Group by** tab.</span></span>
31. <span data-ttu-id="4f8f8-138">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-138">Select **Add**.</span></span>
32. <span data-ttu-id="4f8f8-139">En la lista, seleccione un valor de **Empleado**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-139">In the list, select a value of **Employee** .</span></span>
33. <span data-ttu-id="4f8f8-140">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-140">Select **Add**.</span></span>
34. <span data-ttu-id="4f8f8-141">En la lista, seleccione un valor de **Categoría de gastos**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-141">In the list, select a value of **Expense category**.</span></span>
35. <span data-ttu-id="4f8f8-142">En el campo **Campo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-142">In the **Field** field, enter or select a value.</span></span>
36. <span data-ttu-id="4f8f8-143">Seleccione la pestaña **Tiene**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-143">Select the **Having** tab.</span></span>
37. <span data-ttu-id="4f8f8-144">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-144">Select **Add**.</span></span>
38. <span data-ttu-id="4f8f8-145">Seleccione **Importe de transacción**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-145">Select **Transaction amount**.</span></span>
39. <span data-ttu-id="4f8f8-146">En el campo **Campo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-146">In the **Field** field, enter or select a value.</span></span>
40. <span data-ttu-id="4f8f8-147">En el campo de **AggregateFunction**, seleccione **Suma**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-147">In the **AggregateFunction** field, select **Sum**.</span></span>
41. <span data-ttu-id="4f8f8-148">En el campo **Criterios**, escriba `>2000`.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-148">In the **Criteria** field, type `>2000`.</span></span>
42. <span data-ttu-id="4f8f8-149">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-149">Select **OK**.</span></span>
43. <span data-ttu-id="4f8f8-150">Seleccione **Prueba**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-150">Select **Test**.</span></span>
44. <span data-ttu-id="4f8f8-151">En el campo **Fecha inicial de selección de documentos**, especifique una fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-151">In the **Document selection starting date** field, enter a date and time.</span></span>
45. <span data-ttu-id="4f8f8-152">En el campo **Fecha final de selección de documentos**, especifique una fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-152">In the **Document selection ending date** field, enter a date and time.</span></span>
46. <span data-ttu-id="4f8f8-153">Seleccione **Ejecutar prueba**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-153">Select **Run test**.</span></span>
47. <span data-ttu-id="4f8f8-154">En el panel de acciones, seleccione **Directiva de auditoría**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-154">On the Action Pane, select **Audit policy**.</span></span>
48. <span data-ttu-id="4f8f8-155">Seleccione **Opciones adicionales**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-155">Select **Additional options**.</span></span>
49. <span data-ttu-id="4f8f8-156">En el campo **Fecha inicial**, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-156">In the **Starting date** field, enter a date and time.</span></span>
50. <span data-ttu-id="4f8f8-157">En el campo **Fecha de finalización**, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-157">In the **Ending date** field, enter a date and time.</span></span>
51. <span data-ttu-id="4f8f8-158">Seleccione **Lote**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-158">Select **Batch**.</span></span>
52. <span data-ttu-id="4f8f8-159">Expanda la sección **Ejecutar en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-159">Expand the **Run in the background** section.</span></span>
53. <span data-ttu-id="4f8f8-160">Seleccione **Sí** en el campo **Procesamiento por lotes**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-160">Select **Yes** in the **Batch processing** field.</span></span>
54. <span data-ttu-id="4f8f8-161">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-161">Select **OK**.</span></span>
55. <span data-ttu-id="4f8f8-162">En el panel de exploración, vaya a **Módulos > Área de trabajo de auditoría > Configuración > Casos de auditoría**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-162">In the navigation pane, go to **Modules > Audit workbench > Audit cases**.</span></span>
56. <span data-ttu-id="4f8f8-163">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-163">In the list, find and select the desired record.</span></span>
57. <span data-ttu-id="4f8f8-164">Expanda la sección **Asociaciones**.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-164">Expand the **Associations** section.</span></span>
58. <span data-ttu-id="4f8f8-165">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="4f8f8-165">In the list, find and select the desired record.</span></span>

