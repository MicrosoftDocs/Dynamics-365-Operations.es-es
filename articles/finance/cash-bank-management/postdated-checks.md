---
title: Cheques con fecha futura
description: Este artículo proporciona información acerca de la compatibilidad de los cheques posfechados en Microsoft Dynamics 365 Finance. Los cheques con fecha futura son cheques que se emiten con el fin de realizar y recibir pagos en una fecha futura. Por tanto, no se puede cobrar el cheque hasta la fecha especificada.
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, CustPostDatedChecks
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 38ee6c5b3d258c313a2066b388a83330bf696d39
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447758"
---
# <a name="postdated-checks"></a>Cheques con fecha futura

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca de la compatibilidad de los cheques posfechados. Los cheques con fecha futura son cheques que se emiten con el fin de realizar y recibir pagos en una fecha futura. Por tanto, no se puede cobrar el cheque hasta la fecha especificada.

Dynamics 365 Finance admite el ciclo de gestión completo para los cheques posfechados tanto en Clientes como en Proveedores, como se muestra en la siguiente tabla.
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
<td>Registrar los detalles de un cheque posfechado que emite a un proveedor. Cuando se registra el pago, se reconoce el pasivo del proveedor pero la cuenta bancaria no es crédito todavía. En su lugar, se usa una cuenta de compensación para este propósito. </td>
</tr>
<tr class="odd">
<td>Registro de un cheque con fecha futura para un cliente</td>
<td>Registrar los detalles de un cheque con fecha futura que recibe de un cliente. Cuando se registra el pago, la cuenta por cobrar del cliente es crédito pero la cuenta bancaria no es débito todavía. En su lugar, se usa una cuenta de compensación para este propósito.</td>
</tr>
<tr class="even">
<td>Registrar un cheque con pago diferido de sustitución para un proveedor o cliente.</td>
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
- El cheque se ha aplicado a una factura incorrecta.
- Se debe hacer un pago en efectivo en relación al cheque.
  </td>
  </tr>
  <tr class="even">
  <td>Detener un pago de un cheque con pago diferido</td>
  <td>Puede detener el pago de cheque posfechado que se emitió a un proveedor por motivos como fondos insuficientes, cambio de las condiciones del contrato con el proveedor, suministro de mercancías defectuosas por proveedor o devolución de mercancías al proveedor. Puede detener el pago solo en los cheques que no ha compensado.</td>
  </tr>
  </tbody>
  </table>



Para obtener más información, consulte los siguientes temas:

[Configuración de cheques con pago diferido](tasks/set-up-postdated-checks.md)

[Registrar un cheque con pago diferido para un cliente](tasks/register-post-postdated-check-customer.md)

[Liquidar un cheque con pago diferido de un cliente](tasks/settle-postdated-check-customer.md)

[Registrar un cheque con pago diferido para un proveedor](tasks/register-post-postdated-check-vendor.md) 

[Liquidar un cheque con pago diferido para un proveedor](tasks/settle-postdated-check-vendor.md)



