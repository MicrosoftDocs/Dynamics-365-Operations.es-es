---
title: Sincronizar productos directamente de Supply Chain Management con productos de Sales
description: En este tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar productos de Dynamics 365 Supply Chain Management a Dynamics 365 Sales.
author: ChristianRytt
ms.date: 06/10/2019
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
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 576516e17f015e33ca54bb6beceec43158bee79cfb7bd9a2db132085674bc035
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742665"
---
# <a name="synchronize-products-directly-from-supply-chain-management-to-products-in-sales"></a>Sincronizar productos directamente de Supply Chain Management con productos de Sales

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> Para poder usar la solución Prospect to cash, deberá familiarizarse con [Integración de datos en Microsoft Dataverse para aplicaciones](/powerapps/administrator/data-integrator).

En este tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar productos de directamente de Dynamics 365 Supply Chain Management a Dynamics 365 Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Flujo de datos en Prospect to cash

La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Supply Chain Management y Sales. Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos de cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Supply Chain Management y Sales. La ilustración siguiente muestra cómo se sincronizan los datos entre Supply Chain Management y Sales.

[![Flujo de datos en Prospect to cash.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas

Para obtener acceso a las plantillas disponibles, abra [Centro de administración de Power Apps](https://admin.powerapps.com/dataintegration). Seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

La plantilla y las tareas subyacente siguientes se usan para sincronizar productos de Sales en Supply Chain Management a Sales.

- **Nombre de la plantilla en la integración de datos:** Productos (Supply Chain Management a Sales) - Direct
- **Nombre de la tarea en el proyecto de integración de datos**: Productos

No se requieren tareas de sincronización para que pueda producirse la sincronización de productos.

## <a name="entity-set"></a>Conjunto de entidades

| Gestión de la cadena de abastecimiento    | Ventas    |
|----------------------------|----------|
| Productos liberados para ventas | Productos |

## <a name="entity-flow"></a>Flujo de la entidad

Los productos se administran en Supply Chain Management y se sincronizan con Sales. La entidad de datos **Productos liberados para ventas** en Supply Chain Management exporta solo los productos que son *para ventas*. Los productos para ventas son productos que tienen la información que requieren para usarse en un pedido de ventas. Se aplican las mismas reglas cuando un producto se valida con la función **Validar** en la página **Producto emitido**.

El número de producto se usa como clave. Por tanto, cuando las variantes del producto se sincronizan con Sales, cada variante del producto tiene un Id. de producto individual.

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales

En Sales, un nuevo campo **Mantenidos externamente** se ha agregado en productos para indicar que un producto determinado se mantiene externamente. De forma predeterminada, el valor se establece en **Sí** de forma predeterminada durante la importación a Sales. Los siguientes valores están disponibles:

- **Sí**: el producto se ha originado en Supply Chain Management y no se podrá editar en Sales.
- **No** - El producto se ha especificado directamente en Sales.
- **(En blanco)** - El producto existía en Sales antes de que se habilitara la solución Prospect to cash.

El campo **Mantenido externamente** ayuda a garantizar que solo se sincronizarán con Supply Chain Management presupuestos y pedidos de ventas con productos mantenidos externamente.

Los Productos mantenidos externamente se agregan automáticamente a la primera lista de precios válida con la misma divisa. Las listas de precios se organizan alfabéticamente por nombre. El precio de venta del producto de Supply Chain Management se usa como precio en la lista de precios. Por tanto, debe haber una lista de precios existen en Sales para todas las divisas de ventas del producto en Supply Chain Management. La divisa en los productos liberados para ventas se establece en la divisa de contabilidad de la entidad jurídica desde la que se exporta el producto.

> [!NOTE]
> - La sincronización de productos no se realizará correctamente a menos que haya una lista de precios que tenga una divisa correspondiente.
> - Puede controlar la lista de precios utilizada con la integración mediante la asignación de pricelevelid.name [Lista de precios predeterminada (Nombre)] en el proyecto de integración de datos. La entrada tiene que estar en letras minúsculas. Por ejemplo, el valor predeterminado para una lista de precios en las Ventas denominada ‘Estándar’ sería: Campo de destino: pricelevelid.name [Lista de precios predeterminada (Nombre)] y tipo de asignación: [ { "transformType": "Default", "defaultValue": "standard" } ].

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

- Antes de ejecutar la sincronización por primera vez, debe rellenar la tabla de producto único para los productos existentes en Supply Chain Management. Los productos existentes no se sincronizarán hasta que este trabajo esté completado.

    1. En Supply Chain Management, utilice Buscar para buscar **Rellenar tabla de producto único**.
    2. Seleccione **Rellenar tabla de producto único** para ejecutar el trabajo. Este trabajo se debe ejecutar una vez.

- Asegúrese de que la asignación de valores requeridas para la unidad de medida (U. de M.) vendedora entre Supply Chain Management y Sales existe en la asignación de **SalesUnitSymbol** a **DefaultUnit (Nombre)**.
- Actualice la asignación de valores para el **Grupo de unidad** (**defaultuomscheduleid.name**) para que coincida con los **Grupos de unidad** en Sales.

    El valor de la plantilla predeterminada es **Unidad predeterminada**.

- Asegúrese de que las U. de M. de venta para todos los productos de Supply Chain Management existen en Sales.
- Asegúrese de que las listas de precios existen en Sales para todas las divisas de ventas del producto en Supply Chain Management.
- Cuando los productos se crean en Sales, pueden tener un estado de **Borrador** o **Activo**. El comportamiento se controla en **Configuración** > **Administración** > **Configuración del sistema** > **Sales** en Sales.

    Los productos que tienen estado **Borrador** cuando se crean deben activarse antes de que puedan agregarse a presupuestos o pedidos de ventas.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

La siguiente ilustración muestra un ejemplo de una asignación de plantilla en integración de datos. 

> [!NOTE]
> La asignación muestra qué información de campos se sincronizará de Sales a Supply Chain Management.

![Asignación de la plantilla en el integrador de datos.](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>Temas relacionados

[Cliente potencial a cliente](prospect-to-cash.md)

[Sincronizar cuentas directamente desde Sales con clientes de Supply Chain Management](accounts-template-mapping-direct.md)

[Sincronizar contactos directamente desde Sales con contactos o clientes de Supply Chain Management](contacts-template-mapping-direct.md)

[Sincronización de pedidos de ventas entre Sales y Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Sincronizar encabezados y líneas de factura de ventas directamente desde Supply Chain Management a Sales](sales-invoice-template-mapping-direct.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]