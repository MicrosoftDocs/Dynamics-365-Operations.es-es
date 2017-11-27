---
title: "Sincronice los encabezados y las líneas del presupuesto de Sales con Finance and Operations"
description: "En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas del presupuesto de ventas de Microsoft Dynamics 365 for Sales (ventas) con Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
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
ms.openlocfilehash: c8cfc484eed02423dbf0c7caaf8ac2337b6ac38d
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a>Sincronice los encabezados y las líneas del presupuesto de Sales con Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Para poder usar el cliente potencial para cobrar la solución, familiarícese con [Integración de datos de Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration). 

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas del presupuesto de ventas de Microsoft Dynamics 365 for Sales (ventas) con Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (finanzas y operaciones). 

## <a name="template-and-tasks"></a>Plantilla y tareas

Las plantillas y las tareas subyacentes siguientes se usan para sincronizar encabezados y líneas del presupuestos de ventas de Sales a Finance and Operations:

- **Nombre de la plantilla:** Presupuestos de ventas (Sales a Fin and Ops)
- **Nombres de las tareas en el proyecto:**

    - QuoteHeader
    - QuoteLine

Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los encabezados y líneas del presupuesto de ventas:

- Productos (de Fin and Ops a Sales)
- Cuentas (de Sales a Fin and Ops), si es que se usan
- Contactos a Clientes (de Sales a Fin and Ops) si es que se usan

## <a name="entity-set"></a>Conjunto de entidades

| Ventas        | CDS           | Finance and Operations    |
|--------------|---------------|---------------------------|
| Ofertas       | Presupuesto     | Encabezados de presupuesto de ventas   |
| QuoteDetails | QuotationLine | Líneas de presupuesto de ventas de CDS |

## <a name="entity-flow"></a>Flujo de la entidad

Los presupuestos de ventas se crean en Sales y se sincronizan en Finance and Operations.

Los presupuestos de ventas de Sales se sincronizan solo si se cumplen las siguientes condiciones:

- Todos los productos en las líneas de presupuesto de ventas se mantienen externamente.
- El presupuesto de ventas está activo o activado.

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales

El campo **Solo tiene productos mantenidos externamente** se ha agregado a la entidad Presupuesto para realizar un seguimiento constante si el presupuesto de ventas se compone por completo de productos mantenidos externamente. Si un presupuesto de ventas solo tiene productos mantenidos externamente, los productos se mantienen en Finance and Operations. Este comportamiento ayuda a garantizar que no intenta sincronizar las líneas de presupuesto de ventas con productos desconocidos para Finance and Operations.

Todos los productos y líneas del presupuesto se actualizan con la información **Solo tiene productos mantenidos externamente** de la cabecera de presupuesto. Esta información se puede encontrar en el campo **Solo tiene productos mantenidos externamente** en la entidad Línea de presupuesto.

Los campos **Descuento**, **Cargos** e **Impuestos** se controlan mediante una configuración compleja en Finance and Operations. Esta configuración no admite actualmente la asignación de la integración. En el diseño actual, los campos **Precio**, **Descuento**, **Cargo** e **Impuestos** son dominados y gestionados por Finance and Operations.

En Sales, la solución crea los siguientes campos de solo lectura, ya que los valores no se sincronizan con Finance and Operations:

- **Campos de solo lectura en el encabezado del presupuesto de ventas:** % de descuento, Descuento, Importe del fleje
- **Campos de solo lectura en líneas de presupuesto de ventas:** Impuestos

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

Antes de sincronizar los pedidos de ventas, es importante actualizar los sistemas mediante la configuración siguiente:

### <a name="setup-in-sales"></a>Configuración en Sales

- Vaya a **Configuración** &gt; **Administración** &gt; **Configuración del sistema** &gt; **Ventas** y asegúrese de que el campo **Método de cálculo del descuento** está establecido en **Por unidad**. Este valor ayuda a garantizar que el descuento del artículo de la línea de Sales coincide con la configuración en Finance and Operations. De lo contrario, el descuento no será correcto en Finance and Operations, ya que Finance and Operations leerá el descuento como un descuento por unidad incluso si era un descuento por línea en Sales.

### <a name="setup-in-finance-and-operations"></a>Configuración en Finance and Operations

- Vaya a **Clientes** &gt; **Configuración** &gt; **Parámetros de clientes**. En la pestaña **Secuencia numérica**, seleccione la secuencia numérica para presupuestos de ventas y luego haga clic en **Ver detalles**. A continuación, en **Configuración general**, establezca el campo **Manual** en **Sí**.
- Vaya a **Clientes** &gt; **Configuración** &gt; **Parámetros de clientes**. A continuación, en la pestaña **Envíos**, establezca el campo **Control de fecha de entrega** en **Ninguno**. Este valor ayuda a evitar que la sincronización falle para presupuestos de ventas.

