---
title: Liberar al almacén
description: Este tema proporciona detalles sobre el proceso de liberación al almacén. Describe las entidades que se crean cuando libera un pedido al almacén y las opciones que puede utilizar para iniciar el proceso.
author: mirzaab
ms.date: 8/13/2021
ms.topic: article
ms.search.form: WHSReleaseToWarehouse, WHSReleaseToWarehouseSalesOrder, WHSReleaseToWarehouseTransferOrder, WHSLoadPlanningWorkbench, WHSWaveTemplateTable, WHSWorkTemplateTable, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 3269bf3f8a5475fb85e6b51514db29006be9aab1
ms.sourcegitcommit: b52ff5dfd32580121f74a5f262e5c2495e39d578
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376217"
---
# <a name="release-to-warehouse"></a>Liberar al almacén

[!include [banner](../../includes/banner.md)]

Este tema proporciona detalles sobre el proceso de liberación al almacén. Describe las entidades que se crean cuando libera un pedido al almacén y las opciones que puede utilizar para iniciar el proceso.

## <a name="release-to-warehouse-overview"></a>Descripción general de la liberación a almacén

La liberación al almacén es el proceso de preparar el inventario para el procesamiento de despacho. Cuando libera un pedido al almacén, el sistema crea líneas de carga y envíos. Si se configura el procesamiento automático de ondas, también se crean las cargas y el trabajo requerido. La configuración de las entidades involucradas depende de la configuración del sistema. En esta sección del tema se revisan las entidades que se crean durante el proceso de liberación al almacén y la configuración del sistema que las define.

Un *envío* es un grupo de órdenes de venta o líneas de orden de transferencia para el mismo cliente o la misma dirección de entrega.

Una *carga* es un grupo de órdenes de venta o líneas de orden de transferencia que se agrupan y que normalmente salen en un solo camión, vagón de ferrocarril u otro modo de transporte. Una carga puede tener uno o varios envíos. Puede crear una carga manualmente agregando líneas de pedido a una nueva carga. En este caso, las líneas de orden se asignan a la carga antes de que se inicie el proceso de liberación al almacén, y solo se pueden liberar desde la página **Banco de trabajo de planificación de carga**.

El *trabajo* de almacén es cualquier operación de almacén que realiza un trabajador de almacén. Normalmente, las operaciones de trabajo del almacén constan de al menos dos acciones consecutivas: un trabajador de almacén recoge inventario disponible en una ubicación y después lo pone en otra ubicación.

Cuando los pedidos se liberan al almacén, el sistema crea *líneas de carga* y las agrupa en envíos. El proceso de consolidación de envíos permite la consolidación automatizada de envíos durante el proceso de liberación al almacén. Para obtener más información, consulte [Directivas de consolidación de envíos](about-shipment-consolidation-policies.md).

El sistema utiliza *oleadas* para crear trabajos de picking y cargas para envío. Una *plantilla de oleada* debe estar disponible para el tipo de oleada que desea crear y para el almacén de la línea de pedido. Las plantillas de oleada de tipo *Envío* se usan para enviar artículos para los pedidos de ventas y los pedidos de transferencia.

Cada plantilla de onda contiene *métodos de oleada*. Los métodos de onda realizan acciones como crear trabajo para la onda o crear cargas. Por ejemplo, una plantilla de oleada para oleadas de envío puede contener métodos para crear cargas, asignar líneas a las oleadas, reabastecer y crear trabajo de picking para la oleada. La plantilla de oleada establece configuraciones que definen cómo se generará y procesará la oleada, incluidos los pasos que se deben realizar manualmente y los que se realizan automáticamente. Para obtener más información, vea [Plantillas de oleada](wave-templates.md). Por lo tanto, dependiendo de la configuración de su plantilla de oleada, una oleada se crea, procesa y libera automáticamente cuando libera un pedido al almacén, o algunas o todas esas acciones se realizan manualmente después de que se realiza el lanzamiento al almacén.

Cuando se procesa una ola, el sistema crea un trabajo de picking, basado en una *plantilla de trabajo* y una *directiva de ubicación* adecuadas, y hace que ese trabajo esté disponible en dispositivos móviles. La plantilla de trabajo determina cómo se realiza el trabajo para cada proceso de almacén y la directiva de ubicación especifica las ubicaciones de picking y colocación para el movimiento de inventario. Para obtener más información, consulte [Controlar el trabajo de almacén usando plantillas de trabajo y directivas de ubicación](control-warehouse-location-directives.md).

