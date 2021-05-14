---
title: Inspeccionar la calidad de las mercancías
description: Este tema explica cómo procesar los pedidos de calidad.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec67e7864db12178c0f3cfe8b93d510a46e8a0d4
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956143"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="ee5c7-103">Inspeccionar la calidad de las mercancías</span><span class="sxs-lookup"><span data-stu-id="ee5c7-103">Inspect the quality of goods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ee5c7-104">Este tema explica cómo procesar los pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-104">This topic describes how to process quality orders.</span></span> <span data-ttu-id="ee5c7-105">Las inspecciones de calidad las realiza normalmente un empleado de control de calidad.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-105">Quality inspections are typically done by a quality clerk.</span></span>

<span data-ttu-id="ee5c7-106">Si los datos de demostración estándar están instalados, puede utilizarlos para completar los procedimientos de este tema.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-106">If the standard demo data is installed, you can use it to complete the procedures in this topic.</span></span> <span data-ttu-id="ee5c7-107">Para usar los datos de demostración, seleccione la entidad legal *USMF* antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-107">To use the demo data, select the *USMF* legal entity before you begin.</span></span> <span data-ttu-id="ee5c7-108">A continuación, debe confirmar la orden de compra *000016* y registrar una recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-108">You must then confirm purchase order *000016* and post a product receipt.</span></span> <span data-ttu-id="ee5c7-109">Se genera automáticamente un pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-109">A quality order is automatically generated.</span></span>

## <a name="step-1-select-a-quality-order"></a><span data-ttu-id="ee5c7-110">Paso 1: seleccionar un pedido de calidad</span><span class="sxs-lookup"><span data-stu-id="ee5c7-110">Step 1: Select a quality order</span></span>

<span data-ttu-id="ee5c7-111">Para seleccionar un pedido de calidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-111">To select a quality order, follow these steps.</span></span>

1. <span data-ttu-id="ee5c7-112">Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Pedidos de calidad**.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-112">Go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>
1. <span data-ttu-id="ee5c7-113">Seleccione el pedido de calidad que se generó antes de empezar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-113">Select the quality order that was generated before you started this procedure.</span></span>

## <a name="step-2-record-test-results"></a><span data-ttu-id="ee5c7-114">Paso 2: registrar resultados de prueba</span><span class="sxs-lookup"><span data-stu-id="ee5c7-114">Step 2: Record test results</span></span>

<span data-ttu-id="ee5c7-115">Para registrar los resultados de prueba, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-115">To record test results, follow these steps.</span></span>

1. <span data-ttu-id="ee5c7-116">Seleccione **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-116">Select **Results**.</span></span>
1. <span data-ttu-id="ee5c7-117">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-117">Select **Edit**.</span></span>
1. <span data-ttu-id="ee5c7-118">En el campo **Cantidad de resultado**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-118">In the **Result quantity** field, enter a number.</span></span>
1. <span data-ttu-id="ee5c7-119">En el campo **Resultado**, seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-119">In the **Outcome** field, select the desired record.</span></span> <span data-ttu-id="ee5c7-120">En este ejemplo, el resultado se basa en un resultado predefinido.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-120">In this example, the result is based on a predefined outcome.</span></span> <span data-ttu-id="ee5c7-121">Normalmente, registrará un resultado de prueba más específico, como el tamaño u otra dimensión.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-121">Usually, you will record a more specific test result, such as a size or other dimension.</span></span>
1. <span data-ttu-id="ee5c7-122">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-122">Select **Save**.</span></span>
1. <span data-ttu-id="ee5c7-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-123">Close the page.</span></span>

## <a name="step-3-validate-the-quality-order"></a><span data-ttu-id="ee5c7-124">Paso 3: validar el pedido de calidad</span><span class="sxs-lookup"><span data-stu-id="ee5c7-124">Step 3: Validate the quality order</span></span>

<span data-ttu-id="ee5c7-125">Para validar el pedido de calidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-125">To validate the quality order, follow these steps.</span></span>

1. <span data-ttu-id="ee5c7-126">Seleccione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-126">Select **Validate**.</span></span>
1. <span data-ttu-id="ee5c7-127">En el campo **Validado por**, seleccione el usuario que está realizando la inspección.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-127">In the **Validated by** field, select the user who is doing the inspection.</span></span>
1. <span data-ttu-id="ee5c7-128">Seleccione **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-128">Select **Select**.</span></span>
1. <span data-ttu-id="ee5c7-129">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-129">Select **OK**.</span></span>
1. <span data-ttu-id="ee5c7-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ee5c7-130">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
