---
title: Configuración de libros depreciación (mayo de 2016)
description: Esta guía de la tarea creará un nuevo libro de amortización y lo asociará a un grupo de activos fijos.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1fd53ea1dff9b116d19c525c5d6967ece0993b6f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566924"
---
# <a name="set-up-depreciation-books-may-2016"></a><span data-ttu-id="a7439-103">Configuración de libros depreciación (mayo de 2016)</span><span class="sxs-lookup"><span data-stu-id="a7439-103">Set up depreciation books (May 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a7439-104">Esta guía de la tarea creará un nuevo libro de amortización y lo asociará a un grupo de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="a7439-104">This task guide will create a new depreciation book and associate it with a fixed asset group.</span></span>  <span data-ttu-id="a7439-105">Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="a7439-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-depreciation-book"></a><span data-ttu-id="a7439-106">Crear un libro de amortización</span><span class="sxs-lookup"><span data-stu-id="a7439-106">Create a depreciation book</span></span>
1. <span data-ttu-id="a7439-107">Vaya a Activos fijos > Configuración > Libros amortización.</span><span class="sxs-lookup"><span data-stu-id="a7439-107">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="a7439-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a7439-108">Click New.</span></span>
3. <span data-ttu-id="a7439-109">En el campo Libro amortización, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a7439-109">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="a7439-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a7439-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a7439-111">Active o desactive la casilla Calcular depreciación.</span><span class="sxs-lookup"><span data-stu-id="a7439-111">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="a7439-112">En el campo Método de depreciación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a7439-112">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="a7439-113">En la lista, busque y seleccione el método de depreciación deseado.</span><span class="sxs-lookup"><span data-stu-id="a7439-113">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="a7439-114">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a7439-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="a7439-115">En el campo Método de depreciación alternativo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a7439-115">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="a7439-116">En la lista, seleccione el método de depreciación deseado.</span><span class="sxs-lookup"><span data-stu-id="a7439-116">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="a7439-117">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a7439-117">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="a7439-118">El método de depreciación extraordinaria que se usa para la depreciación adicional de un activo en circunstancias inusuales.</span><span class="sxs-lookup"><span data-stu-id="a7439-118">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="a7439-119">Por ejemplo, puede usar esta opción para registrar la depreciación que se produzca a causa de un desastre natural.</span><span class="sxs-lookup"><span data-stu-id="a7439-119">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="a7439-120">Active o desactive la casilla Crear ajustes de depreciación con ajustes de base.</span><span class="sxs-lookup"><span data-stu-id="a7439-120">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="a7439-121">En el campo Calendario, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a7439-121">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="a7439-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a7439-122">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="a7439-123">Asociar el libro de amortización con un grupo de activos fijos</span><span class="sxs-lookup"><span data-stu-id="a7439-123">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="a7439-124">Haga clic en Grupos de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="a7439-124">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="a7439-125">En el campo Grupo de activos fijos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a7439-125">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="a7439-126">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a7439-126">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="a7439-127">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a7439-127">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="a7439-128">En el campo Convención de amortizaciones, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="a7439-128">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="a7439-129">En el campo Tiempo de vida, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="a7439-129">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="a7439-130">Tenga en cuenta que el valor del campo Períodos de depreciación se calcula después de definir el tiempo de vida.</span><span class="sxs-lookup"><span data-stu-id="a7439-130">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  

