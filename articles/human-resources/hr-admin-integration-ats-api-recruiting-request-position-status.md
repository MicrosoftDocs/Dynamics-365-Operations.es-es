---
title: Estado de posición de solicitud de reclutamiento
description: Este tema describe el conjunto de opciones de estado de puesto de solicitud de contratación para Dynamics 365 Human Resources.
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
ms.openlocfilehash: e287ec4b9b78194b76ef3c993c6ce32f808e26f9
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051890"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="9763c-103">Estado de posición de solicitud de reclutamiento</span><span class="sxs-lookup"><span data-stu-id="9763c-103">Recruiting request position status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="9763c-104">Este tema describe el conjunto de opciones de estado de puesto de solicitud de contratación para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9763c-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="9763c-105">Nombre físico: mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="9763c-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="9763c-106">Esta enumeración proporciona el conjunto de opciones para los valores de estado de cada puesto y una solicitud de contratación en la entidad RecruitingRequestPosition.</span><span class="sxs-lookup"><span data-stu-id="9763c-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="9763c-107">Valor</span><span class="sxs-lookup"><span data-stu-id="9763c-107">Value</span></span> | <span data-ttu-id="9763c-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="9763c-108">Label</span></span> | <span data-ttu-id="9763c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9763c-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="9763c-110">200000000</span><span class="sxs-lookup"><span data-stu-id="9763c-110">200000000</span></span> | <span data-ttu-id="9763c-111">Abiertas</span><span class="sxs-lookup"><span data-stu-id="9763c-111">Open</span></span> | <span data-ttu-id="9763c-112">El puesto en la solicitud de contratación está abierto para la contratación.</span><span class="sxs-lookup"><span data-stu-id="9763c-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="9763c-113">Esto no indica que no haya una asignación de puesto activa actualmente para el puesto.</span><span class="sxs-lookup"><span data-stu-id="9763c-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="9763c-114">Puede haber un empleado en el puesto en el momento de la contratación.</span><span class="sxs-lookup"><span data-stu-id="9763c-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="9763c-115">Solo indica que el puesto está disponible para contratación en el contexto de la solicitud de contratación.</span><span class="sxs-lookup"><span data-stu-id="9763c-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="9763c-116">200000001</span><span class="sxs-lookup"><span data-stu-id="9763c-116">200000001</span></span> | <span data-ttu-id="9763c-117">Relleno</span><span class="sxs-lookup"><span data-stu-id="9763c-117">Filled</span></span> | <span data-ttu-id="9763c-118">Se ha seleccionado un trabajador para asignárselo al puesto.</span><span class="sxs-lookup"><span data-stu-id="9763c-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="9763c-119">200000002</span><span class="sxs-lookup"><span data-stu-id="9763c-119">200000002</span></span> | <span data-ttu-id="9763c-120">Cancelados</span><span class="sxs-lookup"><span data-stu-id="9763c-120">Canceled</span></span> | <span data-ttu-id="9763c-121">Se ha cancelado la solicitud de contratación para este puesto.</span><span class="sxs-lookup"><span data-stu-id="9763c-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="9763c-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9763c-122">See also</span></span>

[<span data-ttu-id="9763c-123">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="9763c-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="9763c-124">Consulta de ejemplo para solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="9763c-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]