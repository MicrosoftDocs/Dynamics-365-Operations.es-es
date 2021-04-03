---
title: Tipos de filtrado
description: Este tema describe la entidad Tipos de cribado para Dynamics 365 Human Resources.
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
ms.openlocfilehash: d3a45d802ab6b574338a09e77d432357cb9df507
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465927"
---
# <a name="screening-types"></a><span data-ttu-id="e3b54-103">Tipos de filtrado</span><span class="sxs-lookup"><span data-stu-id="e3b54-103">Screening types</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e3b54-104">Este tema describe la entidad Tipos de cribado para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e3b54-104">This topic describes the Screening types entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="e3b54-105">Nombre físico: mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="e3b54-105">Physical name: mshr_hcmscreeningtypeentity</span></span>

## <a name="description"></a><span data-ttu-id="e3b54-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3b54-106">Description</span></span>

<span data-ttu-id="e3b54-107">Esta entidad describe los tipos de cribado establecidos por la empresa para los procesos de cribado de empleados previo a la contratación y en curso.</span><span class="sxs-lookup"><span data-stu-id="e3b54-107">This entity describes the screening types set up by the company for pre-employment and ongoing employee screening processes.</span></span>

## <a name="json-representation"></a><span data-ttu-id="e3b54-108">Representación JSON</span><span class="sxs-lookup"><span data-stu-id="e3b54-108">JSON representation</span></span>

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="e3b54-109">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e3b54-109">Properties</span></span>

