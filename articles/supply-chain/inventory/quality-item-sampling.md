---
title: Muestreo de artículos de gestión de calidad
description: Este tema describe cómo configurar el muestreo de artículos.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 495bef32d63738e367167ee69f2028bc77945cc4
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956812"
---
# <a name="quality-management-item-sampling"></a><span data-ttu-id="a1464-103">Muestreo de artículos de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="a1464-103">Quality management item sampling</span></span>

<span data-ttu-id="a1464-104">El muestreo de elementos se utiliza como parte de una asociación de calidad.</span><span class="sxs-lookup"><span data-stu-id="a1464-104">Item sampling is used as part of a quality association.</span></span> <span data-ttu-id="a1464-105">Define la cantidad de inventario físico actual que debe inspeccionarse.</span><span class="sxs-lookup"><span data-stu-id="a1464-105">It defines the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="a1464-106">El muestreo puede basarse en cantidades fijas, en un porcentaje o en una matrícula completa.</span><span class="sxs-lookup"><span data-stu-id="a1464-106">Sampling can be based on fixed quantities, a percentage, or a full license plate.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="a1464-107">Configurar el muestreo de artículos</span><span class="sxs-lookup"><span data-stu-id="a1464-107">Set up item sampling</span></span>

<span data-ttu-id="a1464-108">Siga estos pasos para configurar el muestreo de artícuos.</span><span class="sxs-lookup"><span data-stu-id="a1464-108">Follow these steps to set up item sampling.</span></span>

1. <span data-ttu-id="a1464-109">Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Muestreo de artículos**.</span><span class="sxs-lookup"><span data-stu-id="a1464-109">Go to **Inventory management \> Setup \> Quality control \> Item sampling**.</span></span>
1. <span data-ttu-id="a1464-110">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a1464-110">Select **New**.</span></span>
1. <span data-ttu-id="a1464-111">En el campo **Muestreo de artículos,** introduzca un valor.</span><span class="sxs-lookup"><span data-stu-id="a1464-111">In the **Item sampling** field, enter a value.</span></span>
1. <span data-ttu-id="a1464-112">En el campo **Descripción**, especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="a1464-112">In the **Description** field, enter a value.</span></span>
1. <span data-ttu-id="a1464-113">En el campo **Valor,** especifique un número.</span><span class="sxs-lookup"><span data-stu-id="a1464-113">In the **Value** field, enter a number.</span></span> <span data-ttu-id="a1464-114">Este valor está relacionado con el valor de especificación de cantidad seleccionado en el campo adyacente.</span><span class="sxs-lookup"><span data-stu-id="a1464-114">This value is related to the quantity specification value that is selected in the adjacent field.</span></span>
1. <span data-ttu-id="a1464-115">En la sección **Proceso**, seleccione la casilla **Bloqueo completo** si se debe bloquear todo el lote o la cantidad de la línea de pedido si no se supera una prueba.</span><span class="sxs-lookup"><span data-stu-id="a1464-115">In the **Process** section, select the **Full blocking** check box if the whole lot or order line quantity should be blocked if a test is failed.</span></span> <span data-ttu-id="a1464-116">Si esta casilla está desactivada, solo se bloquearán los artículos del pedido de calidad si no se supera una prueba.</span><span class="sxs-lookup"><span data-stu-id="a1464-116">If this check box is cleared, only the items in the quality order will be blocked if a test is failed.</span></span>
1. <span data-ttu-id="a1464-117">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a1464-117">Select **Save**.</span></span>
1. <span data-ttu-id="a1464-118">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a1464-118">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="a1464-119">La característica *Gestión de calidad para procesos de almacén* proporciona capacidades de muestreo de elementos adicionales.</span><span class="sxs-lookup"><span data-stu-id="a1464-119">The *Quality management for warehouse processes* feature provides additional item sampling capabilities.</span></span> <span data-ttu-id="a1464-120">Agrega un concepto de *ámbito de muestreo del artículo* y lle ofrece la capacidad de definir una matrícula completa como especificación de cantidad.</span><span class="sxs-lookup"><span data-stu-id="a1464-120">It adds the concept of *item sampling scope* and lets you define a full license plate as the quantity specification.</span></span> <span data-ttu-id="a1464-121">Si ha activado esta función, vea [Gestión de calidad para procesos de almacén](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="a1464-121">If you've turned on this feature, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
