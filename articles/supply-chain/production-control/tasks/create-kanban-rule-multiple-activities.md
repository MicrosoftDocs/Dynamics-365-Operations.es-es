---
title: Crear una regla kanban para varias actividades
description: Este procedimiento muestra cómo crear una regla kanban que incluya varias actividades de un flujo de producción.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f55034f4f0557023ce0c659c1e8258214cf8bfa3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569248"
---
# <a name="create-a-kanban-rule-for-multiple-activities"></a>Crear una regla kanban para varias actividades

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear una regla kanban que incluya varias actividades de un flujo de producción. La empresa de datos de prueba utilizada para crear esta tarea es USMF. Esta tarea está pensada para el ingeniero de procesos o el administrador de flujo de valor, conforme preparan la producción de un producto nuevo o modificado en un entorno de producción ajustada.


## <a name="create-a-new-kanban-rule"></a>Crear una nueva regla kanban
1. Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.
2. Haga clic en Nuevo.
3. En el campo Estrategia de reabastecimiento, seleccione "Programado".
4. En el campo Actividad del primer plan, especifique o seleccione un valor.
    * Seleccione SpeakerAssemblyAndPolish.  
5. Seleccione la casilla Varias actividades.
    * El propósito es incluir más de una actividad en la regla kanban. Elige una ruta en el flujo de producción al seleccionar la última actividad del plan.  
6. En el campo Última actividad del plan, especifique o seleccione un valor.
    * Seleccione SpeakerTestAndPackaging. Tras seleccionar el valor, se abre automáticamente una página. Seleccione el flujo kanban MontajeYPulidoAltavoces > PruebayEmpaquetdoAltavoces. Haga clic en Aceptar  
7. Expanda la sección Detalles.
8. En el campo Producto, especifique o seleccione un valor.
    * Seleccione el artículo L0006.  

## <a name="create-kanban-and-view-jobs"></a>Crear kanban y ver trabajos
1. Expanda la sección Kanbans.
2. Haga clic en Agregar.
3. En el campo Número de kanbans nuevos, escriba "1".
    * Esto creará un kanban.  
4. Defina la cantidad del producto en "3".
    * El kanban procesará 3 productos.  
5. En el campo Tiempo transcurrido, especifique una fecha y una hora.
    * Se puede especificar Hoy.  
6. Haga clic en Crear.
7. Haga clic en Detalles.
    * Observe que el kanban tiene dos trabajos de proceso del flujo de producción. El primero es SpeakerAssemblyAndPolish y el segundo es SpeakerTestAndPackaging.  
    * Este es el último paso.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]