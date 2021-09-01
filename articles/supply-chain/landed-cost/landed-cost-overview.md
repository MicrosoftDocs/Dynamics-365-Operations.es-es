---
title: Módulo de costo descargado
description: El módulo de costos de aterrizaje ayuda a las empresas a agilizar las operaciones de envío entrante al brindar a los usuarios un control financiero y logístico completo sobre el flete importado, desde el fabricante hasta el almacén.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 87cce7a00d5ae8af2f9992a7dadda6a55880e4af51e26c31b54baf065c34059f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744139"
---
# <a name="landed-cost-module"></a>Módulo de costo descargado

[!include [banner](../../includes/banner.md)]

El módulo de **costos de aterrizaje** ayuda a las empresas a agilizar las operaciones de envío entrante al brindar a los usuarios un control financiero y logístico completo sobre el flete importado, desde el fabricante hasta el almacén. Para los bienes importados, los costos de desembarque pueden representar el 40 por ciento o más del costo total de cada artículo importado. Por lo tanto, el desafío consiste en proporcionar estimaciones precisas de los costos de entrega.

Las empresas pueden utilizar el costo aterrizado para completar las siguientes tareas:

- Estimar los costos de aterrizaje en el momento de la creación del viaje.
- Distribuya los costos de desembarque entre varios artículos y órdenes de compra u órdenes de transferencia en un solo viaje.
- Apoyar la transferencia de bienes entre ubicaciones físicas reconociendo los costos de entrega.
- Reconocer las acumulaciones de mercancías en tránsito.

El costo de entrega proporciona estimaciones de costos precisas y oportunas para los costos de entrega generales. Al mismo tiempo, proporciona una mayor visibilidad financiera y logística de la cadena de suministro extendida. También ayuda a reducir la administración de costos y errores de cálculo de costos.

## <a name="highlights"></a>Reflejos

### <a name="voyages"></a>Viajes

En el costo de aterrizaje, un viaje es un movimiento distinto desde una ubicación de salida, a través de un conjunto específico de destinos durante un período específico, a una ubicación de almacén de entrada específica. Los pedidos de compra y las líneas de pedido se pueden agregar a un solo contenedor o a varios contenedores para un viaje, y los costos se asignarán correctamente a la línea del artículo. Los pedidos y las líneas de pedido también se pueden agregar entre entidades legales para un solo viaje.

### <a name="item-ownership"></a>Propiedad del artículo

En Microsoft Dynamics 365 Supply Chain Management, las mercancías normalmente se reciben en el destino del almacén y luego se facturan. Sin embargo, según la mayoría de los acuerdos comerciales internacionales, una empresa adquiere la propiedad de los bienes desde el momento en que salen del puerto original, antes de que se hayan recibido físicamente. El costo de entrega permite a las empresas facturar los bienes antes de que se hayan recibido físicamente. Este concepto se conoce como una orden de mercancías en tránsito. Crea un nuevo tipo de orden para gestionar la recepción de mercancías después de que se haya facturado la orden de compra original.

### <a name="costs"></a>Costes

Cuando crea un viaje en el costo de aterrizaje, los costos se pueden agregar automáticamente. Estos costos se establecen en el costo de destino, y se encuentran disponibles para ellos varias opciones de costos y bases de costos. Cada costo puede configurarse para diferentes niveles de un viaje y distribuirse al nivel del artículo a través de reglas de distribución que respalden la cantidad, el volumen, el peso, la cantidad y los divisores volumétricos definidos. Estos costos estimados proporcionan una estimación precisa de todos los costos de un viaje.

El costo de aterrizaje luego ejecuta una publicación / acumulación preliminar de los costos de desembarco estimados para garantizar que se proporcione un cálculo preciso de los costos estimados en el momento de la creación del viaje. A medida que se facturan estos costos automáticos, los costos estimados se invierten y se reemplazan por los costos reales, según las facturas de costos.

