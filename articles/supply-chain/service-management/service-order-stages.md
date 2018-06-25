---
title: Etapas de pedido de servicio
description: "Al definir etapas para un pedido de servicio y asignarlas a los trabajadores, puede controlar el flujo de un pedido de servicio a través de las tareas que diferentes personas realizan en la organización de servicio."
author: YuyuScheller
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 9aa90dfcfc4b30d6cb4fa7ed4e6faaf505548d41
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="service-order-stages"></a><span data-ttu-id="59be7-103">Etapas de pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="59be7-103">Service order stages</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="59be7-104">Puede establecer etapas en un pedido de servicio para definir las tareas que se deben completar, el orden en el que se completarán y los trabajadores responsables de completarlas.</span><span class="sxs-lookup"><span data-stu-id="59be7-104">You can set up stages for a service order to define the tasks that must be completed, the order in which they are completed, and the workers who are responsible for completing them.</span></span> <span data-ttu-id="59be7-105">Al definir etapas para un pedido de servicio y asignarlas a los trabajadores, puede controlar el flujo de un pedido de servicio a través de las tareas que diferentes personas realizan en la organización de servicio.</span><span class="sxs-lookup"><span data-stu-id="59be7-105">By defining the stages for a service order and assigning them to workers, you can control the flow of a service order through the tasks that various people perform in the service organization.</span></span> <span data-ttu-id="59be7-106">La secuencia de etapas debe incluir una etapa inicial.</span><span class="sxs-lookup"><span data-stu-id="59be7-106">The sequence of stages must include an initial stage.</span></span>

<span data-ttu-id="59be7-107">También puede definir las acciones que están permitidas en cada etapa.</span><span class="sxs-lookup"><span data-stu-id="59be7-107">You can also define the actions that are permitted at each stage.</span></span> <span data-ttu-id="59be7-108">Por ejemplo, si desactiva la casilla de verificación **Registrar** en todas las etapas, excepto la última, evita el registro de pedidos de servicio antes de que estos se hayan procesado en toda la secuencia de etapas.</span><span class="sxs-lookup"><span data-stu-id="59be7-108">For example, if you clear the **Post** check box for all stages except the final stage, you prevent any service orders from being posted before the service orders are processed through the complete sequence of stages.</span></span>

## <a name="branching-in-service-order-stages"></a><span data-ttu-id="59be7-109">Ramificación de las etapas de pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="59be7-109">Branching in service order stages</span></span>

<span data-ttu-id="59be7-110">Cuando configure una etapa de servicio, puede crear varias opciones, o ramas, para seleccionar para la siguiente etapa de servicio.</span><span class="sxs-lookup"><span data-stu-id="59be7-110">When you set up a service stage, you can create multiple options, or branches, to select from for the next service stage.</span></span> <span data-ttu-id="59be7-111">Todas las ramas que cree estarán disponibles para seleccionarlas cuando la etapa inicial se complete.</span><span class="sxs-lookup"><span data-stu-id="59be7-111">All the branches that you create are available to select from when the initial stage is completed.</span></span> <span data-ttu-id="59be7-112">Por ejemplo, configure **Planificación** como etapa inicial.</span><span class="sxs-lookup"><span data-stu-id="59be7-112">For example, you set up **Planning** as an initial stage.</span></span> <span data-ttu-id="59be7-113">Cree dos etapas denominadas **En proceso** y **Cancelar**, y seleccione **Planificación** como etapa principal para ellas.</span><span class="sxs-lookup"><span data-stu-id="59be7-113">You create two stages named **In process** and **Cancel**, and then select **Planning** as the parent for them.</span></span> <span data-ttu-id="59be7-114">Asigne la etapa **Planificación** al pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="59be7-114">You assign the **Planning** stage to sales order.</span></span> <span data-ttu-id="59be7-115">Cuando la etapa de planificación para el pedido de ventas se complete, podrá seleccionar la etapa **En proceso** si el pedido de ventas está listo para trabajar en él, o puede seleccionar la etapa **Cancelar** si el pedido de ventas se ha cancelado.</span><span class="sxs-lookup"><span data-stu-id="59be7-115">When the planning stage for the sales order is completed, you can select the **In process** stage if the sales order is ready to work on, or you can select the **Cancel** stage if the sales order is canceled.</span></span>

## <a name="see-also"></a><span data-ttu-id="59be7-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59be7-116">See also</span></span>

[<span data-ttu-id="59be7-117">Configurar las etapas de pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="59be7-117">Set up service order stages</span></span>](set-up-service-order-stages.md)

[<span data-ttu-id="59be7-118">Cambiar la etapa del pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="59be7-118">Change the service order stage</span></span>](change-service-order-stage.md)

  


