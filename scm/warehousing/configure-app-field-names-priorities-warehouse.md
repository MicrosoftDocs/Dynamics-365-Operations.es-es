---
title: "Configurar los nombres de campo de la aplicación de aplicación de almacenamiento de datos"
description: "Este tema describe cómo definir y configurar nombres de campo y las prioridades de la aplicación del almacén de Dynamics 365 para las operaciones."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: ce8f6d6f7090995bc44db1ba0103a7d6c0416620
ms.lasthandoff: 03/31/2017


---

# <a name="configure-app-field-names-in-warehousing-app"></a>Configurar los nombres de campo de la aplicación de aplicación de almacenamiento de datos

Este tema describe cómo definir y configurar nombres de campo y las prioridades de la aplicación del almacén de Dynamics 365 para las operaciones. 

** Nota: ** Este tema se aplica a las funciones de gestión de almacenes. No se aplica a las funciones de gestión de inventario. Dinámica 365 para las operaciones (el almacenamiento de datos es una aplicación que puede usar para realizar tareas de almacén. Es posible definir y configurar los nombres de campo que se utilizan en la aplicación, así como configurar la prioridad a la que los nombres de campo se deben asignar. Este tema explica cómo definir y configurar los nombres de campo y las prioridades de la aplicación de almacenes, y cómo se usan en Dynamics 365 para las operaciones (almacenamiento de datos. Para obtener información detallada sobre cómo configurar la conexión a Dynamics 365 para las operaciones (almacenamiento de datos, consulte a preceptoral [la instalación y configure Dynamics 365 para las operaciones (almacenamiento de datos install-configure-warehousing-app.md] ().

<a name="configure-warehouse-app-field-names"></a>Configurar los nombres de campo de la solicitud de almacén
===================================

Cuando se usa Dynamics 365 para las operaciones (almacenamiento de datos del dispositivo móvil, puede configurar cómo los metadatos se deben mostrar en su dispositivo en ** los nombres de campo de la solicitud de almacén ** página. En una nueva empresa en Dynamics 365 para las operaciones, seleccione ** crear la configuración predeterminada ** para generar todos los nombres de campo que se usarán en los flujos de trabajo del dispositivo móvil del almacén y, a continuación para asignar un modo de entrada y una entrada preferidos escritos a ellos. Una vez que haya generado todos los nombres de campo, puede seleccionar las siguientes opciones en la entrada.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opción</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Modo de entrada preferido</td>
<td>Esta opción define si un campo de detección o un campo de entrada de entrada manual se debe mostrar para el nombre del campo seleccionado. Esto resulta útil para distinguir campos en función de si los códigos de barras se usan para el campo. <strong>Nota:</strong> Para los nombres de campo con el modo de entrada preferido establecido como, puede especificar información manualmente si el código de barras es ilegible o está dañado.</td>
</tr>
<tr class="even">
<td>Tipo de entrada</td>
<td>Esta opción define qué tipo de entrada se va a utilizar para el nombre del campo seleccionado. Cuatro opciones están disponibles:
<ul>
<li><strong>Selección</strong> - contiene una lista de opciones de elegir entre. Los nombres de campo con esta opción no se puede editar.</li>
<li><strong>Fecha</strong>los nombres de campos - especificados como fecha muestren un formato de fecha con la etiqueta. Esto ayuda a trabajadores de almacén a ver en qué formato para especificar la fecha. Los nombres de campo con esta opción no se puede editar.</li>
<li><strong>Alfa</strong> - si se selecciona, el teclado del dispositivo se usará al especificar la información manualmente en la aplicación. La experiencia de teclado se puede modificar en función de la cual se usa el dispositivo.</li>
<li><strong>Numérico</strong> - para los nombres de campo que usan entrada numérica, sólo puede seleccionar esta opción para mostrar un teclado numérico personalizado con el campo de entrada en lugar del teclado del dispositivo.</li>
</ul></td>
</tr>
</tbody>
</table>

<a name="configure-warehouse-app-field-priority"></a>Configurar la prioridad del campo de la solicitud de almacén
======================================

En ** almacene la prioridad del campo de la aplicación ** la página, puede establecer nombres de campo en distintos grupos de prioridad. Esto permite a decidir qué información se debe mostrar en la página principal de labor cuando los trabajadores de almacén realizan tareas mediante la aplicación. Si hace clic en ** crear la configuración predeterminada, ** generarán un conjunto del valor predeterminado de grupos de prioridad. Es posible crear tantos grupos de prioridad según sea necesario, pero sólo se mostrarán tres grupos de prioridad en la página de tareas. Cuando Dynamics 365 para las operaciones registra metadatos a la aplicación, asigne cada campo con una prioridad en función de su prioridad, y la aplicación mostrará a los primeros tres grupos de prioridad contenido en los metadatos en la página de tareas. El resto de metadatos desbordan que se mostrará en una página de detalles secundaria. En la tabla siguiente se muestra un ejemplo de cinco grupos de prioridad.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo de prioridad</th>
<th>Campos asignados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> Prioridad 10</td>
<td><ul>
<li>Artículo</li>
<li>Cantidad</li>
<li>Unidad de medida</li>
</ul></td>
</tr>
<tr class="even">
<td> Prioridad 20</td>
<td><ul>
<li>Posición del clúster</li>
<li>Clúster</li>
</ul></td>
</tr>
<tr class="odd">
<td> Prioridad 30</td>
<td><ul>
<li>Descripción de artículo</li>
</ul></td>
</tr>
<tr class="even">
<td> Prioridad 40</td>
<td><ul>
<li>Configuración</li>
<li>Color</li>
<li>Tamaño</li>
<li>Estilo</li>
</ul></td>
</tr>
<tr class="odd">
<td> Prioridad 50</td>
<td><ul>
<li>Ubicación</li>
<li>Matrícula de entidad de almacén</li>
</ul></td>
</tr>
</tbody>
</table>

Por ejemplo, cuando un trabajador del almacén realiza una tarea en un dispositivo móvil, si los metadatos que se mostrarán en la aplicación constan de los campos siguientes:

-   Artículo
-   Cantidad
-   Unidad de medida
-   Descripción de artículo
-   Tamaño y ubicación

En función de la configuración de la prioridad del campo de la aplicación de almacén en la tabla anterior, las 3 filas siguientes de información se mostrarán en la página de tareas:

-   Fila 1: Artículo, cantidad, unidad de medida
-   Fila 2: Descripción del artículo
-   Fila 3: Tamaño

Metadatos restantes, por ejemplo, ubicación, no se muestren en la página de tareas, pero se mostrarán en una página de detalles. Para obtener más información y ver ejemplos de la interfaz de usuario, consulte el artículo a partir de blog [que anuncia Dynamics 365 para las operaciones (almacenamiento de datos (https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/)].

<a name="see-also"></a>Consulte también
--------

[La instalación y configurar Microsoft Dynamics 365 para las operaciones (almacenamiento de datos (install-configure-warehousing-app.md])


