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
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092046"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="d6d2d-103">Visión general de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="d6d2d-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="d6d2d-104">La entidad MyLeaveRequests en Microsoft Dynamics 365 Human Resources proporciona la lista de Solicitudes de licencia en el sistema, con ámbito (limitada) a las solicitudes accesibles para el usuario actual que consulta la entidad.</span><span class="sxs-lookup"><span data-stu-id="d6d2d-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="d6d2d-105">Clave</span><span class="sxs-lookup"><span data-stu-id="d6d2d-105">Key</span></span>

  | <span data-ttu-id="d6d2d-106">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="d6d2d-106">Property Name</span></span> | <span data-ttu-id="d6d2d-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d6d2d-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="d6d2d-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="d6d2d-108">dataAreaId</span></span>    | <span data-ttu-id="d6d2d-109">Cadena</span><span class="sxs-lookup"><span data-stu-id="d6d2d-109">String</span></span>    |
  | <span data-ttu-id="d6d2d-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="d6d2d-110">RequestId</span></span>     | <span data-ttu-id="d6d2d-111">Cadena</span><span class="sxs-lookup"><span data-stu-id="d6d2d-111">String</span></span>    |
  | <span data-ttu-id="d6d2d-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="d6d2d-112">LeaveType</span></span>     | <span data-ttu-id="d6d2d-113">Cadena</span><span class="sxs-lookup"><span data-stu-id="d6d2d-113">String</span></span>    |
  | <span data-ttu-id="d6d2d-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="d6d2d-114">LeaveDate</span></span>     | <span data-ttu-id="d6d2d-115">Fecha</span><span class="sxs-lookup"><span data-stu-id="d6d2d-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="d6d2d-116">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d6d2d-116">Properties</span></span>

  | <span data-ttu-id="d6d2d-117">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="d6d2d-117">Property Name</span></span>     | <span data-ttu-id="d6d2d-118">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d6d2d-118">Data Type</span></span> | <span data-ttu-id="d6d2d-119">Requerido</span><span class="sxs-lookup"><span data-stu-id="d6d2d-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="d6d2d-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="d6d2d-120">dataAreaId</span></span>        | <span data-ttu-id="d6d2d-121">Cadena</span><span class="sxs-lookup"><span data-stu-id="d6d2d-121">String</span></span>    | <span data-ttu-id="d6d2d-122">X</span><span class="sxs-lookup"><span data-stu-id="d6d2d-122">X</span></span>        |
  | <span data-ttu-id="d6d2d-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="d6d2d-123">RequestId</span></span>         | <span data-ttu-id="d6d2d-124">Cadena</span><span class="sxs-lookup"><span data-stu-id="d6d2d-124">String</span></span>    | <span data-ttu-id="d6d2d-125">X</span><span class="sxs-lookup"><span data-stu-id="d6d2d-125">X</span></span>        |
  | <span data-ttu-id="d6d2d-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="d6d2d-126">LeaveType</span></span>         | <span data-ttu-id="d6d2d-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="d6d2d-127">String</span></span>    | <span data-ttu-id="d6d2d-128">X</span><span class="sxs-lookup"><span data-stu-id="d6d2d-128">X</span></span>        |
  | <span data-ttu-id="d6d2d-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="d6d2d-129">LeaveDate</span></span>         | <span data-ttu-id="d6d2d-130">Fecha</span><span class="sxs-lookup"><span data-stu-id="d6d2d-130">Date</span></span>      | <span data-ttu-id="d6d2d-131">X</span><span class="sxs-lookup"><span data-stu-id="d6d2d-131">X</span></span>        |
  | <span data-ttu-id="d6d2d-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="d6d2d-132">ReasonCodeId</span></span>      | <span data-ttu-id="d6d2d-133">Cadena</span><span class="sxs-lookup"><span data-stu-id="d6d2d-133">String</span></span>    |          |
  | <span data-ttu-id="d6d2d-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="d6d2d-134">PersonnelNumber</span></span>   | <span data-ttu-id="d6d2d-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="d6d2d-135">String</span></span>    | <span data-ttu-id="d6d2d-136">X</span><span class="sxs-lookup"><span data-stu-id="d6d2d-136">X</span></span>        |
  | <span data-ttu-id="d6d2d-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="d6d2d-137">RequestDate</span></span>       | <span data-ttu-id="d6d2d-138">Fecha</span><span class="sxs-lookup"><span data-stu-id="d6d2d-138">Date</span></span>      | <span data-ttu-id="d6d2d-139">X</span><span class="sxs-lookup"><span data-stu-id="d6d2d-139">X</span></span>        |
  | <span data-ttu-id="d6d2d-140">Comentar</span><span class="sxs-lookup"><span data-stu-id="d6d2d-140">Comment</span></span>           | <span data-ttu-id="d6d2d-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="d6d2d-141">String</span></span>    |          |
  | <span data-ttu-id="d6d2d-142">Estado</span><span class="sxs-lookup"><span data-stu-id="d6d2d-142">Status</span></span>            | <span data-ttu-id="d6d2d-143">Enumeración</span><span class="sxs-lookup"><span data-stu-id="d6d2d-143">Enum</span></span>      | <span data-ttu-id="d6d2d-144">X</span><span class="sxs-lookup"><span data-stu-id="d6d2d-144">X</span></span>        |
  | <span data-ttu-id="d6d2d-145">Importe</span><span class="sxs-lookup"><span data-stu-id="d6d2d-145">Amount</span></span>            | <span data-ttu-id="d6d2d-146">Real</span><span class="sxs-lookup"><span data-stu-id="d6d2d-146">Real</span></span>      |          |
  | <span data-ttu-id="d6d2d-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="d6d2d-147">HalfDayDefinition</span></span> | <span data-ttu-id="d6d2d-148">Enumeración</span><span class="sxs-lookup"><span data-stu-id="d6d2d-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="d6d2d-149">Acciones </span><span class="sxs-lookup"><span data-stu-id="d6d2d-149">Actions</span></span>

 | <span data-ttu-id="d6d2d-150">Nombre de acción</span><span class="sxs-lookup"><span data-stu-id="d6d2d-150">Action Name</span></span>                               | <span data-ttu-id="d6d2d-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6d2d-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="d6d2d-152">enviar</span><span class="sxs-lookup"><span data-stu-id="d6d2d-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="d6d2d-153">Envíe la solicitud para que la procese el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d6d2d-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="d6d2d-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6d2d-154">See also</span></span>

- [<span data-ttu-id="d6d2d-155">Enviar una solicitud de baja al flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="d6d2d-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="d6d2d-156">Autenticación</span><span class="sxs-lookup"><span data-stu-id="d6d2d-156">Authentication</span></span>](hr-developer-api-authentication.md)