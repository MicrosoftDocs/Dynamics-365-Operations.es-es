---
title: Estrategias de embalaje de contenedores
description: Este tema describe las diferencias entre las estrategias de embalaje de contenedores y proporciona ejemplos.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: article
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f481f6ca047ee0285fe0e81d8fa96665e9d27cee
ms.sourcegitcommit: 8e846b52763f90d2232ec7d427839f4722570bce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "6292770"
---
# <a name="container-packing-strategies"></a><span data-ttu-id="e017b-103">Estrategias de embalaje de contenedores</span><span class="sxs-lookup"><span data-stu-id="e017b-103">Container packing strategies</span></span>

<span data-ttu-id="e017b-104">Una *estrategia de embalaje de contenedores* es una estrategia que puede utilizar para definir asignaciones de artículos entre contenedores.</span><span class="sxs-lookup"><span data-stu-id="e017b-104">A *container packing strategy* is a strategy that you can use to define item allocations across containers.</span></span> <span data-ttu-id="e017b-105">Este tema explica las diferencias entre las estrategias *Empaquetar en todos los contenedores abiertos* y *Empaquetar solo en el contenedor actual*.</span><span class="sxs-lookup"><span data-stu-id="e017b-105">This topic explains the differences between the *Pack into all open containers* and *Pack into current container only* strategies.</span></span>

- <span data-ttu-id="e017b-106">**Empaquetar en todos los contenedores abiertos** - El sistema debe verificar todos los contenedores abiertos que ya se hayan creado durante el ciclo de contenedorización, para asegurarse de que el artículo quepa en uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="e017b-106">**Pack into all open containers** – The system must check all open containers that have already been created during the containerization cycle, to make sure that the item will fit into one of them.</span></span> <span data-ttu-id="e017b-107">Durante el embalaje, el sistema verifica cada artículo para determinar si cabe en alguno de los contenedores creados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e017b-107">During packing, the system checks each item to determine whether it will fit into any of the previously created containers.</span></span> <span data-ttu-id="e017b-108">Si el artículo no cabe en un contenedor existente, el sistema crea un contenedor nuevo y continúa hasta que haya terminado de empaquetar todo el pedido.</span><span class="sxs-lookup"><span data-stu-id="e017b-108">If the item won't fit into an existing container, the system creates a new container and continues until it has finished packing the whole order.</span></span>

    <span data-ttu-id="e017b-109">Por ejemplo, *n* artículos pedidos requieren contenedorización.</span><span class="sxs-lookup"><span data-stu-id="e017b-109">For example, *n* ordered items require containerization.</span></span> <span data-ttu-id="e017b-110">En el peor de los casos, cada vez que el sistema procesa un artículo que no cabe en ningún contenedor existente, hará un total de (\[(*n* – 1) × (*n* + 1)\] ÷ 2) comprobaciones para evaluar si el artículo encaja en los contenedores existentes.</span><span class="sxs-lookup"><span data-stu-id="e017b-110">In the worst case, every time that the system processes an item that doesn't fit into any existing container, it will do a total of (\[(*n* – 1) × (*n* + 1)\] ÷ 2) checks to evaluate whether the item fits into the existing containers.</span></span>

- <span data-ttu-id="e017b-111">**Embalar solo en el contenedor actual**: el sistema debe comprobar solo el contenedor creado más recientemente para asegurarse de que el artículo cabrá en él.</span><span class="sxs-lookup"><span data-stu-id="e017b-111">**Pack into current container only** – The system must check only the most recently created container to make sure that the item will fit into it.</span></span> <span data-ttu-id="e017b-112">Durante el embalaje, el sistema verifica cada artículo para determinar si cabe en el contenedor creado más recientemente.</span><span class="sxs-lookup"><span data-stu-id="e017b-112">During packing, the system checks each item to determine whether it will fit into the most recently created container.</span></span> <span data-ttu-id="e017b-113">Si el artículo no cabe en ese contenedor, el sistema crea un contenedor nuevo y continúa hasta que haya terminado de empaquetar todo el pedido.</span><span class="sxs-lookup"><span data-stu-id="e017b-113">If the item won't fit into that container, the system creates a new container and continues until it has finished packing the whole order.</span></span>

    <span data-ttu-id="e017b-114">Por ejemplo, *n* artículos pedidos requieren contenedorización.</span><span class="sxs-lookup"><span data-stu-id="e017b-114">For example, *n* ordered items require containerization.</span></span> <span data-ttu-id="e017b-115">En el peor de los casos, el sistema hará un total de (*n* – 1) controles para evaluar si el artículo cabe en los contenedores.</span><span class="sxs-lookup"><span data-stu-id="e017b-115">In the worst case, the system will do a total of (*n* – 1) checks to evaluate whether the item fits into the containers.</span></span>

## <a name="example-of-the-flow-for-container-packing-strategies"></a><span data-ttu-id="e017b-116">Ejemplo de flujo para estrategias de empaque de contenedores</span><span class="sxs-lookup"><span data-stu-id="e017b-116">Example of the flow for container packing strategies</span></span>

<span data-ttu-id="e017b-117">Debe configurar los siguientes elementos para la creación de contenedores.</span><span class="sxs-lookup"><span data-stu-id="e017b-117">You set up the following items for containerization.</span></span>

| <span data-ttu-id="e017b-118">Artículo</span><span class="sxs-lookup"><span data-stu-id="e017b-118">Item</span></span> | <span data-ttu-id="e017b-119">Dimensiones físicas (ancho x profundidad x altura)</span><span class="sxs-lookup"><span data-stu-id="e017b-119">Physical dimensions (width × depth × height)</span></span> | <span data-ttu-id="e017b-120">Importancia</span><span class="sxs-lookup"><span data-stu-id="e017b-120">Weight</span></span> |
|---|---|---|
| <span data-ttu-id="e017b-121">Cable HDMI 6'</span><span class="sxs-lookup"><span data-stu-id="e017b-121">HDMI Cable 6'</span></span> | <span data-ttu-id="e017b-122">1 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="e017b-122">1 × 1 × 1</span></span> | <span data-ttu-id="e017b-123">1</span><span class="sxs-lookup"><span data-stu-id="e017b-123">1</span></span> |
| <span data-ttu-id="e017b-124">Cable HDMI 12'</span><span class="sxs-lookup"><span data-stu-id="e017b-124">HDMI Cable 12'</span></span> | <span data-ttu-id="e017b-125">2 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="e017b-125">2 × 1 × 1</span></span> | <span data-ttu-id="e017b-126">1</span><span class="sxs-lookup"><span data-stu-id="e017b-126">1</span></span> |
| <span data-ttu-id="e017b-127">Cable HDMI 18'</span><span class="sxs-lookup"><span data-stu-id="e017b-127">HDMI Cable 18'</span></span> | <span data-ttu-id="e017b-128">3 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="e017b-128">3 × 1 × 1</span></span> | <span data-ttu-id="e017b-129">2</span><span class="sxs-lookup"><span data-stu-id="e017b-129">2</span></span> |

<span data-ttu-id="e017b-130">También configura la siguiente caja que se utilizará para el embalaje.</span><span class="sxs-lookup"><span data-stu-id="e017b-130">You also set up the following box that will be used for packaging.</span></span>

