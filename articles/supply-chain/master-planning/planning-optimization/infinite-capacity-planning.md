---
title: Programación con capacidad infinita
description: Este tema proporciona información sobre la programación de capacidad infinita para Planning Optimization. También describe las limitaciones de las funciones actuales.
author: ChristianRytt
ms.date: 09/21/2021
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 9c1eef91bcf7d1ce6379e87417be5a8b3be069e5
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575641"
---
# <a name="scheduling-with-infinite-capacity"></a>Programación con capacidad infinita

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

La fucnión *Programación de capacidad infinita para la optimización de la planificación* presenta la programación basada en la información de la ruta. Le permite programar trabajos basados en una amplia gama de configuraciones de ruta. La programación para la optimización de la planificación cubre la configuración de ruta de uso frecuente, incluida la secuencia de operación de ruta o los requisitos para los recursos de operación de ruta.

## <a name="turn-on-the-infinite-capacity-scheduling-feature"></a>Active la función de programación de capacidad infinita

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de características**, la función aparece de la siguiente forma:

- **Módulo:** *Planificación maestra*
- **Nombre de la función:** *Programación de capacidad infinita para Optimización de planificación*

Para obtener más información sobre esta función, consulte [Programación con selección de recursos según la capacidad](capability-based-scheduling.md).

## <a name="added-functionality"></a>Funcionalidad agregada

La fucnión *Programación de capacidad infinita para la optimización de la planificación* permite la programación de trabajos basada en la información de la ruta. Por lo tanto, se puede utilizar una configuración de ruta para programar procesos de producción. Aunque esta característica tiene algunas limitaciones que la planificación maestra incorporada no tiene, admite la funcionalidad más común que se requiere para los escenarios de fabricación.

La característica considera tanto *rutas simples* como *redes de rutas*. Usando el campo **Siguiente** en una operación de ruta, puede configurar rutas complejas que tienen múltiples puntos de partida y múltiples operaciones que se ejecutan en paralelo. El sistema considerará estructuras de ruta complejas de este tipo durante la programación.

Además, la función admite *operaciones paralelas* en rutas. Usando las opciones *Primario* y *Secundario* en el campo **Prioridad** en operaciones de ruta, puede definir una estructura de ruta donde una operación de ruta es la operación principal y otra operación es secundaria. En este caso, el sistema considerará la estructura de ruta durante la programación.

Durante el proceso de programación, el sistema también considera los *requerimientos de recursos* que se especifican para una operación. El sistema utiliza los requisitos de recursos para determinar qué recursos se requieren para realizar la operación. Actualmente, la función *Programación de capacidad infinita para la optimización de la planificación* admite los siguientes tipos de requisitos de recursos:

- Tipo de recurso
- Recurso
- Grupo de recursos
- Capacidad (para obtener más información sobre esta función, consulte [Programación con selección de recursos según la capacidad](capability-based-scheduling.md)).

> [!NOTE]
> Los requisitos relacionados con los recursos humanos, como las habilidades o los requisitos de certificados, aún no se admiten.

La función también es compatible con las propiedades operativas **Tiempo de preparación** y **Tiempo de ejecución**. Cuando configura estas propiedades en una operación de ruta, el proceso de programación creará los trabajos de configuración y proceso adecuados.

En resumen, la programación de Planning Optimization admite los escenarios más utilizados. Puede crear la ruta, agregar operaciones primarias y secundarias, definir las próximas operaciones, agregar requisitos de recursos y agregar tiempo de configuración y tiempo de ejecución. El sistema considerará esta información durante la programación.

## <a name="limitations"></a>Limitaciones

Se aplican las siguientes limitaciones cuando utiliza la programación para Planning Optimization:

- La función solo admite una capacidad infinita.
- La función no admite la función de carga de recursos.
- La función no considera el rechazo de ruta.
- La función admite *Duración* solo como la selección de recurso principal.

Tenga en cuenta que la función *Programación de capacidad infinita para la optimización de la planificación* se mejora constantemente. Microsoft espera introducir soporte para configuraciones de programación adicionales en versiones futuras.
