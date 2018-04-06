---
title: Sincronizar directamente contactos de Sales con contactos o clientes de Finance and Operations
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar las entidades Contacto (contactos) y Contacto (clientes) de Microsoft Dynamics 365 for Sales con Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 021a43c78cec83b23aff5dcc40db1a4be81aefc3
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---

# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-finance-and-operations"></a>Sincronizar contactos directamente desde Sales con contactos o clientes de Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Para poder usar la solución Prospect to cash, deberá familiarizarse con [Integración de datos de Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar directamente las entidades Contacto (contactos) y Contacto (clientes) de Microsoft Dynamics 365 for Sales con Microsoft Dynamics 365 for Finance and Operations.

## <a name="data-flow-in-prospect-to-cash"></a>Flujo de datos en Prospect to cash

La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Finance and Operations y Sales. Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos sobre cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Finance and Operations y Sales. La ilustración siguiente muestra cómo se sincronizan los datos entre Finance and Operations y Sales.

[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas

Para obtener acceso a las plantillas disponibles, abra [Centro de gestión de PowerApps](https://preview.admin.powerapps.com/dataintegration). Seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

Las plantillas y las tareas subyacentes siguientes se usan para sincronizar entidades Contacto (contactos) de Sales con entidades Contacto (clientes) de Finance and Operations:

- **Nombres de las plantillas en la integración de datos:**

    - Contactos (de Sales a Fin and Ops) - Directos
    - Contactos a Cliente (de Sales a Fin and Ops) - Directos

- **Nombres de las tareas en el proyecto de integración de datos:**

    - Contactos
    - ContactToCustomer

La tarea siguiente de sincronización es obligatoria antes de la sincronización de contacto: Cuentas (de Sales a Fin and Ops)

## <a name="entity-sets"></a>Conjuntos de entidades

| Ventas    | Finance and Operations |
|----------|------------------------|
| Contactos | Contactos de CDS           |
| Contactos | Clientes V2           |

## <a name="entity-flow"></a>Flujo de la entidad

Los contactos se administran en Sales y se sincronizan en Finance and Operations.

Un contacto de Sales se puede convertir en un contacto o un cliente de Finance and Operations. Para determinar si un contacto de Sales se debe sincronizar con Finance and Operations como contacto o cliente, el sistema buscará las siguientes propiedades en el contacto en Sales:

- **Sincronizar con un cliente en Finance and Operations:** Contactos donde **Es el cliente activo** está establecido en **Sí**
- **Sincronizar con contacto en Finance and Operations:** Contactos donde **Es cliente activo** se establece en **No** y **Empresa** (cuenta o contacto principal) apunta a una cuenta (no a un contacto)

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales

Un nuevo campo **Es cliente activo** se ha agregado al contacto. Este campo se utiliza para distinguir los contactos que tienen actividad de ventas y los contactos que no tienen actividad de ventas. **Es cliente activo** se establece en **Sí** únicamente para los contactos que tienen presupuestos, pedidos o facturas relacionados. Solo estos contactos se sincronizan con Finance and Operations como clientes.

Un nuevo campo **IsCompanyAnAccount** se ha agregado al contacto. Este campo indica si un contacto está vinculado a una empresa (cuenta o contacto principal) del tipo **Cuenta**. Esta información se usa para identificar los contactos que se deben sincronizar con Finance and Operations como contactos.

Un nuevo campo **Número de contacto** se ha agregado al contacto para ayudar a garantizar una clave natural y única para la integración. Cuando se crea un contacto nuevo, un valor **Número de contacto** se genera automáticamente mediante una secuencia numérica. El valor consiste en **CON**, seguido por una secuencia numérica que aumenta y después un sufijo de seis caracteres. He aquí un ejemplo: **CON-01000-BVRCPS**

Cuando la solución de integración para Sales se aplica, una secuencia de comandos de actualización establece el campo **Número de contacto** para los contactos existentes usando la secuencia numérica que hemos mencionado antes. La secuencia de comandos de actualización también define el campo **Es cliente activo** en **Sí** para todos los contactos con actividad de ventas.

## <a name="in-finance-and-operations"></a>En Finance and Operations

Los contactos se etiquetan con la propiedad **IsContactPersonExternallyMaintained**. Esta propiedad indica que un contacto determinado se mantiene externamente. En este caso, los contactos mantenidos externamente se mantienen en Sales.

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

### <a name="contact-to-customer"></a>Contacto con cliente

- **CustomerGroup** se requiere en Finance and Operations. Para ayudar a evitar errores de sincronización, puede especificar un valor predeterminado en la asignación. El valor predeterminado se utiliza si el campo se deja en blanco en Sales.

    El valor de plantilla predeterminado es **10**.

- Si agrega las asignaciones siguientes, puede ayudar a reducir el número de actualizaciones manuales necesarias en Finance and Operations. Puede usar un valor predeterminado o asignar un valor de, por ejemplo, **País/región** o **Ciudad**.

    - **SiteId**: un sitio predeterminado también se puede definir en productos de Finance and Operations. Un sitio es obligatorio para generar presupuestos y pedidos de ventas en Finance and Operations.

        No hay definido un valor de plantilla para **SiteId**.

    - **WarehouseId**: un almacén predeterminado también se puede definir en productos de Finance and Operations. Un almacén es obligatorio para generar presupuestos y pedidos de ventas en Finance and Operations.

        No hay definido un valor de plantilla para **WarehouseId**.

    - **LanguageId** – Se requiere un idioma para generar presupuestos y pedidos de ventas en Finance and Operations.
    
        El valor de plantilla predeterminado es **en-us**.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en la integración de datos. 

> [!NOTE]
> La asignación muestra qué información de campos se sincronizará de Sales a Finance and Operations.

### <a name="contact-to-contact"></a>Contacto con contacto

![Asignación de la plantilla en el integrador de datos](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a>Contacto con cliente

![Asignación de la plantilla en el integrador de datos](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>Temas relacionados

[Prospect to cash](prospect-to-cash.md)

[Sincronizar directamente cuentas de Sales con clientes de Finance and Operations](accounts-template-mapping-direct.md)

[Sincronizar directamente productos de Finance and Operations con productos de Sales](products-template-mapping-direct.md)

[Sincronizar encabezados y líneas de pedido de ventas directamente de Finance and Operations en Sales](sales-order-template-mapping-direct-two-ways.md)

[Sincronizar encabezados y líneas de factura directamente de Finance and Operations en Sales](sales-invoice-template-mapping-direct.md)



