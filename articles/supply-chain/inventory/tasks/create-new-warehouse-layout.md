---
title: Creación de un nuevo diseño de almacén
description: En este tema se describe cómo configurar la información sobre las ubicaciones en un almacén.
author: perlynne
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3a329df85c339c90e4bdc620c8a63837ebc19a7c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833986"
---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="3068b-103">Creación de un nuevo diseño de almacén</span><span class="sxs-lookup"><span data-stu-id="3068b-103">Create a new warehouse layout</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3068b-104">En este tema se describe cómo configurar la información sobre las ubicaciones en un almacén.</span><span class="sxs-lookup"><span data-stu-id="3068b-104">This topic describes how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="3068b-105">Esto solo se aplica a los almacenes creados con el “almacenamiento básico” en el módulo Gestión del inventario, no en los almacenes creados en el módulo Gestión de almacenes.</span><span class="sxs-lookup"><span data-stu-id="3068b-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="3068b-106">Puede utilizar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="3068b-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="3068b-107">Definir la capacidad de la ubicación predeterminada</span><span class="sxs-lookup"><span data-stu-id="3068b-107">Set the default location capacity</span></span>
1. <span data-ttu-id="3068b-108">En el panel de exploración, vaya a **Módulos > Gestión del inventario > Configurar > Inventario y parámetros de gestión de inventario y almacenes**.</span><span class="sxs-lookup"><span data-stu-id="3068b-108">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory and warehouse management parameters**.</span></span>
2. <span data-ttu-id="3068b-109">Seleccione la pestaña **Ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="3068b-109">Select the **Locations** tab.</span></span>
3. <span data-ttu-id="3068b-110">En el campo **Ancho estándar**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="3068b-110">In the **Standard width** field, enter a number.</span></span>
4. <span data-ttu-id="3068b-111">En el campo **Profundidad estándar**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="3068b-111">In the **Standard depth** field, enter a number.</span></span>
5. <span data-ttu-id="3068b-112">En el campo **Alto estándar**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="3068b-112">In the **Standard height** field, enter a number.</span></span>
6. <span data-ttu-id="3068b-113">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3068b-113">Select **Save**.</span></span>
7. <span data-ttu-id="3068b-114">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3068b-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="3068b-115">Definir el formato del nombre de ubicación</span><span class="sxs-lookup"><span data-stu-id="3068b-115">Define the location name format</span></span>
1. <span data-ttu-id="3068b-116">En el Panel de exploración, vaya a **Módulos > Gestión de inventario > Configuración > Desglose del inventario > Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="3068b-116">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>
2. <span data-ttu-id="3068b-117">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3068b-117">Select **New**.</span></span>
3. <span data-ttu-id="3068b-118">En el campo **Almacén**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3068b-118">In the **Warehouse** field, type a value.</span></span>
4. <span data-ttu-id="3068b-119">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3068b-119">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="3068b-120">En el campo **Sitio**, seleccione el registro deseado en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3068b-120">In the **Site** field, select the desired record in the lookup.</span></span>
6. <span data-ttu-id="3068b-121">Alterne la expansión de la sección **Nombres de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="3068b-121">Toggle the expansion of the **Location names** section.</span></span> <span data-ttu-id="3068b-122">Las opciones de esta sección definen el formato predeterminado para los nombres de ubicación.</span><span class="sxs-lookup"><span data-stu-id="3068b-122">The options in this section define the default format for location names.</span></span> <span data-ttu-id="3068b-123">En nuestro ejemplo, incluiremos el número de pasillo, el número de la estantería y el número de balda.</span><span class="sxs-lookup"><span data-stu-id="3068b-123">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
7. <span data-ttu-id="3068b-124">Establezca la opción **Incluir pasillo** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="3068b-124">Set the **Include aisle** option to **Yes**.</span></span>
8. <span data-ttu-id="3068b-125">Establezca la opción **Incluir estantería** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="3068b-125">Set the **Include rack** option to **Yes**.</span></span> 
9. <span data-ttu-id="3068b-126">En el campo **Formato**, escriba una valor para la estantería.</span><span class="sxs-lookup"><span data-stu-id="3068b-126">In the **Format** field, for the rack, type a value.</span></span>
10. <span data-ttu-id="3068b-127">Establezca la opción **Incluir balda** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="3068b-127">Set the **Include shelf** option to **Yes**.</span></span>
11. <span data-ttu-id="3068b-128">En el campo **Formato**, escriba una valor para la balda.</span><span class="sxs-lookup"><span data-stu-id="3068b-128">In the **Format** field, for the shelf, type a value.</span></span>

## <a name="define-warehouse-locations"></a><span data-ttu-id="3068b-129">Definir las ubicaciones del almacén</span><span class="sxs-lookup"><span data-stu-id="3068b-129">Define warehouse locations</span></span>
1. <span data-ttu-id="3068b-130">En el panel de acciones, haga clic en **Almacén**.</span><span class="sxs-lookup"><span data-stu-id="3068b-130">On the Action Pane, select **Warehouse**.</span></span>
2. <span data-ttu-id="3068b-131">Seleccione **Asistente para ubicación**.</span><span class="sxs-lookup"><span data-stu-id="3068b-131">Select **Location Wizard**.</span></span>
3. <span data-ttu-id="3068b-132">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3068b-132">Select **Next**.</span></span>
4. <span data-ttu-id="3068b-133">Anular la selección de la opción **Muelle de salida**</span><span class="sxs-lookup"><span data-stu-id="3068b-133">De-select the **Outbound docks** option</span></span>
5. <span data-ttu-id="3068b-134">Anular la selección de la opción **Ubicaciones de almacenaje**</span><span class="sxs-lookup"><span data-stu-id="3068b-134">De-select the **Bulk locations** option</span></span>
6. <span data-ttu-id="3068b-135">Seleccione **Siguiente** hasta llegar a la opción donde se puede seleccionar **Fin**.</span><span class="sxs-lookup"><span data-stu-id="3068b-135">Select **Next** until you come to the option to select **Finish**.</span></span>
7. <span data-ttu-id="3068b-136">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3068b-136">Close the page.</span></span>
8. <span data-ttu-id="3068b-137">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="3068b-137">Refresh the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]