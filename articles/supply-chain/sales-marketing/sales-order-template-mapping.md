---
title: "Sincronizar encabezados y líneas de pedido de ventas de Finance and Operations en Sales"
description: "En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de pedidos de ventas de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c7b2ff6430e99661ee284f65089086df9fa5a1ad
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-from-finance-and-operations-to-sales"></a>Sincronizar encabezados y líneas de pedido de ventas de Finance and Operations en Sales

[!include[banner](../includes/banner.md)]

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de pedidos de ventas de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales. 

## <a name="template-and-tasks"></a>Plantilla y tareas

Las plantillas y las tareas subyacentes siguientes se usan para sincronizar encabezados y líneas del pedido de ventas de Finance and Operations a Sales:

- **Nombre de la plantilla en la integración de datos** 

    - Pedidos de ventas (de Fin and Ops a Sales)
    
- **Nombres de las tareas en el proyecto de integración de datos**

    - OrderHeader
    - OrderLine

Tareas de sincronización necesarias antes de sincronizar el encabezado y las líneas de factura en Sales:

- Productos (de Fin and Ops a Sales)
- Cuentas (de Sales a Fin and Ops), si es que se usan
- Contactos a Clientes (de Sales a Fin and Ops) si es que se usan

## <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations |    Common Data Service (CDS)         |     Ventas      |
|------------------------|----------------|----------------|
| Encabezados de pedido de ventas de CDS| SalesOrder     | SalesOrders |
| Líneas de pedido de ventas de CDS  | SalesOrderLine | SalesOrderDetails|

## <a name="entity-flow"></a>Flujo de la entidad

Los pedidos de ventas se crean en Finance and Operations y se sincronizan en Sales.

Los filtros de la plantilla le garantizan que solo se incluyan en la sincronización los pedidos de ventas más importantes:

- Asimismo, se incluirán en la sincronización los clientes de pedidos y facturación del pedido de ventas que se creó en Sales. En Finance and Operations, los campos **OrderingCustomerIsExternallyMaintained** y **InvoiceCustomerIsExternallyMaintained** se usan para realizar el seguimiento de la sincronización en las entidades de datos.

- Debe confirmar el **Pedido de ventas** en Finance and Operations. Solo se sincronizan en Sales los pedidos de ventas confirmados o los pedidos de ventas con un estado más alto de procesamiento como, por ejemplo, aquellos que tengan un estado de Enviado o Facturado.

- Después de crear o modificar un pedido de ventas, debe ejecutar el trabajo por lotes **Calcular las ventas totales** en Finance and Operations. Solo los pedidos de ventas que tengan las ventas totales calculadas se sincronizarán en CDS y Sales.

> [!NOTE]
> Los impuestos relacionados con los gastos en **Cabecera del pedido de ventas** no se incluyen actualmente en la sincronización de Finance and Operations a Sales. Esto se debe a que Sales no admite información fiscal en el nivel de la cabecera. Se incluyen los cargos relacionados con los impuestos a nivel de línea.

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales

Los nuevos campos se agregan a la entidad **Pedido** y se muestran en la página:

- **Se mantiene externamente**: establecido en **Sí** cuando el pedido proviene de Finance and Operations.

- **Estado de procesamiento**: se usa para mostrar el estado de procesamiento del pedido en Finance and Operations. Los valores son:

    - Activos
    - Confirmado
    - Albarán
    - Facturado
    - Seleccionado
    - Parcialmente seleccionado
    - Parcialmente empaquetado
    - Enviados
    - Parcialmente enviado
    - Parcialmente facturado
    - Cancelado

La configuración **Solo tiene productos mantenidos externamente** se usa en otros escenarios del pedido de ventas (sincronización de Sales a Finance and Operations) para realizar un seguimiento constante y así saber si el pedido de ventas está enteramente compuesto de **Productos mantenidos externamente**, en cuyo caso los productos se mantienen en Finance and Operations. Gracias a ello, se puede garantizar que no intenta sincronizar las líneas de pedido de ventas con productos desconocidos para Finance and Operations.
 
Los botones **Crear factura**, **Cancelar pedido**, **Recalcular**, **Obtener productos** y **Buscar dirección** de la página del **Pedido de ventas** se ocultan en los pedidos mantenidos de forma externa, ya que las facturas se crearán en Finance and Operations y se sincronizarán en Sales. No se puede editar la página del pedido porque la información del pedido de ventas se sincronizará desde Finance and Operations.
 
El **Estado del pedido de ventas** permanecerá activo para garantizar que los cambios de Finance and Operations se incluyen en el **Pedido de ventas** de Sales. Esta opción puede gestionarse si se configura el **código de estado [Status]** de forma predeterminada en **Activo** en el proyecto de integración de datos.

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación 

Antes de sincronizar los pedidos de ventas, es importante actualizar los sistemas mediante la configuración siguiente:

