---
title: Configuración de la reasignación de artículos para la selección corta
description: En este tema se muestra cómo permitir que los trabajadores del almacén busquen rápidamente ubicaciones alternativas si no hay suficiente inventario en la ubicación a la que les han dirigido.
author: ShylaThompson
manager: tfehr
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker, WHSLocationWithWorkException
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3ecd05add44bacae517109f8bab2cb43376fe07c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216820"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="ff4bc-103">Configuración de la reasignación de artículos para la selección corta</span><span class="sxs-lookup"><span data-stu-id="ff4bc-103">Set up short picking item reallocation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ff4bc-104">En este procedimiento se muestra cómo permitir que los trabajadores del almacén busquen rápidamente ubicaciones alternativas si no hay suficiente inventario en la ubicación a la que les han dirigido.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-104">This procedure shows how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> 

<span data-ttu-id="ff4bc-105">El proceso de reasignación lo controla una **Excepción de trabajo** y lo utiliza el **trabajador** del almacén.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-105">The reallocation process is controlled by a **Work exception** and used by the warehouse **worker.**</span></span>

<span data-ttu-id="ff4bc-106">Es posible utilizar procesos de reasignación automáticos, manuales o ambos:</span><span class="sxs-lookup"><span data-stu-id="ff4bc-106">It is possible to use Automatic, Manual, or both reallocation processes:</span></span>

- <span data-ttu-id="ff4bc-107">Reasignación automática: se utilizan directivas de ubicación para determinar si las mercancías están disponibles en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-107">Automatic reallocation - Location directives are used to determine if the goods are available at another location.</span></span> <span data-ttu-id="ff4bc-108">Si es posible, el trabajo se actualizará y el usuario del almacén será dirigido a la ubicación alternativa.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-108">If possible, the work will be updated and the warehouse user will be directed to the alternative location.</span></span>
- <span data-ttu-id="ff4bc-109">Reasignación manual: permite al usuario del almacén seleccionar entre una o varias ubicaciones con cantidades de mercancías sin reservar.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-109">Manual reallocation - Allows the warehouse user to select from one or more locations with unreserved quantities of goods.</span></span> 
- <span data-ttu-id="ff4bc-110">Automática y manual: si el sistema no puede realizar una reasignación automática y las ubicaciones están disponibles con cantidades sin reservar, se le pedirá al usuario que seleccione una ubicación.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-110">Automatic and manual - If the system is unable to perform an automatic reallocation, and locations are available with unreserved quantities, the user will be prompted to select a location.</span></span>

## <a name="set-up-work-exceptions"></a><span data-ttu-id="ff4bc-111">Configurar excepciones de trabajo</span><span class="sxs-lookup"><span data-stu-id="ff4bc-111">Set up work exceptions</span></span>
<span data-ttu-id="ff4bc-112">Es posible definir varias excepciones de trabajo con directivas de la reasignación de artículo diferentes para permitir el trabajador del almacén para elegir uno basado en las necesidades de envío que están procesando.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-112">It's possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>

