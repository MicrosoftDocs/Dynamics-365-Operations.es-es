---
title: Página principal de Finance Insights
description: Finance Insights proporciona modelos configurables y extensibles para ayudarle a predecir con precisión e inteligencia el flujo de efectivo de su empresa, predecir cuándo recibirá los pagos pendientes y generar una propuesta de presupuesto que puede acelerar su proceso de presupuestación. Todas estas características se basan en modelos de Machine Learning inteligentes.
author: ShivamPandey-msft
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 2f04ef1a0de815596f629fede25a247c58e026f4
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "9643887"
---
# <a name="finance-insights-home-page"></a>Página principal de Finance Insights

[!include [banner](../includes/banner.md)]

Finance Insights proporciona soluciones configurables y extensibles para ayudarle a predecir con inteligencia el flujo de efectivo de su empresa, predecir cuándo recibirá los pagos pendientes y generar una propuesta de presupuesto que puede ayudar a acelerar su proceso de presupuestación. Estas funciones utilizan plantillas inteligentes de aprendizaje automático para crear modelos con los datos que usted proporciona (incluidos los datos de terceros, como información de informes de consumidores de un servicio de información). Estas capacidades inteligentes informan la toma de decisiones y lo ayudan a tomar medidas para responder de manera efectiva a los desafíos comerciales actuales y anticipados. Usted es responsable de todos los datos que se utilicen o procedan de Finance Insights.

> [!NOTE]
> Finance Insights está disponible para la implementación en los Estados Unidos de América, Canadá, Reino Unido, Europa, Asia Pacífico, Japón, Australia y Nueva Zelanda. Microsoft está agregando gradualmente soporte para más regiones.

## <a name="prerequisites"></a>Requisitos previos

En esta sección se enumeran los requisitos para utilizar la información financiera. Siempre que sea posible, se proporcionan vínculos a fuentes de información adicional.

### <a name="system-requirements"></a>Requisitos del sistema

