---
title: Crear relaciones de tareas de servicio
description: Puede asociar tareas de servicio con contratos de servicio o pedidos de servicio para describir la tarea de servicio para completar el contrato o pedido.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ea5952376fe30f489d385c8f8295fbf86f2af085
ms.sourcegitcommit: 34b8f6f5c6134b7b97a9fb41d0b2e63215c67062
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470746"
---
# <a name="create-service-task-relations"></a><span data-ttu-id="9adc7-103">Crear relaciones de tareas de servicio</span><span class="sxs-lookup"><span data-stu-id="9adc7-103">Create service task relations</span></span>    

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9adc7-104">Puede asociar tareas de servicio con contratos de servicio o pedidos de servicio para describir la tarea de servicio para completar el contrato o pedido.</span><span class="sxs-lookup"><span data-stu-id="9adc7-104">You can associate service tasks with service agreements or service orders in order to describe the service task to be completed for the agreement or order.</span></span> <span data-ttu-id="9adc7-105">Esta información está disponible para técnicos de servicio y clientes.</span><span class="sxs-lookup"><span data-stu-id="9adc7-105">This information is available to service technicians and customers.</span></span>

## <a name="create-a-relation-with-a-service-agreement"></a><span data-ttu-id="9adc7-106">Crear una relación con un acuerdo de servicio</span><span class="sxs-lookup"><span data-stu-id="9adc7-106">Create a relation with a service agreement</span></span>

1.  <span data-ttu-id="9adc7-107">Vaya a **Gestión de servicio** \> **Común** \> **Contratos de servicio** \> **Contratos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="9adc7-107">Go to **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="9adc7-108">Seleccione un acuerdo de servicio existente o cree uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="9adc7-108">Select an existing service agreement, or create a new service agreement.</span></span>

3.  <span data-ttu-id="9adc7-109">En el panel de acciones, seleccione el botón **Tareas de servicio**.</span><span class="sxs-lookup"><span data-stu-id="9adc7-109">On the Action Pane, select the **Service tasks** button.</span></span>

4.  <span data-ttu-id="9adc7-110">En el formulario **Tareas de servicio**, seleccione **Nuevo** para crear una nueva línea y, a continuación, seleccione una tarea de servicio desde la lista **Tarea de servicio** para adjuntar la tarea de servicio al acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="9adc7-110">On the **Service tasks** form, select **New** to create a new line, and then select a service task from the **Service task** list to attach the service task to the service agreement.</span></span>

5.  <span data-ttu-id="9adc7-111">En los campos de texto sin formato de la ficha **Descripción**, especifique las descripciones de nota interna o externa.</span><span class="sxs-lookup"><span data-stu-id="9adc7-111">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="9adc7-112">Cierre el formulario para guardar el registro.</span><span class="sxs-lookup"><span data-stu-id="9adc7-112">Close the form to save the record.</span></span>

<span data-ttu-id="9adc7-113">Repita este procedimiento hasta haber creado todas las relaciones de tarea de servicio para el acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="9adc7-113">Repeat this procedure until you have created all the necessary service task relations for the service agreement.</span></span> <span data-ttu-id="9adc7-114">A continuación, podrá especificar estas tareas para cualquiera de las líneas del acuerdo vinculadas.</span><span class="sxs-lookup"><span data-stu-id="9adc7-114">You can now specify these service tasks for any attached agreement lines.</span></span>

<span data-ttu-id="9adc7-115">Una relación de tareas de servicio creada en un acuerdo de servicio estará disponible en todos los pedidos de servicio vinculados al acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="9adc7-115">A service tasks relation that is created on a service agreement is available from all service orders that are attached to the service agreement.</span></span>

## <a name="create-a-relation-with-a-service-order"></a><span data-ttu-id="9adc7-116">Crear una relación con un pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="9adc7-116">Create a relation with a service order</span></span>

1.  <span data-ttu-id="9adc7-117">Vaya a **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="9adc7-117">Go to **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="9adc7-118">Seleccione un pedido de servicio existente o cree uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="9adc7-118">Select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="9adc7-119">En el panel de acciones, seleccione el botón **Tareas de servicio**.</span><span class="sxs-lookup"><span data-stu-id="9adc7-119">On the Action Pane, select the **Service tasks** button.</span></span>

4.  <span data-ttu-id="9adc7-120">En el formulario **Tareas de servicio**, seleccione **Nuevo** para crear una nueva línea y, a continuación, seleccione una tarea de servicio desde la lista **Tarea de servicio** para adjuntar las tareas de servicio al pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="9adc7-120">From the **Service tasks** form, select **New** to create a new line, and then select a service task from the **Service task** list to attach the service tasks to the service order.</span></span>

5.  <span data-ttu-id="9adc7-121">En los campos de texto sin formato de la ficha **Descripción**, especifique las descripciones de nota interna o externa.</span><span class="sxs-lookup"><span data-stu-id="9adc7-121">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="9adc7-122">Cierre el formulario para guardar el registro.</span><span class="sxs-lookup"><span data-stu-id="9adc7-122">Close the form to save the record.</span></span>

<span data-ttu-id="9adc7-123">Repita este procedimiento hasta haber creado todas las relaciones de tarea de servicio para el acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="9adc7-123">Repeat this procedure until you have created all the necessary service task relations for the service order.</span></span> <span data-ttu-id="9adc7-124">A continuación, podrá seleccionar la tarea de servicio para la que creó la relación al crear las líneas de pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="9adc7-124">You can now select the service task for which you have created the relation when you create service order lines.</span></span>

<span data-ttu-id="9adc7-125">Las relaciones de tarea de servicio creadas en un pedido de servicio estarán disponibles en el pedido de servicio específico.</span><span class="sxs-lookup"><span data-stu-id="9adc7-125">Service task relations that are created on a service order are available on the specific service order.</span></span>

## <a name="see-also"></a><span data-ttu-id="9adc7-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9adc7-126">See also</span></span>

[<span data-ttu-id="9adc7-127">Visión general de las tareas de servicio</span><span class="sxs-lookup"><span data-stu-id="9adc7-127">Service tasks overview</span></span>](service-tasks.md)


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]