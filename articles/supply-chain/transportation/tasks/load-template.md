---
title: Cargar plantillas
description: Este tema describe cómo configurar plantillas de carga y cómo asociar una plantilla de carga a una nueva carga.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1ea7f5244b483a1b9d6c55227c676a3878a71d83
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646432"
---
# <a name="load-templates"></a><span data-ttu-id="58d1c-103">Cargar plantillas</span><span class="sxs-lookup"><span data-stu-id="58d1c-103">Load templates</span></span>

<span data-ttu-id="58d1c-104">Cuando crea una nueva carga, puede asignar una plantilla de carga.</span><span class="sxs-lookup"><span data-stu-id="58d1c-104">When you create a new load, you can assign a load template.</span></span> <span data-ttu-id="58d1c-105">La plantilla de carga contiene información sobre el equipo y sobre medidas como la altura, el ancho, la profundidad y el volumen de la carga.</span><span class="sxs-lookup"><span data-stu-id="58d1c-105">The load template contains information about equipment, and about measures such as the height, width, depth, and volume of the load.</span></span>

<span data-ttu-id="58d1c-106">Este tema describe cómo configurar plantillas de carga y cómo asociar una plantilla de carga a una nueva carga.</span><span class="sxs-lookup"><span data-stu-id="58d1c-106">This topic describes how to set up load templates, and how to associate a load template with a new load.</span></span>

## <a name="set-up-a-load-template"></a><span data-ttu-id="58d1c-107">Configurar una plantilla de carga</span><span class="sxs-lookup"><span data-stu-id="58d1c-107">Set up a load template</span></span>

1. <span data-ttu-id="58d1c-108">Ir **Gestión de transporte \> Preparar \> Creación de carga \> Plantilla de carga**.</span><span class="sxs-lookup"><span data-stu-id="58d1c-108">Go to **Transportation management \> Setup \> Load Building \> Load template**.</span></span>
1. <span data-ttu-id="58d1c-109">En el panel de acciones, seleccione **Nuevo** para agregar una nueva plantilla o **Editar** para editar una plantilla existente.</span><span class="sxs-lookup"><span data-stu-id="58d1c-109">On the Action Pane, select **New** to add a new template or **Edit** to edit an existing template.</span></span>
1. <span data-ttu-id="58d1c-110">En la fila de la plantilla nueva o existente, configure los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="58d1c-110">In the row for the new or existing template, set the following fields:</span></span>

    - <span data-ttu-id="58d1c-111">**ID de plantilla de carga** – Introduzca un identificador único para la plantilla de carga.</span><span class="sxs-lookup"><span data-stu-id="58d1c-111">**Load template ID** – Enter a unique identifier (ID) for the load template.</span></span>
    - <span data-ttu-id="58d1c-112">**Equipo** - Seleccione el equipo que se debe utilizar para enviar la carga.</span><span class="sxs-lookup"><span data-stu-id="58d1c-112">**Equipment** – Select the equipment that should be used to ship the load.</span></span>
    - <span data-ttu-id="58d1c-113">**Altura de carga**, **Ancho de carga** y **Profundidad de carga** - Ingrese las dimensiones de la carga.</span><span class="sxs-lookup"><span data-stu-id="58d1c-113">**Load height**, **Load width**, and **Load depth** – Enter the dimensions of the load.</span></span>
    - <span data-ttu-id="58d1c-114">**Max. volumen de carga permitido** y **Max. peso de carga permitido** - Introduzca el volumen y el peso máximos permitidos de la carga.</span><span class="sxs-lookup"><span data-stu-id="58d1c-114">**Max. allowed load volume** and **Max. allowed load weight** – Enter the maximum allowed volume and weight of the load.</span></span>
    - <span data-ttu-id="58d1c-115">**Peso bruto máximo permitido** - Ingrese el peso bruto máximo permitido de la carga.</span><span class="sxs-lookup"><span data-stu-id="58d1c-115">**Maximum allowed gross weight** – Enter the maximum allowed gross weight of the load.</span></span> <span data-ttu-id="58d1c-116">Un peso bruto de la carga incluye la tara actual y el peso de carga máximo.</span><span class="sxs-lookup"><span data-stu-id="58d1c-116">A load's gross weight includes both its tare weight and its loading weight.</span></span>
    - <span data-ttu-id="58d1c-117">**Número máximo de bultos permitidos** - Ingrese el número máximo de bultos que puede contener la carga.</span><span class="sxs-lookup"><span data-stu-id="58d1c-117">**Maximum number of freight pieces allowed** – Enter the maximum number of freight pieces that the load can contain.</span></span>
    - <span data-ttu-id="58d1c-118">**Carga de pila en el piso** - Seleccione esta casilla de verificación para usar la carga de piso.</span><span class="sxs-lookup"><span data-stu-id="58d1c-118">**Stack load on floor** – Select this check box to use floor loading.</span></span> <span data-ttu-id="58d1c-119">En un escenario de carga de planta, las cajas están apiladas del suelo al techo y de pared a pared dentro del contenedor, para maximizar la capacidad interior.</span><span class="sxs-lookup"><span data-stu-id="58d1c-119">In a floor loading scenario, boxes are stacked floor to ceiling and wall to wall inside the container, to maximize capacity.</span></span>

1. <span data-ttu-id="58d1c-120">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="58d1c-120">On the Action Pane, select **Save**.</span></span>

## <a name="associate-a-load-template-with-a-new-load"></a><span data-ttu-id="58d1c-121">Asociar una plantilla de carga con una nueva carga</span><span class="sxs-lookup"><span data-stu-id="58d1c-121">Associate a load template with a new load</span></span>

1. <span data-ttu-id="58d1c-122">Vaya a **Administración de transporte \> Planificación \> Área de trabajo de planificación de la carga**.</span><span class="sxs-lookup"><span data-stu-id="58d1c-122">Go to **Transportation management \> Planning \> Load planning workbench**.</span></span>
1. <span data-ttu-id="58d1c-123">En la parte superior de la página, seleccione una de las siguientes pestañas, según el tipo de documento de origen para el que está creando una carga: **Envíos**, **Líneas de venta**, **Líneas de transferencia** o **Líneas de orden de compra**.</span><span class="sxs-lookup"><span data-stu-id="58d1c-123">In the upper part of the page, select one of the following tabs, depending on the type of source document that you're creating a load for: **Shipments**, **Sales lines**, **Transfer lines**, or **Purchase order lines**.</span></span> 
1. <span data-ttu-id="58d1c-124">Seleccione el documento específico para planificar la carga.</span><span class="sxs-lookup"><span data-stu-id="58d1c-124">Select the specific document to plan the load for.</span></span>
1. <span data-ttu-id="58d1c-125">En el panel de acciones, en la ficha **Suministro y demanda**, en el grupo **Agregar**, seleccione **A una carga nueva**.</span><span class="sxs-lookup"><span data-stu-id="58d1c-125">On the Action Pane, on the **Supply and demand** tab, in the **Add** group, select **To new load**.</span></span>
1. <span data-ttu-id="58d1c-126">En el cuadro de diálogo **Cargar plantilla**, en el campo **Cargar Id. de plantilla**, seleccione la plantilla para aplicar.</span><span class="sxs-lookup"><span data-stu-id="58d1c-126">In the **Load template** dialog box, in the **Load template ID** field, select the template to apply.</span></span>
1. <span data-ttu-id="58d1c-127">Seleccione **Aceptar** para aplicar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="58d1c-127">Select **OK** to apply the template.</span></span>
