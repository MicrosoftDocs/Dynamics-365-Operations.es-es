--- 
title: "Configuración del id. de IVA"
description: "Este procedimiento recorre los requisitos previos de registro del identificador de IVA, como configuración de un tipo de registro y asignación a la categoría del registro."
author: v-oloski
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: ff12ab434d88471452f191cd56b630419e07b22e
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-vat-id"></a><span data-ttu-id="3247b-103">Configuración del id. de IVA</span><span class="sxs-lookup"><span data-stu-id="3247b-103">Set up VAT ID</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3247b-104">Este procedimiento recorre los requisitos previos de registro del identificador de IVA, como configuración de un tipo de registro y asignación a la categoría del registro.</span><span class="sxs-lookup"><span data-stu-id="3247b-104">This procedure walks you through VAT ID registration prerequisites, such as setting up a registration type and assigning it to a registration category.</span></span> <span data-ttu-id="3247b-105">Puede obtener información adicional acerca del identificador de registro y el procesamiento del identificador de registro, incluidas requisitos previos necesarios, en el tema de ayuda Id. de registro.</span><span class="sxs-lookup"><span data-stu-id="3247b-105">You can find additional information about registration IDs and registration ID processing, including required prerequisites, in the Registration IDs help topic.</span></span> 

<span data-ttu-id="3247b-106">Esta información se aplica a todos los países o regiones europeos.</span><span class="sxs-lookup"><span data-stu-id="3247b-106">The information here applies to all European countries/regions.</span></span> <span data-ttu-id="3247b-107">La tarea se ha creado con los datos de demostración de la empresa DEMF y con una dirección principal de entidad jurídica en Alemania.</span><span class="sxs-lookup"><span data-stu-id="3247b-107">The task was created using the demo data company DEMF with Germany as the legal entity primary address.</span></span> <span data-ttu-id="3247b-108">Esta tarea está destinada a administradores del sistema.</span><span class="sxs-lookup"><span data-stu-id="3247b-108">This task is intended for system administrators.</span></span> <span data-ttu-id="3247b-109">Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="3247b-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="3247b-110">Vaya a Administración de la organización > Libreta de direcciones global > Tipos de registro > Tipos de registro.</span><span class="sxs-lookup"><span data-stu-id="3247b-110">Go to Organization administration > Global address book > Registration types > Registration types.</span></span>
2. <span data-ttu-id="3247b-111">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="3247b-111">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="3247b-112">En el campo Nombre, escriba "Id. de IVA".</span><span class="sxs-lookup"><span data-stu-id="3247b-112">In the Name field, type 'VAT ID'.</span></span>
4. <span data-ttu-id="3247b-113">En el campo Descripción, número de IVA.</span><span class="sxs-lookup"><span data-stu-id="3247b-113">In the Description field, VAT number.</span></span>
5. <span data-ttu-id="3247b-114">En el campo País o región, especifique o seleccione un valor DEU</span><span class="sxs-lookup"><span data-stu-id="3247b-114">In the Country/region field, enter or select a value DEU</span></span>
6. <span data-ttu-id="3247b-115">Seleccione Sí en el campo Único.</span><span class="sxs-lookup"><span data-stu-id="3247b-115">Select Yes in the Unique field.</span></span>
    * <span data-ttu-id="3247b-116">Seleccione esta casilla para comprobar si el Id. de IVA es único.</span><span class="sxs-lookup"><span data-stu-id="3247b-116">Select this check box to verify if the VAT ID is unique.</span></span>  
7. <span data-ttu-id="3247b-117">Seleccione Sí en el campo Principal para país.</span><span class="sxs-lookup"><span data-stu-id="3247b-117">Select Yes in the Primary for country field.</span></span>
    * <span data-ttu-id="3247b-118">Seleccione esta casilla si el Id. de IVA debe ser efectivo para todas las direcciones que pertenecen al país/región especificados.</span><span class="sxs-lookup"><span data-stu-id="3247b-118">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
