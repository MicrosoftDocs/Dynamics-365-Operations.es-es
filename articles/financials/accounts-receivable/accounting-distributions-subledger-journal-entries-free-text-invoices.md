---
title: Distribuciones contables y asientos del subdiario contable para las facturas de servicios
description: "Las distribuciones contables se usan para definir cómo se contabilizará un importe; por ejemplo, cómo se contabilizarán los ingresos, impuestos o gastos en una factura de servicios. Cada importe que se debe contabilizar cuando se registre la factura de servicios en el diario tendrá una o varias distribuciones contables."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d13fbd98597fc8138bfb4d549608d75f790e0e52
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="accounting-distributions-and-subledger-journal-entries-for-free-text-invoices"></a>Distribuciones contables y asientos del subdiario contable para las facturas de servicios

[!include[banner](../includes/banner.md)]


Las distribuciones contables se usan para definir cómo se contabilizará un importe; por ejemplo, cómo se contabilizarán los ingresos, impuestos o gastos en una factura de servicios. Cada importe que se debe contabilizar cuando se registre la factura de servicios en el diario tendrá una o varias distribuciones contables.

<a name="accounting-distributions"></a>Distribuciones contables
------------------------

Puede usar los siguientes botones de la página Factura de texto libre para ver y para modificar probablemente las distribuciones contables de cada importe de la factura de texto libre.

-   **Distribuir importes**: permite ver y cambiar las distribuciones contables de una línea individual y todas las líneas secundarias, como impuestos o gastos. También puede ver y cambiar distribuciones contables para la línea secundaria directamente desde la página Transacciones de impuestos o la página Transacciones de gastos.
    -   Permite cambiar importes de encabezado de factura de servicios, como gastos o importes de redondeo de divisa.
    -   Cambie importes de líneas de facturas de texto libre.
-   **Ver distribuciones**: permite ver las distribuciones contables para todas las líneas del documento. No se pueden cambiar las distribuciones contables desde esta vista.
    -   Permite ver los importes de línea y encabezado.

## <a name="distributing-amounts"></a>Distribución de importes
Al introducir una factura de servicios, cada importe se va a distribuir de la siguiente manera.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de importe monetario</th>
<th>Desde dónde se muestra la cuenta principal</th>
<th>Orden de prioridad que determina que dimensión financiera se visualiza</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Línea de factura de servicios</td>
<td>La cuenta contable en la línea de factura de servicios.</td>
<td><ol>
<li>Si la cuenta principal es una cuenta de asignación, use el valor predeterminado de la definición de cuenta de asignación.</li>
<li>Si la cuenta principal no es una cuenta de asignación, use la plantilla predeterminada de dimensión financiera en la línea de factura de servicios.</li>
<li>Use los valores de la dimensión financiera predeterminados en la línea de factura de servicios.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta contable en la página Plan de cuentas.</li>
</ol></td>
</tr>
<tr class="even">
<td>Línea de factura de servicios para un número de activo fijo y una combinación de modelo de valor
<div class="alert">
<table>
<thead>
<tr class="header">
<th><strong>Nota</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>La cuenta principal en la línea de factura de servicios será la primera cuenta de cancelación de activos fijos.</td>
</tr>
</tbody>
</table>
</div></td>
<td>La cuenta contable en la línea de factura de servicios.</td>
<td><ol>
<li>Use los valores de la dimensión financiera predeterminados en la línea de factura de servicios.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta contable en la página Plan de cuentas.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Importe de descuento de la factura de servicios</td>
<td>El campo Cuenta principal para descuentos de cliente en la página Descuentos por pronto pago.</td>
<td><ol>
<li>Si la cuenta principal es una cuenta de asignación, use el valor predeterminado de la definición de cuenta de asignación.</li>
<li>Si la cuenta principal no es una cuenta de asignación, use la plantilla predeterminada de dimensión financiera en la línea de factura de servicios.</li>
<li>Use los valores de la dimensión financiera predeterminados en la línea de factura de servicios.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta contable en la página Plan de cuentas.</li>
</ol></td>
</tr>
<tr class="even">
<td>Importe de impuestos de la factura de servicios</td>
<td>El campo Impuestos repercutidos en la página Grupos de registro.</td>
<td><ol>
<li>Use las dimensiones financieras que se definen en el importe de línea de factura de servicios o las distribuciones del importe de la línea de gastos.</li>
<li>Use los valores de la dimensión financiera predeterminados en la línea de factura de servicios.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta contable en la página Plan de cuentas.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Importe de línea de gastos de la factura de servicios</td>
<td>El campo Cuenta de crédito en la página Código de gastos.</td>
<td><ol>
<li>Si la cuenta principal es una cuenta de asignación, use el valor predeterminado de la definición de cuenta de asignación.</li>
<li>Si la cuenta principal no es una cuenta de asignación, use la plantilla predeterminada de dimensión financiera en la línea de factura de servicios.</li>
<li>Use los valores de la dimensión financiera predeterminados en la línea de factura de servicios.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta contable en la página Plan de cuentas.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a>Distribución de impuestos
Las distribuciones contables para los impuestos no se pueden crear hasta que se calculen los impuestos. Para calcular los impuestos, debe completar una de las tareas que se describen a continuación en el formulario Factura de texto libre:
-   Ver los impuestos.
-   Ver el total de la factura.
-   Ver el flujo de efectivo.
-   Ver las distribuciones contables de toda la factura de servicios.
-   Ver el subdiario contable.

## <a name="subledger-journals-for-free-text-invoices"></a>Subdiarios contables para facturas de servicios
Antes de registrar una factura de servicios, se debe visualizar el asiento contable completo de la factura, que incluye débitos y créditos, para verificar que la factura se está registrando en las cuentas correctas. Esta visualización del asiento contable completo se denomina subdiario contable. Si el asiento del subdiario contable es incorrecto cuando se obtiene una vista previa antes de registrar la factura de servicios en el diario, no se puede cambiar el asiento del subdiario contable. En lugar de ello, se deben cambiar las distribuciones contables o el perfil de registro. Las distribuciones contables se usan para definir un lado del asiento contable, el débito o el crédito. El asiento contable del subdiario contable se crea a partir de los perfiles de registro, como por ejemplo, desde la cuenta de cliente o los impuestos.




