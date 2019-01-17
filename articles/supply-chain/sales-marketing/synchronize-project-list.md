---
title: Sincronizar lista de proyectos de Finance and Operations a Field Service
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar proyectos de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: adcb1c1b241ce2b073cd26cf2a8a8d64931c8b0f
ms.contentlocale: es-es
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a>Sincronizar lista de proyectos de Finance and Operations a Field Service

[!include[banner](../includes/banner.md)]

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar proyectos de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Plantillas y tareas
La plantilla y las tareas subyacentes siguientes se usan para ejecutar la sincronización de proyectos desde Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

**Nombre de la plantilla en la integración de datos:**
- Proyectos (desde Finance and Operations a Field Service)

**Nombres de las tareas en el proyecto de integración de datos:**
- Proyectos

Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de la lista de proyectos:
- Cuentas (de Sales a Finance and Operations) 

## <a name="entity-set"></a>Conjunto de entidades
Field Service   Finance and Operations

| Field Service           | Finance and Operations  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Proyectos                |

## <a name="entity-flow"></a>Flujo de la entidad
Los proyectos se crean en Finance and Operations. Los proyectos con el tiempo y el material **Tipo de proyecto** y la **Etapa de proyecto** en proceso se sincronizarán con la entidad **Proyecto externo** en Field Service, incluida la información de número de proyecto, el nombre de proyecto, la fase de proyecto y la cuenta de cliente. La lista **Proyecto externo** se utiliza para emparejar pedidos de trabajo de Field Service con proyectos de Finance and Operations.
Solución de CRM de Field Service El proyecto externo es una nueva entidad que recoge todos los proyectos de Operations.
El campo Proyecto externo se ha agregado a la entidad del pedido de trabajo. Este campo etiqueta la búsqueda y la compra de su orden de trabajo con un proyecto. Después el pedido de ventas se conectará con un proyecto en Operations. Una vez que el estado del sistema cambia Abierto - En progreso (690,970,000) a un estado más alto, el campo Proyecto externo se bloquea y no puede agregar, quitar o cambiar el valor.

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación
### <a name="in-finance-and-operations"></a>En Finance and Operations
Habilitar el seguimiento de cambios de proyectos de entidad de datos

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos


### <a name="projects-finance-and-operations-to-field-service-projects"></a>Proyectos (desde Finance and Operations a Field Service): proyectos

[![Asignación de la plantilla en la integración de datos](./media/FSProject1.png)](./media/FSProject1.png)

