---
title: Tolerancia al retraso (días negativos)
description: Este tema proporciona información sobre el cálculo de la tolerancia de demora y cómo afecta la creación de órdenes planificadas en Planning Optimization.
author: crytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 748e047e89747f2eabccc04a40c79bcb1e6f3dea
ms.sourcegitcommit: f21659f1c23bc2cd65bbe7fb7210910d5a8e1cb9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306472"
---
# <a name="delay-tolerance-negative-days"></a><span data-ttu-id="849d4-103">Tolerancia al retraso (días negativos)</span><span class="sxs-lookup"><span data-stu-id="849d4-103">Delay tolerance (negative days)</span></span>

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="849d4-104">La funcionalidad de tolerancia de retardo permite a Planning Optimization considerar el valor **Días negativos** que se establece para los grupos de cobertura.</span><span class="sxs-lookup"><span data-stu-id="849d4-104">The delay tolerance functionality enables Planning Optimization to consider the **Negative days** value that is set for coverage groups.</span></span> <span data-ttu-id="849d4-105">Se utiliza para extender el período de tolerancia de demora que se aplica durante la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="849d4-105">It's used to extend the delay tolerance period that is applied during master planning.</span></span> <span data-ttu-id="849d4-106">De esta manera, puede evitar la creación de nuevos pedidos de suministro si el suministro existente podrá cubrir la demanda después de un breve retraso.</span><span class="sxs-lookup"><span data-stu-id="849d4-106">In this way, you can avoid creating new supply orders if existing supply will be able to cover the demand after a short delay.</span></span> <span data-ttu-id="849d4-107">El propósito de la funcionalidad es determinar si tiene sentido crear un nuevo pedido de suministro para una demanda determinada.</span><span class="sxs-lookup"><span data-stu-id="849d4-107">The purpose of the functionality is to determine whether it makes sense to create a new supply order for a given demand.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="849d4-108">Activar la función en el sistema</span><span class="sxs-lookup"><span data-stu-id="849d4-108">Turn on the feature in your system</span></span>

