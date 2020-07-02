---
title: Disponibilidad de inventario en doble escritura
description: Este tema proporciona información sobre cómo comprobar la disponibilidad de inventarios en doble escritura.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 227a2062a7985a787f8278c196f7df2fb6f31691
ms.sourcegitcommit: cf709f1421a0bf66ecea493088ecb4eb08004187
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2020
ms.locfileid: "3443881"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="bf4fb-103">Disponibilidad de inventario en doble escritura</span><span class="sxs-lookup"><span data-stu-id="bf4fb-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bf4fb-104">Al utilizar la disponibilidad de inventario, puede verificar su inventario antes de agregar un producto a las páginas **Presupuestos**, **Pedidos** o **Facturas** en aplicaciones en Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="bf4fb-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations**, **Orders**, or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="bf4fb-105">Por ejemplo, comprueba el inventario y determina una fecha de cumplimiento como una tarea clave en el proceso [cliente potencial a efectivo](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="bf4fb-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="bf4fb-106">Si no tiene suficiente inventario, puede estimar una fecha de entrega basada en los recibos y problemas de inventario proyectados.</span><span class="sxs-lookup"><span data-stu-id="bf4fb-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="bf4fb-107">También puede verificar la información de neto no comprometido (ATP), donde puede encontrar la cantidad de ATP en el intervalo de tiempo predefinido.</span><span class="sxs-lookup"><span data-stu-id="bf4fb-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="bf4fb-108">Inventario disponible</span><span class="sxs-lookup"><span data-stu-id="bf4fb-108">On-hand inventory</span></span>

<span data-ttu-id="bf4fb-109">En Dynamics 365 Sales, se ha agregado un nuevo botón **Inventario disponible** al encabezado de las páginas **Presupuestos**, **Pedidos** y **Facturas**.</span><span class="sxs-lookup"><span data-stu-id="bf4fb-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="bf4fb-110">Cuando selecciona este botón, aparece un cuadro de diálogo, donde puede especificar la empresa y el producto para el que desea comprobar el inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="bf4fb-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="bf4fb-111">Este cuadro de diálogo muestra la misma información que [Inventario disponible](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="bf4fb-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="bf4fb-112">El cuadro de diálogo devuelve la información de inventario desde Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bf4fb-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="bf4fb-113">Esta información incluye las siguientes cantidades:</span><span class="sxs-lookup"><span data-stu-id="bf4fb-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="bf4fb-114">Cantidad disponible</span><span class="sxs-lookup"><span data-stu-id="bf4fb-114">On-hand quantity</span></span>
- <span data-ttu-id="bf4fb-115">Cantidad disponible reservada</span><span class="sxs-lookup"><span data-stu-id="bf4fb-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="bf4fb-116">Cantidad disponible lista</span><span class="sxs-lookup"><span data-stu-id="bf4fb-116">Available on-hand quantity</span></span>
- <span data-ttu-id="bf4fb-117">Cantidad pedida</span><span class="sxs-lookup"><span data-stu-id="bf4fb-117">Ordered quantity</span></span>
- <span data-ttu-id="bf4fb-118">Cantidad en pedido</span><span class="sxs-lookup"><span data-stu-id="bf4fb-118">On-order quantity</span></span>
- <span data-ttu-id="bf4fb-119">Cantidad solicitada reservada</span><span class="sxs-lookup"><span data-stu-id="bf4fb-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="bf4fb-120">Cantidad total disponible</span><span class="sxs-lookup"><span data-stu-id="bf4fb-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="bf4fb-121">Información de NNC</span><span class="sxs-lookup"><span data-stu-id="bf4fb-121">ATP information</span></span>

<span data-ttu-id="bf4fb-122">En Sales, se ha agregado un nuevo botón **Información de NNC** a los artículos de línea en las páginas **Presupuestos**, **Pedidos** y **Facturas**.</span><span class="sxs-lookup"><span data-stu-id="bf4fb-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="bf4fb-123">Cuando selecciona este botón, aparece un cuadro de diálogo, donde puede especificar la empresa, el producto, el sitio del inventario, el almacén de inventario y la cantidad pedida.</span><span class="sxs-lookup"><span data-stu-id="bf4fb-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="bf4fb-124">Este cuadro de diálogo tiene la misma configuración que se describe en [Compromisos de pedido](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="bf4fb-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="bf4fb-125">El cuadro de diálogo devuelve la información de NNC de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bf4fb-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="bf4fb-126">Esta información incluye las siguientes cantidades:</span><span class="sxs-lookup"><span data-stu-id="bf4fb-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="bf4fb-127">Cantidad de NNC</span><span class="sxs-lookup"><span data-stu-id="bf4fb-127">ATP quantity</span></span>
- <span data-ttu-id="bf4fb-128">Cantidad de recepción</span><span class="sxs-lookup"><span data-stu-id="bf4fb-128">Receipt quantity</span></span>
- <span data-ttu-id="bf4fb-129">Cantidad de emisión</span><span class="sxs-lookup"><span data-stu-id="bf4fb-129">Issue quantity</span></span>
- <span data-ttu-id="bf4fb-130">Cantidad disponible</span><span class="sxs-lookup"><span data-stu-id="bf4fb-130">On-hand quantity</span></span>
