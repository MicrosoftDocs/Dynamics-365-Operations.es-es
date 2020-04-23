---
title: Sincronizar información de nivel de inventario de Supply Chain Management a Field Service
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar información de nivel de inventario de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2019
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
ms.openlocfilehash: 1228339c12d26f7b91875d15f0daa8da2869cba0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215916"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a>Sincronizar información de nivel de inventario de Supply Chain Management a Field Service 

[!include[banner](../includes/banner.md)]

En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar información de nivel de inventario de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.

[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas
La plantilla siguiente y las tareas subyacentes se usan para sincronizar niveles disponibles de inventario de Supply Chain Management a Field Service.

**Plantilla en la integración de datos**
- Inventario de producto (Supply Chain Management a Field Service)
  
**Tarea en el proyecto de integración de datos**
- Inventario de producto

Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los niveles de inventario:
- Almacenes (Supply Chain Management a Field Service) 
- Productos Field Service con unidad de inventario (Supply Chain Management a Sales) 

## <a name="entity-set"></a>Conjunto de entidades

| Field Service                      | Gestión de la cadena de abastecimiento                |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | Inventario de CDS disponible por almacén     |

## <a name="entity-flow"></a>Flujo de la entidad
La información de nivel de inventario de Finance and Operations se envía a Field Service para productos seleccionados. La información del nivel de inventario incluye: 
- Cantidad disponible (cantidad física registrada actual ubicada en el almacén)
- Cantidad en pedido (cantidad pedida registrada total, como por ejemplo, pedidos de ventas)
- Cantidad pedida (cantidad pedida registrada total como por ejemplo, pedidos de compras)

Esta información se captura por producto emitido para cada almacén y se sincroniza basándose en seguimiento de cambios, cuando cambia el nivel de inventario.

En Field Service la solución de integración crea diarios de inventario para el delta, para conseguir que los niveles de Field Service coincidan con los niveles en Supply Chain Management.

Supply Chain Management actuará como el maestro de los niveles de inventario. Por lo tanto es importante configurar la integración de pedidos de trabajo, las transferencias y los ajustes desde Field Service a Supply Chain Management si esta funcionalidad se utiliza en Field Service, junto con la sincronización de los niveles de inventario desde Supply Chain Management.

Los productos y los almacenes dónde se han realizado los niveles de inventario se gestionan desde Supply Chain Management y se pueden controlar con la consulta y el filtrado avanzados (Power Query).

> [!NOTE]
> Es posible crear varios almacenes en Field Services (con **Se mantiene externamente = No**) y después asignarlos a un único almacén en Supply Chain Management, con la funcionalidad de consulta y filtrado avanzados. Se usa en situaciones en las que desea que Field Service domine el nivel de inventario detallado y solo envíe actualizaciones a Supply Chain Management. En este caso Field Service no recibirá actualizaciones del nivel de inventario desde Supply Chain Management. Para consultar información adicional, vea [Sincronizar los ajustes de inventario desde Field Service a Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) y [Sincronizar pedidos de trabajo en Field Service con pedidos de ventas vinculados a proyecto en Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="field-service-crm-solution"></a>Solución CRM de Field Service
La entidad del **inventario de productos externos** solo se usa para back end en la integración. Esta entidad recibe los valores del nivel de inventario de Supply Chain Management en la integración y después transforma estos valores en diarios de inventario manual, que luego cambia los productos de inventario en el almacén.

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación

### <a name="data-integration"></a>Integración de datos
Para que funcione el proyecto, debe asegurarse de que la clave de Integración esté actualizada para msdynce_externalproductinventories.
1.  Vaya a **Integración de datos > Conjuntos de conexión**.
2.  Seleccione el Conjunto de conexión utilizado.
3.  En la pestaña **Clave de integración**, asegúrese de que las claves siguientes se agreguen a msdynce_externalproductinventories:
      - msdynce_productnumber (número de producto)
      - msdynce_warehouseid (identificador de almacén)
      
### <a name="data-integration-project"></a>Proyecto de integración de datos
Puede aplicar filtros con la consulta y un filtrado avanzados para que sólo determinados productos y almacenes envíen información del nivel de inventario desde Supply Chain Management hasta Field Service.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a>Inventario de producto (Supply Chain Management a Field Service): Inventario de producto

[![Asignación de la plantilla en la integración de datos](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)
