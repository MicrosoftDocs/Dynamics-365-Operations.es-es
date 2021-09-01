---
title: Procesar, revisar y publicar devoluciones
description: Este tema describe cómo procesar sus acuerdos de gestión de devoluciones, calcular sus descuentos, revisar las transacciones que se generan, contabilizar transacciones y revisar las contabilizaciones.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 1a9603df8fd3b2c81c37ca95fd1b13d0b6f4004a38b0cf86846486e3b5d41bfa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6729419"
---
# <a name="process-review-and-post-rebates"></a>Procesar, revisar y publicar devoluciones

[!include [banner](../includes/banner.md)]

Este tema describe cómo procesar sus acuerdos de gestión de devoluciones, calcular sus descuentos, revisar las transacciones que se generan, contabilizar transacciones y revisar las contabilizaciones.

## <a name="change-the-status-of-a-deal"></a>Cambio del estado de un acuerdo

Puede asignar un estado a cada acuerdo para ayudar a rastrearlo. El estado de este campo es meramente informativa.

1. Seleccione un acuerdo (por ejemplo, en la página [**Todas las ofertas de gestión de devoluciones**](rebate-management-deals.md)).
1. En el panel de acciones, en la pestaña **Acuerdos de gestión de devoluciones**, en el grupo **Mantener**, seleccione **Cambiar estado**.
1. En el cuadro de diálogo **Cambiar Estado**, establezca el campo **Estado de devolución** a un nuevo estado.
1. Seleccione **Aceptar**.

## <a name="calculate-fifo-purchase-prices"></a>Calcular precios de compra FIFO

La tarea periódica **Calcular el precio de compra FIFO** se debe ejecutar para calcular las devoluciones para [acuerdos](rebate-management-deals.md) donde el campo **Base de precio** está configurado en *FIFO*. El sistema utilizará una regla de primero en entrar, primero en salir (FIFO) para calcular el valor de las existencias que se vendieron. Este valor luego se utilizará para calcular las devoluciones del proveedor.

Vaya a **Gestión de devoluciones \> Tareas periódicas \> Calcular el precio de compra FIFO**. En el cuadro de diálogo que aparece, seleccione **Aceptar** para ejecutar el cálculo.

## <a name="create-source-transactions"></a>Crear transacciones de origen

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Puede crear los pedidos de venta o los pedidos de compra que tengan transacciones de origen antes o después de crear un acuerdo de gestión de devoluciones aplicable.