> [!NOTE]
> De forma predeterminada, las ondas se procesan en modo por lotes.

Durante el procesamiento de oleadas, el sistema generalmente crea una nueva carga para cada envío al que no se asigna ninguna carga. Si desea que el sistema asigne envíos no asignados a cargas existentes, puede utilizar la funcionalidad avanzada de generación de carga de olas. Para más información, consulte [Planificación de carga avanzada durante un lanzamiento](advanced-load-building-during-wave.md).

Sobre las páginas **Ordenes de venta** y **Órdenes de transferencia**, puede revisar las entidades que se crean para las líneas de pedido durante el proceso de liberación al almacén.

- Página **Pedidos de ventas**:

    - En la ficha desplegable **Líneas de orden de venta**, seleccione **Depósito** y luego, en el menú, seleccione **Detalles del envío** para abrir envíos relacionados, **Cargar detalles** para abrir cargas relacionadas o **Detalles del trabajo** para abrir detalles de trabajo relacionados.
    - En la ficha despelgable **Detalles de la línea**, seleccione la pesetaña **Carga** pestaña para revisar las cargas relacionadas.

- Página **Pedidos de transferencia**:

    - En el panel de acciones, en la pestaña **Enviar**, seleccione **Detalles del envío** para abrir envíos relacionados o **Cargar detalles** para abrir cargas relacionadas.
    - En la ficha desplegable **Líneas de orden de transferencia**, seleccione **Detalles del trabajo** para abrir detalles de trabajo relacionados.

En conclusión, cuando se libera un pedido al almacén, el flujo más automatizado funciona de la siguiente manera:

1. El sistema crea un envío para el pedido y una oleada.
1. La ola se procesa.
1. El sistema crea una carga y una identificación de trabajo.

Dependiendo de las plantillas de oleadas, las plantillas de trabajo y la configuración de las directivas de ubicación, algunos pasos de este flujo pueden volverse manuales. Sin embargo, el flujo general sigue siendo el mismo.

Tiene varias opciones sobre cómo enviar un pedido al almacén. Puede realizar la operación manualmente o puede configurar un trabajo por lotes. Las secciones restantes de este tema revisan, en detalle, las diversas formas en que puede realizar una operación de liberación al almacén.

## <a name="manual-release-to-the-warehouse-from-the-sales-orders-and-transfer-orders-pages"></a>Liberación manual al almacén desde las páginas Órdenes de venta y Órdenes de transferencia

Puede liberar un pedido al almacén directamente desde la página **Ordenes de venta** o la página **Órdenes de transferencia**, seleccionando **Liberar al almacén**.

- En la página **Ordenes de venta**, el botón está en la pestaña **Depósito** del Panel de acciones.
- En la página **Ordenes de transferencia**, el botón está en la pestaña **Enviar** del Panel de acciones.

Desde la página **Ordenes de venta**, puede liberar varios pedidos de venta simultáneamente.

## <a name="manual-release-to-the-warehouse-from-the-release-to-warehouse-pages"></a>Liberación manual al almacén desde las páginas de Liberación al almacén

Actualmente, el sistema proporciona tres páginas en las que puede revisar las líneas de varios pedidos y enviarlas al almacén:

- **Liberar al almacén** (**Gestion de almacenes \> Liberar al almacén \> Liberar al almacén**): esta página le permite trabajar tanto con órdenes de venta como con órdenes de transferencia. Sin embargo, proporciona un rendimiento más lento que las otras dos páginas. Esta página pronto quedará obsoleta.
- **Liberar órdenes de venta al almacén** (**Gestion de almacenes \> Liberar al almacén \> Liberar órdenes de venta al almacén**): esta página le permite trabajar solo con órdenes de venta. Sin embargo, proporciona un mejor rendimiento que la página **Liberar al almacén**.
- **Liberar órdenes de transferencia al almacén** (**Gestion de almacenes \> Liberar al almacén \> Liberar órdenes de transferencia al almacén**): esta página le permite trabajar solo con órdenes de transferencia. Sin embargo, proporciona un mejor rendimiento que la página **Liberar al almacén**.

Las tres páginas proporcionan una funcionalidad similar, como se describe en el resto de esta sección. Todos ellos le permiten seleccionar líneas de pedido o pedidos completos y luego enviarlos al almacén.

