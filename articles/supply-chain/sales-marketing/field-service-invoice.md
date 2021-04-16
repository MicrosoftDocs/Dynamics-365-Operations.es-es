---
title: Sincronizar facturas de acuerdos en Field Service con facturas de texto libre en Supply Chain Management
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar facturas de acuerdo en Dynamics 365 Field Service a facturas de texto libre en Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 04/10/2018
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
ms.openlocfilehash: f3066741781bd9058e09d7f577a35df4c9b453d4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819217"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a>Sincronizar facturas de acuerdos en Field Service con facturas de texto libre en Supply Chain Management

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar facturas de acuerdo en Dynamics 365 Field Service a facturas de texto libre en Dynamics 365 Supply Chain Management.

## <a name="templates-and-tasks"></a>Plantillas y tareas

Se utilizan la plantilla siguiente y las tareas subyacentes para ejecutar la sincronización de las facturas de acuerdos de Field Service con las facturas de servicios en Supply Chain Management.

**Nombre de la plantilla en la integración de datos**

- Facturas de acuerdo (Field service a Supply Chain Management)

**Nombres de las tareas en el proyecto de integración de datos**

- Encabezados de factura
- Líneas de factura

Las siguiente sincronización es necesaria antes de que pueda producirse la sincronización de las facturas de acuerdos:

- Cuentas (Sales a Supply Chain Management) - Direct

## <a name="entity-set"></a>Conjunto de entidades

| Field Service  | Gestión de la cadena de abastecimiento                 |
|----------------|----------------------------------------|
| facturas       | Encabezados de factura de servicios de cliente de Dataverse |
| invoicedetails | Líneas de factura de servicios de cliente de Dataverse   |

## <a name="entity-flow"></a>Flujo de la entidad

Las facturas creadas desde un acuerdo en Field Service se pueden sincronizar con Supply Chain Management mediante un proyecto de integración de datos del Microsoft Dataverse. Las actualizaciones de estas facturas se sincronizan a las facturas de Supply Chain Management si el estado contable de las facturas de servicios es **En proceso**. Una vez que las facturas de servicios se registren en Supply Chain Management y el estado contable se actualice a **Completado**, ya no se pueden sincronizar las actualizaciones desde Field Service.

## <a name="field-service-crm-solution"></a>Solución CRM de Field Service

La columna **Tiene líneas con origen del acuerdo** se ha agregado a la tabla **Factura**. Esta columna permite garantizar que solo las facturas que se crean a partir de un acuerdo se sincronicen. El valor es **verdadero** si la factura contiene al menos una línea de factura que origine desde un acuerdo.

La columna **Tiene origen del acuerdo** se ha agregado a la tabla **Línea de factura**. Esta columna permite garantizar que solo las líneas de factura que se crean a partir de un acuerdo se sincronicen. El valor es **verdadero** si la línea de factura se origina desde un acuerdo.

**Fecha de factura** es un campo obligatorio en Supply Chain Management. Por lo tanto, la columna debe contener un valor en Field Service antes de que se realice la sincronización. Para cumplir este requisito, se agrega la lógica siguiente:

- Si la columna **Fecha de factura** está en blanco en la tabla **Factura** (es decir, si no tiene ningún valor), se establece en la fecha actual en que se agrega una línea de factura que se origina desde un acuerdo.
- El usuario puede modificar la columna **Fecha de factura**. Sin embargo, cuando el usuario intenta guardar una factura que se origina desde un acuerdo, recibe un error de proceso de negocio si la columna **Fecha de factura** está en blanco en la factura.

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación

### <a name="in-supply-chain-management"></a>En Supply Chain Management

Un origen de factura se debe configurar para la integración, para distinguir las facturas de servicios en Supply Chain Management que se crean de facturas de acuerdos en Field Service. Cuando una factura tiene un origen de factura del tipo **Integración de factura de acuerdo**, el campo **Número de factura externo** se muestra en el encabezado **Factura de ventas**.

Además de aparecer en el encabezado de factura, la información **Número de factura externo** se pueden usar para ayudar a garantizar que las facturas que se crean desde facturas de acuerdo de Field Service se filtran durante la sincronización de Supply Chain Management con Field Service.

1. Vaya a **Clientes** \> **Configuración** \> **Códigos de origen de factura**.
2. Seleccione **Nuevo** para crear un nuevo origen de factura.
3. En el campo **Origen de factura**, especifique un nombre para el origen de la factura, como **FS**.
4. En el campo **Descripción**, especifique una descripción, como **Factura de acuerdo de Field Service**.
5. Seleccione la casilla de verificación **Asignación de tipo de origen**.
6. Establezca el campo **Tipo de origen de la factura** a **Integración de la factura de acuerdo**.
7. Seleccione **Guardar**.

### <a name="in-the-data-integration-project"></a>En el proyecto de integración de datos

Tarea: **Líneas de factura**  

Asegúrese de que el valor predeterminado del campo de Supply Chain Management **Mostrar valor de la cuenta principal** se haya actualizado para que coincida con el valor deseado.

El valor de plantilla predeterminado es **401100**.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a>Facturas de acuerdo (Field service a Supply Chain Management): encabezados de facturas

[![Asignación de la plantilla en la integración de datos](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a>Facturas de acuerdo (Field service a Supply Chain Management): líneas de facturas

[![Asignación de la plantilla en la integración de datos](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]