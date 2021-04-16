---
title: Contabilización previa de los costes
description: Este tema presenta el concepto de contabilización previa de los costes que se utiliza para lean manufacturing.
author: cvocph
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeanCosting, LeanCostingTimeBucket
audience: Application User
ms.reviewer: kamaybac
ms.custom: 272063
ms.assetid: 62a2a7da-ff79-49bf-a6e8-29460ba5252f
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: ca6ca1ce53e81ac7c64489f505decd84a9534f74
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834346"
---
# <a name="backflush-costing"></a>Contabilización previa de los costes

[!include [banner](../includes/banner.md)]

Este tema presenta el concepto de contabilización previa de los costes que se utiliza para lean manufacturing. 

El coste de la producción ajustada permite al flujo de producción para utilizar el método de acumulación de costes que se conoce como contabilización previa de los costes. En el método de la contabilización previa de los costes, el material directo que se consume se acumula en la cuenta de costes de (WIP) del trabajo en curso del flujo de producción. Se usa el grupo de modelos de inventario de costes estándar. Los productos recibidos del flujo de producción se deducen del trabajo en curso en su coste estándar. La principal diferencia entre la contabilización previa de los costes y el coste estándar es que, para la contabilización previa de los costes, las desviaciones no se calculan por kanban o el producto terminado. En su lugar, las desviaciones se calculan por el flujo de producción durante un período. Este método presenta un concepto verdaderamente lean para notificar el consumo de materiales. Las cantidades seleccionadas dedicadas de material no se notifican a un kanban o a un pedido de producción. En su lugar, los lotes completos o las unidades de manipulación se almacenan provisionalmente en el flujo de producción. Después de que los lotes o las unidades de manipulación se registren como vacíos, se declaran consumidos. Se puede usar el consumo avanzado, según la [configuración del flujo de producción](../production-control/lean-manufacturing-modeling-lean-organization.md). Antes de que el consumo avanzado se pueda usar, las organizaciones deben permitirse hacer desaparecer material en el trabajo en curso del flujo de producción. La contabilización previa de los costes periódica determina el valor efectivo del trabajo en curso al final del período. Esta determinación se basa en el estado del kanban, las unidades de manipulación y el trabajo kanban. Las desviaciones entre los valores reales y los valores reales del trabajo en curso por grupo de costes y artículos se tienen en cuenta y se muestran como desviaciones.

## <a name="configuring-backflush-costing"></a>Configuración de la contabilización previa de los costes
Para habilitar la gestión de costes, debe completar la configuración siguiente:

-   **La configuración de las cuentas de trabajo en curso para el grupo de producción y el flujo de producción.** Las cuentas de trabajo en curso para el flujo de producción se especifican en el grupo de producción. El flujo de producción de la contabilización previa de los costes calcula las desviaciones como la diferencia en el valor de trabajo en curso antes y después de la ejecución de la contabilización previa de los costes para cada flujo de producción. Por lo tanto, se recomienda que cree una cuenta de trabajo en curso para cada flujo de producción.
-   **Asigne una categoría de coste al grupo de recursos.** Debe asignar una categoría de coste para la categoría de tiempo de ejecución de la celda de trabajo. Para determinar las desviaciones por actividad, debe crear una categoría de coste para cada celda de trabajo. Las categorías de coste para la configuración y la cantidad no se tienen en consideración en la gestión de costes para lean manufacturing. Las cuentas de trabajo en curso por grupo de recursos se ignorarán en la contabilización previa de los costes. Para las actividades subcontratadas, no se requiere ninguna categoría de coste. El grupo de costes asignado al servicio activo en su lugar.
-   **Asignar grupos de costes.** Para habilitar la segmentación de la contribución de costes de un flujo de producción, debe asignar grupos de costes por tipo de grupo de costes:
    -   **Grupo de costes de material directo**: el material directo requiere un grupo de costes que identifique la categoría de material para la gestión de costes. Este grupo de costes permite una vista agregada de coste, de trabajo en curso, y de desviaciones en función del material directo.
    -   **Grupo de costes de fabricación directa**: el grupo de costes de fabricación directa capta la contribución de coste directa de los recursos operativos en el flujo de producción. Este grupo de costes permite una vista agregada de coste, de trabajo en curso, y de desviaciones en función del coste de fabricación directa.
    -   **Grupo de costes indirecto**: el grupo de costes indirecto se requiere para calcular la contribución del coste indirecto el flujo de producción. Este grupo de costes permite obtener una vista agregada del coste, el trabajo en curso, y las desviaciones en función del coste indirecto.
    -   **Grupo de costes de externalización directa** - El grupo de costes para los servicios habilita una vista agregada de coste asignado y el trabajo en curso, y determina las variaciones de coste de los servicios subcontratados.
    -   **Grupo de costes de un producto terminado**: los productos terminados requieren un grupo de costes que identifique la categoría de gestión de costes. Este grupo de costes permite una vista agregada del coste, el trabajo en curso, y las desviaciones en función de la categoría de producto. El coste estándar para los productos se calcula mediante el cálculo de coste que se basa en la lista de materiales (BOM), y el flujo de producción y las reglas kanban o la ruta.

