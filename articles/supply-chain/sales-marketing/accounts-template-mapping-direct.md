---
title: Sincronizar cuentas directamente desde Sales con clientes de Supply Chain Management
description: En este tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar cuentas de Dynamics 365 Sales en Supply Chain Management.
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
ms.openlocfilehash: 4624f7e31c6dca616ff4ee824453b8971c1865e7
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249897"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a>Sincronizar cuentas directamente desde Sales con clientes de Supply Chain Management

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Para poder usar la solución Prospect to cash, deberá familiarizarse con [Integración de datos en Common Data Service para aplicaciones](https://docs.microsoft.com/powerapps/administrator/data-integrator).

En este tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar cuentas directamente de Dynamics 365 Sales en Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Flujo de datos en Prospect to cash

La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Supply Chain Management y Sales.  Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos de cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Supply Chain Management y Sales. La ilustración siguiente muestra cómo se sincronizan los datos entre Supply Chain Management y Sales.

[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas

Para obtener acceso a las plantillas disponibles, abra [Centro de administración de PowerApps](https://preview.admin.powerapps.com/dataintegration). Seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

La plantilla y la tarea subyacente siguientes se usan para sincronizar cuentas de Sales en Supply Chain Management:

- **Nombre de la plantilla en la integración de datos:** Cuentas (de Sales a Fin and Ops) - Directos
- **Nombre de la tarea en el proyecto:** Cuentas - Clientes

No se requieren tareas de sincronización para que pueda producirse la sincronización de cuentas/clientes.

## <a name="entity-set"></a>Conjunto de entidades

| Ventas    | Gestión de la cadena de abastecimiento |
|----------|------------------------|
| Cuentas | Clientes V2           |

## <a name="entity-flow"></a>Flujo de la entidad

Las cuentas se administran en Sales y se sincronizan con Supply Chain Management como clientes. La propiedad **Mantenida externamente** de estos clientes se establece en **Sí** para realizar un seguimiento de los clientes que proceden de Sales. Durante la facturación, esta información se usa para filtrar las facturas que se sincronizan con Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales

El campo **Número de cuenta** está disponible en la página **Cuenta** . Se ha convertido en una clave natural y única para admitir la integración. La característica de clave natural de la solución de la gestión de relaciones con el cliente (CRM) puede afectar a los clientes que utilicen ya el campo **Número de cuenta** , pero que no usen los valores **Número de cuenta** únicos por cuenta. Actualmente, la solución de integración no admite este caso.

Cuando se crea una nueva cuenta, si todavía no existe un valor **Número de cuenta** , se genera automáticamente mediante una secuencia numérica. El valor consiste en **ACC**, seguido por una secuencia numérica que aumenta y después un sufijo de seis caracteres. He aquí un ejemplo: **ACC-01000-BVRCPS**

Cuando se aplique la solución de integración para Sales, una secuencia de comandos de actualización establece el campo **Número de cuenta** de las cuentas existentes en Sales. Si no hay valores para **Número de cuenta** , se usa la secuencia numérica que se ha mencionado anteriormente.

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

- La asignación **CustomerGroupId** se debe actualizar en un valor válido en Supply Chain Management. Puede especificar un valor predeterminado, o se puede definir el valor mediante una asignación del valor.

    El valor de plantilla predeterminado es **10**.

- Si agrega las asignaciones siguientes, puede ayudar a reducir el número de actualizaciones manuales necesarias en Supply Chain Management. Puede usar un valor predeterminado o asignar un valor de, por ejemplo, **País/región** o **Ciudad**.

    - **SiteId** – Se requiere un sitio para generar presupuestos y las líneas de pedido de ventas en Supply Chain Management. Un sitio predeterminado se puede obtener del producto, o el cliente del encabezado del pedido.

        El valor de plantilla predeterminado es **1**.

    - **WarehouseId** – Se requiere un almacén para procesar presupuestos y las líneas de pedido de ventas en Supply Chain Management. Un almacén predeterminado se puede obtener del producto, o el cliente del encabezado del pedido en Supply Chain Management.

        El valor de plantilla predeterminado es **13**.

    - **LanguageId** – Se requiere un sitio para generar presupuestos y pedidos de ventas en Supply Chain Management. De forma predeterminada, se usa el idioma del encabezado del pedido del cliente.

        El valor de plantilla predeterminado es **en-us**.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

> [!NOTE]
> Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no se incluyen en las asignaciones predeterminadas. Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.

Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en la integración de datos. 

> [!NOTE]
> La asignación muestra qué información de campos se sincronizará de Sales a Supply Chain Management.

![Asignación de la plantilla en la integración de datos](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a>Temas relacionados


[Cliente potencial a cliente](prospect-to-cash.md)

[Sincronizar cuentas directamente desde Sales con clientes de Supply Chain Management](accounts-template-mapping-direct.md)

[Sincronizar contactos directamente desde Sales con contactos o clientes de Supply Chain Management](contacts-template-mapping-direct.md)

[Sincronizar encabezados y líneas de pedidos de ventas directamente desde Supply Chain Management a Sales](sales-order-template-mapping-direct-two-ways.md)

[Sincronizar encabezados y líneas de factura de ventas directamente desde Supply Chain Management a Sales](sales-invoice-template-mapping-direct.md)

