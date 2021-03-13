---
title: Integrar las adquisiciones entre Supply Chain Management y Field Service
description: Este tema describe cómo la integración de escritura dual admite la creación de pedidos de compra y las actualizaciones de Supply Chain Management y Field Service.
author: RichardLuan
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: c2b0d5be38425b5ceebb38b7964f5ec600b1c838
ms.sourcegitcommit: ca05440ee503bf15fe98fe138d317c1cdf21ad16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "5141913"
---
# <a name="integrate-procurement-between-supply-chain-management-and-field-service"></a>Integrar las adquisiciones entre Supply Chain Management y Field Service

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Microsoft Dynamics 365 Supply Chain Management proporciona una sólida funcionalidad de adquisición. Dynamics 365 Field Service ofrece una funcionalidad similar que admite los procesos de compra asociados con el proceso de servicio. La funcionalidad de estas dos aplicaciones se integra mediante escritura dual, y los casos de uso multifuncionales resultantes se habilitan mediante asignaciones de tablas, lógica de solución, vistas y formularios.

Esta integración admite la creación de pedidos de compra y, en la mayoría de los casos, las actualizaciones de ambas aplicaciones. Sin embargo, Supply Chain Management controla los precios, las direcciones y la recepción del producto. Se habilitan varios casos de uso de funciones cruzadas de gran alcance para las organizaciones que utilizan tanto Field Service como Supply Chain Management. Estos casos de uso permiten iniciar y realizar un seguimiento de las adquisiciones en ambos sistemas.

La siguiente ilustración muestra las tablas en ambos sistemas y cómo se asignan entre sí. Los pedidos de compra en Field Service hacen referencia a una fila *Cuenta*, mientras que los pedidos de compra en Supply Chain Management hacen referencia a una fila *Proveedor*. Para resolver la integración, la escritura dual usa una referencia para vincular filas de *Proveedor* con filas de *Cuenta*. Para obtener más información, consulte [Lista maestra de proveedores integrada](vendor-mapping.md).

![Asignaciones para adquisiciones](media/scm-field-service-tables.png)

## <a name="prerequisites"></a>Requisitos previos

Para integrar Supply Chain Management con Field Service, debe instalar los siguientes componentes:

- Versión de Field Service 8.8.31.60 o posterior, para una integración completa del pedido de compra
- Supply Chain Management versión 10.0.14 o posterior
- Escritura doble, para ejecutar la solución OneFSSCM

## <a name="installation-guidelines"></a>Directrices de instalación

### <a name="prerequisites"></a>Requisitos previos

