---
title: Sincronice contactos de Sales con contactos o clientes en Finance and Operations
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar Contacto (contactos) y Contacto (clientes) de Microsoft Dynamics 365 for Sales con Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c838fef502f643c764fade9cd79ae770ffc36974
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-contacts-from-sales-to-contacts-or-customers-in-finance-and-operations"></a>Sincronice contactos de Sales con contactos o clientes en Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Para poder usar el cliente potencial para cobrar la solución, familiarícese con [Integración de datos de Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration). 

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar entidades de Contacto (contactos) y Contacto (clientes) de Microsoft Dynamics 365 for Sales con Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (finanzas y operaciones).

## <a name="templates-and-tasks"></a>Plantillas y tareas

Las plantillas y las tareas subyacentes siguientes se usan para sincronizar Contacto (contactos) de Sales con Contacto (clientes) de Finance and Operations:

- **Nombres de la plantillas:**

    - Contactos (de Sales a Fin and Ops)
    - Contactos a Cliente (de Sales a Fin and Ops)

- **Nombres de las tareas en el proyecto:**

    - Contactos
    - ContactToCustomer

La tarea siguiente de sincronización es obligatoria antes de la sincronización de contacto: Cuentas (de Sales a Fin and Ops)

## <a name="entity-sets"></a>Conjuntos de entidades

| Ventas    | CDS     | Finance and Operations |
|----------|---------|------------------------|
| Contactos | Contacto | Contactos de CDS           |
| Contactos | Cuenta | Clientes V2           |

## <a name="entity-flow"></a>Flujo de la entidad

Los contactos se administran en Sales y se sincronizan con Common Data Service (CDS) y Finance and Operations.

Un contacto de Sales se puede convertir en un contacto de CDS y Finance and Operations. Como alternativa, puede convertirse en una cuenta en CDS y un cliente en Finance and Operations. Para determinar si un contacto debe elegirse en Sales para sincronizarlo con CDS y Finance and Operations (por ejemplo, Contactos en Sales &gt; Contacto en CDS &gt; Contactos en Finance and Operations), el sistema buscará las siguientes propiedades en Contacto en Sales:

- **Sincronizar con cuenta en CDS y Cliente en Finance and Operations:** Contactos donde **Es el cliente activo** está establecido en **Sí**
- **Sincronizar con Contacto en CDS y Contacto en Finance and Operations:** Contactos donde **Es cliente activo** se establece en **No** y **Empresa** (cuenta o contacto principal) apunta a una cuenta (no a un contacto)

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales 

Un nuevo campo **Es cliente activo** se ha agregado al contacto. Este campo se utiliza para distinguir los contactos que tienen actividad de ventas y los contactos que no tienen actividad de ventas. **Es cliente activo** se establece en **Sí** únicamente para los contactos que tienen presupuestos, pedidos o facturas relacionados. Solo estos contactos se sincronizan con Finance and Operations como clientes.

Un nuevo campo **IsCompanyAnAccount** se ha agregado al contacto. Este campo se usa para indicar si un contacto está vinculado a una empresa (cuenta o contacto principal) del tipo **Cuenta** . Esta información se usa para identificar los contactos que se deben sincronizar con Finance and Operations como contactos.

Un nuevo campo **Número de contacto** se ha agregado al contacto para ayudar a garantizar una clave natural y única para la integración. Cuando se crea un contacto nuevo, un valor **Número de contacto** se genera automáticamente mediante una secuencia numérica. El valor consiste en **CON**, seguido por una secuencia numérica que aumenta y después un sufijo de seis caracteres. He aquí un ejemplo: **CON-01000-BVRCPS**

Cuando la solución de integración para Sales se agrega a Sales, una secuencia de comandos de actualización establece el campo **Número de contacto** para los contactos existentes usando la secuencia numérica que hemos tratado antes. La secuencia de comandos de actualización también define el campo **Es cliente activo** en **Sí** para todos los contactos con actividad de ventas.

## <a name="in-finance-and-operations"></a>En Finance and Operations 

Los contactos se etiquetan con la propiedad **IsContactPersonExternallyMaintained**. Esta propiedad indica que un contacto determinado se mantiene externamente. En este caso, los contactos mantenidos externamente se mantienen en Sales.

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

