---
title: Crear una celda de trabajo subcontratado para lean manufacturing (producción ajustada)
description: Para modelar trabajo subcontratado para lean manufacturing, debe crear una celda de trabajo que esté asociada al proveedor que proporciona el trabajo.
author: cvocph
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 58b725af456f1a5c7f158f01ffe48a2d8cdf056b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550546"
---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a>Crear una celda de trabajo subcontratado para lean manufacturing (producción ajustada)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Para modelar trabajo subcontratado para lean manufacturing, debe crear una celda de trabajo que esté asociada al proveedor que proporciona el trabajo. Se vincula a una celda de trabajo subcontratada al proveedor a través de la asociación de un recurso del tipo proveedor. Si ejecuta este registro en la empresa de demostración USMF, puede seleccionar el identificador del proveedor 1002 y el sitio 1.


## <a name="create-a-vendor-resource"></a>Crear un recurso de proveedores
1. Vaya a Recursos.
2. Haga clic en Nuevo.
3. En el campo Recurso, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Tipo, seleccione el tipo "Proveedor".
6. En el campo Proveedor, haga clic en el botón desplegable para abrir la búsqueda.

## <a name="create-the-resource-group"></a>Crear el grupo de recursos
1. Vaya a Grupos de recursos.
2. Haga clic en Nuevo.
3. En el campo Grupo de recursos, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.
    * Seleccione el sitio al debe asignarse la celda de trabajo. En teoría, un sitio puede representar un solo sitio que opera un proveedor. Sin embargo, en la mayoría de los casos, solo los recursos subcontratados se asignan al sitio que solicita el trabajo subcontratado. Tenga en cuenta que los almacenes de entrada y salida de celdas de trabajo subcontratadas deben encontrarse en el mismo sitio.  
6. En el campo Sitio, escriba un valor.
7. @SysTaskRecorder: _RequestClose
8. Seleccione o desactive la casilla Celda de trabajo.
9. En el campo Almacén de entrada, haga clic en el botón desplegable para abrir la búsqueda.
    * Seleccione el almacén y la ubicación que se usan para organizar el material para la celda de trabajo que administra el proveedor. En muchos casos, el almacén y la ubicación se crean mediante un almacén separado por proveedor y una ubicación por celda de trabajo.  
10. En el campo Ubicación de entrada, haga clic en el botón desplegable para abrir la búsqueda.
11. En el campo Almacén de salida, haga clic en el botón desplegable para abrir la búsqueda.
    * Definir el almacén y la ubicación donde se envía material cuando las actividades subcontratadas de la celda de trabajo se registran. El almacén y la ubicación pueden estar en el sitio del proveedor si el proveedor registra trabajos kanban. De manera alternativa, el almacén y la ubicación pueden ser la ubicación de recepción asociada al siguiente paso del flujo de producción.  
12. En el campo Ubicación de salida, haga clic en el botón desplegable para abrir la búsqueda.
13. Expanda o contraiga la sección Calendarios.
14. Haga clic en Agregar.
15. En el campo Calendario, haga clic en el botón desplegable para abrir la búsqueda.
    * Asocie el horario de trabajo de la celda de trabajo con el grupo de recursos. Para los recursos críticos, se recomienda que defina calendarios específicos que representen los horarios de trabajo precisos y las capacidades relacionadas de la celda de trabajo o el sitio del proveedor.  
16. Expanda o contraiga la sección Recursos.
17. Haga clic en Agregar.
    * Un grupo de recursos subcontratado debe tener un recurso asociado del tipo proveedor que vincule el grupo de recursos a la cuenta de proveedor.  
18. En el campo Recursos, haga clic en el botón desplegable para abrir la búsqueda.
    * Seleccione o especifique el recurso de proveedor que ha creado en la subtarea anterior.  
19. Expanda o contraiga la sección Capacidad de la celda de trabajo.
20. Haga clic en Agregar.
    * Una celda de trabajo debe tener una capacidad definida. En este ejemplo, creamos una capacidad de rendimiento de 100 piezas por día laborable estándar.  
21. En el campo Modelo de flujo de producción, haga clic en el botón desplegable para abrir la búsqueda.
22. En el campo Período de capacidad, seleccione una opción.
23. En el campo Cantidad promedio de proceso, especifique un número.
24. En el campo Unidad, haga clic en el botón desplegable para abrir la búsqueda.
25. Resuelva los cambios en la unidad.

