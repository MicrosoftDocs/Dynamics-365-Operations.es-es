---
title: Usar predicciones de pago de clientes (versión preliminar)
description: Este tema describe los requisitos previos y los pasos generales necesarios para usar una versión de prueba de información financiera.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-11-16
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: e0445046d8016dfa2c02c1ff1a05bdd148f9409a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969262"
---
# <a name="use-customer-payment-predictions-preview"></a>Usar predicciones de pago de clientes (versión preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tema explica cómo utilizar las predicciones de pago de clientes. Antes de utilizar esta característica, asegúrese de haber completado los pasos de configuración correspondientes. Para obtener más información, consulte [Habilitar predicciones de pago de clientes](enable-cust-paymnt-prediction.md).

Puede ver las predicciones de pago de clientes en el espacio de trabajo **Administrar crédito y cobros de clientes** y en dos nuevas páginas de lista, **Predicciones de pago por transacción** y **Predicción de pago por cliente**.

### <a name="manage-customer-credit-and-collections-workspace"></a>Gestionar el espacio de trabajo de crédito y cobros de clientes

El espacio de trabajo **Administrar crédito y cobros de clientes** incluye dos nuevos mosaicos, **Predicción de pago por transacción** y **Clientes con saldos atrasados elevados previstos**.

- El mosaico **Predicción de pago por transacción** muestra el número de transacciones de clientes abiertas que tienen una probabilidad de pago inferior al 50 por ciento en la categoria **Puntual**. Puede seleccionar este mosaico para abrir la página de lista **Predicciones de pago por transacción**.
- El mosaico **Clientes con saldos atrasados altos previstos** muestra el número de clientes para los que se prevé que más de la mitad (50 por ciento) del saldo total se pagará tarde o muy tarde. Puede seleccionar este mosaico para abrir la página de lista **Predicción de pago por transacción**.

[![Gestionar el espacio de trabajo de crédito y cobros de clientes](./media/manage-customer-credit-collections.png)](./media/manage-customer-credit-collections.png)

### <a name="payment-predictions-per-transaction-list-page"></a>Predicciones de pago por página de lista de transacciones

En la página de lista **Predicciones de pago por transacción** puede ver la probabilidad de pago de las transacciones abiertas en las categorías **Puntual**, **Tarde** y **Muy tarde**. Para cada transacción de la cuadrícula, la columna **Probabilidad de Puntual** muestra la probabilidad de que la factura se pague en la fecha de vencimiento o antes. Si la probabilidad de un pago puntual es inferior al 50 por ciento, aparece un círculo rojo junto al porcentaje en la columna **Probabilidad de Puntual** para indicar el riesgo de pago tardío.

[![Predicción de pago por página de lista de transacciones](./media/payment-predictions-per-transaction.png)](./media/payment-predictions-per-transaction.png)

El panel **Información relacionada** del lado derecho de la página muestra más detalles sobre las predicciones:

- Para la transacción que se selecciona en la cuadrícula, la ficha desplegable **Predicción de pagos** muestra los detalles de las predicciones de pago en las categorías **Puntual**, **Tarde** y **Muy tarde**. La sección **Factores principales** muestra los principales factores que influyeron en las predicciones. Los factores principales son los atributos de la transacción seleccionada y/o el cliente de esa transacción.
- La ficha desplegable **Información del cliente** muestra la factura actual, el pago y las estadísticas de cobros del cliente para la transacción seleccionada.
- La ficha desplegable **Historial del cliente** muestra el historial de pagos del cliente en las categorías **Puntual**, **Tarde** y **Muy tarde**.

Los datos de la sección **Factores principales** y de las fichas desplegables **Información del cliente** e **Historial del cliente** ayudan a explicar las predicciones de pago. Puede ayudarle a aumentar su confianza en la eficacia de las predicciones.

[![Indicadores gráficos de predicciones de pago en el panel Información relacionada](./media/payment-prediction-gauges.png)](./media/payment-prediction-gauges.png)

### <a name="payment-prediction-per-customer-list-page"></a>Predicción de pago por página de lista de clientes

La página de lista **Predicción de pago por cliente** muestra el saldo abierto total y la cantidad que se prevé que se pague en las categorías **Puntual**, **Tarde** y **Muy tarde**.

[![Predicciones de pago por página de clientes](./media/payment-predictions-per-transaction-02.png)](./media/payment-predictions-per-transaction-02.png)

