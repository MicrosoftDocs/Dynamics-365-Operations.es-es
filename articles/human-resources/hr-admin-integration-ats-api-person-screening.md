---
title: Filtrado de persona
description: Este tema describe la entidad Cribado de la persona para Dynamics 365 Human Resources.
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
ms.openlocfilehash: d76bb57d85ee16f4faa0bb9cfec77047feb7df5f
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125386"
---
# <a name="person-screening"></a><span data-ttu-id="5d3f6-103">Filtrado de persona</span><span class="sxs-lookup"><span data-stu-id="5d3f6-103">Person screening</span></span>

<span data-ttu-id="5d3f6-104">Este tema describe la entidad Cribado de la persona para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5d3f6-104">This topic describes the Person screening entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="5d3f6-105">Nombre físico: mshr_hcmpersonscreeningentity</span><span class="sxs-lookup"><span data-stu-id="5d3f6-105">Physical name: mshr_hcmpersonscreeningentity</span></span>

## <a name="description"></a><span data-ttu-id="5d3f6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d3f6-106">Description</span></span>

<span data-ttu-id="5d3f6-107">Esta entidad describe los cribados que un candidato ha superado o debe superar para conseguir el empleo.</span><span class="sxs-lookup"><span data-stu-id="5d3f6-107">This entity describes screenings a candidate has passed or must pass for employment.</span></span>

## <a name="json-representation"></a><span data-ttu-id="5d3f6-108">Representación JSON</span><span class="sxs-lookup"><span data-stu-id="5d3f6-108">JSON representation</span></span>

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a><span data-ttu-id="5d3f6-109">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5d3f6-109">Properties</span></span>

