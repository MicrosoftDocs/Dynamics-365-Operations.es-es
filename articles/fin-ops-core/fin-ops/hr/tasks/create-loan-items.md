---
title: Crear artículos de préstamo
description: Los artículos en préstamo son registros que ayudan a realizar un seguimiento de los artículos físicos que su empresa presta a los trabajadores, como teléfonos u ordenadores.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 75b2f17eb41ead7422276f72429eb6ede2ef4759
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179890"
---
# <a name="create-loan-items"></a><span data-ttu-id="a5ec4-103">Crear artículos de préstamo</span><span class="sxs-lookup"><span data-stu-id="a5ec4-103">Create loan items</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a5ec4-104">Los artículos en préstamo son registros que ayudan a realizar un seguimiento de los artículos físicos que su empresa presta a los trabajadores, como teléfonos u ordenadores.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-104">Loan items are records that help you track physical items, such as phones or computers, that your company lends to workers.</span></span> <span data-ttu-id="a5ec4-105">Cada artículo físico debe tener un artículo correspondiente de préstamo.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-105">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="a5ec4-106">Cada registro de los artículos de préstamo debe describir lo que se está prestando, la persona responsable del préstamo y el número de días que se puede prestar el artículo.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-106">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can be on loan.</span></span> <span data-ttu-id="a5ec4-107">Puede crear varios artículos en préstamo al mismo tiempo, como llaves, tarjetas de acceso o uniformes.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-107">You can create multiple loan items, such as keys, access cards, or uniforms, at the same time.</span></span> <span data-ttu-id="a5ec4-108">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-loan-types"></a><span data-ttu-id="a5ec4-109">Creación de tipos de préstamo</span><span class="sxs-lookup"><span data-stu-id="a5ec4-109">Create Loan types</span></span>
1. <span data-ttu-id="a5ec4-110">Vaya a Recursos humanos > Trabajadores > Artículos de préstamo > Tipos de préstamo.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-110">Go to Human resources > Workers > Loan items > Loan types.</span></span>
2. <span data-ttu-id="a5ec4-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-111">Click New.</span></span>
3. <span data-ttu-id="a5ec4-112">En el campo Tipo de préstamos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-112">In the Loan type field, type a value.</span></span>
4. <span data-ttu-id="a5ec4-113">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a5ec4-114">Especifique el número de días en los que se pueden devolver los artículos asignados a este tipo de préstamo una vez vencida la fecha de devolución.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-114">Enter the number of days that items assigned to this loan type can be overdue.</span></span> 
6. <span data-ttu-id="a5ec4-115">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-115">Click Save.</span></span>
7. <span data-ttu-id="a5ec4-116">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-116">Close the page.</span></span>
8. <span data-ttu-id="a5ec4-117">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-117">Refresh the page.</span></span>

## <a name="create-loan-items"></a><span data-ttu-id="a5ec4-118">Creación de artículos de préstamo</span><span class="sxs-lookup"><span data-stu-id="a5ec4-118">Create Loan items</span></span>
1. <span data-ttu-id="a5ec4-119">Vaya a Recursos humanos > Trabajadores > Artículos de préstamo > Artículos de préstamo.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-119">Go to Human resources > Workers > Loan items > Loan items.</span></span>
2. <span data-ttu-id="a5ec4-120">Haga clic en Crear artículos de préstamo.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-120">Click Create loan items.</span></span>
3. <span data-ttu-id="a5ec4-121">En el campo Cant., especifique un número.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-121">In the Qty. field, enter a number.</span></span>
4. <span data-ttu-id="a5ec4-122">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-122">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a5ec4-123">En el campo Tipo de préstamo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-123">In the Loan type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="a5ec4-124">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-124">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="a5ec4-125">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="a5ec4-126">Escribir el número de días en el que el artículo puede estar en préstamo.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-126">Enter the number of days the item can be on loan.</span></span>
    * <span data-ttu-id="a5ec4-127">El valor predeterminado del campo Devolución planificada en la página Equipo prestado se calcula como la fecha en curso más este número.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-127">The default value for the Planned return field on the Loaned equipment page is calculated as the current date plus this number.</span></span>  
9. <span data-ttu-id="a5ec4-128">En el campo Persona a cargo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-128">In the Person in charge field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="a5ec4-129">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-129">Click Select.</span></span>
11. <span data-ttu-id="a5ec4-130">En el campo Valor inicial, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-130">In the Starting value field, enter a number.</span></span>
12. <span data-ttu-id="a5ec4-131">Escriba un número en el campo Intervalo.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-131">In the Interval field, enter a number.</span></span>
13. <span data-ttu-id="a5ec4-132">En el campo Formato, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-132">In the Format field, type a value.</span></span>
    * <span data-ttu-id="a5ec4-133">Por ejemplo, si el número de inicio para un artículo en préstamo es 10, especifique dos símbolos de almohadilla en el campo Formato.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-133">For example, if the starting number for a loan item is 10, enter two number symbols symbols in the Format field.</span></span>  
14. <span data-ttu-id="a5ec4-134">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a5ec4-134">Click OK.</span></span>
15. <span data-ttu-id="a5ec4-135">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="a5ec4-135">Refresh the page.</span></span>

