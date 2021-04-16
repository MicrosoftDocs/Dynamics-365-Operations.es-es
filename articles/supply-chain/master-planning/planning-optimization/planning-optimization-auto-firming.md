---
title: Puesta en firme automática con Optimización de planificación
description: Este tema explica cómo usar la puesta en firme automática con la optimización de la planificación.
author: ChristianRytt
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-30
ms.dyn365.ops.version: AX 10.0.7
ms.openlocfilehash: 3542e343de29c9fd9d19ed99cab4b4eebacd2899
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813012"
---
# <a name="autofirming-with-planning-optimization"></a><span data-ttu-id="caf35-103">Puesta en firme automática con Optimización de planificación</span><span class="sxs-lookup"><span data-stu-id="caf35-103">Autofirming with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="caf35-104">La puesta en firme automática permite poner en firme (es decir, enviar) los pedidos planificados como parte del proceso de planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="caf35-104">Automatic firming lets you firm (that is, release) planned orders as part of the master planning process.</span></span> <span data-ttu-id="caf35-105">Cuando se ponen en firme los pedidos planificados, se transforman en pedidos de compra reales, pedidos de transferencia o pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="caf35-105">When planned orders are firmed, they are transformed into actual purchase orders, transfer orders, or production orders.</span></span> <span data-ttu-id="caf35-106">Cuando se usa la optimización de la planificación, los pedidos planificados se ponen en firme durante una planificación maestra ejecutada cuando la fecha del pedido (es decir, la fecha inicial) está dentro del límite de tiempo para la puesta en firme.</span><span class="sxs-lookup"><span data-stu-id="caf35-106">When Planning Optimization is used, planned orders are firmed during a master planning run when the order date (that is, the start date) is within the time fence for firming.</span></span>

> [!NOTE]
> <span data-ttu-id="caf35-107">La puesta en firme automática de un pedido de compra planificado solo puede producirse si el artículo se asocia a un proveedor.</span><span class="sxs-lookup"><span data-stu-id="caf35-107">Auto-firming of a planned purchase order can occur only if the item is associated with a vendor.</span></span>
> 
> <span data-ttu-id="caf35-108">Las órdenes derivadas firmes (órdenes de compra subcontratadas) mostrarán un estado de *En revisión* cuando el seguimiento de cambios de caso está habilitado.</span><span class="sxs-lookup"><span data-stu-id="caf35-108">Firmed derived orders (subcontract purchase orders) will show a status of *In-review* when case change tracking is enabled.</span></span>

## <a name="turn-on-autofirming"></a><span data-ttu-id="caf35-109">Activar la puesta en firme automática</span><span class="sxs-lookup"><span data-stu-id="caf35-109">Turn on autofirming</span></span>

<span data-ttu-id="caf35-110">Para activar la puesta en firme automática, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="caf35-110">To turn on autofirming, follow these steps.</span></span>

1. <span data-ttu-id="caf35-111">En el espacio de trabajo **Administración de funciones**, en la pestaña **Nuevo**, seleccione **Puesta en firme para la optimización de la planificación** en la lista.</span><span class="sxs-lookup"><span data-stu-id="caf35-111">In the **Feature management** workspace, on the **New** tab, select **Auto-firming for Planning Optimization** in the list.</span></span> <span data-ttu-id="caf35-112">Si la función no aparece en la pestaña **Nuevo**, mire en las pestañas **No habilitado** y **Todo**.</span><span class="sxs-lookup"><span data-stu-id="caf35-112">If the feature doesn't appear on the **New** tab, look on the **Not enabled** and **All** tabs.</span></span>
1. <span data-ttu-id="caf35-113">Seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="caf35-113">Select **Enable now**.</span></span> <span data-ttu-id="caf35-114">Como alternativa, seleccione **Programación** y el tiempo en que desea que la función esté activada.</span><span class="sxs-lookup"><span data-stu-id="caf35-114">Alternatively, select **Schedule**, and then select the time when you want the feature to be turned on.</span></span>

