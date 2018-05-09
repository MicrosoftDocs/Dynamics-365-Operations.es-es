--- 
title: "Creación de entradas de un presupuesto original y de un presupuesto preliminar inverso para el sector público"
description: "Cuando crea una entrada de presupuesto original y usa el modelo presupuestario y los valores de dimensión que contienen importes presupuestarios preliminares, se pueden invertir los importes presupuestarios preliminares."
author: twheeloc
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: dc315a53e420049689828cce375630a1adf5d843
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="create-an-original-budget-and-reverse-preliminary-budget-entries-in-the-public-sector"></a><span data-ttu-id="e69bb-103">Creación de entradas de un presupuesto original y de un presupuesto preliminar inverso para el sector público</span><span class="sxs-lookup"><span data-stu-id="e69bb-103">Create an original budget and reverse preliminary budget entries in the public sector</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e69bb-104">Cuando crea una entrada de presupuesto original y usa el modelo presupuestario y los valores de dimensión que contienen importes presupuestarios preliminares, se pueden invertir los importes presupuestarios preliminares.</span><span class="sxs-lookup"><span data-stu-id="e69bb-104">When you create an original budget entry and use the budget model and dimension values that contain preliminary budget amounts, the preliminary budget amounts can be reversed.</span></span> <span data-ttu-id="e69bb-105">Este procedimiento se ha creado con los datos de empresa de demostración PSUS en la partición del sector público.</span><span class="sxs-lookup"><span data-stu-id="e69bb-105">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="e69bb-106">Vaya a Gestión presupuestaria > Entradas de registro presupuestario.</span><span class="sxs-lookup"><span data-stu-id="e69bb-106">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="e69bb-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="e69bb-107">Click New.</span></span>
3. <span data-ttu-id="e69bb-108">En el campo Modelo presupuestario, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e69bb-108">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e69bb-109">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e69bb-109">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="e69bb-110">En el campo Código presupuestario, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e69bb-110">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="e69bb-111">En la lista, haga clic en Presupuesto original.</span><span class="sxs-lookup"><span data-stu-id="e69bb-111">In the list, click Original budget.</span></span>
7. <span data-ttu-id="e69bb-112">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e69bb-112">Click Save.</span></span>
8. <span data-ttu-id="e69bb-113">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="e69bb-113">Click Add line.</span></span>
9. <span data-ttu-id="e69bb-114">Opcional: Si desea cambiar la fecha de la que se encuentra en el encabezado, especifique una fecha nueva.</span><span class="sxs-lookup"><span data-stu-id="e69bb-114">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="e69bb-115">Esta fecha determina el período fiscal en el que registrará el presupuesto.</span><span class="sxs-lookup"><span data-stu-id="e69bb-115">This date determines the fiscal period that the budget will be recorded to.</span></span>
10. <span data-ttu-id="e69bb-116">En el campo Estructura contable, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e69bb-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="e69bb-117">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e69bb-117">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="e69bb-118">En el campo Valores de dimensión, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="e69bb-118">In the Dimension values field, specify the desired values.</span></span>
13. <span data-ttu-id="e69bb-119">En el campo Importe, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="e69bb-119">In the Amount field, enter a number.</span></span>
14. <span data-ttu-id="e69bb-120">En el campo Divisa, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e69bb-120">In the Currency field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="e69bb-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e69bb-121">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="e69bb-122">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e69bb-122">Click Save.</span></span>
17. <span data-ttu-id="e69bb-123">Haga clic en Actualizar saldos presupuestarios.</span><span class="sxs-lookup"><span data-stu-id="e69bb-123">Click Update budget balances.</span></span>
    * <span data-ttu-id="e69bb-124">Opcional: Puede seleccionar la opción Invertir presupuesto preliminar.</span><span class="sxs-lookup"><span data-stu-id="e69bb-124">Optional: You can select the Reverse preliminary budget option.</span></span> <span data-ttu-id="e69bb-125">Tenga en cuenta que puede invertir todas las entradas de presupuesto preliminares o solo las entradas de presupuesto preliminares que tengan el código de presupuesto que especifique.</span><span class="sxs-lookup"><span data-stu-id="e69bb-125">Note that you can reverse all preliminary budget entries, or only the preliminary budget entries that have the budget code that you specify.</span></span>  
    * <span data-ttu-id="e69bb-126">Para realizar selecciones opcionales, haga clic en el icono Desbloquear de la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="e69bb-126">To make optional selections, click the Unlock icon at the top of the page.</span></span>  
18. <span data-ttu-id="e69bb-127">Haga clic en Actualizar.</span><span class="sxs-lookup"><span data-stu-id="e69bb-127">Click Update.</span></span>


