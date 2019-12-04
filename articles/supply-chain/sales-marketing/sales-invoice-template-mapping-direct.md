---
title: Sincronizar encabezados y líneas de factura de ventas directamente desde Supply Chain Management a Sales
description: En este tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de factura de ventas directamente de Dynamics 365 Supply Chain Management a Dynamics 365 Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: fb5073fe8db0b51c4ea378cac57097e15e88bf83
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814061"
---
# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Sincronizar encabezados y líneas de factura de ventas directamente desde Finance and Operations en Sales

[!include [banner](../includes/banner.md)]

En este tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de factura de ventas directamente de Dynamics 365 Supply Chain Management a Dynamics 365 Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Flujo de datos en Prospect to cash

La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Supply Chain Management y Sales. Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos de cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Supply Chain Management y Sales. La ilustración siguiente muestra cómo se sincronizan los datos entre Supply Chain Management y Sales.

[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas

Para obtener acceso a las plantillas disponibles, abra [Centro de administración de Power Apps](https://preview.admin.powerapps.com/dataintegration). Seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

La plantilla y las tareas subyacentes siguientes se usan para sincronizar encabezados y líneas de la factura de ventas de Supply Chain Management a Sales:

- **Nombre de la plantilla en la integración de datos:** Facturas de ventas (Fin and Ops a Sales) - Directos
- **Nombres de las tareas en el proyecto de integración de datos:**

    - SalesInvoiceHeader
    - SalesInvoiceLine

Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los encabezados y líneas de factura:

- Productos (Supply Chain Management a Sales) - Directo
- Cuentas (Sales a Supply Chain Management) - Directo (si se usa)
- Contactos (Sales a Supply Chain Management) - Directo (si se usa)
- Encabezado y líneas de pedido de ventas (Supply Chain Management a Sales) - Directo

## <a name="entity-set"></a>Conjunto de entidades

| Gestión de la cadena de abastecimiento                              | Ventas          |
|------------------------------------------------------|----------------|
| Encabezados de factura de ventas de clientes mantenidos externamente | Facturas       |
| Líneas de factura de ventas de clientes mantenidas externamente   | InvoiceDetails |

## <a name="entity-flow"></a>Flujo de la entidad

Las facturas de ventas se crean en Supply Chain Management y se sincronizan en Sales.

> [!NOTE]
> Actualmente, los impuestos relacionados con los gastos en cabecera de las facturas de ventas no se incluyen en la sincronización de Supply Chain Management a Sales. Sales no admite información fiscal en el nivel de la cabecera. Sin embargo, los impuestos relacionados con cargos en el nivel de línea se incluyen en la sincronización.

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales

- El campo **Número de factura** se ha agregado a la entidad **Factura** y se muestra en la página.
- El botón **Crear factura** de la página **Pedido de ventas** se oculta, ya que las facturas se crearán en Supply Chain Management y se sincronizarán en Sales. No se puede editar la página **Factura** porque las facturas se sincronizarán desde Supply Chain Management.
- El valor de **Estado del pedido de ventas** cambia automáticamente a **Facturado** si la factura relacionada de Supply Chain Management se ha sincronizado con Sales. Además, el propietario del pedido de ventas desde el cual se creó la factura, se asigna como propietario de la factura. Por tanto, el propietario del pedido de ventas puede ver la factura.

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

Antes de sincronizar facturas de ventas, es importante actualizar la configuración siguiente en los sistemas.

### <a name="setup-in-sales"></a>Configuración en Sales

Vaya a **Configuración** > **Administración** > **Configuración del sistema** > **Sales**, y asegúrese de que se utilicen los valores siguientes:

- La opción **Usar el sistema de cálculo del sistema de precios** se establece en **Sí**.
- El campo **Método de cálculo de descuentos** se establece en **Artículo de línea**.

### <a name="setup-in-the-data-integration-project"></a>Configuración del proyecto de integración de datos

#### <a name="salesinvoiceheader-task"></a>Tarea SalesInvoiceHeader

- Asegúrese de que la asignación requerida existe para **InvoiceCountryRegionId** como **BillingAddress\_Country**.

    El valor de plantilla es una asignación de valores en la que se asignan varios países o regiones.

- Una lista de precios es necesaria para poder crear facturas en Sales. Actualice la asignación de valores para **pricelevelid.name \[Nombre de la lista de precios\]** con la lista de precios que se usa en Sales según la divisa. Puede usar la lista de precios predeterminada para una sola divisa. Como alternativa, si tiene listas de precios en varias divisas, puede usar una asignación de valores.

    El valor de la plantilla para **pricelevelid.name \[Nombre de lista de precios\]** es una asignación de valores que se basa en la divisa con USD = CRM Service USA (ejemplo).  
    
#### <a name="salesinvoiceline-task"></a>Tarea de SalesInvoiceLine

- Asegúrese de que la asignación requerida existe para **Unidad de medida**.
- Asegúrese de que existe la asignación de valores requerida para **SalesUnitSymbol** en Supply Chain Management.

    Un valor de plantilla que tiene una asignación de valores se define para **SalesUnitSymbol** como **Quantity\_UOM**.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

> [!NOTE]
> Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no se incluyen en las asignaciones predeterminadas. Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.

Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en la integración de datos. 

> [!NOTE]
> La asignación muestra qué información de campos se sincronizará de Sales a Supply Chain Management.

### <a name="salesinvoiceheader"></a>SalesInvoiceHeader

![Asignación de la plantilla en la integración de datos](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a>SalesInvoiceLine

![Asignación de la plantilla en la integración de datos](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Temas relacionados

[Cliente potencial a cliente](prospect-to-cash.md)

[Sincronizar cuentas directamente desde Sales con clientes de Supply Chain Management](accounts-template-mapping-direct.md)

[Sincronizar productos directamente de Supply Chain Management con productos de Sales](products-template-mapping-direct.md)

[Sincronizar contactos directamente desde Sales con contactos o clientes de Supply Chain Management](contacts-template-mapping-direct.md)

[Sincronización de pedidos de ventas entre Sales y Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)
