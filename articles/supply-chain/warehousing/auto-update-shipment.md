---
title: Actualizaciones automáticas de envíos
description: Este tema proporciona una visión general de la funcionalidad que proporciona las actualizaciones automáticas para envíos.
author: josaw1
manager: tfehr
ms.date: 11/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable,SalesTableListPage,SalesTable,WHSWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7fa2684340f5ce45b99ff9aee9937071f936b81a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436651"
---
# <a name="shipment-auto-updates"></a>Actualizaciones automáticas de envíos

[!include [banner](../includes/banner.md)]

La funcionalidad de envío automático actualiza automáticamente cantidades (aumentos y disminuciones) en una línea de carga que está asociada a un envío, después de que la carga se haya liberado a un almacén. Esta funcionalidad sigue activada hasta que la línea de carga del envío o la carga se procesa en una oleada. Cuando se usa, las actualizaciones de pedidos pueden ir automáticamente al almacén, sin requerir la intervención manual, hasta que se cree el trabajo del almacén se cree.

Cuando la funcionalidad de envío de actualización automática no se utiliza, sólo fluyen las disminuciones de la cantidad automáticamente hasta que se crea el trabajo del almacén. Los usuarios deben actualizar o eliminar manualmente las líneas, y deben a continuación volver a liberar las líneas si se aumentan cantidades de pedido o se agregan nuevas líneas de pedido. Mediante la funcionalidad de envío de actualización automática, las empresas pueden proporcionar actualizaciones continuamente al almacén sin tener que preocuparse por que los envíos y las cargas relacionados no reflejen actualizaciones de la línea de pedido.

La funcionalidad de envío de actualización automática se aplica a las líneas de pedido de ventas y a las líneas de pedido de transferencia, y está activada para un almacén específico. Por lo tanto, las empresas pueden aplicar diferentes directivas de actualización automática a través de los almacenes, según las necesidades. De forma predeterminada, la directiva de envío de actualización automática para disminuciones de la cantidad se aplica a todos los almacenes que utilicen procesos de gestión de almacenes. Cuando se usa este valor de la directiva predeterminada, sólo fluyen las disminuciones de la cantidad automáticamente a un envío y una carga hasta que se cree el trabajo del almacén. Este comportamiento se parece al comportamiento usado antes de que la funcionalidad de envío de actualización automática fuera especificada.

## <a name="main-elements-of-the-functionality"></a>Elementos principales de la funcionalidad

La funcionalidad de envío de actualización automática se basa principalmente en el estado de envío para determinar si la cantidad en una línea de carga debe cambiarse al realizar un cambio en una línea de pedido de ventas o una línea de pedido de transferencia. También se basa principalmente en el estado de envío para determinar cuándo una nueva línea de carga se debe agregar automáticamente a una carga existente. Cuando el estado de envío es **Oleada** o superior, ninguna actualización automática se produce.

El estado de la oleada también se considera para las actualizaciones automáticas. Cuando la oleada relacionada con la línea de carga tiene un estado **Retenido**, **En ejecución**, **Liberado**, **Seleccionado**, o **Enviado**, si un usuario intenta para reducir la cantidad en una línea de carga (mediante una reducción de la cantidad en la línea de pedido de ventas o la línea de pedido de transferencia), se muestra el siguiente mensaje de error: "Las reservas no se pueden quitar porque hay trabajo creado que depende de ellas". Además, cuando la oleada tiene uno de los estados de oleada anteriormente mencionados, si un usuario intenta indirectamente incrementar la cantidad de la línea de carga aumentando la cantidad en la línea de pedido de ventas o la línea de pedido de transferencia, la cantidad de la línea de carga no aumenta automáticamente. En este caso, la línea de carga se debe actualizar manualmente.

## <a name="scenarios"></a>Situaciones

La funcionalidad de envío de actualización automática admite cuatro escenarios: agregar una nueva línea de pedido, incrementar la cantidad en una línea de pedido, reducir la cantidad en una línea de pedido, y quitar una línea de pedido.

