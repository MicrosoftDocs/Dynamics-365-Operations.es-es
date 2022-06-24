---
title: Evaluar el modelo de predicción de pago de cliente inicial
description: Este artículo describe los pasos que puede seguir para conocer el modelo de predicción de pagos de clientes y evaluar su efectividad.
author: ShivamPandey-msft
ms.date: 05/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: fcdf276505cf58267a38e9d6174a155ad307653b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847013"
---
# <a name="evaluate-the-initial-customer-payment-prediction-model"></a>Evaluar el modelo de predicción de pago de cliente inicial

[!include [banner](../includes/banner.md)]

Este artículo explica cómo evaluar un modelo de predicción después de haber activado Finance Insights y luego haber generado y entrenado su primer modelo. Este artículo trata los modelos para predecir los pagos de los clientes. Describe los pasos que puede seguir para conocer el modelo de predicción de pagos de clientes y evaluar su efectividad.

## <a name="getting-details-about-the-model"></a>Obtener detalles sobre el modelo

En la página **Parámetros de Finance Insights** de Microsoft Dynamics 365 Finance, aparece un vínculo **Mejorar la precisión del modelo** junto a la puntuación de precisión.

[![Vínculo Mejorar la precisión del modelo.](./media/prediction-model.png)](./media/prediction-model.png)

Este vínculo le lleva a AI Builder, donde puede obtener más información sobre el modelo actual y también tomar medidas para mejorarlo. La ilustración siguiente muestra la página que se abre.

[![AI Builder.](./media/what-to-predict.png)](./media/what-to-predict.png)

La página que se abre muestra la siguiente información:

- En la sección **Rendimiento**, el grado de rendimiento del modelo proporciona una perspectiva sobre la calidad del modelo. Para obtener más información sobre este grado, consulte [Rendimiento del modelo de predicción](/ai-builder/prediction-performance) en la documentación de AI Builder.
- La sección **Datos más influyentes** muestra la importancia de los diferentes tipos de datos de entrada para su modelo. Puede evaluar esta lista y los porcentajes correspondientes para determinar si la información es coherente con lo que sabe sobre su negocio y mercado.

    [![Secciones de datos Rendimiento y Más influyentes para el modelo de predicción.](./media/models.png)](./media/models.png)

- En la sección **Rendimiento**, seleccione **Ver detalles** para obtener más información sobre el grado y otras consideraciones. En la siguiente ilustración, los detalles muestran que el modelo usa menos información de la recomendada. Por tanto, el sistema ha generado un mensaje de advertencia.

    [![Advertencias sobre el rendimiento del modelo.](./media/details.png)](./media/details.png)

## <a name="digging-deeper"></a>Mayor profundidad

Aunque la precisión es un buen punto de partida para evaluar un modelo, y el grado de rendimiento proporciona perspectiva, AI Builder proporciona métricas más detalladas que puede utilizar para su evaluación. Para descargar los detalles, en la sección **Rendimiento**, seleccione el botón de puntos suspensivos (**...**) próximo al botón **Modelo de uso** y luego seleccione **Descargar métricas detalladas**.

[![Comando Descargar métricas detalladas.](./media/performance.png)](./media/performance.png)

La siguiente ilustración muestra el formato en el que puede descargar los datos.

[![Formato de datos descargados.](./media/data-format.png)](./media/data-format.png)

Para un análisis más profundo de los resultados, un buen punto de partida es revisar la métrica "Matriz de confusión". Por ejemplo, aquí están los datos que se muestran para esta métrica en la ilustración anterior.

`{"name": "Confusion Matrix", "value": {"schema_type": "confusion_matrix", "schema_version": "1.0.0", "data": {"class_labels": ["0", "1", "2"], "matrix": [[71, 9, 21], [5, 0, 27], [2, 0, 45]]}}, "type": "dictionaryNumericalList", "isGlobalScore": false}`

Puede expandir estos datos de la siguiente manera.

