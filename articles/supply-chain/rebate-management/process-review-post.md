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
ms.openlocfilehash: 82b8a4e6ba7ebea7df9f5dad5abc3dfc3ce2687d
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270770"
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

## <a name="process-rebate-management-deals"></a>Procesar Acuerdos de gestión de devoluciones

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

## <a name="view-and-edit-rebate-management-transactions"></a>Ver y editar transacciones de gestión de devoluciones

Cuando procesa una o más transacciones, el sistema crea transacciones que puede ver y, quizás, editar antes de publicarlas.

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

## <a name="review-rebate-management-journals"></a>Revisar los diarios de gestión de devoluciones

Una vez que se hayan contabilizado sus transacciones, puede revisar los diarios, documentos o artículos resultantes. Las transacciones de destino para devoluciones y regalías se basan en el tipo de pago que se establece en el perfil de contabilización y el tipo de salida de la devolución. Por ejemplo, si la salida de la devolución se establece en *Artículo*, se creará una orden de venta para una devolución de cliente y se creará una orden de compra para una devolución de proveedor. Estos pedidos se pueden ver a través de las transacciones de destino. Alternativamente, si el pago está configurado para usar Proveedores, se creará una factura de proveedor para el proveedor que se configura en el cliente para los reembolsos del cliente.

Para revisar los asientos de diario que están asociados con un acuerdo de gestión de devolución, siga estos pasos.

1. Abra la [página de lista de ofertas de devolución](rebate-management-deals.md) apropiada para el tipo de acuerdo con el que desea trabajar.
1. Seleccione el acuerdo para inspeccionar las entradas del diario.
1. En el panel de acciones, en la pestaña **Gestión de acuerdos de devoluciones**, en el grupo **Transacciones**, seleccione **Transacciones** o **Transacciones de garantía**, según el tipo de transacciones que desee ver.
1. Asegúrese de que el campo **Mostrar** está configurado en *Todo* o *Publicado*.
1. Busque y seleccione la colección de transacciones que desea inspeccionar y luego, en el Panel de acciones, seleccione uno de los siguientes botones. (Estos botones están disponibles solo cuando existen publicaciones relevantes para la colección de transacciones seleccionada).

    - **Transacciones objetivo** - Revisar diarios relevantes y otros tipos de documentos que fueron generados por el acuerdo seleccionado.
    - **Artículos** - Revise las órdenes de venta o las órdenes de compra relevantes que fueron generadas por la oferta seleccionada.

1. Aparece una lista de diarios, documentos o elementos relevantes. Para ver más información sobre cualquier diario, documento o artículo, seleccione su fila y luego, en el Panel de acciones, seleccione **Ver detalles**.
