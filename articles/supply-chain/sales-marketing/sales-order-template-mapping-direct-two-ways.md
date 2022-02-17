---
title: Sincronización de pedidos de ventas entre Sales y Supply Chain Management
description: En el tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar pedidos de ventas directamente entre Dynamics 365 Sales y Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 05/09/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: eb41a21395a5d115b779e6b1ef71e9eb1176e28e
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8061527"
---
# <a name="synchronization-of-sales-orders-directly-between-sales-and-supply-chain-management"></a>Sincronización de pedidos de ventas entre Sales y Supply Chain Management

[!include [banner](../includes/banner.md)]



En el tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar pedidos de ventas directamente entre Dynamics 365 Sales y Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Flujo de datos en Prospect to cash

La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Supply Chain Management y Sales. Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos de cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Supply Chain Management y Sales. La ilustración siguiente muestra cómo se sincronizan los datos entre Supply Chain Management y Sales.

[![Flujo de datos en Prospect to cash.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas

Para obtener acceso a las plantillas disponibles, abra [Centro de administración de Power Apps](https://preview.admin.powerapps.com/dataintegration). Seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

Las plantillas y las tareas subyacentes siguientes se usan para ejecutar sincronizaciones de pedidos de ventas directamente entre Sales y Supply Chain Management.

- **Nombres de las plantillas en la integración de datos:** 

    - Pedidos de Sales (Sales a Supply Chain Management) - Directo
    - Pedidos de Sales (Supply Chain Management a Sales) - Directo

- **Nombres de las tareas en el proyecto de integración de datos:**

    - OrderHeader
    - OrderLine

Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los encabezados y líneas de factura:

- Productos (Supply Chain Management a Sales) - Directo
- Cuentas (Sales a Supply Chain Management) - Directo (si se usa)
- Contactos a clientes (de Sales a Supply Chain Management) - Directo (si se usa)

## <a name="entity-set"></a>Conjunto de entidades

| Gestión de la cadena de abastecimiento  | Sales             |
|-------------------------|-------------------|
| Encabezados de pedido de ventas de Dataverse | SalesOrders       |
| Líneas de pedido de ventas de Dataverse   | SalesOrderDetails |

## <a name="entity-flow"></a>Flujo de la entidad

Los pedidos de ventas se crean en Sales y se sincronizan con Supply Chain Management cuando se activa **Ejecutar proyecto** para un proyecto basado en la plantilla **Pedidos de ventas (Sales a Supply Chain Management) - Directos**. Puede activar y sincronizar solo pedidos desde Sales si todos los **Productos del pedido** constan de productos que se mantienen externamente. Por lo tanto, no puede haber productos de escritura. Después de activar el pedido, el pedido de ventas pasará a ser de solo lectura en la interfaz de usuario (UI). En ese momento, las actualizaciones se realizan desde Supply Chain Management. Después de que el pedido de ventas tenga un estado de **Confirmado**, podrá utilizarse un proyecto basado en la plantilla **Pedidos de ventas (Supply Chain Managementa Sales) - Directos** para sincronizar las actualizaciones o el estado de cumplimiento de Supply Chain Management a Sales.

No es necesario crear pedidos en Sales. Puede crear nuevos pedidos de ventas en Supply Chain Management en su lugar. Después de que un pedido de ventas tenga un estado de **Confirmado**, se sincroniza con Sales como se describe en el párrafo anterior.

En Supply Chain Management, los filtros de la plantilla ayudan a garantizar que solo se incluyan en la sincronización los pedidos de ventas más importantes:

- En el pedido de ventas, tanto el cliente de pedidos como el cliente de facturación tienen que originarse en Sales para incluirse en la sincronización. En Supply Chain Management, las columnas **OrderingCustomerIsExternallyMaintained** y **InvoiceCustomerIsExternallyMaintained** se usan para filtrar pedidos de ventas de las tablas de datos.
- Debe confirmar el pedido de ventas en Supply Chain Management. Solo se sincronizan en Sales los pedidos de ventas confirmados o los pedidos de ventas con un estado más alto de procesamiento como, por ejemplo, aquellos que tengan un estado de **Enviado** o **Facturado**.
- Después de crear o modificar un pedido de ventas, debe ejecutar el trabajo por lotes **Calcular las ventas totales** en Supply Chain Management. Solo se sincronizarán con Sales los pedidos de ventas en los que se calculan las ventas totales.

## <a name="freight-tax"></a>Impuestos de transporte

Sales no admite impuestos a nivel de encabezado, ya que los impuestos se almacenan a nivel de línea. Para admitir impuestos a nivel de encabezado de Supply Chain Management, como impuestos de transporte, el sistema sincroniza impuestos a Sales como producto de escritura que se denomina **Impuestos de transporte** y que tiene el importe de impuestos de Supply Chain Management. De esta manera, el cálculo de precios estándar en Sales se puede usar para totales, incluso si hay impuestos a nivel de encabezado de Supply Chain Management.

## <a name="discount-calculation-and-rounding"></a>Cálculo del descuento y redondeo

El modelo de cálculo del descuento en Sales es distinto del modelo de cálculo de descuento en Supply Chain Management. En Supply Chain Management, el importe del descuento final en una línea de ventas puede ser el resultado de una combinación de importes de descuento y de porcentajes de descuento. Si este importe del descuento final se divide por la cantidad en la línea, puede producirse redondeo. Sin embargo, este redondeo no se tiene en cuenta si un importe de descuento por unidad redondeado se sincroniza con Sales. Para ayudar a garantizar que el importe de descuento completo de una línea de ventas en Supply Chain Management se sincronice correctamente con Sales, el importe completo debe sincronizarse sin ser dividido por la cantidad de línea. Por lo tanto, debe definir **Método de cálculo de descuentos** como **Artículo de línea** en Sales.

Cuando una línea de pedido de ventas se sincroniza de Sales a Supply Chain Management, se usará el importe de descuento de línea completo. Dado que Supply Chain Management no tiene ningún campo que pueda almacenar el importe de descuento completo para una línea, el importe se divide por la cantidad y se almacena en el campo **Descuento de línea**. El redondeo que se produzca en esta división se almacena en el campo **Gastos de ventas** en la línea de ventas.

### <a name="example"></a>Ejemplo

**Sincronización de Sales a Supply Chain Management**

- **Ventas:** Cantidad = 3, descuento por línea = $10.00
- **Supply Chain Management:** Cantidad = 3, importe de descuento de línea = 3,33 $, cargo de ventas = -0,01 $ 

**Sincronización de Supply Chain Management a Sales**

- **Supply Chain Management:** Cantidad = 3, importe de descuento de línea = 3,33 $, cargo de ventas = -0,01 $
- **Ventas:** Cantidad = 3, descuento por línea = (3 × $3.33) + $0.01 = $10.00

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales

Se han agregado nuevas columnas a la tabla **Pedido** y se muestran en la página:

- **Se mantiene externamente** – Establezca esta opción en **Sí** cuando el pedido proviene de Supply Chain Management.
- **Estado de procesamiento** – Esta columna muestra el estado de procesamiento del pedido en Supply Chain Management. Los siguientes valores están disponibles:

    - **Borrador** – El estado inicial cuando se crea un pedido en Sales. En Sales, solo se pueden editar los pedidos con este estado de procesamiento.
    - **Activo** – El estado después de que el pedido se active en Sales mediante el botón **Activar**.
    - **Confirmado**
    - **Albarán**
    - **Facturado**
    - **Seleccionado**
    - **Parcialmente seleccionado**
    - **Parcialmente empaquetado**
    - **Enviados**
    - **Parcialmente enviado**
    - **Parcialmente facturado**
    - **Cancelado**

El campo **Solo tiene productos mantenidos externamente** se utiliza durante la activación de pedidos para realizar un seguimiento constante si el pedido de ventas se compone por completo de productos mantenidos externamente. Si un pedido de ventas solo contiene productos mantenidos externamente, los productos se mantienen en Supply Chain Management. Este ajuste ayuda a garantizar que no activa ni intenta sincronizar las líneas de pedido de ventas que tienen productos desconocidos para Supply Chain Management.

Los botones **Crear factura**, **Cancelar pedido**, **Recalcular**, **Obtener productos** y **Buscar dirección** de la página del **Pedido de ventas** se ocultan para los pedidos mantenidos de forma externa, ya que las facturas se crearán en Supply Chain Management y se sincronizarán en Sales. Estos pedidos no se pueden editar porque la información del pedido de ventas se sincronizará desde Supply Chain Management después de la activación.

El estado del pedido de ventas permanecerá **Activo** para ayudar a garantizar que los cambios de Supply Chain Management se incluyen en el pedido de ventas de Sales. Para controlar este comportamiento, establezca el valor del **Código de estado \[Status\]** en **Activo** en el proyecto de integración de datos.

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

Antes de sincronizar pedidos de ventas, es importante actualizar la configuración siguiente en los sistemas:

### <a name="setup-in-sales"></a>Configuración en Sales

- Asegúrese de que los permisos se configuran para el equipo al que está asignado el usuario desde la conexión de Sales. Si utiliza datos de prueba, el usuario normalmente tiene acceso de administrador, pero no el equipo. Si el equipo no tiene derechos de administrador cuando usted ejecuta el proyecto desde la integración de datos, recibirá un mensaje de error que dice que falta el equipo principal.

    Vaya a **Configuración** &gt; **Seguridad** &gt; **Equipos**, seleccione el equipo adecuado, seleccione **Gestionar roles** y seleccione un rol que tenga los permisos deseados, por ejemplo, **Administrador de sistema**.

- Para garantizar el cálculo correcto de descuentos en Sales y Supply Chain Management, **Método de cálculo de descuentos** deben establecerse en **Artículo de línea**.
- Vaya a **Configuración** &gt; **Administración** &gt; **Configuración del sistema** &gt; **Sales**, y asegúrese de que se utilicen los valores siguientes:

    - La opción **Usar el sistema de cálculo del sistema de precios** se establece en **Sí**.
    - La columna **Método de cálculo de descuentos** se establece en **Artículo de línea**.

### <a name="setup-in-supply-chain-management"></a>Configurar Supply Chain Management

- Vaya a **Ventas y marketing** &gt; **Tareas periódicas** &gt; **Calcular ventas totales**, y configure el trabajo para ejecutar como un trabajo por lotes. Establezca la opción **Calcular totales para pedidos de ventas** como **Sí**. Este paso es importante, porque solo se sincronizan con Sales los pedidos de ventas en los que se calculan las ventas totales. La frecuencia del trabajo por lotes debe coincidir con la frecuencia de la sincronización del pedido de ventas.

Si también usa la integración de pedidos de trabajo, debe configurar el origen de ventas. El origen de la venta se utiliza para distinguir los pedidos de ventas en Supply Chain Management creados a partir de pedidos de trabajo en Field Service. Cuando un pedido de ventas tiene un origen de ventas del tipo **Integración del pedido de trabajo** aparece en la pestaña **Estado del pedido de trabajo externo** en el encabezado del pedido de ventas. Además, el origen de la venta garantiza que los pedidos de ventas creados a partir de pedidos de trabajo en Field Service se filtren durante la sincronización del pedido de ventas de Supply Chain Management a Field Service.

1. Vaya a **Ventas y marketing** \> **Configuración** \> **Pedidos de ventas** \> **Origen de ventas**.
2. Seleccione **Nuevo** para crear un nuevo origen de ventas.
3. En la columna **Origen de ventas**, especifique un nombre para el origen de la venta, como **SalesOrder**.
4. En la columna **Descripción**, especifique una descripción, como **Pedido de ventas desde ventas**.
5. Seleccione la casilla de verificación **Asignación de tipo de origen**.
6. Establezca la columna **Tipo de origen de ventas** a **Integración del pedido de ventas**.
7. Seleccione **Guardar**.

### <a name="setup-in-the-sales-orders-sales-to-supply-chain-management---direct-data-integration-project"></a>Configuración en los pedidos de ventas (Sales a Supply Chain Management) - Proyecto de integración de datos directos

- Asegúrese de que la asignación requerida existe para **Shipto\_country** como **DeliveryAddressCountryRegionISOCode**. Puede crear en blanco un valor predeterminado en la asignación de valores para evitar tener que escribir el país para los pedidos nacionales. Establezca el lado izquierdo como 'En blanco', y establezca el lado derecho como el país o la región deseada.

    El valor de plantilla es una asignación de valores en la que se asignan varios países o regiones, y donde 'En blanco' = US.

### <a name="setup-in-the-sales-orders-supply-chain-management-to-sales---direct-data-integration-project"></a>Configuración en los pedidos de ventas (Supply Chain Management a Sales) - Proyecto de integración de datos directos

#### <a name="salesheader-task"></a>Tarea de SalesHeader

- Una lista de precios es necesaria para poder crear pedidos en Sales. Actualice la asignación de valores para **pricelevelid.name \[Nombre de la lista de precios\]** con la lista de precios que se usa en Sales según la divisa. Puede usar la lista de precios predeterminada para una sola divisa. Como alternativa, si tiene listas de precios en varias divisas, puede usar una asignación de valores.

    El valor de la plantilla predeterminada de **pricelevelid.name \[Nombre de la lista de precios\]** es **CRM Service USA (ejemplo).**

#### <a name="salesline-task"></a>Tarea de SalesLine

- Asegúrese de que existe la asignación de valores requerida para **SalesUnitSymbol** en Supply Chain Management.
- Asegúrese de que las unidades necesarias están definidas en Sales.

    Un valor de plantilla que tiene una asignación de valores se define para **SalesUnitSymbol** como **oumid.name**.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

> [!NOTE]
> Las columnas **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío** y **Modo de entrega** no forman parte de las asignaciones predeterminadas. Para asignar estas columnas, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la tabla.

Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en la integración de datos.

> [!NOTE]
> La asignación muestra qué información de columnas se sincronizará de Sales a Supply Chain Management, o de Supply Chain Management a Sales.

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderheader"></a>Pedidos de Sales (Supply Chain Management a Sales) - Directo: OrderHeader

[![Asignación de plantilla en integración de datos, pedidos de ventas (Supply Chain Management a Sales) - Directo: OrderHeader.](./media/sales-order-direct-template-mapping-data-integrator-1.png)](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderline"></a>Pedidos de Sales (Supply Chain Management a Sales) - Directo: OrderLine

[![Asignación de plantilla en integración de datos, pedidos de ventas (Supply Chain Management a Sales) - Directo: OrderLine.](./media/sales-order-direct-template-mapping-data-integrator-2.png)](./media/sales-order-direct-template-mapping-data-integrator-2.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderheader"></a>Pedidos de Sales (Sales a Supply Chain Management) - Directo: OrderHeader

[![Asignación de plantilla en integración de datos, pedidos de ventas (Sales a Supply Chain Management) - Directo: OrderHeader.](./media/sales-order-direct-template-mapping-data-integrator-3.png)](./media/sales-order-direct-template-mapping-data-integrator-3.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderline"></a>Pedidos de Sales (Sales Supply Chain Management) - Directo: OrderLine

[![Asignación de plantilla en integración de datos, pedidos de ventas (Sales Supply Chain Management) - Directo: OrderLine.](./media/sales-order-direct-template-mapping-data-integrator-4.png)](./media/sales-order-direct-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Temas relacionados

[Cliente potencial a cliente](prospect-to-cash.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]