<span data-ttu-id="849d4-109">Para que esta funcionalidad de tolerancia de retraso esté disponible en su sistema, vaya a [Gestión de funciones](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active la función *Días negativos para Optimización de planificación*.</span><span class="sxs-lookup"><span data-stu-id="849d4-109">To make the delay tolerance functionality available in your system, go to [Feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Negative days for Planning Optimization* feature.</span></span>

## <a name="delay-tolerance-in-planning-optimization"></a><span data-ttu-id="849d4-110">Tolerancia de retraso en la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="849d4-110">Delay tolerance in Planning Optimization</span></span>

<span data-ttu-id="849d4-111">La tolerancia de demora representa la cantidad de días más allá del tiempo de entrega que está dispuesto a esperar antes de ordenar un nuevo reabastecimiento cuando el suministro existente ya está planeado.</span><span class="sxs-lookup"><span data-stu-id="849d4-111">Delay tolerance represents the number of days beyond the lead time that you're willing to wait before you order new replenishment when existing supply is already planned.</span></span> <span data-ttu-id="849d4-112">La tolerancia de demora se define mediante el uso de días calendario, no días hábiles.</span><span class="sxs-lookup"><span data-stu-id="849d4-112">Delay tolerance is defined by using calendar days, not business days.</span></span>

<span data-ttu-id="849d4-113">En el momento de la planificación maestra, cuando el sistema calcula la tolerancia de demora, considera la configuración **Días negativos**.</span><span class="sxs-lookup"><span data-stu-id="849d4-113">At the time of master planning, when the system calculates the delay tolerance, it considers the **Negative days** setting.</span></span> <span data-ttu-id="849d4-114">Puede establecer el valor **Días negativos** en la página **Grupos de cobertura** o en la página **Cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="849d4-114">You can set the **Negative days** value on either the **Coverage groups** page or the **Item coverage** page.</span></span>

<span data-ttu-id="849d4-115">El sistema vincula el cálculo de la tolerancia de retardo a la *fecha de reabastecimiento más temprana*, que equivale a la fecha de hoy más el plazo de entrega.</span><span class="sxs-lookup"><span data-stu-id="849d4-115">The system links the delay tolerance calculation to the *earliest replenishment date*, which equals today's date plus the lead time.</span></span> <span data-ttu-id="849d4-116">La tolerancia de retardo se calcula utilizando la siguiente fórmula, donde *max ()* encuentra el mayor de dos valores:</span><span class="sxs-lookup"><span data-stu-id="849d4-116">The delay tolerance is calculated by using following formula, where *max()* finds the larger of two values:</span></span>

<span data-ttu-id="849d4-117">*max (fecha de reabastecimiento más temprana, fecha de vencimiento de la demanda)* - *Fecha de vencimiento de la demanda* + *Días negativos*</span><span class="sxs-lookup"><span data-stu-id="849d4-117">*max(Earliest replenishment date, Demand due date)* – *Demand due date* + *Negative days*</span></span>

<span data-ttu-id="849d4-118">Esta fórmula garantiza que la planificación maestra no cree nuevos pedidos de suministro cuando existe suficiente suministro durante el tiempo de entrega del producto.</span><span class="sxs-lookup"><span data-stu-id="849d4-118">This formula ensures that master planning doesn't create new supply orders when enough supply exists during the product lead time.</span></span>

> [!NOTE]
> <span data-ttu-id="849d4-119">El cálculo de la tolerancia de retraso en la Optimización de planificación siempre utiliza el cálculo de días negativos dinámicos de la planificación maestra incorporada.</span><span class="sxs-lookup"><span data-stu-id="849d4-119">The delay tolerance calculation in Planning Optimization always uses the dynamic negative days calculation from built-in master planning.</span></span> <span data-ttu-id="849d4-120">El valor **Utilice días negativos dinámicos** de la paǵina **Parámetros de planificación maestra** no tiene ningún efecto sobre este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="849d4-120">The **Use dynamic negative days** setting on the **Master planning parameters** page has no effect on this behavior.</span></span>

<span data-ttu-id="849d4-121">Si el suministro existente implica un retraso en la demanda menor o igual que la tolerancia de retraso calculada, la optimización de planificación relaciona el suministro existente con la demanda.</span><span class="sxs-lookup"><span data-stu-id="849d4-121">If the existing supply implies a demand delay that is less than or equal to the calculated delay tolerance, Planning Optimization pegs existing supply with the demand.</span></span> <span data-ttu-id="849d4-122">En algunos casos, es mejor retrasar la demanda que terminar con un exceso de oferta.</span><span class="sxs-lookup"><span data-stu-id="849d4-122">In some cases, it's better to delay the demand than to end up with oversupply.</span></span>

<span data-ttu-id="849d4-123">Las siguientes subsecciones proporcionan ejemplos que muestran cómo la tolerancia de demora afecta la creación de órdenes planificadas en Planning Optimization.</span><span class="sxs-lookup"><span data-stu-id="849d4-123">The following subsections provide examples that show how delay tolerance affects the creation of planned orders in Planning Optimization.</span></span>

### <a name="example-1"></a><span data-ttu-id="849d4-124">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="849d4-124">Example 1</span></span>

<span data-ttu-id="849d4-125">Un producto tiene la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="849d4-125">A product has the following configuration:</span></span>

- <span data-ttu-id="849d4-126">**Plazo:** *10*</span><span class="sxs-lookup"><span data-stu-id="849d4-126">**Lead time:** *10*</span></span>
- <span data-ttu-id="849d4-127">**Días negativos:** *2*</span><span class="sxs-lookup"><span data-stu-id="849d4-127">**Negative days:** *2*</span></span>

<span data-ttu-id="849d4-128">Existe la siguiente oferta y demanda para el producto:</span><span class="sxs-lookup"><span data-stu-id="849d4-128">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="849d4-129">**Demanda para hoy:** Un pedido de cliente por una cantidad de 10</span><span class="sxs-lookup"><span data-stu-id="849d4-129">**Demand for today:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="849d4-130">**Suministro en 12 días:** Una orden de compra por una cantidad de 10</span><span class="sxs-lookup"><span data-stu-id="849d4-130">**Supply in 12 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="849d4-131">La oferta existente puede cubrir la demanda en un plazo de 12 días, y ese período es igual a la tolerancia de demora.</span><span class="sxs-lookup"><span data-stu-id="849d4-131">Existing supply can cover the demand within 12 days, and that period equals the delay tolerance.</span></span> <span data-ttu-id="849d4-132">Por lo tanto, cuando se ejecuta la planificación maestra, no se crean órdenes previsionales.</span><span class="sxs-lookup"><span data-stu-id="849d4-132">Therefore, when master planning runs, no planned orders are created.</span></span>

### <a name="example-2"></a><span data-ttu-id="849d4-133">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="849d4-133">Example 2</span></span>

<span data-ttu-id="849d4-134">Un producto tiene la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="849d4-134">A product has the following configuration:</span></span>

- <span data-ttu-id="849d4-135">**Plazo:** *10*</span><span class="sxs-lookup"><span data-stu-id="849d4-135">**Lead time:** *10*</span></span>
- <span data-ttu-id="849d4-136">**Días negativos:** *0*</span><span class="sxs-lookup"><span data-stu-id="849d4-136">**Negative days:** *0*</span></span>

<span data-ttu-id="849d4-137">Existe la siguiente oferta y demanda para el producto:</span><span class="sxs-lookup"><span data-stu-id="849d4-137">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="849d4-138">**Demanda para hoy:** Un pedido de cliente por una cantidad de 10</span><span class="sxs-lookup"><span data-stu-id="849d4-138">**Demand for today:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="849d4-139">**Suministro en 12 días:** Una orden de compra por una cantidad de 10</span><span class="sxs-lookup"><span data-stu-id="849d4-139">**Supply in 12 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="849d4-140">La oferta existente puede cubrir la demanda solo después de 12 días.</span><span class="sxs-lookup"><span data-stu-id="849d4-140">Existing supply can cover the demand only after 12 days.</span></span> <span data-ttu-id="849d4-141">Sin embargo, la tolerancia de retraso es de 10 días.</span><span class="sxs-lookup"><span data-stu-id="849d4-141">However, the delay tolerance is 10 days.</span></span> <span data-ttu-id="849d4-142">Por lo tanto, cuando se ejecuta la planificación maestra, se crea una orden previsional para una cantidad de 10.</span><span class="sxs-lookup"><span data-stu-id="849d4-142">Therefore, when master planning runs, a planned order for a quantity of 10 is created.</span></span>

### <a name="example-3"></a><span data-ttu-id="849d4-143">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="849d4-143">Example 3</span></span>

<span data-ttu-id="849d4-144">Un producto tiene la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="849d4-144">A product has the following configuration:</span></span>

- <span data-ttu-id="849d4-145">**Plazo:** *10*</span><span class="sxs-lookup"><span data-stu-id="849d4-145">**Lead time:** *10*</span></span>
- <span data-ttu-id="849d4-146">**Días negativos:** *2*</span><span class="sxs-lookup"><span data-stu-id="849d4-146">**Negative days:** *2*</span></span>

<span data-ttu-id="849d4-147">Existe la siguiente oferta y demanda para el producto:</span><span class="sxs-lookup"><span data-stu-id="849d4-147">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="849d4-148">**Demanda en 11 días:** Un pedido de cliente por una cantidad de 10</span><span class="sxs-lookup"><span data-stu-id="849d4-148">**Demand in 11 days:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="849d4-149">**Suministro en 14 días:** Una orden de compra por una cantidad de 10</span><span class="sxs-lookup"><span data-stu-id="849d4-149">**Supply in 14 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="849d4-150">La oferta existente puede cubrir la demanda solo después de tres días.</span><span class="sxs-lookup"><span data-stu-id="849d4-150">Existing supply can cover the demand only after three days.</span></span> <span data-ttu-id="849d4-151">Sin embargo, la tolerancia de retraso es de dos días.</span><span class="sxs-lookup"><span data-stu-id="849d4-151">However, the delay tolerance is two days.</span></span> <span data-ttu-id="849d4-152">(En este caso, la tolerancia de demora incluye solo los dos días negativos.</span><span class="sxs-lookup"><span data-stu-id="849d4-152">(In this case, the delay tolerance includes only the two negative days.</span></span> <span data-ttu-id="849d4-153">La fecha de demanda no se incluye porque es posterior al plazo de entrega del producto). Por lo tanto, cuando se ejecuta la planificación maestra, se crea un pedido planificado para una cantidad de 10.</span><span class="sxs-lookup"><span data-stu-id="849d4-153">The demand date isn't included because it's after the product lead time.) Therefore, when master planning runs, a planned order for a quantity of 10 is created.</span></span>
