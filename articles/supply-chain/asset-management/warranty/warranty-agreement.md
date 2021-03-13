---
title: Contratos de garantía
description: En este tema se explican los contratos de garantía en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7080af2059c9c9bcdd11ca0ee9c5e339cef69302
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021513"
---
# <a name="warranty-agreements"></a><span data-ttu-id="43e3e-103">Contratos de garantía</span><span class="sxs-lookup"><span data-stu-id="43e3e-103">Warranty agreements</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="43e3e-104">En gestión de activos, puede configurar los términos de garantía que se pueden conectar a un activo o un tipo de activo.</span><span class="sxs-lookup"><span data-stu-id="43e3e-104">In Asset Management, you can set up warranty terms that can be connected to an asset or an asset type.</span></span> <span data-ttu-id="43e3e-105">Los términos de garantía se crean para un período específico.</span><span class="sxs-lookup"><span data-stu-id="43e3e-105">Warranty terms are created for a specific period.</span></span> <span data-ttu-id="43e3e-106">La garantía se puede configurar para proporcionar cobertura total o alcance parcial, y puede configurar condiciones relacionadas con las horas, los gastos, y artículos.</span><span class="sxs-lookup"><span data-stu-id="43e3e-106">Warranty can be set up to provide full coverage or partial coverage, and you can set up terms that are related to hours, expenses, and items.</span></span>

<span data-ttu-id="43e3e-107">El primer paso consiste en crear los acuerdos de la garantía de proveedor que tiene en el equipo.</span><span class="sxs-lookup"><span data-stu-id="43e3e-107">The first step is to create any vendor warranty agreements that you have for your equipment.</span></span> <span data-ttu-id="43e3e-108">A continuación adjunta los acuerdos de la garantía a los activos o a tipos de activos.</span><span class="sxs-lookup"><span data-stu-id="43e3e-108">You then attach warranty agreements to assets or asset types.</span></span> <span data-ttu-id="43e3e-109">Los acuerdos de la garantía de proveedor solo se usan con fines informativos.</span><span class="sxs-lookup"><span data-stu-id="43e3e-109">Vendor warranty agreements are used only for informational purposes.</span></span> <span data-ttu-id="43e3e-110">Si la garantía de proveedor se configura en un activo, puede consultar el período de cobertura de la garantía en el activo.</span><span class="sxs-lookup"><span data-stu-id="43e3e-110">If vendor warranty is set up on an asset, you can see the warranty coverage period on the asset.</span></span>

## <a name="create-a-warranty-agreement"></a><span data-ttu-id="43e3e-111">Crear un acuerdo de garantía</span><span class="sxs-lookup"><span data-stu-id="43e3e-111">Create a warranty agreement</span></span>

<span data-ttu-id="43e3e-112">Un acuerdo de la garantía puede incluir varias líneas del acuerdo para cubrir la garantía para las horas de trabajo, gastos, y artículos.</span><span class="sxs-lookup"><span data-stu-id="43e3e-112">A warranty agreement can include several agreement lines to cover the warranty for work hours, expenses, and items.</span></span>

1. <span data-ttu-id="43e3e-113">Seleccione **Administración de activos** \> **Configuración** \> **Activos** \> **Garantía**.</span><span class="sxs-lookup"><span data-stu-id="43e3e-113">Select **Asset management** \> **Setup** \> **Assets** \> **Warranty**.</span></span>
2. <span data-ttu-id="43e3e-114">Seleccione **Nuevo** para crear un producto.</span><span class="sxs-lookup"><span data-stu-id="43e3e-114">Select **New** to create a product.</span></span>
3. <span data-ttu-id="43e3e-115">En el campo **Garantía**, especifique un identificador de la garantía.</span><span class="sxs-lookup"><span data-stu-id="43e3e-115">In the **Warranty** field, enter a warranty ID.</span></span> 
4. <span data-ttu-id="43e3e-116">En el campo **Nombre**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="43e3e-116">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="43e3e-117">En la ficha desplegable **Detalles**, el campo **Activos** se muestra el número de activos activos que usan el acuerdo de la garantía.</span><span class="sxs-lookup"><span data-stu-id="43e3e-117">On the **Details** FastTab, the **Assets** field shows the number of active assets that use the warranty agreement.</span></span>

5. <span data-ttu-id="43e3e-118">En la ficha desplegable **Líneas de garantía**, siga estos pasos para agregar líneas que deben incluirse en un acuerdo de garantía:</span><span class="sxs-lookup"><span data-stu-id="43e3e-118">On the **Warranty lines** FastTab, follow these steps to add lines that should be included in a warranty agreement:</span></span>

    1. <span data-ttu-id="43e3e-119">Seleccione **Agregar línea** para agregar una nueva condición a la garantía.</span><span class="sxs-lookup"><span data-stu-id="43e3e-119">Select **Add line** to add a new condition to the warranty.</span></span> <span data-ttu-id="43e3e-120">Se especifica automáticamente un número de línea secuencial en el campo **Línea**.</span><span class="sxs-lookup"><span data-stu-id="43e3e-120">A sequential line number is automatically entered in the **Line** field.</span></span>
    2. <span data-ttu-id="43e3e-121">En el campo **Período**, seleccione el tipo de período de garantía.</span><span class="sxs-lookup"><span data-stu-id="43e3e-121">In the **Period** field, select the type of warranty period.</span></span>
    3. <span data-ttu-id="43e3e-122">Escriba un número en el campo **Intervalo**.</span><span class="sxs-lookup"><span data-stu-id="43e3e-122">In the **Interval** field, enter a number.</span></span> <span data-ttu-id="43e3e-123">Este campo define el número de períodos para los que la garantía debe ser válida.</span><span class="sxs-lookup"><span data-stu-id="43e3e-123">This field defines the number of periods that the warranty should be valid for.</span></span>
    4. <span data-ttu-id="43e3e-124">En el campo **Porcentaje**, especifique el porcentaje de cobertura para la línea de la garantía.</span><span class="sxs-lookup"><span data-stu-id="43e3e-124">In the **Percent** field, enter the coverage percentage for the warranty line.</span></span> <span data-ttu-id="43e3e-125">El porcentaje indica cuánto está cubierta por la empresa.</span><span class="sxs-lookup"><span data-stu-id="43e3e-125">The percentage indicates how much is covered by your company.</span></span>

![Página de garantía](media/01-warranty.png)
