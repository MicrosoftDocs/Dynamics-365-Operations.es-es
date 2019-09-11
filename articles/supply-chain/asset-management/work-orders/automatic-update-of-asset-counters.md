---
title: Actualización automática de los contadores de activos
description: Este tema describe la actualización automática de contadores de activos en la Administración de activos.
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
ms.openlocfilehash: 97e6912cd37d6f82d8bf022141f04645a3364ee1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875889"
---
# <a name="automatic-update-of-asset-counters"></a><span data-ttu-id="3f583-103">Actualización automática de los contadores de activos</span><span class="sxs-lookup"><span data-stu-id="3f583-103">Automatic update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="3f583-104">En la sección anterior, se describe el registro manual de los contadores de activos.</span><span class="sxs-lookup"><span data-stu-id="3f583-104">In the previous section, manual registration of asset counters is described.</span></span> <span data-ttu-id="3f583-105">La configuración de los contadores de activos se describe en [Contadores](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="3f583-105">Setup of asset counters is described in [Counters](../setup-for-objects/counters.md).</span></span>

<span data-ttu-id="3f583-106">Los valores de un contador también se pueden actualizar automáticamente a partir de los registros de producción, en función de las horas de producción o la cantidad de producción.</span><span class="sxs-lookup"><span data-stu-id="3f583-106">Counter values can also be automatically updated from production registrations, based on production hours or production quantity.</span></span> <span data-ttu-id="3f583-107">Esto se hace en **Actualizar contadores de activos**.</span><span class="sxs-lookup"><span data-stu-id="3f583-107">This is done in **Update asset counters**.</span></span> <span data-ttu-id="3f583-108">Puede actualizar uno o varios activos insertando un parámetro, **Desde fecha**.</span><span class="sxs-lookup"><span data-stu-id="3f583-108">You can update one or several assets by inserting one parameter, **From date**.</span></span> <span data-ttu-id="3f583-109">Este parámetro especifica la fecha de inicio para los registros de producción (horas o cantidad producida), es decir, la fecha de inicio a partir de la cual deben actualizarse los valores de contador.</span><span class="sxs-lookup"><span data-stu-id="3f583-109">This parameter specifies the start date for production registrations (hours or quantity produced), meaning the start date from which counter values should be updated.</span></span>

<span data-ttu-id="3f583-110">Todos los activos que están relacionadas con un recurso *y* tienen contadores de activos, configurados para actualizarse según la cantidad producida o las horas de producción, se incluirán en una actualización automática, y se crearán nuevos valores de contador.</span><span class="sxs-lookup"><span data-stu-id="3f583-110">All assets that are related to a resource *and* have asset counters, which are set up to be updated based on produced quantity or production hours, will be included in an automatic update, and new counter values will be created.</span></span>

<span data-ttu-id="3f583-111">En relación con los contadores basados en la cantidad de producción, la cantidad de artículos y la cantidad de defectos registrados se incluyen en el recuento.</span><span class="sxs-lookup"><span data-stu-id="3f583-111">Regarding counters based on production quantity, good quantity as well as error quantity registered are included in the count.</span></span> <span data-ttu-id="3f583-112">Si la unidad utilizada para el registro de cantidad producida es diferente de la unidad utilizada en el contador, la cantidad se convierte para que se corresponda con la unidad del contador.</span><span class="sxs-lookup"><span data-stu-id="3f583-112">If the unit used for produced quantity registration is different from the unit used on the counter, quantity is converted to correspond with the counter unit.</span></span>

<span data-ttu-id="3f583-113">Como se mencionó anteriormente, los contadores automáticos se pueden actualizar a partir de los registros de producción.</span><span class="sxs-lookup"><span data-stu-id="3f583-113">As mentioned above, automatic counters can be updated from production registrations.</span></span> <span data-ttu-id="3f583-114">Por tanto, el activo para el que desea para actualizar automáticamente los contadores debe estar relacionado con un recurso (máquina).</span><span class="sxs-lookup"><span data-stu-id="3f583-114">Therefore, the asset for which you want to automatically update counters must be related to a resource (machine).</span></span> <span data-ttu-id="3f583-115">Las descripciones siguientes proporcionan una visión general de la configuración y el procesamiento de órdenes de producción (en el módulo **Control de producción**), que se utiliza como base para la actualización automática de los contadores en un activo del módulo **Administración de activos**.</span><span class="sxs-lookup"><span data-stu-id="3f583-115">The following descriptions provide an overview of the setup and processing of production orders (in the **Production control** module), which is used as a basis for automatic update of counters on an asset in the **Asset management** module.</span></span>

<span data-ttu-id="3f583-116">Cuando se hayan registrado las cantidades o las horas de producción en el recurso, puede actualizar los contadores de activos relacionados.</span><span class="sxs-lookup"><span data-stu-id="3f583-116">When produced quantities or production hours have been registered on the resource, you can update the related asset counters.</span></span>