| <span data-ttu-id="5d3f6-110">Propiedad</span><span class="sxs-lookup"><span data-stu-id="5d3f6-110">Property</span></span><br><span data-ttu-id="5d3f6-111">**Nombre físico**</span><span class="sxs-lookup"><span data-stu-id="5d3f6-111">**Physical name**</span></span><br><span data-ttu-id="5d3f6-112">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="5d3f6-112">**_Type_**</span></span> | <span data-ttu-id="5d3f6-113">Utilizar</span><span class="sxs-lookup"><span data-stu-id="5d3f6-113">Use</span></span> | <span data-ttu-id="5d3f6-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d3f6-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="5d3f6-115">**Id. de entidad de cribado de la persona**</span><span class="sxs-lookup"><span data-stu-id="5d3f6-115">**Person Screening Entity ID**</span></span><br><span data-ttu-id="5d3f6-116">mshr_hcmpersonscreeningentityid</span><span class="sxs-lookup"><span data-stu-id="5d3f6-116">mshr_hcmpersonscreeningentityid</span></span><br><span data-ttu-id="5d3f6-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="5d3f6-117">*GUID*</span></span> | <span data-ttu-id="5d3f6-118">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="5d3f6-118">Read-only</span></span><br><span data-ttu-id="5d3f6-119">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="5d3f6-119">Required</span></span><br><span data-ttu-id="5d3f6-120">Generado por el sistema</span><span class="sxs-lookup"><span data-stu-id="5d3f6-120">System-generated</span></span> | <span data-ttu-id="5d3f6-121">Identificador principal único del registro de cribado de la persona.</span><span class="sxs-lookup"><span data-stu-id="5d3f6-121">Unique primary identifier for the person screening record.</span></span> |
| <span data-ttu-id="5d3f6-122">**Número de parte**</span><span class="sxs-lookup"><span data-stu-id="5d3f6-122">**Party Number**</span></span><br><span data-ttu-id="5d3f6-123">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="5d3f6-123">mshr_partynumber</span></span><br><span data-ttu-id="5d3f6-124">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="5d3f6-124">*String*</span></span> | <span data-ttu-id="5d3f6-125">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="5d3f6-125">Read/write</span></span><br><span data-ttu-id="5d3f6-126">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="5d3f6-126">Required</span></span> | <span data-ttu-id="5d3f6-127">El número de entidad (persona) asociado con el candidato.</span><span class="sxs-lookup"><span data-stu-id="5d3f6-127">The party (person) number associated with the candidate.</span></span> |
| <span data-ttu-id="5d3f6-128">**Valor de id. de persona**</span><span class="sxs-lookup"><span data-stu-id="5d3f6-128">**Person ID Value**</span></span><br><span data-ttu-id="5d3f6-129">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="5d3f6-129">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="5d3f6-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="5d3f6-130">*GUID*</span></span> | <span data-ttu-id="5d3f6-131">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="5d3f6-131">Read-only</span></span><br><span data-ttu-id="5d3f6-132">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="5d3f6-132">Required</span></span><br><span data-ttu-id="5d3f6-133">Clave externa: mshr_dirpersonentityid de mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="5d3f6-133">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="5d3f6-134">Identificador único generado por el sistema de registro de entidad (persona) de la parte.</span><span class="sxs-lookup"><span data-stu-id="5d3f6-134">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="5d3f6-135">**Id. de tipo de cribado**</span><span class="sxs-lookup"><span data-stu-id="5d3f6-135">**Screening Type ID**</span></span><br><span data-ttu-id="5d3f6-136">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="5d3f6-136">mshr_screeningtypeid</span></span><br><span data-ttu-id="5d3f6-137">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="5d3f6-137">*String*</span></span> | <span data-ttu-id="5d3f6-138">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="5d3f6-138">Read/write</span></span><br><span data-ttu-id="5d3f6-139">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="5d3f6-139">Required</span></span><br><span data-ttu-id="5d3f6-140">Clave externa: ScreeningType</span><span class="sxs-lookup"><span data-stu-id="5d3f6-140">Foreign key: ScreeningType</span></span> | <span data-ttu-id="5d3f6-141">Identificador del tipo de cribado definido en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5d3f6-141">The identifier of the screening type defined in Human Resources.</span></span> |
| <span data-ttu-id="5d3f6-142">**Valor de id. de tipo de cribado**</span><span class="sxs-lookup"><span data-stu-id="5d3f6-142">**Screening Type ID Value**</span></span><br><span data-ttu-id="5d3f6-143">_mshr_fk_screeningtype_id_value</span><span class="sxs-lookup"><span data-stu-id="5d3f6-143">_mshr_fk_screeningtype_id_value</span></span><br><span data-ttu-id="5d3f6-144">*GUID*</span><span class="sxs-lookup"><span data-stu-id="5d3f6-144">*GUID*</span></span> | <span data-ttu-id="5d3f6-145">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="5d3f6-145">Read-only</span></span><br><span data-ttu-id="5d3f6-146">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="5d3f6-146">Required</span></span><br><span data-ttu-id="5d3f6-147">Clave externa: mshr_hcmscreeningtypeentityid de mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="5d3f6-147">Foreign key: mshr_hcmscreeningtypeentityid of mshr_hcmscreeningtypeentity</span></span> | <span data-ttu-id="5d3f6-148">Identificador único generado por el sistema para el registro de tipo de cribado en la entidad asociada.</span><span class="sxs-lookup"><span data-stu-id="5d3f6-148">System-generated identifier for the screening type record in the associated entity.</span></span> |
| <span data-ttu-id="5d3f6-149">**Requerido antes del**</span><span class="sxs-lookup"><span data-stu-id="5d3f6-149">**Required By**</span></span><br><span data-ttu-id="5d3f6-150">mshr_requiredby</span><span class="sxs-lookup"><span data-stu-id="5d3f6-150">mshr_requiredby</span></span><br><span data-ttu-id="5d3f6-151">*Fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="5d3f6-151">*Datetime*</span></span> | <span data-ttu-id="5d3f6-152">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="5d3f6-152">Read/write</span></span><br><span data-ttu-id="5d3f6-153">Opcional</span><span class="sxs-lookup"><span data-stu-id="5d3f6-153">Optional</span></span> | <span data-ttu-id="5d3f6-154">La fecha en la que debe estar completada la evaluación.</span><span class="sxs-lookup"><span data-stu-id="5d3f6-154">The date by which the screening is required to be completed.</span></span> |
| <span data-ttu-id="5d3f6-155">**Estado**</span><span class="sxs-lookup"><span data-stu-id="5d3f6-155">**Status**</span></span><br><span data-ttu-id="5d3f6-156">mshr_status</span><span class="sxs-lookup"><span data-stu-id="5d3f6-156">mshr_status</span></span><br><span data-ttu-id="5d3f6-157">*Conjunto de opciones mshr_hcmcompletionstatus*</span><span class="sxs-lookup"><span data-stu-id="5d3f6-157">*mshr_hcmcompletionstatus option set*</span></span><br><span data-ttu-id="5d3f6-158">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="5d3f6-158">Read/write</span></span><br><span data-ttu-id="5d3f6-159">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="5d3f6-159">Required</span></span> | <span data-ttu-id="5d3f6-160">Proporciona el estado del candidato para el cribado.</span><span class="sxs-lookup"><span data-stu-id="5d3f6-160">Provides the candidate’s status for the screening.</span></span> |
| <span data-ttu-id="5d3f6-161">**Fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="5d3f6-161">**Completed Date**</span></span><br><span data-ttu-id="5d3f6-162">mshr_completeddate</span><span class="sxs-lookup"><span data-stu-id="5d3f6-162">mshr_completeddate</span></span><br><span data-ttu-id="5d3f6-163">*Fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="5d3f6-163">*Datetime*</span></span> | <span data-ttu-id="5d3f6-164">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="5d3f6-164">Read/write</span></span><br><span data-ttu-id="5d3f6-165">Opcional</span><span class="sxs-lookup"><span data-stu-id="5d3f6-165">Optional</span></span> | <span data-ttu-id="5d3f6-166">La fecha en que se completó el cribado.</span><span class="sxs-lookup"><span data-stu-id="5d3f6-166">The date the screening was completed.</span></span> |
| <span data-ttu-id="5d3f6-167">**Notas**</span><span class="sxs-lookup"><span data-stu-id="5d3f6-167">**Notes**</span></span><br><span data-ttu-id="5d3f6-168">mshr_note</span><span class="sxs-lookup"><span data-stu-id="5d3f6-168">mshr_note</span></span><br><span data-ttu-id="5d3f6-169">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="5d3f6-169">*String*</span></span> | <span data-ttu-id="5d3f6-170">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="5d3f6-170">Read/write</span></span><br><span data-ttu-id="5d3f6-171">Opcional</span><span class="sxs-lookup"><span data-stu-id="5d3f6-171">Optional</span></span> | <span data-ttu-id="5d3f6-172">Notas para los técnicos de selección de personal y los responsables de contratación.</span><span class="sxs-lookup"><span data-stu-id="5d3f6-172">Notes for use by hiring managers and recruiters.</span></span> |

## <a name="see-also"></a><span data-ttu-id="5d3f6-173">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5d3f6-173">See also</span></span>

[<span data-ttu-id="5d3f6-174">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="5d3f6-174">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="5d3f6-175">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="5d3f6-175">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

