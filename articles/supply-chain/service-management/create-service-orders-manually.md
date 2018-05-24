---
title: Crear pedidos de servicio manualmente
description: Es posible crear pedidos de servicio manualmente mediante un acuerdo de servicio o mediante el formulario **Pedidos de servicio**.
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
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
ms.openlocfilehash: a0cc6b2646929776f4efb20474de6b0fc5c4719c
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="create-service-orders-manually"></a><span data-ttu-id="4790a-103">Crear pedidos de servicio manualmente</span><span class="sxs-lookup"><span data-stu-id="4790a-103">Create service orders manually</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="4790a-104">Es posible crear pedidos de servicio manualmente mediante un acuerdo de servicio o mediante el formulario **Pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="4790a-104">You can create service orders manually by using a service agreement or by using the **Service orders** form.</span></span> <span data-ttu-id="4790a-105">También podrá crear un pedido de servicio a partir de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="4790a-105">You can also create a service order from a project.</span></span>

> [!TIP]
> <P><span data-ttu-id="4790a-106">Puede utilizar procesos automatizados para crear pedidos de servicio.</span><span class="sxs-lookup"><span data-stu-id="4790a-106">You can use automated processes to create service orders.</span></span> 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a><span data-ttu-id="4790a-107">Crear un pedido de servicio manualmente a partir de un acuerdo de servicio</span><span class="sxs-lookup"><span data-stu-id="4790a-107">Create a service order manually from a service agreement</span></span>

1.  <span data-ttu-id="4790a-108">Haga clic en **Gestión de servicio** \> **Común** \> **Contratos de servicio** \> **Contratos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="4790a-108">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="4790a-109">Seleccione un acuerdo de servicio o cree uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="4790a-109">Select a service agreement or create a new service agreement.</span></span>

3.  <span data-ttu-id="4790a-110">Haga clic en la pestaña **Entregar** y en el grupo **Crear** haga clic en **Pedidos de servicio planificados** para abrir el formulario **Crear pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="4790a-110">Click the **Deliver** tab and in the **Create** group click **Planned service orders** to open the **Create service orders** form.</span></span>

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a><span data-ttu-id="4790a-111">Crear un pedido de servicio manualmente en el formulario de pedidos de servicio</span><span class="sxs-lookup"><span data-stu-id="4790a-111">Create a service order manually in the Service orders form</span></span>

1.  <span data-ttu-id="4790a-112">Haga clic en **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="4790a-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="4790a-113">Presione Ctrl+N para crear un nuevo pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="4790a-113">Press Ctrl+N to create a new service order.</span></span>

3.  <span data-ttu-id="4790a-114">Cree las líneas del pedido de servicio para el pedido.</span><span class="sxs-lookup"><span data-stu-id="4790a-114">Create service order lines for the service order.</span></span>

> [!NOTE]
> <P><span data-ttu-id="4790a-115">Si la casilla de verificación <STRONG>Permitir sin acuerdo de servicio</STRONG> del formulario <STRONG>Parámetros de la gestión de servicio</STRONG> está activada, podrá registrar las transacciones desde las líneas del pedido de servicio sin adjuntar el pedido de servicio a un acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="4790a-115">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="4790a-116">Si la casilla de verificación no está marcada, deberá adjuntar el pedido de servicio creado manualmente a un proyecto antes de registrar las líneas del pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="4790a-116">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-a-project"></a><span data-ttu-id="4790a-117">Crear un pedido de servicio desde un proyecto</span><span class="sxs-lookup"><span data-stu-id="4790a-117">Create a service order from a project</span></span>

1.  <span data-ttu-id="4790a-118">Haga clic en **Gestión de proyectos y contabilidad** \> **Común** \> **Proyectos** \> **Todos los proyectos**.</span><span class="sxs-lookup"><span data-stu-id="4790a-118">Click **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="4790a-119">En el formulario **Proyectos**, en el **Panel de acciones**, haga clic en la ficha **Administrar** \> haga clic en **Servicio** \> **Pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="4790a-119">In the **Projects** form, on the **Action pane**, click the **Manage** tab \> click **Service** \> **Service orders**.</span></span>

3.  <span data-ttu-id="4790a-120">Siga el procedimiento anterior para crear un pedido de servicio manualmente en el formulario **Pedidos de Servicio**.</span><span class="sxs-lookup"><span data-stu-id="4790a-120">Follow the previous procedure to create a service order manually in the **Service orders** form.</span></span> <span data-ttu-id="4790a-121">El campo **Id. de proyecto** muestra la referencia del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4790a-121">The **Project ID** field displays the project reference.</span></span>

> [!NOTE]
> <P><span data-ttu-id="4790a-122">Si la casilla de verificación <STRONG>Permitir sin acuerdo de servicio</STRONG> del formulario <STRONG>Parámetros de la gestión de servicio</STRONG> está activada, podrá registrar las transacciones desde las líneas del pedido de servicio sin adjuntar el pedido de servicio a un acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="4790a-122">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="4790a-123">Si la casilla de verificación no está marcada, deberá adjuntar el pedido de servicio creado manualmente a un proyecto antes de registrar las líneas del pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="4790a-123">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-the-sales-order-form"></a><span data-ttu-id="4790a-124">Crear un pedido de servicio desde el formulario de pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="4790a-124">Create a service order from the Sales order form</span></span>

