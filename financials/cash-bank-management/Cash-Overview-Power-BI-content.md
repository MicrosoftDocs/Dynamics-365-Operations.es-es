---
title: "Contenido de Power BI de visión general de efectivo"
description: "Este tema describe el contenido de Power BI de visión general de efectivo. Explica cómo tener acceso a los informes que se incluyen en el contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el contenido."
author: saraschi2
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: e969c2033463d565ce782c7dc8cfc4b458349289
ms.contentlocale: es-es
ms.lasthandoff: 06/20/2017

---

# Contenido de Power BI de visión general de efectivo
<a id="cash-overview-power-bi-content" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Este tema describe el contenido de Microsoft Power BI de **visión general de efectivo**. Explica cómo tener acceso a los informes que se incluyen en el contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el contenido.

## Información general
<a id="overview" class="xliff"></a>

El contenido de Power BI **visión general de efectivo** se creó para las personas responsables del efectivo en su organización. El contenido de Power BI **visión general de efectivo** proporciona visibilidad en su flujo de efectivo. También proporcionan previsiones que pueden ayudarle a tomar decisiones mejores y por tanto mejorar el estado del flujo de efectivo. Puede analizar el efectivo por entidad jurídica, divisa y cuenta bancaria para obtener una mejor comprensión de los excesos y la escasez.

## Acceso al contenido de Power BI
<a id="accessing-the-power-bi-content" class="xliff"></a>

Si utiliza Dynamics 365 for Finance and Operations, Enterprise Edition (actualización de julio de 2017), los informes de contenido de Power BI de **visión general de efectivo** aparecen en los espacios de trabajo **Visión general de efectivo** y **Gestión bancaria**.

## Informes que se incluyen en el contenido de Power BI
<a id="reports-that-are-included-in-the-power-bi-content" class="xliff"></a>
La siguiente tabla ofrece información sobre las métricas que se encuentran en cada página de informe en el contenido de Power BI de **visión general de efectivo**.

| Informe                                | Contenido |
|---------------------------------------|----------|
| Visión general del efectivo para todas las empresas         | <ul><li>Entradas y salidas en la divisa del sistema</li><li>Saldos de divisa previstos</li><li>Saldo bancario total en divisa del sistema</li><li>Saldo por entidad jurídica</li><li>Saldo real de hoy frente al saldo previsto en la divisa de la cuenta bancaria</li></ul> |
| Visión general del efectivo para la empresa actual       | <ul><li>Entradas y salidas en la divisa de contabilidad</li><li>Saldos de divisa previstos</li><li>Saldo bancario total en divisa de contabilidad</li><li>Saldo real de hoy frente al saldo previsto en la divisa de la cuenta bancaria</li></ul> |
| Visión general del efectivo para todas las empresas    | <ul><li>Entradas y salidas en la divisa del sistema</li><li>Resumen de previsiones diario</li><li>Detalles de previsión</li></ul> |
| Previsión de flujo de efectivo en divisa de la empresa | <ul><li>Entradas y salidas en la divisa de contabilidad</li><li>Resumen de previsiones diario</li><li>Detalles de previsión</li></ul> |
| Previsión actual                     | <ul><li>Saldos de divisa previstos</li><li>Resumen de divisa diario</li><li>Detalles de previsión</li></ul> |
| Saldos bancarios                         | <ul><li>Saldo bancario total en divisa del sistema</li><li>Saldo por entidad jurídica</li><li>Saldo real de hoy frente al saldo previsto en la divisa de la cuenta bancaria</li><li>Saldo por cuenta bancaria</li><li>Saldo por divisa</li></ul> |

## Ampliar el contenido de Power BI
<a id="extending-the-power-bi-content" class="xliff"></a>
Puede proporcionar análisis muy buenos a aquellos que no se registren en Dynamics 365 mediante los paquetes de contenido disponibles en Lifecycle Services (LCS). Estos paquetes de contenido se pueden modificar para que incluyan otros informes o representaciones visuales y, a continuación, publicarlos en el inquilino de Power BI.com para su análisis. 

El contenido de Power BI de **visión general del efectivo** se encuentra en la biblioteca de activos compartidos de LCS. Para obtener información sobre cómo descargar contenido e implementarlo en su organización, consulte [Contenido de Power BI en LCS en Microsoft y sus socios](/dynamics365/unified-operations/dev-itpro/analytics/power-bi-content-microsoft-partners). Para ver una demostración que muestra cómo implementar el contenido de Power BI, consulte [Contenido de Power BI de Microsoft y sus socios en Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) (Office Mix).

## Comprensión del modelo de datos y de las entidades
<a id="understanding-the-data-model-and-entities" class="xliff"></a>

En la tabla siguiente se muestran las entidades en las que se basaba el paquete de contenido de Power BI de **visión general del efectivo**.

| Entidad                                                                          | Contenido |
|---------------------------------------------------------------------------------|----------|
| LedgerCovLiquidityMeasurement\_Company                                          | Empresas para filtrar informes por |
| LedgerCovLiquidityMeasurement\_Date                                             | Fechas para filtrar informes por |
| LedgerCovLiquidityMeasurement\_LedgerCovForecastActual                          | Saldo bancario real en comparación con el último saldo bancario previsto |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidity                               | Detalles de transacción previstos |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceCompany    | Entradas, salidas y saldo de efectivo resumidos mediante la divisa de contabilidad de cada empresa |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceEnterprise | Entradas, salidas y saldo de efectivo resumidos mediante la divisa del sistema para todas las empresas |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityTransactionCurrency            | Importe neto de la transacción y saldo de divisas resumidos mediante la divisa de transacción |

Estas entidades se usaban para crear medidas calculadas en el modelo de datos. Estas medidas calculadas se utilizan para calcular los gráficos en informes que se utilizan en el contenido de Power BI de **visión general del efectivo**. Para incluir cálculos adicionales en sus informes y en el panel de información, puede descargar y modificar el archivo de Power BI en LCS. Este archivo es el modelo de datos predeterminado usado para crear el contenido. Una vez que haya realizado las modificaciones, puede crear contenido organizativo y paneles informativos que contienen la información que ha agregado.

