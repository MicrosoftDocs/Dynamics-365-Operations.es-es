---
title: Media móvil secuencia de costes de reserva
description: Este tema proporciona información sobre secuencias de costos de reserva para cálculos de promedio móvil en Microsoft Dynamics 365 Supply Chain Management.
author: AndersGirke
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 09da3c3a79b5540670db25d5466023132d2848f4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832283"
---
# <a name="moving-average-fallback-cost-sequence"></a><span data-ttu-id="ee405-103">Media móvil secuencia de costes de reserva</span><span class="sxs-lookup"><span data-stu-id="ee405-103">Moving average fallback cost sequence</span></span>

<span data-ttu-id="ee405-104">Una forma de calcular el costo de su inventario es mediante el uso de una _media móvil_.</span><span class="sxs-lookup"><span data-stu-id="ee405-104">One way that you can calculate the cost of your inventory is by using a _moving average_.</span></span> <span data-ttu-id="ee405-105">Se pueden asociar hasta tres valores de coste con cada artículo de inventario:</span><span class="sxs-lookup"><span data-stu-id="ee405-105">Up to three cost values can be associated with each inventory item:</span></span>

- <span data-ttu-id="ee405-106">**Ultima emisión** - El último costo de emisión que se asignó antes de que el inventario fuera negativo</span><span class="sxs-lookup"><span data-stu-id="ee405-106">**Last issue** – The last issue cost that was assigned before inventory went negative</span></span>
- <span data-ttu-id="ee405-107">**Coste activo** - El último coste que se activó en una versión de gestión de costes</span><span class="sxs-lookup"><span data-stu-id="ee405-107">**Active cost** – The latest cost that was activated in a costing version</span></span>
- <span data-ttu-id="ee405-108">**Precio del articulo** - El coste que se especifica para el producto lanzado</span><span class="sxs-lookup"><span data-stu-id="ee405-108">**Item price** – The cost that is specified for the released product</span></span>

<span data-ttu-id="ee405-109">Para determinar cuál de estos valores de coste debe usarse en los cálculos de promedio móvil, el sistema utiliza una _secuencia de costos de reserva_ para establecer el orden de preferencia para los valores.</span><span class="sxs-lookup"><span data-stu-id="ee405-109">To determine which of these cost values should be used in moving average calculations, the system uses a _fallback cost sequence_ to establish the order of preference for the values.</span></span> <span data-ttu-id="ee405-110">Si el valor de coste preferido no está disponible, el sistema usa el siguiente valor preferido, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="ee405-110">If the preferred cost value isn't available, the system uses the next-preferred value, and so on.</span></span>

<span data-ttu-id="ee405-111">En versiones anteriores de Microsoft Dynamics 365 Supply Chain Management, el sistema utilizó una secuencia de costo de recuperación fija (_Última emisión - Coste activo - Precio del artículo_).</span><span class="sxs-lookup"><span data-stu-id="ee405-111">In previous versions of Microsoft Dynamics 365 Supply Chain Management, the system used a fixed fallback cost sequence (_Last issue – Active cost – Item price_).</span></span> <span data-ttu-id="ee405-112">En la versión 10.0.11, esta secuencia sigue siendo la secuencia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ee405-112">In version 10.0.11, this sequence is still the default sequence.</span></span> <span data-ttu-id="ee405-113">Sin embargo, también puede activar una función que le permite seleccionar entre tres secuencias de costes de reserva disponibles.</span><span class="sxs-lookup"><span data-stu-id="ee405-113">However, you can also turn on a feature that lets you select among three available fallback cost sequences.</span></span> <span data-ttu-id="ee405-114">Esta característica puede ser especialmente útil para organizaciones que usan regularmente valores de inventario negativos.</span><span class="sxs-lookup"><span data-stu-id="ee405-114">This feature can be especially useful for organizations that regularly use negative inventory values.</span></span>

<span data-ttu-id="ee405-115">Para que el selector de la secuencia de costes de reserva esté disponible, usted (o un administrador) debe usar [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para activar la función que se llama _Secuencia de coste de recuperación promedio móvil_.</span><span class="sxs-lookup"><span data-stu-id="ee405-115">To make the selector for the fallback cost sequence available, you (or an admin) must use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the feature that is named _Moving average fallback cost sequence_.</span></span>

<span data-ttu-id="ee405-116">Para seleccionar la secuencia de costes de respaldo para los cálculos de promedio móvil, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ee405-116">To select the fallback cost sequence for moving average calculations, follow these steps.</span></span>

1. <span data-ttu-id="ee405-117">Abra la página **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="ee405-117">Open the **Parameters** page.</span></span>
2. <span data-ttu-id="ee405-118">En la pestaña **Contabilidad de inventario**, en la sección **Media móvil**, establezca el campo **Secuencia de costes de reserva** a uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ee405-118">On the **Inventory accounting** tab, in the **Moving average** section, set the **Fallback cost sequence** field to one of the following values:</span></span>

    - <span data-ttu-id="ee405-119">**Última emisión - Coste activo - Precio del artículo** - Esta secuencia es la secuencia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ee405-119">**Last issue – Active cost – Item price** – This sequence is the default sequence.</span></span> <span data-ttu-id="ee405-120">Es la misma secuencia que se usa si la función _Secuencia de costo de recuperación promedio móvil_ no está activada.</span><span class="sxs-lookup"><span data-stu-id="ee405-120">It's the same sequence that is used if the _Moving average fallback cost sequence_ feature isn't turned on.</span></span>
    - <span data-ttu-id="ee405-121">**Coste activo - Última emisión**</span><span class="sxs-lookup"><span data-stu-id="ee405-121">**Active cost – Last issue**</span></span>
    - <span data-ttu-id="ee405-122">**Coste activo - Precio del artículo** - Las organizaciones pueden experimentar problemas de rendimiento si utilizan procesos comerciales en los que el inventario se vuelve negativo regularmente y, al mismo tiempo, el volumen de transacciones es alto.</span><span class="sxs-lookup"><span data-stu-id="ee405-122">**Active cost – Item price** – Organizations might experience performance issues if they use business processes where inventory regularly goes negative and, at the same time, the transaction volume is high.</span></span> <span data-ttu-id="ee405-123">Esta configuración puede ayudar a mitigar esos problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ee405-123">This setting can help mitigate those performance issues.</span></span>

<span data-ttu-id="ee405-124">![Parámetros de contabilidad de inventario](media/inventory-accounting-parameters.png "Parámetros de contabilidad de inventario")</span><span class="sxs-lookup"><span data-stu-id="ee405-124">![Inventory accounting parameters](media/inventory-accounting-parameters.png "Inventory accounting parameters")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]