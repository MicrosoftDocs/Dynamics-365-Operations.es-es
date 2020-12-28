---
title: Activos de entrada y de salida
description: En este tema se explica cómo registrar activos de entrada y salida en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetOutboundObjectsListPage, EntAssetOutboundObjectsDeliver, EntAssetInboundObjectsListPage, EntAssetInboundObjectsRecieve
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a7239bf5f8e53e61c4259abbcbf2ff740f4cef55
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436912"
---
# <a name="inbound-and-outbound-assets"></a><span data-ttu-id="5518b-103">Activos de entrada y de salida</span><span class="sxs-lookup"><span data-stu-id="5518b-103">Inbound and outbound assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="5518b-104">Si la empresa emite trabajos de reparación o trabajos de mantenimiento en los activos que se reciben de otras ubicaciones o clientes, Administración de activos puede realizar un seguimiento de los activos de entrada que se encuentran de camino a la empresa y los activos de salida que se van a devolver.</span><span class="sxs-lookup"><span data-stu-id="5518b-104">If your company does repair jobs or maintenance jobs on assets that are received from other locations or customers, Asset Management can track both inbound assets that are on their way to your company and outbound assets that are being returned.</span></span>

> [!NOTE]
> <span data-ttu-id="5518b-105">Si desea usar los estados de ciclo de vida de entrada y salida para gestionar los activos que llegan y salen, debe configurar los estados y modelos de ciclo de vida de la solicitud de mantenimiento para que admitan estas acciones.</span><span class="sxs-lookup"><span data-stu-id="5518b-105">If you want to use inbound and outbound lifecycle states to manage assets that are coming in and being returned, you must set up maintenance request lifecycle states and lifecycle models to support these actions.</span></span> <span data-ttu-id="5518b-106">Para obtener más información, consulte [Solicitudes de mantenimiento](../setup-for-maintenance-requests/requests.md).</span><span class="sxs-lookup"><span data-stu-id="5518b-106">For more information, see [Maintenance requests](../setup-for-maintenance-requests/requests.md).</span></span>

<span data-ttu-id="5518b-107">La configuración de Administración de activos determina si puede trabajar con activos de entrada y de salida.</span><span class="sxs-lookup"><span data-stu-id="5518b-107">The setup of Asset Management determines whether you can work with inbound and outbound assets.</span></span>

## <a name="register-assets-as-inbound"></a><span data-ttu-id="5518b-108">Registrar activos como de entrada</span><span class="sxs-lookup"><span data-stu-id="5518b-108">Register assets as inbound</span></span>

1. <span data-ttu-id="5518b-109">Seleccione **Administración de activos** \> **Común** \> **Solicitudes de mantenimiento** \> **Solicitudes de mantenimiento activas**.</span><span class="sxs-lookup"><span data-stu-id="5518b-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="5518b-110">Seleccione la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="5518b-110">Select the maintenance request.</span></span>
3. <span data-ttu-id="5518b-111">Seleccione **Actualizar estado de solicitud de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="5518b-111">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="5518b-112">Seleccione **Entrante** (u otro estado de ciclo de vida que haya creado para los activos de entrada) y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5518b-112">Select **Inbound** (or another lifecycle state that you've created for inbound assets), and then select **OK**.</span></span>

![Registrar activos como de entrada](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a><span data-ttu-id="5518b-114">Registrar los activos entrantes como recibidos</span><span class="sxs-lookup"><span data-stu-id="5518b-114">Register inbound assets as received</span></span>

1. <span data-ttu-id="5518b-115">Seleccione **Administración de activos** \> **Común** \> **Entrante/saliente** \> **Activos entrantes**.</span><span class="sxs-lookup"><span data-stu-id="5518b-115">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Inbound assets**.</span></span>
2. <span data-ttu-id="5518b-116">Seleccione el activo o la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="5518b-116">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="5518b-117">Seleccione **Recibir activos**.</span><span class="sxs-lookup"><span data-stu-id="5518b-117">Select **Receive assets**.</span></span>
4. <span data-ttu-id="5518b-118">En el campo **Recibido**, especifique la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="5518b-118">In the **Received** field, enter the date and time.</span></span> <span data-ttu-id="5518b-119">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5518b-119">Then select **OK**.</span></span> <span data-ttu-id="5518b-120">El registro se eliminará de la página de lista **Activos de entrada**.</span><span class="sxs-lookup"><span data-stu-id="5518b-120">The record is removed from the **Inbound assets** list page.</span></span>

![Registrar los activos entrantes como recibidos](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a><span data-ttu-id="5518b-122">Registrar activos como de salida</span><span class="sxs-lookup"><span data-stu-id="5518b-122">Register assets as outbound</span></span>

<span data-ttu-id="5518b-123">Cuando haya completado el mantenimiento o el trabajo de reparación, puede registrar el activo como devuelto.</span><span class="sxs-lookup"><span data-stu-id="5518b-123">When you've completed the maintenance or repair job, you can register the asset as returned.</span></span>

1. <span data-ttu-id="5518b-124">Seleccione **Administración de activos** \> **Común** \> **Solicitudes de mantenimiento** \> **Solicitudes de mantenimiento activas**.</span><span class="sxs-lookup"><span data-stu-id="5518b-124">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="5518b-125">Seleccione la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="5518b-125">Select the maintenance request.</span></span>
3. <span data-ttu-id="5518b-126">Seleccione **Actualizar estado de solicitud de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="5518b-126">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="5518b-127">Seleccione **Saliente** (u otro estado de ciclo de vida que haya creado para los activos de salida) y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5518b-127">Select **Outbound** (or another lifecycle state that you've created for outbound assets), and then select **OK**.</span></span>

## <a name="register-outbound-assets-as-delivered"></a><span data-ttu-id="5518b-128">Registrar activos de salida como entregados</span><span class="sxs-lookup"><span data-stu-id="5518b-128">Register outbound assets as delivered</span></span>

1. <span data-ttu-id="5518b-129">Seleccione **Administración de activos** \> **Común** \> **Entrante/saliente** \> **Activos salientes**.</span><span class="sxs-lookup"><span data-stu-id="5518b-129">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Outbound assets**.</span></span>
2. <span data-ttu-id="5518b-130">Seleccione el activo o la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="5518b-130">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="5518b-131">Seleccione **Entregar activos**.</span><span class="sxs-lookup"><span data-stu-id="5518b-131">Select **Deliver assets**.</span></span>
4. <span data-ttu-id="5518b-132">En el campo **Entregado**, especifique la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="5518b-132">In the **Delivered** field, enter the date and time.</span></span> <span data-ttu-id="5518b-133">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5518b-133">Then select **OK**.</span></span> <span data-ttu-id="5518b-134">El registro se eliminará de la página de lista **Activos de salida**.</span><span class="sxs-lookup"><span data-stu-id="5518b-134">The record is removed from the **Outbound assets** list page.</span></span>
