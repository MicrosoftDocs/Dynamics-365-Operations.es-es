---
title: Crear actividades de proceso para lean manufacturing (producción ajustada)
description: Cree una actividad de proceso para lean manufacturing.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup, PlanActivityDetails, KanbanJobPickingListPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bd505446456791b26850d676722b6676b50dca4b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981215"
---
# <a name="create-process-activities-for-lean-manufacturing"></a>Crear actividades de proceso para lean manufacturing (producción ajustada)

[!include [banner](../../includes/banner.md)]

Cree una actividad de proceso para lean manufacturing. 

Requisitos previos: 

1. Se deben crear un flujo de producción y una versión que no estén activas.

2. Se debe crear una celda de trabajo.


## <a name="find-the-production-flow-version"></a>Buscar la versión del flujo de producción
1. Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.

## <a name="create-a-new-activity"></a>Crear una actividad nueva
1. Haga clic en Actividades.
    * Asegúrese de que el flujo de producción seleccionado tiene una versión en borrador y seleccione esa versión.  
2. Haga clic en Crear actividad de plan nueva.
3. Haga clic en Siguiente.
4. En el campo Nombre, escriba un valor.
5. En el campo Nombre, escriba un valor.
    * Tenga en cuenta que el nombre debe ser único para un flujo de producción dado para todas las versiones.  
6. En el campo Cantidad del proceso, especifique un número.
    * Tenga en cuenta que no importa cuál sea la cantidad de trabajo que se procesará, esta es la cantidad mínima por trabajo para calcular el coste de mano de obra. Si las cantidades de trabajo se desvían de esta cantidad, se creará la desviación del coste de mano de obra.  
7. Haga clic en Siguiente.

## <a name="select-the-work-cell"></a>Seleccionar la celda de trabajo
1. En el campo Celda de trabajo, haga clic en el botón desplegable para abrir la búsqueda.
2. En la lista, haga clic en el vínculo de la fila seleccionada.

## <a name="define-the-inventory-updates"></a>Definir las actualizaciones de inventario
1. Active o desactive la casilla Actualizar recepción disponible.
    * Si Actualizar disponible = No, puede definir la actividad para recibir un producto semiterminado (la actividad no llega al siguiente nivel de L. MAT).    También puede seleccionar consumir productos semiterminados.  

## <a name="define-the-picking-activities"></a>Definir las actividades de picking
1. Haga clic en Siguiente.
2. En la lista, marque la fila seleccionada.
    * Se creará una actividad de selección predeterminada para la ubicación de entrada de la celda de trabajo seleccionada.  
3. Haga clic en Agregar.
    * Puede crear actividades de picking adicionales para productos específicos, que no se almacenan provisionalmente en la actividad de entrada de la celda de trabajo.  
4. En la lista, busque y seleccione el registro deseado.
5. En el campo Código de artículo, escriba un valor.
6. En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.
    * Con esta definición, todos los materiales consumidos en la actividad se seleccionan de la ubicación y del almacén de entrada predeterminada excepto el artículo que se define en la segunda actividad de selección. Este artículo se seleccionará de una ubicación y almacén distintos.  
7. En la lista, busque y seleccione el registro deseado.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. Active o desactive la casilla Registrar residuo.
10. Haga clic en Siguiente.

## <a name="define-the-activity-times"></a>Defina los tiempos de actividad
1. En la lista, busque y seleccione el registro deseado.
    * Se requiere la definición de un tiempo de ejecución. El tiempo de ejecución se usa para calcular costes y los tiempos de procesamiento de los trabajos kanban. Los tiempos de ejecución no se usan para calcular la carga de capacidad y el consumo; esto se calcula por el tiempo de ciclo, derivado de la tarea de la versión del flujo de producción.  
2. En campo de tiempo, escriba un número.
3. En el campo Unidad, escriba un valor.
4. Seleccione la unidad de tiempo.
5. En el campo Por cantidad, especifique un número.
6. En la lista, busque y seleccione el registro deseado.
    * Los tiempos de cola son opcionales.  
7. En campo de tiempo, escriba un número.
8. En el campo Unidad, escriba un valor.
9. Seleccione la unidad de tiempo.
10. En el campo Por cantidad, especifique un número.
11. Haga clic en Siguiente.
12. Haga clic en Finalizar.
13. Cierre la página.

