---
title: Cliente potencial a efectivo en doble escritura
description: Este artículo proporciona información sobre cliente potencial a efectivo en doble escritura.
author: RamaKrishnamoorthy
ms.date: 01/07/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 4321d980f56e321a653ca4f4c5738ebd1bb0153d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289620"
---
# <a name="prospect-to-cash-in-dual-write"></a>Cliente potencial a efectivo en doble escritura

[!include [banner](../../includes/banner.md)]

Un objetivo importante de la mayoría de las empresas es convertir clientes potenciales en clientes y luego mantener una relación comercial continua con esos clientes. En las aplicaciones Microsoft Dynamics 365, el proceso de cliente potencial a efectivo ocurre a través de presupuestos o flujos de trabajo de procesamiento de pedidos, y las finanzas se concilian y reconocen. La integración de cliente potencial a efectivo con doble escritura crea un flujo de trabajo que toma una cotización y un pedido que se origina en Dynamics 365 Sales o Dynamics 365 Supply Chain Management y hace que la oferta y el pedido estén disponibles en ambas aplicaciones.

En las interfaces de la aplicación, puede acceder a los estados de procesamiento y a la información de la factura en tiempo real. Por lo tanto, puede administrar más fácilmente funciones como el almacenamiento de productos, el manejo de inventario y el cumplimiento en Supply Chain Management, sin tener que volver a crear los presupuestos y los pedidos.

![Flujo de datos de doble escritura en cliente potencial a efectivo.](../dual-write/media/dual-write-prospect-to-cash[1].png)

Para obtener información sobre la integración de clientes y contactos, consulte [Maestro de clientes integrado](customer-mapping.md). Para obtener información sobre la integración de productos, consulte [Experiencia unificada del producto](product-mapping.md).

> [!NOTE]
> En Dynamics 365 Sales, tanto el cliente potencial como el cliente hacen referencia a un registro en la tabla **Cuenta** donde la columna **RelationshipType** es **Cliente potencial** o **Cliente**. Si su lógica empresarial incluye un proceso de calificación **Cuenta** en el que el registro **Cuenta** se crea y califica como cliente potencial primero y después como cliente, ese registro se sincroniza con la aplicación de finanzas y operaciones solo cuando es un cliente (`RelationshipType=Customer`). Si quiere que la fila **Cuenta** se sincronice como un cliente potencial, entonces necesita una asignación personalizada para integrar los datos del cliente potencial.

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación

Antes de poder sincronizar los presupuestos de ventas, debe actualizar la siguiente configuración.

### <a name="setup-in-sales"></a>Configuración en Sales

En Ventas vaya a **Configuración \> Administración \> Configuración del sistema \> Sales**, y asegúrese de que se utilicen los valores siguientes:

- La opción del sistema **Usar el cálculo de precios del sistema** se establece en **Sí**.
- La columna **Método de cálculo de descuentos** se establece en **Artículo de línea**.

### <a name="sites-and-warehouses"></a>Ubicaciones y almacenes

En Supply Chain Management, las columnas **Ubicación** y **almacén** son obligatorias para las líneas de cotización y de pedido. Si configura la ubicación y el almacén en la configuración de pedido predeterminada, esas columnas se establecerán automáticamente cuando agregue un producto a una línea de presupuesto o línea de pedido. 

### <a name="number-sequences-for-quotations-and-orders"></a>Secuencias numéricas para presupuestos y pedidos

Las secuencias numéricas para Supply Chain Management y Sales no están conectadas cuando se crean y sincronizan presupuestos y pedidos en Sales y Supply Chain Management. Si un pedido de ventas que se crea en Sales se sincroniza con Supply Chain Management, tiene el mismo número de pedido de ventas en Supply Chain Management. Para ayudar a garantizar que el número de pedido de ventas no esté duplicado, debe usar diferentes sistemas de secuencia numérica en las dos aplicaciones.

Por ejemplo, la secuencia numérica en Supply Chain Management es **1, 2, 3, 4, 5, ...**, y la secuencia numérica en Sales es **100, 99, 98, ...**. Si crea 100 pedidos de ventas en Sales, eventualmente se generará un número de pedido que ya existe en Supply Chain Management. En otras palabras, las dos secuencias numéricas eventualmente se superpondrán a medida que se creen pedidos de ventas en Supply Chain Management y Sales. En su lugar, puede usar una secuencia numérica como **F1, F2, F3, ...** en Supply Chain Management y una secuencia numérica como **C1, C2, C3, ...** en Sales. Estas secuencias de números nunca producirán números de pedido de ventas duplicados.