| <span data-ttu-id="e017b-131">Contenedor</span><span class="sxs-lookup"><span data-stu-id="e017b-131">Container</span></span> | <span data-ttu-id="e017b-132">Dimensiones físicas (largo x ancho x altura)</span><span class="sxs-lookup"><span data-stu-id="e017b-132">Physical dimensions (length × width × height)</span></span> | <span data-ttu-id="e017b-133">Importancia</span><span class="sxs-lookup"><span data-stu-id="e017b-133">Weight</span></span> | <span data-ttu-id="e017b-134">Volumen</span><span class="sxs-lookup"><span data-stu-id="e017b-134">Volume</span></span> |
|---|---|---|---|
| <span data-ttu-id="e017b-135">Caja mediana</span><span class="sxs-lookup"><span data-stu-id="e017b-135">Medium Box</span></span> | <span data-ttu-id="e017b-136">6 × 3 × 2</span><span class="sxs-lookup"><span data-stu-id="e017b-136">6 × 3 × 2</span></span> | <span data-ttu-id="e017b-137">10</span><span class="sxs-lookup"><span data-stu-id="e017b-137">10</span></span> | <span data-ttu-id="e017b-138">100</span><span class="sxs-lookup"><span data-stu-id="e017b-138">100</span></span> |

<span data-ttu-id="e017b-139">Finalmente, configura un pedido que tiene los siguientes productos y cantidades.</span><span class="sxs-lookup"><span data-stu-id="e017b-139">Finally, you set up an order that has the following products and quantities.</span></span>

| <span data-ttu-id="e017b-140">Línea de pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="e017b-140">Sales order line</span></span> | <span data-ttu-id="e017b-141">Cantidad</span><span class="sxs-lookup"><span data-stu-id="e017b-141">Quantity</span></span> |
|---|---|
| <span data-ttu-id="e017b-142">Cable HDMI 12'</span><span class="sxs-lookup"><span data-stu-id="e017b-142">HDMI Cable 12'</span></span> | <span data-ttu-id="e017b-143">9</span><span class="sxs-lookup"><span data-stu-id="e017b-143">9</span></span> |
| <span data-ttu-id="e017b-144">Cable HDMI 18'</span><span class="sxs-lookup"><span data-stu-id="e017b-144">HDMI Cable 18'</span></span> | <span data-ttu-id="e017b-145">8</span><span class="sxs-lookup"><span data-stu-id="e017b-145">8</span></span> |
| <span data-ttu-id="e017b-146">Cable HDMI 6'</span><span class="sxs-lookup"><span data-stu-id="e017b-146">HDMI Cable 6'</span></span> | <span data-ttu-id="e017b-147">13</span><span class="sxs-lookup"><span data-stu-id="e017b-147">13</span></span> |

<span data-ttu-id="e017b-148">La siguiente tabla resume cómo funciona la contenedorización cuando usa la estrategia *Empaque en todos los contenedores abiertos* y cuando utilizas la estrategia *Empaquetar solo en el contenedor actual*.</span><span class="sxs-lookup"><span data-stu-id="e017b-148">The following table summarizes how containerization works when you use the *Pack into all open containers* strategy and when you use the *Pack into current container only* strategy.</span></span>

| <span data-ttu-id="e017b-149">Embalar en todos los contenedores abiertos</span><span class="sxs-lookup"><span data-stu-id="e017b-149">Pack into all open containers</span></span> | <span data-ttu-id="e017b-150">Empacar en contenedor actual</span><span class="sxs-lookup"><span data-stu-id="e017b-150">Pack into current container</span></span> |
|---|---|
| <p><span data-ttu-id="e017b-151">Cable HDMI 12':</span><span class="sxs-lookup"><span data-stu-id="e017b-151">HDMI Cable 12':</span></span></p><ol><li><span data-ttu-id="e017b-152">Crear un nuevo tipo de contenedor, CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e017b-152">Create a new container, CONT0001.</span></span></li><li><span data-ttu-id="e017b-153">Ponga 9 ea en el recipiente CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e017b-153">Put 9 ea into container CONT0001.</span></span></li></ol> | <p><span data-ttu-id="e017b-154">Cable HDMI 12':</span><span class="sxs-lookup"><span data-stu-id="e017b-154">HDMI Cable 12':</span></span></p><ol><li><span data-ttu-id="e017b-155">Crear un nuevo tipo de contenedor, CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e017b-155">Create a new container, CONT0001.</span></span></li><li><span data-ttu-id="e017b-156">Ponga 9 ea en el recipiente CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e017b-156">Put 9 ea into container CONT0001.</span></span></li></ol> |
| <p><span data-ttu-id="e017b-157">Cable HDMI 18':</span><span class="sxs-lookup"><span data-stu-id="e017b-157">HDMI Cable 18':</span></span></p><ol><li><span data-ttu-id="e017b-158">Compruebe si el artículo puede caber en el contenedor CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e017b-158">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="e017b-159">Crear un nuevo tipo de contenedor, CONT0002.</span><span class="sxs-lookup"><span data-stu-id="e017b-159">Create a new container, CONT0002.</span></span></li><li><span data-ttu-id="e017b-160">Ponga 5 ea en el recipiente CONT0002.</span><span class="sxs-lookup"><span data-stu-id="e017b-160">Put 5 ea into container CONT0002.</span></span></li><li><span data-ttu-id="e017b-161">Crear un nuevo tipo de contenedor, CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e017b-161">Create a new container, CONT0003.</span></span></li><li><span data-ttu-id="e017b-162">Ponga 3 ea en el recipiente CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e017b-162">Put 3 ea into container CONT0003.</span></span></li></ol> | <p><span data-ttu-id="e017b-163">Cable HDMI 18':</span><span class="sxs-lookup"><span data-stu-id="e017b-163">HDMI Cable 18':</span></span></p><ol><li><span data-ttu-id="e017b-164">Compruebe si el artículo puede caber en el contenedor CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e017b-164">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="e017b-165">Crear un nuevo tipo de contenedor, CONT0002.</span><span class="sxs-lookup"><span data-stu-id="e017b-165">Create a new container, CONT0002.</span></span></li><li><span data-ttu-id="e017b-166">Ponga 5 ea en el recipiente CONT0002.</span><span class="sxs-lookup"><span data-stu-id="e017b-166">Put 5 ea into container CONT0002.</span></span></li><li><span data-ttu-id="e017b-167">Crear un nuevo tipo de contenedor, CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e017b-167">Create a new container, CONT0003.</span></span></li><li><span data-ttu-id="e017b-168">Ponga 3 ea en el recipiente CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e017b-168">Put 3 ea into container CONT0003.</span></span></li></ol> |
| <p><span data-ttu-id="e017b-169">Cable HDMI 6':</span><span class="sxs-lookup"><span data-stu-id="e017b-169">HDMI Cable 6':</span></span></p><ol><li><span data-ttu-id="e017b-170">Compruebe si el artículo puede caber en el contenedor CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e017b-170">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="e017b-171">Ponga 1 ea en el recipiente CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e017b-171">Put 1 ea into container CONT0001.</span></span></li><li><span data-ttu-id="e017b-172">Compruebe si el artículo puede caber en el contenedor CONT0002.</span><span class="sxs-lookup"><span data-stu-id="e017b-172">Check whether the item can fit into container CONT0002.</span></span></li><li><span data-ttu-id="e017b-173">Compruebe si el artículo puede caber en el contenedor CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e017b-173">Check whether the item can fit into container CONT0003.</span></span></li><li><span data-ttu-id="e017b-174">Ponga 4 ea en el recipiente CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e017b-174">Put 4 ea into container CONT0003.</span></span></li><li><span data-ttu-id="e017b-175">Crear un nuevo tipo de contenedor, CONT0004.</span><span class="sxs-lookup"><span data-stu-id="e017b-175">Create a new container, CONT0004.</span></span></li><li><span data-ttu-id="e017b-176">Ponga 8 ea en el recipiente CONT0004.</span><span class="sxs-lookup"><span data-stu-id="e017b-176">Put 8 ea into container CONT0004.</span></span></li></ol> | <p><span data-ttu-id="e017b-177">Cable HDMI 6':</span><span class="sxs-lookup"><span data-stu-id="e017b-177">HDMI Cable 6':</span></span></p><ol><li><span data-ttu-id="e017b-178">Compruebe si el artículo puede caber en el contenedor CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e017b-178">Check whether the item can fit into container CONT0003.</span></span></li><li><span data-ttu-id="e017b-179">Ponga 4 ea en el recipiente CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e017b-179">Put 4 ea into container CONT0003.</span></span></li><li><span data-ttu-id="e017b-180">Crear un nuevo tipo de contenedor, CONT0004.</span><span class="sxs-lookup"><span data-stu-id="e017b-180">Create a new container, CONT0004.</span></span></li><li><span data-ttu-id="e017b-181">Ponga 9 ea en el recipiente CONT0004.</span><span class="sxs-lookup"><span data-stu-id="e017b-181">Put 9 ea into container CONT0004.</span></span></li></ol> |