### <a name="contact-to-contact"></a>Contacto con contacto

- Actualice el **identificador de la organización de CDS** en la asignación **Origen &gt; CDS**.

    - El valor de plantilla predeterminado para **Organization_OrganizationId [id. de organización]** es **ORG001**.
    - El valor de plantilla predeterminado para **PrimaryAccount_Organization_OrganizationId [id. de organización]** es **ORG001**.

- **Código de país/región de la dirección** se requiere en Finance and Operations. Para evitar errores de sincronización, puede especificar un valor predeterminado en la asignación **CDS &gt; Operaciones**. El valor predeterminado se utiliza si el campo se deja en blanco en Sales. El valor de plantilla predeterminado para **PrimaryAddressCountryRegionISOCode** es **EE. UU**.
- Asegúrese de que el valor para el campo siguiente existe en Finance and Operations. Si la información no se requiere en Finance and Operations, puede quitar la asignación de la asignación **CDS &gt; Destino**.

    - **Nombre de campo en Finance and Operations:** Decisión
    - **Asignación:** PrimaryAccountRole = DecisionMakingRole

### <a name="contact-to-customer"></a>Contacto con cliente

- Actualice el **identificador de la organización de CDS** en la asignación **Origen &gt; CDS**. El valor de plantilla predeterminado para **Organization_OrganizationId [id. de organización]** es **ORG001**.
- **Código de país/región de la dirección** se requiere en Finance and Operations. Para evitar errores de sincronización, puede especificar un valor predeterminado en la asignación **CDS &gt; Destino**. El valor predeterminado se utiliza si el campo se deja en blanco en Sales. El valor de plantilla predeterminado para **PrimaryAddressCountryRegionISOCode** es **EE. UU**.
- **CustomerGroup** se requiere en Finance and Operations. Para evitar errores de sincronización, puede especificar un valor predeterminado en la asignación **CDS &gt; Destino**. El valor predeterminado se utiliza si el campo se deja en blanco en Sales. El valor de plantilla predeterminado para **CustomerGroupId** es **10**.
- Si agrega las asignaciones siguientes desde **CDS &gt; Destino**, puede ayudar a reducir el número de actualizaciones manuales en Finance and Operations. Puede usar un valor predeterminado o asignar un valor de, por ejemplo, **País/región** o **Ciudad**.

    - **SiteId**: un sitio predeterminado también se puede definir en productos de Finance and Operations. Un sitio es obligatorio para generar presupuestos y pedidos de ventas en Finance and Operations. No hay definido un valor de plantilla para **SiteId**.
    - **WarehouseId**: un almacén predeterminado también se puede definir en productos de Finance and Operations. Un almacén es obligatorio para generar presupuestos y pedidos de ventas en Finance and Operations. No hay definido un valor de plantilla para **WarehouseId**.
    - **LanguageId**: Se requiere un idioma para generar presupuestos y pedidos de ventas en Finance and Operations. El valor de plantilla predeterminado para **LanguageId** es **en-us**.

## <a name="template-mapping-in-data-integrator"></a>Asignación de la plantilla en el integrador de datos

Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.

### <a name="contact-to-contact"></a>Contacto con contacto

![Asignación de la plantilla en el integrador de datos](./media/contacts-template-mapping-data-integrator-1.png)

![Asignación de la plantilla para contactos en el integrador de datos](./media/contacts-template-mapping-data-integrator-2.png)

### <a name="contact-to-customer"></a>Contacto con cliente

![Asignación de la plantilla en el integrador de datos](./media/contacts-template-mapping-data-integrator-3.png)

![Asignación de la plantilla para contactos en el integrador de datos](./media/contacts-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Temas relacionados

[Sincronice los productos de Finance and Operations con productos en Sales](products-template-mapping.md)

[Sincronizar cuentas de Sales con clientes de Finance and Operations](accounts-template-mapping.md)

[Sincronizar encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations](sales-quotation-template-mapping.md)

[Sincronizar encabezados y líneas de pedido de ventas de Finance and Operations en Sales](sales-order-template-mapping.md)

[Sincronizar encabezados y líneas de factura de Finance and Operations en Sales](sales-invoice-template-mapping.md)

