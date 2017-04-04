---
title: Pedidos de compra para un proyecto
description: "Este artículo describe los distintos métodos que puede usar para crear pedidos de compra para un proyecto. El método que use depende del propósito del pedido de compra y de la fecha de consumo y de cargo a un proyecto de los artículos comprados."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 82305cfe38e7193cece3b9e7784fb81fd40f9c70
ms.lasthandoff: 03/31/2017


---

# <a name="purchase-orders-for-a-project"></a>Pedidos de compra para un proyecto

Este artículo describe los distintos métodos que puede usar para crear pedidos de compra para un proyecto. El método que use depende del propósito del pedido de compra y de la fecha de consumo y de cargo a un proyecto de los artículos comprados.

En Microsoft Dynamics 365 para las operaciones, puede usar varios métodos para crear pedidos de compra para un proyecto. El método que use depende del propósito del pedido de compra, de la fecha de consumo de los artículos comprados y de la fecha de cargo de los artículos comprados a un proyecto.

### <a name="methods-for-creating-a-purchase-order"></a>Métodos de creación de un pedido de compra

Puede usar uno de los siguientes métodos para crear un pedido de compra en Gestión de proyectos y contabilidad. La finalidad del pedido de compra determina cuándo se consume el pedido de compra y, por tanto, cuándo se cargan los artículos a un proyecto.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Método</th>
<th>Propósito</th>
<th>Consumo de artículos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Cree un pedido de compra directamente de un proyecto.</td>
<td>Use este método para comprar artículos de un proveedor externo para consumo en un proyecto. Puede crear el pedido de compra de dos formas:
<ul>
<li>Desde el propio proyecto. En este caso, el proyecto ya está definido para el pedido de compra.</li>
<li>Desplazándose hasta el pedido de compra del proyecto. Debe seleccionar tanto el proveedor como el proyecto para el que se creará el pedido de compra.</li>
</ul></td>
<td>Los artículos se consumen al actualizar la factura del proveedor.</td>
</tr>
<tr class="even">
<td>Cree un pedido de venta a partir de un pedido de ventas.</td>
<td>Utilice este método para adquirir artículos al crear un pedido de ventas a partir de un proyecto.</td>
<td>Los artículos se consumen al facturar el pedido de ventas al cliente.</td>
</tr>
<tr class="odd">
<td>Cree un pedido de compra a partir de un artículo requerido.</td>
<td>Utilice este método para adquirir artículos al crear un artículo requerido a partir de un proyecto.</td>
<td>Los artículos se consumen al actualizar el requisito de artículo.</td>
</tr>
</tbody>
</table>

> [!NOTE] 
> Al actualizar la factura del proveedor o el albarán, se le pedirá que actualice el albarán con el requisito de artículo.


