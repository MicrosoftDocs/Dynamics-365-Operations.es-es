---
title: Nivel de servicio y descripción
description: Este tema explica el nivel de servicio y su descripción en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectServiceLevel, EntAssetWorkOrderStandardDescription, EntAssetWorkOrderServiceLevel, EntAssetServiceLevelLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8bb56e5103bd9e18e88c164cd308e55d48e64823
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019388"
---
# <a name="service-level-and-description"></a><span data-ttu-id="4119c-103">Nivel de servicio y descripción</span><span class="sxs-lookup"><span data-stu-id="4119c-103">Service level and description</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="4119c-104">Cuando cree una orden de trabajo, puede que desee definir los niveles de servicio para este y agregarle una descripción general.</span><span class="sxs-lookup"><span data-stu-id="4119c-104">When you create a work order, you might want to define the service levels for it and add a general description to it.</span></span> <span data-ttu-id="4119c-105">Puede crear niveles de servicio de la orden de trabajo en la página **Niveles de servicio de la orden de trabajo** y descripciones en la página **Descripción de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="4119c-105">You can create work order service levels on the **Work order service levels** page and descriptions on the **Work order description** page.</span></span>

## <a name="create-a-service-level"></a><span data-ttu-id="4119c-106">Crear un nivel de servicio</span><span class="sxs-lookup"><span data-stu-id="4119c-106">Create a service level</span></span>

1. <span data-ttu-id="4119c-107">Seleccione **Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Nivel de servicio**.</span><span class="sxs-lookup"><span data-stu-id="4119c-107">Select **Asset management** \> **Setup** \> **Work orders** \> **Service level**.</span></span>
2. <span data-ttu-id="4119c-108">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4119c-108">Select **New**.</span></span>
3. <span data-ttu-id="4119c-109">En el campo **Nivel de servicio**, especifique el nivel de servicio (por ejemplo, un número).</span><span class="sxs-lookup"><span data-stu-id="4119c-109">In the **Service level** field, enter the service level (for example, a number).</span></span>
4. <span data-ttu-id="4119c-110">Escriba un nombre en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="4119c-110">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="4119c-111">En la ficha desplegable **Órdenes de trabajo**, puede definir las fechas y horas esperadas de inicio y finalización.</span><span class="sxs-lookup"><span data-stu-id="4119c-111">On the **Work orders** FastTab, you can define expected start and end dates and times.</span></span> <span data-ttu-id="4119c-112">Los campos de esta ficha desplegable definen el periodo durante el cual deben iniciarse y finalizarse las órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4119c-112">The fields on this FastTab define the period that work orders should be started and ended during.</span></span> <span data-ttu-id="4119c-113">Se utilizan para órdenes de trabajo que se crean manualmente y órdenes de trabajo que se crean a partir de solicitudes de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="4119c-113">They are used for work orders that are manually created and work orders that are created based on maintenance requests.</span></span> 

5. <span data-ttu-id="4119c-114">En el campo **Día de inicio**, especifique un número de días para definir el periodo durante el cual debe comenzar la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4119c-114">In the **Start day** field, enter a number of days to define the period that the work order should start during.</span></span> <span data-ttu-id="4119c-115">El número de días se calcula a partir de la fecha de creación de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4119c-115">The number of days is calculated from the creation date of the work order.</span></span> <span data-ttu-id="4119c-116">Por ejemplo, si la orden de trabajo debe comenzar cuando se crea, introduzca **0**.</span><span class="sxs-lookup"><span data-stu-id="4119c-116">For example, if the work order should start when it's created, enter **0**.</span></span> <span data-ttu-id="4119c-117">Si la orden de trabajo debe comenzar en el plazo de una semana después de crearla, introduzca **7**.</span><span class="sxs-lookup"><span data-stu-id="4119c-117">If the work order should start within one week after it's created, enter **7**.</span></span>
6. <span data-ttu-id="4119c-118">Para establecer una hora de inicio para la orden de trabajo, además de una fecha de inicio, establezca la opción **Establecer hora de inicio** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="4119c-118">To set a start time for the work order, in addition to a start date, set the **Set start time** option to **Yes**.</span></span> <span data-ttu-id="4119c-119">A continuación, especifique la hora de inicio en el campo **Hora de inicio**.</span><span class="sxs-lookup"><span data-stu-id="4119c-119">Then enter the start time in the **Start time** field.</span></span> <span data-ttu-id="4119c-120">Si establece la opción **No**, se utiliza la hora del día actual.</span><span class="sxs-lookup"><span data-stu-id="4119c-120">If you set the option to **No**, the current time of day is used.</span></span>
7. <span data-ttu-id="4119c-121">En el campo **Día de finalización**, especifique un número de días para definir el periodo durante el cual debe finalizar la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4119c-121">In the **End day** field, enter a number of days to define the period that the work order should end during.</span></span> <span data-ttu-id="4119c-122">El número de días se calcula a partir de la fecha de inicio de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4119c-122">The number of days is calculated from the start date of the work order.</span></span> <span data-ttu-id="4119c-123">Por ejemplo, si la orden de trabajo debe finalizar en el plazo de una semana de su fecha de inicio, introduzca **7**.</span><span class="sxs-lookup"><span data-stu-id="4119c-123">For example, if the work order should end within one week of its start date, enter **7**.</span></span>
8. <span data-ttu-id="4119c-124">Para establecer una hora de finalización para la orden de trabajo, además de una fecha de finalización, establezca la opción **Establecer hora de finalización** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="4119c-124">To set an end time for the work order, in addition to an end date, set the **Set end time** option to **Yes**.</span></span> <span data-ttu-id="4119c-125">A continuación, especifique la hora de finalización en el campo **Hora de finalización**.</span><span class="sxs-lookup"><span data-stu-id="4119c-125">Then enter the end time in the **End time** field.</span></span> <span data-ttu-id="4119c-126">Si establece la opción **No**, se utiliza la hora del día actual.</span><span class="sxs-lookup"><span data-stu-id="4119c-126">If you set the option to **No**, the current time of day is used.</span></span>
9. <span data-ttu-id="4119c-127">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4119c-127">Select **Save**.</span></span>

![Página de nivel de servicio de órdenes de trabajo](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a><span data-ttu-id="4119c-129">Crear una descripción</span><span class="sxs-lookup"><span data-stu-id="4119c-129">Create a description</span></span>

1. <span data-ttu-id="4119c-130">Seleccione **Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Descripciones**.</span><span class="sxs-lookup"><span data-stu-id="4119c-130">Select **Asset management** \> **Setup** \> **Work orders** \> **Descriptions**.</span></span>
2. <span data-ttu-id="4119c-131">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4119c-131">Select **New**.</span></span>
3. <span data-ttu-id="4119c-132">En el campo **Descripción**, escriba la descripción.</span><span class="sxs-lookup"><span data-stu-id="4119c-132">In the **Description** field, enter the description.</span></span>
4. <span data-ttu-id="4119c-133">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4119c-133">Select **Save**.</span></span>
