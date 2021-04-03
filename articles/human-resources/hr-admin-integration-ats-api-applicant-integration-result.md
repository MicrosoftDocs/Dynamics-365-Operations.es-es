---
title: Resultado de integración de candidatos
description: Este tema describe el conjunto de opciones de resultados de integración del solicitante para Dynamics 365 Human Resources.
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
ms.openlocfilehash: dd25eca9cccf46ec4e4bb2a1d948ca98985e73e4
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467562"
---
# <a name="applicant-integration-result"></a><span data-ttu-id="84850-103">Resultado de integración de candidatos</span><span class="sxs-lookup"><span data-stu-id="84850-103">Applicant integration result</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="84850-104">Este tema describe el conjunto de opciones de resultados de integración del solicitante para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="84850-104">This topic describes the Applicant integration result option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="84850-105">Nombre físico: mshr_hcmapplicantintegrationresult</span><span class="sxs-lookup"><span data-stu-id="84850-105">Physical name: mshr_hcmapplicantintegrationresult</span></span>

<span data-ttu-id="84850-106">Esta enumeración proporciona el estado de un registro de candidato.</span><span class="sxs-lookup"><span data-stu-id="84850-106">This enumeration provides status for a candidate record.</span></span>

| <span data-ttu-id="84850-107">Valor</span><span class="sxs-lookup"><span data-stu-id="84850-107">Value</span></span> | <span data-ttu-id="84850-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="84850-108">Label</span></span> | <span data-ttu-id="84850-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="84850-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="84850-110">200000000</span><span class="sxs-lookup"><span data-stu-id="84850-110">200000000</span></span> | <span data-ttu-id="84850-111">No procesado</span><span class="sxs-lookup"><span data-stu-id="84850-111">Not processed</span></span> | <span data-ttu-id="84850-112">El candidato aún está bajo consideración.</span><span class="sxs-lookup"><span data-stu-id="84850-112">Candidate is still under consideration.</span></span> |
| <span data-ttu-id="84850-113">200000001</span><span class="sxs-lookup"><span data-stu-id="84850-113">200000001</span></span> | <span data-ttu-id="84850-114">Contratado</span><span class="sxs-lookup"><span data-stu-id="84850-114">Hired</span></span> | <span data-ttu-id="84850-115">El candidato ha sido contratado.</span><span class="sxs-lookup"><span data-stu-id="84850-115">The candidate has been hired.</span></span> |
| <span data-ttu-id="84850-116">200000002</span><span class="sxs-lookup"><span data-stu-id="84850-116">200000002</span></span> | <span data-ttu-id="84850-117">No contratado</span><span class="sxs-lookup"><span data-stu-id="84850-117">Not hired</span></span> | <span data-ttu-id="84850-118">Se tomó la decisión de no contratar al candidato.</span><span class="sxs-lookup"><span data-stu-id="84850-118">Decision was made to not hire the candidate.</span></span> |
| <span data-ttu-id="84850-119">200000003</span><span class="sxs-lookup"><span data-stu-id="84850-119">200000003</span></span> | <span data-ttu-id="84850-120">Descartado</span><span class="sxs-lookup"><span data-stu-id="84850-120">Dismissed</span></span> | <span data-ttu-id="84850-121">El candidato fue descartado del planteamiento.</span><span class="sxs-lookup"><span data-stu-id="84850-121">The candidate was dismissed from consideration.</span></span> |

## <a name="see-also"></a><span data-ttu-id="84850-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84850-122">See also</span></span>

[<span data-ttu-id="84850-123">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="84850-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="84850-124">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="84850-124">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]