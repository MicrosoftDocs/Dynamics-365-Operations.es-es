---
title: Combinación de pedidos de servicio
description: Puede combinar pedidos de servicio.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f89c60561746ac9f1c2e9d611089bfac69089081
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676786"
---
# <a name="combine-service-orders"></a>Combinación de pedidos de servicio   

[!include [banner](../includes/banner.md)]


Al crear líneas de pedido de servicio automáticamente en el formulario **Acuerdos de servicio**, puede elegir una de las siguientes opciones para especificar cómo desea agruparlas:

  - **Por acuerdo de servicio**

  - **Por tarea de servicio**

  - **Por empleado**

  - **Por objeto de servicio**

## <a name="example"></a>Ejemplo

Imagine que crea un acuerdo de servicio que incluya la fecha de inicio del 31-03-2007. En el campo **Combinar pedidos de servicio**, especifique **Por objeto de servicio**. A continuación, crea las siguientes líneas de acuerdo de servicio:

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>Número de línea del acuerdo</p></th>
<th><p>Tipo de transacción</p></th>
<th><p>Descripción</p></th>
<th><p>Intervalo</p></th>
<th><p>Objeto de servicio</p></th>
<th><p>Fecha de inicio</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p><strong>Hora</strong></p></td>
<td><p>SAL1</p></td>
<td><p>Semanalmente</p></td>
<td><p>X-1</p></td>
<td><p>01-04-2007</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p><strong>Hora</strong></p></td>
<td><p>SAL2</p></td>
<td><p>Quincenal</p></td>
<td><p>X-2</p></td>
<td><p>01-04-2007</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p><strong>Hora</strong></p></td>
<td><p>SAL3</p></td>
<td><p>Semanalmente</p></td>
<td><p>X-2</p></td>
<td><p>01-04-2007</p></td>
</tr>
</tbody>
</table>


No especifica ventanas de tiempo para ninguna línea de acuerdo de servicio. Por lo tanto, las líneas de acuerdo de servicio no se transferirán del día calculado en el que se encuentren.

A continuación, genere líneas de pedido de servicio desde el formulario **Crear pedidos de servicio** del 01-04-2007 al 30-04-2007.

En total, se crean 10 pedidos de servicio. Dado que la configuración combinada que seleccionó fue **Por objeto de servicio**, todos los pedidos de servicio que se crean sólo tienen líneas de pedido de servicio con un objeto de servicio específico. Las líneas de pedido de servicio que se generan a partir del acuerdo de servicio que tienen la misma fecha de servicio y el mismo objeto se combinan en el mismo pedido de servicio.


> [!NOTE]
> <P>En este ejemplo, el calendario especificado en el formulario <STRONG>Parámetros de gestión de servicio</STRONG> no tiene días cerrados.</P>



Se producen más agrupaciones de líneas de pedido de servicio en pedidos de servicio en función de las ventanas de tiempo que especifique en las líneas de acuerdo de servicio.

## <a name="see-also"></a>Consulte también

[Crear pedidos de servicio automáticamente](create-service-orders-automatically.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]