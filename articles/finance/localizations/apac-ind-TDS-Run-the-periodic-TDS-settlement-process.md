---
title: Ejecutar el proceso de liquidación periódica de TDS
description: Este tema explica cómo liquidar impuestos deducidos en el origen (TDS) periódicos.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: bfa7dc9c2a86b5bd8783327c0e7cfa6b8b9ddd4c
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358347"
---
# <a name="run-the-periodic-tds-settlement-process"></a>Ejecutar el proceso de liquidación periódica de TDS

[!include [banner](../includes/banner.md)]

Este tema explica cómo liquidar impuestos deducidos en el origen (TDS) periódicos.

1. Vaya a **Impuesto \> Declaraciones \> Retención de impuestos \> Pago de retención de impuestos**.

    [![Cuadro de diálogo de pago de retención de impuestos.](./media/apac-ind-TDS-47.png)](./media/apac-ind-TDS-47.png)

2. En el cuadro de diálogo **Pago de retención de impuestos**, en el campo **Tipo de impuesto**, seleccione **TDS**.
3. En el campo **Número de cuenta de impuestos (TAN)**, seleccione el Número de cuenta de impuestos (TAN) para ejecutar el proceso de liquidación.
4. En el campo **Grupo de componentes de retención de impuestos**, seleccione el grupo de componentes de TDS para el que ejecutar el proceso de liquidación.
5. En el campo **Periodo de liquidación**, seleccione el periodo de liquidación de TDS para el que se ejecutará el proceso de liquidación.

    > [!NOTE]
    > El proceso de liquidación de TDS se ejecuta para todos los periodos que se configuran para el periodo de liquidación de TDS en la pestaña **Periodos** de la página **Periodos de liquidación de retención de impuestos** (**Impuesto \> Impuestos indirectos \> Retención de impuestos \> Periodos de liquidación de retención de impuestos**).

6. En el campo **Fecha inicial**, seleccione la fecha de inicio para ejecutar el proceso de liquidación de TDS.

    Para un periodo específico dentro del periodo de liquidación, la fecha inicial que se define para el periodo se toma como la fecha "desde". Por ejemplo, el periodo de liquidación de TDS tiene dos diferentes: del 1 de abril al 30 de abril de 2009 y del 1 de mayo al 31 de mayo de 2009. Si selecciona **06/04/2009** (6 de abril de 2009) como fecha inicial en el campo **Fecha inicial**, el proceso de liquidación aún se ejecutará a partir del 1 de abril de 2009.

    Si introduce un periodo posterior en el campo **Fecha inicial**, pero sin liquidar un periodo anterior dentro del periodo de liquidación, la liquidación no se producirá para ningún periodo anterior. Por ejemplo, el periodo de liquidación de TDS tiene tres diferentes: del 1 de abril al 30 de abril de 2009, del 1 de mayo al 31 de mayo de 2009 y del 1 de junio al 30 de junio de 2009. Si selecciona **01/05/2009** (1 de mayo de 2009) como fecha inicial en el campo **Fecha inicial**, el proceso de liquidación se ejecutará solo desde el 1 de mayo hasta el 31 de mayo de 2009. La liquidación no ocurrirá del 1 de abril al 30 de abril de 2009.

7. En el campo **Fecha de transacción**, seleccione la fecha para ejecutar la transacción de liquidación de TDS.
8. En el cuadro de diálogo **Versión del pago de retención de impuestos**, seleccione la versión de liquidación de TDS:

     - **Original**: utilice esta opción para ejecutar el proceso de liquidación de TDS por primera vez. La versión de pago original se utiliza solo una vez para ejecutar el proceso de liquidación de TDS para una combinación de un TAN, un grupo de componentes de retención de impuestos y un periodo de liquidación de retención de impuestos.
    - **Últimas versiones**: utilice esta opción si el proceso de liquidación de TDS ya se ha ejecutado en el periodo especificado. Incluya transacciones con fecha anterior que se registraron después de que se ejecutara previamente el proceso de liquidación para el periodo. Puede utilizar esta opción para ejecutar el proceso de liquidación tantas veces como desee.

9. Seleccione la casiila **Actualizar** para ejecutar el proceso de liquidación de TDS y registrar los importes en las cuentas contables. Si esta casilla de verificación está desactivada, el proceso de liquidación no se ejecutará y no se generarán las entradas financieras.
10. Seleccione **Aceptar** para ejecutar el proceso de liquidación de TDS y generar el informe de pago de retención de impuestos. El estado de las transacciones de TDS que se incluyen en el proceso de liquidación se muestra como **Liquidado** en la página **Liquidación** (vaya a **Proveedores \> Pagos \> Diario de pagos del proveedor**, seleccione **Líneas**, celeccione **Funciones** y luego seleccione **Liquidación**).

### <a name="important-points"></a>Puntos importantes

- Si no se selecciona un grupo de componentes de retención de impuestos durante el proceso de liquidación, la liquidación se produce para todos los grupos de componentes de retención de impuestos para el periodo de liquidación y TAN seleccionados. Se crea una línea separada para cada grupo de componentes de retención de impuestos en la página **Edición de transacciones abiertas**.
- El proceso de liquidación se basa en la naturaleza de la categoría del evaluado para un periodo de liquidación. Se liquidan las transacciones en las que la naturaleza de la categoría del evaluado es **Empresa** y se muestran como una línea en la página **Edición de transacciones abiertas**. Se liquidan las transacciones en las que la naturaleza de la categoría del evaluado sea diferente de **Empresa** y se muestran como una línea en la página **Edición de transacciones abiertas**.
- La fecha de vencimiento para las líneas de transacción de TDS liquidadas en la página **Edición de transacciones abiertas** se basa en las condiciones de pago que se definen para el proveedor de autoridad de TDS en la página **Proveedores**. Si las condiciones de pago no se han definido para el proveedor de la autoridad de TDS, el último día del periodo de liquidación se muestra como la fecha de vencimiento.
