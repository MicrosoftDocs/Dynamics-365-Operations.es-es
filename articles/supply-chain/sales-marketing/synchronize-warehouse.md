---
title: Sincronizar almacenes de Supply Chain Management a Field Service
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar almacenes de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
author: Henrikan
ms.date: 03/13/2019
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
ms.openlocfilehash: f38d2dfdba1f2afa1005bd740cba27afe9dcb0ec
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062145"
---
# <a name="synchronize-warehouses-from-supply-chain-management-to-field-service"></a>Sincronizar almacenes de Supply Chain Management a Field Service

[!include[banner](../includes/banner.md)]



En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar almacenes de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.

[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service.](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas
La plantilla siguiente y las tareas subyacentes se usan para ejecutar sincronización de almacenes de Supply Chain Management a Field Service.

**Plantilla en la integración de datos**
- Almacenes (Supply Chain Management a Field Service)

**Tarea en el proyecto de integración de datos**
- Almacén

## <a name="table-set"></a>Conjunto de tablas
| Field Service    | Gestión de la cadena de abastecimiento                 |
|------------------|----------------------------------------|
| msdyn_warehouses | Almacenes                             |

## <a name="table-flow"></a>Flujo de tabla
Los almacenes creados y mantenidos en Supply Chain Management se pueden sincronizar con Field Service mediante un proyecto de integración de datos de Microsoft Dataverse. Los almacenes que quiere sincronizar con Field Service se pueden controlar con la consulta y un filtrado avanzado en el proyecto. Los almacenes que se sincronizan desde Supply Chain Management se crean en Field Service con la columna **Se mantienen externamente** establecida en **Sí** y el registro se convierte en solo lectura.

## <a name="field-service-crm-solution"></a>Solución CRM de Field Service
Para admitir la integración entre Field Service y Supply Chain Management, la funcionalidad adicional de la solución de CRM Field Service es necesaria. En la solución, la columna **Se mantiene externamente** se ha agregado a la tabla **Almacén (msdyn_warehouses)**. Esta columna ayuda a identificar si el almacén se administra desde Supply Chain Management o si solo existe en Field Service. Los parámetros de esta columna son:
- **Sí** - El almacén se ha originado en Supply Chain Management y no se podrá editar en Sales.
- **No** – el almacén se especificó directamente en Field Service y se mantiene aquí.

La columna **Se mantiene externamente** ayuda a controlar la sincronización de los niveles de inventario, los ajustes, las transferencias y uso en pedidos de trabajo. Solo los almacenes con **Se mantiene externamente** establecido en **Sí** se pueden usar para sincronizarse directamente con el mismo almacén en el otro sistema. 

> [!NOTE]
> Es posible crear varios almacenes en Field Service (con **Se mantiene externamente** = No) y después asignarlos a un único almacén, con la funcionalidad de consulta y filtrado avanzados. Se usa en situaciones en las que desea que Field Service domine el nivel de inventario detallado y solo envíe actualizaciones a Supply Chain Management. En este caso Field Service no recibirá actualizaciones del nivel de inventario desde Supply Chain Management. Para consultar información adicional, vea [Sincronizar los ajustes de inventario desde Field Service a Finance and Operations](/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) y [Sincronizar pedidos de trabajo en Field Service con pedidos de ventas vinculados a proyecto en Finance and Operations](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación
### <a name="data-integration-project"></a>Proyecto de integración de datos
Antes de sincronizar los almacenes asegúrese de actualizar la consulta y el filtrado avanzados en el proyecto para incluir solo los almacenes que desea llevar de Supply Chain Management a Field Service. Tenga en cuenta que necesitará el almacén de Field Service para aplicarlo en pedidos de trabajo, ajustes y transferencias.  

Para asegurarse de que haya una **clave de integración** para **msdyn_warehouses**:
1. Vaya a integración de datos.
2. Seleccione la ficha **Conjunto de conexión**.
3. Seleccione el conjunto de conexión utilizado para la sincronización de pedidos de trabajo.
4. Seleccione la ficha **Tecla de integración**.
5. Busque msdyn_warehouses y confirme que se haya agregado la clave **msdyn_name (nombre)**. Si no se muestra, agréguela haciendo clic en **Agregar clave** y luego en **Guardar** en la parte superior de la página.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

La siguiente ilustración muestra la asignación de plantilla en la integración de datos.

### <a name="warehouses-supply-chain-management-to-field-service-warehouse"></a>Almacenes (Supply Chain Management a Field Service): Almacén

[![Asignación de la plantilla en la integración de datos.](./media/Warehouse1.png)](./media/Warehouse1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]