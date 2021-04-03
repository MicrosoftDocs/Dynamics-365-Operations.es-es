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
ms.openlocfilehash: d8ea90785f303301a21a4ac799578b08cabd0e3d
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468212"
---
# <a name="completion-status"></a><span data-ttu-id="825cb-103">Estado de finalización</span><span class="sxs-lookup"><span data-stu-id="825cb-103">Completion status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="825cb-104">Este tema describe el conjunto de opciones de estado de terminación para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="825cb-104">This topic describes the Completion status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="825cb-105">Nombre físico: mshr_hcmcompletionstatus</span><span class="sxs-lookup"><span data-stu-id="825cb-105">Physical name: mshr_hcmcompletionstatus</span></span>

<span data-ttu-id="825cb-106">Esta enumeración proporciona el conjunto de opciones de valores de estado para el cribado de candidatos.</span><span class="sxs-lookup"><span data-stu-id="825cb-106">This enumeration provides the option set of status values for candidate screenings.</span></span> 

| <span data-ttu-id="825cb-107">Valor</span><span class="sxs-lookup"><span data-stu-id="825cb-107">Value</span></span> | <span data-ttu-id="825cb-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="825cb-108">Label</span></span> | <span data-ttu-id="825cb-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="825cb-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="825cb-110">200000000</span><span class="sxs-lookup"><span data-stu-id="825cb-110">200000000</span></span> | <span data-ttu-id="825cb-111">Incompleto</span><span class="sxs-lookup"><span data-stu-id="825cb-111">Not Complete</span></span> | <span data-ttu-id="825cb-112">El candidato aún no ha completado el cribado.</span><span class="sxs-lookup"><span data-stu-id="825cb-112">The candidate has not yet completed the screening.</span></span> |
| <span data-ttu-id="825cb-113">200000001</span><span class="sxs-lookup"><span data-stu-id="825cb-113">200000001</span></span> | <span data-ttu-id="825cb-114">Correcto</span><span class="sxs-lookup"><span data-stu-id="825cb-114">Pass</span></span> | <span data-ttu-id="825cb-115">El candidato ha superado el cribado.</span><span class="sxs-lookup"><span data-stu-id="825cb-115">The candidate has passed the screening.</span></span> |
| <span data-ttu-id="825cb-116">200000002</span><span class="sxs-lookup"><span data-stu-id="825cb-116">200000002</span></span> | <span data-ttu-id="825cb-117">Error</span><span class="sxs-lookup"><span data-stu-id="825cb-117">Fail</span></span> | <span data-ttu-id="825cb-118">El candidato no ha superado el cribado.</span><span class="sxs-lookup"><span data-stu-id="825cb-118">The candidate has failed the screening.</span></span> |

## <a name="see-also"></a><span data-ttu-id="825cb-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="825cb-119">See also</span></span>

[<span data-ttu-id="825cb-120">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="825cb-120">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="825cb-121">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="825cb-121">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]