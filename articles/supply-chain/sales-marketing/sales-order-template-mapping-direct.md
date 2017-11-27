---
title: "Sincronizar encabezados y líneas de pedido de ventas directamente de Finance and Operations en Sales"
description: "Este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de pedidos de ventas directamente de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.openlocfilehash: cc0be50552ae680ba5291e72b7c482ee67e1e70e
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Sincronizar encabezados y líneas de pedido de ventas directamente de Finance and Operations en Sales

[!include[banner](../includes/banner.md)]

Este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de pedidos de ventas directamente de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Flujo de datos en Prospect to cash

La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Finance and Operations y Sales. Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos sobre cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Finance and Operations y Sales. La ilustración siguiente muestra cómo se sincronizan los datos entre Finance and Operations y Sales.

[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas

Para obtener acceso a las plantillas disponibles, abra [Centro de gestión de PowerApps](https://preview.admin.powerapps.com/dataintegration). Seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

La plantilla y las tareas subyacentes siguientes se usan para sincronizar encabezados y líneas del pedido de ventas de Finance and Operations a Sales:

- **Nombre de la plantilla en la integración de datos:** Pedidos de ventas (Fin and Ops a Sales) - Directos
- **Nombres de las tareas en el proyecto de integración de datos:**

    - OrderHeader
    - OrderLine

Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los encabezados y líneas de factura:

- Productos (de Fin and Ops a Sales) - Directos
- Cuentas (de Sales a Fin and Ops) - Directos (si es que se usan)
- Contactos a Clientes (de Sales a Fin and Ops) - Directos (si es que se usan)

## <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations  | Ventas             |
|-------------------------|-------------------|
| Encabezados de pedido de ventas de CDS | SalesOrders       |
| Líneas de pedido de ventas de CDS   | SalesOrderDetails |

## <a name="entity-flow"></a>Flujo de la entidad

Los pedidos de ventas se crean en Finance and Operations y se sincronizan en Sales.

Los filtros de la plantilla ayudan a garantizar que solo se incluyan en la sincronización los pedidos de ventas más importantes:

- En el pedido de ventas, tanto el cliente de pedidos como el cliente de facturación que se originan en Sales se incluirán en la sincronización. En Finance and Operations, los campos **OrderingCustomerIsExternallyMaintained** y **InvoiceCustomerIsExternallyMaintained** se usan para realizar el seguimiento de la sincronización en las entidades de datos.
- Debe confirmar el pedido de ventas en Finance and Operations. Solo se sincronizan en Sales los pedidos de ventas confirmados o los pedidos de ventas con un estado más alto de procesamiento como, por ejemplo, aquellos que tengan un estado de **Enviado** o **Facturado**.
- Después de crear o modificar un pedido de ventas, debe ejecutar el trabajo por lotes **Calcular las ventas totales** en Finance and Operations. Solo se sincronizarán con Sales los pedidos de ventas en los que se calculan las ventas totales.

> [!NOTE]
> Actualmente, los impuestos relacionados con los gastos en cabecera de pedidos de ventas no se incluyen en la sincronización de Finance and Operations a Sales. Sales no admite información fiscal en el nivel de la cabecera. Sin embargo, los impuestos relacionados con cargos en el nivel de línea se incluyen en la sincronización.

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales

Se han agregado nuevos campos a la entidad **Pedido** y se muestran en la página:

- **Se mantiene externamente** – Establezca esta opción en **Sí** cuando el pedido proviene de Finance and Operations.
- **Estado de procesamiento** – Este campo muestra el estado de procesamiento del pedido en Finance and Operations. Los siguientes valores están disponibles:

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

La configuración **Solo tiene productos mantenidos externamente** se usa en otros escenarios del pedido de ventas (por ejemplo, sincronización de Sales a Finance and Operations) para realizar un seguimiento constante de si un pedido de ventas está enteramente compuesto de productos mantenidos externamente. Si un pedido de ventas solo contiene productos mantenidos externamente, los productos se mantienen en Finance and Operations. Este ajuste ayuda a garantizar que no intenta sincronizar las líneas de pedido de ventas que tienen productos desconocidos para Finance and Operations.

Los botones **Crear factura**, **Cancelar pedido**, **Recalcular**, **Obtener productos** y **Buscar dirección** de la página del **Pedido de ventas** se ocultan para los pedidos mantenidos de forma externa, ya que las facturas se crearán en Finance and Operations y se sincronizarán en Sales. No se puede editar la página del pedido porque la información del pedido de ventas se sincronizará desde Finance and Operations.

El estado de un pedido de ventas permanecerá **Activo** para ayudar a garantizar que los cambios de Finance and Operations se incluyen en el pedido de ventas de Sales. Para controlar este comportamiento, establezca el valor del **Código de estado \[Status\]** en **Activo** en el proyecto de integración de datos.

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

Antes de sincronizar pedidos de ventas, es importante actualizar la configuración siguiente en los sistemas:

### <a name="setup-in-sales"></a>Configuración en Sales

- Asegúrese de que los permisos se configuran para el equipo al que está asignado el usuario desde la conexión de Sales. Si utiliza datos de prueba, el usuario normalmente tiene acceso de administrador, pero no el equipo. Si el equipo tampoco tiene derechos de administrador, cuando usted ejecuta el proyecto desde la integración de datos, recibirá un mensaje de error que dice que falta el equipo principal.

    Vaya a **Configuración** > **Seguridad** > **Equipos,** seleccione el equipo adecuado, seleccione **Gestionar roles** y seleccione un rol que tenga los permisos deseados, por ejemplo, **Administrador de sistema**.

- Vaya a **Configuración** > **Administración** > **Configuración del sistema** > **Sales**, y asegúrese de que se utilicen los valores siguientes:

    - La opción **Usar el sistema de cálculo del sistema de precios** se establece en **Sí**.
    - El campo **Método de cálculo de descuentos** se establece en **Artículo de línea**.

### <a name="setup-in-finance-and-operations"></a>Configuración en Finance and Operations

Vaya a **Ventas y marketing** > **Tareas periódicas** > **Calcular ventas totales**, y configure el trabajo para ejecutar como un trabajo por lotes. Establezca la opción **Calcular totales para pedidos de ventas** como **Sí**. Este paso es importante, porque solo se sincronizan con Sales los pedidos de ventas en los que se calculan las ventas totales. La frecuencia del trabajo por lotes debe coincidir con la frecuencia de la sincronización del pedido de ventas.

### <a name="setup-in-the-data-integration-project"></a>Configuración del proyecto de integración de datos

#### <a name="salesheader-task"></a>Tarea de SalesHeader

- Asegúrese de que existe la asignación necesaria para **InvoiceCountryRegionId** como **BillingAddress\_Country** y para **DeliveryCountryRegionId** como **DeliveryAddress\_Country**.

    El valor de plantilla es una asignación de valores en la que se asignan varios países o regiones.

- Una lista de precios es necesaria para poder crear pedidos en Sales. Actualice la asignación de valores para **pricelevelid.name \[Nombre de la lista de precios\]** con la lista de precios que se usa en Sales según la divisa. Puede usar la lista de precios predeterminada para una sola divisa. Como alternativa, si tiene listas de precios en varias divisas, puede usar una asignación de valores.

    El valor de la plantilla predeterminada de **pricelevelid.name \[Nombre de la lista de precios\]** es **CRM Service USA (ejemplo).**

#### <a name="salesline-task"></a>Tarea de SalesLine

- Asegúrese de que la asignación requerida existe para **DeliveryCountryRegionId** como **DeliveryAddress\_Country**.

    El valor de plantilla es una asignación de valores en la que se asignan varios países o regiones.

- Asegúrese de que la asignación de valores requerida para **SalesUnitSymbol** existe en Finance and Operations.

    Un valor de plantilla que tiene una asignación de valores se define para **SalesUnitSymbol** como **Quantity\_UOM**.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

> [!NOTE]
> Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no se incluyen en las asignaciones predeterminadas. Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.

Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en la integración de datos. 

> [!NOTE]
> La asignación muestra qué información de campos se sincronizará de Sales a Finance and Operations.

### <a name="orderheader"></a>OrderHeader

![Asignación de la plantilla en el integrador de datos](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="orderline"></a>OrderLine

![Asignación de la plantilla en el integrador de datos](./media/sales-order-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Temas relacionados

[Prospect to cash](prospect-to-cash.md)

[Sincronizar directamente cuentas de Sales con clientes de Finance and Operations](accounts-template-mapping-direct.md)

[Sincronizar directamente productos de Finance and Operations con productos de Sales](products-template-mapping-direct.md)

[Sincronizar directamente contactos de Sales con contactos o clientes de Finance and Operations](contacts-template-mapping-direct.md)

[Sincronizar encabezados y líneas de factura directamente de Finance and Operations en Sales](sales-invoice-template-mapping-direct.md)




