---
title: Inspeccionar la calidad de las mercancías
description: Este procedimiento muestra cómo procesar un pedido de calidad.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9e9d750f116db62519ac7148f19bf62050430e9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "315438"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="1a964-103">Inspeccionar la calidad de las mercancías</span><span class="sxs-lookup"><span data-stu-id="1a964-103">Inspect the quality of goods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1a964-104">Este procedimiento muestra cómo procesar un pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="1a964-104">This procedure shows you how to process a quality order.</span></span> <span data-ttu-id="1a964-105">Puede ejecutar esta guía en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="1a964-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="1a964-106">Antes de comenzar este procedimiento de ejemplo, debe confirmar el pedido de compra "000016" y registrar una recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="1a964-106">Before you start this example procedure, you need to confirm purchase order “000016” and post a product receipt.</span></span> <span data-ttu-id="1a964-107">Esto crea automáticamente un pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="1a964-107">This will automatically create a quality order.</span></span> <span data-ttu-id="1a964-108">Las inspecciones de calidad las lleva a cabo normalmente un empleado de control de calidad.</span><span class="sxs-lookup"><span data-stu-id="1a964-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="1a964-109">Selección de un pedido de calidad</span><span class="sxs-lookup"><span data-stu-id="1a964-109">Select a quality order</span></span>
1. <span data-ttu-id="1a964-110">Vaya a Gestión del inventario > Tareas periódicas > Administración de calidad > Pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="1a964-110">Go to Inventory management > Periodic tasks > Quality management > Quality orders.</span></span>
2. <span data-ttu-id="1a964-111">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1a964-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="1a964-112">Seleccione el pedido de calidad que se creó antes de empezar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1a964-112">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="1a964-113">Registrar resultados de prueba</span><span class="sxs-lookup"><span data-stu-id="1a964-113">Record test results</span></span>
1. <span data-ttu-id="1a964-114">Haga clic en Resultados.</span><span class="sxs-lookup"><span data-stu-id="1a964-114">Click Results.</span></span>
2. <span data-ttu-id="1a964-115">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="1a964-115">Click Edit.</span></span>
3. <span data-ttu-id="1a964-116">En el campo Cantidad de resultado, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="1a964-116">In the Result quantity field, enter a number.</span></span>
4. <span data-ttu-id="1a964-117">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1a964-117">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="1a964-118">En el campo Resultado, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1a964-118">In the Outcome field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="1a964-119">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="1a964-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1a964-120">En este ejemplo, el resultado se basa en un resultado predefinido.</span><span class="sxs-lookup"><span data-stu-id="1a964-120">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="1a964-121">Normalmente, registrará un resultado de prueba más específico, como el tamaño u otra dimensión.</span><span class="sxs-lookup"><span data-stu-id="1a964-121">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
7. <span data-ttu-id="1a964-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1a964-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="1a964-123">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="1a964-123">Click Save.</span></span>
9. <span data-ttu-id="1a964-124">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1a964-124">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="1a964-125">Validar el pedido de calidad</span><span class="sxs-lookup"><span data-stu-id="1a964-125">Validate the quality order</span></span>
1. <span data-ttu-id="1a964-126">Haga clic en Validar.</span><span class="sxs-lookup"><span data-stu-id="1a964-126">Click Validate.</span></span>
2. <span data-ttu-id="1a964-127">En el campo Validado por, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1a964-127">In the Validated by field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1a964-128">Seleccione el usuario que realiza la inspección.</span><span class="sxs-lookup"><span data-stu-id="1a964-128">Select the user performing the inspection.</span></span>  
3. <span data-ttu-id="1a964-129">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1a964-129">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="1a964-130">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="1a964-130">Click Select.</span></span>
5. <span data-ttu-id="1a964-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="1a964-131">Click OK.</span></span>
6. <span data-ttu-id="1a964-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1a964-132">Close the page.</span></span>

