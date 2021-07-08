---
title: El número de fórmula seleccionado no está aprobado para pedidos de lote
description: Cuando intenta confirmar un pedido planificado, recibe un mensaje de error que indica que el número de fórmula seleccionado no está aprobado para un pedido por lotes.
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
ms.openlocfilehash: 4f993c92ca0a2f8f79e4b0e0eda43904529163f8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294169"
---
# <a name="selected-formula-number-isnt-approved-for-a-batch-order"></a><span data-ttu-id="b896c-103">El número de fórmula seleccionado no está aprobado para pedidos de lote</span><span class="sxs-lookup"><span data-stu-id="b896c-103">Selected formula number isn't approved for a batch order</span></span>

<span data-ttu-id="b896c-104">Código de error: PRO2614</span><span class="sxs-lookup"><span data-stu-id="b896c-104">Error code: PRO2614</span></span>

## <a name="symptoms"></a><span data-ttu-id="b896c-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="b896c-105">Symptoms</span></span>

<span data-ttu-id="b896c-106">Cuando intenta confirmar un pedido planificado, recibe el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="b896c-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="b896c-107">El número de fórmula seleccionado no está aprobado para pedidos de lote.</span><span class="sxs-lookup"><span data-stu-id="b896c-107">The selected formula number is not approved for a batch order.</span></span>

## <a name="cause"></a><span data-ttu-id="b896c-108">Causa</span><span class="sxs-lookup"><span data-stu-id="b896c-108">Cause</span></span>

<span data-ttu-id="b896c-109">El sistema valida la operación de endurecimiento para asegurarse de que haya una fórmula aprobada disponible para el artículo activo.</span><span class="sxs-lookup"><span data-stu-id="b896c-109">The system validates the firming operation to make sure that an approved formula is available for the active item.</span></span> <span data-ttu-id="b896c-110">Probablemente debas aprobar la fórmula.</span><span class="sxs-lookup"><span data-stu-id="b896c-110">You must probably approve the formula.</span></span>

## <a name="resolution"></a><span data-ttu-id="b896c-111">Resolución</span><span class="sxs-lookup"><span data-stu-id="b896c-111">Resolution</span></span>

<span data-ttu-id="b896c-112">Para aprobar una fórmula, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b896c-112">To approve a formula, follow these steps.</span></span>

1. <span data-ttu-id="b896c-113">Vaya a **Gestión de información de productos \> Listas de materiales y fórmulas \> Fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="b896c-113">Go to **Product information management \> Bills of materials and formulas \> Formulas**.</span></span>
1. <span data-ttu-id="b896c-114">Seleccione la fórmula relevante.</span><span class="sxs-lookup"><span data-stu-id="b896c-114">Select the relevant formula.</span></span>
1. <span data-ttu-id="b896c-115">En el Panel de acciones, en la ficha **Fórmula**, en el grupo **Mantener**, haga clic en **Aprobar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="b896c-115">On the Action Pane, on the **Formula** tab, in the **Maintain** group, select **Approve formula**.</span></span>
1. <span data-ttu-id="b896c-116">En el cuadro de diálogo **Aprobar lista de materiales o fórmula**, seleccione un aprobador y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b896c-116">In the **Approve BOM or formula** dialog box, select an approver, and then select **OK**.</span></span>
