---
title: "Sincronizar directamente encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations"
description: "En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas del presupuesto de ventas directamente de Microsoft Dynamics 365 for Sales (ventas) con Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: efe943f5c874ed041ce7984272ebc19f57cca6ef
ms.contentlocale: es-es
ms.lasthandoff: 11/01/2018

---

# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-finance-and-operations"></a>Sincronizar directamente encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations

[!include [banner](../includes/banner.md)]

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas del presupuesto de ventas directamente de Microsoft Dynamics 365 for Sales (ventas) con Microsoft Dynamics 365 for Finance and Operations.

> [!NOTE]
> Para poder usar la solución Prospect to cash, deberá familiarizarse con [Integrar datos en Common Data Service for Apps](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).

## <a name="data-flow-in-prospect-to-cash"></a>Flujo de datos en Prospect to cash

La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Finance and Operations y Sales. Las plantillas de integración de cliente viable y líquido que están disponibles con la característica de integración de datos permiten habilitar el flujo de datos de cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Finance and Operations y Sales. La ilustración siguiente muestra cómo se sincronizan los datos entre Finance and Operations y Sales.

[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="template-and-tasks"></a>Plantilla y tareas

La plantilla y las tareas subyacentes siguientes se usan para sincronizar encabezados y líneas del presupuestos de ventas directamente de Sales a Finance and Operations:

- **Nombre de la plantilla en la integración de datos:** Presupuestos de ventas (Sales y Fin and Ops) - Directos
- **Nombres de las tareas en el proyecto de integración de datos:**

    - QuoteHeader
    - QuoteLine

Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los encabezados y líneas del presupuesto de ventas:

- Productos (de Fin and Ops a Sales) - Directos
- Cuentas (de Sales a Fin and Ops) - Directos (si es que se usan)
- Contactos a Clientes (de Sales a Fin and Ops) - Directos (si es que se usan)

## <a name="entity-set"></a>Conjunto de entidades

| Ventas        | Finance and Operations     |
|--------------|----------------------------|
| Ofertas       | Encabezado de presupuesto de ventas de CDS |
| QuoteDetails | Líneas de presupuesto de ventas de CDS  |

## <a name="entity-flow"></a>Flujo de la entidad

Los presupuestos de ventas se crean en Sales y se sincronizan en Finance and Operations.

Los presupuestos de ventas de Sales se sincronizan solo si se cumplen las siguientes condiciones:

- Todos los productos de presupuestos en las líneas de ventas se mantienen externamente.
- Tras hacer clic en **Activar presupuesto**, el presupuesto de ventas se activa.

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales

El campo **Solo tiene productos mantenidos externamente** se ha agregado a la entidad **Presupuesto** para realizar un seguimiento constante si el presupuesto de ventas se compone por completo de productos mantenidos externamente. Si un presupuesto de ventas solo tiene productos mantenidos externamente, los productos se mantienen en Finance and Operations. Este comportamiento ayuda a garantizar que no intenta sincronizar las líneas de presupuesto de ventas que tienen productos desconocidos para Finance and Operations.

Todos los productos de presupuestos en el presupuesto de ventas se actualizan con información de **Solo tiene productos mantenidos externamente** de la cabecera de presupuesto de ventas. Esta información se encuentra en el campo **Solo tiene productos mantenidos externamente** en la entidad **QuoteDetails**.

Un descuento se puede agregar al producto de presupuesto y será sincronizado con Finance and Operations. Los campos **Descuento**, **Cargos** e **Impuestos** en el encabezado se controlan mediante una configuración compleja en Finance and Operations. Actualmente esta configuración no admite la asignación de la integración. En el diseño actual, los campos **Precio**, **Descuento**, **Cargo** e **Impuestos** son mantenidos y gestionados en Finance and Operations.

En Sales, la solución crea los siguientes campos de solo lectura, ya que los valores no se sincronizan con Finance and Operations:

- Campos de solo lectura en el encabezado del presupuesto de ventas: **% de descuento**, **Descuento** e **Importe del fleje**
- Campos de sólo lectura de productos de presupuesto: **Impuestos**

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

Antes de sincronizar presupuestos de ventas, es importante actualizar la configuración siguiente.

### <a name="setup-in-sales"></a>Configuración en Sales

- Asegúrese de que los permisos se configuran para el equipo al que está asignado el usuario desde la conexión establecida en Sales. Si utiliza datos de prueba, el usuario normalmente tiene acceso de administrador, pero no el equipo. Si el equipo no tiene derechos de administrador cuando usted ejecuta el proyecto desde la integración de datos, recibirá un mensaje de error que dice que falta el equipo principal.

    Para configurar permisos para el equipo, vaya a **Configuración** &gt; **Seguridad** &gt; **Equipos**, y seleccione el equipo relevante. Seleccione **Gestionar roles**, y seleccione un rol que tenga los permisos necesarios, como **Administrador del sistema**.

- Vaya a **Configuración** &gt; **Administración** &gt; **Configuración del sistema** &gt; **Sales**, y asegúrese de que se utilicen los valores siguientes:

    - La opción **Usar el sistema de cálculo del sistema de precios** se establece en **Sí**.
    - El campo **Método de cálculo de descuentos** se establece en **Artículo de línea**.

### <a name="setup-in-the-data-integration-project"></a>Configuración del proyecto de integración de datos

#### <a name="quoteheader"></a>QuoteHeader

- Asegúrese de que la asignación requerida existe para **Shipto\_country** como **DeliveryAddressCountryRegionISOCode**. En la asignación de valor, puede definir un valor predeterminado que se usa si el valor se deja en blanco. Simplemente deje en blanco el lado izquierdo, y establezca el lado derecho como el país o la región deseada. De esta manera, no es necesario escribir el país o la región para pedidos nacionales.

    El valor de plantilla es una asignación de valores en la que se asignan varios países o regiones, y donde un valor en blanco es igual a un valor **US**

#### <a name="quoteline"></a>QuoteLine

- Asegúrese de que existe la asignación de valores requerida para **SalesUnitSymbol** en Finance and Operations.
- Asegúrese de que las unidades necesarias están definidas en Sales.

    Un valor de plantilla que tiene una asignación de valores se define para **oumid.name** como **SalesUnitSymbol**.

- Opcional: Puede agregar las siguientes asignaciones para ayudar a garantizar que las líneas de presupuesto de ventas se importan en Finance and Operations si no hay información predeterminada del cliente o del producto:

    - **SiteId** – Se requiere un sitio para generar presupuestos y las líneas de pedido de ventas en Finance and Operations. No hay valor de plantilla predeterminado para **SiteId**.
    - **WarehouseId** – Se requiere un almacén para procesar presupuestos y las líneas de pedido de ventas en Finance and Operations. No hay valor de plantilla predeterminado para **WarehouseId**.

## <a name="template-mapping-in-data-integrator"></a>Asignación de la plantilla en el integrador de datos

> [!NOTE]
> - Los campos **Descuento**, **Cargos** e **Impuestos** se controlan mediante una configuración compleja en Finance and Operations. Actualmente esta configuración no admite la asignación de la integración. En el diseño actual, los campos **Precio**, **Descuento**, **Cargo** e **Impuestos** son gestionados por Finance and Operations.
> - Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no forman parte de las asignaciones predeterminadas. Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.

Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.

### <a name="quoteheader"></a>QuoteHeader

![Asignación de la plantilla en el integrador de datos](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a>QuoteLine

![Asignación de la plantilla en el integrador de datos](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Temas relacionados

[Prospect to cash](prospect-to-cash.md)