1. <span data-ttu-id="3f583-117">Haga clic en **Administración de activos** > **Periódico** > **Activos** > **Actualizar contadores de activos**.</span><span class="sxs-lookup"><span data-stu-id="3f583-117">Click **Asset management** > **Periodic** > **Assets** > **Update asset counters**.</span></span>

2. <span data-ttu-id="3f583-118">Seleccione la fecha de inicio de la actualización automática en el campo **Desde fecha**.</span><span class="sxs-lookup"><span data-stu-id="3f583-118">Select the start date of the automatic update in the **From date** field.</span></span>

>[!NOTE]
><span data-ttu-id="3f583-119">La fecha de este campo es la fecha de "trabajo en curso" **Transacciones de ruta** (campo **Control de producción** > **Consultas e informes** > **Producción** > **Transacciones e rutas** > **Fecha física**).</span><span class="sxs-lookup"><span data-stu-id="3f583-119">The date in this field is the "work in progress" date from **Route transactions** (**Production control** > **Inquiries and reports** > **Production** > **Route transactions** > **Physical date** field).</span></span>

3. <span data-ttu-id="3f583-120">Si desea seleccionar los activos específicos, los tipos de activo o los recursos de la actualización automática, haga clic en **Filtro** en la ficha desplegable **Registros que incluir** y haga la selección relevante.</span><span class="sxs-lookup"><span data-stu-id="3f583-120">If you want to select specific assets, asset types, or resources for the automatic update, click **Filter** on the **Records to include** FastTab, and make the relevant selections.</span></span>

4. <span data-ttu-id="3f583-121">Si es necesario, puede configurar la actualización automática como un trabajo por lotes en la ficha desplegable **Ejecutar en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="3f583-121">If required, you can set up the automatic update as a batch job on the **Run in the background** FastTab.</span></span>

![Figura 1](media/12-work-orders.png)

5. <span data-ttu-id="3f583-123">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f583-123">Click **OK**.</span></span> <span data-ttu-id="3f583-124">Cuando haya finalizado la actualización del contador, podrá ver los registros del contador relacionados con el activo en **Contadores de activos** (**Administración de activos** > **Común** > **Activos** > **Todos os activos** >seleccionar activo > botón **Contadores**).</span><span class="sxs-lookup"><span data-stu-id="3f583-124">When the automatic asset counter update is done, you can see the counter registrations related to the asset in **Asset counters** (**Asset management** > **Common** > **Assets** > **All assets** > select asset > **Counters** button).</span></span>

<span data-ttu-id="3f583-125">En **Totales del contador de activos**, puede obtener una visión general del último registro hecho en todos los tipos de contador en todos los activos.</span><span class="sxs-lookup"><span data-stu-id="3f583-125">In **Asset counter totals**, you can get an overview of the latest registration made on all counter types on all assets.</span></span> <span data-ttu-id="3f583-126">Haga clic en **Administración de activos** > **Consultas** > **Activos** > **Valor agregado de activos**.</span><span class="sxs-lookup"><span data-stu-id="3f583-126">Click **Asset management** > **Inquiries** > **Assets** > **Asset aggregated value**.</span></span> <span data-ttu-id="3f583-127">La vista se muy parecida **Contadores de activos**, pero no puede agregar o editar registros en **Valor agregado de activo**.</span><span class="sxs-lookup"><span data-stu-id="3f583-127">The view is very similar to **Asset counters**, but you cannot add or edit registrations in **Asset aggregated value**.</span></span> <span data-ttu-id="3f583-128">Es solo para la visión general.</span><span class="sxs-lookup"><span data-stu-id="3f583-128">It is for overview only.</span></span>

![Figura 2](media/13-work-orders.png)


- <span data-ttu-id="3f583-130">Aún es posible crear registros manuales de valor del contador para los tipos de contador que se actualizan.</span><span class="sxs-lookup"><span data-stu-id="3f583-130">It is still possible to create manual counter value registrations for counter types that are automatically updated.</span></span> <span data-ttu-id="3f583-131">Consulte la sección "Actualización manual de contadores de activos" para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3f583-131">Refer to the "Manual update of asset counters" section for more information.</span></span>
- <span data-ttu-id="3f583-132">Puede configurar los contadores relacionados con otro contador, lo que significa que cuando se actualizan un contador, los contadores se actualizan automáticamente al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="3f583-132">You can set up counters related to another counter, which means that when a counter is updated, related counters are automatically updated at the same time.</span></span> <span data-ttu-id="3f583-133">Consulte [Contadores](../setup-for-objects/counters.md) en que respecta a la configuración de los contadores relacionados.</span><span class="sxs-lookup"><span data-stu-id="3f583-133">Refer to [Counters](../setup-for-objects/counters.md) regarding setup of related counters.</span></span>
