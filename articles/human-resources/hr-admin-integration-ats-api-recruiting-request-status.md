---
title: Estado de solicitud de contratación
description: Este tema describe el conjunto de opciones de estado de solicitud de contratación para Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 888fbc511bffbecd837c929049006266191da5ba
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5806051"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="3229f-103">Estado de solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="3229f-103">Recruiting request status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="3229f-104">Este tema describe el conjunto de opciones de estado de solicitud de contratación para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="3229f-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="3229f-105">Nombre físico: mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="3229f-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="3229f-106">Esta enumeración proporciona el conjunto de opciones de los valores de estado de una solicitud de contratación.</span><span class="sxs-lookup"><span data-stu-id="3229f-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="3229f-107">Valor</span><span class="sxs-lookup"><span data-stu-id="3229f-107">Value</span></span> | <span data-ttu-id="3229f-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="3229f-108">Label</span></span> | <span data-ttu-id="3229f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3229f-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="3229f-110">200000000</span><span class="sxs-lookup"><span data-stu-id="3229f-110">200000000</span></span> | <span data-ttu-id="3229f-111">Borrador</span><span class="sxs-lookup"><span data-stu-id="3229f-111">Draft</span></span> | <span data-ttu-id="3229f-112">La solicitud está en estado de borrador. No está lista para la contratación activa.</span><span class="sxs-lookup"><span data-stu-id="3229f-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="3229f-113">200000001</span><span class="sxs-lookup"><span data-stu-id="3229f-113">200000001</span></span> | <span data-ttu-id="3229f-114">En revisión</span><span class="sxs-lookup"><span data-stu-id="3229f-114">In Review</span></span> | <span data-ttu-id="3229f-115">Se ha enviado la solicitud y se está enrutando para su aprobación por flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3229f-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="3229f-116">Solo está disponible cuando el flujo de trabajo está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3229f-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="3229f-117">200000002</span><span class="sxs-lookup"><span data-stu-id="3229f-117">200000002</span></span> | <span data-ttu-id="3229f-118">Pendientes</span><span class="sxs-lookup"><span data-stu-id="3229f-118">Pending</span></span> | <span data-ttu-id="3229f-119">La solicitud está pendiente de una acción de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3229f-119">The request is pending workflow action.</span></span> <span data-ttu-id="3229f-120">Solo está disponible cuando el flujo de trabajo está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3229f-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="3229f-121">200000003</span><span class="sxs-lookup"><span data-stu-id="3229f-121">200000003</span></span> | <span data-ttu-id="3229f-122">Cancelados</span><span class="sxs-lookup"><span data-stu-id="3229f-122">Canceled</span></span> | <span data-ttu-id="3229f-123">Se ha cancelado la solicitud.</span><span class="sxs-lookup"><span data-stu-id="3229f-123">The request has been canceled.</span></span> <span data-ttu-id="3229f-124">Solo está disponible cuando el flujo de trabajo está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3229f-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="3229f-125">200000004</span><span class="sxs-lookup"><span data-stu-id="3229f-125">200000004</span></span> | <span data-ttu-id="3229f-126">Denegada</span><span class="sxs-lookup"><span data-stu-id="3229f-126">Denied</span></span> | <span data-ttu-id="3229f-127">Se ha denegado la solicitud.</span><span class="sxs-lookup"><span data-stu-id="3229f-127">The request has been denied.</span></span> <span data-ttu-id="3229f-128">Solo está disponible cuando el flujo de trabajo está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3229f-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="3229f-129">200000005</span><span class="sxs-lookup"><span data-stu-id="3229f-129">200000005</span></span> | <span data-ttu-id="3229f-130">Activa</span><span class="sxs-lookup"><span data-stu-id="3229f-130">Active</span></span> | <span data-ttu-id="3229f-131">Se ha completado y aprobado cualquier flujo de trabajo, y la solicitud está lista para la contratación activa.</span><span class="sxs-lookup"><span data-stu-id="3229f-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="3229f-132">200000006</span><span class="sxs-lookup"><span data-stu-id="3229f-132">200000006</span></span> | <span data-ttu-id="3229f-133">Cerradas</span><span class="sxs-lookup"><span data-stu-id="3229f-133">Closed</span></span> | <span data-ttu-id="3229f-134">La solicitud de contratación se ha cerrado.</span><span class="sxs-lookup"><span data-stu-id="3229f-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3229f-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3229f-135">See also</span></span>

[<span data-ttu-id="3229f-136">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="3229f-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="3229f-137">Consulta de ejemplo para solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="3229f-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]