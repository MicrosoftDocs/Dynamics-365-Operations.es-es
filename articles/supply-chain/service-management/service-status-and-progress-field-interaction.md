---
title: Interacción del campo de progreso y estado del servicio
description: En el formulario Pedidos de servicio, el campo Progreso de la cabecera del pedido de servicio refleja el estado de todo el pedido de servicio, y el campo Estado indica el estado de líneas individuales del pedido de servicio.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2dd7b5160149a38dd62535901c1225bf704f404d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570795"
---
# <a name="service-status-and-progress-field-interaction"></a>Interacción del campo de progreso y estado del servicio 

[!include [banner](../includes/banner.md)]


En el formulario **Pedidos de servicio**, el campo **Progreso** de la cabecera del pedido de servicio refleja el estado de todo el pedido de servicio, y el campo **Estado** indica el estado de líneas individuales del pedido de servicio.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Progreso</p></th>
<th><p>Estado de línea 1</p></th>
<th><p>Estado de línea 2</p></th>
<th><p>Estado de línea 3</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>En proceso</strong></p></td>
<td><p><strong>Creado</strong></p></td>
<td><p><strong>Creado</strong></p></td>
<td><p><strong>Creado</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>En proceso</strong></p></td>
<td><p><strong>Cancelado</strong></p></td>
<td><p><strong>Creado</strong></p></td>
<td><p><strong>Creado</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>En proceso</strong></p></td>
<td><p><strong>Creado</strong></p></td>
<td><p><strong>Cancelado</strong></p></td>
<td><p><strong>Registrado</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Cancelado</strong></p></td>
<td><p><strong>Cancelado</strong></p></td>
<td><p><strong>Cancelado</strong></p></td>
<td><p><strong>Cancelado</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Registrado</strong></p></td>
<td><p><strong>Registrado</strong></p></td>
<td><p><strong>Registrado</strong></p></td>
<td><p><strong>Registrado</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Registrado</strong></p></td>
<td><p><strong>Registrado</strong></p></td>
<td><p><strong>Cancelado</strong></p></td>
<td><p><strong>Cancelado</strong></p></td>
</tr>
</tbody>
</table>


El progreso de un pedido de servicio será En proceso si todas las líneas tienen el estado **Creado** y también si alguna de las líneas tiene el estado **Cancelado** o **Registrado**.

Si todas las líneas de un pedido de servicio tienen el estado **Registrado**, el progreso del pedido de estado será **Registrado**. Si algunas líneas tienen el estado **Registrado** y otras el estado **Cancelado**, el progreso seguirá siendo **Registrado**.

  


