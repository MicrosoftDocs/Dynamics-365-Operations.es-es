--- 
title: Configurar uso compartido de datos financieros entre empresas
description: "Este procedimiento muestra cómo configurar, habilitar, validar y resolver conflictos al compartir datos entre empresas."
author: aprilolson
manager: AnnBe
ms.date: 06/22/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: margoc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 547e5d82defbf004335e1c5fcd5e2cd7013e1b63
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="configure-financial-cross-company-data-sharing"></a><span data-ttu-id="0b935-103">Configurar uso compartido de datos financieros entre empresas</span><span class="sxs-lookup"><span data-stu-id="0b935-103">Configure financial cross-company data sharing</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0b935-104">Este procedimiento muestra cómo configurar, habilitar, validar y resolver conflictos al compartir datos entre empresas.</span><span class="sxs-lookup"><span data-stu-id="0b935-104">This procedure shows how to configure, enable, validate, and resolve conflicts when sharing data between companies.</span></span> <span data-ttu-id="0b935-105">Usa la empresa USMF y la plantilla de uso compartido de datos financieros.</span><span class="sxs-lookup"><span data-stu-id="0b935-105">It uses the USMF company and the Financial data sharing template.</span></span>



<span data-ttu-id="0b935-106">Esta guía de tareas requiere la plataforma Dynamics AX 7.1 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="0b935-106">This task guide requires Dynamics AX platform 7.1 or later.</span></span>

1. <span data-ttu-id="0b935-107">Vaya a Administración del sistema > Áreas de trabajo > Administración de datos.</span><span class="sxs-lookup"><span data-stu-id="0b935-107">Go to System administration > Workspaces > Data management.</span></span>
2. <span data-ttu-id="0b935-108">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="0b935-108">Click Import.</span></span>
3. <span data-ttu-id="0b935-109">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0b935-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="0b935-110">En el campo Formato de datos de origen, seleccione el Tipo de paquete.</span><span class="sxs-lookup"><span data-stu-id="0b935-110">In the Source data format field, select the Package type.</span></span>
    * <span data-ttu-id="0b935-111">Haga clic en Cargar.</span><span class="sxs-lookup"><span data-stu-id="0b935-111">Click Upload.</span></span> <span data-ttu-id="0b935-112">Desplácese hasta la ubicación de los datos financieros que compartan el archivo del paquete de la plantilla y seleccione ese archivo.</span><span class="sxs-lookup"><span data-stu-id="0b935-112">Navigate to the location of the Financial data sharing template package file and select that file.</span></span>  
5. <span data-ttu-id="0b935-113">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="0b935-113">Click Save.</span></span>
6. <span data-ttu-id="0b935-114">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0b935-114">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0b935-115">Seleccione la directiva de uso compartido de datos que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="0b935-115">Select the data sharing policy that was just created.</span></span>  
7. <span data-ttu-id="0b935-116">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="0b935-116">Click Import.</span></span>
8. <span data-ttu-id="0b935-117">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="0b935-117">Click Close.</span></span>
9. <span data-ttu-id="0b935-118">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="0b935-118">Refresh the page.</span></span>
10. <span data-ttu-id="0b935-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0b935-119">Close the page.</span></span>
11. <span data-ttu-id="0b935-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0b935-120">Close the page.</span></span>
12. <span data-ttu-id="0b935-121">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0b935-121">Close the page.</span></span>
13. <span data-ttu-id="0b935-122">Vaya a Administración del sistema > Configurar > Configurar uso compartido de datos entre empresas.</span><span class="sxs-lookup"><span data-stu-id="0b935-122">Go to System administration > Setup > Configure cross-company data sharing.</span></span>
14. <span data-ttu-id="0b935-123">En la lista, busque y seleccione Días de pago.</span><span class="sxs-lookup"><span data-stu-id="0b935-123">In the list, find and select Payment days.</span></span>
15. <span data-ttu-id="0b935-124">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="0b935-124">Click Add.</span></span>
16. <span data-ttu-id="0b935-125">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0b935-125">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="0b935-126">En el campo Empresa, escriba "USSI".</span><span class="sxs-lookup"><span data-stu-id="0b935-126">In the Company field, type 'USSI'.</span></span>
18. <span data-ttu-id="0b935-127">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="0b935-127">Click Add.</span></span>
19. <span data-ttu-id="0b935-128">En el campo Empresa, escriba "USMF".</span><span class="sxs-lookup"><span data-stu-id="0b935-128">In the Company field, type 'USMF'.</span></span>
20. <span data-ttu-id="0b935-129">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="0b935-129">Click Save.</span></span>
21. <span data-ttu-id="0b935-130">Haga clic en Habilitar.</span><span class="sxs-lookup"><span data-stu-id="0b935-130">Click Enable.</span></span>
22. <span data-ttu-id="0b935-131">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="0b935-131">Click Yes.</span></span>
23. <span data-ttu-id="0b935-132">Haga clic en Buscar problemas de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="0b935-132">Click Find sharing issues.</span></span>
24. <span data-ttu-id="0b935-133">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="0b935-133">Click Yes.</span></span>
25. <span data-ttu-id="0b935-134">Haga clic en el valor de campo Actualizar.</span><span class="sxs-lookup"><span data-stu-id="0b935-134">Click Update field value.</span></span>
26. <span data-ttu-id="0b935-135">Haga clic en Usar valor de la empresa 1.</span><span class="sxs-lookup"><span data-stu-id="0b935-135">Click Use value from company 1.</span></span>
27. <span data-ttu-id="0b935-136">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="0b935-136">Refresh the page.</span></span>
28. <span data-ttu-id="0b935-137">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0b935-137">Close the page.</span></span>


