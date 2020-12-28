---
title: Visión general de MyLeaveRequests
description: La entidad MyLeaveRequests en Microsoft Dynamics 365 Human Resources proporciona la lista de Solicitudes de licencia en el sistema, con ámbito (limitada) a las solicitudes accesibles para el usuario actual que consulta la entidad.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: 4bf3b298af9eb39e03514a4005afb43a42908e47
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420347"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="1e0a8-103">Visión general de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="1e0a8-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="1e0a8-104">La entidad MyLeaveRequests en Microsoft Dynamics 365 Human Resources proporciona la lista de Solicitudes de licencia en el sistema, con ámbito (limitada) a las solicitudes accesibles para el usuario actual que consulta la entidad.</span><span class="sxs-lookup"><span data-stu-id="1e0a8-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="1e0a8-105">Clave</span><span class="sxs-lookup"><span data-stu-id="1e0a8-105">Key</span></span>

  | <span data-ttu-id="1e0a8-106">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="1e0a8-106">Property Name</span></span> | <span data-ttu-id="1e0a8-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1e0a8-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="1e0a8-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="1e0a8-108">dataAreaId</span></span>    | <span data-ttu-id="1e0a8-109">Cadena</span><span class="sxs-lookup"><span data-stu-id="1e0a8-109">String</span></span>    |
  | <span data-ttu-id="1e0a8-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="1e0a8-110">RequestId</span></span>     | <span data-ttu-id="1e0a8-111">Cadena</span><span class="sxs-lookup"><span data-stu-id="1e0a8-111">String</span></span>    |
  | <span data-ttu-id="1e0a8-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="1e0a8-112">LeaveType</span></span>     | <span data-ttu-id="1e0a8-113">Cadena</span><span class="sxs-lookup"><span data-stu-id="1e0a8-113">String</span></span>    |
  | <span data-ttu-id="1e0a8-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="1e0a8-114">LeaveDate</span></span>     | <span data-ttu-id="1e0a8-115">Fecha</span><span class="sxs-lookup"><span data-stu-id="1e0a8-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="1e0a8-116">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1e0a8-116">Properties</span></span>

  | <span data-ttu-id="1e0a8-117">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="1e0a8-117">Property Name</span></span>     | <span data-ttu-id="1e0a8-118">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1e0a8-118">Data Type</span></span> | <span data-ttu-id="1e0a8-119">Requerido</span><span class="sxs-lookup"><span data-stu-id="1e0a8-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="1e0a8-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="1e0a8-120">dataAreaId</span></span>        | <span data-ttu-id="1e0a8-121">Cadena</span><span class="sxs-lookup"><span data-stu-id="1e0a8-121">String</span></span>    | <span data-ttu-id="1e0a8-122">X</span><span class="sxs-lookup"><span data-stu-id="1e0a8-122">X</span></span>        |
  | <span data-ttu-id="1e0a8-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="1e0a8-123">RequestId</span></span>         | <span data-ttu-id="1e0a8-124">Cadena</span><span class="sxs-lookup"><span data-stu-id="1e0a8-124">String</span></span>    | <span data-ttu-id="1e0a8-125">X</span><span class="sxs-lookup"><span data-stu-id="1e0a8-125">X</span></span>        |
  | <span data-ttu-id="1e0a8-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="1e0a8-126">LeaveType</span></span>         | <span data-ttu-id="1e0a8-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="1e0a8-127">String</span></span>    | <span data-ttu-id="1e0a8-128">X</span><span class="sxs-lookup"><span data-stu-id="1e0a8-128">X</span></span>        |
  | <span data-ttu-id="1e0a8-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="1e0a8-129">LeaveDate</span></span>         | <span data-ttu-id="1e0a8-130">Fecha</span><span class="sxs-lookup"><span data-stu-id="1e0a8-130">Date</span></span>      | <span data-ttu-id="1e0a8-131">X</span><span class="sxs-lookup"><span data-stu-id="1e0a8-131">X</span></span>        |
  | <span data-ttu-id="1e0a8-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="1e0a8-132">ReasonCodeId</span></span>      | <span data-ttu-id="1e0a8-133">Cadena</span><span class="sxs-lookup"><span data-stu-id="1e0a8-133">String</span></span>    |          |
  | <span data-ttu-id="1e0a8-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="1e0a8-134">PersonnelNumber</span></span>   | <span data-ttu-id="1e0a8-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="1e0a8-135">String</span></span>    | <span data-ttu-id="1e0a8-136">X</span><span class="sxs-lookup"><span data-stu-id="1e0a8-136">X</span></span>        |
  | <span data-ttu-id="1e0a8-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="1e0a8-137">RequestDate</span></span>       | <span data-ttu-id="1e0a8-138">Fecha</span><span class="sxs-lookup"><span data-stu-id="1e0a8-138">Date</span></span>      | <span data-ttu-id="1e0a8-139">X</span><span class="sxs-lookup"><span data-stu-id="1e0a8-139">X</span></span>        |
  | <span data-ttu-id="1e0a8-140">Comentar</span><span class="sxs-lookup"><span data-stu-id="1e0a8-140">Comment</span></span>           | <span data-ttu-id="1e0a8-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="1e0a8-141">String</span></span>    |          |
  | <span data-ttu-id="1e0a8-142">Estado</span><span class="sxs-lookup"><span data-stu-id="1e0a8-142">Status</span></span>            | <span data-ttu-id="1e0a8-143">Enumeración</span><span class="sxs-lookup"><span data-stu-id="1e0a8-143">Enum</span></span>      | <span data-ttu-id="1e0a8-144">X</span><span class="sxs-lookup"><span data-stu-id="1e0a8-144">X</span></span>        |
  | <span data-ttu-id="1e0a8-145">Importe</span><span class="sxs-lookup"><span data-stu-id="1e0a8-145">Amount</span></span>            | <span data-ttu-id="1e0a8-146">Real</span><span class="sxs-lookup"><span data-stu-id="1e0a8-146">Real</span></span>      |          |
  | <span data-ttu-id="1e0a8-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="1e0a8-147">HalfDayDefinition</span></span> | <span data-ttu-id="1e0a8-148">Enumeración</span><span class="sxs-lookup"><span data-stu-id="1e0a8-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="1e0a8-149">Acciones </span><span class="sxs-lookup"><span data-stu-id="1e0a8-149">Actions</span></span>

 | <span data-ttu-id="1e0a8-150">Nombre de acción</span><span class="sxs-lookup"><span data-stu-id="1e0a8-150">Action Name</span></span>                               | <span data-ttu-id="1e0a8-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e0a8-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="1e0a8-152">enviar</span><span class="sxs-lookup"><span data-stu-id="1e0a8-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="1e0a8-153">Envíe la solicitud para que la procese el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1e0a8-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1e0a8-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e0a8-154">See also</span></span>

- [<span data-ttu-id="1e0a8-155">Enviar una solicitud de baja al flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="1e0a8-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="1e0a8-156">Autenticación</span><span class="sxs-lookup"><span data-stu-id="1e0a8-156">Authentication</span></span>](hr-developer-api-authentication.md)