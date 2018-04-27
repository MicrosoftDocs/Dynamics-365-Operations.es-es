---
title: "Configuración de entrega"
description: "Este tema explica cómo usar los procesos de entrada de inventario de envío."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ConsignmentDraftReplenishmentOrderJournal, ConsignmentProductReceiptLines, ConsignmentReplenishmentOrder, ConsignmentVendorPortalOnHand, InventJournalOwnershipChange, InventOnHandItemListPage, PurchTable, PurchVendorPortalConfirmedOrders, DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 220834
ms.assetid: 3c9d6de4-45d4-459a-aef7-0d9ad2c22b3a
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: df5862a75646976d315fa77531d7c4fe9b1ec499
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-consignment"></a>Configuración de entrega

[!INCLUDE [banner](../includes/banner.md)]

Este tema explica cómo usar los procesos de entrada de inventario de envío.

El inventario de envío es el inventario que es propiedad de un proveedor, pero se almacena en su ubicación. Cuando esté listo para consumir o usar el inventario, asume el control de la propiedad del inventario. Este tema incluye información acerca de cómo recibir físicamente el inventario disponible propiedad del proveedor sin crear transacciones de contabilidad general, cómo iniciar un proceso de producción en el que se pueda reservar físicamente el inventario propiedad del proveedor, y cómo cambiar la propiedad de la materia prima para poder procesar el consumo como parte del procesamiento del pedido de producción. También contiene información acerca de cómo los proveedores pueden controlar el consumo del inventario mediante la interfaz de colaboración de proveedor. 

## <a name="overview-of-the-consignment-process"></a>Información general del proceso de envío
En este ejemplo, la empresa USMF tiene un acuerdo de envío con el proveedor US-104 para la materia prima M9211CI.

1.  Una persona de USMF ha creado un pedido de reabastecimiento de envío en función de la demanda prevista. Se crea el pedido para el proveedor US-104 y se añade una línea para el artículo MS9211CI.
2.  Se informa al proveedor de la entrega esperada. Esto puede llevarse a cabo de una de estas tres maneras:
    -   Alguien que trabaja en USMF envía la información del pedido al proveedor.
    -   El proveedor puede controlar el inventario esperado disponible mediante la interfaz de colaboración de proveedor.
    -   Alguien que trabaja en USMF filtra los datos de la página **Inventario disponible** para mostrar solo los registros para el proveedor US-104, donde el estado del recibo es **Solicitado**, y después envía esta información al proveedor.
3.  El inventario se entrega de US-104 a USMF.
4.  Cuando el material llega a USMF, el pedido de reabastecimiento de envío se actualiza con un recibo de producto. Solo se registran las cantidades físicas del inventario propiedad del proveedor. No hay transacciones de contabilidad general creadas, ya que el inventario todavía es propiedad del proveedor.
5.  El proveedor controla las actualizaciones del inventario físico disponible mediante la página **Inventario disponible de envío**.
6.  Una vez el inventario físico está disponible, el proceso de producción reservar el inventario propiedad del proveedor e inicia una orden de producción para la mercancía terminada que va a consumir la materia prima M9211CI.
7.  El propietario de las materias primas reservadas que se van a consumir en la producción de hoy se cambia de US-104 a USMF. Esto se realiza mediante un diario de cambios de propiedad del inventario. Este proceso crea los pedidos de compra donde el campo **Origen** está establecido en **Envío**.
8.  El proveedor controla el consumo (cambio de propiedad) en la página **Productos recibidos de inventario de envío** y emite una factura en función de los acuerdos entre las dos empresas.
9.  El proceso de producción consume la materia prima mediante una lista de selección de producción. La reserva física se actualiza automáticamente para reflejar que el inventario disponible es propiedad de USMF.
10. La factura de US-104 se procesa con los pedidos de compra que se generaron automáticamente cuando se tramitó el diario de cambio de propiedad del inventario. El pago se realiza al proveedor US-104 por el inventario que se consumió.

USMF realiza procesos periódicos adicionales:

-   El movimiento de inventario físico propiedad del proveedor entre almacenes diferentes se procesa usando un diario de transferencia.
-   El inventario físico disponible se actualiza mediante un diario de **Recuento de artículo**. El recuento también se puede usar por parte del proveedor para actualizar el inventario disponible, si tiene permiso para ello.

El proveedor, US-104, puede controlar las actualizaciones mediante la página **Inventario disponible de envío**.

## <a name="consignment-replenishment-orders"></a>Pedidos de reabastecimiento de entrega
Un pedido de reabastecimiento de envío es un documento que se usa para solicitar y realizar un seguimiento de las cantidades de producto de inventario que un proveedor pretende entregar dentro de un intervalo de fechas concreto mediante la creación de transacciones de inventario solicitadas. Normalmente, esto se realiza en función del pronóstico y la demanda real de productos concretos. El inventario que va se va a recibir con el pedido de reabastecimiento de envío permanece siendo propiedad del proveedor. Únicamente se registra la propiedad de los productos relacionados con la actualización de la factura física y por tanto, no hay actualizaciones de la transacción de contabilidad general. 

