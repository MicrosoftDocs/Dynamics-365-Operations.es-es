---
title: Secuencia numérica unificada para id. de trabajo
description: Esta función proporciona una secuencia numérica única y unificada que genera identificaciones de trabajo para los módulos de control de producción, ejecución de fabricación y tiempo y asistencia.
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 00212803c46d898a39eafbc5c62016eb829535e2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824951"
---
# <a name="unified-number-sequence-for-job-ids"></a>Secuencia numérica unificada para id. de trabajo

[!include [banner](../includes/banner.md)]

Esta función proporciona una secuencia numérica única y unificada que genera identificaciones de trabajo para los módulos de control de producción, ejecución de fabricación y tiempo y asistencia. Anteriormente, podía elegir una secuencia de números diferente para cada uno de estos módulos, lo que podría resultar en identificación de trabajo en conflicto si dos o más de estas secuencias usaban un formato idéntico. Tal conflicto puede provocar daños en los datos.

## <a name="turn-on-this-feature-for-your-system"></a>Activar esta función para su sistema

Si su sistema aún no incluye la función descrita en este tema, vaya a [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active la característica *Secuencia numérica unificada para identificaciones de trabajo*.

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a>Configurar la secuencia numérica unificada para id. de trabajo

Después de habilitar esta función, la configuración **Identificación de trabajo** de secuencia numérica ubicada en las páginas de parámetros para los módulos Control de producción, Ejecución de fabricación y Tiempo y asistencia quedará obsoleta y se añadirá un campo nuevo **Identificación de trabajo unificado**. El valor **ID de trabajo unificado** es compartido por los tres módulos, asegurando así que todos los módulos hagan referencia a la misma secuencia numérica. Por lo tanto, los identificadores de trabajo serán únicos en los tres módulos y nunca se producirá un conflicto.

Para configurar la secuencia numérica unificada para id. de trabajo:

1. Active la función como se describe en la sección anterior.
1. Identifique la secuencia numérica que desea utilizar para sus id. de trabajo unificados o cree una nueva. Para obtener más información, consulte [Información general de secuencias numéricas](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).
1. Vaya a la página **Parámetros de control de producción**, **Parámetros de ejecución de fabricación**, o **Parámetros de tiempo y asistencia**. No importa cuál elija porque cuando realiza esta configuración en cualquiera de esas páginas, todas las demás páginas se actualizarán automáticamente.
1. Abra la pestaña **Secuencias numéricas** en la página de parámetros seleccionados.
1. Asigne el **Código de secuencia numérica** que identificó previamente a la fila de la cuadrícula **Id. de trabajo unificados**.
