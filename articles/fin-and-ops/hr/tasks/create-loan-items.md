--- 
title: "Crear artículos de préstamo"
description: "Los artículos en préstamo son registros que ayudan a realizar un seguimiento de los artículos físicos que su empresa presta a los trabajadores, como teléfonos u ordenadores."
author: kherr75
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: cef1f9b2e3d202d7eea3a967fa8a6c371c6ac3a5
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-loan-items"></a><span data-ttu-id="3c7a6-103">Crear artículos de préstamo</span><span class="sxs-lookup"><span data-stu-id="3c7a6-103">Create loan items</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3c7a6-104">Los artículos en préstamo son registros que ayudan a realizar un seguimiento de los artículos físicos que su empresa presta a los trabajadores, como teléfonos u ordenadores.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-104">Loan items are records that help you track physical items, such as phones or computers, that your company lends to workers.</span></span> <span data-ttu-id="3c7a6-105">Cada artículo físico debe tener un artículo correspondiente de préstamo.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-105">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="3c7a6-106">Cada registro de los artículos de préstamo debe describir lo que se está prestando, la persona responsable del préstamo y el número de días que se puede prestar el artículo.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-106">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can be on loan.</span></span> <span data-ttu-id="3c7a6-107">Puede crear varios artículos en préstamo al mismo tiempo, como llaves, tarjetas de acceso o uniformes.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-107">You can create multiple loan items, such as keys, access cards, or uniforms, at the same time.</span></span> <span data-ttu-id="3c7a6-108">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-loan-types"></a><span data-ttu-id="3c7a6-109">Creación de tipos de préstamo</span><span class="sxs-lookup"><span data-stu-id="3c7a6-109">Create Loan types</span></span>
1. <span data-ttu-id="3c7a6-110">Vaya a Recursos humanos > Trabajadores > Artículos de préstamo > Tipos de préstamo.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-110">Go to Human resources > Workers > Loan items > Loan types.</span></span>
2. <span data-ttu-id="3c7a6-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-111">Click New.</span></span>
3. <span data-ttu-id="3c7a6-112">En el campo Tipo de préstamos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-112">In the Loan type field, type a value.</span></span>
4. <span data-ttu-id="3c7a6-113">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3c7a6-114">Especifique el número de días en los que se pueden devolver los artículos asignados a este tipo de préstamo una vez vencida la fecha de devolución.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-114">Enter the number of days that items assigned to this loan type can be overdue.</span></span> 
6. <span data-ttu-id="3c7a6-115">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-115">Click Save.</span></span>
7. <span data-ttu-id="3c7a6-116">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-116">Close the page.</span></span>
8. <span data-ttu-id="3c7a6-117">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-117">Refresh the page.</span></span>

## <a name="create-loan-items"></a><span data-ttu-id="3c7a6-118">Creación de artículos de préstamo</span><span class="sxs-lookup"><span data-stu-id="3c7a6-118">Create Loan items</span></span>
1. <span data-ttu-id="3c7a6-119">Vaya a Recursos humanos > Trabajadores > Artículos de préstamo > Artículos de préstamo.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-119">Go to Human resources > Workers > Loan items > Loan items.</span></span>
2. <span data-ttu-id="3c7a6-120">Haga clic en Crear artículos de préstamo.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-120">Click Create loan items.</span></span>
3. <span data-ttu-id="3c7a6-121">En el campo Cant., especifique un número.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-121">In the Qty. field, enter a number.</span></span>
4. <span data-ttu-id="3c7a6-122">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-122">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3c7a6-123">En el campo Tipo de préstamo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-123">In the Loan type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="3c7a6-124">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-124">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="3c7a6-125">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="3c7a6-126">Escribir el número de días en el que el artículo puede estar en préstamo.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-126">Enter the number of days the item can be on loan.</span></span>
    * <span data-ttu-id="3c7a6-127">El valor predeterminado del campo Devolución planificada en la página Equipo prestado se calcula como la fecha en curso más este número.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-127">The default value for the Planned return field on the Loaned equipment page is calculated as the current date plus this number.</span></span>  
9. <span data-ttu-id="3c7a6-128">En el campo Persona a cargo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-128">In the Person in charge field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="3c7a6-129">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-129">Click Select.</span></span>
11. <span data-ttu-id="3c7a6-130">En el campo Valor inicial, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-130">In the Starting value field, enter a number.</span></span>
12. <span data-ttu-id="3c7a6-131">Escriba un número en el campo Intervalo.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-131">In the Interval field, enter a number.</span></span>
13. <span data-ttu-id="3c7a6-132">En el campo Formato, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-132">In the Format field, type a value.</span></span>
    * <span data-ttu-id="3c7a6-133">Por ejemplo, si el número de inicio para un artículo en préstamo es 10, especifique dos símbolos de almohadilla en el campo Formato.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-133">For example, if the starting number for a loan item is 10, enter two number symbols symbols in the Format field.</span></span>  
14. <span data-ttu-id="3c7a6-134">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3c7a6-134">Click OK.</span></span>
15. <span data-ttu-id="3c7a6-135">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="3c7a6-135">Refresh the page.</span></span>


