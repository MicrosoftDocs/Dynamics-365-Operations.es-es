---
title: Solicitud de liquidación de contabilidad
description: Este artículo describe la ventana de consulta de liquidación del libro mayor
author: kweekley
ms.date: 12/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33ae49d9503c0a83bda7e0093ab6ef69fb4aef0a
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853145"
---
# <a name="ledger-settlement-inquiry"></a>Solicitud de liquidación de contabilidad

[!include [banner](../includes/banner.md)]

Este artículo describe la ventana **Consulta de liquidación del libro mayor** que se puede usar para ver las transacciones del libro mayor liquidadas, no liquidadas o liquidadas y no liquidadas para un período fiscal.

## <a name="view-ledger-settlement-transactions"></a>Ver transacciones sobre la liquidación contable
1.  Vaya a **Contabilidad general > Consultas e informes > Contulta de liquidación contable**.
2.  Utilice los campos **Desde la fecha** y **Hasta la fecha** o el campo **Intervalo de fechas** para especificar un intervalo de fechas. En cuanto al balance de comprobación, el rango de fechas debe estar dentro de un solo año fiscal.
3.  En el campo **Cuentas principales**, seleccione una o más cuentas principales para ver las transacciones del libro mayor. La lista desplegable muestra solo las cuentas principales que están configuradas para la liquidación del libro mayor en la página **Parámetros del libro mayor**.
4.  Utilice el campo **Conjunto de dimensiones financieras** para mostrar las dimensiones financieras en la cuadrícula. Debido a que se requiere la cuenta principal, el valor del campo **Cuenta principal** siempre se mostrará como la primera columna, incluso si selecciona un conjunto de dimensiones financieras que no incluye la cuenta principal.
5.  En el campo **Estado**, seleccione:
-   **Todo** para ver las transacciones liquidadas y no liquidadas
-   **Sin liquidar** para ver solo las transacciones no liquidadas 
-   **Liquidadas** para ver solo las transacciones liquidadas
6.  Seleccione **Mostrar transacciones**. Las transacciones contables aparecen en la cuadrícula, según los criterios que ingresó. Puede exportar los resultados de la consulta a Microsoft Excel pra un análisis adicional. Seleccione y mantenga pulsado (o haga clic con el botón derecho en) la cuadrícula.

### <a name="column-details"></a>Detalles de columna
La cuadrícula de la página **Consulta de liquidación del libro mayor** incluye las siguientes columnas:
-   **Cuenta principal**: este campo es obligatorio y siempre se muestra.
-   **Dimensiones financieras**: las dimensiones financieras se muestran en función del conjunto de dimensiones financieras seleccionado.
-   **Fecha de transacción** - La fecha de registro de la transacción contable.
-   **Fecha de transacción original**: si se ejecutó el cierre de fin de año y se configuró la liquidación del libro mayor para que conserve los detalles de una cuenta principal, las transacciones no liquidadas se traen en detalle como un saldo de apertura. La fecha de registro original de la transacción del libro mayor se mantiene en el campo **Fecha de la transacción original**.
-   **Tiempo de transacción**: el valor es 0 (cero) para todas las transacciones liquidadas. Para las transacciones no liquidadas, el valor se calcula como el número de días desde la fecha de la transacción original o la fecha de la transacción hasta la fecha en que se ejecuta la consulta.
Por ejemplo, una transacción del libro mayor tiene una fecha de transacción del 1 de enero de 2022 (1/1/2022) y una fecha de transacción original del 30 de diciembre de 2021 (30/12/2021). Si la consulta se ejecuta el 2 de enero de 2022 (1/2/2022) para el año fiscal 2022, el **valor de antigüedad de la transacción** será 4. Este valor se calcula como el número de días entre la fecha de la transacción original (30/12/2021) y el 2/1/2022.

Si no hay una fecha de transacción original, se utiliza la fecha de transacción en su lugar.
-   **(Otra información transaccional)**: las columnas adicionales muestran información como el número de comprobante, la descripción y los montos de débito y crédito en las tres monedas (transacción, contabilidad e informes).
-   **Estado**: este valor es **Liquidado** o **No liquidado**.
-   **Id. de liquidación**: el identificador asignado a las transacciones liquidadas.

[![Página de consulta de liquidación de contabilidad](./media/Inquiry1.png)](./media/Inquiry1.png)

 
Los totales se pueden mostrar debajo de la cuadrícula.
1.  Seleccione los puntos suspensivos (...) a la derecha de la cuadrícula y luego seleccione **Mostrar pie de página**.
2.  Seleccione y mantenga presionado (o haga clic con el botón derecho) en cada columna de importe y luego selecfcione **Agrupar por esta columna** para mostrar los torales. Los totales se muestran en el pie de página. Si la consulta se filtra para que muestre solo las transacciones no liquidadas, puede usar los totales para conciliar los montos con el balance de comprobación.







