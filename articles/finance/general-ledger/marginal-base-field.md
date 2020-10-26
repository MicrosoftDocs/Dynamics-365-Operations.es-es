---
title: Índices de impuestos en función de la base marginal y los métodos de cálculo
description: Este tema explica cómo los valores de los campos Base marginal y Método de cálculo determinan los índices de impuestos en transacciones de compras y ventas.
author: ShylaThompson
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8617785ea969f9f4facaccdf81cfaf5344c30839
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975012"
---
# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a>Índices de impuestos en función de la base marginal y los métodos de cálculo

[!include [banner](../includes/banner.md)]

Este tema explica cómo los valores de los campos Base marginal y Método de cálculo determinan los índices de impuestos en transacciones de compras y ventas.

La base marginal en la ficha desplegable Cálculo de la página Códigos de impuestos determina qué importe usar para seleccionar las tasas de impuestos adecuadas para los índices en la página Valores de código de impuestos. El tipo de importe en el campo Base marginal, junto con el método del campo Método de cálculo, determinan la lógica para buscar las tasas de impuestos correctas para una transacción. 

Las distintas combinaciones de los valores de estos campos permiten obtener cálculos de impuestos muy diferentes, tal y como se muestra en los siguientes ejemplos. En estos ejemplos se utilizan los mismos valores de intervalo de impuestos, los cuales se configuran para cada código de impuestos en la página Valores de códigos de impuestos. Para abrir esta página, haga clic en Código de impuestos &gt; Valores en la página Códigos de impuestos.

> [!Important]                                                                                                                  
> Si la base marginal de uno o más de los códigos de impuestos se basa en unidades o importes de línea, el valor del campo Método de cálculo de la página Parámetros de contabilidad general se debe establecer en Línea. |

## <a name="net-amount-per-line"></a> Importe neto por línea
Seleccione esta opción para determinar las tasas de impuestos en base al importe neto de las líneas de la factura, sin incluir los demás impuestos.

### <a name="example"></a>ejemplo

Los índices de impuestos se configuran en los siguientes intervalos.

| Intervalo de importe    | Índice de impuestos |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

> [!NOTE]                                                                                                             
> El límite superior de cero (0) del último intervalo quiere decir que todos los importes superiores a 100 se incluyen en el intervalo.

Base marginal: **Importe neto por línea** 

Método de cálculo: **Intervalo** 

Supongamos que compra 8 lámparas que cuestan 25,00 cada una. 

El importe neto de la línea de factura es 200,00. 

El impuesto se calcula del modo siguiente: 

Importe total de impuestos = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = 35,00. 

Importe total de la factura = 200,00 + 35,00 = 235,00. 

**Variación** 

Si la factura tiene dos líneas de cuatro artículos en cada línea, el importe neto por línea es 100,00 y los impuestos se calculan del modo siguiente: 

Línea 1 de impuestos = 50 x 30% + 50 x 20% = 15 + 10 = 25,00. 

Línea 2 de impuestos = 50 x 30% + 50 x 20% = 15 + 10 = 25,00. 

Total de impuestos = 25,00 + 25,00 = 50,00 

Importe total de la factura = 200,00 + 50,00 = 250,00.

## <a name="net-amount-per-unit"></a> Importe neto por unidad
Seleccione esta opción para determinar las tasas de impuestos en base al valor de cada unidad, sin incluir los demás impuestos. Cuando se selecciona una base marginal basada en unidad, también se tiene que especificar una unidad para el código de impuestos.

### <a name="example"></a>Ejemplo

Los índices de impuestos se configuran en los siguientes intervalos.

| Importe             | Índice de impuestos |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Base marginal: **Importe neto por unidad** 

Método de cálculo: **Importe completo** 

Supongamos que compra 8 lámparas que cuestan 25,00 cada una. 

El importe neto de la línea de factura es 200,00. 

Los impuestos se calculan como sigue: Impuestos por unidad = 25,00 x 30% = 7,50 Impuestos totales = 7,50 x 8 unidades = 60,00 Importes de factura total = 200,00 + 60,00 = 260,00

## <a name="net-amount-of-invoice-balance"></a> Importe neto del saldo de la factura

Seleccione esta opción para determinar las tasas de impuestos en base al valor total de la factura, sin incluir los demás impuestos.

### <a name="example"></a>ejemplo

Los índices de impuestos se configuran en los siguientes intervalos.

| Importe            | Índice de impuestos |
|-------------------|----------|
| 0 - 50            | 30%      |
| 50 - 100          | 20%      |
| 100 -0 (&gt; 100) | 10%      |

Base marginal: **Importe neto del saldo de la factura** 

