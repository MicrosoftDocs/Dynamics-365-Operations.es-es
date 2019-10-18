---
title: Cree y actualizar el horario comercial
description: En este tema se describe cómo crear y actualizar el horario comercial en Retail Headquarters.
author: josaw1
manager: AnnBe
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Retail 10.0.1 update
ms.openlocfilehash: 811d499a3eb8133e5ffd29bb4ae6a0c57708accd
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "2023451"
---
# <a name="create-and-update-store-hours"></a><span data-ttu-id="a1856-103">Cree y actualizar el horario comercial</span><span class="sxs-lookup"><span data-stu-id="a1856-103">Create and update store hours</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="a1856-104">Información general</span><span class="sxs-lookup"><span data-stu-id="a1856-104">Overview</span></span>

<span data-ttu-id="a1856-105">De un único lugar, los minoristas pueden crear, mantener y administrar el horario comercial para diferentes tiendas en regiones geográficas.</span><span class="sxs-lookup"><span data-stu-id="a1856-105">From a single place, retailers can create, maintain, and manage the store hours for different stores across geographic regions.</span></span> <span data-ttu-id="a1856-106">El horario comercial se puede mostrar en los terminales de punto de venta (PDV).</span><span class="sxs-lookup"><span data-stu-id="a1856-106">The store hours can then be shown on point of sale (POS) terminals.</span></span> <span data-ttu-id="a1856-107">De esta manera, los cajeros pueden compartir el horario comercial con los clientes y ayudar mejor a los compradores que están interesados en el inventario de otras tiendas.</span><span class="sxs-lookup"><span data-stu-id="a1856-107">In this way, cashiers can share store hours with customers and better help shoppers who are interested in inventory in other stores.</span></span> <span data-ttu-id="a1856-108">El horario comercial también se puede imprimir en recibos, en caso de que los clientes deseen volver a la tienda más adelante.</span><span class="sxs-lookup"><span data-stu-id="a1856-108">The store hours can also be printed on receipts, in case customers want to return to the store later.</span></span>

<span data-ttu-id="a1856-109">Se pueden configurar varios horarios comerciales en distintos canales.</span><span class="sxs-lookup"><span data-stu-id="a1856-109">Multiple store hours can be configured across different channels.</span></span> <span data-ttu-id="a1856-110">Estos canales incluyen tiendas físicas, centros de llamadas, dispositivos móviles y sitios de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1856-110">These channels include brick-and-mortar stores, call centers, mobile devices, and e-Commerce sites.</span></span>

<span data-ttu-id="a1856-111">Si un cliente tiene un pedido de recogida en una tienda diferente, el cajero puede seleccionar las fechas en las que la recogida estará disponible en dicha tienda.</span><span class="sxs-lookup"><span data-stu-id="a1856-111">If a customer has a pickup order for a different store, the cashier can select dates when the pickup will be available in that store.</span></span> <span data-ttu-id="a1856-112">La búsqueda de la tienda proporcionará una referencia a las fechas y horarios de la tienda.</span><span class="sxs-lookup"><span data-stu-id="a1856-112">The store lookup will provide a reference to the dates and store times.</span></span> <span data-ttu-id="a1856-113">El cajero puede seleccionar una fecha y una ubicación, y también puede imprimir un recibo de recogida que incluya el horario comercial.</span><span class="sxs-lookup"><span data-stu-id="a1856-113">The cashier can select a date and location, and can also print a pickup receipt that includes the store hours.</span></span>

<span data-ttu-id="a1856-114">Esta función está disponible en las versiones 8.1.2 y posteriores de Microsoft Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="a1856-114">This functionality is available in Microsoft Dynamics 365 Retail versions 8.1.2 and later.</span></span>

## <a name="configure-store-hours"></a><span data-ttu-id="a1856-115">Configurar horario comercial</span><span class="sxs-lookup"><span data-stu-id="a1856-115">Configure store hours</span></span>

