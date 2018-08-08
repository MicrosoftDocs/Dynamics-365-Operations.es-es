---
title: "Reglas de directivas de auditoría"
description: "Puede usar directivas de auditoría para evaluar si ciertos informes de gastos, facturas de proveedor y pedidos de compra para asegurarse de que cumplan las reglas de directivas que ha creado. Todas las reglas asociadas a una directiva de auditoría se ejecutan en el modo por lotes, de acuerdo con la programación que haya especificado.  Cada regla de directivas pertenece a un tipo de regla de directivas. Sólo puede haber una regla de directivas activa por cada tipo de regla de directivas."
author: ryansandness
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 18b8a1649a26ebacc34b828ed25ec9646dd438a1
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="audit-policy-rules"></a><span data-ttu-id="c6ff6-106">Reglas de directivas de auditoría</span><span class="sxs-lookup"><span data-stu-id="c6ff6-106">Audit policy rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c6ff6-107">Puede usar directivas de auditoría para evaluar si ciertos informes de gastos, facturas de proveedor y pedidos de compra para asegurarse de que cumplan las reglas de directivas que ha creado.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-107">You can use audit policies to evaluate expense reports, vendor invoices, and purchase orders to make sure that they comply with policy rules that you create.</span></span> <span data-ttu-id="c6ff6-108">Todas las reglas asociadas a una directiva de auditoría se ejecutan en el modo por lotes, de acuerdo con la programación que haya especificado.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-108">All of the rules that are associated with an audit policy are run in batch mode, according to a schedule that you specify.</span></span>  <span data-ttu-id="c6ff6-109">Cada regla de directivas pertenece a un tipo de regla de directivas.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-109">Each policy rule is an instance of a policy rule type.</span></span> <span data-ttu-id="c6ff6-110">Sólo puede haber una regla de directivas activa por cada tipo de regla de directivas.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-110">For each policy rule type, only one policy rule can be active at a time.</span></span> 

<a name="queries-and-query-types"></a><span data-ttu-id="c6ff6-111">Consultas y tipos de consulta</span><span class="sxs-lookup"><span data-stu-id="c6ff6-111">Queries and query types</span></span>
-----------------------

