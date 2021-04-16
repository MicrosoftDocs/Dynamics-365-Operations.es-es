---
title: Visión general de los contratos de nivel de servicio
description: En un contrato de nivel de servicio, el cliente acuerda un tiempo de respuesta mínimo desde que la empresa de servicios registra el problema y hasta que se resuelve el problema.
author: ShylaThompson
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServicelevelagreement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 55d65de5c041bd100bf8267bdbe3c5c5eb061a61
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835927"
---
# <a name="service-level-agreements-overview"></a><span data-ttu-id="7254b-103">Visión general de los contratos de nivel de servicio</span><span class="sxs-lookup"><span data-stu-id="7254b-103">Service level agreements overview</span></span>       

[!include [banner](../includes/banner.md)]


<span data-ttu-id="7254b-104">Un acuerdo de nivel de servicio (SLA) es un acuerdo entre una empresa de servicio y un cliente de servicio.</span><span class="sxs-lookup"><span data-stu-id="7254b-104">A service level agreement (SLA) is an agreement between a service company and a service customer.</span></span> <span data-ttu-id="7254b-105">En un SLA, el cliente acuerda un tiempo de respuesta mínimo desde que la empresa de servicios registra el problema y hasta que se resuelve el problema.</span><span class="sxs-lookup"><span data-stu-id="7254b-105">In a SLA, the customer agrees to a minimum response time based on when the service company records the issue and when the issue is resolved.</span></span>

<span data-ttu-id="7254b-106">Un SLA impone un modo estándar de servicio que se ofrece a los clientes e indica a una empresa de servicio cuándo debería realizar un trabajo de servicio.</span><span class="sxs-lookup"><span data-stu-id="7254b-106">A SLA enforces a standard level of service that is offered to customers, and also makes it transparent to a service company when a service job should be completed.</span></span>

<span data-ttu-id="7254b-107">Se puede crear el número de SLA que se desee para ofrecer a los clientes de servicio distintos niveles de servicio.</span><span class="sxs-lookup"><span data-stu-id="7254b-107">Any number of SLAs can be created to offer service customers different levels of service.</span></span>

## <a name="create-a-service-level-agreement"></a><span data-ttu-id="7254b-108">Crear un acuerdo de nivel de servicio</span><span class="sxs-lookup"><span data-stu-id="7254b-108">Create a service level agreement</span></span>

1.  <span data-ttu-id="7254b-109">Haga clic en **Gestión de servicio** \> **Configurar** \> **Contratos de servicio** \> **Contratos de nivel de servicio**.</span><span class="sxs-lookup"><span data-stu-id="7254b-109">Click **Service management** \> **Setup** \> **Service agreements** \> **Service level agreements**.</span></span>

2.  <span data-ttu-id="7254b-110">Escriba un nombre para el contrato de nivel de servicio en el campo **Contrato de nivel de servicio**.</span><span class="sxs-lookup"><span data-stu-id="7254b-110">Type a name for the service level agreement in the **Service level agreement** field.</span></span>

3.  <span data-ttu-id="7254b-111">Escriba el tiempo que desea asignar a la finalización de las llamadas de servicio vinculados al acuerdo de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="7254b-111">Type the time that you want to allow for completion of service calls that are attached to the service level agreement.</span></span> <span data-ttu-id="7254b-112">Seleccione un calendario si desea basar el contrato de nivel de servicio en un calendario específico.</span><span class="sxs-lookup"><span data-stu-id="7254b-112">Then select a calendar if you want to base the service level agreement on a specific calendar.</span></span>

## <a name="apply-a-service-level-agreement"></a><span data-ttu-id="7254b-113">Aplicar un acuerdo de nivel de servicio</span><span class="sxs-lookup"><span data-stu-id="7254b-113">Apply a service level agreement</span></span>

<span data-ttu-id="7254b-114">El SLA se aplica directamente a un acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="7254b-114">The SLA is applied directly to a service agreement.</span></span>

<span data-ttu-id="7254b-115">Los pedidos de servicio que crea manualmente y vincula a un acuerdo de servicio con un SLA se miden con este SLA.</span><span class="sxs-lookup"><span data-stu-id="7254b-115">Service orders that you create manually and attach to a service agreement that has an SLA are measured against that SLA.</span></span>