### <a name="setup-in-sales"></a>Configuración en Sales

- Garantice los permisos del equipo del cual forma parte el usuario (desde el **Conjunto de conexión** de Sales). Si utiliza datos de prueba, el usuario normalmente tiene acceso de administrador, pero no el equipo. Sin esta configuración, verá un error que indica que el equipo principal no está al ejecutar el proyecto desde el integrador de datos. 

    - En **Configuración** > **Seguridad** > **Equipos**, seleccione el equipo adecuado, haga clic en **Gestionar roles** y seleccione un rol que tenga los permisos deseados (por ejemplo, administrador de sistema).

- En **Configuración** > **Administración** > **Configuración del sistema** > **Sales**, asegúrese de que la opción **Usar el sistema de cálculo del sistema de precios** está establecida en **Sí**. 

- En **Configuración** > **Administración** > **Configuración del sistema** > **Sales**, asegúrese de que la opción **Método de cálculo de descuentos** está establecida en **Artículo de línea**. 

### <a name="setup-in-finance-and-operations"></a>Configuración en Finance and Operations

Establezca **Ventas y marketing** > **Tareas periódicas** > **Calcular las ventas totales** para que se ejecuten como un trabajo por lotes y establezca **Calcular los totales de los pedidos de ventas** en **Sí**. Esto es importante, ya que solo los pedidos de ventas que tengan las ventas totales calculadas se sincronizarán en CDS y Sales. La frecuencia del trabajo por lotes debe coincidir con la frecuencia de la sincronización del pedido de ventas.

### <a name="setup-in-the-data-integration-project"></a>Configuración del proyecto de integración de datos

#### <a name="salesheader-task"></a>Tarea de SalesHeader

- Actualice la asignación del **id. de la organización de CDS en Origen** > **CDS**.

    - El valor de plantilla predeterminado de **Account_Organization_OrganizationId** es ORG001.
    - El valor de plantilla predeterminado de **InvoiceAccount_Organization_OrganizationId** es ORG001.
    - El valor de plantilla predeterminado de **Organization_OrganizationId** es ORG001.

- Asegúrese de que existe la asignación necesaria en el CDS **Origen** > **para InvoiceCountryRegionId a BillingAddress_Country** y para **DeliveryCountryRegionId a DeliveryAddress_Country**.

    - El valor de la plantilla es **ValueMap** con varios países asignados.

- La **Lista de precios** es necesaria para poder crear pedidos en Sales. Actualice el valor **ValueMap** en **CDS** > **Destino** para **pricelevelid.name [nombre de la lista de precios]** en la **lista de precios** que se usa en Sales según la divisa. Puede usar la **lista de precios** predeterminada de una sola divisa o usar el valor **ValueMap** si tiene **listas de precios** en varias divisas.
    
    - El valor de la plantilla predeterminada de **pricelevelid.name [nombre de la lista de precios]** es CRM Service USA (ejemplo). 

#### <a name="salesline-task"></a>Tarea de SalesLine

- Actualice la asignación del **id. de la organización de CDS en Origen** > **CDS**. 
    
    - El valor de plantilla predeterminado de **SalesOrder_Organization_OrganizationId** es ORG001.
    - El valor de plantilla predeterminado de **Product_Organization_OrganizationId** es ORG001.

- Asegúrese de que la asignación necesaria existe en **Origen** > **CDS** de **DeliveryCountryRegionId** a **DeliveryAddress_Country**.

    - El valor de la plantilla es **ValueMap** con varios países asignados.
    
- Asegúrese de que el valor necesario **ValueMap** de **SalesUnitSymbol** en Finance and Operations está en **Origen** > **Asignación de CDS**.

    - El valor de la plantilla con **ValueMap** se define de **SalesUnitSymbol a Quantity_UOM**.

## <a name="template-mapping-in-data-integrator"></a>Asignación de la plantilla en el integrador de datos

> [!NOTE]
> Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no forman parte de las asignaciones predeterminadas. Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.

Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.

### <a name="orderheader"></a>OrderHeader

![Asignación de la plantilla en el integrador de datos](./media/sales-order-template-mapping-data-integrator-1.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-order-template-mapping-data-integrator-2.png)

### <a name="orderline"></a>OrderLine

![Asignación de la plantilla en el integrador de datos](./media/sales-order-template-mapping-data-integrator-3.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-order-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Temas relacionados

[Sincronice los productos de Finance and Operations con productos en Sales](products-template-mapping.md)

[Sincronizar cuentas de Sales con clientes de Finance and Operations](accounts-template-mapping.md)

[Sincronizar contactos de Sales con contactos o clientes de Finance and Operations](contacts-template-mapping.md)

[Sincronizar encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations](sales-quotation-template-mapping.md)

[Sincronizar encabezados y líneas de factura de Finance and Operations en Sales](sales-invoice-template-mapping.md)