8. <span data-ttu-id="3247b-119">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="3247b-119">Click Create.</span></span>
9. <span data-ttu-id="3247b-120">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="3247b-120">Click Add.</span></span>
10. <span data-ttu-id="3247b-121">En el campo País o región, especifique o seleccione un valor ITA</span><span class="sxs-lookup"><span data-stu-id="3247b-121">In the Country/region field, enter or select a value ITA</span></span>
11. <span data-ttu-id="3247b-122">En el campo Formato, escriba "###########".</span><span class="sxs-lookup"><span data-stu-id="3247b-122">In the Format field, type '###########'.</span></span>
    * <span data-ttu-id="3247b-123">Cuando se especifica un identificador de registro de este tipo para el país o la región seleccionada, el identificador de registro se comprueba según este formato.</span><span class="sxs-lookup"><span data-stu-id="3247b-123">When you enter a registration ID of this type for the selected country/region, the registration ID will be verified against this format.</span></span>  
12. <span data-ttu-id="3247b-124">Seleccione la casilla Único.</span><span class="sxs-lookup"><span data-stu-id="3247b-124">Select the Unique check box.</span></span>
    * <span data-ttu-id="3247b-125">Seleccione esta casilla para comprobar si el Id. de IVA es único.</span><span class="sxs-lookup"><span data-stu-id="3247b-125">Select this check box to verify if the VAT ID is unique.</span></span>  
13. <span data-ttu-id="3247b-126">Seleccione la casilla Principal para país.</span><span class="sxs-lookup"><span data-stu-id="3247b-126">Select the Primary for country check box.</span></span>
    * <span data-ttu-id="3247b-127">Seleccione esta casilla si el Id. de IVA debe ser efectivo para todas las direcciones que pertenecen al país/región especificados.</span><span class="sxs-lookup"><span data-stu-id="3247b-127">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
14. <span data-ttu-id="3247b-128">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3247b-128">Click Save.</span></span>
15. <span data-ttu-id="3247b-129">Vaya a Administración de la organización > Libreta de direcciones global > Tipos de registro > Categorías de registro.</span><span class="sxs-lookup"><span data-stu-id="3247b-129">Go to Organization administration > Global address book > Registration types > Registration categories.</span></span>
16. <span data-ttu-id="3247b-130">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3247b-130">Click New.</span></span>
17. <span data-ttu-id="3247b-131">En el campo País o región, especifique o seleccione un valor Id. de IVA, DEU</span><span class="sxs-lookup"><span data-stu-id="3247b-131">In the Country/region field, enter or select a value VAT ID, DEU</span></span>
18. <span data-ttu-id="3247b-132">En el campo Categoría de registro, seleccione "Id. de IVA".</span><span class="sxs-lookup"><span data-stu-id="3247b-132">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="3247b-133">Asigne el tipo de registro que ha creado anteriormente a una categoría de registro predefinida.</span><span class="sxs-lookup"><span data-stu-id="3247b-133">Assign the registration type that you created earlier to a predefined Registration category.</span></span>  
19. <span data-ttu-id="3247b-134">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3247b-134">Click New.</span></span>
20. <span data-ttu-id="3247b-135">En el campo País o región, especifique o seleccione un valor Id. de IVA, ITA</span><span class="sxs-lookup"><span data-stu-id="3247b-135">In the Country/region field, enter or select a value VAT ID, ITA</span></span>
21. <span data-ttu-id="3247b-136">En el campo Categoría de registro, seleccione "Id. de IVA".</span><span class="sxs-lookup"><span data-stu-id="3247b-136">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="3247b-137">Asigne el tipo de registro que ha creado a una categoría de registro predefinida.</span><span class="sxs-lookup"><span data-stu-id="3247b-137">Assign the registration type that you created to a predefined registration category.</span></span>  
22. <span data-ttu-id="3247b-138">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3247b-138">Click Save.</span></span>


