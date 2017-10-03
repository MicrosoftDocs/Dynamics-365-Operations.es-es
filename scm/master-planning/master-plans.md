---
title: Planes maestros
description: "Utilice varios planes maestros para dar soporte a las operaciones de trabajo diarias de la empresa, simular distintas estrategias de planificación que desee supervisar e implementar una directiva empresarial, como una directiva sobre rendimiento interno o la satisfacción del cliente."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqParameters, ReqPlanSched
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 7911
ms.assetid: a116b7de-3d6d-4321-87ba-5a5d99c2f64e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 85d57a2acb492cbcf2f2cef6c4983df1a3076a81
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017

---

# <a name="master-plans"></a>Planes maestros

[!include[banner](../includes/banner.md)]


Utilice varios planes maestros para dar soporte a las operaciones de trabajo diarias de la empresa, simular distintas estrategias de planificación que desee supervisar e implementar una directiva empresarial, como una directiva sobre rendimiento interno o la satisfacción del cliente. 

Puede configurar planes maestros en la página **Planes maestros**.

Hay dos tipos de planes:
-   **Plan estático**: el cálculo de la planificación maestra usa los datos actuales para generar un plan neto de los requisitos. Este plan permanece sin cambios hasta la próxima vez que se ejecute la planificación maestra. Es un plan operativo que varios miembros del personal de la empresa, como el comprador o el encargado de la planificación de producción, pueden utilizar para basar sus decisiones en él y realizar sus actividades y tareas diarias.
-   **Plan dinámico**: este plan se inicia con el mismo plan de requisitos netos que generó la planificación maestra. No obstante, puede actualizar el plan dinámico cada vez que cambien los datos maestros. Esto podría ser al crear un nuevo pedido de ventas, por ejemplo. Esto le permite supervisar la red de pedido de cambio y la disponibilidad de artículos sin alterar el plan estático que otros utilizan para sus procesos de trabajo.

Una empresa puede elegir trabajar solo con un plan dinámico o puede utilizar ambos planes, el estático y el dinámico. Además, puede configurar cualquier plan maestro para reflejar una estrategia concreta o dirigir un asunto. Los ejemplos son:
-   Establecer niveles de inventario superiores para garantizar que no se agoten las existencias.
-   Establecer márgenes de seguridad mayores para protección frente a los proveedores poco fiables.

También puede configurar el inicio del plan dinámico de modo que se actualice con el nuevo plan de requisitos cada vez que se ejecute la planificación maestra. Puede especificar estos ajustes en la página **Parámetros de planificación maestra**.



<a name="see-also"></a>Consulte también
--------

[Configuración de cobertura](coverage-settings.md)

[Separación de la planificación táctica y operativa para la programación maestra](http://blogs.msdn.com/b/axmfg/archive/2012/10/12/separating-tactical-and-operative-planning-for-master-scheduling.aspx)

[Planificación maestra: ¿usar un plan maestro estático y dinámico o usar un plan?](https://community.dynamics.com/ax/b/msdynaxlessonslearned/archive/2014/01/16/master-planning-use-a-static-and-dynamic-master-plan-or-use-one-plan)