Puede configurar cada línea del acuerdo para que cree automáticamente una provisión de devolución contabilizando la entrega o la factura de una orden de venta o de compra. Defina el campo **Tipo de transacción** para la línea del acuerdo como *Entrega* o *Factura* y establezca **Procesar en contabilización** como *Sí*. Si el campo **Tipo de transacción** está configurado en *Pedido*, el procesamiento en contabilización está deshabilitado. Para las transacciones de origen que se crearon después de que se activó un acuerdo, aún puede procesar la provisión como se describe en la sección [Procesar Acuerdos de gestión de devoluciones](#process-deals) más adelante en este tema.

### <a name="enable-price-details"></a>Habilitar detalles de precio

Antes de poder crear transacciones de origen, debe habilitar la opción **Habilitar detalles de precios** para cliente.

1. Vaya a **Clientes \> Configuración \> Parámetros de clientes**.
1. En la ficha **Precios**, en la ficha desplegable **Detalles de precios**, establezca la opción **Habilitar detalles de precios** en *Sí*.

### <a name="create-a-source-transaction"></a>Crear una transacción de origen

Para crear una transacción de origen, siga estos pasos.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo**.

    Para imitar la manera en la que se generarán las reclamaciones de devolución, debe crear un pedido de ventas donde el producto y la cantidad permitirán al cliente optar a una devolución.

1. En el campo **Cuenta de cliente**, introduzca o seleccione un cliente que calificará para una oferta de devolución.
1. Seleccione **Aceptar** para crear el pedido de ventas.
1. En la ficha desplegable **Líneas de pedido de venta**, agregue una línea y defina los siguientes campos:

    - **Número de artículo** - Especifique un artículo que califique para una devolución.
    - **Cantidad** - Especifique una cantidad que califique para una oferta de devolución que incluya una línea donde el campo **Base** está configurado en *Cantidad*.
    - **Precio unitario** - Especifique un precio que califique para una oferta de devolución que incluya una línea donde el campo **Base** está configurado en *Valor*.
    - **Sitio** - Seleccione un sitio donde el producto esté disponible y que califique para una oferta de devolución.
    - **Almacén** - Seleccione un almacén donde el producto esté disponible y que califique para una oferta de devolución.

1. En la ficha desplegable **Líneas de pedido de ventas**, en la barra de herramientas, seleccione **Línea de pedido de ventas \> Detalles de precios**. Este comando está disponible solo si habilitó los detalles del precio como se describe en la sección anterior.
1. En la página **Detalles del precio**, seleccione la ficha desplegable **Gestión de devoluciones**. Esta ficha desplegable muestra todos los acuerdos de gestión de devoluciones aplicables a la línea de pedido actual y el importe estimado de devolución en la moneda del pedido. Tenga en cuenta que los importes son solo estimaciones de las reclamaciones de devolución futuras. Los importes de devolución reales pueden diferir. Estos son algunos de los factores que pueden afectar a los importes reales:

    - El volumen total de ventas que logró el cliente en virtud de un acuerdo de devolución periódica.
    - Si el cliente devolvió todas las cantidades o cantidades parciales.
    - Si el pedido de venta aplicable alcanzó el tipo de transacción (*Orden, Entrega* o *Factura*) que se define para el acuerdo de gestión de devoluciones.
    - El valor de **Salida** del acuerdo. Se mostrará un importe de devolución en blanco para las ofertas en las que el campo **Salida** está configurado en *Artículo*.

1. En la ficha desplegable **Detalle**, observe que la sección **Estimación de margen** incluye los siguientes campos. Estos campos son agregados por la gestión de devoluciones. Todos ellos muestran valores por unidad (mientras que los campos de la ficha desplegable **Gestión de devoluciones** muestran los valores totales de la línea).

    - **Importe de la devolución de gestión de devoluciones** (solo pedidos de venta)
    - **Importe de regalía de gestión de devoluciones** (solo pedidos de venta)
    - **Importe de la devolución del proveedor de gestión de devoluciones** (pedidos de venta y de compra)

1. Cierre la página **Detalles de precios**.
1. Si el pedido de ventas no debe calificar para las devoluciones que acaba de ver, siga estos pasos para excluir las devoluciones. (Sin embargo, generalmente no excluirá las devoluciones).

    1. En la ficha desplegable **Líneas de pedido de ventas**, seleccione la línea relevante.
    1. En la ficha desplegable **Detalles de la línea**, en la ficha **Precio y descuento**, establezca la opción **Excluir de la gestión de devoluciones** en *Sí*. Esta opción no se aplica a los pedidos de compra. Además, solo se excluyen las devoluciones de clientes cuando esta opción se establece en *Sí*. Aún se aplican devoluciones de regalías de clientes y de proveedores.

1. En el panel de acciones, en la ficha **Seleccionar y empaquetar** del grupo **Generar**, seleccione **Registrar albarán**.
1. En la ficha desplegable **Parámetros**, en el campo **Cantidad**, seleccione *Todos*.
1. Seleccione **Aceptar**.
1. Si se le solicita que confirme la operación, seleccione **Aceptar**.
1. En el panel de acciones, en la ficha **Factura**, en el grupo **Generar**, seleccione **Factura**.
1. En la ficha desplegable **Parámetros**, en el campo **Cantidad**, seleccione *Todos* o *Albarán*.
1. Seleccione **Aceptar**.
1. Si se le solicita que confirme la operación, seleccione **Aceptar**.

## <a name="process-rebate-management-deals"></a><a name="process-deals"></a>Procesar Acuerdos de gestión de devoluciones

Cuando procesa un acuerdo, el sistema calcula todos las devoluciones y regalías relevantes que se configuran. Solo acuerdos seleccionados que tienen períodos de cálculo que están listos para ser calculados y que tienen un estado de *Activo* se procesarán. Una vez completado el procesamiento, el sistema genera un conjunto de transacciones que puede revisar y luego contabilizar.

> [!NOTE]
> En todos los casos, los reembolsos se procesan al nivel especificado por la configuración **Reconciliar por** (*Acuerdo* o *Línea*). Puede realizar cálculos de una sola línea solo para acuerdos en los que el campo **Reconciliar por** está configurado en *Línea*.

### <a name="process-all-lines-for-one-or-more-deals"></a>Procesar todas las líneas para uno o más acuerdos

1. Abra la [página de lista de ofertas de devolución](rebate-management-deals.md) apropiada para el tipo de acuerdo con el que desea trabajar.
1. Seleccione la fila para cada acuerdo que desee procesar (o abra el acuerdo que desea procesar).
1. En el panel de acciones, en la pestaña **Gestión de acuerdos de devoluciones**, en el grupo **Generar**, seleccione uno de los siguientes comandos:

    - **Proceso \> Provisión** - Aprovisione un conjunto de acumulaciones para cada oferta de reembolso relevante, pero no las publique. Este elemento de menú no está disponible para ofertas en las que el campo **Rebaja de salida** está configurado en *Artículo*.
    - **Proceso \> Gestión de devoluciones** - Procesar una serie de transacciones que proporcionen el valor de la devolución para cada acuerdo.
    - **Proceso \> Pedir por escrito** - Para cada transacción de origen para el acuerdo de devolución y el período especificado, procese la variación entre los importes contabilizados para una provisión y para la gestión de devolución. Este elemento de menú no está disponible para ofertas en las que el campo **Rebaja de salida** está configurado en *Artículo*.

1. En el cuadro de diálogo que aparece, configure los campos **A partir de** y **Hasta** para definir el rango de fechas para el cálculo.
1. Seleccione **Aceptar** para ejecutar el cálculo.

### <a name="process-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Procesar una o más líneas de acuerdo específicas para un acuerdo seleccionado

1. Abra la [página de lista de ofertas de devolución](rebate-management-deals.md) apropiada para el tipo de acuerdo con el que desea trabajar.
1. Abra el acuerdo desde el que desea procesar una línea.
1. Seleccione la pestaña **Líneas** en la esquina superior derecha.
1. En la ficha desplegable **Gestión de devoluciones**, seleccione la fila para cada línea de acuerdo que desee procesar.
1. En la barra de herramientas de la ficha desplegable **Gestión de devoluciones**, seleccione uno de los siguientes comandos. (Estos comandos solo están disponibles para acuerdos en los que el campo **Reconciliar por** el campo está configurado en *Línea*).

    - **Proceso \> Provisión** - Aprovisione un conjunto de acumulaciones para cada línea de acuerdo relevante, pero no las publique. Este elemento de menú no está disponible para ofertas en las que el campo **Rebaja de salida** está configurado en *Artículo*.
    - **Proceso \> Gestión de devoluciones** - Procesar una serie de transacciones que proporcionen el valor de la devolución para cada línea de acuerdo.
    - **Proceso \> Pedir por escrito** - Para cada transacción de origen para el acuerdo de devolución y el período especificado, procese la variación entre los importes contabilizados para una provisión y para la gestión de devolución. Este elemento de menú no está disponible para ofertas en las que el campo **Rebaja de salida** está configurado en *Artículo*. 

1. En el cuadro de diálogo que aparece, configure los campos **A partir de** y **Hasta** para definir el rango de fechas para el cálculo.
1. Seleccione **Aceptar** para ejecutar el cálculo.

### <a name="process-deals-using-a-batch-job"></a>Procesar acuerdos mediante un trabajo por lotes

En lugar de procesar acuerdos o líneas de acuerdos específicos, puede ejecutar un trabajo por lotes para procesar varios acuerdos al mismo tiempo. Opcionalmente, puede aplicar filtros de registro y / o configurar una programación periódica. Para procesar acuerdos mediante un trabajo por lotes, siga estos pasos.

1. Siga uno de estos pasos:

    - Vaya a **Gestión de devoluciones \> Tareas periódicas \> Proceso \> Provisión** para proporcionar un conjunto de acumulaciones para cada acuerdo relevante, pero sin publicarlas.
    - Vaya a **Gestión de devoluciones \> Tareas periódicas \> Proceso \> Gestión de devolución** para procesar una serie de transacciones que proporcionen el valor de la devolución para cada acuerdo.
    - Vaya a **Gestión de devoluciones \> Tareas periódicas \> Proceso \> Cancelar** para revertir las transacciones publicadas anteriormente para cancelarlas de modo que se puedan calcular las nuevas transacciones de devolución.

1. En el cuadro de diálogo que aparece, en la ficha desplegable **Parámetros**, en la sección **Período** sección, establezca los campos **A partir de la fecha** y **Hasta la fecha** para definir el rango de fechas para las transacciones para el cálculo.
1. En la sección **Período garantizado**, configure los campos **A partir de** y **Hasta** para definir el rango de garantías para el cálculo.
1. En la ficha desplegable **Registros para incluir**, puede configurar filtros para limitar el conjunto de acuerdos que procesará el trabajo por lotes. Estas configuraciones funcionan de la misma forma que funcionan para otros tipos de trabajos por lotes.
1. En la ficha desplegable **Ejecutar en segundo plano** puede configurar el proceso por lotes y opciones de programación según sea necesario. Estas configuraciones funcionan de la misma forma que funcionan para otros tipos de trabajos por lotes.
1. Seleccione **Aceptar** para ejecutar y/o programar el cálculo.

### <a name="process-deals-by-using-the-rebate-workbench"></a>Procesar acuerdos utilizando el banco de trabajo de devoluciones

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

En lugar de procesar acuerdos o líneas de acuerdos específicos, use el *banco de trabajo de devoluciones* para procesar varios acuerdos al mismo tiempo. Opcionalmente, puede aplicar filtros de registro y / o configurar una programación periódica. No tiene que seleccionar ninguna fila. El sistema procesará todas las líneas que cumplan con los requisitos de fecha y filtro que configuró.

Para procesar acuerdos mediante el banco de trabajo de devoluciones, siga estos pasos.

1. Vaya a **Gestión de devoluciones \> Acuerdos de gestión de devoluciones \>Banco de trabajo de devoluciones**.
1. En el panel de acciones, en la pestaña **Banco de trabajo de devoluciones**, en el grupo **Proceso**, seleccione uno de los siguientes comandos:

    - **Proceso \> Provisión** - Aprovisione un conjunto de acumulaciones para cada línea de acuerdo relevante, pero no las publique.
    - **Proceso \> Gestión de devoluciones** - Procesar una serie de transacciones que proporcionen el valor de la devolución para cada línea de acuerdo.
    - **Proceso \> Cancelación** - Procese la desviación entre la provisión y la gestión de devolución que se contabiliza para cada transacción de origen por acuerdo de devolución y período especificado.

1. En el cuadro de diálogo **Gestión de devoluciones**, en la sección **Período**, establezca los campos **A partir de la fecha** y **Hasta la fecha** para definir el rango de fechas para el cálculo.
1. En la sección **Período garantizado**, configure los campos **A partir de** y **Hasta** para definir el rango de garantías para el cálculo.
1. En la ficha desplegable **Registros para incluir**, puede configurar filtros para limitar el conjunto de acuerdos que procesará el trabajo por lotes. Estas configuraciones funcionan de la misma forma que funcionan para otros tipos de trabajos por lotes.
1. En la ficha desplegable **Ejecutar en segundo plano** puede configurar el proceso por lotes y opciones de programación según sea necesario. Estas configuraciones funcionan de la misma forma que funcionan para otros tipos de trabajos por lotes.
1. Seleccione **Aceptar** para ejecutar y/o programar el cálculo.

## <a name="view-and-edit-rebate-management-transactions"></a>Ver y editar transacciones de gestión de devoluciones

Cuando procesa una o más transacciones, el sistema crea transacciones que puede ver y, quizás, editar antes de publicarlas.

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-deals-list-page"></a>Ver y editar las transacciones de gestión de devoluciones mediante la página de lista de ofertas de devoluciones

Para ver y editar las transacciones de gestión de devoluciones mediante la página de lista de ofertas de devoluciones, siga estos pasos.

1. Siga uno de estos pasos:

    - Seleccione el trato para ver las transacciones (por ejemplo, en la página [**Todos los acuerdos de gestión de devoluciones**](rebate-management-deals.md)). En el panel de acciones, en la pestaña **Gestión de acuerdos de devoluciones**, en el grupo **Transacciones**, seleccione **Transacciones** o **Transacciones garantizadas**, según el tipo de transacción que desee ver.
    - Abra un acuerdo (por ejemplo, en la página [**Todos los acuerdos de gestión de devoluciones**](rebate-management-deals.md)) para ver sus detalles. En la ficha desplegable **Gestión de devoluciones**, seleccione la línea de acuerdo de la que ver las transacciones. Luego, en la barra de herramientas, seleccione **Transacciones** o **Transacciones garantizadas**, según el tipo de transacción que desee ver. (Estos botones solo están disponibles para acuerdos en los que el campo **Reconciliar por** el campo está configurado en *Línea*).

1. La página **Transacciones de fecha de gestión de devoluciones** o **Transacciones de garantía de gestión de devoluciones** aparece. Contiene una cuadrícula, donde cada línea representa una colección de transacciones de un solo período de devolución o garantía. Seleccione una fila en la cuadrícula y luego, en el Panel de acciones, seleccione **Transacciones de origen** para ver las transacciones que pertenecen a esa fila.
1. La página que aparece muestra una lista de las transacciones del tipo seleccionado que pertenecen a la fila seleccionada. Cada transacción proporciona detalles relevantes, según el tipo de transacción. Para las transacciones de garantía, solo puede ver la lista. Para otros tipos de transacciones, puede realizar las siguientes acciones en esta página:

    - Para verificar el valor total de todas las transacciones reclamadas en la página, vea el campo **Cantidad reclamada**.
    - Para ver más información sobre cualquier transacción, selecciónela y luego seleccione la pestaña **General**, **Dimensión financiera**, o **Dimensión**.
    - Para ver las reducciones que se aplican, seleccione **Transacciones de reducción** en el Panel de acciones. Para más información, vea [Principios de reducción de devoluciones](rebate-reduction-principle.md).
    - Para marcar transacciones como reclamadas o no reclamadas si está utilizando un proceso de reclamaciones, seleccione las filas relevantes y luego, en el Panel de acciones, seleccione uno de los siguientes comandos. (Habilite los procesos de reclamaciones en la página [**Parámetros de gestión de devoluciones**](rebate-management-parameters.md)).

        - **Conjunto reclamado \> Todo** - Marque todas las transacciones como reclamadas.
        - **Conjunto reclamado \> Seleccionado** - Marque las transacciones seleccionadas como reclamadas.
        - **Conjunto no reclamado \> Todo** - Marque todas las transacciones como no reclamadas.
        - **Conjunto no reclamado \> Seleccionado** - Marque las transacciones seleccionadas como no reclamadas.

    - Seleccione **Correo** en el Panel de acciones para publicar el reclamo para todas las líneas relevantes. Si está utilizando un proceso de reclamos (cuando la opción **Usar proceso de reclamo** está habilitada en la página **Parámetros de gestión de descuentos**), solo las líneas que están marcadas como **Reclamado** se publican. De lo contrario, se contabilizan todas las transacciones de origen para la transacción de devolución seleccionada. El botón **Publicar** está disponible solo para transacciones de reembolso. No está disponible para transacciones de provisión y cancelación. En el cuadro de diálogo **Correo**, los campos **Partir de la fecha** y **Hasta la fecha** se establecen automáticamente. Establezca el campo **Fecha de publicación** y después seleccione **Aceptar**.
    - Para ajustar la cantidad que se muestra para cualquier transacción abierta o no contabilizada, seleccione la transacción y luego siga uno de estos pasos:

        - Edite el valor en el campo **Importe corregido**.
        - En el panel de acciones, seleccione **Establecer corrección**. Luego, en el cuadro de diálogo desplegable que aparece, en el campo **Importe corregido**, introduzca un valor.

> [!NOTE]
> Si usa un proceso de reclamaciones, cuando procese el siguiente período, la lista de transacciones incluirá todas las transacciones no reclamadas de la publicación anterior, más cualquier transacción nueva para el período seleccionado.

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-workbench"></a>Ver y editar las transacciones de gestión de devoluciones mediante el banco de trabajo de devoluciones

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Para ver y editar las transacciones de gestión de devoluciones mediante el banco de trabajo de devoluciones, siga estos pasos.

1. Vaya a **Gestión de devoluciones \> Acuerdos de gestión de devoluciones \>Banco de trabajo de devoluciones**.
1. Defina el campo **Mostrar** como *No publicado*.
1. La página **Banco de trabajo de devoluciones** muestra una lista de las transacciones. Cada transacción proporciona detalles relevantes. Estos detalles varían según el tipo de transacción. En esta página , puede realizar las acciones siguientes:

    - Para ver más información sobre cualquier transacción, selecciónela y luego seleccione la pestaña **General**, **Dimensión financiera**, o **Dimensión**.
    - Si está utilizando un proceso de reclamaciones, puede marcar las transacciones como reclamadas o no reclamadas. Seleccione las filas relevantes y, en el panel de acciones, en la pestaña **Banco de trabajo de devoluciones**, seleccione uno de los siguientes comandos. (Habilite los procesos de reclamaciones en la página [**Parámetros de gestión de devoluciones**](rebate-management-parameters.md).)

        - **Conjunto reclamado** - Marque las transacciones seleccionadas como reclamadas.
        - **Conjunto no reclamado** - Marque las transacciones seleccionadas como no reclamadas.

    - Para contabilizar la reclamación de una o más líneas, seleccione las líneas relevantes. En el panel de acciones, en la pestaña **Banco de trabajo de devoluciones**, seleccione **Contabilizar**. El botón **Contabilizar** está disponible para transacciones de provisión, devolución y cancelación. En el cuadro de diálogo **Correo**, los campos **Partir de la fecha** y **Hasta la fecha** se establecen automáticamente. Establezca el campo **Fecha de publicación** y después seleccione **Aceptar**.
    - Para ajustar la cantidad que se muestra para cualquier transacción abierta o no contabilizada, seleccione la transacción y luego siga uno de estos pasos:

        - Edite el valor en el campo **Importe corregido**.
        - En el panel de acciones, en la pestaña **Banco de trabajo de devoluciones**, seleccione **Establecer corrección**. Luego, en el cuadro de diálogo desplegable que aparece, en el campo **Importe corregido**, introduzca un valor.

> [!NOTE]
> Si usa un proceso de reclamaciones, cuando procese el siguiente período, la lista de transacciones incluirá todas las transacciones no reclamadas de la publicación anterior, más cualquier transacción nueva para el período seleccionado.

## <a name="post-rebates-transactions"></a>Transacciones post devoluciones

Para contabilizar el valor de una provisión procesada, el monto de la gestión de reembolsos y la cancelación, debe ejecutar el proceso de contabilización. El proceso de contabilización marca la provisión, la gestión de descuentos o las transacciones de cancelación como contabilizadas y crea la transacción de destino. Si no tiene que revisar la transacción de destino, estas transacciones se pueden configurar para que se registren automáticamente.

### <a name="set-up-the-system-to-post-all-target-transactions-automatically"></a>Configure el sistema para registrar todas las transacciones de destino automáticamente

Para configurar su sistema para que contabilice todas las transacciones de destino tan pronto como se generen por una provisión de registro, cantidad de gestión de descuento y cancelación, active la opción **Publicar diarios automáticamente** y/o **Publique automáticamente facturas de servicios** en la página **Parámetros de gestión de descuentos**. Para más información, vea [Parámetros de gestión de devolución](rebate-management-parameters.md).

### <a name="post-transactions-for-all-lines-for-one-or-more-deals"></a>Publicar transacciones para todas las líneas para uno o más acuerdos

Después de haber procesado las ofertas relevantes, siga estos pasos para revisar y publicar las transacciones generadas para todas las líneas de una o más ofertas.

1. Abra la [página de lista de ofertas de devolución](rebate-management-deals.md) apropiada para el tipo de acuerdo con el que desea trabajar.
1. Seleccione la fila para cada acuerdo que desee publicar (o abra el acuerdo que desea publicar).
1. En el panel de acciones, en la pestaña **Gestión de acuerdos de devoluciones**, en el grupo **Generar**, seleccione uno de los siguientes comandos:

    - **Publicar \> Provisión** - Publique las transacciones de acumulación disponibles que haya creado.
    - **Publicar \> Gestión de devolución** - Publique las transacciones de devolución disponibles que haya creado.
    - **Publicar \> Cancelar** - Publique las transacciones canceladas disponibles que haya creado.

1. En el cuadro de diálogo que aparece, establezca el campo **Fecha de publicación**. Entonces establezca los campos **A partir de** y **Hasta** para definir el rango de fechas para las transacciones que deben publicarse.
1. Seleccione **Aceptar** para publicar las transacciones.

### <a name="post-transactions-for-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Publicar transacciones para una o más líneas de acuerdo específicas para un acuerdo seleccionado

Después de haber procesado las ofertas relevantes, siga estos pasos para revisar y publicar las transacciones generadas para una o más líneas de ofertas específicas para una oferta específica. Este procedimiento se aplica solo para acuerdos en los que el campo **Reconciliar por** el campo está configurado en *Línea*.

1. Abra la [página de lista de ofertas de devolución](rebate-management-deals.md) apropiada para el tipo de acuerdo con el que desea trabajar.
1. Abra el acuerdo que tiene una línea para la que desea registrar transacciones.
1. Seleccione la pestaña **Líneas** en la esquina superior derecha.
1. En la ficha desplegable **Gestión de devoluciones**, seleccione la fila para cada línea de acuerdo que desee publicar.
1. En la barra de herramientas de la ficha desplegable **Gestión de devoluciones**, seleccione uno de los siguientes comandos. (Estos comandos solo están disponibles para acuerdos en los que el campo **Reconciliar por** el campo está configurado en *Línea*).

    - **Publicar \> Provisión** - Publique las transacciones de acumulación disponibles que haya creado.
    - **Publicar \> Gestión de devolución** - Publique las transacciones de devolución disponibles que haya creado.
    - **Publicar \> Cancelar** - Publique las transacciones canceladas disponibles que haya creado.

1. En el cuadro de diálogo que aparece, establezca el campo **Fecha de publicación**. Entonces establezca los campos **A partir de** y **Hasta** para definir el rango de fechas para las transacciones que deben publicarse.
1. Seleccione **Aceptar** para publicar las transacciones.

### <a name="post-transactions-using-a-batch-job"></a>Contabilizar transacciones mediante un trabajo por lotes

En lugar de publicar transacciones para acuerdos o líneas de acuerdos específicos, puede ejecutar un trabajo por lotes para publicar transacciones varios acuerdos al mismo tiempo. Opcionalmente, puede aplicar filtros de registro y / o configurar una programación periódica. Para publicar transacciones mediante un trabajo por lotes, siga estos pasos.

1. Siga uno de estos pasos:

    - Vaya a **Gestión de devoluciones \> Tareas periódicas \> Publicar \> Provisión** para registrar las transacciones de acumulación disponibles que ha creado.
    - Vaya a **Gestión de devoluciones \> Tareas periódicas \> Publicar \> Gestión de devolución** para registrar las transacciones de devolución disponibles que ha creado.
    - Vaya a **Gestión de devoluciones \> Tareas periódicas \> Publicar \> Cancelar** para registrar las transacciones de cancelación disponibles que ha creado.

1. En el cuadro de diálogo que aparece, en la ficha desplegable **Parámetros**, en la sección **Período**, establezca el campo **Fecha de publicación**. Entonces establezca los campos **A partir de** y **Hasta** para definir el rango de fechas para las transacciones que deben publicarse.
1. En la sección **Período garantizado**, configure los campos **A partir de** y **Hasta** para definir el rango para las garantías que deben publicarse.
1. En la ficha desplegable **Registros para incluir**, puede configurar filtros para limitar el conjunto de acuerdos que procesará el trabajo por lotes. Estas configuraciones funcionan de la misma forma que funcionan para otros tipos de trabajos por lotes.
1. En la ficha desplegable **Ejecutar en segundo plano** puede configurar el proceso por lotes y opciones de programación según sea necesario. Estas configuraciones funcionan de la misma forma que funcionan para otros tipos de trabajos por lotes.
1. Seleccione **Aceptar** para ejecutar y/o programar el cálculo.

### <a name="post-transactions-by-using-the-rebate-workbench"></a>Registrar transacciones utilizando el banco de trabajo de devoluciones

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Una vez que haya procesado las transacciones de provisión, devolución o cancelación, siga estos pasos para usar el banco de trabajo de devoluciones para revisar y registrar las transacciones generadas para una o más líneas de transacciones específicas para todas las ofertas.

1. Vaya a **Gestión de devoluciones \> Acuerdos de gestión de devoluciones \>Banco de trabajo de devoluciones**.
1. En la cuadrícula, seleccione la fila para cada línea de transacción que desee registrar. Puede seleccionar transacciones de provisión, devolución o cancelación no registradas. Se aplican las siguientes reglas:

    - El sistema también registrará todas las líneas que tengan el mismo valor de **Número de transacción de devolución** como las líneas que seleccione.
    - El sistema no registrará ninguna línea del tipo de transacción *Devolución* que no está marcada como reclamada.
    - Si selecciona líneas que ya se han contabilizado, el sistema omitirá las líneas contabilizadas.
    - El botón **Contabilizar** está disponible solo si selecciona al menos una línea no contabilizada.

1. En el panel Acciones, en la pestaña **Banco de trabajo de devoluciones** del grupo **Proceso**, seleccione **Contabilizar**.
1. En el cuadro de diálogo **Contabilizar**, establezca el campo **Fecha de contabilización**. Los campos de **Fecha de inicio** y **Fecha de finalización** se configuran automáticamente, en función de los primeros valores de **Fecha de inicio** y **Fecha de finalización** para las filas seleccionadas.
1. Seleccione **Aceptar** para publicar las transacciones.

## <a name="review-rebate-management-journals"></a><a name="review-journals"></a>Revisar los diarios de gestión de devoluciones

Una vez que se hayan contabilizado sus transacciones, puede revisar los diarios, documentos o artículos resultantes. Las transacciones de destino para devoluciones y regalías se basan en el tipo de pago que se establece en el perfil de contabilización y el tipo de salida de la devolución. Por ejemplo, si la salida de la devolución se establece en *Artículo*, se creará una orden de venta para una devolución de cliente y se creará una orden de compra para una devolución de proveedor. Estos pedidos se pueden ver a través de las transacciones de destino. Alternativamente, si el pago está configurado para usar Proveedores, se creará una factura de proveedor para el proveedor que se configura en el cliente para los reembolsos del cliente.

### <a name="review-journals-by-using-the-rebate-deals-list-page"></a>Revise los diarios utilizando la página de lista de acuerdos de devoluciones

Para revisar los asientos de diario que están asociados con un acuerdo de gestión de devolución, siga estos pasos.

1. Abra la [página de lista de ofertas de devolución](rebate-management-deals.md) apropiada para el tipo de acuerdo con el que desea trabajar.
1. Seleccione el acuerdo para inspeccionar las entradas del diario.
1. En el panel de acciones, en la pestaña **Gestión de acuerdos de devoluciones**, en el grupo **Transacciones**, seleccione **Transacciones** o **Transacciones de garantía**, según el tipo de transacciones que desee ver.
1. Defina el campo **Mostrar** como *Todo* o *Contabilizado*.
1. Busque y seleccione la colección de transacciones que desea inspeccionar y luego, en el Panel de acciones, seleccione uno de los siguientes botones. (Estos botones están disponibles solo cuando existen publicaciones relevantes para la colección de transacciones seleccionada).

    - **Transacciones objetivo** - Revisar diarios relevantes y otros tipos de documentos que fueron generados por el acuerdo seleccionado.
    - **Artículos** - Revise las órdenes de venta o las órdenes de compra relevantes que fueron generadas por la oferta seleccionada.

1. Aparece una lista de diarios, documentos o elementos relevantes. Para ver más información sobre cualquier diario, documento o artículo, seleccione su fila y luego, en el Panel de acciones, seleccione **Ver detalles**.

### <a name="review-journals-by-using-the-rebate-workbench"></a>Revisar los diarios utilizando el banco de trabajo de devoluciones

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Para revisar diarios mediante el banco de trabajo de devoluciones, siga estos pasos.

1. Vaya a **Gestión de devoluciones \> Acuerdos de gestión de devoluciones \>Banco de trabajo de devoluciones**.
1. Defina el campo **Mostrar** como _Todo_ o _Contabilizado_.
1. Busque y seleccione la línea que se desea analizar. En el panel Acciones, en la pestaña **Banco de trabajo de devoluciones** del grupo **Ver**, seleccione **Transacciones de destino**. Este botón está disponible solo si existen contabilizaciones relevantes para la línea seleccionada.
1. Aparece una lista de diarios, documentos o elementos relevantes. Para ver más información sobre cualquier diario, documento o artículo, seleccione su fila y luego, en el Panel de acciones, seleccione **Ver detalles**.

## <a name="rebate-management-transactions-on-the-deduction-workbench"></a>Transacciones de gestión de devoluciones en el banco de trabajo de deducción

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Cuando registra una transacción de gestión de devoluciones que tiene uno de los siguientes valores de **Tipo de pago**, el sistema crea un diario de deducción de cliente o una factura de servicios para la cuenta de cliente relevante:

- Deducciones de clientes
- Deducciones de clientes de facturas de impuestos
- Gastos comerciales
- Notificación

Una vez creada y publicada una transacción de destino, estará disponible como una transacción abierta en la página **Banco de trabajo de deducciones** (**Ventas y marketing \> Derechos comerciales \> Deducciones \> Banco de trabajo de deducción**). Las transacciones abiertas tienen un valor de **Tipo de reclamación** de *Gestión de devoluciones* y un valor de **Número de transacción de devolución** está disponible para permitir la trazabilidad. La fecha se establece en la fecha de contabilización de la transacción de destino de la gestión de devoluciones. Para usar el banco de trabajo de deducción para liquidar transacciones abiertas con deducciones existentes para la misma cuenta de cliente, seleccione **Mantener\>Coincidencia** en el Panel de acciones.

Para obtener más información, consulte [Gestionar las deducciones utilizando el banco de trabajo de deducciones](deduction-workbench.md).

## <a name="purge-unposted-transactions"></a>Purgar transacciones no contabilizadas

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Una vez que haya procesado las transacciones de provisión, devolución o cancelación, siga estos pasos para depurar las transacciones seleccionadas no contabilizadas.

1. Vaya a **Gestión de devoluciones \> Acuerdos de gestión de devoluciones \>Banco de trabajo de devoluciones**.
2. Defina el campo **Mostrar** como *No publicado*.
3. Busque y seleccione las transacciones que desee eliminar. En el panel Acciones, en la pestaña **Banco de trabajo de devoluciones** del grupo **Proceso**, seleccione **Purgar**.
4. Seleccione **Aceptar** para eliminar las transacciones no contabilizadas.

## <a name="cancel-a-posted-provision"></a>Cancelar una provisión publicada

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Una vez que haya procesado y publicado una provisión, siga estos pasos para cancelar las transacciones de provisión publicadas.

1. Vaya a **Gestión de devoluciones \> Acuerdos de gestión de devoluciones \>Banco de trabajo de devoluciones**.
2. Defina el campo **Mostrar** como *Publicado*.
3. Busque y seleccione las transacciones de provisión que desee cancelar. En el panel Acciones, en la pestaña **Banco de trabajo de devoluciones** del grupo **Proceso**, seleccione **Cancelar provisión**.
4. Seleccione **Aceptar** para revertir las transacciones.

Estas reversiones de provisiones también serán visibles en los [Diarios de gestión de devoluciones](#review-journals).
