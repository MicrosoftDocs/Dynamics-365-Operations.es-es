---
title: Filtrado de persona
description: Este tema describe la entidad Cribado de la persona para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 9d29b26094e307c3f68d57f297ab3614f3a5ccae
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059289"
---
# <a name="person-screening"></a><span data-ttu-id="bf27a-103">Filtrado de persona</span><span class="sxs-lookup"><span data-stu-id="bf27a-103">Person screening</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="bf27a-104">Este tema describe la entidad Cribado de la persona para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="bf27a-104">This topic describes the Person screening entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="bf27a-105">Nombre físico: mshr_hcmpersonscreeningentity</span><span class="sxs-lookup"><span data-stu-id="bf27a-105">Physical name: mshr_hcmpersonscreeningentity</span></span>

## <a name="description"></a><span data-ttu-id="bf27a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf27a-106">Description</span></span>

<span data-ttu-id="bf27a-107">Esta entidad describe los cribados que un candidato ha superado o debe superar para conseguir el empleo.</span><span class="sxs-lookup"><span data-stu-id="bf27a-107">This entity describes screenings a candidate has passed or must pass for employment.</span></span>

## <a name="json-representation"></a><span data-ttu-id="bf27a-108">Representación JSON</span><span class="sxs-lookup"><span data-stu-id="bf27a-108">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="bf27a-109">Propiedades</span><span class="sxs-lookup"><span data-stu-id="bf27a-109">Properties</span></span>

