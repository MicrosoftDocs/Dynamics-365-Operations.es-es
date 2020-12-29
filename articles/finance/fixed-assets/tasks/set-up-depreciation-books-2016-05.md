---
title: Configurar libros de amortización
description: Este procedimiento explica el proceso de creación de un nuevo libro de amortización y lo asocia con un grupo de activos fijos.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 03f915fa91e0eeff2f26ab9a60bbd5118317e853
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447677"
---
# <a name="set-up-depreciation-books"></a><span data-ttu-id="a8efc-103">Configurar libros de amortización</span><span class="sxs-lookup"><span data-stu-id="a8efc-103">Set up depreciation books</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a8efc-104">Este procedimiento explica el proceso de creación de un nuevo libro de amortización y lo asocia con un grupo de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="a8efc-104">This procedure walks through the process of creating a new depreciation book and associate it with a fixed asset group.</span></span> 

## <a name="create-a-depreciation-book"></a><span data-ttu-id="a8efc-105">Crear un libro de amortización</span><span class="sxs-lookup"><span data-stu-id="a8efc-105">Create a depreciation book</span></span>
1. <span data-ttu-id="a8efc-106">Vaya a Activos fijos > Configuración > Libros amortización.</span><span class="sxs-lookup"><span data-stu-id="a8efc-106">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="a8efc-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a8efc-107">Click New.</span></span>
3. <span data-ttu-id="a8efc-108">En el campo Libro amortización, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a8efc-108">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="a8efc-109">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a8efc-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a8efc-110">Active o desactive la casilla Calcular depreciación.</span><span class="sxs-lookup"><span data-stu-id="a8efc-110">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="a8efc-111">En el campo Método de depreciación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a8efc-111">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="a8efc-112">En la lista, busque y seleccione el método de depreciación deseado.</span><span class="sxs-lookup"><span data-stu-id="a8efc-112">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="a8efc-113">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a8efc-113">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="a8efc-114">En el campo Método de depreciación alternativo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a8efc-114">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="a8efc-115">En la lista, seleccione el método de depreciación deseado.</span><span class="sxs-lookup"><span data-stu-id="a8efc-115">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="a8efc-116">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a8efc-116">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="a8efc-117">El método de depreciación extraordinaria que se usa para la depreciación adicional de un activo en circunstancias inusuales.</span><span class="sxs-lookup"><span data-stu-id="a8efc-117">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="a8efc-118">Por ejemplo, puede usar esta opción para registrar la depreciación que se produzca a causa de un desastre natural.</span><span class="sxs-lookup"><span data-stu-id="a8efc-118">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="a8efc-119">Active o desactive la casilla Crear ajustes de depreciación con ajustes de base.</span><span class="sxs-lookup"><span data-stu-id="a8efc-119">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="a8efc-120">En el campo Calendario, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a8efc-120">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="a8efc-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a8efc-121">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="a8efc-122">Asociar el libro de amortización con un grupo de activos fijos</span><span class="sxs-lookup"><span data-stu-id="a8efc-122">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="a8efc-123">Haga clic en Grupos de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="a8efc-123">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="a8efc-124">En el campo Grupo de activos fijos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a8efc-124">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="a8efc-125">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a8efc-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="a8efc-126">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a8efc-126">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="a8efc-127">En el campo Convención de amortizaciones, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="a8efc-127">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="a8efc-128">En el campo Tiempo de vida, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="a8efc-128">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="a8efc-129">Tenga en cuenta que el valor del campo Períodos de depreciación se calcula después de definir el tiempo de vida.</span><span class="sxs-lookup"><span data-stu-id="a8efc-129">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  

