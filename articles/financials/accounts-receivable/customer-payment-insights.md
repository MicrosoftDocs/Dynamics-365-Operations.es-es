---
title: Customer payment insights (vista previa)
description: "Este tema describe cómo Customer payment insights puede ayudar a predecir cuándo se pagará una factura y ayuda a las organizaciones a crear estrategias de optimización que mejoren la probabilidad de que se les pague a tiempo."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: 
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-04-02
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: 841ea53f754f61c2930e77fdafc85eac72f47d7a
ms.openlocfilehash: 9e722db6302d7ef51c01601cde245d4f4a333eba
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="customer-payment-insights-preview"></a>Customer payment insights (vista previa)

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> Esta característica forma parte de una versión de destino y solo está disponible para los usuarios que han optado por participar en la vista previa privada. Esta característica se incluirá en una próxima versión de disponibilidad general.

# <a name="overview"></a>Información general

Las organizaciones a menudo encuentran difícil predecir cuándo un cliente pagará sus facturas. Esta falta de información puede llevar a previsiones de flujo de caja inexactos, procesos de cobro ineficientes y la posibilidad de que los pedidos se entreguen a clientes que pueden presentar un riesgo de crédito. Customer payment insights (vista previa) utiliza el aprendizaje automático para predecir cuándo se pagará una factura. También proporciona estrategias de optimización que se pueden adaptar para maximizar la probabilidad de que los clientes paguen a tiempo.

## <a name="predictions"></a>Predicciones

Las predicciones de pago permiten a las organizaciones mejorar sus procesos empresariales al ayudarles a:

-   Identificar fácilmente las facturas que se prevé que se pagarán con retraso.
-   Tomar las medidas adecuadas para mejorar las posibilidades de recibir el pago a tiempo.

Customer payment insights (vista previa) utiliza el aprendizaje automático para predecir cuándo se pagará una factura. Utiliza datos históricos de facturas, pagos y clientes para crear un modelo de aprendizaje automático que se utiliza para predecir cuándo se pagará una factura.

Para cada factura abierta, Customer payment insights (vista previa) predice tres probabilidades de pago:

-  Probabilidad de que el pago se realice a tiempo (dentro de la fecha de vencimiento de la factura).
-  Probabilidad de que el pago se realice dentro de los 30 días siguientes a la fecha de vencimiento de la factura,
-  Probabilidad de que el pago se realice después de los 30 días siguientes a la fecha de vencimiento de la factura,

La probabilidad de pagos se puede ver en la sección de predicciones.

[![Predicciones de pago](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)

A cada factura también se le asigna una probabilidad de pago ganadora utilizando uno de los tres escenarios de probabilidades de pago previstas definidos anteriormente. El escenario con mayor probabilidad de pago es el escenario ganador.


Por ejemplo, supongamos que para una factura la predicción muestra un 71 por ciento de probabilidad de que la factura se pague a tiempo, un 13 por ciento de probabilidad de que la factura se pague dentro de los 30 días siguientes a la fecha de vencimiento y un 16 por ciento de probabilidad de que la factura se pague después de los 30 días siguientes a la fecha de vencimiento. La probabilidad más alta muestra que la factura estará en el escenario de pago a tiempo, por lo que la factura se etiquetará con la probabilidad de que se pague a tiempo.

[![Predicciones de pago](./media/payment-predict.png)](./media/payment-predict.png)

## <a name="optimization-strategies"></a>Estrategias de optimización

Además de las predicciones de pago, Customer payment insights (vista previa) puede utilizar estrategias de optimización para mejorar las posibilidades de recibir el pago a tiempo. Esto permite a las organizaciones realizar análisis del tipo "Y si...", por lo que los usuarios pueden ajustar los parámetros de la factura y del cliente y, después, comparar el efecto correspondiente en la probabilidad de recibir a tiempo el pago de las facturas.

Por ejemplo, una organización puede desear evaluar el efecto de actualizar el descuento por pronto pago en las facturas sobre la probabilidad de recibir el pago a tiempo. Cuando las facturas están optimizadas para utilizar el nuevo descuento, los usuarios pueden revisar el efecto de aplicar el descuento sobre la probabilidad de recibir los pagos de esas facturas a tiempo. Si el coste de aplicar el descuento es mínimo en comparación con el beneficio de cobrar el pago a tiempo, la organización puede optar por aplicar el descuento seleccionado a todos los pedidos pendientes futuros.

> [!NOTE] 
> Actualmente, solo el descuento está disponible como una estrategia de optimización para Customer payment insights (vista previa).

[![Predicciones optimizadas](./media/optimized-pay.png)](./media/optimized-pay.png)

## <a name="how-to-get-customer-payment-insights-preview"></a>Cómo obtener Customer payment insights (vista previa)

Si está interesado en probar Customer payment insights (vista previa), envíe un correo electrónico al [equipo de Finance Insights Preview](mailto:fiap@microsoft.com). 

## <a name="privacy-statement"></a>Declaración de privacidad

Las vistas previas almacenan los datos de los clientes en Estados Unidos. Además, las vistas previas (1) pueden utilizar menos medidas de privacidad y seguridad que el servicio Dynamics 365 for Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) tienen soporte limitado.

