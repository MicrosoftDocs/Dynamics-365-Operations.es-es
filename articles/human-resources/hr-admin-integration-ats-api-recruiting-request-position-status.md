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
ms.openlocfilehash: 01e8aa5157d0ad1c01f996886e7845e49ab97603
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464727"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="ee1c3-103">Estado de posición de solicitud de reclutamiento</span><span class="sxs-lookup"><span data-stu-id="ee1c3-103">Recruiting request position status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="ee1c3-104">Este tema describe el conjunto de opciones de estado de puesto de solicitud de contratación para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ee1c3-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="ee1c3-105">Nombre físico: mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="ee1c3-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="ee1c3-106">Esta enumeración proporciona el conjunto de opciones para los valores de estado de cada puesto y una solicitud de contratación en la entidad RecruitingRequestPosition.</span><span class="sxs-lookup"><span data-stu-id="ee1c3-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="ee1c3-107">Valor</span><span class="sxs-lookup"><span data-stu-id="ee1c3-107">Value</span></span> | <span data-ttu-id="ee1c3-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="ee1c3-108">Label</span></span> | <span data-ttu-id="ee1c3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee1c3-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="ee1c3-110">200000000</span><span class="sxs-lookup"><span data-stu-id="ee1c3-110">200000000</span></span> | <span data-ttu-id="ee1c3-111">Abiertas</span><span class="sxs-lookup"><span data-stu-id="ee1c3-111">Open</span></span> | <span data-ttu-id="ee1c3-112">El puesto en la solicitud de contratación está abierto para la contratación.</span><span class="sxs-lookup"><span data-stu-id="ee1c3-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="ee1c3-113">Esto no indica que no haya una asignación de puesto activa actualmente para el puesto.</span><span class="sxs-lookup"><span data-stu-id="ee1c3-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="ee1c3-114">Puede haber un empleado en el puesto en el momento de la contratación.</span><span class="sxs-lookup"><span data-stu-id="ee1c3-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="ee1c3-115">Solo indica que el puesto está disponible para contratación en el contexto de la solicitud de contratación.</span><span class="sxs-lookup"><span data-stu-id="ee1c3-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="ee1c3-116">200000001</span><span class="sxs-lookup"><span data-stu-id="ee1c3-116">200000001</span></span> | <span data-ttu-id="ee1c3-117">Relleno</span><span class="sxs-lookup"><span data-stu-id="ee1c3-117">Filled</span></span> | <span data-ttu-id="ee1c3-118">Se ha seleccionado un trabajador para asignárselo al puesto.</span><span class="sxs-lookup"><span data-stu-id="ee1c3-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="ee1c3-119">200000002</span><span class="sxs-lookup"><span data-stu-id="ee1c3-119">200000002</span></span> | <span data-ttu-id="ee1c3-120">Cancelados</span><span class="sxs-lookup"><span data-stu-id="ee1c3-120">Canceled</span></span> | <span data-ttu-id="ee1c3-121">Se ha cancelado la solicitud de contratación para este puesto.</span><span class="sxs-lookup"><span data-stu-id="ee1c3-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="ee1c3-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee1c3-122">See also</span></span>

[<span data-ttu-id="ee1c3-123">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="ee1c3-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="ee1c3-124">Consulta de ejemplo para solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="ee1c3-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]