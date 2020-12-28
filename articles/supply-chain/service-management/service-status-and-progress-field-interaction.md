---
title: Interacción del campo de progreso y estado del servicio
description: En el formulario Pedidos de servicio, el campo Progreso de la cabecera del pedido de servicio refleja el estado de todo el pedido de servicio, y el campo Estado indica el estado de líneas individuales del pedido de servicio.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a94f2df6a4ddb71a29ff951dfe38618ac7762783
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436544"
---
# <a name="service-status-and-progress-field-interaction"></a><span data-ttu-id="79358-103">Interacción del campo de progreso y estado del servicio</span><span class="sxs-lookup"><span data-stu-id="79358-103">Service status and progress field interaction</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="79358-104">En el formulario **Pedidos de servicio**, el campo **Progreso** de la cabecera del pedido de servicio refleja el estado de todo el pedido de servicio, y el campo **Estado** indica el estado de líneas individuales del pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="79358-104">In the **Service orders** form, the **Progress** field on the service order header reflects the status of the whole service order, and the **Status** reports the status of individual service order lines.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="79358-105">Progreso</span><span class="sxs-lookup"><span data-stu-id="79358-105">Progress</span></span></p></th>
<th><p><span data-ttu-id="79358-106">Estado de línea 1</span><span class="sxs-lookup"><span data-stu-id="79358-106">Line 1 Status</span></span></p></th>
<th><p><span data-ttu-id="79358-107">Estado de línea 2</span><span class="sxs-lookup"><span data-stu-id="79358-107">Line 2 Status</span></span></p></th>
<th><p><span data-ttu-id="79358-108">Estado de línea 3</span><span class="sxs-lookup"><span data-stu-id="79358-108">Line 3 Status</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79358-109"><strong>En proceso</strong></span><span class="sxs-lookup"><span data-stu-id="79358-109"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-110"><strong>Creado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-110"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-111"><strong>Creado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-111"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-112"><strong>Creado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-112"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79358-113"><strong>En proceso</strong></span><span class="sxs-lookup"><span data-stu-id="79358-113"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-114"><strong>Cancelado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-114"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-115"><strong>Creado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-115"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-116"><strong>Creado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-116"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79358-117"><strong>En proceso</strong></span><span class="sxs-lookup"><span data-stu-id="79358-117"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-118"><strong>Creado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-118"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-119"><strong>Cancelado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-119"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-120"><strong>Registrado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-120"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79358-121"><strong>Cancelado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-121"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-122"><strong>Cancelado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-122"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-123"><strong>Cancelado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-123"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-124"><strong>Cancelado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-124"><strong>Canceled</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79358-125"><strong>Registrado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-125"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-126"><strong>Registrado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-126"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-127"><strong>Registrado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-127"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-128"><strong>Registrado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-128"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79358-129"><strong>Registrado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-129"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-130"><strong>Registrado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-130"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-131"><strong>Cancelado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-131"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="79358-132"><strong>Cancelado</strong></span><span class="sxs-lookup"><span data-stu-id="79358-132"><strong>Canceled</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="79358-133">El progreso de un pedido de servicio será En proceso si todas las líneas tienen el estado **Creado** y también si alguna de las líneas tiene el estado **Cancelado** o **Registrado**.</span><span class="sxs-lookup"><span data-stu-id="79358-133">The progress of a service order is in process if all lines have the status **Created**; it is still in process if some of the lines have a status of **Canceled** or **Posted**.</span></span>

<span data-ttu-id="79358-134">Si todas las líneas de un pedido de servicio tienen el estado **Registrado**, el progreso del pedido de estado será **Registrado**.</span><span class="sxs-lookup"><span data-stu-id="79358-134">If all lines in a service order are marked as **Posted**, the progress of the status order is **Posted**.</span></span> <span data-ttu-id="79358-135">Si algunas líneas tienen el estado **Registrado** y otras el estado **Cancelado**, el progreso seguirá siendo **Registrado**.</span><span class="sxs-lookup"><span data-stu-id="79358-135">If some lines are **Posted** and some are **Canceled**, the progress is still **Posted**.</span></span>

  