<span data-ttu-id="ff4bc-113">Para crear este procedimiento se utiliza la empresa de datos de prueba USMF.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-113">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="ff4bc-114">En el **Panel de navegación**, vaya a **Administración de almacenes > Configuración > Trabajo > Excepciones de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-114">In the **Navigation pane**, go to **Warehouse management > Setup > Work > Work exceptions**.</span></span>
2. <span data-ttu-id="ff4bc-115">Haga clic en **Nuevo**</span><span class="sxs-lookup"><span data-stu-id="ff4bc-115">Click **New**</span></span> 
3. <span data-ttu-id="ff4bc-116">En el campo **Código de excepción de trabajo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-116">In the **Work exception code** field, type a value.</span></span> <span data-ttu-id="ff4bc-117">Este será el título de esta excepción.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-117">This will be the title of this exception .</span></span> <span data-ttu-id="ff4bc-118">Por ejemplo, manual de picking corto.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-118">For example, Short picking manual.</span></span>
4. <span data-ttu-id="ff4bc-119">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-119">In the **Description** field, type a value.</span></span> <span data-ttu-id="ff4bc-120">Esta será una descripción breve del uso de esta excepción.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-120">This will be a short description of the usage of this exception.</span></span> <span data-ttu-id="ff4bc-121">Por ejemplo, Picking corto: elemento no disponible.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-121">For example, Short picking - item not available.</span></span>
5. <span data-ttu-id="ff4bc-122">En el campo **Tipo de excepción**, seleccione **Picking corto**.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-122">In the **Exception** type field, select **Short pick**.</span></span>
6. <span data-ttu-id="ff4bc-123">Active la casilla **Ajustar inventario**.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-123">Select the **Adjust inventory** check box.</span></span> <span data-ttu-id="ff4bc-124">Se está seleccionada, el inventario se ajustará automáticamente a 0 en la ubicación de picking corto.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-124">If selected, inventory will automatically be adjusted to 0 at the short picked location.</span></span>
7. <span data-ttu-id="ff4bc-125">En el campo **Código de tipo de ajuste predeterminado**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-125">In the **Default adjustment type code** field, enter or select a value.</span></span> <span data-ttu-id="ff4bc-126">Por ejemplo, en USMF puede seleccionar **Quitar Res Adj Out**. Cada código de tipo de ajuste contiene cuatro características: nombre, descripción, nombre de diario de inventario y **Quitar reservas**.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-126">For example, in USMF you can select **Remove Res Adj Out**. Each Adjustment type code contains four characteristics: name, description, inventory journal name, and **Remove reservations**.</span></span> <span data-ttu-id="ff4bc-127">Si **Quitar reservas** está habilitada, se quitarán las reservas de la línea de pedido de picking corto.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-127">If **Remove reservations** is enabled, the short-picked order line's reservations will be removed.</span></span>  
8. <span data-ttu-id="ff4bc-128">En el campo **Reasignación de artículos**, seleccione un valor, como Manual.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-128">In the **Item reallocation** field, select a value, such as Manual.</span></span> <span data-ttu-id="ff4bc-129">Si selecciona Manual o Automático y manual, el trabajador del almacén debe estar habilitado para usar la reasignación manual.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-129">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="ff4bc-130">Configurar un trabajador para usar la reasignación manual de artículos</span><span class="sxs-lookup"><span data-stu-id="ff4bc-130">Set up a worker to use manual item reallocation</span></span>

<span data-ttu-id="ff4bc-131">Para crear este procedimiento se utiliza la empresa de datos de prueba USMF.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-131">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="ff4bc-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-132">Close the page.</span></span>
2. <span data-ttu-id="ff4bc-133">En el **Panel de navegación**, vaya a **Administración de almacenes > Configuración > Trabajador**.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-133">In the **Navigation pane**, go to **Warehouse management > Setup > Worker**.</span></span>
3. <span data-ttu-id="ff4bc-134">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-134">Click **Edit**.</span></span>
4. <span data-ttu-id="ff4bc-135">En la lista, seleccione un trabajador.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-135">In the list, select worker.</span></span> <span data-ttu-id="ff4bc-136">Por ejemplo, Julia Funderburk.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-136">For example, Julia Funderburk.</span></span>
5. <span data-ttu-id="ff4bc-137">Expanda la ficha desplegable **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-137">Expand the **Users** FastTab.</span></span>
6. <span data-ttu-id="ff4bc-138">Seleccione un **Id. de usuario** en la lista.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-138">In the list, select a **User ID**.</span></span> <span data-ttu-id="ff4bc-139">Por ejemplo, 24.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-139">For example, 24.</span></span>
7. <span data-ttu-id="ff4bc-140">Expanda la ficha desplegable **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-140">Expand the **Work** FastTab.</span></span>
8. <span data-ttu-id="ff4bc-141">Seleccione **Sí** en el campo **Permitir reasignación de artículos manual**.</span><span class="sxs-lookup"><span data-stu-id="ff4bc-141">Select **Yes** in the **Allow manual item reallocation** field.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]