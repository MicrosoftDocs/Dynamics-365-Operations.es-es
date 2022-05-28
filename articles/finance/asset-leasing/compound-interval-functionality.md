---
title: Funcionalidad de intervalo de capitalización
description: Este tema proporciona información que le ayudará a elegir entre intervalos de capitalización mensuales, trimestrales, semestrales y anuales.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d1b8af3d5f8f6a6812fe309f57f682d0c5023d00
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8710453"
---
# <a name="compounding-interval-functionality"></a>Funcionalidad de intervalo de capitalización

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tema proporciona información que le ayudará a elegir entre intervalos de capitalización mensuales, trimestrales, semestrales y anuales. La función de intervalo de capitalización se utiliza para determinar el número de períodos de capitalización por año en la programación de pagos de un arrendamiento. Cada uno de los cuatro ejemplos de este tema muestra cómo se verá la programación de pagos de un arrendamiento para un intervalo diferente.

No puede seleccionar un intervalo de capitalización que sea menos frecuente que la frecuencia de pago del arrendamiento. Por ejemplo, un intervalo de capitalización trimestral no se puede usar con una frecuencia de pago mensual, y un intervalo de capitalización anual no se puede usar con una frecuencia de pago semestral. Si intenta seleccionar un intervalo de capitalización que sea menos frecuente que la frecuencia de pago del arrendamiento, recibirá un mensaje de error.

> [!NOTE]
> En los cuatro ejemplos de este tema, el intervalo de capitalización coincide con la frecuencia de pago.

## <a name="examples"></a>Ejemplo

### <a name="setup-for-all-four-leases"></a>Configuración para los cuatro arrendamientos

Las siguientes tablas muestran los valores que se establecen en las pestañas **General** y **Líneas de programación de pagos** para los cuatro arrendamientos que se utilizan en los ejemplos.

**Pestaña General**

| Campo                      | Valor                        |
|----------------------------|------------------------------|
| Tipo de interés incremental del endeudamiento | **5 %**                       |
| Tipo de anualidad               | **Anualidad ordinaria**         |
| Intervalo de composición       | Vea los ejemplos individuales. |
| Frecuencia de pago          | **Mensual**                  |
| Fecha de inicio          | **1/1/2020**                 |

**Pestaña Líneas de programación de pagos**

| Campo             | Valor                        |
|-------------------|------------------------------|
| Fecha inicial        | **1/1/2020**                 |
| Períodos           | **120**                      |
| Intervalo del período   | **Meses**                   |
| Fecha final          | **31/12/2029**               |
| Frecuencia de pago | Vea los ejemplos individuales. |
| Importe del pago    | **50,000**                   |

### <a name="lease-1-monthly-compounding-interval-and-monthly-payment-frequency"></a>Arrendamiento 1: intervalo de capitalización mensual y frecuencia de pago mensual

La siguiente tabla enumera los primeros 12 meses de la programación de pagos. Tenga en cuenta los siguientes detalles:

- El valor de la columna "Período" aumenta en 1 cada mes, porque cada mes es un nuevo intervalo de capitalización.
- En la fórmula de la columna "Valor presente", la tasa se divide por 12, porque hay 12 períodos de capitalización por año. El exponente (es decir, el superíndice) es igual al valor de la columna "Período".

| Periodo | Mes | Fecha       | Importe del pago | Valor actual                                       |
|--------|-------|------------|----------------|-----------------------------------------------------|
| 1      | 1     | 31/1/2020  | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 12\])<sup>1</sup> = 49.792,53  |
| 2      | 2     | 29/2/2020  | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 12\])<sup>2</sup> = 49.585,92  |
| 3      | 3     | 31/3/2020  | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 12\])<sup>3</sup> = 49.380,17  |
| 4      | 4     | 30/4/2020  | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 12\])<sup>4</sup> = 49.175,28  |
| 5      | 5     | 31/5/2020  | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 12\])<sup>5</sup> = 48.971,23  |
| 6      | 6     | 30/6/2020  | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 12\])<sup>6</sup> = 48.768,03  |
| 7      | 7     | 31/7/2020  | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 12\])<sup>7</sup> = 48.565,67  |
| 8      | 8     | 31/8/2020  | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 12\])<sup>8</sup> = 48.364,15  |
| 9      | 9     | 30/9/2020  | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 12\])<sup>9</sup> = 48.163,47  |
| 10     | 10    | 31/10/2020 | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 12\])<sup>10</sup> = 47.963,62 |
| 11     | 11    | 30/11/2020 | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 12\])<sup>11</sup> = 47.764,61 |
| 12     | 12    | 31/12/2020 | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 12\])<sup>12</sup> = 47.566,41 |

### <a name="lease-2-quarterly-compounding-interval-and-quarterly-payment-frequency"></a>Arrendamiento 2: intervalo de capitalización trimestral y frecuencia de pago trimestral

