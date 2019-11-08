---
title: Actualización manual de los contadores de activos
description: En este tema se describe la actualización manual de contadores de activos en la Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3072ab204b53b16988d2973b28a697041cb84c27
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626149"
---
# <a name="manual-update-of-asset-counters"></a><span data-ttu-id="b7ed0-103">Actualización manual de los contadores de activos</span><span class="sxs-lookup"><span data-stu-id="b7ed0-103">Manual update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="b7ed0-104">Los contadores se utilizan para crear registros de un activo, como registros sobre el número de horas que el activo ha estado en funcionamiento o la cantidad que se ha producido.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-104">Counters are used to create registrations on an asset, such as registrations about the number of hours that the asset has been in operation or the quantity that has been produced.</span></span>

<span data-ttu-id="b7ed0-105">Se puede definir el tipo de contador para un contador de manera que herede los valores del contador.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-105">The counter type that is selected for a counter might be set to inherit counter values.</span></span> <span data-ttu-id="b7ed0-106">Es decir la opción **Heredar valores de contador de activo** se establece en **Sí** en la ficha desplegable **General** de la página **Contadores** (**Administración de activos** > **Configuración** > **Tipos del activo** > **Contadores**).</span><span class="sxs-lookup"><span data-stu-id="b7ed0-106">In other words, the **Inherit asset counter values** option is set to **Yes** on the **General** FastTab of the **Counters** page (**Asset management** > **Setup** > **Asset types** > **Counters**).</span></span> <span data-ttu-id="b7ed0-107">En este caso, al crear una línea de contador nueva de ese tipo, cada activo secundario que utiliza el mismo tipo de contador se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-107">In this case, when you create a new counter line of that type, every child asset that uses the same counter type is automatically updated.</span></span>

<span data-ttu-id="b7ed0-108">En la página **Todos los activos**, cree registros de contador de horas o cantidad en un activo, según sus lecturas en el activo.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-108">On the **All assets** page, you create hours or quantity counter registrations on an asset, based on your readings on the asset.</span></span>

1. <span data-ttu-id="b7ed0-109">Seleccione **Administración de activos** > **Común** > **Activos** > **Todos los activos**.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-109">Select **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="b7ed0-110">Seleccione el activo y, a continuación, en el panel de acciones, en la pestaña **Activo**, en el grupo **Preventivo**, seleccione **Contadores**.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-110">Select the asset, and then, on the Action Pane, on the **Asset** tab, in the **Preventive** group, select **Counters**.</span></span> <span data-ttu-id="b7ed0-111">La página **Contadores de activos** muestra una lista de todos los registros de contador previos realizados en el activo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-111">The **Asset counters** page shows a list of all previous counter registrations that have been made on the selected asset.</span></span>

3. <span data-ttu-id="b7ed0-112">Seleccionar **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-112">Select **New** to create a registration.</span></span> <span data-ttu-id="b7ed0-113">El ID de activo se inserta automáticamente en el campo **Activo**.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-113">The asset ID is automatically entered in the **Asset** field.</span></span>

4. <span data-ttu-id="b7ed0-114">En el campo **Contador**, seleccione el contador pertinente.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-114">In the **Counter** field, select the relevant counter.</span></span> <span data-ttu-id="b7ed0-115">Solo están disponibles para la selección los contadores relacionados con el tipo de activo seleccionado en el activo.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-115">Only counters that are related to the asset type selected on the asset are available for selection.</span></span> <span data-ttu-id="b7ed0-116">La unidad relacionada se inserta automáticamente en el campo **Unidad**.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-116">The related unit is automatically entered in the **Unit** field.</span></span>

5. <span data-ttu-id="b7ed0-117">En el campo **Registrado**, seleccione la fecha y hora del registro contrario.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-117">In the **Registered** field, select the date and time for the counter registration.</span></span>

6. <span data-ttu-id="b7ed0-118">En el campo **Valor**, especifique el número ya que el registro de contador.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-118">In the **Value** field, enter the number since the last counter registration.</span></span> <span data-ttu-id="b7ed0-119">Como alternativa, en el campo **Valor agregado**, especifique el número de contadores total.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-119">Alternatively, in the **Aggregated value** field, enter the total count number.</span></span>

<span data-ttu-id="b7ed0-120">Tenga en cuenta los aspectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b7ed0-120">Note the following points:</span></span>

- <span data-ttu-id="b7ed0-121">Si instala físicamente un nuevo contador en un activo, debe registrar el cambio en el activo en la página **Contadores de activos**.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-121">If you physically install a new counter on an asset, you must register the change on the asset on the **Asset counters** page.</span></span> <span data-ttu-id="b7ed0-122">A continuación, debe crear dos líneas de registro con horas de registro idénticas.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-122">Next, you must create two registration lines that have identical timestamps.</span></span> <span data-ttu-id="b7ed0-123">La primera línea debe ser para el contador que va a sustituir.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-123">The first line must be for the counter that you're replacing.</span></span> <span data-ttu-id="b7ed0-124">En la línea relacionada con el nuevo contador, seleccione la casilla de verificación **Reinicio del contador**.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-124">On the line that is related to the new counter, select the **Counter reset** check box.</span></span> <span data-ttu-id="b7ed0-125">En el campo **Totales**, el número total de recuentos es la suma de contadores totales de todos los valores registrados en ese tipo de contador.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-125">In the **Totals** field, the total count number is the sum of the counter totals of all registered values on that counter type.</span></span>

- <span data-ttu-id="b7ed0-126">Si se selecciona la casilla **Restablecimiento del contador** en un activo mediante un plan de mantenimiento con un tipo de intervalo "Una vez de..." o "Una vez alcanzado…", el contador sigue activo en la nueva línea del contador porque crea una línea de contador independiente y empieza de nuevo con un nuevo contador.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-126">If the **Counter reset** check box is selected on an asset using a maintenance plan that has a "Once from..." or "Once reached..." interval type, the counter is still active on the new counter line, because you create a separate counter line and start over with a new counter.</span></span>

<span data-ttu-id="b7ed0-127">La ilustración siguiente muestra un ejemplo de la página de lista **Contadores de activos**.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-127">The illustration below shows an example of the **Asset counters** page.</span></span>

![Figura 1](media/11-work-orders.png)

<span data-ttu-id="b7ed0-129">En la página **Contadores de activos** (**Administración de activos** > **Consultas** > **Activos** > **Contadores de activos**), puede crear registros de contador en varios activos simultáneamente, como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-129">On the **Asset counters** page (**Asset management** > **Inquiries** > **Assets** > **Asset counters**), you can make counter registrations on several assets at the same time, as you require.</span></span>

>[!NOTE]
><span data-ttu-id="b7ed0-130">Puede configurar un intervalo para definir desviaciones en los registros de contadores manuales.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-130">You can set up a range to define deviations in manual counter registrations.</span></span> <span data-ttu-id="b7ed0-131">También puede especificar el tipo de mensaje que se muestra si los registros están fuera del intervalo definido.</span><span class="sxs-lookup"><span data-stu-id="b7ed0-131">You can also specify the type of message that is shown if registrations are outside the defined range.</span></span> <span data-ttu-id="b7ed0-132">Para obtener más información sobre la configuración de los contadores, consulte [Contadores](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="b7ed0-132">For more information about how to set up counters, see [Counters](../setup-for-objects/counters.md).</span></span>

