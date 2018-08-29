--- 
title: Crear estaciones de hardware
description: "Este procedimiento le muestra cómo crear una nueva estación de hardware."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 3551e37c6aae37c01b5cacff8b908faaf75fb3e2
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="create-hardware-stations"></a><span data-ttu-id="0b574-103">Crear estaciones de hardware</span><span class="sxs-lookup"><span data-stu-id="0b574-103">Create hardware stations</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="0b574-104">Este procedimiento le muestra cómo crear una nueva estación de hardware.</span><span class="sxs-lookup"><span data-stu-id="0b574-104">This procedure walks through how to create a new hardware station.</span></span> <span data-ttu-id="0b574-105">Se creará y se usará un nuevo perfil de hardware para agregar nuevas estaciones de hardware a un almacén predefinido (canal).</span><span class="sxs-lookup"><span data-stu-id="0b574-105">A new hardware profile will be created and used to add new hardware stations to a pre-defined store (channel).</span></span> <span data-ttu-id="0b574-106">Este procedimiento usa la empresa USRT en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="0b574-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="0b574-107">Vaya a > Esenciales de comercio > Canales > ..</span><span class="sxs-lookup"><span data-stu-id="0b574-107">Go to Commerce essentials > Channels > ..</span></span> <span data-ttu-id="0b574-108">> ..</span><span class="sxs-lookup"><span data-stu-id="0b574-108">> ..</span></span> <span data-ttu-id="0b574-109">> ..</span><span class="sxs-lookup"><span data-stu-id="0b574-109">> ..</span></span> <span data-ttu-id="0b574-110">> Perfiles de la estación de hardware.</span><span class="sxs-lookup"><span data-stu-id="0b574-110">> Hardware station profiles.</span></span>
2. <span data-ttu-id="0b574-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="0b574-111">Click New.</span></span>
3. <span data-ttu-id="0b574-112">En el campo Id. de la estación de hardware, escriba “TestHWProfile”.</span><span class="sxs-lookup"><span data-stu-id="0b574-112">In the Hardware station ID field, type 'TestHWProfile'.</span></span>
4. <span data-ttu-id="0b574-113">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0b574-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="0b574-114">En el campo Número de puerto, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="0b574-114">In the Port number field, enter a number.</span></span>
6. <span data-ttu-id="0b574-115">En el campo Perfil de hardware, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0b574-115">In the Hardware profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="0b574-116">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="0b574-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="0b574-117">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0b574-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="0b574-118">En el campo Nombre del paquete, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0b574-118">In the Package name field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="0b574-119">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0b574-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="0b574-120">Este es el paquete estándar que se incluye con un nuevo entorno.</span><span class="sxs-lookup"><span data-stu-id="0b574-120">This is the standard package that comes with a new environment.</span></span> <span data-ttu-id="0b574-121">El número de versión puede variar.</span><span class="sxs-lookup"><span data-stu-id="0b574-121">The version number may vary.</span></span>  
11. <span data-ttu-id="0b574-122">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="0b574-122">Click Save.</span></span>
12. <span data-ttu-id="0b574-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0b574-123">Close the page.</span></span>
13. <span data-ttu-id="0b574-124">Vaya a Venta minorista y comercio > Canales > Todas las tiendas minoristas.</span><span class="sxs-lookup"><span data-stu-id="0b574-124">Go to Retail and commerce > Channels > All retail stores.</span></span>
14. <span data-ttu-id="0b574-125">En la lista, seleccione la fila 17.</span><span class="sxs-lookup"><span data-stu-id="0b574-125">In the list, select row 17.</span></span>
    * <span data-ttu-id="0b574-126">Si usa la empresa de datos de demostración de USRT, esta es la tienda de Houston.</span><span class="sxs-lookup"><span data-stu-id="0b574-126">If you are using the USRT demo data company, this is the Houston store.</span></span>  
15. <span data-ttu-id="0b574-127">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0b574-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="0b574-128">Alterne la expansión de la sección Estaciones de hardware.</span><span class="sxs-lookup"><span data-stu-id="0b574-128">Toggle the expansion of the Hardware stations section.</span></span>
17. <span data-ttu-id="0b574-129">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="0b574-129">Click Add.</span></span>
18. <span data-ttu-id="0b574-130">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0b574-130">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="0b574-131">En el campo Id. del perfil, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0b574-131">In the Profile ID field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="0b574-132">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="0b574-132">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="0b574-133">Este debe ser el nuevo perfil de estación de hardware que se creó en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="0b574-133">This must be the new hardware station profile that was created in the previous steps.</span></span>  
21. <span data-ttu-id="0b574-134">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0b574-134">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="0b574-135">En el campo Nombre de host, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0b574-135">In the Host name field, type a value.</span></span>
23. <span data-ttu-id="0b574-136">En el campo Id. de terminal EFT, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0b574-136">In the EFT terminal ID field, type a value.</span></span>
24. <span data-ttu-id="0b574-137">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="0b574-137">Click Save.</span></span>


