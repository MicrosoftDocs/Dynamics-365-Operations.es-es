--- 
title: "Inicializar los niveles de existencias en el almacén"
description: "Este procedimiento muestra cómo obtener el inventario disponible actualizado manualmente mediante un diario de movimientos de inventario."
author: perlynne
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalMovement, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 6500092f8d0aa87914828f2a107907cf1176dcfe
ms.contentlocale: es-es
ms.lasthandoff: 09/11/2018

---
# <a name="initialize-stock-levels-in-the-warehouse"></a><span data-ttu-id="b19a0-103">Inicializar los niveles de existencias en el almacén</span><span class="sxs-lookup"><span data-stu-id="b19a0-103">Initialize stock levels in the warehouse</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b19a0-104">Este procedimiento muestra cómo obtener el inventario disponible actualizado manualmente mediante un diario de movimientos de inventario.</span><span class="sxs-lookup"><span data-stu-id="b19a0-104">This procedure shows you how to get the on-hand inventory updated manually using an Inventory movement journal.</span></span> <span data-ttu-id="b19a0-105">(También es posible actualizar el inventario disponible importando transacciones en entidades de datos). Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF, donde todos los requisitos previos, como el nombre del diario, la configuración del artículo, los perfiles de contabilización y las cuentas, están disponibles.</span><span class="sxs-lookup"><span data-stu-id="b19a0-105">(It’s also possible to update on-hand inventory by importing transactions in data entities.) You can run this guide in demo data company USMF where all the prerequisites like journal name, item setup, posting profiles, and accounts are available.</span></span> <span data-ttu-id="b19a0-106">El procedimiento sugiere los valores específicos para el artículo y las dimensiones que se usan.</span><span class="sxs-lookup"><span data-stu-id="b19a0-106">The guide suggests specific values for the item and dimensions that are used.</span></span> <span data-ttu-id="b19a0-107">Si elige un artículo diferente, es posible que tenga que especificar valores para distintas dimensiones.</span><span class="sxs-lookup"><span data-stu-id="b19a0-107">If you choose a different item, you may need to enter values for different dimensions.</span></span>

1. <span data-ttu-id="b19a0-108">Vaya a Gestión del inventario > Movimientos de diario > Artículos > Movimiento.</span><span class="sxs-lookup"><span data-stu-id="b19a0-108">Go to Inventory management > Journal entries > Items > Movement.</span></span>
2. <span data-ttu-id="b19a0-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="b19a0-109">Click New.</span></span>
3. <span data-ttu-id="b19a0-110">En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b19a0-110">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="b19a0-111">Seleccione IMov.</span><span class="sxs-lookup"><span data-stu-id="b19a0-111">Select IMov.</span></span>
    * <span data-ttu-id="b19a0-112">Es buena práctica utilizar distintas plantillas de nombre de diario para distintos fines empresariales.</span><span class="sxs-lookup"><span data-stu-id="b19a0-112">It’s a good practise to use different journal name templates for the different business purposes.</span></span>  
5. <span data-ttu-id="b19a0-113">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b19a0-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="b19a0-114">En el campo Cuenta de contrapartida, especifique los valores "140200".</span><span class="sxs-lookup"><span data-stu-id="b19a0-114">In the Offset account field, specify the values '140200'.</span></span>
    * <span data-ttu-id="b19a0-115">Se trata de la cuenta de contrapartida que será la cuenta predeterminada en las líneas de diario.</span><span class="sxs-lookup"><span data-stu-id="b19a0-115">This is the offset account that will be the default account on the journal lines.</span></span> <span data-ttu-id="b19a0-116">Es posible anular el valor predeterminado para asignar distintas cuentas de contrapartida por línea.</span><span class="sxs-lookup"><span data-stu-id="b19a0-116">It’s possible to override the default to assign different offset accounts per line.</span></span>  
7. <span data-ttu-id="b19a0-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="b19a0-117">Click OK.</span></span>
8. <span data-ttu-id="b19a0-118">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="b19a0-118">Click New.</span></span>
9. <span data-ttu-id="b19a0-119">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b19a0-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="b19a0-120">Seleccione el artículo A0001.</span><span class="sxs-lookup"><span data-stu-id="b19a0-120">Select item A0001.</span></span>
11. <span data-ttu-id="b19a0-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b19a0-121">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="b19a0-122">Haga clic en la ficha Dimensiones de inventario.</span><span class="sxs-lookup"><span data-stu-id="b19a0-122">Click the Inventory dimensions tab.</span></span>
13. <span data-ttu-id="b19a0-123">En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b19a0-123">In the Site field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="b19a0-124">Seleccione el sitio 1.</span><span class="sxs-lookup"><span data-stu-id="b19a0-124">Select site 1.</span></span>
15. <span data-ttu-id="b19a0-125">En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b19a0-125">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="b19a0-126">Seleccione el almacén 13.</span><span class="sxs-lookup"><span data-stu-id="b19a0-126">Select warehouse 13.</span></span>
17. <span data-ttu-id="b19a0-127">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b19a0-127">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="b19a0-128">En el campo Ubicación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b19a0-128">In the Location field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="b19a0-129">Seleccione la ubicación 13.</span><span class="sxs-lookup"><span data-stu-id="b19a0-129">Select location 13.</span></span>
20. <span data-ttu-id="b19a0-130">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="b19a0-130">In the Quantity field, enter a number.</span></span>
21. <span data-ttu-id="b19a0-131">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b19a0-131">Click Save.</span></span>
22. <span data-ttu-id="b19a0-132">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="b19a0-132">Click Post.</span></span>
23. <span data-ttu-id="b19a0-133">Active o desactive la casilla Transferir todos los errores de registro a un nuevo diario.</span><span class="sxs-lookup"><span data-stu-id="b19a0-133">Check or uncheck the Transfer all posting errors to a new journal check box.</span></span>
    * <span data-ttu-id="b19a0-134">Si activa esta opción, cualquier línea que no pueda registrar se copiará a un nuevo diario.</span><span class="sxs-lookup"><span data-stu-id="b19a0-134">If you enable this option, any lines that fail to post will be copied to a new journal.</span></span> <span data-ttu-id="b19a0-135">Puede usar la información del registro para corregir problemas y después volver a registrar las líneas.</span><span class="sxs-lookup"><span data-stu-id="b19a0-135">You can use the information in the log to correct the issues and then re-post the lines.</span></span>  
24. <span data-ttu-id="b19a0-136">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="b19a0-136">Click OK.</span></span>
25. <span data-ttu-id="b19a0-137">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b19a0-137">Close the page.</span></span>
26. <span data-ttu-id="b19a0-138">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b19a0-138">Close the page.</span></span>


