---
title: Visión general de MyLeaveRequests
description: La entidad MyLeaveRequests en Microsoft Dynamics 365 Human Resources proporciona la lista de Solicitudes de licencia en el sistema, con ámbito (limitada) a las solicitudes accesibles para el usuario actual que consulta la entidad.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f29d5cf1469b58b4ea1837dc82b9513f5c002609
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054965"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="288cb-103">Visión general de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="288cb-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="288cb-104">La entidad MyLeaveRequests en Microsoft Dynamics 365 Human Resources proporciona la lista de Solicitudes de licencia en el sistema, con ámbito (limitada) a las solicitudes accesibles para el usuario actual que consulta la entidad.</span><span class="sxs-lookup"><span data-stu-id="288cb-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="288cb-105">Clave</span><span class="sxs-lookup"><span data-stu-id="288cb-105">Key</span></span>

  | <span data-ttu-id="288cb-106">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="288cb-106">Property Name</span></span> | <span data-ttu-id="288cb-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="288cb-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="288cb-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="288cb-108">dataAreaId</span></span>    | <span data-ttu-id="288cb-109">Cadena</span><span class="sxs-lookup"><span data-stu-id="288cb-109">String</span></span>    |
  | <span data-ttu-id="288cb-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="288cb-110">RequestId</span></span>     | <span data-ttu-id="288cb-111">Cadena</span><span class="sxs-lookup"><span data-stu-id="288cb-111">String</span></span>    |
  | <span data-ttu-id="288cb-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="288cb-112">LeaveType</span></span>     | <span data-ttu-id="288cb-113">Cadena</span><span class="sxs-lookup"><span data-stu-id="288cb-113">String</span></span>    |
  | <span data-ttu-id="288cb-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="288cb-114">LeaveDate</span></span>     | <span data-ttu-id="288cb-115">Fecha</span><span class="sxs-lookup"><span data-stu-id="288cb-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="288cb-116">Propiedades</span><span class="sxs-lookup"><span data-stu-id="288cb-116">Properties</span></span>

  | <span data-ttu-id="288cb-117">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="288cb-117">Property Name</span></span>     | <span data-ttu-id="288cb-118">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="288cb-118">Data Type</span></span> | <span data-ttu-id="288cb-119">Requerido</span><span class="sxs-lookup"><span data-stu-id="288cb-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="288cb-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="288cb-120">dataAreaId</span></span>        | <span data-ttu-id="288cb-121">Cadena</span><span class="sxs-lookup"><span data-stu-id="288cb-121">String</span></span>    | <span data-ttu-id="288cb-122">X</span><span class="sxs-lookup"><span data-stu-id="288cb-122">X</span></span>        |
  | <span data-ttu-id="288cb-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="288cb-123">RequestId</span></span>         | <span data-ttu-id="288cb-124">Cadena</span><span class="sxs-lookup"><span data-stu-id="288cb-124">String</span></span>    | <span data-ttu-id="288cb-125">X</span><span class="sxs-lookup"><span data-stu-id="288cb-125">X</span></span>        |
  | <span data-ttu-id="288cb-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="288cb-126">LeaveType</span></span>         | <span data-ttu-id="288cb-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="288cb-127">String</span></span>    | <span data-ttu-id="288cb-128">X</span><span class="sxs-lookup"><span data-stu-id="288cb-128">X</span></span>        |
  | <span data-ttu-id="288cb-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="288cb-129">LeaveDate</span></span>         | <span data-ttu-id="288cb-130">Fecha</span><span class="sxs-lookup"><span data-stu-id="288cb-130">Date</span></span>      | <span data-ttu-id="288cb-131">X</span><span class="sxs-lookup"><span data-stu-id="288cb-131">X</span></span>        |
  | <span data-ttu-id="288cb-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="288cb-132">ReasonCodeId</span></span>      | <span data-ttu-id="288cb-133">Cadena</span><span class="sxs-lookup"><span data-stu-id="288cb-133">String</span></span>    |          |
  | <span data-ttu-id="288cb-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="288cb-134">PersonnelNumber</span></span>   | <span data-ttu-id="288cb-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="288cb-135">String</span></span>    | <span data-ttu-id="288cb-136">X</span><span class="sxs-lookup"><span data-stu-id="288cb-136">X</span></span>        |
  | <span data-ttu-id="288cb-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="288cb-137">RequestDate</span></span>       | <span data-ttu-id="288cb-138">Fecha</span><span class="sxs-lookup"><span data-stu-id="288cb-138">Date</span></span>      | <span data-ttu-id="288cb-139">X</span><span class="sxs-lookup"><span data-stu-id="288cb-139">X</span></span>        |
  | <span data-ttu-id="288cb-140">Comentar</span><span class="sxs-lookup"><span data-stu-id="288cb-140">Comment</span></span>           | <span data-ttu-id="288cb-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="288cb-141">String</span></span>    |          |
  | <span data-ttu-id="288cb-142">Estado</span><span class="sxs-lookup"><span data-stu-id="288cb-142">Status</span></span>            | <span data-ttu-id="288cb-143">Enumeración</span><span class="sxs-lookup"><span data-stu-id="288cb-143">Enum</span></span>      | <span data-ttu-id="288cb-144">X</span><span class="sxs-lookup"><span data-stu-id="288cb-144">X</span></span>        |
  | <span data-ttu-id="288cb-145">Importe</span><span class="sxs-lookup"><span data-stu-id="288cb-145">Amount</span></span>            | <span data-ttu-id="288cb-146">Real</span><span class="sxs-lookup"><span data-stu-id="288cb-146">Real</span></span>      |          |
  | <span data-ttu-id="288cb-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="288cb-147">HalfDayDefinition</span></span> | <span data-ttu-id="288cb-148">Enumeración</span><span class="sxs-lookup"><span data-stu-id="288cb-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="288cb-149">Acciones </span><span class="sxs-lookup"><span data-stu-id="288cb-149">Actions</span></span>

 | <span data-ttu-id="288cb-150">Nombre de acción</span><span class="sxs-lookup"><span data-stu-id="288cb-150">Action Name</span></span>                               | <span data-ttu-id="288cb-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="288cb-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="288cb-152">enviar</span><span class="sxs-lookup"><span data-stu-id="288cb-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="288cb-153">Envíe la solicitud para que la procese el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="288cb-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="288cb-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="288cb-154">See also</span></span>

- [<span data-ttu-id="288cb-155">Enviar una solicitud de baja al flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="288cb-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="288cb-156">Autenticación</span><span class="sxs-lookup"><span data-stu-id="288cb-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]