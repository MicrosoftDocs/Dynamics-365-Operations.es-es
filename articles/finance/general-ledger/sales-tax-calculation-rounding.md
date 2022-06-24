---
title: Redondeo y cálculo de impuestos
description: Este artículo proporciona una descripción general del cálculo y el redondeo del impuesto sobre las ventas y explica los parámetros del cálculo y la configuración del redondeo del impuesto sobre las ventas.
author: wangchen
ms.date: 06/01/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom:
- "13111"
- intro-internal
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2022-05-31
ms.dyn365.ops.version: AX 10.0.28
ms.openlocfilehash: aa3564f0fcf4a958637ba4a5cdcc497bffc50000
ms.sourcegitcommit: 8b716849707ec96d1cb4cac85b9e782dc25f5a70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2022
ms.locfileid: "8939244"
---
# <a name="sales-tax-calculation-and-rounding"></a>Redondeo y cálculo de impuestos

[!include [banner](../includes/banner.md)]

Este artículo proporciona una descripción general del cálculo y redondeo de impuestos sobre las ventas en Microsoft Dynamics 365 Finance. También explica los parámetros que se utilizan en la configuración para el cálculo y el redondeo de impuestos sobre las ventas, y cómo funcionan juntos esos parámetros.

## <a name="parameters"></a>Parámetros

Varios parámetros controlan el cálculo y el redondeo del impuesto sobre las ventas:

- **Método de cálculo**: este parámetro se configura en la página **Parámetros de contabilidad general** y define si el importe de la base imponible se calcula por documento o por línea. Si el parámetro **Base marginal** para el código de impuestos sobre las ventas se establece en **Importe neto del saldo de la factura**, el importe de la base imponible siempre se calcula por documento, independientemente de la configuración de este parámetro.
- **Redondear por**: este parámetro se establece para el grupo de impuestos sobre las ventas y define si el importe del impuesto se redondea por código de impuestos sobre las ventas o por combinación de códigos de impuestos sobre las ventas.
- **Origen**: este parámetro se establece para el código de impuestos sobre las ventas y define cómo se calcula el importe del impuesto. Para obtener más información, consulte [Métodos de cálculo de impuestos en el campo Origen](sales-tax-calculation-methods-origin-field.md).
- **Base marginal**: este parámetro se establece para el código de impuesto sobre las ventas y determina qué importe se usa para seleccionar las tasas de impuestos en la página **Valores de código de impuestos**. Para obtener más información, consulte [Impuestos basados en los métodos de Base marginal y Cálculo](marginal-base-field.md)
- **Regla de redondeo de impuestos sobre las ventas**: este parámetro se establece para el código de impuestos sobre las ventas y define cómo se redondea el importe del impuesto sobre las ventas determinado, incluida la precisión del redondeo y el método de redondeo.

El resto de este artículo presenta algunos ejemplos típicos de cálculo y redondeo de impuestos sobre las ventas que utilizan una combinación de los parámetros anteriores.

## <a name="scenario-for-the-examples"></a>Escenario para los ejemplos

- Hay dos líneas en el documento gravable, y el importe de la base imponible para cada línea es 42,42.
- Se definen dos códigos de impuestos sobre las ventas para cada línea: el código de impuestos sobre las ventas 1 y el código de impuestos sobre las ventas 2.
- La tasa impositiva del código fiscal 1 y el código fiscal 2 es del 10 por ciento.
- El precio excluye impuestos.
- La precisión de redondeo es de 0,01.
- El método de redondeo es **Redondeo al alza**.

## <a name="example-1"></a>Ejemplo 1

### <a name="parameter-values"></a>Valores de parámetro

| Método de cálculo | Redondear por    | Origen                   | Base marginal       |
| ------------------ | -------------- | ------------------------ | ------------------- |
| Línea               | Código de impuestos | Porcentaje del importe neto | Importe neto por línea |

### <a name="calculation-and-rounding-behavior"></a>Cálculo y comportamiento del redondeo

| Número de línea | Código de impuestos | Origen de importe | Importe de impuestos |
| ------------| ---------------| --------------| -----------------|
| 1           | Código 1         | 42.42         | 4.25             |
| 1           | Código 2         | 42.42         | 4.25             |
| 2           | Código 1         | 42.42         | 4.25             |
| 2           | Código 2         | 42.42         | 4.25             |

