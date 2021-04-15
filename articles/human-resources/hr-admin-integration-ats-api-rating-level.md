---
title: Nivel de evaluación
description: Este tema describe la entidad Nivel de calificación para Dynamics 365 Human Resources.
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
ms.openlocfilehash: eac80599de07a045aa233f1cdfd16fe0db8733a2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800342"
---
# <a name="rating-level"></a><span data-ttu-id="b464d-103">Nivel de evaluación</span><span class="sxs-lookup"><span data-stu-id="b464d-103">Rating level</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b464d-104">Este tema describe la entidad Nivel de calificación para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b464d-104">This topic describes the Rating level entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="b464d-105">Nombre físico: mshr_hcmratinglevelentity</span><span class="sxs-lookup"><span data-stu-id="b464d-105">Physical name: mshr_hcmratinglevelentity</span></span>

## <a name="description"></a><span data-ttu-id="b464d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b464d-106">Description</span></span>

<span data-ttu-id="b464d-107">Esta entidad proporciona los niveles de calificación disponibles para las aptitudes.</span><span class="sxs-lookup"><span data-stu-id="b464d-107">This entity provides the available rating levels for skills.</span></span> <span data-ttu-id="b464d-108">Los niveles de calificación se aplican a todas las entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="b464d-108">Rating levels apply across all legal entities.</span></span>

## <a name="json-representation"></a><span data-ttu-id="b464d-109">Representación JSON</span><span class="sxs-lookup"><span data-stu-id="b464d-109">JSON representation</span></span>

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="b464d-110">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b464d-110">Properties</span></span>

