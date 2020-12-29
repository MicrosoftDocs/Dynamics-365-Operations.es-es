---
title: Registrar depreciación de activo por derecho de uso (Vista previa)
description: Este tema explica cómo crear el asiento de diario para la amortización que se requiere para los arrendamientos que se reconocen en el balance de situación de una organización.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0dd8308acb875affc96ca6d9ed856d74d4b2eb37
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447797"
---
# <a name="record-right-of-use-asset-depreciation-preview"></a>Registrar depreciación de activo por derecho de uso (Vista previa)

[!include [banner](../includes/banner.md)]

Para los arrendamientos que se reconocen en el balance de situación de una organización, el activo por derecho de uso (ROU) se amortiza mensualmente. Este tema explica cómo crear el movimiento de diario para la amortización. La amortización debita la cuenta del libro mayor de gastos y acredita la cuenta del libro mayor de depreciación acumulada, según la configuración de su perfil de contabilización y el tipo de arrendamiento. Estas entradas se pueden crear para cada arrendamiento o se pueden crear para varios arrendamientos utilizando la funcionalidad de diario por lotes.

## <a name="asset-depreciation-schedule"></a>Programación de depreciación de activos

1. En la página **Resumen de arrendamientos**, seleccione un arrendamiento. Luego seleccione **Libros \> Programación de depreciación de activos** para abrir la página **Programación de depreciación de activos**.

    El movimiento de diario de gastos de depreciación de activos por derecho de uso se basa en el importe de la columna **Gasto de depreciación**. Para ver un ejemplo de la guía para el cumplimiento de estándares contables, consulte la sección [Cálculo del gasto de amortización de activos de ROU para arrendamientos financieros](#calculation-of-rou-asset-amortization-expense-for-finance-leases), más adelante en este tema.

2. Seleccione el período de depreciación y luego seleccione **Crear diario**. Recibe un mensaje que indica que se creó el diario que se utilizará para registrar la depreciación.
3. Seleccione **Diarios \> Diarios de arrendamiento de activos** para abrir la página **Diario de arrendamiento de activos**, donde puede ver el movimiento de diario de gastos de depreciación que se creó.
4. Seleccione la entrada del diario y luego seleccione **Registrar** para registrar el movimiento de depreciación en el Libro mayor.

## <a name="calculation-of-rou-asset-amortization-expense-for-operating-leases"></a>Cálculo del gasto de amortización de activos por derecho de uso para arrendamientos operativos

El gasto por depreciación de un arrendamiento operativo se calcula como la diferencia entre el gasto mensual por arrendamiento lineal y el gasto mensual por intereses sobre el pasivo por arrendamiento, de acuerdo con el Tema de Codificación de Normas Contables 842 (ASC 842), que es el estándar en Principios Contables Generalmente Aceptados en los EE. UU. (US GAAP). El gasto de arrendamiento lineal se calcula como la suma de todos los pagos por arrendamiento dividida por el plazo del arrendamiento en meses. (La suma de los pagos por arrendamiento incluye cualquier pago anticipado, costos directos iniciales, costos de desmantelamiento e incentivos de arrendamiento). La siguiente tabla muestra un ejemplo del gasto de amortización para un arrendamiento operativo.

### <a name="example-of-rou-asset-amortization-expense-for-operating-leases"></a>Ejemplo de gasto de amortización de activos por derecho de uso para arrendamientos operativos

| Campo                                          | Valor       |
|------------------------------------------------|-------------|
| Importe del pago                                 | 1.000       |
| Frecuencia de pago                              | Mensual     |
| Plazo del arrendamiento (meses)                            | 24          |
| Pagos totales de arrendamiento                           | 24,000      |
| Tipo de interés incremental del endeudamiento                     | 5%          |
| Tipo de anualidad                                   | Anualidad vencida |
| Intervalo de composición                           | Mensual     |
| Valor presente de los pagos mínimos de arrendamiento futuros | 22,888.87   |

Como se indicó anteriormente, el gasto de arrendamiento lineal se calcula como la suma de todos los pagos dividida por el plazo del arrendamiento. El sistema calcula automáticamente el gasto por intereses mensual en el programa de amortización del pasivo. El gasto por intereses se calcula utilizando el método de la tasa de interés efectiva. El sistema utilizará el coste de arrendamiento lineal para restar el gasto por intereses de cada mes. El valor se utiliza para reducir el activo por derecho de uso.

| Mes | Coste de arrendamiento lineal | Gastos de intereses                        | Cálculo del gasto de amortización de activos por derecho de uso |
|-------|--------------------------|-----------------------------------------|-----------------------------------------------|
| 1     | (24.000 ÷ 24) = 1.000,00 | (22.888,87 – 1.000) × (5 % ÷ 12) = 91,20 | 1.000 – 91,20 = 908,80                        |
| 2     | (24.000 ÷ 24) = 1.000,00 | (21.980,08 – 1.000) × (5 % ÷ 12) = 87,42 | 1.000 – 87,42 = 912,58                        |
| 3     | (24.000 ÷ 24) = 1.000,00 | (21.067,49 – 1.000) × (5 % ÷ 12) = 83,62 | 1.000 – 83,62 = 916,39                        |

> [!NOTE]
> De acuerdo con la ASC 842, la depreciación del activo por derecho de uso para un arrendamiento operativo se clasifica como un gasto de arrendamiento en el estado de resultados. Para mayor visibilidad, Arrendamiento de activos describe la entrada como la depreciación del activo por derecho de uso. Sin embargo, la entrada de débito debe asignarse a una cuenta de gastos de arrendamiento operativo, y la entrada de crédito debe asignarse directamente al activo por derecho de uso para el arrendamiento operativo. No obstante, en los parámetros de arrendamiento, puede especificar que las entradas de crédito se deban realizar en una cuenta de depreciación acumulada para activos por derecho de uso operativos.

## <a name="calculation-of-rou-asset-amortization-expense-for-finance-leases"></a>Cálculo del gasto de amortización de activos por derecho de uso para arrendamientos financieros

Para los arrendamientos que tienen clasificación financiera, el sistema calcula la amortización de activos por derecho de uso de forma lineal. Por lo tanto, el gasto por depreciación será el mismo para cada mes.

De acuerdo con la Norma Internacional de Información Financiera 16 (IFRS 16) y la ASC 842, el activo se amortizará durante el plazo del arrendamiento o la vida útil del activo, el que sea menor. Además, si el parámetro **Transferencia de propiedad** está activado para el arrendamiento, el arrendamiento se depreciará automáticamente durante la vida útil del activo.

### <a name="example-of-rou-asset-amortization-expense-for-finance-leases"></a>Ejemplo de gasto de amortización de activos por derecho de uso para arrendamientos financieros

| Campo                                | Valor                                   |
|--------------------------------------|-----------------------------------------|
| Saldo inicial de activos por derecho de uso | 22,889.87                               |
| Plazo del arrendamiento (meses)                  | 24                                      |
| Vida útil del activo (meses)           | 36                                      |
| Mes                                | Gasto de amortización de activos por derecho de uso |
| 1                                    | 22.889,87 ÷ 24 = 953,74                 |
| 2                                    | 22.889,87 ÷ 24 = 953,74                 |
| 3                                    | 22.889,87 ÷ 24 = 953,74                 |