### <a name="setup-in-the-data-integration-project"></a>Configuración del proyecto de integración de datos

#### <a name="quoteheader"></a>QuoteHeader

- El campo **Fecha de entrega solicitada** es obligatorio en Finance and Operations, y la sincronización fallará si el campo se deja en blanco. Para evitar este problema, si el campo está en blanco, la fecha predeterminada se toma de **Origen &gt; CDS**. La fecha debe actualizarse a un valor preferido. Actualmente, no puede introducir un valor como **Hoy** para representar la fecha de hoy. Debe introducir una fecha específica. El valor de plantilla predeterminado para **Fecha de entrega solicitada** es **1/1/2020**.
- El campo **Código de país/región de la dirección** es obligatorio en Finance and Operations. Para ayudar a evitar errores de sincronización, puede especificar un valor predeterminado que se usa si el campo se deja en blanco en Sales. Este valor predeterminado también resulta útil, ya que no tiene que introducir manualmente un valor en el campo **País/región** para direcciones locales. No hay valor de plantilla predeterminado para **DeliveryAddressCountryRegionISOCode**.
- Actualice la asignación para **Identificador de la organización de CDS** en **Origen &gt; CDS** para que coincida con la **Organización de CDS** en la entidad de organización:

    - El valor de plantilla predeterminado para **Organization_OrganizationId** es **ORG001**.
    - El valor de plantilla predeterminado para **Account_Organization_OrganizationId** es **ORG001**.
    - El valor de plantilla predeterminado para **InvoiceAccount_OrganizationId** es **ORG001**.

#### <a name="quoteline"></a>QuoteLine

- Actualice la asignación para **Identificador de la organización de CDS** en **Origen &gt; CDS** para que coincida con la **Organización de CDS** en la entidad de organización:

    - El valor de plantilla predeterminado para **Organization_OrganizationId** es **ORG001**.
    - El valor de plantilla predeterminado para **Product_Organization_Organization_OrganizationId** es **ORG001**.
    - El valor de plantilla predeterminado para **Quotation_Organization_Organization_OrganizationId** es **ORG001**.

- El campo **Fecha de entrega solicitada** es obligatorio en Finance and Operations, y la sincronización fallará si el campo se deja en blanco. Para evitar este problema, si el campo está en blanco, la fecha predeterminada se toma de **Origen &gt; CDS**. La fecha debe actualizarse a un valor preferido. Actualmente, no puede introducir un valor como **Hoy** para representar la fecha de hoy. Debe introducir una fecha específica. El valor de plantilla predeterminado para **Fecha de entrega solicitada** es **1/1/2020**.
- Puede agregar las siguientes asignaciones desde **CDS &gt; Destino** para ayudar a garantizar que las líneas de presupuesto se importan en Finance and Operations si no hay información predeterminada del cliente o del producto:

    - **SiteId** – Se requiere un sitio para generar presupuestos y las líneas de pedido de ventas en Finance and Operations. No hay valor de plantilla predeterminado para **SiteId**.
    - **WarehouseId** – Se requiere un almacén para procesar presupuestos y las líneas de pedido de ventas en Finance and Operations. No hay valor de plantilla predeterminado para **WarehouseId**.

- Asegúrese de que la asignación del valor requerido para la unidad de medida (U. de M.) vendedora en Finance and Operations existe en la asignación **CDS &gt; Destino** para **Quantity_UOM.** a **SALESUNITSYMBOL**.

## <a name="template-mapping-in-data-integrator"></a>Asignación de la plantilla en el integrador de datos

> [!NOTE]
> - Los campos **Descuento**, **Cargos** e **Impuestos** se controlan mediante una configuración compleja en Finance and Operations. Esta configuración no admite actualmente la asignación de la integración. En el diseño actual, los campos **Precio**, **Descuento**, **Cargo** e **Impuestos** son gestionados por Finance and Operations.
> - Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no forman parte de las asignaciones predeterminadas. Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.

Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.

### <a name="quoteheader"></a>QuoteHeader

![Asignación de la plantilla en el integrador de datos](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a>QuoteLine

![Asignación de la plantilla en el integrador de datos](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Temas relacionados

[Sincronice los productos de Finance and Operations con productos en Sales](products-template-mapping.md)

[Sincronizar cuentas de Sales con clientes de Finance and Operations](accounts-template-mapping.md)

[Sincronice contactos de Sales con contactos o clientes en Finance and Operations](contacts-template-mapping.md)



