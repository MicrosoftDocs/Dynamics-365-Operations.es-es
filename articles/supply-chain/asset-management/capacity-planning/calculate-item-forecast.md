---
title: Calcular previsión de artículo
description: En este tema se explica cómo calcular la previsión de artículo Administración de activos.
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
ms.openlocfilehash: 65d95507e27ade373008e2046ac4691c271484ca
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652457"
---
# <a name="calculate-item-forecast"></a><span data-ttu-id="f216e-103">Calcular previsión de artículo</span><span class="sxs-lookup"><span data-stu-id="f216e-103">Calculate item forecast</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="f216e-104">Al igual que puede crear los cálculos de la carga de capacidad, que se describe en la sección anterior, también puede crear cálculos de previsión de artículos en:</span><span class="sxs-lookup"><span data-stu-id="f216e-104">Just as you can make capacity load calculations, which are described in the previous section, you can also make item forecast calculations on:</span></span>

- <span data-ttu-id="f216e-105">líneas del programa de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="f216e-105">maintenance schedule lines</span></span>  
- <span data-ttu-id="f216e-106">órdenes de trabajo que aún no se han programado</span><span class="sxs-lookup"><span data-stu-id="f216e-106">work orders that have not yet been scheduled</span></span>  
- <span data-ttu-id="f216e-107">órdenes de trabajo programadas</span><span class="sxs-lookup"><span data-stu-id="f216e-107">scheduled work orders</span></span>

<span data-ttu-id="f216e-108">Esto resulta útil si desea obtener una visión general del consumo de artículos esperado (piezas de repuesto así como otros elementos requeridos para completar los pedidos de trabajo) para un período específico.</span><span class="sxs-lookup"><span data-stu-id="f216e-108">This is useful if you want to get an overview of expected item consumption (spare parts as well as other items required for completing work orders) for a specific period.</span></span> <span data-ttu-id="f216e-109">El cálculo de la previsión de artículo se puede realizar en todos los activos o los activos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="f216e-109">Calculation of item forecast can be done on all assets or selected assets.</span></span> <span data-ttu-id="f216e-110">También puede crear un cálculo en una actividad del tiempo de inactividad por mantenimiento (**Todas las actividades del tiempo de inactividad por mantenimiento** o **Actividades de tiempo de inactividad por mantenimiento activas**) o bien respecto a un conjunto de pedidos de trabajo (**Todos los grupos de órdenes de trabajo** o **Grupos de órdenes de trabajo activas**).</span><span class="sxs-lookup"><span data-stu-id="f216e-110">You can also make a calculation on a maintenance downtime activity (**All maintenance downtime activities** or **Active maintenance downtime activities**), or on a work order pool (**All work order pools** or **Active work order pools**).</span></span>

1. <span data-ttu-id="f216e-111">Haga clic en **Administración de activos** > **Consultas** > **Previsión de artículo** o **Administración de activos** > **Común** > **Grupos de órdenes de trabajo** > **Todos los grupos de órdenes de trabajo** / **Grupos de órdenes de trabajo activas** > seleccionar el grupo de órdenes de trabajo en la lista > botón **Previsión de artículo** o **Administración de activos** > **Común**  > **Actividades de tiempo de inactividad por mantenimiento** > **Todas las actividades de tiempo de inactividad por mantenimiento** / **Actividades de tiempo de inactividad por mantenimiento activas** > seleccione actividad de tiempo e inactividad por mantenimiento en la lista > botón **Previsión de artículo**.</span><span class="sxs-lookup"><span data-stu-id="f216e-111">Click **Asset management** > **Inquiries** > **Item forecast**, or **Asset management** > **Common** > **Work order pools** > **All work order pools** / **Active work order pools** > select work order pool in the list > **Item forecast** button, or **Asset management** > **Common** > **Maintenance downtime activities** > **All maintenance downtime activities** / **Active maintenance downtime activities** > select maintenance downtime activity in the list > **Item forecast** button.</span></span>

2. <span data-ttu-id="f216e-112">En el diálogo **Calcular la previsión de artículo**, seleccione un período para el cálculo en los campos **Fecha y hora de inicio** y los campos **Fecha y hora final**.</span><span class="sxs-lookup"><span data-stu-id="f216e-112">In the **Calculate item forecast** dialog, select a period for the calculation in the **Start date/time** and **End date/time** fields.</span></span>

3. <span data-ttu-id="f216e-113">Seleccione "Sí" en el botón de alternar **Incluir programación de mantenimiento** si desea incluir líneas de mantenimiento en el cálculo de la previsión.</span><span class="sxs-lookup"><span data-stu-id="f216e-113">Select "Yes" on the **Include maintenance schedule** toggle button if you want to include maintenance schedule lines in the forecast calculation.</span></span>

4. <span data-ttu-id="f216e-114">Seleccione "Sí" en el botón de alternar **Incluir orden de trabajo** si desea incluir trabajos de orden de trabajo en el cálculo de la previsión.</span><span class="sxs-lookup"><span data-stu-id="f216e-114">Select "Yes" on the **Include work order** toggle button if you want to include work order jobs in the forecast calculation.</span></span>

5. <span data-ttu-id="f216e-115">Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para las líneas de previsión de artículo con respecto a las ubicaciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="f216e-115">You can use the **Level** field to indicate how detailed you want the item forecast lines to be regarding functional locations.</span></span> 

      <span data-ttu-id="f216e-116">Por ejemplo, si especifica el número "1" en el campo, y tiene una estructura de ubicación técnica de varios niveles, todas líneas del programa de mantenimiento y órdenes de trabajo para una ubicación técnica se mostrarán en el nivel superior, y por tanto, las horas en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="f216e-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines and work orders for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
  
      <span data-ttu-id="f216e-117">Si especifica el número "0" en el campo **Nivel**, verá un resultado detallado que muestra todas las líneas del programa de mantenimiento y todas las órdenes de trabajo en todos los niveles de la ubicación técnica con el que están relacionadas.</span><span class="sxs-lookup"><span data-stu-id="f216e-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines and all work orders on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="f216e-118">Haga clic en **Aceptar** para iniciar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="f216e-118">Click **OK** to start the calculation.</span></span>

7. <span data-ttu-id="f216e-119">En los grupos **Agrupar por...**, haga clic en los botones relevantes para mostrar el nivel de detalle necesario del cálculo.</span><span class="sxs-lookup"><span data-stu-id="f216e-119">In the **Group by...** groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="f216e-120">En la captura de pantalla siguiente, los botones **Agrupar por** seleccionados se destacan en color azul.</span><span class="sxs-lookup"><span data-stu-id="f216e-120">In the screenshot below, the selected **Group by** buttons are highlighted in blue color.</span></span> <span data-ttu-id="f216e-121">Haga clic en un botón para activarlo o desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="f216e-121">Click on a button to activate or deactivate it.</span></span>

8. <span data-ttu-id="f216e-122">Haga clic en el botón **Mostrar dimensiones** si desea ver el producto, el almacenamiento o las dimensiones de seguimiento relacionadas con los artículos.</span><span class="sxs-lookup"><span data-stu-id="f216e-122">Click the **Display dimensions** button if you want to see the product, storage, or tracking dimensions related to the items.</span></span> <span data-ttu-id="f216e-123">Seleccione las casillas de verificación relevantes y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f216e-123">Select the relevant check boxes, and click **OK**.</span></span>

![Figura 1](media/02-capacity-planning.png)
