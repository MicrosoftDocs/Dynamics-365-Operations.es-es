---
title: Sintaxis de consulta y filtro avanzados
description: Este tema describe el filtrado y las opciones de consulta que están disponibles cuando usa el diálogo Ordenación o filtro avanzados o el operador coincide en el panel de filtro o los filtros de los encabezados de las columnas de la cuadrícula.
author: jasongre
manager: AnnBe
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 15805e24c46603afd34d40c5f94c1422b01cab4c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566075"
---
# <a name="advanced-filtering-and-query-syntax"></a><span data-ttu-id="4675f-103">Sintaxis de consulta y filtro avanzados</span><span class="sxs-lookup"><span data-stu-id="4675f-103">Advanced filtering and query syntax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4675f-104">Este tema describe el filtrado y las opciones de consulta que están disponibles cuando usa el diálogo Ordenación o filtro avanzados o el operador **coincide** en el panel de filtro o los filtros de los encabezados de las columnas de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="4675f-104">This topic describes the filtering and query options that are available when you use the Advanced filter/sort dialog or the **matches** operator in the Filter pane or grid column header filters.</span></span>

## <a name="advanced-query-syntax"></a><span data-ttu-id="4675f-105">Sintaxis de consulta avanzada</span><span class="sxs-lookup"><span data-stu-id="4675f-105">Advanced query syntax</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4675f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4675f-106">Syntax</span></span></th>
<th><span data-ttu-id="4675f-107">Descripción de carácter</span><span class="sxs-lookup"><span data-stu-id="4675f-107">Character description</span></span></th>
<th><span data-ttu-id="4675f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4675f-108">Description</span></span></th>
<th><span data-ttu-id="4675f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4675f-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4675f-110"><em>valor</em></span><span class="sxs-lookup"><span data-stu-id="4675f-110"><em>value</em></span></span></td>
<td><span data-ttu-id="4675f-111">Igual que el valor que se especifica</span><span class="sxs-lookup"><span data-stu-id="4675f-111">Equal to the value that is entered</span></span></td>
<td><span data-ttu-id="4675f-112">Escriba el valor que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="4675f-112">Type the value to find.</span></span></td>
<td><span data-ttu-id="4675f-113"><strong>Serrano</strong> encuentra &quot;Serrano&quot;.</span><span class="sxs-lookup"><span data-stu-id="4675f-113"><strong>Smith</strong> finds &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4675f-114">!<em>valor</em> (signo de exclamación)</span><span class="sxs-lookup"><span data-stu-id="4675f-114">!<em>value</em> (exclamation point)</span></span></td>
<td><span data-ttu-id="4675f-115">No es igual que el valor que se especifica</span><span class="sxs-lookup"><span data-stu-id="4675f-115">Not equal to the value that is entered</span></span></td>
<td><span data-ttu-id="4675f-116">Escriba un signo de exclamación y, después, el valor que desee excluir.</span><span class="sxs-lookup"><span data-stu-id="4675f-116">Type an exclamation point and then the value to exclude.</span></span></td>
<td><span data-ttu-id="4675f-117"><strong>!Serrano</strong> encuentra todos los valores excepto &quot;Serrano&quot;.</span><span class="sxs-lookup"><span data-stu-id="4675f-117"><strong>!Smith</strong> finds all values except &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4675f-118"><em>valor-inicial</em>..<em>valor-final</em> (dos puntos seguidos)</span><span class="sxs-lookup"><span data-stu-id="4675f-118"><em>from-value</em>..<em>to-value</em> (double period)</span></span></td>
<td><span data-ttu-id="4675f-119">Entre los dos valores que están separados por dos puntos seguidos</span><span class="sxs-lookup"><span data-stu-id="4675f-119">Between the two values that are separated by double periods</span></span></td>
<td><span data-ttu-id="4675f-120">Escriba el valor inicial, después los dos puntos y, por último, el valor final.</span><span class="sxs-lookup"><span data-stu-id="4675f-120">Type the from-value, then two periods, and then the to-value.</span></span></td>
<td><span data-ttu-id="4675f-121"><strong>1..10</strong> encuentra todos los valores desde 1 hasta 10.</span><span class="sxs-lookup"><span data-stu-id="4675f-121"><strong>1..10</strong> finds all values from 1 through 10.</span></span> <span data-ttu-id="4675f-122">No obstante, en un campo de cadena, <strong>A..C</strong> encuentra todos los valores que empiezan por &quot;A&quot; y &quot;B&quot; y los valores que son exactamente iguales a &quot;C&quot;.</span><span class="sxs-lookup"><span data-stu-id="4675f-122">However, in a string field, <strong>A..C</strong> finds all values that start with &quot;A&quot; and &quot;B&quot;, and values that are exactly equal to &quot;C&quot;.</span></span> <span data-ttu-id="4675f-123">Por ejemplo, esta consulta no encontrará &quot;Ca&quot;.</span><span class="sxs-lookup"><span data-stu-id="4675f-123">For example, this query won't find &quot;Ca&quot;.</span></span> <span data-ttu-id="4675f-124">Para encontrar todos los valores de la &quot;A<em>&quot; a la &quot;C</em>&quot;, escriba <strong>A..D</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-124">To find all values from &quot;A<em>&quot; through &quot;C</em>&quot;, type <strong>A..D</strong>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4675f-125">..<em>valor</em> (dos puntos seguidos)</span><span class="sxs-lookup"><span data-stu-id="4675f-125">..<em>value</em> (double period)</span></span></td>
<td><span data-ttu-id="4675f-126">Menor o igual que el valor especificado</span><span class="sxs-lookup"><span data-stu-id="4675f-126">Less than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="4675f-127">Escriba los dos puntos y, a continuación, el valor.</span><span class="sxs-lookup"><span data-stu-id="4675f-127">Type two periods and then the value.</span></span></td>
<td><span data-ttu-id="4675f-128"><strong>..1000</strong> encuentra cualquier número menor o igual que 1000, por ejemplo &quot;100&quot;, &quot;999,95&quot; y &quot;1000&quot;.</span><span class="sxs-lookup"><span data-stu-id="4675f-128"><strong>..1000</strong> finds any number that is less than or equal to 1000, such as &quot;100&quot;, &quot;999.95&quot;, and &quot;1,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4675f-129"><em>valor</em>..</span><span class="sxs-lookup"><span data-stu-id="4675f-129"><em>value</em>..</span></span> <span data-ttu-id="4675f-130">(doble punto)</span><span class="sxs-lookup"><span data-stu-id="4675f-130">(double period)</span></span></td>
<td><span data-ttu-id="4675f-131">Mayor o igual que el valor especificado</span><span class="sxs-lookup"><span data-stu-id="4675f-131">Greater than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="4675f-132">Escriba el valor y, a continuación, dos puntos .</span><span class="sxs-lookup"><span data-stu-id="4675f-132">Type the value and then two periods.</span></span></td>
<td><span data-ttu-id="4675f-133"><strong>1000..</strong></span><span class="sxs-lookup"><span data-stu-id="4675f-133"><strong>1000..</strong></span></span> <span data-ttu-id="4675f-134">encuentra cualquier número mayor o igual que 1000, por ejemplo &quot;1000&quot;, &quot;1000,01&quot; y &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="4675f-134">finds any number that is greater than or equal to 1000, such as &quot;1,000&quot;, &quot;1,000.01&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4675f-135">&gt;<em>valor</em> (signo mayor que)</span><span class="sxs-lookup"><span data-stu-id="4675f-135">&gt;<em>value</em> (greater than sign)</span></span></td>
<td><span data-ttu-id="4675f-136">Mayor que el valor especificado</span><span class="sxs-lookup"><span data-stu-id="4675f-136">Greater than the value that is entered</span></span></td>
<td><span data-ttu-id="4675f-137">Escriba un signo mayor que (<strong>&gt;</strong>) y, a continuación, el valor.</span><span class="sxs-lookup"><span data-stu-id="4675f-137">Type a greater than sign (<strong>&gt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="4675f-138"><strong>&gt;1000</strong> encuentra cualquier número mayor que 1000, por ejemplo &quot;1000,01&quot;, &quot;20 000&quot; y &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="4675f-138"><strong>&gt;1000</strong> finds any number that is greater than 1000, such as &quot;1000.01&quot;, &quot;20,000&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4675f-139">&lt;<em>valor</em> (signo menor que)</span><span class="sxs-lookup"><span data-stu-id="4675f-139">&lt;<em>value</em> (less than sign)</span></span></td>
<td><span data-ttu-id="4675f-140">Menor que el valor especificado</span><span class="sxs-lookup"><span data-stu-id="4675f-140">Less than the value that is entered</span></span></td>
<td><span data-ttu-id="4675f-141">Escriba un signo menor que (<strong>&lt;</strong>) y, a continuación, el valor.</span><span class="sxs-lookup"><span data-stu-id="4675f-141">Type a less than sign (<strong>&lt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="4675f-142"><strong>&lt;1000</strong> encuentra cualquier número menor que 1000, por ejemplo &quot;999,99&quot;, &quot;1&quot; y &quot;-200&quot;.</span><span class="sxs-lookup"><span data-stu-id="4675f-142"><strong>&lt;1000</strong> finds any number that is less than 1000, such as &quot;999.99&quot;, &quot;1&quot;, and &quot;-200&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4675f-143"><em>valor</em>\* (asterisco)</span><span class="sxs-lookup"><span data-stu-id="4675f-143"><em>value</em>\* (asterisk)</span></span></td>
<td><span data-ttu-id="4675f-144">Que empieza por el valor que se especifica</span><span class="sxs-lookup"><span data-stu-id="4675f-144">Starting from the value that is entered</span></span></td>
<td><span data-ttu-id="4675f-145">Escriba el valor inicial y, a continuación, un asterisco (<strong>\*</strong>).</span><span class="sxs-lookup"><span data-stu-id="4675f-145">Type the starting value and then an asterisk (<strong>\*</strong>).</span></span></td>
<td><span data-ttu-id="4675f-146"><strong>S\*</strong> encuentra cualquier cadena que empiece por &quot;S&quot;, como &quot;Suecia&quot;, &quot;Sydney&quot; y &quot;San Francisco&quot;.</span><span class="sxs-lookup"><span data-stu-id="4675f-146"><strong>S\*</strong> finds any string that starts with &quot;S&quot;, such as &quot;Stockholm&quot;, &quot;Sydney&quot;, and &quot;San Francisco&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4675f-147">\*<em>valor</em> (asterisco)</span><span class="sxs-lookup"><span data-stu-id="4675f-147">\*<em>value</em> (asterisk)</span></span></td>
<td><span data-ttu-id="4675f-148">Termina por el valor que se especifica</span><span class="sxs-lookup"><span data-stu-id="4675f-148">Ending with the value that is entered</span></span></td>
<td><span data-ttu-id="4675f-149">Escriba un asterisco y, a continuación, el valor final.</span><span class="sxs-lookup"><span data-stu-id="4675f-149">Type an asterisk and then the ending value.</span></span></td>
<td><span data-ttu-id="4675f-150"><strong>\*este</strong> encuentra cualquier cadena que termine por &quot;este&quot;, como &quot;Nordeste&quot; y &quot;Sudeste&quot;.</span><span class="sxs-lookup"><span data-stu-id="4675f-150"><strong>\*east</strong> finds any string that ends with &quot;east&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4675f-151">*<em>valor</em>* (asterisco)</span><span class="sxs-lookup"><span data-stu-id="4675f-151">*<em>value</em>* (asterisk)</span></span></td>
<td><span data-ttu-id="4675f-152">Contiene el valor especificado</span><span class="sxs-lookup"><span data-stu-id="4675f-152">Containing the value that is entered</span></span></td>
<td><span data-ttu-id="4675f-153">Escriba un asterisco, a continuación un valor y, por último, otro asterisco.</span><span class="sxs-lookup"><span data-stu-id="4675f-153">Type an asterisk, then a value, and then another asterisk.</span></span></td>
<td><span data-ttu-id="4675f-154"><strong>*de*</strong> encuentra las cadenas que contengan &quot;de&quot; como &quot;Nordeste&quot; y &quot;Sudeste&quot;.</span><span class="sxs-lookup"><span data-stu-id="4675f-154"><strong>*th*</strong> finds any string that contains &quot;th&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4675f-155">?</span><span class="sxs-lookup"><span data-stu-id="4675f-155">?</span></span> <span data-ttu-id="4675f-156">(signo de interrogación)</span><span class="sxs-lookup"><span data-stu-id="4675f-156">(question mark)</span></span></td>
<td><span data-ttu-id="4675f-157">Que tenga uno o más caracteres desconocidos</span><span class="sxs-lookup"><span data-stu-id="4675f-157">Having one or more unknown characters</span></span></td>
<td><span data-ttu-id="4675f-158">Escriba un signo de interrogación en la posición del carácter desconocido en el valor.</span><span class="sxs-lookup"><span data-stu-id="4675f-158">Type a question mark at the position of the unknown character in the value.</span></span></td>
<td><span data-ttu-id="4675f-159"><strong>Se?rr</strong> encuentra &quot;Serr&quot; y &quot;Ser&quot;.</span><span class="sxs-lookup"><span data-stu-id="4675f-159"><strong>Sm?th</strong> finds &quot;Smith&quot; and &quot;Smyth&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4675f-160"><em>valor</em>,<em>valor</em> (coma)</span><span class="sxs-lookup"><span data-stu-id="4675f-160"><em>value</em>,<em>value</em> (comma)</span></span></td>
<td><span data-ttu-id="4675f-161">Que coincida con los valores separados por comas</span><span class="sxs-lookup"><span data-stu-id="4675f-161">Matching the values that are separated by commas</span></span></td>
<td><span data-ttu-id="4675f-162">Escriba todos los criterios y sepárelos con comas.</span><span class="sxs-lookup"><span data-stu-id="4675f-162">Type all your criteria, and separate them by using commas.</span></span></td>
<td><span data-ttu-id="4675f-163"><strong>A, D, F, G</strong> encuentra exactamente &quot;A&quot;, &quot;D&quot;, &quot;F&quot; y &quot;G&quot;.</span><span class="sxs-lookup"><span data-stu-id="4675f-163"><strong>A, D, F, G</strong> finds exactly &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, and &quot;G&quot;.</span></span> <span data-ttu-id="4675f-164"><strong>10, 20, 30, 100</strong> encuentra exactamente &quot;10, 20, 30, 100&quot;.</span><span class="sxs-lookup"><span data-stu-id="4675f-164"><strong>10, 20, 30, 100</strong> finds exactly &quot;10, 20, 30, 100&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4675f-165">"" (dos comillas dobles)</span><span class="sxs-lookup"><span data-stu-id="4675f-165">"" (two double quotes)</span></span></td>
<td><span data-ttu-id="4675f-166">Hacer coincidir un valor en blanco</span><span class="sxs-lookup"><span data-stu-id="4675f-166">Matching a blank value</span></span></td>
<td><span data-ttu-id="4675f-167">Escriba dos comillas dobles consecutivas para filtrar valores en blanco en ese campo.</span><span class="sxs-lookup"><span data-stu-id="4675f-167">Type two consecutive double quotes to filter for blank values in that field.</span></span></td>
<td><span data-ttu-id="4675f-168">Dos comillas dobles consecutivas (<strong>""</strong>) busca filas sin valor para la columna actual.</span><span class="sxs-lookup"><span data-stu-id="4675f-168">Two consecutive double quotes (<strong>""</strong>) finds rows with no value for the current column.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4675f-169">(<span class="code">Finance and Operations consulta</span>) (Finance and Operations consulta entre paréntesis)</span><span class="sxs-lookup"><span data-stu-id="4675f-169">(<span class="code">Finance and Operations query</span>) (Finance and Operations query between parentheses)</span></span></td>
<td><span data-ttu-id="4675f-170">Que coincide con una consulta definida</span><span class="sxs-lookup"><span data-stu-id="4675f-170">Matching a defined query</span></span></td>
<td><span data-ttu-id="4675f-171">Escriba una consulta como una declaración SQL entre paréntesis utilizando el lenguaje de consulta de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4675f-171">Type a query as an SQL statement between parentheses using the Finance and Operations query language.</span></span></td>
  <td><span data-ttu-id="4675f-172"><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong></span><span class="sxs-lookup"><span data-stu-id="4675f-172"><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong></span></span><br><br> 
       <span data-ttu-id="4675f-173">Como ejemplo de sintaxis para una condición de filtro en un campo del origen de datos raíz, así como un campo de un origen de datos diferente (para la página Todos los clientes)</span><span class="sxs-lookup"><span data-stu-id="4675f-173">as an example of syntax for a filter condition on a field from the root datasource as well as a field from a different datasource (for the All customers page)</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4675f-174">M</span><span class="sxs-lookup"><span data-stu-id="4675f-174">T</span></span></td>
<td><span data-ttu-id="4675f-175">Fecha de hoy</span><span class="sxs-lookup"><span data-stu-id="4675f-175">Today's date</span></span></td>
<td><span data-ttu-id="4675f-176">Escriba <strong>B</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-176">Type <strong>T</strong>.</span></span></td>
<td><span data-ttu-id="4675f-177"><strong>B</strong> coincide con la fecha de hoy.</span><span class="sxs-lookup"><span data-stu-id="4675f-177"><strong>T</strong> matches today's date.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4675f-178">(methodName(parámetros)) (<strong>método SysQueryRangeUtil</strong> entre paréntesis)</span><span class="sxs-lookup"><span data-stu-id="4675f-178">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> method between parentheses)</span></span></td>
<td><span data-ttu-id="4675f-179">Coincide con el valor o el intervalo de valores especificados por los parámetros del método <strong>SysQueryRangeUtil</strong></span><span class="sxs-lookup"><span data-stu-id="4675f-179">Matching the value or range of values that are specified by the parameters of the <strong>SysQueryRangeUtil</strong> method</span></span></td>
<td><span data-ttu-id="4675f-180">Escriba un método <strong>SysQueryRangeUtil</strong> con los parámetros que especifican el valor o el intervalo de valores.</span><span class="sxs-lookup"><span data-stu-id="4675f-180">Type a <strong>SysQueryRangeUtil</strong> method that has parameters that specify the value or range of values.</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4675f-181">Haga clic en <strong>Clientes</strong> &gt; <strong>Facturas</strong> &gt; <strong>Facturas de cliente abiertas</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-181">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Open customer invoices</strong>.</span></span></li>
<li><span data-ttu-id="4675f-182">Presione Ctrl+Mayús+F3 para abrir la página <strong>Consulta</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-182">Press Ctrl+Shift+F3 to open the <strong>Inquiry</strong> page.</span></span></li>
<li><span data-ttu-id="4675f-183">En la ficha <strong>Intervalo</strong>, haga clic en <strong>Agregar</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-183">On the <strong>Range</strong> tab, click <strong>Add</strong>.</span></span></li>
<li><span data-ttu-id="4675f-184">En el campo <strong>Tabla</strong>, seleccione <strong>Transacciones de cliente abiertas</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-184">In the <strong>Table</strong> field, select <strong>Open customer transactions</strong>.</span></span></li>
<li><span data-ttu-id="4675f-185">En el campo <strong>Campo</strong>, seleccione <strong>Fecha de vencimiento</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-185">In the <strong>Field</strong> field, select <strong>Due date</strong>.</span></span></li>
<li><span data-ttu-id="4675f-186">En el campo <strong>Criterios</strong>, escriba <strong>(yearRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-186">In the <strong>Criteria</strong> field, enter <strong>(yearRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="4675f-187">Haga clic en <strong>Aceptar</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-187">Click <strong>OK</strong>.</span></span> <span data-ttu-id="4675f-188">La página de lista se actualiza para mostrar las facturas que coincidan con el criterio especificado.</span><span class="sxs-lookup"><span data-stu-id="4675f-188">The list page is updated and lists the invoices that match the criterion that you entered.</span></span> <span data-ttu-id="4675f-189">En este ejemplo, se muestran las facturas vencidas en los dos años anteriores.</span><span class="sxs-lookup"><span data-stu-id="4675f-189">For this example, invoices that were due in the previous two years are listed.</span></span></li>
</ol>
<span data-ttu-id="4675f-190">Consulte la tabla en la sección siguiente para ver los detalles adicionales sobre los métodos de fecha <strong>SysQueryRangeUtil</strong> y varios ejemplos.</span><span class="sxs-lookup"><span data-stu-id="4675f-190">See the table in the next section for additional details about <strong>SysQueryRangeUtil</strong> date methods, and several examples.</span></span></td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a><span data-ttu-id="4675f-191">Consultas de fecha avanzadas que usan los métodos SysQueryRangeUtil</span><span class="sxs-lookup"><span data-stu-id="4675f-191">Advanced date queries that use SysQueryRangeUtil methods</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4675f-192">Método</span><span class="sxs-lookup"><span data-stu-id="4675f-192">Method</span></span></th>
<th><span data-ttu-id="4675f-193">Descripción</span><span class="sxs-lookup"><span data-stu-id="4675f-193">Description</span></span></th>
<th><span data-ttu-id="4675f-194">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4675f-194">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4675f-195">Día (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="4675f-195">Day (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="4675f-196">Busca una fecha en relación con la fecha de la sesión.</span><span class="sxs-lookup"><span data-stu-id="4675f-196">Find a date relative to the session date.</span></span> <span data-ttu-id="4675f-197">Los valores positivos indican fechas futuras y los valores negativos indican fechas anteriores.</span><span class="sxs-lookup"><span data-stu-id="4675f-197">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="4675f-198"><strong>Mañana</strong>: introduzca <strong>(Día (1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-198"><strong>Tomorrow</strong> – Enter <strong>(Day(1))</strong>.</span></span></li>
<li><span data-ttu-id="4675f-199"><strong>Hoy</strong>: introduzca <strong>(Día(0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-199"><strong>Today</strong> – Enter <strong>(Day(0))</strong>.</span></span></li>
<li><span data-ttu-id="4675f-200"><strong>Ayer</strong>: introduzca <strong>(Día(-1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-200"><strong>Yesterday</strong> – Enter <strong>(Day(-1))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="4675f-201">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span><span class="sxs-lookup"><span data-stu-id="4675f-201">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span></span></td>
<td><span data-ttu-id="4675f-202">Busca un intervalo de fechas en relación con la fecha de la sesión.</span><span class="sxs-lookup"><span data-stu-id="4675f-202">Find a range of dates relative to the session date.</span></span> <span data-ttu-id="4675f-203">Los valores positivos indican fechas futuras y los valores negativos indican fechas anteriores.</span><span class="sxs-lookup"><span data-stu-id="4675f-203">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="4675f-204"><strong>Últimos 30 días</strong>: introduzca <strong>(DayRange(-30,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-204"><strong>Last 30 days</strong> – Enter <strong>(DayRange(-30,0))</strong>.</span></span></li>
<li><span data-ttu-id="4675f-205"><strong>30 días anteriores y futuros</strong>: especifique <strong>(DayRange(-30,30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-205"><strong>Previous 30 days and next 30 days</strong> – Enter <strong>(DayRange(-30,30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="4675f-206">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="4675f-206">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="4675f-207">Busca todas las fechas después de la fecha relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="4675f-207">Find all dates after the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="4675f-208"><strong>Más de 30 días a partir de ahora</strong>: especifique <strong>(GreaterThanDate(30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-208"><strong>More than 30 days from now</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="4675f-209">GreaterThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="4675f-209">GreaterThanUtcNow ()</span></span></td>
<td><span data-ttu-id="4675f-210">Busca todas las entradas de hora o fecha posteriores a la hora actual.</span><span class="sxs-lookup"><span data-stu-id="4675f-210">Find all date/time entries after the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="4675f-211"><strong>Todas las horas o fechas futuras</strong>: especifique <strong>(GreaterThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-211"><strong>All future date/times</strong> – Enter <strong>(GreaterThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="4675f-212">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="4675f-212">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="4675f-213">Busca todas las fechas anteriores a la fecha relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="4675f-213">Find all dates before the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="4675f-214"><strong>Menos de siete días desde ahora</strong>: especifique <strong>(LessThanDate(7))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-214"><strong>Less than seven days from now</strong> – Enter <strong>(LessThanDate(7))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="4675f-215">LessThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="4675f-215">LessThanUtcNow ()</span></span></td>
<td><span data-ttu-id="4675f-216">Busca todas las entradas de hora o fecha anteriores a la hora actual.</span><span class="sxs-lookup"><span data-stu-id="4675f-216">Find all date/time entries before the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="4675f-217"><strong>Todas las horas o fechas anteriores</strong>: especifique <strong>(LessThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-217"><strong>All past date/times</strong> – Enter <strong>(LessThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="4675f-218">MonthRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="4675f-218">MonthRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="4675f-219">Busca un intervalo de fechas, en función de meses en relación con el mes actual.</span><span class="sxs-lookup"><span data-stu-id="4675f-219">Find a range of dates, based on months relative to the current month.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="4675f-220"><strong>Dos meses anteriores</strong>: especifique <strong>(MonthRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-220"><strong>Previous two months</strong> – Enter <strong>(MonthRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="4675f-221"><strong>Los tres meses siguientes</strong>: especifique <strong>(MonthRange(0,3))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-221"><strong>Next three months</strong> – Enter <strong>(MonthRange(0,3))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="4675f-222">YearRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="4675f-222">YearRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="4675f-223">Busca un intervalo de fechas, en función de años en relación con el año actual.</span><span class="sxs-lookup"><span data-stu-id="4675f-223">Find a range of dates, based on years relative to the current year.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="4675f-224"><strong>Año próximo</strong>: especifique <strong>(YearRange(0, 1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-224"><strong>Next year</strong> – Enter <strong>(YearRange(0, 1))</strong>.</span></span></li>
<li><span data-ttu-id="4675f-225"><strong>Año anterior</strong>: especifique <strong>(YearRange(-1,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4675f-225"><strong>Previous year</strong> – Enter <strong>(YearRange(-1,0))</strong>.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]