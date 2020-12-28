---
title: Reabastecimiento inmediato
description: Este tema describe cómo puede usar el reabastecimiento inmediato para reabastecer el inventario cuando una directiva de la ubicación no puede asignar el inventario.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSReplenishmentTemplates
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: c69a9c9fd595280ba4f05a11409a3e672e4b1691
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437245"
---
# <a name="immediate-replenishment"></a><span data-ttu-id="b609a-103">Reabastecimiento inmediato</span><span class="sxs-lookup"><span data-stu-id="b609a-103">Immediate replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b609a-104">El reabastecimiento inmediato le permite reabastecer el inventario de forma inmediata cuando una línea de directiva de la ubicación no puede asignar el inventario.</span><span class="sxs-lookup"><span data-stu-id="b609a-104">Immediate replenishment lets you replenish inventory immediately after a location directive line fails to allocate inventory.</span></span> <span data-ttu-id="b609a-105">El reabastecimiento se basa en una única línea en la configuración de la directiva de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="b609a-105">The replenishment is based on a single line in the setup of the location directive.</span></span> <span data-ttu-id="b609a-106">Si el inventario no está disponible en la unidad de medida que se especifica por dicha línea, el reabastecimiento de esa unidad de medida aparece inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="b609a-106">If inventory isn't on hand in the unit of measure that is specified by that line, replenishment of that unit of measure occurs immediately.</span></span>

<span data-ttu-id="b609a-107">El reabastecimiento inmediato proporciona una alternativa al método en el que la asignación del inventario se basa en más líneas en la directiva de la ubicación y dónde la demanda se suma al final de la asignación y se reabastece en la unidad de medida especificada en la última línea en la directiva de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="b609a-107">Immediate replenishment provides an alternative to the method where the allocation of inventory is based on more lines in the location directive, and where the demand is summed at the end of the allocation and replenished in the unit of measure that is specified by the last line in the location directive.</span></span>

<span data-ttu-id="b609a-108">Los beneficios del uso del reabastecimiento inmediato son que el reabastecimiento se puede limitar por las unidades específicas y la cantidad se puede dirigir a ubicaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="b609a-108">The benefits of using immediate replenishment are that replenishment can be limited by specific units and the quantity can be directed to specific locations.</span></span>

## <a name="business-scenario"></a><span data-ttu-id="b609a-109">Escenario empresarial</span><span class="sxs-lookup"><span data-stu-id="b609a-109">Business scenario</span></span>

<span data-ttu-id="b609a-110">Por ejemplo, tiene un almacén que tiene áreas de picking individuales para las unidades de medida "caja" y "unidad".</span><span class="sxs-lookup"><span data-stu-id="b609a-110">For example, you have a warehouse that has separate picking areas for the "box" and "each" units of measure.</span></span> <span data-ttu-id="b609a-111">Desea optimizar el proceso de picking recogiendo tantas cajas como sea posible y después recoger cualquier cantidad restante que sea inferior a una caja del área "unidad".</span><span class="sxs-lookup"><span data-stu-id="b609a-111">You want to optimize the picking process by picking as many boxes as possible and then picking any remaining quantity that is less than a box from the "each" area.</span></span>

