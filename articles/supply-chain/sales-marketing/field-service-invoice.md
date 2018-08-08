---
title: Sincronizar facturas de acuerdos en Field Service con facturas de servicios en Finance and Operations
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar facturas de acuerdos en Microsoft Dynamics 365 for Field Service con facturas en Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2018
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
ms.sourcegitcommit: ace66c037953f4b1b2e8b93a315faefdb090b1eb
ms.openlocfilehash: 6672e283a5e56b068e3494d53a0fd6dd08253ba9
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-finance-and-operations"></a>Sincronizar facturas de acuerdos en Field Service con facturas de servicios en Finance and Operations

[!include[banner](../includes/banner.md)]

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar facturas de acuerdos en Microsoft Dynamics 365 for Field Service con facturas en Microsoft Dynamics 365 for Finance and Operations.

## <a name="templates-and-tasks"></a>Plantillas y tareas

Se utilizan la plantilla siguiente y las tareas subyacentes para ejecutar la sincronización de las facturas de acuerdos de Field Service con las facturas de servicios en Finance and Operations.

**Nombre de la plantilla en la integración de datos:**

- Facturas de acuerdos (Field Service to Fin and Ops)

**Nombres de las tareas en el proyecto de integración de datos:**

- Encabezados de factura
- Líneas de factura

Las siguiente sincronización es necesaria antes de que pueda producirse la sincronización de las facturas de acuerdos:

- Cuentas (Sales to Fin and Ops) - Direct

## <a name="entity-set"></a>Conjunto de entidades

| Field Service  | Finance and Operations                 |
|----------------|----------------------------------------|
| facturas       | Encabezados de factura de servicios de cliente de CDS |
| invoicedetails | Líneas de factura de servicios de cliente de CDS   |

## <a name="entity-flow"></a>Flujo de la entidad

Las facturas creadas desde un acuerdo en Field Service se pueden sincronizar con Finance and Operations mediante un proyecto de integración de datos del Common Data Service (CDS). Las actualizaciones de estas facturas se sincronizan a las facturas de Finance and Operations si el estado contable de las facturas de servicios es **En proceso**. Una vez que las facturas de servicios se registren Finance and Operations y el estado contable se actualice a **Completado**, ya no se pueden sincronizar las actualizaciones desde Field Service.

## <a name="field-service-crm-solution"></a>Solución CRM de Field Service

El campo **Tiene líneas con origen del acuerdo** se ha agregado a la entidad **Factura**. Este campo permite garantizar que solo las facturas que se crean a partir de un acuerdo se sincronicen. El valor es **verdadero** si la factura contiene al menos una línea de factura que origine desde un acuerdo.

El campo **Tiene origen del acuerdo** se ha agregado a la entidad **Línea de factura**. Este campo permite garantizar que solo las líneas de facturas que se crean a partir de un acuerdo se sincronicen. El valor es **verdadero** si la línea de factura se origina desde un acuerdo.

**Fecha de factura** es un campo obligatorio en Finance and Operations. Por lo tanto, el campo debe contener un valor en Field Service antes de que se realice la sincronización. Para cumplir este requisito, se agrega la lógica siguiente:

- Si el campo **Fecha de factura** está en blanco en la entidad **Factura** (es decir, si no tiene ningún valor), se establece en la fecha actual en que se agrega una línea de factura que se origina desde un acuerdo.
- El usuario puede modificar el campo **Fecha de factura**. Sin embargo, cuando el usuario intenta guardar una factura que se origina desde un acuerdo, recibe un error de proceso de negocio si el campo **Fecha de factura** está en blanco en la factura.

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación

### <a name="in-finance-and-operations"></a>En Finance and Operations

Un origen de factura se debe configurar para la integración, para distinguir las facturas de servicios en Finance and Operations que se crean de facturas de acuerdos en Field Service. Cuando una factura tiene un origen de factura del tipo **Integración de factura de acuerdo**, el campo **Número de factura externo** se muestra en el encabezado **Factura de ventas**.

Además de aparecer en el encabezado de factura, la información **Número de factura externo** se pueden usar para ayudar a garantizar que las facturas que se crean desde facturas de acuerdo de Field Service se filtran durante la sincronización de Finance and Operations con Field Service.

1. Vaya a **Clientes** \> **Configuración** \> **Códigos de origen de factura**.
2. Seleccione **Nuevo** para crear un nuevo origen de factura.
3. En el campo **Origen de factura**, especifique un nombre para el origen de la factura, como **FS**.
4. En el campo **Descripción**, especifique una descripción, como **Factura de acuerdo de Field Service**.
5. Seleccione la casilla de verificación **Asignación de tipo de origen**.
6. Establezca el campo **Tipo de origen de la factura** a **Integración de la factura de acuerdo**.
7. Seleccione **Guardar**.

### <a name="in-the-data-integration-project"></a>En el proyecto de integración de datos

Tarea: **Líneas de factura**  

Asegúrese de que el valor predeterminado del campo Finance and Operations **Mostrar valor de la cuenta principal** se haya actualizado para que coincida con el valor deseado.

El valor de plantilla predeterminado es **401100**.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-headers"></a>Facturas de acuerdos (Field Service a Fin and Ops): Encabezados de factura

[![Asignación de la plantilla en la integración de datos](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-lines"></a>Facturas de acuerdos (Field Service a Fin and Ops): Líneas de factura

[![Asignación de la plantilla en la integración de datos](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)

