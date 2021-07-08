---
title: El artículo no puede tener una lista de materiales ni una fórmula
description: Cuando intenta confirmar un pedido, recibe un mensaje de error durante la validación del artículo. Establece que el artículo no puede tener una lista de materiales (BOM) o una fórmula.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6739b8b1e4d080055a2a0501427eac1c2e8a96c5
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294173"
---
# <a name="item-cant-have-a-bom-or-formula"></a><span data-ttu-id="7f988-104">El artículo no puede tener una lista de materiales ni una fórmula</span><span class="sxs-lookup"><span data-stu-id="7f988-104">Item can't have a BOM or formula</span></span>

<span data-ttu-id="7f988-105">Código de error: PRO2614</span><span class="sxs-lookup"><span data-stu-id="7f988-105">Error code: PRO2614</span></span>

## <a name="symptoms"></a><span data-ttu-id="7f988-106">Síntomas</span><span class="sxs-lookup"><span data-stu-id="7f988-106">Symptoms</span></span>

<span data-ttu-id="7f988-107">Cuando intenta confirmar un pedido, recibe el siguiente mensaje de error durante la validación del artículo:</span><span class="sxs-lookup"><span data-stu-id="7f988-107">When you try to firm an order, you receive the following error message during item validation:</span></span>

> <span data-ttu-id="7f988-108">El artículo no puede tener una L. MAT o fórmula.</span><span class="sxs-lookup"><span data-stu-id="7f988-108">Item cannot have a BOM or formula</span></span>

## <a name="resolution"></a><span data-ttu-id="7f988-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="7f988-109">Resolution</span></span>

<span data-ttu-id="7f988-110">Los artículos que tienen una lista de materiales (BOM) o una fórmula deben ser de tipo *Elemento de planificación*, *BOM* o *fórmula*.</span><span class="sxs-lookup"><span data-stu-id="7f988-110">Items that have a bill of materials (BOM) or formula must be of the *Planning item*, *BOM*, or *formula* type.</span></span> <span data-ttu-id="7f988-111">Para cambiar el tipo de un elemento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7f988-111">To change the type of an item, follow these steps.</span></span>

1. <span data-ttu-id="7f988-112">Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="7f988-112">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="7f988-113">Abrir el producto relevante.</span><span class="sxs-lookup"><span data-stu-id="7f988-113">Open the relevant product.</span></span>
1. <span data-ttu-id="7f988-114">En la ficha desplegable **Ingeniero**, establezca el campo **Tipo de producción** en *Elemento de planificación*, *L. MAT* o *fórmula*.</span><span class="sxs-lookup"><span data-stu-id="7f988-114">On the **Engineer** FastTab, set the **Production type** field to *Planning item*, *BOM*, or *formula*.</span></span>