Cada una de las páginas consta de una sección superior, donde puede seleccionar líneas de pedido, y una sección inferior, donde puede iniciar el proceso de liberación al almacén. Puede utilizar filtros en la sección superior para buscar las líneas de orden de venta que desea liberar. La página **Liberar al almacén** proporciona una pestaña separada para pedidos de venta y pedidos de transferencia en la sección superior, mientras que cada una de las otras dos páginas muestra solo un tipo de pedido.

La barra de herramientas en la sección superior incluye los siguientes botones que puede usar para seleccionar líneas de pedido para enviar al almacén:

- **Agregar** - Seleccione una o más líneas de orden en la sección superior, y luego seleccione este botón para las líneas de la sección inferior.
- **Añadir todo** - Agregue todas las líneas de la sección superior a la sección inferior.
- **Agregar orden** - Seleccione un pedido y luego seleccione este botón para agregar todas las líneas de ese pedido a la sección inferior.

Una vez que haya terminado de agregar líneas a la sección inferior, marque cada línea que desee liberar. Luego seleccione **Liberar al almacén** en la barra de herramientas para liberar esas líneas al almacén.

## <a name="manual-release-to-the-warehouse-from-the-load-planning-workbench-page"></a>Liberación manual al almacén desde la página Área de trabajo de planificación de la carga

También puede liberar pedidos manualmente al almacén utilizando la página **Banco de trabajo de planificación de carga**. Esta página le permite organizar las líneas de pedido en cargas y luego liberar esas cargas al almacén.

Para abrir el **Área de trabajo de planificación de la carga** vaya a **Gestión de almacén \> Cargas**. También puede abrirla desde las páginas **Ordenes de venta** y **Órdenes de transferencia**. En la sección superior de la página, puede seleccionar líneas de orden de venta en la pesetaña **Lineas de venta** y líneas de orden de transferencia en la pestaña **Líneas de transferencia**, y luego agregue esas líneas a una carga nueva o existente.

La pestaña **Oferta y demanda** del Panel de acciones incluye los siguientes botones que puede usar para agregar líneas de pedido en la sección superior a una carga:

- **A nueva carga** - Seleccione una o más líneas de orden en la sección superior, y luego seleccione este botón para crear una nueva carga y agregarle las líneas.
- **A carga existente** - Seleccione una o más líneas de orden en la sección superior, y luego seleccione este botón para agregar las líneas a una carga existente.
- **Orden completa a nueva carga** - Seleccione una o más líneas de orden en la sección superior, y luego seleccione este botón para crear una nueva carga y agregarle todas las líneas de esas órdenes.
- **Orden completa a carga existente** - Seleccione una orden y y luego seleccione este botón para agregar todas las líneas de esa orden a una carga existenete.

En la sección inferior, puede revisar las cargas que se crean. Para liberar cargas al almacén, selecciónelas y luego seleccione **Despachar \> Despachar al almacén** en la barra de herramientas. Si está utilizando el procesamiento automático de oleadas, debido a que las cargas ya están asignadas a las líneas de pedido, el sistema crea los envíos y los ID de trabajo cuando se realiza la operación de liberación al almacén.

## <a name="automatic-release-to-the-warehouse"></a>Liberación automática al almacén

Para liberar pedidos automáticamente al almacén, utilice los trabajos **Liberación automática de órdenes de venta** y **Liberación automática de órdenes de transferencia**.

Para configurar el trabajo por lotes para liberar automáticamente pedidos de compra, siga estos pasos.

