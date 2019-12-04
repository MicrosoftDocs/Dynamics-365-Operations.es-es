---
title: Incluir valor físico en coste
description: Use la casilla Incluir valor físico en coste de la ficha desplegable Modelo de inventario del formulario Grupos de modelos de artículo se utiliza para especificar si las transacciones actualizadas físicamente se incluyen en el cálculo del precio de coste promedio móvil del artículo.
author: AndersGirke
manager: AnnBe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 834438f8389e295bbb992f0b8397ff45559690c3
ms.sourcegitcommit: 92322167f57b66d2accc134aaf862e6b9931ec94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "2693006"
---
# <a name="include-physical-value"></a><span data-ttu-id="c16ae-103">Incluir valor físico en coste</span><span class="sxs-lookup"><span data-stu-id="c16ae-103">Include physical value</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c16ae-104">Use la casilla Incluir valor físico en coste de la ficha desplegable Modelo de inventario del formulario Grupos de modelos de artículo se utiliza para especificar si las transacciones actualizadas físicamente se incluyen en el cálculo del precio de coste promedio móvil del artículo.</span><span class="sxs-lookup"><span data-stu-id="c16ae-104">You use the Include physical value check box on the Inventory model FastTab of the Item model groups page to specify whether physically updated transactions are considered when the running average cost price is calculated for an item.</span></span>

<span data-ttu-id="c16ae-105">La casilla **Incluir valor físico** tiene los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="c16ae-105">The **Include physical value** check box has the following values.</span></span>

| <span data-ttu-id="c16ae-106">Valor</span><span class="sxs-lookup"><span data-stu-id="c16ae-106">Value</span></span>    | <span data-ttu-id="c16ae-107">Resultado</span><span class="sxs-lookup"><span data-stu-id="c16ae-107">Result</span></span>                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="c16ae-108">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="c16ae-108">Selected</span></span> | <span data-ttu-id="c16ae-109">Tanto las transacciones actualizadas físicamente como las actualizadas financieramente se usarán para calcular el precio de coste promedio móvil.</span><span class="sxs-lookup"><span data-stu-id="c16ae-109">Both physically updated transactions and financially updated transactions are used to calculate the running average cost price.</span></span> |
| <span data-ttu-id="c16ae-110">Desactivada</span><span class="sxs-lookup"><span data-stu-id="c16ae-110">Cleared</span></span>  | <span data-ttu-id="c16ae-111">Sólo se usarán las transacciones actualizadas financieramente para calcular el precio de coste promedio móvil.</span><span class="sxs-lookup"><span data-stu-id="c16ae-111">Only financially updated transactions are used to calculate the running average cost price.</span></span>                                     |

<span data-ttu-id="c16ae-112">La casilla tiene efectos ligeramente diferentes, en función del modelo de inventario que use.</span><span class="sxs-lookup"><span data-stu-id="c16ae-112">The check box has slightly different effects, depending on the inventory model that you use.</span></span>

-   <span data-ttu-id="c16ae-113">Si se activa la casilla de verificación **Incluir valor físico en coste** cuando se usa el modelo de inventario de fecha FIFO (primero en entrar, primero en salir), LIFO (el último en entrar es el primero en salir) o Fecha LIFO, el cierre de inventario también realiza ajustes en las transacciones actualizadas físicamente.</span><span class="sxs-lookup"><span data-stu-id="c16ae-113">If you select the **Include physical value** check box when you use the FIFO (First in, first out), LIFO (Last in, first out), or LIFO date inventory model, inventory close also makes adjustments to physically updated transactions.</span></span>
-   <span data-ttu-id="c16ae-114">Si no se activa la casilla de verificación **Incluir valor físico en coste** cuando se usan estos modelos de inventario, el cierre de inventario realiza liquidaciones únicamente en las transacciones actualizadas financieramente.</span><span class="sxs-lookup"><span data-stu-id="c16ae-114">If you don't select the **Include physical value** check box when you use these inventory models, inventory close makes settlements only to financially updated transactions.</span></span>
-   <span data-ttu-id="c16ae-115">Al usar el modelo de inventario de media ponderada o de fecha media ponderada, el cierre de inventario liquida únicamente las transacciones actualizadas financieramente, independientemente de si se activa la casilla de verificación **Incluir valor físico en coste**.</span><span class="sxs-lookup"><span data-stu-id="c16ae-115">When you use the weighted average or weighted average date inventory model, inventory close settles only financially updated transactions, regardless of whether you select the **Include physical value** check box.</span></span>

<span data-ttu-id="c16ae-116">**Ejemplo 1** Ha activado la casilla**Incluir valor físico en coste** y recibido los siguientes pedidos de compra:</span><span class="sxs-lookup"><span data-stu-id="c16ae-116">**Example 1** You've selected the **Include physical value** check box and receive the following purchase orders:</span></span>

-   <span data-ttu-id="c16ae-117">Se ha actualizado el albarán para un pedido de compra para una cantidad de 2 y un precio de coste de 10,00 dólares.</span><span class="sxs-lookup"><span data-stu-id="c16ae-117">A purchase order for a quantity of 2 and a cost price of USD 10.00 that has been packing slip–updated.</span></span>
-   <span data-ttu-id="c16ae-118">Se ha actualizado la factura para un pedido de compra para una cantidad de 3 y un precio de coste de 12,00 dólares.</span><span class="sxs-lookup"><span data-stu-id="c16ae-118">A purchase order for a quantity of 3 and a cost price of USD 12.00 that has been invoice-updated.</span></span>

<span data-ttu-id="c16ae-119">En este caso, el precio de coste promedio móvil será de 11,20 USD = (2x10+3x12)/(2+3), ya que se usan transacciones actualizadas tanto física como financieramente para calcular el precio de coste.</span><span class="sxs-lookup"><span data-stu-id="c16ae-119">In this case, the running average cost price will be USD 11.20 = (2x10+3x12)/(2+3), because both physically updated transactions and financially updated transactions are used to calculate the cost price.</span></span> 

<span data-ttu-id="c16ae-120">**Ejemplo 2** No ha activado la casilla de verificación **Incluir valor físico en coste** y el precio de coste en la configuración del artículo es de 10,00 USD.</span><span class="sxs-lookup"><span data-stu-id="c16ae-120">**Example 2** You haven't selected the **Include physical value** check box, and the cost price on the item setup is USD 10.00.</span></span> 

-   <span data-ttu-id="c16ae-121">Recibe un pedido de compra para una cantidad de 20 y un precio de coste de 12,00 dólares del que se ha actualizado el albarán.</span><span class="sxs-lookup"><span data-stu-id="c16ae-121">You receive a purchase order for a quantity of 20 and a cost price of USD 12.00 that has been packing slip–updated.</span></span>

<span data-ttu-id="c16ae-122">Cuando se registre un pedido de ventas, se registrará un importe de coste de 10,00 USD, ya que el precio de coste promedio móvil no incluirá las transacciones actualizadas físicamente.</span><span class="sxs-lookup"><span data-stu-id="c16ae-122">When a sales order is posted, the posted cost amount is USD 10.00, because the running average cost price won't include physically posted transactions.</span></span> 

> [!NOTE]
> <span data-ttu-id="c16ae-123">A modo de comparación, si activa la casilla **Incluir valor físico** para este artículo, cuando se registre un pedido de ventas, el importe de coste registrado será 12,00 USD.</span><span class="sxs-lookup"><span data-stu-id="c16ae-123">For comparison, if you select the **Include physical value** check box for this item, when a sales order is posted, the posted cost amount will be USD 12.00.</span></span>
