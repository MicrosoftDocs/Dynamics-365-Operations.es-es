---
title: Proceso de lanzamiento de Optimización de planificación e historial de versiones
description: Este artículo proporciona información sobre el proceso de lanzamiento y el historial de lanzamiento de Optimización de planificación.
author: t-benebo
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 5e8b4ab74bf973a131499799efa66e9c7fe9d5be
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "9403727"
---
# <a name="planning-optimization-release-process-and-release-history"></a>Proceso de lanzamiento de Optimización de planificación e historial de versiones

[!include [banner](../../includes/banner.md)]

Microsoft actualiza Optimización de planificación mensualmente. Sin embargo, según los requisitos comerciales, ocasionalmente publicamos actualizaciones adicionales entre los lanzamientos programados.

Cada versión se publica en las regiones individuales donde está disponible Optimización de planificación. El proceso suele tardar tres días.

Mientras se actualiza Optimización de planificación, la planificación maestra puede ejecutarse un poco más lento de lo habitual.

Los entornos que utilizan Optimización de planificación reciben automáticamente la última versión. No se requiere ninguna acción por parte del usuario: el servicio se actualiza automáticamente. Sin embargo, ninguna funcionalidad de cambio radical se envía automáticamente a los entornos. De forma predeterminada, los cambios que se consideran radicales están desactivados y deben activarse explícitamente mediante el uso de [administración de características ](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Por lo tanto, esos cambios no aparecerán en los entornos hasta que elija habilitarlos.

Debido a que las notificaciones no se muestran cuando se actualiza Optimización de planificación en su entorno, puede revisar las notas de la versión en la siguiente tabla para determinar cuándo se publicaron los cambios y qué funcionalidad introdujeron. Esta tabla muestra los cambios que se publicaron para Optimización de planificación, si esos cambios están asociados con una función de la gestión de funciones y la fecha del lanzamiento.

| Cambios | Detalles de la gestión de funciones | Fechas de emisión |
|---|---|---|
| <p>Mejoras generales de rendimiento, calidad y estabilidad. | No se requiere administración de características. | 29 de agosto - 3 de septiembre de 2022 |
| <p>Mejoras generales de rendimiento, calidad y estabilidad.<p>[Mantenimiento de calendario centralizado de optimización de planificación](../supply-chain-calendars-master-planning.md)<p>[Sugerencias de optimización de la planificación para optimizar el suministro existente](../action-messages.md)<p>[Soporte de optimización de planificación para subcontrataciones](../../production-control/manage-subcontract-work-production.md) | No se requiere administración de características. | 7-11 de marzo de 2022 |
| <p>Se agregó soporte de prioridad de planificación para órdenes de producción. | Disponible con la versión 10.0.25 como parte de la función denominada *Soporte de MRP basado en prioridades para la optimización de la planificación*. | 12-18 de noviembre de 2021 |
| <p>Mejoras generales de rendimiento, calidad y estabilidad. | No se requiere administración de características. | 12-18 de noviembre de 2021 |
| <p>Se agregó compatibilidad para fórmulas de cálculo de tiempo de proceso, ruta de producción con superposición y número de operación de producción en transacciones de requisitos.</p><p>Mensajes de error mejorados para la programación de producción relacionados con el tiempo de espera, no se pudo encontrar la capacidad y ruta cíclica.</p><p>Consistencia mejorada al calcular las fechas de recepción y emisión tanto en pedidos planificados como en pedidos firmes.</p><p>Mejoras generales de rendimiento, calidad y estabilidad. | Nombre de la función: *Programación de capacidad infinita para Optimización de planificación* | Octubre 22-27, 2021 |
| <p>Se agregó compatibilidad para considerar el porcentaje de residuos en el cálculo del tiempo de procesamiento.</p><p>Se agregó compatibilidad para el número de operaciones y el uso de materiales durante la programación. | Nombre de la función: *Programación de capacidad infinita para Optimización de planificación* | Octubre 5-7, 2021 |
| <p>Se agregó compatibilidad para tipos de trabajo de la ruta de producción: **Cola antes**, **Cola después** y **Tiempo de transporte**.</p><p>Mejoras generales de rendimiento, calidad y estabilidad. | Nombre de la función: *Programación de capacidad infinita para Optimización de planificación* | Septiembre 25-30, 2021 |
| <p>Compatibilidad agregada para planes maestros con **Método de programación** establecido en *Programación de operaciones*.</p><p>En la página **Grupos de ruta**, respete la configuración de las casillas **Activación**, **Tiempo de trabajo** y **Capacidad** para filas con un **Tipo de ruta/trabajo** de *Configuración* o *Proceso*. </p><p>Mejoras generales de rendimiento, calidad y estabilidad. | <p>La programación de operaciones está disponible en la administración de características a partir de la versión 10.0.20.</p><p>Nombre de la función: *Programación de capacidad infinita para Optimización de planificación*</p>  | 9-17 de septiembre de 2021 |
| Mejoras generales de rendimiento, calidad y estabilidad. | No se requiere administración de características. | 25–30 de agosto, 2021 |
| <p>Se ha agregado el campo **Plazo** a pedidos planificados.</p><p>Mejoras generales de rendimiento, calidad y estabilidad.</p> | No se requiere administración de características. | 12–17 de agosto, 2021 |
| <p>Se han agregado requisitos de tipo de recurso para la programación de capacidad infinita.</p><p>Se ha mejorado la eficiencia de recursos y la eficiencia de calendario para una programación de capacidad infinita.</p><p>Para más información, consulte [Programación con capacidad infinita ](infinite-capacity-planning.md). | <p>Disponible en la administración de características a partir de la versión 10.0.20.</p><p>Nombre de la función: *Programación de capacidad infinita para Optimización de planificación*</p> | 6–12 de julio, 2021 |
| Mejoras generales de calidad. | No se requiere administración de características. | 6–12 de julio, 2021 |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
