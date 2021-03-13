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
ms.openlocfilehash: 1d2d53a628ef43d50bd83fd6b62807f44eddd653
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125722"
---
# <a name="certificate-type"></a><span data-ttu-id="7a956-103">Tipo de certificado</span><span class="sxs-lookup"><span data-stu-id="7a956-103">Certificate type</span></span>

<span data-ttu-id="7a956-104">Este tema describe la entidad Tipo de certificado para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7a956-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="7a956-105">Nombre físico: mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="7a956-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="7a956-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a956-106">Description</span></span>

<span data-ttu-id="7a956-107">Esta entidad define la lista de tipos de certificados profesionales configurados en Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="7a956-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="7a956-108">La entidad no es específica de una entidad jurídica (empresa).</span><span class="sxs-lookup"><span data-stu-id="7a956-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="7a956-109">Representación JSON</span><span class="sxs-lookup"><span data-stu-id="7a956-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="7a956-110">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7a956-110">Properties</span></span>

| <span data-ttu-id="7a956-111">Propiedad</span><span class="sxs-lookup"><span data-stu-id="7a956-111">Property</span></span><br><span data-ttu-id="7a956-112">**Nombre físico**</span><span class="sxs-lookup"><span data-stu-id="7a956-112">**Physical name**</span></span><br><span data-ttu-id="7a956-113">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="7a956-113">**_Type_**</span></span> | <span data-ttu-id="7a956-114">Utilizar</span><span class="sxs-lookup"><span data-stu-id="7a956-114">Use</span></span> | <span data-ttu-id="7a956-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a956-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="7a956-116">**Id. de entidad de tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="7a956-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="7a956-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="7a956-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="7a956-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="7a956-118">*GUID*</span></span> | <span data-ttu-id="7a956-119">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="7a956-119">Read-only</span></span><br><span data-ttu-id="7a956-120">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="7a956-120">Required</span></span> 
<span data-ttu-id="7a956-121">Generado por el sistema</span><span class="sxs-lookup"><span data-stu-id="7a956-121">System-generated</span></span> | <span data-ttu-id="7a956-122">Identificador primario único del tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="7a956-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="7a956-123">**Tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="7a956-123">**Certificate Type**</span></span><br><span data-ttu-id="7a956-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="7a956-124">mshr_certificatetype</span></span><br><span data-ttu-id="7a956-125">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="7a956-125">*String*</span></span> | <span data-ttu-id="7a956-126">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="7a956-126">Read/write</span></span><br><span data-ttu-id="7a956-127">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="7a956-127">Required</span></span> | <span data-ttu-id="7a956-128">Identificador único legible por el usuario del tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="7a956-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="7a956-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7a956-129">**Description**</span></span><br><span data-ttu-id="7a956-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="7a956-130">mshr_description</span></span><br><span data-ttu-id="7a956-131">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="7a956-131">*String*</span></span> | <span data-ttu-id="7a956-132">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="7a956-132">Read/write</span></span><br><span data-ttu-id="7a956-133">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="7a956-133">Required</span></span> | <span data-ttu-id="7a956-134">Descripción del tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="7a956-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="7a956-135">**Requiere renovación**</span><span class="sxs-lookup"><span data-stu-id="7a956-135">**Require Renewal**</span></span><br><span data-ttu-id="7a956-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="7a956-136">mshr_requirerenewal</span></span><br><span data-ttu-id="7a956-137">*Opción mshr_noyes establecida*</span><span class="sxs-lookup"><span data-stu-id="7a956-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="7a956-138">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="7a956-138">Read/write</span></span><br><span data-ttu-id="7a956-139">Opcional</span><span class="sxs-lookup"><span data-stu-id="7a956-139">Optional</span></span> | <span data-ttu-id="7a956-140">Indica si se requiere renovación para el certificado.</span><span class="sxs-lookup"><span data-stu-id="7a956-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7a956-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a956-141">See also</span></span>

[<span data-ttu-id="7a956-142">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="7a956-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="7a956-143">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="7a956-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

