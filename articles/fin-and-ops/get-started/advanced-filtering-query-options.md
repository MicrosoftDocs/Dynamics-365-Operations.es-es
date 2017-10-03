---
title: Sintaxis de consulta y filtro avanzados
description: "Este artículo describe el filtrado y las opciones de consulta que están disponibles cuando usa el operador “coincide” en el cuadro de diálogo Ordenación o filtro avanzados."
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
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 616366009ce7bf7135704e980becc331617cf5af
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---

# <a name="advanced-filtering-and-query-syntax"></a>Sintaxis de consulta y filtro avanzados

[!include[banner](../includes/banner.md)]


Este artículo describe el filtrado y las opciones de consulta que están disponibles cuando usa el operador “coincide” en el cuadro de diálogo Ordenación o filtro avanzados.

<a name="advanced-query-syntax"></a>Sintaxis de consulta avanzada
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
<th>Sintaxis</th>
<th>Descripción de carácter</th>
<th>Descripción</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>valor</em></td>
<td>Igual que el valor que se especifica</td>
<td>Escriba el valor que desea buscar.</td>
<td><strong>Serrano</strong> encuentra &quot;Serrano&quot;.</td>
</tr>
<tr class="even">
<td>!<em>valor</em> (signo de exclamación)</td>
<td>No es igual que el valor que se especifica</td>
<td>Escriba un signo de exclamación y, después, el valor que desee excluir.</td>
<td><strong>!Serrano</strong> encuentra todos los valores excepto &quot;Serrano&quot;.</td>
</tr>
<tr class="odd">
<td><em>valor-inicial</em>..<em>valor-final</em> (dos puntos seguidos)</td>
<td>Entre los dos valores que están separados por dos puntos seguidos</td>
<td>Escriba el valor inicial, después los dos puntos y, por último, el valor final.</td>
<td><strong>1..10</strong> encuentra todos los valores desde 1 hasta 10. No obstante, en un campo de cadena, <strong>A..C</strong> encuentra todos los valores que empiezan por &quot;A&quot; y &quot;B&quot; y los valores que son exactamente iguales a &quot;C&quot;. Por ejemplo, esta consulta no encontrará &quot;Ca&quot;. Para encontrar todos los valores de la &quot;A*&quot; a la &quot;C*&quot;, escriba <strong>A..D</strong>.</td>
</tr>
<tr class="even">
<td>..<em>valor</em> (dos puntos seguidos)</td>
<td>Menor o igual que el valor especificado</td>
<td>Escriba los dos puntos y, a continuación, el valor.</td>
<td><strong>..1000</strong> encuentra cualquier número menor o igual que 1000, por ejemplo &quot;100&quot;, &quot;999,95&quot; y &quot;1000&quot;.</td>
</tr>
<tr class="odd">
<td><em>valor</em>.. (doble punto)</td>
<td>Mayor o igual que el valor especificado</td>
<td>Escriba el valor y, a continuación, dos puntos .</td>
<td><strong>1000..</strong> encuentra cualquier número mayor o igual que 1000, por ejemplo &quot;1000&quot;, &quot;1000,01&quot; y &quot;1 000 000&quot;.</td>
</tr>
<tr class="even">
<td>&gt;<em>valor</em> (signo mayor que)</td>
<td>Mayor que el valor especificado</td>
<td>Escriba un signo mayor que (<strong>&gt;</strong>) y, a continuación, el valor.</td>
<td><strong>&gt;1000</strong> encuentra cualquier número mayor que 1000, por ejemplo &quot;1000,01&quot;, &quot;20 000&quot; y &quot;1 000 000&quot;.</td>
</tr>
<tr class="odd">
<td>&lt;<em>valor</em> (signo menor que)</td>
<td>Menor que el valor especificado</td>
<td>Escriba un signo menor que (<strong>&lt;</strong>) y, a continuación, el valor.</td>
<td><strong>&lt;1000</strong> encuentra cualquier número menor que 1000, por ejemplo &quot;999,99&quot;, &quot;1&quot; y &quot;-200&quot;.</td>
</tr>
<tr class="even">
<td><em>valor</em>* (asterisco)</td>
<td>Que empieza por el valor que se especifica</td>
<td>Escriba el valor inicial y, a continuación, un asterisco (<strong>*</strong>).</td>
<td><strong>S*</strong> encuentra cualquier cadena que empiece por &quot;S&quot;, como &quot;Suecia&quot;, &quot;Sydney&quot; y &quot;San Francisco&quot;.</td>
</tr>
<tr class="odd">
<td>*<em>valor</em> (asterisco)</td>
<td>Termina por el valor que se especifica</td>
<td>Escriba un asterisco y, a continuación, el valor final.</td>
<td><strong>*este</strong> encuentra cualquier cadena que termine por &quot;este&quot;, como &quot;Nordeste&quot; y &quot;Sudeste&quot;.</td>
</tr>
<tr class="even">
<td>*<em>valor</em>* (asterisco)</td>
<td>Contiene el valor especificado</td>
<td>Escriba un asterisco, a continuación un valor y, por último, otro asterisco.</td>
<td><strong>*de*</strong> encuentra las cadenas que contengan &quot;de&quot; como &quot;Nordeste&quot; y &quot;Sudeste&quot;.</td>
</tr>
<tr class="odd">
<td>? (signo de interrogación)</td>
<td>Que tenga uno o más caracteres desconocidos</td>
<td>Escriba un signo de interrogación en la posición del carácter desconocido en el valor.</td>
<td><strong>Se?rr</strong> encuentra &quot;Serr&quot; y &quot;Ser&quot;.</td>
</tr>
<tr class="even">
<td><em>valor</em>,<em>valor</em> (coma)</td>
<td>Que coincida con los valores separados por comas</td>
<td>Escriba todos los criterios y sepárelos con comas.</td>
<td><strong>A, D, F, G</strong> encuentra exactamente &quot;A&quot;, &quot;D&quot;, &quot;F&quot; y &quot;G&quot;. <strong>10, 20, 30, 100</strong> encuentra exactamente &quot;10, 20, 30, 100&quot;.</td>
</tr>
<tr class="odd">
<td>(<span class="code">Instrucción SQL</span>) (instrucción SQL entre paréntesis)</td>
<td>Que coincide con una consulta definida</td>
<td>Escriba una consulta como una instrucción SQL entre paréntesis.</td>
<td><strong><span class="code">(origen_de_datos.Nombre_de_campo != &quot;A&quot;)</span></strong></td>
</tr>
<tr class="even">
<td>N</td>
<td>Fecha de hoy</td>
<td>Escriba <strong>B</strong>.</td>
<td><strong>B</strong> coincide con la fecha de hoy.</td>
</tr>
<tr class="odd">
<td>(methodName(parámetros)) (<strong>método SysQueryRangeUtil</strong> entre paréntesis)</td>
<td>Coincide con el valor o el intervalo de valores especificados por los parámetros del método <strong>SysQueryRangeUtil</strong></td>
<td>Escriba un método <strong>SysQueryRangeUtil</strong> con los parámetros que especifican el valor o el intervalo de valores.</td>
<td><ol>
<li>Haga clic en <strong>Clientes</strong> &gt; <strong>Facturas</strong> &gt; <strong>Facturas de cliente abiertas</strong>.</li>
<li>Presione Ctrl+Mayús+F3 para abrir la página <strong>Consulta</strong>.</li>
<li>En la ficha <strong>Intervalo</strong>, haga clic en <strong>Agregar</strong>.</li>
<li>En el campo <strong>Tabla</strong>, seleccione <strong>Transacciones de cliente abiertas</strong>.</li>
<li>En el campo <strong>Campo</strong>, seleccione <strong>Fecha de vencimiento</strong>.</li>
<li>En el campo <strong>Criterios</strong>, escriba <strong>(yearRange(-2,0))</strong>.</li>
<li>Haga clic en <strong>Aceptar</strong>. La página de lista se actualiza para mostrar las facturas que coincidan con el criterio especificado. En este ejemplo, se muestran las facturas vencidas en los dos años anteriores.</li>
</ol>
Consulte la tabla en la sección siguiente para ver los detalles adicionales sobre los métodos de fecha <strong>SysQueryRangeUtil</strong> y varios ejemplos.</td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a>Consultas de fecha avanzadas que usan los métodos SysQueryRangeUtil
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Método</th>
<th>Descripción</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Día (_relativeDays=0)</td>
<td>Busca una fecha en relación con la fecha de la sesión. Los valores positivos indican fechas futuras y los valores negativos indican fechas anteriores.</td>
<td><ul>
<li><strong>Mañana</strong>: introduzca <strong>(Día (1))</strong>.</li>
<li><strong>Hoy</strong>: introduzca <strong>(Día(0))</strong>.</li>
<li><strong>Ayer</strong>: introduzca <strong>(Día(-1))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</td>
<td>Busca un intervalo de fechas en relación con la fecha de la sesión. Los valores positivos indican fechas futuras y los valores negativos indican fechas anteriores.</td>
<td><ul>
<li><strong>Últimos 30 días</strong>: introduzca <strong>(DayRange(-30,0))</strong>.</li>
<li><strong>30 días anteriores y futuros</strong>: especifique <strong>(DayRange(-30,30))</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</td>
<td>Busca todas las fechas después de la fecha relativa especificada.</td>
<td><ul>
<li><strong>Más de 30 días a partir de ahora</strong>: especifique <strong>(GreaterThanDate(30))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>GreaterThanUtcNow ()</td>
<td>Busca todas las entradas de hora o fecha posteriores a la hora actual.</td>
<td><ul>
<li><strong>Todas las horas o fechas futuras</strong>: especifique <strong>(GreaterThanUtcNow())</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</td>
<td>Busca todas las fechas anteriores a la fecha relativa especificada.</td>
<td><ul>
<li><strong>Menos de siete días desde ahora</strong>: especifique <strong>(LessThanDate(7))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>LessThanUtcNow ()</td>
<td>Busca todas las entradas de hora o fecha anteriores a la hora actual.</td>
<td><ul>
<li><strong>Todas las horas o fechas anteriores</strong>: especifique <strong>(LessThanUtcNow())</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>MonthRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Busca un intervalo de fechas, en función de meses en relación con el mes actual.</td>
<td><ul>
<li><strong>Dos meses anteriores</strong>: especifique <strong>(MonthRange(-2,0))</strong>.</li>
<li><strong>Los tres meses siguientes</strong>: especifique <strong>(MonthRange(0,3))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>YearRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Busca un intervalo de fechas, en función de años en relación con el año actual.</td>
<td><ul>
<li><strong>Año próximo</strong>: especifique <strong>(YearRange(0, 1))</strong>.</li>
<li><strong>Año anterior</strong>: especifique <strong>(YearRange(-1,0))</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>






