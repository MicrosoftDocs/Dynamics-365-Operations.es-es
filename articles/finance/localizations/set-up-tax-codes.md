---
title: Configurar de códigos de impuestos
description: En este tema se explica cómo configurar códigos de impuestos en el servicio de cálculo de Impuestos.
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 8bdb194e7d8b704d1e58d3c25bf2e1f6bff1ba00
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883879"
---
# <a name="set-up-tax-codes"></a>Configurar de códigos de impuestos

[!include [banner](../includes/banner.md)]

En este tema se explica cómo configurar códigos de impuestos en el servicio de cálculo de Impuestos. Incluye la configuración de un escenario simple para hacer que el código de impuestos funcione e información sobre algunas funciones avanzadas del código de impuestos para escenarios complejos.

> [!IMPORTANT]
> La configuración de códigos de impuestos en el servicio de cálculo de impuestos es independiente de la entidad jurídica. Puede completar esta configuración en Regulatory Configuration Service (RCS) solo una vez. Los códigos de impuestos se sincronizan automáticamente con Microsoft Dynamics 365 Finance cuando se activa el servicio de cálculo de impuestos para una entidad jurídica seleccionada en Finanzas.

## <a name="simple-setup"></a>Configuración sencilla

Siga estos pasos para utilizar un código de impuestos en un escenario sencillo, como un escenario en el que solo hay un tipo impositivo.

1. Inicie sesión en [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).
2. Vaya a **Espacios de trabajo** \> **Características de globalización** \> **Cálculo de impuestos**.
3. Seleccione la característica y la versión que desee configurar y, a continuación, seleccione **Editar**.
4. En la pestaña **General**, seleccione **Versión de configuración**.
5. En la pestaña **Códigos de impuestos**, seleccione **Agregar** e introduzca el código de impuestos y una descripción.
6. Seleccione **Origen de cálculo**. Un origen de cálculo es un grupo de métodos que se definen en la versión de configuración de impuestos que ha seleccionado. Para este escenario sencillo, seleccione **Por importe neto**.
7. Seleccione **Guardar**. Hay más campos disponibles, según el origen de cálculo que haya seleccionado.
8. En la ficha desplegable **Tarifas**, seleccione **Agregar** para agregar una tasa impositiva para este código de impuestos.
9. Seleccione **Guardar**.

## <a name="calculation-origin"></a>Origen del cálculo

El origen del cálculo define cómo se calculan el importe de la base imponible y el importe del impuesto. Se configura mediante la configuración de impuestos en el espacio de trabajo **Informes electrónicos**. Los siguientes valores están disponibles en el campo **Origen de cálculo**:

- Por importe neto
- Por importe bruto
- Por cantidad
- Por margen
- Impuesto sobre impuesto

### <a name="by-net-amount"></a>Por importe neto

Si selecciona **Por importe neto** en el campo **Origen de cálculo**, el importe de impuestos se calcula como un porcentaje del importe de la compra o de la venta, excluyendo cualquier otro código de impuestos.

Por ejemplo, el tipo impositivo es del 25 por ciento, la línea de la factura muestra una cantidad de 10 artículos a 1,00 cada uno, y al cliente se le permite un descuento de línea del 10 por ciento. En ese caso, los importes se calculan de la siguiente manera:

- **Importe neto:** (10 × 1,00) – 10 por ciento = 9,00 
- **Impuesto sobre la venta:** 9,00 × 25 por ciento = 2,25 
- **Importe total de la factura:** 9,00 + 2,25 = 11,25

### <a name="by-gross-amount"></a>Por importe bruto

Si selecciona **Por importe bruto** en el campo **Origen de cálculo** el importe del impuesto se calcula como un porcentaje del importe bruto de las ventas. El importe bruto es el importe neto de la línea más todos los impuestos y tasas de la línea, excepto el impuesto en el que el campo **Origen de cálculo** está configurado en **Por importe bruto**.

Por ejemplo, la autoridad fiscal ha impuesto aranceles especiales sobre un artículo. Los importes de aranceles se agregan al importe neto antes de calcular los impuestos. Se usan los códigos de impuestos siguientes:

- **Arancel 1**: el tipo es del 10 por ciento y se utiliza el método de cálculo **Por importe neto**.
- **Arancel 2**: el tipo es del 20 por ciento y se utiliza el método de cálculo **Por importe neto**.
- **Índice de impuestos**: el tipo es del 25 por ciento y se utiliza el método de cálculo **Por importe bruto**.

Si el importe neto es de 10,00, el importe del arancel 1 es de 1,00 (10,00 × 10 por ciento), y el importe del arancel 2 es de 2,00 (10,00 × 20 por ciento). En ese caso, los importes se calculan de la siguiente manera: 

- **Importe bruto:** importe neto + importe de Arancel 1 + importe de Arancel 2 = 10,00 + 1,00 + 2,00 = 13,00 
- **Importe de impuesto:** 13,00 × 25 por ciento = 3,25 
- **Arancel e impuestos en total:** 1,00 + 2,00 + 3,25 = 6,25 
- **Importe total de la factura:** 10,00 + 6,25 = 16,25

