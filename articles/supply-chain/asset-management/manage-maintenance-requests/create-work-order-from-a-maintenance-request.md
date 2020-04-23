---
title: Crear órdenes de trabajo a partir de solicitudes de mantenimiento
description: En este tema se explica cómo crear una orden de trabajo a partir de una solicitud de mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b6bd98796140ab7aa3e7813ff1526413504554c5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205216"
---
# <a name="create-work-orders-from-maintenance-requests"></a><span data-ttu-id="4c58b-103">Crear órdenes de trabajo a partir de solicitudes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="4c58b-103">Create work orders from maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="4c58b-104">Después de crear solicitudes de mantenimiento, puede convertirlas fácilmente en órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c58b-104">After you've created maintenance requests, you can easily convert them to work orders.</span></span> <span data-ttu-id="4c58b-105">En este tema se describe la forma más rápida de trabajar con solicitudes de mantenimiento, actualiza varias solicitudes de mantenimiento al mismo tiempo y crear una orden de trabajo para varias solicitudes de mantenimiento a la vez.</span><span class="sxs-lookup"><span data-stu-id="4c58b-105">This topic describes the quickest way to work with maintenance requests, update several maintenance requests at the same time, and then create a work order for several maintenance requests at the same time.</span></span> <span data-ttu-id="4c58b-106">En **Solicitudes de mantenimiento activas** o en la página **Mis solicitudes de mantenimiento de ubicación técnica** también puede trabajar con una solicitud de mantenimiento a la vez y convertir una solicitud de mantenimiento en una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c58b-106">On the **Active maintenance requests** or **My functional location maintenance requests** page, you can also work with one maintenance request at a time and convert one maintenance request to a work order.</span></span>

> [!NOTE]
> <span data-ttu-id="4c58b-107">Cada solicitud de mantenimiento puede relacionarse únicamente con una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c58b-107">Every maintenance request can be related to only one work order.</span></span> <span data-ttu-id="4c58b-108">Sin embargo, se pueden incluir varias solicitudes de mantenimiento en una orden de trabajo, aunque las solicitudes de mantenimiento tenga activos diferentes.</span><span class="sxs-lookup"><span data-stu-id="4c58b-108">However, multiple maintenance requests can be included in one work order, even if the maintenance requests have different assets.</span></span>

1. <span data-ttu-id="4c58b-109">Seleccione **Administración de activos** \> **Común** \> **Solicitudes de mantenimiento** \> **Todas las solicitudes de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="4c58b-109">Select **Asset management** \> **Common** \> **maintenance requests** \> **All maintenance requests**.</span></span>
2. <span data-ttu-id="4c58b-110">Antes de poder crear una orden de trabajo a partir de solicitudes de mantenimiento, debe seleccionar como mínimo un tipo de trabajo de mantenimiento para las solicitudes de mantenimiento, así como una variante y un comercio del tipo de trabajo de mantenimiento, si esta información es pertinente.</span><span class="sxs-lookup"><span data-stu-id="4c58b-110">Before you can create a work order from maintenance requests, you must select, at a minimum, a maintenance job type for the maintenance requests, and also a maintenance job type variant and trade, if this information is relevant.</span></span> <span data-ttu-id="4c58b-111">En la vista de cuadrícula puede actualizar fácilmente la información de una solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="4c58b-111">In the grid view, you can easily update information for a maintenance request.</span></span>
3. <span data-ttu-id="4c58b-112">Cuando esté listo para crear una orden de trabajo, seleccione las solicitudes de mantenimiento que desea incluir en ella.</span><span class="sxs-lookup"><span data-stu-id="4c58b-112">When you're ready to create a work order, select the maintenance requests to include in it.</span></span>

    - <span data-ttu-id="4c58b-113">Si selecciona varias solicitudes de mantenimiento para convertirlas en una orden de trabajo, debe establecer los campos **Activo** y **Tipo de trabajo de mantenimiento** antes de crear la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c58b-113">If you select several maintenance requests to convert to a work order, both the **Asset** field and the **Maintenance job type** field must be set before you create the work order.</span></span>
    - <span data-ttu-id="4c58b-114">Si selecciona una solicitud de mantenimiento para convertirla en una orden de trabajo, solo hay que establecer el campo **Activo** antes de crear la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c58b-114">If you select one maintenance request to convert to a work order, only the **Asset** field must be set before you create the work order.</span></span> <span data-ttu-id="4c58b-115">Sin embargo, al crear la orden de trabajo, puede seleccionar un tipo de trabajo de mantenimiento (así como una variante y un oficio relacionados con el tipo de trabajo de mantenimiento, si esta información es pertinente) en el cuadro de diálogo **Crear orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="4c58b-115">However, when you create the work order, you can select a maintenance job type (and a related maintenance job type variant and trade, if this information is relevant) in the **Create work order** dialog box.</span></span>

4. <span data-ttu-id="4c58b-116">Seleccione **Orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="4c58b-116">Select **Work order**.</span></span>
5. <span data-ttu-id="4c58b-117">En el cuadro de diálogo **Crear orden de trabajo**, establezca los valores de los campos y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4c58b-117">In the **Create work order** dialog box, set the fields, and then select **OK**.</span></span>

    <span data-ttu-id="4c58b-118">Una barra de mensajes le notificará cuando se haya creado un nueva orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c58b-118">A message bar might notify you that a new work order has been created.</span></span>

    <span data-ttu-id="4c58b-119">Además, al crear una orden de trabajo basada en una solicitud de mantenimiento, si el activo relacionado con la solicitud de mantenimiento se incluye en un acuerdo de garantía, una barra de mensajes le notificará el acuerdo de garantía.</span><span class="sxs-lookup"><span data-stu-id="4c58b-119">Additionally, when you create a work order that is based on a maintenance request, if the asset that is related to the maintenance request is included in a warranty agreement, a message bar notifies you about the warranty agreement.</span></span>

6. <span data-ttu-id="4c58b-120">Seleccione **Administración de activos** \> **Común** \> **Órdenes de trabajo** \> **Todas las órdenes de trabajo**, y abra la nueva orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c58b-120">Select **Asset management** \> **Common** \> **Work orders** \> **All work orders**, and open the new work order.</span></span>

    ![Abrir nueva orden de trabajo](media/05-manage-maintenance-requests.png)

