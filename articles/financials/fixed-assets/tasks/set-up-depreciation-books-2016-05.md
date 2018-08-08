--- 
title: "Configurar libros de amortización"
description: "Esta guía de la tarea creará un nuevo libro de amortización y lo asociará a un grupo de activos fijos."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: c4660cd31ef0cd80a2f73eeeb01523e34510ca38
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="set-up-depreciation-books"></a><span data-ttu-id="9da7d-103">Configurar libros de amortización</span><span class="sxs-lookup"><span data-stu-id="9da7d-103">Set up depreciation books</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9da7d-104">Esta guía de la tarea creará un nuevo libro de amortización y lo asociará a un grupo de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="9da7d-104">This task guide will create a new depreciation book and associate it with a fixed asset group.</span></span>  <span data-ttu-id="9da7d-105">Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="9da7d-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-depreciation-book"></a><span data-ttu-id="9da7d-106">Crear un libro de amortización</span><span class="sxs-lookup"><span data-stu-id="9da7d-106">Create a depreciation book</span></span>
1. <span data-ttu-id="9da7d-107">Vaya a Activos fijos > Configuración > Libros amortización.</span><span class="sxs-lookup"><span data-stu-id="9da7d-107">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="9da7d-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9da7d-108">Click New.</span></span>
3. <span data-ttu-id="9da7d-109">En el campo Libro amortización, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9da7d-109">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="9da7d-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9da7d-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9da7d-111">Active o desactive la casilla Calcular depreciación.</span><span class="sxs-lookup"><span data-stu-id="9da7d-111">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="9da7d-112">En el campo Método de depreciación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9da7d-112">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="9da7d-113">En la lista, busque y seleccione el método de depreciación deseado.</span><span class="sxs-lookup"><span data-stu-id="9da7d-113">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="9da7d-114">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9da7d-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="9da7d-115">En el campo Método de depreciación alternativo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9da7d-115">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="9da7d-116">En la lista, seleccione el método de depreciación deseado.</span><span class="sxs-lookup"><span data-stu-id="9da7d-116">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="9da7d-117">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9da7d-117">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="9da7d-118">El método de depreciación extraordinaria que se usa para la depreciación adicional de un activo en circunstancias inusuales.</span><span class="sxs-lookup"><span data-stu-id="9da7d-118">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="9da7d-119">Por ejemplo, puede usar esta opción para registrar la depreciación que se produzca a causa de un desastre natural.</span><span class="sxs-lookup"><span data-stu-id="9da7d-119">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="9da7d-120">Active o desactive la casilla Crear ajustes de depreciación con ajustes de base.</span><span class="sxs-lookup"><span data-stu-id="9da7d-120">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="9da7d-121">En el campo Calendario, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9da7d-121">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="9da7d-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9da7d-122">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="9da7d-123">Asociar el libro de amortización con un grupo de activos fijos</span><span class="sxs-lookup"><span data-stu-id="9da7d-123">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="9da7d-124">Haga clic en Grupos de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="9da7d-124">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="9da7d-125">En el campo Grupo de activos fijos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9da7d-125">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="9da7d-126">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="9da7d-126">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="9da7d-127">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9da7d-127">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="9da7d-128">En el campo Convención de amortizaciones, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="9da7d-128">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="9da7d-129">En el campo Tiempo de vida, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="9da7d-129">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="9da7d-130">Tenga en cuenta que el valor del campo Períodos de depreciación se calcula después de definir el tiempo de vida.</span><span class="sxs-lookup"><span data-stu-id="9da7d-130">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  


