---
title: Liquidar pagos de TDS a proveedores de autoridad de TDS y generar challan de TDS
description: Este tema explica cómo liquidar pagos de impuestos deducidos en el origen (TDS) a proveedores de autoridad de TDS.
author: kailiang
ms.date: 03/12/2021
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
ms.openlocfilehash: a9912151ef9fc68941858545e39bccc1e5d3e411
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358323"
---
# <a name="settle-tds-payments-to-tds-authority-vendors-and-generate-tds-challan"></a>Liquidar pagos de TDS a proveedores de autoridad de TDS y generar challan de TDS

[!include [banner](../includes/banner.md)]

Este tema explica cómo liquidar pagos de impuestos deducidos en el origen (TDS) a proveedores de autoridad de TDS.

1. Vaya a **Proveedores \> Pagos \> Diario de pagos a proveedores**.

    [![Página del diario de pagos a proveedores.](./media/apac-ind-TDS-51.png)](./media/apac-ind-TDS-51.png)

2. En la página **Diario de pagos del proveedor**, seleccione **Nuevo** para crear una línea de diario.
3. En el campo **Cuenta**, seleccione el proveedor de autoridad de TDS al que liquidar los pagos de TDS.
4. Seleccione **Transacciones de liquidación** para abrir la página **Transacciones de liquidación**, donde puede ver las transacciones de TDS liquidadas para el proveedor de autoridad de TDS.

    Las transacciones de TDS liquidadas para un periodo de liquidación se muestran de la siguiente manera:

    - Transacciones de TDS donde la naturaleza de la categoría de evaluados es **Empresa** se muestran como una línea de transacción.
    - Transacciones de TDS donde la naturaleza de la categoría de evaluados es **HUF**, **Firma**, **Individuo**, **AOP**, **BOI**, **Autoridad local** u **Otros** se muestran como una línea de transacción.
    - El campo **Importe** muestra la cantidad total de TDS que se debe pagar al proveedor de la autoridad de TDS.

5. Seleccione **Transacciones de retención de impuestos** para ver las diferentes transacciones de TDS que se incluyen para el registro de liquidación. Puede ver la división de cada transacción de TDS que se ha incluido en el proceso de liquidación para el periodo de liquidación en esta página.
6. En la pestaña **Información general**, seleccione la casilla **Marcar** para que las transacciones de TDS se liquiden al proveedor de la autoridad de TDS.

    La pestaña **Información general** muestra la siguiente información para cada transacción de TDS abierta:

    - **Fecha**: la fecha de la transacción de TDS.
    - **Asiento**: el número de asiento.
    - **Origen**: el módulo en el que se registra la transacción de TDS.
    - **Proveedor/Cliente**: el número de cuenta del proveedor o cliente del que se deducen los TDS.
    - **Nombre del deducible/parte**: el nombre del proveedor o cliente del que se deducen los TDS.
    - **Naturaleza del evaluado**: la naturaleza de la categoría del evaluado a la que pertenece el deducible.
    - **Importe**: el importe de la factura sobre el que se calcularón los TDS.
    - **Importe del impuesto**: el importe de TDS que se calculó para la transacción.

    > [!NOTE]
    > Desmarque la casilla **Marcar** para cualquier transacción de TDS que no deba liquidarse con el proveedor de la autoridad de TDS.

    En la pestaña **General**, el campo **PAN** muestra el número de cuenta permanente (PAN) del deducible. El campo **Fecha** muestra la fecha del cálculo de TDS y el campo **Valor** muestra el porcentaje total que se utilizó para el cálculo de TDS.

7. Seleccione **Asiento** para ver las entradas de asiento para la transacción TDS.
8. Cierre la página.
10. Seleccione **Componentes de retención de impuestos** para abrir la página **Componentes de retención de impuestos**, donde puede ver los TDS que se calcularon por componente de impuestos de TDS para un código de impuestos de TDS específico.

    En la pestaña **Información general**, el campo **Componente de impuestos** muestra el componente de impuestos de TDS que se utilizó para la transacción. El campo **Importe** muestra el importe de TDS que se calculó para el componente de impuestos de TDS en la divisa base. El campo **Importe acumulado** muestra el importe total de TDS que se calculó para el componente de impuestos TDS para todas las transacciones liquidadas.

    En la pestaña **Importe**, la sección **Divisa predeterminada** muestra el importe de TDS que se calculó para el componente de impuestos de TDS en la divisa predeterminada. La sección **Divisa secundaria** muestra el importe en la divisa secundaria.