| <span data-ttu-id="bf27a-110">Propiedad</span><span class="sxs-lookup"><span data-stu-id="bf27a-110">Property</span></span><br><span data-ttu-id="bf27a-111">**Nombre físico**</span><span class="sxs-lookup"><span data-stu-id="bf27a-111">**Physical name**</span></span><br><span data-ttu-id="bf27a-112">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="bf27a-112">**_Type_**</span></span> | <span data-ttu-id="bf27a-113">Utilizar</span><span class="sxs-lookup"><span data-stu-id="bf27a-113">Use</span></span> | <span data-ttu-id="bf27a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf27a-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="bf27a-115">**Id. de entidad de cribado de la persona**</span><span class="sxs-lookup"><span data-stu-id="bf27a-115">**Person Screening Entity ID**</span></span><br><span data-ttu-id="bf27a-116">mshr_hcmpersonscreeningentityid</span><span class="sxs-lookup"><span data-stu-id="bf27a-116">mshr_hcmpersonscreeningentityid</span></span><br><span data-ttu-id="bf27a-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="bf27a-117">*GUID*</span></span> | <span data-ttu-id="bf27a-118">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="bf27a-118">Read-only</span></span><br><span data-ttu-id="bf27a-119">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="bf27a-119">Required</span></span><br><span data-ttu-id="bf27a-120">Generado por el sistema</span><span class="sxs-lookup"><span data-stu-id="bf27a-120">System-generated</span></span> | <span data-ttu-id="bf27a-121">Identificador principal único del registro de cribado de la persona.</span><span class="sxs-lookup"><span data-stu-id="bf27a-121">Unique primary identifier for the person screening record.</span></span> |
| <span data-ttu-id="bf27a-122">**Número de parte**</span><span class="sxs-lookup"><span data-stu-id="bf27a-122">**Party Number**</span></span><br><span data-ttu-id="bf27a-123">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="bf27a-123">mshr_partynumber</span></span><br><span data-ttu-id="bf27a-124">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="bf27a-124">*String*</span></span> | <span data-ttu-id="bf27a-125">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="bf27a-125">Read/write</span></span><br><span data-ttu-id="bf27a-126">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="bf27a-126">Required</span></span> | <span data-ttu-id="bf27a-127">El número de entidad (persona) asociado con el candidato.</span><span class="sxs-lookup"><span data-stu-id="bf27a-127">The party (person) number associated with the candidate.</span></span> |
| <span data-ttu-id="bf27a-128">**Valor de id. de persona**</span><span class="sxs-lookup"><span data-stu-id="bf27a-128">**Person ID Value**</span></span><br><span data-ttu-id="bf27a-129">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="bf27a-129">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="bf27a-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="bf27a-130">*GUID*</span></span> | <span data-ttu-id="bf27a-131">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="bf27a-131">Read-only</span></span><br><span data-ttu-id="bf27a-132">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="bf27a-132">Required</span></span><br><span data-ttu-id="bf27a-133">Clave externa: mshr_dirpersonentityid de mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="bf27a-133">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="bf27a-134">Identificador único generado por el sistema de registro de entidad (persona) de la parte.</span><span class="sxs-lookup"><span data-stu-id="bf27a-134">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="bf27a-135">**Id. de tipo de cribado**</span><span class="sxs-lookup"><span data-stu-id="bf27a-135">**Screening Type ID**</span></span><br><span data-ttu-id="bf27a-136">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="bf27a-136">mshr_screeningtypeid</span></span><br><span data-ttu-id="bf27a-137">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="bf27a-137">*String*</span></span> | <span data-ttu-id="bf27a-138">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="bf27a-138">Read/write</span></span><br><span data-ttu-id="bf27a-139">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="bf27a-139">Required</span></span><br><span data-ttu-id="bf27a-140">Clave externa: ScreeningType</span><span class="sxs-lookup"><span data-stu-id="bf27a-140">Foreign key: ScreeningType</span></span> | <span data-ttu-id="bf27a-141">Identificador del tipo de cribado definido en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="bf27a-141">The identifier of the screening type defined in Human Resources.</span></span> |
| <span data-ttu-id="bf27a-142">**Valor de id. de tipo de cribado**</span><span class="sxs-lookup"><span data-stu-id="bf27a-142">**Screening Type ID Value**</span></span><br><span data-ttu-id="bf27a-143">_mshr_fk_screeningtype_id_value</span><span class="sxs-lookup"><span data-stu-id="bf27a-143">_mshr_fk_screeningtype_id_value</span></span><br><span data-ttu-id="bf27a-144">*GUID*</span><span class="sxs-lookup"><span data-stu-id="bf27a-144">*GUID*</span></span> | <span data-ttu-id="bf27a-145">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="bf27a-145">Read-only</span></span><br><span data-ttu-id="bf27a-146">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="bf27a-146">Required</span></span><br><span data-ttu-id="bf27a-147">Clave externa: mshr_hcmscreeningtypeentityid de mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="bf27a-147">Foreign key: mshr_hcmscreeningtypeentityid of mshr_hcmscreeningtypeentity</span></span> | <span data-ttu-id="bf27a-148">Identificador único generado por el sistema para el registro de tipo de cribado en la entidad asociada.</span><span class="sxs-lookup"><span data-stu-id="bf27a-148">System-generated identifier for the screening type record in the associated entity.</span></span> |
| <span data-ttu-id="bf27a-149">**Requerido antes del**</span><span class="sxs-lookup"><span data-stu-id="bf27a-149">**Required By**</span></span><br><span data-ttu-id="bf27a-150">mshr_requiredby</span><span class="sxs-lookup"><span data-stu-id="bf27a-150">mshr_requiredby</span></span><br><span data-ttu-id="bf27a-151">*Fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="bf27a-151">*Datetime*</span></span> | <span data-ttu-id="bf27a-152">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="bf27a-152">Read/write</span></span><br><span data-ttu-id="bf27a-153">Opcional</span><span class="sxs-lookup"><span data-stu-id="bf27a-153">Optional</span></span> | <span data-ttu-id="bf27a-154">La fecha en la que debe estar completada la evaluación.</span><span class="sxs-lookup"><span data-stu-id="bf27a-154">The date by which the screening is required to be completed.</span></span> |
| <span data-ttu-id="bf27a-155">**Estado**</span><span class="sxs-lookup"><span data-stu-id="bf27a-155">**Status**</span></span><br><span data-ttu-id="bf27a-156">mshr_status</span><span class="sxs-lookup"><span data-stu-id="bf27a-156">mshr_status</span></span><br><span data-ttu-id="bf27a-157">*Conjunto de opciones mshr_hcmcompletionstatus*</span><span class="sxs-lookup"><span data-stu-id="bf27a-157">*mshr_hcmcompletionstatus option set*</span></span><br><span data-ttu-id="bf27a-158">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="bf27a-158">Read/write</span></span><br><span data-ttu-id="bf27a-159">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="bf27a-159">Required</span></span> | <span data-ttu-id="bf27a-160">Proporciona el estado del candidato para el cribado.</span><span class="sxs-lookup"><span data-stu-id="bf27a-160">Provides the candidate’s status for the screening.</span></span> |
| <span data-ttu-id="bf27a-161">**Fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="bf27a-161">**Completed Date**</span></span><br><span data-ttu-id="bf27a-162">mshr_completeddate</span><span class="sxs-lookup"><span data-stu-id="bf27a-162">mshr_completeddate</span></span><br><span data-ttu-id="bf27a-163">*Fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="bf27a-163">*Datetime*</span></span> | <span data-ttu-id="bf27a-164">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="bf27a-164">Read/write</span></span><br><span data-ttu-id="bf27a-165">Opcional</span><span class="sxs-lookup"><span data-stu-id="bf27a-165">Optional</span></span> | <span data-ttu-id="bf27a-166">La fecha en que se completó el cribado.</span><span class="sxs-lookup"><span data-stu-id="bf27a-166">The date the screening was completed.</span></span> |
| <span data-ttu-id="bf27a-167">**Notas**</span><span class="sxs-lookup"><span data-stu-id="bf27a-167">**Notes**</span></span><br><span data-ttu-id="bf27a-168">mshr_note</span><span class="sxs-lookup"><span data-stu-id="bf27a-168">mshr_note</span></span><br><span data-ttu-id="bf27a-169">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="bf27a-169">*String*</span></span> | <span data-ttu-id="bf27a-170">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="bf27a-170">Read/write</span></span><br><span data-ttu-id="bf27a-171">Opcional</span><span class="sxs-lookup"><span data-stu-id="bf27a-171">Optional</span></span> | <span data-ttu-id="bf27a-172">Notas para los técnicos de selección de personal y los responsables de contratación.</span><span class="sxs-lookup"><span data-stu-id="bf27a-172">Notes for use by hiring managers and recruiters.</span></span> |

## <a name="see-also"></a><span data-ttu-id="bf27a-173">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf27a-173">See also</span></span>

[<span data-ttu-id="bf27a-174">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="bf27a-174">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="bf27a-175">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="bf27a-175">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]