+ **Escritura dual** - Para obtener más información, consulte la [página de inicio de doble escritura](dual-write-home-page.md#dual-write-setup).
+ **Dynamics 365 Field Service** - Para obtener más información consulte [Cómo instalar Dynamics 365 Field Service](https://docs.microsoft.com/dynamics365/field-service/install-field-service#step-1-install-dynamics-365-field-service).

Cuando están habilitados en Microsoft Dataverse, la escritura dual y Field Service presentan varias capas de soluciones que amplían el entorno con nuevos metadatos, formularios, vistas y lógica. Estas soluciones se pueden habilitar en cualquier orden, aunque normalmente se instala en el orden que se indica aquí:

1. **Field Service Common** - Field Service Common se instala cuando Field Service está instalado en el entorno.
2. **Field Service (Anchor)** - Field Service (Anchor) se instala cuando Field Service está instalado en el entorno. 
3. **Supply Chain Management Extended** - Supply Chain Management Extended se instala automáticamente cuando se habilita la escritura dual en un entorno. 
4. **Solución OneFSSCM** - OneFSSCM se instala automáticamente con cualquier solución (Field Service o Supply Chain Management) que se instale en último lugar.

    + Si Field Service ya está instalado en el entorno y habilita la escritura dual, que instala Supply Chain Management Extended, OneFSSCM está instalado.
    + Si Supply Chain Management Extended ya está instalado en el entorno e instala Field Service, OneFSSCM está instalado.

## <a name="initial-synchronization"></a>Sincronización inicial

Para crear nuevos pedidos de compra y trabajar con pedidos de compra existentes, debe sincronizar los datos de referencia entre Supply Chain Management y Dataverse. Utilice la funcionalidad de escritura inicial para detectar las relaciones de la tabla y encontrar las tablas que debe habilitar para un mapa determinado.

Debe sincronizar las siguientes tablas:

- Plantillas de productos

    Cuando ejecuta la escritura inicial, obtiene una lista completa de las tablas necesarias. Algunos ejemplos de estas plantillas son:

    - Todos los productos
    - Productos liberados V2
    - Productos únicos emitidos por Dataverse

- Sitios
- Almacenes
- Plantillas de categorías de adquisiciones

    Algunos ejemplos de estas plantillas son:

    - Categorías de adquisición
    - Pro
    - Jerarquía de categoría de productos
    - Asignaciones de categorías de producto

- Plantillas de proveedor, como Vendor V2
- Plantillas de personas de contacto, como Dataverse Contacts V2
- Plantillas de trabajador, como Worker

La sincronización de las tablas asegura que todos los documentos (pedidos de compra y recibos de productos) en Supply Chain Management estén disponibles en Dataverse.

### <a name="account-and-vendor-tables"></a>Tablas Cuenta y Proveedor

Los pedidos de compra en Field Service se basan en la tabla Cuenta para realizar un seguimiento de los proveedores. Por lo tanto, las tablas de Dataverse para pedidos de compra usan cuentas para rastrear proveedores. Para adaptarse a esta diferencia clave, se deben activar los siguientes cuatro flujos de trabajo para mantener las cuentas y los proveedores sincronizados: 

- Crear Proveedores en tabla Cuentas
- Crear Proveedores en tabla Proveedores
- Actualizar Proveedores en tabla Cuentas
- Actualizar Proveedores en tabla Proveedores

Si OneFSSCM está instalado, debido a que tanto Field Service como Supply Chain Management Extended están instalados, estos flujos de trabajo se activan automáticamente. Si Field Service no está instalado, pero desea integrar las tablas de pedidos de compra con Dataverse, debe activar estos flujos de trabajo. En ambos casos, a menos que empiece desde cero, es posible que deba asegurarse de que todos los proveedores se creen como cuentas en Dataverse antes de crear pedidos de compra. De lo contrario, podrían producirse errores.

### <a name="initial-synchronization"></a>Sincronización inicial

Una vez que se cumplan todos los requisitos previos, si desea que los pedidos de compra y los recibos de productos existentes estén disponibles en ambos sistemas, debe realizar una sincronización inicial de las siguientes plantillas:

- Encabezado del pedido de compra V2
- Línea de pedido de compra de CDS
- Eliminación temporal de Línea de pedido de compra de CDS
- Recibo del pedido de compra
- Recepción de producto de pedido de compra

## <a name="mappings-with-logic"></a>Asignaciones con lógica

La integración de adquisiciones amplía el mapeo del producto con la siguiente lógica para garantizar que la columna **Tipo de producto de Field Service** está configurada correctamente en la tabla de productos en Dataverse:

- Si **Tipo de producto** se establece en *Producto* y **Grupo de modelo de artículo, producto en stock** se establece en *Verdadero*, **el Tipo de producto de Field Service** se establece en *Inventario*.
- Si **Tipo de producto** se establece en *Producto* y **Grupo de modelo de artículo, producto en stock** se establece en *Falso*, **el Tipo de producto de Field Service** se establece en *No de inventario*.
- Si el **Tipo de producto** se establece en *Servicio*, **Tipo de producto de Field Service** se establece en *Servicio*.

Adicionalmente, Dataverse incluye lógica que asigna a los proveedores a sus cuentas relacionadas. Esta lógica establece la cuenta de proveedor de facturas predeterminada. Durante la creación, la lógica del complemento del lado del servidor establece la cuenta del proveedor de facturas predeterminada del proveedor que está relacionado con la cuenta. El proveedor tiene una referencia a la cuenta de factura que se utiliza para establecer este valor.

## <a name="supported-scenarios"></a>Escenarios admitidos

+ Los pedidos de compra se pueden crear y actualizar mediante usuarios de Dataverse. Sin embargo, el proceso y los datos están controlados por Supply Chain Management. Las restricciones sobre las actualizaciones de las columnas de pedidos de compra en Supply Chain Management se aplican cuando las actualizaciones provienen de Field Service. Por ejemplo, no puede actualizar un pedido de compra si se ha finalizado. 
+ Si el pedido de compra está controlado por la gestión de cambios en Supply Chain Management, un usuario de Field Service puede actualizar el pedido de compra solo cuando el estado de aprobación de Supply Chain Management es *Borrador*.
+ Varias columnas son administradas solo por Supply Chain Management y no se pueden actualizar en Field Service. Para saber qué columnas no se pueden actualizar, revise las tablas de asignación en el producto. En aras de la simplicidad, la mayoría de estas columnas están configuradas como de solo lectura en páginas de Dataverse. 

    Por ejemplo, Supply Chain Management administra las columnas para la información de precios. Supply Chain Management tiene acuerdos comerciales de los que Field Service puede beneficiarse. columnas como **Precio unitario**, **Descuento** e **Importe neto** provienen únicamente de Supply Chain Management. Para asegurarse de que el precio esté sincronizado con Field Service, debe utilizar la característica **Sincronización** en las páginas **Pedido de compra** y **Producto de pedido de compra** en Dataverse cuando se hayan introducido los datos del pedido de compra. Para más información, ver [Sincronizar con los datos de adquisiciones bajo demanda de Dynamics 365 Supply Chain Management](#sync-procurement).

+ La columna **Totales** está disponible solo en Field Service, porque no hay totales actualizados del pedido de compra en Supply Chain Management. Los totales en Supply Chain Management se calculan en función de varios parámetros que no están disponibles en Field Service.
+ Las líneas de pedido de compra donde solo se especifica una categoría de compra, o donde el producto que se especifica es un artículo del tipo de producto *Servicio* o tipo de producto de Field Service, solo se puede iniciar en Supply Chain Management. A continuación, las líneas se sincronizan con Dataverse y son visibles en Field Service.
+ Si solo se instala Field Service, y no Supply Chain Management, la columna **Almacén** es obligatoria en el pedido de compra. Sin embargo, si Supply Chain Management está instalado, este requisito se relaja, porque Supply Chain Management permite líneas de pedidos de compra donde no se especifica ningún almacén en determinadas situaciones.
+ Recibos de productos (recibos de pedidos de compra en Dataverse) son administrados por Supply Chain Management y no se pueden crear desde Dataverse si está instalado Supply Chain Management. Los recibos de productos de Supply Chain Management se sincronizan desde Supply Chain Management a Dataverse.
+ Se permite la entrega insuficiente en Supply Chain Management. La solución OneFSSCM agrega lógica para que, cuando la línea de recepción del producto (o el producto de recepción de la orden de compra en Dataverse) se crea o actualiza, se cree una fila de diario de inventario en Dataverse para ajustar la cantidad restante que está en orden para escenarios de entrega insuficiente.

## <a name="unsupported-scenarios"></a>Escenarios no admitidos

+ Field Service evita que se agreguen líneas a un pedido de compra cancelado en Supply Chain Management. Como solución alternativa, puede cambiar el estado del sistema del pedido de compra en Field Service y luego agregar la nueva línea en Field Service o Supply Chain Management.
+ Aunque las filas de adquisición afectan los niveles de inventario en ambos sistemas, esta integración no garantiza la alineación del inventario en Supply Chain Management y Field Service. Tanto Field Service como Supply Chain Management tienen otros procesos que actualizan los niveles de inventario. Estos procesos están fuera del alcance de las adquisiciones.

## <a name="status-management"></a>Administración de estado

Los estados de las órdenes de compra en Field Service difieren de los estados en Supply Chain Management.

### <a name="field-service-purchase-order-and-purchase-order-product-statuses"></a>Pedido de compra de Field Service y estados de producto de pedido de compra

| Encabezado: estado del sistema | Encabezado: estado de aprobación | Estado del artículo |
|---|---|---|
| <ul><li>Borrador</li><li>Emitido</li><li>Cancelada</li><li>Producto recibido</li><li>Facturado</li></ul> | <ul><li>Nulo</li><li>Aprobada</li><li>Rechazadas</li></ul> | <ul><li>Pendientes</li><li>Recibidos</li><li>Cancelada</li></ul> |

### <a name="supply-chain-management-purchase-order-and-purchase-order-line-statuses"></a>Pedido de compra de Supply Chain Management y estados de línea de pedido de compra

Los estados de aprobación de línea están activos solo cuando hay un flujo de trabajo de línea.

| Encabezado: estado de los documentos | Encabezado: estado de aprobación | Estado de línea | Estado de aprobación de línea |
|---|---|---|---|
| <ul><li>Pedido abierto (pedido pendiente)</li><li>Recibidos</li><li>Facturado</li><li>Cancelada</li></ul> | <ul><li>Borrador</li><li>En revisión</li><li>Aprobada</li><li>Rechazadas</li><li>En revisión externa</li><li>Confirmado</li><li>Finalizada</li></ul> | <ul><li>Pedido abierto (pedido pendiente)</li><li>Recibidos</li><li>Facturado</li><li>Cancelada</li></ul> | <ul><li>No enviado</li><li>En revisión</li><li>Aprobada</li><li>Rechazadas</li></ul> |

Las siguientes reglas se aplican a las columnas de estado:

+ El estado en Supply Chain Management no se puede actualizar desde Field Service. Sin embargo, en algunos casos, el estado en Field Service se actualizará cuando se cambie el estado del pedido de compra en Supply Chain Management.
+ Si un pedido de compra en Supply Chain Management está bajo gestión de cambios y se está procesando un cambio, el estado de aprobación es *Borrador* o *En revisión*. En este caso, el estado de aprobación de Field Service se establecerá en *Nulo*.
+ Si el estado de aprobación del pedido de compra en Supply Chain Management se establece en *Aprobado*, *En revisión externa*, *Confirmado* o *Finalizado*, el estado de aprobación del pedido de compra de Field Service se establecerá en *Aprobado*.
+ Si el estado de aprobación del pedido de compra en Supply Chain Management se establece en *Rechazado*, el estado de aprobación del pedido de compra de Field Service se establecerá en *Rechazado*.
+ Si el estado del encabezado del documento en Supply Chain Management se cambia a *Pedido abierto (pedido pendiente)* y el estado del pedido de compra de Field Service es *Borrador* o *Cancelado*, el estado del pedido de compra de Field Service se cambiará a *Emitido*.
+ Si el estado del encabezado del documento en Supply Chain Management se cambia a *Cancelado*, y ningún producto de recepción de pedido de compra en Field Service está asociado con el pedido de compra (a través de productos de pedidos de compra), el estado del sistema de Field Service se establece en *Cancelado*.
+ Si el estado de la línea de pedido de compra en Supply Chain Management es *Cancelado*, el estado del producto del pedido de compra en Field Service se establece en *Cancelado*. Además, si el estado de la línea del pedido de compra en Supply Chain Management cambia de *Cancelado* a *Pedido pendiente*, el estado del artículo de producto del pedido de compra en Field Service se establece en *Pendiente*.

## <a name="sync-with-the-supply-chain-management-procurement-data-on-demand"></a><a id="sync-procurement"></a>Sincronizar con los datos de adquisición a petición de Supply Chain Management

Supply Chain Management incluye datos de adquisiciones que manejan acuerdos comerciales, descuentos y otros escenarios que dependen de procesos secundarios en Supply Chain Management. El motor de adquisición utiliza reglas complejas para determinar el mejor precio para un pedido de compra. Cuando usa escritura dual, los datos no siempre se mantienen sincronizados en los dos entornos, especialmente en escenarios donde la fila se creó o se actualizó desde Dataverse, y podría desencadenar procesos de seguimiento en Supply Chain Management.

## <a name="sync-the-procurement-data-from-supply-chain-management"></a>Sincronizar con los datos de adquisición de Supply Chain Management

1. En Dataverse, vaya a **Inventario \> Pedido de compra**.
2. Seleccione **Nuevo** para crear un nuevo pedido o seleccione la fila para un pedido existente.
3. Desde el pedido de compra o la línea del pedido de compra.
4. En el panel Acciones, seleccione **Sincronización**.

Todas las columnas de Dataverse y Field Service que son compartidas por Supply Chain Management se sincronizan.

Estas son las situaciones en las que puede usar la función **Sincronización**:

- Si realiza varios cambios sucesivos en la misma fila desde Dataverse, ejecute la función **Sincronización**.
- Si no está seguro de si un cambio podría ser el segundo cambio sucesivo de Dataverse, podría tener sentido ejecutar la función **Sincronización**.
- Si recibe un mensaje de error sobre la actualización de un valor de Supply Chain Management, ejecute la **Sincronización** y vuelva a intentar la actualización en Dataverse.

## <a name="cancelling-the-posting-process"></a>Cancelar el proceso de registro

Si el proceso de registro de la recepción del producto se cancela durante el procesamiento, la escritura dual podría crear una fila de Dataverse, pero no crear una fila de recepción de producto en Supply Chain Management. Esta situación ocurre porque la escritura dual no admite transacciones distribuidas.

## <a name="templates"></a>Plantillas

Las siguientes plantillas están disponibles para la integración de documentos relacionados con adquisiciones.

| Gestión de la cadena de abastecimiento | Field Service | Descripción |
|---|---|---|
| Encabezado de pedido de compras V2 | msdyn\_Purchaseorders | Esta tabla contiene las columnas que representan el encabezado del pedido de compra. |
| Entidad de línea de pedido de compra | msdyn\_PurchaseOrderProducts | Esta tabla contiene las filas que representan las lineas en un pedido de compra. El número de producto se usa para la sincronización. Esto identifica el producto como una unidad de mantenimiento de existencias (SKU), incluidas las dimensiones del producto. Para obtener más información sobre la integración de productos con Dataverse, consulte [Experiencia unificada del producto](product-mapping.md). |
| Encabezado de recepción de producto | msdyn\_purchaseorderreceipts | Esta tabla contiene los encabezados de recepción de productos que se crean cuando se registra una recepción de producto en Supply Chain Management. |
| Línea de recepción de producto | msdyn\_purchaseorderreceiptproducts | Esta tabla contiene las líneas de recepción de productos que se crean cuando se registra una recepción de producto en Supply Chain Management. |
| Entidad de línea de pedido de compra eliminada provisionalmente | msdyn\_purchaseorderproducts | Esta tabla contiene información sobre las líneas de pedido de compra que se eliminan temporalmente. Una línea de pedido de compra en Supply Chain Management se puede eliminar temporalmente solo cuando el pedido de compra ha sido confirmado o aprobado, si la gestión de cambios está activada. La fila existe en la base de datos de Supply Chain Management y está marcada como **IsDeleted**. Ya que Dataverse no admite la eliminación temporal, es importante que esta información se sincronice con Dataverse. De esta manera, las líneas que se eliminan temporalmente en Supply Chain Management se pueden eliminar automáticamente de Dataverse. En este caso, la lógica para borrar una línea en Dataverse se encuentra en Supply Chain Management Extended. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Currency](includes/productreceiptheader-msdyn-purchaseorderreceipts.md)]

[!include [Currency](includes/productreceiptline-msdyn-purchaseorderreceiptproducts.md)]

[!include [Currency](includes/purchaseorderheadersv2-msdyn-purchaseorders.md)]

[!include [Currency](includes/purchaseorderlinesoftdeletedtable-msdyn-purchaseorderproducts.md)]

[!include [Currency](includes/purchaseorderlinetable-msdyn-purchaseorderproducts.md)]