| &nbsp;                   | Previsto Puntual | Previsto Tarde | Previsto Muy tarde |
|--------------------------|-------------------|----------------|---------------------|
| Pago real puntual   | **71**            | 0              | 21                  |
| Pago real tarde      | 5                 | **0**          | 27                  |
| Pago real muy tarde | 2                 | 0              | **45**              |

La matriz de confusión muestra los resultados de un conjunto de datos de prueba seleccionados al azar en el proceso de entrenamiento. Debido a que estas facturas cerradas no se utilizaron para entrenar el modelo, son buenos casos de prueba para el modelo. Además, dado que se conoce el estado real de la factura, también se puede ver el rendimiento del modelo.

Lo primero que debe buscar es el valor real más común. Aunque este valor puede no estar perfectamente alineado con el conjunto de datos general, es una aproximación razonable. En este caso, **Pago real puntual** ocurre para 92 de las 171 facturas totales y es el valor real más común. Por lo tanto, es una buena base para su modelo. Si imaginara que todas las facturas fueran puntuales, estaría en lo correcto en 92 de 171 veces (es decir, el 54 por ciento de las veces).

Es importante que conozca lo equilibrado que está su conjunto de datos. En este caso, 92 de entre 171 facturas se pagaron a tiempo, 32 se pagaron tarde y 47 se pagaron muy tarde. Estos valores indican un conjunto de datos razonablemente equilibrado, porque hay resultados no triviales en cada clasificación. Una situación en la que uno de los estados tiene muy pocos resultados puede ser un desafío para un modelo de Machine Learning.

La precisión del modelo indica el número de predicciones correctas para el conjunto de datos de prueba. Estas predicciones correctas son los valores que se muestran en negrita en el ejemplo anterior. En este caso, los valores producen una precisión calculada del 67,8 por ciento (= \[71 + 0 + 45\] ÷ 171). Este valor representa una mejora del 14 por ciento sobre la estimación inicial del 54 por ciento y es un indicador de la calidad del modelo.

Si observa más de cerca la matriz de confusión, notará que el modelo hace un buen trabajo al predecir los pagos de facturas puntuales y muy tarde. Sin embargo, es incorrecto acerca de las 32 facturas que en realidad se pagaron tarde (pero no muy tarde). Este resultado sugiere que se requiere exploración y mejora adicional del modelo.

Un número que representa mejor el rendimiento del modelo que la precisión es la puntuación F1 Macro. Esta puntuación considera los resultados de cada estado de clasificación (puntual, tarde y muy tarde). Por ejemplo, aquí están los datos que se muestran para la métrica "F1 Macro" en la ilustración anterior.

`{"name": "F1 Macro", "value": 0.4927170868347339, "type": "percentage", "isGlobalScore": false}`

En este caso, la puntuación de F1 Macro de aproximadamente 49,3 por ciento indica que el modelo no proporciona predicciones efectivas en cada estado, a pesar de una puntuación de precisión general que parece razonablemente alta.

## <a name="improving-the-model"></a>Mejora del modelo

Una vez que comprenda mejor los resultados de su primer modelo, es posible que desee mejorar el modelo agregando o quitando columnas de características, o filtrando cualquier parte del conjunto de datos que no admita predicciones precisas. Cierre AI Builder y luego use el vínculo **Mejorar el modelo** en Dynamics 365 Finance para reiniciar el proceso de AI Builder. Puede experimentar con diferentes características sin afectar el modelo publicado. El modelo publicado se ve afectado solo cuando selecciona **Publicar**. Recuerde que se utiliza un solo modelo para su instancia de Dynamics 365 Finance. Por lo tanto, debe revisar cuidadosamente cualquier modelo nuevo antes de publicarlo.

## <a name="for-more-information"></a>Para obtener más información

Para obtener más información sobre cómo evaluar modelos de predicción, consulte [Resultados de los modelos de Machine Learning](confusion-matrix.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
