---
title: Programación con capacidad infinita
description: Este tema proporciona información sobre la programación de capacidad infinita para Planning Optimization. También describe las limitaciones de las funciones actuales.
author: crytt
ms.date: 6/9/2021
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fc40dc2bcf1969e4c566b624a9425638e69ab2a17892f035aeabb74068aadd14
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718981"
---
# <a name="scheduling-with-infinite-capacity"></a>Programación con capacidad infinita

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

La fucnión *Programación de capacidad infinita para la optimización de la planificación* presenta la programación basada en la información de la ruta. Le permite programar trabajos basados en una amplia gama de configuraciones de ruta. La programación para la optimización de la planificación cubre la configuración de ruta de uso frecuente, incluida la secuencia de operación de ruta o los requisitos para los recursos de operación de ruta.

## <a name="turn-on-the-infinite-capacity-scheduling-feature"></a>Active la función de programación de capacidad infinita

Si su sistema aún no incluye la función descrita en este tema, abra el espacio de trabajo [Gestión de funciones](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active la característica *Programación de capacidad infinita para Optimización de planificación*.

## <a name="added-functionality"></a>Funcionalidad agregada

La fucnión *Programación de capacidad infinita para la optimización de la planificación* permite la programación de trabajos basada en la información de la ruta. Por lo tanto, se puede utilizar una configuración de ruta para programar procesos de producción. Aunque esta característica tiene algunas limitaciones que la planificación maestra incorporada no tiene, admite la funcionalidad más común que se requiere para los escenarios de fabricación.

La característica considera tanto *rutas simples* como *redes de rutas*. Usando el campo **Siguiente** en una operación de ruta, puede configurar rutas complejas que tienen múltiples puntos de partida y múltiples operaciones que se ejecutan en paralelo. El sistema considerará estructuras de ruta complejas de este tipo durante la programación.

Además, la función admite *operaciones paralelas* en rutas. Usando las opciones *Primario* y *Secundario* en el campo **Prioridad** en operaciones de ruta, puede definir una estructura de ruta donde una operación de ruta es la operación principal y otra operación es secundaria. En este caso, el sistema considerará la estructura de ruta durante la programación.

Durante el proceso de programación, el sistema también considera los *requerimientos de recursos* que se especifican para una operación. El sistema utiliza los requisitos de recursos para determinar qué recursos se requieren para realizar la operación. Actualmente, la función *Programación de capacidad infinita para la optimización de la planificación* admite los siguientes tipos de requisitos de recursos:

- Tipo de recurso
- Recurso
- Grupo de recursos
- Capacidad

> [!NOTE]
> Los requisitos relacionados con los recursos humanos, como las habilidades o los requisitos de certificados, aún no se admiten.

La función también es compatible con las propiedades operativas **Tiempo de preparación** y **Tiempo de ejecución**. Cuando configura estas propiedades en una operación de ruta, el proceso de programación creará los trabajos de configuración y proceso adecuados.

En resumen, la programación de Planning Optimization admite los escenarios más utilizados. Puede crear la ruta, agregar operaciones primarias y secundarias, definir las próximas operaciones, agregar requisitos de recursos y agregar tiempo de configuración y tiempo de ejecución. El sistema considerará esta información durante la programación.

## <a name="limitations"></a>Limitaciones

Se aplican las siguientes limitaciones cuando utiliza la programación para Planning Optimization:

- La función solo admite la programación de trabajos. Las configuraciones relacionadas con la programación de operaciones no se consideran durante la programación, independientemente del método de programación en los planes maestros.
- La función solo admite una capacidad infinita.
- La función no admite la función de carga de recursos.
- La función no considera el rechazo de ruta.
- La función admite *Duración* solo como la selección de recurso principal.

Tenga en cuenta que la función *Programación de capacidad infinita para la optimización de la planificación* se mejora constantemente. Microsoft espera introducir soporte para configuraciones de programación adicionales en versiones futuras.
