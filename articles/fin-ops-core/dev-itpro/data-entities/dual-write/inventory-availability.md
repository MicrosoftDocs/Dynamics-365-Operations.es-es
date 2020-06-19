---
title: Disponibilidad de inventario en doble escritura
description: Este tema proporciona información sobre la disponibilidad de comprobación de inventarios en doble escritura.
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
ms.openlocfilehash: dd0995eb8c70ed06cdc3c0f6a28b13b117297533
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426991"
---
# <a name="inventory-availability"></a><span data-ttu-id="27564-103">Disponibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="27564-103">Inventory availability</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="27564-104">Utilizando la disponibilidad de inventario, puede verificar su inventario antes de agregar un producto a los formularios **Presupuesto**, **Pedidos** o **Facturas** en aplicaciones basadas en modelos en Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="27564-104">Using inventory availability, you can check your inventory before you add a product into the **Quotes**, **Orders**, or **Invoices** forms in model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="27564-105">Por ejemplo, comprobar el inventario y determinar una fecha de cumplimiento es una tarea clave en el proceso [cliente potencial a efectivo](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="27564-105">For example, checking inventory and determining a fulfullment date is a key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span> <span data-ttu-id="27564-106">Si no tiene suficiente inventario, puede estimar una fecha de entrega basada en los recibos y problemas de inventario proyectados.</span><span class="sxs-lookup"><span data-stu-id="27564-106">If you don't have enough inventory, you can estimate a delivery date based on projected inventory receipts and issues.</span></span> <span data-ttu-id="27564-107">También puede verificar la información de neto no comprometido (ATP), donde puede encontrar la cantidad de ATP en el intervalo de tiempo predefinido.</span><span class="sxs-lookup"><span data-stu-id="27564-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the pre-defined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="27564-108">Inventario disponible</span><span class="sxs-lookup"><span data-stu-id="27564-108">On-hand Inventory</span></span> 

<span data-ttu-id="27564-109">En el encabezado de los formularios **Citas**, **Pedidos** o **Facturas** en Dynamics 365 Sales, se ha añadido un nuevo botón **Inventario disponible**.</span><span class="sxs-lookup"><span data-stu-id="27564-109">In the header of the **Quotes**, **Orders**, or **Invoices** forms in Dynamics 365 Sales, a new button **On-hand Inventory** is added.</span></span> <span data-ttu-id="27564-110">Cuando hace clic en el botón, aparece un cuadro de diálogo y puede especificar la empresa y el producto para el que desea comprobar el inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="27564-110">When you click the button, a dialog box appears and you can specify the company and the product for which you want to check the on-hand inventory.</span></span> <span data-ttu-id="27564-111">Devuelve la información de inventario de Dynamics 365 Supply Chain Management y muestra la misma información que [Inventario disponible](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="27564-111">It returns the inventory information from Dynamics 365 Supply Chain Management, and shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span> <span data-ttu-id="27564-112">La información incluye estas cantidades:</span><span class="sxs-lookup"><span data-stu-id="27564-112">The information includes these quantities:</span></span>

- <span data-ttu-id="27564-113">**Cantidad disponible**</span><span class="sxs-lookup"><span data-stu-id="27564-113">**On-hand Quantity**</span></span>
- <span data-ttu-id="27564-114">**Cantidad disponible reservada**</span><span class="sxs-lookup"><span data-stu-id="27564-114">**Reserved On-hand Quantity**</span></span>
- <span data-ttu-id="27564-115">**Cantidad disponible lista**</span><span class="sxs-lookup"><span data-stu-id="27564-115">**Available On-hand Quantity**</span></span>
- <span data-ttu-id="27564-116">**Cantidad pedida**</span><span class="sxs-lookup"><span data-stu-id="27564-116">**Orderd Quantity**</span></span>
- <span data-ttu-id="27564-117">**Cantidad en pedido**</span><span class="sxs-lookup"><span data-stu-id="27564-117">**On-order Quantity**</span></span>
- <span data-ttu-id="27564-118">**Cantidad solicitada reservada**</span><span class="sxs-lookup"><span data-stu-id="27564-118">**Reserved Ordered Quantity**</span></span>
- <span data-ttu-id="27564-119">**Cantidad total disponible**</span><span class="sxs-lookup"><span data-stu-id="27564-119">**Total Available Quantity**</span></span>

## <a name="atp-information"></a><span data-ttu-id="27564-120">Información de NNC</span><span class="sxs-lookup"><span data-stu-id="27564-120">ATP information</span></span>

<span data-ttu-id="27564-121">En los elementos de línea de los formularios **Citas**, **Pedidos** o **Facturas** en Dynamics 365 Sales, se ha añadido un nuevo botón **Información ATP**.</span><span class="sxs-lookup"><span data-stu-id="27564-121">On line items of the **Quotes**, **Orders**, or **Invoices** forms in Dynamics 365 Sales, a new button **ATP Information** is added.</span></span> <span data-ttu-id="27564-122">Cuando hace clic en el botón, aparece un cuadro de diálogo y puede especificar la empresa, el producto, el sitio del inventario, el almacén de inventario y la cantidad pedida.</span><span class="sxs-lookup"><span data-stu-id="27564-122">When you click the button, a dialog box appears and you can specify the company, product, inventory Site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="27564-123">Devuelve la **Información ATP** desde Supply Chain Management y muestra la configuración descrita en [Promesas de pedidos](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="27564-123">It returns the **ATP Information** from Supply Chain Management and shows the settings descrbed in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span> <span data-ttu-id="27564-124">La información incluye **Cantidad ATP**, **Cantidad de recibo**, **Cantidad emitida**y **Cantidad disponible**.</span><span class="sxs-lookup"><span data-stu-id="27564-124">The information includes **ATP quantity**, **Receipt quantity**, **Issue quantity**, and **On-hand quantity**.</span></span>
