---
title: Informe de vencimiento de clientes
description: El informe de vencimiento de clientes muestra los saldos ordenados por intervalo de fechas o período de vencimiento.
author: JodiChristiansen
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 384e44ef07771a174aaed4f8fb893e75b0206da7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236995"
---
# <a name="customer-aging-report"></a>Informe de vencimiento de clientes 

El informe **Vencimiento de clientes** muestra los saldos ordenados por intervalo de fechas o período de vencimiento.

Cuando genere este informe, se mostrarán los siguientes parámetros predeterminados. Puede usar estos parámetros para filtrar los datos que se mostrarán en el informe. Para obtener más información, consulte [Configurar cobros](set-up-collections.md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Campo</p></th>
<th><p>Descripción</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Clasificación de la facturación</strong></p></td>
<td><p>Seleccione una o varias clasificaciones de la facturación para incluirlas en el informe.</p>
<div class="alert">

**Nota**: Este control solo está disponible si está seleccionada la clave de configuración del <STRONG>Sector público</STRONG>.</P>


</div></td>
</tr>
<tr class="even">
<td><p><strong>Incluir transacciones sin una clasificación de la facturación</strong></p></td>
<td><p>Si esta casilla está activada, todas las transacciones que no tengan una clasificación de la facturación asignada se mostrarán en el informe.</p>
<div class="alert">

**Nota**: Este control solo está disponible si está seleccionada la clave de configuración del <STRONG>Sector público</STRONG>.</P>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>Vencimiento a partir de</strong></p></td>
<td><p>Ingrese la fecha utilizada en el depósito de antigüedad actual.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Saldo a partir de</strong></p></td>
<td><p>Especifique la fecha para la que desea consultar los saldos de cliente. Esta fecha también se conoce como una fecha límite para transacciones.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fecha inicial</strong></p></td>
<td><p>Especifique una fecha que se encuentra en el primer intervalo de períodos o período de vencimiento para incluirla en el informe.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Criterios</strong></p></td>
<td><p>Seleccione el tipo de fecha en la que se basa el informe.</p>
<ul>
<li><p><strong>Fecha de transacción</strong> - La fecha de registro de las transacciones. Por ejemplo, podría ser una fecha de factura que es la base del cálculo de la fecha de vencimiento.</p></li>
<li><p><strong>Fecha de vencimiento</strong> - La fecha de vencimiento de las transacciones, de acuerdo con las condiciones de pago.</p></li>
<li><p><strong>Fecha de documento</strong> – Una fecha de documento definida por el usuario que es la base para el cálculo de la fecha de vencimiento.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Definición de período de vencimiento</strong></p></td>
<td><p>Seleccione una definición de período de vencimiento. El campo <strong>Intervalo</strong> no se usa si se selecciona una definición de período de vencimiento.</p>
<p>Las definiciones del período de vencimiento que tienen más de seis períodos de vencimiento no se pueden usar en el informe impreso.</p>
<div class="alert">

**Nota:** Puede configurar períodos de envejecimiento en la página <STRONG>Definiciones del período de envejecimiento</STRONG>.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Imprimir descripción de período de vencimiento</strong></p></td>
<td><p>Seleccione <strong>Sí</strong> para incluir descripciones del depósito de vencimiento al principio de cada columna de período de vencimiento en el informe. Seleccione <strong>No</strong> para imprimir el informe sin encabezados de columna.</p></td>
</tr>
<tr class="even">
<td><p><strong>Intervalo</strong></p></td>
<td><p>Defina el período que se usará especificando el número de unidades de días o meses en cada período. Por ejemplo, para ver la información de vencimiento por semana, escriba 7 en este campo y seleccione <strong>Día</strong> en el campo <strong>Día/Mes</strong>.</p>
<div class="alert">

**Nota**: La información que se especifica en este campo solo se usa si no se ha seleccionado ninguna definición de período de vencimiento. De lo contrario, la dirección de impresión se define en la definición del período de envejecimiento.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Día/Mes</strong></p></td>
<td><p>Seleccione la unidad, <strong>Día</strong> o <strong>Mes</strong>, que se usa para definir el período en el campo <strong>Intervalo</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dirección de impresión</strong></p></td>
<td><p>Seleccione si desea calcular saldos e imprimir el informe de vencimiento para los períodos pasados o futuros. La fechas se evalúan con relación a la fecha seleccionada en el campo <strong>Saldo según</strong>. Seleccione <strong>Regresivo</strong> para mostrar la información de períodos pasados. Seleccione <strong>Adelante</strong> para mostrar la información de períodos futuros.</p>
<div class="alert">
  
<STRONG>Nota</STRONG>: La información que se especifica en este campo solo se usa si no se ha seleccionado ninguna definición de período de vencimiento.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Detalles</strong></p></td>
<td><p>Se selecciona para mostrar las transacciones que están comprendidas en los saldos que se muestran en el informe.</p></td>
</tr>
<tr class="even">
<td><p><strong>Incluir importes en la divisa de la transacción</strong></p></td>
<td><p>Se selecciona para incluir importes en la divisa de transacción además de importes en la divisa de contabilidad. Si no se activa esta casilla, los importes del informe solo se muestra en la divisa de contabilidad.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Saldo negativo</strong></p></td>
<td><p>Se selecciona para incluir las cuentas de cliente con saldos negativos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Excluir cuentas de saldo cero</strong></p></td>
<td><p>Se selecciona para excluir las cuentas de cliente con saldo cero.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ubicación del pago</strong></p></td>
<td><p>Se selecciona para mostrar los pagos que no se han liquidado. Se muestran en la primera columna del informe.</p></td>
</tr>
</tbody>
</table>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]