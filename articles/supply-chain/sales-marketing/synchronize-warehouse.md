---
title: Sincronizar almacenes de Finance and Operations a Field Service
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar almacenes de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 10/10/2018
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
ms.openlocfilehash: eb8ba6051777e27bd44504a8160118e8096b1435
ms.contentlocale: es-es
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a>Sincronizar almacenes de Finance and Operations a Field Service

[!include[banner](../includes/banner.md)]

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar almacenes de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas
La plantilla y las tareas subyacentes siguientes se usan para ejecutar la sincronización de almacenes desde Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

**Nombre de la plantilla en la integración de datos:**
- Almacenes (desde Finance and Operations a Field Service)

**Nombres de las tareas en el proyecto de integración de datos:**
- Almacén

## <a name="entity-set"></a>Conjunto de entidades
| Field Service    | Finance and Operations                 |
|------------------|----------------------------------------|
| msdyn_warehouses | Almacenes                             |

## <a name="entity-flow"></a>Flujo de la entidad
Los almacenes creados y mantenidos en Finance and Operations se pueden sincronizar con Field Service mediante un proyecto de integración de datos del Common Data Service (CDS). Los almacenes deseados que se sincronizan con Field Service se pueden controlar con la consulta y un filtrado avanzado en el proyecto. Los almacenes que se sincronizan desde Finance and Operations se crean en Field Service con el campo Se mantienen externamente establecido en Sí y el registro se convierte en sólo lectura.
Solución CRM Field Service Para admitir la integración entre Field Service y Finance and Operations, la funcionalidad adicional de la solución de CRM Field Service es necesaria. La solución incluye los siguientes cambios.
El campo **Se mantiene externamente** se ha agregado a la entidad **Almacén (msdyn_warehouses)** . Este campo ayuda a identificar si el almacén se administra desde Operations o si sólo existe en Field Service.
- Sí - El almacén se ha originado en Finance and Operations y no se podrá editar en Sales.
- No – el almacén se especificó directamente en Field Service y se mantiene aquí.

El campo **Se mantiene externamente** ayuda a controlar la sincronización de los niveles de inventario, los ajustes, las transferencias y uso en pedidos de trabajo. Solo los almacenes con **Se mantiene externamente** = Sí se pueden usar para sincronizarse directamente con el mismo almacén en el otro sistema. 

Nota: Es posible crear varios almacenes en Field Services (con **Mantenido externamente** = No) y después asignarlos a un único almacén en Finance and Operations, con la funcionalidad de consulta y filtrado avanzados. Se usa en situaciones en las que desea que Field Service domine el nivel de inventario detallado y sólo envíe actualizaciones a Finance and Operations. En este caso Field Service no recibirá actualizaciones del nivel de inventario desde Finance and Operations. Vea información adicional en Sincronizar los ajustes de inventario desde Field Service a Finance and Operations y Sincronizar pedidos de trabajo en Field Service con pedidos de ventas vinculados a proyecto en Finance and Operations.

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación
### <a name="in-the-data-integration-project"></a>En el proyecto de integración de datos
Antes de sincronizar los almacenes asegúrese de actualizar la consulta y el filtrado avanzados en el proyecto para incluir solo los almacenes que desea llevar de Finance and Operations a Field Service. Tenga en cuenta que necesitará el almacén de Field Service para aplicarlo en pedidos de trabajo, ajustes y transferencias.  

Asegúrese de que haya una **clave de integración** para **msdyn_warehouses**
1. Ir a integración de datos
2. Seleccione la ficha **Conjunto de conexión**
3. Seleccione el conjunto de conexión utilizado para la sincronización de pedidos de trabajo
4. Seleccione la ficha **Tecla de integración**
5. Busque msdyn_warehouses y compruebe que se haya agregado la clave **msdyn_name (nombre)**. Si no se muestra, agréguela haciendo clic en **Agregar clave** y en **Guardar** en la parte superior de la página

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.

### <a name="warehouses-finance-and-operations-to-field-service-warehouse"></a>Almacenes (desde Finance and Operations a Field Service): almacén

[![Asignación de la plantilla en la integración de datos](./media/Warehouse1.png)](./media/Warehouse1.png)

