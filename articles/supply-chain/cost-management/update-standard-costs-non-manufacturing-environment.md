---
title: Actualizar costes estándar en un entorno de no fabricación
description: Este artículo proporciona orientación para actualizar los costes estándar en un entorno de no fabricación.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 09dca3012952b739a75a6930908752fba73a4550
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436801"
---
# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a><span data-ttu-id="5fa98-103">Actualizar costes estándar en un entorno de no fabricación</span><span class="sxs-lookup"><span data-stu-id="5fa98-103">Update standard costs in a non-manufacturing environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5fa98-104">Este artículo proporciona orientación para actualizar los costes estándar en un entorno de no fabricación.</span><span class="sxs-lookup"><span data-stu-id="5fa98-104">This article provides guidance for updating standard costs in a non-manufacturing environment.</span></span>

<span data-ttu-id="5fa98-105">En las directrices siguientes se supone que se usa el enfoque de dos versiones para actualizar el coste estándar.</span><span class="sxs-lookup"><span data-stu-id="5fa98-105">The following guidelines assume that you use a two-version approach to update standard cost.</span></span> <span data-ttu-id="5fa98-106">En este enfoque, una versión de gestión de costes contiene los costes estándar que se definieron originalmente para el período congelado y la segunda versión de gestión de costes contiene las actualizaciones incrementales.</span><span class="sxs-lookup"><span data-stu-id="5fa98-106">In this approach, one costing version contains the standard costs that were originally defined for the frozen period, and the second costing version contains the incremental updates.</span></span> <span data-ttu-id="5fa98-107">Cada actualización se especifica como un registro de coste incluido en la segunda versión de gestión de costes y, finalmente, se activa.</span><span class="sxs-lookup"><span data-stu-id="5fa98-107">Each update is entered as a cost record that is enclosed in the second costing version, and eventually it's enabled.</span></span> <span data-ttu-id="5fa98-108">El enfoque alternativo de una versión utiliza el conjunto de costes estándar que se definió originalmente.</span><span class="sxs-lookup"><span data-stu-id="5fa98-108">An alternative, one-version approach uses the set of standard costs that was originally defined.</span></span> <span data-ttu-id="5fa98-109">El enfoque de dos versiones requiere que defina una segunda versión de gestión de costes.</span><span class="sxs-lookup"><span data-stu-id="5fa98-109">The two-version approach requires that you define a second costing version.</span></span> <span data-ttu-id="5fa98-110">Esta son las instrucciones para definir esta versión de gestión de costes:</span><span class="sxs-lookup"><span data-stu-id="5fa98-110">Here are the guidelines for defining this costing version:</span></span>

-   <span data-ttu-id="5fa98-111">Asigne un tipo de gestión de costes de **Costes estándar**.</span><span class="sxs-lookup"><span data-stu-id="5fa98-111">Assign a costing type of **Standard costs**.</span></span>
-   <span data-ttu-id="5fa98-112">Asigne un identificador significativo que indique el contenido de la versión de gestión de costes como, por ejemplo, **2016-ACTUALIZACIONES**.</span><span class="sxs-lookup"><span data-stu-id="5fa98-112">Assign a meaningful identifier that indicates the contents of the costing version, such as **2016-UPDATES**.</span></span>
-   <span data-ttu-id="5fa98-113">Asegúrese de que el contenido incluya registros de costes.</span><span class="sxs-lookup"><span data-stu-id="5fa98-113">Make sure that the content includes cost records.</span></span>
-   <span data-ttu-id="5fa98-114">Permita la entrada de registros de costes para todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="5fa98-114">Allow cost records to be entered for all sites.</span></span> <span data-ttu-id="5fa98-115">Si especifica un sitio, los registros de costes se pueden especificar solo para ese sitio.</span><span class="sxs-lookup"><span data-stu-id="5fa98-115">If you specify a site, cost records can be entered only for that site.</span></span>
-   <span data-ttu-id="5fa98-116">Indique un principio de reserva igual a **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="5fa98-116">Indicate a fallback principle of **None**.</span></span> <span data-ttu-id="5fa98-117">El principio de reserva solo se aplica a los cálculos de coste para artículos fabricados.</span><span class="sxs-lookup"><span data-stu-id="5fa98-117">The fallback principle applies only to cost calculations for manufactured items.</span></span>

<span data-ttu-id="5fa98-118">Para corregir, ajustar o actualizar costes estándar para nuevos artículos, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5fa98-118">To correct, adjust, or update standard costs for new items, follow these steps.</span></span>

