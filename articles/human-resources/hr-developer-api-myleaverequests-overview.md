---
title: Visión general de MyLeaveRequests
description: La entidad MyLeaveRequests en Microsoft Dynamics 365 Human Resources proporciona la lista de Solicitudes de licencia en el sistema, con ámbito (limitada) a las solicitudes accesibles para el usuario actual que consulta la entidad.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ca5bc225400338e76faee41a279e91fc00ce570
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115545"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="5e07b-103">Visión general de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="5e07b-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="5e07b-104">La entidad MyLeaveRequests en Microsoft Dynamics 365 Human Resources proporciona la lista de Solicitudes de licencia en el sistema, con ámbito (limitada) a las solicitudes accesibles para el usuario actual que consulta la entidad.</span><span class="sxs-lookup"><span data-stu-id="5e07b-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="5e07b-105">Clave</span><span class="sxs-lookup"><span data-stu-id="5e07b-105">Key</span></span>

  | <span data-ttu-id="5e07b-106">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="5e07b-106">Property Name</span></span> | <span data-ttu-id="5e07b-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="5e07b-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="5e07b-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="5e07b-108">dataAreaId</span></span>    | <span data-ttu-id="5e07b-109">Cadena</span><span class="sxs-lookup"><span data-stu-id="5e07b-109">String</span></span>    |
  | <span data-ttu-id="5e07b-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="5e07b-110">RequestId</span></span>     | <span data-ttu-id="5e07b-111">Cadena</span><span class="sxs-lookup"><span data-stu-id="5e07b-111">String</span></span>    |
  | <span data-ttu-id="5e07b-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="5e07b-112">LeaveType</span></span>     | <span data-ttu-id="5e07b-113">Cadena</span><span class="sxs-lookup"><span data-stu-id="5e07b-113">String</span></span>    |
  | <span data-ttu-id="5e07b-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="5e07b-114">LeaveDate</span></span>     | <span data-ttu-id="5e07b-115">Fecha</span><span class="sxs-lookup"><span data-stu-id="5e07b-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="5e07b-116">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5e07b-116">Properties</span></span>

  | <span data-ttu-id="5e07b-117">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="5e07b-117">Property Name</span></span>     | <span data-ttu-id="5e07b-118">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="5e07b-118">Data Type</span></span> | <span data-ttu-id="5e07b-119">Requerido</span><span class="sxs-lookup"><span data-stu-id="5e07b-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="5e07b-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="5e07b-120">dataAreaId</span></span>        | <span data-ttu-id="5e07b-121">Cadena</span><span class="sxs-lookup"><span data-stu-id="5e07b-121">String</span></span>    | <span data-ttu-id="5e07b-122">X</span><span class="sxs-lookup"><span data-stu-id="5e07b-122">X</span></span>        |
  | <span data-ttu-id="5e07b-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="5e07b-123">RequestId</span></span>         | <span data-ttu-id="5e07b-124">Cadena</span><span class="sxs-lookup"><span data-stu-id="5e07b-124">String</span></span>    | <span data-ttu-id="5e07b-125">X</span><span class="sxs-lookup"><span data-stu-id="5e07b-125">X</span></span>        |
  | <span data-ttu-id="5e07b-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="5e07b-126">LeaveType</span></span>         | <span data-ttu-id="5e07b-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="5e07b-127">String</span></span>    | <span data-ttu-id="5e07b-128">X</span><span class="sxs-lookup"><span data-stu-id="5e07b-128">X</span></span>        |
  | <span data-ttu-id="5e07b-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="5e07b-129">LeaveDate</span></span>         | <span data-ttu-id="5e07b-130">Fecha</span><span class="sxs-lookup"><span data-stu-id="5e07b-130">Date</span></span>      | <span data-ttu-id="5e07b-131">X</span><span class="sxs-lookup"><span data-stu-id="5e07b-131">X</span></span>        |
  | <span data-ttu-id="5e07b-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="5e07b-132">ReasonCodeId</span></span>      | <span data-ttu-id="5e07b-133">Cadena</span><span class="sxs-lookup"><span data-stu-id="5e07b-133">String</span></span>    |          |
  | <span data-ttu-id="5e07b-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="5e07b-134">PersonnelNumber</span></span>   | <span data-ttu-id="5e07b-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="5e07b-135">String</span></span>    | <span data-ttu-id="5e07b-136">X</span><span class="sxs-lookup"><span data-stu-id="5e07b-136">X</span></span>        |
  | <span data-ttu-id="5e07b-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="5e07b-137">RequestDate</span></span>       | <span data-ttu-id="5e07b-138">Fecha</span><span class="sxs-lookup"><span data-stu-id="5e07b-138">Date</span></span>      | <span data-ttu-id="5e07b-139">X</span><span class="sxs-lookup"><span data-stu-id="5e07b-139">X</span></span>        |
  | <span data-ttu-id="5e07b-140">Comentar</span><span class="sxs-lookup"><span data-stu-id="5e07b-140">Comment</span></span>           | <span data-ttu-id="5e07b-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="5e07b-141">String</span></span>    |          |
  | <span data-ttu-id="5e07b-142">Estado</span><span class="sxs-lookup"><span data-stu-id="5e07b-142">Status</span></span>            | <span data-ttu-id="5e07b-143">Enumeración</span><span class="sxs-lookup"><span data-stu-id="5e07b-143">Enum</span></span>      | <span data-ttu-id="5e07b-144">X</span><span class="sxs-lookup"><span data-stu-id="5e07b-144">X</span></span>        |
  | <span data-ttu-id="5e07b-145">Importe</span><span class="sxs-lookup"><span data-stu-id="5e07b-145">Amount</span></span>            | <span data-ttu-id="5e07b-146">Real</span><span class="sxs-lookup"><span data-stu-id="5e07b-146">Real</span></span>      |          |
  | <span data-ttu-id="5e07b-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="5e07b-147">HalfDayDefinition</span></span> | <span data-ttu-id="5e07b-148">Enumeración</span><span class="sxs-lookup"><span data-stu-id="5e07b-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="5e07b-149">Acciones </span><span class="sxs-lookup"><span data-stu-id="5e07b-149">Actions</span></span>

 | <span data-ttu-id="5e07b-150">Nombre de acción</span><span class="sxs-lookup"><span data-stu-id="5e07b-150">Action Name</span></span>                               | <span data-ttu-id="5e07b-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e07b-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="5e07b-152">enviar</span><span class="sxs-lookup"><span data-stu-id="5e07b-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="5e07b-153">Envíe la solicitud para que la procese el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5e07b-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="5e07b-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e07b-154">See also</span></span>

- [<span data-ttu-id="5e07b-155">Enviar una solicitud de baja al flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5e07b-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="5e07b-156">Autenticación</span><span class="sxs-lookup"><span data-stu-id="5e07b-156">Authentication</span></span>](hr-developer-api-authentication.md)