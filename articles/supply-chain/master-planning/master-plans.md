---
title: Visión general de los planes maestros
description: Utilice varios planes maestros para dar soporte a las operaciones de trabajo diarias de la empresa, simular distintas estrategias de planificación que desee supervisar e implementar una directiva empresarial, como una directiva sobre rendimiento interno o la satisfacción del cliente.
author: t-benebo
ms.date: 05/28/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ReqParameters, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "7911"
- intro-internal
ms.assetid: a116b7de-3d6d-4321-87ba-5a5d99c2f64e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b3d30d9ef2f08c2cb7b2ca022ff1a816567a247
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468766"
---
# <a name="master-plans-overview"></a>Visión general de los planes maestros

[!include [banner](../includes/banner.md)]

Utilice varios planes maestros para dar soporte a las operaciones de trabajo diarias de la empresa, simular distintas estrategias de planificación que desee supervisar e implementar una directiva empresarial, como una directiva sobre rendimiento interno o la satisfacción del cliente.

Puede configurar planes maestros en la página **Planes maestros**.

Hay dos tipos de planes:

- **Plan estático**: el cálculo de la planificación maestra usa los datos actuales para generar un plan neto de los requisitos. Este plan permanece sin cambios hasta la próxima vez que se ejecute la planificación maestra o se cambie el plan manualmente. Este es un plan operativo que varios miembros del personal de la empresa, como el comprador o el encargado de la planificación de producción, pueden utilizar para basar sus decisiones en él y realizar sus actividades diarias.
- **Plan dinámico**: este plan se inicia con el mismo plan de requisitos netos que generó la planificación maestra. No obstante, puede actualizar el plan dinámico cada vez que cambien los datos maestros. Esto podría ser al crear un nuevo pedido de ventas, por ejemplo. Esto le permite supervisar la red de pedido de cambio y la disponibilidad de artículos sin alterar el plan estático que otros utilizan para sus procesos de trabajo.

Una empresa puede elegir trabajar solo con un plan dinámico o puede utilizar ambos planes, el estático y el dinámico. Además, puede configurar cualquier plan maestro para reflejar una estrategia concreta o dirigir un asunto. Los ejemplos son:

- Establecer niveles de inventario superiores para garantizar que no se agoten las existencias.
- Establecer márgenes de seguridad mayores para protección frente a los proveedores poco fiables.

También puede configurar el inicio del plan dinámico de modo que se actualice con el nuevo plan de requisitos cada vez que se ejecute la planificación maestra. Puede especificar estos ajustes en la página **Parámetros de planificación maestra**.

## <a name="additional-resources"></a>Recursos adicionales

- [Configuración de cobertura](coverage-settings.md)
- [Separación de la planificación táctica y operativa para la programación maestra](https://community.dynamics.com/ax/b/dynamicsaxmanufacturingrdteamblog/posts/separating-tactical-and-operative-planning-for-master-scheduling)
- [Planificación maestra: ¿usar un plan maestro estático y dinámico o usar un plan?](https://community.dynamics.com/ax/b/msdynaxlessonslearned/archive/2014/01/16/master-planning-use-a-static-and-dynamic-master-plan-or-use-one-plan)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