## <a name="set-up-the-firming-time-fence"></a><span data-ttu-id="caf35-115">Configurar el límite de tiempo de la puesta en firme</span><span class="sxs-lookup"><span data-stu-id="caf35-115">Set up the firming time fence</span></span>

<span data-ttu-id="caf35-116">El límite de tiempo de puesta en firme se calcula en adelante desde la fecha de ejecución de programación maestra.</span><span class="sxs-lookup"><span data-stu-id="caf35-116">The firming time fence is calculated forward from the master planning run date.</span></span> <span data-ttu-id="caf35-117">Está definido por el número de días que especifique.</span><span class="sxs-lookup"><span data-stu-id="caf35-117">It's defined by the number of days that you enter.</span></span> <span data-ttu-id="caf35-118">Puede controlar el límite de tiempo de puesta en firme de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="caf35-118">You can control the firming time fence in the following ways:</span></span>

- <span data-ttu-id="caf35-119">Para definir el límite de tiempo de puesta en firme predeterminado para un grupo de cobertura, vaya **Planificación maestra** \> **Configuración** \> **Cobertura** \> **Grupos de cobertura**, y seleccione un grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="caf35-119">To define the default firming time fence for a coverage group, go to **Master planning** \> **Setup** \> **Coverage** \> **Coverage groups**, and select a coverage group.</span></span> <span data-ttu-id="caf35-120">A continuación, en la pestaña desplegable **Otro**, en el campo **Límite de tiempo de puesta en firme automática (días)**, especifique el número de días.</span><span class="sxs-lookup"><span data-stu-id="caf35-120">Then, on the **Other** FastTab, in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="caf35-121">Para sobrescribir el intervalo de tiempo de puesta en firme que se define para el grupo de cobertura para un artículo específico, vaya **Gestión de información de productos** \> **Productos despachados** y, a continuación, desde el panel Acciones, seleccione **Plan** y después seleccione **Cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="caf35-121">To overwrite the firming time fence that is defined for the coverage group for a specific item, go to **Product information management** \> **Released products**, then from the Action Pane select **Plan** and then select **Item coverage**.</span></span> <span data-ttu-id="caf35-122">A continuación, en la pestaña **General** , seleccione **Límite de tiempo de la anulación** y en el campo **Límite de tiempo de puesta en firme automática (días)**, especifique el número de días.</span><span class="sxs-lookup"><span data-stu-id="caf35-122">Then, on the **General** tab, select **Override time fence** and in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="caf35-123">Para sobrescribir el límite de tiempo de consolidación que se define para el grupo de cobertura y la cobertura de artículos para un plan maestro específico, vaya a **Planificación maestra** \> **Configuración** \> **Planes maestros** y seleccione un plan maestro.</span><span class="sxs-lookup"><span data-stu-id="caf35-123">To overwrite the firming time fence that is defined for the coverage group and item coverage for a specific master plan, go to **Master planning** \> **Setup** \> **Master plans**, and select a Master plan.</span></span> <span data-ttu-id="caf35-124">A continuación, en la pestaña desplegable **Límite de tiempo en días**, establezca **Puesta en firme** en **Sí** y escriba en número de días.</span><span class="sxs-lookup"><span data-stu-id="caf35-124">Then, on the **Time fence in days** FastTab, set **Firming** to **Yes**, and enter the number of days.</span></span>

<span data-ttu-id="caf35-125">Si se activa la puesta en firme automática para la ejecución del plan maestro que usa la optimización de la planificación, el proceso de puesta en firme automática se realiza de acuerdo con la configuración de la puesta en firme automática.</span><span class="sxs-lookup"><span data-stu-id="caf35-125">If autofirming is turned on for a master planning run that uses Planning Optimization, the autofirming process is done according to the autofirming setup.</span></span> <span data-ttu-id="caf35-126">Si la puesta en firme automática está activada, o si la planificación se inicia desde la página **Requisitos netos**, se omite el proceso de puesta en firme automática.</span><span class="sxs-lookup"><span data-stu-id="caf35-126">If autofirming isn't turned on, or if planning is started from the **Net requirements** page, the autofirming process is skipped.</span></span>

