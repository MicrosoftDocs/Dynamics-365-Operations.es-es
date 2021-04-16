---
title: Descripciones predeterminadas para el libro mayor
description: Las descripciones predeterminadas se pueden utilizar para actualizar el campo Descripción en las contabilizaciones de comprobantes en el libro mayor.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: d5a38af57d614ae2c93b0af74ec4a1c085519d46
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841914"
---
# <a name="default-descriptions-for-the-general-ledger"></a><span data-ttu-id="770ed-103">Descripciones predeterminadas para el libro mayor</span><span class="sxs-lookup"><span data-stu-id="770ed-103">Default descriptions for the general ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="770ed-104">Las descripciones predeterminadas se pueden utilizar para actualizar el campo **Descripción** en las contabilizaciones de comprobantes en el libro mayor.</span><span class="sxs-lookup"><span data-stu-id="770ed-104">Default descriptions can be used to update the **Description** field in voucher postings to the general ledger.</span></span> <span data-ttu-id="770ed-105">Esta funcionalidad se ha mejorado para que funcione con el costo de aterrizaje.</span><span class="sxs-lookup"><span data-stu-id="770ed-105">This functionality has been enhanced to work with Landed cost.</span></span>

<span data-ttu-id="770ed-106">Para configurar descripciones predeterminadas para las contabilizaciones del libro mayor, vaya a **Administración organizacional \> Configuración \> Descripciones predeterminadas**.</span><span class="sxs-lookup"><span data-stu-id="770ed-106">To set up default descriptions for ledger postings, go to **Organizational administration \> Setup \> Default descriptions**.</span></span>

<span data-ttu-id="770ed-107">La siguiente tabla enumera los nuevos valores que se han agregado para el campo **Descripción** en la página **Descripciones predeterminadas** para respaldar el costo de aterrizaje.</span><span class="sxs-lookup"><span data-stu-id="770ed-107">The following table lists the new values that have been added for the **Description** field on the **Default descriptions** page to support Landed cost.</span></span>

| <span data-ttu-id="770ed-108">Tipo de descripción</span><span class="sxs-lookup"><span data-stu-id="770ed-108">Description type</span></span> | <span data-ttu-id="770ed-109">Notas</span><span class="sxs-lookup"><span data-stu-id="770ed-109">Notes</span></span> |
|---|---|
| <span data-ttu-id="770ed-110">Gestión de costes de importación: acumulación de costes</span><span class="sxs-lookup"><span data-stu-id="770ed-110">Import costing – Cost accrual</span></span> | <span data-ttu-id="770ed-111">Cuando se registra una factura de orden de compra, se procesa una acumulación de costos para estimar los costos del viaje.</span><span class="sxs-lookup"><span data-stu-id="770ed-111">When a purchase order invoice is posted, a cost accrual is processed for estimate voyage costs.</span></span> <span data-ttu-id="770ed-112">Se pueden especificar descripciones predeterminadas para agregar el número de viaje a la descripción.</span><span class="sxs-lookup"><span data-stu-id="770ed-112">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="770ed-113">Use *%4* para el número de envío.</span><span class="sxs-lookup"><span data-stu-id="770ed-113">Use *%4* for the shipment number.</span></span> |
| <span data-ttu-id="770ed-114">Gestión de costes de importación: pedido de mercancía en tránsito</span><span class="sxs-lookup"><span data-stu-id="770ed-114">Import costing – Goods in transit order</span></span> | <span data-ttu-id="770ed-115">Si utiliza el procesamiento en tránsito, se registra la factura de la orden de compra y las mercancías se registran en una cuenta de mercancías en tránsito.</span><span class="sxs-lookup"><span data-stu-id="770ed-115">If you're using in-transit processing, the purchase order invoice is posted, and the goods are posted to a goods in transit account.</span></span> <span data-ttu-id="770ed-116">Se pueden especificar descripciones predeterminadas para agregar el número de pedido en tránsito a la descripción.</span><span class="sxs-lookup"><span data-stu-id="770ed-116">Default descriptions can be specified to add the in-transit order number to the description.</span></span> <span data-ttu-id="770ed-117">Use *%4* para el número de pedido en tránsito.</span><span class="sxs-lookup"><span data-stu-id="770ed-117">Use *%4* for the in-transit order number.</span></span> |
| <span data-ttu-id="770ed-118">Inventario - cierre - ajuste</span><span class="sxs-lookup"><span data-stu-id="770ed-118">Inventory – close – adjustment</span></span> | <span data-ttu-id="770ed-119">Cuando se procesa la factura de cuentas por pagar (AP) para un costo de viaje, se procesa un ajuste de inventario para estimar los costos de viaje.</span><span class="sxs-lookup"><span data-stu-id="770ed-119">When the accounts payable (AP) invoice is processed for a voyage cost, an inventory adjustment is processed to estimate voyage costs.</span></span> <span data-ttu-id="770ed-120">Se pueden especificar descripciones predeterminadas para agregar el número de viaje a la descripción.</span><span class="sxs-lookup"><span data-stu-id="770ed-120">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="770ed-121">Use *%4* para el número de envío.</span><span class="sxs-lookup"><span data-stu-id="770ed-121">Use *%4* for the shipment number.</span></span> |

<span data-ttu-id="770ed-122">Para obtener más información sobre cómo trabajar con la página **Descripciones predeterminadas**, vea [Configurar descripciones predeterminadas para la publicación automática](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span><span class="sxs-lookup"><span data-stu-id="770ed-122">For more information about how to work with the **Default descriptions** page, see [Set up default descriptions for automatic posting](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span></span>
