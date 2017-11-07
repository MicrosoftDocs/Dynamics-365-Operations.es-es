---
title: Sincronice las cuentas de Sales con clientes de Finance and Operations
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar cuentas de Microsoft Dynamics 365 for Sales con Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.
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
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: f322c5b273c29d863c059092bf1a41c424c19a7d
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-accounts-from-sales-to-customers-in-finance-and-operations"></a>Sincronice las cuentas de Sales con clientes de Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Para poder usar el cliente potencial para cobrar la solución, familiarícese con [Integración de datos de Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration). 

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar cuentas de Microsoft Dynamics 365 for Sales (ventas) con Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (finanzas y operaciones).

## <a name="template-and-task"></a>Plantilla y tarea

Las plantillas y las tareas subyacentes siguientes se usan para sincronizar cuentas de Sales en Finance and Operations:

- **Nombre de la plantilla:** Cuentas (Sales a Fin and Ops)
- **Nombre de la tarea en el proyecto:** Cuentas - Cuenta - Clientes

Tareas de sincronización requeridas antes de la sincronización de la cuenta/cliente: Ninguna

## <a name="entity-set"></a>Conjunto de entidades

| Ventas    | CDS     | Finance and Operations |
|----------|---------|------------------------|
| Cuentas | Cuenta | Empresas cliente              |

## <a name="entity-flow"></a>Flujo de la entidad

Las cuentas se administran en Sales y se sincronizan en Finance and Operations como clientes. La propiedad **Mantenida externamente** de estos clientes se establece en **Sí** para realizar un seguimiento de los clientes que proceden de Sales. Durante la facturación, esta información se usa para filtrar las facturas que se sincronizan con Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales

El campo **Número de cuenta** está disponible en la página **Cuenta** . Se ha convertido en una clave natural y única para admitir la integración. La característica de clave natural de la solución de la gestión de relaciones con el cliente (CRM) puede afectar a los clientes que utilicen ya el campo **Número de cuenta** , pero que no usen los valores **Número de cuenta** únicos por cuenta. Actualmente, la solución de integración no admite este caso.

Cuando se crea una nueva cuenta, si todavía no existe un valor **Número de cuenta** , se genera automáticamente mediante una secuencia numérica. El valor consiste en **ACC**, seguido por una secuencia numérica que aumenta y después un sufijo de seis caracteres. He aquí un ejemplo: **ACC-01000-BVRCPS**

Cuando se aplique la solución de integración para Sales, una secuencia de comandos de actualización establece el campo **Número de cuenta** de las cuentas existentes en Sales. Si no hay valores para **Número de cuenta** , se usa la secuencia numérica que se ha descrito anteriormente.

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

- La asignación **CustomerGroupId** de **CDS &gt; Destino** debe actualizarse a un valor válido en Finance and Operations. Puede especificar un valor predeterminado, o se puede definir el valor mediante una asignación del valor. El valor de plantilla predeterminado es **10**.
- **Código de país/región de la dirección** se requiere en Finance and Operations. Para evitar errores de sincronización, puede especificar un valor predeterminado en la asignación **CDS &gt; Destino**. El valor predeterminado se utiliza si el campo se deja en blanco en Sales.

    - El valor de plantilla predeterminado para **AddressCountryRegionISOCode** es **USA**.
    - El valor de plantilla predeterminado para **DeliveryAddressCountryRegionISOCode** es **USA**.

- Si agrega las asignaciones siguientes desde **CDS &gt; Destino**, puede ayudar a reducir el número de actualizaciones manuales necesarias en Finance and Operations. Puede usar un valor predeterminado o asignar un valor de, por ejemplo, **País/región** o **Ciudad**.

    - **SiteId** – Se requiere un sitio para generar presupuestos y las líneas de pedido de ventas en Finance and Operations. Un sitio predeterminado se puede obtener del producto, o el cliente del encabezado del pedido. El valor de plantilla predeterminado para **SiteId** es **1**.
    - **WarehouseId** – Se requiere un almacén para procesar presupuestos y las líneas de pedido de ventas en Finance and Operations. Un almacén predeterminado se puede obtener del producto, o el cliente del encabezado del pedido en Finance and Operations. El valor de plantilla predeterminado para **WarehouseId** es **13**.
    - **LanguageId** – Se requiere un idioma para generar presupuestos y pedidos de ventas en Finance and Operations. De forma predeterminada, se usa el idioma del encabezado del pedido del cliente. El valor de plantilla predeterminado para **LanguageId** es **en-us**.

- Actualice el identificador de la organización de CDS (**Organization_OrganizationId**) en la asignación **Origen &gt; CDS** . El valor de plantilla predeterminado es **ORG001**.

## <a name="template-mapping-in-data-integrator"></a>Asignación de la plantilla en el integrador de datos

> [!NOTE]
> Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no se incluyen en las asignaciones predeterminadas. Para asignar estos campos, debe configurar una asignación de valores. Las asignaciones de valores son específicas de los datos de las organizaciones entre las que se sincroniza la entidad.

Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.

![Asignación de la plantilla en el integrador de datos](./media/accounts-template-mapping-data-integrator-1.png)

![Asignación de la plantilla para cuentas en el integrador de datos](./media/accounts-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Temas relacionados

[Sincronice los productos de Finance and Operations con productos en Sales](products-template-mapping.md)

[Sincronice contactos de Sales con contactos o clientes en Finance and Operations](contacts-template-mapping.md)

[Sincronizar encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations](sales-quotation-template-mapping.md)

[Sincronizar encabezados y líneas de pedido de ventas de Finance and Operations en Sales](sales-order-template-mapping.md)

[Sincronizar encabezados y líneas de factura de Finance and Operations en Sales](sales-invoice-template-mapping.md)




