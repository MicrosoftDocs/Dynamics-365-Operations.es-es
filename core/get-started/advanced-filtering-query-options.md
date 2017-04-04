---
title: Sintaxis de consulta y filtro avanzado
description: "Este artículo describe el filtrado y las opciones de consulta que están disponibles cuando usa el operador “coincide” en el cuadro de diálogo Ordenación o filtro avanzados."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysQueryForm
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 5ee7a04572e350a7c08d0418bade6d332aa920c6
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-filtering-and-query-syntax"></a>Sintaxis de consulta y filtro avanzado

Este artículo describe el filtrado y las opciones de consulta que están disponibles cuando usa el operador “coincide” en el cuadro de diálogo Ordenación o filtro avanzados.

<a name="advanced-query-syntax"></a>Sintaxis de la consulta avanzado
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
<td><strong>Serrano</strong> Serrano&quot;búsquedas &quot;.</td>
</tr>
<tr class="even">
<td>!<em>valor</em> (signo de exclamación)</td>
<td>No es igual que el valor que se especifica</td>
<td>Escriba un signo de exclamación y, después, el valor que desee excluir.</td>
<td><strong>! Serrano</strong> encuentra todos los valores excepto &quot;Serrano&quot;.</td>
</tr>
<tr class="odd">
<td><em>valor-inicial</em>..<em>valor-final</em> (dos puntos seguidos)</td>
<td>Entre los dos valores que están separados por dos puntos seguidos</td>
<td>Escriba el valor inicial, después los dos puntos y, por último, el valor final.</td>
<td><strong>1..10</strong> encuentra todos los valores desde 1 a 10. Sin embargo, en un campo de la cadena, <strong>A.C</strong> encuentra todos los valores que comienzan por A&quot; y &quot;B&quot;, y los valores que se exactamente igual &quot;a la C&quot;. Por ejemplo, esta consulta no &quot;encontrarán el CA.&quot; Para buscar todos los valores &quot;de A*&quot; con &quot;C*&quot;, tipo <strong>A.D</strong>.</td>
</tr>
<tr class="even">
<td>..<em>valor</em> (dos puntos seguidos)</td>
<td>Menor o igual que el valor especificado</td>
<td>Escriba los dos puntos y, a continuación, el valor.</td>
<td><strong>. .1000</strong> encuentra cualquier número menor o igual a 1000, &quot;como &quot;100&quot;, 999.95&quot;, y &quot;1,000&quot;.</td>
</tr>
<tr class="odd">
<td><em>valor</em>.. (doble punto)</td>
<td>Mayor o igual que el valor especificado</td>
<td>Escriba el valor y, a continuación, dos puntos .</td>
<td><strong>1000..</strong> encuentra cualquier número que mayor o igual a 1000, como &quot;1,000&quot;, &quot;1,000.01&quot;, y &quot;1,000,000&quot;.</td>
</tr>
<tr class="even">
<td>&gt;<em>valor</em> (signo mayor que)</td>
<td>Mayor que el valor especificado</td>
<td>Escriba un mayor que firman (<strong>&gt;</strong>) y finalmente el valor.</td>
<td><strong>&gt;1000</strong> encuentra cualquier número mayor que 1000, &quot;como &quot;1000.01&quot;, 20,000&quot;, y &quot;1,000,000&quot;.</td>
</tr>
<tr class="odd">
<td>&lt;<em>valor</em> (signo menos que)</td>
<td>Menor que el valor especificado</td>
<td>Escriba menos que firman (<strong>&lt;</strong>) y finalmente el valor.</td>
<td><strong>&lt;1000</strong> encuentra cualquier número menor que 1000, &quot;como &quot;999.99&quot;, 1&quot;, y &quot;-200&quot;.</td>
</tr>
<tr class="even">
<td><em>valor</em>* (asterisco)</td>
<td>Que empieza por el valor que se especifica</td>
<td>Escriba el valor inicial y después un asterisco (<strong>*</strong>).</td>
<td><strong>S*</strong> encuentra cualquier cadena que empiece por &quot;&quot;S, como &quot;Suecia&quot;, &quot;Sydney&quot;, y &quot;San&quot;Francisco.</td>
</tr>
<tr class="odd">
<td>*<em>value</em> (asterisk)</td>
<td>Termina por el valor que se especifica</td>
<td>Escriba un asterisco y, a continuación, el valor final.</td>
<td><strong>*east</strong> encuentra cualquier cadena que termina con &quot;el este&quot;, como &quot;noreste&quot; y &quot;sureste&quot;.</td>
</tr>
<tr class="even">
<td>*<em>valor</em>* (asterisco)</td>
<td>Contiene el valor especificado</td>
<td>Escriba un asterisco, a continuación un valor y, por último, otro asterisco.</td>
<td><strong>*th*</strong> encuentra cualquier cadena que contenga &quot;rr&quot;, como &quot;noreste&quot; y &quot;sureste&quot;.</td>
</tr>
<tr class="odd">
<td>? (signo de interrogación)</td>
<td>Que tenga uno o más caracteres desconocidos</td>
<td>Escriba un signo de interrogación en la posición del carácter desconocido en el valor.</td>
<td><strong>¿Se? th</strong> Serrano&quot; búsquedas &quot;y &quot;Ser&quot;.</td>
</tr>
<tr class="even">
<td><em>valor</em>,<em>valor</em> (coma)</td>
<td>Que coincida con los valores separados por comas</td>
<td>Escriba todos los criterios y sepárelos con comas.</td>
<td><strong>A, D, F, G</strong> encuentra exactamente &quot;encuentra&quot;&quot;exactamente 10&quot;,&quot;<strong>10, 20, 30, 100</strong> 20&quot;, 30 &quot;, 100 de A &quot;, de D, de la F, G&quot;y el.</td>
</tr>
<tr class="odd">
<td>(<span class="code">Instrucción SQL</span>) (instrucción SQL entre paréntesis)</td>
<td>Que coincide con una consulta definida</td>
<td>Escriba una consulta como una instrucción SQL entre paréntesis.</td>
<td><strong><span class="code">(origen de datos. Esta Nombre de campo! = &quot;A&quot;)</span></strong></td>
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
<li>Haga <strong>clientes</strong> &gt; <strong>Facturas</strong> &gt; <strong>Facturas de cliente abiertas</strong>clic en.</li>
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




