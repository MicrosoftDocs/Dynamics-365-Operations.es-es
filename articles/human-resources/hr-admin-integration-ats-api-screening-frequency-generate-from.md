---
title: Origen de generación de la frecuencia de cribado
description: Este tema describe la frecuencia de cribado generada a partir del conjunto de opciones para Dynamics 365 Human Resources.
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
ms.openlocfilehash: f291e28584dadc465092d99a1354fda793ff7560
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126155"
---
# <a name="screening-frequency-generate-from"></a><span data-ttu-id="4c694-103">Origen de generación de la frecuencia de cribado</span><span class="sxs-lookup"><span data-stu-id="4c694-103">Screening frequency generate from</span></span>

<span data-ttu-id="4c694-104">Este tema describe la frecuencia de cribado generada a partir del conjunto de opciones para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4c694-104">This topic describes the Screening frequency generate from option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="4c694-105">Nombre físico: mshr_hcmfrequencygeneratefrom</span><span class="sxs-lookup"><span data-stu-id="4c694-105">Physical name: mshr_hcmfrequencygeneratefrom</span></span>

<span data-ttu-id="4c694-106">Esta enumeración proporciona el conjunto de opciones de valores para determinar la fecha de inicio del cálculo para el siguiente cribado necesario.</span><span class="sxs-lookup"><span data-stu-id="4c694-106">This enumeration provides the option set of values for determining the start date of the calculation for the next required screening.</span></span>

| <span data-ttu-id="4c694-107">Valor</span><span class="sxs-lookup"><span data-stu-id="4c694-107">Value</span></span> | <span data-ttu-id="4c694-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="4c694-108">Label</span></span> | <span data-ttu-id="4c694-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c694-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="4c694-110">200000000 No seleccionado</span><span class="sxs-lookup"><span data-stu-id="4c694-110">200000000 Not selected</span></span> | <span data-ttu-id="4c694-111">No se ha seleccionado ningún valor.</span><span class="sxs-lookup"><span data-stu-id="4c694-111">No value has been selected.</span></span> |
| <span data-ttu-id="4c694-112">200000001 Fecha de finalización</span><span class="sxs-lookup"><span data-stu-id="4c694-112">200000001 Date completed</span></span> | <span data-ttu-id="4c694-113">El cálculo se realiza a partir de la última fecha de cribado completada.</span><span class="sxs-lookup"><span data-stu-id="4c694-113">Calculation is done from the last screening date completed.</span></span> |
| <span data-ttu-id="4c694-114">200000002 Fecha es obligatoria</span><span class="sxs-lookup"><span data-stu-id="4c694-114">200000002 Date required</span></span> | <span data-ttu-id="4c694-115">El cálculo se realiza a partir de la última fecha de cribado obligatoria.</span><span class="sxs-lookup"><span data-stu-id="4c694-115">Calculation is done from the last screening date required.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4c694-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c694-116">See also</span></span>

[<span data-ttu-id="4c694-117">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="4c694-117">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="4c694-118">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="4c694-118">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)
