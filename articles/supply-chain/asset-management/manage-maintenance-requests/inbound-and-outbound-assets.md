---
title: Activos de entrada y de salida
description: En este tema se explica cómo registrar activos de entrada y salida en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 62998da7f541379296d5ac325ae29f24a42f9b7c
ms.sourcegitcommit: 871b76f8808a48d282f151144829323258ffc912
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1847560"
---
# <a name="inbound-and-outbound-assets"></a><span data-ttu-id="37fdc-103">Activos de entrada y de salida</span><span class="sxs-lookup"><span data-stu-id="37fdc-103">Inbound and outbound assets</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="37fdc-104">Si la empresa emite trabajos de reparación o trabajos de mantenimiento en los activos que se reciben de otras ubicaciones o clientes, Administración de activos puede realizar un seguimiento de los activos de entrada que se encuentran de camino a la empresa y los activos de salida que se van a devolver.</span><span class="sxs-lookup"><span data-stu-id="37fdc-104">If your company does repair jobs or maintenance jobs on assets that are received from other locations or customers, Asset Management can track both inbound assets that are on their way to your company and outbound assets that are being returned.</span></span>

> [!NOTE]
> <span data-ttu-id="37fdc-105">Si desea usar los estados de ciclo de vida de entrada y salida para gestionar los activos que llegan y salen, debe configurar los estados y modelos de ciclo de vida de la solicitud de mantenimiento para que admitan estas acciones.</span><span class="sxs-lookup"><span data-stu-id="37fdc-105">If you want to use inbound and outbound lifecycle states to manage assets that are coming in and being returned, you must set up maintenance request lifecycle states and lifecycle models to support these actions.</span></span> <span data-ttu-id="37fdc-106">Para obtener más información, consulte [Condiguración de las solicitudes de mantenimiento](../setup-for-maintenance-requests/requests.md).</span><span class="sxs-lookup"><span data-stu-id="37fdc-106">For more information, see [Setup for maintenance requests](../setup-for-maintenance-requests/requests.md).</span></span>

<span data-ttu-id="37fdc-107">La configuración de Administración de activos determina si puede trabajar con activos de entrada y de salida.</span><span class="sxs-lookup"><span data-stu-id="37fdc-107">The setup of Asset Management determines whether you can work with inbound and outbound assets.</span></span>

## <a name="register-assets-as-inbound"></a><span data-ttu-id="37fdc-108">Registrar activos como de entrada</span><span class="sxs-lookup"><span data-stu-id="37fdc-108">Register assets as inbound</span></span>

1. <span data-ttu-id="37fdc-109">Seleccione **Administración de activos** \> **Común** \> **Solicitudes de mantenimiento** \> **Solicitudes de mantenimiento activas**.</span><span class="sxs-lookup"><span data-stu-id="37fdc-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="37fdc-110">Seleccione la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="37fdc-110">Select the maintenance request.</span></span>
3. <span data-ttu-id="37fdc-111">Seleccione **Actualizar estado de solicitud de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="37fdc-111">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="37fdc-112">Seleccione **Entrante** (u otro estado de ciclo de vida que haya creado para los activos de entrada) y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="37fdc-112">Select **Inbound** (or another lifecycle state that you've created for inbound assets), and then select **OK**.</span></span>

![Figura 1](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a><span data-ttu-id="37fdc-114">Registrar los activos entrantes como recibidos</span><span class="sxs-lookup"><span data-stu-id="37fdc-114">Register inbound assets as received</span></span>

1. <span data-ttu-id="37fdc-115">Seleccione **Administración de activos** \> **Común** \> **Entrante/saliente** \> **Activos entrantes**.</span><span class="sxs-lookup"><span data-stu-id="37fdc-115">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Inbound assets**.</span></span>
2. <span data-ttu-id="37fdc-116">Seleccione el activo o la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="37fdc-116">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="37fdc-117">Seleccione **Recibir activos**.</span><span class="sxs-lookup"><span data-stu-id="37fdc-117">Select **Receive assets**.</span></span>
4. <span data-ttu-id="37fdc-118">En el campo **Recibido**, especifique la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="37fdc-118">In the **Received** field, enter the date and time.</span></span> <span data-ttu-id="37fdc-119">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="37fdc-119">Then select **OK**.</span></span> <span data-ttu-id="37fdc-120">El registro se eliminará de la página de lista **Activos de entrada**.</span><span class="sxs-lookup"><span data-stu-id="37fdc-120">The record is removed from the **Inbound assets** list page.</span></span>

![Figura 2](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a><span data-ttu-id="37fdc-122">Registrar activos como de salida</span><span class="sxs-lookup"><span data-stu-id="37fdc-122">Register assets as outbound</span></span>

<span data-ttu-id="37fdc-123">Cuando haya completado el mantenimiento o el trabajo de reparación, puede registrar el activo como devuelto.</span><span class="sxs-lookup"><span data-stu-id="37fdc-123">When you've completed the maintenance or repair job, you can register the asset as returned.</span></span>

1. <span data-ttu-id="37fdc-124">Seleccione **Administración de activos** \> **Común** \> **Solicitudes de mantenimiento** \> **Solicitudes de mantenimiento activas**.</span><span class="sxs-lookup"><span data-stu-id="37fdc-124">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="37fdc-125">Seleccione la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="37fdc-125">Select the maintenance request.</span></span>
3. <span data-ttu-id="37fdc-126">Seleccione **Actualizar estado de solicitud de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="37fdc-126">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="37fdc-127">Seleccione **Saliente** (u otro estado de ciclo de vida que haya creado para los activos de salida) y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="37fdc-127">Select **Outbound** (or another lifecycle state that you've created for outbound assets), and then select **OK**.</span></span>

## <a name="register-outbound-assets-as-delivered"></a><span data-ttu-id="37fdc-128">Registrar activos de salida como entregados</span><span class="sxs-lookup"><span data-stu-id="37fdc-128">Register outbound assets as delivered</span></span>

1. <span data-ttu-id="37fdc-129">Seleccione **Administración de activos** \> **Común** \> **Entrante/saliente** \> **Activos salientes**.</span><span class="sxs-lookup"><span data-stu-id="37fdc-129">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Outbound assets**.</span></span>
2. <span data-ttu-id="37fdc-130">Seleccione el activo o la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="37fdc-130">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="37fdc-131">Seleccione **Entregar activos**.</span><span class="sxs-lookup"><span data-stu-id="37fdc-131">Select **Deliver assets**.</span></span>
4. <span data-ttu-id="37fdc-132">En el campo **Entregado**, especifique la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="37fdc-132">In the **Delivered** field, enter the date and time.</span></span> <span data-ttu-id="37fdc-133">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="37fdc-133">Then select **OK**.</span></span> <span data-ttu-id="37fdc-134">El registro se eliminará de la página de lista **Activos de salida**.</span><span class="sxs-lookup"><span data-stu-id="37fdc-134">The record is removed from the **Outbound assets** list page.</span></span>
