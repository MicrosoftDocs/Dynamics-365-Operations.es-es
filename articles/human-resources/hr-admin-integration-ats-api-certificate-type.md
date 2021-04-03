---
title: Tipo de certificado
description: Este tema describe la entidad Tipo de certificado para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 962bccb3aaab16322d072417660ec3aac821183b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467490"
---
# <a name="certificate-type"></a><span data-ttu-id="e628a-103">Tipo de certificado</span><span class="sxs-lookup"><span data-stu-id="e628a-103">Certificate type</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e628a-104">Este tema describe la entidad Tipo de certificado para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e628a-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="e628a-105">Nombre físico: mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="e628a-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="e628a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e628a-106">Description</span></span>

<span data-ttu-id="e628a-107">Esta entidad define la lista de tipos de certificados profesionales configurados en Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="e628a-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="e628a-108">La entidad no es específica de una entidad jurídica (empresa).</span><span class="sxs-lookup"><span data-stu-id="e628a-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="e628a-109">Representación JSON</span><span class="sxs-lookup"><span data-stu-id="e628a-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="e628a-110">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e628a-110">Properties</span></span>

| <span data-ttu-id="e628a-111">Propiedad</span><span class="sxs-lookup"><span data-stu-id="e628a-111">Property</span></span><br><span data-ttu-id="e628a-112">**Nombre físico**</span><span class="sxs-lookup"><span data-stu-id="e628a-112">**Physical name**</span></span><br><span data-ttu-id="e628a-113">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="e628a-113">**_Type_**</span></span> | <span data-ttu-id="e628a-114">Utilizar</span><span class="sxs-lookup"><span data-stu-id="e628a-114">Use</span></span> | <span data-ttu-id="e628a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e628a-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="e628a-116">**Id. de entidad de tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="e628a-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="e628a-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="e628a-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="e628a-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="e628a-118">*GUID*</span></span> | <span data-ttu-id="e628a-119">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="e628a-119">Read-only</span></span><br><span data-ttu-id="e628a-120">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e628a-120">Required</span></span> 
<span data-ttu-id="e628a-121">Generado por el sistema</span><span class="sxs-lookup"><span data-stu-id="e628a-121">System-generated</span></span> | <span data-ttu-id="e628a-122">Identificador primario único del tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="e628a-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="e628a-123">**Tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="e628a-123">**Certificate Type**</span></span><br><span data-ttu-id="e628a-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="e628a-124">mshr_certificatetype</span></span><br><span data-ttu-id="e628a-125">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="e628a-125">*String*</span></span> | <span data-ttu-id="e628a-126">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="e628a-126">Read/write</span></span><br><span data-ttu-id="e628a-127">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e628a-127">Required</span></span> | <span data-ttu-id="e628a-128">Identificador único legible por el usuario del tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="e628a-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="e628a-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e628a-129">**Description**</span></span><br><span data-ttu-id="e628a-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="e628a-130">mshr_description</span></span><br><span data-ttu-id="e628a-131">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="e628a-131">*String*</span></span> | <span data-ttu-id="e628a-132">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="e628a-132">Read/write</span></span><br><span data-ttu-id="e628a-133">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e628a-133">Required</span></span> | <span data-ttu-id="e628a-134">Descripción del tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="e628a-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="e628a-135">**Requiere renovación**</span><span class="sxs-lookup"><span data-stu-id="e628a-135">**Require Renewal**</span></span><br><span data-ttu-id="e628a-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="e628a-136">mshr_requirerenewal</span></span><br><span data-ttu-id="e628a-137">*Opción mshr_noyes establecida*</span><span class="sxs-lookup"><span data-stu-id="e628a-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="e628a-138">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="e628a-138">Read/write</span></span><br><span data-ttu-id="e628a-139">Opcional</span><span class="sxs-lookup"><span data-stu-id="e628a-139">Optional</span></span> | <span data-ttu-id="e628a-140">Indica si se requiere renovación para el certificado.</span><span class="sxs-lookup"><span data-stu-id="e628a-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e628a-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e628a-141">See also</span></span>

[<span data-ttu-id="e628a-142">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="e628a-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="e628a-143">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="e628a-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]