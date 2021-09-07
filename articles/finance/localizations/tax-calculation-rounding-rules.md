---
title: Reglas de redondeo de cálculo de impuestos
description: Este tema proporciona información sobre las reglas de redondeo en los parámetros de cálculo de impuestos del servicio de cálculo de impuestos.
author: kailiang
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 38760879d84d8262cc1e8395c59bcbc0429bc753
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "7347694"
---
# <a name="tax-calculation-rounding-rules"></a>Reglas de redondeo de cálculo de impuestos

[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre cómo funcionan las reglas de redondeo en los parámetros de cálculo de impuestos del servicio de cálculo de impuestos.

> [!NOTE] 
> Cuando el servicio de cálculo de impuestos está habilitado, las reglas de redondeo de las páginas **Código de impuesto sobre las ventas** y **Grupo de impuestos sobre las ventas** no son efectivas.

Puede ver la configuración de las reglas de redondeo para el servicio de cálculo de impuestos en la sección **Regla de redondeo de impuestos sobre las ventas** de la ficha desplegable **Cálculo** de la ficha **General** de la página **Parámetros de cálculo de impuestos** (**Impuesto**\> **Configuración**\> **Configuración de impuestos**\> **Parámetros de cálculo de impuestos**).

[![Configuración de la regla de redondeo en la página Parámetros de cálculo de impuestos](./media/tax-calculation-parameters-calculation-1.png)](./media/tax-calculation-parameters-calculation-1.png)

Los campos **Precisión de redondeo** y **Método de redondeo** determinan cómo se redondean los importes calculados en la carga útil del servicio de cálculo de impuestos.

## <a name="rounding-precision"></a>Precisión del redondeo

Los campos de **Precisión de redondeo** admiten un valor de hasta seis decimales. Por ejemplo, si configura el campo **Precisión de redondeo** con el valor **0.000000**, los importes calculados se redondean a seis decimales y luego se envían a Microsoft Dynamics 365 Finance. Por ejemplo, si se utiliza el método de redondeo **Normal**, la cantidad **987.1234567** se redondea a **987.123457**.

> [!NOTE]
> Finanzas redondea los importes de acuerdo con las reglas de redondeo de divisas. Por lo tanto, los importes de impuestos que se muestran y registran en las transacciones se ven afectados tanto por las reglas de redondeo de cálculo de impuestos como por las reglas de redondeo de divisas.

## <a name="rounding-method"></a>Método de redondeo

El método de redondeo para el cálculo de impuestos se puede configurar para cada entidad jurídica. En el campo **Método de redondeo**, puede seleccionar entre tres opciones: **Normal**, **A la baja** y **Redondeo al alza**.

### <a name="rounding-example"></a>Ejemplo de redondeo

La siguiente tabla proporciona un ejemplo que muestra cómo la cantidad **987.345** se redondea para diferentes combinaciones de precisiones de redondeo y métodos de redondeo.

<table>
<thead>
<tr>
<th rowspan="2">Método de redondeo</th>
<th colspan="8">Precisión del redondeo</th>
</tr>
<tr>
<th>0,00</th>
<th>0.01</th>
<th>0.10</th>
<th>1.00</th>
<th>10,00</th>
<th>0.02</th>
<th>0.05</th>
<th>0.25</th>
</tr>
</thead>
<tbody>
<tr>
<td>Normal</td>
<td>987.35</td>
<td>987.35</td>
<td>987.30</td>
<td>987.00</td>
<td>990.00</td>
<td>987.34</td>
<td>987.35</td>
<td>987.25</td>
</tr>
<tr>
<td>Hacia abajo</td>
<td>987.00</td>
<td>987.34</td>
<td>987.30</td>
<td>987.00</td>
<td>980.00</td>
<td>987.34</td>
<td>987.30</td>
<td>987.25</td>
</tr>
<tr>
<td>Redondeo por arriba</td>
<td>988.00</td>
<td>987.35</td>
<td>987.40</td>
<td>988.00</td>
<td>990.00</td>
<td>987.36</td>
<td>987.35</td>
<td>987.50</td>
</tr>
</tbody>
</table>

La lógica de cálculo y redondeo de los importes de impuestos se puede configurar de acuerdo con las reglas de impuestos.

## <a name="rounding-by"></a>Redondear por 

En el campo **Redondeo por**, seleccione el principio de redondeo que se aplica a los impuestos. Las siguientes opciones están disponibles:

- **Códigos de impuestos** - Redondea el importe del impuesto dentro de cada código impositivo.
- **Combinaciones de códigos de impuestos** - Redondea la el importe del impuesto dentro de la combinación de códigos de impuestos en la línea.

## <a name="calculation-method"></a>Método de cálculo

En el campo **Método de cálculo**, seleccione si los impuestos de las facturas se calculan para cada línea o para todas las líneas. Las siguientes opciones están disponibles:

- **Línea** – El importe del impuesto se calcula línea por línea. El importe del impuesto de cada línea no se ve afectado por el importe del impuesto de otras líneas.
- **Total** –  El importe del impuesto se calcula en todas las líneas de un documento.

### <a name="rounding-calculation-example"></a>Ejemplo de cálculo de redondeo

Este ejemplo muestra los diferentes cálculos que se pueden hacer para una factura, para diferentes combinaciones de valores de **Redondeo por** y **Método de cálculo**. Para este ejemplo, se ha implementado la siguiente configuración:

- La factura tiene cuatro líneas.
- Hay dos códigos de impuestos: **IVA1** (10 por ciento) e **IVA2** (10 por ciento).
- La precisión de redondeo se establece en **0.01**.
- El método de redondeo se establece en **Redondeo al alza**.

#### <a name="rounding-by--tax-codes-and-calculation-method--line"></a>Redondeo por = Códigos de impuestos y Método de cálculo = Línea

| Número de línea | Importe neto de línea | Códigos de impuestos determinados | Importe de impuestos antes del redondeo | Importe de impuesto redondeado |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | IVA1                 | 1.111                      | 1.12               |
| 2           | 22.22           | IVA1; IVA2           | 2.222; 2.222               | 2.23; 2.23         |
| 3           | 33.33           | IVA1                 | 3.333                      | 3.34               |
| 4           | 44.44           | IVA1; IVA2           | 4.444; 4;444               | 4.45; 4.45         |

#### <a name="rounding-by--tax-code-combinations-and-calculation-method--line"></a>Redondeo por = Combinaciones de códigos de impuestos y Método de cálculo = Línea

| Número de línea | Importe neto de línea | Códigos de impuestos determinados | Importe de impuestos antes del redondeo | Importe de impuesto redondeado |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | IVA1                 | 1.111                      | 1.12               |
| 2\*         | 22.22           | IVA1; IVA2           | 2.222; 2.222               | 2.23; 2.22         |
| 3           | 33.33           | IVA1                 | 3.333                      | 3.34               |
| 4\*\*       | 44.44           | IVA1; IVA2           | 4.444; 4;444               | 4.45; 4.44         |

\*Línea 2 = Redondear\[ 22.22 × (10 por ciento + 10 por ciento)\] = 2.23 + 2.22

\*\* Línea 4 = Redondear\[44.44 × (10 por ciento + 10 por ciento)\] = 4.45 + 4.44

#### <a name="rounding-by--tax-codes-and-calculation-method--total"></a>Redondeo por = Códigos de impuestos y Método de cálculo = Total

| Número de línea | Importe neto de línea | Códigos de impuestos determinados | Importe de impuestos antes del redondeo | Importe de impuesto redondeado |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | IVA1\*               | 1.111                      | 1.12               |
| 2           | 22.22           | IVA1\*; IVA2\*\*     | 2.222; 2.222               | 2.22; 2.23         |
| 3           | 33.33           | IVA1\*               | 3.333                      | 3.33               |
| 4           | 44.44           | IVA1\*; IVA2\*\*     | 4.444; 4;444               | 4.44; 4.44         |

\* IVA1 (Línea 1, Línea 2, Línea 3, Línea 4) = Redondear\[ (11.11 + 22.22 + 33.33 + 44.44) × 10 por ciento\] = 1.12 + 2.22 + 3.33 + 4.44

\*\* IVA2 (Línea 2, Línea 4) = Redondear\[ (22.22 + 44.44) × 10 por ciento\] = 2.23 + 4.44

#### <a name="rounding-by--tax-code-combinations-and-calculation-method--total"></a>Redondeo por = Combinaciones de códigos de impuestos y Método de cálculo = Total

| Número de línea | Importe neto de línea | Códigos de impuestos determinados | Importe de impuestos antes del redondeo | Importe de impuesto redondeado |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1\*         | 11.11           | IVA1                 | 1.111                      | 1.12               |
| 2\*\*       | 22.22           | IVA1; IVA2           | 2.222; 2.222               | 2.23; 2.22         |
| 3\*         | 33.33           | IVA1                 | 3.333                      | 3.33               |
| 4\*\*       | 44.44           | IVA1; IVA2           | 4.444; 4;444               | 4.44; 4.45         |

\* Línea 1, Línea 3 = Redondear\[(11.11 + 33.33) × 10 por ciento\] = 1.12 + 3.33

\*\* Línea 2, Línea 4 = Redondear\[ (22.22 + 44.44) × (10 por ciento + 10 por ciento)\] = 2.23 + 2.22 + 4.44 + 4.45

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
