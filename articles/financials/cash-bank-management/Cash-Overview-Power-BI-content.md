---
title: "Contenido de Power BI de visión general de efectivo"
description: "Este tema describe el contenido de Power BI de visión general de efectivo. Explica cómo tener acceso a los informes que se incluyen en el contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el contenido."
author: saraschi2
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: cb43245afe578341251b140383a3b03ba2abd962
ms.openlocfilehash: 5d02a009ca988f91a212e467d4f9784248bbae76
ms.contentlocale: es-es
ms.lasthandoff: 12/19/2017

---

# <a name="cash-overview-power-bi-content"></a>Contenido de Power BI de visión general de efectivo

[!include[banner](../includes/banner.md)]

Este tema describe el contenido de Microsoft Power BI de **visión general de efectivo**. Explica cómo tener acceso a los informes que se incluyen en el contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el contenido.

## <a name="overview"></a>Información general

El contenido de Power BI **visión general de efectivo** se creó para las personas responsables del efectivo en su organización. El contenido de Power BI **visión general de efectivo** proporciona visibilidad en su flujo de efectivo. También proporcionan previsiones que pueden ayudarle a tomar decisiones mejores y por tanto mejorar el estado del flujo de efectivo. Puede analizar el efectivo por entidad jurídica, divisa y cuenta bancaria para obtener una mejor comprensión de los excesos y la escasez.

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI

Los informes del contenido de Power BI **Visión general de efectivo** aparecen en las áreas de trabajo **Visión general de efectivo** y **Gestión bancaria**.

Para ver los informes de previsiones de flujo de efectivo con datos, debe primero ejecutar el proceso de cálculo de previsión con la función **Calcular previsiones de flujo de efectivo** del área de gestión de efectivo y bancos.  Esto es necesario realizarlo para cada empresa incluida en la previsión.  Después, necesita actualizar la medida agregada LedgerCovLiquidityMeasurement en la página **Almacén de entidades**.  

Como demostración, puede agregar datos de demostración de previsiones de flujo de efectivo mediante la página **Generar datos** del módulo de datos de demostración.  Este script insertará datos en tablas de previsiones de flujo de efectivo para rellenar rápidamente la información necesaria para los informes.  Este módulo solo está disponible si tiene el modelo de la suite de datos de demostración implementado en el entorno. 

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Informes que se incluyen en el contenido de Power BI
La siguiente tabla ofrece información sobre las métricas que se encuentran en cada página de informe en el contenido de Power BI de **visión general de efectivo**.

| Informe                                | Contenido |
|---------------------------------------|----------|
| Visión general del efectivo para todas las empresas         | <ul><li>Entradas y salidas en la divisa del sistema</li><li>Saldos de divisa previstos</li><li>Saldo bancario total en divisa del sistema</li><li>Saldo por entidad jurídica</li><li>Saldo real de hoy frente al saldo previsto en la divisa de la cuenta bancaria</li></ul> |
| Visión general del efectivo para la empresa actual       | <ul><li>Entradas y salidas en la divisa de contabilidad</li><li>Saldos de divisa previstos</li><li>Saldo bancario total en divisa de contabilidad</li><li>Saldo real de hoy frente al saldo previsto en la divisa de la cuenta bancaria</li></ul> |
| Visión general del efectivo para todas las empresas    | <ul><li>Entradas y salidas en la divisa del sistema</li><li>Resumen de previsiones diario</li><li>Detalles de previsión</li></ul> |
| Previsión de flujo de efectivo en divisa de la empresa | <ul><li>Entradas y salidas en la divisa de contabilidad</li><li>Resumen de previsiones diario</li><li>Detalles de previsión</li></ul> |
| Previsión actual                     | <ul><li>Saldos de divisa previstos</li><li>Resumen de divisa diario</li><li>Detalles de previsión</li></ul> |
| Saldos bancarios                         | <ul><li>Saldo bancario total en divisa del sistema</li><li>Saldo por entidad jurídica</li><li>Saldo real de hoy frente al saldo previsto en la divisa de la cuenta bancaria</li><li>Saldo por cuenta bancaria</li><li>Saldo por divisa</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades

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



