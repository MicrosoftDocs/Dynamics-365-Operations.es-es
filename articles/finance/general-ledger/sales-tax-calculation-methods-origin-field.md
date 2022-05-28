---
title: Métodos de cálculo de impuestos en el campo Origen
description: Este artículo explica las opciones del campo Origen en la página de códigos de impuestos y cómo se calculan los impuestos en función de la opción seleccionada para un código de impuestos.
author: kailiang
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 04d600d00425f03d0ecc7897055849541d50883c
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724710"
---
# <a name="sales-tax-calculation-methods-in-the-origin-field"></a>Métodos de cálculo de impuestos en el campo Origen

[!include [banner](../includes/banner.md)]

Este artículo explica las opciones del campo Origen en la página de códigos de impuestos y cómo se calculan los impuestos en función de la opción seleccionada para un código de impuestos.

Para cada código de impuestos que cree en la página de códigos de impuestos, debe seleccionar el método de cálculo que se aplica al importe base del impuesto en el campo Origen.

## <a name="percentage-of-net-amount"></a>Porcentaje del importe neto
El método de cálculo de porcentaje del importe neto es el valor predeterminado del campo Origen. Los impuestos se calculan como un porcentaje del importe de compra o de venta, sin incluir otros impuestos.
### <a name="example"></a>Ejemplo

El índice de impuestos es 25%. La línea de factura muestra una cantidad de 10 artículos a 1,00 cada uno, y al cliente se le ofrece un descuento de línea del 10%. Importe neto: (10 x 1,00) - 10% = 9,00 Impuestos: 9,00 x 25 % = 2,25 Importe total: 9,00 + 2,25 = 11,25

## <a name="percentage-of-gross-amount"></a> Porcentaje del importe bruto
Si selecciona el método de porcentaje del importe bruto, los impuestos se calculan como un porcentaje del importe bruto. El importe bruto es el importe neto de línea más todos los impuestos y las cuotas para la línea, excepto impuestos con origen = porcentaje del importe bruto.
### <a name="example"></a>Ejemplo

La autoridad fiscal ha impuesto aranceles especiales sobre un artículo. Los importes de aranceles se agregan al importe neto antes de calcular los impuestos. Dados los códigos de impuestos siguientes:
-   ARANCEL 1 = 10 %, con el método de cálculo de porcentaje del importe neto
-   ARANCEL 2 = 20 %, con el método de cálculo de porcentaje del importe neto
-   IMPUESTOS = 25 %, con el método de cálculo de porcentaje del importe bruto

Si el importe neto es 10,00, entonces ARANCEL 1 es 1,00 (10,00 x 10 %) y ARANCEL 2 = 2,00 (10,00 x 20 %). Los importes serían los siguientes: Importe bruto: Importe neto + Importe ARANCEL 1 + Importe ARANCEL 2 (10,00 + 1,00 + 2,00) = 13,00 IMPUESTOS = 13,00 x 25 % = 3,25 Total de ARANCELES e IMPUESTOS: 1,00 + 2,00 + 3,25 = 6,25 Importe total: 10,00 + 6,25 = 16,25

| **Nota**                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Solo un código de impuestos con origen = el porcentaje del importe bruto se puede usar para una transacción. Si se determina más de un código de impuesto de este tipo para una transacción, se mostrará un error acerca de que los impuestos no se pueden calcular. |


## <a name="percentage-of-sales-tax"></a>Porcentaje de impuestos

Al seleccionar Porcentaje de impuestos en el campo Origen, los impuestos se calculan como un porcentaje de los impuestos seleccionados en el campo Impuestos sobre impuestos. Los impuestos seleccionados en el campo Impuestos sobre impuestos se calculan en primer lugar. Los segundos impuestos se calculan a continuación en función del primer importe de impuestos.
### <a name="example"></a>Ejemplo

Dados los códigos de impuestos siguientes:
-   ARANCEL 1 = 10 %, con el método de porcentaje del importe neto
-   ARANCEL 2 = 20 %, con el método de porcentaje de impuestos, con Arancel 1 en el campo Impuestos sobre impuestos
-   IMPUESTOS = 25 %, con el método de porcentaje del importe bruto

Importe neto: 10,00 ARANCEL 1: 10,00 x 10 % = 1,00 ARANCEL 2: 1,00 x 20 % = 0,20 Importe bruto: 10,00 + 1,00 + 0,20 = 11,20 IMPUESTOS: 11,20 x 25 % = 2,80 Total de ARANCELES e IMPUESTOS: 1,00 + 0,20 + 2,80 = 4,00 Importe total: 10,00 + 4,00 = 14,00

| **Nota**                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Los impuestos de varios niveles en los cálculos de los impuestos no son posibles. Los impuestos no se pueden calcular sobre un impuesto que ya se ha calculado sobre otro impuesto. Los impuestos de un único nivel dentro de códigos de impuestos se pueden calcular en una transacción. |

## <a name="amount-per-unit"></a> Importe por unidad
Cuando selecciona Importe por unidad en el campo Origen, los impuestos se calculan como un importe fijo por unidad multiplicado por la cantidad especificada en la línea del documento. Tiene que seleccionar una unidad en el campo Unidad. El importe por unidad se especifica en la página de valores de código de impuestos.
### <a name="example"></a>Ejemplo

