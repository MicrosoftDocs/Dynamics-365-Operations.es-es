---
title: Cliente potencial a efectivo en doble escritura
description: Este tema proporciona información sobre cliente potencial a efectivo en doble escritura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 57aabeef0ee94b4b13bbe6e3925bcafe1e809ab2
ms.sourcegitcommit: 984604fd651d74aa49a2d7513f096faaf49f9f27
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2020
ms.locfileid: "3270297"
---
# <a name="prospect-to-cash-in-dual-write"></a>Cliente potencial a efectivo en doble escritura

[!include [banner](../../includes/banner.md)]



Un objetivo importante de la mayoría de las empresas es convertir clientes potenciales en clientes y luego mantener una relación comercial continua con esos clientes. En las aplicaciones Microsoft Dynamics 365, el proceso de cliente potencial a efectivo ocurre a través de presupuestos o flujos de trabajo de procesamiento de pedidos, y las finanzas se concilian y reconocen. La integración de cliente potencial a efectivo con doble escritura crea un flujo de trabajo que toma una cotización y un pedido que se origina en Dynamics 365 Sales o Dynamics 365 Supply Chain Management y hace que la oferta y el pedido estén disponibles en ambas aplicaciones.

En las interfaces de la aplicación, puede acceder a los estados de procesamiento y a la información de la factura en tiempo real. Por lo tanto, puede administrar más fácilmente funciones como el almacenamiento de productos, el manejo de inventario y el cumplimiento en Supply Chain Management, sin tener que volver a crear los presupuestos y los pedidos.

![Flujo de datos de doble escritura en cliente potencial a efectivo](../dual-write/media/dual-write-prospect-to-cash[1].png)

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación

Antes de poder sincronizar los presupuestos de ventas, debe actualizar la siguiente configuración.

### <a name="setup-in-sales"></a>Configuración en Sales

En Ventas vaya a **Configuración \> Administración \> Configuración del sistema \> Sales**, y asegúrese de que se utilicen los valores siguientes:

- La opción de sistema **Usar el sistema de cálculo del sistema de precios** está en **Sí**.
- El campo **Método de cálculo de descuentos** se establece en **Artículo de línea**.

### <a name="sites-and-warehouses"></a>Ubicaciones y almacenes

En Supply Chain Management, los campos **Ubicación** y **almacén** son obligatorios para las líneas de cotización y de pedido. Si configura el sitio y el almacén en la configuración de pedido predeterminada, esos campos se establecerán automáticamente cuando agregue un producto a una línea de presupuesto o línea de pedido. 

### <a name="number-sequences-for-quotations-and-orders"></a>Secuencias numéricas para presupuestos y pedidos

Las secuencias numéricas para Supply Chain Management y Sales no están conectadas cuando se crean y sincronizan presupuestos y pedidos en Sales y Supply Chain Management. Si un pedido de ventas que se crea en Sales se sincroniza con Supply Chain Management, tiene el mismo número de pedido de ventas en Supply Chain Management. Para ayudar a garantizar que el número de pedido de ventas no esté duplicado, debe usar diferentes sistemas de secuencia numérica en las dos aplicaciones.

Por ejemplo, la secuencia numérica en Supply Chain Management es **1, 2, 3, 4, 5, ...**, y la secuencia numérica en Sales es **100, 99, 98, ...**. Si crea 100 pedidos de ventas en Sales, eventualmente se generará un número de pedido que ya existe en Supply Chain Management. En otras palabras, las dos secuencias numéricas eventualmente se superpondrán a medida que se creen pedidos de ventas en Supply Chain Management y Sales. En su lugar, puede usar una secuencia numérica como **F1, F2, F3, ...** en Supply Chain Management y una secuencia numérica como **C1, C2, C3, ...** en Sales. Estas secuencias de números nunca producirán números de pedido de ventas duplicados.

## <a name="sales-quotations"></a>Presupuestos de ventas

Los presupuestos de ventas pueden crearse en Sales o Supply Chain Management. Si crea un presupuesto en Sales, se sincroniza con Supply Chain Management en tiempo real. De forma similar, si crea un presupuesto en Supply Chain Management, se sincroniza con Sales en tiempo real. Tenga en cuenta los aspectos siguientes:

