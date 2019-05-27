---
title: Crear reglas de configuración
description: Este procedimiento crea reglas de configuración que se pueden usar para que la configuración basada en dimensiones aplique o impida combinaciones de líneas de lista de materiales.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMTable, BOMConfigRule, ConfigItemIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a315ddecd2e10f508b86ac8ea18a36df71616963
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568475"
---
# <a name="create-configuration-rules"></a><span data-ttu-id="1f1f2-103">Crear reglas de configuración</span><span class="sxs-lookup"><span data-stu-id="1f1f2-103">Create configuration rules</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1f1f2-104">Este procedimiento crea reglas de configuración que se pueden usar para que la configuración basada en dimensiones aplique o impida combinaciones de líneas de lista de materiales.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-104">This procedure creates configuration rules that can be used for dimension-based configuration to enforce or prevent certain combinations of BOM lines.</span></span> <span data-ttu-id="1f1f2-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="1f1f2-106">Este es el séptimo procedimiento de ocho que explica cómo crear combinaciones para la configuración basada en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-106">This is the seventh procedure out of eight that explains how to build combinations for dimension-based configuration.</span></span>

1. <span data-ttu-id="1f1f2-107">Vaya a Gestión de información de productos > Listas de materiales y fórmulas > Listas de materiales.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-107">Go to Product information management > Bills of materials and formulas > Bills of materials.</span></span>
2. <span data-ttu-id="1f1f2-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1f1f2-109">Localice y seleccione la lista de materiales para la configuración basada en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-109">Find and select the BOM for the dimension-based configuration.</span></span>  
3. <span data-ttu-id="1f1f2-110">En el panel de acciones, haga clic en Opciones.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-110">On the Action Pane, click Options.</span></span>
4. <span data-ttu-id="1f1f2-111">Haga clic en Cambiar vista.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-111">Click Change view.</span></span>
5. <span data-ttu-id="1f1f2-112">Haga clic en Visualización de encabezado.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-112">Click Header view.</span></span>
    * <span data-ttu-id="1f1f2-113">Abra la vista de encabezado para acceder a la ficha desplegable Ruta de configuración.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-113">Open the header view to access the Configuration route FastTab.</span></span>  
6. <span data-ttu-id="1f1f2-114">Expanda o contraiga la sección Ruta de configuración.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-114">Expand or collapse the Configuration route section.</span></span>
    * <span data-ttu-id="1f1f2-115">La ficha desplegable Ruta de configuración debe estar en modo expandido.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-115">The Configuration route FastTab must be in the expanded mode.</span></span>  
7. <span data-ttu-id="1f1f2-116">Haga clic en Reglas de configuración.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-116">Click Configuration rules.</span></span>
8. <span data-ttu-id="1f1f2-117">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-117">Click New.</span></span>
9. <span data-ttu-id="1f1f2-118">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-118">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="1f1f2-119">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1f1f2-120">Se muestran los elementos en el grupo de configuración actual.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-120">The items in the current configuration group are displayed.</span></span> <span data-ttu-id="1f1f2-121">Seleccione el que representa la condición en la regla.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-121">Select the one that represents the condition in the rule.</span></span>  
11. <span data-ttu-id="1f1f2-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="1f1f2-123">En el campo Método, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-123">In the Method field, select an option.</span></span>
    * <span data-ttu-id="1f1f2-124">Es posible hacer que se seleccione un elemento, o se anule su selección, de otro grupo de configuración.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-124">It is possible to enforce either a selection or a deselection of an item from another configuration group.</span></span>  
13. <span data-ttu-id="1f1f2-125">En el campo Grupo derivado, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-125">In the Derived group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="1f1f2-126">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-126">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="1f1f2-127">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1f1f2-128">Seleccione el grupo de configuración que le interese.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-128">Select the desired configuration group.</span></span>  
16. <span data-ttu-id="1f1f2-129">En el campo Código de artículo derivado, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-129">In the Derived item number field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="1f1f2-130">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-130">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1f1f2-131">Seleccione el número de elemento que se seleccionará o dejará de seleccionarse, según el método elegido.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-131">Select the item number that will be either selected or deselected depending on the chosen method.</span></span>  
18. <span data-ttu-id="1f1f2-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1f1f2-132">Close the page.</span></span>

