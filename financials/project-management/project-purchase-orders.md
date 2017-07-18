---
title: Pedidos de compra para un proyecto
description: "Este artículo describe los distintos métodos que puede usar para crear pedidos de compra para un proyecto. El método que use depende del propósito del pedido de compra y de la fecha de consumo y de cargo a un proyecto de los artículos comprados."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 9715d33598c0749ff1ad2523f2fa8834987998ed
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017

---

# <a name="purchase-orders-for-a-project"></a>Pedidos de compra para un proyecto

[!include[banner](../includes/banner.md)]


Este artículo describe los distintos métodos que puede usar para crear pedidos de compra para un proyecto. El método que use depende del propósito del pedido de compra y de la fecha de consumo y de cargo a un proyecto de los artículos comprados.

En Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, puede usar varios métodos para crear pedidos de compra para un proyecto. El método que use depende del propósito del pedido de compra, de la fecha de consumo de los artículos comprados y de la fecha de cargo de los artículos comprados a un proyecto.

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
> Al actualizar la factura del proveedor o albarán, se solicita que actualice el albarán con el artículo requerido.