- **Agregar una nueva línea de pedido** Cuando el campo **Envío de actualización automática** en la ficha desplegable de la página **Almacén** de la página **Almacenes** (**Administración de almacenes \> Configuración \> Almacén \> Almacenes**) se establece en **Siempre**, si existe un envío para el pedido y una nueva línea de pedido se agrega a un pedido de ventas o a un pedido de transferencia después de que una carga se haya creado previamente para el pedido de ventas, la carga existente no se actualiza. Una nueva línea de carga que no tiene ninguna referencia a la carga existente se crea y se asocia al envío existente. La nueva línea se agrega a la carga y se libera.
- **Aumentar la cantidad en una línea de pedido** Cuando el campo **Envío de actualización automática** se establece en **Siempre**, si existe un envío para el pedido, y la cantidad en una línea de pedido de ventas o una línea de pedido de transferencia aumenta después de que una carga ya se haya creado para el pedido de ventas, la línea de carga aumenta en la misma cantidad que la línea de pedido. Si la carga se liberó, pero no se creó ningún trabajo, la línea de carga aumenta en la misma cantidad que la línea de pedido.
- **Reducir la cantidad en una línea de pedido** Cuando el campo **Envío de actualización automática** se establece en **Siempre** o en **Al reducir la cantidad**, si existe un envío para el pedido, y la cantidad en una línea de pedido de ventas o línea de pedido de transferencia disminuye después de que una carga ya se haya creado previamente para el pedido de ventas, la cantidad de la línea de carga asociada se actualizará para que coincida, a menos que la cantidad de dicha línea de carga ya sea igual o inferior a la nueva cantidad en la línea de pedido. En ese caso, la línea de carga no se ve afectada. Si la carga se liberó, pero no se creó ningún trabajo, la cantidad de la línea de carga asociada se actualizará para que coincida, a menos que la cantidad de la línea de carga ya sea igual o inferior a la nueva cantidad en la línea de pedido. En ese caso, la línea de carga se ve afectada.
- **Quite una línea de pedido** Cuando el campo **Envío de actualización automática** se establece en **Siempre** o **Al reducir la cantidad**, si el usuario intenta eliminar una línea de pedido para la que existe una línea de carga, se muestra un mensaje de error.

## <a name="example-scenario"></a>Supuesto de ejemplo

Para este escenario, los datos de prueba deben estar instalados y debe usar la compañía de los datos de prueba **USMF**.

### <a name="turn-on-the-auto-update-shipment-functionality"></a>Activar la funcionalidad de envío de actualización automática

Para activar la funcionalidad de envío de actualización automática, siga los pasos siguientes.

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Almacenes**.
2. Seleccione el almacén **24**.
3. En la ficha desplegable **Almacén**, en el campo **Envío de actualización automática**, cambie el valor de **Al reducir la cantidad** a **Siempre**.

Tras cambiar el valor a **Siempre**, todos los aumentos o disminuciones en las cantidades de las líneas de pedido de ventas y las líneas de pedido de transferencia, y cualquier adición de nuevas líneas, se reflejan en los envíos y las cargas para el almacén seleccionado, dadas las restricciones anteriormente mencionadas de actualización.

### <a name="change-the-wave-template-so-that-load-lines-arent-automatically-processed"></a>Cambiar la plantilla de la oleada para no procesar líneas de carga automáticamente

Para configurar la plantilla de la oleada de modo que no procese líneas de carga automáticamente, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.
2. Seleccione la plantilla **Plantilla predeterminada 24**.
3. Seleccione **Editar**.
4. En la ficha desplegable **General**, establezca la opción **Automatizar la creación de oleadas** en **Sí**, y asegúrese de que todas las demás opciones se establecen en **No**.

Es importante que no se cree ni se libere ningún trabajo automáticamente como parte del proceso de creación de la oleada. Una vez que se haya creado el trabajo relacionado con la línea de carga que se creó para la línea de pedido de ventas, la línea de carga ya no se actualiza automáticamente si la cantidad de la línea de pedido de ventas cambia.

### <a name="create-a-sales-order"></a>Crear un pedido de ventas

Para crear un pedido de ventas, siga estos pasos.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
2. Seleccione el cliente **US-003.**
3. Cree una línea para el número de artículo **A0001**.
4. Especifique una cantidad de **10**. (Asegúrese de que utiliza el almacén **24**).
5. Seleccione **Guardar**.
6. En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**. Se crean un envío y una oleada.

Dado que ha cambiado la plantilla de la oleada en el procedimiento anterior, no se creará ninguna carga o trabajo. El estado de envío es **Abierto**, y el estado de la oleada es **Creado**.

