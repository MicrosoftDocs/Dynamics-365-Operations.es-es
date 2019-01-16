---
title: Sincronizar las transferencias y los ajustes de inventario desde Field Service a Finance and Operations
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar los ajustes y transferencias de inventario desde Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: 79a1cfac3fa94223cc9af73e758ce95fd47065c9
ms.contentlocale: es-es
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a>Sincronizar los ajustes de inventario desde Field Service a Finance and Operations

[!include[banner](../includes/banner.md)]

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar los ajustes y transferencias de inventario desde Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas
La plantilla y las tareas subyacentes siguientes se usan para ejecutar la sincronización de los ajustes y transferencias de inventario desde Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.

**Nombre de las plantillas en la integración de datos:**
- Ajuste de inventario (desde Field Service a Finance and Operations)
- Transferencias de inventario (desde Field Service a Finance and Operations)

**Nombres de las tareas en los proyectos de integración de datos:**
- Ajustes de inventario
- Transferencias de inventario

## <a name="entity-set"></a>Conjunto de entidades
| Field Service                     | Finance and Operations                             |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   Encabezados y líneas de diario de ajustes de inventario de CDS |
| msdyn_inventoryadjustmentproducts | Encabezados y líneas de diario de transferencia de inventario de CDS   |

## <a name="entity-flow"></a>Flujo de la entidad
Los ajustes y las transferencias de inventario realizados en Field Service se sincronizarán con Finance and Operations una vez que se cambia **Estado de Registrar** de creado a registrado. Cuando esto sucede el pedido de ajuste o transferencia se bloquea y se convierte en de solo lectura, ya que los ajustes y transferencias pueden ser enviados a Finance and Operations y por tanto no se pueden modificar.
En Finance and Operations puede configurar un trabajo por lotes para registrar automáticamente los diarios de inventario de ajustes y transferencias generados con la integración. Consulte el requisito previo siguiente para obtener información sobre cómo habilitar el trabajo por lotes.

## <a name="field-service-crm-solution"></a>Solución CRM de Field Service 
El campo de la unidad de inventario se ha agregado a la entidad del producto. Este campo es necesario ya que la unidad de inventario y ventas no siempre es la misma en Operations y para el inventario de almacén en Operations necesitamos la unidad de inventario.
Cuando establece el producto en un producto de ajuste de inventario para los ajustes y las transferencias de inventario, la unidad se obtendrá del valor producto de inventario de los productos. Si se encuentra un valor el campo Unidad se bloquea en el producto de ajuste de inventario

El campo de registro de estado se ha agregado a la entidad de ajuste de inventario y a la entidad de transferencia de inventario. Este campo se usa como filtro para cuando un ajuste o una transferencia se envía a Operations. El valor predeterminado pasa a Creado (1) y no se envía a Operations. Una vez que lo cambia a Registrado (2) se envía a Operaciones, pero ya no podrá cambiar nada en el ajuste o la transferencia ni agregar cualquier nueva línea.
El campo de secuencia numérica se ha agregado a la entidad del producto de ajuste de inventario. Este campo ayuda a que la integración tenga un número único, para que la integración sepa cuándo crear y cuándo hacer actualizaciones. Al crear su primer producto de ajuste de inventario creará un nuevo registro en la entidad P2C AutoNumber para mantener la serie numérica y el prefijo que se usa.

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación

### <a name="in-finance-and-operations"></a>En Finance and Operations
Los diarios de inventario de integración generados mediante la integración se pueden registrar automáticamente con un trabajo por lotes. Esto se habilita desde: Gestión del inventario > Tareas periódicas > integración de CDS > Registrar diarios de inventario de integración

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a>Ajuste de inventario (desde Field Service a Finance and Operations): ajuste de inventario

[![Asignación de la plantilla en la integración de datos](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a>Transferencia de inventario (desde Field Service a Finance and Operations): transferencia de inventario

[![Asignación de la plantilla en la integración de datos](./media/FSTrans1.png)](./media/FSTrans1.png)

