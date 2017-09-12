---
title: Reserva del mismo lote para un pedido de ventas
description: "Este artículo explica cómo configurar un producto para permitir la reserva de inventario con un único lote de inventario."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 8e0f8f85609e7c3095f13738d43cdf5734018eaa
ms.contentlocale: es-es
ms.lasthandoff: 07/18/2017

---

# <a name="reserve-the-same-batch-for-a-sales-order"></a><span data-ttu-id="3abe0-103">Reserva del mismo lote para un pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="3abe0-103">Reserve the same batch for a sales order</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="3abe0-104">Este artículo explica cómo configurar un producto para permitir la reserva de inventario con un único lote de inventario.</span><span class="sxs-lookup"><span data-stu-id="3abe0-104">This article explains how to set up a product to allow reservation of inventory against a single batch of inventory.</span></span>

<span data-ttu-id="3abe0-105">La reserva del mismo lote le permite reservar inventario de una línea del pedido de ventas de un único lote del inventario.</span><span class="sxs-lookup"><span data-stu-id="3abe0-105">Same batch reservation lets you reserve inventory for a sales order line against a single batch of inventory.</span></span> <span data-ttu-id="3abe0-106">Por ejemplo, un cliente que realiza un pedido de papel pintado puede solicitar que todo el pedido se abastezca desde el mismo lote para evitar incoherencias entre los rollos de papel.</span><span class="sxs-lookup"><span data-stu-id="3abe0-106">For example, a customer who orders wallpaper can request that the whole order be filled from the same batch or lot, to avoid inconsistencies among the rolls.</span></span> <span data-ttu-id="3abe0-107">Para configurar un producto para usar la reserva del mismo lote, deben haberse activado los siguientes ajustes en el grupo de modelos de artículos, el grupo de dimensiones de seguimiento y el grupo de dimensiones de almacenamiento que se asigne al producto:</span><span class="sxs-lookup"><span data-stu-id="3abe0-107">To set up a product to use same batch reservation, the following settings must be active in the item model group, tracking dimension group, and storage dimension group that you assign to the product:</span></span>

-   <span data-ttu-id="3abe0-108">**Grupos de modelos de artículo**: el grupo de modelos de artículo debe tener los campos **Selección del mismo lote** y **Consolidar requisito** seleccionados en el grupo de campos **Reserva** para las directivas de inventario.</span><span class="sxs-lookup"><span data-stu-id="3abe0-108">**Item model groups** – The item model group must have the **Same batch selection** and **Consolidate requirement** fields selected in the **Reservation** field group for inventory policies.</span></span>
-   <span data-ttu-id="3abe0-109">**Grupo de dimensiones de seguimiento**: este grupo debe tener el campo **Plan de cobertura por dimensión** seleccionado para el número de lote.</span><span class="sxs-lookup"><span data-stu-id="3abe0-109">**Tracking dimensions groups** – The tracking dimension group must have the **Coverage plan by dimension** field selected for the batch number.</span></span>
-   <span data-ttu-id="3abe0-110">**Grupo de dimensiones de almacenamiento**: este grupo debe tener el campo **Plan de cobertura por dimensión** seleccionado para **Sitio** y **Almacén**.</span><span class="sxs-lookup"><span data-stu-id="3abe0-110">**Storage dimensions groups** – The storage dimension group must have the **Coverage plan by dimension** field selected for **Site** and **Warehouse**.</span></span>

<span data-ttu-id="3abe0-111">Al reservar inventario para un producto en una línea de pedido de ventas configurada para la selección del mismo lote, Microsoft Dynamics 365 for Finance and Operations intenta reservar la cantidad pedida desde un único lote de inventario.</span><span class="sxs-lookup"><span data-stu-id="3abe0-111">When you reserve inventory for a product on a sales order line that is set up for same batch selection, Microsoft Dynamics 365 for Finance and Operations tries to reserve the ordered quantity from a single inventory batch.</span></span> <span data-ttu-id="3abe0-112">También se tienen en cuenta los requisitos de atributo de lote específicos.</span><span class="sxs-lookup"><span data-stu-id="3abe0-112">Any specific batch attribute requirements are also considered.</span></span> <span data-ttu-id="3abe0-113">Si la cantidad no se puede rellenar desde un único lote, aparecerá la página **Conflicto de reserva del mismo lote**.</span><span class="sxs-lookup"><span data-stu-id="3abe0-113">If the quantity can't be filled from a single batch, the **Same batch reservation conflict** page appears.</span></span> <span data-ttu-id="3abe0-114">Esta página describe las emisiones y también las acciones que puede realizar para continuar con la reserva.</span><span class="sxs-lookup"><span data-stu-id="3abe0-114">This page describes the issues and also the actions that you can take to continue with the reservation.</span></span> <span data-ttu-id="3abe0-115">Las siguientes condiciones podrían impedir la reserva del lote:</span><span class="sxs-lookup"><span data-stu-id="3abe0-115">The following conditions might prevent the batch from being reserved:</span></span>

-   <span data-ttu-id="3abe0-116">El código de disposición del lote tiene **Bloquear reserva** para las ventas marcado como **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="3abe0-116">The batch disposition code has **Block reservation** for sales flagged as **Blocked**.</span></span>
-   <span data-ttu-id="3abe0-117">El lote ha caducado según la fecha de vencimiento y los días para ventas al cliente aplicables.</span><span class="sxs-lookup"><span data-stu-id="3abe0-117">The batch has expired, based on the expiration date and any applicable customer sellable days.</span></span> <span data-ttu-id="3abe0-118">El artículo aún se podrá reservar si el grupo de modelos de artículo está controlado por fecha FEFO y se selecciona la fecha de consumo preferente como criterio de selección.</span><span class="sxs-lookup"><span data-stu-id="3abe0-118">The item can still be considered for reservation if the item model group for the item is First Expiry First Out (FEFO) date–controlled, and if the best-before date is selected as the pick criterion.</span></span>
-   <span data-ttu-id="3abe0-119">El lote no tiene suficientes días de vida útil restantes según la fecha de caducidad/consumo preferente y los días para ventas al cliente.</span><span class="sxs-lookup"><span data-stu-id="3abe0-119">The batch doesn't have enough shelf-life days remaining, based on the expiration date and best-before date, plus any customer sellable days.</span></span>