## <a name="sales-quotations"></a>Presupuestos de ventas

Los presupuestos de ventas pueden crearse en Sales o Supply Chain Management. Si crea un presupuesto en Sales, se sincroniza con Supply Chain Management en tiempo real. De forma similar, si crea un presupuesto en Supply Chain Management, se sincroniza con Sales en tiempo real. Tenga en cuenta los aspectos siguientes:

+ Puede agregar un descuento al producto en el presupuesto. En este caso, el descuento se sincronizará con Supply Chain Management. Las columnas **Descuento**, **Cargos** e **Impuestos** en el encabezado se controlan mediante una configuración en Supply Chain Management. Esta configuración no admite la asignación de la integración. En su lugar, las columnas **Precio**, **Descuento**, **Cargo** e **Impuestos** son gestionadas y mantenidas en Supply Chain Management.
+ Las columnas **% de descuento**, **Descuento** e **Importe del flete** en el encabezado del presupuesto de ventas son columnas de solo lectura.
+ Las columnas **Condiciones de flete**, **Condiciones de entrega**, **Método de envío** y **Modo de entrega** no forman parte de las asignaciones predeterminadas. Para asignar estas columnas, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la tabla.

Si también está utilizando la solución Field Service, asegúrese de volver a habilitar el parámetro **Creación rápida de línea de presupuesto**. Volver a habilitar el parámetro le permite continuar creando líneas de presupuesto usando la función de creación rápida.

1. Navegue a su aplicación Dynamics 365 Sales.
2. Seleccione el icono de configuración en la barra de navegación superior.
3. Seleccione **Ajustes avanzados**.
4. Elija la opción **Personalizar el sistema**.
5. Seleccione el elemento de menú **Línea de cotización**.
6. Vaya a la sección **Servicios de datos** y seleccione la casilla **Permitir creación rápida**.

## <a name="sales-orders"></a>Pedidos de ventas

Los pedidos de ventas pueden crearse en Sales o Supply Chain Management. Si crea un pedido de ventas en Sales, se sincroniza con Supply Chain Management en tiempo real. De forma similar, si crea un pedido de ventas en Supply Chain Management, se sincroniza con Sales en tiempo real. Tenga en cuenta los aspectos siguientes:

+ Los productos de escritura en Dynamics 365 Sales aparecerán como categorías de productos en Dynamics 365 Supply Chain Management.
+ Cálculo del descuento y redondeo:

    - El modelo de cálculo del descuento en Sales es distinto del modelo de cálculo de descuento en Supply Chain Management. En Supply Chain Management, el importe del descuento final en una línea de ventas puede ser el resultado de una combinación de importes de descuento y de porcentajes de descuento. Si este importe del descuento final se divide por la cantidad en la línea, puede producirse redondeo. Sin embargo, este redondeo no se tiene en cuenta si un importe de descuento por unidad redondeado se sincroniza con Sales. Para ayudar a garantizar que el importe de descuento completo de una línea de ventas en Supply Chain Management se sincronice correctamente con Sales, el importe completo debe sincronizarse sin ser dividido por la cantidad de línea. Por lo tanto, debe definir método de cálculo de descuentos como **Artículo de línea** en Sales.
    - Cuando una línea de pedido de ventas se sincroniza de Sales a Supply Chain Management, se usará el importe de descuento de línea completo. Dado que Supply Chain Management no tiene ninguna columna que pueda almacenar el importe de descuento completo para una línea, el importe se divide por la cantidad y se almacena en la columna **Descuento de línea**. El redondeo que se produzca durante esta división se almacena en la columna **Gastos de ventas** en la línea de ventas.

### <a name="example-synchronization-from-sales-to-supply-chain-management"></a>Ejemplo: Sincronización de Sales a Supply Chain Management

Tiene el siguiente pedido de ventas:

+ **Ventas:** Cantidad = 3, descuento por línea = $10.00
+ **Supply Chain Management:** Cantidad = 3, importe de descuento de línea = 3,33 $, cargo de ventas = -0,01 $

Si sincroniza desde Supply Chain Management a Sales, obtendrá el siguiente resultado:

+ **Supply Chain Management:** Cantidad = 3, importe de descuento de línea = 3,33 $, cargo de ventas = -0,01 $
+ **Ventas:** Cantidad = 3, descuento por línea = (3 × $3.33) + $0.01 = $10.00

## <a name="dual-write-solution-for-sales"></a>Solución de doble escritura para Sales

Se han agregado nuevas columnas a la tabla **Pedido** y se muestran en la página. La mayoría de estas columnas aparecen en la pestaña **Integración** en Sales. Para obtener más información sobre cómo se asignan las columnas de estado, consulte [Configurar la asignación para las columnas de estado del pedido de ventas](sales-status-map.md).

+ Los botones **Crear factura** y **Cancelar pedido** en la página **Pedido de ventas** están ocultos en Sales.
+ El valor **Estado del pedido de ventas** permanecerá **Activo** para ayudar a garantizar que los cambios de Supply Chain Management se incluyen en el pedido de ventas de Sales. Para controlar este comportamiento, establezca el valor del **Statecode \[Status\]** en **Activo**.

## <a name="invoices"></a>Facturas

Las facturas de ventas se crean en Supply Chain Management y se sincronizan en Sales. Tenga en cuenta los aspectos siguientes:

+ La columna **Número de factura** se ha agregado a la tabla **Factura** y se muestra en la página.
+ El botón **Crear factura** de la página **Pedido de ventas** se oculta, ya que las facturas se crearán en Supply Chain Management y se sincronizarán en Sales. No se puede editar la página **Factura** porque las facturas se sincronizarán desde Supply Chain Management.
+ El valor de **Estado del pedido de ventas** cambia automáticamente a **Facturado** si la factura relacionada de Supply Chain Management se ha sincronizado con Sales. Además, el propietario del pedido de ventas desde el cual se creó la factura, se asigna como propietario de la factura. Por tanto, el propietario del pedido de ventas puede ver la factura.
+ Las columnas **Condiciones de flete**, **Condiciones de entrega** y **Modo de entrega** no se incluyen en las asignaciones predeterminadas. Para asignar estas columnas, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la tabla.

## <a name="templates"></a>Plantillas

Cliente potencial a efectivo incluye una colección de mapas de tabla básicos que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.

| Aplicaciones de finanzas y operaciones | Aplicaciones Customer Engagement | Description |
|-----------------------------|-----------------------------------|-------------|
[Todos los productos](mapping-reference.md#138) | msdyn_globalproducts | |
[Clientes V3](mapping-reference.md#101) | cuentas | |
[Clientes V3](mapping-reference.md#116) | contactos | |
[Contactos V2](mapping-reference.md#221) | msdyn_contactforparties | |
[Encabezado de pedidos de ventas de CDS](mapping-reference.md#217) | salesorders | |
[Líneas de pedido de ventas de CDS](mapping-reference.md#216) | salesorderdetails | |
[Encabezado de presupuesto de ventas de CDS](mapping-reference.md#215) | presupuestos | |
[Líneas de presupuesto de ventas de CDS](mapping-reference.md#214) | quotedetails | |
[Productos liberados V2](mapping-reference.md#189) | msdyn_sharedproductdetails | |
[Encabezados de factura de ventas V2](mapping-reference.md#118) | facturas | La tabla V2 de encabezados de facturas de Sales en la aplicación de finanzas y operaciones contiene facturas para pedidos de venta y facturas de servicios. Se aplica un filtro en Dataverse para escritura dual que filtrará cualquier documento de factura de servicios. |
[Líneas de factura de ventas V2](mapping-reference.md#117) | invoicedetails | |
[Códigos de origen de pedido de ventas](mapping-reference.md#186) | msdyn_salesorderorigins | |

Para obtener información sobre las listas de precios, consulte [Experiencia unificada del producto](product-mapping.md).

## <a name="limitations"></a>Limitaciones

- No se admiten pedidos de devolución.
- No se admiten notas de abono.
- Las dimensiones financieras deben establecerse para los datos maestros, por ejemplo, cliente y proveedor. Cuando se agrega un cliente a un presupuesto o pedido de venta, las dimensiones financieras asociadas con el registro del cliente fluyen automáticamente al pedido. Actualmente, la escritura dual no incluye datos de dimensiones financieras para datos maestros.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

