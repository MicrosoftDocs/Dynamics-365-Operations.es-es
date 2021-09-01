---
title: Proceso de lanzamiento de Optimización de planificación e historial de versiones
description: Este tema proporciona información sobre el proceso de lanzamiento y el historial de lanzamiento de Optimización de planificación.
author: crytt
ms.date: 7/28/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 64c8cd3ed6ff522a9ef90831ae502c5d50fbc05816aaa764d2a8e122934fc2bb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722400"
---
# <a name="planning-optimization-release-process-and-release-history"></a>Proceso de lanzamiento de Optimización de planificación e historial de versiones

[!include [banner](../../includes/banner.md)]

Microsoft actualiza Optimización de planificación mensualmente. Sin embargo, según los requisitos comerciales, ocasionalmente publicamos actualizaciones adicionales entre los lanzamientos programados.

Cada versión se publica en las regiones individuales donde está disponible Optimización de planificación. El proceso suele tardar tres días.

Mientras se actualiza Optimización de planificación, la planificación maestra puede ejecutarse un poco más lento de lo habitual.

Los entornos que utilizan Optimización de planificación reciben automáticamente la última versión. No se requiere ninguna acción por parte del usuario: el servicio se actualiza automáticamente. Sin embargo, ninguna funcionalidad de cambio radical se envía automáticamente a los entornos. De forma predeterminada, los cambios que se consideran radicales están desactivados y deben activarse explícitamente mediante el uso de [gestión de funciones ](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Por lo tanto, esos cambios no aparecerán en los entornos hasta que elija habilitarlos.

Debido a que las notificaciones no se muestran cuando se actualiza Optimización de planificación en su entorno, puede revisar las notas de la versión en la siguiente tabla para determinar cuándo se publicaron los cambios y qué funcionalidad introdujeron. Esta tabla muestra los cambios que se publicaron para Optimización de planificación, si esos cambios están asociados con una función de la gestión de funciones y la fecha del lanzamiento.

| Cambios | Detalles de la gestión de funciones | Fecha de emisión |
|---|---|---|
| <p>Requisitos de tipo de recurso para la programación de capacidad infinita</p><p>Eficiencia de recursos y eficiencia de calendario para una programación de capacidad infinita</p><p>Para más información, consulte [Programación con capacidad infinita ](infinite-capacity-planning.md). | <p>Disponible en la gestión de funciones a partir de la versión 10.0.20.</p><p>Nombre de la función: *Programación de capacidad infinita para Optimización de planificación*</p> | 6 de julio de 2021 |
| Mejoras generales de calidad | No se requiere gestión de funciones. | 6 de julio de 2021 |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
