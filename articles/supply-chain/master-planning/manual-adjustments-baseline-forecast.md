---
title: Realización de ajustes manuales en la previsión de línea base
description: Este tema explica cómo puede realizar ajustes manuales a una previsión de línea base y ver los detalles de la previsión.
author: roxanadiaconu
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8897e0fe01e7ed5af9a8d5b99de6b9b4506554f1
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "2815143"
---
# <a name="make-manual-adjustments-to-the-baseline-forecast"></a>Realización de ajustes manuales en la previsión de línea base

[!include [banner](../includes/banner.md)]

Este tema explica cómo puede realizar ajustes manuales a una previsión de línea base y ver los detalles de la previsión. 

Antes de realizar ajustes manuales, es importante que entienda algunos conceptos en diversas páginas.

## <a name="grid-on-the-adjusted-demand-forecast-page"></a>Cuadrícula en la página Previsión de la demanda ajustada
La página **Previsión de la demanda ajustada** incluye una cuadrícula con la estructura siguiente:

-   La primera columna muestra los artículos, las claves de asignación de artículos, empresas, etc., para los que se ha generado la previsión. El subtítulo de la página ofrece una descripción de las dimensiones de previsión actuales que se muestran en la cuadrícula. Por ejemplo, si el subtítulo de la página es **Empresa / Sitio / Clave de asignación de artículos**, y uno de los encabezados de la fila en la cuadrícula es **USMF / 1 / D\_Alloc**, esa fila muestra la previsión para la empresa USMF, sitio 1 y clave de asignación de artículos **D\_Alloc**.
-   Las columnas siguientes representan los cubos de previsión para los que se ha generado la previsión. Cada encabezado de columna es la primera fecha del cubo de previsión que la columna muestra.
-   Los valores de las celdas representan la previsión para un artículo, una clave de asignación de artículos, etc., para dicho cubo específico de previsión.

## <a name="forecast-aggregation-and-de-aggregation"></a>Agregación de inicio y agregación de previsión
El subtítulo de la página muestra el nivel de agregación de previsión. 

Por ejemplo, si el título de la página es **Empresa / Sitio / Clave de asignación / Número de artículo / Color / Tamaño / Configuración / Estilo**, no hay agregación de previsión, y la previsión se muestra en el nivel del artículo y sus dimensiones. Para cambiar la agregación, use la página **Cambiar las dimensiones de previsión**, que puede abrir desde el menú de la aplicación. 

Para modificar la previsión, haga clic en una de las celdas disponibles, y especifique el valor ajustado de previsión. La celda corregida pasa a estar en negrita inmediatamente para indicar que la previsión que muestra no es la previsión creada por el servicio de previsión de demanda, sino que se ha ajustado manualmente. 

Si cambia la agregación para hacer que la página muestre más datos agregados, puede usar la página **Líneas de previsión de la demanda** para ver las líneas de previsión individuales que constituyen la previsión agregada. 

Por ejemplo, ha generado la previsión en el nivel de artículo, pero sabe que la demanda para este artículo aumentará en todos los sitios debido a una promoción u otro evento similar. En este caso, puede establecer la agregación en **Empresa / Clave de asignación de artículos / Artículo** en la página **Cambiar las dimensiones de previsión**. Puede ajustar la previsión global para el artículo en todos los sitios en la cuadrícula **Previsión de la demanda ajustada**. Para ver el efecto del cambio a través de todos los sitios, abra la página **Líneas de previsión de la demanda**. En esta página, verá una línea para el artículo para cada sitio, la cantidad ajustada de previsión y la cantidad original de la previsión. 

Cuando el ajuste de la cantidad prevista se realiza en un nivel agregado, el sistema usa la asignación ponderada para distribuir el cambio entre las líneas que crean la agregación. 

También puede realizar ajustes manuales en la página **Líneas de previsión de la demanda**, modificando el valor **Cantidad total** o las celdas de **Cantidad** en la cuadrícula de agregación.

## <a name="viewing-details-of-the-forecast"></a>Visualización de los detalles de la previsión
Puede abrir la página **Detalles de previsión de la demanda** para ver más información acerca de la previsión. 

La página **Detalles de previsión de la demanda** muestra la siguiente información en un formato gráfico y tabular:

-   La demanda histórica en las que se basan las predicciones de previsión.
-   La previsión actual que usa la planificación maestra.
-   Los nuevos valores e importes de previsión de la demanda por los que se han ajustado manualmente.
-   El intervalo de confianza para los valores de previsión.
-   El modelo de previsión que se usó para generar la previsión. Si está viendo datos agregados, verá la lista de todos los métodos que se usaron para toda la serie de tiempo agregada.
-   La precisión de modelo interna (MAPE). Para obtener más información acerca de la precisión de previsión, consulte [Seguimiento de la precisión de previsión](monitor-forecast-accuracy.md).

**Notas:**

-   El intervalo de confianza que aparece en la sección **Previsión** de la página representa la diferencia entre el límite superior del intervalo de confianza y el límite inferior del intervalo de confianza. Para ver los valores de los límites máximo y mínimo, pase el ratón por encima del gráfico en la sección **Demanda y previsión históricas gráficamente**.
-   Si utiliza el servicio de aprendizaje automático de Microsoft Azure Machine de previsión de demanda, puede especificar el porcentaje del nivel de confianza que debe tener la previsión que se genera. Un intervalo de confianza consta de un intervalo de valores que actúan como estimaciones para la previsión de la demanda. Un porcentaje de nivel de confianza del 95 por ciento indica que hay un 5 por ciento de riesgo de que la previsión de la demanda se encuentre fuera del intervalo de confianza.

También puede realizar ajustes manuales en la previsión en la página **Detalles de previsión de la demanda**, modificando los valores en la fila **Previsión** en la sección **Previsión**.

<a name="additional-resources"></a>Recursos adicionales
--------

[Supervisión de la precisión de previsión](monitor-forecast-accuracy.md)

[Generar previsión estadística de línea base](generate-statistical-baseline-forecast.md)