El importe base de impuestos se calcula por línea:

- **Línea 1:** 42,42
- **Línea 2:** 42,42

El importe de impuestos se calcula por código de impuesto de ventas:

- **Línea 1:**

    - El importe del impuesto para el código de impuesto sobre las ventas 1 = 42,42 &times; 10 por ciento = 4,242
    - El importe del impuesto para el código de impuesto sobre las ventas 2 = 42,42 &times; 10 por ciento = 4,242

- **Línea 2:**

    - El importe del impuesto para el código de impuesto sobre las ventas 1 = 42,42 &times; 10 por ciento = 4,242
    - El importe del impuesto para el código de impuesto sobre las ventas 2 = 42,42 &times; 10 por ciento = 4,242

El importe de impuestos se redondea por código de impuesto de ventas:

- **Línea 1:**

    - El importe de impuestos redondeado para el código de impuestos sobre las ventas 1 = 4,25
    - El importe de impuestos redondeado para el código de impuestos sobre las ventas 2 = 4,25

- **Línea 2:**

    - El importe de impuestos redondeado para el código de impuestos sobre las ventas 1 = 4,25
    - El importe de impuestos redondeado para el código de impuestos sobre las ventas 2 = 4,25

## <a name="example-2"></a>Ejemplo 2

### <a name="parameter-values"></a>Valores de parámetro

| Método de cálculo | Redondear por    | Origen                   | Base marginal                 |
| ------------------ | -------------- | ------------------------ | ----------------------------- |
| Línea/Total         | Código de impuestos | Porcentaje del importe neto | Importe neto del saldo de la factura |

### <a name="calculation-and-rounding-behavior"></a>Cálculo y comportamiento del redondeo

| Número de línea | Código de impuestos | Origen de importe | Importe de impuestos |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Código 1         | 42.42         | 4.25             |
| 1           | Código 2         | 42.42         | 4.25             |
| 2           | Código 1         | 42.42         | 4.24             |
| 2           | Código 2         | 42.42         | 4.24             |

El importe base de impuestos se calcula por documento:

- Importe de base fiscal = 42,42 + 42,42 = 84,84

El importe de impuestos se calcula por código de impuesto de ventas:

- El importe del impuesto para el código de impuesto sobre las ventas 1 = 84,84 &times; 10 por ciento = 8,484
- El importe del impuesto para el código de impuesto sobre las ventas 2 = 84,84 &times; 10 por ciento = 8,484

El importe de impuestos se redondea por código de impuesto de ventas:

- El importe de impuestos redondeado para el código de impuestos sobre las ventas 1 = 8,49
- El importe de impuestos redondeado para el código de impuestos sobre las ventas 2 = 8,49

El importe de impuestos redondeado se asigna a cada línea por código de impuestos sobre las ventas:

- Asigne el importe del impuesto redondeado para el código de impuestos sobre las ventas 1 (8,49) a la línea 1 (4,25) y la línea 2 (4,24).
- Asigne el importe del impuesto redondeado para el código de impuestos sobre las ventas 2 (8,49) a la línea 1 (4,25) y la línea 2 (4,24).

## <a name="example-3"></a>Ejemplo 3

### <a name="parameter-values"></a>Valores de parámetro

| Método de cálculo | Redondear por    | Origen                              | Base marginal       |
| ------------------ | -------------- | ----------------------------------- | ------------------- |
| Línea               | Código de impuestos | Porcentaje calculado del importe neto | Importe neto por línea |

### <a name="calculation-and-rounding-behavior"></a>Cálculo y comportamiento del redondeo

| Número de línea | Código de impuestos | Origen de importe | Importe de impuestos |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Código 1         | 42.42         | 4.72             |
| 1           | Código 2         | 42.42         | 4.72             |
| 2           | Código 1         | 42.42         | 4.72             |
| 2           | Código 2         | 42.42         | 4.72             |

El importe base de impuestos se calcula por línea:

- **Línea 1:** 42,42
- **Línea 2:** 42,42

El importe de impuestos se calcula por código de impuesto de ventas:

