---
title: Cálculo de TDS sobre pagos y pagarés
description: Este tema proporciona información de referencia sobre las diferentes transacciones de pago en las que se calcula el impuesto deducido en el origen (TDS).
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
ms.openlocfilehash: ea57963e41b90bbc11efa00b85aad8bc60c2357d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023570"
---
# <a name="tds-calculation-on-payments-and-promissory-notes"></a>Cálculo de TDS sobre pagos y pagarés

[!include [banner](../includes/banner.md)]

Este tema proporciona información de referencia sobre las diferentes transacciones de pago en las que se calcula el impuesto deducido en el origen (TDS).

| Número de serie | Tipo de transacción | Importe de la transacción | Nombre y ruta de la página | Tipo de cuenta y tipo de cuenta de contrapartida |
|---------------|------------------|--------------------|--------------------|--------------------------------------|
| 1             | Pago anticipado/Pago contra factura (proveedor de TDS) | Debe o Haber | <ul><li>Diario general (**Contabilidad general \> Movimientos de diario \> Diarios generales**)</li><li>Diario de facturas (**Proveedores \> Facturas \> Diario de facturas**)</li><li>Diajos de pagos (**Proveedores \> Pagos \> Diario de pagos a proveedores**)</li></ul> | Contabilidad (Dr.) Banco (Cr.). |
| 2             | Pago anticipado/Pago contra factura (compra realizada al cliente - proveedor de TDS) | Debe o Haber | <ul><li>Diario general (**Contabilidad general \> Movimientos de diario \> Diarios generales**)</li><li>Diario de facturas (**Proveedores \> Facturas \> Diario de facturas**)</li><li>Diajos de pagos (**Proveedores \> Pagos \> Diario de pagos a proveedores**)</li></ul> | Cliente (Dr.) Banco (Cr.) |
| 3             | Pagarés | Débito | Crear diario de pagarés (**Proveedores \> Pagos \> Pagarés \> Crear diario de pagarés**) | Proveedor (Dr.) Contabilidad (Cr.) |
| 4             | Ingresos varios (cliente de TDS) | Debe o Haber | Diario general (**Contabilidad general \> Movimientos de diario \> Diarios generales**) | Banco (Dr.) Contabilidad (Cr.). |
| 5             | Otros gastos (proveedor de TDS) | Debe o Haber | Diario general (**Contabilidad general \> Movimientos de diario \> Diarios generales**) | Banco (Dr.) Contabilidad (Cr.). |

Siga estos pasos para calcular los TDS en pagos y pagarés.

1. En las páginas del diario, cree líneas de diario. Seleccione el tipo de cuenta y el tipo de cuenta de contrapartida.
2. Seleccione **Funciones \> Liquidación** para abrir la página **Edición de transacciones abiertas**. Luego seleccione una factura específica que deba liquidarse. Si los TDS ya se han calculado a nivel de factura, el campo **Origen de importe** muestra el importe base sobre el que se calcularon los TDS. El campo **Importe de TDS** muestra el importe de TDS que se calcuó para la transacción. El campo **Importe** muestra el importe del pago neto (es decir, el importe del pago después de deducir los TDS).

    > [!NOTE]
    > Para un pago que se realizó contra una factura, se aplican las siguientes condiciones:
    >
    > - Si el importe del pago y el importe de la factura son iguales, el TDS no se calcula si ya se ha calculado en el nivel de la factura.
    > - Si el importe de la factura después de deducir el importe de TDS es mayor que el importe del pago, no se calcula el TDS.
    > - Si el importe de la factura después de deducir el importe del TDS es menor que el importe del pago, el TDS se calcula sobre el importe que excede el de la factura.

3. En la página **Asiento del diario**, en la pestaña **Información general**, en el campo **Grupos de TDS**, revise o cambio el grupo de TDS predeterminado que se ha definico para el proveedor o cliente. El TDS que se calcula en las líneas de diario en función de la fórmula definida para los códigos de impuestos de TDS que se enumeran en el campo Grupo TDS.

    > [!NOTE]
    > TDS se calcula solo si se ha establecido la opción **Calcular retención de impuestos** en **Sí** para el proveedor en la página **Proveedores**.

4. En la pestaña **Información de impuestos**, en la sección **Información de la empresa**, en el campo **Nombre**, puede seleccionar el nombre de la empresa para direcciones alternativas que se han configurado para la empresa.

    En la sección **Retención de impuestos**, el campo **Naturaleza del evaluado** muestra la categoría de naturaleza del evaluado del proveedor o cliente. El campo **Número de cuenta de impuestos (TAN)** muestra el número de cuenta de impuestos (TAN) de la empresa seleccionada.

5. Seleccione el botón **Retención de impuestos \> retención de impuestos** para abrir la página **Transacciones de retención temporal de impuestos**. La parte superior de esta página tiene los siguientes campos:

    - **Retención de importe total de impuestos**: el total de TDS calculado para la transacción para el grupo de TDS.
    - **Valor**: el porcentaje total utilizado para calcular TDS para la transacción. El porcentaje total se basa en la fórmula que se define para los códigos de impuestos TDS y que se adjunta al grupo TDS.
    - **Importe total de la retención de impuestos ajustada**: el importe total de TDS ajustado para todos los códigos de impuestos en el grupo TDS.
    - **TDS**: una casilla seleccionada indica que un grupo de TDS está adjunto a la transacción.

    Los campos en las pestañas **Información general**, **General** e **Ajuste** muestran el importe de TDS calculado y los detalles del importe de TDS ajustado para cada código de impuestos de TDS adjunto al grupo de TDS.

6. Seleccione **Umbral** para abrir la página **Umbral**, donde puede revisar el límite de umbral que se define para el componente de impuestos de TDS que está adjunto a un código de impuestos de TDS específico.
7. Seleccione **Diseñador de fórmulas** para abrir la página **Diseñador de fórmulas**, donde puede revisar la fórmula que se define para un código de impuestos de TDS específico.
8. Cierre las páginas **Diseñador de fórmulas** y **Transacciones de retención temporal de impuestos** para volver a la página **Asiento del diario**.
9. Valide y registre el diario. El importe de TDS que se calculó se registra en la cuenta de proveedor que se define para cada código de impuestos de TDS en el grupo de TDS. Las cuentas de clientes para los códigos de impuestos TDS se definen en la página **Códigos de retención de impuestos**.
10. Seleccione **Retención de impuestos registrados** para abrir la página **Transacciones de retención de impuestos**. El campo **Valor** muestra el porcentaje total utilizado para calcular TDS para la transacción.

    Los campos en las pestañas **Información general**, **General** e **Importe** muestran los importes de TDS que se calcularon para el grupo de TDS que está adjunto a la transacción.

11. Revise la información de cálculo de TDS para cada código de impuestos de TDS adjunto al grupo de TDS.

## <a name="generate-payments"></a>Generar pagos

Siga los siguientes pasos para generar pagos.

1. Siga uno de estos pasos:

    - Vaya a **Proveedores \> Pagos \> Diario de pagos a proveedores**.
    - Vaya a **Clientes \> Pagos \> Diario de pagos de clientes**.
    - Vaya a **Proveedores \> Pagos \> Pagarés \> Crear diario de pagarés**.
    - Vaya a **Clientes \> Pagos \> Letra de cambio \> Diario de creación de letra de cambio**.
    - Vaya a **Clientes \> Pagos \> Letra de cambio \> Diario de renegociación de letras de cambio**.

2. Seleccionar **Líneas**.
3. Seleccione **Funciones \> Generar pagos**
