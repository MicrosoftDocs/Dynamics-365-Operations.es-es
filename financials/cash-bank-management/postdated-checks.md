---
title: Cheques con fecha futura
description: "Este artículo proporciona información acerca del soporte para los cheques posfechados en Microsoft Dynamics 365 para las operaciones. Los cheques con fecha futura son cheques que se emiten con el fin de realizar y recibir pagos en una fecha futura. Por tanto, no se puede cobrar el cheque hasta la fecha especificada."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 7349771b7f9a1ad4cd5b239f1d10bd3229d2d0df
ms.lasthandoff: 03/31/2017


---

# <a name="postdated-checks"></a>Cheques con fecha futura

Este artículo proporciona información acerca del soporte para los cheques posfechados en Microsoft Dynamics 365 para las operaciones. Los cheques con fecha futura son cheques que se emiten con el fin de realizar y recibir pagos en una fecha futura. Por tanto, no se puede cobrar el cheque hasta la fecha especificada.

Microsoft Dynamics 365 para las operaciones admite el ciclo de administración completo para los cheques posfechados en clientes y proveedores, tal y como se muestra en la tabla siguiente.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Situación</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuración de cheques con pago diferido</td>
<td>Debe configurar un nuevo método de pago y especifica la rutina de pago para las cuentas de compensación para los cheques emitidos, los cheques recibidos y la retención de impuestos.</td>
</tr>
<tr class="even">
<td>Registrar un cheque con pago diferido para un proveedor</td>
<td>Registrar los detalles de un cheque posfechado que emite a un proveedor. Cuando se registra el pago, se reconoce el pasivo del proveedor, pero la cuenta bancaria no está aún crédito. En su lugar, se usa una cuenta de compensación para este propósito.</td>
</tr>
<tr class="odd">
<td>Registro de un cheque con fecha futura para un cliente</td>
<td>Registrar los detalles de un cheque con fecha futura que recibe de un cliente. Cuando se registra el pago, el cliente es de crédito de clientes, pero la cuenta bancaria no se debe aún. En su lugar, se usa una cuenta de compensación para este propósito.</td>
</tr>
<tr class="even">
<td>Registrar un cheque con pago diferido de sustitución para un cliente o un proveedor</td>
<td>
Si ha perdido o dañado el cheque original a un proveedor o de un cliente, puede emitir un cheque posfechado de sustitución al proveedor. Al registrar los detalles del cheque, proporcione una referencia del cheque original e indique que el nuevo cheque es una sustitución del original. También puede registrar el cheque de sustitución.</td>
</tr>
<tr class="odd">
<td>Transferir un cheque con pago diferido de un cliente a un proveedor</td>
<td>Cuando reciba un cheque posfechado de un cliente, puede transferir ese cheque a un proveedor como pago.</td>
</tr>
<tr class="even">
<td>Liquidar un cheque con pago diferido para un cliente o proveedor</td>
<td>Liquidar un cheque posfechado registrado en una cuenta puente para un cliente o proveedor cuando el cheque finalmente madura. Cuando se liquida el cheque, el banco es finalmente débito o crédito frente a la cuenta de compensación que se usó anterior.</td>
</tr>
<tr class="odd">
<td>Cancelar un cheque con pago diferido para un proveedor</td>
<td>Puede cancelar un cheque posfechado registrado en las situaciones siguientes: - El banco ha devuelto el cheque.
- La comprobación se aplica a una factura incorrecta.
- Un pago en efectivo en relación al cheque.
</td>
</tr>
<tr class="even">
<td>Pago de detención para un cheque posfechado</td>
<td>Puede detener el pago de cheque posfechado que se emitió a un proveedor por motivos como fondos insuficientes, cambio de las condiciones del contrato con el proveedor, suministro de mercancías defectuosas por proveedor o devolución de mercancías al proveedor. Puede detener el pago sólo en los cheques que no ha compensado.</td>
</tr>
</tbody>
</table>





