---
title: "Tránsito directo desde pedidos de producción a muelles de salida"
description: "Este tema describe cómo se administra el proceso de material de tránsito directo que se le notifica como terminado desde una línea de producción a un muelle de salida de transporte."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSCrossDockOpportunityPolicy
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 62194012cfbe101d19e9de3254afb004da79a562
ms.contentlocale: es-es
ms.lasthandoff: 03/08/2018

---

# <a name="cross-docking-from-production-orders-to-outbound-docks"></a>Tránsito directo desde pedidos de producción a muelles de salida

[!INCLUDE [banner](../includes/banner.md)]

Este tema describe cómo se administra el proceso de material de tránsito directo que se le notifica como terminado desde una línea de producción a un muelle de salida de transporte.

<a name="introduction"></a>Introducción
------------

El tránsito directo desde la producción a una ubicación de salida es relevante para los fabricantes que generan grandes cantidades y desean enviar en el menor de los casos los productos terminados en cuanto se notifica que están terminados desde las líneas de producción. El objetivo es enviar los productos a los centros de distribución que se ubican físicamente cerca de la demanda de los clientes, en lugar de generar un inventario en el sitio de fabricación.

En caso de que no haya demanda inmediata para un producto, debe apartarse en las ubicaciones de almacén en el sitio de fabricación. Este proceso también se conoce como *tránsito directo oportunista*, que indica que si existe una demanda para enviar el producto, esta oportunidad debe ser utilizada en lugar de apartar el producto para el almacenamiento interno.

El siguiente ejemplo muestra tres variaciones de un flujo que empieza al final de la línea de producción (2).

Un producto se registra como terminado a la ubicación de salida de producción (3) y un elevador recogerá el pallet en esta ubicación (3).

-   Si hay una actividad planificada (6) para transferir el producto desde fabricación (1) a un centro de distribución (7), el conductor del camión será dirigido por el sistema para dejar el pallet en una ubicación con compuerta (4).
-   Si hay un tráiler asignado en la compuerta, se indicará al conductor del camión que cargue el producto directamente en el tráiler.
-   Si no hay ninguna actividad planificada para transferir el producto, se indicará al conductor del elevador que coloque el producto en una ubicación en el almacén interno (5).

[![Tránsito directo oportunista](./media/scenario1.png)](./media/scenario1.png)

## <a name="configure-cross-docking"></a>Configurar el tránsito directo
Puede configurar el proceso de tránsito director en las **directivas de trabajo**. Una directiva de trabajo incluye un tipo de pedido de trabajo, una ubicación y un producto. En el siguiente ejemplo, el tránsito directo se configura para el producto X y la ubicación Y.

#### <a name="work-order-types"></a>Tipos de pedido de trabajo

-   Tipo de pedido de trabajo: Los productos terminados se retiran
-   Método de creación de trabajo: Tránsito directo
-   Nombre de la directiva de tránsito directo: Pedidos de transferencia

#### <a name="inventory-locations"></a>Ubicaciones del inventario

-   Almacén: 51
-   Ubicación: Y

#### <a name="products"></a>Productos

-   Número de artículo: X

Actualmente, el tránsito directo se puede configurar para solo dos tipos de pedido de trabajo:

-   Ubicación de bienes terminados
-   Ubicación de coproducto y producto derivado

En la **directiva de tránsito directa**, define qué tipos de documentos son de aplicación para el tránsito directo. Actualmente, el único tipo de documento que se admite es **Pedidos de transferencia**. El ejemplo siguiente se muestra la configuración de una directiva de tránsito directo.

### <a name="cross-docking-policy-name-transfer-order"></a>Nombre de la directiva de tránsito directo: Pedido de transferencia

- Número de secuencia: 10
  -   Tipo de pedido de trabajo: Problema de transferencia
- La demanda de tránsito directo precisa una ubicación: Falso
- Estrategia de tránsito directo: Fecha y hora

### <a name="sequence-number"></a>Número de secuencia

El **número de secuencia** indica la prioridad del tipo de documento. Actualmente, **Problema de transferencia** es el único tipo que se admite. Por lo tanto, el número de secuencia pasará a ser relevante solo cuando se admitan más tipos de pedido de trabajo.

