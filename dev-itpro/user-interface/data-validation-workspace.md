---
title: "Espacio de trabajo de validación de datos"
description: "El espacio de trabajo de la lista de comprobación de la validación de datos le permite realizar un seguimiento de los procesos de validación de datos de distintas empresas, áreas y personas. La lista de comprobación se puede usar durante una nueva implementación, después de una actualización o después de una migración."
author: bking
manager: AnnBe
ms.date: 05/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: 
ms.assetid: 
ms.search.region: Global
ms.author: bking
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: e105c4b171979a03c20718c1fa9d558c921cd704
ms.contentlocale: es-es
ms.lasthandoff: 06/20/2017


---

# Espacio de trabajo de validación de datos
<a id="data-validation-workspace" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Este tema proporciona una visión general del **Espacio de trabajo de la lista de comprobación de validación de datos** y la configuración asociada.

## Espacio de trabajo de la lista de comprobación de datos
<a id="data-validation-checklist-workspace" class="xliff"></a>

El espacio de trabajo de la **Lista de comprobación de la validación de datos** le permite realizar un seguimiento de los procesos de validación de datos de distintas empresas, áreas y personas. La lista de comprobación se puede usar durante una nueva implementación, después de una actualización o después de una migración. En función de su vista del espacio de trabajo **Lista de comprobación de validación de datos**, verá todas las tareas y estados de un proyecto de validación de datos o solo de las tareas que tiene asignadas.

Debe seleccionar un proyecto de validación de datos en la parte superior del espacio de trabajo. Todos los datos que se muestra en el espacio de trabajo se filtran por el proyecto de validación de datos.

### Iconos de resumen
<a id="summary-tiles" class="xliff"></a>

Los iconos de **Resumen** proporcionan una visión general del proceso y los indicadores para ayudarle a controlar la validación de datos. Puede ver todas las tareas restantes, las tareas completadas, las tareas en curso y las tareas no comenzadas para el proceso. Esta información se muestra para todas las empresas incluidas en el proyecto de validación de datos.

### Sección Tareas y estados
<a id="tasks-and-status-section" class="xliff"></a>

En la sección **Tareas y estado**, se mostrará el estado del proyecto total de la validación de datos de varias maneras: estado por entidad jurídica, por área y por lista de tareas. También puede seleccionar el filtro para ver el estado de una empresa específica. Cada ficha de estado ofrece un desglose por el porcentaje que se ha completado y por el número de tareas restantes.

La última ficha es para la lista de tareas detallada. Esta lista muestra la lista de tareas completa.
Puede filtrar la lista de tareas de varias maneras. Haga clic en **Editar tarea** para cambiar el estado de una tarea o para asignar una tarea. Haga clic en **Datos adjuntos** para ver los datos adjuntos para una tarea.

El nombre de tarea es un hipervínculo a la página Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition o a otra página web donde el usuario debe ir para completar el trabajo. Puede establecer este hipervínculo mediante el campo **Nombre del elemento de menú** al editar o crear una tarea en el formulario **Configurar el proyecto de validación de datos**.

Puede adjuntar archivos, notas, imágenes, y las direcciones URL a una tarea mediante la acción **Archivos adjuntos**. Por ejemplo, puede vincular un archivo de informe que se imprimió para una tarea. Un icono aparece en la columna **Archivos adjuntos** para la tarea si hay un archivo adjunto.

La opción **Completado por** será rellenada automáticamente después de que la tarea se complete con el nombre del trabajador que completó la tarea. Cuando una tarea se ha marcado como completada, el campo **Fecha de finalización** se actualiza automáticamente a la fecha y hora actuales.

### Configurar la paǵina del proyecto de validación de datos
<a id="configure-data-validation-project-page" class="xliff"></a>

Antes de poder usar el espacio de trabajo **Lista de comprobación de validación de datos**, debe configurar el proceso mediante la página **Configurar el proyecto de validación de datos**. (Haga clic en **Espacios de trabajo** \> **Lista de comprobación de validación de datos** \> **Configurar el proyecto de validación de datos**).

### Áreas de tareas
<a id="task-areas" class="xliff"></a>

Use las áreas de tareas para agrupar las tareas de validación de datos en áreas lógicas dentro de su organización. Por ejemplo, Proveedores, Clientes o Contabilidad general se pueden usar como áreas de tareas.

El **Nombre del elemento de menú** está asociado al esfuerzo de trabajo de la tarea y se puede usar para ir directamente a la página asociada desde el vínculo de la tarea en el espacio de trabajo. Por ejemplo, una tarea de validación de datos para ejecutar el informe **Vencimiento de proveedores** para los proveedores se puede vincular a la página **Informe de vencimiento de proveedores** .
