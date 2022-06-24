---
title: Sincronizar lista de proyecto de Supply Chain Management a Field Service
description: En este artículo se describen las plantillas y las tareas subyacentes que se usan para sincronizar proyectos de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
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
ms.openlocfilehash: 71c0580953f01c2d29e99fa2928a0b4a3937d5c5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899364"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a>Sincronizar lista de proyecto de Supply Chain Management a Field Service

[!include[banner](../includes/banner.md)]

En este artículo se describen las plantillas y las tareas subyacentes que se usan para sincronizar proyectos de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.

[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service.](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas
La plantilla siguiente y las tareas subyacentes se usan para ejecutar sincronización de proyectos de Supply Chain Management a Field Service.

**Plantilla en la integración de datos**
- Proyectos (Supply Chain Management a Field Service)

**Tarea en el proyecto de integración de datos**
- Proyectos

Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de la lista de proyectos:
- Cuentas (Sales a Supply Chain Management) 

## <a name="entity-set"></a>Conjunto de entidades
| Field Service           | Gestión de la cadena de abastecimiento  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Proyectos                |

## <a name="entity-flow"></a>Flujo de la entidad
Los proyectos se crean en Supply Chain Management. Los proyectos con **Tipo de proyecto** establecido en **tiempo y el material** y **Etapa de proyecto** establecido en **En proceso** se sincronizarán con la entidad **Proyecto externo** en Field Service, incluida la información de número de proyecto, el nombre de proyecto, la fase de proyecto y la cuenta de cliente. La lista **Proyecto externo** se utiliza para emparejar pedidos de trabajo de Field Service con proyectos de Supply Chain Management.

## <a name="field-service-crm-solution"></a>Solución CRM de Field Service
La entidad **Proyecto externo** recoge todos los proyectos de Supply Chain Management. El campo **Proyecto externo** se ha agregado a la entidad **pedido de trabajo**. Este es un campo etiqueta, así que al etiquetar su orden de trabajo con un proyecto, el pedido de ventas se conectará a un proyecto en Supply Chain Management. Una vez que el **estado del sistema** cambie **Abierto - En progreso (690 970 000)** a un estado más alto, el campo **Proyecto externo** se bloqueará y ya no podrá agregar, quitar o cambiar el valor.

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación
### <a name="supply-chain-management"></a>Gestión de la cadena de abastecimiento
Habilitar el seguimiento de cambios de proyectos de entidad de datos.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos


### <a name="projects-supply-chain-management-to-field-service-projects"></a>Proyectos (Supply Chain Management a Field Service): Proyectos

[![Asignación de la plantilla en la integración de datos.](./media/FSProject1.png)](./media/FSProject1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]