---
title: Origen de generación de la frecuencia de cribado
description: Este tema describe la frecuencia de cribado generada a partir del conjunto de opciones para Dynamics 365 Human Resources.
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
ms.openlocfilehash: ae5ad3e556f40cedd385d8aadded9ef76447a98b
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054101"
---
# <a name="screening-frequency-generate-from"></a><span data-ttu-id="8a022-103">Origen de generación de la frecuencia de cribado</span><span class="sxs-lookup"><span data-stu-id="8a022-103">Screening frequency generate from</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8a022-104">Este tema describe la frecuencia de cribado generada a partir del conjunto de opciones para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8a022-104">This topic describes the Screening frequency generate from option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="8a022-105">Nombre físico: mshr_hcmfrequencygeneratefrom</span><span class="sxs-lookup"><span data-stu-id="8a022-105">Physical name: mshr_hcmfrequencygeneratefrom</span></span>

<span data-ttu-id="8a022-106">Esta enumeración proporciona el conjunto de opciones de valores para determinar la fecha de inicio del cálculo para el siguiente cribado necesario.</span><span class="sxs-lookup"><span data-stu-id="8a022-106">This enumeration provides the option set of values for determining the start date of the calculation for the next required screening.</span></span>

| <span data-ttu-id="8a022-107">Valor</span><span class="sxs-lookup"><span data-stu-id="8a022-107">Value</span></span> | <span data-ttu-id="8a022-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="8a022-108">Label</span></span> | <span data-ttu-id="8a022-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a022-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="8a022-110">200000000 No seleccionado</span><span class="sxs-lookup"><span data-stu-id="8a022-110">200000000 Not selected</span></span> | <span data-ttu-id="8a022-111">No se ha seleccionado ningún valor.</span><span class="sxs-lookup"><span data-stu-id="8a022-111">No value has been selected.</span></span> |
| <span data-ttu-id="8a022-112">200000001 Fecha de finalización</span><span class="sxs-lookup"><span data-stu-id="8a022-112">200000001 Date completed</span></span> | <span data-ttu-id="8a022-113">El cálculo se realiza a partir de la última fecha de cribado completada.</span><span class="sxs-lookup"><span data-stu-id="8a022-113">Calculation is done from the last screening date completed.</span></span> |
| <span data-ttu-id="8a022-114">200000002 Fecha es obligatoria</span><span class="sxs-lookup"><span data-stu-id="8a022-114">200000002 Date required</span></span> | <span data-ttu-id="8a022-115">El cálculo se realiza a partir de la última fecha de cribado obligatoria.</span><span class="sxs-lookup"><span data-stu-id="8a022-115">Calculation is done from the last screening date required.</span></span> |

## <a name="see-also"></a><span data-ttu-id="8a022-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a022-116">See also</span></span>

[<span data-ttu-id="8a022-117">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="8a022-117">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="8a022-118">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="8a022-118">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]