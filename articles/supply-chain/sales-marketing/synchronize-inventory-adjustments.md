---
title: Sincronizar las transferencias y los ajustes de inventario desde Field Service a Finance and Operations
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar transferencias y ajustes de inventario de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 01/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: aa54945cea5821da163e1f6ea1747ac29b31a3ce
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "308377"
---
# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a>Sincronizar los ajustes de inventario desde Field Service a Finance and Operations

[!include[banner](../includes/banner.md)]

En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar transferencias y ajustes de inventario de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas
La plantilla siguiente y las tareas subyacentes se usan para sincronizar transferencias y ajustes de inventario de Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.

**Plantillas en la integración de datos**
- Ajuste de inventario (desde Field Service a Finance and Operations)
- Transferencias de inventario (desde Field Service a Finance and Operations)

**Tareas en los proyectos de integración de datos**
- Ajustes de inventario
- Transferencias de inventario

## <a name="entity-set"></a>Conjunto de entidades
| Field Service                     | Finance and Operations                             |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   Encabezados y líneas de diario de ajustes de inventario de CDS |
| msdyn_inventoryadjustmentproducts | Encabezados y líneas de diario de transferencia de inventario de CDS   |

## <a name="entity-flow"></a>Flujo de la entidad
Los ajustes y las transferencias de inventario realizados en Field Service se sincronizarán con Finance and Operations después de que se cambie **Estado de Registrar** de **creado** a **registrado**. Si esto ocurre, el ajuste o el pedido de transferencia será bloqueado y se convertirá en de solo lectura. Esto significa que los ajustes y las transferencias se pueden registrar en Finance and Operations, pero no se pueden modificar. En Finance and Operations puede configurar un trabajo por lotes para registrar automáticamente los diarios de inventario de ajustes y transferencias que se han generado durante la integración. Consulte los siguientes requisitos previos para obtener información sobre cómo habilitar el trabajo por lotes.

## <a name="field-service-crm-solution"></a>Solución CRM de Field Service 
El campo **unidad de inventario** se ha agregado a la entidad **Producto**. Este campo es necesario ya que la unidad de inventario y ventas no siempre es la misma en Finance and Operations y la unidad de inventario es necesaria en el inventario de almacén en Finance and Operations.
Cuando establece el producto en un producto de ajuste de inventario para los ajustes y las transferencias de inventario, la unidad se obtendrá del valor de producto de inventario. Si se encuentra un valor el campo **Unidad** se bloquea en el producto de ajuste de inventario.

El campo de **registro de estado** se ha agregado a la entidad de **ajuste de inventario** y a la entidad de **transferencia de inventario**. Este campo se usa como filtro cuando un ajuste o una transferencia se envía a Finance and Operations. El valor predeterminado para este campo es Creado (1), aunque no se envía a Finance and Operations. Cuando actualiza el valor en Registrado (2), este se envía a Finance and Operations, pero después ya no podrá cambiar el ajuste o la transferencia ni agregar líneas nuevas.

El campo de **secuencia numérica** se ha agregado a la entidad del **producto de ajuste de inventario**. Este campo garantiza que la integración tiene un número único, por lo que la integración puede crear y actualizar el ajuste. Al crear su primer producto de ajuste de inventario creará un nuevo registro en la entidad **P2C AutoNumber** para mantener la serie numérica y el prefijo que se usa.

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación

### <a name="finance-and-operations"></a>Finance and Operations
Los diarios de inventario de integración generados mediante la integración se pueden registrar automáticamente mediante un trabajo por lotes. Esto se habilita desde: **Gestión del inventario > Tareas periódicas > integración de CDS > Registrar diarios de inventario de integración**.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a>Ajuste de inventario (desde Field Service a Finance and Operations): ajuste de inventario

[![Asignación de la plantilla en la integración de datos](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a>Transferencia de inventario (desde Field Service a Finance and Operations): transferencia de inventario

[![Asignación de la plantilla en la integración de datos](./media/FSTrans1.png)](./media/FSTrans1.png)
