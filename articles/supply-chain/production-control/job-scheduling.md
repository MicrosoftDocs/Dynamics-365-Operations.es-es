---
title: Programación de trabajos
description: Este artículo proporciona información acerca de la programación de trabajos, que es un formulario más detallado de programación que la programación de operaciones. Puede utilizar una programación de trabajos para programar trabajos o pedidos de tienda y controlar el entorno de fabricación.
author: ChristianRytt
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19431
ms.assetid: aef37341-91d8-4263-80eb-35d9584be156
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bff966a68001d479b8631e13caa18c9ec8d2bf4c
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211500"
---
# <a name="job-scheduling"></a>Programación de trabajos

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca de la programación de trabajos, que es un formulario más detallado de programación que la programación de operaciones. Puede utilizar una programación de trabajos para programar trabajos o pedidos de tienda y controlar el entorno de fabricación.

Puede utilizar una programación de trabajos para programar trabajos o pedidos de tienda y controlar el entorno de fabricación. La programación de trabajos divide cada operación en tareas o trabajos individuales. Estos trabajos se asignan a los recursos de operación que los realizarán. La programación de trabajos también le permite sincronizar todos los trabajos a los que se hace referencia en el trabajo seleccionado. Puede especificar una fecha y hora de inicio o de fin para el trabajo y ejecutar la programación. El tiempo que se especifica puede ser la hora de inicio o de final en función de la dirección de programación. Esta función resulta útil, por ejemplo, cuando un trabajo se puede ejecutar solo en una máquina a la vez o bien para optimizar el trabajo que se ejecuta para cada recurso.

## <a name="tasks-in-the-job-scheduling-process"></a>Tareas en el proceso de programación de trabajos
El proceso de programación del trabajo incluye las siguientes tareas:

-   Dividir cada operación en trabajos.
-   Programar trabajos que se basan en las fechas y en los tiempos de los recursos que se especifican en la operación relacionada.
-   Calcular la hora de inicio y la hora de finalización para cada trabajo. Puede usar capacidad limitada para asegurarse de que no hay horas superpuestas.
-   Determine en qué recursos del grupo de recursos ejecutar el trabajo. Esta tarea requiere que se especifique un grupo de recursos para una operación. La programación de trabajos selecciona los recursos y grupos de recursos en función del plazo más corto y también tiene en cuenta las reservas previas en los recursos.
-   Expanda las operaciones en trabajos cuando ejecuta la programación de trabajos. Los trabajos se programan por la fecha y la hora del pedido especificado por la ruta de producción. La configuración de la operación determina qué trabajos expandir durante el proceso de programación. El grupo de rutas asignado a la operación controla si los trabajos están generados. Los trabajos se generan únicamente si tienen una duración específica. Por ejemplo, un trabajo de tiempo de transporte se genera si se ha especificado un tiempo de transporte para la operación seleccionada.

## <a name="scheduling-direction"></a>Dirección de programación
Puede programar trabajos hacia adelante o hacia atrás.

-   **Hacia adelante**: use la dirección de programación hacia adelante para iniciar la producción lo más rápidamente posible. Este método también se conoce como método de empuje, pues la producción se "empuja" hacia adelante a lo largo del proceso de producción. La producción se programa para iniciarse y completarse lo más rápido posible.
-   **Hacia atrás**: use la dirección de programación hacia atrás para iniciar la producción lo más tarde posible. También se conoce como método de extracción, ya que se basa en la fecha en que se debe completar la producción. La programación hacia atrás calcula la última fecha posible en la que se puede iniciar la producción sin dejar de cumplir con la fecha límite.