<span data-ttu-id="7254b-116">Los pedidos de servicio que cree automáticamente no se vinculan a un SLA.</span><span class="sxs-lookup"><span data-stu-id="7254b-116">Service orders that you create automatically are not attached to an SLA.</span></span>

## <a name="apply-the-service-level-agreement-to-the-service-agreement"></a><span data-ttu-id="7254b-117">Aplicar el acuerdo de nivel de servicio al acuerdo de servicio</span><span class="sxs-lookup"><span data-stu-id="7254b-117">Apply the service level agreement to the service agreement</span></span>

1.  <span data-ttu-id="7254b-118">Haga clic en **Gestión de servicio** \> **Común** \> **Contratos de servicio** \> **Contratos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="7254b-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span> <span data-ttu-id="7254b-119">Seleccione el acuerdo de servicio al que desea aplicar el SLA y, a continuación, haga clic en **Editar** en el **Panel de acciones**.</span><span class="sxs-lookup"><span data-stu-id="7254b-119">Select the service agreement that you want to apply the SLA to, and then click **Edit** on the **Action Pane**.</span></span>

2.  <span data-ttu-id="7254b-120">En el campo **Contrato de nivel de servicio**, seleccione el SLA que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="7254b-120">In the **Service level agreement** field, select the SLA that you want to assign.</span></span>

## <a name="apply-the-service-level-agreement-to-the-service-agreement-group"></a><span data-ttu-id="7254b-121">Aplicar el acuerdo de nivel de servicio al grupo de acuerdos de servicio</span><span class="sxs-lookup"><span data-stu-id="7254b-121">Apply the service level agreement to the service agreement group</span></span>

1.  <span data-ttu-id="7254b-122">Haga clic en **Gestión de servicio** \> **Configurar** \> **Contratos de servicio** \> **Grupos de contrato de servicio**.</span><span class="sxs-lookup"><span data-stu-id="7254b-122">Click **Service management** \> **Setup** \> **Service agreements** \> **Service agreement groups**.</span></span>

2.  <span data-ttu-id="7254b-123">En el campo **Contrato de nivel de servicio**, seleccione el SLA que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="7254b-123">In the **Service level agreement** field, select the SLA that you want to assign.</span></span>

## <a name="track-time-on-a-service-order-against-an-sla"></a><span data-ttu-id="7254b-124">Realizar un seguimiento del tiempo en un pedido de servicio contra un SLA</span><span class="sxs-lookup"><span data-stu-id="7254b-124">Track time on a service order against an SLA</span></span>

<span data-ttu-id="7254b-125">Cuando se crea un nuevo pedido de servicio para un acuerdo de servicio al cual se ha asignado un SLA, el intervalo de tiempo para la entrega del servicio se inicia y el sistema comienza a realizar un seguimiento del plazo de entrega.</span><span class="sxs-lookup"><span data-stu-id="7254b-125">When you create a new service order for a service agreement that an SLA is assigned to, the time interval for the delivery of the service is initiated, and the system starts to track the delivery time.</span></span> <span data-ttu-id="7254b-126">Además, puede configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="7254b-126">Additionally, you can set the following options:</span></span>

  - <span data-ttu-id="7254b-127">Puede iniciar y detener grabaciones de tiempo en el pedido de servicio para registrar el tiempo total que se dedica en pedidos de servicio.</span><span class="sxs-lookup"><span data-stu-id="7254b-127">You can start and stop time recording on the service order to register the total amount of time that is spent on service orders.</span></span>

  - <span data-ttu-id="7254b-128">Puede supervisar la conformidad con el intervalo de tiempo definido en el acuerdo de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="7254b-128">You can monitor compliance with the time interval that is set in the service level agreement.</span></span>

  - <span data-ttu-id="7254b-129">Puede definir códigos de motivo que se deban configurar si se supera el intervalo de tiempo del acuerdo de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="7254b-129">You can define reason codes that must be set if the time interval of the service level agreement is exceeded.</span></span>

## <a name="see-also"></a><span data-ttu-id="7254b-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7254b-130">See also</span></span>

[<span data-ttu-id="7254b-131">Ver conformidad con contratos de nivel de servicio</span><span class="sxs-lookup"><span data-stu-id="7254b-131">View compliance with service level agreements</span></span>](view-compliance-with-service-level-agreements.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]