--- 
title: "Agregar una actividad existente a una versión del flujo de producción"
description: "Al crear nuevas versiones de flujos de producción, puede decidir si agregar actividades creadas para versiones anteriores a la nueva versión."
author: cvocph
manager: AnnBe
ms.date: 10/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: a74fb34db71ba4b539c1b6ede361329aaeb94920
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a>Agregar una actividad existente a una versión del flujo de producción

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Al crear nuevas versiones de flujos de producción, puede decidir si agregar actividades creadas para versiones anteriores a la nueva versión. Este procedimiento muestra cómo se crea una nueva versión para un flujo de producción existente, sin copiar las actividades. En el paso siguiente, una actividad existente se agrega a la nueva versión. 

Esta tarea necesita que haya un flujo de producción con versión y actividades ya creadas.


## <a name="create-a-new-production-flow-version"></a>Crear una nueva versión de flujo de producción
1. Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Haga clic en Editar.
5. En la lista, marque la fila seleccionada.
6. En el campo Fecha de vencimiento, especifique una fecha y una hora.
    * Tenga en cuenta que antes de crear una nueva versión del flujo de producción, debe asegurarse de comprobar la fecha y hora de vencimiento de la versión activa. La nueva versión se creará con una fecha de vigencia inicial, que se vincula a la fecha de caducidad de la versión seleccionada.  
7. Haga clic en Agregar.
8. Seleccione No en la Copia del campo de la versión.
    * Seleccione No para empezar con una versión vacía si la mayoría de las actividades de la versión copiada van a ser sustituidas por nuevas actividades. Agregue las actividades sin cambios a la función Agregar existente en el formulario de actividades manualmente.  
9. Seleccione No en el campo Duplicado de las reglas kanban.
    * Cuando las actividades no se copian en la nueva versión, no se podrá copiar reglas kanban en el momento de la creación de la nueva versión.   En su lugar, deberá usar la función para crear una sustitución kanban más adelante en el formulario de la regla kanban, para reemplazar las reglas kanban de la antigua versión del flujo de producción, con reglas kanban que utilicen las actividades de la nueva versión.  
10. Haga clic en Aceptar
11. En la lista, busque y seleccione el registro deseado.

## <a name="add-an-existing-activity"></a>Agregue una actividad existente
1. Haga clic en Actividades.
2. Haga clic en Agregar existentes para abrir el cuadro de diálogo desplegable.
    * Busque y seleccione una actividad existente para agregarla a la nueva versión del flujo de producción.  Tenga en cuenta que la lista muestra todas las actividades creadas para este flujo de producción para todas las versiones anteriores del flujo.  
3. En el campo Actividad, especifique o seleccione un valor.
4. Haga clic en Aceptar


