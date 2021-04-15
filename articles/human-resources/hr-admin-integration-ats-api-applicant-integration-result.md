---
title: Resultado de integración de candidatos
description: Este tema describe el conjunto de opciones de resultados de integración del solicitante para Dynamics 365 Human Resources.
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
ms.openlocfilehash: e8e41fe485cc70a668d4610ce6eabba5cd16ac86
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795126"
---
# <a name="applicant-integration-result"></a><span data-ttu-id="8c269-103">Resultado de integración de candidatos</span><span class="sxs-lookup"><span data-stu-id="8c269-103">Applicant integration result</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8c269-104">Este tema describe el conjunto de opciones de resultados de integración del solicitante para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8c269-104">This topic describes the Applicant integration result option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="8c269-105">Nombre físico: mshr_hcmapplicantintegrationresult</span><span class="sxs-lookup"><span data-stu-id="8c269-105">Physical name: mshr_hcmapplicantintegrationresult</span></span>

<span data-ttu-id="8c269-106">Esta enumeración proporciona el estado de un registro de candidato.</span><span class="sxs-lookup"><span data-stu-id="8c269-106">This enumeration provides status for a candidate record.</span></span>

| <span data-ttu-id="8c269-107">Valor</span><span class="sxs-lookup"><span data-stu-id="8c269-107">Value</span></span> | <span data-ttu-id="8c269-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="8c269-108">Label</span></span> | <span data-ttu-id="8c269-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c269-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="8c269-110">200000000</span><span class="sxs-lookup"><span data-stu-id="8c269-110">200000000</span></span> | <span data-ttu-id="8c269-111">No procesado</span><span class="sxs-lookup"><span data-stu-id="8c269-111">Not processed</span></span> | <span data-ttu-id="8c269-112">El candidato aún está bajo consideración.</span><span class="sxs-lookup"><span data-stu-id="8c269-112">Candidate is still under consideration.</span></span> |
| <span data-ttu-id="8c269-113">200000001</span><span class="sxs-lookup"><span data-stu-id="8c269-113">200000001</span></span> | <span data-ttu-id="8c269-114">Contratado</span><span class="sxs-lookup"><span data-stu-id="8c269-114">Hired</span></span> | <span data-ttu-id="8c269-115">El candidato ha sido contratado.</span><span class="sxs-lookup"><span data-stu-id="8c269-115">The candidate has been hired.</span></span> |
| <span data-ttu-id="8c269-116">200000002</span><span class="sxs-lookup"><span data-stu-id="8c269-116">200000002</span></span> | <span data-ttu-id="8c269-117">No contratado</span><span class="sxs-lookup"><span data-stu-id="8c269-117">Not hired</span></span> | <span data-ttu-id="8c269-118">Se tomó la decisión de no contratar al candidato.</span><span class="sxs-lookup"><span data-stu-id="8c269-118">Decision was made to not hire the candidate.</span></span> |
| <span data-ttu-id="8c269-119">200000003</span><span class="sxs-lookup"><span data-stu-id="8c269-119">200000003</span></span> | <span data-ttu-id="8c269-120">Descartado</span><span class="sxs-lookup"><span data-stu-id="8c269-120">Dismissed</span></span> | <span data-ttu-id="8c269-121">El candidato fue descartado del planteamiento.</span><span class="sxs-lookup"><span data-stu-id="8c269-121">The candidate was dismissed from consideration.</span></span> |

## <a name="see-also"></a><span data-ttu-id="8c269-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c269-122">See also</span></span>

[<span data-ttu-id="8c269-123">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="8c269-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="8c269-124">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="8c269-124">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]