1.  <span data-ttu-id="5fa98-119">Utilice la página **Configuración de la versión de** **gestión de costes** para permitir la entrada de datos de coste en la segunda versión de gestión de costes.</span><span class="sxs-lookup"><span data-stu-id="5fa98-119">Use the **Costing version** **setup** page to enable cost data to be entered into the second costing version.</span></span> <span data-ttu-id="5fa98-120">También puede evitar la activación de costes pendientes, de modo que la activación se permita después de que los costes pendientes se hayan definido completa y detalladamente.</span><span class="sxs-lookup"><span data-stu-id="5fa98-120">Optionally, prevent the activation of pending costs, so that activation will be allowed after pending costs have been completely and accurately defined.</span></span> <span data-ttu-id="5fa98-121">También puede especificar de forma opcional una fecha en el campo **Fecha inicial**.</span><span class="sxs-lookup"><span data-stu-id="5fa98-121">You can also optionally enter a date in the **From date** field.</span></span> <span data-ttu-id="5fa98-122">Como regla general, use la fecha que represente en la que desea habilitar las actualizaciones incrementales.</span><span class="sxs-lookup"><span data-stu-id="5fa98-122">As a general guideline, use the date when you intend to enable the incremental updates.</span></span> <span data-ttu-id="5fa98-123">Como método alternativo, deje el campo **Fecha inicial** en blanco para la versión de gestión de costes y, a continuación, indique una fecha en el campo **Fecha inicial** para cada registro de coste.</span><span class="sxs-lookup"><span data-stu-id="5fa98-123">Alternatively, leave the **From date** field blank for the costing version, and then enter a date in the **From date** field for each cost record.</span></span>
2.  <span data-ttu-id="5fa98-124">Utilice la página **Precio de artículo** para especificar las actualizaciones como registros de coste del artículo incluidos en la segunda versión de gestión de costes.</span><span class="sxs-lookup"><span data-stu-id="5fa98-124">Use the **Item price** page to enter updates as item cost records that are enclosed in the second costing version.</span></span>
3.  <span data-ttu-id="5fa98-125">Utilice el informe **Precios del artículo** para comprobar si los registros de costes de artículos incluidos en la segunda versión de gestión de costes están completos y son precisos.</span><span class="sxs-lookup"><span data-stu-id="5fa98-125">Use the **Item prices** report to verify the completeness and accuracy of the item cost records that are enclosed in the second costing version.</span></span>
4.  <span data-ttu-id="5fa98-126">Utilice la página **Mantenimiento de la versión de gestión de costes** para modificar el indicador de bloqueo y permitir la activación de los registros de costes pendientes incluidos en la segunda versión de gestión de costes.</span><span class="sxs-lookup"><span data-stu-id="5fa98-126">Use the **Costing version maintenance** page to change the blocking flag to allow activation of the pending cost records that are enclosed in the second costing version.</span></span>
5.  <span data-ttu-id="5fa98-127">Use la página **Activar precios** (que se abre desde la página **Mantenimiento de la versión de gestión de costes**) para activar todos los registros de costes de artículos pendientes que se incluyen en la segunda versión de gestión de costes.</span><span class="sxs-lookup"><span data-stu-id="5fa98-127">Use the **Activate prices** page (which you open from the **Costing version maintenance** page) to activate all pending item cost records that are enclosed in the second costing version.</span></span> <span data-ttu-id="5fa98-128">También puede activar los registros de costes pendientes para los artículos individuales haciendo clic en la página **Activar precios pendientes** de la página **Precio de artículo**.</span><span class="sxs-lookup"><span data-stu-id="5fa98-128">You can also activate the pending cost records for individual items by clicking the **Activate pending price** button on the **Item price** page.</span></span>
6.  <span data-ttu-id="5fa98-129">Para impedir la actualización posterior de los datos, use la página **Configuración de la versión de gestión de costes** para modificar los indicadores de bloqueo incluidos en la segunda versión de gestión de costes.</span><span class="sxs-lookup"><span data-stu-id="5fa98-129">To prevent additional data maintenance, use the **Costing version setup** page to change the blocking flags that are enclosed in the second costing version.</span></span> <span data-ttu-id="5fa98-130">Las directivas de bloqueo impedirán la entrada de nuevos costes pendientes y la activación de costes pendientes.</span><span class="sxs-lookup"><span data-stu-id="5fa98-130">The blocking policies will prevent the entry of new pending costs and the activation of pending costs.</span></span>




