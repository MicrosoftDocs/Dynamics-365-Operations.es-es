---
title: Programación con capacidad infinita
description: En este artículo se proporciona información acerca de capacidad infinita de programación. También describe las limitaciones de las funciones actuales.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7249734e5d2644145a36276dbc818a40b5962805
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740015"
---
# <a name="scheduling-with-infinite-capacity"></a>Programación con capacidad infinita

[!include [banner](../../includes/banner.md)]

La fucnión *Programación de capacidad infinita para la optimización de la planificación* presenta la programación basada en la información de la ruta. Le permite programar trabajos basados en una amplia gama de configuraciones de ruta. La programación cubre la configuración de ruta de uso frecuente, incluida la secuencia de operación de ruta o los requisitos para los recursos de operación de ruta.

## <a name="turn-the-infinite-capacity-scheduling-feature-on-or-off"></a>Active o desactive la función de programación de capacidad infinita

Para usar esta característica, debe estar activada para su sistema. A partir de la versión 10.0.29 de Supply Chain Management, la característica está activada de forma predeterminada. Los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Programación de capacidad infinita para Optimización de planificación* en el espacio de trabajo [Administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Para obtener más información sobre esta función, consulte [Programación con selección de recursos según la capacidad](capability-based-scheduling.md).

## <a name="added-functionality"></a>Funcionalidad agregada

La fucnión *Programación de capacidad infinita para la optimización de la planificación* permite la programación de trabajos basada en la información de la ruta. Por lo tanto, se puede utilizar una configuración de ruta para programar procesos de producción. Aunque esta característica tiene algunas limitaciones que el motor de planificación maestra en desuso incorporada no tiene, admite la funcionalidad más común que se requiere para los escenarios de fabricación.

La característica considera tanto *rutas simples* como *redes de rutas*. Usando el campo **Siguiente** en una operación de ruta, puede configurar rutas complejas que tienen múltiples puntos de partida y múltiples operaciones que se ejecutan en paralelo. El sistema considerará estructuras de ruta complejas de este tipo durante la programación.

Además, la función admite *operaciones paralelas* en rutas. Usando las opciones *Primario* y *Secundario* en el campo **Prioridad** en operaciones de ruta, puede definir una estructura de ruta donde una operación de ruta es la operación principal y otra operación es secundaria. En este caso, el sistema considerará la estructura de ruta durante la programación.

Durante el proceso de programación, el sistema también considera los *requerimientos de recursos* que se especifican para una operación. El sistema utiliza los requisitos de recursos para determinar qué recursos se requieren para realizar la operación. Actualmente, la función *Programación de capacidad infinita para la optimización de la planificación* admite los siguientes tipos de requisitos de recursos:

- Tipo de recurso
- Recurso
- Grupo de recursos
- Capacidad (para obtener más información sobre esta función, consulte [Programación con selección de recursos según la capacidad](capability-based-scheduling.md)).

> [!NOTE]
>
> - Si el recurso o el grupo de recursos se establecen en capacidad infinita, la planificación maestra los considerará como capacidad infinita.
> - Los requisitos relacionados con los recursos humanos, como las habilidades o los requisitos de certificados, aún no se admiten.

La función también es compatible con las propiedades operativas **Tiempo de preparación** y **Tiempo de ejecución**. Cuando configura estas propiedades en una operación de ruta, el proceso de programación creará los trabajos de configuración y proceso adecuados.

En resumen, la programación admite los escenarios más utilizados. Puede crear la ruta, agregar operaciones primarias y secundarias, definir las próximas operaciones, agregar requisitos de recursos y agregar tiempo de configuración y tiempo de ejecución. El sistema considerará esta información durante la programación.

## <a name="limitations"></a>Limitaciones

Se aplican las siguientes limitaciones cuando utiliza la característica *Capacidad infinita de programación para Planning Optimization*:

- La función solo admite una capacidad infinita.
- La función no admite la función de carga de recursos.
- La función no considera el rechazo de ruta.
- La función admite *Duración* solo como la selección de recurso principal.
