---
title: Reclasificar activos fijos
description: Para reclasificar un activo fijo, debe transferirlo a un grupo de activos fijos nuevo o asignarle un número de activo fijo nuevo en el mismo grupo.
author: saraschi2
manager: AnnBe
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df4a2fa3c1a38519da83391bcf1c4aa38b6504ff
ms.sourcegitcommit: 6890b5a372a18e11354003098a512685e339ddb0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "1541206"
---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="5d4e1-103">Reclasificar activos fijos</span><span class="sxs-lookup"><span data-stu-id="5d4e1-103">Reclassify fixed assets</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5d4e1-104">Para reclasificar un activo fijo, debe transferirlo a un grupo de activos fijos nuevo o asignarle un número de activo fijo nuevo en el mismo grupo.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="5d4e1-105">Cuando se reclasifica un activo fijo:</span><span class="sxs-lookup"><span data-stu-id="5d4e1-105">When a fixed asset is reclassified:</span></span>

<span data-ttu-id="5d4e1-106">• Todos los libros del activo fijo existente se crean para el activo fijo nuevo.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-106">• All books for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="5d4e1-107">Cualquier información que se haya configurado para el activo fijo se copia en el activo fijo nuevo.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="5d4e1-108">El estado de los libros para el activo fijo original es Cerrado.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-108">The status of the books for the original fixed asset is Closed.</span></span> 

<span data-ttu-id="5d4e1-109">• Los libros nuevos de un nuevo activo fijo contienen la fecha de reclasificación en el campo **Fecha de adquisición**.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-109">• The new books of the new fixed asset contain the date of the reclassification in the **Acquisition date** field.</span></span> <span data-ttu-id="5d4e1-110">La fecha del campo **Fecha de ejecución de la depreciación** se copia de la información del activo original.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-110">The date in the **Depreciation run date** field is copied from the original asset information.</span></span> <span data-ttu-id="5d4e1-111">Si ya se inició la depreciación, el campo **Fecha en la que se ejecutó la última depreciación** mostrará la fecha de reclasificación.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-111">If the depreciation has already started, the **Date when depreciation was last run** field displays the date of the reclassification.</span></span> 

<span data-ttu-id="5d4e1-112">• Las transacciones de activos fijos existentes para el activo fijo original se cancelan y se vuelven a generar para el activo fijo nuevo.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-112">• The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

<span data-ttu-id="5d4e1-113">Siga estos pasos para reclasificar un activo fijo:</span><span class="sxs-lookup"><span data-stu-id="5d4e1-113">Follow these steps to reclassify a fixed asset:</span></span>

1. <span data-ttu-id="5d4e1-114">Vaya a **Activos fijos > Tareas periódicas > Reclasificación**.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-114">Go to **Fixed assets > Periodic tasks > Reclassification.**</span></span>
2. <span data-ttu-id="5d4e1-115">En el campo **Grupo de activos fijos**, seleccione el grupo a reclasificar.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-115">In the **Fixed asset group** field, select the group to reclassify.</span></span>
3. <span data-ttu-id="5d4e1-116">En el campo **Número de activo fijo**, seleccione el activo fijo a reclasificar.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-116">In the **Fixed asset number** field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="5d4e1-117">En el campo **Nuevo grupo de activos fijos**, seleccione un grupo al que transferirle el activo fijo.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-117">In the **New fixed asset group** field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="5d4e1-118">Si el nuevo grupo de activos fijos está vinculado a una secuencia numérica, el campo **Nuevo número de activo fijo** se actualiza con el número de la nueva secuencia numérica del grupo de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-118">If the new fixed asset group is attached to a number sequence, the **New fixed asset number** field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="5d4e1-119">De no ser así, el campo **Nuevo número de activo fijo** se actualizará con el número de la secuencia numérica que esté configurada en la página de los **Parámetros de activo fijo**.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-119">Otherwise, the **New fixed asset number** field is updated with the number from the number sequence that is set up on the **Fixed asset parameters** page.</span></span> <span data-ttu-id="5d4e1-120">Si no hay configurada una secuencia numérica en la página de **Parámetros del Activo fijo**, introduzca un número en el campo **Nuevo número de activo fijo**.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-120">If a number sequence is not set up on the **Fixed asset parameters** page, enter a number in the **New fixed asset number** field.</span></span>  
5. <span data-ttu-id="5d4e1-121">En el campo **Fecha de reclasificación**, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-121">In the **Reclassification date** field, enter a date.</span></span>
6. <span data-ttu-id="5d4e1-122">En el campo **Series de asientos**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-122">In the **Voucher series** field, enter or select a value.</span></span>
7. <span data-ttu-id="5d4e1-123">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5d4e1-123">Click **OK**.</span></span>
