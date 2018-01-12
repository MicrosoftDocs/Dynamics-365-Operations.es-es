---
title: "Página principal de planificación maestra"
description: "La planificación maestra permite a las empresas determinar y establecer la necesidad futura de materias primas y la capacidad para cumplir los objetivos de la empresa."
author: YuyuScheller
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: roxanadiaconu
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a24f75bf7e27702505d8a61ae3db83d03fe4a933
ms.openlocfilehash: a2e91cd2b72ffed78669fe3cc83b141db6f26aa2
ms.contentlocale: es-es
ms.lasthandoff: 11/29/2017

---

# <a name="master-planning-home-page"></a>Página principal de planificación maestra

[!include[banner](../includes/banner.md)]


Básicamente, la planificación maestra permite a las empresas determinar y establecer la necesidad futura de materias primas y la capacidad para cumplir los objetivos de la empresa. La planificación maestra evalúa lo siguiente: 

-  ¿Qué materias primas y capacidades hay disponibles actualmente? 
-  ¿Qué materias primas y capacidades se requieren para completar la producción? Por ejemplo, qué debe ser manufacturado, comprado, transferido, o apartado como existencias de seguridad antes de poder completar la producción.

La planificación maestra utiliza la información para calcular los requisitos y generar pedidos planificados.

Los tres procesos de planificación principales son:

-  **Planificación maestra** - El plan maestro calcula los requisitos netos. Se basa en pedidos reales actuales y permite a las empresas controlar el reaprovisionamiento de inventario a diario y a corto plazo. Otro término para describirlo es *Plan de requisitos netos*. Para obtener más información consulte [Planificación maestra](master-plans.md). 

-  **Planificación de previsión** - La programación de previsiones calcula los requisitos brutos. Se basa en las proyecciones futuras (o previsiones) y permite a las empresas realizar la planificación a largo plazo de la capacidad y los materiales. Para obtener más información consulte [Planificación de previsión](introduction-demand-forecasting.md). 

-  **Planificación maestra de empresas vinculadas** - El plan maestro de empresas vinculadas calcula los requisitos netos para todas las entidades jurídicas. Conecta la oferta y la demanda entre las empresas no solo para la oferta y la demanda a corto plazo y en firme, sino también para la oferta y la demanda a largo plazo y planificada (que aún no es en firme). Para obtener más información, consulte [Planificación maestra de empresas vinculadas](https://mbspartner.microsoft.com/AX/CourseOverview/1276)  (eLearning) (requiere la cuenta de CustomerSource). 

Las empresas pueden cambiar la salida del plan. Pueden ejecutar un cambio neto regenerador, o ambos. Los planes regeneradores actualizan todos los requisitos, mientras que los planes de cambio neto solo actualizan el plan en los artículos con nuevos requisitos que han llegado desde la última ejecución.

Los planes de programación maestra normalmente abordan el a corto plazo, que puede ser de una semana a seis meses. El módulo de la planificación maestra determina las necesidades de suministro (material) y capacidad (recursos) necesarias para cubrir la demanda actual (requisitos netos). En la mayoría de las empresas esto se amplía para incluir el plazo acumulativo más largo de los productos que se van a recibir.

## <a name="learning-map"></a>Mapa de aprendizaje

El siguiente mapa de aprendizaje muestra los conceptos y tareas principales que forman el marco del módulo de planificación maestra. Haga clic en la sección [Vínculos rápidos](#quick-links) para obtener información sobre cómo utilizar el módulo.

[![Mapa de aprendizaje de la planificación maestra](./media/master-planning-learning-map.png)](./media/master-planning-learning-map.png)

## <a name="quick-links"></a>Vínculos rápidos
|      |   |
|------|---|
|        [Planes maestros](master-plans.md)       |     [Generar un plan con restricciones](./tasks/constrained-plan.md)  |
| [Creación de un plan de materiales para coproductos](./tasks/create-material-plan-co-products.md)   |  [Planificación maestra y funcionalidad multisitio](master-plan-multisite-functionality.md)  |
| [Crear un plan de empresas vinculadas](./tasks/create-intercompany-plan.md) | [Visión general de previsión de la demanda](introduction-demand-forecasting.md)  | 
|[Claves de reducción](reduction-keys.md)| [Conceptos básicos de planificación maestra](https://mbspartner.microsoft.com/AX/CourseOverview/1275) (eLearning) (Requiere la cuenta de CustomerSource)     |
|  [Conceptos básicos de fabricación de procesos](https://mbspartner.microsoft.com/D365E/CourseOverview/1514) (eLearning) (Requiere la cuenta de CustomerSource) | [Planificación maestra de empresas vinculadas](https://mbspartner.microsoft.com/AX/CourseOverview/1276) (eLearning) (Requiere la cuenta de CustomerSource)|
                                  
## <a name="additional-resources"></a>Recursos adicionales

### <a name="roadmaps"></a>Mapas de ruta
Consulte la [Guía básica de Microsoft Dynamics 365](https://roadmap.dynamics.com/) para ver qué características nuevas hemos lanzado y cuáles están en desarrollo.

### <a name="blogs"></a>Blogs
Puede encontrar opiniones, novedades y otra información acerca de la planificación maestra y otras soluciones en el [blog del equipo de I+D y fabricación de Dynamics AX](https://blogs.msdn.microsoft.com/axmfg) y el [blog del equipo de I+D de administración de cadenas de suministros en Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm).

### <a name="task-guides"></a>Guías de tareas
Hay ayuda adicional disponible como guías de tareas en Finance and Operations. Para tener acceso a las guías de tareas, haga clic en el botón **Ayuda** en cualquier página.

### <a name="webinars"></a>Seminarios web
[Utilizar Azure Machine Learning para la previsión de demanda](https://www.youtube.com/watch?v=4nQsccdFFDA&feature=youtu.be)