## <a name="finite-capacity"></a>Capacidad limitada
Puede programar trabajos al utilizar una capacidad limitada. Cuando se usa capacidad limitada, la capacidad que se programa no puede ser mayor a la capacidad disponible para el recurso. El tiempo disponible se define como el intervalo de tiempo en el que está disponible el recurso y no hay otras reservas en la capacidad. Una programación que se basa en capacidad limitada garantiza que no se superpongan las horas de inicio y finales para una operación en una fecha determinada. Se tiene en cuenta la capacidad del recurso que ya está reservada y las superposiciones entre las horas de inicio y de fin. La capacidad limitada determina la cantidad de capacidad que debe estar disponible para un recurso para lograr un uso óptimo de dicho recurso. Esta resolución se equilibrada con un cálculo del plazo más corto posible entre operaciones.

## <a name="finite-materials"></a>Materiales finitos
La programación de trabajos que se basa en los materiales limitados garantiza que los materiales necesarios están disponibles cuando la operación inicia. Las reglas de cobertura para los artículos definen estos límites. La programación usa una expansión de requisitos para determinar cuándo están disponibles los artículos. Si programa sin configurar materiales limitados, el sistema asume que todos los artículos están disponibles cuando se necesitan.

## <a name="finite-properties"></a>propiedad finita
La programación de trabajos con propiedades especiales requiere que se especifiquen propiedades para las operaciones de la ruta de producción. Estas propiedades deben cumplirse para reservar la capacidad.

## <a name="references"></a>Referencias
La programación de trabajos programa todas las producciones a las que hace referencia la producción actual. Si una producción tiene una o varias subproducciones, deben programarse al mismo tiempo que la producción principal, pues ésta no se puede iniciar hasta que se completen las subproducciones relacionadas.

## <a name="schedule-resources"></a>Programar recursos
El motor de programación examina las combinaciones de recursos para identificar aquellas que cumplen con los requisitos. Puede especificar criterios de selección eligiendo uno de los siguientes valores en el campo **Selección de recurso principal** de la página **Parámetros de programación**:

-   **Duración**: el motor de programación selecciona los recursos que tienen el plazo más breve. **Nota**: la programación por duración puede reducir el rendimiento cuando el mismo grupo de recursos contiene muchos recursos y se usan operaciones secundarias. Se puede programar un máximo de 32 recursos por operación. Si se supera esta cantidad, aparecerá un mensaje de registro de información y la programación de trabajo no encuentra el mejor recurso alternativo.
-   **Prioridad**: el motor de programación selecciona el recurso con la mayor prioridad cuando dos o más recursos tienen idénticas capacidades y niveles. El recurso con el menor valor numérico en este campo tiene la máxima prioridad.

Cuando se ejecuta la programación de trabajos, el sistema planifica los recursos en función de las limitaciones definidas en los parámetros del recurso. Puede controlar la capacidad de los recursos mediante la configuración del calendario. El sistema calcula las cargas para los recursos durante el proceso de programación. **Nota**: para las producciones que usan la función de programación de operaciones, puede ejecutar la programación de trabajos después de la programación de operaciones. Si no usa la programación de operaciones, puede ejecutar la programación de trabajo sólo.

## <a name="maximum-capacities-for-resources-per-job-order"></a>Capacidades máximas para los recursos por orden de trabajo
Los recursos se asignan a los trabajos con la programación de trabajos. Pueden establecerse las capacidades máximas para los recursos por pedido de trabajo. Por ejemplo, puede configurar el sistema para programar no más del 50% de la capacidad total para un pedido de producción. Esta configuración proporciona más control sobre la programación de recursos en el nivel de programación de trabajos. De este modo, puede ayudar a prevenir problemas si no hay capacidad suficiente para realizar producciones simultáneas.

## <a name="resource-efficiency"></a>Eficiencia de recursos
La programación de trabajos considera los porcentajes de eficacia especificados para los recursos. Los porcentajes de eficiencia reducen o aumentan el tiempo reservado para el recurso. En consecuencia, el plazo también aumenta o se reduce. Para el cálculo se usa la fórmula siguiente: Tiempo de programación = Tiempo x 100 ÷ Porcentaje de eficiencia En esta fórmula, *Tiempo* incluye el tiempo de ejecución y el tiempo de configuración.



