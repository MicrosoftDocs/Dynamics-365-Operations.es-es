---
title: Subcontratación basada en actividad
description: Este tema describe detalladamente cómo usar actividades subcontratadas en un flujo de producción para la lean manufacturing.
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 267034
ms.assetid: 15c76a51-fa6d-42d2-994a-c67df6bae6a9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35ec47a13d9119c755702e019d09c76e1281b4a6
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250240"
---
# <a name="activity-based-subcontracting"></a>Subcontratación basada en actividad

[!include [banner](../includes/banner.md)]

Este tema describe detalladamente cómo usar actividades subcontratadas en un flujo de producción para la lean manufacturing.

En Microsoft Dynamics 365 Supply Chain Management hay dos enfoques para subcontratar: pedidos de producción y lean manufacturing. En el método de lean manufacturing, el trabajo de subcontratación se modela como servicio relacionado con una actividad de un flujo de producción. Se han introducido un tipo especial de tipo de grupo de costes que se denomina **Subcontratación directa** y los servicios de subcontratación ya no son parte de una lista de materiales (L. MAT.). La contabilidad de costes del trabajo subcontratado está completamente integrada en la solución de la gestión de costes de la lean manufacturing.

## <a name="production-flows-that-involve-subcontractors"></a>Flujos de producción que implican subcontratistas
El principio básico de un flujo de producción no cambia cuando se subcontratan actividades. El material aún fluye entre las ubicaciones, las actividades de proceso convierten el material en productos y las actividades de transferencia mueven el material o los productos de una ubicación a otra. Puede modelar ubicaciones y celdas de trabajo como administradas por el proveedor asignando la cuenta de proveedor a un almacén o un recurso de un grupo de recursos.  

Según estas capacidades, la lean manufacturing no requiere ninguna característica específica para admitir el flujo de materiales y productos. Todas las situaciones que implican a los proveedores, como proveedores de servicios de producción o de transporte, se pueden modelar en función de la arquitectura del flujo de producción y las actividades.  

Por ejemplo, un subcontratista trabaja en un supermercado ubicado en el subcontratista. Cuando las unidades de gestión de material se vacían en el subcontratista, las tarjetas kanban se devuelven a la celda de montaje junto con el envío siguiente. El supermercado en el subcontratista se reabastece. Las transferencias hacia y desde el subcontratista se pueden modelar como actividades de transferencia explícitas para admitir un proceso de picking y de envío. Si un registro explícito no se requiere para admitir el transporte físico, las actividades de transferencia se pueden omitir.  

Un subcontratista se puede usar para equilibrar la carga de la capacidad total del flujo de producción. Por ejemplo, un flujo de producción se modela usando las reglas kanban programadas. El planificador utiliza el panel de programación kanban para programar y equilibrar la carga de ambas celdas de trabajo a petición. El planificador también controla la programación consolidada del suministro del supermercado en la página **Programación de suministros**. Se pueden crear varios subcontratistas en uno o varios flujos de producción, y puede haber varias reglas kanban que se pueden usar para suministrar el mismo producto en la misma ubicación con distintas actividades. El planificador puede convertir kanbans a una regla kanban alternativa para programar de nuevo un kanban que se creó originalmente para la producción interna en un proceso alternativo. De hecho, la naturaleza subcontratada de la celda de trabajo no tiene ningún impacto sobre el flujo de producción. El mismo principio de trabajo se aplica a dos celdas de trabajo internas paralelas o a dos celdas subcontratadas.   

Como cualquier otra actividad de un flujo de producción, las actividades subcontratadas pueden consumir y proporcionar materiales y productos inventariados, no inventariados (trabajo en curso \[WIP\]) y semiacabados. En todos los casos, los procesos para programar y ejecutar actividades subcontratadas son iguales. Además, estos procesos son iguales que los procesos del trabajo interno.

## <a name="purchase-process-for-subcontracted-activities-services"></a>Proceso de compra de actividades subcontratadas (servicios)
El proceso de compra de las actividades subcontratadas se basa en el flujo de material físico registrado por el progreso de trabajo kanban, por ejemplo, iniciado o completado. El flujo financiero, por ejemplo, coste de trabajo subcontratado es un flujo secundario que sigue al flujo físico. Al mismo tiempo, el proceso de compra es un proceso independiente que permite el ajuste manual de los documentos de compra en cada paso. Este es el proceso de compra de actividades subcontratadas:

