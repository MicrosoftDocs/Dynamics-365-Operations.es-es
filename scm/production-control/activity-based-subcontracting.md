---
title: "subcontratación Actividad-basada"
description: "Este tema describe, detalladamente cómo usar, actividades subcontratadas en un flujo de producción para la producción ajustada."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267034
ms.assetid: 15c76a51-fa6d-42d2-994a-c67df6bae6a9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8e57c53ca894aa44b71e15c1f66bd7c722ea8a81
ms.lasthandoff: 03/31/2017


---

# <a name="activity-based-subcontracting"></a>subcontratación Actividad-basada

Este tema describe, detalladamente cómo usar, actividades subcontratadas en un flujo de producción para la producción ajustada.

En Microsoft Dynamics 365 para las operaciones, hay dos enfoques para subcontratar: pedidos de producción y producción ajustada. En el método de producción ajustada, el trabajo se de subcontratación de modelo como servicio relacionada con una actividad de un flujo de producción. Se han enviado a un tipo especial de tipo de grupo de costes se denomina que ** contratación de recursos externos ** directa, y los servicios de subcontratación ya no es parte de una lista de materiales (BOM). La contabilidad de costes del trabajo subcontratado está completamente integrada en la solución de la gestión de costes para la producción ajustada.

## <a name="production-flows-that-involve-subcontractors"></a>Flujos de producción que implican subcontratistas
El principio de base de un flujo de producción no cambia cuando se subcontratan las actividades. Los materiales aún fluye entre las ubicaciones, material de proceso de convertido de actividades a los productos, y las actividades de transferencia avanzar el material o productos desde una ubicación a otra. Puede crear ubicaciones y celdas de trabajo como de administrado asignando la cuenta de proveedor a un almacén o recurso de un grupo de recursos.  

Según estas capacidades, la producción ajustada no requiere ninguna características específica para admitir el flujo de materiales y productos. Todas las situaciones que implican posibles proveedores de servicios de producción o de transporte se pueden modelar función de la arquitectura del flujo de producción y las actividades.  

Por ejemplo, un subcontratista se alcanza de un supermercado ubicado en el subcontratista. Cuando las unidades de gestión de material se vacian en el subcontratista, las tarjetas kanban se devuelven a la celda de montaje junto con el envío siguiente. El supermercado en el subcontratista se reabastece. Las transferencias hacia y desde el subcontratista se pueden modelar las actividades de transferencia explícitas para admitir una recogida y un proceso de envío. Si un registro explícito no se requiere para admitir el transporte físico, las actividades de transferencia se pueden omitir.  

Un subcontratista se puede usar para equilibrar la carga la capacidad total del flujo de producción. Por ejemplo, un flujo de producción se de modelo usando las reglas kanban programadas. El planificador utiliza al Consejo de la programación kanban para programar y adeudar el nivel ambas celdas de trabajo a petición. El planificador también controla la programación consolidada del suministro de supermercado en ** programación de la fuente ** la página. Los subcontratistas que se pueden crear en uno o varios flujos de producción, y puede haber las varias reglas kanban que se pueden usar para suministrar el mismo producto en la misma ubicación con distintas actividades. El planificador puede convertir kanban a una regla kanban alternativa para programar de nuevo un kanban que se creó originalmente para la producción interna a un proceso alternativo. De hecho, la naturaleza subcontratada de la celda de trabajo no tiene ningún impacto en el flujo de producción. El mismo principio de ejecución solicita para dos celdas de trabajo internas paralelas o dos celdas subcontratadas.   

Como cualquier otra actividad de un flujo de producción, las actividades subcontratadas pueden consumir y proporcionar material y los productos maestros hace un inventario, no realizados un inventario (trabajo en curso \[\]trabajo en curso), y semiacabado. En todos los casos, los procesos para programar y ejecutar actividades subcontratadas son iguales. Además, éstos procesan los mismos que los procesos para el trabajo interno.

## <a name="purchase-process-for-subcontracted-activities-services"></a>Proceso de compra para las actividades subcontratadas (servicios)
El proceso de compra de las actividades subcontratadas se basa en el flujo de material físico que lo registra el progreso del trabajo kanban, por ejemplo, el inicio o completado. El flujo financiero, por ejemplo, coste de trabajo subcontratado, es un flujo secundario que sigue el flujo físico. Al mismo tiempo, el proceso de compra es un proceso independiente que tiene en cuenta el ajuste manual de los documentos de compra en cada paso. A continuación se indica el proceso de compra de las actividades subcontratadas:

