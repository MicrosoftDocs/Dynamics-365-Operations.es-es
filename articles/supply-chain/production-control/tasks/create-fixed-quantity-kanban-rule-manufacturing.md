---
title: Crear una regla kanban de cantidad fija para fabricación
description: Este procedimiento se centra en la configuración necesaria para crear una regla kanban de fabricación fija para activar actividades de transformación, en una celda de trabajo, en un entorno de producción ajustada.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e0f58d1e265fb001474eb572b9bc325cf08790c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "338691"
---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a>Crear una regla kanban de cantidad fija para fabricación

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento se centra en la configuración necesaria para crear una regla kanban de fabricación fija para activar actividades de transformación, en una celda de trabajo, en un entorno de producción ajustada. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento está pensado para el Ingeniero de procesos o el Administrador de flujo de valor, ya que preparan la producción de un producto nuevo o modificado.


## <a name="create-new-kanban-rule"></a>Crear nueva regla kanban
1. Vaya a Reglas kanban.
2. Haga clic en Nuevo.
    * Observe que el tipo predeterminado es Fabricación y la estrategia de reabastecimiento es Fijo. No tiene que cambiar estos parámetros.  
3. En el campo Actividad del primer plan, especifique o seleccione un valor.
    * Esta es la actividad que se realizará para los kanbans creados según esta regla kanban.  Seleccione “SpeakerTestAndPackaging”.  
4. Expanda la sección Detalles.
5. En el campo Producto, especifique o seleccione un valor.
    * Seleccione L0050.  
6. En el campo Unidad de medida, especifique o seleccione un valor.
    * Seleccione minutos.  
7. En el campo Plazo, especifique un número.
    * Escriba 5.  

## <a name="set-quantities"></a>Definir cantidades
1. Expanda la sección Cantidades.
2. Defina la cantidad predeterminada en "10".
    * Esta es la cantidad que se transferirá para cada kanban.  
3. Active la casilla Desviación de cantidad de productos.
    * Con esto, los kanbans seleccionados se puedan completar con una desviación de la cantidad predeterminada.  Para permitir que se completen los kanbans con una cantidad comprendida entre 8 y 12, establezca las desviaciones en 2.  
4. Establezca la desviación por debajo de "2".
    * Esto le permitirá completar hasta 10 - 2 = 8  
5. Establezca la desviación por encima de "2".
    * Esto le permitirá completar hasta 10 + 2 = 12  
6. En el campo Cantidad kanban fija, escriba un número.
    * Este es el importe de kanbans que deben estar activos. En este caso, 5 kanban que procesan 10 por cada uno.  
7. En el campo Mínimo de límite de alerta, especifique "2".
    * Se usa para realizar el seguimiento del importe mínimo de kanbans completos que deben encontrarse en el destino. Por ejemplo, esto se usa en la visión general de la cantidad kanban.  
8. En el campo Máximo de límite de alerta, especifique "4".
    * Se usa para realizar el seguimiento del importe máximo de kanbans completos que deben encontrarse en el destino. Por ejemplo, esto se usa en la visión general de la cantidad kanban.  
9. En el campo Cantidad de planificación automática, especifique "1".
    * La configuración de este valor en 1 significa que cada kanban se planeará automáticamente.   Si especificamos 3, los kanbans no se planificarán hasta que 3 kanbans vacíos estén listos para planificación. Esto resulta útil para agrupar el trabajo y evitar una configuración excesiva.  

## <a name="create-kanbans"></a>Crear kanbans
1. Expanda la sección Kanbans.
2. Haga clic en Guardar.
    * La regla kanban se tiene que guardar para que se puedan crear los kanbans.  
3. Haga clic en Agregar.
    * Tenga en cuenta que no hay kanbans activos, debido a esto el 'Número de los nuevos kanbans' sugerido es 5. Esto es igual a “la cantidad kanban fija”.  
4. Haga clic en Crear.
    * Esto creará 5 kanbans.  
    * Tenga en cuenta que se crearon 5 kanbans, para 10 cada uno, para esta regla kanban de fabricación. Este es el último paso de este procedimiento.  