La dimensión del **Propietario** se utiliza para separar la información sobre qué inventario es propiedad del proveedor y cuál es propiedad de la entidad jurídica receptora. Las líneas de pedido de reabastecimiento del envío tienen un estado de **Pedido abierto** siempre que la cantidad completa de las líneas no se haya recibido ni cancelado. Cuando la cantidad completa se ha recibido o cancelado, el estado se cambia a **Completado**. El inventario físico disponible relacionado con un pedido de reabastecimiento de envío se puede registrar mediante un Proceso de registro así como mediante un Proceso de actualización de recepción de producto. El registro se puede realizar como parte del proceso de recepción de artículo o actualizando manualmente las líneas de pedido. Cuando se usa el Proceso de actualización de la recepción de producto, se realiza un registro en el diario de recepción de producto, que puede usarse para confirmar la recepción de mercancías a los proveedores.

[![consignment-replenishment-order](./media/consignment-replenishment-order.png)](./media/consignment-replenishment-order.png)

## <a name="inventory-ownership-change-journal"></a>Diario de cambio de propiedad de inventario
El proceso de cambio de propietario de inventario del proveedor a la entidad jurídica receptora se realiza mediante un diario de cambio de propiedad de inventario. Para el diario, no se crean transacciones de inventario inesperadas. Las únicas transacciones de inventario que se crean son aquellas relacionadas con un diario registrado. Cuando se registra el diario:

-   El inventario propiedad del proveedor se emite mediante una referencia **Cambio de propiedad** con estado **Vendido**.
-   El inventario disponible se recibe por parte de la entidad jurídica consumidora mediante una transacción de inventario actualizada de recepción de producto del pedido de compra. Esto establece el estado del pedido a **Recibido**. Los pedidos de compra utilizados para el envío tienen el campo **Origen** establecido en **Envío**.

No es posible actualizar la cantidad de líneas de pedido de compra del envío después de que se haya creado el pedido.

[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Colaboración de proveedor en procesos de envío
La interfaz de colaboración del proveedor tiene tres páginas relacionadas con el proceso de entrada de envío:

-   **Pedidos de compra** **que consumen el inventario de envío** - Muestra información detallada del pedido de compra relacionada con el cambio de propiedad del proceso de envío.
-   **Productos recibidos de inventario de envío** - Muestra información sobre los artículos y las cantidades que tienen facturas de productos actualizados durante el proceso de cambio de propiedad.
-   **Inventario disponible de envío** - Muestra información sobre los artículos de envío que se esperan entregar, y los artículos que ya están físicamente disponibles en la ubicación del cliente.

## <a name="inventory-owners"></a>Propietarios de inventario
Para registrar el inventario entrante físico de envío, es necesario definir un propietario de proveedor. Esto se hace en la página **Propietario de inventario**. Al seleccionar **Cuenta de proveedor** se generan valores predeterminados para los campos **Nombre** y **Propietario**. El valor del campo **Propietario** estará visible para el proveedor, por lo que es posible que desee cambiarlo si los nombres de cuenta de sus proveedores no son fáciles de reconocer por parte de las entidades externas. Es posible editar el campo **Propietario**, pero solo hasta el punto al guardar el registro **Propietario de inventario**. El campo **Nombre** se rellena con el nombre de la parte a la que se asocia la cuenta del proveedor y no se puede cambiar.

[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)

## <a name="tracking-dimension-group"></a>Grupo de dimensiones de seguimiento
Los artículos que se van a usar en procesos de envío se deben asociar al **Grupo de dimensiones de seguimiento** donde la dimensión de **Propietario** está establecida en **Activa**. La dimensión de Propietario siempre tiene las opciones **Inventario físico** e **Inventario financiero** seleccionadas. El **Plan de cobertura por dimensión** nunca está seleccionado.

[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)

## <a name="inventory-ownership-change-journal"></a>Diario de cambio de propiedad de inventario
El diario de **Cambio de propiedad de inventario**se usa para registrar la transferencia de propiedad del inventario de envío del proveedor a la entidad jurídica que lo consume. Como cualquier diario de inventario, debe identificarse con un nombre de diario de inventario. Dichos nombres se crean en la página **Nombres de diario de inventario**, y el **Tipo de diario** se debe establecer en **Cambio de propiedad**.

[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Colaboración de proveedor en procesos de envío
Si los proveedores usan la interfaz de colaboración de proveedor, pueden usarla para controlar el consumo de inventario de su ubicación. Para obtener más información acerca de la configuración de los proveedores para utilizar la colaboración de proveedor, vea [Configuración de seguridad para los usuarios de colaboración de proveedor](../procurement/configure-security-vendor-portal-users.md).