- **Línea 1:**

    - El importe del impuesto para el código de impuesto sobre las ventas 1 = 42,42 &times; 10 por ciento &divide; (1 - 10 por ciento) = 4,7133
    - El importe del impuesto para el código de impuesto sobre las ventas 2 = 42,42 &times; 10 por ciento &divide; (1 - 10 por ciento) = 4,7133

- **Línea 2:**

    - El importe del impuesto para el código de impuesto sobre las ventas 1 = 42,42 &times; 10 por ciento &divide; (1 - 10 por ciento) = 4,7133
    - El importe del impuesto para el código de impuesto sobre las ventas 2 = 42,42 &times; 10 por ciento &divide; (1 - 10 por ciento) = 4,7133

El importe de impuestos se redondea por código de impuesto de ventas:

- **Línea 1:**

    - El importe de impuestos redondeado para el código de impuestos sobre las ventas 1 = 4,72
    - El importe de impuestos redondeado para el código de impuestos sobre las ventas 2 = 4,72

- **Línea 2:**

    - El importe de impuestos redondeado para el código de impuestos sobre las ventas 1 = 4,72
    - El importe de impuestos redondeado para el código de impuestos sobre las ventas 2 = 4,72

## <a name="example-4"></a>Ejemplo 4

### <a name="parameter-values"></a>Valores de parámetro

| Método de cálculo | Redondear por    | Origen                              | Base marginal                 |
| ------------------ | -------------- | ----------------------------------- | ----------------------------- |
| Línea/Total         | Código de impuestos | Porcentaje calculado del importe neto | Importe neto del saldo de la factura |

### <a name="calculation-and-rounding-behavior"></a>Cálculo y comportamiento del redondeo

| Número de línea | Código de impuestos | Origen de importe | Importe de impuestos |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Código 1         | 42.42         | 4.72             |
| 1           | Código 2         | 42.42         | 4.72             |
| 2           | Código 1         | 42.42         | 4.71             |
| 2           | Código 2         | 42.42         | 4.71             |

El importe base de impuestos se calcula por documento:

- Importe de base fiscal = 42,42 + 42,42 = 84,84

El importe de impuestos se calcula por código de impuesto de ventas:

- El importe del impuesto para el código de impuesto sobre las ventas 1 = 84,84 &times; 10 por ciento &divide; (1 - 10 por ciento) = 9,4267
- El importe del impuesto para el código de impuesto sobre las ventas 2 = 84,84 &times; 10 por ciento &divide; (1 - 10 por ciento) = 9,4267

El importe de impuestos se redondea por código de impuesto de ventas:

- El importe de impuestos redondeado para el código de impuestos sobre las ventas 1 = 9,43
- El importe de impuestos redondeado para el código de impuestos sobre las ventas 2 = 9,43

El importe de impuestos redondeado se asigna a cada línea por código de impuestos sobre las ventas:

- Asigne el importe del impuesto para el código de impuestos sobre las ventas 1 (9,43) a la línea 1 (4,72) y la línea 2 (4,71).
- Asigne el importe del impuesto para el código de impuestos sobre las ventas 2 (9,43) a la línea 1 (4,72) y la línea 2 (4,71).

## <a name="example-5"></a>Ejemplo 5

### <a name="parameter-values"></a>Valores de parámetro

| Método de cálculo | Redondear por                | Origen                   | Base marginal       |
| ------------------ | -------------------------- | ------------------------ | ------------------- |
| Línea               | Combinación de códigos de impuestos | Porcentaje del importe neto | Importe neto por línea |

### <a name="calculation-and-rounding-behavior"></a>Cálculo y comportamiento del redondeo

| Número de línea | Código de impuestos | Origen de importe | Importe de impuestos |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Código 1         | 42.42         | 4.25             |
| 1           | Código 2         | 42.42         | 4.24             |
| 2           | Código 1         | 42.42         | 4.24             |
| 2           | Código 2         | 42.42         | 4.24             |

El importe base de impuestos se calcula por línea:

- **Línea 1:** 42,42
- **Línea 2:** 42,42

El importe de impuestos se calcula por código de impuesto de ventas:

- **Línea 1:**

    - El importe del impuesto para el código de impuesto sobre las ventas 1 = 42,42 &times; 10 por ciento = 4,242
    - El importe del impuesto para el código de impuesto sobre las ventas 2 = 42,42 &times; 10 por ciento = 4,242

- **Línea 2:**

    - El importe del impuesto para el código de impuesto sobre las ventas 1 = 42,42 &times; 10 por ciento = 4,242
    - El importe del impuesto para el código de impuesto sobre las ventas 2 = 42,42 &times; 10 por ciento = 4,242

El importe de impuestos se redondea por combinación de código de impuesto de ventas:

- Importe total del impuesto sobre las ventas = 4,242 + 4,242 + 4,242 + 4,242 = 16,968, que se redondea a 16,97

El importe de impuestos redondeado se asigna a cada línea por código de impuestos sobre las ventas:

- Asigne el importe del impuesto sobre las ventas (16,97) a la línea 1 y la línea 2:

    - **Línea 1:**

        - El importe de impuestos para el código de impuestos sobre las ventas 1 = 4,25
        - El importe de impuestos para el código de impuestos sobre las ventas 2 = 4,24

    - **Línea 2:**

        - El importe de impuestos para el código de impuestos sobre las ventas 1 = 4,24
        - El importe de impuestos para el código de impuestos sobre las ventas 2 = 4,24

## <a name="example-6"></a>Ejemplo 6

### <a name="parameter-values"></a>Valores de parámetro

| Método de cálculo | Redondear por                | Origen                   | Base marginal                 |
| ------------------ | -------------------------- | ------------------------ | ----------------------------- |
| Línea/Total         | Combinación de códigos de impuestos | Porcentaje del importe neto | Importe neto del saldo de la factura |

### <a name="calculation-and-rounding-behavior"></a>Cálculo y comportamiento del redondeo

| Número de línea | Código de impuestos | Origen de importe | Importe de impuestos |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Código 1         | 42.42         | 4.25             |
| 1           | Código 2         | 42.42         | 4.24             |
| 2           | Código 1         | 42.42         | 4.24             |
| 2           | Código 2         | 42.42         | 4.24             |

El importe base de impuestos se calcula por documento:

- Importe de base fiscal = 42,42 + 42,42 = 84,84

El importe de impuestos se calcula por código de impuesto de ventas:

- El importe del impuesto para el código de impuesto sobre las ventas 1 = 84,84 &times; 10 por ciento = 8,484
- El importe del impuesto para el código de impuesto sobre las ventas 2 = 84,84 &times; 10 por ciento = 8,484

El importe de impuestos se redondea por combinación de código de impuesto de ventas:

- Importe total del impuesto sobre las ventas = 8,484 + 8484 = 16,968, que se redondea a 16,97

El importe de impuestos redondeado se asigna a cada línea por código de impuestos sobre las ventas:

- Asigne el importe del impuesto sobre las ventas (16,97) a la línea 1 y la línea 2:

    - **Línea 1:**

        - El importe de impuestos para el código de impuestos sobre las ventas 1 = 4,25
        - El importe de impuestos para el código de impuestos sobre las ventas 2 = 4,24

    - **Línea 2:**

        - El importe de impuestos para el código de impuestos sobre las ventas 1 = 4,24
        - El importe de impuestos para el código de impuestos sobre las ventas 2 = 4,24

## <a name="example-7"></a>Ejemplo 7

### <a name="parameter-values"></a>Valores de parámetro

| Método de cálculo | Redondear por                | Origen                              | Base marginal       |
| ------------------ | -------------------------- | ----------------------------------- | ------------------- |
| Línea               | Combinación de códigos de impuestos | Porcentaje calculado del importe neto | Importe neto por línea |

### <a name="calculation-and-rounding-behavior"></a>Cálculo y comportamiento del redondeo

| Número de línea | Código de impuestos | Origen de importe | Importe de impuestos |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Código 1         | 42.42         | 4.72             |
| 1           | Código 2         | 42.42         | 4.71             |
| 2           | Código 1         | 42.42         | 4.71             |
| 2           | Código 2         | 42.42         | 4.72             |

El importe base de impuestos se calcula por línea:

- **Línea 1:** 42,42
- **Línea 2:** 42,42

El importe de impuestos se calcula por código de impuesto de ventas:

- **Línea 1:**

    - El importe del impuesto para el código de impuesto sobre las ventas 1 = 42,42 &times; 10 por ciento &divide; (1 - 10 por ciento) = 4,7133
    - El importe del impuesto para el código de impuesto sobre las ventas 2 = 42,42 &times; 10 por ciento &divide; (1 - 10 por ciento) = 4,7133

- **Línea 2:**

    - El importe del impuesto para el código de impuesto sobre las ventas 1 = 42,42 &times; 10 por ciento &divide; (1 - 10 por ciento) = 4,7133
    - El importe del impuesto para el código de impuesto sobre las ventas 2 = 42,42 &times; 10 por ciento &divide; (1 - 10 por ciento) = 4,7133

El importe de impuestos se redondea por combinación de código de impuesto de ventas:

- Importe total del impuesto sobre las ventas = 4,7133 + 4,7133 + 4,7133 + 4,7133 = 18,8532, que se redondea a 18,86

El importe de impuestos redondeado se asigna a cada línea por código de impuestos sobre las ventas:

- Asigne el importe del impuesto sobre las ventas (18,86) a la línea 1 y la línea 2:

    - **Línea 1:**

        - El importe de impuestos para el código de impuestos sobre las ventas 1 = 4,72
        - El importe de impuestos para el código de impuestos sobre las ventas 2 = 4,71

    - **Línea 2:**

        - El importe de impuestos para el código de impuestos sobre las ventas 1 = 4,71
        - El importe de impuestos para el código de impuestos sobre las ventas 2 = 4,72

## <a name="example-8"></a>Ejemplo 8

### <a name="parameter-values"></a>Valores de parámetro

| Método de cálculo | Redondear por                | Origen                              | Base marginal                 |
| ------------------ | -------------------------- | ----------------------------------- | ----------------------------- |
| Línea/Total         | Combinación de códigos de impuestos | Porcentaje calculado del importe neto | Importe neto del saldo de la factura |

### <a name="calculation-and-rounding-behavior"></a>Cálculo y comportamiento del redondeo

| Número de línea | Código de impuestos | Origen de importe | Importe de impuestos |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Código 1         | 42.42         | 4.72             |
| 1           | Código 2         | 42.42         | 4.71             |
| 2           | Código 1         | 42.42         | 4.71             |
| 2           | Código 2         | 42.42         | 4.72             |

El importe base de impuestos se calcula por documento:

- Importe de base fiscal = 42,42 + 42,42 = 84,84

El importe de impuestos se calcula por código de impuesto de ventas:

- El importe del impuesto para el código de impuesto sobre las ventas 1 = 84,84 &times; 10 por ciento &divide; (1 - 10 por ciento) = 9,4267
- El importe del impuesto para el código de impuesto sobre las ventas 2 = 84,84 &times; 10 por ciento &divide; (1 - 10 por ciento) = 9,4267

El importe de impuestos se redondea por combinación de código de impuesto de ventas:

- Importe total del impuesto sobre las ventas = 9,4267 + 9,4267 = 18,8534, que se redondea a 18,86

El importe de impuestos redondeado se asigna a cada línea por código de impuestos sobre las ventas:

- Asigne el importe del impuesto sobre las ventas (18,86) a la línea 1 y la línea 2:

    - **Línea 1:**

        - El importe de impuestos para el código de impuestos sobre las ventas 1 = 4,72
        - El importe de impuestos para el código de impuestos sobre las ventas 2 = 4,71

    - **Línea 2:**

        - El importe de impuestos para el código de impuestos sobre las ventas 1 = 4,71
        - El importe de impuestos para el código de impuestos sobre las ventas 2 = 4,72

## <a name="additional-resources"></a>Recursos adicionales

- [Métodos de cálculo de impuestos en el campo Origen](sales-tax-calculation-methods-origin-field.md)
- [Índices de impuestos en función de la base marginal y los métodos de cálculo](marginal-base-field.md)
- [Importe completo y opciones de cálculo de Intervalo para los códigos de impuestos](whole-amount-interval-options-sales-tax-codes.md)
