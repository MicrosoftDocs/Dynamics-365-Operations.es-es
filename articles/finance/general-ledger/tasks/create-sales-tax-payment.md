---
title: Crear un pago de impuestos
description: El procedimiento de la tarea de liquidar y registrar impuestos liquida los saldos de impuestos de las cuentas de impuestos y los anota como contrapartida en la cuenta de liquidación de impuestos para un período determinado.
author: twheeloc
ms.date: 01/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c388a8f98cd4581abe2ec13d8922e232321e4039
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735942"
---
# <a name="create-a-sales-tax-payment"></a>Crear un pago de impuestos

[!include [banner](../../includes/banner.md)]

El procedimiento de la tarea de liquidar y registrar impuestos liquida los saldos de impuestos de las cuentas de impuestos, y los anota como contrapartida en la cuenta de liquidación de impuestos para un período determinado.

1. Vaya a **Impuestos > Declaraciones > Impuestos > Liquidar y registrar impuestos**.
2. En el campo **Período de liquidación**, seleccione el botón desplegable para abrir la búsqueda.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En el campo **Fecha inicial**, escriba una fecha. Si no selecciona la opción **Incluir correcciones** en la página **Parámetros de contabilidad general**, la liquidación se puede procesar para diferentes versiones. **Original** es la primera liquidación para un intervalo de períodos y se puede procesar solo una vez para un intervalo de períodos. Las últimas correcciones liquidarán las transacciones de impuestos que se hayan registrado después de crear la versión original.
5. En el campo **Fecha de transacción**, especifique una fecha.
6. Seleccione **Aceptar**. El informe **Pagos de impuestos** se imprime un informe para revisar las transacciones de impuestos liquidadas en el período.

A partir de la versión 10.0.24 de Finance, puede omitir el informe **Pagos de impuestos** que se genera directamente después de que se implante el procedimiento periódico **Liquidar y registrar impuestos** bajo la característica **Generación de informes de pago de impuestos independientes a partir de la liquidación de impuestos** del espacio de trabajo **Administración de características**.

Cuando la característica está habilitada, una vez que se completa el proceso de liquidación, no se imprime ningún informe de pago de impuestos. En su lugar, recibe el siguiente mensaje: "La liquidación de impuestos y el registro han finalizado. Se ha registrado el asiento "xxxx, m/d/yyyy"".

Todavía puede ejecutar manualmente el informe de pago de impuestos; para ello, vaya a **Impuesto** > **Consultas e informes** > **Consultas de impuestos** > **Pagos de impuestos**.

## <a name="performance-consideration"></a>Consideración de rendimiento

El procedimiento de pago del impuesto sobre las ventas puede tardar bastante en completarse. Los principales factores que afectan la ejecución del procedimiento son el número de facturas en el período de liquidación y el número de entradas que deben contabilizarse en el comprobante de liquidación del impuesto sobre las ventas. Para ayudar a mejorar el rendimiento, puede elegir omitir algunas funciones que no se requieren en su proceso.

### <a name="enable-the-sales-tax-payment-performance-improvement-feature"></a>Habilitar la función de mejora del rendimiento del pago de impuestos sobre las ventas

La característica **Mejora del rendimiento del pago de impuestos sobre las ventas** puede ayudar a mejorar el rendimiento del procedimiento de pago del impuesto sobre las ventas agregando, en una línea, el importe de la moneda contable y el importe de la moneda del informe en las líneas de comprobantes de pago del impuesto sobre las ventas que tienen la misma cuenta principal, dimensión del libro mayor y moneda.

1. Vaya a **Administración del sistema** \> **Espacios de trabajo** \> **Administración de características**.
2. En la pestaña **Todos**, busque y seleccione **Mejorar el rendimiento del pago de impuestos sobre las ventas**.
3. Seleccione **Habilitar**.

### <a name="prevent-generation-of-offset-tax-transactions"></a>Evitar la generación de transacciones de impuestos de contrapartida

De forma predeterminada, el comprobante de pago de impuestos sobre las ventas contabiliza transacciones de impuestos de contrapartida contra cada transacción de impuestos sobre las ventas que se liquida en el procedimiento de pago de impuestos sobre las ventas. Estas transacciones de impuestos de contrapartida se incluyen en el informe **Impuesto sobre las ventas/conciliación del libro mayor**. Muestran el saldo pendiente de las transacciones de impuestos que no se liquidan durante el período.

Sin embargo, las transacciones de impuestos de contrapartida pueden aumentar la carga sobre el procedimiento de pago del impuesto sobre las ventas. Por lo tanto, un paquete piloto que se llama **TaxReportGenOffsetTaxTransPerRecordSetFlighting** se puede activar bajo demanda. Esta distribución puede ayudar a mejorar el rendimiento de la generación de transacciones de impuestos de contrapartida para países y regiones excepto Tailandia, Polonia, Hungría, Lituania, Malasia, India, Italia, Rusia, República Checa, Estonia y Letonia.

> [!NOTE]
> Si hay campos personalizados en la tabla de transacciones de impuestos, no se puede activar la división en paquetes piloto.

Puesto que el informe **Impuesto sobre las ventas/conciliación del libro mayor** se usa generalmente solo para fines de control interno y no es obligatorio en muchos regímenes tributarios, puede optar por no generar transacciones de impuestos de contrapartida en el comprobante de pago de impuestos sobre las ventas.

1. Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos de ventas** \> **Períodos de liquidación de impuestos**.
2. Permite seleccionar un período de liquidación.
3. En la ficha desplegable **General**, establezca la opción **Evitar la generación de transacciones de impuestos de contrapartida** como **Sí**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
