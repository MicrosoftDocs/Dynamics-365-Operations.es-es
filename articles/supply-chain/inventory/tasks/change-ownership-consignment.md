---
title: Cambiar la propiedad del inventario de entrega en base a la demanda de la producción
description: Este procedimiento muestra cómo cambiar el propietario del inventario de entrega del proveedor a su entidad jurídica cuando hay demanda del inventario en producción.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1324da6996230eb383e2f37d3a133ec35cb0f41
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550056"
---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a><span data-ttu-id="d2ad6-103">Cambiar la propiedad del inventario de entrega en base a la demanda de la producción</span><span class="sxs-lookup"><span data-stu-id="d2ad6-103">Change the ownership of consignment inventory based on production demand</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d2ad6-104">Este procedimiento muestra cómo cambiar el propietario del inventario de entrega del proveedor a su entidad jurídica cuando hay demanda del inventario en producción.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-104">This procedure shows how to change the owner of consignment inventory from the vendor to your legal entity when there is demand for the inventory in production.</span></span> <span data-ttu-id="d2ad6-105">Este cambio de propiedad se hace creando y registrando un diario de cambio de propiedad del inventario.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-105">This change of ownership is done by creating and posting an inventory ownership change journal.</span></span> <span data-ttu-id="d2ad6-106">Las líneas de diario de cambio de propiedad se pueden crear manualmente o, tal como se muestra en este registro, en función de la demanda existente de la producción.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-106">The ownership change journal lines can be created manually or, as shown in this recording, based on existing production demand.</span></span> <span data-ttu-id="d2ad6-107">Normalmente, un supervisor de planta realiza esta tarea.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-107">Typically, a shop floor supervisor performs this task.</span></span> <span data-ttu-id="d2ad6-108">Puede utilizar este procedimiento en la empresa de demostración USMF o en sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-108">You can use this procedure in the USMF demo data company or on your own data.</span></span> <span data-ttu-id="d2ad6-109">Si utiliza sus propios datos, asegúrese de que tiene los requisitos previos siguientes: un nombre de diario de inventario que se ha configurado para el cambio de propiedad de inventario, artículos disponibles propiedad del proveedor registrados físicamente y una o más líneas de pedido de producción del material.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-109">If you're using your own data, make sure that you have the following prerequisites: an inventory journal name that has been set up for inventory ownership change, physically recorded vendor-owned on-hand items, and one or more production order lines for the material.</span></span> <span data-ttu-id="d2ad6-110">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-110">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-an-inventory-ownership-journal"></a><span data-ttu-id="d2ad6-111">Crear un diario de propiedad de inventario</span><span class="sxs-lookup"><span data-stu-id="d2ad6-111">Create an inventory ownership journal</span></span>
1. <span data-ttu-id="d2ad6-112">Ir a Gestión del inventario > Entradas de diario > Artículos > Cambio de propiedad de inventario.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-112">Go to Inventory management > Journal entries > Items > Inventory ownership change.</span></span>
2. <span data-ttu-id="d2ad6-113">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-113">Click New.</span></span>
    * <span data-ttu-id="d2ad6-114">El diario de cambio de propiedad de inventario se usa para cambiar el propietario del inventario de entrega del proveedor a la entidad jurídica actual.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-114">The inventory ownership change journal is used to change the owner of consignment inventory from the vendor to the current legal entity.</span></span> <span data-ttu-id="d2ad6-115">Este cambio de propiedad se hace liberando el inventario disponible propiedad del proveedor y posteriormente recibiendo ese inventario en la entidad jurídica actual.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-115">This change of ownership is done by releasing the on-hand inventory that is owned by the vendor and then receiving that inventory in the current legal entity.</span></span>  
3. <span data-ttu-id="d2ad6-116">En el campo Nombre, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-116">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="d2ad6-117">Solo puede seleccionar los nombres de diarios de inventario que tengan el tipo de diario Cambio de propiedad.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-117">You can select only inventory journal names that have a journal type of Ownership change.</span></span>  
4. <span data-ttu-id="d2ad6-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d2ad6-118">Click OK.</span></span>
5. <span data-ttu-id="d2ad6-119">Haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-119">Click Functions.</span></span>
6. <span data-ttu-id="d2ad6-120">Haga clic en Crear líneas de diario a partir de pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-120">Click Create journal lines from production orders.</span></span>
    * <span data-ttu-id="d2ad6-121">Puede iniciar el proceso de cambio de propiedad si consulta todas las líneas de producción que tienen demanda de consumo de materias primas.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-121">You can start the change of ownership process by querying all the production lines that have demand for consumption of raw material.</span></span>  
7. <span data-ttu-id="d2ad6-122">En el campo Estados de emisión de inventario que incluir, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-122">In the Inventory issue statuses to include field, select an option.</span></span>
    * <span data-ttu-id="d2ad6-123">Esta opción permite filtrar por el estado de emisión de las transacciones de inventario.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-123">This option lets you filter by the issue status of the inventory transactions.</span></span> <span data-ttu-id="d2ad6-124">Por ejemplo, puede crear líneas de diario para el inventario con los estados Seleccionado y Física reservada.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-124">For example, you can create journal lines for inventory that has the Picked and Reserved physical statuses.</span></span>  
8. <span data-ttu-id="d2ad6-125">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-125">Expand the Records to include section.</span></span>
    * <span data-ttu-id="d2ad6-126">Esta sección le permite aplicar filtrado adicional.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-126">This section lets you apply additional filtering.</span></span> <span data-ttu-id="d2ad6-127">Por ejemplo, puede seleccionar una fecha específica de la materia prima.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-127">For example, you can select a specific raw material date.</span></span>  
9. <span data-ttu-id="d2ad6-128">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d2ad6-128">Click OK.</span></span>

## <a name="post-the-inventory-ownership-change-journal"></a><span data-ttu-id="d2ad6-129">Registrar el diario de cambio de propiedad de inventario</span><span class="sxs-lookup"><span data-stu-id="d2ad6-129">Post the inventory ownership change journal</span></span>
1. <span data-ttu-id="d2ad6-130">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-130">Click Post.</span></span>
    * <span data-ttu-id="d2ad6-131">Cuando se registra el diario, el inventario propiedad del proveedor se libera usando la referencia "Cambio de propiedad".</span><span class="sxs-lookup"><span data-stu-id="d2ad6-131">When the journal is posted, the vendor-owned inventory is released by using an "Ownership change" reference.</span></span> <span data-ttu-id="d2ad6-132">El inventario se recibe como disponible usando una transacción de inventario que se actualiza con una recepción de producto del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-132">The inventory is then received as on-hand by using an inventory transaction that is updated with a purchase order product receipt.</span></span> <span data-ttu-id="d2ad6-133">Tenga en cuenta que sólo se crean las transacciones relacionadas con el diario registrado.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-133">Note that only transactions that are related to the posted journal are created.</span></span> <span data-ttu-id="d2ad6-134">No se crean transacciones de inventario previstas.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-134">No expected inventory transactions are created.</span></span>  
2. <span data-ttu-id="d2ad6-135">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d2ad6-135">Click OK.</span></span>
3. <span data-ttu-id="d2ad6-136">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d2ad6-136">Close the page.</span></span>

