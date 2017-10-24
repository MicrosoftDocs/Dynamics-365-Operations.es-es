--- 
title: "Creación de grupos de permisos de PDV"
description: "Este procedimiento mostrará cómo crear un grupo de permisos de PDV."
author: scott-tucker
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e924dc59c3e4cb9b6979014852512453dd3d70db
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-pos-permission-groups"></a>Creación de grupos de permisos de PDV

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimiento mostrará cómo crear un grupo de permisos de PDV. La empresa de datos de prueba utilizada para crear esta tarea es USRT. Esta tarea está pensada para el rol de encargado de operaciones comerciales.

1. Vaya a Grupos de permisos.
2. Haga clic en Nuevo.
3. En el campo Id. de grupo de permisos de PDV, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. Seleccione Sí en el campo Ver entradas de reloj de tiempo.
    * Ahora puede habilitar o deshabilitar varios permisos para el grupo de permisos de PDV. Para algún permiso puede establecer un valor que se usará para evaluar si el usuario del PDV puede realizar la acción.  Esta guía de tareas permite algunos permisos que se pueden dar a un cajero.  
6. Seleccione Sí en el campo Permitir creación de pedidos.
7. Seleccione Sí en el campo Permitir edición de pedidos.
8. Seleccione Sí en el campo Permitir recuperación de pedidos.
9. Seleccione Sí en el campo Permitir cambio de contraseña.
10. Seleccione Sí en el campo Permitir cierre en ciego.
11. Haga clic en Guardar.
    * Una vez se guarden los cambios necesita ejecutar la programación de distribución del personal para aplicar los cambios en canales comerciales.  
12. Cierre la página.
13. Vaya a Trabajos.
    * A continuación asignaremos el grupo de permisos de PDV a un trabajo.  
14. En la lista, busque y seleccione el registro deseado.
15. En la lista, haga clic en el vínculo de la fila seleccionada.
16. Haga clic en Editar.
17. Expanda la sección Clasificación de trabajos.
18. En el campo Grupo de permisos de PDV, especifique o seleccione un valor.
    * Todos los trabajadores de puestos para este trabajo usarán los parámetros de este grupo de permisos de PDV a menos que los permisos de PDV de los trabajadores se hayan anulada en su nivel del puesto.  
19. Haga clic en Guardar.
    * Una vez se guarden los cambios necesita ejecutar la programación de distribución del personal para aplicar los cambios en canales comerciales.  


