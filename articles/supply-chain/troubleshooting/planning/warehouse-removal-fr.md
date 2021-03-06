---
title: No puede eliminar la dimensión de previsión de la demanda de almacén de las líneas de previsión
description: No puede eliminar la dimensión de previsión de la demanda de almacén de las líneas de previsión.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6b643c4fe51ae6ce73b34ab81d4e458dcd5032df
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026884"
---
# <a name="you-cant-remove-the-warehouse-demand-forecast-dimension-from-forecast-lines"></a>No puede eliminar la dimensión de previsión de la demanda de almacén de las líneas de previsión

Número de KB: 4614408

## <a name="symptoms"></a>Síntomas

Este problema ocurre cuando la dimensión **Almacén** no está asignada en la pestaña **Dimensiones de previsión** de la página **Parámetros de previsión de la demanda**. Sin embargo, la columna **Almacén** se muestra en la página **Previsión de la demanda** (**Planificacion maestra \> Previsión \> Entidad de previsión manual \> Líneas de previsión de la demanda**).

## <a name="resolution"></a>Resolución

Los ajustes en la pestaña **Dimensiones de previsión** de la página **Parámetros de previsión de la demanda** no afecta a la página **Previsión de la demanda**. Controlan la previsión de línea de base que se genera y se muestra en la previsión de la demanda ajustada. Sin embargo, no controlan las dimensiones que se requieren para el pronóstico de la demanda "real". Al autorizar los registros que se muestran en la página **Previsión de la demanda ajustada**, puede convertirlos en entradas de previsión "reales" para un modelo de previsión. Después, ese modelo se puede utilizar para la planificación maestra.

En la página **Previsión de la demanda**, las dimensiones de la previsión "real" que se muestran en las líneas de previsión de la demanda son parte de las dimensiones del inventario. (Este comportamiento se asemeja al comportamiento de las líneas de pedidos de ventas). Si su sistema no está configurado para usar **Almacén** como dimensión de inventario obligatoria, puede personalizar la página para ocultar la columna.
