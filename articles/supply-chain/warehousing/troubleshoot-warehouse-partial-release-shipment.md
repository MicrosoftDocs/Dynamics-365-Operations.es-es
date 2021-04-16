---
title: Solucionar problemas de lanzamientos parciales y envíos parciales
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con liberaciones parciales y envíos parciales en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 5534099f81a97a1dcf4908784fd71dd03cf94eaf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828163"
---
# <a name="troubleshoot-partial-releases-and-partial-shipments"></a><span data-ttu-id="edcb6-103">Solucionar problemas de lanzamientos parciales y envíos parciales</span><span class="sxs-lookup"><span data-stu-id="edcb6-103">Troubleshoot partial releases and partial shipments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="edcb6-104">Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con liberaciones parciales y envíos parciales en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="edcb6-104">This topic describes how to fix common issues that you might encounter while you work with partial releases and partial shipments in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="the-release-status-of-a-sales-order-remains-partially-released-even-after-the-sales-order-is-invoiced"></a><span data-ttu-id="edcb6-105">El estado de liberación de un pedido de cliente permanece Liberado parcialmente incluso después de facturar el pedido de cliente.</span><span class="sxs-lookup"><span data-stu-id="edcb6-105">The release status of a sales order remains Partially released even after the sales order is invoiced.</span></span>

### <a name="issue-description"></a><span data-ttu-id="edcb6-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="edcb6-106">Issue description</span></span>

<span data-ttu-id="edcb6-107">Una orden de venta es una orden de entrega, pero uno o más artículos tienen un modo de entrega diferente.</span><span class="sxs-lookup"><span data-stu-id="edcb6-107">A sales order is a delivery order, but one or more items on it have a different mode of delivery.</span></span> <span data-ttu-id="edcb6-108">Después de facturar el pedido, todavía tiene un estado de liberación de *Liberado parcialmente*.</span><span class="sxs-lookup"><span data-stu-id="edcb6-108">After the order is invoiced, it still has a release status of *Partially released*.</span></span>

<span data-ttu-id="edcb6-109">Por ejemplo, una orden de venta tiene dos artículos: uno para entrega y otro para recolección.</span><span class="sxs-lookup"><span data-stu-id="edcb6-109">For example, a sales order has two items: one for delivery and one for pickup.</span></span> <span data-ttu-id="edcb6-110">Tanto la entrega como la recogida se han realizado.</span><span class="sxs-lookup"><span data-stu-id="edcb6-110">Both the delivery and the pickup have been done.</span></span> <span data-ttu-id="edcb6-111">Por tanto, se han facturado ambas líneas.</span><span class="sxs-lookup"><span data-stu-id="edcb6-111">Therefore, both lines have been invoiced.</span></span> <span data-ttu-id="edcb6-112">Sin embargo, el estado de la versión todavía se muestra como *Liberado parcialmente*, que es engañoso.</span><span class="sxs-lookup"><span data-stu-id="edcb6-112">However, the release status is still shown as *Partially released*, which is misleading.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="edcb6-113">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="edcb6-113">Issue resolution</span></span>

<span data-ttu-id="edcb6-114">El estado de liberación se aplica solo a las líneas de pedido donde los artículos están habilitados para la gestión del almacén.</span><span class="sxs-lookup"><span data-stu-id="edcb6-114">The release status applies only to order lines where the items are enabled for warehouse management.</span></span> <span data-ttu-id="edcb6-115">Por lo tanto, el estado de publicación sigue siendo *Liberado parcialmente* en este escenario.</span><span class="sxs-lookup"><span data-stu-id="edcb6-115">Therefore, the release status remains *Partially released* in this scenario.</span></span> <span data-ttu-id="edcb6-116">Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones.</span><span class="sxs-lookup"><span data-stu-id="edcb6-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="edcb6-117">Se podría agregar una extensión como parte del albarán y el proceso de facturación para actualizar el estado de liberación.</span><span class="sxs-lookup"><span data-stu-id="edcb6-117">An extension could be added as part of the packing slip and invoicing process to update the release status.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]