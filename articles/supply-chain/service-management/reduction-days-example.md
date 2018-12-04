---
title: "Ejemplo de días de reducción"
description: "Ejemplo de días de reducción."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 69e4b1b0fe100b17e5b2c59be81604019347956f
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---


# <a name="reduction-days-example"></a>Ejemplo de días de reducción 

[!include [banner](../includes/banner.md)]


Ha creado una transacción de suscripción para la suscripción de mantenimiento de un cliente, tal como se describe en la tabla siguiente.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Desde fecha</p></th>
<th><p>Hasta fecha</p></th>
<th><p>Suscripción</p></th>
<th><p>Tipo de suscripción</p></th>
<th><p>Proyecto</p></th>
<th><p>Categoría</p></th>
<th><p>Divisa de ventas</p></th>
<th><p>Precio de venta</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>01 de marzo de 2011</p></td>
<td><p>31 de marzo de 2011</p></td>
<td><p>NR-2</p></td>
<td><p><strong>Normal</strong></p></td>
<td><p>9013</p></td>
<td><p>SubCat2</p></td>
<td><p>EUR</p></td>
<td><p>200,00</p></td>
</tr>
</tbody>
</table>


El cliente indica que no necesita cobertura de servicio durante dos días (el 10 de marzo y el 11 de marzo) y el usuario acepta reducir la suscripción por estos dos días.

Se crea una nueva transacción del tipo **Días de reducción**, tal como se describe en la tabla siguiente.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Desde fecha</p></th>
<th><p>Hasta fecha</p></th>
<th><p>Suscripción</p></th>
<th><p>Tipo de suscripción</p></th>
<th><p>Proyecto</p></th>
<th><p>Categoría</p></th>
<th><p>Divisa de ventas</p></th>
<th><p>Precio de venta</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>10 de marzo de 2011</p></td>
<td><p>11 de marzo de 2011</p></td>
<td><p>NR-2</p></td>
<td><p><strong>Días de reducción</strong></p></td>
<td><p>9013</p></td>
<td><p>SubCat2</p></td>
<td><p>EUR</p></td>
<td><p>-12,90</p></td>
</tr>
</tbody>
</table>


Cuando se facturen las transacciones de marzo de 2011, el precio de ventas de EUR 200 se reduce en EUR 12,90. Por lo tanto, el importe imputable para la transacción es EUR 187,10 y se facturan dos transacciones por un total de EUR 187,10.

## <a name="see-also"></a>Consulte también

[Reducir los días de las cuotas de suscripción](reduce-the-days-on-subscription-fees.md)

  



