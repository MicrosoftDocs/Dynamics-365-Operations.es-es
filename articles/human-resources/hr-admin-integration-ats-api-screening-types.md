---
title: Tipos de filtrado
description: Este tema describe la entidad Tipos de cribado para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 361f8c866abb9d34eb3e2be7ea42626e98e34779
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805139"
---
# <a name="screening-types"></a><span data-ttu-id="67ac2-103">Tipos de filtrado</span><span class="sxs-lookup"><span data-stu-id="67ac2-103">Screening types</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="67ac2-104">Este tema describe la entidad Tipos de cribado para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="67ac2-104">This topic describes the Screening types entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="67ac2-105">Nombre físico: mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="67ac2-105">Physical name: mshr_hcmscreeningtypeentity</span></span>

## <a name="description"></a><span data-ttu-id="67ac2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="67ac2-106">Description</span></span>

<span data-ttu-id="67ac2-107">Esta entidad describe los tipos de cribado establecidos por la empresa para los procesos de cribado de empleados previo a la contratación y en curso.</span><span class="sxs-lookup"><span data-stu-id="67ac2-107">This entity describes the screening types set up by the company for pre-employment and ongoing employee screening processes.</span></span>

## <a name="json-representation"></a><span data-ttu-id="67ac2-108">Representación JSON</span><span class="sxs-lookup"><span data-stu-id="67ac2-108">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="67ac2-109">Propiedades</span><span class="sxs-lookup"><span data-stu-id="67ac2-109">Properties</span></span>

