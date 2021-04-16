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
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 44e23a076733bac782a0366aeba3456911522abe
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803642"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="974e9-103">Visión general de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="974e9-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="974e9-104">La entidad MyLeaveRequests en Microsoft Dynamics 365 Human Resources proporciona la lista de Solicitudes de licencia en el sistema, con ámbito (limitada) a las solicitudes accesibles para el usuario actual que consulta la entidad.</span><span class="sxs-lookup"><span data-stu-id="974e9-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="974e9-105">Clave</span><span class="sxs-lookup"><span data-stu-id="974e9-105">Key</span></span>

  | <span data-ttu-id="974e9-106">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="974e9-106">Property Name</span></span> | <span data-ttu-id="974e9-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="974e9-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="974e9-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="974e9-108">dataAreaId</span></span>    | <span data-ttu-id="974e9-109">Cadena</span><span class="sxs-lookup"><span data-stu-id="974e9-109">String</span></span>    |
  | <span data-ttu-id="974e9-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="974e9-110">RequestId</span></span>     | <span data-ttu-id="974e9-111">Cadena</span><span class="sxs-lookup"><span data-stu-id="974e9-111">String</span></span>    |
  | <span data-ttu-id="974e9-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="974e9-112">LeaveType</span></span>     | <span data-ttu-id="974e9-113">Cadena</span><span class="sxs-lookup"><span data-stu-id="974e9-113">String</span></span>    |
  | <span data-ttu-id="974e9-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="974e9-114">LeaveDate</span></span>     | <span data-ttu-id="974e9-115">Fecha</span><span class="sxs-lookup"><span data-stu-id="974e9-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="974e9-116">Propiedades</span><span class="sxs-lookup"><span data-stu-id="974e9-116">Properties</span></span>

  | <span data-ttu-id="974e9-117">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="974e9-117">Property Name</span></span>     | <span data-ttu-id="974e9-118">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="974e9-118">Data Type</span></span> | <span data-ttu-id="974e9-119">Requerido</span><span class="sxs-lookup"><span data-stu-id="974e9-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="974e9-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="974e9-120">dataAreaId</span></span>        | <span data-ttu-id="974e9-121">Cadena</span><span class="sxs-lookup"><span data-stu-id="974e9-121">String</span></span>    | <span data-ttu-id="974e9-122">X</span><span class="sxs-lookup"><span data-stu-id="974e9-122">X</span></span>        |
  | <span data-ttu-id="974e9-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="974e9-123">RequestId</span></span>         | <span data-ttu-id="974e9-124">Cadena</span><span class="sxs-lookup"><span data-stu-id="974e9-124">String</span></span>    | <span data-ttu-id="974e9-125">X</span><span class="sxs-lookup"><span data-stu-id="974e9-125">X</span></span>        |
  | <span data-ttu-id="974e9-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="974e9-126">LeaveType</span></span>         | <span data-ttu-id="974e9-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="974e9-127">String</span></span>    | <span data-ttu-id="974e9-128">X</span><span class="sxs-lookup"><span data-stu-id="974e9-128">X</span></span>        |
  | <span data-ttu-id="974e9-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="974e9-129">LeaveDate</span></span>         | <span data-ttu-id="974e9-130">Fecha</span><span class="sxs-lookup"><span data-stu-id="974e9-130">Date</span></span>      | <span data-ttu-id="974e9-131">X</span><span class="sxs-lookup"><span data-stu-id="974e9-131">X</span></span>        |
  | <span data-ttu-id="974e9-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="974e9-132">ReasonCodeId</span></span>      | <span data-ttu-id="974e9-133">Cadena</span><span class="sxs-lookup"><span data-stu-id="974e9-133">String</span></span>    |          |
  | <span data-ttu-id="974e9-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="974e9-134">PersonnelNumber</span></span>   | <span data-ttu-id="974e9-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="974e9-135">String</span></span>    | <span data-ttu-id="974e9-136">X</span><span class="sxs-lookup"><span data-stu-id="974e9-136">X</span></span>        |
  | <span data-ttu-id="974e9-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="974e9-137">RequestDate</span></span>       | <span data-ttu-id="974e9-138">Fecha</span><span class="sxs-lookup"><span data-stu-id="974e9-138">Date</span></span>      | <span data-ttu-id="974e9-139">X</span><span class="sxs-lookup"><span data-stu-id="974e9-139">X</span></span>        |
  | <span data-ttu-id="974e9-140">Comentar</span><span class="sxs-lookup"><span data-stu-id="974e9-140">Comment</span></span>           | <span data-ttu-id="974e9-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="974e9-141">String</span></span>    |          |
  | <span data-ttu-id="974e9-142">Estado</span><span class="sxs-lookup"><span data-stu-id="974e9-142">Status</span></span>            | <span data-ttu-id="974e9-143">Enumeración</span><span class="sxs-lookup"><span data-stu-id="974e9-143">Enum</span></span>      | <span data-ttu-id="974e9-144">X</span><span class="sxs-lookup"><span data-stu-id="974e9-144">X</span></span>        |
  | <span data-ttu-id="974e9-145">Importe</span><span class="sxs-lookup"><span data-stu-id="974e9-145">Amount</span></span>            | <span data-ttu-id="974e9-146">Real</span><span class="sxs-lookup"><span data-stu-id="974e9-146">Real</span></span>      |          |
  | <span data-ttu-id="974e9-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="974e9-147">HalfDayDefinition</span></span> | <span data-ttu-id="974e9-148">Enumeración</span><span class="sxs-lookup"><span data-stu-id="974e9-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="974e9-149">Acciones </span><span class="sxs-lookup"><span data-stu-id="974e9-149">Actions</span></span>

 | <span data-ttu-id="974e9-150">Nombre de acción</span><span class="sxs-lookup"><span data-stu-id="974e9-150">Action Name</span></span>                               | <span data-ttu-id="974e9-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="974e9-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="974e9-152">enviar</span><span class="sxs-lookup"><span data-stu-id="974e9-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="974e9-153">Envíe la solicitud para que la procese el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="974e9-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="974e9-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="974e9-154">See also</span></span>

- [<span data-ttu-id="974e9-155">Enviar una solicitud de baja al flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="974e9-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="974e9-156">Autenticación</span><span class="sxs-lookup"><span data-stu-id="974e9-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]