El importe del pago en cada categoría se calcula como la suma del promedio ponderado del saldo de transacciones. Este importe se calcula en función de las probabilidades de pago de cada categoría.

Por ejemplo, un cliente tiene tres transacciones abiertas que tienen las siguientes probabilidades de pago en cada categoría.

| Transacción | Importe | Probabilidad de pago puntual | Probabilidad de pago tarde | Probabilidad de pago muy tarde |
|-------------|--------|-----------------------------|--------------------------|-------------------------------|
| T1          | 100    | Porcentaje 10                  | Porcentaje 50               | Porcentaje 40                    |
| T2          | 1.000  | Porcentaje 50                  | Porcentaje 30               | Porcentaje 20                    |
| T3          | 10,000 | Porcentaje 1                   | Porcentaje 4                | Porcentaje 95                    |

En este caso, los pagos se proyectan para cada categoría de la siguiente manera.

| Categorías   | Transacción T1      | Transacción T2         | Transacción T3            | Total |
|-----------|---------------------|------------------------|---------------------------|-------|
| Puntual   | 100 × 10 ÷ 100 = 10 | 1.000 × 50 ÷ 100 = 500 | 10.000 × 1 ÷ 100 = 100    | 610   |
| Con retraso      | 100 × 50 ÷ 100 = 50 | 1.000 × 30 ÷ 100 = 300 | 10.000 × 4 ÷ 100 = 400    | 750   |
| Con mucho retraso | 100 × 40 ÷ 100 = 40 | 1.000 × 20 ÷ 100 = 200 | 10.000 × 95 ÷ 100 = 9.500 | 9,740 |

La sección **Información relacionada** del lado derecho de la página muestra más detalles sobre las predicciones:

- Para la transacción que se selecciona en la cuadrícula, la ficha desplegable **Predicción de pagos** muestra los detalles de las predicciones de pago en las categorías **Puntual**, **Tarde** y **Muy tarde**. La sección **Factores principales** muestra los principales factores que influyeron en los pagos. Los factores principales son los atributos de la transacción seleccionada y/o el cliente de esa transacción.
- La ficha desplegable **Información del cliente** muestra la factura actual, el pago y las estadísticas de cobros del cliente para la transacción seleccionada.
- La ficha desplegable **Historial del cliente** muestra el historial de pagos del cliente en las categorías **Puntual**, **Tarde** y **Muy tarde**.

Los datos de la sección **Factores principales** y de las fichas desplegables **Información del cliente** e **Historial del cliente** ayudan a explicar las predicciones de pago. Puede ayudarle a aumentar su confianza en la eficacia de las predicciones.

## <a name="improving-the-accuracy-of-payment-predictions"></a>Mejora de la precisión de las predicciones de pagos

Puede ver la precisión de las predicciones de pagos yendo a **Crédito y cobros \> Configurar \> Información financiera \> Parámetros de información financiera**. En la pestaña **Información de pagos del clientes**, la sección **Modelo de predicción** muestra la precisión del modelo de predicción en forma de porcentaje.

[![Precisión de las predicciones de pagos](./media/finance-insights-parameters-accuracy-2nd.png)](./media/finance-insights-parameters-accuracy-2nd.png)

Si no está satisfecho con la precisión, seleccione el vínculo **Mejorar la precisión del modelo** para abrir la experiencia de la extensión AI Builder. En la experiencia de la extensión AI Builder, puede seleccionar o cancelar la selección de campos hasta que haya seleccionado los campos que crea que son más importantes para predecir con precisión las probabilidades de pago. Cuando haya terminado, puede volver a entrenar fácilmente el modelo de predicción y publicar sus cambios. El modelo de predicción recién entrenado se seleccionará automáticamente para las predicciones en Dynamics 365 Finance.

[![Experiencia de extensión AI Builder](./media/ai-builder.png)](./media/ai-builder.png)

## <a name="release-details"></a>Detalles de la liberación

La versión preliminar pública de Finance Insights está disponible para probarla en implementaciones en los Estados Unidos de América, Europa y el Reino Unido. Microsoft está agregando gradualmente soporte para más regiones.

Las funciones de versión preliminar pública pueden y deben activarse solo en entornos de espacio aislado de nivel 2. Los modelos de configuración e IA que se crean en un entorno de espacio aislado no se pueden migrar a un entorno de producción. Para más información, consulte [Condiciones de uso suplementarias para Vistas previas de Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).

## <a name="privacy-notice"></a>Aviso de privacidad

Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.
