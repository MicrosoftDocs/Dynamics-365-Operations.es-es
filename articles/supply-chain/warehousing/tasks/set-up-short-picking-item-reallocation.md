---
title: Configuración de la reasignación de artículos para la selección corta
description: Este procedimiento muestra cómo permitir que los trabajadores del almacén busquen rápidamente ubicaciones alternativas si no hay suficiente inventario en la ubicación a la que les han dirigido.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eae86b307ac8d8539c3897293c2fc21ea57d2d60
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148248"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="cfee7-103">Configuración de la reasignación de artículos para la selección corta</span><span class="sxs-lookup"><span data-stu-id="cfee7-103">Set up short picking item reallocation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cfee7-104">Este procedimiento muestra cómo permitir que los trabajadores del almacén busquen rápidamente ubicaciones alternativas si no hay suficiente inventario en la ubicación a la que les han dirigido.</span><span class="sxs-lookup"><span data-stu-id="cfee7-104">This procedure shows you how to enable warehouse workers to quickly find alternative locations if there isn't sufficient inventory at the location they've been directed to.</span></span> <span data-ttu-id="cfee7-105">Se puede usar un proceso automático de reasignación, que usa las directivas de la ubicación para recuperar las mercancías si está disponibles en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="cfee7-105">It's possible to use an automatic re-allocation process, which uses location directives to retrieve the goods if they're available at another location.</span></span> <span data-ttu-id="cfee7-106">Como alternativa, cuando se usa la reasignación manual, se muestra una lista de las ubicaciones con la cantidad disponible en el dispositivo móvil, para que el trabajador del almacén elija de qué ubicación usar el inventario.</span><span class="sxs-lookup"><span data-stu-id="cfee7-106">Alternatively, when manual re-allocation is used, a list of the locations with the available quantity is shown on the mobile device, allowing the warehouse worker to choose which location to use inventory from.</span></span> <span data-ttu-id="cfee7-107">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="cfee7-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="cfee7-108">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="cfee7-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-work-exceptions"></a><span data-ttu-id="cfee7-109">Configurar excepciones de trabajo</span><span class="sxs-lookup"><span data-stu-id="cfee7-109">Set up work exceptions</span></span>
1. <span data-ttu-id="cfee7-110">En el **Panel de navegación**, vaya a **Administración de almacenes > Configuración > Trabajo > Excepciones de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="cfee7-110">In the **Navigation pane**, go to **Warehouse management > Setup > Work > Work exceptions**.</span></span>
2. <span data-ttu-id="cfee7-111">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="cfee7-111">Click **New**.</span></span> <span data-ttu-id="cfee7-112">Es posible definir varias excepciones de trabajo con directivas de la reasignación de artículo diferentes para permitir el trabajador del almacén para elegir uno basado en las necesidades de envío que están procesando.</span><span class="sxs-lookup"><span data-stu-id="cfee7-112">It's possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>  
3. <span data-ttu-id="cfee7-113">En el campo **Código de excepción de trabajo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cfee7-113">In the **Work exception code** field, type a value.</span></span> <span data-ttu-id="cfee7-114">Dé a la excepción de trabajo un título para indicar para qué se utiliza.</span><span class="sxs-lookup"><span data-stu-id="cfee7-114">Give the work exception a title to indicate what it's used for.</span></span> <span data-ttu-id="cfee7-115">Por ejemplo, manual de picking corto.</span><span class="sxs-lookup"><span data-stu-id="cfee7-115">For example, Short picking manual.</span></span>  
4. <span data-ttu-id="cfee7-116">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cfee7-116">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="cfee7-117">En el campo Tipo de **excepción**, seleccione "Selección corta".</span><span class="sxs-lookup"><span data-stu-id="cfee7-117">In the **Exception** type field, select 'Short pick'.</span></span>
6. <span data-ttu-id="cfee7-118">Active la casilla **Ajustar inventario**.</span><span class="sxs-lookup"><span data-stu-id="cfee7-118">Select the **Adjust inventory** check box.</span></span> <span data-ttu-id="cfee7-119">Esta opción significa que el inventario se ajusta automáticamente a 0 en la ubicación de picking corto.</span><span class="sxs-lookup"><span data-stu-id="cfee7-119">This option means that inventory will automatically be adjusted to 0 at the short picked location.</span></span>  
7. <span data-ttu-id="cfee7-120">En el campo **Código de tipo de ajuste predeterminado**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cfee7-120">In the **Default adjustment type code** field, enter or select a value.</span></span> <span data-ttu-id="cfee7-121">Por ejemplo, en USMF puede seleccionar "Quitar Res Adj Out".</span><span class="sxs-lookup"><span data-stu-id="cfee7-121">For example, in USMF you can select 'Remove Res Adj Out'.</span></span>  
8. <span data-ttu-id="cfee7-122">En el campo **Reasignación de artículos**, seleccione "Manual".</span><span class="sxs-lookup"><span data-stu-id="cfee7-122">In the **Item reallocation** field, select 'Manual'.</span></span> <span data-ttu-id="cfee7-123">Si selecciona Manual o Automático y manual, el trabajador del almacén debe estar habilitado para usar la reasignación manual.</span><span class="sxs-lookup"><span data-stu-id="cfee7-123">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="cfee7-124">Configurar un trabajador para usar la reasignación manual de artículos</span><span class="sxs-lookup"><span data-stu-id="cfee7-124">Set up a worker to use manual item reallocation</span></span>
1. <span data-ttu-id="cfee7-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cfee7-125">Close the page.</span></span>
2. <span data-ttu-id="cfee7-126">En el **Panel de navegación**, vaya a **Administración de almacenes > Configuración > Trabajador**.</span><span class="sxs-lookup"><span data-stu-id="cfee7-126">In the **Navigation pane**, go to **Warehouse management > Setup > Worker**.</span></span>
3. <span data-ttu-id="cfee7-127">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cfee7-127">Click **Edit**.</span></span>
4. <span data-ttu-id="cfee7-128">En la lista, seleccione trabajador 24.</span><span class="sxs-lookup"><span data-stu-id="cfee7-128">In the list, select worker 24.</span></span>
5. <span data-ttu-id="cfee7-129">Expanda la ficha desplegable **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="cfee7-129">Expand the **Work** fastTab.</span></span>
6. <span data-ttu-id="cfee7-130">Seleccione "Sí" en el campo **Permitir reasignación de artículos manual**.</span><span class="sxs-lookup"><span data-stu-id="cfee7-130">Select 'Yes' in the **Allow manual item reallocation** field.</span></span>