Los costos reales son costos estimados inversos que se contabilizan en el momento de la facturación de costos mediante el uso de cuentas de compensación que se configuran para cada tipo de costo (por ejemplo, impuestos, fletes y seguros). Estas publicaciones siguen el comportamiento de publicación que está asociado con el artículo específico. Actualizan automáticamente la contabilización de inventario, independientemente de si el tipo de contabilización es primero en entrar, primero en salir (FIFO), último en entrar, primero en salir (LIFO), promedio ponderado móvil o promedio móvil. Se admiten todos los tipos de contabilización de grupos de modelos de inventario. Para la contabilización de costos promedio y estándar, las cuentas de variación de precio de compra están disponibles para registrar las diferencias entre los costos estimados y los costos reales.

### <a name="item-and-order-tracking"></a>Seguimiento de artículos y pedidos

A medida que un viaje se mueve desde la ubicación de salida de origen hasta el almacén de destino final, los usuarios pueden actualizar cada paso o *tramo* de su viaje según sea necesario. Para cada tramo, se identifican un plazo de entrega y un estado de envío. También se identifican las fechas de entrega confirmadas para el traslado al siguiente tramo del viaje. Juntas, estas fechas de entrega proporcionan una fecha estimada de entrega de las mercancías al almacén de entrada. Los usuarios pueden cambiar estas fechas de entrega. En este caso, la fecha estimada de entrega de la mercancía se actualiza automáticamente en función de los plazos de entrega y los tramos del viaje. La visibilidad de las mercancías en tránsito por viaje y barco está disponible por contenedor antes de la recepción de las mercancías. Debido a que las fechas se actualizan en cada línea de orden de compra, las empresas tienen más control sobre la logística y la planificación del almacén.

## <a name="landed-cost-concepts"></a>Conceptos de costos de destino

La siguiente tabla resume algunos conceptos básicos del costo de aterrizaje.

| Concepto | Descripción |
|---|---|
| Viaje | Normalmente, un viaje es un barco. Sin embargo, dependiendo de sus prácticas y procedimientos, puede ser un proveedor o una orden de compra. No existen limitaciones en el uso de este concepto. |
| Folio | Un folio suele estar determinado por las normas aduaneras. Puede constar de los productos de un proveedor para una entidad o empresa por envío. Los productos en un folio pueden estar en un contenedor o esparcidos entre múltiples contenedores. |
| Contenedor de envío | Los contenedores de envío almacenan líneas de órdenes de compra. Están un nivel por debajo del nivel de envío. Por lo general, se utilizan si los costos se asignan a las mercancías por contenedor o si la recepción se realiza por contenedor. |
| Tipo de contenedor de envío | Los tipos de contenedores de envío pueden determinar el precio de un tipo de costo (por ejemplo, flete). También proporcionan información de envío útil. |
| Tipo de coste | Los tipos de costos identifican los costos asociados con las importaciones, como aranceles, fletes y seguros. |
| Coste automático | Los costos de los automóviles funcionan como acuerdos comerciales. Un coste de automóvil está vinculado a un nivel de viaje. |
| Puerto | Los puertos son áreas desde donde se reciben y transfieren mercancías. |
| Embarcación | Una nave es el medio que se utiliza para transportar mercancías, como un barco o un avión. |
| Mercancía en tránsito | Dependiendo de la configuración, las mercancías se colocan en un almacén en tránsito después de actualizar una factura. |
| Actividad | Las actividades se pueden utilizar para almacenar cada paso significativo del viaje entre dos puertos. Se pueden utilizar para actualizar fechas. |
| Plantilla de recorrido | Las plantillas de viaje son rutas que toman las mercancías entre dos puertos. |

Para una comparación de la terminología y características de los módulos **Coste descargado** y **Gestión de transporte** (TMS), consulte [Costo descargado frente a Gestión del transporte](landed-cost-vs-tms.md).