### <a name="by-quantity"></a>Por cantidad

Si selecciona **Por cantidad** en el campo **Origen de cálculo**, el impuesto se calcula como un importe fijo por unidad y se multiplica por la cantidad que se introduce en la línea del documento. El importe por unidad se especifica en la ficha desplegable **Tasas**.

Por ejemplo, el código de impuestos está configurado como 1,20 por unidad. En una línea de factura de venta, se venden 25 unidades de un artículo. En este caso, el importe de impuestos se calcula como 25 × 1,20 = 30,00.

### <a name="by-margin"></a>Por margen

Si selecciona **Por margen** en el campo **Origen de cálculo** el importe del impuesto se calcula como un porcentaje del margen de ventas. El margen de ventas es el importe de las ventas menos el importe de los costes. Este método de cálculo se aplica solo a las transacciones de ventas.

Por ejemplo, el tipo impositivo es del 25 por ciento, la línea de la factura muestra una cantidad de 10 artículos a 10,00 cada uno, y el coste por artículo es 6. En ese caso, los importes se calculan de la siguiente manera:

- **Margen de ventas:** 10 × ( 10,00 – 6,00) = 40,00
- **Importe de impuesto:** 40,00 × 25 por ciento = 10,00
- **Importe total de la factura:** 100,00 + 10,00 = 110,00

### <a name="tax-on-tax"></a>Impuesto sobre impuesto

Si selecciona **Impuesto sobre impuesto** en el campo **Origen de cálculo**, el impuesto sobre las ventas se calcula como un porcentaje de todos los demás importes del impuesto en la misma línea del documento.

Por ejemplo, se utilizan los siguientes códigos de impuestos:

- **Arancel 1**: el tipo es del 10 por ciento y se utiliza el método de cálculo **Por importe neto**.
- **Arancel 2**: el tipo es del 20 por ciento y se utiliza el método de cálculo **Por importe neto**.
- **Impuesto sobre arancel**: el tipo es del 25 por ciento y se utiliza el método de cálculo **Impuesto sobre impuesto**.

En ese caso, los importes se calculan de la siguiente manera:

- **Importe neto:** 10,00 
- **Arancel 1:** 10,00 × 10 por ciento = 1,00 
- **Arancel 2:** 10,00 × 20 por ciento = 2,00 
- **Impuesto sobre arancel:** 3,00 × 25 por ciento = 0,75
- **Impuestos totales:** 1,00 + 2,00 + 0,75 = 3,75 
- **Importe total de la factura:** 10,00 + 3,75 = 13,75

## <a name="advanced-functionality"></a>Funcionalidad avanzada

En esta sección se explican algunas funcionalidades avanzadas de la configuración del código de impuestos para escenarios complejos.

### <a name="tax-exemption"></a>Exención de impuestos

Si establece la opción **Está exento** en **Sí** en la ficha desplegable **General**, el importe del impuesto siempre se anulará a 0 (cero), independientemente del tipo impositivo real.

Puede establecer el campo **Código de exención** para especificar el motivo de la exención. 

Puede activar la búsqueda de datos maestros para el campo **Código de exención**. De este modo, puede seleccionar entre los valores de códigos de exención que se definen en Finanzas. Para obtener información sobre cómo habilitar la búsqueda de datos maestros, consulte [Habilitar la búsqueda de datos maestros para la configuración del cálculo de impuestos](tax-service-set-up-environment-master-data-lookup.md).

Por ejemplo, la tasa impositiva es del 25 por ciento y la opción **Está exento** está configurada en **Sí** en el código de impuestos. La línea de factura muestra una cantidad de 10 artículos a 1,00 cada uno, y al cliente se le ofrece un descuento de línea del 10 por ciento. En ese caso, los importes se calculan de la siguiente manera:

- **Importe neto:** (10 × 1,00) – 10 por ciento = 9,00 
- **Impuestos:** 0,00 
- **Importe total de la factura:** 9,00 + 0,00 = 9,00

### <a name="use-tax"></a>IVA de importación

Si establece la opción **Es IVA de importación** en **Sí** en la ficha desplegable **General**, el importe del impuesto se contabilizará en la cuenta **IVA de importación repercutido** en lugar de la cuenta **Resumen de proveedor**.

Por ejemplo, la tasa impositiva es del 25 por ciento y la opción **Es IVA de importación** está configurada en **Sí** en el código de impuestos. La línea de factura muestra una cantidad de 10 artículos a 1,00 cada uno, y al cliente se le ofrece un descuento de línea del 10 por ciento. En ese caso, los importes se calculan de la siguiente manera:

- **Importe neto:** (10 × 1,00) – 10 por ciento = 9,00 
- **IVA de importación:** 9,00 × 25 por ciento = 2,25
- **Importe total de la factura:** 9,00 + 0,00 = 9,00

> [!IMPORTANT]
> Si se establecen las opciones **Está exento** y **Es IVA de importación** en **Sí** en un código de impuestos, el código se reconocerá como exento de impuestos para las transacciones de venta y de IVA de importación para las transacciones de compra.

