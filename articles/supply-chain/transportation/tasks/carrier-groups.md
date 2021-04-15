---
title: Grupos de transportistas
description: Este tema describe cómo configurar datos para grupos de transportistas.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSCarrierGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 9fe95ee9a0b6d69544f35ac6bc9cdf3dd00db291
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809071"
---
# <a name="carrier-groups"></a><span data-ttu-id="2bd9b-103">Grupos de transportistas</span><span class="sxs-lookup"><span data-stu-id="2bd9b-103">Carrier groups</span></span>

<span data-ttu-id="2bd9b-104">Un grupo de transportistas es un conjunto de transportistas y servicios de transportistas.</span><span class="sxs-lookup"><span data-stu-id="2bd9b-104">A carrier group is a collection of shipping carriers and carrier services.</span></span> <span data-ttu-id="2bd9b-105">Cada grupo de transportistas especifica la secuencia preferida para los transportistas de envío y los servicios de transportista que le pertenecen.</span><span class="sxs-lookup"><span data-stu-id="2bd9b-105">Each carrier group specifies the preferred sequence for the shipping carriers and carrier services that belong to it.</span></span>

<span data-ttu-id="2bd9b-106">Cuando existen varios transportistas de envío y servicios de transportista para el mismo segmento de ruta, puede especificar un grupo de transportistas en lugar de un transportista de envío específico y un servicio de transportista en el plan de ruta o guía de ruta.</span><span class="sxs-lookup"><span data-stu-id="2bd9b-106">When multiple shipping carriers and carrier services exist for the same route segment, you can specify a carrier group instead of a specific shipping carrier and carrier service in the route plan or route guide.</span></span>

## <a name="create-a-carrier-group"></a><span data-ttu-id="2bd9b-107">Crear un grupo de transportistas</span><span class="sxs-lookup"><span data-stu-id="2bd9b-107">Create a carrier group</span></span>

1. <span data-ttu-id="2bd9b-108">Vaya a **Administración de transporte &gt; Configuración &gt; Transportistas &gt; Grupo de transportistas**.</span><span class="sxs-lookup"><span data-stu-id="2bd9b-108">Go to **Transportation management &gt; Setup &gt; Carriers &gt; Carrier group**.</span></span>
1. <span data-ttu-id="2bd9b-109">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2bd9b-109">Select **New**.</span></span>
1. <span data-ttu-id="2bd9b-110">En el campo **Grupo de transportistas**, especifique un identificador (ID) único para el grupo.</span><span class="sxs-lookup"><span data-stu-id="2bd9b-110">In the **Carrier group** field, enter a unique identifier (ID) for the group.</span></span>
1. <span data-ttu-id="2bd9b-111">En el campo **Nombre**, especifique un nombre descriptivo para el grupo.</span><span class="sxs-lookup"><span data-stu-id="2bd9b-111">In the **Name** field, enter a descriptive name for the group.</span></span>
1. <span data-ttu-id="2bd9b-112">En la ficha desplegable **Detalles**, agregue una fila y seleccione un transportista de envío y un servicio de transportista para ello.</span><span class="sxs-lookup"><span data-stu-id="2bd9b-112">On the **Details** FastTab, add a row, and select a shipping carrier and a carrier service for it.</span></span> <span data-ttu-id="2bd9b-113">Repita este paso hasta que haya agregado tantos operadores como necesite para el grupo.</span><span class="sxs-lookup"><span data-stu-id="2bd9b-113">Repeat this step until you've added as many carriers as you require for the group.</span></span>
1. <span data-ttu-id="2bd9b-114">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="2bd9b-114">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]