## <a name="planning-optimization-vs-the-built-in-supply-chain-management-planning-engine"></a><span data-ttu-id="caf35-127">Optimización de la planificación comparada con el motor de planificación de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="caf35-127">Planning Optimization vs. the built-in Supply Chain Management planning engine</span></span>

<span data-ttu-id="caf35-128">La optimización de la planificación y el motor de planificación que se integra en Microsoft Dynamics 365 Supply Chain Management pueden utilizarse en pedidos planificaos de puesta en firme automática.</span><span class="sxs-lookup"><span data-stu-id="caf35-128">Both Planning Optimization and the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management can be used to autofirm planned orders.</span></span> <span data-ttu-id="caf35-129">Sin embargo, existen algunas diferencias importantes.</span><span class="sxs-lookup"><span data-stu-id="caf35-129">However, there are some important differences.</span></span> <span data-ttu-id="caf35-130">Por ejemplo, mientras que la optimización de la planificación utiliza la fecha del pedido (es decir, la fecha inicial) para determinar qué pedidos planificados desea poner en firme, el motor de planificación de Supply Chain Management usa la fecha de requisito (es decir, la fecha final).</span><span class="sxs-lookup"><span data-stu-id="caf35-130">For example, whereas Planning Optimization uses the order date (that is, the start date) to determine which planned orders to firm, the built-in Supply Chain Management planning engine uses the requirement date (that is, the end date).</span></span> <span data-ttu-id="caf35-131">A continuación se indica un resumen de las diferencias.</span><span class="sxs-lookup"><span data-stu-id="caf35-131">Here is a summary of the differences.</span></span>

<span data-ttu-id="caf35-132">**Optimización de planificación**</span><span class="sxs-lookup"><span data-stu-id="caf35-132">**Planning Optimization**</span></span>

- <span data-ttu-id="caf35-133">La puesta en firme automática se basa en la fecha del pedido (fecha inicial).</span><span class="sxs-lookup"><span data-stu-id="caf35-133">Autofirming is based on the order date (start date).</span></span>
- <span data-ttu-id="caf35-134">Dado que la fecha del pedido (fecha inicial) activa la puesta en firme, no tiene que tener e cuenta el plazo como parte del límite de tiempo de la puesta en firme.</span><span class="sxs-lookup"><span data-stu-id="caf35-134">Because the order date (start date) triggers the firming, you don't have to consider the lead time as part of the firming time fence.</span></span>
- <span data-ttu-id="caf35-135">Si desea poner en firme todos los pedidos que deben iniciarse durante la semana actual, el límite de tiempo de la puesta en firme debe ser una semana.</span><span class="sxs-lookup"><span data-stu-id="caf35-135">If you want to firm all orders that must start during the current week, the firming time fence must be one week.</span></span>

<span data-ttu-id="caf35-136">**Motor de planificación de Supply Chain Management integrado**</span><span class="sxs-lookup"><span data-stu-id="caf35-136">**Built-in Supply Chain Management planning engine**</span></span>

- <span data-ttu-id="caf35-137">La puesta en firme automática en la fecha de requisito (fecha final).</span><span class="sxs-lookup"><span data-stu-id="caf35-137">Autofirming is based on the requirement date (end date).</span></span>
- <span data-ttu-id="caf35-138">Para ayudar a garantizar que los pedidos se ponen en firme a tiempo, el límite de tiempo de puesta en firme debe ser superior al plazo.</span><span class="sxs-lookup"><span data-stu-id="caf35-138">To help guarantee that orders are firmed in due time, the firming time fence must be longer than the lead time.</span></span>
- <span data-ttu-id="caf35-139">Si desea poner en firme todos los pedidos que deben iniciarse durante la semana actual, el límite de tiempo de la puesta en firme debe ser el plazo más una semana.</span><span class="sxs-lookup"><span data-stu-id="caf35-139">If you want to firm all orders that must start during the current week, the firming time fence must be the lead time plus one week.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
