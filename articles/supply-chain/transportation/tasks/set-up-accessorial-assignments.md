---
title: Configurar asignaciones de cargos adicionales
description: Este procedimiento muestra cómo configurar una asignación de cargos adicionales.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b69bd2029914efd31569c57272339e27ef1bd6a3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560905"
---
# <a name="set-up-accessorial-assignments"></a><span data-ttu-id="12687-103">Configurar asignaciones de cargos adicionales</span><span class="sxs-lookup"><span data-stu-id="12687-103">Set up accessorial assignments</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="12687-104">Este procedimiento muestra cómo configurar una asignación de cargos adicionales.</span><span class="sxs-lookup"><span data-stu-id="12687-104">This procedure shows how to set up an accessorial assignment.</span></span> <span data-ttu-id="12687-105">Esto lo hace normalmente el coordinador de transporte.</span><span class="sxs-lookup"><span data-stu-id="12687-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="12687-106">Antes de usar este procedimiento, debe ejecutar el procedimiento "Configuración de cargos adicionales del centro y cargos adicionales maestros".</span><span class="sxs-lookup"><span data-stu-id="12687-106">Before you use this guide you need to run the "Set up hub accessorial charges and accessorial masters" guide.</span></span>


## <a name="set-up-accessorial-assignment"></a><span data-ttu-id="12687-107">Configuración de asignaciones de cargos adicionales</span><span class="sxs-lookup"><span data-stu-id="12687-107">Set up Accessorial assignment</span></span>
1. <span data-ttu-id="12687-108">Vaya a Administración de transporte > Configuración > Clasificación > Asignaciones de cargos adicionales.</span><span class="sxs-lookup"><span data-stu-id="12687-108">Go to Transportation management > Setup > Rating > Accessorial assignments.</span></span>
2. <span data-ttu-id="12687-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="12687-109">Click New.</span></span>
3. <span data-ttu-id="12687-110">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="12687-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="12687-111">Expanda la sección Detalles.</span><span class="sxs-lookup"><span data-stu-id="12687-111">Toggle the expansion of the Details section.</span></span>
5. <span data-ttu-id="12687-112">En el campo Centro, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="12687-112">In the Hub field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="12687-113">En la lista, seleccione el centro para el que creó cargos adicionales maestros al ejecutar el procedimiento "Configuración de cargos adicionales y maestros adicionales.</span><span class="sxs-lookup"><span data-stu-id="12687-113">In the list, select the Hub that you created an accessorial master for when you ran the "Set up hub accessorial charges and accessorial masters" guide.</span></span> 
7. <span data-ttu-id="12687-114">En el campo Id. de cargos adicionales del centro, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="12687-114">In the Hub accessorial ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="12687-115">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="12687-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="12687-116">Expanda la sección Criterios.</span><span class="sxs-lookup"><span data-stu-id="12687-116">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="12687-117">En la sección Criterios, puede elegir los criterios exactos para cuando se deba aplicar el cargo, en función de los distintos valores ofrecidos aquí.</span><span class="sxs-lookup"><span data-stu-id="12687-117">In the Criteria section you can choose the exact criteria for when the charge should apply, based on the different values offered here.</span></span>  
10. <span data-ttu-id="12687-118">Establezca la opción Aplicar siempre en Sí.</span><span class="sxs-lookup"><span data-stu-id="12687-118">Set the Always apply option to Yes.</span></span>
11. <span data-ttu-id="12687-119">En el campo Nivel de asignación de cargos adicionales, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="12687-119">In the Accessorial assignment level field, select an option.</span></span>
12. <span data-ttu-id="12687-120">Expanda la sección Cálculo.</span><span class="sxs-lookup"><span data-stu-id="12687-120">Toggle the expansion of the Calculation section.</span></span>
13. <span data-ttu-id="12687-121">En el campo Tipo de tasas de cargos adicionales, seleccione Fijo.</span><span class="sxs-lookup"><span data-stu-id="12687-121">In the Accessorial fee type field, select 'Flat'.</span></span>
    * <span data-ttu-id="12687-122">El tipo de tasa de cargos adicionales determina cómo se calcula el cargo real.</span><span class="sxs-lookup"><span data-stu-id="12687-122">The Accessorial fee type determines how to calculate the actual charge.</span></span> <span data-ttu-id="12687-123">En este ejemplo se trata de un cargo fijo.</span><span class="sxs-lookup"><span data-stu-id="12687-123">In this example it's a flat charge.</span></span>  
14. <span data-ttu-id="12687-124">En el campo Tasa de cargos adicionales, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="12687-124">In the Accessorial fee field, enter a number.</span></span>
15. <span data-ttu-id="12687-125">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="12687-125">Click Save.</span></span>

