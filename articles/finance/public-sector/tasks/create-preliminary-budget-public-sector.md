---
title: Creación de un presupuesto preliminar para el sector público
description: Puede crear entradas de registro de presupuesto preliminar para un modelo presupuestario concreto y valores de dimensión.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 800b7009f023bd2a0d8437b81d82c0e9de770841
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174383"
---
# <a name="create-a-preliminary-budget-for-public-sector"></a><span data-ttu-id="56d0b-103">Creación de un presupuesto preliminar para el sector público</span><span class="sxs-lookup"><span data-stu-id="56d0b-103">Create a preliminary budget for Public sector</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="56d0b-104">Puede crear entradas de registro de presupuesto preliminar para un modelo presupuestario concreto y valores de dimensión.</span><span class="sxs-lookup"><span data-stu-id="56d0b-104">You can create preliminary budget register entries for a specific budget model and dimension values.</span></span> <span data-ttu-id="56d0b-105">Después de que se apruebe el presupuesto real, puede crear entradas de registro presupuestarias original.</span><span class="sxs-lookup"><span data-stu-id="56d0b-105">After the actual budget is approved, you can create original budget register entries.</span></span> <span data-ttu-id="56d0b-106">Este procedimiento se ha creado con los datos de empresa de demostración PSUS en la partición del sector público.</span><span class="sxs-lookup"><span data-stu-id="56d0b-106">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="56d0b-107">Vaya a Gestión presupuestaria > Entradas de registro presupuestario.</span><span class="sxs-lookup"><span data-stu-id="56d0b-107">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="56d0b-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="56d0b-108">Click New.</span></span>
3. <span data-ttu-id="56d0b-109">En el campo Modelo presupuestario, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="56d0b-109">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="56d0b-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="56d0b-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="56d0b-111">En el campo Código presupuestario, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="56d0b-111">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="56d0b-112">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="56d0b-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="56d0b-113">En el campo Código de motivo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="56d0b-113">In the Reason code field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="56d0b-114">En la lista, haga clic en el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="56d0b-114">In the list, click the desired record.</span></span>
9. <span data-ttu-id="56d0b-115">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="56d0b-115">Click Save.</span></span>
10. <span data-ttu-id="56d0b-116">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="56d0b-116">Click Add line.</span></span>
    * <span data-ttu-id="56d0b-117">Opcional: Si desea cambiar la fecha de la que se encuentra en el encabezado, especifique una fecha nueva.</span><span class="sxs-lookup"><span data-stu-id="56d0b-117">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="56d0b-118">Esta fecha determina el período fiscal en el que registrará el presupuesto.</span><span class="sxs-lookup"><span data-stu-id="56d0b-118">This date determines the fiscal period that the budget will be recorded to.</span></span> <span data-ttu-id="56d0b-119">Al ver la guía de tareas, para rellenar otros campos, haga clic en Desbloquear en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="56d0b-119">When viewing the task guide, to fill out other fields, click Unlock at the top of the page.</span></span>  
11. <span data-ttu-id="56d0b-120">En el campo Estructura contable, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="56d0b-120">In the Account structure field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="56d0b-121">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="56d0b-121">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="56d0b-122">En el campo Valores de dimensión, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="56d0b-122">In the Dimension values field, specify the desired values.</span></span>
14. <span data-ttu-id="56d0b-123">En el campo Importe, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="56d0b-123">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="56d0b-124">También puede especificar un tipo de importe.</span><span class="sxs-lookup"><span data-stu-id="56d0b-124">You can also enter an amount type.</span></span>  
15. <span data-ttu-id="56d0b-125">En el campo Divisa, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="56d0b-125">In the Currency field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="56d0b-126">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="56d0b-126">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="56d0b-127">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="56d0b-127">Click Save.</span></span>
18. <span data-ttu-id="56d0b-128">Haga clic en Actualizar saldos presupuestarios.</span><span class="sxs-lookup"><span data-stu-id="56d0b-128">Click Update budget balances.</span></span>
19. <span data-ttu-id="56d0b-129">Haga clic en Actualizar.</span><span class="sxs-lookup"><span data-stu-id="56d0b-129">Click Update.</span></span>
    * <span data-ttu-id="56d0b-130">Para ver los resultados de la actualización, haga clic en Detalles de mensaje en la barra azul.</span><span class="sxs-lookup"><span data-stu-id="56d0b-130">To see the results of the update, click Message details on the blue bar.</span></span>  