### <a name="costing-sheet"></a>Hoja de gestión de costes

La hoja de gestión de costes da forma a la estructura de costes para la empresa y se crea en función de los grupos de coste para clasificar el coste. La hoja de gestión de costes tiene varios formularios. Muestra la información de coste según la estructura diseñada en ella. En la hoja de gestión de costes, también puede definir la fórmula utilizada para calcular el coste indirecto. La fórmula de cálculo se puede basar en cantidades, el peso, el volumen, o el valor.

-   **Definición de una versión de gestión de costes** En la versión de gestión de costes, la empresa define cómo el coste debe mantenerse. Además, puede contener un conjunto de registros de costes estándar o de costes planificados, según en el tipo de gestión de costes asignado a la versión de gestión de costes. La versión de gestión de costes que se utiliza gestionar los costes de lean manufacturing se debe basar en el coste estándar.
-   **Asigne un grupo de modelos de inventario a los productos liberados.** Se debe asignar a todos los productos relacionados con el flujo de producción un grupo de modelos de inventario que use el grupo de modelos de inventario **Coste estándar** . El coste estándar se mantiene por sitio y fecha de activación. Para los productos maestros, el grupo de modelos de inventario se puede seleccionar si el coste se mantiene por variante o por producto maestro.
-   **Por definición, los servicios subcontratados son servicios que no están inventariados.** Las actividades subcontratadas no tienen ningún grupo de modelos de inventario. Para calcular una actividad subcontratada correctamente, debe asegurarse de que la actividad de servicio pertenece a un grupo de modelos de inventario en la que la directiva de inventario se establece en **artículo mantenido en existencias = falso**.

Para los productos resultantes, el cálculo de coste que se basa en el flujo de producción requiere que se mantenga un coste estándar para los servicios que están relacionados con las actividades subcontratadas. El grupo de costes que se asigna a los servicios se usa para determinar las variaciones de coste de la actividad subcontratada.

## <a name="cost-calculation-for-lean-manufacturing"></a>Cálculo de coste de lean manufacturing
Para los productos que se proporcionan fuera de un flujo de producción, el cálculo de L. MAT se debe basar en una versión de ruta o un flujo de producción. El cálculo de BOM calcula el coste de un producto y el desglose relacionado con los recursos y el material que se requieren para crear el producto. La deducción de la cuenta de trabajo en curso para el flujo de producción se realiza mediante el desglose de un producto por artículos y por grupo de costes.

### <a name="calculation-that-is-based-on-the-production-flow"></a>Cálculo que se basa el flujo de producción

La lean manufacturing para Dynamics 365 Supply Chain Management es independiente de rutas. El cálculo del coste para los productos que se proporcionan de un flujo de producción se puede basar en el flujo de producción en sí. Antes de realizar el cálculo, se debe crear una regla kanban que proporcione el producto fuera del flujo de producción. Si un producto se puede suministrar desde varios flujos de producción en el mismo sitio en la fecha de cálculo, puede seleccionar el flujo de producción para el cálculo de L. MAT. En la página **Flujo de producción predeterminado** , puede configurar un flujo de producción predeterminado para cada artículo. Si varias reglas kanban existen para el mismo producto en el mismo flujo de producción que está activo en la fecha de cálculo, el cálculo selecciona la primera regla kanban que está activa para el cálculo.

