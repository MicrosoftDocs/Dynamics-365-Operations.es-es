---
title: Actualización automática de los contadores de activos
description: Este tema describe la actualización automática de contadores de activos en la Administración de activos.
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
ms.openlocfilehash: d51b9a7684e460d555632c3896e9dd8a4e10d92c
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626187"
---
# <a name="automatic-update-of-asset-counters"></a><span data-ttu-id="9c2b6-103">Actualización automática de los contadores de activos</span><span class="sxs-lookup"><span data-stu-id="9c2b6-103">Automatic update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9c2b6-104">Para obtener información acerca del registro manual de contadores de activos, consulte [Actualización manual de contadores de activos](../work-orders/manual-update-of-asset-counters.md).</span><span class="sxs-lookup"><span data-stu-id="9c2b6-104">For information about manual registration of asset counters, see [Manual update of asset counters](../work-orders/manual-update-of-asset-counters.md).</span></span> <span data-ttu-id="9c2b6-105">Para obtener más información sobre cómo configurar contadores de activos, consulte [Contadores](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="9c2b6-105">For information on how to set up asset counters, see [Counters](../setup-for-objects/counters.md).</span></span>

<span data-ttu-id="9c2b6-106">Los valores de un contador también se pueden actualizar automáticamente a partir de los registros de producción, en función de las horas de producción o la cantidad de producción (es decir, la cantidad que se produce).</span><span class="sxs-lookup"><span data-stu-id="9c2b6-106">Counter values can also be automatically updated from production registrations, based on the production hours or production quantity (that is, the quantity that is produced).</span></span> <span data-ttu-id="9c2b6-107">Esta actualización se realiza en la página **Actualizar contadores de activos**.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-107">This update is done on the **Update asset counters** page.</span></span> <span data-ttu-id="9c2b6-108">Puede actualizar uno o varios activos configurando un parámetro, **Desde fecha**.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-108">You can update one or several assets by setting one parameter, **From date**.</span></span> <span data-ttu-id="9c2b6-109">Este parámetro especifica la fecha de inicio para los registros de producción (horas de producción o cantidades de producción).</span><span class="sxs-lookup"><span data-stu-id="9c2b6-109">This parameter specifies the start date for production registrations (production hours or production quantities).</span></span> <span data-ttu-id="9c2b6-110">Es decir, especifica la fecha desde la que deben actualizarse los valores del contador.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-110">In other words, it specifies the date that counter values should be updated from.</span></span>

<span data-ttu-id="9c2b6-111">Todos los activos que están relacionados con un recurso *y* que tienen contadores de activos que están configurados para actualizarse según las horas de producción o la cantidad de producción, se incluirán en una actualización automática.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-111">All assets that are related to a resource, *and* that have asset counters that are set up to be updated based on the production hours or production quantity, will be included in an automatic update.</span></span> <span data-ttu-id="9c2b6-112">Se crearán nuevos valores del contador.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-112">New counter values will be created.</span></span>

<span data-ttu-id="9c2b6-113">Para los contadores que se basan en la cantidad de producción, el recuento incluye la cantidad sin errores y la cantidad con errores que se registran.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-113">For counters that are based on the production quantity, the count includes both the good quantity and the error quantity that are registered.</span></span> <span data-ttu-id="9c2b6-114">Si la unidad que se utiliza para el registro de cantidad de producción difiere de la unidad que se utiliza para el contador, la cantidad se convierte para que se corresponda con la unidad del contador.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-114">If the unit that is used for production quantity registration differs from the unit that is used for the counter, the quantity is converted so that it corresponds to the counter unit.</span></span>

<span data-ttu-id="9c2b6-115">Como se mencionó anteriormente, los contadores automáticos se pueden actualizar a partir de los registros de producción.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-115">As mentioned above, automatic counters can be updated from production registrations.</span></span> <span data-ttu-id="9c2b6-116">Por tanto, el activo para el que desea para actualizar automáticamente los contadores debe estar relacionado con un recurso (máquina).</span><span class="sxs-lookup"><span data-stu-id="9c2b6-116">Therefore, the asset for which you want to automatically update counters must be related to a resource (machine).</span></span> <span data-ttu-id="9c2b6-117">Cuando se hayan registrado las cantidades o las horas de producción en el recurso, puede actualizar los contadores de activos relacionados.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-117">When produced quantities or production hours have been registered on the resource, you can update the related asset counters.</span></span>

1. <span data-ttu-id="9c2b6-118">Seleccione **Administración de activos** > **Periódico** > **Activos** > **Actualizar contadores de activos**.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-118">Select **Asset management** > **Periodic** > **Assets** > **Update asset counters**.</span></span>

2. <span data-ttu-id="9c2b6-119">En el campo **Desde fecha**, seleccione la fecha de inicio de la actualización automática.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-119">In the **From date** field, select the start date of the automatic update.</span></span>