### <a name="cross-docking-policy"></a>Directiva de tránsito directo

La directiva de tránsito también define la directiva para la priorización de la demanda del pedido de transferencia. Por ejemplo, si existen varios pedidos de transferencia para el mismo producto, la fecha y hora programadas que se establecen en la carga y se asocian al pedido de transferencia determinan la priorización entre los pedidos. La fecha y hora programadas se pueden establecer directamente en la carga o se pueden configurar en una **programación de presupuesto** que esté asociado a la carga. La priorización está determinada por la estrategia de tránsito directo. Actualmente, solo existe una estrategia: **Fecha y hora**.

### <a name="cross-docking-demand-requires-location"></a>La demanda de tránsito directo precisa una ubicación

En la directiva de tránsito directo, puede configurar un criterio para requerir que los pedidos de transferencia tengan una ubicación asignada para ser aptos para el tránsito directo. Este criterio se establece en el campo **La demanda de tránsito directo precisa una ubicación**. La ubicación en la programación de citas que está asociada a la carga se usa como la ubicación final para las mercancías del tránsito directo. La ubicación final de las mercancías del tránsito directo viene determinada por la directiva de la ubicación para **Emisión de transferencia** para el tipo de pedido del trabajo **Colocar**. Es posible que lo encuentre útil para establecer los valores del campo **La demanda de tránsito directo precisa una ubicación** en un escenario en el que el producto terminado se procesará en tránsito directo si se asigna un tráiler a una compuerta. En esta situación, las mercancías se trasladan directamente desde la línea de producción al tráiler. Cuando un tráiler se asigna a la compuerta, un usuario asignará la ubicación a la programación de citas y por tanto hará que se puede usar la ubicación en el tránsito directo. Las secciones siguientes describen dos ejemplos.

#### <a name="scenario-1--cross-docking-from-production-to-transfer-orders"></a>Situación 1: Tránsito directo desde pedidos de producción a pedidos de transferencia

Después de que un producto se notifica como terminado en la línea de producción se transfiere a una ubicación de compuerta donde se carga en un camión y se transfiere a un centro de distribución. Use USMF de la empresa.

1.  Habilite una nueva secuencia numérica para el tránsito directo. Vaya a la página **Secuencias numéricas** y seleccione el botón **Generar** . Un asistente le guiará a través del proceso.
2.  Cree una directiva de tránsito directo Vaya a la página **Directiva de tránsito directo** y cree una nueva directiva que se llame **Tránsito directo para pedido de transferencia**. Tenga en cuenta que el único tipo de pedido de trabajo que puede seleccionar es **Emisión de transferencia** y la única estrategia de tránsito disponible es **Fecha y hora**.
3.  Cree una directiva de trabajo. Vaya a la página **Directivas de trabajo** y cree una directiva de trabajo nueva que se llame **Tránsito directo L0101**.
4.  Configure las cargas para que se creen automáticamente para los pedidos de transferencia. En los parámetros de almacén, configure cargas para que se puedan crear automáticamente al cuando se creen pedidos de transferencia. Una carga es un requisito previo para crear el pedido de transferencia apto para el tránsito directo.
5.  Configure la asignación de carga de artículos. Vaya a la página **Asignación de carga de artículos** y configure una plantilla estándar de carga para el grupo de artículos **CarAudio**. Esta asignación insertará automáticamente la plantilla de carga en la carga cuando se crea el pedido de transferencia.
6.  Cree un pedido de transferencia. Cree el pedido de transferencia para el número de artículo L0101. Cantidad = 20.
7.  Libere el pedido de transferencia bancaria de área de trabajo de planificación de la carga. En la pestaña **Envío**, seleccione el elemento de menú para el área de trabajo de planificación de la carga y en el menú **Liberar** de la línea de carga, seleccione **Liberar a almacén**. Ahora existe una línea de oleada abierta de tipo **Emisión de transferencia** para el pedido de transferencia.
8.  Cree un pedido de producción. Vaya a la página de lista **Pedido de producción** y cree un pedido de producción para el producto L0101. Cantidad = 20. Estime e inicie el pedido de producción. Tenga en cuenta que el campo **Registrar ahora la lista de selección** sigue en **No**.
9.  Notifique como terminado desde el dispositivo móvil. Vaya al portar del dispositivo móvil y seleccione el elemento de menú **Notificar como terminado y poner en ubicación**. Notifique ahora como terminado L0101 desde el dispositivo de mano. Cantidad = 10. Tenga en cuenta que la ubicación de colocación es **BAYDOOR**. Esta ubicación se encuentra de la directiva de ubicación **Emisión de transferencia** para el tipo de pedido de trabajo **Colocar** . Tenga también en cuenta que el trabajo del tipo **Emisión de transferencia** se ha creado y completado. Vaya a los detalles de trabajo del pedido de transferencia para comprobar el trabajo.
10. Ahora informe de las 10 piezas adicionales del dispositivo móvil. Tenga en cuenta que de nuevo la ubicación de colocación es **BAYDOOR**. Tenga también en cuenta que se ha creado un nuevo tipo de trabajo **Emisión de transferencia** para las 10 piezas.
11. Ahora intente iniciar 20 piezas más en el pedido de producción y después intente notificar 20 c/u como terminadas usando el dispositivo de mano. Esta vez, la ubicación **LP-001** se sugiere como ubicación de colocación. Esta ubicación se encuentra en la directiva de ubicación para **Ubicación de bienes terminados**. Se usa esta directiva de ubicación porque no existen oportunidades para el tránsito directo. Las dos actividades de tránsito directo de los pasos 9 y 10 completaron totalmente el pedido de transferencia para LP-001. Observe que el trabajo del tipo **Ubicación de bienes terminados** se creó y procesó.

