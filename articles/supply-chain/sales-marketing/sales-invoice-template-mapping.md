---
title: "Sincronizar encabezados y líneas de factura de Finance and Operations en Sales"
description: "En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de facturación de ventas de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: fb5ba099911deda5308daf92d82cd6b3489995bf
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-from-finance-and-operations-to-sales"></a>Sincronizar encabezados y líneas de factura de Finance and Operations en Sales

[!include[banner](../includes/banner.md)]

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de facturación de ventas de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales. 

## <a name="templates-and-tasks"></a>Plantillas y tareas

Las plantillas y las tareas subyacentes siguientes se usan para sincronizar encabezados y líneas de facturación de ventas de Finance and Operations a Sales:

- **Nombre de la plantilla en la integración de datos** 

     - Facturación de ventas (de Fin and Ops a Sales)

- **Nombres de las tareas en el proyecto de integración de datos**

    - SalesInvoiceHeader
    - SalesInvoiceLine

Tareas de sincronización necesarias antes de sincronizar el encabezado y las líneas de factura en Sales:
-   Productos (de Fin and Ops a Sales)
-   Cuentas (de Sales a Fin and Ops), si es que se usan
-   Contactos (de Sales a Fin and Ops), si es que se usan
-   Cabecera y líneas del pedido de ventas (de Fin and Ops a Sales)

## <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations                               | Common Data Service (CDS)              | Ventas          |
|------------------------------------------------------|------------------|----------------|
| Encabezados de factura de ventas de clientes mantenidos externamente | SalesInvoice     | Facturas       |
| Líneas de factura de ventas de clientes mantenidas externamente   | SalesInvoiceLine | InvoiceDetails |

## <a name="entity-flow"></a>Flujo de la entidad

Las facturas de ventas se crean en Finance and Operations y se sincronizan en Sales.

> [!NOTE]
> Los impuestos relacionados con los gastos en **Cabecera de las facturas de ventas** no se incluyen actualmente en la sincronización de Finance and Operations a Sales. Esto se debe a que Sales no admite información fiscal en el nivel de la cabecera. Se incluyen los cargos relacionados con los impuestos a nivel de línea.

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales

-  Se agrega el **Campo de número de factura** a la entidad **Factura** y se muestra en la página.
 
-  El botón **Crear factura** de la página **Pedido de ventas** se oculta, ya que las facturas se crearán en Finance and Operations y se sincronizarán en Sales. No se puede editar la página **Factura** porque las facturas se sincronizarán desde Finance and Operations.
 
-  El **estado del pedido de ventas** cambia automáticamente a **Facturado** si la factura relacionada de Finance and Operations se ha sincronizado con Sales. Además, el propietario del pedido de ventas desde el cual se creó la factura, se asigna como propietario de la factura. Esto ofrece al propietario del pedido de ventas la capacidad de ver la factura.
 
## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

Antes de sincronizar las facturas de ventas, es importante actualizar los sistemas mediante la configuración siguiente:

### <a name="setup-in-sales"></a>Configuración en Sales

- En **Configuración** > **Administración** > **Configuración del sistema** > **Sales**, asegúrese de que la opción **Usar el sistema de cálculo del sistema de precios** está establecida en **Sí**. 

- En **Configuración** > **Administración** > **Configuración del sistema** > **Sales**, asegúrese de que la opción **Método de cálculo de descuentos** está establecida en **Artículo de línea**. 

### <a name="setup-in-the-data-integration-project"></a>Configuración del proyecto de integración de datos

#### <a name="salesinvoiceheader-task"></a>Tarea SalesInvoiceHeader

- Actualice la asignación del **id. de la organización de CDS** en **Origen** > **CDS**. 

    -  El valor de plantilla predeterminado de **SalesOrder_Organization_OrganizationId** es ORG001.
    -  El valor de plantilla predeterminado de **Account_Organization_OrganizationId** es ORG001.
    -  El valor de plantilla predeterminado de **Organization_OrganizationId** es ORG001.

- Asegúrese de que la asignación necesaria existe en **Origen** > **CDS de InvoiceCountryRegionId** a **BillingAddress_Country**.

    -  El valor de la plantilla es **ValueMap** con varios países asignados.

- La **Lista de precios** es necesaria para poder crear facturas en Sales. Actualice el valor **ValueMap** en **CDS** > **Destino para pricelevelid.name [nombre de la lista de precios]** en la **lista de precios** que se usa en Sales según la divisa. Puede usar la **lista de precios** predeterminada de una sola divisa o usar el valor **ValueMap** si tiene **listas de precios** en varias divisas.

    -  El valor de la plantilla de **pricelevelid.name [nombre de la lista de precios]** es **ValueMap** basado en la **Divisa**.
    -  usd: CRM Service USA (ejemplo). 

#### <a name="salesinvoiceline-task"></a>Tarea de SalesInvoiceLine

- Asegúrese de que la asignación necesaria está en **Origen** > **CDS de la unidad de medida**.

- Asegúrese de que el valor necesario **ValueMap** de **SalesUnitSymbol** en Finance and Operations está en **Origen** > **Asignación de CDS**. 
    
    - El valor de la plantilla con **ValueMap** se define de **SalesUnitSymbol a Quantity_UOM**.
    
-  Actualice la asignación del **id. de la organización de CDS en Origen** > **CDS**. 

    -  El valor de plantilla predeterminado de **SalesInvoicer_Organization_OrganizationId** es ORG001.
    -  El valor de plantilla predeterminado de **Product_Organization_OrganizationId** es ORG001.
 
## <a name="template-mapping-in-data-integrator"></a>Asignación de la plantilla en el integrador de datos

> [!NOTE]
> Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío** y **Modo de entrega** no forman parte de las asignaciones predeterminadas. Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.

Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.

![Asignación de la plantilla en el integrador de datos](./media/sales-invoice-template-mapping-data-integrator-1.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-invoice-template-mapping-data-integrator-2.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-invoice-template-mapping-data-integrator-3.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-invoice-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Temas relacionados

[Sincronice los productos de Finance and Operations con productos en Sales](products-template-mapping.md)

[Sincronizar cuentas de Sales con clientes de Finance and Operations](accounts-template-mapping.md)

[Sincronizar contactos de Sales con contactos o clientes de Finance and Operations](contacts-template-mapping.md)

[Sincronizar encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations](sales-quotation-template-mapping.md)

[Sincronizar encabezados y líneas de pedido de ventas de Finance and Operations en Sales](sales-order-template-mapping.md)


