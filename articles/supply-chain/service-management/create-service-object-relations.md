---
title: Crear relaciones de objetos de servicio
description: Este tema describe cómo crear relaciones de objeto de servicio para un acuerdo de servicio y para un pedido de servicio.
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
ms.openlocfilehash: 380514b6e95292597d3eb52ce191d1e282e154ce
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965914"
---
# <a name="create-service-object-relations"></a><span data-ttu-id="f1332-103">Crear relaciones de objetos de servicio</span><span class="sxs-lookup"><span data-stu-id="f1332-103">Create service object relations</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f1332-104">Este tema describe cómo crear relaciones de objeto de servicio para un acuerdo de servicio y para un pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="f1332-104">This topic describes how to create service object relations for a service agreement and a service order.</span></span> <span data-ttu-id="f1332-105">Al crear una relación de objeto de servicio, se asocia el objeto de servicio a un acuerdo de servicio o un pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="f1332-105">When you a create service object relation, you associate the service object to a service agreement or service order.</span></span> <span data-ttu-id="f1332-106">Cuando un cliente solicite el servicio para un artículo que sea un objeto de servicio, puede seleccionar el objeto de servicio en la lista de relaciones de objetos de servicio.</span><span class="sxs-lookup"><span data-stu-id="f1332-106">When a customer requests service for an item that is a service object, you can select the service object from the list of service object relations.</span></span>

## <a name="create-a-service-object-relation-for-a-service-agreement"></a><span data-ttu-id="f1332-107">Crear una relación de objetos de servicio para un acuerdo de servicio</span><span class="sxs-lookup"><span data-stu-id="f1332-107">Create a service object relation for a service agreement</span></span>

<span data-ttu-id="f1332-108">Siga estos pasos para crear una relación de objeto de servicio para un acuerdo de servicio:</span><span class="sxs-lookup"><span data-stu-id="f1332-108">Use the following steps to create a service object relation for a service agreement:</span></span>

1.  <span data-ttu-id="f1332-109">Haga clic en **Gestión de servicio** \> **Común** \> **Contratos de servicio** \> **Contratos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="f1332-109">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="f1332-110">En la lista de **Acuerdos de servicio**, seleccione un acuerdo de servicio existente o haga clic en **Nuevo** para crear un nuevo acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="f1332-110">In the **Service agreements** list, select an existing service agreement, or click **New** to create a new service agreement.</span></span>

3.  <span data-ttu-id="f1332-111">En el formulario **Acuerdos de servicio**, en el **Panel de acciones**, en la pestaña **Contrato de servicio**, en el grupo **Relaciones**, haga clic en **Objetos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="f1332-111">In the **Service agreements** form, on the **Action Pane**, on the **Service agreement** tab, in the **Relations** group, click **Service objects**.</span></span>

4.  <span data-ttu-id="f1332-112">En el formulario **Objetos de servicio**, haga clic en **Nuevo** y, a continuación, seleccione un objeto de servicio para este contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="f1332-112">In the **Service objects** form, click **New**, and then select a service object for this service agreement.</span></span>

5.  <span data-ttu-id="f1332-113">Para asignar una lista de materiales (L. MAT) de plantilla al acuerdo de servicio, haga clic en **Funciones** y, a continuación, seleccione **Adjuntar L.MAT de plantilla**.</span><span class="sxs-lookup"><span data-stu-id="f1332-113">To assign a template bill of materials (BOM) to the service agreement, click **Functions**, and then select **Attach template BOM**.</span></span> <span data-ttu-id="f1332-114">En el formulario **Seleccionar L.MAT de plantilla**, en el campo **Plantilla de L.MAT**, seleccione una plantilla.</span><span class="sxs-lookup"><span data-stu-id="f1332-114">In the **Select template BOM** form, in the **Template BOM** field, select a template.</span></span> 

## <a name="create-a-service-object-relation-for-a-service-order"></a><span data-ttu-id="f1332-115">Crear una relación de objetos de servicio para un pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="f1332-115">Create a service object relation for a service order</span></span>

<span data-ttu-id="f1332-116">Siga estos pasos para crear una relación de objeto de servicio para un pedido de servicio:</span><span class="sxs-lookup"><span data-stu-id="f1332-116">Use the following steps to create a service object relation for a service order:</span></span>

1.  <span data-ttu-id="f1332-117">Haga clic en **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="f1332-117">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="f1332-118">En la lista **Pedidos de servicio**, seleccione un pedido de servicio existente o cree un nuevo pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="f1332-118">In the **Service orders** list, select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="f1332-119">En el formulario **Pedidos de servicio**, en el **Panel de acciones**, en la pestaña **Pedido de servicio**, en el grupo **Relaciones**, haga clic en **Objetos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="f1332-119">In the **Service orders** form, on the **Action Pane**, on the **Service order** tab, in the **Relations** group, click **Service objects**.</span></span>

4.  <span data-ttu-id="f1332-120">En el formulario **Objetos de servicio**, haga clic en **Nuevo** y, a continuación, seleccione un objeto de servicio para este pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="f1332-120">In the **Service objects** form, click **New**, and then select a service object for this service order.</span></span>

5.  <span data-ttu-id="f1332-121">Para asignar una L. MAT de plantilla al acuerdo de servicio, haga clic en **Funciones** y, a continuación, seleccione **Adjuntar L.MAT de plantilla**.</span><span class="sxs-lookup"><span data-stu-id="f1332-121">To assign a template BOM to the service agreement, click **Functions**, and then select **Attach template BOM**.</span></span> <span data-ttu-id="f1332-122">En el formulario **Seleccionar L.MAT de plantilla**, en el campo **Plantilla de L.MAT**, seleccione una plantilla.</span><span class="sxs-lookup"><span data-stu-id="f1332-122">In the **Select template BOM** form, in the **Template BOM** field, select a template.</span></span> 


## <a name="see-also"></a><span data-ttu-id="f1332-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1332-123">See also</span></span>

[<span data-ttu-id="f1332-124">Visión genera de los objetos de servicio</span><span class="sxs-lookup"><span data-stu-id="f1332-124">Service objects overview</span></span>](service-objects.md)

[<span data-ttu-id="f1332-125">Relaciones de objetos de servicio</span><span class="sxs-lookup"><span data-stu-id="f1332-125">Service object relations</span></span>](service-object-relations.md)

[<span data-ttu-id="f1332-126">Plantilla de L. MAT</span><span class="sxs-lookup"><span data-stu-id="f1332-126">Template BOMs</span></span>](template-boms.md)

  