#### <a name="scenario-2---cross-docking-from-production-to-transfer-orders-with-an-appointment-schedule"></a>Situación 2: Tránsito directo desde producción a los pedidos de transferencia con una programación de citas

Después de que un producto se notifica como terminado en la línea de producción se transfiere a una ubicación de compuerta que se identifica por una programación de citas para las ubicaciones de compuerta. Use USMF de la empresa.

1.  Cambie la directiva de tránsito directo. Modifique la directiva de tránsito directo que ha creado en la situación 1 seleccionando la casilla de verificación **La demanda de tránsito directo precisa una ubicación**.
2.  Cree una nuevo pedido de transferencia.
3.  Abra el **Área de trabajo de planificación de la carga**.
4.  Desde el área de trabajo de la planificación de la carga, vaya a la sección **Cargas** y seleccione **Programación de presupuesto** en el menú **Transporte** para crear una nueva programación de citas. Tenga en cuenta que la programación de citas tiene una referencia al pedido de transferencia en el campo **Número de pedido**. En el campo **Fecha y hora iniciales planeadas en ubicación** puede establecer la fecha y hora para la cita. Esta fecha y hora se usará cuando la demanda de tránsito directo se prioriza durante el proceso de tránsito directo. La fecha y hora que establece en este campo actualizará el campo **Fecha y hora de envío programado de la carga** en la carga correspondiente. La ubicación en el FastTab **Detalles del envío** determina la ubicación en que se envió el pedio de transferencia.
5.  En la versión **Área de trabajo de planificación de la carga** al almacén.
6.  Cree un pedido de producción para el número de artículo **L0101** y establezca el estado en **Iniciado**, con una cantidad de 20.
7.  Notifique como terminado desde el dispositivo móvil.
8.  Vaya al portar del dispositivo móvil y seleccione el elemento de menú **Notificar como terminado y poner en ubicación**.
9.  Notifique el numero de artículo **L0101** como terminado desde el dispositivo de mano. Tenga en cuenta que la ubicación de colocación es ahora **BAYDOOR**. Esta ubicación se encuentra en la programación de citas en lugar de la directiva de ubicación **Recibo de transferencia**.

### <a name="additional-information"></a>Información adicional

-   La situación de tránsito directo se admite para artículos controlados de lote y serie, con las dimensiones de lote y número de serie definidas anteriormente y la ubicación de más abajo en la jerarquía de la reserva. 



