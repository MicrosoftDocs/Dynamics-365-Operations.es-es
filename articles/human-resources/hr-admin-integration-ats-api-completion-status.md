---
title: Estado de finalización
description: Este tema describe el conjunto de opciones de estado de terminación para Dynamics 365 Human Resources.
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
ms.openlocfilehash: e9024e00b5d25117fd255084609c4f8db9284f32
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125698"
---
# <a name="completion-status"></a><span data-ttu-id="70974-103">Estado de finalización</span><span class="sxs-lookup"><span data-stu-id="70974-103">Completion status</span></span>

<span data-ttu-id="70974-104">Este tema describe el conjunto de opciones de estado de terminación para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="70974-104">This topic describes the Completion status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="70974-105">Nombre físico: mshr_hcmcompletionstatus</span><span class="sxs-lookup"><span data-stu-id="70974-105">Physical name: mshr_hcmcompletionstatus</span></span>

<span data-ttu-id="70974-106">Esta enumeración proporciona el conjunto de opciones de valores de estado para el cribado de candidatos.</span><span class="sxs-lookup"><span data-stu-id="70974-106">This enumeration provides the option set of status values for candidate screenings.</span></span> 

| <span data-ttu-id="70974-107">Valor</span><span class="sxs-lookup"><span data-stu-id="70974-107">Value</span></span> | <span data-ttu-id="70974-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="70974-108">Label</span></span> | <span data-ttu-id="70974-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="70974-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="70974-110">200000000</span><span class="sxs-lookup"><span data-stu-id="70974-110">200000000</span></span> | <span data-ttu-id="70974-111">Incompleto</span><span class="sxs-lookup"><span data-stu-id="70974-111">Not Complete</span></span> | <span data-ttu-id="70974-112">El candidato aún no ha completado el cribado.</span><span class="sxs-lookup"><span data-stu-id="70974-112">The candidate has not yet completed the screening.</span></span> |
| <span data-ttu-id="70974-113">200000001</span><span class="sxs-lookup"><span data-stu-id="70974-113">200000001</span></span> | <span data-ttu-id="70974-114">Correcto</span><span class="sxs-lookup"><span data-stu-id="70974-114">Pass</span></span> | <span data-ttu-id="70974-115">El candidato ha superado el cribado.</span><span class="sxs-lookup"><span data-stu-id="70974-115">The candidate has passed the screening.</span></span> |
| <span data-ttu-id="70974-116">200000002</span><span class="sxs-lookup"><span data-stu-id="70974-116">200000002</span></span> | <span data-ttu-id="70974-117">Error</span><span class="sxs-lookup"><span data-stu-id="70974-117">Fail</span></span> | <span data-ttu-id="70974-118">El candidato no ha superado el cribado.</span><span class="sxs-lookup"><span data-stu-id="70974-118">The candidate has failed the screening.</span></span> |

## <a name="see-also"></a><span data-ttu-id="70974-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="70974-119">See also</span></span>

[<span data-ttu-id="70974-120">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="70974-120">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="70974-121">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="70974-121">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)
