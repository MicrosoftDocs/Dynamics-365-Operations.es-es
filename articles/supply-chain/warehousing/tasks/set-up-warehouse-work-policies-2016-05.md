---
title: Configurar directivas de trabajo de almacén (solicitud, mayo de 2016)
description: Los procesos de almacén no siempre incluyen trabajo de almacén.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy, WMSLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 23ad33a2f070a33e4e658870561406c4604f4dce
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847072"
---
# <a name="set-up-warehouse-work-policies-application-may-2016"></a><span data-ttu-id="9c7b9-103">Configurar directivas de trabajo de almacén (solicitud, mayo de 2016)</span><span class="sxs-lookup"><span data-stu-id="9c7b9-103">Set up warehouse work policies (Application, May 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9c7b9-104">Los procesos de almacén no siempre incluyen trabajo de almacén.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-104">Warehouse processes don’t always include warehouse work.</span></span> <span data-ttu-id="9c7b9-105">Al definir una directiva de trabajo, puede evitar la creación de trabajo para picking de materia prima y ubicación de bienes terminados para un conjunto de productos en ubicaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-105">By defining a work policy, you can prevent the creation of work for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span> <span data-ttu-id="9c7b9-106">La empresa de datos de demostración USMF se usó para crear este registro.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-106">The USMF demo data company was used to create this recording.</span></span> <span data-ttu-id="9c7b9-107">Esta guía de tareas requiere la aplicación Dynamics AX 7.0.1 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-107">This task guide requires Dynamics AX application 7.0.1 or later.</span></span>

1. <span data-ttu-id="9c7b9-108">Vaya a Gestión de almacenes > Configurar > Trabajo > Directivas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-108">Go to Warehouse management > Setup > Work > Work policies.</span></span>
2. <span data-ttu-id="9c7b9-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-109">Click New.</span></span>
3. <span data-ttu-id="9c7b9-110">En el campo Nombre de directiva de trabajo, escriba "Ningún trabajo de ubicación".</span><span class="sxs-lookup"><span data-stu-id="9c7b9-110">In the Work policy name field, type 'No put-away work'.</span></span>
4. <span data-ttu-id="9c7b9-111">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-111">Click Save.</span></span>
5. <span data-ttu-id="9c7b9-112">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-112">Click Add.</span></span>
6. <span data-ttu-id="9c7b9-113">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-113">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="9c7b9-114">En el campo Tipo de pedido de trabajo, seleccione "Ubicación de bienes terminados".</span><span class="sxs-lookup"><span data-stu-id="9c7b9-114">In the Work order type field, select 'Finished goods put away'.</span></span>
8. <span data-ttu-id="9c7b9-115">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-115">Click Add.</span></span>
9. <span data-ttu-id="9c7b9-116">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-116">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="9c7b9-117">En el campo Tipo de pedido de trabajo, seleccione "Ubicación de coproducto y producto derivado".</span><span class="sxs-lookup"><span data-stu-id="9c7b9-117">In the Work order type field, select 'Co-product and by-product put away'.</span></span>
11. <span data-ttu-id="9c7b9-118">Expanda la sección Ubicaciones del inventario.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-118">Expand the Inventory locations section.</span></span>
12. <span data-ttu-id="9c7b9-119">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-119">Click Add.</span></span>
13. <span data-ttu-id="9c7b9-120">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-120">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="9c7b9-121">En la lista Almacén, especifique “51".</span><span class="sxs-lookup"><span data-stu-id="9c7b9-121">In the Warehouse list, enter '51'.</span></span>
15. <span data-ttu-id="9c7b9-122">En el campo Ubicación, especifique o seleccione ·"001".</span><span class="sxs-lookup"><span data-stu-id="9c7b9-122">In the Location field, enter or select '001'.</span></span>
16. <span data-ttu-id="9c7b9-123">Expanda la sección Productos.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-123">Expand the Products section.</span></span>
17. <span data-ttu-id="9c7b9-124">En el campo Selección de productos, seleccione "Seleccionado".</span><span class="sxs-lookup"><span data-stu-id="9c7b9-124">In the Product selection field, select 'Selected'.</span></span>
18. <span data-ttu-id="9c7b9-125">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-125">Click Add.</span></span>
19. <span data-ttu-id="9c7b9-126">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-126">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="9c7b9-127">En el campo Número de artículo, especifique o seleccione "L0101".</span><span class="sxs-lookup"><span data-stu-id="9c7b9-127">In the Item number field, enter or select 'L0101'.</span></span>
21. <span data-ttu-id="9c7b9-128">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9c7b9-128">Click Save.</span></span>

