---
title: Visión general de MyLeaveRequests
description: ''
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
ms.openlocfilehash: 66f161d6736b1bb544d02871d9d51b2949b1cfa0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010463"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="fa66f-102">Visión general de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="fa66f-102">MyLeaveRequests overview</span></span>

<span data-ttu-id="fa66f-103">La entidad MyLeaveRequests en Microsoft Dynamics 365 Human Resources proporciona la lista de Solicitudes de licencia en el sistema, con ámbito (limitada) a las solicitudes accesibles para el usuario actual que consulta la entidad.</span><span class="sxs-lookup"><span data-stu-id="fa66f-103">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="fa66f-104">Clave</span><span class="sxs-lookup"><span data-stu-id="fa66f-104">Key</span></span>

  | <span data-ttu-id="fa66f-105">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="fa66f-105">Property Name</span></span> | <span data-ttu-id="fa66f-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="fa66f-106">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="fa66f-107">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="fa66f-107">dataAreaId</span></span>    | <span data-ttu-id="fa66f-108">Cadena</span><span class="sxs-lookup"><span data-stu-id="fa66f-108">String</span></span>    |
  | <span data-ttu-id="fa66f-109">RequestId</span><span class="sxs-lookup"><span data-stu-id="fa66f-109">RequestId</span></span>     | <span data-ttu-id="fa66f-110">Cadena</span><span class="sxs-lookup"><span data-stu-id="fa66f-110">String</span></span>    |
  | <span data-ttu-id="fa66f-111">LeaveType</span><span class="sxs-lookup"><span data-stu-id="fa66f-111">LeaveType</span></span>     | <span data-ttu-id="fa66f-112">Cadena</span><span class="sxs-lookup"><span data-stu-id="fa66f-112">String</span></span>    |
  | <span data-ttu-id="fa66f-113">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="fa66f-113">LeaveDate</span></span>     | <span data-ttu-id="fa66f-114">Fecha</span><span class="sxs-lookup"><span data-stu-id="fa66f-114">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="fa66f-115">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fa66f-115">Properties</span></span>

  | <span data-ttu-id="fa66f-116">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="fa66f-116">Property Name</span></span>     | <span data-ttu-id="fa66f-117">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="fa66f-117">Data Type</span></span> | <span data-ttu-id="fa66f-118">Requerido</span><span class="sxs-lookup"><span data-stu-id="fa66f-118">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="fa66f-119">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="fa66f-119">dataAreaId</span></span>        | <span data-ttu-id="fa66f-120">Cadena</span><span class="sxs-lookup"><span data-stu-id="fa66f-120">String</span></span>    | <span data-ttu-id="fa66f-121">X</span><span class="sxs-lookup"><span data-stu-id="fa66f-121">X</span></span>        |
  | <span data-ttu-id="fa66f-122">RequestId</span><span class="sxs-lookup"><span data-stu-id="fa66f-122">RequestId</span></span>         | <span data-ttu-id="fa66f-123">Cadena</span><span class="sxs-lookup"><span data-stu-id="fa66f-123">String</span></span>    | <span data-ttu-id="fa66f-124">X</span><span class="sxs-lookup"><span data-stu-id="fa66f-124">X</span></span>        |
  | <span data-ttu-id="fa66f-125">LeaveType</span><span class="sxs-lookup"><span data-stu-id="fa66f-125">LeaveType</span></span>         | <span data-ttu-id="fa66f-126">Cadena</span><span class="sxs-lookup"><span data-stu-id="fa66f-126">String</span></span>    | <span data-ttu-id="fa66f-127">X</span><span class="sxs-lookup"><span data-stu-id="fa66f-127">X</span></span>        |
  | <span data-ttu-id="fa66f-128">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="fa66f-128">LeaveDate</span></span>         | <span data-ttu-id="fa66f-129">Fecha</span><span class="sxs-lookup"><span data-stu-id="fa66f-129">Date</span></span>      | <span data-ttu-id="fa66f-130">X</span><span class="sxs-lookup"><span data-stu-id="fa66f-130">X</span></span>        |
  | <span data-ttu-id="fa66f-131">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="fa66f-131">ReasonCodeId</span></span>      | <span data-ttu-id="fa66f-132">Cadena</span><span class="sxs-lookup"><span data-stu-id="fa66f-132">String</span></span>    |          |
  | <span data-ttu-id="fa66f-133">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="fa66f-133">PersonnelNumber</span></span>   | <span data-ttu-id="fa66f-134">Cadena</span><span class="sxs-lookup"><span data-stu-id="fa66f-134">String</span></span>    | <span data-ttu-id="fa66f-135">X</span><span class="sxs-lookup"><span data-stu-id="fa66f-135">X</span></span>        |
  | <span data-ttu-id="fa66f-136">RequestDate</span><span class="sxs-lookup"><span data-stu-id="fa66f-136">RequestDate</span></span>       | <span data-ttu-id="fa66f-137">Fecha</span><span class="sxs-lookup"><span data-stu-id="fa66f-137">Date</span></span>      | <span data-ttu-id="fa66f-138">X</span><span class="sxs-lookup"><span data-stu-id="fa66f-138">X</span></span>        |
  | <span data-ttu-id="fa66f-139">Comentar</span><span class="sxs-lookup"><span data-stu-id="fa66f-139">Comment</span></span>           | <span data-ttu-id="fa66f-140">Cadena</span><span class="sxs-lookup"><span data-stu-id="fa66f-140">String</span></span>    |          |
  | <span data-ttu-id="fa66f-141">Estado</span><span class="sxs-lookup"><span data-stu-id="fa66f-141">Status</span></span>            | <span data-ttu-id="fa66f-142">Enumeración</span><span class="sxs-lookup"><span data-stu-id="fa66f-142">Enum</span></span>      | <span data-ttu-id="fa66f-143">X</span><span class="sxs-lookup"><span data-stu-id="fa66f-143">X</span></span>        |
  | <span data-ttu-id="fa66f-144">Importe</span><span class="sxs-lookup"><span data-stu-id="fa66f-144">Amount</span></span>            | <span data-ttu-id="fa66f-145">Real</span><span class="sxs-lookup"><span data-stu-id="fa66f-145">Real</span></span>      |          |
  | <span data-ttu-id="fa66f-146">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="fa66f-146">HalfDayDefinition</span></span> | <span data-ttu-id="fa66f-147">Enumeración</span><span class="sxs-lookup"><span data-stu-id="fa66f-147">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="fa66f-148">Acciones </span><span class="sxs-lookup"><span data-stu-id="fa66f-148">Actions</span></span>

 | <span data-ttu-id="fa66f-149">Nombre de acción</span><span class="sxs-lookup"><span data-stu-id="fa66f-149">Action Name</span></span>                               | <span data-ttu-id="fa66f-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa66f-150">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="fa66f-151">enviar</span><span class="sxs-lookup"><span data-stu-id="fa66f-151">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="fa66f-152">Envíe la solicitud para que la procese el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fa66f-152">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="fa66f-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa66f-153">See also</span></span>

- [<span data-ttu-id="fa66f-154">Enviar una solicitud de baja al flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="fa66f-154">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="fa66f-155">Autenticación</span><span class="sxs-lookup"><span data-stu-id="fa66f-155">Authentication</span></span>](hr-developer-api-authentication.md)