El código de impuestos se configura como: 1,20 dólares por unidad = cuadro En una línea de factura de venta se venden 25 cajas de un artículo Los impuestos se calculan como 25 x 1,20 = 30,00

| **Nota**                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Si la transacción se ha especificado en otra unidad distinta de la unidad especificada en el código de impuestos, se convierte automáticamente en función de las conversiones de unidades que se configuran en la página de conversiones de unidades. |

###  <a name="amount-per-unit-additional-option"></a> Importe por unidad, opción adicional

En la ficha Cálculo, puede seleccionar si un impuesto calculado por importe de unidad se calcula antes que otros códigos de impuestos y se suma al importe neto antes de calcular otros códigos de impuestos con Origen = Porcentaje del importe neto.

### <a name="examples"></a>Ejemplo

Supongamos que calculamos 2 códigos de impuestos en una transacción:

-   ARANCEL: Origen = Importe por unidad e impuestos, el valor se establece en 5,00 por unidad = uds
-   IMPUESTOS: Origen = tal y como se muestra en los ejemplos siguientes, el valor se establece en 25 %

Vendemos 1 unidad de un artículo a un precio unitario de 10,00
#### <a name="example-1"></a>Ejemplo 1

IMPUESTOS: Origen = médodo de porcentaje del importe bruto El cálculo anterior a la opción de impuestos no tiene efecto, ya que IMPUESTOS se calcula como porcentaje del importe bruto. ARANCEL: 1 x 5,00 = 5,00 Importe bruto: 10,00 + 5,00 = 15,00 IMPUESTOS: 15,00 x 25 % = 3,75 Total de impuestos: 5,00 + 3,75 = 8,75 Importe total: 10,00 + 8,75 = 18,75

#### <a name="example-2"></a>Ejemplo 2

IMPUESTOS: Origen = Porcentaje del importe neto El cálculo anterior a la opción de impuestos no se selecciona para el cálculo del ARANCEL. Importe neto: 10,00 ARANCEL: 1 x 5,00 = 5,00 IMPUESTOS: 10,00 x 25 % = 2,50 Total de impuestos: 5,00 + 2,50 = 7,50 Importe total: 10,00 + 7,50 = 17,50

#### <a name="example-3"></a>Ejemplo 3

IMPUESTOS: Origen = Porcentaje del importe neto El cálculo anterior a la opción de impuestos se selecciona para el cálculo del ARANCEL. Importe neto: 10,00 ARANCEL: 1 x 5,00 = 5,00 IMPUESTOS: (10,00 + 5,00) x 25 % = 3,75 Total de impuestos: 5,00 + 3,75 = 8,75 Importe total: 10,00 + 8,75 = 18,75

#### <a name="example-4"></a>Ejemplo 4

El resultado del ejemplo 3 y el ejemplo 1 es el mismo, ya que sólo hay un arancel. Suponga que tiene dos ARANCELES y solo uno de ellos se incluye en el importe neto para el cálculo de impuestos: ARANCEL 1: 5,00, con el método de importe por unidad y se selecciona la opción Calcular antes de impuestos ARANCEL 2: 2,50, con el método de importe por unidad y no se selecciona la opción Calcular antes de impuestos Impuestos: el 25 %, con el método de porcentaje del importe neto Importe neto: 10,00 ARANCEL 1: 1 x 5,00 = 5,00 ARANCEL 2: 1 x 2,50 = 2,50 Importe neto sujeto a impuestos: 10,00 + 5,00 = 15,00 IMPUESTOS: 15,00 x 25 % = 3,75 Total de impuestos, incluidos los aranceles: 5,00 + 2,50 + 3,75 = 11,25 Importe total: 10,00 + 11,25 = 21,25 Se calcula el 25 % de IMPUESTOS para la suma del importe neto (10,00) + el ARANCEL 1 (5,00) = 15,00. El ARANCEL 2 se agrega al importe del impuesto tras calcular el impuesto.

## <a name="calculated-percentage-of-net-amount"></a> Porcentaje calculado del importe neto
El porcentaje calculado del importe neto maneja el cálculo del impuesto de manera diferente en función de la configuración del parámetro Importe impuestos incluidos para el documento o el diario.
### <a name="example-1"></a>Ejemplo 1

El documento o el diario se establecen en Importe impuestos incluidos = Sí Importe de la línea de transacción: 10,00 Índice de impuestos: 25% Impuestos: Importe de la línea de transacción x índice de impuestos (10,00 x 25 %) = 2,50 Importe base impuestos (importe de origen): Importe de la línea de transacción - impuestos (10,00 - 2,50) = 7,50

### <a name="example-2"></a>Ejemplo 2

El documento o el diario se establecen en Importe impuestos incluidos = No Importe de la línea de transacción: 10,00 Índice de impuestos: 25% Impuestos: (Importe de la línea de transacción x índice de impuestos) / (100 - índice de impuestos) (10,00 x 25 %) / (100 % - 25 %) = 3,33 Importe base impuestos (importe de origen): Importe de la línea de transacción = 10,00



## <a name="additional-resources"></a>Recursos adicionales

[Índices de impuestos en función de la base marginal y los métodos de cálculo](marginal-base-field.md)

[Importe completo y opciones de cálculo de Intervalo para los códigos de impuestos](whole-amount-interval-options-sales-tax-codes.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
