---
title: Eliminación de valores atípicos de los datos de transacción históricos al calcular una previsión de la demanda
description: Este artículo describe cómo excluir valores atípicos de los datos históricos que se usan para calcular una previsión de la demanda. Al excluir los valores atípicos se puede mejorar precisión de la previsión.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup, ReqDemPlanOutlierQueryPreview
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d4e42e566cef774c1a25cf48ec131b74924868d0
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741104"
---
# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a>Eliminación de valores atípicos de los datos de transacción históricos al calcular una previsión de la demanda

[!include [banner](../includes/banner.md)]

Este artículo describe cómo excluir valores atípicos de los datos históricos que se usan para calcular una previsión de la demanda. Al excluir los valores atípicos se puede mejorar precisión de la previsión.

Puede excluir valores atípicos para mejorar la precisión de la previsión. Esta tarea es opcional. Esta es una visión general del proceso:

1.  Haga clic en **Planificación maestra** &gt; **Configuración** &gt; **Previsión de demanda** &gt; **Eliminación de valores atípicos** para abrir la página **Eliminación de valores atípicos**, donde puede usar una consulta para seleccionar las transacciones que desea excluir.
2.  Seleccione la empresa a la que se aplica la consulta y especifique un nombre y una descripción. El campo **Fecha de consulta** se establece automáticamente en la fecha actual.
3.  Seleccione la casilla **Activo** para excluir de los datos históricos las transacciones que se encuentran mediante la consulta. Esta configuración se aplicará cuando cree una previsión de línea base.
4.  En la página **Consulta de eliminación de valores atípicos** puede agregar, quitar y seleccionar los criterios que definen las transacciones que se excluirán al calcular la previsión de línea base. Por ejemplo, seleccione un artículo o una transacción de pedido concreto que desee excluir.
5.  Haga clic en **Mostrar transacciones**. La página **Transacciones de valores atípicos** enumera las transacciones que cumplen los criterios que se define en la consulta y que se excluyen de los datos históricos al calcular la previsión de la demanda.

**Nota:** también puede crear una consulta basada en una pregunta existente. Seleccione la consulta que copiar y, a continuación, haga clic en **Duplicar**. El campo **Fecha de consulta** identifica la versión. Puede usar la consulta tal cual, o puede hacer clic en **Editar consulta** para modificar los criterios. Puede modificar el nombre y la descripción de la nueva consulta.

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de la previsión de la demanda](introduction-demand-forecasting.md)
- [Supervisión de la precisión de previsión](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]