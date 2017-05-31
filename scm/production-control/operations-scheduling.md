---
title: "Programación de operaciones"
description: "Este tema proporciona información acerca de la programación de las operaciones. Puede usar la programación de operaciones para proporcionar una estimación general del tiempo extra del proceso de producción."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdSchedule
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 198073
ms.assetid: 12c28b11-80aa-4668-b15b-724cb24890bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: eb9a9aa3fa0d1928101204e7c902a6777bbbef5b
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="operations-scheduling"></a>Programación de operaciones

[!include[banner](../includes/banner.md)]


Este tema proporciona información acerca de la programación de las operaciones. Puede usar la programación de operaciones para proporcionar una estimación general del tiempo extra del proceso de producción.

Puede programar la producción en el nivel de operación y en el nivel de trabajo. A diferencia de la programación de trabajos, la programación de operaciones no expande las operaciones de la ruta de producción en trabajos. Si desea incluir más información en relación con la programación, como información acerca de la capacidad actual, puede ejecutar la programación de trabajos tras ejecutar la programación de operaciones. También puede ejecutar solo una programación de trabajos. La programación de trabajos se usa normalmente para programar trabajos individuales en la planta para un período de tiempo inmediato o a corto plazo.

## <a name="components-of-operations-scheduling"></a>Componentes de la programación de operaciones
Los componentes principales de la programación de operaciones son la dirección de la programación, la capacidad de los recursos y la optimización de los materiales. Al usar la programación de operaciones, puede alcanzar los siguientes objetivos:

-   Controlar el método de planificación adelantando o posponiendo la programación a partir de una fecha determinada.
-   Optimizar el uso de recursos programando las producciones en función de la capacidad de los recursos. Este método también ayuda a identificar cuándo deben usarse los recursos alternativos.
-   Optimizar el uso de los materiales programando las producciones en función de la disponibilidad de los materiales necesarios.
-   Programar y sincronizar las producciones de referencia. Las fechas de las producciones de referencia se ajustan cuando se cambia la programación del pedido de producción.

Debe estimar el coste de un pedido de producción antes de poder ejecutar la programación de operaciones. Si no ha llevado a cabo una estimación, esta se realiza automáticamente antes de empezar con el proceso de programación de las operaciones. En una programación de operaciones se especifica la siguiente información:

-   El producto que se planifica para la producción
-   La configuración del producto
-   Las cantidades involucradas en la producción
-   Las fechas en las que comenzará y finalizará la producción
-   Las reservas de capacidad para los recursos que realizan las actividades de producción

Se establece el tiempo de preparación, el tiempo de proceso y el tiempo de ejecución para las operaciones de producción. Tras ejecutar la programación de operaciones, el estado del pedido de producción será **Programado** y todas las operaciones se programarán en el orden que ha especificado la ruta de producción. Sin embargo, solo se tiene en cuenta la duración de la operación. Las horas de inicio y finalización no se programan.

## <a name="scheduling-direction-and-date"></a>Dirección y fecha de programación
La dirección de programación es indispensable en el proceso de programación. La producción se puede programar hacia adelante o hacia atrás a partir de cualquier fecha, en función de los requisitos de tiempo y programación.

-   **A partir de la fecha de programación**: puede programar la producción para que se inicie lo antes posible. La producción puede iniciarse hoy, mañana o en cualquier fecha en el futuro. La producción está programada hacia adelante en el tiempo hasta la fecha final más próxima posible.
-   **Regresivo a partir de la fecha de programación**: puede programar la producción para que se inicie lo más tarde posible. La programación regresiva se basa en la fecha en la que se debe terminar la producción. La programación cuenta hacia atrás a partir de esa fecha hasta la última fecha posible en que se puede iniciar la producción y aún completarse a tiempo.

## <a name="resource-scheduling"></a>Programación de recursos
Cuando se ejecuta una programación de operaciones, cada operación de la ruta de producción está programada para el recurso especificado para la operación. Además, la duración de cada operación se especifica en la ruta de producción. Si se ha especificado un grupo de recursos para una operación, la programación reserva capacidad en el grupo. Sin embargo, a diferencia de la programación de trabajos, la programación de operaciones no selecciona los recursos específicos en el grupo. Si trabaja con capacidad limitada, la programación depende de la disponibilidad de los recursos necesarios para poder completar la producción. La programación de operaciones sigue la secuencia de operaciones que se especifica en la ruta de producción. La programación reserva capacidad en los grupos de recursos en función de los tiempos de operación que están definidos en la ruta de producción. La suma de la capacidad disponible en los recursos implicados determina la capacidad del grupo de recursos. Las reservas de capacidad que ya existen para los recursos se consideran capacidad no disponible. Si no hay suficiente capacidad disponible para la producción, los pedidos de producción pueden retrasarse e incluso detenerse. También puede especificar la eficacia que espera de los recursos implicados en la producción. Podrá especificar la eficacia como un porcentaje en el recurso. El porcentaje de eficacia ajusta el rendimiento del recurso. Dicho ajuste afecta al tiempo reservado para el recurso. Los plazos para las operaciones que usan el recurso también se ajustan según corresponda.

## <a name="operations-scheduling-and-master-planning"></a>Programación de operaciones y planificación maestra
La programación de operaciones también genera la programación maestra y determina los cálculos de los requisitos materiales. La programación de operaciones tiene en cuenta la siguiente información:

-   **Producciones registradas**: productos planificados, liberados o iniciados
-   **Disponibilidad de material**: inventario, subproducciones, distribuidores y proveedores
-   **Disponibilidad de capacidad**: recursos necesarios para la producción

## <a name="cancellations"></a>Cancelaciones
Cuando está utilizando la programación de operaciones, puede cancelar partes concretas de la ruta. Dichas partes incluyen el tiempo en cola, el tiempo de preparación, el tiempo de proceso, el tiempo de superposición y los tiempos de transporte.

## <a name="finite-materials"></a>Materiales finitos
Si trabaja con materiales finitos, la programación también depende de la disponibilidad de los materiales que se requieren para la producción. Si no hay componentes disponibles suficientes para la producción, se puede retrasar. Puede basar la programación en el uso de materiales mediante la especificación de los materiales que deben estar disponibles para la producción. Cuando optimice tanto la capacidad de recursos y la disponibilidad de materiales, la producción se calcula en función de estas restricciones. Un pedido de producción no se puede programar para que se inicie hasta que la capacidad y los materiales no estén disponibles a la vez y en las cantidades necesarias.

<a name="see-also"></a>Consulte también
--------

[Opciones de programación de la operación](operation-scheduling-options.md)