Método de cálculo: **Intervalo** Una factura de ventas tiene 2 líneas con 4 lámparas en cada línea de 25,00 cada una. El importe neto del saldo de la factura es 4 x 25,00 + 4 x 25,00 = 200,00. Los impuestos se calculan como sigue: Total de impuestos = 50 x 0,30 + 50 x 0,20 + 100 x 0,10 = 15 + 10 + 10 = 35,00 Importe total de factura = 200,00 + 35,00 = 235,00

## <a name="gross-amount-per-line"></a> Importe bruto por línea

Seleccione esta opción para determinar las tasas de impuestos en base al valor de la línea, incluidos los demás impuestos para esa línea.

> [!NOTE]
> En un grupo de impuestos, solo puede tener un código de impuestos con esta selección en el campo Base marginal.

### <a name="example"></a>Ejemplo

Los índices de impuestos se configuran en los siguientes intervalos.

| Importe             | Índice de impuestos |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Base marginal: **Importe bruto por línea** Método de cálculo: **Intervalo** Hay además otro código de impuestos calculado para un arancel especial de 5,00 en cada lámpara. Los aranceles se añaden al importe neto antes del cálculo de impuestos de ventas. Supongamos que compra 8 lámparas que cuestan 25,00 cada una. El importe neto de la línea de factura es 200,00. El importe bruto de la línea de factura es 8 x 25,00 + 8 x 5,00 = 240,00. Los impuestos se calculan como sigue: Impuestos totales = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 20 + 14 = 39,00 Arancel total = 5,00 x 8 = 40,00 Importe total de factura = 200,00 + 39,00 + 40,00 = 279,00

**Variación** 

Si la factura se crea con 2 líneas de de factura con 4 artículos en cada línea, el importe neto por línea de factura es 100,00 euros. El importe bruto (incluidos los aranceles 4 x 5,00) por línea de factura sería 120,00, y se crearían los impuestos como sigue: Factura de impuestos línea 1 = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Factura de impuestos línea 2 = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Impuestos totales = 27,00 + 27,00 = 54,00 Arancel total = 5,00 x 8 = 40,00 Importe total de factura = 200,00 + 54,00 + 40,00 = 294,00

## <a name="gross-amount-per-unit"></a> Importe bruto por unidad

Seleccione esta opción para determinar las tasas de impuestos en base al valor de la unidad, incluidos los demás impuestos.

> [!NOTE]
> En un grupo de impuestos, solo puede tener un código de impuestos con esta selección en el campo Base marginal.

### <a name="example"></a>Ejemplo

Los índices de impuestos se configuran en los siguientes intervalos.

| Importe             | Índice de impuestos |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Base marginal: **Importe bruto por unidad** Existen un arancel especial de 5,00 en cada lámpara. Los aranceles se añaden al importe neto antes del cálculo de impuestos de ventas. Supongamos que compra 8 lámparas que cuestan 25,00 cada una. El importe bruto por unidad es 30,00. Los impuestos se calculan como sigue: Impuestos por unidad = 30 x 30% = 9,00 Impuestos totales = 9,00 x 8 = 72,00 Arancel total = 5,00 x 8 = 40,00 Importe total de factura = 200,00 + 72,00 + 40,00 = 312,00

## <a name="invoice-total-incl-other-sales-tax-amounts"></a> Total de la factura incluidos otros impuestos

Seleccione esta opción para determinar las tasas de impuestos en base al valor total de la factura, incluidos los demás impuestos.
> [!NOTE]
> En un grupo de impuestos, solo puede tener un código de impuestos con esta selección en el campo Base marginal

### <a name="example"></a>Ejemplo

Los índices de impuestos se configuran en los siguientes intervalos.

| Importe             | Índice de impuestos |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Base marginal: **Total de factura incluidos otros importes de impuestos** Método de cálculo: **Intervalo**   
Existen unos aranceles especiales que gravan las lámparas de 5,00. Los aranceles se añaden al importe neto antes del cálculo de impuestos de ventas. Supongamos que compra 8 lámparas que cuestan 25,00 cada una. El importe neto de la factura es 200,00. El importe bruto de la factura es 200,00 + (8 x 5,00) = 240,00. Los impuestos se calculan como sigue: Impuestos totales = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 10 + 14 = 39,00 Arancel total = 5,00 x 8 = 40,00 Importe total de factura = 200,00 + 39,00 + 40,00 = 279,00

Para obtener más información, consulte [Importe completo y opciones de cálculo de intervalo para los códigos de impuestos](whole-amount-interval-options-sales-tax-codes.md) y [Métodos de cálculo de impuestos en el campo Origen](sales-tax-calculation-methods-origin-field.md).



