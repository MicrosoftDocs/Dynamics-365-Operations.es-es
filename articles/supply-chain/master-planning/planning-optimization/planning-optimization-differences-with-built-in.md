---
title: Diferencias entre la Optimización de planificación y el motor de planificación maestra en desuso
description: Este artículo enumera las características que Optimización de planificación aún no admite y que no aparecen en la página de análisis de ajuste de Optimización de planificación.
author: t-benebo
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 6e1671a508b85a94ac9687af15e898d885ea94c1
ms.sourcegitcommit: 55e440e30490b2d36d86b22aa1263d5da97633aa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2022
ms.locfileid: "9745371"
---
# <a name="differences-between-planning-optimization-and-the-deprecated-master-planning-engine"></a>Diferencias entre la Optimización de planificación y el motor de planificación maestra en desuso

[!include [banner](../../includes/banner.md)]

Los resultados de Optimización de planificación pueden diferir de los resultados del motor de planificación maestro en desuso. Las diferencias pueden estar provocadas por funciones pendientes. Este artículo enumera las características que Optimización de planificación aún no admite y que no aparecen en la **[página de análisis de ajuste de Optimización de planificación](planning-optimization-fit-analysis.md)**].

| Característica | Comportamiento actual en Optimización de planificación |
|---|---|
| Productos de peso capturado | Los productos de peso capturado se consideran productos habituales.|
| Dimensiones extensibles | Las dimensiones extensibles no son compatibles con la optimización de la planificación. Cuando se utiliza la optimización de la planificación, las dimensiones extensibles están vacías en los pedidos planificados, incluso cuando la casilla **Plan de cobertura por dimensión** está seleccionada en la página **Grupos de dimensiones de almacenamiento** o **Seguimiento de grupos de dimensiones**. |
| Ejecuciones de producción filtradas | Para obtener más detalles, consulte [Planificación de la producción - Filtros](production-planning.md#filters). |
| Planificación de previsión | No se admite la planificación de previsiones. Recomendamos que utilice la planificación maestra donde se asigna un modelo de previsión al plan maestro. |
| Secuencias numéricas para pedidos planificados | No se admiten secuencias numéricas para pedidos planificados. Los números de orden planificados se generan en el lado del servicio. El número de pedido planificado normalmente se muestra con 10 dígitos, pero la secuencia en realidad se basa en 20 caracteres, con 10 dígitos asignados para el recuento de ejecución de planificación y los otros 10 dígitos para el recuento de pedidos planificados. |
| Copia del plan, eliminación del plan y limpieza de la versión del plan | <p>Los siguientes elementos están deshabilitados en **Planificación maestra\> Planificación maestra\> Mantener planes** en el panel de navegación:</p><ul><li>Copia de plan</li><li>Eliminar el plan</li><li>Limpieza de la versión del plan</li></ul> |
| Pedidos de devolución | No se consideran los pedidos de devolución. |
| Programación de características relacionadas | Para obtener más información, consulte [Programación con capacidad infinita ](infinite-capacity-planning.md#limitations). |
| Cumplimiento de existencias de seguridad | La Optimización de planificación siempre utiliza la opción *Fecha de hoy + hora de adquisición* para el campo **Cumplir con el mínimo** en la página **Cobertura de artículos**. Esto ayuda a evitar pedidos planificados no deseados y otros problemas porque, si no se incluye el tiempo de adquisición para el stock de seguridad, los pedidos planificados que se creen con inventario disponible siempre se retrasarán debido al tiempo inicial. |
| Diagrama de árbol de existencias de seguridad y requisitos netos | El tipo de requisito *Stock de seguridad* no se incluye y no se muestra en la página **Requisitos netos**. El stock de seguridad no representa la demanda y no tiene una fecha de requisito asociada. En cambio, establece una restricción sobre la cantidad de inventario que debe estar presente en todo momento. Sin embargo, el valor de campo **Mínimo** se sigue teniendo en cuenta al calcular las órdenes planificadas durante la planificación maestra. Le sugerimos que inspeccione la columna **Cantidad acumulada** de la página **Requisitos netos** para ver cómo se consideró este valor. Debido a que la vinculación es diferente, se pueden sugerir diferentes acciones. |
| Calendarios de transporte | Se ignora el valor de la columna **Calendario de transporte** de la página **Modos de entrega**. |
| Código de cobertura mínima/máxima sin valores| Con el motor de planificación maestra en desuso, cuando utiliza un código de cobertura mínimo/máximo en el que no se establecen valores mínimos ni máximos, el motor de planificación trata el código de cobertura como un requisito y crea un pedido para cada requisito. Con la optimización de la planificación, el sistema creará un pedido por día para cubrir el monto total de ese día.  |
| Requisitos netos y pedidos previsionales creados manualmente | Con el motor de planificación maestra en desuso, los pedidos de suministro creados manualmente para un artículo aparecen automáticamente entre los requisitos netos de ese artículo. Por ejemplo, al crear un pedido de compra a partir de un pedido de ventas, el pedido de ventas aparece en la página **Requisitos netos** sin necesidad de realizar ninguna acción previa. Esto se debe a que el motor de planificación maestra en desuso registra las transacciones de inventario en la tabla `inventLogTTS` y muestra los cambios en la página **Requisitos netos** para planes dinámicos. Sin embargo, con la Optimización de la planificación, los pedidos creados manualmente no aparecerán entre los requisitos netos de un artículo hasta que se ejecute la Optimización de la Planificación (usando un plan que incluya el artículo), o hasta que seleccione **Actualizar \> Planificacion maestra** en el Panel de Acciones en la página **Requisitos netos**, que ejecutará la planificación maestra para el artículo. Para obtener más información sobre cómo trabajar con la página **Requisitos netos**, consulte [Requisitos netos e información de diagrama de árbol](net-requirements.md). |
| Asignación de recursos | Cuando se trabaja con capacidad infinita, el motor de planificación maestro en desuso asigna todos los pedidos planificados al mismo recurso en un grupo de recursos determinado. La optimización de la planificación mejora esto al seleccionar recursos de manera aleatoria para que diferentes órdenes de producción puedan usar diferentes recursos. Si desea utilizar el mismo recurso para todos los pedidos planificados, debe especificar ese recurso en la ruta. |
| Tipos de datos extendidos (EDT) | La optimización de la planificación no admite cambios en la precisión de los EDT. Esto significa que este proceso no cuenta con soporte oficial y no se garantiza que funcione. |
| Cumplimiento de existencias de seguridad | La optimización de la planificación siempre utiliza **Mínimo de cumplimiento** de *Fecha de hoy + tiempo de adquisición*. Esto prepara el sistema para usar una configuración de planificación simplificada en el futuro y para proporcionar un resultado procesable. Si no se incluye el tiempo de adquisición para el stock de seguridad, los pedidos planificados que se creen para el inventario disponible bajo siempre se retrasarán debido al tiempo de entrega. Este comportamiento puede causar ruido significativo y órdenes planificadas no deseadas. La mejor práctica es cambiar la configuración para que se use *Fecha de hoy + tiempo de adquisición*. Actualice los datos maestros para evitar advertencias. |
| Copia estática en plan dinámico | La optimización de la planificación no copia el plan estático en el plan dinámico, independientemente de esta configuración en la página **Parámetros de planificación maestra**. En general, esta operación es menos relevante debido a la velocidad y la regeneración completa que proporciona la optimización de planificación. Si se utilizan dos o más planes, se debe activar la planificación maestra para cada plan. |

## <a name="additional-resources"></a>Recursos adicionales

- [Análisis de idoneidad de optimización de la planificación](planning-optimization-fit-analysis.md)
- [Parámetros no utilizados por Optimización de planificación](not-used-parameters.md)
- [Parámetros de fecha y hora utilizados por Optimización de planificación](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
