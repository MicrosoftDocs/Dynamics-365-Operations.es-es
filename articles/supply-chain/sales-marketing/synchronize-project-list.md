---
title: Sincronizar lista de proyectos de Finance and Operations a Field Service
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar proyectos de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: b5aeb4c3925994d7488e8e113e88b9d06ee6b350
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "312517"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a>Sincronizar lista de proyectos de Finance and Operations a Field Service

[!include[banner](../includes/banner.md)]

En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar proyectos de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas
Se utilizan la plantilla y las tareas subyacentes siguientes para ejecutar la sincronización de proyectos de Microsoft Dynamics 365 for Finance and Operations en Microsoft Dynamics 365 for Field Service.

**Plantilla en la integración de datos**
- Proyectos (desde Finance and Operations a Field Service)

**Tarea en el proyecto de integración de datos**
- Proyectos

Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de la lista de proyectos:
- Cuentas (de Sales a Finance and Operations) 

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


### <a name="projects-finance-and-operations-to-field-service-projects"></a>Proyectos (desde Finance and Operations a Field Service): proyectos

[![Asignación de la plantilla en la integración de datos](./media/FSProject1.png)](./media/FSProject1.png)
