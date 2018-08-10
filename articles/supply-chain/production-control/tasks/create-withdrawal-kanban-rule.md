--- 
title: Crear una nueva regla kanban de retirada
description: "Este procedimiento muestra la configuración necesaria para crear una regla kanban de retirada para transferir material en un entorno de producción ajustada."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 02c7133d2e02b27fb428874deeda21e2bab28fb6
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-withdrawal-kanban-rule"></a>Crear una nueva regla kanban de retirada

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra la configuración necesaria para crear una regla kanban de retirada para transferir material en un entorno de producción ajustada. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento está pensado para el Ingeniero de procesos o el Administrador de flujo de valor, ya que preparan el reabastecimiento de material nuevo o modificado.


## <a name="create-new-kanban-rule"></a>Crear nueva regla kanban
1. Vaya a Reglas kanban.
2. Haga clic en Nuevo.
3. En el campo Tipo, seleccione "Retirada".
    * El tipo Retirada se usa para que las reglas kanban transfieran material o mercancías.  
4. En el campo Actividad del primer plan, especifique o seleccione un valor.
    * Seleccione ReplenishSpeakerComponents.   Esta actividad se configura para mover componentes del almacén 11, ubicación 11 al almacén 12 y la ubicación 12.  
5. En el campo Producto, especifique o seleccione un valor.
    * Seleccione M0007.  
6. En el campo Plazo, especifique un número.
    * Por ejemplo, 60.  
7. En el campo Unidad de medida, especifique o seleccione un valor.
    * Por ejemplo, Minutos.  

## <a name="set-quantities-for-kanban"></a>Establecer cantidades para kanban
1. Defina la cantidad predeterminada en "5".
    * Esta es la cantidad que se transferirá para cada kanban.  
2. En el campo Cantidad kanban fija, especifique "2".
    * Este es el importe de kanbans que deben estar activos. En este caso, 2 kanbans que transfieren 5 por cada uno.  
3. En el campo Mínimo de límite de alerta, especifique "1".
    * Se usa para realizar el seguimiento del importe mínimo de kanbans completos que deben encontrarse en el destino. Por ejemplo, esto se usa en la visión general de la cantidad kanban.  
4. En el campo Máximo de límite de alerta, especifique "2".
    * Se usa para realizar el seguimiento del importe máximo de kanbans completos que deben encontrarse en el destino. Por ejemplo, esto se usa en la visión general de la cantidad kanban.  

## <a name="create-kanbans"></a>Crear kanbans
1. Haga clic en Guardar.
    * La regla kanban se tiene que guardar para que se puedan crear los kanbans.  
2. Haga clic en Agregar.
    * Tenga en cuenta que no hay kanbans activos porque el "Número de kanbans nuevos" es 2, lo que es igual a la "Cantidad kanban fija".  
3. Haga clic en Crear.
    * Esto creará dos kanbans.  
    * Tenga en cuenta que se crearon 2 kanbans, para 5 cada uno, para esta regla kanban de retirada.  Este es el último paso de este procedimiento.  


