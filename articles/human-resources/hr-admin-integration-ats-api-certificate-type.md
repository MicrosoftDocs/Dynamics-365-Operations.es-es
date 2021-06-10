---
title: Tipo de certificado
description: Este tema describe la entidad Tipo de certificado para Dynamics 365 Human Resources.
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
ms.openlocfilehash: b8e979f242eb689b730b7f8a8684b3e697adbee6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054701"
---
# <a name="certificate-type"></a><span data-ttu-id="f45db-103">Tipo de certificado</span><span class="sxs-lookup"><span data-stu-id="f45db-103">Certificate type</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f45db-104">Este tema describe la entidad Tipo de certificado para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f45db-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="f45db-105">Nombre físico: mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="f45db-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="f45db-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f45db-106">Description</span></span>

<span data-ttu-id="f45db-107">Esta entidad define la lista de tipos de certificados profesionales configurados en Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="f45db-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="f45db-108">La entidad no es específica de una entidad jurídica (empresa).</span><span class="sxs-lookup"><span data-stu-id="f45db-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="f45db-109">Representación JSON</span><span class="sxs-lookup"><span data-stu-id="f45db-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="f45db-110">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f45db-110">Properties</span></span>

| <span data-ttu-id="f45db-111">Propiedad</span><span class="sxs-lookup"><span data-stu-id="f45db-111">Property</span></span><br><span data-ttu-id="f45db-112">**Nombre físico**</span><span class="sxs-lookup"><span data-stu-id="f45db-112">**Physical name**</span></span><br><span data-ttu-id="f45db-113">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="f45db-113">**_Type_**</span></span> | <span data-ttu-id="f45db-114">Utilizar</span><span class="sxs-lookup"><span data-stu-id="f45db-114">Use</span></span> | <span data-ttu-id="f45db-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f45db-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="f45db-116">**Id. de entidad de tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="f45db-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="f45db-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="f45db-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="f45db-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f45db-118">*GUID*</span></span> | <span data-ttu-id="f45db-119">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="f45db-119">Read-only</span></span><br><span data-ttu-id="f45db-120">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="f45db-120">Required</span></span> 
<span data-ttu-id="f45db-121">Generado por el sistema</span><span class="sxs-lookup"><span data-stu-id="f45db-121">System-generated</span></span> | <span data-ttu-id="f45db-122">Identificador primario único del tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="f45db-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="f45db-123">**Tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="f45db-123">**Certificate Type**</span></span><br><span data-ttu-id="f45db-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="f45db-124">mshr_certificatetype</span></span><br><span data-ttu-id="f45db-125">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="f45db-125">*String*</span></span> | <span data-ttu-id="f45db-126">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="f45db-126">Read/write</span></span><br><span data-ttu-id="f45db-127">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="f45db-127">Required</span></span> | <span data-ttu-id="f45db-128">Identificador único legible por el usuario del tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="f45db-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="f45db-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f45db-129">**Description**</span></span><br><span data-ttu-id="f45db-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="f45db-130">mshr_description</span></span><br><span data-ttu-id="f45db-131">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="f45db-131">*String*</span></span> | <span data-ttu-id="f45db-132">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="f45db-132">Read/write</span></span><br><span data-ttu-id="f45db-133">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="f45db-133">Required</span></span> | <span data-ttu-id="f45db-134">Descripción del tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="f45db-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="f45db-135">**Requiere renovación**</span><span class="sxs-lookup"><span data-stu-id="f45db-135">**Require Renewal**</span></span><br><span data-ttu-id="f45db-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="f45db-136">mshr_requirerenewal</span></span><br><span data-ttu-id="f45db-137">*Opción mshr_noyes establecida*</span><span class="sxs-lookup"><span data-stu-id="f45db-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="f45db-138">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="f45db-138">Read/write</span></span><br><span data-ttu-id="f45db-139">Opcional</span><span class="sxs-lookup"><span data-stu-id="f45db-139">Optional</span></span> | <span data-ttu-id="f45db-140">Indica si se requiere renovación para el certificado.</span><span class="sxs-lookup"><span data-stu-id="f45db-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f45db-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f45db-141">See also</span></span>

[<span data-ttu-id="f45db-142">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="f45db-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="f45db-143">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="f45db-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]