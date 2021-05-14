---
title: Utilizar el motor de precios de Dynamics 365 Commerce con Dynamics 365 Sales
description: Este tema describe cómo usar el motor de precios de Microsoft Dynamics 365 Commerce para crear presupuestos de ventas en Dynamics 365 Sales.
author: ShalabhjainMSFT
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: shajain
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-11-03
ms.openlocfilehash: fa93b1262049d80148ff23b3d7223ec0f6c2fe68
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941175"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a><span data-ttu-id="c9e45-103">Utilizar el motor de precios de Dynamics 365 Commerce con Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="c9e45-103">Use the Dynamics 365 Commerce pricing engine with Dynamics 365 Sales</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c9e45-104">Este tema describe cómo usar el motor de precios de Microsoft Dynamics 365 Commerce para crear presupuestos de ventas en Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="c9e45-104">This topic describes how to use the Microsoft Dynamics 365 Commerce pricing engine to create sales quotations in Dynamics 365 Sales.</span></span>

<span data-ttu-id="c9e45-105">El motor de precios de Dynamics 365 Commerce es compatible con la mayoría de los escenarios de precios de empresa a consumidor (B2C), como precios a nivel de tienda, precios basados en afiliación y lealtad, descuentos combinados, descuentos por cantidad y descuentos por umbral.</span><span class="sxs-lookup"><span data-stu-id="c9e45-105">The Dynamics 365 Commerce pricing engine supports most business-to-consumer (B2C) pricing scenarios, such as store-level pricing, affiliation-based and loyalty-based pricing, mix-and-match discounts, quantity discounts, and threshold discounts.</span></span> <span data-ttu-id="c9e45-106">El motor de fijación de precios utiliza reglas complejas para determinar el mejor precio para un presupuesto o pedido determinado.</span><span class="sxs-lookup"><span data-stu-id="c9e45-106">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span>

<span data-ttu-id="c9e45-107">Cuando usa [escritura dual](./dual-write-overview.md), tiene tres opciones para sus necesidades de precios.</span><span class="sxs-lookup"><span data-stu-id="c9e45-107">When you use [dual-write](./dual-write-overview.md), you have three options for your pricing needs.</span></span> <span data-ttu-id="c9e45-108">Puede usar el precio estático que proviene de la lista de precios en Dynamics 365 Sales, el motor de precios en Dynamics 365 Supply Chain Management o el motor de precios en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c9e45-108">You can use the static pricing that comes from the price list in Dynamics 365 Sales, the pricing engine in Dynamics 365 Supply Chain Management, or the pricing engine in Dynamics 365 Commerce.</span></span> <span data-ttu-id="c9e45-109">Entre estas opciones, el motor de precios de Commerce se adapta mejor a los escenarios B2C.</span><span class="sxs-lookup"><span data-stu-id="c9e45-109">Among these options, the Commerce pricing engine is best suited to B2C scenarios.</span></span>

## <a name="use-the-commerce-pricing-engine-in-sales"></a><span data-ttu-id="c9e45-110">Utilice el motor de precios de Commerce en Sales</span><span class="sxs-lookup"><span data-stu-id="c9e45-110">Use the Commerce pricing engine in Sales</span></span>

> [!NOTE]
> <span data-ttu-id="c9e45-111">Actualmente, el motor de precios de Commerce solo se puede utilizar para la creación de cotizaciones en Sales.</span><span class="sxs-lookup"><span data-stu-id="c9e45-111">Currently, the Commerce pricing engine can be used only for quotation creation in the Sales.</span></span> <span data-ttu-id="c9e45-112">La integración de pedidos de venta con el motor de precios de Commerce aún no está disponible.</span><span class="sxs-lookup"><span data-stu-id="c9e45-112">Sales order integration with the Commerce pricing engine isn't yet available.</span></span>

<span data-ttu-id="c9e45-113">Cuando los usuarios inician una cotización en Sales, el marco de escritura dual copia los detalles de la cotización a Commerce.</span><span class="sxs-lookup"><span data-stu-id="c9e45-113">When users initiate a quotation in Sales, the dual-write framework copies the quotation details to Commerce.</span></span> <span data-ttu-id="c9e45-114">Cualquier cambio en las líneas de cotización existentes o cualquier línea de presupuesto recién agregada en Sales se copia en Commerce.</span><span class="sxs-lookup"><span data-stu-id="c9e45-114">Any changes to existing quotation lines or any newly added quotation lines in Sales are copied to Commerce.</span></span> <span data-ttu-id="c9e45-115">Cuando los usuarios quieran utilizar el motor de precios de Commerce para fijar el precio de la cotización, pueden seleccionar **Presupuesto de precio** para actualizar los precios del presupuesto, según el motor de precios de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c9e45-115">When users want to use the Commerce pricing engine to price the quotation, they can select **Price quote** to update the prices of the quotation, based on the Commerce pricing engine.</span></span> <span data-ttu-id="c9e45-116">Los precios se actualizan automáticamente tanto en Sales como en Commerce.</span><span class="sxs-lookup"><span data-stu-id="c9e45-116">Prices are then automatically updated in both Sales and Commerce.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c9e45-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c9e45-117">Prerequisites</span></span>

- <span data-ttu-id="c9e45-118">Antes de poder utilizar el motor de precios de Commerce en Sales , debe seguir los pasos en [Cliente potencial a efectivo en escritura dual](./dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="c9e45-118">Before you can use the Commerce pricing engine in Sales, you must follow the steps in [Prospect-to-cash in dual-write](./dual-write-prospect-to-cash.md).</span></span>
- <span data-ttu-id="c9e45-119">Debe desactivar la evaluación de acuerdos comerciales para la entrada manual siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c9e45-119">You must turn off trade agreement evaluation for manual entry by following these steps:</span></span>

    1. <span data-ttu-id="c9e45-120">En su entorno de Commerce vaya a **Clientes \> Configuración \> Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="c9e45-120">In your Commerce environment, go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
    1. <span data-ttu-id="c9e45-121">En la pestaña **Precios**, en la ficha desplegable **Evaluación de acuerdos comerciales**, borre la casilla de verificación **Entrada manual**.</span><span class="sxs-lookup"><span data-stu-id="c9e45-121">On the **Prices** tab, on the **Trade agreement evaluation** FastTab, clear the **Manual entry** check box.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c9e45-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c9e45-122">Additional resources</span></span>

[<span data-ttu-id="c9e45-123">Cliente potencial a efectivo en doble escritura</span><span class="sxs-lookup"><span data-stu-id="c9e45-123">Prospect-to-cash in dual-write</span></span>](./dual-write-prospect-to-cash.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]