### <a name="decrease-the-quantity-on-a-sales-order-line"></a>Disminuir la cantidad de un pedido de ventas

Para reducir la cantidad en una línea de pedido de ventas, siga estos pasos.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
2. Seleccione el pedido de ventas que acaba de liberar al almacén.
3. Seleccione la línea del pedido de ventas. En el campo **Cantidad**, cambie el valor de **10** a **8**.
4. En la línea de pedido de ventas, seleccione **Almacén \> Detalles de envío**. En la página **Detalles de envío**, en la ficha desplegable **Líneas de carga**, la cantidad refleja el cambio en la línea de pedido de ventas.

### <a name="increase-the-quantity-on-a-sales-order-line"></a>Aumentar la cantidad de un pedido de ventas

Para aumentar la cantidad en una línea de pedido de ventas, siga estos pasos.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
2. Seleccione el pedido de ventas que liberó previamente al almacén.
3. Cambie la cantidad de la línea de **8** a **12**.
4. Seleccione **Guardar**.
5. Vuelva a la página **Todos los pedidos de venta** y seleccione el pedido de ventas otra vez.
5. En el panel de acciones, en la ficha **Almacén** del grupo **Información relacionada**, seleccione **Detalles de envío**. En la página **Detalles de envío**, en la ficha desplegable **Líneas de carga**, la cantidad refleja el cambio en la línea de pedido de ventas.

Aunque la cantidad de la línea de carga ha aumentado de 8 a 12, sólo hay ocho elementos que permanecen reservados, a menos que la reserva automática esté activada. Dado que la cantidad que se ha agregado al envío existente no se ha reservado, si la oleada se procesa en este punto, sin reserva, se crea trabajo únicamente para la cantidad que ya se ha reservado.

> [!NOTE]
> Si la cantidad en una línea de pedido se reduce, la cantidad de la línea de carga no se ve afectada si ya es igual o es inferior a la nueva cantidad en la línea de pedido. Si la cantidad en una línea de pedido aumenta, la línea de carga aumenta en la misma cantidad que la línea de pedido. Si la cantidad de la línea de pedido difiere de la cantidad en la línea de carga, la diferencia permanece.

### <a name="add-a-sales-order-line"></a>Agregar una línea de pedido de ventas

Para agregar una nota de pedido de ventas, siga estos pasos.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
2. Seleccione el pedido de ventas que liberó previamente al almacén.
3. Cree una línea para el número de artículo **A0002**.
4. En el campo **Cantidad**, especifique **10**. (Asegúrese de que utiliza el almacén **24**). La nueva línea se agrega automáticamente al envío existente.
5. Seleccione **Guardar**.
6. Vuelva a la página **Todos los pedidos de venta** y seleccione el pedido de ventas otra vez.
7. En el panel de acciones, en la ficha **Almacén** del grupo **Información relacionada**, seleccione **Detalles de envío**. En la página **Detalles de envío**, en la ficha desplegable **Líneas de carga**, observe la segunda línea de carga.

Dado que la línea de pedido de ventas que acaba de agregar al envío existente no se ha reservado, si la oleada se procesa en este punto, el trabajo se crea únicamente para la cantidad en la primera línea de pedido de ventas y la primera línea de carga.

### <a name="process-a-wave"></a>Procesar una oleada

Para procesar la oleada, siga estos pasos:

1. Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.
2. Seleccione la oleada creada anteriormente.
3. En el panel de acciones, en la pestaña **Oleada**, en el grupo **Oleada**, seleccione **Proceso**.

La oleada se procesa y crea el trabajo para las cantidades reservadas en las líneas de carga. El estado de envío se actualiza de **abierto** a **Oleada**. Como se actualiza el estado de envío a **Oleada**, todos los cambios que se produzcan, por ejemplo aumentos o disminuciones en cantidades de línea o la agregación de nuevas líneas al pedido de ventas, no afectan a las líneas existentes de carga asociadas al envío de la oleada.

Si un envío tiene el estado **Oleada** o mayor, las actualizaciones a la cantidad en una línea de pedido de ventas no se reflejan ni se validan con una línea de carga que esté asociada al envío. Los cambios en la cantidad en una línea de carga se deben realizar directamente en la línea de carga.

La validación se hace después de crear el trabajo para la línea de carga y de realizar una reserva. Una reducción de la cantidad en la línea de pedido de ventas se valida con la reserva de línea del trabajo.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]