## <a name="example-scenario-pack-single-orders-per-container"></a><span data-ttu-id="e017b-182">Escenario de ejemplo: empacar pedidos individuales por contenedor</span><span class="sxs-lookup"><span data-stu-id="e017b-182">Example scenario: Pack single orders per container</span></span>

<span data-ttu-id="e017b-183">Esta sección presenta un escenario en el que el sistema está configurado para consolidar varios pedidos en un solo envío.</span><span class="sxs-lookup"><span data-stu-id="e017b-183">This section presents a scenario where the system is set up to consolidate multiple orders into one shipment.</span></span> <span data-ttu-id="e017b-184">Por lo tanto, la contenedorización se realizará a partir del pedido de venta para garantizar que cada pedido que contenga varios productos se empaque en su propio contenedor.</span><span class="sxs-lookup"><span data-stu-id="e017b-184">Therefore, containerization will be done from the sales order to ensure that every order that contains multiple products is packed into its own container.</span></span>

<span data-ttu-id="e017b-185">Esta funcionalidad le permite manejar escenarios en los que debe empaquetar solo un pedido de venta en cada contenedor, de modo que el centro de distribución pueda cruzar contenedores completos entre tiendas minoristas.</span><span class="sxs-lookup"><span data-stu-id="e017b-185">This functionality lets you handle scenarios where you must pack only one sales order into each container, so that the distribution center can cross-dock full containers between retail stores.</span></span> <span data-ttu-id="e017b-186">Además de los escenarios minoristas (pedido por tienda minorista y envío a un centro de distribución para cross-docking), esta técnica también se usa comúnmente en cadenas de suministro ajustadas (pedido de venta por línea de producción justo a tiempo).</span><span class="sxs-lookup"><span data-stu-id="e017b-186">In addition to the retail scenarios (order per retail store and shipping to a distribution center for cross-docking) this technique is also commonly used in lean supply chains (sales order per just-in-time production line).</span></span>

<span data-ttu-id="e017b-187">Este escenario muestra cómo puede disminuir el número de contenedores que se evalúan durante el embalaje mediante el uso de la estrategia *Empaquetar solo en el contenedor actual* de contenedorización.</span><span class="sxs-lookup"><span data-stu-id="e017b-187">This scenario shows how you can decrease the number of containers that are evaluated during packing by using the *Pack into current container only* strategy for containerization.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e017b-188">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e017b-188">Prerequisites</span></span>

#### <a name="turn-on-the-consolidate-shipments-feature-in-your-system"></a><span data-ttu-id="e017b-189">Active la función Consolidar envíos en su sistema</span><span class="sxs-lookup"><span data-stu-id="e017b-189">Turn on the Consolidate shipments feature in your system</span></span>

