---
title: Sintaxis de consulta y filtro avanzados
description: Este artículo describe el filtrado y las opciones de consulta que están disponibles cuando usa el diálogo Ordenación o filtro avanzados o el operador coincide en el panel de filtro o los filtros de los encabezados de las columnas de la cuadrícula.
author: jasongre
manager: AnnBe
ms.date: 01/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
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
ms.openlocfilehash: c5a96921436311440ba60c3fa31135457cf9f291
ms.sourcegitcommit: 8585de8acf579bcc033671ef270fa9d92230121b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/02/2020
ms.locfileid: "2931297"
---
# <a name="advanced-filtering-and-query-syntax"></a><span data-ttu-id="552a2-103">Sintaxis de consulta y filtro avanzados</span><span class="sxs-lookup"><span data-stu-id="552a2-103">Advanced filtering and query syntax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="552a2-104">Este artículo describe el filtrado y las opciones de consulta que están disponibles cuando usa el diálogo Ordenación o filtro avanzados o el operador **coincide** en el panel de filtro o los filtros de los encabezados de las columnas de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="552a2-104">This article describes the filtering and query options that are available when you use the Advanced filter/sort dialog or the **matches** operator in the Filter pane or grid column header filters.</span></span>

## <a name="advanced-query-syntax"></a><span data-ttu-id="552a2-105">Sintaxis de consulta avanzada</span><span class="sxs-lookup"><span data-stu-id="552a2-105">Advanced query syntax</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="552a2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="552a2-106">Syntax</span></span></th>
<th><span data-ttu-id="552a2-107">Descripción de carácter</span><span class="sxs-lookup"><span data-stu-id="552a2-107">Character description</span></span></th>
<th><span data-ttu-id="552a2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="552a2-108">Description</span></span></th>
<th><span data-ttu-id="552a2-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="552a2-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="552a2-110"><em>valor</em></span><span class="sxs-lookup"><span data-stu-id="552a2-110"><em>value</em></span></span></td>
<td><span data-ttu-id="552a2-111">Igual que el valor que se especifica</span><span class="sxs-lookup"><span data-stu-id="552a2-111">Equal to the value that is entered</span></span></td>
<td><span data-ttu-id="552a2-112">Escriba el valor que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="552a2-112">Type the value to find.</span></span></td>
<td><span data-ttu-id="552a2-113"><strong>Serrano</strong> encuentra &quot;Serrano&quot;.</span><span class="sxs-lookup"><span data-stu-id="552a2-113"><strong>Smith</strong> finds &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="552a2-114">!<em>valor</em> (signo de exclamación)</span><span class="sxs-lookup"><span data-stu-id="552a2-114">!<em>value</em> (exclamation point)</span></span></td>
<td><span data-ttu-id="552a2-115">No es igual que el valor que se especifica</span><span class="sxs-lookup"><span data-stu-id="552a2-115">Not equal to the value that is entered</span></span></td>
<td><span data-ttu-id="552a2-116">Escriba un signo de exclamación y, después, el valor que desee excluir.</span><span class="sxs-lookup"><span data-stu-id="552a2-116">Type an exclamation point and then the value to exclude.</span></span></td>
<td><span data-ttu-id="552a2-117"><strong>!Serrano</strong> encuentra todos los valores excepto &quot;Serrano&quot;.</span><span class="sxs-lookup"><span data-stu-id="552a2-117"><strong>!Smith</strong> finds all values except &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="552a2-118"><em>valor-inicial</em>..<em>valor-final</em> (dos puntos seguidos)</span><span class="sxs-lookup"><span data-stu-id="552a2-118"><em>from-value</em>..<em>to-value</em> (double period)</span></span></td>
<td><span data-ttu-id="552a2-119">Entre los dos valores que están separados por dos puntos seguidos</span><span class="sxs-lookup"><span data-stu-id="552a2-119">Between the two values that are separated by double periods</span></span></td>
<td><span data-ttu-id="552a2-120">Escriba el valor inicial, después los dos puntos y, por último, el valor final.</span><span class="sxs-lookup"><span data-stu-id="552a2-120">Type the from-value, then two periods, and then the to-value.</span></span></td>
<td><span data-ttu-id="552a2-121"><strong>1..10</strong> encuentra todos los valores desde 1 hasta 10.</span><span class="sxs-lookup"><span data-stu-id="552a2-121"><strong>1..10</strong> finds all values from 1 through 10.</span></span> <span data-ttu-id="552a2-122">No obstante, en un campo de cadena, <strong>A..C</strong> encuentra todos los valores que empiezan por &quot;A&quot; y &quot;B&quot; y los valores que son exactamente iguales a &quot;C&quot;.</span><span class="sxs-lookup"><span data-stu-id="552a2-122">However, in a string field, <strong>A..C</strong> finds all values that start with &quot;A&quot; and &quot;B&quot;, and values that are exactly equal to &quot;C&quot;.</span></span> <span data-ttu-id="552a2-123">Por ejemplo, esta consulta no encontrará &quot;Ca&quot;.</span><span class="sxs-lookup"><span data-stu-id="552a2-123">For example, this query won't find &quot;Ca&quot;.</span></span> <span data-ttu-id="552a2-124">Para encontrar todos los valores de la &quot;A<em>&quot; a la &quot;C</em>&quot;, escriba <strong>A..D</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-124">To find all values from &quot;A<em>&quot; through &quot;C</em>&quot;, type <strong>A..D</strong>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="552a2-125">..<em>valor</em> (dos puntos seguidos)</span><span class="sxs-lookup"><span data-stu-id="552a2-125">..<em>value</em> (double period)</span></span></td>
<td><span data-ttu-id="552a2-126">Menor o igual que el valor especificado</span><span class="sxs-lookup"><span data-stu-id="552a2-126">Less than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="552a2-127">Escriba los dos puntos y, a continuación, el valor.</span><span class="sxs-lookup"><span data-stu-id="552a2-127">Type two periods and then the value.</span></span></td>
<td><span data-ttu-id="552a2-128"><strong>..1000</strong> encuentra cualquier número menor o igual que 1000, por ejemplo &quot;100&quot;, &quot;999,95&quot; y &quot;1000&quot;.</span><span class="sxs-lookup"><span data-stu-id="552a2-128"><strong>..1000</strong> finds any number that is less than or equal to 1000, such as &quot;100&quot;, &quot;999.95&quot;, and &quot;1,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="552a2-129"><em>valor</em>..</span><span class="sxs-lookup"><span data-stu-id="552a2-129"><em>value</em>..</span></span> <span data-ttu-id="552a2-130">(doble punto)</span><span class="sxs-lookup"><span data-stu-id="552a2-130">(double period)</span></span></td>
<td><span data-ttu-id="552a2-131">Mayor o igual que el valor especificado</span><span class="sxs-lookup"><span data-stu-id="552a2-131">Greater than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="552a2-132">Escriba el valor y, a continuación, dos puntos .</span><span class="sxs-lookup"><span data-stu-id="552a2-132">Type the value and then two periods.</span></span></td>
<td><span data-ttu-id="552a2-133"><strong>1000..</strong></span><span class="sxs-lookup"><span data-stu-id="552a2-133"><strong>1000..</strong></span></span> <span data-ttu-id="552a2-134">encuentra cualquier número mayor o igual que 1000, por ejemplo &quot;1000&quot;, &quot;1000,01&quot; y &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="552a2-134">finds any number that is greater than or equal to 1000, such as &quot;1,000&quot;, &quot;1,000.01&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="552a2-135">&gt;<em>valor</em> (signo mayor que)</span><span class="sxs-lookup"><span data-stu-id="552a2-135">&gt;<em>value</em> (greater than sign)</span></span></td>
<td><span data-ttu-id="552a2-136">Mayor que el valor especificado</span><span class="sxs-lookup"><span data-stu-id="552a2-136">Greater than the value that is entered</span></span></td>
<td><span data-ttu-id="552a2-137">Escriba un signo mayor que (<strong>&gt;</strong>) y, a continuación, el valor.</span><span class="sxs-lookup"><span data-stu-id="552a2-137">Type a greater than sign (<strong>&gt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="552a2-138"><strong>&gt;1000</strong> encuentra cualquier número mayor que 1000, por ejemplo &quot;1000,01&quot;, &quot;20 000&quot; y &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="552a2-138"><strong>&gt;1000</strong> finds any number that is greater than 1000, such as &quot;1000.01&quot;, &quot;20,000&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="552a2-139">&lt;<em>valor</em> (signo menor que)</span><span class="sxs-lookup"><span data-stu-id="552a2-139">&lt;<em>value</em> (less than sign)</span></span></td>
<td><span data-ttu-id="552a2-140">Menor que el valor especificado</span><span class="sxs-lookup"><span data-stu-id="552a2-140">Less than the value that is entered</span></span></td>
<td><span data-ttu-id="552a2-141">Escriba un signo menor que (<strong>&lt;</strong>) y, a continuación, el valor.</span><span class="sxs-lookup"><span data-stu-id="552a2-141">Type a less than sign (<strong>&lt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="552a2-142"><strong>&lt;1000</strong> encuentra cualquier número menor que 1000, por ejemplo &quot;999,99&quot;, &quot;1&quot; y &quot;-200&quot;.</span><span class="sxs-lookup"><span data-stu-id="552a2-142"><strong>&lt;1000</strong> finds any number that is less than 1000, such as &quot;999.99&quot;, &quot;1&quot;, and &quot;-200&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="552a2-143"><em>valor</em>\* (asterisco)</span><span class="sxs-lookup"><span data-stu-id="552a2-143"><em>value</em>\* (asterisk)</span></span></td>
<td><span data-ttu-id="552a2-144">Que empieza por el valor que se especifica</span><span class="sxs-lookup"><span data-stu-id="552a2-144">Starting from the value that is entered</span></span></td>
<td><span data-ttu-id="552a2-145">Escriba el valor inicial y, a continuación, un asterisco (<strong>\*</strong>).</span><span class="sxs-lookup"><span data-stu-id="552a2-145">Type the starting value and then an asterisk (<strong>\*</strong>).</span></span></td>
<td><span data-ttu-id="552a2-146"><strong>S\*</strong> encuentra cualquier cadena que empiece por &quot;S&quot;, como &quot;Suecia&quot;, &quot;Sydney&quot; y &quot;San Francisco&quot;.</span><span class="sxs-lookup"><span data-stu-id="552a2-146"><strong>S\*</strong> finds any string that starts with &quot;S&quot;, such as &quot;Stockholm&quot;, &quot;Sydney&quot;, and &quot;San Francisco&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="552a2-147">\*<em>valor</em> (asterisco)</span><span class="sxs-lookup"><span data-stu-id="552a2-147">\*<em>value</em> (asterisk)</span></span></td>
<td><span data-ttu-id="552a2-148">Termina por el valor que se especifica</span><span class="sxs-lookup"><span data-stu-id="552a2-148">Ending with the value that is entered</span></span></td>
<td><span data-ttu-id="552a2-149">Escriba un asterisco y, a continuación, el valor final.</span><span class="sxs-lookup"><span data-stu-id="552a2-149">Type an asterisk and then the ending value.</span></span></td>
<td><span data-ttu-id="552a2-150"><strong>\*este</strong> encuentra cualquier cadena que termine por &quot;este&quot;, como &quot;Nordeste&quot; y &quot;Sudeste&quot;.</span><span class="sxs-lookup"><span data-stu-id="552a2-150"><strong>\*east</strong> finds any string that ends with &quot;east&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="552a2-151">*<em>valor</em>* (asterisco)</span><span class="sxs-lookup"><span data-stu-id="552a2-151">*<em>value</em>* (asterisk)</span></span></td>
<td><span data-ttu-id="552a2-152">Contiene el valor especificado</span><span class="sxs-lookup"><span data-stu-id="552a2-152">Containing the value that is entered</span></span></td>
<td><span data-ttu-id="552a2-153">Escriba un asterisco, a continuación un valor y, por último, otro asterisco.</span><span class="sxs-lookup"><span data-stu-id="552a2-153">Type an asterisk, then a value, and then another asterisk.</span></span></td>
<td><span data-ttu-id="552a2-154"><strong>*de*</strong> encuentra las cadenas que contengan &quot;de&quot; como &quot;Nordeste&quot; y &quot;Sudeste&quot;.</span><span class="sxs-lookup"><span data-stu-id="552a2-154"><strong>*th*</strong> finds any string that contains &quot;th&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="552a2-155">?</span><span class="sxs-lookup"><span data-stu-id="552a2-155">?</span></span> <span data-ttu-id="552a2-156">(signo de interrogación)</span><span class="sxs-lookup"><span data-stu-id="552a2-156">(question mark)</span></span></td>
<td><span data-ttu-id="552a2-157">Que tenga uno o más caracteres desconocidos</span><span class="sxs-lookup"><span data-stu-id="552a2-157">Having one or more unknown characters</span></span></td>
<td><span data-ttu-id="552a2-158">Escriba un signo de interrogación en la posición del carácter desconocido en el valor.</span><span class="sxs-lookup"><span data-stu-id="552a2-158">Type a question mark at the position of the unknown character in the value.</span></span></td>
<td><span data-ttu-id="552a2-159"><strong>Se?rr</strong> encuentra &quot;Serr&quot; y &quot;Ser&quot;.</span><span class="sxs-lookup"><span data-stu-id="552a2-159"><strong>Sm?th</strong> finds &quot;Smith&quot; and &quot;Smyth&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="552a2-160"><em>valor</em>,<em>valor</em> (coma)</span><span class="sxs-lookup"><span data-stu-id="552a2-160"><em>value</em>,<em>value</em> (comma)</span></span></td>
<td><span data-ttu-id="552a2-161">Que coincida con los valores separados por comas</span><span class="sxs-lookup"><span data-stu-id="552a2-161">Matching the values that are separated by commas</span></span></td>
<td><span data-ttu-id="552a2-162">Escriba todos los criterios y sepárelos con comas.</span><span class="sxs-lookup"><span data-stu-id="552a2-162">Type all your criteria, and separate them by using commas.</span></span></td>
<td><span data-ttu-id="552a2-163"><strong>A, D, F, G</strong> encuentra exactamente &quot;A&quot;, &quot;D&quot;, &quot;F&quot; y &quot;G&quot;.</span><span class="sxs-lookup"><span data-stu-id="552a2-163"><strong>A, D, F, G</strong> finds exactly &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, and &quot;G&quot;.</span></span> <span data-ttu-id="552a2-164"><strong>10, 20, 30, 100</strong> encuentra exactamente &quot;10, 20, 30, 100&quot;.</span><span class="sxs-lookup"><span data-stu-id="552a2-164"><strong>10, 20, 30, 100</strong> finds exactly &quot;10, 20, 30, 100&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="552a2-165">"" (dos comillas dobles)</span><span class="sxs-lookup"><span data-stu-id="552a2-165">"" (two double quotes)</span></span></td>
<td><span data-ttu-id="552a2-166">Hacer coincidir un valor en blanco</span><span class="sxs-lookup"><span data-stu-id="552a2-166">Matching a blank value</span></span></td>
<td><span data-ttu-id="552a2-167">Escriba dos comillas dobles consecutivas para filtrar valores en blanco en ese campo.</span><span class="sxs-lookup"><span data-stu-id="552a2-167">Type two consecutive double quotes to filter for blank values in that field.</span></span></td>
<td><span data-ttu-id="552a2-168">Dos comillas dobles consecutivas (<strong>""</strong>) busca filas sin valor para la columna actual.</span><span class="sxs-lookup"><span data-stu-id="552a2-168">Two consecutive double quotes (<strong>""</strong>) finds rows with no value for the current column.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="552a2-169">(<span class="code">Instrucción SQL</span>) (instrucción SQL entre paréntesis)</span><span class="sxs-lookup"><span data-stu-id="552a2-169">(<span class="code">SQL statement</span>) (SQL statement between parentheses)</span></span></td>
<td><span data-ttu-id="552a2-170">Que coincide con una consulta definida</span><span class="sxs-lookup"><span data-stu-id="552a2-170">Matching a defined query</span></span></td>
<td><span data-ttu-id="552a2-171">Escriba una consulta como una instrucción SQL entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="552a2-171">Type a query as an SQL statement between parentheses.</span></span></td>
<td><span data-ttu-id="552a2-172"><strong><span class="code">(origen_de_datos.Nombre_de_campo != &quot;A&quot;)</span></strong></span><span class="sxs-lookup"><span data-stu-id="552a2-172"><strong><span class="code">(data source.Fieldname != &quot;A&quot;)</span></strong></span></span></td>
</tr>
<tr>
<td><span data-ttu-id="552a2-173">N</span><span class="sxs-lookup"><span data-stu-id="552a2-173">T</span></span></td>
<td><span data-ttu-id="552a2-174">Fecha de hoy</span><span class="sxs-lookup"><span data-stu-id="552a2-174">Today's date</span></span></td>
<td><span data-ttu-id="552a2-175">Escriba <strong>B</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-175">Type <strong>T</strong>.</span></span></td>
<td><span data-ttu-id="552a2-176"><strong>B</strong> coincide con la fecha de hoy.</span><span class="sxs-lookup"><span data-stu-id="552a2-176"><strong>T</strong> matches today's date.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="552a2-177">(methodName(parámetros)) (<strong>método SysQueryRangeUtil</strong> entre paréntesis)</span><span class="sxs-lookup"><span data-stu-id="552a2-177">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> method between parentheses)</span></span></td>
<td><span data-ttu-id="552a2-178">Coincide con el valor o el intervalo de valores especificados por los parámetros del método <strong>SysQueryRangeUtil</strong></span><span class="sxs-lookup"><span data-stu-id="552a2-178">Matching the value or range of values that are specified by the parameters of the <strong>SysQueryRangeUtil</strong> method</span></span></td>
<td><span data-ttu-id="552a2-179">Escriba un método <strong>SysQueryRangeUtil</strong> con los parámetros que especifican el valor o el intervalo de valores.</span><span class="sxs-lookup"><span data-stu-id="552a2-179">Type a <strong>SysQueryRangeUtil</strong> method that has parameters that specify the value or range of values.</span></span></td>
<td>
<ol>
<li><span data-ttu-id="552a2-180">Haga clic en <strong>Clientes</strong> &gt; <strong>Facturas</strong> &gt; <strong>Facturas de cliente abiertas</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-180">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Open customer invoices</strong>.</span></span></li>
<li><span data-ttu-id="552a2-181">Presione Ctrl+Mayús+F3 para abrir la página <strong>Consulta</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-181">Press Ctrl+Shift+F3 to open the <strong>Inquiry</strong> page.</span></span></li>
<li><span data-ttu-id="552a2-182">En la ficha <strong>Intervalo</strong>, haga clic en <strong>Agregar</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-182">On the <strong>Range</strong> tab, click <strong>Add</strong>.</span></span></li>
<li><span data-ttu-id="552a2-183">En el campo <strong>Tabla</strong>, seleccione <strong>Transacciones de cliente abiertas</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-183">In the <strong>Table</strong> field, select <strong>Open customer transactions</strong>.</span></span></li>
<li><span data-ttu-id="552a2-184">En el campo <strong>Campo</strong>, seleccione <strong>Fecha de vencimiento</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-184">In the <strong>Field</strong> field, select <strong>Due date</strong>.</span></span></li>
<li><span data-ttu-id="552a2-185">En el campo <strong>Criterios</strong>, escriba <strong>(yearRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-185">In the <strong>Criteria</strong> field, enter <strong>(yearRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="552a2-186">Haga clic en <strong>Aceptar</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-186">Click <strong>OK</strong>.</span></span> <span data-ttu-id="552a2-187">La página de lista se actualiza para mostrar las facturas que coincidan con el criterio especificado.</span><span class="sxs-lookup"><span data-stu-id="552a2-187">The list page is updated and lists the invoices that match the criterion that you entered.</span></span> <span data-ttu-id="552a2-188">En este ejemplo, se muestran las facturas vencidas en los dos años anteriores.</span><span class="sxs-lookup"><span data-stu-id="552a2-188">For this example, invoices that were due in the previous two years are listed.</span></span></li>
</ol>
<span data-ttu-id="552a2-189">Consulte la tabla en la sección siguiente para ver los detalles adicionales sobre los métodos de fecha <strong>SysQueryRangeUtil</strong> y varios ejemplos.</span><span class="sxs-lookup"><span data-stu-id="552a2-189">See the table in the next section for additional details about <strong>SysQueryRangeUtil</strong> date methods, and several examples.</span></span></td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a><span data-ttu-id="552a2-190">Consultas de fecha avanzadas que usan los métodos SysQueryRangeUtil</span><span class="sxs-lookup"><span data-stu-id="552a2-190">Advanced date queries that use SysQueryRangeUtil methods</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="552a2-191">Método</span><span class="sxs-lookup"><span data-stu-id="552a2-191">Method</span></span></th>
<th><span data-ttu-id="552a2-192">Descripción</span><span class="sxs-lookup"><span data-stu-id="552a2-192">Description</span></span></th>
<th><span data-ttu-id="552a2-193">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="552a2-193">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="552a2-194">Día (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="552a2-194">Day (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="552a2-195">Busca una fecha en relación con la fecha de la sesión.</span><span class="sxs-lookup"><span data-stu-id="552a2-195">Find a date relative to the session date.</span></span> <span data-ttu-id="552a2-196">Los valores positivos indican fechas futuras y los valores negativos indican fechas anteriores.</span><span class="sxs-lookup"><span data-stu-id="552a2-196">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="552a2-197"><strong>Mañana</strong>: introduzca <strong>(Día (1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-197"><strong>Tomorrow</strong> – Enter <strong>(Day(1))</strong>.</span></span></li>
<li><span data-ttu-id="552a2-198"><strong>Hoy</strong>: introduzca <strong>(Día(0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-198"><strong>Today</strong> – Enter <strong>(Day(0))</strong>.</span></span></li>
<li><span data-ttu-id="552a2-199"><strong>Ayer</strong>: introduzca <strong>(Día(-1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-199"><strong>Yesterday</strong> – Enter <strong>(Day(-1))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="552a2-200">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span><span class="sxs-lookup"><span data-stu-id="552a2-200">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span></span></td>
<td><span data-ttu-id="552a2-201">Busca un intervalo de fechas en relación con la fecha de la sesión.</span><span class="sxs-lookup"><span data-stu-id="552a2-201">Find a range of dates relative to the session date.</span></span> <span data-ttu-id="552a2-202">Los valores positivos indican fechas futuras y los valores negativos indican fechas anteriores.</span><span class="sxs-lookup"><span data-stu-id="552a2-202">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="552a2-203"><strong>Últimos 30 días</strong>: introduzca <strong>(DayRange(-30,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-203"><strong>Last 30 days</strong> – Enter <strong>(DayRange(-30,0))</strong>.</span></span></li>
<li><span data-ttu-id="552a2-204"><strong>30 días anteriores y futuros</strong>: especifique <strong>(DayRange(-30,30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-204"><strong>Previous 30 days and next 30 days</strong> – Enter <strong>(DayRange(-30,30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="552a2-205">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="552a2-205">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="552a2-206">Busca todas las fechas después de la fecha relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="552a2-206">Find all dates after the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="552a2-207"><strong>Más de 30 días a partir de ahora</strong>: especifique <strong>(GreaterThanDate(30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-207"><strong>More than 30 days from now</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="552a2-208">GreaterThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="552a2-208">GreaterThanUtcNow ()</span></span></td>
<td><span data-ttu-id="552a2-209">Busca todas las entradas de hora o fecha posteriores a la hora actual.</span><span class="sxs-lookup"><span data-stu-id="552a2-209">Find all date/time entries after the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="552a2-210"><strong>Todas las horas o fechas futuras</strong>: especifique <strong>(GreaterThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-210"><strong>All future date/times</strong> – Enter <strong>(GreaterThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="552a2-211">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="552a2-211">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="552a2-212">Busca todas las fechas anteriores a la fecha relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="552a2-212">Find all dates before the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="552a2-213"><strong>Menos de siete días desde ahora</strong>: especifique <strong>(LessThanDate(7))</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-213"><strong>Less than seven days from now</strong> – Enter <strong>(LessThanDate(7))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="552a2-214">LessThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="552a2-214">LessThanUtcNow ()</span></span></td>
<td><span data-ttu-id="552a2-215">Busca todas las entradas de hora o fecha anteriores a la hora actual.</span><span class="sxs-lookup"><span data-stu-id="552a2-215">Find all date/time entries before the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="552a2-216"><strong>Todas las horas o fechas anteriores</strong>: especifique <strong>(LessThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-216"><strong>All past date/times</strong> – Enter <strong>(LessThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="552a2-217">MonthRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="552a2-217">MonthRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="552a2-218">Busca un intervalo de fechas, en función de meses en relación con el mes actual.</span><span class="sxs-lookup"><span data-stu-id="552a2-218">Find a range of dates, based on months relative to the current month.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="552a2-219"><strong>Dos meses anteriores</strong>: especifique <strong>(MonthRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-219"><strong>Previous two months</strong> – Enter <strong>(MonthRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="552a2-220"><strong>Los tres meses siguientes</strong>: especifique <strong>(MonthRange(0,3))</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-220"><strong>Next three months</strong> – Enter <strong>(MonthRange(0,3))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="552a2-221">YearRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="552a2-221">YearRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="552a2-222">Busca un intervalo de fechas, en función de años en relación con el año actual.</span><span class="sxs-lookup"><span data-stu-id="552a2-222">Find a range of dates, based on years relative to the current year.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="552a2-223"><strong>Año próximo</strong>: especifique <strong>(YearRange(0, 1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-223"><strong>Next year</strong> – Enter <strong>(YearRange(0, 1))</strong>.</span></span></li>
<li><span data-ttu-id="552a2-224"><strong>Año anterior</strong>: especifique <strong>(YearRange(-1,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="552a2-224"><strong>Previous year</strong> – Enter <strong>(YearRange(-1,0))</strong>.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