La siguiente tabla enumera los primeros 12 meses de la programación de pagos. Tenga en cuenta los siguientes detalles:

- El valor de la columna "Período" aumenta en 1 cada tres meses (o sea, cada trimestre), porque cada trimestre es un nuevo intervalo de capitalización.
- En la fórmula de la columna "Valor presente", la tasa se divide por 4, porque hay cuatro períodos de capitalización por año. El exponente es igual al valor de la columna "Período".

| Periodo | Mes | Fecha       | Importe del pago | Valor actual                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 31/1/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>1</sup> = 0           |
| 1      | 2     | 29/2/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>1</sup> = 0           |
| 1      | 3     | 31/3/2020  | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 4\])<sup>1</sup> = 49.382,72 |
| 2      | 4     | 30/4/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>2</sup> = 0           |
| 2      | 5     | 31/5/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>2</sup> = 0           |
| 2      | 6     | 30/6/2020  | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 4\])<sup>2</sup> = 48.773,05 |
| 3      | 7     | 31/7/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>3</sup> = 0           |
| 3      | 8     | 31/8/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>3</sup> = 0           |
| 3      | 9     | 30/9/2020  | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 4\])<sup>3</sup> = 48.170,92 |
| 4      | 10    | 31/10/2020 | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>4</sup> = 0           |
| 4      | 11    | 30/11/2020 | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 4\])<sup>4</sup> = 0           |
| 4      | 12    | 31/12/2020 | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 4\])<sup>4</sup> = 47.576,21 |

> [!NOTE]
> Si el tipo de anualidad se cambia a **Anualidad adeudada**, el pago se realizará al comienzo del trimestre en lugar de al final del trimestre.

### <a name="lease-3-semiannual-compounding-interval-and-semiannual-payment-frequency"></a>Arrendamiento 3: intervalo de capitalización semestral y frecuencia de pago semestral

La siguiente tabla enumera los primeros 12 meses de la programación de pagos. Tenga en cuenta los siguientes detalles:

- El valor de la columna "Período" aumenta en 1 cada seis meses (o sea, cada semestre), porque cada semestre es un nuevo intervalo de capitalización.
- En la fórmula de la columna "Valor presente", la tasa se divide por 2, porque hay cuatro dos períodos de capitalización por año. El exponente es igual al valor de la columna "Período".

| Periodo | Mes | Fecha       | Importe del pago | Valor actual                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 31/1/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>1</sup> = 0           |
| 1      | 2     | 29/2/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>1</sup> = 0           |
| 1      | 3     | 31/3/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>1</sup> = 0           |
| 1      | 4     | 30/4/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>1</sup> = 0           |
| 1      | 5     | 31/5/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>1</sup> = 0           |
| 1      | 6     | 30/6/2020  | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 2\])<sup>1</sup> = 48.780,49 |
| 2      | 7     | 31/7/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>2</sup> = 0           |
| 2      | 8     | 31/8/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>2</sup> = 0           |
| 2      | 9     | 30/9/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>2</sup> = 0           |
| 2      | 10    | 31/10/2020 | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>2</sup> = 0           |
| 2      | 11    | 30/11/2020 | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 2\])<sup>2</sup> = 0           |
| 2      | 12    | 31/12/2020 | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 2\])<sup>2</sup> = 47.590,72 |

> [!NOTE]
> Si el tipo de anualidad se cambia a **Anualidad adeudada**, el pago será en enero y julio en lugar de junio y diciembre.

### <a name="lease-4-annual-compounding-interval-and-annual-payment-frequency"></a>Arrendamiento 4: intervalo de capitalización anual y frecuencia de pago anual

La siguiente tabla enumera los primeros 12 meses de la programación de pagos. Tenga en cuenta los siguientes detalles:

- El valor de la columna "Período" aumenta en 1 cada 12 meses (o sea, anualmente), porque cada año es un nuevo intervalo de capitalización.
- En la fórmula de la columna "Valor presente", la tasa se divide por 1, porque hay un período de capitalización por año. El exponente es igual al valor de la columna "Período".

| Periodo | Mes | Fecha       | Importe del pago | Valor actual                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 31/1/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 2     | 29/2/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 3     | 31/3/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 4     | 30/4/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 5     | 31/5/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 6     | 30/6/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 7     | 31/7/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 8     | 31/8/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 9     | 30/9/2020  | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 10    | 31/10/2020 | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 11    | 30/11/2020 | 0,00           | 0,00 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 0           |
| 1      | 12    | 31/12/2020 | 50.000,00      | 50.000 ÷ (1 + \[5 % ÷ 1\])<sup>1</sup> = 47.619,05 |

> [!NOTE]
> Si el tipo de anualidad se cambia a **Anualidad adeudada**, el pago será en enero en lugar de en diciembre.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
