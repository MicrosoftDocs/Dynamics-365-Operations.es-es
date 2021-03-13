---
title: Estado de solicitud de contratación
description: Este tema describe el conjunto de opciones de estado de solicitud de contratación para Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 55ed9c391a1b5f86c3c443b9fceeee5c2301444d
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125963"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="3462d-103">Estado de solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="3462d-103">Recruiting request status</span></span>

<span data-ttu-id="3462d-104">Este tema describe el conjunto de opciones de estado de solicitud de contratación para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="3462d-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="3462d-105">Nombre físico: mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="3462d-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="3462d-106">Esta enumeración proporciona el conjunto de opciones de los valores de estado de una solicitud de contratación.</span><span class="sxs-lookup"><span data-stu-id="3462d-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="3462d-107">Valor</span><span class="sxs-lookup"><span data-stu-id="3462d-107">Value</span></span> | <span data-ttu-id="3462d-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="3462d-108">Label</span></span> | <span data-ttu-id="3462d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3462d-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="3462d-110">200000000</span><span class="sxs-lookup"><span data-stu-id="3462d-110">200000000</span></span> | <span data-ttu-id="3462d-111">Borrador</span><span class="sxs-lookup"><span data-stu-id="3462d-111">Draft</span></span> | <span data-ttu-id="3462d-112">La solicitud está en estado de borrador. No está lista para la contratación activa.</span><span class="sxs-lookup"><span data-stu-id="3462d-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="3462d-113">200000001</span><span class="sxs-lookup"><span data-stu-id="3462d-113">200000001</span></span> | <span data-ttu-id="3462d-114">En revisión</span><span class="sxs-lookup"><span data-stu-id="3462d-114">In Review</span></span> | <span data-ttu-id="3462d-115">Se ha enviado la solicitud y se está enrutando para su aprobación por flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3462d-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="3462d-116">Solo está disponible cuando el flujo de trabajo está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3462d-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="3462d-117">200000002</span><span class="sxs-lookup"><span data-stu-id="3462d-117">200000002</span></span> | <span data-ttu-id="3462d-118">Pendientes</span><span class="sxs-lookup"><span data-stu-id="3462d-118">Pending</span></span> | <span data-ttu-id="3462d-119">La solicitud está pendiente de una acción de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3462d-119">The request is pending workflow action.</span></span> <span data-ttu-id="3462d-120">Solo está disponible cuando el flujo de trabajo está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3462d-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="3462d-121">200000003</span><span class="sxs-lookup"><span data-stu-id="3462d-121">200000003</span></span> | <span data-ttu-id="3462d-122">Cancelados</span><span class="sxs-lookup"><span data-stu-id="3462d-122">Canceled</span></span> | <span data-ttu-id="3462d-123">Se ha cancelado la solicitud.</span><span class="sxs-lookup"><span data-stu-id="3462d-123">The request has been canceled.</span></span> <span data-ttu-id="3462d-124">Solo está disponible cuando el flujo de trabajo está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3462d-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="3462d-125">200000004</span><span class="sxs-lookup"><span data-stu-id="3462d-125">200000004</span></span> | <span data-ttu-id="3462d-126">Denegada</span><span class="sxs-lookup"><span data-stu-id="3462d-126">Denied</span></span> | <span data-ttu-id="3462d-127">Se ha denegado la solicitud.</span><span class="sxs-lookup"><span data-stu-id="3462d-127">The request has been denied.</span></span> <span data-ttu-id="3462d-128">Solo está disponible cuando el flujo de trabajo está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3462d-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="3462d-129">200000005</span><span class="sxs-lookup"><span data-stu-id="3462d-129">200000005</span></span> | <span data-ttu-id="3462d-130">Activa</span><span class="sxs-lookup"><span data-stu-id="3462d-130">Active</span></span> | <span data-ttu-id="3462d-131">Se ha completado y aprobado cualquier flujo de trabajo, y la solicitud está lista para la contratación activa.</span><span class="sxs-lookup"><span data-stu-id="3462d-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="3462d-132">200000006</span><span class="sxs-lookup"><span data-stu-id="3462d-132">200000006</span></span> | <span data-ttu-id="3462d-133">Cerradas</span><span class="sxs-lookup"><span data-stu-id="3462d-133">Closed</span></span> | <span data-ttu-id="3462d-134">La solicitud de contratación se ha cerrado.</span><span class="sxs-lookup"><span data-stu-id="3462d-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3462d-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3462d-135">See also</span></span>

[<span data-ttu-id="3462d-136">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="3462d-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="3462d-137">Consulta de ejemplo para solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="3462d-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)
