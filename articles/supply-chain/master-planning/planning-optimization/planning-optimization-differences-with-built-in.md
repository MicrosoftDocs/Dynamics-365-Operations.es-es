---
title: Diferencias entre la planificación maestra incorporada y Optimización de planificación
description: Este tema enumera las características que Optimización de planificación aún no admite y que no aparecen en la página de análisis de ajuste de Optimización de planificación.
author: crytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a102f1d77362f650c060ce5d0aee5b62d2102532
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344963"
---
# <a name="differences-between-built-in-master-planning-and-planning-optimization"></a>Diferencias entre la planificación maestra incorporada y Optimización de planificación

[!include [banner](../../includes/banner.md)]

Los resultados de Optimización de planificación pueden diferir de los resultados del motor de planificación maestro integrado. Las diferencias pueden estar provocadas por funciones pendientes. Este tema enumera las características que Optimización de planificación aún no admite y que no aparecen en la **[página de análisis de ajuste de Optimización de planificación](planning-optimization-fit-analysis.md)**].

| Característica | Comportamiento actual en Optimización de planificación |
|---|---|
| Productos de peso capturado | Los productos de peso capturado se consideran productos habituales.|
| Dimensiones extensibles | Las dimensiones extensibles están vacías en los pedidos planificados, incluso cuando la casilla **Plan de cobertura por dimensión** está seleccionada en la página **Grupos de dimensiones de almacenamiento** o **Seguimiento de grupos de dimensiones**. |
| Ejecuciones de producción filtradas | Para obtener más detalles, consulte [Planificación de la producción - Filtros](production-planning.md#filters). |
| Planificación de previsión | No se admite la planificación de previsiones. Recomendamos que utilice la planificación maestra donde se asigna un modelo de previsión al plan maestro. |
| Secuencias numéricas para pedidos planificados | No se admiten secuencias numéricas para pedidos planificados. Los números de orden planificados se generan en el lado del servicio. |
| Copia del plan, eliminación del plan y limpieza de la versión del plan | <p>Los siguientes elementos están deshabilitados en **Planificación maestra\> Planificación maestra\> Mantener planes** en el panel de navegación:</p><ul><li>Copia de plan</li><li>Eliminar el plan</li><li>Limpieza de la versión del plan</li></ul> |
| Pedidos de devolución | No se consideran los pedidos de devolución. |
| Programación de funciones relacionadas | Para obtener más información, consulte [Programación con capacidad infinita ](infinite-capacity-planning.md#limitations). |
| Calendarios de transporte | Se ignora el valor de la columna **Calendario de transporte** de la página **Modos de entrega**. |

## <a name="additional-resources"></a>Recursos adicionales

- [Análisis de idoneidad de optimización de la planificación](planning-optimization-fit-analysis.md)
- [Parámetros no utilizados por Optimización de planificación](not-used-parameters.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
