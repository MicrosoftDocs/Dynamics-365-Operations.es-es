---
title: Actualización manual de los contadores de activos
description: En este tema se describe la actualización manual de contadores de activos en la Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e7c5ec288404c18b00f9dcd0e66f50744d0aa2f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875884"
---
# <a name="manual-update-of-asset-counters"></a><span data-ttu-id="c6c8c-103">Actualización manual de los contadores de activos</span><span class="sxs-lookup"><span data-stu-id="c6c8c-103">Manual update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="c6c8c-104">Los contadores se utilizan para crear registros en un activo acerca de, por ejemplo, el número de horas en funcionamiento o el número de cantidades producidas.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-104">Counters are used to create registrations on an asset regarding, for example, number of hours in operation, or the number of quantities produced.</span></span>

<span data-ttu-id="c6c8c-105">Si el tipo de contador seleccionado para un contador se establece para heredar valores de contador (Ficha desplegable **Administración de activos** > **Configuración** > **Tipos de activos** > **Contadores** > **General** > botón de alternancia **Heredar valores de contador de activos** establecido en "Sí"), entonces cuando cree una nueva línea de contador de ese tipo, cada activo secundario que utiliza el mismo tipo de contador se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-105">If the counter type selected for a counter is set to inherit counter values (**Asset management** > **Setup** > **Asset types** > **Counters** > **General** FastTab > **Inherit asset counter values** toggle button set to "Yes"), then, when you create a new counter line of that type, every child asset that uses the same counter type is automatically updated.</span></span>

<span data-ttu-id="c6c8c-106">En **Todos los activos**, cree registros de contador de horas o cantidad en un activo, según sus lecturas en el activo.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-106">In **All assets**, you create hours or quantity counter registrations on an asset, based on your readings on the asset.</span></span>

1. <span data-ttu-id="c6c8c-107">Haga clic en **Administración de activos** > **Común** > **Activos** > **Todos los activos**.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-107">Click **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="c6c8c-108">Seleccione el activo en la lista y haga clic en **Contadores**.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-108">Select the asset in the list, and click **Counters**.</span></span> <span data-ttu-id="c6c8c-109">En el formulario **Contadores de activos**, verá una lista de todos los registros de contador previos en el activo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-109">In the **Asset counters** form, you see a list of all previous counter registrations on the selected asset.</span></span>

3. <span data-ttu-id="c6c8c-110">Haga clic en **Nuevo** para crear un nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-110">Click **New** to create a new registration.</span></span> <span data-ttu-id="c6c8c-111">El id. de activo se inserta automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-111">The asset ID is automatically inserted.</span></span>

4. <span data-ttu-id="c6c8c-112">En el campo **Contador**, seleccione el contador pertinente.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-112">In the **Counter** field, select the relevant counter.</span></span> <span data-ttu-id="c6c8c-113">Solo están disponibles los contadores relacionados con el tipo de activo seleccionado en el activo.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-113">Only counters related to the asset type selected on the asset are available.</span></span> <span data-ttu-id="c6c8c-114">La unidad relacionada se inserta automáticamente en el campo **Unidad**.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-114">The related unit is automatically inserted in the **Unit** field.</span></span>

5. <span data-ttu-id="c6c8c-115">Seleccione la fecha y la hora para el registro del contador.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-115">Select date and time for the counter registration.</span></span>

6. <span data-ttu-id="c6c8c-116">En el campo **Valor**, inserte el número desde el último registro del contador, o en el campo **Valor agregado**, inserte el número total de contadores.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-116">In the **Value** field, insert the number since the last counter registration, or, in the **Aggregated value** field, insert the total count number.</span></span>

- <span data-ttu-id="c6c8c-117">Si instala físicamente un nuevo contador en un activo, debe registrar el cambio en el activo en **Contadores de activos**.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-117">If you physically install a new counter on an asset, you need to register the change on the asset in **Asset counters**.</span></span> <span data-ttu-id="c6c8c-118">A continuación, debe crear dos líneas de registro con horas de registro idénticas y seleccionar la casilla **Restablecimiento del contador** en la línea relativa al nuevo contador.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-118">Next, you must create two registration lines with identical timestamps, and on the line regarding the new counter, you select the **Counter reset** check box.</span></span> <span data-ttu-id="c6c8c-119">Cuando cree las dos líneas de registro, la primera línea debe ser para el contador que va a sustituir.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-119">When you create the two registration lines, the first line must be for the counter that you are replacing.</span></span> <span data-ttu-id="c6c8c-120">En el campo **Totales**, el número total de recuentos es la suma de contadores totales de todos los valores registrados en ese tipo de contador.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-120">In the **Totals** field, the total count number is the sum of the counter total of all registered values on that counter type.</span></span>  
- <span data-ttu-id="c6c8c-121">Si se selecciona la casilla **Restablecimiento del contador** en un activo mediante un plan de mantenimiento con un tipo de intervalo "Una vez de..." o "Una vez alcanzado…", el contador sigue activo en la nueva línea del contador porque crea una línea de contador independiente y empieza de nuevo con un nuevo contador.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-121">If the **Counter reset** check box is selected on an asset using a maintenance plan with a "Once from..." or "Once reached..." interval type, the counter is still active on the new counter line because you create a separate counter line and start over with a new counter.</span></span>

![Figura 1](media/11-work-orders.png)


<span data-ttu-id="c6c8c-123">Si tiene que realizar registros de contadores en varios activos, esto se puede hacer en **Administración de activos** > **Consultas** > **Activos** > **Contadores de activos**.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-123">If you need to make counter registrations on several assets, that can be done in **Asset management** > **Inquiries** > **Assets** > **Asset counters**.</span></span>

>[!NOTE]
><span data-ttu-id="c6c8c-124">Puede configurar un intervalo para definir desviaciones en los registros de contadores manuales, así como el tipo de mensaje que se debe mostrar si los registros están fuera del intervalo definido.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-124">You can set up a range to define deviations in manual counter registrations, and the type of message that should be displayed if registrations are outside the defined range.</span></span> <span data-ttu-id="c6c8c-125">Consulte el tema [Contadores](../setup-for-objects/counters.md) en los que respecta a la configuración de los contadores.</span><span class="sxs-lookup"><span data-stu-id="c6c8c-125">Refer to the [Counters](../setup-for-objects/counters.md) topic regarding setup of counters.</span></span>
