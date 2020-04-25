---
title: Sincronizar transferencias y ajustes de inventario de Field Service a Supply Chain Management
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar transferencias y ajustes de inventario de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: ff64f28af570b792f73b51aa9caf06dd2445b2ca
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204433"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a>Sincronizar transferencias y ajustes de inventario de Field Service a Supply Chain Management

[!include[banner](../includes/banner.md)]

En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar transferencias y ajustes de inventario de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.

[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas
La plantilla siguiente y las tareas subyacentes se usan para sincronizar ajustes y transferencias de inventario de Field Service a Supply Chain Management.

**Plantillas en la integración de datos**
- Ajuste de inventario (Field service a Supply Chain Management)
- Transferencias de inventario (Field service a Supply Chain Management)

**Tareas en los proyectos de integración de datos**
- Ajustes de inventario
- Transferencias de inventario

## <a name="entity-set"></a>Conjunto de entidades
| Field Service                     | Gestión de la cadena de abastecimiento                          |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   Encabezados y líneas de diario de ajustes de inventario de CDS |
| msdyn_inventoryadjustmentproducts | Encabezados y líneas de diario de transferencia de inventario de CDS   |

## <a name="entity-flow"></a>Flujo de la entidad
Los ajustes y las transferencias de inventario realizados en Field Service se sincronizarán con Supply Chain Management después de que se cambie **Estado de Registrar** de **creado** a **registrado**. Si esto ocurre, el ajuste o el pedido de transferencia será bloqueado y se convertirá en de solo lectura. Esto significa que los ajustes y las transferencias se pueden registrar en Supply Chain Management, pero no se pueden modificar. En Supply Chain Management puede configurar un trabajo por lotes para registrar automáticamente los diarios de inventario de ajustes y transferencias que se han generado durante la integración. Consulte los siguientes requisitos previos para obtener información sobre cómo habilitar el trabajo por lotes.

## <a name="field-service-crm-solution"></a>Solución CRM de Field Service 
El campo **unidad de inventario** se ha agregado a la entidad **Producto**. Este campo es necesario ya que la unidad de inventario y ventas no siempre es la misma en Supply Chain Management y la unidad de inventario es necesaria en el inventario de almacén en Supply Chain Management.
Cuando establece el producto en un producto de ajuste de inventario para los ajustes y las transferencias de inventario, la unidad se obtendrá del valor de producto de inventario. Si se encuentra un valor el campo **Unidad** se bloquea en el producto de ajuste de inventario.

El campo de **registro de estado** se ha agregado a la entidad de **ajuste de inventario** y a la entidad de **transferencia de inventario**. Este campo se usa como filtro cuando un ajuste o una transferencia se envía a Supply Chain Management. El valor predeterminado para este campo es Creado (1), aunque no se envía a Supply Chain Management. Cuando actualiza el valor en Registrado (2), este se envía a Supply Chain Management, pero después ya no podrá cambiar el ajuste o la transferencia ni agregar líneas nuevas.

El campo de **secuencia numérica** se ha agregado a la entidad del **producto de ajuste de inventario**. Este campo garantiza que la integración tiene un número único, por lo que la integración puede crear y actualizar el ajuste. Al crear su primer producto de ajuste de inventario creará un nuevo registro en la entidad **P2C AutoNumber** para mantener la serie numérica y el prefijo que se usa.

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación

### <a name="supply-chain-management"></a>Gestión de la cadena de abastecimiento
Los diarios de inventario de integración generados mediante la integración se pueden registrar automáticamente mediante un trabajo por lotes. Esto se habilita desde: **Gestión del inventario > Tareas periódicas > integración de CDS > Registrar diarios de inventario de integración**.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a>Ajuste de inventario (Field Service a Supply Chain Management): Ajuste de inventario

[![Asignación de la plantilla en la integración de datos](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a>Transferencia de inventario (Field Service a Supply Chain Management): Transferencia de inventario

[![Asignación de la plantilla en la integración de datos](./media/FSTrans1.png)](./media/FSTrans1.png)
