---
title: Sincronizar contactos directamente desde Sales con contactos o clientes de Supply Chain Management
description: En este artículo se describen las plantillas y las tareas subyacentes que se usan para sincronizar entidades de Contacto (Contactos) y Contacto (Clientess) directamente de Dynamics 365 Sales a Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 10/25/2018
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
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 4ddb91c34816791d8eca80e4798eb46c1b496439
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857355"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a>Sincronizar contactos directamente desde Sales con contactos o clientes de Supply Chain Management

[!include [banner](../includes/banner.md)]



> [!NOTE]
> Para poder usar la solución Prospect to cash, deberá familiarizarse con [Integración de datos en Microsoft Dataverse para aplicaciones](/powerapps/administrator/data-integrator).

En este artículo se describen las plantillas y las tareas subyacentes que se usan para sincronizar tablas de Contacto (Contactos) y Contacto (Clientes) directamente de Dynamics 365 Sales a Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Flujo de datos en Prospect to cash

La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Supply Chain Management y Sales. Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos de cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Supply Chain Management y Sales. La ilustración siguiente muestra cómo se sincronizan los datos entre Supply Chain Management y Sales.

[![Flujo de datos en Prospect to cash.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas

Para obtener acceso a las plantillas disponibles, abra [Centro de administración de PowerApps](https://preview.admin.powerapps.com/dataintegration). Seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

Las plantillas y las tareas subyacentes siguientes se usan para sincronizar tablas de Contacto (contactos) de Sales con tablas de Contacto (clientes) de Supply Chain Management.

- **Nombres de las plantillas en la integración de datos**

    - Contactos (de Sales a Supply Chain Management) - Directo
    - Contactos a cliente (de Sales a Supply Chain Management) - Directo

- **Nombres de las tareas en el proyecto de integración de datos**

    - Contactos
    - ContactToCustomer

La tarea siguiente de sincronización es obligatoria antes de la sincronización de contactos: Cuentas (de Sales a Supply Chain Management)

## <a name="entity-sets"></a>Conjuntos de entidades

| Sales    | Gestión de la cadena de abastecimiento |
|----------|------------------------|
| Contactos | Contactos de Dataverse           |
| Contactos | Clientes V2           |

## <a name="entity-flow"></a>Flujo de la entidad

Los contactos se administran en Sales y se sincronizan con Supply Chain Management.

Un contacto de Sales se puede convertir en un contacto o un cliente en Supply Chain Management. Para determinar si un contacto de Sales se debe sincronizar con Supply Chain Management como contacto o cliente, el sistema buscará las siguientes propiedades en el contacto en Sales:

- **Sincronizar con un cliente en Supply Chain Management:** Contactos donde **Es el cliente activo** está establecido en **Sí**
- **Sincronizar con contacto en Supply Chain Management:** Contactos donde **Es cliente activo** se establece en **No** y **Empresa** (cuenta o contacto principal) apunta a una cuenta (no a un contacto)

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales

Una nueva columna **Es cliente activo** se ha agregado al contacto. Esta columna se utiliza para distinguir los contactos que tienen actividad de ventas y los contactos que no tienen actividad de ventas. **Es cliente activo** se establece en **Sí** únicamente para los contactos que tienen presupuestos, pedidos o facturas relacionados. Solo estos contactos se sincronizan con Supply Chain Management como clientes.

Una nueva columna **IsCompanyAnAccount** se ha agregado al contacto. Esta columna indica si un contacto está vinculado a una empresa (cuenta o contacto principal) del tipo **Cuenta**. Esta información se usa para identificar los contactos que se deben sincronizar con Supply Chain Management como contactos.

Una nueva columna **Número de contacto** se ha agregado al contacto para ayudar a garantizar una clave natural y única para la integración. Cuando se crea un contacto nuevo, un valor **Número de contacto** se genera automáticamente mediante una secuencia numérica. El valor consiste en **CON**, seguido por una secuencia numérica que aumenta y después un sufijo de seis caracteres. He aquí un ejemplo: **CON-01000-BVRCPS**

Cuando la solución de integración para Sales se aplica, una secuencia de comandos de actualización establece la columna **Número de contacto** para los contactos existentes usando la secuencia numérica que hemos mencionado antes. La secuencia de comandos de actualización también define la columna **Es cliente activo** en **Sí** para todos los contactos con actividad de ventas.

## <a name="in-supply-chain-management"></a>En Supply Chain Management

Los contactos se etiquetan con la propiedad **IsContactPersonExternallyMaintained**. Esta propiedad indica que un contacto determinado se mantiene externamente. En este caso, los contactos mantenidos externamente se mantienen en Sales.

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

### <a name="contact-to-customer"></a>Contacto con cliente

- **CustomerGroup** se requiere en Supply Chain Management. Para ayudar a evitar errores de sincronización, puede especificar un valor predeterminado en la asignación. El valor predeterminado se utiliza si la columna se deja en blanco en Sales.

    El valor de plantilla predeterminado es **10**.

- Si agrega las asignaciones siguientes, puede ayudar a reducir el número de actualizaciones manuales necesarias en Supply Chain Management. Puede usar un valor predeterminado o asignar un valor de, por ejemplo, **País/región** o **Ciudad**.

    - **SiteId**: un sitio predeterminado también se puede definir en productos de Supply Chain Management. Un sitio es obligatorio para generar presupuestos y pedidos de ventas en Supply Chain Management.

        No hay definido un valor de plantilla para **SiteId**.

    - **WarehouseId**: un almacén predeterminado también se puede definir en productos de Supply Chain Management. Un almacén es obligatorio para generar presupuestos y pedidos de ventas en Supply Chain Management.

        No hay definido un valor de plantilla para **WarehouseId**.

    - **LanguageId** – Se requiere un sitio para generar presupuestos y pedidos de ventas en Supply Chain Management.
    
        El valor de plantilla predeterminado es **en-us**.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en la integración de datos. 

> [!NOTE]
> La asignación muestra qué información de columnas se sincronizará de Sales a Supply Chain Management.

### <a name="contact-to-contact-example"></a>Ejemplo de Contacto para contactar

![Asignación de plantilla contacto a contactar en el integrador de datos.](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer-example"></a>Ejemplo de cliente para contactar

![Asignación de plantilla contacto a cliente en el integrador de datos.](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-articles"></a>Artículos relacionados

[Cliente potencial a cliente](prospect-to-cash.md)

[Sincronizar cuentas directamente desde Sales con clientes de Supply Chain Management](accounts-template-mapping-direct.md)

[Sincronizar productos directamente de Supply Chain Management con productos de Sales](products-template-mapping-direct.md)

[Sincronización de pedidos de ventas entre Sales y Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Sincronizar encabezados y líneas de factura de ventas directamente desde Supply Chain Management a Sales](sales-invoice-template-mapping-direct.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]