<span data-ttu-id="a1856-116">Siga estos pasos para configurar un horario comercial.</span><span class="sxs-lookup"><span data-stu-id="a1856-116">Follow these steps to configure store hours.</span></span>

1. <span data-ttu-id="a1856-117">Vaya a **Venta minorista** \> **Configuración de canal** \> **Horario comercial**.</span><span class="sxs-lookup"><span data-stu-id="a1856-117">Go to **Retail** \> **Channel Setup** \> **Store hours**.</span></span>
2. <span data-ttu-id="a1856-118">Seleccione **Nueva** para crear una nueva plantilla de horario comercial.</span><span class="sxs-lookup"><span data-stu-id="a1856-118">Select **New** to create a new store hours template.</span></span> <span data-ttu-id="a1856-119">Para usar una plantilla existente, seleccione la plantilla en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="a1856-119">To use an existing template, select the template in the left pane.</span></span>
3. <span data-ttu-id="a1856-120">En el cuadro de diálogo **Agregar intervalo**, defina el intervalo de fechas, el horario comercial y cualquier festivo que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a1856-120">In the **Add range** dialog box, define the date range, the store hours, and any holidays that are required.</span></span>

    - <span data-ttu-id="a1856-121">Si el horario comercial no cambia, seleccione **Nunca termina** en el campo **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="a1856-121">If store hours don't change, select **Never ends** in the **End date** field.</span></span>
    - <span data-ttu-id="a1856-122">Si el horario comercial es para un mes, semana o día determinado, establezca las fechas adecuadas en los campos **Fecha de inicio** y **Fecha de finalización**.</span><span class="sxs-lookup"><span data-stu-id="a1856-122">If the store hours are for a specific month, week, or day, set the appropriate dates in the **Start Date** and **End date** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a1856-123">Puede crear varias plantillas que tengan fechas de inicio y de finalización solapadas.</span><span class="sxs-lookup"><span data-stu-id="a1856-123">You can create multiple templates that have overlapping start and end dates.</span></span> <span data-ttu-id="a1856-124">De este modo, puede, por ejemplo, definir el horario comercial para las tiendas en distintas zonas horarias.</span><span class="sxs-lookup"><span data-stu-id="a1856-124">Therefore, you can, for example, define store hours for stores in different time zones.</span></span>

    <span data-ttu-id="a1856-125">![Cuadro de diálogo Agregar intervalo](../dev-itpro/media/Storehours1.png "Cuadro de diálogo Agregar intervalo")</span><span class="sxs-lookup"><span data-stu-id="a1856-125">![Add range dialog box](../dev-itpro/media/Storehours1.png "Add range dialog box")</span></span>

