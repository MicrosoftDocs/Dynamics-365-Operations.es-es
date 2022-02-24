---
title: Configuración de nombres de campo de aplicación en la aplicación de almacén
description: Este tema describe cómo definir y configurar nombres de campo y prioridades de la aplicación de almacén en Dynamics 365 Supply Chain Management.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ac31b3d2b3b1d9ca51919fe75e06f0de1cda0c63
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963444"
---
# <a name="configure-app-field-names-in-the-warehouse-app"></a>Configuración de nombres de campo de aplicación en la aplicación de almacén

[!include [banner](../includes/banner.md)]

Este tema describe cómo definir y configurar nombres de campo y prioridades de la aplicación de almacén en Dynamics 365 Supply Chain Management. 

> [!NOTE]
> Este tema se aplica a las características de gestión de almacenes. No se aplica a las características de gestión del inventario. Warehousing es una aplicación que puede usar para realizar tareas de almacén. Es posible definir y configurar los nombres de campo que se utilizan en la aplicación, así como configurar la prioridad a la que los nombres de campo se deben asignar. Este tema explica cómo definir y configurar estos nombres de campo y prioridades de la aplicación de almacén y cómo se usan en Warehousing. Para obtener información detallada sobre cómo configurar la conexión a Warehousing, consulte el tutorial sobre [Instalación y configuración de la aplicación de almacén](install-configure-warehousing-app.md).

## <a name="configure-warehouse-app-field-names"></a>Configurar nombres de campo de la aplicación de almacén

Cuando se usa Warehousing en el dispositivo móvil, puede configurar cómo los metadatos se deben mostrar en su dispositivo en la página **Nombres de campo de aplicación de almacén**. En una nueva empresa, seleccione **Crear configuración predeterminada** para generar todos los nombres de campo que se usarán en los flujos de trabajo del dispositivo móvil de almacén y, a continuación, para asignarles un modo y un tipo de entrada preferidos. Una vez que haya generado todos los nombres de campo, puede seleccionar las siguientes opciones de entrada.

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
<td>Esta opción define si un campo de detección o un campo de entrada manual se debe mostrar para el nombre del campo seleccionado. Esto resulta útil para distinguir campos en función de si los códigos de barras se usan para el campo. <strong>Nota:</strong> Para los nombres de campo con el modo de entrada preferido establecido como <strong>Exploración</strong>, puede especificar información manualmente si el código de barras es ilegible o está dañado.</td>
</tr>
<tr class="even">
<td>Tipo de entrada</td>
<td>Esta opción define qué tipo de entrada se va a utilizar para el nombre del campo seleccionado. Las opciones disponibles son cuatro:
<ul>
<li><strong>Selección</strong> - contiene una lista de opciones entre las que elegir. Los nombres de campo con esta opción no se pueden editar.</li>
<li><strong>Fecha</strong> - los nombres de campos especificados como fecha muestran un formato de fecha con la etiqueta. Esto ayuda a los trabajadores del almacén a ver en qué formato deben especificar la fecha. Los nombres de campo con esta opción no se pueden editar.</li>
<li><strong>Alfa</strong> - si se selecciona, el teclado del dispositivo se usará al especificar la información manualmente en la aplicación. La experiencia de teclado se puede modificar en función de qué dispositivo se usa.</li>
<li><strong>Numérico</strong> - para los nombres de campo que usan solo entradas numéricas, puede seleccionar esta opción para mostrar un teclado numérico personalizado con el campo de entrada en lugar del teclado del dispositivo.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a>Configurar la prioridad de campo de aplicación de almacén

En la página **Prioridad de campo de aplicación de almacén**, puede poner nombres de campo en distintos grupos de prioridad. Esto permite decidir qué información se debe mostrar en la página de la tarea principal cuando los trabajadores del almacén realizan tareas mediante la aplicación. Si hace clic en **Crear configuración predeterminada**, se generará un conjunto predeterminado de grupos de prioridad. Es posible crear tantos grupos de prioridad según sea necesario, pero solo se mostrarán tres grupos de prioridad en la página de tareas. Cuando el sistema envía metadatos a la aplicación, asignará a cada campo una prioridad relativa en función de su grupo de prioridad, y la aplicación mostrará los primeros tres grupos de prioridad contenidos en los metadatos en la página de tareas. El resto de los metadatos que se desbordan se mostrará en una página de detalles secundaria. En la tabla siguiente se muestra un ejemplo de cinco grupos de prioridad.

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

Por ejemplo, cuando un trabajador del almacén realiza una tarea en un dispositivo móvil, si los metadatos que se van a mostrar en la aplicación constan de los campos siguientes:

-   Artículo
-   Cantidad
-   Unidad de medida
-   Descripción de artículo
-   Tamaño y ubicación

En función de la configuración de la prioridad del campo de la aplicación de almacén de la tabla anterior, las 3 filas siguientes de información se mostrarán en la página de tareas:

-   Fila 1: artículo, cantidad, unidad de medida
-   Fila 2: descripción del artículo
-   Fila 3: tamaño

Los metadatos restantes, por ejemplo, ubicación, no se muestran en la página de tareas, pero se mostrarán en una página de detalles. Para obtener más información y ver ejemplos de la interfaz de usuario, consulte el artículo del blog [Presentando Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).

<a name="additional-resources"></a>Recursos adicionales
--------

[Visión general sobre cómo instalar y configurar la aplicación almacén](install-configure-warehousing-app.md)
