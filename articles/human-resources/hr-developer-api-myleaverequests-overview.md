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
ms.openlocfilehash: c2c14a0cc935ad166a2c6600f1e96c3e09ab16ca
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465519"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="85f99-103">Visión general de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="85f99-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="85f99-104">La entidad MyLeaveRequests en Microsoft Dynamics 365 Human Resources proporciona la lista de Solicitudes de licencia en el sistema, con ámbito (limitada) a las solicitudes accesibles para el usuario actual que consulta la entidad.</span><span class="sxs-lookup"><span data-stu-id="85f99-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="85f99-105">Clave</span><span class="sxs-lookup"><span data-stu-id="85f99-105">Key</span></span>

  | <span data-ttu-id="85f99-106">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="85f99-106">Property Name</span></span> | <span data-ttu-id="85f99-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="85f99-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="85f99-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="85f99-108">dataAreaId</span></span>    | <span data-ttu-id="85f99-109">Cadena</span><span class="sxs-lookup"><span data-stu-id="85f99-109">String</span></span>    |
  | <span data-ttu-id="85f99-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="85f99-110">RequestId</span></span>     | <span data-ttu-id="85f99-111">Cadena</span><span class="sxs-lookup"><span data-stu-id="85f99-111">String</span></span>    |
  | <span data-ttu-id="85f99-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="85f99-112">LeaveType</span></span>     | <span data-ttu-id="85f99-113">Cadena</span><span class="sxs-lookup"><span data-stu-id="85f99-113">String</span></span>    |
  | <span data-ttu-id="85f99-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="85f99-114">LeaveDate</span></span>     | <span data-ttu-id="85f99-115">Fecha</span><span class="sxs-lookup"><span data-stu-id="85f99-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="85f99-116">Propiedades</span><span class="sxs-lookup"><span data-stu-id="85f99-116">Properties</span></span>

  | <span data-ttu-id="85f99-117">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="85f99-117">Property Name</span></span>     | <span data-ttu-id="85f99-118">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="85f99-118">Data Type</span></span> | <span data-ttu-id="85f99-119">Requerido</span><span class="sxs-lookup"><span data-stu-id="85f99-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="85f99-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="85f99-120">dataAreaId</span></span>        | <span data-ttu-id="85f99-121">Cadena</span><span class="sxs-lookup"><span data-stu-id="85f99-121">String</span></span>    | <span data-ttu-id="85f99-122">X</span><span class="sxs-lookup"><span data-stu-id="85f99-122">X</span></span>        |
  | <span data-ttu-id="85f99-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="85f99-123">RequestId</span></span>         | <span data-ttu-id="85f99-124">Cadena</span><span class="sxs-lookup"><span data-stu-id="85f99-124">String</span></span>    | <span data-ttu-id="85f99-125">X</span><span class="sxs-lookup"><span data-stu-id="85f99-125">X</span></span>        |
  | <span data-ttu-id="85f99-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="85f99-126">LeaveType</span></span>         | <span data-ttu-id="85f99-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="85f99-127">String</span></span>    | <span data-ttu-id="85f99-128">X</span><span class="sxs-lookup"><span data-stu-id="85f99-128">X</span></span>        |
  | <span data-ttu-id="85f99-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="85f99-129">LeaveDate</span></span>         | <span data-ttu-id="85f99-130">Fecha</span><span class="sxs-lookup"><span data-stu-id="85f99-130">Date</span></span>      | <span data-ttu-id="85f99-131">X</span><span class="sxs-lookup"><span data-stu-id="85f99-131">X</span></span>        |
  | <span data-ttu-id="85f99-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="85f99-132">ReasonCodeId</span></span>      | <span data-ttu-id="85f99-133">Cadena</span><span class="sxs-lookup"><span data-stu-id="85f99-133">String</span></span>    |          |
  | <span data-ttu-id="85f99-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="85f99-134">PersonnelNumber</span></span>   | <span data-ttu-id="85f99-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="85f99-135">String</span></span>    | <span data-ttu-id="85f99-136">X</span><span class="sxs-lookup"><span data-stu-id="85f99-136">X</span></span>        |
  | <span data-ttu-id="85f99-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="85f99-137">RequestDate</span></span>       | <span data-ttu-id="85f99-138">Fecha</span><span class="sxs-lookup"><span data-stu-id="85f99-138">Date</span></span>      | <span data-ttu-id="85f99-139">X</span><span class="sxs-lookup"><span data-stu-id="85f99-139">X</span></span>        |
  | <span data-ttu-id="85f99-140">Comentar</span><span class="sxs-lookup"><span data-stu-id="85f99-140">Comment</span></span>           | <span data-ttu-id="85f99-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="85f99-141">String</span></span>    |          |
  | <span data-ttu-id="85f99-142">Estado</span><span class="sxs-lookup"><span data-stu-id="85f99-142">Status</span></span>            | <span data-ttu-id="85f99-143">Enumeración</span><span class="sxs-lookup"><span data-stu-id="85f99-143">Enum</span></span>      | <span data-ttu-id="85f99-144">X</span><span class="sxs-lookup"><span data-stu-id="85f99-144">X</span></span>        |
  | <span data-ttu-id="85f99-145">Importe</span><span class="sxs-lookup"><span data-stu-id="85f99-145">Amount</span></span>            | <span data-ttu-id="85f99-146">Real</span><span class="sxs-lookup"><span data-stu-id="85f99-146">Real</span></span>      |          |
  | <span data-ttu-id="85f99-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="85f99-147">HalfDayDefinition</span></span> | <span data-ttu-id="85f99-148">Enumeración</span><span class="sxs-lookup"><span data-stu-id="85f99-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="85f99-149">Acciones </span><span class="sxs-lookup"><span data-stu-id="85f99-149">Actions</span></span>

 | <span data-ttu-id="85f99-150">Nombre de acción</span><span class="sxs-lookup"><span data-stu-id="85f99-150">Action Name</span></span>                               | <span data-ttu-id="85f99-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="85f99-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="85f99-152">enviar</span><span class="sxs-lookup"><span data-stu-id="85f99-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="85f99-153">Envíe la solicitud para que la procese el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="85f99-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="85f99-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85f99-154">See also</span></span>

- [<span data-ttu-id="85f99-155">Enviar una solicitud de baja al flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="85f99-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="85f99-156">Autenticación</span><span class="sxs-lookup"><span data-stu-id="85f99-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]