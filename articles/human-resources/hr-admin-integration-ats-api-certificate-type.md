---
title: Tipo de certificado
description: Este tema describe la entidad Tipo de certificado para Dynamics 365 Human Resources.
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
ms.openlocfilehash: fe5713b6b5f38ad7f6857b36c6b2f63a1dc0c320
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798402"
---
# <a name="certificate-type"></a><span data-ttu-id="aa09a-103">Tipo de certificado</span><span class="sxs-lookup"><span data-stu-id="aa09a-103">Certificate type</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="aa09a-104">Este tema describe la entidad Tipo de certificado para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="aa09a-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="aa09a-105">Nombre físico: mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="aa09a-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="aa09a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa09a-106">Description</span></span>

<span data-ttu-id="aa09a-107">Esta entidad define la lista de tipos de certificados profesionales configurados en Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="aa09a-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="aa09a-108">La entidad no es específica de una entidad jurídica (empresa).</span><span class="sxs-lookup"><span data-stu-id="aa09a-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="aa09a-109">Representación JSON</span><span class="sxs-lookup"><span data-stu-id="aa09a-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="aa09a-110">Propiedades</span><span class="sxs-lookup"><span data-stu-id="aa09a-110">Properties</span></span>

| <span data-ttu-id="aa09a-111">Propiedad</span><span class="sxs-lookup"><span data-stu-id="aa09a-111">Property</span></span><br><span data-ttu-id="aa09a-112">**Nombre físico**</span><span class="sxs-lookup"><span data-stu-id="aa09a-112">**Physical name**</span></span><br><span data-ttu-id="aa09a-113">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="aa09a-113">**_Type_**</span></span> | <span data-ttu-id="aa09a-114">Utilizar</span><span class="sxs-lookup"><span data-stu-id="aa09a-114">Use</span></span> | <span data-ttu-id="aa09a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa09a-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="aa09a-116">**Id. de entidad de tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="aa09a-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="aa09a-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="aa09a-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="aa09a-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="aa09a-118">*GUID*</span></span> | <span data-ttu-id="aa09a-119">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="aa09a-119">Read-only</span></span><br><span data-ttu-id="aa09a-120">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="aa09a-120">Required</span></span> 
<span data-ttu-id="aa09a-121">Generado por el sistema</span><span class="sxs-lookup"><span data-stu-id="aa09a-121">System-generated</span></span> | <span data-ttu-id="aa09a-122">Identificador primario único del tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="aa09a-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="aa09a-123">**Tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="aa09a-123">**Certificate Type**</span></span><br><span data-ttu-id="aa09a-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="aa09a-124">mshr_certificatetype</span></span><br><span data-ttu-id="aa09a-125">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="aa09a-125">*String*</span></span> | <span data-ttu-id="aa09a-126">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="aa09a-126">Read/write</span></span><br><span data-ttu-id="aa09a-127">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="aa09a-127">Required</span></span> | <span data-ttu-id="aa09a-128">Identificador único legible por el usuario del tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="aa09a-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="aa09a-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="aa09a-129">**Description**</span></span><br><span data-ttu-id="aa09a-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="aa09a-130">mshr_description</span></span><br><span data-ttu-id="aa09a-131">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="aa09a-131">*String*</span></span> | <span data-ttu-id="aa09a-132">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="aa09a-132">Read/write</span></span><br><span data-ttu-id="aa09a-133">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="aa09a-133">Required</span></span> | <span data-ttu-id="aa09a-134">Descripción del tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="aa09a-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="aa09a-135">**Requiere renovación**</span><span class="sxs-lookup"><span data-stu-id="aa09a-135">**Require Renewal**</span></span><br><span data-ttu-id="aa09a-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="aa09a-136">mshr_requirerenewal</span></span><br><span data-ttu-id="aa09a-137">*Opción mshr_noyes establecida*</span><span class="sxs-lookup"><span data-stu-id="aa09a-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="aa09a-138">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="aa09a-138">Read/write</span></span><br><span data-ttu-id="aa09a-139">Opcional</span><span class="sxs-lookup"><span data-stu-id="aa09a-139">Optional</span></span> | <span data-ttu-id="aa09a-140">Indica si se requiere renovación para el certificado.</span><span class="sxs-lookup"><span data-stu-id="aa09a-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="aa09a-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa09a-141">See also</span></span>

[<span data-ttu-id="aa09a-142">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="aa09a-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="aa09a-143">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="aa09a-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]