---
title: Certificado de la persona
description: Este tema describe la entidad Certificado de la persona para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 4587337d8fd52828309826f3301b6f053b267819
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466529"
---
# <a name="person-certificate"></a><span data-ttu-id="8ab52-103">Certificado de la persona</span><span class="sxs-lookup"><span data-stu-id="8ab52-103">Person certificate</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8ab52-104">Este tema describe la entidad Certificado de la persona para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8ab52-104">This topic describes the Person certificate entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="8ab52-105">Nombre físico: mshr_hcmpersoncertificateentity</span><span class="sxs-lookup"><span data-stu-id="8ab52-105">Physical name: mshr_hcmpersoncertificateentity</span></span>

## <a name="description"></a><span data-ttu-id="8ab52-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ab52-106">Description</span></span>

<span data-ttu-id="8ab52-107">Esta entidad describe los certificados profesionales de un candidato.</span><span class="sxs-lookup"><span data-stu-id="8ab52-107">This entity describes the professional certificates of a candidate.</span></span>

## <a name="json-representation"></a><span data-ttu-id="8ab52-108">Representación JSON</span><span class="sxs-lookup"><span data-stu-id="8ab52-108">JSON representation</span></span>

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="8ab52-109">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8ab52-109">Properties</span></span>

| <span data-ttu-id="8ab52-110">Propiedad</span><span class="sxs-lookup"><span data-stu-id="8ab52-110">Property</span></span><br><span data-ttu-id="8ab52-111">**Nombre físico**</span><span class="sxs-lookup"><span data-stu-id="8ab52-111">**Physical name**</span></span><br><span data-ttu-id="8ab52-112">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="8ab52-112">**_Type_**</span></span> | <span data-ttu-id="8ab52-113">Utilizar</span><span class="sxs-lookup"><span data-stu-id="8ab52-113">Use</span></span> | <span data-ttu-id="8ab52-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ab52-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="8ab52-115">**Id. de entidad de certificado de la persona**</span><span class="sxs-lookup"><span data-stu-id="8ab52-115">**Person Certificate Entity ID**</span></span><br><span data-ttu-id="8ab52-116">mshr_hcmpersoncertificateentityid</span><span class="sxs-lookup"><span data-stu-id="8ab52-116">mshr_hcmpersoncertificateentityid</span></span><br><span data-ttu-id="8ab52-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="8ab52-117">*GUID*</span></span> | <span data-ttu-id="8ab52-118">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ab52-118">Read-only</span></span><br><span data-ttu-id="8ab52-119">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8ab52-119">Required</span></span> | <span data-ttu-id="8ab52-120">Identificador único generado por el sistema para el registro de entidad de certificado de la persona.</span><span class="sxs-lookup"><span data-stu-id="8ab52-120">System-generated unique identifier for the person certificate entity record.</span></span> |
| <span data-ttu-id="8ab52-121">**Número de parte**</span><span class="sxs-lookup"><span data-stu-id="8ab52-121">**Party Number**</span></span><br><span data-ttu-id="8ab52-122">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="8ab52-122">mshr_partynumber</span></span><br><span data-ttu-id="8ab52-123">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="8ab52-123">*String*</span></span> | <span data-ttu-id="8ab52-124">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="8ab52-124">Read/write</span></span><br><span data-ttu-id="8ab52-125">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8ab52-125">Required</span></span> | <span data-ttu-id="8ab52-126">El id. de entidad (persona) del candidato.</span><span class="sxs-lookup"><span data-stu-id="8ab52-126">The party (person) ID of the candidate.</span></span> |
| <span data-ttu-id="8ab52-127">**Valor de id. de persona**</span><span class="sxs-lookup"><span data-stu-id="8ab52-127">**Person ID Value**</span></span><br><span data-ttu-id="8ab52-128">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="8ab52-128">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="8ab52-129">*GUID*</span><span class="sxs-lookup"><span data-stu-id="8ab52-129">*GUID*</span></span> | <span data-ttu-id="8ab52-130">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ab52-130">Read-only</span></span><br><span data-ttu-id="8ab52-131">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8ab52-131">Required</span></span><br><span data-ttu-id="8ab52-132">Clave externa: mshr_dirpersonentityid de mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="8ab52-132">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="8ab52-133">Identificador único generado por el sistema de registro de entidad (persona) de la parte.</span><span class="sxs-lookup"><span data-stu-id="8ab52-133">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="8ab52-134">**Id. de tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="8ab52-134">**Certificate Type ID**</span></span><br><span data-ttu-id="8ab52-135">mshr_certificatetypeid</span><span class="sxs-lookup"><span data-stu-id="8ab52-135">mshr_certificatetypeid</span></span><br><span data-ttu-id="8ab52-136">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="8ab52-136">*String*</span></span> | <span data-ttu-id="8ab52-137">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="8ab52-137">Read/write</span></span><br><span data-ttu-id="8ab52-138">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8ab52-138">Required</span></span> |  <span data-ttu-id="8ab52-139">Identificador del tipo de certificado definido en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8ab52-139">The identifier of the certificate type defined in Human Resources.</span></span> |
| <span data-ttu-id="8ab52-140">**Valor de id. de tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="8ab52-140">**Certificate Type ID Value**</span></span><br><span data-ttu-id="8ab52-141">_mshr_fk_certificatetype_id_value</span><span class="sxs-lookup"><span data-stu-id="8ab52-141">_mshr_fk_certificatetype_id_value</span></span><br><span data-ttu-id="8ab52-142">*GUID*</span><span class="sxs-lookup"><span data-stu-id="8ab52-142">*GUID*</span></span> | <span data-ttu-id="8ab52-143">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ab52-143">Read-only</span></span><br><span data-ttu-id="8ab52-144">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8ab52-144">Required</span></span><br><span data-ttu-id="8ab52-145">Clave externa: mshr_hcmcertificatetypeentityid de mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="8ab52-145">Foreign key: mshr_hcmcertificatetypeentityid of mshr_hcmcertificatetypeentity</span></span> | <span data-ttu-id="8ab52-146">Identificador único generado por el sistema del tipo de certificado de la entidad asociada.</span><span class="sxs-lookup"><span data-stu-id="8ab52-146">System-generated unique identifier of the certificate type in the associated entity.</span></span> |
| <span data-ttu-id="8ab52-147">**Fecha inicial**</span><span class="sxs-lookup"><span data-stu-id="8ab52-147">**Start Date**</span></span><br><span data-ttu-id="8ab52-148">mshr_startdate</span><span class="sxs-lookup"><span data-stu-id="8ab52-148">mshr_startdate</span></span><br><span data-ttu-id="8ab52-149">*Fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="8ab52-149">*Datetime*</span></span> | <span data-ttu-id="8ab52-150">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="8ab52-150">Read/write</span></span><br><span data-ttu-id="8ab52-151">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8ab52-151">Required</span></span> | <span data-ttu-id="8ab52-152">La fecha en la que se emitió el certificado.</span><span class="sxs-lookup"><span data-stu-id="8ab52-152">The date at which the certificate was issued.</span></span> |
| <span data-ttu-id="8ab52-153">**Fecha final**</span><span class="sxs-lookup"><span data-stu-id="8ab52-153">**End Date**</span></span><br><span data-ttu-id="8ab52-154">mshr_enddate</span><span class="sxs-lookup"><span data-stu-id="8ab52-154">mshr_enddate</span></span><br><span data-ttu-id="8ab52-155">*Fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="8ab52-155">*Datetime*</span></span> | <span data-ttu-id="8ab52-156">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="8ab52-156">Read/write</span></span><br><span data-ttu-id="8ab52-157">Opcional</span><span class="sxs-lookup"><span data-stu-id="8ab52-157">Optional</span></span> | <span data-ttu-id="8ab52-158">La fecha en la que expirará el certificado.</span><span class="sxs-lookup"><span data-stu-id="8ab52-158">The date at which the certificate will expire.</span></span> |
| <span data-ttu-id="8ab52-159">**Notas**</span><span class="sxs-lookup"><span data-stu-id="8ab52-159">**Notes**</span></span><br><span data-ttu-id="8ab52-160">mshr_notes</span><span class="sxs-lookup"><span data-stu-id="8ab52-160">mshr_notes</span></span><br><span data-ttu-id="8ab52-161">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="8ab52-161">*String*</span></span> | <span data-ttu-id="8ab52-162">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="8ab52-162">Read/write</span></span><br><span data-ttu-id="8ab52-163">Opcional</span><span class="sxs-lookup"><span data-stu-id="8ab52-163">Optional</span></span> | <span data-ttu-id="8ab52-164">Notas para los técnicos de selección de personal y los responsables de contratación.</span><span class="sxs-lookup"><span data-stu-id="8ab52-164">Notes for use by hiring managers and recruiters.</span></span> |
| <span data-ttu-id="8ab52-165">**Campo principal**</span><span class="sxs-lookup"><span data-stu-id="8ab52-165">**Primary Field**</span></span><br><span data-ttu-id="8ab52-166">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="8ab52-166">mshr_primaryfield</span></span><br><span data-ttu-id="8ab52-167">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="8ab52-167">*String*</span></span> | <span data-ttu-id="8ab52-168">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="8ab52-168">Read-only</span></span><br><span data-ttu-id="8ab52-169">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8ab52-169">Required</span></span> |  <span data-ttu-id="8ab52-170">Campo que se utilizará como identificador principal del registro de entidad.</span><span class="sxs-lookup"><span data-stu-id="8ab52-170">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="8ab52-171">Combinación de número de entidad, id. de tipo de certificado y fecha de inicio.</span><span class="sxs-lookup"><span data-stu-id="8ab52-171">Combination of party number, certificate type ID, and start date.</span></span> |

## <a name="see-also"></a><span data-ttu-id="8ab52-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ab52-172">See also</span></span>

[<span data-ttu-id="8ab52-173">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="8ab52-173">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="8ab52-174">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="8ab52-174">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]