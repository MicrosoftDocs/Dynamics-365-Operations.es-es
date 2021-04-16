---
title: Cancelar pedidos de servicio
description: Puede cancelar un pedido de servicio o línea de pedido de servicio desde el propio pedido o cancelar varios pedidos de servicio mediante un trabajo periódico.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 779f535ac617d3f3940cc1b226fa53dc72e3411a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831611"
---
# <a name="cancel-service-orders"></a><span data-ttu-id="3be41-103">Cancelar pedidos de servicio</span><span class="sxs-lookup"><span data-stu-id="3be41-103">Cancel service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="3be41-104">Puede cancelar un pedido de servicio o línea de pedido de servicio desde el propio pedido o cancelar varios pedidos de servicio mediante un trabajo periódico.</span><span class="sxs-lookup"><span data-stu-id="3be41-104">You can cancel a service order or service order line from the service order itself, or you can cancel multiple service orders by running a periodic job.</span></span>


> [!NOTE]
> <P><span data-ttu-id="3be41-105">Los pedidos de servicio no se pueden cancelar si la etapa del pedido de servicio no permite la cancelación, si el pedido de servicio tiene requisitos de artículos o si el pedido de servicio ya se ha registrado.</span><span class="sxs-lookup"><span data-stu-id="3be41-105">Service orders cannot be canceled if the stage of the service order does not allow cancelation, if the service order has item requirements, or if the service order has already been posted.</span></span></P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a><span data-ttu-id="3be41-106">Cancelar un pedido de servicio desde el formulario Pedidos de servicio</span><span class="sxs-lookup"><span data-stu-id="3be41-106">Cancel a service order in the Service orders form</span></span>

1.  <span data-ttu-id="3be41-107">Haga clic en **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="3be41-107">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span> <span data-ttu-id="3be41-108">Seleccione el pedido de servicio y haga clic en **Cancelar pedido** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="3be41-108">Select the service order, and on the Action Pane, click **Cancel order**.</span></span>

## <a name="cancel-a-service-order-line"></a><span data-ttu-id="3be41-109">Cancelar una línea de pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="3be41-109">Cancel a service order line</span></span>

1.  <span data-ttu-id="3be41-110">Haga clic en **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="3be41-110">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span> <span data-ttu-id="3be41-111">Haga doble clic en el pedido de servicio que contiene la línea que desee cancelar.</span><span class="sxs-lookup"><span data-stu-id="3be41-111">Double-click the service order that contains the line you want to cancel.</span></span>

2.  <span data-ttu-id="3be41-112">Seleccione la línea del pedido de servicio que desea cancelar y, a continuación, haga clic en **Cancelar línea de pedido** para cambiar el estado de la línea a **Cancelado**.</span><span class="sxs-lookup"><span data-stu-id="3be41-112">Select the service order line that you want to cancel, and then click **Cancel order line** to change the status of the line to **Canceled**.</span></span>


> [!TIP]
> <P><span data-ttu-id="3be41-113">Para invertir la cancelación de una línea de pedido de servicio y volver a cambiar el estado a <STRONG>Creada</STRONG>, haga clic en <STRONG>Revocar cancelación</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3be41-113">To reverse the cancellation of a service order line and change the status back to <STRONG>Created</STRONG>, click <STRONG>Revoke cancel</STRONG>.</span></span></P>


## <a name="cancel-multiple-service-orders"></a><span data-ttu-id="3be41-114">Cancelación de varios pedidos de servicio</span><span class="sxs-lookup"><span data-stu-id="3be41-114">Cancel multiple service orders</span></span>

1.  <span data-ttu-id="3be41-115">Haga clic en **Gestión de servicio** \> **Periódico** \> **Pedidos de servicio** \> **Cancelar pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="3be41-115">Click **Service management** \> **Periodic** \> **Service orders** \> **Cancel service orders**.</span></span>

2.  <span data-ttu-id="3be41-116">Haga clic en el botón **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="3be41-116">Click the **Select** button.</span></span>

3.  <span data-ttu-id="3be41-117">En el formulario **Consulta**, en la columna **Criterios**, seleccione los pedidos de servicio que desee cancelar.</span><span class="sxs-lookup"><span data-stu-id="3be41-117">In the **Inquiry** form, in the **Criteria** column, select the service orders that you want to cancel.</span></span>

4.  <span data-ttu-id="3be41-118">Haga clic en **Aceptar** para cerrar el formulario **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="3be41-118">Click **OK** to close the **Inquiry** form.</span></span>

5.  <span data-ttu-id="3be41-119">Active la casilla **Mostrar registro de información** para generar un registro de información con los pedidos de servicio cancelados.</span><span class="sxs-lookup"><span data-stu-id="3be41-119">Select the **Show Infolog** check box to generate an Infolog that lists the canceled service orders.</span></span>

6.  <span data-ttu-id="3be41-120">Active la casilla **Revocar cancelación** para invertir el estado **Cancelado** de un pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="3be41-120">Select the **Revoke cancel** check box if you want to reverse the **Canceled** status of a service order.</span></span>

7.  <span data-ttu-id="3be41-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3be41-121">Click **OK**.</span></span>

<span data-ttu-id="3be41-122">Los pedidos de servicio seleccionados se cancelarán o su estado de progreso de **Cancelado** se ha invertido a **En proceso**.</span><span class="sxs-lookup"><span data-stu-id="3be41-122">The selected service orders are either canceled or their progress status of **Canceled** has been reversed to **In process**.</span></span>


> [!NOTE]
> <P><span data-ttu-id="3be41-123">Si activa la casilla <STRONG>Revocar cancelación</STRONG>, los pedidos de servicio con el estado de progreso <STRONG>Cancelado</STRONG> se invertirán y no se producirá ninguna cancelación de pedidos de servicio con el estado <STRONG>En proceso</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3be41-123">If you select the <STRONG>Revoke cancel</STRONG> check box, service orders with a progress status of <STRONG>Canceled</STRONG> are reversed and service orders with a progress status of <STRONG>In process</STRONG> are not canceled.</span></span></P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]