---
title: Sincronizar directamente productos de Finance and Operations con productos de Sales
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar productos de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
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
ms.openlocfilehash: feb9fbc066162e2caa9fc5dbaeec2c063ae23060
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572613"
---
# <a name="synchronize-products-directly-from-finance-and-operations-to-products-in-sales"></a>Sincronizar productos directamente desde Finance and Operations con productos de Sales

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Para poder usar la solución Prospect to cash, deberá familiarizarse con [Integración de datos en Common Data Service para aplicaciones](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar productos directamente de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Flujo de datos en Prospect to cash

La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Finance and Operations y Sales. Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos sobre cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Finance and Operations y Sales. La ilustración siguiente muestra cómo se sincronizan los datos entre Finance and Operations y Sales.

[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas

Para obtener acceso a las plantillas disponibles, abra [Centro de gestión de PowerApps](https://preview.admin.powerapps.com/dataintegration). Seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

La plantilla y las tareas subyacentes siguientes se usan para sincronizar productos de Finance and Operations a Sales.

- **Nombre de la plantilla en la integración de datos:** Productos (Fin and Ops a Sales) - Directos
- **Nombre de la tarea en el proyecto de integración de datos**: Productos

No se requieren tareas de sincronización para que pueda producirse la sincronización de productos.

## <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations     | Ventas    |
|----------------------------|----------|
| Productos liberados para ventas | Productos |

## <a name="entity-flow"></a>Flujo de la entidad

Los productos se administran en Finance and Operations y se sincronizan en Sales. La entidad de datos **Productos liberados para ventas** en Finance and Operations exporta solo los productos que son *para ventas*. Los productos para ventas son productos que tienen la información que requieren para usarse en un pedido de ventas. Se aplican las mismas reglas cuando un producto se valida con la función **Validar** en la página **Producto emitido**.

El número de producto se usa como clave. Por tanto, cuando las variantes del producto se sincronizan con Sales, cada variante del producto tiene un Id. de producto individual.

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales

En Sales, un nuevo campo **Mantenidos externamente** se ha agregado en productos para indicar que un producto determinado se mantiene externamente. De forma predeterminada, el valor se establece en **Sí** de forma predeterminada durante la importación a Sales. Los siguientes valores están disponibles:

- **Sí** - El producto originado de Finance and Operations y no se podrá editar en Sales.
- **No** - El producto se ha especificado directamente en Sales.
- **(En blanco)** - El producto existía en Sales antes de que se habilitara la solución Prospect to cash.

La información **Mantenido externamente** ayuda a asegurarse que solo se sincronizarán con Finance and Operations presupuestos y pedidos de ventas con productos mantenidos externamente.

Los Productos mantenidos externamente se agregan automáticamente a la primera lista de precios válida con la misma divisa. Las listas de precios se organizan alfabéticamente por nombre. El precio de venta del producto de Finance and Operations se usa como precio en la lista de precios. Por tanto, debe haber una lista de precios existen en Sales para todas las divisas de ventas del producto en Finance and Operations. La divisa en los productos liberados para ventas se establece en la divisa de contabilidad de la entidad jurídica desde la que se exporta el producto.

> [!NOTE]
> - La sincronización de productos no se realizará correctamente a menos que haya una lista de precios que tenga una divisa correspondiente.
> - Puede controlar la lista de precios utilizada con la integración mediante la asignación de pricelevelid.name [Lista de precios predeterminada (Nombre)] en el proyecto de integración de datos. La entrada tiene que estar en letras minúsculas. Por ejemplo, el valor predeterminado para una lista de precios en las Ventas denominada ‘Estándar’ sería: Campo de destino: pricelevelid.name [Lista de precios predeterminada (Nombre)] y tipo de asignación: [ { "transformType": "Default", "defaultValue": "standard" } ].

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

- Antes de ejecutar la sincronización por primera vez, debe rellenar la tabla de producto único para los productos existentes en Finance and Operations. Los productos existentes no se sincronizarán hasta que este trabajo esté completado.

    1. En Finance and Operations, utilice Buscar para buscar **Rellenar tabla de producto único**.
    2. Seleccione **Rellenar tabla de producto único** para ejecutar el trabajo. Este trabajo se debe ejecutar una vez.

- Asegúrese de que la asignación de valores requeridas para la unidad de medida (U. de M.) vendedora entre Finance and Operations y Sales existe en la asignación de **SalesUnitSymbol** a **DefaultUnit (Nombre)**.
- Actualice la asignación de valores para el **Grupo de unidad** (**defaultuomscheduleid.name**) para que coincida con los **Grupos de unidad** en Sales.

    El valor de la plantilla predeterminada es **Unidad predeterminada**.

- Asegúrese de que las U. de M. de venta para todos los productos de Finance and Operations existen en Sales.
- Asegúrese de que las listas de precios existen en Sales para todas las divisas de ventas del producto en Finance and Operations.
- Cuando los productos se crean en Sales, pueden tener un estado de **Borrador** o **Activo**. El comportamiento se controla en **Configuración** > **Administración** > **Configuración del sistema** > **Sales** en Sales.

    Los productos que tienen estado **Borrador** cuando se crean deben activarse antes de que puedan agregarse a presupuestos o pedidos de ventas.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

La siguiente ilustración muestra un ejemplo de una asignación de plantilla en integración de datos. 

> [!NOTE]
> La asignación muestra qué información de campos se sincronizará de Sales a Finance and Operations.

![Asignación de la plantilla en el integrador de datos](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>Temas relacionados

[Prospect to cash](prospect-to-cash.md)

[Sincronizar directamente cuentas de Sales con clientes de Finance and Operations](accounts-template-mapping-direct.md)

[Sincronizar directamente contactos de Sales con contactos o clientes de Finance and Operations](contacts-template-mapping-direct.md)

[Sincronizar encabezados y líneas de pedido de ventas directamente desde Finance and Operations en Sales](sales-order-template-mapping-direct-two-ways.md)

[Sincronizar encabezados y líneas de factura directamente de Finance and Operations en Sales](sales-invoice-template-mapping-direct.md)