<span data-ttu-id="c6ff6-112">Para crear una regla de directivas de auditoría, en primer lugar se selecciona un tipo de regla de directivas.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-112">When you create an audit policy rule, you first select a policy rule type.</span></span> <span data-ttu-id="c6ff6-113">El tipo de regla de directivas determina la consulta del árbol de objetos de aplicación (AOT) que se usa como punto de partida para crear la regla de directivas.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-113">The policy rule type specifies the Application Object Tree (AOT) query to use as the starting point for creating the policy rule.</span></span> <span data-ttu-id="c6ff6-114">También especifica el tipo de consulta que se usará para la regla de directivas.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-114">It also specifies the query type to use for the policy rule.</span></span> <span data-ttu-id="c6ff6-115">La consulta determina el documento de origen que evalúa la regla de directivas.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-115">The query determines the source document that the policy rule evaluates.</span></span> <span data-ttu-id="c6ff6-116">También especifica los campos del documento de origen que identifican tanto la entidad jurídica y como la fecha que se usará al seleccionar documentos para una auditoría.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-116">It also specifies the fields in the source document that identify both the legal entity and the date to use when documents are selected for audit.</span></span> <span data-ttu-id="c6ff6-117">El tipo de consulta controla los campos predeterminados de la página de consulta y de la página Regla de directivas de auditoría.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-117">The query type controls the default fields in the query page and in the Audit policy rule page.</span></span> <span data-ttu-id="c6ff6-118">En la tabla siguiente se incluyen los tipos de consulta disponibles para reglas de directivas de auditoría.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-118">The following table shows the query types that are available for audit policy rules.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6ff6-119">Tipo de consulta</span><span class="sxs-lookup"><span data-stu-id="c6ff6-119">Query type</span></span></th>
<th><span data-ttu-id="c6ff6-120">Propósito</span><span class="sxs-lookup"><span data-stu-id="c6ff6-120">Purpose</span></span></th>
<th><span data-ttu-id="c6ff6-121">Más información</span><span class="sxs-lookup"><span data-stu-id="c6ff6-121">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c6ff6-122">Condicional</span><span class="sxs-lookup"><span data-stu-id="c6ff6-122">Conditional</span></span></td>
<td><span data-ttu-id="c6ff6-123">Evalúe los atributos del documento de origen respecto a los valores especificados.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-123">Evaluate source document attributes against specified values.</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6ff6-124">Agregado</span><span class="sxs-lookup"><span data-stu-id="c6ff6-124">Aggregate</span></span></td>
<td><span data-ttu-id="c6ff6-125">Evalúe varios documentos de origen o líneas de documento de origen respecto a una regla de directivas agregando valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-125">Evaluate multiple source documents or source document lines against a policy rule by aggregating numeric values.</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c6ff6-126">Muestra</span><span class="sxs-lookup"><span data-stu-id="c6ff6-126">Sampling</span></span></td>
<td><span data-ttu-id="c6ff6-127">Seleccione de manera aleatoria un porcentaje especificado de los documentos de origen para evaluar si se infringen las directivas.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-127">Randomly select a specified percentage of the source documents to evaluate for policy violations.</span></span></td>
<td><span data-ttu-id="c6ff6-128">Al seleccionar esta opción, use la página Regla de directivas de auditoría para especificar el porcentaje de documentos que se seleccionarán de manera aleatoria para una auditoría.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-128">When you select this option, use the Audit policy rule page to specify the percentage of documents to randomly select for audit.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6ff6-129">Duplicado</span><span class="sxs-lookup"><span data-stu-id="c6ff6-129">Duplicate</span></span></td>
<td><span data-ttu-id="c6ff6-130">Evalúe los documentos de origen para determinar si contienen entradas duplicadas en campos específicos.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-130">Evaluate source documents to determine whether they contain duplicate entries in specified fields.</span></span></td>
<td><span data-ttu-id="c6ff6-131">Al seleccionar esta opción, use la página Regla de directivas de auditoría para especificar el número de días que desea agregar al inicio del intervalo de fechas de selección de documentos al comprobar si existen entradas duplicadas en los documentos.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-131">When you select this option, use the Audit policy rule page to specify the number of days to add to the start of the document selection date range when documents are evaluated for duplicate entries.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c6ff6-132">Enumerar búsqueda</span><span class="sxs-lookup"><span data-stu-id="c6ff6-132">List search</span></span></td>
<td><span data-ttu-id="c6ff6-133">Evalúe entidades específicas de los documentos de origen.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-133">Evaluate source documents for specific entities.</span></span></td>
<td><span data-ttu-id="c6ff6-134">El documento raíz de la consulta define el documento al que se está realizando la auditoría.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-134">The root document of the query defines the document that is being audited.</span></span> <span data-ttu-id="c6ff6-135">La consulta debe ser una consulta de lista que incluya una referencia a la tabla dirpartytable.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-135">The query must be a list query that includes a reference to the dirpartytable table.</span></span> <span data-ttu-id="c6ff6-136">Esta opción sólo se puede usar con las siguientes consultas del AOT:</span><span class="sxs-lookup"><span data-stu-id="c6ff6-136">This option can be used only with the following AOT queries:</span></span>
<ul>
<li><span data-ttu-id="c6ff6-137"><span class="ui">AuditPolicyExpenseList</span> (Empleados supervisados del informe de gastos)</span><span class="sxs-lookup"><span data-stu-id="c6ff6-137"><span class="ui">AuditPolicyExpenseList</span> (Expense report monitored employees)</span></span></li>
<li><span data-ttu-id="c6ff6-138"><span class="ui">AuditPolicyPurchList</span> (Proveedores supervisados de pedido de compra)</span><span class="sxs-lookup"><span data-stu-id="c6ff6-138"><span class="ui">AuditPolicyPurchList</span> (Purchase order monitored vendors)</span></span></li>
<li><span data-ttu-id="c6ff6-139"><span class="ui">AuditPolicyVendInvoiceList</span> (proveedores supervisados de factura de proveedor)</span><span class="sxs-lookup"><span data-stu-id="c6ff6-139"><span class="ui">AuditPolicyVendInvoiceList</span> (Vendor invoice monitored vendors)</span></span></li>
</ul>
<span data-ttu-id="c6ff6-140">Al seleccionar esta opción, especifique las entidades supervisadas en la página Regla de directivas de auditoría.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-140">When you select this option, specify the monitored entities in the Audit policy rule page.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6ff6-141">Búsqueda de palabra clave</span><span class="sxs-lookup"><span data-stu-id="c6ff6-141">Keyword search</span></span></td>
<td><span data-ttu-id="c6ff6-142">Evalúe los documentos de origen para determinar si contienen ciertas palabras.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-142">Evaluate source documents to determine whether they contain certain words.</span></span></td>
<td><span data-ttu-id="c6ff6-143">Al seleccionar esta opción, especifique las palabras que se buscarán en la página Regla de directivas de auditoría.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-143">When you select this option, enter the words to look for in the Audit policy rule page.</span></span> <span data-ttu-id="c6ff6-144">La página Regla de directivas de auditoría también incluye opciones que permiten especificar las tablas y campos en que desea buscar las palabras especificadas.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-144">The Audit policy rule page also includes options that let you specify the tables and fields to evaluate for the words you entered.</span></span></td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a><span data-ttu-id="c6ff6-145">Parámetros comunes</span><span class="sxs-lookup"><span data-stu-id="c6ff6-145">Common parameters</span></span>
<span data-ttu-id="c6ff6-146">Todas las reglas de directivas de una directiva de auditoría concreta comparten los mismos parámetros de lotes y el mismo intervalo de fechas de selección de documentos.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-146">All of the policy rules for a particular audit policy share the same batch parameters and the same document selection date range.</span></span> <span data-ttu-id="c6ff6-147">Estos parámetros se especifican para la directiva en la página Opciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="c6ff6-147">These parameters are specified for the policy in the Additional options page.</span></span>



<a name="additional-resources"></a><span data-ttu-id="c6ff6-148">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c6ff6-148">Additional resources</span></span>
--------

<span data-ttu-id="c6ff6-149">[Infracciones de directivas de auditoría y casos](audit-policy-violations-cases.md)
[Defina directivas de auditoría para los documentos de origen](tasks/define-audit-policies-source-documents.md)</span><span class="sxs-lookup"><span data-stu-id="c6ff6-149">[Audit policy violations and cases](audit-policy-violations-cases.md)
[Define audit policies for source documents](tasks/define-audit-policies-source-documents.md)</span></span>



