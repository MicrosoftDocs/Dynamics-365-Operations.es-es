---
title: El producto está en espera para las transacciones
description: Después de confirmar los pedidos de planificación, recibe un mensaje de error que indica que un artículo está en espera para transacciones.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6654e6437a088218db116b955631be4c7e62de5f
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301288"
---
# <a name="product-is-on-hold-for-transactions"></a><span data-ttu-id="04c4a-103">El producto está en espera para las transacciones</span><span class="sxs-lookup"><span data-stu-id="04c4a-103">Product is on hold for transactions</span></span>

<span data-ttu-id="04c4a-104">Código de error: SYS13295</span><span class="sxs-lookup"><span data-stu-id="04c4a-104">Error code: SYS13295</span></span>

## <a name="symptoms"></a><span data-ttu-id="04c4a-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="04c4a-105">Symptoms</span></span>

<span data-ttu-id="04c4a-106">Después de confirmar pedidos planificados, recibe el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="04c4a-106">After you firm planned orders, you receive the following error message:</span></span>

> <span data-ttu-id="04c4a-107">El artículo %1 está en bloqueo para transacciones en %2.</span><span class="sxs-lookup"><span data-stu-id="04c4a-107">Item %1 is on hold for transactions in %2.</span></span>

## <a name="cause"></a><span data-ttu-id="04c4a-108">Causa</span><span class="sxs-lookup"><span data-stu-id="04c4a-108">Cause</span></span>

<span data-ttu-id="04c4a-109">Al describir los artículos bloqueados, el sistema utiliza los términos *obstruido*, *detenido* y *en espera* indistintamente.</span><span class="sxs-lookup"><span data-stu-id="04c4a-109">When describing blocked items, system uses the terms *blocked*, *stopped*, and *on hold* interchangeably.</span></span> <span data-ttu-id="04c4a-110">Este error significa que el elemento está configurado como **Detenido** en su configuración de orden predeterminada.</span><span class="sxs-lookup"><span data-stu-id="04c4a-110">This error means that the item is set as **Stopped** in its default order settings.</span></span>

<span data-ttu-id="04c4a-111">Si un artículo está bloqueado y lo agrega a una orden de compra o una línea de orden de venta, recibirá un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="04c4a-111">If an item is blocked, and you add it to a purchase order or sales order line, you receive a warning message.</span></span> <span data-ttu-id="04c4a-112">Si un artículo está bloqueado, las transacciones de inventario relacionadas con la línea del pedido de compra o ventas no se pueden modificar (por ejemplo, al registrar un albarán o una factura).</span><span class="sxs-lookup"><span data-stu-id="04c4a-112">When an item is blocked, inventory transactions that are related to the purchase order or sales order line can't be modified (for example, when you post a packing slip or an invoice).</span></span> <span data-ttu-id="04c4a-113">Puede bloquear un artículo adquirido y venderlo de manera simultánea.</span><span class="sxs-lookup"><span data-stu-id="04c4a-113">You can block a purchased item, and, at the same time, sell the item.</span></span> <span data-ttu-id="04c4a-114">En ese caso, la casilla **Detenido** se selecciona en un pedido de compra, pero el artículo no se bloquea en el inventario ni en el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="04c4a-114">In this case, the **Stopped** check box is selected on a purchase order, but the item isn't blocked in inventory or on a sales order.</span></span>

<span data-ttu-id="04c4a-115">Estas son algunas de las condiciones que pueden hacer que se bloquee la venta de un número de artículo:</span><span class="sxs-lookup"><span data-stu-id="04c4a-115">Here are some of the conditions that can cause an item number to be blocked from being sold:</span></span>

- <span data-ttu-id="04c4a-116">El artículo aún está en desarrollo o fabricación.</span><span class="sxs-lookup"><span data-stu-id="04c4a-116">The item is still under development or manufacture.</span></span> <span data-ttu-id="04c4a-117">Por lo tanto, no desea que se venda ni se reserve.</span><span class="sxs-lookup"><span data-stu-id="04c4a-117">Therefore, you don't want it to be sold or reserved.</span></span>
- <span data-ttu-id="04c4a-118">Ha recibido muchos artículos defectuosos y los defectos deben corregirse antes de que el artículo pueda venderse.</span><span class="sxs-lookup"><span data-stu-id="04c4a-118">You've received many defective items, and the defects must be corrected before the item can be sold.</span></span>

<span data-ttu-id="04c4a-119">En casos como este, puede bloquear el artículo hasta que se resuelva el problema.</span><span class="sxs-lookup"><span data-stu-id="04c4a-119">In cases of this type, you can block the item until the issue is resolved.</span></span>

<span data-ttu-id="04c4a-120">Si un artículo está bloqueado y crea una línea de pedido de devolución, recibe un mensaje.</span><span class="sxs-lookup"><span data-stu-id="04c4a-120">If an item is blocked, and you create a return order line, you receive a message.</span></span> <span data-ttu-id="04c4a-121">No puede bloquear una serie o un lote de un artículo.</span><span class="sxs-lookup"><span data-stu-id="04c4a-121">You can't block a series or a lot of an item.</span></span> <span data-ttu-id="04c4a-122">Si debe bloquear partes del artículo, puede hacerlo moviendo el inventario o bloqueando todas las existencias del artículo durante este período.</span><span class="sxs-lookup"><span data-stu-id="04c4a-122">If parts of an item must be blocked, you can block them by moving inventory or by blocking the full stock of the item for that period.</span></span>

## <a name="resolution"></a><span data-ttu-id="04c4a-123">Resolución</span><span class="sxs-lookup"><span data-stu-id="04c4a-123">Resolution</span></span>

- <span data-ttu-id="04c4a-124">Abra la página **Configuración de orden predeterminada** del elemento y borre la casilla **Detenido**.</span><span class="sxs-lookup"><span data-stu-id="04c4a-124">Open the **Default order settings** page for the item, and clear the **Stopped** checkbox.</span></span>