### <a name="calculation-that-is-based-on-the-route"></a>Cálculo basado en la ruta

El cálculo que se basa en una ruta es tan válido como el cálculo que se basa en un flujo de producción. Sin embargo, el cálculo que se basa en una ruta no usa la gestión de costes para la funcionalidad de lean manufacturing. La ruta debe usar requisitos de recurso para los grupos de recursos. Para evitar las desviaciones sistemáticas, debe usar también las mismas celdas de trabajo, o al menos las mismas categorías de coste. Una vez más debe evitar las categorías de coste para la configuración y la cantidad. No ayudan a calcular el coste en un desglose más específico que el flujo invertido del coste de lean manufacturing. Para determinar la opción (flujo de producción o ruta) que debe usar para calcular el coste, tenga en cuenta los resultados del desglose de costes. La versión más cercana a la realidad y genera menos desviaciones en general es la mejor opción. En un entorno de lean manufacturing donde un producto se proporciona mediante un solo flujo de producción y una sola regla kanban, el cálculo que se basa en el flujo de producción es probablemente más preciso. Para un producto que se puede suministrar mediante lean manufacturing y pedidos de producción en el mismo sitio, o que puede tener varios flujos de producción o varias reglas kanban en el mismo flujo, un cálculo puede ser más preciso si se basa en una versión de ruta que se crea específicamente para el cálculo de costes, no para la producción. El cálculo del flujo de producción se debe usar para calcular los productos en los que hay una subcontratación. Los modelos de coste para subcontratar mediante pedidos de producción y subcontratar en lean manufacturing usan dos enfoques diferentes. El lean manufacturing presenta a un nuevo tipo de grupo de costes, **Subcontratación directa**, para calcular los servicios subcontratados.

## <a name="material-consumption"></a>Lista de selección
Cuando el material se consume de inventario a trabajo en curso, el coste de material se agrega al trabajo en curso a su coste estándar real para un grupo de costes. Esta operación se produce en las condiciones siguientes:

-   Las emisiones de kanban se envían para las líneas de picking de kanban que actualizan el inventario.
-   Se completan trabajos de transferencia que actualizan el inventario en la selección pero no la recepción (transferencia de materiales del inventario al trabajo en curso).

## <a name="receiving-products-from-the-production-flow"></a>Recibir productos del flujo de producción
Los productos se reciben del flujo de producción bajo las siguientes condiciones:

-   Se completan los trabajos de proceso que tienen **Actualizar inventario al recibir** definido en **Sí**.
-   Se completan los trabajos de transferencia que actualizan el inventario en recepción, pero que tienen la **actualización del inventario al seleccionar** establecida en **No** (transferencia de trabajo en curso al inventario). Esta opción permite recibir cualquier producto fuera de un flujo de producción al margen de la lista de materiales y distribuir la configuración. El proceso solo sigue los flujos físicos. Esta opción resulta especialmente adecuada para recibir productos derivados, productos conjuntos, o residuos fuera de un flujo de producción, y para corregir el saldo de coste del trabajo en curso del flujo de producción en consecuencia.

Los productos recibidos del flujo de producción se deducen del trabajo en curso.

## <a name="products-in-wip"></a>Productos en el trabajo en curso
El modelo de trabajo en curso de lean manufacturing permite usar el estado de unidad de manipulación de kanban para la gestión de materiales, los productos semiterminados, y los productos terminados que forman parte del trabajo en curso.

-   **Asignado** - El kanban puede haber consumido el material que se considera en el trabajo en curso.
-   **Recibido** - Si el kanban hace referencia a una última actividad en que la **actualización del inventario en recepción** está establecida en **No**, representa una unidad de manipulación completa de un producto o de un producto semiterminado que no se registra en el inventario.

Tenga en cuenta que el trabajo en curso no estará visible en las visiones generales del inventario disponible. Sin embargo, se puede ver en visiones generales sobre la cantidad kanban.

## <a name="consuming-products-in-wip"></a>Consumir productos del trabajo en curso
Los productos del trabajo en curso se consumen cuando se vacían las unidades de manipulación de kanban correspondientes. Una señal de kanban vacío no genera una transacción de gestión de costes activa pero se hará efectiva cuando se ejecute la contabilización previa de los costes siguiente. Las unidades de manipulación de kanban vacías ya no se consideran como disponibles y se calculan como consumidas en el período.