+ Puede agregar un descuento al producto en el presupuesto. En este caso, el descuento se sincronizará con Supply Chain Management. Los campos **Descuento**, **Cargos** e **Impuestos** en el encabezado se controlan mediante una configuración compleja en Supply Chain Management. Esta configuración no admite la asignación de la integración. En su lugar, los campos **Precio**, **Descuento**, **Cargo** e **Impuestos** son gestionados y mantenidos en Supply Chain Management.
+ Los campos **% de descuento**, **Descuento** e **Importe del fleje** en el encabezado del presupuesto de ventas son campos de solo lectura.
+ Los campos **Condiciones de flete**, **Condiciones de entrega**, **Método de envío** y **Modo de entrega** no forman parte de las asignaciones predeterminadas. Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.

Si también está utilizando la solución Field Service, asegúrese de volver a habilitar el parámetro **Creación rápida de línea de presupuesto**. Volver a habilitar el parámetro le permite continuar creando líneas de presupuesto usando la función de creación rápida.
1. Navegue a su aplicación Dynamics 365 Sales.
2. Seleccione el icono de configuración en la barra de navegación superior.
3. Seleccione **Ajustes avanzados**.
4. Elija la opción **Personalizar el sistema**.
5. Seleccione el elemento de menú **Línea de cotización**.
6. Vaya a la sección **Servicios de datos** y seleccione la casilla **Permitir creación rápida**.

## <a name="sales-orders"></a>Pedidos de ventas

Los pedidos de ventas pueden crearse en Sales o Supply Chain Management. Si crea un pedido de ventas en Sales, se sincroniza con Supply Chain Management en tiempo real. De forma similar, si crea un pedido de ventas en Supply Chain Management, se sincroniza con Sales en tiempo real. Tenga en cuenta los aspectos siguientes:

+ Puede activar y sincronizar pedidos de Sales solo si todos los productos del pedido provienen de aplicaciones de Finance and Operations. Por lo tanto, no puede haber productos de escritura.
+ Cálculo del descuento y redondeo:

    - El modelo de cálculo del descuento en Sales es distinto del modelo de cálculo de descuento en Supply Chain Management. En Supply Chain Management, el importe del descuento final en una línea de ventas puede ser el resultado de una combinación de importes de descuento y de porcentajes de descuento. Si este importe del descuento final se divide por la cantidad en la línea, puede producirse redondeo. Sin embargo, este redondeo no se tiene en cuenta si un importe de descuento por unidad redondeado se sincroniza con Sales. Para ayudar a garantizar que el importe de descuento completo de una línea de ventas en Supply Chain Management se sincronice correctamente con Sales, el importe completo debe sincronizarse sin ser dividido por la cantidad de línea. Por lo tanto, debe definir método de cálculo de descuentos como **Artículo de línea** en Sales.
    - Cuando una línea de pedido de ventas se sincroniza de Sales a Supply Chain Management, se usará el importe de descuento de línea completo. Dado que Supply Chain Management no tiene ningún campo que pueda almacenar el importe de descuento completo para una línea, el importe se divide por la cantidad y se almacena en el campo **Descuento de línea**. El redondeo que se produzca durante esta división se almacena en el campo **Gastos de ventas** en la línea de ventas.

### <a name="example-synchronization-from-sales-to-supply-chain-management"></a>Ejemplo: Sincronización de Sales a Supply Chain Management

Tiene el siguiente pedido de ventas:

+ **Ventas:** Cantidad = 3, descuento por línea = $10.00
+ **Supply Chain Management:** Cantidad = 3, importe de descuento de línea = 3,33 $, cargo de ventas = -0,01 $

Si sincroniza desde Supply Chain Management a Sales, obtendrá el siguiente resultado:

+ **Supply Chain Management:** Cantidad = 3, importe de descuento de línea = 3,33 $, cargo de ventas = -0,01 $
+ **Ventas:** Cantidad = 3, descuento por línea = (3 × $3.33) + $0.01 = $10.00

## <a name="dual-write-solution-for-sales"></a>Solución de doble escritura para Sales

Se han agregado nuevos campos a la entidad **Pedido** y se muestran en la página. La mayoría de estos campos aparecen en la pestaña **Integración** en Ventas. Hay algunos campos especiales:

+ El campo **Estado de procesamiento** muestra el estado de procesamiento del pedido en Supply Chain Management. Este campo está bloqueado y muestra solo el estado del pedido de Supply Chain Management. Los siguientes valores están disponibles:

    + **Activo** – El estado después de que el pedido se active en Sales mediante el botón **Activar**.
    + **Confirmado**
    + **Entregado**
    + **Facturado**
    + **Parcialmente entregado**
    + **Parcialmente facturado**
    + **Seleccionado**
    + **Cancelada**

    La siguiente tabla muestra cómo se asigna el estado de procesamiento al valor **Código de estado de CRM**.

    | Estado de procesamiento           | Código de estado CRM    |
    |-----------------------------|--------------------|
    | Activas                      | Nuevo/Pendiente/En espera |
    | Confirmado/elegido            | En proceso        |
    | Parcialmente entregado         | Parcial            |
    | Entregado                   | Completada           |
    | Facturado/Facturado parcialmente | Facturado           |
    | Cancelada                    | Sin dinero           |

+ Los botones **Crear factura** y **Cancelar pedido** en la página **Pedido de ventas** están ocultos en Sales.
+ El valor **Estado del pedido de ventas** permanecerá **Activo** para ayudar a garantizar que los cambios de Supply Chain Management se incluyen en el pedido de ventas de Sales. Para controlar este comportamiento, establezca el valor del **Statecode \[Status\]** en **Activo**.

## <a name="invoices"></a>Facturas

Las facturas de ventas se crean en Supply Chain Management y se sincronizan en Sales. Tenga en cuenta los aspectos siguientes:

+ El campo **Número de factura** se ha agregado a la entidad **Factura** y se muestra en la página.
+ El botón **Crear factura** de la página **Pedido de ventas** se oculta, ya que las facturas se crearán en Supply Chain Management y se sincronizarán en Sales. No se puede editar la página **Factura** porque las facturas se sincronizarán desde Supply Chain Management.
+ El valor de **Estado del pedido de ventas** cambia automáticamente a **Facturado** si la factura relacionada de Supply Chain Management se ha sincronizado con Sales. Además, el propietario del pedido de ventas desde el cual se creó la factura, se asigna como propietario de la factura. Por tanto, el propietario del pedido de ventas puede ver la factura.
+ Los campos **Condiciones de flete**, **Condiciones de entrega** y **Modo de entrega** no se incluyen en las asignaciones predeterminadas. Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.

## <a name="templates"></a>Plantillas

Cliente potencial a efectivo incluye una colección de mapas de entidad básicos que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.

| Aplicaciones de Finance and Operations | Aplicaciones basadas en modelos en Dynamics 365 | Descripción |
|-----------------------------|-----------------------------------|-------------|
| Encabezados de factura de ventas V2    | facturas                          |             |
| Líneas de factura de ventas V2      | invoicedetails                    |             |
| Encabezado de pedidos de ventas de CDS     | salesorders                       |             |
| Líneas de pedido de ventas de CDS       | salesorderdetails                 |             |
| Códigos de origen de pedido de ventas    | msdyn\_salesorderorigins          |             |
| Encabezado de presupuesto de ventas de CDS  | presupuestos                            |             |
| Líneas de presupuesto de ventas de CDS   | quotedetails                      |             |

Estos son los mapas de entidades centrales relacionadas para cliente potencial a efectivo:

+ [Clientes V3 para cuentas](customer-mapping.md#customers-v3-to-accounts)
+ [Contactos V2 de CDS para contactos](customer-mapping.md#cds-contacts-v2-to-contacts)
+ [Clientes V3 para contactos](customer-mapping.md#customers-v3-to-contacts)
+ [Productos lanzados V2 para msdyn_sharedproductdetails](product-mapping.md#released-products-v2-to-msdyn_sharedproductdetails)
+ [Todos los productos para msdyn_globalproducts](product-mapping.md#all-products-to-msdyn_globalproducts)
+ [Lista de precios](product-mapping.md)

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [sales invoice](includes/SalesInvoiceHeaderV2Entity-invoice.md)]

[!include [sales invoice line](includes/SalesInvoiceLineV2Entity-invoicedetail.md)]

[!include [sales order header](includes/SalesOrderHeaderCDSEntity-salesorder.md)]

[!include [sales order line](includes/SalesOrderLineCDSEntity-salesorderdetails.md)]

[!include [sales order origin](includes/SalesOrderOriginEntity-msdyn-salesorderorigin.md)]

[!include [sales quotation header](includes/SalesQuotationHeaderCDSEntity-quote.md)]

[!include [sales quotation line](includes/SalesQuotationLineCDSEntity-QuoteDetails.md)]
