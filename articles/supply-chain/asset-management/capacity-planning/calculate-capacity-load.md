---
title: Calcular carga de capacidad
description: En este tema se explica cómo calcular la carca de capacidad Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/16/2019
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
ms.openlocfilehash: 82f65293679591f278e0e3b79c112ba36debc3bb
ms.sourcegitcommit: 5b53bdafa5cb9a1279576bfece0452a50383b122
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "2277952"
---
# <a name="calculate-capacity-load"></a><span data-ttu-id="05a51-103">Calcular carga de capacidad</span><span class="sxs-lookup"><span data-stu-id="05a51-103">Calculate capacity load</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="05a51-104">En Administración de activos, puede calcular la carga de capacidad en</span><span class="sxs-lookup"><span data-stu-id="05a51-104">In Asset Management, you can calculate capacity load on</span></span>

- <span data-ttu-id="05a51-105">líneas del programa de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="05a51-105">maintenance schedule lines</span></span>  
- <span data-ttu-id="05a51-106">órdenes de trabajo que aún no se han programado</span><span class="sxs-lookup"><span data-stu-id="05a51-106">work orders that have not yet been scheduled</span></span>  
- <span data-ttu-id="05a51-107">órdenes de trabajo programadas</span><span class="sxs-lookup"><span data-stu-id="05a51-107">scheduled work orders</span></span>

<span data-ttu-id="05a51-108">Esto resulta útil si desea obtener una visión general de la carga de capacidad esperada para un período específico.</span><span class="sxs-lookup"><span data-stu-id="05a51-108">This is useful if you want to get an overview of expected capacity load for a specific period.</span></span> <span data-ttu-id="05a51-109">El cálculo de la carga de capacidad se puede realizar en todos los activos o los activos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="05a51-109">Calculation of capacity load can be done on all assets or selected assets.</span></span> <span data-ttu-id="05a51-110">También puede crear un cálculo de los conjuntos de las actividades del tiempo de inactividad o los grupos de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="05a51-110">You can also make a calculation on maintenance downtime activities or work order pools.</span></span>

1. <span data-ttu-id="05a51-111">Haga clic en **Administración de activos** > **Consultas** > **Carga de capacidad** o **Administración de activos** > **Común** > **Grupos de órdenes de trabajo** > **Todos los grupos de órdenes de trabajo** / **Grupos de órdenes de trabajo activas** > seleccionar el grupo de órdenes de trabajo en la lista > botón **Carga de capacidad** o **Administración de activos** > **Común**  > **Actividades de tiempo de inactividad por mantenimiento** > **Todas las actividades de tiempo de inactividad por mantenimiento** / **Actividades de tiempo de inactividad por mantenimiento activas** > seleccione actividad de mantenimiento en la lista > botón **Carga de capacidad**.</span><span class="sxs-lookup"><span data-stu-id="05a51-111">Click **Asset management** > **Inquiries** > **Capacity load**, or **Asset management** > **Common** > **Work order pools** > **All work order pools** / **Active work order pools** > select work order pool in the list > **Capacity load** button, or **Asset management** > **Common** > **Maintenance downtime activities** > **All maintenance downtime activities** / **Active maintenance downtime activities** > select maintenance activity in the list > **Capacity load** button.</span></span>

2. <span data-ttu-id="05a51-112">En el diálogo **Calcular la carga de capacidad**, seleccione un período para el cálculo en los campos **Fecha y hora de inicio** y los campos **Fecha y hora final**.</span><span class="sxs-lookup"><span data-stu-id="05a51-112">In the **Calculate capacity load** dialog, select a period for the calculation in the **Start date/time** and **End date/time** fields.</span></span>

3. <span data-ttu-id="05a51-113">Seleccione "Sí" en el botón de alternar **Incluir programación de mantenimiento** si desea incluir líneas de mantenimiento en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="05a51-113">Select "Yes" on the **Include maintenance schedule** toggle button if you want to include maintenance schedule lines in the calculation.</span></span>

4. <span data-ttu-id="05a51-114">Seleccione "Sí" en el botón de alternar **Incluir orden de trabajo** si desea incluir trabajos de orden de trabajo en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="05a51-114">Select "Yes" on the **Include work order** toggle button if you want to include work order jobs in the calculation.</span></span>

5. <span data-ttu-id="05a51-115">Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para las líneas de carga de capacidad con respecto a las ubicaciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="05a51-115">You can use the **Level** field to indicate how detailed you want the capacity load lines to be regarding functional locations.</span></span> <span data-ttu-id="05a51-116">Por ejemplo, si especifica el número "1" en el campo, y tiene una estructura de ubicación técnica de varios niveles, todas líneas del programa de mantenimiento y órdenes de trabajo para una ubicación técnica se mostrarán en el nivel superior, y por tanto, las horas en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="05a51-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines and work orders for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="05a51-117">Si especifica el número "0" en el campo **Nivel**, verá un resultado detallado que muestra todas las líneas del programa de mantenimiento y todas las órdenes de trabajo en todos los niveles de la ubicación técnica con el que están relacionadas.</span><span class="sxs-lookup"><span data-stu-id="05a51-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines and all work orders on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="05a51-118">Haga clic en **Aceptar** para iniciar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="05a51-118">Click **OK** to start the calculation.</span></span>

7. <span data-ttu-id="05a51-119">En los grupos del panel de acciones **Agrupar por...**, haga clic en los botones relevantes para mostrar el nivel de detalle necesario del cálculo.</span><span class="sxs-lookup"><span data-stu-id="05a51-119">In the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="05a51-120">Se resaltarán en color azul los botones del grupo del panel de acciones seleccionados.</span><span class="sxs-lookup"><span data-stu-id="05a51-120">The selected action pane group buttons are highlighted in blue color.</span></span> <span data-ttu-id="05a51-121">Haga clic en un botón para activarlo o desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="05a51-121">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="05a51-122">La ilustración siguiente muestra un ejemplo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="05a51-122">The figure below shows an example of the interface.</span></span>

![Figura 1](media/01-capacity-planning.png)

>[!NOTE]
><span data-ttu-id="05a51-124">Si desea centrarse únicamente en el diseño de la capacidad en relación a las órdenes de trabajo programadas, consulte [Calcular la carga de capacidad en órdenes de trabajo programadas](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).</span><span class="sxs-lookup"><span data-stu-id="05a51-124">If you want to focus only on capacity planning regarding scheduled work orders, refer to [Calculate capacity load on scheduled work orders](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).</span></span>

