---
title: Activos y órdenes de trabajo
description: En este tema se describen los activos y las órdenes de trabajo en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6fd5aa8914437fb77ea25ec229c94cfb0bb12def
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253071"
---
# <a name="assets-and-work-orders"></a><span data-ttu-id="eb70d-103">Activos y órdenes de trabajo</span><span class="sxs-lookup"><span data-stu-id="eb70d-103">Assets and work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="eb70d-104">En este tema se describen los activos y las órdenes de trabajo en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="eb70d-104">This topic describes assets and work orders in Asset Management.</span></span> <span data-ttu-id="eb70d-105">Los activos y las órdenes de trabajo son las partes centrales de Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="eb70d-105">Assets and work orders are the central parts of Asset Management.</span></span> <span data-ttu-id="eb70d-106">Un *activo* es una máquina o una pieza de la máquina que requiere mantenimiento y servicio continuos.</span><span class="sxs-lookup"><span data-stu-id="eb70d-106">An *asset* is a machine or machine part that requires continuous maintenance and service.</span></span> <span data-ttu-id="eb70d-107">Los activos se pueden crear en una estructura jerárquica y pueden estar relacionados con ubicaciones funcionales.</span><span class="sxs-lookup"><span data-stu-id="eb70d-107">Assets can be created in a hierarchical structure, and they can be related to functional locations.</span></span> <span data-ttu-id="eb70d-108">Los trabajos de mantenimiento pueden planificarse en todos los niveles de la estructura de activos.</span><span class="sxs-lookup"><span data-stu-id="eb70d-108">Maintenance jobs can be planned at all levels in the asset structure.</span></span>

<span data-ttu-id="eb70d-109">Los distintos datos, como la información de producto y la especificación del activo, así como los planes de mantenimiento necesarios, se configuran en cada activo.</span><span class="sxs-lookup"><span data-stu-id="eb70d-109">Various data, such as product information and asset specification, and required maintenance plans are set up on each asset.</span></span> <span data-ttu-id="eb70d-110">La ilustración siguiente muestra una visión general de los datos de activos y la afiliación de los activos con los tipos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eb70d-110">The following illustration shows an overview of asset data and the affiliation of assets to job types.</span></span> <span data-ttu-id="eb70d-111">El texto rojo se usa para ejemplos que muestran herencia y dependencias.</span><span class="sxs-lookup"><span data-stu-id="eb70d-111">Red text is used for examples that show inheritance and dependencies.</span></span>

![Diagrama que muestra los datos de activos relacionados con los tipos de trabajo](media/05-overview-image.png)

<span data-ttu-id="eb70d-113">Cada orden de trabajo tiene un tipo de orden de trabajo, tal como mantenimiento preventivo, mantenimiento correctivo o inspección.</span><span class="sxs-lookup"><span data-stu-id="eb70d-113">Every work order has a work order type, such preventive maintenance, corrective maintenance, or inspection.</span></span> <span data-ttu-id="eb70d-114">La orden de trabajo contiene uno o más trabajos de orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eb70d-114">The work order contains one or more work order jobs.</span></span> <span data-ttu-id="eb70d-115">Cada trabajo de la orden de trabajo define un trabajo que se debe realizar en un activo y en un tipo de trabajo relacionado.</span><span class="sxs-lookup"><span data-stu-id="eb70d-115">Every work order job defines a job that must be performed on an asset and a related job type.</span></span> <span data-ttu-id="eb70d-116">Ejemplos de tipos de trabajo relacionados son 10 000 km, 50 000 km, revisión de un año e inspección de seguridad.</span><span class="sxs-lookup"><span data-stu-id="eb70d-116">Examples of related job types include 10,000 km, 50,000 km, 1-year overhaul, and safety inspection.</span></span> <span data-ttu-id="eb70d-117">Una orden de trabajo puede estar relacionada con varios activos.</span><span class="sxs-lookup"><span data-stu-id="eb70d-117">One work order can be related to multiple assets.</span></span>

<span data-ttu-id="eb70d-118">La ilustración siguiente muestra una visión general de los datos clave en una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eb70d-118">The following illustration shows an overview of the key data in a work order.</span></span>

![Diagrama que muestra los datos clave de una orden de trabajo](media/06-overview-image.png)

<span data-ttu-id="eb70d-120">Una orden de trabajo puede estar relacionada con otra y los tipos de trabajo pueden contener trabajos posteriores que creen una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eb70d-120">A work order can be related to another work order, and job types can contain succeeding jobs that create a work order.</span></span> <span data-ttu-id="eb70d-121">En genearl, no hay dependencias entre las órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eb70d-121">In general, there are no dependencies between work orders.</span></span> <span data-ttu-id="eb70d-122">Por lo tanto, pueden cambiar su estado de ciclo de vida de orden de trabajo y pueden programarse independientemente entre sí.</span><span class="sxs-lookup"><span data-stu-id="eb70d-122">Therefore, they can change their work order lifecycle state and can be scheduled independently of each other.</span></span>

<span data-ttu-id="eb70d-123">Las órdenes de trabajo se pueden crear de distintas maneras que guardan relación con el mantenimiento correctivo, preventivo o reactivo.</span><span class="sxs-lookup"><span data-stu-id="eb70d-123">Work orders can be created in various ways that are related to corrective, preventive, or reactive maintenance.</span></span> <span data-ttu-id="eb70d-124">También puede crear órdenes de trabajo de manera manual.</span><span class="sxs-lookup"><span data-stu-id="eb70d-124">You can also create work orders manually.</span></span> <span data-ttu-id="eb70d-125">La ilustración siguiente muestra una visión general del proceso de creación automática o manual de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eb70d-125">The following illustration shows an overview of the process for automatic or manual creation of work orders.</span></span>

![Diagrama que muestra la creación automática o manual de las órdenes de trabajo](media/07-overview-image.png)

<span data-ttu-id="eb70d-127">Se deben cojpletar varios pasos para programar y ejecutar un trabajo de mantenimiento en una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eb70d-127">Several steps must be completed when you want to schedule and run a maintenance job on a work order.</span></span> <span data-ttu-id="eb70d-128">La ilustración siguiente muestra una visión general del procesameinto de una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eb70d-128">The following illustration shows an overview of the processing for a work order.</span></span>

![Diagrama que muestra la información general de procesamiento de una orden de trabajo](media/08-overview-image.png)

> [!NOTE]
> <span data-ttu-id="eb70d-130">Normalmente, cuando se trabaja en Dynamics 365 Supply Chain Management y el módulo **Administración de activos**, se selecciona **Nuevo** para crear un nuevo registro, se selecciona **Editar** para actualizar un registro existente y se selecciona **Guardar** para guardar datos nuevos o modificados.</span><span class="sxs-lookup"><span data-stu-id="eb70d-130">In general, when you work in Dynamics 365 Supply Chain Management and the **Asset Management** module, you select **New** to create a new record, you select **Edit** to update an existing record, and you select **Save** to save new or edited data.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]