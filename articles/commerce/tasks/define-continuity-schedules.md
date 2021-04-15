---
title: Definir programaciones de continuidad
description: Este tema explica la configuración de un programa de continuidad (conocido también como pedidos recurrentes).
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRContinuitySchedule, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8414377ddec0e001f003f842866725eb58bd75a3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791616"
---
# <a name="define-continuity-schedules"></a><span data-ttu-id="bfe80-103">Definir programaciones de continuidad</span><span class="sxs-lookup"><span data-stu-id="bfe80-103">Define continuity schedules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bfe80-104">Este tema explica la configuración de un programa de continuidad (conocido también como pedidos recurrentes).</span><span class="sxs-lookup"><span data-stu-id="bfe80-104">This topic walks through setting up a continuity program (otherwise known as reoccurring orders).</span></span> <span data-ttu-id="bfe80-105">Este tema usa la empresa USRT en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="bfe80-105">This topic uses company USRT in the demo data.</span></span>


## <a name="create-continuity-program"></a><span data-ttu-id="bfe80-106">Crear un programa de continuidad</span><span class="sxs-lookup"><span data-stu-id="bfe80-106">Create continuity program</span></span>
1. <span data-ttu-id="bfe80-107">Vaya a Retail y Commerce > Continuidad > Programas de continuidad.</span><span class="sxs-lookup"><span data-stu-id="bfe80-107">Go to Retail and Commerce > Continuity > Continuity programs.</span></span>
2. <span data-ttu-id="bfe80-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="bfe80-108">Click New.</span></span>
3. <span data-ttu-id="bfe80-109">En el campo Id. de programación, escriba el Id. de programación de continuidad.</span><span class="sxs-lookup"><span data-stu-id="bfe80-109">In the Schedule ID field, type the continuity schedule ID.</span></span>
4. <span data-ttu-id="bfe80-110">En el campo Inicio del pedido, seleccione "Primer evento".</span><span class="sxs-lookup"><span data-stu-id="bfe80-110">In the Order start field, select 'First event'.</span></span>
    * <span data-ttu-id="bfe80-111">Si un cliente realiza un pedido nuevo del programa de continuidad, hay dos opciones para las que el producto será enviado:  1.</span><span class="sxs-lookup"><span data-stu-id="bfe80-111">If a customer places a new order for the continuity program, there are two options for which product will be shipped:  1.</span></span> <span data-ttu-id="bfe80-112">Primer evento: el primer producto en el programa de la continuidad se enviará.</span><span class="sxs-lookup"><span data-stu-id="bfe80-112">First event: the first product in the continuity program will be shipped.</span></span>  <span data-ttu-id="bfe80-113">2.</span><span class="sxs-lookup"><span data-stu-id="bfe80-113">2.</span></span> <span data-ttu-id="bfe80-114">Evento actual: el producto actual se enviará.</span><span class="sxs-lookup"><span data-stu-id="bfe80-114">Current event: the current product will be shipped.</span></span> <span data-ttu-id="bfe80-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bfe80-115">For example.</span></span> <span data-ttu-id="bfe80-116">tras tres meses en el programa, el cliente recibirá el tercero en el programa.</span><span class="sxs-lookup"><span data-stu-id="bfe80-116">three months into the program, the customer will receive the third in the program.</span></span>  
5. <span data-ttu-id="bfe80-117">Seleccione "Sí" para solicitar la fecha de inicio del pedido.</span><span class="sxs-lookup"><span data-stu-id="bfe80-117">Select 'Yes' to prompt for the order start date.</span></span>
6. <span data-ttu-id="bfe80-118">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="bfe80-118">Click Add line.</span></span>
7. <span data-ttu-id="bfe80-119">En el campo Número de artículo, escriba el número de artículo del primer producto ("0013").</span><span class="sxs-lookup"><span data-stu-id="bfe80-119">In the Item number field, type the item number for the first product ('0013').</span></span>
8. <span data-ttu-id="bfe80-120">Tipo "CP".</span><span class="sxs-lookup"><span data-stu-id="bfe80-120">Type 'CP'.</span></span>
9. <span data-ttu-id="bfe80-121">Escriba la fecha en que el primer producto esté disponible para el pedido.</span><span class="sxs-lookup"><span data-stu-id="bfe80-121">Enter the date when the first product will be available for order.</span></span>
10. <span data-ttu-id="bfe80-122">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="bfe80-122">Click Add line.</span></span>
11. <span data-ttu-id="bfe80-123">En el campo Código de artículo, escriba "0014".</span><span class="sxs-lookup"><span data-stu-id="bfe80-123">In the Item number field, type '0014'.</span></span>
12. <span data-ttu-id="bfe80-124">En el campo Código de intervalo de fechas, borre el valor para que el campo esté vacío.</span><span class="sxs-lookup"><span data-stu-id="bfe80-124">In the Date interval code field, clear the value so the field is empty.</span></span>
    * <span data-ttu-id="bfe80-125">Para este procedimiento, desactive el intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="bfe80-125">For this procedure, clear the date interval.</span></span> <span data-ttu-id="bfe80-126">Establecerá la fecha como incremental desde la fecha de inicio del primer artículo.</span><span class="sxs-lookup"><span data-stu-id="bfe80-126">You'll set the date as incremental from the start date of the first item.</span></span>  