### <a name="automatic-empty-registration"></a>Registro vacío automático

Los kanbans programados o de evento se pueden establecer en un registro automático vacío en la regla kanban:

-   **Cuando se reciben las unidades de manipulación de material** - De forma predeterminada, para los kanbans programados, los materiales se declaran consumidos cuando el último trabajo del kanban se ha completado. Para kanbans de cantidad fija, esta opción se recomienda solo para los kanbans de hueco único, ya que devuelve la tarjeta al origen de la demanda siempre que un kanban se reciba en el destino final.
-   **Cuando se registra el requisito de origen** - Esta opción solo está disponible para los kanbans de evento y es la opción predeterminada para ellos. En relación con el trabajo en curso, esta opción es útil para conservar el trabajo en curso limpio, ya que los kanbans para componentes del trabajo en curso se vacían automáticamente, y por tanto se consumen del trabajo en curso, cuando se prepara el kanban principal.

En conclusión, las unidades de manipulación de material de kanban se pueden asignar (= en proceso), recibir (=full), o ser vaciadas. No existe un vaciado parcial. Por lo tanto, para habilitar el registro preciso de consumo, es importante que limite las cantidades de producto de un kanban de modo que sean menores que el consumo por período. Los productos que se trasladan a la planta en grandes lotes que cubren días o semanas de demanda no se deben consumir en el trabajo en curso. En su lugar, estos productos deben mantenerse en el inventario.

## <a name="backflush-costing"></a>Contabilización previa de los costes
Debe ejecutar una contabilización previa de los costes para valorar el trabajo en curso periódicamente y generar un estado de final del período que calcula las desviaciones de material, trabajo, y costes indirectos. Las desviaciones calculadas se registran en las cuentas de desviación. En el proceso de la contabilización previa de los costes, todos los flujos de producción de la entidad jurídica se usan en la misma ejecución por lotes. Cuando la contabilización previa de los costes se ejecuta en un lote, el procesamiento puede ser de varios subprocesos por flujo de producción. El período del flujo invertido se define con una fecha de finalización. No puede enviar nuevas transacciones a una fecha cuando se ha ejecutado un cálculo de contabilización previa de los costes. Nunca debe ejecutar la contabilización previa de los costes para la fecha actual antes de que el día haya acabado realmente. La contabilización previa de los costes realiza los pasos siguientes.

1.  Determina las cantidades no utilizadas en el flujo de producción en la fecha final del período. Una vez que se haya ejecutado la contabilización previa de los costes, podrá ver las cantidades no utilizadas en la fecha de la ejecución de la gestión de costes en el cuadro de diálogo **Cantidades sin usar** .
2.  Calcule el uso neto realizado del flujo de producción durante el período.
3.  Borre el trabajo en curso del consumo de recursos y productos realizados.
4.  Calcule las desviaciones de producción a coste estándar para el período. **Para los componentes consumidos para el período:**
    -   Actualice financieramente las cantidades netas realizadas de material que el flujo de producción consumió durante el período. El sistema procesa con salida en orden de entrada (FIFO) en las transacciones de inventario individuales para actualizar financieramente las transacciones actualizadas físicamente para el flujo de producción, hasta que se alcancen las cantidades realizadas netas para el período.
    -   Las transacciones se dividen financieramente para asignar las cantidades exactas consumidas.
    -   Las cantidades no utilizadas en el trabajo en curso del flujo de producción permanecen en el estado actualizado físicamente.

    **Para las cantidades de producción del período completadas:**
    -   Actualice financieramente las transacciones de inventario para las cantidades completadas para el período.

    **Para el coste de conversión:**
    -   Las transacciones de coste de conversión aplicadas (transacciones de ruta) que se registraron para el período se actualizan financieramente.
    -   Todo coste de fabricación directa se actualiza financieramente. Todos los trabajos del proceso de kanban que se completan durante el período se acumulan.
    -   Todo el coste indirecto calculado para los materiales consumidos dentro del período se calcula y se deduce del trabajo en curso. El coste indirecto restante se registra como desviación.

5.  Calcule las desviaciones de producción a coste estándar. La desviación se calcula por grupo de costes.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]