| <span data-ttu-id="b464d-111">Propiedad</span><span class="sxs-lookup"><span data-stu-id="b464d-111">Property</span></span><br><span data-ttu-id="b464d-112">**Nombre físico**</span><span class="sxs-lookup"><span data-stu-id="b464d-112">**Physical name**</span></span><br><span data-ttu-id="b464d-113">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="b464d-113">**_Type_**</span></span> | <span data-ttu-id="b464d-114">Utilizar</span><span class="sxs-lookup"><span data-stu-id="b464d-114">Use</span></span> | <span data-ttu-id="b464d-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="b464d-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b464d-116">**Id. de entidad de nivel de calificación**</span><span class="sxs-lookup"><span data-stu-id="b464d-116">**Rating Level Entity ID**</span></span><br><span data-ttu-id="b464d-117">mshr_hcmratinglevelentityid</span><span class="sxs-lookup"><span data-stu-id="b464d-117">mshr_hcmratinglevelentityid</span></span><br><span data-ttu-id="b464d-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="b464d-118">*GUID*</span></span> | <span data-ttu-id="b464d-119">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="b464d-119">Read-only</span></span><br><span data-ttu-id="b464d-120">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="b464d-120">Required</span></span><br><span data-ttu-id="b464d-121">Generado por el sistema</span><span class="sxs-lookup"><span data-stu-id="b464d-121">System-generated</span></span> | <span data-ttu-id="b464d-122">El identificador único generado por el sistema para el nivel.</span><span class="sxs-lookup"><span data-stu-id="b464d-122">The system-generated unique identifier for the level.</span></span> |
| <span data-ttu-id="b464d-123">**Id. de nivel de calificación**</span><span class="sxs-lookup"><span data-stu-id="b464d-123">**Rating Level ID**</span></span><br><span data-ttu-id="b464d-124">mshr_ratinglevelid</span><span class="sxs-lookup"><span data-stu-id="b464d-124">mshr_ratinglevelid</span></span><br><span data-ttu-id="b464d-125">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="b464d-125">*String*</span></span> | <span data-ttu-id="b464d-126">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="b464d-126">Read/write</span></span><br><span data-ttu-id="b464d-127">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="b464d-127">Required</span></span> | <span data-ttu-id="b464d-128">Identificador único legible por el usuario para el nivel.</span><span class="sxs-lookup"><span data-stu-id="b464d-128">User-readable unique identifier for the level.</span></span> |
| <span data-ttu-id="b464d-129">**Id. de modelo de calificación**</span><span class="sxs-lookup"><span data-stu-id="b464d-129">**Rating Model ID**</span></span><br><span data-ttu-id="b464d-130">mshr_ratingmodelid</span><span class="sxs-lookup"><span data-stu-id="b464d-130">mshr_ratingmodelid</span></span><br><span data-ttu-id="b464d-131">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="b464d-131">*String*</span></span> | <span data-ttu-id="b464d-132">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="b464d-132">Read/write</span></span><br><span data-ttu-id="b464d-133">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="b464d-133">Required</span></span> | <span data-ttu-id="b464d-134">El modelo de calificación al que pertenece el nivel de calificación.</span><span class="sxs-lookup"><span data-stu-id="b464d-134">The rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="b464d-135">**Id. de entidad de modelo de calificación**</span><span class="sxs-lookup"><span data-stu-id="b464d-135">**Rating Model Entity ID**</span></span><br><span data-ttu-id="b464d-136">_mshr_fk_ratingmodelentity_id_value</span><span class="sxs-lookup"><span data-stu-id="b464d-136">_mshr_fk_ratingmodelentity_id_value</span></span><br><span data-ttu-id="b464d-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="b464d-137">*GUID*</span></span> | <span data-ttu-id="b464d-138">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="b464d-138">Read-only</span></span><br><span data-ttu-id="b464d-139">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="b464d-139">Required</span></span><br><span data-ttu-id="b464d-140">Clave externa: mshr_hcmratingmodelentityid de mshr_hcmratingmodelentity</span><span class="sxs-lookup"><span data-stu-id="b464d-140">Foreign key: mshr_hcmratingmodelentityid of mshr_hcmratingmodelentity</span></span> | <span data-ttu-id="b464d-141">El identificador generado por el sistema para el modelo de calificación al que pertenece el nivel de calificación.</span><span class="sxs-lookup"><span data-stu-id="b464d-141">The system-generated identifier for the rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="b464d-142">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b464d-142">**Description**</span></span><br><span data-ttu-id="b464d-143">mshr_description</span><span class="sxs-lookup"><span data-stu-id="b464d-143">mshr_description</span></span><br><span data-ttu-id="b464d-144">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="b464d-144">*String*</span></span> | <span data-ttu-id="b464d-145">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="b464d-145">Read/write</span></span><br><span data-ttu-id="b464d-146">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="b464d-146">Required</span></span> | <span data-ttu-id="b464d-147">La descripción del nivel de calificación.</span><span class="sxs-lookup"><span data-stu-id="b464d-147">The description of the rating level.</span></span> |
| <span data-ttu-id="b464d-148">**Factor**</span><span class="sxs-lookup"><span data-stu-id="b464d-148">**Factor**</span></span><br><span data-ttu-id="b464d-149">mshr_factor</span><span class="sxs-lookup"><span data-stu-id="b464d-149">mshr_factor</span></span><br><span data-ttu-id="b464d-150">*Entero*</span><span class="sxs-lookup"><span data-stu-id="b464d-150">*Integer*</span></span> | <span data-ttu-id="b464d-151">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="b464d-151">Read/write</span></span><br><span data-ttu-id="b464d-152">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="b464d-152">Required</span></span> | <span data-ttu-id="b464d-153">Factor para el nivel de calificación.</span><span class="sxs-lookup"><span data-stu-id="b464d-153">The factor for the rating level.</span></span> <span data-ttu-id="b464d-154">Cuando se comparan elementos con un número diferente de niveles de calificación, el factor se emplea para normalizar puntuaciones.</span><span class="sxs-lookup"><span data-stu-id="b464d-154">When you compare items with a different number of rating levels, the factor is used to normalize the scores.</span></span> <span data-ttu-id="b464d-155">El valor debe ser un número entero entre 0 y 9.</span><span class="sxs-lookup"><span data-stu-id="b464d-155">The value must be an integer between 0 and 9.</span></span> |
| <span data-ttu-id="b464d-156">**Nota**</span><span class="sxs-lookup"><span data-stu-id="b464d-156">**Note**</span></span><br><span data-ttu-id="b464d-157">mshr_note</span><span class="sxs-lookup"><span data-stu-id="b464d-157">mshr_note</span></span><br><span data-ttu-id="b464d-158">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="b464d-158">*String*</span></span> | <span data-ttu-id="b464d-159">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="b464d-159">Read/write</span></span><br><span data-ttu-id="b464d-160">Opcional</span><span class="sxs-lookup"><span data-stu-id="b464d-160">Optional</span></span> | <span data-ttu-id="b464d-161">Las notas asociadas al nivel de calificación.</span><span class="sxs-lookup"><span data-stu-id="b464d-161">Any notes associated with the rating level.</span></span> |
| <span data-ttu-id="b464d-162">**Campo principal**</span><span class="sxs-lookup"><span data-stu-id="b464d-162">**Primary Field**</span></span><br><span data-ttu-id="b464d-163">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="b464d-163">mshr_primaryfield</span></span><br><span data-ttu-id="b464d-164">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="b464d-164">*String*</span></span> | <span data-ttu-id="b464d-165">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="b464d-165">Read-only</span></span><br><span data-ttu-id="b464d-166">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="b464d-166">Required</span></span> | <span data-ttu-id="b464d-167">Campo que se utilizará como identificador principal del registro de entidad.</span><span class="sxs-lookup"><span data-stu-id="b464d-167">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="b464d-168">Combinación del id. de nivel de calificación y el id. de modelo de calificación.</span><span class="sxs-lookup"><span data-stu-id="b464d-168">Combination of rating level ID and rating model ID.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b464d-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b464d-169">See also</span></span>

[<span data-ttu-id="b464d-170">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="b464d-170">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="b464d-171">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="b464d-171">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]