1.  Crear un acuerdo de compra. El acuerdo de compra se crea para el servicio y está conectado a la actividad del flujo de producción.
2.  Cree un pedido de compra. Un pedido de compra de liberación se puede crear para el servicio, en función de los trabajos kanbans programados. Los trabajos para el mismo servicio se pueden agrupar a las líneas de pedido de compra por día, semana o mes. Las líneas de pedido de compra se pueden crear en cualquier momento después de que se creen los trabajos kanban. Las líneas de pedido de compra se pueden crear incluso después el hecho. Esta opción suele seleccionarse si un subcontratista ofrece servicios sin aviso adicional, en función de los kanbans o de las tarjetas kanban que recibe el subcontratista. En este caso, las desviaciones entre el pedido de compra y la factura se pueden minimizadas.
3.  Generar las tarjetas kanban, los materiales, y una lista de selección para enviarlo al subcontratista para preparar el procesamiento. Basado en el modelado detallado del flujo de producción, la preparación se realiza en el tablero kanban para las actividades de proceso mediante la lista de selección y la función de preparación. O bien, la preparación se realiza en el tablero kanban para trabajos de la transferencia utilizando la lista de selección y el inicio o la finalización. Para el material realizado un inventario, ambos procesos se admiten por un proceso de la WMS- de recogida y envío. Un conocimiento de embarque se puede crear a petición.
4.  Generar las unidades de gestión de material y las tarjetas kanban de kanban. Tras el procesamiento, las tarjetas se devuelven del subcontratista. Normalmente, las tarjetas incluyen una nota de entrega que especifica el material físico se ha enviado. Una referencia a los servicios proporcionados no se requiere. La llegada de material o de productos en el cliente se registra en el tablero kanban, en función de las tarjetas kanban. (Los el tablero kanban de actividades de proceso o el tablero kanban para trabajos de transferencia, en función de las actividades modeladas.).
5.  Crear un recibo aviso. El asesor recepción se puede usar para reemplazar un documento de albarán para los servicios recibidos. Los advisories de recepción se pueden generarse en función de los trabajos kanban completado para la actividad de subcontratación para un período seleccionado. Para cada recepción de trabajo, los advisories se crean para la línea de pedido de compra relacionadas. El asesor recepción se puede imprimir y enviar al subcontratista como confirmación del recibo.
6.  Generar una factura.

Los finalizará el proceso cuando el subcontratista se factura por un período. La conciliación de facturas se realiza con los advisories de recepción se han creado. Dado que los advisories de recepción representan la recepción física precisa material, se simplifica la triple conciliación.

## <a name="configuring-activities-for-subcontracting"></a>Actividades de configuración para subcontratar
Las secciones siguientes describen cómo configurar actividades para subcontratar.

### <a name="subcontracted-services"></a>Servicios subcontratados

El artículo del pago que se usa en la subcontratación actividad- basada debe ser un producto que tiene las siguientes propiedades:

-   ** Tipo de producto: ** Servicio
-   ** Grupo de modelos de inventario: ** No se mantiene en existencias

Este requisito aplica el uso de FIFO, modelo de inventario de (FIFO). ** Nota: ** El cálculo del coste de los productos que requiere el coste estándar de servicio se haya definido. Un acuerdo de compra con el proveedor es necesario. Si no, el servicio no puede usarse para la subcontratación actividad- basada.

### <a name="subcontracted-process-activities"></a>Actividades de proceso subcontratadas

Para configurar una actividad de proceso como actividad subcontratada, siga estos pasos.

1.  Configurar una celda de trabajo subcontratada. Para configurar una celda de trabajo subcontratado como, debe crear un recurso de proveedor ** ** la escribe y asociar con la celda de trabajo (grupo de recursos). Una categoría de coste del tiempo de ejecución ** contratación de recursos externos directa ** de tipo de grupo de costes se debe asignar a la celda de trabajo. Las categorías de coste para la configuración y la cantidad no son necesarias.
2.  Una vez que una actividad de proceso se cree y esté relacionado con una celda de trabajo subcontratada, debe configurar un servicio para la actividad antes de que la versión del flujo de producción se pueda activar. Completa este paso en ** actividad ** ** los detalles ** página. Para las actividades que están asociados a una celda de trabajo, subcontratada ** el servicio denomina ** se muestra la ficha desplegable. En esta ficha desplegable, agregue un servicio predeterminado que sea válido para todos los artículos de salida. Si los artículos específicos de salida requieren diferentes servicios o diferentes parámetros de cálculo de servicio (por ejemplo, otra proporción de servicio), puede agregarle otros servicios a la actividad.

## <a name="subcontracted-transfer-activities"></a>Actividades de transferencia subcontratadas
Una actividad de transferencia se configure como actividad subcontratada, en función fletado ** por ** del valor de la actividad de transferencia. Están disponibles las siguientes opciones:

-   ** Subcontratan al expedidor – ** la actividad si la transferencia desde el almacén se gestiona a través de un proveedor (según defina una propiedad del almacén). Todos los acuerdos de compra seleccionado para los servicios deben tener el mismo identificador de proveedor que el almacén.
-   ** Subcontratan el destinatario – ** la actividad si la transferencia a almacén se gestiona a través de un proveedor (según defina una propiedad del almacén). Todos los acuerdos de compra seleccionado para los servicios deben tener el mismo identificador de proveedor que el almacén.
-   ** El operador – ** la actividad se subcontrata ningún proveedor que proporcione el servicio. Para ser válido, un operador debe crearse para la gestión de almacenes y debe tener una cuenta de proveedor asignada.

Con respecto a actividades de proceso, debe configurar un servicio predeterminado para las actividades subcontratadas de transferencia en ** las condiciones de servicio ** la ficha desplegable ** actividad ** ** de detalles ** página.

## <a name="service-quantity-calculation"></a>Cálculo de cantidad de servicio
El proceso de compra del conjunto se basa en una referencia de artículo para un servicio. Esta referencia del artículo se mide en una unidad de medida de un servicio. Miden servicios generalmente en el número de unidades servicios () o a tiempo. Para calcular la cantidad de servicio, en función de la finalización registrada de trabajos kanban, puede usar los métodos siguientes:

-   ** El cálculo que se basa en el número de trabajos ** un trabajo kanban es igual a unidades de *n* de servicio, independientemente de la cantidad de producto que se proporciona. En lean manufacturing, un trabajo corresponde a una unidad de gestión de material. Este método de cálculo se aplica a todos los servicios que tienen un precio fijo por unidad de gestión de material. Por lo tanto, este método aplica normalmente en las actividades de transferencia. Sin embargo, puede aplicar para procesar las actividades que procesan las unidades de gestión de material totalidad.
-   ** El cálculo que se basa en la cantidad de producto – ** la cantidad de servicio se encuentra en relación con la cantidad de producto se programa/que se proporciona. Al calcular la cantidad de producto especificada, las cantidades con errores pueden incluir o ser excluidas. Este método de cálculo se aplica a todos los casos en los que el precio de servicio por unidad de producto procesado se acordó.
-   ** El cálculo que se basa en el tiempo de actividad ** – los tiempos de actividad teóricos, se calcula a partir del tiempo de procesamiento de la actividad, la cantidad procesada total, y del coeficiente de capacidad de proceso del producto procesado. Este método de cálculo se aplica a los servicios que se pagan por horas y tienen una desviación a tiempo por producto procesado.

## <a name="cost-accounting-of-subcontracted-services"></a>Contabilidad de costes de servicios subcontratados
Cuando una recepción asesor o un albarán del proveedor en un pedido de compra creado para un flujo de producción (es decir un pedido de compra que se ha generado en función de los trabajos kanban para las actividades subcontratadas) se envía, el valor del recibo se considera en las cuentas de trabajo en curso del flujo de producción. Las desviaciones de facturas también se consideran al flujo de producción. Una categoría de coste para el trabajo subcontratado se han especificado. Este seguimiento transparente habilitado de la categoría de coste del valor del trabajo subcontratado que se asigna a trabajo en curso y se consume por período.  

La contabilización previa de los costes de fabricación ajustada al final de un período de la gestión de costes calcular las desviaciones reales de los productos generados en el flujo de producción durante el período de gestión de costes.

## <a name="modeling-transfers-as-subcontracted-activities"></a>Modelos de transferencias las actividades subcontratadas
Las entidades consideran el transporte no productivas y utilizan a menudo que no agrega ningún valor. No obstante, si el coste de la subcontratación se compara con el coste de producción interna, el coste de actividades de transporte adicionales debe ser considerados. Un flujo de producción que abarca distintas ubicaciones y requiere que los servicios de transporte debe crear un modelo del coste de transporte como parte del coste para proporcionar los productos al cliente. 

subcontratación Actividad- basada en lean manufacturing permite integrar los transportistas y los proveedores de transporte que mueven materiales y productos entre ubicaciones de un flujo de producción. Modelando una actividad de transferencia, puede asignar un operador o un proveedor. Las actividades de transferencia/trabajo se basan en un servicio y un acuerdo de compra, y puede crear pedidos de compra y advisories de recepción, en función de los trabajos reales de la transferencia. Esta funcionalidad es el mismo que la funcionalidad para las actividades subcontratadas de proceso.  

Por lo tanto, Dynamics 365 para las operaciones ahora admite el cálculo de L que incluye servicios de transporte, la creación de pedidos de compra relacionados, integrado el registro de recepción, y la integración de los costes del servicio de transporte en la gestión de costes del flujo de producción.


