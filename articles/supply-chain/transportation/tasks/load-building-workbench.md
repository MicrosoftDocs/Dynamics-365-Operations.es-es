---
title: Área de trabajo de planificación de la carga
description: Este tema describe cómo trabajar con el banco de trabajo de creación de carga.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSLoadBuildWorkbench,TMSLoadBuildTemplateCreate,TMSLoadBuildStrategy,TMSLoadBuildTemplateApply
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d1ed91adba5c7accf9a18d7a754d33b2b35b848f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974242"
---
# <a name="load-building-workbench"></a><span data-ttu-id="7e1f3-103">Área de trabajo de planificación de la carga</span><span class="sxs-lookup"><span data-stu-id="7e1f3-103">Load building workbench</span></span>

<span data-ttu-id="7e1f3-104">El banco de trabajo de construcción de carga le permite aplicar estrategias de construcción de carga cuando crea cargas.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-104">The load building workbench lets you apply load building strategies when you create loads.</span></span>

## <a name="create-a-load-building-strategy"></a><span data-ttu-id="7e1f3-105">Crear una estrategia de creación de carga</span><span class="sxs-lookup"><span data-stu-id="7e1f3-105">Create a load building strategy</span></span>

<span data-ttu-id="7e1f3-106">Utiliza estrategias de construcción de carga para generar cargas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-106">You use load building strategies to automatically build loads.</span></span> <span data-ttu-id="7e1f3-107">Esta capacidad puede resultar beneficiosa en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="7e1f3-107">This capability can be beneficial in the following situations:</span></span>

- <span data-ttu-id="7e1f3-108">Si envía regularmente un conjunto específico de productos, las estrategias de carga le ayudarán a ahorrar tiempo, ya que no tiene que generar la misma carga cada vez.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-108">If you regularly ship a specific set of products, load strategies help save time, because you don't have to build the same load every time.</span></span>
- <span data-ttu-id="7e1f3-109">Si desea evitar cargas medio llenas para maximizar la eficiencia, las estrategias de carga pueden ayudar a llenar cada carga tanto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-109">If you want to avoid half-full loads to maximize efficiency, load strategies can help fill each load as much as possible.</span></span>

<span data-ttu-id="7e1f3-110">Una clase de estrategia de construcción de carga que se denomina `TMSLoadBuildingVolumeStrategy` proporciona una estrategia de construcción de carga que se denomina *Estrategia de construcción de carga basada en volumen*.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-110">A load building strategy class that is named `TMSLoadBuildingVolumeStrategy` provides a load building strategy that is named *Volume-based load building strategy*.</span></span> <span data-ttu-id="7e1f3-111">Esta estrategia le permite usar los valores máximos que se especifican para la altura y el peso de la plantilla de carga o bien, puede reemplazar los ajustes especificando valores nuevos.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-111">This strategy lets you use the maximum values that are specified for height and weight in the load template, or you can override the settings by entering new values.</span></span> <span data-ttu-id="7e1f3-112">Esta estrategia es la única estrategia que se incluye de fábrica.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-112">This strategy is the only strategy that is included out of the box.</span></span> <span data-ttu-id="7e1f3-113">(Sin embargo, es posible que tenga algunas estrategias personalizadas).</span><span class="sxs-lookup"><span data-stu-id="7e1f3-113">(However, you might have some custom strategies.)</span></span>

<span data-ttu-id="7e1f3-114">Para usar la estrategia incluida *Estrategia de construcción de carga basada en volumen*, selecciónela en el campo **Estrategia de construcción de carga** en la página **Banco de trabajo de construcción de carga** (**Gestión de transporte &gt; Planificación &gt; Banco de trabajo de construcción de carga**).</span><span class="sxs-lookup"><span data-stu-id="7e1f3-114">To use the out-of-box *Volume-based load building strategy* strategy, select it in the **Load building strategy** field on the **Load building workbench** page (**Transportation management &gt; Planning &gt; Load building workbench**).</span></span>

<span data-ttu-id="7e1f3-115">Para crear una estrategia de creación de carga, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-115">To create a load building strategy, follow these steps.</span></span>