<span data-ttu-id="b609a-112">En este caso, puede usar el reabastecimiento inmediato.</span><span class="sxs-lookup"><span data-stu-id="b609a-112">In this case, you can use immediate replenishment.</span></span> <span data-ttu-id="b609a-113">En la directiva de la ubicación, puede configurar el reabastecimiento inmediato para las cajas para usar el reabastecimiento de la demanda tan pronto como haya escasez de cajas que se pueden recoger para la cantidad de demanda.</span><span class="sxs-lookup"><span data-stu-id="b609a-113">In the location directive, you can set up immediate replenishment for boxes so that demand replenishment is used as soon as there is a shortage of boxes that can be picked for the demand quantity.</span></span> <span data-ttu-id="b609a-114">De esta manera, se optimiza el proceso de picking de modo que la distribución incluya tantas cajas como sea posible.</span><span class="sxs-lookup"><span data-stu-id="b609a-114">In this way, you optimize the picking process so that picking includes as many boxes as possible.</span></span> <span data-ttu-id="b609a-115">El reabastecimiento inmediato generará el reabastecimiento de las cajas y la demanda no se transferirá para seleccionar las cantidades de la unidad de medida "unidad".</span><span class="sxs-lookup"><span data-stu-id="b609a-115">Immediate replenishment will generate replenishment of the boxes, and the demand won't be passed on so that the quantities are picked in the "each" unit of measure.</span></span> <span data-ttu-id="b609a-116">Es decir, sólo las cantidades que se supone que deben de ser seleccionadas en la unidad de medida "unidad" (es decir, las cantidades inferiores a una caja) se seleccionarán del área "unidad".</span><span class="sxs-lookup"><span data-stu-id="b609a-116">In other words, only the quantities that are supposed to be picked in the "each" unit of measure (that is, quantities that are less than a box) will be picked from the "each" area.</span></span> <span data-ttu-id="b609a-117">Si hay escasez en el área "caja", puede seleccionar tantas cajas como sea posible de la demanda total.</span><span class="sxs-lookup"><span data-stu-id="b609a-117">If a shortage occurs in the "box" area, you can pick as many boxes as possible out of the total demand.</span></span> <span data-ttu-id="b609a-118">Las cantidades restantes se seleccionarán del área "unidad".</span><span class="sxs-lookup"><span data-stu-id="b609a-118">The remaining quantities will then be picked from the "each" area.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="b609a-119">Dónde se aplica</span><span class="sxs-lookup"><span data-stu-id="b609a-119">Where it applies</span></span>

<span data-ttu-id="b609a-120">El reabastecimiento inmediato se usa durante la ejecución de una oleada si falla la asignación de una línea de directiva de ubicación que tenga una plantilla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="b609a-120">Immediate replenishment is used during wave execution if allocation fails for a location directive line that a replenishment template is set for.</span></span>

## <a name="set-up-immediate-replenishment"></a><span data-ttu-id="b609a-121">Configure el reabastecimiento inmediato</span><span class="sxs-lookup"><span data-stu-id="b609a-121">Set up immediate replenishment</span></span>

- <span data-ttu-id="b609a-122">Vaya a **Administración de almacenes** \> **Configuración** \> **Directivas de la ubicación** y, a continuación, en la pestaña **Líneas** , en la lista **Plantilla de reabastecimiento inmediato**, seleccione una plantilla de reabastecimiento para la demanda de la oleada.</span><span class="sxs-lookup"><span data-stu-id="b609a-122">Go to **Warehouse management** \> **Setup** \> **Location directives**, and then, on the **Lines** tab, in the **Immediate replenishment template** list, select a replenishment template for wave demand.</span></span>

<span data-ttu-id="b609a-123">Se aplica la plantilla de reabastecimiento si la línea de directiva de la ubicación no puede asignar una unidad de medida dedicada.</span><span class="sxs-lookup"><span data-stu-id="b609a-123">The replenishment template is applied if the location directive line fails to allocate a dedicated unit of measure.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b609a-124">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="b609a-124">Troubleshooting</span></span>

<span data-ttu-id="b609a-125">Si el reabastecimiento inmediato está activado para una línea directiva de la ubicación, pero no se generará ningún trabajo de reabastecimiento al utilizar plantillas de reabastecimiento de demanda para dicha línea de directiva de la ubicación, dos causas principales deben ser investigadas:</span><span class="sxs-lookup"><span data-stu-id="b609a-125">If immediate replenishment is selected for a location directive line, but no replenishment work is generated when you use demand replenishment templates for that location directive line, two main causes must be investigated:</span></span>

- <span data-ttu-id="b609a-126">Asegúrese de que la plantilla de reabastecimiento de la demanda que se aplica esté configurada para usar plantillas correctas de la ubicación y plantillas de trabajo del tipo **reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="b609a-126">Make sure that the demand replenishment template that is applied is set up to use the correct location templates and work templates of the **Replenishment** type.</span></span>
- <span data-ttu-id="b609a-127">Asegúrese de que haya suficiente inventario disponible en las ubicaciones en las que la plantilla de reabastecimiento de la demanda busca inventario disponible para reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="b609a-127">Make sure that there is enough on-hand inventory at the locations where the demand replenishment template searches for on-hand inventory for replenishment.</span></span>