Se requiere un entorno de nivel 2 (caja múltiple) para obtener una vista previa de Finance Insights. Para información general sobre los entornos, consulte [Planificación de entornos](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

### <a name="version-requirements"></a>Requisitos de las versiones

Este artículo se aplica a la versión 10.0.21 Microsoft Dynamics 365 Finance y posteriores.

### <a name="license-requirements"></a>Requisitos de licencia

Finance insights usa créditos de AI Builder para crear predicciones financieras. Todas las licencias necesarias para ello se incluyen con la licencia de inquilino. A cada inquilino de Dynamics 365 Finance se le proporcionan 20.000 créditos de AI Builder cada mes. Si se requieren créditos adicionales para necesidades comerciales, se pueden comprar directamente de AI Builder.

### <a name="historical-data-requirements"></a>Requisitos de datos históricos

Se requiere al menos un año de facturas de clientes para entrenar correctamente el modelo de Machine Learning que se usa para la característica de predicciones de pagos de clientes. Se recomiendan tres años de datos históricos para las previsiones de flujo de efectivo. Se recomiendan tres años de presupuesto histórico y/o datos reales para propuestas presupuestarias inteligentes.

## <a name="configure-finance-insights"></a>Configurar Finance Insights

Debe completar pasos de configuración antes de poder utilizar Finance Insights. Para obtener más información sobre cómo configurar la información financiera, consulte [Configuración de información financiera](configure-for-fin-insites.md).

## <a name="create-a-data-integrator-project"></a>Crear un proyecto integrador de datos

Deberá crear un proyecto integrador de datos para que los datos que genera el modelo de Machine Learning puedan fluir hacia Dynamics 365 Finance. Para conocer los pasos para crear ese proyecto, consulte [Crear un proyecto integrador de datos](create-data-integrate-project.md).

## <a name="enable-finance-insights-capabilities"></a>Habilitar las capacidades de información financiera

Cuando haya completado los pasos de configuración y haya configurado los datos de demostración, debe activar y configurar cada capacidad que planea usar: predicciones de pago de clientes, pronóstico de flujo de efectivo y propuestas de presupuesto.

### <a name="enable-customer-payment-predictions"></a>Habilitar las predicciones de pago de clientes
Si está utilizando datos de demostración para probar las predicciones de pago de los clientes, es posible que deba importar datos de demostración adicionales para crear su modelo de IA correctamente. 

Para habilitar las predicciones de pago de clientes, debe completar un conjunto de pasos para crear un modelo de Machine Learning que use los datos de su organización para generar predicciones sobre cuándo es probable que los clientes paguen facturas pendientes y cuándo es probable que se paguen facturas específicas. Para obtener más información y los pasos específicos para completarlo, consulte [Habilitar las predicciones de pago de los clientes](enable-cust-paymnt-prediction.md). 

### <a name="enable-cash-flow-forecasting"></a>Habilitar previsiones de flujo de efectivo
Para habilitar la previsión de flujo de efectivo, debe completar un conjunto de pasos para crear un modelo de Machine Learning que utilice los datos de su organización para generar previsiones de flujo de efectivo. Para obtener más información y los pasos específicos para completarlo, consulte [Habilitar las predicciones de flujo de efectivo](enable-cash-flow-forecasting.md).

### <a name="enable-budget-proposals"></a>Habilitar propuestas de presupuesto

La función de propuestas de presupuestos utiliza un modelo de Machine Learning junto con los datos históricos de su organización para generar una propuesta de presupuesto. La propuesta generada puede ayudarle a comenzar un proceso de presupuestación que es más efectivo y eficiente que un proceso manual. Para conocer los pasos específicos para habilitar esta característica, consulte [Habilitar propuestas de presupuesto](enable-budget-proposal.md). 

## <a name="using-finance-insights-features"></a>Uso de las funciones de información financiera

### <a name="using-customer-payment-predictions"></a>Uso de las predicciones de pago de clientes

- Para saber cómo las predicciones de pago de clientes pueden proporcionar la información necesaria para comenzar actividades de cobro de manera proactiva, consulte [Utilizar las predicciones de pagos de clientes](use-customer-payment-predictions.md).
- Para obtener información que pueda ayudarle a evaluar la efectividad del modelo de predicción después de que haya comenzado a usar la característica, consulte [Evaluar el modelo de predicción de pagos inicial del cliente](evaluate-payment-prediction.md).
- Para obtener información que pueda ayudarlo a ajustar los datos que se utilizan para construir la predicción y, por lo tanto, mejorar su efectividad, consulte [Mejorar el modelo de predicción](improve-model.md).
- Para obtener más información sobre los resultados de los modelos de predicción, consulte [Resultados de los modelos de Machine Learning](confusion-matrix.md).

### <a name="using-cash-flow-forecasts"></a>Uso de las previsiones de flujo de efectivo

La capacidad de pronóstico de flujo de efectivo puede ayudarle a estimar con mayor precisión su posición de efectivo. La previsión de flujo de efectivo inteligente se basa en la funcionalidad de previsión de flujo de efectivo existente en Dynamics 365 Finance. Para revisar la capacidad existente, consulte [Previsión de flujo de efectivo](../cash-bank-management/cash-flow-forecasting.md).

- Para conocer las nuevas capacidades de los pronósticos de flujo de efectivo, consulte [Pronóstico de flujo de efectivo](cash-flow-forecast-intro.md).
- Para obtener información sobre la importación de datos externos para incluirlos en su pronóstico de flujo de efectivo aquí, consulte [Utilizar datos externos en las previsiones de flujo de efectivo](external-data-in-cash-flow.md). 
- Para obtener información sobre cómo utilizar un modelo de IA para proyectar el flujo de efectivo a corto plazo, consulte [Posición de efectivo](cash-position.md).
- Para obtener información sobre cómo guardar posiciones de flujo de efectivo y pronósticos de flujo de efectivo como instantáneas, y para comparar una instantánea con los datos reales, consulte [Descripción general de instantáneas](payment-snapshots.md).

### <a name="using-budget-proposal"></a>Uso de propuesta de presupuesto

Para obtener información sobre cómo acelerar la creación de un presupuesto, consulte [Propuestas de presupuesto](budget-proposals.md). 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