1. <span data-ttu-id="7e1f3-116">Ir **Gestión de transporte &gt; Preparar &gt; Creación de carga &gt; Estrategias de construcción de carga**.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-116">Go to **Transportation management &gt; Setup &gt; Load building &gt; Load building strategies**.</span></span>
1. <span data-ttu-id="7e1f3-117">En el panel de acciones, seleccione **Generar lista de clases** para asegurarse de tener las últimas versiones de todas las clases disponibles.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-117">On the Action Pane, select **Generate class list** to make sure that you have the latest versions of all available classes.</span></span>
1. <span data-ttu-id="7e1f3-118">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-118">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="7e1f3-119">Ingrese un nombre único para la estrategia, seleccione la clase de estrategia de construcción de carga para ella e ingrese una descripción.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-119">Enter a unique name for the strategy, select the load building strategy class for it, and enter a description.</span></span>
1. <span data-ttu-id="7e1f3-120">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-120">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="7e1f3-121">En el panel Acciones, seleccione **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-121">On the Action Pane, select **Parameters**.</span></span>
1. <span data-ttu-id="7e1f3-122">Sobre la página **Parámetros de estrategia de construcción de carga**, seleccione **Capacidad de volumen** en la lista y luego, en el campo **Valor**, ingrese el porcentaje de la capacidad de volumen total de la carga que se debe aplicar para la nueva estrategia de construcción de carga.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-122">On the **Load building strategy parameters** page, select **Volume capacity** in the list, and then, in the **Value** field, enter the percentage of the load's total volume capacity that should be applied for the new load building strategy.</span></span>
1. <span data-ttu-id="7e1f3-123">Seleccione **Capacidad de volumen** en la lista y luego, en el campo **Valor**, ingrese el porcentaje de la capacidad de peso total de la carga que se debe aplicar para la nueva estrategia de construcción de carga.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-123">Select **Weight capacity** in the list, and then, in the **Value** field, enter the percentage of the load's total weight capacity that should be applied for the new load building strategy.</span></span>
1. <span data-ttu-id="7e1f3-124">Cierre la página **Parámetros de estrategia de construcción de carga**.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-124">Close the **Load building strategy parameters** page.</span></span>
1. <span data-ttu-id="7e1f3-125">Cierre la página **Estrategias de construcción de carga**.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-125">Close the **Load building strategies** page.</span></span>

<span data-ttu-id="7e1f3-126">Ahora puede asignar la estrategia de creación de carga a una plantilla de creación de carga.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-126">You can now assign the load building strategy to a load building template.</span></span> <span data-ttu-id="7e1f3-127">Alternativamente, puede usarlo directamente en el banco de trabajo de planificación de carga.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-127">Alternatively, you can use it directly in the load planning workbench.</span></span>

## <a name="use-a-load-building-strategy-in-the-load-building-workbench"></a><span data-ttu-id="7e1f3-128">Utilice una estrategia de creación de carga en el banco de trabajo de creación de carga</span><span class="sxs-lookup"><span data-stu-id="7e1f3-128">Use a load building strategy in the load building workbench</span></span>

1. <span data-ttu-id="7e1f3-129">Vaya a **Administración de transporte &gt; Planificación &gt; Área de trabajo de planificación de la carga**.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-129">Go to **Transportation management &gt; Planning &gt; Load building workbench**.</span></span>
1. <span data-ttu-id="7e1f3-130">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="7e1f3-130">Follow one of these steps:</span></span>

    - <span data-ttu-id="7e1f3-131">Seleccione una estrategia en el campo **Estrategia de construcción de carga**.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-131">Select a strategy in the **Load building strategy** field.</span></span>
    - <span data-ttu-id="7e1f3-132">Si ha definido una plantilla de creación de carga y le ha asignado la estrategia de creación de carga, en el Panel de acciones, en la pesaña **Administrar plantillas**, seleccione **Aplicar plantilla**.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-132">If you've defined a load building template and assigned the load building strategy to it, on the Action Pane, on the **Manage templates** tab, select **Apply template**.</span></span> <span data-ttu-id="7e1f3-133">Entonces, en el cuadro de diálogo desplegable **Aplicar plantilla de construcción de carga**, seleccione una plantilla en el campo **Cargar el nombre de la plantilla de construcción**.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-133">Then, in the **Apply load building template** drop-down dialog box, select a template in the **Load building template name** field.</span></span>

1. <span data-ttu-id="7e1f3-134">En la ficha desplegable **Secuencia de carga de plantillas**, seleccione una o más [plantillas de carga](load-template.md).</span><span class="sxs-lookup"><span data-stu-id="7e1f3-134">On the **Load templates sequence** FastTab, select one or more [load templates](load-template.md).</span></span> <span data-ttu-id="7e1f3-135">El banco de trabajo intentará encajar la carga en este tipo de contenedores, en la secuencia que se especifica aquí.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-135">The workbench will try to fit the load into these types of containers, in the sequence that is specified here.</span></span> <span data-ttu-id="7e1f3-136">Por lo general, debe colocar los contenedores más pequeños al principio de la lista para asegurarse de que se seleccione primero el contenedor más pequeño posible.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-136">Typically, you should put the smallest containers at the top of the list to ensure that the smallest possible container is selected first.</span></span>
1. <span data-ttu-id="7e1f3-137">En el panel de acciones, seleccione **Proponer cargas**.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-137">On the Action Pane, select **Propose loads**.</span></span>
1. <span data-ttu-id="7e1f3-138">Revise las cargas propuestas y las líneas de carga propuestas.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-138">Review the proposed loads and proposed load lines.</span></span>
1. <span data-ttu-id="7e1f3-139">En el panel de acciones, seleccione **Crear cargas** para crear cargas que se basan en las líneas del documento de origen en la ficha desplegable **Líneas de carga propuestas**.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-139">On the Action Pane, select **Create loads** to create loads that are based on the source document lines on the **Proposed load lines** FastTab.</span></span>
1. <span data-ttu-id="7e1f3-140">Cierre la página **Workbench de construcción de carga**.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-140">Close the **Load building workbench** page.</span></span>
