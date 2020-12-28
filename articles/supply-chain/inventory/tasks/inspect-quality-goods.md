---
title: Inspeccionar la calidad de las mercancías
description: Este tema explica cómo procesar un pedido de calidad.
author: perlynne
manager: tfehr
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee5f83b2dad60567341f33a73ce63d01e9da8289
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437114"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="48af0-103">Inspeccionar la calidad de las mercancías</span><span class="sxs-lookup"><span data-stu-id="48af0-103">Inspect the quality of goods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="48af0-104">Este tema explica cómo procesar un pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="48af0-104">This topic explains how to process a quality order.</span></span> <span data-ttu-id="48af0-105">Puede ejecutar esta guía en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="48af0-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="48af0-106">Antes de comenzar este procedimiento de ejemplo, debe confirmar el pedido de compra "000016" y registrar una recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="48af0-106">Before you start this example procedure, you need to confirm purchase order "000016" and post a product receipt.</span></span> <span data-ttu-id="48af0-107">Esto crea automáticamente un pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="48af0-107">This will automatically create a quality order.</span></span> <span data-ttu-id="48af0-108">Las inspecciones de calidad las lleva a cabo normalmente un empleado de control de calidad.</span><span class="sxs-lookup"><span data-stu-id="48af0-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="48af0-109">Selección de un pedido de calidad</span><span class="sxs-lookup"><span data-stu-id="48af0-109">Select a quality order</span></span>
1. <span data-ttu-id="48af0-110">En el panel de navegación, vaya a **Módulos > Gestión de inventario > Tareas periódicas > Administración de calidad > Pedidos de calidad**.</span><span class="sxs-lookup"><span data-stu-id="48af0-110">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="48af0-111">Seleccione el pedido de calidad que se creó antes de empezar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="48af0-111">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="48af0-112">Registrar resultados de prueba</span><span class="sxs-lookup"><span data-stu-id="48af0-112">Record test results</span></span>
1. <span data-ttu-id="48af0-113">Seleccione **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="48af0-113">Select **Results**.</span></span>
2. <span data-ttu-id="48af0-114">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="48af0-114">Select **Edit**.</span></span>
3. <span data-ttu-id="48af0-115">En el campo **Cantidad de resultado**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="48af0-115">In the **Result quantity** field, enter a number.</span></span>
4. <span data-ttu-id="48af0-116">En el campo **Resultado**, seleccione en el menú desplegable el registro que desee.</span><span class="sxs-lookup"><span data-stu-id="48af0-116">In the **Outcome** field, select the desired record in the drop-down menu.</span></span>  
- <span data-ttu-id="48af0-117">En este ejemplo, el resultado se basa en un resultado predefinido.</span><span class="sxs-lookup"><span data-stu-id="48af0-117">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="48af0-118">Normalmente, registrará un resultado de prueba más específico, como el tamaño u otra dimensión.</span><span class="sxs-lookup"><span data-stu-id="48af0-118">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
5. <span data-ttu-id="48af0-119">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="48af0-119">Select **Save**.</span></span>
6. <span data-ttu-id="48af0-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="48af0-120">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="48af0-121">Validar el pedido de calidad</span><span class="sxs-lookup"><span data-stu-id="48af0-121">Validate the quality order</span></span>
1. <span data-ttu-id="48af0-122">Seleccione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="48af0-122">Select **Validate**.</span></span>
2. <span data-ttu-id="48af0-123">En el campo **Validado por** , seleccione el usuario que estaba realizando la inspección en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="48af0-123">In the **Validated by** field, select the user performing the inspection from the drop-down menu.</span></span>  
3. <span data-ttu-id="48af0-124">Haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="48af0-124">Click **Select**.</span></span>
4. <span data-ttu-id="48af0-125">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="48af0-125">Select **OK**.</span></span>
5. <span data-ttu-id="48af0-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="48af0-126">Close the page.</span></span>

