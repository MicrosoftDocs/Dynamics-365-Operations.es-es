---
title: Estado de finalización
description: Este tema describe el conjunto de opciones de estado de terminación para Dynamics 365 Human Resources.
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
ms.openlocfilehash: f1b0c61ac9d9dc611d2a4700a1a004e3d15b4445
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798378"
---
# <a name="completion-status"></a><span data-ttu-id="82eaf-103">Estado de finalización</span><span class="sxs-lookup"><span data-stu-id="82eaf-103">Completion status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="82eaf-104">Este tema describe el conjunto de opciones de estado de terminación para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="82eaf-104">This topic describes the Completion status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="82eaf-105">Nombre físico: mshr_hcmcompletionstatus</span><span class="sxs-lookup"><span data-stu-id="82eaf-105">Physical name: mshr_hcmcompletionstatus</span></span>

<span data-ttu-id="82eaf-106">Esta enumeración proporciona el conjunto de opciones de valores de estado para el cribado de candidatos.</span><span class="sxs-lookup"><span data-stu-id="82eaf-106">This enumeration provides the option set of status values for candidate screenings.</span></span> 

| <span data-ttu-id="82eaf-107">Valor</span><span class="sxs-lookup"><span data-stu-id="82eaf-107">Value</span></span> | <span data-ttu-id="82eaf-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="82eaf-108">Label</span></span> | <span data-ttu-id="82eaf-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="82eaf-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="82eaf-110">200000000</span><span class="sxs-lookup"><span data-stu-id="82eaf-110">200000000</span></span> | <span data-ttu-id="82eaf-111">Incompleto</span><span class="sxs-lookup"><span data-stu-id="82eaf-111">Not Complete</span></span> | <span data-ttu-id="82eaf-112">El candidato aún no ha completado el cribado.</span><span class="sxs-lookup"><span data-stu-id="82eaf-112">The candidate has not yet completed the screening.</span></span> |
| <span data-ttu-id="82eaf-113">200000001</span><span class="sxs-lookup"><span data-stu-id="82eaf-113">200000001</span></span> | <span data-ttu-id="82eaf-114">Correcto</span><span class="sxs-lookup"><span data-stu-id="82eaf-114">Pass</span></span> | <span data-ttu-id="82eaf-115">El candidato ha superado el cribado.</span><span class="sxs-lookup"><span data-stu-id="82eaf-115">The candidate has passed the screening.</span></span> |
| <span data-ttu-id="82eaf-116">200000002</span><span class="sxs-lookup"><span data-stu-id="82eaf-116">200000002</span></span> | <span data-ttu-id="82eaf-117">Error</span><span class="sxs-lookup"><span data-stu-id="82eaf-117">Fail</span></span> | <span data-ttu-id="82eaf-118">El candidato no ha superado el cribado.</span><span class="sxs-lookup"><span data-stu-id="82eaf-118">The candidate has failed the screening.</span></span> |

## <a name="see-also"></a><span data-ttu-id="82eaf-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82eaf-119">See also</span></span>

[<span data-ttu-id="82eaf-120">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="82eaf-120">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="82eaf-121">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="82eaf-121">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]