| <span data-ttu-id="67ac2-110">Propiedad</span><span class="sxs-lookup"><span data-stu-id="67ac2-110">Property</span></span><br><span data-ttu-id="67ac2-111">**Nombre físico**</span><span class="sxs-lookup"><span data-stu-id="67ac2-111">**Physical name**</span></span><br><span data-ttu-id="67ac2-112">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="67ac2-112">**_Type_**</span></span> | <span data-ttu-id="67ac2-113">Utilizar</span><span class="sxs-lookup"><span data-stu-id="67ac2-113">Use</span></span> | <span data-ttu-id="67ac2-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="67ac2-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="67ac2-115">**Id. de entidad de tipo de cribado**</span><span class="sxs-lookup"><span data-stu-id="67ac2-115">**Screening Type Entity ID**</span></span><br><span data-ttu-id="67ac2-116">mshr_hcmscreeningtypeentityid</span><span class="sxs-lookup"><span data-stu-id="67ac2-116">mshr_hcmscreeningtypeentityid</span></span><br><span data-ttu-id="67ac2-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="67ac2-117">*GUID*</span></span> | <span data-ttu-id="67ac2-118">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="67ac2-118">Read-only</span></span><br><span data-ttu-id="67ac2-119">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="67ac2-119">Required</span></span><br><span data-ttu-id="67ac2-120">Generado por el sistema</span><span class="sxs-lookup"><span data-stu-id="67ac2-120">System-generated</span></span> | <span data-ttu-id="67ac2-121">Identificador principal único del registro de tipo de cribado.</span><span class="sxs-lookup"><span data-stu-id="67ac2-121">Unique primary identifier for the screening type record.</span></span> |
| <span data-ttu-id="67ac2-122">**Id. de tipo de cribado**</span><span class="sxs-lookup"><span data-stu-id="67ac2-122">**Screening Type ID**</span></span><br><span data-ttu-id="67ac2-123">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="67ac2-123">mshr_screeningtypeid</span></span><br><span data-ttu-id="67ac2-124">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="67ac2-124">*String*</span></span> | <span data-ttu-id="67ac2-125">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="67ac2-125">Read/write</span></span><br><span data-ttu-id="67ac2-126">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="67ac2-126">Required</span></span> | <span data-ttu-id="67ac2-127">Identificador único definido por el usuario para el tipo de cribado.</span><span class="sxs-lookup"><span data-stu-id="67ac2-127">User-defined unique identifier for the screening type.</span></span> |
| <span data-ttu-id="67ac2-128">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="67ac2-128">**Description**</span></span><br><span data-ttu-id="67ac2-129">mshr_description</span><span class="sxs-lookup"><span data-stu-id="67ac2-129">mshr_description</span></span><br><span data-ttu-id="67ac2-130">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="67ac2-130">*String*</span></span> | <span data-ttu-id="67ac2-131">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="67ac2-131">Read/write</span></span><br><span data-ttu-id="67ac2-132">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="67ac2-132">Required</span></span> | <span data-ttu-id="67ac2-133">La descripción del tipo de cribado.</span><span class="sxs-lookup"><span data-stu-id="67ac2-133">The description of the screening type.</span></span> |
| <span data-ttu-id="67ac2-134">**Unidad de frecuencia**</span><span class="sxs-lookup"><span data-stu-id="67ac2-134">**Frequency Unit**</span></span><br><span data-ttu-id="67ac2-135">mshr_frequencyunit</span><span class="sxs-lookup"><span data-stu-id="67ac2-135">mshr_frequencyunit</span></span><br><span data-ttu-id="67ac2-136">*Conjunto de opciones mshr_hcmfrequencyunit*</span><span class="sxs-lookup"><span data-stu-id="67ac2-136">*mshr_hcmfrequencyunit option set*</span></span> | <span data-ttu-id="67ac2-137">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="67ac2-137">Read/write</span></span><br><span data-ttu-id="67ac2-138">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="67ac2-138">Required</span></span> | <span data-ttu-id="67ac2-139">Describe la frecuencia con la que se debe completar el cribado para la persona asignada.</span><span class="sxs-lookup"><span data-stu-id="67ac2-139">Describes the frequency with which the screening must be completed for the assigned person.</span></span> |
| <span data-ttu-id="67ac2-140">**Generar desde**</span><span class="sxs-lookup"><span data-stu-id="67ac2-140">**Generate From**</span></span><br><span data-ttu-id="67ac2-141">mshr_generatefrom</span><span class="sxs-lookup"><span data-stu-id="67ac2-141">mshr_generatefrom</span></span><br><span data-ttu-id="67ac2-142">*Conjunto de opciones mshr_hcmfrequencygeneratefrom*</span><span class="sxs-lookup"><span data-stu-id="67ac2-142">*mshr_hcmfrequencygeneratefrom option set*</span></span> | <span data-ttu-id="67ac2-143">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="67ac2-143">Read-write</span></span><br><span data-ttu-id="67ac2-144">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="67ac2-144">Required</span></span> | <span data-ttu-id="67ac2-145">Si el valor de Frecuencia es distinto de "Solo una vez", el valor de GenerateFrom determina la fecha a partir de la cual se calculará el siguiente evento de cribado.</span><span class="sxs-lookup"><span data-stu-id="67ac2-145">If the Frequency value is any value other than “One-time only”, the GenerateFrom value determines the date from which to calculate the next screening event.</span></span> |
| <span data-ttu-id="67ac2-146">**Intervalo de frecuencia**</span><span class="sxs-lookup"><span data-stu-id="67ac2-146">**Frequency Interval**</span></span><br><span data-ttu-id="67ac2-147">mshr_frequencyinterval</span><span class="sxs-lookup"><span data-stu-id="67ac2-147">mshr_frequencyinterval</span></span><br><span data-ttu-id="67ac2-148">*Entero*</span><span class="sxs-lookup"><span data-stu-id="67ac2-148">*Integer*</span></span> | <span data-ttu-id="67ac2-149">Leer/Escribir</span><span class="sxs-lookup"><span data-stu-id="67ac2-149">Read-write</span></span><br><span data-ttu-id="67ac2-150">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="67ac2-150">Required</span></span> | <span data-ttu-id="67ac2-151">Si el valor de Frecuencia es distinto de "Solo una vez", debe definir un intervalo para las unidades de tiempo entre cada evento de cribado.</span><span class="sxs-lookup"><span data-stu-id="67ac2-151">If the Frequency value is any value other than “One-time only”, you must define an interval for the units of time between each screening event.</span></span> |

## <a name="see-also"></a><span data-ttu-id="67ac2-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67ac2-152">See also</span></span>

[<span data-ttu-id="67ac2-153">Introducción a la API de integración del sistema de seguimiento de candidatos</span><span class="sxs-lookup"><span data-stu-id="67ac2-153">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="67ac2-154">Consulta de ejemplo para candidato a contratar</span><span class="sxs-lookup"><span data-stu-id="67ac2-154">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]