<span data-ttu-id="4790a-125">Puede crear un pedido de servicio desde el formulario **Pedidos de ventas** mediante el asistente **Crear un nuevo pedido de servicio basado en el pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="4790a-125">You can create a service order from the **Sales orders** form by using the **Create a new service order based on the sales order** wizard.</span></span>

1.  <span data-ttu-id="4790a-126">Haga clic en **Ventas y marketing** \> **Común** \> **Pedidos de ventas** \> **Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="4790a-126">Click **Sales and marketing** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="4790a-127">Abra el pedido de ventas pertinente.</span><span class="sxs-lookup"><span data-stu-id="4790a-127">Open the relevant sales order.</span></span>

3.  <span data-ttu-id="4790a-128">En la pestaña **pedido de ventas**, haga clic en **Pedido de servicio** para iniciar el asistente **Crear un nuevo pedido de servicio basado en el pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="4790a-128">On the **Sales order** tab, click **Service order** to start the **Create a new service order based on the sales order** wizard.</span></span>

4.  <span data-ttu-id="4790a-129">Haga clic en **Siguiente \>**, y ejecute los pasos siguientes en la página **Seleccionar acuerdo para pedido de servicio**:</span><span class="sxs-lookup"><span data-stu-id="4790a-129">Click **Next \>**, and then complete the following steps on the **Select agreement for service order** page:</span></span>
    
      - <span data-ttu-id="4790a-130">Use el campo **Acuerdo de servicio** para seleccionar el acuerdo de servicio al que desea asociar el pedido de servicio nuevo.</span><span class="sxs-lookup"><span data-stu-id="4790a-130">Use the **Service agreement** field to select the service agreement with which the new service order should be associated.</span></span>
    
      - <span data-ttu-id="4790a-131">Opcional: use el campo **Id. de proyecto** para asociar este pedido de servicio a un proyecto particular.</span><span class="sxs-lookup"><span data-stu-id="4790a-131">Optional: Use the **Project ID** field to associate this service order with a particular project.</span></span>

5.  <span data-ttu-id="4790a-132">Haga clic en **Siguiente \>**, y ejecute los pasos siguientes en la página **Crear pedido de servicio**:</span><span class="sxs-lookup"><span data-stu-id="4790a-132">Click **Next \>**, and then complete the following steps on the **Create service order** page:</span></span>
    
      - <span data-ttu-id="4790a-133">Especifique una fecha y una hora de inicio para la llamada de servicio en el campo **Hora de servicio preferida**.</span><span class="sxs-lookup"><span data-stu-id="4790a-133">Enter a date and time for the service call to begin in the **Preferred service time** field.</span></span>
    
      - <span data-ttu-id="4790a-134">Opcional: modifique el texto en el campo **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="4790a-134">Optional: Modify the text in the **Description** field.</span></span> <span data-ttu-id="4790a-135">De forma predeterminado, este campo contiene la descripción del acuerdo de servicio que seleccionó en la página anterior.</span><span class="sxs-lookup"><span data-stu-id="4790a-135">By default, this field contains the description of the service agreement that you selected on the previous page.</span></span>
    
      - <span data-ttu-id="4790a-136">En el campo **Responsable**, seleccione el identificador del empleado responsable del contrato, y si lo conoce, especifique el identificador del técnico preferido del cliente para la llamada de servicio.</span><span class="sxs-lookup"><span data-stu-id="4790a-136">In the **Responsible** field, select the ID of the employee who is responsible for the agreement, and if you know what it is, enter the ID of the customer's preferred technician for the service call.</span></span>
    
      - <span data-ttu-id="4790a-137">En el campo **Id. de contacto**, seleccione la persona de la empresa del cliente con la que se debe poner en contacto en relación con este pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="4790a-137">In the **Contact ID** field, select the person in the customer's company who should be contacted regarding this service order.</span></span>

6.  <span data-ttu-id="4790a-138">Haga clic en **Siguiente\>** y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4790a-138">Click **Next \>**, and then click **Finish**.</span></span>


## <a name="see-also"></a><span data-ttu-id="4790a-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4790a-139">See also</span></span>

[<span data-ttu-id="4790a-140">Pedidos de servicio</span><span class="sxs-lookup"><span data-stu-id="4790a-140">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="4790a-141">Crear pedidos de servicio automáticamente</span><span class="sxs-lookup"><span data-stu-id="4790a-141">Create service orders automatically</span></span>](create-service-orders-automatically.md)

<span data-ttu-id="4790a-142">[Crear pedidos de servicio (formulario de clase)](https://technet.microsoft.com/en-us/library/aa553901\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="4790a-142">[Create service orders (class form)](https://technet.microsoft.com/en-us/library/aa553901\(v=ax.60\))</span></span> 


