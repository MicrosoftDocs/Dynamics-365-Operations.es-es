---
title: Información general de contenido de efectivo de Power BI
description: Este artículo describe el contenido de efectivo de Power BI. Explica cómo tener acceso a los informes que se incluyen en el contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el contenido.
author: angelad116
ms.date: 07/16/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a255afac3aa68f3a48b21e4d2fbfb046a9de603c
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "9152011"
---
# <a name="cash-overview-power-bi-content"></a>Información general de contenido de efectivo de Power BI

[!include [banner](../includes/banner.md)]

Este artículo describe el contenido de la **visión general de efectivo** de Microsoft Power BI. Explica cómo tener acceso a los informes que se incluyen en el contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el contenido.

## <a name="overview"></a>Información general

El contenido de Power BI **Visión general de efectivo** se creó para las personas responsables del efectivo en su organización. El contenido de Power BI **Visión general de efectivo** proporciona visibilidad en su flujo de efectivo. También proporcionan previsiones que pueden ayudarle a tomar decisiones mejores y por tanto mejorar el estado del flujo de efectivo. Puede analizar el efectivo por entidad jurídica, divisa y cuenta bancaria para obtener una mejor comprensión de los excesos y la escasez.

## <a name="setup-needed-to-view-power-bi-content"></a>Configuración necesaria para ver el contenido de Power BI

Es necesario completar la siguiente configuración para que los datos se muestren en los elementos visuales de Power BI **Visión general de efectivo** y **Gestión bancaria**.

1. Vaya a **Administración del sistema > Configuración > Parámetros del sistema** para establecer **Divisa del sistema** y **Tipo de cambio del sistema**.
2. Para validar las fechas del calendario fiscal asignadas al período de tiempo activo, vaya a **Contabilidad general > Calendarios > Calendarios fiscales**.
3. Vaya a **Contabilidad general > Configuración > Libro mayor** para establecer **Divisa de contabilidad** y **Tipo de cambio**.
4. Defina los tipos de cambio entre las divisas de transacción y la divisa de contabilidad, la divisa de contabilidad y la divisa del sistema, y la divisa de contabilidad y las divisas bancarias. Para ello, vaya a **Contabilidad general > Divisas > Tipos de cambio de divisas**.
5. Configurar y ejecutar Previsiones de flujo de efectivo. Para obtener más información sobre cómo configurar Previsiones de flujo de efectivo, consulte [Previsiones de flujo de efectivo](./cash-flow-forecasting.md). 
6. Vaya a **Administración del sistema > Configuración > Almacén de entidades** para actualizar la medida agregada **LedgerCovLiquidityMeasurement**.

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI

Los informes del contenido de Power BI **Visión general de efectivo** aparecen en las áreas de trabajo **Visión general de efectivo** y **Gestión bancaria**.

Para ver los informes de previsiones de flujo de efectivo con datos, debe primero ejecutar el proceso de cálculo de previsión con la función **Calcular previsiones de flujo de efectivo** del área de gestión de efectivo y bancos. Esto es necesario realizarlo para cada empresa incluida en la previsión.  Después, necesita actualizar la medida agregada LedgerCovLiquidityMeasurement en la página **Almacén de entidades**.  

Como demostración, puede agregar datos de demostración de previsiones de flujo de efectivo mediante la página **Generar datos** del módulo de datos de demostración.  Este script insertará datos en tablas de previsiones de flujo de efectivo para rellenar rápidamente la información necesaria para los informes.  Este módulo solo está disponible si tiene el modelo de la suite de datos de demostración implementado en el entorno. 

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Informes que se incluyen en el contenido de Power BI

La siguiente tabla ofrece información sobre las métricas que se encuentran en cada página de informe en el contenido de Power BI de **Visión general de efectivo**.

| Informe                                | Contenido |
|---------------------------------------|----------|
| Visión general del efectivo para todas las empresas         | <ul><li>Entradas y salidas en la divisa del sistema</li><li>Saldos de divisa previstos</li><li>Saldo bancario total en divisa del sistema</li><li>Saldo por entidad jurídica</li><li>Saldo real de hoy frente al saldo previsto en la divisa de la cuenta bancaria</li></ul> |
| Visión general del efectivo para la empresa actual       | <ul><li>Entradas y salidas en la divisa de contabilidad</li><li>Saldos de divisa previstos</li><li>Saldo bancario total en divisa de contabilidad</li><li>Saldo real de hoy frente al saldo previsto en la divisa de la cuenta bancaria</li></ul> |
| Visión general del efectivo para todas las empresas    | <ul><li>Entradas y salidas en la divisa del sistema</li><li>Resumen de previsiones diario</li><li>Detalles de previsión</li></ul> |
| Previsión de flujo de efectivo en divisa de la empresa | <ul><li>Entradas y salidas en la divisa de contabilidad</li><li>Resumen de previsiones diario</li><li>Detalles de previsión</li></ul> |
| Previsión actual                     | <ul><li>Saldos de divisa previstos</li><li>Resumen de divisa diario</li><li>Detalles de previsión</li></ul> |
| Saldos bancarios                         | <ul><li>Saldo bancario total en divisa del sistema</li><li>Saldo por entidad jurídica</li><li>Saldo real de hoy frente al saldo previsto en la divisa de la cuenta bancaria</li><li>Saldo por cuenta bancaria</li><li>Saldo por divisa</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades

En la tabla siguiente se muestran las entidades en las que se basaba el paquete de contenido de Power BI de **Visión general de efectivo**.

| Entidad                                                                          | Contenido |
|---------------------------------------------------------------------------------|----------|
| LedgerCovLiquidityMeasurement\_Company                                          | Empresas para filtrar informes por |
| LedgerCovLiquidityMeasurement\_Date                                             | Fechas para filtrar informes por |
| LedgerCovLiquidityMeasurement\_LedgerCovForecastActual                          | Saldo bancario real en comparación con el último saldo bancario previsto |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidity                               | Detalles de transacción previstos |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceCompany    | Entradas, salidas y saldo de efectivo resumidos mediante la divisa de contabilidad de cada empresa |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceEnterprise | Entradas, salidas y saldo de efectivo resumidos mediante la divisa del sistema para todas las empresas |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityTransactionCurrency            | Importe neto de la transacción y saldo de divisas resumidos mediante la divisa de transacción |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