1. Ir **Gestión de almacén \> Despachar al almacén \> Despacho automático de pedidos de ventas**.
1. En el cuadro de diálogo **Liberación automática de pedidos de venta**, en la ficha desplegable **Parámetros**, establezca los siguientes campos:

    - **Cantidad para liberar**: seleccione si la cantidad total o solo la cantidad reservada físicamente se debe liberar al almacén.
    - **Permitir la liberación de pedidos parcialmente liberados** - Especifique si las cantidades restantes para pedidos parcialmente liberados deben liberarse en el almacén.
    - **Mantener las reservas sobre fallos en el lanzamiento** - Especifique si las cantidades que se reservaron automáticamente para un pedido de cliente deben permanecer reservadas si falla el proceso de liberación al almacén.
    - **Versiones de grupo por cliente** - Especifica si el sistema debe procesar las operaciones de liberación al almacén por separado para cada cliente o si debe liberar todos los pedidos de ventas a la vez. Cuando esta opción está establecida en *Sí*, el sistema recopilará todas las líneas de pedidos de venta para un cliente seleccionado, entregará esos pedidos al almacén y luego procesará al siguiente cliente. Cuando esta opción está establecida en *No*, el sistema liberará todas las líneas de pedidos de venta disponibles en una sola liberación para la operación del almacén. Al habilitar esta opción, puede ayudar a mejora el rendimiento y la resistencia del proceso de lanzamiento al almacén. Sin embargo, debe tener cuidado al usar esta opción junto con las plantillas de oleadas que están configuradas para procesar oleadas en el lanzamiento al almacén porque esta combinación puede generar muchas oleadas de un solo cliente, cada una con trabajo generado solo para ese cliente. Si desea generar trabajo que combine envíos para varios clientes, debe desactivar la opción *Liberaciones grupales por cliente* o configurar sus plantillas de oleadas para utilizar el procesamiento pospuesto.
    - **Manejo de pedidos bloqueados** - Seleccione cómo el sistema debe manejar los pedidos de ventas que están actualmente bloqueados porque otros usuarios o procesos los están editando:

        - *Espere a que se desbloqueen las órdenes* - El sistema debe esperar a que los pedidos se desbloqueen antes de enviarlos al almacén. En este caso, el proceso de liberación al almacén puede llevar más tiempo.
        - *Omitir pedidos bloqueados* - El sistema debe omitir los pedidos bloqueados.

    - **Tipos de orden válidos** - Seleccione los tipos de órdenes de venta para incluir en el lote.
    - **Tipo de límite de crédito** - Seleccione si se deben realizar verificaciones de límites de crédito durante el proceso de liberación al almacén y, si se deben realizar las verificaciones, la información de la transacción a incluir en ellas.

1. Para controlar qué pedidos deben procesarse, en la ficha desplegable **Registros para incluir**, seleccione **Filtrar**. Aparece un cuadro de diálogo de consulta estándar, donde puede definir criterios de selección, criterios de clasificación y combinaciones. Los campos funcionan igual que para otros tipos de consultas en Microsoft Dynamics 365 Supply Chain Management.
1. En la ficha desplegable **Ejecutar en segundo plano**, elija si el trabajo se debe ejecutar en modo por lotes y/o establezca una programación periódica. Los campos funcionan igual que para otros tipos de [trabajos en segundo plano](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) en Supply Chain Management.
1. Seleccione **Aceptar** para aplicar su configuración e iniciar el proceso de liberación al almacén.

Para configurar el trabajo por lotes para liberar automáticamente pedidos de transferencia, siga estos pasos.

1. Vaya a **Gestión de almacén \> Despachar al almacén \> Despacho automático de pedidos de transferencia**.
1. En el cuadro de diálogo **Liberación automática de pedidos de transferencia**, en la ficha desplegable **Parámetros**, establezca los siguientes campos:

    - **Cantidad para liberar**: seleccione si la cantidad total o solo la cantidad reservada físicamente se debe liberar al almacén.
    - **Permitir la liberación de pedidos parcialmente liberados** - Especifique si las cantidades restantes para pedidos parcialmente liberados deben liberarse en el almacén.
    - **Liberaciones de grupo por almacén de destino** - Especifique si el sistema debe liberar todas las órdenes de transporte al mismo tiempo, o si debe agrupar las líneas de orden de transferencia por almacén de destino y luego liberar cada grupo al almacén por separado.

1. Para controlar qué pedidos deben procesarse, en la ficha desplegable **Registros para incluir**, seleccione **Filtrar**. Aparece un cuadro de diálogo de consulta estándar, donde puede definir criterios de selección, criterios de clasificación y combinaciones. Los campos funcionan igual que para otros tipos de consultas en Supply Chain Management.
1. En la ficha desplegable **Ejecutar en segundo plano**, elija si el trabajo se debe ejecutar en modo por lotes y/o establezca una programación para periodicidad. Los campos funcionan igual que para otros tipos de [trabajos en segundo plano](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) en Supply Chain Management.
1. Seleccione **Aceptar** para aplicar su configuración e iniciar el proceso de liberación al almacén.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
