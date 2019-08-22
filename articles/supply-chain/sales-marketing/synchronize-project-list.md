---
title: Sincronizar lista de proyectos de Finance and Operations a Field Service
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar proyectos de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 535094821ca7efa33bf40f2057fac8ffc17bb822
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843562"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a>Sincronizar lista de proyectos de Finance and Operations a Field Service

[!include[banner](../includes/banner.md)]

En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar proyectos de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas
Se utilizan la plantilla y las tareas subyacentes siguientes para ejecutar la sincronización de proyectos de Microsoft Dynamics 365 for Finance and Operations en Microsoft Dynamics 365 for Field Service.

**Plantilla en la integración de datos**
- Proyectos (Fin and Ops a Field Service)

**Tarea en el proyecto de integración de datos**
- Proyectos

Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de la lista de proyectos:
- Cuentas (Sales a Fin and Ops) 

## <a name="entity-set"></a>Conjunto de entidades
| Field Service           | Finance and Operations  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Proyectos                |

## <a name="entity-flow"></a>Flujo de la entidad
Los proyectos se crean en Finance and Operations. Los proyectos con **Tipo de proyecto** establecido en **tiempo y el material** y **Etapa de proyecto** establecido en **En proceso** se sincronizarán con la entidad **Proyecto externo** en Field Service, incluida la información de número de proyecto, el nombre de proyecto, la fase de proyecto y la cuenta de cliente. La lista **Proyecto externo** se utiliza para emparejar pedidos de trabajo de Field Service con proyectos de Finance and Operations.

## <a name="field-service-crm-solution"></a>Solución CRM de Field Service
La entidad **Proyecto externo** recoge todos los proyectos de Finance and Operations. El campo **Proyecto externo** se ha agregado a la entidad **pedido de trabajo**. Este es un campo de búsqueda, por lo que etiquetado su orden de trabajo con un proyecto, el pedido de ventas se conectará con un proyecto en Finance and Operations. Una vez que el **estado del sistema** cambie **Abierto - En progreso (690 970 000)** a un estado más alto, el campo **Proyecto externo** se bloqueará y ya no podrá agregar, quitar o cambiar el valor.

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación
### <a name="finance-and-operations"></a>Finance and Operations
Habilitar el seguimiento de cambios de proyectos de entidad de datos.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos


### <a name="projects-fin-and-ops-to-field-service-projects"></a>Proyectos (Fin and Ops a Field Service): proyectos

[![Asignación de la plantilla en la integración de datos](./media/FSProject1.png)](./media/FSProject1.png)