11. Cierre la página **Componentes de retención de impuestos**.
12. En la página **Edición de transacciones abiertas**, en el campo **Importe**, observe que se actualiza el importe total a liquidar al proveedor de la autoridad de TDS para el periotransaccióndo de liquidación.
13. Para liquidar las transacciones de TDS de diferentes periodos de liquidación de TDS al proveedor de la autoridad de TDS, seleccione la casilla **Markar** para las transacciones.
14. Cierre la página **Edición de transacciones abiertas**.

    > [!NOTE]
    > Si solo se seleccionan unas pocas transacciones para liquidación en la página **Transacciones de retención de impuestos**, el importe total de TDS de las transacciones seleccionadas se actualiza en el campo **Corrección** en la página **Edición de transacciones abiertas**. El importe de corrección se actualiza en la línea del diario en la página **Asiento del diario** y se cierra la página **Edición de transacciones abiertas**.

    En la página **Asiento del diario**, el campo **Débito** muestra el imorte total a pagar al proveedor de la autoridad de TDS.

15. Introduzca los detalles de la cuenta de contrapartida.

    > [!NOTE]
    > Si las transacciones de TDS tienen diferentes números de cuenta de impuestos (TAN), las líneas de diario se crean por TAN en la página **Asiento del diario**.

16. En la pestaña **Cuota de pago**, en el campo **Id. de cuota**, seleccione un Id. de cuota que tenga un tipo de tarifa de **Interés** u **Otros** para cobrar la cuota de pago por pagos retrasados que se realicen al proveedor de la autoridad de TDS.

    En la pestaña **Información de impuestos**, en la sección **Información de la empresa**, el campo **Nombre** muestra el nombre de la empresa. En la sección **Retención de impuestos**, el campo **Número de cuenta de impuestos (TAN)** muestra el TAN adjunto a la línea de transacción.

17. Valide y registre el diario.
18. Seleccione **Retención de impuestos \> Información de challan** para introducir los detalles de challan para la transacción.

    El campo **Asiento** muestra el número de asiento de la transacción.
    
19. Seleccione la casilla **TDS depositados por entrada de libro** si el importe de TDS se deposita mediante la entrada de libro.
20. En el campo **Número de challan**, introduzca el número de challan que se utiliza para realizar el pago al proveedor de la autoridad de TDS.
21. En el campo **Fecha**, escriba la fecha del challan.
22. En el campo **Nombre del banco**, seleccione el nombre del banco en el que se debe depositar el importe de TDS que se debe pagar al proveedor de la autoridad de TDS. Este campo enumera todas las cuentas bancarias que se configuraron para el proveedor de autoridad de TDS en **Proveedores \> Todos los proveedores \> Configurar \> Cuentas bancarias**.
23. En el campo **Código BSR**, introduzca el código de devolución estadística básica (BSR) del banco.
24. Cierre la página.

### <a name="example"></a>Ejemplo

El periodo 01/04/2009 se liquida para el grupo de componentes de TDS **Alquiler** mediante el proceso de liquidación periódica de TDS. El importe total de TDS de 141 625,00 se contabiliza en la cuenta de autoridad del proveedor de TDS para el periodo de liquidación de TDS. Puede ver este importe en el campo **Importe** en la página **Edición de transacciones abiertas** para el proveedor de autoridad de TDS.

Si selecciona **Transacciones de retención de impuestos** para ver las diferentes transacciones de TDS que se liquidaron para el periodo, se muestra la siguiente información.

| Importe de TDS |
|------------|
| 16,995.00  |
| 22,660.00  |
| 28,325.00  |
| 16,995.00  |
| 28,325.00  |
| 16,995.00  |
| 11,330.00  |

Para un importe de TDS concreto, seleccione **Componentes de retención de impuestos** para ver los TDS que se calcularon por componente de impuestos de TDS para un código de impuestos de TDS específico. Para este ejemplo, seleccione **Componentes de retención de impuestos** para el importe de TDS 16 995,00. Se muestra el importe del impuesto que se calculó por componente para la transacción.

| Componente impositivo | Importe    | Importe acumulado |
|---------------|-----------|--------------------|
| TDS           | 1,5000.00 | 125,000.00         |
| Suplemento     | 1,500.00  | 12,500.00          |
| PE-Cess       | 330.00    | 2,750.00           |
| SHE Cess      | 165.00    | 1,375.00           |

Si seleccionó solo los importes de TDS 16 995,00, 22 660,00 y 28 325,00 para liquidación en la página **Transacciones de retención de impuestos**, el importe total para liquidación se muestra como **67 980,00** en el campo **Corrección** en la página **Edición de transacciones abiertas**. Si esta transacción está marcada para liquidación y la página **Edición de transacciones abiertas** está cerrada, el importe **67 980,00** se muestra en el cmapo **Débito** en la página **Asiento del diario**.

Ahora puede registrar el diario y generar el challan de TDS.

### <a name="adjustment-of-advance-payments-that-are-made-to-tds-authority-vendors"></a>Ajuste de los pagos anticipados que se realizan a los proveedores autorizados de TDS

Para ajustar un anticipo que se hizo al proveedor de la autoridad de TDS a un pago real, vaya a **Proveedores \> Proveedores \> Todos los proveedores \> Edición de transacciones**. Si el pago real que se realiza excede el anticipo, se generan dos números de challan para la transacción. Sin embargo, solo el primer número de challan se muestra en la consulta de TDS.
