---
title: Sincronizar directamente cuentas de Sales con clientes de Finance and Operations
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar cuentas de Microsoft Dynamics 365 for Sales a Microsoft Dynamics 365 for Finance and Operations.
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
ms.openlocfilehash: 036389a1a52fdf15b73ab90c0a37108871a1a15e
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "1743357"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-finance-and-operations"></a>Sincronizar cuentas directamente desde Sales con clientes de Finance and Operations

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Para poder usar la solución Prospect to cash, deberá familiarizarse con [Integración de datos en Common Data Service para aplicaciones](https://docs.microsoft.com/powerapps/administrator/data-integrator).

En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar cuentas directamente de Microsoft Dynamics 365 for Sales a Microsoft Dynamics 365 for Finance and Operations.

## <a name="data-flow-in-prospect-to-cash"></a>Flujo de datos en Prospect to cash

La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Finance and Operations y Sales.  Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos sobre cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Finance and Operations y Sales. La ilustración siguiente muestra cómo se sincronizan los datos entre Finance and Operations y Sales.

[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas

Para obtener acceso a las plantillas disponibles, abra [Centro de gestión de PowerApps](https://preview.admin.powerapps.com/dataintegration). Seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

La plantilla y la tarea subyacente siguientes se usan para sincronizar cuentas de Sales en Finance and Operations:

- **Nombre de la plantilla en la integración de datos:** Cuentas (de Sales a Fin and Ops) - Directos
- **Nombre de la tarea en el proyecto:** Cuentas - Clientes

No se requieren tareas de sincronización para que pueda producirse la sincronización de cuentas/clientes.

## <a name="entity-set"></a>Conjunto de entidades

| Ventas    | Finance and Operations |
|----------|------------------------|
| Cuentas | Clientes V2           |

## <a name="entity-flow"></a>Flujo de la entidad

Las cuentas se administran en Sales y se sincronizan en Finance and Operations como clientes. La propiedad **Mantenida externamente** de estos clientes se establece en **Sí** para realizar un seguimiento de los clientes que proceden de Sales. Durante la facturación, esta información se usa para filtrar las facturas que se sincronizan con Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales

El campo **Número de cuenta** está disponible en la página **Cuenta** . Se ha convertido en una clave natural y única para admitir la integración. La característica de clave natural de la solución de la gestión de relaciones con el cliente (CRM) puede afectar a los clientes que utilicen ya el campo **Número de cuenta** , pero que no usen los valores **Número de cuenta** únicos por cuenta. Actualmente, la solución de integración no admite este caso.

Cuando se crea una nueva cuenta, si todavía no existe un valor **Número de cuenta** , se genera automáticamente mediante una secuencia numérica. El valor consiste en **ACC**, seguido por una secuencia numérica que aumenta y después un sufijo de seis caracteres. He aquí un ejemplo: **ACC-01000-BVRCPS**

Cuando se aplique la solución de integración para Sales, una secuencia de comandos de actualización establece el campo **Número de cuenta** de las cuentas existentes en Sales. Si no hay valores para **Número de cuenta** , se usa la secuencia numérica que se ha mencionado anteriormente.

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

- La asignación **CustomerGroupId** se debe actualizar en un valor válido en Finance and Operations. Puede especificar un valor predeterminado, o se puede definir el valor mediante una asignación del valor.

    El valor de plantilla predeterminado es **10**.

- Si agrega las asignaciones siguientes, puede ayudar a reducir el número de actualizaciones manuales necesarias en Finance and Operations. Puede usar un valor predeterminado o asignar un valor de, por ejemplo, **País/región** o **Ciudad**.

    - **SiteId** – Se requiere un sitio para generar presupuestos y las líneas de pedido de ventas en Finance and Operations. Un sitio predeterminado se puede obtener del producto, o el cliente del encabezado del pedido.

        El valor de plantilla predeterminado es **1**.

    - **WarehouseId** – Se requiere un almacén para procesar presupuestos y las líneas de pedido de ventas en Finance and Operations. Un almacén predeterminado se puede obtener del producto, o el cliente del encabezado del pedido en Finance and Operations.

        El valor de plantilla predeterminado es **13**.

    - **LanguageId** – Se requiere un idioma para generar presupuestos y pedidos de ventas en Finance and Operations. De forma predeterminada, se usa el idioma del encabezado del pedido del cliente.

        El valor de plantilla predeterminado es **en-us**.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

> [!NOTE]
> Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no se incluyen en las asignaciones predeterminadas. Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.

Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en la integración de datos. 

> [!NOTE]
> La asignación muestra qué información de campos se sincronizará de Sales a Finance and Operations.

![Asignación de la plantilla en la integración de datos](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a>Temas relacionados


[Prospect to cash](prospect-to-cash.md)

[Sincronizar directamente cuentas de Sales con clientes de Finance and Operations](accounts-template-mapping-direct.md)

[Sincronizar directamente contactos de Sales con contactos o clientes de Finance and Operations](contacts-template-mapping-direct.md)

[Sincronizar encabezados y líneas de pedido de ventas directamente desde Finance and Operations en Sales](sales-order-template-mapping-direct-two-ways.md)

[Sincronizar encabezados y líneas de factura directamente de Finance and Operations en Sales](sales-invoice-template-mapping-direct.md)

