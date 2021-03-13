---
title: Estado de posición de solicitud de reclutamiento
description: Este tema describe el conjunto de opciones de estado de puesto de solicitud de contratación para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 3f7bae64f58f0bdc1603b3c1b5493f1ebcfa8de9
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126059"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="fdb36-103">Estado de posición de solicitud de reclutamiento</span><span class="sxs-lookup"><span data-stu-id="fdb36-103">Recruiting request position status</span></span>

<span data-ttu-id="fdb36-104">Este tema describe el conjunto de opciones de estado de puesto de solicitud de contratación para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fdb36-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="fdb36-105">Nombre físico: mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="fdb36-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="fdb36-106">Esta enumeración proporciona el conjunto de opciones para los valores de estado de cada puesto y una solicitud de contratación en la entidad RecruitingRequestPosition.</span><span class="sxs-lookup"><span data-stu-id="fdb36-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="fdb36-107">Valor</span><span class="sxs-lookup"><span data-stu-id="fdb36-107">Value</span></span> | <span data-ttu-id="fdb36-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="fdb36-108">Label</span></span> | <span data-ttu-id="fdb36-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="fdb36-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="fdb36-110">200000000</span><span class="sxs-lookup"><span data-stu-id="fdb36-110">200000000</span></span> | <span data-ttu-id="fdb36-111">Abiertas</span><span class="sxs-lookup"><span data-stu-id="fdb36-111">Open</span></span> | <span data-ttu-id="fdb36-112">El puesto en la solicitud de contratación está abierto para la contratación.</span><span class="sxs-lookup"><span data-stu-id="fdb36-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="fdb36-113">Esto no indica que no haya una asignación de puesto activa actualmente para el puesto.</span><span class="sxs-lookup"><span data-stu-id="fdb36-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="fdb36-114">Puede haber un empleado en el puesto en el momento de la contratación.</span><span class="sxs-lookup"><span data-stu-id="fdb36-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="fdb36-115">Solo indica que el puesto está disponible para contratación en el contexto de la solicitud de contratación.</span><span class="sxs-lookup"><span data-stu-id="fdb36-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="fdb36-116">200000001</span><span class="sxs-lookup"><span data-stu-id="fdb36-116">200000001</span></span> | <span data-ttu-id="fdb36-117">Relleno</span><span class="sxs-lookup"><span data-stu-id="fdb36-117">Filled</span></span> | <span data-ttu-id="fdb36-118">Se ha seleccionado un trabajador para asignárselo al puesto.</span><span class="sxs-lookup"><span data-stu-id="fdb36-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="fdb36-119">200000002</span><span class="sxs-lookup"><span data-stu-id="fdb36-119">200000002</span></span> | <span data-ttu-id="fdb36-120">Cancelados</span><span class="sxs-lookup"><span data-stu-id="fdb36-120">Canceled</span></span> | <span data-ttu-id="fdb36-121">Se ha cancelado la solicitud de contratación para este puesto.</span><span class="sxs-lookup"><span data-stu-id="fdb36-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="fdb36-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fdb36-122">See also</span></span>

[<span data-ttu-id="fdb36-123">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="fdb36-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="fdb36-124">Consulta de ejemplo para solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="fdb36-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)
