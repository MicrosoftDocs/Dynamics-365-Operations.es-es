---
title: Configurar tareas de Administración de tareas
description: Este artículo explica cómo configurar tareas en la administración de tareas en Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2022-06-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6a38cc2e36c24ddbfe0d8b2886301c108599ab25
ms.sourcegitcommit: 55e440e30490b2d36d86b22aa1263d5da97633aa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2022
ms.locfileid: "9745394"
---
# <a name="set-up-tasks-in-task-management"></a>Configurar tareas de Administración de tareas

[!INCLUDE [PEAP](../includes/peap-1.md)]

En versiones de Microsoft Dynamics 365 Human Resources anteriores a la versión 10.0.30, los usuarios que querían editar una tarea tenían que editar individualmente esa tarea en cada lista de verificación que la contenía. Sin embargo, a partir de la versión 10.0.30 de Human Resources, los usuarios pueden seleccionar cómo se manejan las tareas editadas. Si una tarea que se está editando está en una lista de verificación, la opción **Habilitar actualización de administración de tareas** se debe seleccionar la opción en la pestaña **Administración de tareas** de la página **Parámetros compartidos de recursos humanos** para habilitar la lista de verificación para usar la tarea editada.

[![Habilite la opción de actualización de administración de tareas en la página de parámetros compartidos de recursos humanos.](./media/task-update.png)](./media/task-update.png)

Si las ediciones de las tareas se deben aplicar a todas las tareas de la lista de verificación asociadas, ya debe existir una relación entre la tarea en la biblioteca de tareas y la tarea en la lista de verificación. Se agregó una opción para crear la relación entre la tarea de la biblioteca y la tarea de la lista de verificación.

Puede crear tareas individualmente y luego reutilizarlas en múltiples listas de verificación. Para crear una tarea, en la página **Configuración de incorporación**, en la pestaña **Tareas**, seleccione **Nuevo**.

## <a name="set-up-tasks"></a>Configurar tareas

Para asignar una tarea creada a varias listas de verificación, seleccione la tarea y luego seleccione **Aplicar a las listas de verificación** en el menú.

Alternativamente, puede agregar tareas directamente a una lista de verificación. Para agregar una tarea a una lista de verificación, en la página **Configuración de incorporación**, en la pestaña **Lista de Verificación**, cree una nueva lista de verificación para agregar la tarea o agregue la tarea a una lista de verificación existente.

Para editar una tarea en la biblioteca, seleccione **Editar** en el menú de la biblioteca de tareas. Si la tarea está asociada con alguna lista de verificación, esas listas de verificación se mostrarán en la página **Editar tarea**. Si desea que las tareas en cualquier lista de verificación se actualicen con las ediciones, seleccione esas listas de verificación en la sección **Aplicar a las listas de verificación**.

Para eliminar tareas de la biblioteca, seleccione la opción **Eliminar**. Si la tarea está asociada con una lista de verificación, esta acción no eliminará la tarea de la lista de verificación. Se requiere una acción separada para eliminar una tarea de una lista de verificación.

### <a name="set-up-checklists"></a>Configurar listas de verificación

Una lista de verificación es un grupo de tareas. Puede crear tantas listas de verificación como necesite y puede asignar las mismas tareas a varias listas de verificación. Cuando crea una lista de verificación, especifica un propietario y un calendario.

Para crear una nueva tarea en una lista de verificación, seleccione **Nueva** en la barra del menú tareas. Cuando crea una nueva tarea, puede optar por agregar la tarea a la biblioteca de tareas, para que pueda compartirse en varias listas de verificación. Parar agregar la tarea a la biblioteca, debe establecer la opción **Aplicar tarea a la biblioteca** en **Sí**. Si elige agrega la tarea a la biblioteca de tareas, también puede agregar la tarea a otras listas de verificación al mismo tiempo seleccionando esas listas de verificación en la sección **Aplicar a las listas de verificación**. Si elige no agregar la tarea a la biblioteca de tareas, la tarea solo existirá en la lista de comprobación donde la creó.

Para editar una tarea en una lista de comprobación, seleccione **Editar** en el menú de tareas. Si la tarea está asociada con alguna lista de verificación, esas listas de verificación se mostrarán en la página **Editar tarea**. Si desea que las tareas en cualquier otra lista de verificación se actualicen con las ediciones, seleccione esas listas de verificación en la sección **Aplicar a las listas de verificación**.

Para eliminar tareas de una lista de verificación, seleccione **Quitar**. Esta acción eliminará tareas de la lista de verificación. Sin embargo, no elimina las tareas de la biblioteca de tareas. Para eliminar tareas de la biblioteca de tareas, abra la página **Biblioteca de tareas** y seleccione **Eliminar**.