>[!NOTE]
><span data-ttu-id="9c2b6-120">La fecha de este campo es la fecha de "trabajo en curso" **Transacciones de ruta** (campo **Control de producción** > **Consultas e informes** > **Producción** > **Transacciones e rutas** > **Fecha física**).</span><span class="sxs-lookup"><span data-stu-id="9c2b6-120">The date in this field is the "work in progress" date from **Route transactions** (**Production control** > **Inquiries and reports** > **Production** > **Route transactions** > **Physical date** field).</span></span>

3. <span data-ttu-id="9c2b6-121">En la ficha desplegable **Registros que incluir**, puede seleccionar activos específicos, tipos de activos o recursos para la actualización automática.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-121">On the **Records to include** FastTab, you can select specific assets, asset types, or resources for the automatic update.</span></span> <span data-ttu-id="9c2b6-122">Seleccione **Filtrar** y haga las selecciones relevantes.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-122">Select **Filter**, and make the relevant selections.</span></span>

4. <span data-ttu-id="9c2b6-123">En la pestaña desplegable **Ejecutar en segundo plano**, puede configurar la actualización automática como un trabajo por lotes según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-123">On the **Run in the background** FastTab, you can set up the automatic update as a batch job, as you require.</span></span>

<span data-ttu-id="9c2b6-124">La ilustración siguiente muestra un ejemplo del cuadro de diálogo **Actualizar contadores de activos**.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-124">The illustration below shows an example of the **Update asset counters** dialog.</span></span>

![Figura 1](media/12-work-orders.png)

5. <span data-ttu-id="9c2b6-126">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-126">Select **OK**.</span></span> 

<span data-ttu-id="9c2b6-127">Una vez realizada la actualización automática del contador de activos, puede ver los registros del contador que están relacionados con el activo en la página **Contadores de activos**.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-127">After the automatic asset counter update is done, you can view the counter registrations that are related to the asset on the **Asset counters** page.</span></span> <span data-ttu-id="9c2b6-128">Seleccione **Administración de activos** > **Común** > **Activos** > **Todos los activos**, seleccione el activo y, a continuación, en el panel de acciones, en la pestaña **Activo**, en el grupo **Preventivo**, seleccione **Contadores**.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-128">Select **Asset management** > **Common** > **Assets** > **All assets**, select the asset, and then, on the Action Pane, on the **Asset** tab, in the **Preventive** group, select **Counters**.</span></span>

<span data-ttu-id="9c2b6-129">En la página **Valor agregado de activo**, puede obtener una visión general del último registro que se ha hecho en todos los tipos de contador en todos los activos.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-129">On the **Asset aggregated value** page, you can get an overview of the latest registration that have been made on all counter types on all assets.</span></span> <span data-ttu-id="9c2b6-130">Seleccione **Administración de activos** > **Consultas** > **Activos** > **Valor agregado de activos**.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-130">Select **Asset management** > **Inquiries** > **Assets** > **Asset aggregated value**.</span></span> <span data-ttu-id="9c2b6-131">Esta página es similar a la página **Contadores de activos**, pero no puede agregar o editar registros.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-131">This page resembles the **Asset counters** page, but you can't add or edit registrations.</span></span> <span data-ttu-id="9c2b6-132">Es solo para la visión general.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-132">It's for overview only.</span></span>

<span data-ttu-id="9c2b6-133">La ilustración siguiente muestra un ejemplo de la página **Valor agregado de activos**.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-133">The illustration below shows an example of the **Asset aggregated value** page.</span></span>

![Figura 2](media/13-work-orders.png)

<span data-ttu-id="9c2b6-135">Tenga en cuenta los aspectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c2b6-135">Note the following points:</span></span>

- <span data-ttu-id="9c2b6-136">Aún puede crear registros manuales de valor del contador para los tipos de contador que se actualizan.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-136">You can still create manual counter value registrations for counter types that are automatically updated.</span></span> <span data-ttu-id="9c2b6-137">Para obtener más información, consulte [Actualización manual de contadores de activos](../work-orders/manual-update-of-asset-counters.md).</span><span class="sxs-lookup"><span data-stu-id="9c2b6-137">For more information, see [Manual update of asset counters](../work-orders/manual-update-of-asset-counters.md).</span></span>

- <span data-ttu-id="9c2b6-138">Puede configurar los contadores que están relacionados con otro contador.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-138">You can set up counters that are related to another counter.</span></span> <span data-ttu-id="9c2b6-139">En este caso, cuando se actualiza un contador, los contadores relacionados se actualizan automáticamente al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="9c2b6-139">In this case, when a counter is updated, related counters are automatically updated at the same time.</span></span> <span data-ttu-id="9c2b6-140">Para obtener más información sobre la configuración de los contadores relacionados, consulte [Contadores](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="9c2b6-140">For more information about how to set up related counters, see [Counters](../setup-for-objects/counters.md).</span></span>