### <a name="reverse-charges"></a>Cargos invertidos

Si establece la opción **Es cargo invertido** en **Sí** en la ficha desplegable **General**, el tipo impositivo se puede configurar como negativo. Para un escenario de cargo invertido, le recomendamos que configure dos códigos de impuestos: uno que tenga un tipo impositivo positivo y otro que tenga un tipo impositivo negativo. Ambos códigos de impuestos deben tener el mismo valor de tipo y la opción **Es cargo invertido** debe establecerse en **Sí** en el código de impuestos que tiene una tasa impositiva negativa. Para obtener más información sobre la solución de cargo invertido en Finance, consulte [Mecanismo de cargo invertido para esquema de IVA/GST](emea-reverse-charge.md).

Por ejemplo, se determinan dos códigos de impuestos en una línea de factura. Una tasa impositiva es del 25 por ciento. La otra tasa impositiva es del -25 por ciento y la opción **Es cargo invertido** se establece en **Sí** en el segundo código de impuestos. La línea de la factura muestra una cantidad de 10 artículos a 1,00 cada uno. En ese caso, los importes se calculan de la siguiente manera:

- **Importe neto:** (10 × 1,00) = 10,00 
- **Código de impuestos 1:** 10,00 × 25 por ciento = 2,50
- **Código de impuestos 2:** 10 × -25 por ciento = -2,50
- **Importe total de la factura:** 10,00 + 2,50 -2,50 = 10,00

### <a name="exclusion-from-base-amount-calculations"></a>Exclusión del cálculo del importe base

Si establece la opción **Excluir del cálculo del importe base** en **Sí** en la ficha desplegable **General**, el importe del impuesto calculado del indicador de impuestos se excluye de la base imponible para otros cálculos de indicadores de impuestos en el escenario de precio incluido.

Para obtener más información, consulte [Calcular los impuestos de los precios cuando está habilitado que los precios incluyen impuestos](global-exclude-from-tax-base-amount-calculation.md).

### <a name="rates"></a>Índices

En la ficha desplegable **Tipo**, puede definir diferentes tipos impositivos para diferentes rangos de importes de la base imponible. Para calcular el importe del impuesto, el servicio de Cálculo de Impuestos utiliza siempre el tipo que coincide con el importe de la base imponible.

Por ejemplo, las tasas impositivas pueden configurarse como se muestra en la siguiente tabla.

| Importe mínimo | Importe máximo | Índice de impuestos   |
| -------------- | -------------- | ---------- |
| 0              | 1.000          | Porcentaje 10 |
| 1.000          | 5,000          | Porcentaje 15 |
| 5,000          | 10,000         | Porcentaje 20 |
| 10,000         | 0              | Porcentaje 30 |

En ese caso, el importe del impuesto se calcula de la siguiente manera:

- Si el importe de la base imponible es de 300,00, el tipo impositivo es del 10 por ciento, y el importe del impuesto es de 300,00 × 10 por ciento = 30,00.
- Si el importe de la base imponible es de 3.000,00, el tipo impositivo es del 15 por ciento, y el importe del impuesto es de 3.000,00 × 15 por ciento = 450,00.
- Si el importe de la base imponible es de 6.000,00, el tipo impositivo es del 20 por ciento, y el importe del impuesto es de 6.000,00 × 10 por ciento = 1.200,00.
- Si el importe de la base imponible es de 20.000,00, el tipo impositivo es del 30 por ciento, y el importe del impuesto es de 20.000,00 × 30 por ciento = 6.000,00.

> [!NOTE]
> Si el importe de la base imponible puede coincidir tanto con el importe máximo de una línea como con el importe mínimo de la otra línea, la base utilizará el tipo impositivo que coincida con el importe mínimo de la base. Por ejemplo, si el importe de la base imponible es de 1000,00, el tipo impositivo es del 15 por ciento, y el importe del impuesto es de 1.000,00 × 15 por ciento = 150,00.

### <a name="limits"></a>Límites

En la ficha desplegable **Límites**, puede definir los límites de los impuestos para anular el importe de los impuestos calculado si el importe de los impuestos entra en el rango mínimo/máximo.

- Si el importe del impuesto calculado es superior o igual al importe del impuesto máximo configurado en la ficha desplegable **Límites**, el importe del impuesto final es igual al importe del impuesto máximo.
- Si el importe del impuesto calculado es inferior al importe del impuesto mínimo configurado en la ficha desplegable **Límites**, el importe del impuesto final es 0 (cero).

Por ejemplo, los límites de impuestos se configuran de la siguiente manera:

- **Importe mínimo del impuesto:** 100 
- **Importe máximo del impuesto:** 1.000

Si el importe del impuesto calculado es de 2.000, el importe final del impuesto es de 1.000.

Si el importe del impuesto calculado es de 500, el importe final del impuesto es de 500.

Si el importe del impuesto calculado es de 80, el importe final del impuesto es de 0 (cero).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
