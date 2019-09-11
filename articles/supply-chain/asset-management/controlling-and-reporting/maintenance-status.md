---
title: Estado de mantenimiento
description: En este tema se explica cómo calcular un estado de mantenimiento en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 516607c056125a16e075c33f3c2ad069efb396d9
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918358"
---
# <a name="maintenance-status"></a><span data-ttu-id="169ef-103">Estado de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="169ef-103">Maintenance status</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="169ef-104">En Administración de activos, puede realizar un cálculo para obtener una visión general de solicitudes de mantenimiento, órdenes de trabajo y actividades del tiempo de inactividad por mantenimiento nuevas, activas y completadas para un periodo determinado.</span><span class="sxs-lookup"><span data-stu-id="169ef-104">In Asset Management, you can make a calculation to see an overview of new, active, and completed maintenance requests, work orders, and maintenance downtime activities for a specific period.</span></span> <span data-ttu-id="169ef-105">También puede ver el número de evaluaciones de estado completadas para el mismo periodo.</span><span class="sxs-lookup"><span data-stu-id="169ef-105">You can also see the number of completed condition assessments for the same period.</span></span> <span data-ttu-id="169ef-106">Use este cálculo para obtener una visión general de la carga de trabajo relativa a solicitudes de mantenimiento y órdenes de trabajo entrantes y completadas.</span><span class="sxs-lookup"><span data-stu-id="169ef-106">Use this calculation to get an overview of workload regarding incoming and completed maintenance requests and work orders.</span></span>

## <a name="make-a-maintenance-status-calculation"></a><span data-ttu-id="169ef-107">Realizar un cálculo del estado de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="169ef-107">Make a maintenance status calculation</span></span>

1. <span data-ttu-id="169ef-108">Haga clic en **Administración de activos** > **Consultas** > **Estado de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="169ef-108">Click **Asset management** > **Inquiries** > **Maintenance status**.</span></span>

2. <span data-ttu-id="169ef-109">En el diálogo **Calcular estado**, seleccione el período para el que desea crear el cálculo en los campos **Fecha inicial** y **Fecha final**.</span><span class="sxs-lookup"><span data-stu-id="169ef-109">In the **Calculate status** dialog, select the period for which you want to make the calculation in the **From date** and **To date** fields.</span></span>

3. <span data-ttu-id="169ef-110">Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para las líneas de mantenimiento con respecto a las ubicaciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="169ef-110">You can use the **Level** field to indicate how detailed you want the maintenance lines to be regarding functional locations.</span></span> <span data-ttu-id="169ef-111">Por ejemplo, si especifica el número "1" en el campo y tiene una estructura de ubicación técnica de varios niveles, todas líneas de mantenimiento para una ubicación técnica se mostrarán en el nivel superior. De este modo, el estado en una línea se puede agregar desde las ubicaciones técnicas ubicadas en un nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="169ef-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance lines for a functional location will be shown on the top level, and therefore the status on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="169ef-112">Si especifica el número "0" en el campo **Nivel**, verá un resultado detallado que muestra todas las líneas de mantenimiento en todos los niveles de la ubicación técnica con los que están relacionados.</span><span class="sxs-lookup"><span data-stu-id="169ef-112">If you insert the number "0" in the **Level** field, you see a detailed result showing all maintenance lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="169ef-113">Haga clic en **Aceptar** para iniciar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="169ef-113">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="169ef-114">En los grupos del panel de acciones **Agrupar por...**, haga clic en los botones relevantes para mostrar el nivel de detalle necesario del cálculo.</span><span class="sxs-lookup"><span data-stu-id="169ef-114">In the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="169ef-115">Se resaltarán los botones del panel de acciones seleccionados.</span><span class="sxs-lookup"><span data-stu-id="169ef-115">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="169ef-116">Haga clic en un botón para activarlo o desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="169ef-116">Click on a button to activate or deactivate it.</span></span>

6. <span data-ttu-id="169ef-117">Recuerde hacer clic en el botón **Actualizar** para actualizar el cálculo cada vez que haga cambios activando o desactivando los botones **Agrupar por…** o bien haciendo un cálculo para un nuevo periodo.</span><span class="sxs-lookup"><span data-stu-id="169ef-117">Remember to click the **Update** button to update the calculation each time you make changes by activating or deactivating **Group by...** buttons, or by making a calculation for a new period.</span></span>

7. <span data-ttu-id="169ef-118">Haga clic en **Estado** si desea crear un nuevo cálculo del estado de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="169ef-118">Click **Status** if you want to create a new maintenance status calculation.</span></span>

>[!NOTE]
><span data-ttu-id="169ef-119">Los resultados que se muestran en **Estado de mantenimiento** solo incluyen solicitudes de mantenimiento y órdenes de trabajo que tienen una fecha y hora de inicio real.</span><span class="sxs-lookup"><span data-stu-id="169ef-119">The results shown in **Maintenance status** only include maintenance requests and work orders that have an actual start date and time.</span></span> <span data-ttu-id="169ef-120">La fecha y hora de finalización pueden estar en blanco.</span><span class="sxs-lookup"><span data-stu-id="169ef-120">End date and time may be blank.</span></span>

<span data-ttu-id="169ef-121">*Ejemplo 1:*</span><span class="sxs-lookup"><span data-stu-id="169ef-121">*Example 1:*</span></span>

<span data-ttu-id="169ef-122">En la ilustración siguiente, se han activado los botones **Año** y **Mes**.</span><span class="sxs-lookup"><span data-stu-id="169ef-122">In the figure below, the **Year** and **Month** buttons have been activated.</span></span> <span data-ttu-id="169ef-123">Aquí obtiene una visión general de la carga de trabajo y el rendimiento mensual relacionado con solicitudes de mantenimiento y órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="169ef-123">Here, you get a general overview on a monthly basis of workload and throughput related to maintenance requests and work orders.</span></span> 

![Figura 1](media/13-controlling-and-reporting.png)

<span data-ttu-id="169ef-125">*Ejemplo 2:*</span><span class="sxs-lookup"><span data-stu-id="169ef-125">*Example 2:*</span></span>

<span data-ttu-id="169ef-126">En la siguiente ilustración se ha agregado información sobre ubicaciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="169ef-126">In the figure below, information about functional locations has been added.</span></span> <span data-ttu-id="169ef-127">Ahora es posible comparar la carga de trabajo y el rendimiento a través de ubicaciones técnicas, lo que puede representar ubicaciones geográficas, fábricas o áreas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="169ef-127">Now, it is possible to compare workload and throughput across functional locations, which may represent geographical locations, factories, or work areas.</span></span> 

![Figura 2](media/14-controlling-and-reporting.png)