4. <span data-ttu-id="a1856-126">Asocie la plantilla de horario comercial a las tiendas en la que se usará.</span><span class="sxs-lookup"><span data-stu-id="a1856-126">Associate the store hours template with the stores where it will be used.</span></span> <span data-ttu-id="a1856-127">En el cuadro de diálogo **Elegir nodos organizativos**, seleccione las tiendas, regiones y organizaciones a las que debe asociarse la plantilla.</span><span class="sxs-lookup"><span data-stu-id="a1856-127">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>

    - <span data-ttu-id="a1856-128">Solo se puede asociar una plantilla de horario comercial a cada tienda.</span><span class="sxs-lookup"><span data-stu-id="a1856-128">Only one store hours template can be associated with each store.</span></span>
    - <span data-ttu-id="a1856-129">Use los botones de flecha para seleccionar tiendas, regiones u organizaciones.</span><span class="sxs-lookup"><span data-stu-id="a1856-129">Use the arrow buttons to select stores, regions, or organizations.</span></span> <span data-ttu-id="a1856-130">El calendario estará disponible para las tiendas o grupos de tiendas, y será visible en el PDV como referencia.</span><span class="sxs-lookup"><span data-stu-id="a1856-130">The calendar will be available to the stores or store groups, and it will be visible at the POS for reference.</span></span>

    <span data-ttu-id="a1856-131">![Cuadro de diálogo Elegir nodos organizativos](../dev-itpro/media/Storehours2.png "Cuadro de diálogo Elegir nodos organizativos")</span><span class="sxs-lookup"><span data-stu-id="a1856-131">![Choose organization nodes dialog box](../dev-itpro/media/Storehours2.png "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="a1856-132">En la página **Programación de distribución**, ejecute los trabajos **1070** y **1090** para hacer que el horario comercial esté disponible en el PDV.</span><span class="sxs-lookup"><span data-stu-id="a1856-132">On the **Distribution schedule** page, run the **1070** and **1090** jobs to make the store hours available to the POS.</span></span>

## <a name="add-store-hours-to-printed-receipts"></a><span data-ttu-id="a1856-133">Agregar horario comercial a recibos impresos</span><span class="sxs-lookup"><span data-stu-id="a1856-133">Add store hours to printed receipts</span></span>

<span data-ttu-id="a1856-134">Siga estos pasos para agregar un horario comercial a las recepciones de PDV impresos.</span><span class="sxs-lookup"><span data-stu-id="a1856-134">Follow these steps to add store hours to the printed POS receipts.</span></span>

1. <span data-ttu-id="a1856-135">Abra el diseñador de recibos.</span><span class="sxs-lookup"><span data-stu-id="a1856-135">Open the receipt designer.</span></span>
2. <span data-ttu-id="a1856-136">Seleccione **Pie de página** en la esquina inferior izquierda.</span><span class="sxs-lookup"><span data-stu-id="a1856-136">Select **Footer** in the lower-left corner.</span></span>
3. <span data-ttu-id="a1856-137">Arrastre el elemento **Horario comercial** desde el panel izquierdo al pie de página en la parte inferior de la plantilla de recibo.</span><span class="sxs-lookup"><span data-stu-id="a1856-137">Drag the **Store hours** element from the left pane to the footer at the bottom of the receipt template.</span></span>
4. <span data-ttu-id="a1856-138">Puede editar la etiqueta predeterminada en el elemento **Horario comercial** según necesite.</span><span class="sxs-lookup"><span data-stu-id="a1856-138">You can edit the default label on the **Store hours** element as you require.</span></span>
5. <span data-ttu-id="a1856-139">Guarde el recibo y cierre el diseñador de recibos.</span><span class="sxs-lookup"><span data-stu-id="a1856-139">Save the receipt, and close the receipt designer.</span></span>
6. <span data-ttu-id="a1856-140">En la página **Programación de distribución**, ejecute los trabajos **1070** y **1090**.</span><span class="sxs-lookup"><span data-stu-id="a1856-140">On the **Distribution schedule** page, run the **1070** and **1090** jobs.</span></span>
7. <span data-ttu-id="a1856-141">Inicie sesión en el PDV.</span><span class="sxs-lookup"><span data-stu-id="a1856-141">Sign in to the POS.</span></span>
8. <span data-ttu-id="a1856-142">Complete una venta y seleccione imprimir un recibo.</span><span class="sxs-lookup"><span data-stu-id="a1856-142">Complete a sale, and select to print a receipt.</span></span>

<span data-ttu-id="a1856-143">Los recibos de PDV incluyen ahora el horario comercial.</span><span class="sxs-lookup"><span data-stu-id="a1856-143">POS receipts now include the store hours.</span></span> <span data-ttu-id="a1856-144">Si se incluyeron algunos festivos en la plantilla, estos se muestran en el recibo.</span><span class="sxs-lookup"><span data-stu-id="a1856-144">If any holidays were included in the template, they are shown on the receipt.</span></span>

<span data-ttu-id="a1856-145">![Ejemplo de recibo](../dev-itpro/media/Storehours3.png "Ejemplo de recibo")</span><span class="sxs-lookup"><span data-stu-id="a1856-145">![Receipt example](../dev-itpro/media/Storehours3.png "Receipt example")</span></span>
