---
title: Cargar plantillas
description: Este tema describe cómo configurar plantillas de carga y cómo asociar una plantilla de carga a una nueva carga.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 175c8017b14cc298cdaa00031f8450015a747786
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831515"
---
# <a name="load-templates"></a><span data-ttu-id="c006e-103">Cargar plantillas</span><span class="sxs-lookup"><span data-stu-id="c006e-103">Load templates</span></span>

<span data-ttu-id="c006e-104">Cuando crea una nueva carga, puede asignar una plantilla de carga.</span><span class="sxs-lookup"><span data-stu-id="c006e-104">When you create a new load, you can assign a load template.</span></span> <span data-ttu-id="c006e-105">La plantilla de carga contiene información sobre el equipo y sobre medidas como la altura, el ancho, la profundidad y el volumen de la carga.</span><span class="sxs-lookup"><span data-stu-id="c006e-105">The load template contains information about equipment, and about measures such as the height, width, depth, and volume of the load.</span></span>

<span data-ttu-id="c006e-106">Este tema describe cómo configurar plantillas de carga y cómo asociar una plantilla de carga a una nueva carga.</span><span class="sxs-lookup"><span data-stu-id="c006e-106">This topic describes how to set up load templates, and how to associate a load template with a new load.</span></span>

## <a name="set-up-a-load-template"></a><span data-ttu-id="c006e-107">Configurar una plantilla de carga</span><span class="sxs-lookup"><span data-stu-id="c006e-107">Set up a load template</span></span>

1. <span data-ttu-id="c006e-108">Ir **Gestión de transporte \> Preparar \> Creación de carga \> Plantilla de carga**.</span><span class="sxs-lookup"><span data-stu-id="c006e-108">Go to **Transportation management \> Setup \> Load Building \> Load template**.</span></span>
1. <span data-ttu-id="c006e-109">En el panel de acciones, seleccione **Nuevo** para agregar una nueva plantilla o **Editar** para editar una plantilla existente.</span><span class="sxs-lookup"><span data-stu-id="c006e-109">On the Action Pane, select **New** to add a new template or **Edit** to edit an existing template.</span></span>
1. <span data-ttu-id="c006e-110">En la fila de la plantilla nueva o existente, configure los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="c006e-110">In the row for the new or existing template, set the following fields:</span></span>

    - <span data-ttu-id="c006e-111">**ID de plantilla de carga** – Introduzca un identificador único para la plantilla de carga.</span><span class="sxs-lookup"><span data-stu-id="c006e-111">**Load template ID** – Enter a unique identifier (ID) for the load template.</span></span>
    - <span data-ttu-id="c006e-112">**Equipo** - Seleccione el equipo que se debe utilizar para enviar la carga.</span><span class="sxs-lookup"><span data-stu-id="c006e-112">**Equipment** – Select the equipment that should be used to ship the load.</span></span>
    - <span data-ttu-id="c006e-113">**Altura de carga**, **Ancho de carga** y **Profundidad de carga** - Ingrese las dimensiones de la carga.</span><span class="sxs-lookup"><span data-stu-id="c006e-113">**Load height**, **Load width**, and **Load depth** – Enter the dimensions of the load.</span></span>
    - <span data-ttu-id="c006e-114">**Max. volumen de carga permitido** y **Max. peso de carga permitido** - Introduzca el volumen y el peso máximos permitidos de la carga.</span><span class="sxs-lookup"><span data-stu-id="c006e-114">**Max. allowed load volume** and **Max. allowed load weight** – Enter the maximum allowed volume and weight of the load.</span></span>
    - <span data-ttu-id="c006e-115">**Peso bruto máximo permitido** - Ingrese el peso bruto máximo permitido de la carga.</span><span class="sxs-lookup"><span data-stu-id="c006e-115">**Maximum allowed gross weight** – Enter the maximum allowed gross weight of the load.</span></span> <span data-ttu-id="c006e-116">Un peso bruto de la carga incluye la tara actual y el peso de carga máximo.</span><span class="sxs-lookup"><span data-stu-id="c006e-116">A load's gross weight includes both its tare weight and its loading weight.</span></span>
    - <span data-ttu-id="c006e-117">**Número máximo de bultos permitidos** - Ingrese el número máximo de bultos que puede contener la carga.</span><span class="sxs-lookup"><span data-stu-id="c006e-117">**Maximum number of freight pieces allowed** – Enter the maximum number of freight pieces that the load can contain.</span></span>
    - <span data-ttu-id="c006e-118">**Carga de pila en el piso** - Seleccione esta casilla de verificación para usar la carga de piso.</span><span class="sxs-lookup"><span data-stu-id="c006e-118">**Stack load on floor** – Select this check box to use floor loading.</span></span> <span data-ttu-id="c006e-119">En un escenario de carga de planta, las cajas están apiladas del suelo al techo y de pared a pared dentro del contenedor, para maximizar la capacidad interior.</span><span class="sxs-lookup"><span data-stu-id="c006e-119">In a floor loading scenario, boxes are stacked floor to ceiling and wall to wall inside the container, to maximize capacity.</span></span>

1. <span data-ttu-id="c006e-120">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c006e-120">On the Action Pane, select **Save**.</span></span>

## <a name="associate-a-load-template-with-a-new-load"></a><span data-ttu-id="c006e-121">Asociar una plantilla de carga con una nueva carga</span><span class="sxs-lookup"><span data-stu-id="c006e-121">Associate a load template with a new load</span></span>

1. <span data-ttu-id="c006e-122">Vaya a **Administración de transporte \> Planificación \> Área de trabajo de planificación de la carga**.</span><span class="sxs-lookup"><span data-stu-id="c006e-122">Go to **Transportation management \> Planning \> Load planning workbench**.</span></span>
1. <span data-ttu-id="c006e-123">En la parte superior de la página, seleccione una de las siguientes pestañas, según el tipo de documento de origen para el que está creando una carga: **Envíos**, **Líneas de venta**, **Líneas de transferencia** o **Líneas de orden de compra**.</span><span class="sxs-lookup"><span data-stu-id="c006e-123">In the upper part of the page, select one of the following tabs, depending on the type of source document that you're creating a load for: **Shipments**, **Sales lines**, **Transfer lines**, or **Purchase order lines**.</span></span> 
1. <span data-ttu-id="c006e-124">Seleccione el documento específico para planificar la carga.</span><span class="sxs-lookup"><span data-stu-id="c006e-124">Select the specific document to plan the load for.</span></span>
1. <span data-ttu-id="c006e-125">En el panel de acciones, en la ficha **Suministro y demanda**, en el grupo **Agregar**, seleccione **A una carga nueva**.</span><span class="sxs-lookup"><span data-stu-id="c006e-125">On the Action Pane, on the **Supply and demand** tab, in the **Add** group, select **To new load**.</span></span>
1. <span data-ttu-id="c006e-126">En el cuadro de diálogo **Cargar plantilla**, en el campo **Cargar Id. de plantilla**, seleccione la plantilla para aplicar.</span><span class="sxs-lookup"><span data-stu-id="c006e-126">In the **Load template** dialog box, in the **Load template ID** field, select the template to apply.</span></span>
1. <span data-ttu-id="c006e-127">Seleccione **Aceptar** para aplicar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="c006e-127">Select **OK** to apply the template.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]