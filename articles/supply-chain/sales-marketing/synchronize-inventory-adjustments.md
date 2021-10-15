---
title: Sincronizar transferencias y ajustes de inventario de Field Service a Supply Chain Management
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar transferencias y ajustes de inventario de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
author: Henrikan
ms.date: 04/30/2019
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
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 83ab46904815b177640c87fef58ce208d00d800a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566392"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a>Sincronizar transferencias y ajustes de inventario de Field Service a Supply Chain Management

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar transferencias y ajustes de inventario de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.

[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service.](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas
La plantilla siguiente y las tareas subyacentes se usan para sincronizar ajustes y transferencias de inventario de Field Service a Supply Chain Management.

**Plantillas en la integración de datos**
- Ajuste de inventario (Field service a Supply Chain Management)
- Transferencias de inventario (Field service a Supply Chain Management)

**Tareas en los proyectos de integración de datos**
- Ajustes de inventario
- Transferencias de inventario

## <a name="table-set"></a>Conjunto de tablas
| Field Service                     | Gestión de la cadena de abastecimiento                          |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts | Encabezados y líneas de diario de ajustes de inventario de Dataverse |
| msdyn_inventoryadjustmentproducts | Encabezados y líneas de diario de transferencia de inventario de Dataverse   |

## <a name="table-flow"></a>Flujo de tabla
Los ajustes y las transferencias de inventario realizados en Field Service se sincronizarán con Supply Chain Management después de que se cambie **Estado de Registrar** de **creado** a **registrado**. Si esto ocurre, el ajuste o el pedido de transferencia será bloqueado y se convertirá en de solo lectura. Esto significa que los ajustes y las transferencias se pueden registrar en Supply Chain Management, pero no se pueden modificar. En Supply Chain Management puede configurar un trabajo por lotes para registrar automáticamente los diarios de inventario de ajustes y transferencias que se han generado durante la integración. Consulte los siguientes requisitos previos para obtener información sobre cómo habilitar el trabajo por lotes.

## <a name="field-service-crm-solution"></a>Solución CRM de Field Service 
La columna **Unidad de inventario** se ha agregado a la tabla **Producto**. Esta columna es necesario ya que la unidad de inventario y ventas no siempre es la misma en Supply Chain Management y la Unidad de inventario es necesaria en el inventario de almacén en Supply Chain Management.
Cuando establece el producto en un producto de ajuste de inventario para los ajustes y las transferencias de inventario, la unidad se obtendrá del valor de producto de inventario. Si se encuentra un valor, la columna **Unidad** se bloqueará en el producto de ajuste de inventario.

La columna de **Publicar estado** se ha agregado a la tabla de **ajuste de inventario** y a la tabla **transferencia de inventario**. Esta columna se usa como filtro cuando un ajuste o una transferencia se envía a Supply Chain Management. El valor predeterminado para esta columna es Creado (1), aunque no se envía a Supply Chain Management. Cuando actualiza el valor en Registrado (2), este se envía a Supply Chain Management, pero después ya no podrá cambiar el ajuste o la transferencia ni agregar líneas nuevas.

La columna **secuencia numérica** se ha agregado a la tabla **producto de ajuste de inventario**. Esta columna garantiza que la integración tiene un número único, por lo que la integración puede crear y actualizar el ajuste. Al crear su primer producto de ajuste de inventario creará un nuevo registro en la tabla **P2C AutoNumber** para mantener la serie numérica y el prefijo que se usa.

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación

### <a name="supply-chain-management"></a>Gestión de la cadena de abastecimiento
Los diarios de inventario de integración generados mediante la integración se pueden registrar automáticamente mediante un trabajo por lotes. Esto se habilita desde **Gestión del inventario > Tareas periódicas > integración de Dataverse > Registrar diarios de inventario de integración**.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a>Ajuste de inventario (Field Service a Supply Chain Management): Ajuste de inventario

[![Asignación de plantillas en Integración de datos, Ajuste de inventario (Field Service a Supply Chain Management): Ajuste de inventario.](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a>Transferencia de inventario (Field Service a Supply Chain Management): Transferencia de inventario

[![Asignación de plantillas en Integración de datos, Transferencia de inventario (Field Service a Supply Chain Management): Transferencia de inventario.](./media/FSTrans1.png)](./media/FSTrans1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]