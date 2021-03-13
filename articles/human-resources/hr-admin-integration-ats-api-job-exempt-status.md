---
title: Estado de exención de trabajo
description: Este tema describe el conjunto de opciones de estado de exención de trabajo para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 0cd6ffc01793c8ff12e36175c7c9feaf8a4b3cdf
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125578"
---
# <a name="job-exempt-status"></a><span data-ttu-id="143e4-103">Estado de exención de trabajo</span><span class="sxs-lookup"><span data-stu-id="143e4-103">Job exempt status</span></span>

<span data-ttu-id="143e4-104">Este tema describe el conjunto de opciones de estado de exención de trabajo para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="143e4-104">This topic describes the Job exempt status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="143e4-105">Nombre físico: cdm_jobexemptstatus</span><span class="sxs-lookup"><span data-stu-id="143e4-105">Physical name: cdm_jobexemptstatus</span></span>

<span data-ttu-id="143e4-106">Esta enumeración especifica el conjunto de opciones para valores de estado de exención de trabajo FLSA.</span><span class="sxs-lookup"><span data-stu-id="143e4-106">This enumeration specifies the option set for FLSA job exempt status values.</span></span> <span data-ttu-id="143e4-107">Esto se ofrece en el conjunto de opciones cdm_jobexemptstatus existente.</span><span class="sxs-lookup"><span data-stu-id="143e4-107">This is provided in the existing cdm_jobexemptstatus option set.</span></span>

| <span data-ttu-id="143e4-108">Valor</span><span class="sxs-lookup"><span data-stu-id="143e4-108">Value</span></span> | <span data-ttu-id="143e4-109">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="143e4-109">Label</span></span> | <span data-ttu-id="143e4-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="143e4-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="143e4-111">200000000</span><span class="sxs-lookup"><span data-stu-id="143e4-111">200000000</span></span> | <span data-ttu-id="143e4-112">Exento</span><span class="sxs-lookup"><span data-stu-id="143e4-112">Exempt</span></span> | <span data-ttu-id="143e4-113">El trabajo tiene un estado de exención según las pautas de la FLSA.</span><span class="sxs-lookup"><span data-stu-id="143e4-113">The job has an exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="143e4-114">200000001</span><span class="sxs-lookup"><span data-stu-id="143e4-114">200000001</span></span> | <span data-ttu-id="143e4-115">NonExempt</span><span class="sxs-lookup"><span data-stu-id="143e4-115">NonExempt</span></span> | <span data-ttu-id="143e4-116">El trabajo tiene un estado de no exención según las pautas de la FLSA.</span><span class="sxs-lookup"><span data-stu-id="143e4-116">The job has a non-exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="143e4-117">200000002</span><span class="sxs-lookup"><span data-stu-id="143e4-117">200000002</span></span> | <span data-ttu-id="143e4-118">No aplicable</span><span class="sxs-lookup"><span data-stu-id="143e4-118">Does Not Apply</span></span> | <span data-ttu-id="143e4-119">Las pautas de estado de la FLSA no se aplican al trabajo.</span><span class="sxs-lookup"><span data-stu-id="143e4-119">FLSA status guidelines do not apply to the job.</span></span> |

## <a name="see-also"></a><span data-ttu-id="143e4-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="143e4-120">See also</span></span>

[<span data-ttu-id="143e4-121">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="143e4-121">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="143e4-122">Consulta de ejemplo para solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="143e4-122">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)