<span data-ttu-id="e017b-190">Este escenario usa la característica *Consolidar envíos*.</span><span class="sxs-lookup"><span data-stu-id="e017b-190">This scenario uses the *Consolidate shipments* feature.</span></span> <span data-ttu-id="e017b-191">Si esa función aún no está disponible en su sistema, debe activarla usando [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e017b-191">If that feature isn't already available in your system, you must turn it on by using [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

#### <a name="make-demo-data-available"></a><span data-ttu-id="e017b-192">Hacer que los datos de demostración estén disponibles</span><span class="sxs-lookup"><span data-stu-id="e017b-192">Make demo data available</span></span>

<span data-ttu-id="e017b-193">Este escenario de este tema hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e017b-193">This scenario references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="e017b-194">Si desea utilizar los valores que se proporcionan aquí mientras realiza los ejercicios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica en **USMF** antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="e017b-194">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

### <a name="inspect-or-create-container-types"></a><span data-ttu-id="e017b-195">Inspeccionar o crear tipos de contenedores</span><span class="sxs-lookup"><span data-stu-id="e017b-195">Inspect or create container types</span></span>

<span data-ttu-id="e017b-196">Para inspeccionar sus tipos de contenedores, o para crear nuevos tipos de contenedores si son necesarios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e017b-196">To inspect your container types, or to create new container types if they are required, follow these steps.</span></span>

1. <span data-ttu-id="e017b-197">Vaya a **Warehouse Management** \> **Configurar** \> **Contenedores** \> **Tipos de contenedor**.</span><span class="sxs-lookup"><span data-stu-id="e017b-197">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container types**.</span></span>
1. <span data-ttu-id="e017b-198">Asegúrese de que cada uno de los siguientes tipos de contenedores esté disponible en sus datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="e017b-198">Make sure that each of the following container types is available in your demo data.</span></span> <span data-ttu-id="e017b-199">Edite o cree tipos de contenedores según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e017b-199">Edit or create container types as required.</span></span>

    - <span data-ttu-id="e017b-200">Tipo de contenedor 1:</span><span class="sxs-lookup"><span data-stu-id="e017b-200">Container type 1:</span></span>

        - <span data-ttu-id="e017b-201">**Código de tipo de contenedor:** *Caja grande*</span><span class="sxs-lookup"><span data-stu-id="e017b-201">**Container type code:** *Box-Large*</span></span>
        - <span data-ttu-id="e017b-202">**Descripción:** *Caja grande*</span><span class="sxs-lookup"><span data-stu-id="e017b-202">**Description:** *Large Box*</span></span>
        - <span data-ttu-id="e017b-203">**Peso neto máximo:** *100*</span><span class="sxs-lookup"><span data-stu-id="e017b-203">**Maximum net weight:** *100*</span></span>
        - <span data-ttu-id="e017b-204">**Volumen:** *400*</span><span class="sxs-lookup"><span data-stu-id="e017b-204">**Volume:** *400*</span></span>
        - <span data-ttu-id="e017b-205">**Longitud:** *4*</span><span class="sxs-lookup"><span data-stu-id="e017b-205">**Length:** *4*</span></span>
        - <span data-ttu-id="e017b-206">**Anchura:** *10*</span><span class="sxs-lookup"><span data-stu-id="e017b-206">**Width:** *10*</span></span>
        - <span data-ttu-id="e017b-207">**Altura:** *10*</span><span class="sxs-lookup"><span data-stu-id="e017b-207">**Height:** *10*</span></span>

    - <span data-ttu-id="e017b-208">Tipo de contenedor 2:</span><span class="sxs-lookup"><span data-stu-id="e017b-208">Container type 2:</span></span>

        - <span data-ttu-id="e017b-209">**Código de tipo de contenedor:** *Caja mediana*</span><span class="sxs-lookup"><span data-stu-id="e017b-209">**Container type code:** *Box-Medium*</span></span>
        - <span data-ttu-id="e017b-210">**Descripción:** *Caja mediana*</span><span class="sxs-lookup"><span data-stu-id="e017b-210">**Description:** *Medium Box*</span></span>
        - <span data-ttu-id="e017b-211">**Peso neto máximo:** *50*</span><span class="sxs-lookup"><span data-stu-id="e017b-211">**Maximum net weight:** *50*</span></span>
        - <span data-ttu-id="e017b-212">**Volumen:** *200*</span><span class="sxs-lookup"><span data-stu-id="e017b-212">**Volume:** *200*</span></span>
        - <span data-ttu-id="e017b-213">**Longitud:** *2*</span><span class="sxs-lookup"><span data-stu-id="e017b-213">**Length:** *2*</span></span>
        - <span data-ttu-id="e017b-214">**Anchura:** *10*</span><span class="sxs-lookup"><span data-stu-id="e017b-214">**Width:** *10*</span></span>
        - <span data-ttu-id="e017b-215">**Altura:** *10*</span><span class="sxs-lookup"><span data-stu-id="e017b-215">**Height:** *10*</span></span>

    - <span data-ttu-id="e017b-216">Tipo de contenedor 3:</span><span class="sxs-lookup"><span data-stu-id="e017b-216">Container type 3:</span></span>

        - <span data-ttu-id="e017b-217">**Código de tipo de contenedor:** *Caja pequeña*</span><span class="sxs-lookup"><span data-stu-id="e017b-217">**Container type code:** *Box-Small*</span></span>
        - <span data-ttu-id="e017b-218">**Descripción:** *Caja pequeña*</span><span class="sxs-lookup"><span data-stu-id="e017b-218">**Description:** *Small Box*</span></span>
        - <span data-ttu-id="e017b-219">**Peso neto máximo:** *20*</span><span class="sxs-lookup"><span data-stu-id="e017b-219">**Maximum net weight:** *20*</span></span>
        - <span data-ttu-id="e017b-220">**Volumen:** *100*</span><span class="sxs-lookup"><span data-stu-id="e017b-220">**Volume:** *100*</span></span>
        - <span data-ttu-id="e017b-221">**Longitud:** *1*</span><span class="sxs-lookup"><span data-stu-id="e017b-221">**Length:** *1*</span></span>
        - <span data-ttu-id="e017b-222">**Anchura:** *10*</span><span class="sxs-lookup"><span data-stu-id="e017b-222">**Width:** *10*</span></span>
        - <span data-ttu-id="e017b-223">**Altura:** *10*</span><span class="sxs-lookup"><span data-stu-id="e017b-223">**Height:** *10*</span></span>

### <a name="inspect-or-create-container-groups"></a><span data-ttu-id="e017b-224">Inspeccionar o crear grupos de contenedores</span><span class="sxs-lookup"><span data-stu-id="e017b-224">Inspect or create container groups</span></span>

<span data-ttu-id="e017b-225">Para inspeccionar sus grupos de contenedores, o para crear nuevos grupos de contenedores si son necesarios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e017b-225">To inspect your container groups, or to create new container groups if they are required, follow these steps.</span></span>

1. <span data-ttu-id="e017b-226">Vaya a **Administración de almacenes** \> **Configurar** \> **Contenedores** \> **Grupos de contenedores**.</span><span class="sxs-lookup"><span data-stu-id="e017b-226">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container groups**.</span></span>
1. <span data-ttu-id="e017b-227">Asegúrese de que los siguientes grupos de contenedores esté disponible en sus datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="e017b-227">Make sure that the following container group is available in your demo data.</span></span> <span data-ttu-id="e017b-228">Si no está disponible, seleccione **Nuevo** para crearlo.</span><span class="sxs-lookup"><span data-stu-id="e017b-228">If it isn't available, select **New** to create it.</span></span>

    - <span data-ttu-id="e017b-229">**ID de grupo de contenedores:** *Cajas*</span><span class="sxs-lookup"><span data-stu-id="e017b-229">**Container group ID:** *Boxes*</span></span>
    - <span data-ttu-id="e017b-230">**Descripción:** *Tamaños de caja*</span><span class="sxs-lookup"><span data-stu-id="e017b-230">**Description:** *Box sizes*</span></span>

1. <span data-ttu-id="e017b-231">En la ficha desplegable **Detalles** del grupo de contenedores *Cajas*, asegúrese de que existan las siguientes líneas.</span><span class="sxs-lookup"><span data-stu-id="e017b-231">On the **Details** FastTab for the *Boxes* container group, make sure that the following lines exist.</span></span> <span data-ttu-id="e017b-232">Si no es así, seleccione **Nuevo** para agregarlos.</span><span class="sxs-lookup"><span data-stu-id="e017b-232">If they don't, select **New** to add them.</span></span>

    - <span data-ttu-id="e017b-233">Línea 1:</span><span class="sxs-lookup"><span data-stu-id="e017b-233">Line 1:</span></span>

        - <span data-ttu-id="e017b-234">**Número de secuencia:** *1*</span><span class="sxs-lookup"><span data-stu-id="e017b-234">**Sequence number:** *1*</span></span>
        - <span data-ttu-id="e017b-235">**Tipo de contenedor:** *Caja grande*</span><span class="sxs-lookup"><span data-stu-id="e017b-235">**Container type:** *Box-Large*</span></span>
        - <span data-ttu-id="e017b-236">**Porcentaje de utilización de contenedor:** *100*</span><span class="sxs-lookup"><span data-stu-id="e017b-236">**Container utilization percentage:** *100*</span></span>

    - <span data-ttu-id="e017b-237">Línea 2:</span><span class="sxs-lookup"><span data-stu-id="e017b-237">Line 2:</span></span>

        - <span data-ttu-id="e017b-238">**Número de secuencia:** *2*</span><span class="sxs-lookup"><span data-stu-id="e017b-238">**Sequence number:** *2*</span></span>
        - <span data-ttu-id="e017b-239">**Tipo de contenedor:** *Caja mediana*</span><span class="sxs-lookup"><span data-stu-id="e017b-239">**Container type:** *Box-Medium*</span></span>
        - <span data-ttu-id="e017b-240">**Porcentaje de utilización de contenedor:** *100*</span><span class="sxs-lookup"><span data-stu-id="e017b-240">**Container utilization percentage:** *100*</span></span>

    - <span data-ttu-id="e017b-241">Línea 3:</span><span class="sxs-lookup"><span data-stu-id="e017b-241">Line 3:</span></span>

        - <span data-ttu-id="e017b-242">**Número de secuencia:** *3*</span><span class="sxs-lookup"><span data-stu-id="e017b-242">**Sequence number:** *3*</span></span>
        - <span data-ttu-id="e017b-243">**Tipo de contenedor:** *Caja pequeña*</span><span class="sxs-lookup"><span data-stu-id="e017b-243">**Container type:** *Box-Small*</span></span>
        - <span data-ttu-id="e017b-244">**Porcentaje de utilización de contenedor:** *100*</span><span class="sxs-lookup"><span data-stu-id="e017b-244">**Container utilization percentage:** *100*</span></span>

### <a name="create-a-new-container-build-template"></a><span data-ttu-id="e017b-245">Cree una nueva plantilla de creación de contenedores</span><span class="sxs-lookup"><span data-stu-id="e017b-245">Create a new container build template</span></span>

<span data-ttu-id="e017b-246">Para crear una nueva plantilla de creación de contenedores, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e017b-246">To create a new container build template, follow these steps.</span></span>

1. <span data-ttu-id="e017b-247">Vaya a **Administración de almacenes** \> **Configurar** \> **Contenedores** \> **Plantilla de creación de contenedores**.</span><span class="sxs-lookup"><span data-stu-id="e017b-247">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container build template**.</span></span>
1. <span data-ttu-id="e017b-248">Seleccione **Nuevo** para crear una plantilla de construcción de contenedor que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="e017b-248">Select **New** to create a container build template that has the following settings:</span></span>

    - <span data-ttu-id="e017b-249">**Número de secuencia:** *1*</span><span class="sxs-lookup"><span data-stu-id="e017b-249">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="e017b-250">**ID de plantilla de contenedor:** *Caja*</span><span class="sxs-lookup"><span data-stu-id="e017b-250">**Container template ID:** *Box*</span></span>
    - <span data-ttu-id="e017b-251">**ID de grupo de contenedores:** *Cajas*</span><span class="sxs-lookup"><span data-stu-id="e017b-251">**Container group ID:** *Boxes*</span></span>
    - <span data-ttu-id="e017b-252">**Tipos de consultas base:** *Línea de asignación de ventas*</span><span class="sxs-lookup"><span data-stu-id="e017b-252">**Base query types:** *Sales allocation line*</span></span>
    - <span data-ttu-id="e017b-253">**Código de paso de oleada:** *234*</span><span class="sxs-lookup"><span data-stu-id="e017b-253">**Wave step code:** *234*</span></span>
    - <span data-ttu-id="e017b-254">**Permitir selecciones divididas:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="e017b-254">**Allow split picks:** *Yes*</span></span>
    - <span data-ttu-id="e017b-255">**Estrategia de embalaje de contenedores:** *Empaquetar solo en el contenedor actual*</span><span class="sxs-lookup"><span data-stu-id="e017b-255">**Container packing strategy:** *Pack into current container only*</span></span>
    - <span data-ttu-id="e017b-256">**Embalaje por unidad directiva:** *No*</span><span class="sxs-lookup"><span data-stu-id="e017b-256">**Pack by directive unit:** *No*</span></span>

1. <span data-ttu-id="e017b-257">Mientras la fila de la nueva plantilla aún está seleccionada, seleccione **Editar consulta** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="e017b-257">While the row for the new template is still selected, select **Edit query** on the Action Pane.</span></span>
1. <span data-ttu-id="e017b-258">Aparece un cuadro de diálogo de editor de consultas estándar.</span><span class="sxs-lookup"><span data-stu-id="e017b-258">A standard query editor dialog box appears.</span></span> <span data-ttu-id="e017b-259">En la pestaña **Ordenación**, seleccione **Añadir** para agregar una fila que tenga la siguiente configuración a la cuadrícula:</span><span class="sxs-lookup"><span data-stu-id="e017b-259">On the **Sorting** tab, select **Add** to add a row that has the following settings:</span></span>

    - <span data-ttu-id="e017b-260">**Tabla:** *Transacciones laborales temporales*</span><span class="sxs-lookup"><span data-stu-id="e017b-260">**Table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="e017b-261">**Tabla derivada:** *Transacciones laborales temporales*</span><span class="sxs-lookup"><span data-stu-id="e017b-261">**Derived table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="e017b-262">**Campo:** *Número de pedido*</span><span class="sxs-lookup"><span data-stu-id="e017b-262">**Field:** *Order number*</span></span>
    - <span data-ttu-id="e017b-263">**Dirección de búsqueda:** *Ascendente*</span><span class="sxs-lookup"><span data-stu-id="e017b-263">**Search direction:** *Ascending*</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e017b-264">Para evitar pasar por encima de todos los demás recipientes abiertos y acelerar el proceso comprobando un recipiente a la vez, utilice la estrategia *Empaquetar solo en el contenedor actual* además de ordenar por número de orden.</span><span class="sxs-lookup"><span data-stu-id="e017b-264">To avoid cycling over all the other open containers, and to speed up the process by checking one container at a time, use the *Pack into current container only* strategy in addition to sorting by order number.</span></span> <span data-ttu-id="e017b-265">Esta combinación funcionará como un descanso en una plantilla de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e017b-265">This combination will work like a work break on a work template.</span></span>

1. <span data-ttu-id="e017b-266">Seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="e017b-266">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="e017b-267">Mientras la fila de la nueva plantilla aún está seleccionada, seleccione **Restricciones de mezcla de contenedores** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="e017b-267">While the row for the new template is still selected, select **Container mixing constraints** on the Action Pane.</span></span>

    <span data-ttu-id="e017b-268">Ahora agregará una restricción que coloca los artículos de un solo pedido en un solo contenedor.</span><span class="sxs-lookup"><span data-stu-id="e017b-268">You will now add a constraint that puts items from a single order into a single container.</span></span> <span data-ttu-id="e017b-269">Los artículos de cualquier otro pedido se colocarán en un contenedor separado.</span><span class="sxs-lookup"><span data-stu-id="e017b-269">Items from any other order will be put into a separate container.</span></span>

1. <span data-ttu-id="e017b-270">Seleccione **Nuevo** para crear una restricción de mezcla que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="e017b-270">Select **New** to create a mixing constraint that has the following settings:</span></span>

    - <span data-ttu-id="e017b-271">**Tabla:** *Pedidos de ventas*</span><span class="sxs-lookup"><span data-stu-id="e017b-271">**Table:** *Sales orders*</span></span>
    - <span data-ttu-id="e017b-272">**Seleccionar campo:** *SalesId* (el campo aparecerá como *Órdenes de venta* en la cuadrícula).</span><span class="sxs-lookup"><span data-stu-id="e017b-272">**Field select:** *SalesId* (The field will appear as *Sales order* in the grid.)</span></span>

1. <span data-ttu-id="e017b-273">Seleccione **Aceptar** para agregar la restricción.</span><span class="sxs-lookup"><span data-stu-id="e017b-273">Select **OK** to add the constraint.</span></span>
1. <span data-ttu-id="e017b-274">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e017b-274">Close the page.</span></span>

### <a name="set-up-a-wave-template-for-containerization"></a><span data-ttu-id="e017b-275">Configurar una plantilla de oleada para la creación de contenedores</span><span class="sxs-lookup"><span data-stu-id="e017b-275">Set up a wave template for containerization</span></span>

<span data-ttu-id="e017b-276">Para configurar una plantilla de oleada, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e017b-276">To set up a wave template, follow these steps.</span></span>

1. <span data-ttu-id="e017b-277">Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="e017b-277">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="e017b-278">En el panel de lista, establezca el campo **Tipo de plantilla de oleada** en *Envío*.</span><span class="sxs-lookup"><span data-stu-id="e017b-278">In the list pane, set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="e017b-279">Seleccione la plantilla **63 Containerización** en la lista.</span><span class="sxs-lookup"><span data-stu-id="e017b-279">Select the **63 Containerization** template in the list.</span></span>
1. <span data-ttu-id="e017b-280">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e017b-280">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="e017b-281">Sobre la ficha desplegable **Métodos**, en la columna **Métodos seleccionados**, busque la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="e017b-281">On the **Methods** FastTab, in the **Selected methods** column, find the following line:</span></span>

    - <span data-ttu-id="e017b-282">**Nombre del método:** *contenedorización*</span><span class="sxs-lookup"><span data-stu-id="e017b-282">**Method name:** *containerization*</span></span>
    - <span data-ttu-id="e017b-283">**Nombre**: *Creación de contenedores*</span><span class="sxs-lookup"><span data-stu-id="e017b-283">**Name:** *Containerization*</span></span>

1. <span data-ttu-id="e017b-284">Establezca el campo **Código de paso de oleada** para la línea en *234*.</span><span class="sxs-lookup"><span data-stu-id="e017b-284">Set the **Wave step code** field for the line to *234*.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="e017b-285">Configurar una plantilla de trabajo</span><span class="sxs-lookup"><span data-stu-id="e017b-285">Set up a work template</span></span>

<span data-ttu-id="e017b-286">Para configurar una plantilla de trabajo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e017b-286">To set up a work template, follow these steps.</span></span>

1. <span data-ttu-id="e017b-287">Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="e017b-287">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="e017b-288">Establezca el campo **Tipo de orden de trabajo** en *Pedidos de ventas*.</span><span class="sxs-lookup"><span data-stu-id="e017b-288">Set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="e017b-289">En la cuadrícula **Visión general**, busque y seleccione la plantilla de trabajo que debe usarse para embalar pedidos individuales por contenedor.</span><span class="sxs-lookup"><span data-stu-id="e017b-289">In the **Overview** grid, find and select the work template that should be used for packing single orders per container.</span></span> <span data-ttu-id="e017b-290">Para este escenario, seleccione la plantilla **63 Recoger a contenedor**.</span><span class="sxs-lookup"><span data-stu-id="e017b-290">For this scenario, select the **63 Pick to container** template.</span></span>
1. <span data-ttu-id="e017b-291">En el panel Acciones, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="e017b-291">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="e017b-292">Aparece un cuadro de diálogo de editor de consultas estándar.</span><span class="sxs-lookup"><span data-stu-id="e017b-292">A standard query editor dialog box appears.</span></span> <span data-ttu-id="e017b-293">En la pestaña **Ordenación**, agregue las líneas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e017b-293">On the **Sorting** tab, add the following lines:</span></span>

    - <span data-ttu-id="e017b-294">Línea 1:</span><span class="sxs-lookup"><span data-stu-id="e017b-294">Line 1:</span></span>

        - <span data-ttu-id="e017b-295">**Tabla:** *Transacciones laborales temporales*</span><span class="sxs-lookup"><span data-stu-id="e017b-295">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="e017b-296">**Tabla derivada:** *Transacciones laborales temporales*</span><span class="sxs-lookup"><span data-stu-id="e017b-296">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="e017b-297">**Campo:** *Identificación del envío*</span><span class="sxs-lookup"><span data-stu-id="e017b-297">**Field:** *Shipment ID*</span></span>
        - <span data-ttu-id="e017b-298">**Dirección de búsqueda:** *Ascendente*</span><span class="sxs-lookup"><span data-stu-id="e017b-298">**Search direction:** *Ascending*</span></span>

    - <span data-ttu-id="e017b-299">Línea 2:</span><span class="sxs-lookup"><span data-stu-id="e017b-299">Line 2:</span></span>

        - <span data-ttu-id="e017b-300">**Tabla:** *Transacciones laborales temporales*</span><span class="sxs-lookup"><span data-stu-id="e017b-300">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="e017b-301">**Tabla derivada:** *Transacciones laborales temporales*</span><span class="sxs-lookup"><span data-stu-id="e017b-301">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="e017b-302">**Campo:** *Número de pedido*</span><span class="sxs-lookup"><span data-stu-id="e017b-302">**Field:** *Order number*</span></span>
        - <span data-ttu-id="e017b-303">**Dirección de búsqueda:** *Ascendente*</span><span class="sxs-lookup"><span data-stu-id="e017b-303">**Search direction:** *Ascending*</span></span>

    - <span data-ttu-id="e017b-304">Línea 3:</span><span class="sxs-lookup"><span data-stu-id="e017b-304">Line 3:</span></span>

        - <span data-ttu-id="e017b-305">**Tabla:** *Transacciones laborales temporales*</span><span class="sxs-lookup"><span data-stu-id="e017b-305">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="e017b-306">**Tabla derivada:** *Transacciones laborales temporales*</span><span class="sxs-lookup"><span data-stu-id="e017b-306">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="e017b-307">**Campo:** *ID de contenedor*</span><span class="sxs-lookup"><span data-stu-id="e017b-307">**Field:** *Container ID*</span></span>
        - <span data-ttu-id="e017b-308">**Dirección de búsqueda:** *Ascendente*</span><span class="sxs-lookup"><span data-stu-id="e017b-308">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="e017b-309">Seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="e017b-309">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="e017b-310">Recibirá el siguiente mensaje: "La agrupación se restablecerá, ¿continuar?"</span><span class="sxs-lookup"><span data-stu-id="e017b-310">You receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="e017b-311">Seleccione **Sí** para continuar.</span><span class="sxs-lookup"><span data-stu-id="e017b-311">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="e017b-312">Mientras que la plantilla **63 Recoger en contenedor** aún está seleccionada, seleccione **Descansos en el encabezado** en el Panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="e017b-312">While the **63 Pick to container** template is still selected, select **Work header breaks** on the Action Pane.</span></span>

    <span data-ttu-id="e017b-313">Ahora aplicará la configuración para dividir el trabajo de modo que cada contenedor de la orden esté vinculado a una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e017b-313">You will now apply settings to break the work so that each container in the order is linked to one work order.</span></span>

1. <span data-ttu-id="e017b-314">Seleccione la casilla **Agrupar por este campo** para cada fila en la página **Descansos del encabezado de trabajo** (**Identificación del envío**, **Número de orden** e **ID de contenedor**).</span><span class="sxs-lookup"><span data-stu-id="e017b-314">Select the **Group by this field** checkbox for each row on the **Work header breaks** page (**Shipment ID**, **Order number**, and **Container ID**).</span></span>
1. <span data-ttu-id="e017b-315">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e017b-315">Close the page.</span></span>

### <a name="set-up-shipment-consolidation-policies"></a><span data-ttu-id="e017b-316">Configurar directivas de consolidación de envíos</span><span class="sxs-lookup"><span data-stu-id="e017b-316">Set up shipment consolidation policies</span></span>

<span data-ttu-id="e017b-317">Siga estos pasos para configurar una directiva de consolidación de envíos.</span><span class="sxs-lookup"><span data-stu-id="e017b-317">To set up a shipment consolidation policy, follow these steps.</span></span>

1. <span data-ttu-id="e017b-318">Vaya a **Gestión de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.</span><span class="sxs-lookup"><span data-stu-id="e017b-318">Go to **Warehouse management \> Setup \> Release to warehouse \> Shipment consolidation policies**.</span></span>
1. <span data-ttu-id="e017b-319">En el panel de lista, establezca el campo **Tipo de política** en *Pedidos de venta*.</span><span class="sxs-lookup"><span data-stu-id="e017b-319">In the list pane, set the **Policy type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="e017b-320">Seleccione la política **Predeterminada** en la lista.</span><span class="sxs-lookup"><span data-stu-id="e017b-320">Select the **Default** policy in the list.</span></span>
1. <span data-ttu-id="e017b-321">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e017b-321">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="e017b-322">En la ficha desplegable **Campos de consolidacion**, en la lista **Campos seleccionados**, seleccione la fila donde el campo **Nombre del campo** está establecido en *Número de pedido*.</span><span class="sxs-lookup"><span data-stu-id="e017b-322">On the **Consolidation fields** FastTab, in the **Selected fields** list, select the row where the **Field name** field is set to *Order number*.</span></span>
1. <span data-ttu-id="e017b-323">Seleccione el botón **Quitar** ![Flecha izquierda](media/backward-button.png) para mover el campo a la lista **Campos restantes**.</span><span class="sxs-lookup"><span data-stu-id="e017b-323">Select the **Remove** button ![Left arrow](media/backward-button.png) to move the field to the **Remaining fields** list.</span></span>
1. <span data-ttu-id="e017b-324">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e017b-324">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-physical-dimensions-for-the-product"></a><span data-ttu-id="e017b-325">Configurar las dimensiones físicas del producto</span><span class="sxs-lookup"><span data-stu-id="e017b-325">Set up physical dimensions for the product</span></span>

<span data-ttu-id="e017b-326">Para configurar las dimensiones físicas de los productos que se utilizarán en este escenario, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e017b-326">To set up physical dimensions for the products that will be used in this scenario, follow these steps.</span></span>

1. <span data-ttu-id="e017b-327">Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="e017b-327">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="e017b-328">Seleccione el producto cuyo campo **Número de artículo** está establecido en *A0001*.</span><span class="sxs-lookup"><span data-stu-id="e017b-328">Select the product where the **Item number** field is set to *A0001*.</span></span>
1. <span data-ttu-id="e017b-329">En el panel Acciones, en la pestaña **Administrar inventario**, en el grupo **Almacén**, seleccione **Dimensiones físicas**.</span><span class="sxs-lookup"><span data-stu-id="e017b-329">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="e017b-330">En la página **Dimensiones físicas**, debería ver la siguiente línea en la cuadrícula:</span><span class="sxs-lookup"><span data-stu-id="e017b-330">On the **Physical dimensions** page, you should see the following line in the grid:</span></span>

    - <span data-ttu-id="e017b-331">**Unidad:** *piezas*</span><span class="sxs-lookup"><span data-stu-id="e017b-331">**Unit:** *pcs*</span></span>
    - <span data-ttu-id="e017b-332">**Peso bruto:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="e017b-332">**Gross weight:** *3.00*</span></span>
    - <span data-ttu-id="e017b-333">**Anchura:** *2,00*</span><span class="sxs-lookup"><span data-stu-id="e017b-333">**Width:** *2.00*</span></span>
    - <span data-ttu-id="e017b-334">**Profundidad:** *2,00*</span><span class="sxs-lookup"><span data-stu-id="e017b-334">**Depth:** *2.00*</span></span>
    - <span data-ttu-id="e017b-335">**Altura:** *4,00*</span><span class="sxs-lookup"><span data-stu-id="e017b-335">**Height:** *4.00*</span></span>
    - <span data-ttu-id="e017b-336">**Volumen:** *16,00*</span><span class="sxs-lookup"><span data-stu-id="e017b-336">**Volume:** *16.00*</span></span>

1. <span data-ttu-id="e017b-337">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e017b-337">Close the page.</span></span>
1. <span data-ttu-id="e017b-338">Seleccione el producto cuyo campo **Número de artículo** está establecido en *A0002*.</span><span class="sxs-lookup"><span data-stu-id="e017b-338">Select the product where the **Item number** field is set to *A0002*.</span></span>
1. <span data-ttu-id="e017b-339">En el panel Acciones, en la pestaña **Administrar inventario**, en el grupo **Almacén**, seleccione **Dimensiones físicas**.</span><span class="sxs-lookup"><span data-stu-id="e017b-339">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="e017b-340">En la página **Dimensiones físicas**, debería ver la siguiente línea en la cuadrícula:</span><span class="sxs-lookup"><span data-stu-id="e017b-340">On the **Physical dimensions** page, you should see the following line in the grid:</span></span>

    - <span data-ttu-id="e017b-341">**Unidad:** *piezas*</span><span class="sxs-lookup"><span data-stu-id="e017b-341">**Unit:** *pcs*</span></span>
    - <span data-ttu-id="e017b-342">**Peso bruto:** *4,00*</span><span class="sxs-lookup"><span data-stu-id="e017b-342">**Gross weight:** *4.00*</span></span>
    - <span data-ttu-id="e017b-343">**Anchura:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="e017b-343">**Width:** *3.00*</span></span>
    - <span data-ttu-id="e017b-344">**Profundidad:** *1,00*</span><span class="sxs-lookup"><span data-stu-id="e017b-344">**Depth:** *1.00*</span></span>
    - <span data-ttu-id="e017b-345">**Altura:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="e017b-345">**Height:** *3.00*</span></span>
    - <span data-ttu-id="e017b-346">**Volumen:** *9,00*</span><span class="sxs-lookup"><span data-stu-id="e017b-346">**Volume:** *9.00*</span></span>

### <a name="create-sales-order-1"></a><span data-ttu-id="e017b-347">Crear pedido de ventas 1</span><span class="sxs-lookup"><span data-stu-id="e017b-347">Create sales order 1</span></span>

<span data-ttu-id="e017b-348">Para crear un pedido de ventas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e017b-348">To create a sales order, follow these steps.</span></span>

1. <span data-ttu-id="e017b-349">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="e017b-349">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="e017b-350">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="e017b-350">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e017b-351">Aparece un cuadro de diálogo para crear un nuevo pedido de cliente.</span><span class="sxs-lookup"><span data-stu-id="e017b-351">A dialog box for creating a new sales order appears.</span></span> <span data-ttu-id="e017b-352">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="e017b-352">Set the following values:</span></span>

    - <span data-ttu-id="e017b-353">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="e017b-353">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="e017b-354">**Almacén**: *63*</span><span class="sxs-lookup"><span data-stu-id="e017b-354">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="e017b-355">Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e017b-355">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="e017b-356">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="e017b-356">The new sales order is opened.</span></span> <span data-ttu-id="e017b-357">En la ficha desplegable **Líneas de pedido de ventas**, agregue las siguientes líneas de ventas:</span><span class="sxs-lookup"><span data-stu-id="e017b-357">On the **Sales order lines** FastTab, add the following sales lines:</span></span>

    - <span data-ttu-id="e017b-358">Línea 1:</span><span class="sxs-lookup"><span data-stu-id="e017b-358">Line 1:</span></span>

        - <span data-ttu-id="e017b-359">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="e017b-359">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="e017b-360">**Cantidad:** *2*</span><span class="sxs-lookup"><span data-stu-id="e017b-360">**Quantity:** *2*</span></span>

    - <span data-ttu-id="e017b-361">Línea 2:</span><span class="sxs-lookup"><span data-stu-id="e017b-361">Line 2:</span></span>

        - <span data-ttu-id="e017b-362">**Código de artículo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="e017b-362">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="e017b-363">**Cantidad:** *2*</span><span class="sxs-lookup"><span data-stu-id="e017b-363">**Quantity:** *2*</span></span>

1. <span data-ttu-id="e017b-364">Seleccione la primera línea y luego seleccione **Inventario \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="e017b-364">Select the first line, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="e017b-365">En la página **Reserva**, seleccione **Reservar lote**.</span><span class="sxs-lookup"><span data-stu-id="e017b-365">On the **Reservation** page, select **Reserve lot**.</span></span> <span data-ttu-id="e017b-366">A continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e017b-366">Then close the page.</span></span>
1. <span data-ttu-id="e017b-367">Repita los dos pasos anteriores para la segunda línea.</span><span class="sxs-lookup"><span data-stu-id="e017b-367">Repeat the previous two steps for the second line.</span></span>
1. <span data-ttu-id="e017b-368">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e017b-368">Close the page.</span></span>

### <a name="create-sales-order-2"></a><span data-ttu-id="e017b-369">Crear pedido de ventas 2</span><span class="sxs-lookup"><span data-stu-id="e017b-369">Create sales order 2</span></span>

<span data-ttu-id="e017b-370">Siga estos pasos para crear un segundo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="e017b-370">To create a second sales order, follow these steps.</span></span>

1. <span data-ttu-id="e017b-371">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="e017b-371">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="e017b-372">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="e017b-372">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e017b-373">Aparece un cuadro de diálogo para crear un nuevo pedido de cliente.</span><span class="sxs-lookup"><span data-stu-id="e017b-373">A dialog box for creating a new sales order appears.</span></span> <span data-ttu-id="e017b-374">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="e017b-374">Set the following values:</span></span>

    - <span data-ttu-id="e017b-375">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="e017b-375">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="e017b-376">**Almacén**: *63*</span><span class="sxs-lookup"><span data-stu-id="e017b-376">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="e017b-377">Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e017b-377">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="e017b-378">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="e017b-378">The new sales order is opened.</span></span> <span data-ttu-id="e017b-379">En la ficha desplegable **Líneas de pedido de ventas**, agregue las siguientes líneas de ventas:</span><span class="sxs-lookup"><span data-stu-id="e017b-379">On the **Sales order lines** FastTab, add the following sales lines:</span></span>

    - <span data-ttu-id="e017b-380">Línea 1:</span><span class="sxs-lookup"><span data-stu-id="e017b-380">Line 1:</span></span>

        - <span data-ttu-id="e017b-381">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="e017b-381">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="e017b-382">**Cantidad:** *4*</span><span class="sxs-lookup"><span data-stu-id="e017b-382">**Quantity:** *4*</span></span>

    - <span data-ttu-id="e017b-383">Línea 2:</span><span class="sxs-lookup"><span data-stu-id="e017b-383">Line 2:</span></span>

        - <span data-ttu-id="e017b-384">**Código de artículo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="e017b-384">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="e017b-385">**Cantidad:** *4*</span><span class="sxs-lookup"><span data-stu-id="e017b-385">**Quantity:** *4*</span></span>

1. <span data-ttu-id="e017b-386">Seleccione la primera línea y luego seleccione **Inventario \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="e017b-386">Select the first line, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="e017b-387">En la página **Reserva**, seleccione **Reservar lote**.</span><span class="sxs-lookup"><span data-stu-id="e017b-387">On the **Reservation** page, select **Reserve lot**.</span></span> <span data-ttu-id="e017b-388">A continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e017b-388">Then close the page.</span></span>
1. <span data-ttu-id="e017b-389">Repita los dos pasos anteriores para la segunda línea.</span><span class="sxs-lookup"><span data-stu-id="e017b-389">Repeat the previous two steps for the second line.</span></span>
1. <span data-ttu-id="e017b-390">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e017b-390">Close the page.</span></span>

### <a name="create-the-load"></a><span data-ttu-id="e017b-391">Crear la carga</span><span class="sxs-lookup"><span data-stu-id="e017b-391">Create the load</span></span>

<span data-ttu-id="e017b-392">Siga estos pasos para crear una carga para cada conjunto de pedidos que creó para este escenario y luego despacharlo al almacén.</span><span class="sxs-lookup"><span data-stu-id="e017b-392">To create a load for each order that you created for this scenario and then release it to the warehouse, follow these steps.</span></span>

1. <span data-ttu-id="e017b-393">Vaya a **Gestión de almacén \> Cargas \> Área de trabajo de planificación de la carga**.</span><span class="sxs-lookup"><span data-stu-id="e017b-393">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="e017b-394">En la pestaña **Líneas de venta**, busque y seleccione todas las líneas de pedido de los pedidos de venta que creó para este escenario.</span><span class="sxs-lookup"><span data-stu-id="e017b-394">On the **Sales lines** tab, find and select all the sales order lines from the sales orders that you created for this scenario.</span></span>
1. <span data-ttu-id="e017b-395">En el panel de acciones, en la ficha **Suministro y demanda**, en el grupo **Agregar**, seleccione **A una carga nueva**.</span><span class="sxs-lookup"><span data-stu-id="e017b-395">On the Action Pane, on the **Supply and demand** tab, in the **Add** group, select **To new load**.</span></span> <span data-ttu-id="e017b-396">Las líneas de pedido seleccionadas se agregan a una nueva carga.</span><span class="sxs-lookup"><span data-stu-id="e017b-396">The selected order lines are added to a new load.</span></span>
1. <span data-ttu-id="e017b-397">En el cuadro de diálogo **Cargar asignación de plantilla**, en el campo **Cargar id. de plantilla**, seleccione una plantilla de carga, como *40' Container*.</span><span class="sxs-lookup"><span data-stu-id="e017b-397">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *40' Container*.</span></span>
1. <span data-ttu-id="e017b-398">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e017b-398">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="e017b-399">En la sección **Cargas**, busque y seleccione la carga que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="e017b-399">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="e017b-400">Seleccione **Lanzamiento \> Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="e017b-400">Select **Release \> Release to warehouse**.</span></span>
1. <span data-ttu-id="e017b-401">En el cuadro de diálogo **Despachar al almacén**, seleccione **Aceptar** para liberar la carga seleccionada al almacén.</span><span class="sxs-lookup"><span data-stu-id="e017b-401">In the **Release to warehouse** dialog box, select **OK** to release the selected load to the warehouse.</span></span>

### <a name="verify-the-shipments-and-containers"></a><span data-ttu-id="e017b-402">Verificar los envíos y contenedores</span><span class="sxs-lookup"><span data-stu-id="e017b-402">Verify the shipments and containers</span></span>

<span data-ttu-id="e017b-403">El siguiente procedimiento le permite verificar los envíos que se han creado.</span><span class="sxs-lookup"><span data-stu-id="e017b-403">The following procedure lets you verify the shipments that have been created.</span></span> <span data-ttu-id="e017b-404">Úselo para revisar el orden que creó para este escenario, para asegurarse de haber obtenido los resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="e017b-404">Use it to review the order that you created for this scenario, to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="e017b-405">Vaya a **Gestión de almacenes \> Envíos \> Todos los envíos**.</span><span class="sxs-lookup"><span data-stu-id="e017b-405">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="e017b-406">Busque y seleccione el envío que se creó para la carga que acaba de liberar.</span><span class="sxs-lookup"><span data-stu-id="e017b-406">Find and select the shipment that was created for the load that you just released.</span></span>
1. <span data-ttu-id="e017b-407">En el Panel acciones, en la pestaña **Transporte**, seleccione **Ver contenedores**.</span><span class="sxs-lookup"><span data-stu-id="e017b-407">On the Action Pane, on the **Transportation** tab, select **View containers**.</span></span>
1. <span data-ttu-id="e017b-408">Confirme que los artículos de los pedidos de venta se hayan colocado en contenedores en dos contenedores diferentes.</span><span class="sxs-lookup"><span data-stu-id="e017b-408">Confirm that the items from the sales orders were containerized into two different containers.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e017b-409">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e017b-409">Additional resources</span></span>

- [<span data-ttu-id="e017b-410">Creación de contenedores</span><span class="sxs-lookup"><span data-stu-id="e017b-410">Containerization</span></span>](wave-containerization.md)