13. <span data-ttu-id="bfe80-127">Aquí puede escribir el intervalo en el que se envían los productos.</span><span class="sxs-lookup"><span data-stu-id="bfe80-127">Here you'll enter the interval at which the products are shipped.</span></span> <span data-ttu-id="bfe80-128">Tipo "30".</span><span class="sxs-lookup"><span data-stu-id="bfe80-128">Type '30'.</span></span>
    * <span data-ttu-id="bfe80-129">Para un programa mensual, puede especificar 30 días para el intervalo.</span><span class="sxs-lookup"><span data-stu-id="bfe80-129">For a monthly program, you'll enter 30 days for the interval.</span></span>  
14. <span data-ttu-id="bfe80-130">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="bfe80-130">Click Add line.</span></span>
15. <span data-ttu-id="bfe80-131">En el campo Código de artículo, escriba "0015".</span><span class="sxs-lookup"><span data-stu-id="bfe80-131">In the Item number field, type '0015'.</span></span>
16. <span data-ttu-id="bfe80-132">Tipo "Fin".</span><span class="sxs-lookup"><span data-stu-id="bfe80-132">Type 'End'.</span></span>
17. <span data-ttu-id="bfe80-133">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="bfe80-133">Click Save.</span></span>

## <a name="assign-to-continuity-item"></a><span data-ttu-id="bfe80-134">Asignar al artículo de continuidad</span><span class="sxs-lookup"><span data-stu-id="bfe80-134">Assign to continuity item</span></span>
1. <span data-ttu-id="bfe80-135">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="bfe80-135">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="bfe80-136">Seleccionar artículo "0016".</span><span class="sxs-lookup"><span data-stu-id="bfe80-136">Select item '0016'.</span></span>
    * <span data-ttu-id="bfe80-137">Para este procedimiento, seleccionará el número de artículo 0016.</span><span class="sxs-lookup"><span data-stu-id="bfe80-137">For this procedure, you'll select item number 0016.</span></span> <span data-ttu-id="bfe80-138">Normalmente, se habrá creado un producto liberado con una lógica de negocios de continuidad adicional aplicada cuando se coloca en un pedido de ventas en el centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bfe80-138">Normally, you'll have created a released product that has additional continuity business logic applied when it's placed on a sales order in call center.</span></span>  
3. <span data-ttu-id="bfe80-139">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bfe80-139">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="bfe80-140">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="bfe80-140">Click Edit.</span></span>
5. <span data-ttu-id="bfe80-141">Expanda o contraiga la sección Vender.</span><span class="sxs-lookup"><span data-stu-id="bfe80-141">Expand or collapse the Sell section.</span></span>
6. <span data-ttu-id="bfe80-142">Aquí puede escribir el programa de continuidad que representa este artículo.</span><span class="sxs-lookup"><span data-stu-id="bfe80-142">Here you'll enter the continuity program that this item represents.</span></span> <span data-ttu-id="bfe80-143">Especifique el Id. de programación que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bfe80-143">Type the Schedule ID you created earlier.</span></span>
    * <span data-ttu-id="bfe80-144">Cuando este artículo se vende en un centro de llamadas, la lógica de negocios adicional se aplica desde el programa de continuidad seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bfe80-144">When this item is sold in a call center, additional business logic is applied from the selected continuity program.</span></span>  
7. <span data-ttu-id="bfe80-145">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="bfe80-145">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]