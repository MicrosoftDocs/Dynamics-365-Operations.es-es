--- 
title: "Configuración de la reasignación de artículos para la selección corta"
description: "Este procedimiento muestra cómo permitir que los trabajadores del almacén busquen rápidamente ubicaciones alternativas si no hay suficiente inventario en la ubicación a la que les han dirigido."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: e729ebc968b7a102ad4325c638d8604dad6e6ddf
ms.contentlocale: es-es
ms.lasthandoff: 09/11/2018

---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="cf4c5-103">Configuración de la reasignación de artículos para la selección corta</span><span class="sxs-lookup"><span data-stu-id="cf4c5-103">Set up short picking item reallocation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cf4c5-104">Este procedimiento muestra cómo permitir que los trabajadores del almacén busquen rápidamente ubicaciones alternativas si no hay suficiente inventario en la ubicación a la que les han dirigido.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-104">This procedure shows you how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> <span data-ttu-id="cf4c5-105">Se puede usar un proceso automático de reasignación, que usa las directivas de la ubicación para recuperar las mercancías si está disponibles en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-105">It’s possible to use an automatic re-allocation process, which uses location directives to retrieve the goods if they’re available at another location.</span></span> <span data-ttu-id="cf4c5-106">Como alternativa, cuando se usa la reasignación manual, se muestra una lista de las ubicaciones con la cantidad disponible en el dispositivo móvil, para que el trabajador del almacén elija de qué ubicación usar el inventario.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-106">Alternatively, when manual re-allocation is used, a list of the locations with the available quantity is shown on the mobile device, allowing the warehouse worker to choose which location to use inventory from.</span></span> <span data-ttu-id="cf4c5-107">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="cf4c5-108">Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-work-exceptions"></a><span data-ttu-id="cf4c5-109">Configurar excepciones de trabajo</span><span class="sxs-lookup"><span data-stu-id="cf4c5-109">Set up work exceptions</span></span>
1. <span data-ttu-id="cf4c5-110">Ir a Gestión de almacenes > Configurar > Trabajo > Excepciones de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-110">Go to Warehouse management > Setup > Work > Work exceptions.</span></span>
2. <span data-ttu-id="cf4c5-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-111">Click New.</span></span>
    * <span data-ttu-id="cf4c5-112">Es posible definir varias excepciones de trabajo con directivas de la reasignación de artículo diferentes para permitir el trabajador del almacén para elegir uno basado en las necesidades de envío que están procesando.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-112">It’s possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>  
3. <span data-ttu-id="cf4c5-113">En el campo Código de excepción de trabajo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-113">In the Work exception code field, type a value.</span></span>
    * <span data-ttu-id="cf4c5-114">Dé a la excepción de trabajo un título para indicar para qué se utiliza.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-114">Give the work exception a title to indicate what it’s used for.</span></span> <span data-ttu-id="cf4c5-115">Por ejemplo, manual de picking corto.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-115">For example, Short picking manual.</span></span>  
4. <span data-ttu-id="cf4c5-116">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-116">In the Description field, type a value.</span></span>
5. <span data-ttu-id="cf4c5-117">En el campo Tipo de excepción, seleccione "Selección corta".</span><span class="sxs-lookup"><span data-stu-id="cf4c5-117">In the Exception type field, select 'Short pick'.</span></span>
6. <span data-ttu-id="cf4c5-118">Active la casilla Ajustar inventario.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-118">Select the Adjust inventory check box.</span></span>
    * <span data-ttu-id="cf4c5-119">Esta opción significa que el inventario se ajusta automáticamente a 0 en la ubicación de picking corto.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-119">This option means that inventory will automatically be adjusted to 0 at the short picked location.</span></span>  
7. <span data-ttu-id="cf4c5-120">En el campo Código de tipo de ajuste predeterminado, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-120">In the Default adjustment type code field, enter or select a value.</span></span>
    * <span data-ttu-id="cf4c5-121">Por ejemplo, en USMF puede seleccionar "Quitar Res Adj Out".</span><span class="sxs-lookup"><span data-stu-id="cf4c5-121">For example, in USMF you can select 'Remove Res Adj Out'.</span></span>  
8. <span data-ttu-id="cf4c5-122">En el campo Reasignación de artículos, seleccione Manual.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-122">In the Item reallocation field, select 'Manual'.</span></span>
    * <span data-ttu-id="cf4c5-123">Si selecciona Manual o Automático y manual, el trabajador del almacén debe estar habilitado para usar la reasignación manual.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-123">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="cf4c5-124">Configurar un trabajador para usar la reasignación manual de artículos</span><span class="sxs-lookup"><span data-stu-id="cf4c5-124">Set up a worker to use manual item reallocation</span></span>
1. <span data-ttu-id="cf4c5-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-125">Close the page.</span></span>
2. <span data-ttu-id="cf4c5-126">Ir a Gestión de almacenes > Configuración > Empleado.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-126">Go to Warehouse management > Setup > Worker.</span></span>
3. <span data-ttu-id="cf4c5-127">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-127">Click Edit.</span></span>
4. <span data-ttu-id="cf4c5-128">En la lista, seleccione trabajador 24.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-128">In the list, select worker 24.</span></span>
5. <span data-ttu-id="cf4c5-129">Expanda la sección Trabajo.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-129">Expand the Work section.</span></span>
6. <span data-ttu-id="cf4c5-130">Seleccione Sí en el campo Permitir reasignación de artículos manual.</span><span class="sxs-lookup"><span data-stu-id="cf4c5-130">Select Yes in the Allow manual item reallocation field.</span></span>