| <span data-ttu-id="e3b54-110">Propiedad</span><span class="sxs-lookup"><span data-stu-id="e3b54-110">Property</span></span><br><span data-ttu-id="e3b54-111">**Nombre físico**</span><span class="sxs-lookup"><span data-stu-id="e3b54-111">**Physical name**</span></span><br><span data-ttu-id="e3b54-112">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="e3b54-112">**_Type_**</span></span> | <span data-ttu-id="e3b54-113">Utilizar</span><span class="sxs-lookup"><span data-stu-id="e3b54-113">Use</span></span> | <span data-ttu-id="e3b54-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3b54-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="e3b54-115">**Id. de entidad de tipo de cribado**</span><span class="sxs-lookup"><span data-stu-id="e3b54-115">**Screening Type Entity ID**</span></span><br><span data-ttu-id="e3b54-116">mshr_hcmscreeningtypeentityid</span><span class="sxs-lookup"><span data-stu-id="e3b54-116">mshr_hcmscreeningtypeentityid</span></span><br><span data-ttu-id="e3b54-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="e3b54-117">*GUID*</span></span> | <span data-ttu-id="e3b54-118">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="e3b54-118">Read-only</span></span><br><span data-ttu-id="e3b54-119">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e3b54-119">Required</span></span><br><span data-ttu-id="e3b54-120">Generado por el sistema</span><span class="sxs-lookup"><span data-stu-id="e3b54-120">System-generated</span></span> | <span data-ttu-id="e3b54-121">Identificador principal único del registro de tipo de cribado.</span><span class="sxs-lookup"><span data-stu-id="e3b54-121">Unique primary identifier for the screening type record.</span></span> |
| <span data-ttu-id="e3b54-122">**Id. de tipo de cribado**</span><span class="sxs-lookup"><span data-stu-id="e3b54-122">**Screening Type ID**</span></span><br><span data-ttu-id="e3b54-123">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="e3b54-123">mshr_screeningtypeid</span></span><br><span data-ttu-id="e3b54-124">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="e3b54-124">*String*</span></span> | <span data-ttu-id="e3b54-125">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="e3b54-125">Read/write</span></span><br><span data-ttu-id="e3b54-126">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e3b54-126">Required</span></span> | <span data-ttu-id="e3b54-127">Identificador único definido por el usuario para el tipo de cribado.</span><span class="sxs-lookup"><span data-stu-id="e3b54-127">User-defined unique identifier for the screening type.</span></span> |
| <span data-ttu-id="e3b54-128">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e3b54-128">**Description**</span></span><br><span data-ttu-id="e3b54-129">mshr_description</span><span class="sxs-lookup"><span data-stu-id="e3b54-129">mshr_description</span></span><br><span data-ttu-id="e3b54-130">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="e3b54-130">*String*</span></span> | <span data-ttu-id="e3b54-131">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="e3b54-131">Read/write</span></span><br><span data-ttu-id="e3b54-132">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e3b54-132">Required</span></span> | <span data-ttu-id="e3b54-133">La descripción del tipo de cribado.</span><span class="sxs-lookup"><span data-stu-id="e3b54-133">The description of the screening type.</span></span> |
| <span data-ttu-id="e3b54-134">**Unidad de frecuencia**</span><span class="sxs-lookup"><span data-stu-id="e3b54-134">**Frequency Unit**</span></span><br><span data-ttu-id="e3b54-135">mshr_frequencyunit</span><span class="sxs-lookup"><span data-stu-id="e3b54-135">mshr_frequencyunit</span></span><br><span data-ttu-id="e3b54-136">*Conjunto de opciones mshr_hcmfrequencyunit*</span><span class="sxs-lookup"><span data-stu-id="e3b54-136">*mshr_hcmfrequencyunit option set*</span></span> | <span data-ttu-id="e3b54-137">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="e3b54-137">Read/write</span></span><br><span data-ttu-id="e3b54-138">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e3b54-138">Required</span></span> | <span data-ttu-id="e3b54-139">Describe la frecuencia con la que se debe completar el cribado para la persona asignada.</span><span class="sxs-lookup"><span data-stu-id="e3b54-139">Describes the frequency with which the screening must be completed for the assigned person.</span></span> |
| <span data-ttu-id="e3b54-140">**Generar desde**</span><span class="sxs-lookup"><span data-stu-id="e3b54-140">**Generate From**</span></span><br><span data-ttu-id="e3b54-141">mshr_generatefrom</span><span class="sxs-lookup"><span data-stu-id="e3b54-141">mshr_generatefrom</span></span><br><span data-ttu-id="e3b54-142">*Conjunto de opciones mshr_hcmfrequencygeneratefrom*</span><span class="sxs-lookup"><span data-stu-id="e3b54-142">*mshr_hcmfrequencygeneratefrom option set*</span></span> | <span data-ttu-id="e3b54-143">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="e3b54-143">Read-write</span></span><br><span data-ttu-id="e3b54-144">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e3b54-144">Required</span></span> | <span data-ttu-id="e3b54-145">Si el valor de Frecuencia es distinto de "Solo una vez", el valor de GenerateFrom determina la fecha a partir de la cual se calculará el siguiente evento de cribado.</span><span class="sxs-lookup"><span data-stu-id="e3b54-145">If the Frequency value is any value other than “One-time only”, the GenerateFrom value determines the date from which to calculate the next screening event.</span></span> |
| <span data-ttu-id="e3b54-146">**Intervalo de frecuencia**</span><span class="sxs-lookup"><span data-stu-id="e3b54-146">**Frequency Interval**</span></span><br><span data-ttu-id="e3b54-147">mshr_frequencyinterval</span><span class="sxs-lookup"><span data-stu-id="e3b54-147">mshr_frequencyinterval</span></span><br><span data-ttu-id="e3b54-148">*Entero*</span><span class="sxs-lookup"><span data-stu-id="e3b54-148">*Integer*</span></span> | <span data-ttu-id="e3b54-149">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="e3b54-149">Read-write</span></span><br><span data-ttu-id="e3b54-150">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e3b54-150">Required</span></span> | <span data-ttu-id="e3b54-151">Si el valor de Frecuencia es distinto de "Solo una vez", debe definir un intervalo para las unidades de tiempo entre cada evento de cribado.</span><span class="sxs-lookup"><span data-stu-id="e3b54-151">If the Frequency value is any value other than “One-time only”, you must define an interval for the units of time between each screening event.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e3b54-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3b54-152">See also</span></span>

[<span data-ttu-id="e3b54-153">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="e3b54-153">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="e3b54-154">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="e3b54-154">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]