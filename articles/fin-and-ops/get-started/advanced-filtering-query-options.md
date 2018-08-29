---
title: Sintaxis de consulta y filtro avanzados
description: "Este artículo describe el filtrado y las opciones de consulta que están disponibles cuando usa el diálogo Ordenación o filtro avanzados o el operador **coincide** en el panel de filtro o los filtros de los encabezados de las columnas de la cuadrícula."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: edff2fba7e231ae52abf7828d55c1fe4841ccd7f
ms.openlocfilehash: 3e7127a9412dcf9324872c06fbf6cc3cf61bf063
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="advanced-filtering-and-query-syntax"></a><span data-ttu-id="0d3a9-103">Sintaxis de consulta y filtro avanzados</span><span class="sxs-lookup"><span data-stu-id="0d3a9-103">Advanced filtering and query syntax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0d3a9-104">Este artículo describe el filtrado y las opciones de consulta que están disponibles cuando usa el diálogo Ordenación o filtro avanzados o el operador **coincide** en el panel de filtro o los filtros de los encabezados de las columnas de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-104">This article describes the filtering and query options that are available when you use the Advanced filter/sort dialog or the **matches** operator in the Filter pane or grid column header filters.</span></span> 

<a name="advanced-query-syntax"></a><span data-ttu-id="0d3a9-105">Sintaxis de consulta avanzada</span><span class="sxs-lookup"><span data-stu-id="0d3a9-105">Advanced query syntax</span></span>
---------------------

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d3a9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d3a9-106">Syntax</span></span></th>
<th><span data-ttu-id="0d3a9-107">Descripción de carácter</span><span class="sxs-lookup"><span data-stu-id="0d3a9-107">Character description</span></span></th>
<th><span data-ttu-id="0d3a9-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d3a9-108">Description</span></span></th>
<th><span data-ttu-id="0d3a9-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d3a9-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0d3a9-110"><em>valor</em></span><span class="sxs-lookup"><span data-stu-id="0d3a9-110"><em>value</em></span></span></td>
<td><span data-ttu-id="0d3a9-111">Igual que el valor que se especifica</span><span class="sxs-lookup"><span data-stu-id="0d3a9-111">Equal to the value that is entered</span></span></td>
<td><span data-ttu-id="0d3a9-112">Escriba el valor que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-112">Type the value to find.</span></span></td>
<td><span data-ttu-id="0d3a9-113"><strong>Serrano</strong> encuentra &quot;Serrano&quot;.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-113"><strong>Smith</strong> finds &quot;Smith&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d3a9-114">!<em>valor</em> (signo de exclamación)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-114">!<em>value</em> (exclamation point)</span></span></td>
<td><span data-ttu-id="0d3a9-115">No es igual que el valor que se especifica</span><span class="sxs-lookup"><span data-stu-id="0d3a9-115">Not equal to the value that is entered</span></span></td>
<td><span data-ttu-id="0d3a9-116">Escriba un signo de exclamación y, después, el valor que desee excluir.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-116">Type an exclamation point and then the value to exclude.</span></span></td>
<td><span data-ttu-id="0d3a9-117"><strong>!Serrano</strong> encuentra todos los valores excepto &quot;Serrano&quot;.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-117"><strong>!Smith</strong> finds all values except &quot;Smith&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d3a9-118"><em>valor-inicial</em>..<em>valor-final</em> (dos puntos seguidos)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-118"><em>from-value</em>..<em>to-value</em> (double period)</span></span></td>
<td><span data-ttu-id="0d3a9-119">Entre los dos valores que están separados por dos puntos seguidos</span><span class="sxs-lookup"><span data-stu-id="0d3a9-119">Between the two values that are separated by double periods</span></span></td>
<td><span data-ttu-id="0d3a9-120">Escriba el valor inicial, después los dos puntos y, por último, el valor final.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-120">Type the from-value, then two periods, and then the to-value.</span></span></td>
<td><span data-ttu-id="0d3a9-121"><strong>1..10</strong> encuentra todos los valores desde 1 hasta 10.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-121"><strong>1..10</strong> finds all values from 1 through 10.</span></span> <span data-ttu-id="0d3a9-122">No obstante, en un campo de cadena, <strong>A..C</strong> encuentra todos los valores que empiezan por &quot;A&quot; y &quot;B&quot; y los valores que son exactamente iguales a &quot;C&quot;.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-122">However, in a string field, <strong>A..C</strong> finds all values that start with &quot;A&quot; and &quot;B&quot;, and values that are exactly equal to &quot;C&quot;.</span></span> <span data-ttu-id="0d3a9-123">Por ejemplo, esta consulta no encontrará &quot;Ca&quot;.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-123">For example, this query won&#39;t find &quot;Ca&quot;.</span></span> <span data-ttu-id="0d3a9-124">Para encontrar todos los valores de la &quot;A<em>&quot; a la &quot;C</em>&quot;, escriba <strong>A..D</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-124">To find all values from &quot;A<em>&quot; through &quot;C</em>&quot;, type <strong>A..D</strong>.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d3a9-125">..<em>valor</em> (dos puntos seguidos)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-125">..<em>value</em> (double period)</span></span></td>
<td><span data-ttu-id="0d3a9-126">Menor o igual que el valor especificado</span><span class="sxs-lookup"><span data-stu-id="0d3a9-126">Less than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="0d3a9-127">Escriba los dos puntos y, a continuación, el valor.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-127">Type two periods and then the value.</span></span></td>
<td><span data-ttu-id="0d3a9-128"><strong>..1000</strong> encuentra cualquier número menor o igual que 1000, por ejemplo &quot;100&quot;, &quot;999,95&quot; y &quot;1000&quot;.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-128"><strong>..1000</strong> finds any number that is less than or equal to 1000, such as &quot;100&quot;, &quot;999.95&quot;, and &quot;1,000&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d3a9-129"><em>valor</em>..</span><span class="sxs-lookup"><span data-stu-id="0d3a9-129"><em>value</em>..</span></span> <span data-ttu-id="0d3a9-130">(doble punto)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-130">(double period)</span></span></td>
<td><span data-ttu-id="0d3a9-131">Mayor o igual que el valor especificado</span><span class="sxs-lookup"><span data-stu-id="0d3a9-131">Greater than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="0d3a9-132">Escriba el valor y, a continuación, dos puntos .</span><span class="sxs-lookup"><span data-stu-id="0d3a9-132">Type the value and then two periods.</span></span></td>
<td><span data-ttu-id="0d3a9-133"><strong>1000..</strong></span><span class="sxs-lookup"><span data-stu-id="0d3a9-133"><strong>1000..</strong></span></span> <span data-ttu-id="0d3a9-134">encuentra cualquier número mayor o igual que 1000, por ejemplo &quot;1000&quot;, &quot;1000,01&quot; y &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-134">finds any number that is greater than or equal to 1000, such as &quot;1,000&quot;, &quot;1,000.01&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d3a9-135">&gt;<em>valor</em> (signo mayor que)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-135">&gt;<em>value</em> (greater than sign)</span></span></td>
<td><span data-ttu-id="0d3a9-136">Mayor que el valor especificado</span><span class="sxs-lookup"><span data-stu-id="0d3a9-136">Greater than the value that is entered</span></span></td>
<td><span data-ttu-id="0d3a9-137">Escriba un signo mayor que (<strong>&gt;</strong>) y, a continuación, el valor.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-137">Type a greater than sign (<strong>&gt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="0d3a9-138"><strong>&gt;1000</strong> encuentra cualquier número mayor que 1000, por ejemplo &quot;1000,01&quot;, &quot;20 000&quot; y &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-138"><strong>&gt;1000</strong> finds any number that is greater than 1000, such as &quot;1000.01&quot;, &quot;20,000&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d3a9-139">&lt;<em>valor</em> (signo menor que)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-139">&lt;<em>value</em> (less than sign)</span></span></td>
<td><span data-ttu-id="0d3a9-140">Menor que el valor especificado</span><span class="sxs-lookup"><span data-stu-id="0d3a9-140">Less than the value that is entered</span></span></td>
<td><span data-ttu-id="0d3a9-141">Escriba un signo menor que (<strong>&lt;</strong>) y, a continuación, el valor.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-141">Type a less than sign (<strong>&lt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="0d3a9-142"><strong>&lt;1000</strong> encuentra cualquier número menor que 1000, por ejemplo &quot;999,99&quot;, &quot;1&quot; y &quot;-200&quot;.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-142"><strong>&lt;1000</strong> finds any number that is less than 1000, such as &quot;999.99&quot;, &quot;1&quot;, and &quot;-200&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d3a9-143"><em>valor</em>\* (asterisco)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-143"><em>value</em>\* (asterisk)</span></span></td>
<td><span data-ttu-id="0d3a9-144">Que empieza por el valor que se especifica</span><span class="sxs-lookup"><span data-stu-id="0d3a9-144">Starting from the value that is entered</span></span></td>
<td><span data-ttu-id="0d3a9-145">Escriba el valor inicial y, a continuación, un asterisco (<strong><em></strong>).</span><span class="sxs-lookup"><span data-stu-id="0d3a9-145">Type the starting value and then an asterisk (<strong><em></strong>).</span></span></td>
<td><span data-ttu-id="0d3a9-146"><strong>S</em></strong> encuentra cualquier cadena que empiece por &quot;S&quot;, como &quot;Estocolmo&quot;, &quot;Sidney&quot; y &quot;San Francisco&quot;.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-146"><strong>S</em></strong> finds any string that starts with &quot;S&quot;, such as &quot;Stockholm&quot;, &quot;Sydney&quot;, and &quot;San Francisco&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d3a9-147"><em><em>valor</em> (asterisco)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-147"><em><em>value</em> (asterisk)</span></span></td>
<td><span data-ttu-id="0d3a9-148">Termina por el valor que se especifica</span><span class="sxs-lookup"><span data-stu-id="0d3a9-148">Ending with the value that is entered</span></span></td>
<td><span data-ttu-id="0d3a9-149">Escriba un asterisco y, a continuación, el valor final.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-149">Type an asterisk and then the ending value.</span></span></td>
<td><span data-ttu-id="0d3a9-150"><strong></em>este</strong> encuentra cualquier cadena que termine por &quot;este&quot;, como &quot;Nordeste&quot; y &quot;Sudeste&quot;.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-150"><strong></em>east</strong> finds any string that ends with &quot;east&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d3a9-151"><em><em>valor</em></em> (asterisco)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-151"><em><em>value</em></em> (asterisk)</span></span></td>
<td><span data-ttu-id="0d3a9-152">Contiene el valor especificado</span><span class="sxs-lookup"><span data-stu-id="0d3a9-152">Containing the value that is entered</span></span></td>
<td><span data-ttu-id="0d3a9-153">Escriba un asterisco, a continuación un valor y, por último, otro asterisco.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-153">Type an asterisk, then a value, and then another asterisk.</span></span></td>
<td><span data-ttu-id="0d3a9-154"><strong><em>de</em></strong> encuentra las cadenas que contengan &quot;de&quot; como &quot;Nordeste&quot; y &quot;Sudeste&quot;.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-154"><strong><em>th</em></strong> finds any string that contains &quot;th&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d3a9-155">?</span><span class="sxs-lookup"><span data-stu-id="0d3a9-155">?</span></span> <span data-ttu-id="0d3a9-156">(signo de interrogación)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-156">(question mark)</span></span></td>
<td><span data-ttu-id="0d3a9-157">Que tenga uno o más caracteres desconocidos</span><span class="sxs-lookup"><span data-stu-id="0d3a9-157">Having one or more unknown characters</span></span></td>
<td><span data-ttu-id="0d3a9-158">Escriba un signo de interrogación en la posición del carácter desconocido en el valor.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-158">Type a question mark at the position of the unknown character in the value.</span></span></td>
<td><span data-ttu-id="0d3a9-159"><strong>Se?rr</strong> encuentra &quot;Serr&quot; y &quot;Ser&quot;.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-159"><strong>Sm?th</strong> finds &quot;Smith&quot; and &quot;Smyth&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d3a9-160"><em>valor</em>,<em>valor</em> (coma)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-160"><em>value</em>,<em>value</em> (comma)</span></span></td>
<td><span data-ttu-id="0d3a9-161">Que coincida con los valores separados por comas</span><span class="sxs-lookup"><span data-stu-id="0d3a9-161">Matching the values that are separated by commas</span></span></td>
<td><span data-ttu-id="0d3a9-162">Escriba todos los criterios y sepárelos con comas.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-162">Type all your criteria, and separate them by using commas.</span></span></td>
<td><span data-ttu-id="0d3a9-163"><strong>A, D, F, G</strong> encuentra exactamente &quot;A&quot;, &quot;D&quot;, &quot;F&quot; y &quot;G&quot;.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-163"><strong>A, D, F, G</strong> finds exactly &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, and &quot;G&quot;.</span></span> <span data-ttu-id="0d3a9-164"><strong>10, 20, 30, 100</strong> encuentra exactamente &quot;10, 20, 30, 100&quot;.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-164"><strong>10, 20, 30, 100</strong> finds exactly &quot;10, 20, 30, 100&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d3a9-165">(<span class="code">Instrucción SQL</span>) (instrucción SQL entre paréntesis)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-165">(<span class="code">SQL statement</span>) (SQL statement between parentheses)</span></span></td>
<td><span data-ttu-id="0d3a9-166">Que coincide con una consulta definida</span><span class="sxs-lookup"><span data-stu-id="0d3a9-166">Matching a defined query</span></span></td>
<td><span data-ttu-id="0d3a9-167">Escriba una consulta como una instrucción SQL entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-167">Type a query as an SQL statement between parentheses.</span></span></td>
<td><span data-ttu-id="0d3a9-168"><strong><span class="code">(origen_de_datos.Nombre_de_campo != &quot;A&quot;)</span></strong></span><span class="sxs-lookup"><span data-stu-id="0d3a9-168"><strong><span class="code">(data source.Fieldname != &quot;A&quot;)</span></strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d3a9-169">T</span><span class="sxs-lookup"><span data-stu-id="0d3a9-169">T</span></span></td>
<td><span data-ttu-id="0d3a9-170">Fecha de hoy</span><span class="sxs-lookup"><span data-stu-id="0d3a9-170">Today&#39;s date</span></span></td>
<td><span data-ttu-id="0d3a9-171">Escriba <strong>B</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-171">Type <strong>T</strong>.</span></span></td>
<td><span data-ttu-id="0d3a9-172"><strong>B</strong> coincide con la fecha de hoy.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-172"><strong>T</strong> matches today&#39;s date.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d3a9-173">(methodName(parámetros)) (<strong>método SysQueryRangeUtil</strong> entre paréntesis)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-173">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> method between parentheses)</span></span></td>
<td><span data-ttu-id="0d3a9-174">Coincide con el valor o el intervalo de valores especificados por los parámetros del método <strong>SysQueryRangeUtil</strong></span><span class="sxs-lookup"><span data-stu-id="0d3a9-174">Matching the value or range of values that are specified by the parameters of the <strong>SysQueryRangeUtil</strong> method</span></span></td>
<td><span data-ttu-id="0d3a9-175">Escriba un método <strong>SysQueryRangeUtil</strong> con los parámetros que especifican el valor o el intervalo de valores.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-175">Type a <strong>SysQueryRangeUtil</strong> method that has parameters that specify the value or range of values.</span></span></td>
<td><ol>
<li><span data-ttu-id="0d3a9-176">Haga clic en <strong>Clientes</strong> &gt; <strong>Facturas</strong> &gt; <strong>Facturas de cliente abiertas</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-176">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Open customer invoices</strong>.</span></span></li>
<li><span data-ttu-id="0d3a9-177">Presione Ctrl+Mayús+F3 para abrir la página <strong>Consulta</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-177">Press Ctrl+Shift+F3 to open the <strong>Inquiry</strong> page.</span></span></li>
<li><span data-ttu-id="0d3a9-178">En la ficha <strong>Intervalo</strong>, haga clic en <strong>Agregar</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-178">On the <strong>Range</strong> tab, click <strong>Add</strong>.</span></span></li>
<li><span data-ttu-id="0d3a9-179">En el campo <strong>Tabla</strong>, seleccione <strong>Transacciones de cliente abiertas</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-179">In the <strong>Table</strong> field, select <strong>Open customer transactions</strong>.</span></span></li>
<li><span data-ttu-id="0d3a9-180">En el campo <strong>Campo</strong>, seleccione <strong>Fecha de vencimiento</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-180">In the <strong>Field</strong> field, select <strong>Due date</strong>.</span></span></li>
<li><span data-ttu-id="0d3a9-181">En el campo <strong>Criterios</strong>, escriba <strong>(yearRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-181">In the <strong>Criteria</strong> field, enter <strong>(yearRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="0d3a9-182">Haga clic en <strong>Aceptar</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-182">Click <strong>OK</strong>.</span></span> <span data-ttu-id="0d3a9-183">La página de lista se actualiza para mostrar las facturas que coincidan con el criterio especificado.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-183">The list page is updated and lists the invoices that match the criterion that you entered.</span></span> <span data-ttu-id="0d3a9-184">En este ejemplo, se muestran las facturas vencidas en los dos años anteriores.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-184">For this example, invoices that were due in the previous two years are listed.</span></span></li>
</ol>
<span data-ttu-id="0d3a9-185">Consulte la tabla en la sección siguiente para ver los detalles adicionales sobre los métodos de fecha <strong>SysQueryRangeUtil</strong> y varios ejemplos.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-185">See the table in the next section for additional details about <strong>SysQueryRangeUtil</strong> date methods, and several examples.</span></span></td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a><span data-ttu-id="0d3a9-186">Consultas de fecha avanzadas que usan los métodos SysQueryRangeUtil</span><span class="sxs-lookup"><span data-stu-id="0d3a9-186">Advanced date queries that use SysQueryRangeUtil methods</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d3a9-187">Método</span><span class="sxs-lookup"><span data-stu-id="0d3a9-187">Method</span></span></th>
<th><span data-ttu-id="0d3a9-188">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d3a9-188">Description</span></span></th>
<th><span data-ttu-id="0d3a9-189">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d3a9-189">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0d3a9-190">Día (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-190">Day (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="0d3a9-191">Busca una fecha en relación con la fecha de la sesión.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-191">Find a date relative to the session date.</span></span> <span data-ttu-id="0d3a9-192">Los valores positivos indican fechas futuras y los valores negativos indican fechas anteriores.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-192">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td><ul>
<li><span data-ttu-id="0d3a9-193"><strong>Mañana</strong>: introduzca <strong>(Día (1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-193"><strong>Tomorrow</strong> – Enter <strong>(Day(1))</strong>.</span></span></li>
<li><span data-ttu-id="0d3a9-194"><strong>Hoy</strong>: introduzca <strong>(Día(0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-194"><strong>Today</strong> – Enter <strong>(Day(0))</strong>.</span></span></li>
<li><span data-ttu-id="0d3a9-195"><strong>Ayer</strong>: introduzca <strong>(Día(-1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-195"><strong>Yesterday</strong> – Enter <strong>(Day(-1))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d3a9-196">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-196">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span></span></td>
<td><span data-ttu-id="0d3a9-197">Busca un intervalo de fechas en relación con la fecha de la sesión.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-197">Find a range of dates relative to the session date.</span></span> <span data-ttu-id="0d3a9-198">Los valores positivos indican fechas futuras y los valores negativos indican fechas anteriores.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-198">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td><ul>
<li><span data-ttu-id="0d3a9-199"><strong>Últimos 30 días</strong>: introduzca <strong>(DayRange(-30,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-199"><strong>Last 30 days</strong> – Enter <strong>(DayRange(-30,0))</strong>.</span></span></li>
<li><span data-ttu-id="0d3a9-200"><strong>30 días anteriores y futuros</strong>: especifique <strong>(DayRange(-30,30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-200"><strong>Previous 30 days and next 30 days</strong> – Enter <strong>(DayRange(-30,30))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d3a9-201">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-201">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="0d3a9-202">Busca todas las fechas después de la fecha relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-202">Find all dates after the specified relative date.</span></span></td>
<td><ul>
<li><span data-ttu-id="0d3a9-203"><strong>Más de 30 días a partir de ahora</strong>: especifique <strong>(GreaterThanDate(30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-203"><strong>More than 30 days from now</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d3a9-204">GreaterThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="0d3a9-204">GreaterThanUtcNow ()</span></span></td>
<td><span data-ttu-id="0d3a9-205">Busca todas las entradas de hora o fecha posteriores a la hora actual.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-205">Find all date/time entries after the current time.</span></span></td>
<td><ul>
<li><span data-ttu-id="0d3a9-206"><strong>Todas las horas o fechas futuras</strong>: especifique <strong>(GreaterThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-206"><strong>All future date/times</strong> – Enter <strong>(GreaterThanUtcNow())</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d3a9-207">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-207">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="0d3a9-208">Busca todas las fechas anteriores a la fecha relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-208">Find all dates before the specified relative date.</span></span></td>
<td><ul>
<li><span data-ttu-id="0d3a9-209"><strong>Menos de siete días desde ahora</strong>: especifique <strong>(LessThanDate(7))</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-209"><strong>Less than seven days from now</strong> – Enter <strong>(LessThanDate(7))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d3a9-210">LessThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="0d3a9-210">LessThanUtcNow ()</span></span></td>
<td><span data-ttu-id="0d3a9-211">Busca todas las entradas de hora o fecha anteriores a la hora actual.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-211">Find all date/time entries before the current time.</span></span></td>
<td><ul>
<li><span data-ttu-id="0d3a9-212"><strong>Todas las horas o fechas anteriores</strong>: especifique <strong>(LessThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-212"><strong>All past date/times</strong> – Enter <strong>(LessThanUtcNow())</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d3a9-213">MonthRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-213">MonthRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="0d3a9-214">Busca un intervalo de fechas, en función de meses en relación con el mes actual.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-214">Find a range of dates, based on months relative to the current month.</span></span></td>
<td><ul>
<li><span data-ttu-id="0d3a9-215"><strong>Dos meses anteriores</strong>: especifique <strong>(MonthRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-215"><strong>Previous two months</strong> – Enter <strong>(MonthRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="0d3a9-216"><strong>Los tres meses siguientes</strong>: especifique <strong>(MonthRange(0,3))</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-216"><strong>Next three months</strong> – Enter <strong>(MonthRange(0,3))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d3a9-217">YearRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="0d3a9-217">YearRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="0d3a9-218">Busca un intervalo de fechas, en función de años en relación con el año actual.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-218">Find a range of dates, based on years relative to the current year.</span></span></td>
<td><ul>
<li><span data-ttu-id="0d3a9-219"><strong>Año próximo</strong>: especifique <strong>(YearRange(0, 1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-219"><strong>Next year</strong> – Enter <strong>(YearRange(0, 1))</strong>.</span></span></li>
<li><span data-ttu-id="0d3a9-220"><strong>Año anterior</strong>: especifique <strong>(YearRange(-1,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d3a9-220"><strong>Previous year</strong> – Enter <strong>(YearRange(-1,0))</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>






