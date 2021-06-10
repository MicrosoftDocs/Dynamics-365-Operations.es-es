---
title: Estado de exención de trabajo
description: Este tema describe el conjunto de opciones de estado de exención de trabajo para Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8e91fbb420009d5131e2faa7dbea8a302a027e0a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053860"
---
# <a name="job-exempt-status"></a><span data-ttu-id="2b269-103">Estado de exención de trabajo</span><span class="sxs-lookup"><span data-stu-id="2b269-103">Job exempt status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2b269-104">Este tema describe el conjunto de opciones de estado de exención de trabajo para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2b269-104">This topic describes the Job exempt status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="2b269-105">Nombre físico: cdm_jobexemptstatus</span><span class="sxs-lookup"><span data-stu-id="2b269-105">Physical name: cdm_jobexemptstatus</span></span>

<span data-ttu-id="2b269-106">Esta enumeración especifica el conjunto de opciones para valores de estado de exención de trabajo FLSA.</span><span class="sxs-lookup"><span data-stu-id="2b269-106">This enumeration specifies the option set for FLSA job exempt status values.</span></span> <span data-ttu-id="2b269-107">Esto se ofrece en el conjunto de opciones cdm_jobexemptstatus existente.</span><span class="sxs-lookup"><span data-stu-id="2b269-107">This is provided in the existing cdm_jobexemptstatus option set.</span></span>

| <span data-ttu-id="2b269-108">Valor</span><span class="sxs-lookup"><span data-stu-id="2b269-108">Value</span></span> | <span data-ttu-id="2b269-109">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="2b269-109">Label</span></span> | <span data-ttu-id="2b269-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b269-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="2b269-111">200000000</span><span class="sxs-lookup"><span data-stu-id="2b269-111">200000000</span></span> | <span data-ttu-id="2b269-112">Exento</span><span class="sxs-lookup"><span data-stu-id="2b269-112">Exempt</span></span> | <span data-ttu-id="2b269-113">El trabajo tiene un estado de exención según las pautas de la FLSA.</span><span class="sxs-lookup"><span data-stu-id="2b269-113">The job has an exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="2b269-114">200000001</span><span class="sxs-lookup"><span data-stu-id="2b269-114">200000001</span></span> | <span data-ttu-id="2b269-115">NonExempt</span><span class="sxs-lookup"><span data-stu-id="2b269-115">NonExempt</span></span> | <span data-ttu-id="2b269-116">El trabajo tiene un estado de no exención según las pautas de la FLSA.</span><span class="sxs-lookup"><span data-stu-id="2b269-116">The job has a non-exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="2b269-117">200000002</span><span class="sxs-lookup"><span data-stu-id="2b269-117">200000002</span></span> | <span data-ttu-id="2b269-118">No aplicable</span><span class="sxs-lookup"><span data-stu-id="2b269-118">Does Not Apply</span></span> | <span data-ttu-id="2b269-119">Las pautas de estado de la FLSA no se aplican al trabajo.</span><span class="sxs-lookup"><span data-stu-id="2b269-119">FLSA status guidelines do not apply to the job.</span></span> |

## <a name="see-also"></a><span data-ttu-id="2b269-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b269-120">See also</span></span>

[<span data-ttu-id="2b269-121">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="2b269-121">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="2b269-122">Consulta de ejemplo para solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="2b269-122">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]