---
title: Crear actividades de transferencia para lean manufacturing (producción ajustada)
description: Cree una actividad de transferencia para lean manufacturing.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2925833aceba0cffe46b3a44c5d19c87cd3736e7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436564"
---
# <a name="create-transfer-activities-for-lean-manufacturing"></a>Crear actividades de transferencia para lean manufacturing (producción ajustada)

[!include [banner](../../includes/banner.md)]

Cree una actividad de transferencia para lean manufacturing. 

Requisitos previos: 

1. Se deben crear un flujo de producción y una versión que no estén activas.

2. Se deben crear el almacén de origen y destino. Opcionalmente, se debe crear la celda de trabajo que está reabasteciendo o que está reabastecida.


## <a name="find-the-production-flow-version"></a>Buscar la versión del flujo de producción
1. Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.
2. En la lista, busque y seleccione el registro deseado.
    * Tenga en cuenta que el flujo de producción debe tener una versión en estado de borrador.  
3. En la lista, haga clic en el vínculo de la fila seleccionada.

## <a name="create-a-new-activity"></a>Crear una actividad nueva
1. Haga clic en Actividades.
    * Asegúrese de que el flujo de producción seleccionado tiene una versión en borrador y seleccione esa versión.  
2. Haga clic en Crear actividad de plan nueva.
3. Haga clic en Siguiente.
4. En el campo Nombre, escriba un valor.
5. En el campo Tipo de actividad, seleccione "Transferencia".
6. En el campo Cantidad del proceso, especifique un número.
7. Haga clic en Siguiente.

## <a name="select-the-work-cells"></a>Seleccionar las celdas de trabajo
1. En el campo Reabasteciendo, haga clic en el botón desplegable para abrir la búsqueda.
    * Para usar la ubicación de salida de la celda de trabajo como la ubicación de origen en la actividad de transferencia, seleccione una celda de trabajo. Lo mismo se puede realizar con la celda de trabajo reabastecida, que establece la ubicación de destino de la actividad de transferencia.  
2. En la lista, haga clic en el vínculo de la fila seleccionada.

## <a name="define-the-inventory-updates"></a>Definir las actualizaciones de inventario
1. En el campo Tipo de producto, seleccione una opción.
    * Tenga en cuenta que una transferencia no cambia el tipo de producto. Puede transferir los productos terminados o los productos semiterminados (transferencia entre dos actividades de un flujo de producción y posiblemente un flujo kanban).     Al transferir productos terminados, puede elegir si seleccionar o recibir resultados en una transacción de inventario.  

## <a name="define-the-transfer-locations"></a>Definir las ubicaciones de transferencia
1. Haga clic en Siguiente.
2. En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, busque y seleccione el registro deseado.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo Ubicación, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. En el campo Fletado por, seleccione el “Expedidor”.
    * Se incluyen las siguientes opciones: Expedidor: la organización que opera el almacén del envío, Destinatario: la organización que opera el almacén de recepción, Transportista: un proveedor de terceros. Si la organización operativa es un proveedor, la actividad de transferencia requiere un acuerdo de subcontratación.  
8. Haga clic en Siguiente.

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]