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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 65655283c70c99b5d64289b319ecc69f6e414221
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="create-loan-items"></a><span data-ttu-id="e0612-103">Crear artículos de préstamo</span><span class="sxs-lookup"><span data-stu-id="e0612-103">Create loan items</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e0612-104">Los artículos en préstamo son registros que ayudan a realizar un seguimiento de los artículos físicos que su empresa presta a los trabajadores, como teléfonos u ordenadores.</span><span class="sxs-lookup"><span data-stu-id="e0612-104">Loan items are records that help you track physical items, such as phones or computers, that your company lends to workers.</span></span> <span data-ttu-id="e0612-105">Cada artículo físico debe tener un artículo correspondiente de préstamo.</span><span class="sxs-lookup"><span data-stu-id="e0612-105">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="e0612-106">Cada registro de los artículos de préstamo debe describir lo que se está prestando, la persona responsable del préstamo y el número de días que se puede prestar el artículo.</span><span class="sxs-lookup"><span data-stu-id="e0612-106">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can be on loan.</span></span> <span data-ttu-id="e0612-107">Puede crear varios artículos en préstamo al mismo tiempo, como llaves, tarjetas de acceso o uniformes.</span><span class="sxs-lookup"><span data-stu-id="e0612-107">You can create multiple loan items, such as keys, access cards, or uniforms, at the same time.</span></span> <span data-ttu-id="e0612-108">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="e0612-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-loan-types"></a><span data-ttu-id="e0612-109">Creación de tipos de préstamo</span><span class="sxs-lookup"><span data-stu-id="e0612-109">Create Loan types</span></span>
1. <span data-ttu-id="e0612-110">Vaya a Recursos humanos > Trabajadores > Artículos de préstamo > Tipos de préstamo.</span><span class="sxs-lookup"><span data-stu-id="e0612-110">Go to Human resources > Workers > Loan items > Loan types.</span></span>
2. <span data-ttu-id="e0612-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="e0612-111">Click New.</span></span>
3. <span data-ttu-id="e0612-112">En el campo Tipo de préstamos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e0612-112">In the Loan type field, type a value.</span></span>
4. <span data-ttu-id="e0612-113">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e0612-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e0612-114">Especifique el número de días en los que se pueden devolver los artículos asignados a este tipo de préstamo una vez vencida la fecha de devolución.</span><span class="sxs-lookup"><span data-stu-id="e0612-114">Enter the number of days that items assigned to this loan type can be overdue.</span></span> 
6. <span data-ttu-id="e0612-115">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e0612-115">Click Save.</span></span>
7. <span data-ttu-id="e0612-116">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e0612-116">Close the page.</span></span>
8. <span data-ttu-id="e0612-117">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="e0612-117">Refresh the page.</span></span>

## <a name="create-loan-items"></a><span data-ttu-id="e0612-118">Creación de artículos de préstamo</span><span class="sxs-lookup"><span data-stu-id="e0612-118">Create Loan items</span></span>
1. <span data-ttu-id="e0612-119">Vaya a Recursos humanos > Trabajadores > Artículos de préstamo > Artículos de préstamo.</span><span class="sxs-lookup"><span data-stu-id="e0612-119">Go to Human resources > Workers > Loan items > Loan items.</span></span>
2. <span data-ttu-id="e0612-120">Haga clic en Crear artículos de préstamo.</span><span class="sxs-lookup"><span data-stu-id="e0612-120">Click Create loan items.</span></span>
3. <span data-ttu-id="e0612-121">En el campo Cant.,</span><span class="sxs-lookup"><span data-stu-id="e0612-121">In the Qty.</span></span> <span data-ttu-id="e0612-122">especifique un número.</span><span class="sxs-lookup"><span data-stu-id="e0612-122">field, enter a number.</span></span>
4. <span data-ttu-id="e0612-123">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e0612-123">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e0612-124">En el campo Tipo de préstamo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e0612-124">In the Loan type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="e0612-125">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e0612-125">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="e0612-126">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e0612-126">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="e0612-127">Escribir el número de días en el que el artículo puede estar en préstamo.</span><span class="sxs-lookup"><span data-stu-id="e0612-127">Enter the number of days the item can be on loan.</span></span>
    * <span data-ttu-id="e0612-128">El valor predeterminado del campo Devolución planificada en la página Equipo prestado se calcula como la fecha en curso más este número.</span><span class="sxs-lookup"><span data-stu-id="e0612-128">The default value for the Planned return field on the Loaned equipment page is calculated as the current date plus this number.</span></span>  
9. <span data-ttu-id="e0612-129">En el campo Persona a cargo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e0612-129">In the Person in charge field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="e0612-130">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="e0612-130">Click Select.</span></span>
11. <span data-ttu-id="e0612-131">En el campo Valor inicial, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="e0612-131">In the Starting value field, enter a number.</span></span>
12. <span data-ttu-id="e0612-132">Escriba un número en el campo Intervalo.</span><span class="sxs-lookup"><span data-stu-id="e0612-132">In the Interval field, enter a number.</span></span>
13. <span data-ttu-id="e0612-133">En el campo Formato, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e0612-133">In the Format field, type a value.</span></span>
    * <span data-ttu-id="e0612-134">Por ejemplo, si el número de inicio para un artículo en préstamo es 10, especifique dos símbolos de almohadilla en el campo Formato.</span><span class="sxs-lookup"><span data-stu-id="e0612-134">For example, if the starting number for a loan item is 10, enter two number symbols symbols in the Format field.</span></span>  
14. <span data-ttu-id="e0612-135">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e0612-135">Click OK.</span></span>
15. <span data-ttu-id="e0612-136">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="e0612-136">Refresh the page.</span></span>