1.  Creación de un acuerdo de compra. El acuerdo de compra se crea para el servicio y se conecta a la actividad del flujo de producción.
2.  Cree un pedido de compra. Un pedido de compra parcial se puede crear para el servicio, en función de los trabajos kanbans programados. Los trabajos para el mismo servicio se pueden agrupar en líneas de pedido de compra por día, semana o mes. Las líneas de pedido de compra se pueden crear en cualquier momento después de que se creen los trabajos kanban. Las líneas de pedido de compra se pueden crear incluso después del hecho. Esta opción suele seleccionarse si un subcontratista ofrece servicios sin aviso adicional, basados en los kanbans o las tarjetas kanban que recibe el subcontratista. En este caso, las desviaciones entre el pedido de compra y la factura se pueden minimizar.
3.  Genere las tarjetas kanban, los materiales y una lista de selección para enviarlos al subcontratista para preparar el procesamiento. Basándose en el modelado detallado del flujo de producción, la preparación se realiza en el tablero kanban de actividades de proceso mediante la lista de selección y la función de preparación. O bien, la preparación se realiza en el tablero kanban de trabajos de la transferencia utilizando la lista de selección y el inicio o la finalización. En caso de material inventariado, , ambos procesos son admitidos por un proceso de picking WMS o de envío. Un conocimiento de embarque se puede crear a petición.
4.  Generación de unidades de gestión de material y tarjetas kanban. Tras el procesamiento, el subcontratista devuelve las tarjetas. Normalmente, las tarjetas incluyen una nota de entrega que especifica el material físico enviado. Una referencia a los servicios proporcionados no se requiere. La llegada de material o de productos a las instalaciones del cliente se registra en el tablero kanban, en función de las tarjetas kanban. (Se emplea el tablero kanban de actividades de proceso o el tablero kanban de trabajos de transferencia, en función de las actividades modeladas.).
5.  Creación de un aviso de recepción. El aviso de recepción se puede usar para reemplazar un documento de albarán de los servicios recibidos. Los avisos de recepción se pueden generar basándose en los trabajos kanban completados para la actividad de subcontratación durante un período seleccionado. Por cada trabajo recibido se pueden crear avisos para la línea de pedido de compra relacionada. El aviso de recepción se puede imprimir y enviar al subcontratista como confirmación de recepción.
6.  Generación de una factura.

El proceso finalizará cuando se factura al subcontratista por un período. La conciliación de facturas se realiza con los avisos de recepción creados. Dado que los avisos de recepción representan la recepción física precisa del material, se simplifica la triple conciliación.

## <a name="configuring-activities-for-subcontracting"></a>Configuración de actividades para la subcontratación
Las secciones siguientes describen cómo configurar actividades para subcontratar.

### <a name="subcontracted-services"></a>Servicios subcontratados

El artículo del pago que se usa en la subcontratación basada en actividades debe ser un producto que tenga las siguientes propiedades:

-   **Tipo de producto:** servicio
-   **Grupo de modelo de inventario:** no está en existencias

Este requisito fuerza el uso del modelo de inventario de salida en el orden de entrada (FIFO). **Nota:** el cálculo del coste de los productos requiere que se defina el coste estándar del servicio. Un acuerdo de compra con el proveedor es necesario. En caso contrario, el servicio no puede usarse para la subcontratación basada en actividades.

### <a name="subcontracted-process-activities"></a>Actividades de proceso subcontratadas

Para configurar una actividad de proceso como actividad subcontratada, siga estos pasos.

1.  Configuración de una celda de trabajo subcontratada. Para configurar una celda de trabajo subcontratada, debe crear un recurso de tipo **Proveedor** y asociarlo con la celda de trabajo (grupo de recursos). Una categoría de coste de tiempo de ejecución del tipo de grupo de coste **Subcontratación directa** se debe asignar a la celda de trabajo. Las categorías de coste para la configuración y la cantidad no son necesarias.
2.  Una vez que una actividad de proceso se cree y se relacione con una celda de trabajo subcontratada, debe configurar un servicio para la actividad antes de que la versión del flujo de producción se pueda activar. Puede realizar este paso en la página de **detalles de** **actividad**. Para las actividades que están asociadas a una celda de trabajo subcontratada se muestra la ficha desplegable de las **Condiciones de servicio**. En esta ficha desplegable, agregue un servicio predeterminado que sea válido para todos los artículos de salida. Si algunos artículos específicos de salida requieren diferentes servicios o diferentes parámetros de cálculo de servicio (por ejemplo, otro coeficiente del servicio), puede agregar otros servicios a la actividad.

## <a name="subcontracted-transfer-activities"></a>Actividades de transferencia subcontratadas
Una actividad de transferencia se configura como actividad subcontratada en función del ajuste **Fletado por** de la actividad de transferencia. Están disponibles las siguientes opciones:

-   **Expedidor** – La actividad se subcontrata si la transferencia desde el almacén se gestiona a través de un proveedor (según se define con una propiedad del almacén). Todos los acuerdos de compra seleccionados para los servicios deben tener el mismo identificador de proveedor que el almacén.
-   **Destinatario** – La actividad se subcontrata si la transferencia al almacén se gestiona a través de un proveedor (según se define con una propiedad del almacén). Todos los acuerdos de compra seleccionados para los servicios deben tener el mismo identificador de proveedor que el almacén.
-   **Transportista** – La actividad se subcontrata a cualquier proveedor que proporcione el servicio. Para ser válido, un transportista debe crearse para la gestión del almacén y debe tener una cuenta de proveedor asignada.

Con respecto a actividades de proceso, debe configurar un servicio predeterminado para las actividades de transferencia subcontratadas en la ficha desplegable de las **Condiciones de servicio** de la página de **detalles** de la **actividad**.

## <a name="service-quantity-calculation"></a>Cálculo de cantidad de servicio
Todo el proceso de compra se basa en una referencia de artículo para un servicio. Esta referencia del artículo se mide en una unidad de medida de un servicio. Los servicios generalmente se miden por el número de servicios (unidades) o por el tiempo. Para calcular la cantidad de servicio, en función de la finalización registrada de trabajos kanban, puede usar los métodos siguientes:

-   **Cálculo basado en el número de trabajos** – Un trabajo kanban es igual a *n* unidades de servicio, independientemente de la cantidad de producto suministrada. En la lean manufacturing un trabajo se corresponde a una unidad de gestión de material. Este método de cálculo se aplica a todos los servicios que tienen un precio fijo por unidad de gestión de material. Por lo tanto, este método se aplica normalmente a las actividades de transferencia. Sin embargo, puede aplicarse también para procesar las actividades que procesan unidades de gestión de material completas.
-   **Cálculo basado en la cantidad de producto** – La cantidad de servicio está relacionada con la cantidad de producto programada/suministrada. Al calcular la cantidad de producto suministrada, las cantidades con errores se pueden incluir o ser excluidas. Este método de cálculo se aplica a todos los casos en los que el precio de servicio por unidad de producto procesado se acuerda.
-   **Cálculo basado en el tiempo de actividad** – Los tiempos de actividad teóricos se calculan a partir del tiempo de procesamiento de la actividad, la cantidad procesada total y el coeficiente de capacidad de proceso del producto procesado. Este método de cálculo se aplica a los servicios que se pagan por horas y tienen una desviación del tiempo por producto procesado.

## <a name="cost-accounting-of-subcontracted-services"></a>Contabilidad de costes de los servicios subcontratados
Cuando el aviso de recepción o un albarán del proveedor en un pedido de compra creado para un flujo de producción (es decir un pedido de compra que se ha generado en función de los trabajos kanban de las actividades subcontratadas) se envía, el valor del recibo se registra en las cuentas de trabajo en curso del flujo de producción. Las desviaciones de facturas también se registran en el flujo de producción. Una categoría de coste para el trabajo subcontratado se han especificado. Esta categoría de coste permite un seguimiento transparente del valor del trabajo subcontratado que se asigna al trabajo en curso y se consume por período.  

La contabilización previa de los costes de lean manufacturing al final de un período de la gestión de costes calcula las desviaciones reales de los productos generados en el flujo de producción durante el período de gestión de costes.

## <a name="modeling-transfers-as-subcontracted-activities"></a>Modelado de transferencias como actividades subcontratadas
Las personas con frecuencia consideran el transporte como algo no productivo y piensan que no agrega ningún valor. No obstante, si el coste de la subcontratación se compara con el coste de producción interna, el coste de las actividades de transporte adicionales debe tenerse en cuenta. Un flujo de producción que abarca distintas ubicaciones y requiere servicios de transporte debe modelar el coste de transporte como parte del coste del suministro de productos al cliente. 

La subcontratación basada en actividades en lean manufacturing permite integrar a los transportistas y a los proveedores de transporte que mueven materiales y productos entre ubicaciones de un flujo de producción. Modelando una actividad de transferencia, puede asignar un transportista o un proveedor. Las actividades de transferencia/trabajo se basan en un acuerdo de compra y servicio y puede crear pedidos de compra y avisos de recepción basados en los trabajos reales de transferencia. Esta funcionalidad es igual a la funcionalidad para las actividades de proceso subcontratadas.  

Supply Chain Management ahora admite el cálculo de L. MAT que incluye servicios de transporte, la creación de pedidos de compra relacionados, el registro de recepción integrado y la integración de los costes del servicio de transporte en la gestión de costes del flujo de producción.



