---
title: Detalles de nómina para puestos
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad de detalles de nóminas par las posiciones en Dynamics 365 Human Resources.
author: jcart
manager: tfehr
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f6c4bb0e2f4521e8c870f6c4fb645e2ce506138c
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5882068"
---
# <a name="payroll-position"></a><span data-ttu-id="26e17-103">Puesto de nómina</span><span class="sxs-lookup"><span data-stu-id="26e17-103">Payroll position</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="26e17-104">Este tema proporciona detalles y una consulta de ejemplo para la entidad de detalles de nóminas par las posiciones en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="26e17-104">This topic provides details and an example query for the Payroll details for the Positions entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="26e17-105">Propiedades</span><span class="sxs-lookup"><span data-stu-id="26e17-105">Properties</span></span>

| <span data-ttu-id="26e17-106">Propiedad</span><span class="sxs-lookup"><span data-stu-id="26e17-106">Property</span></span><br><span data-ttu-id="26e17-107">**Nombre físico**</span><span class="sxs-lookup"><span data-stu-id="26e17-107">**Physical name**</span></span><br><span data-ttu-id="26e17-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="26e17-108">**_Type_**</span></span> | <span data-ttu-id="26e17-109">Utilizar</span><span class="sxs-lookup"><span data-stu-id="26e17-109">Use</span></span> | <span data-ttu-id="26e17-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="26e17-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="26e17-111">**Horas ordinarias anuales**</span><span class="sxs-lookup"><span data-stu-id="26e17-111">**Annual regular hours**</span></span><br><span data-ttu-id="26e17-112">Horas regulares anuales</span><span class="sxs-lookup"><span data-stu-id="26e17-112">annualregularhours</span></span><br><span data-ttu-id="26e17-113">*Decimal*</span><span class="sxs-lookup"><span data-stu-id="26e17-113">*Decimal*</span></span> | <span data-ttu-id="26e17-114">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="26e17-114">Read-only</span></span><br><span data-ttu-id="26e17-115">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="26e17-115">Required</span></span> | <span data-ttu-id="26e17-116">Horas regulares anuales definidas en el puesto.</span><span class="sxs-lookup"><span data-stu-id="26e17-116">Annual regular hours defined on the position.</span></span>  |
| <span data-ttu-id="26e17-117">**Id de entidad de detalle de puesto de nómina**</span><span class="sxs-lookup"><span data-stu-id="26e17-117">**Payroll position details entity ID**</span></span><br><span data-ttu-id="26e17-118">Nómina posicióndetallesentidadid</span><span class="sxs-lookup"><span data-stu-id="26e17-118">payrollpositiondetailsentityid</span></span><br><span data-ttu-id="26e17-119">*Guid*</span><span class="sxs-lookup"><span data-stu-id="26e17-119">*Guid*</span></span> | <span data-ttu-id="26e17-120">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="26e17-120">Required</span></span><br><span data-ttu-id="26e17-121">Generado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="26e17-121">System generated.</span></span> | <span data-ttu-id="26e17-122">Valor GUID generado por el sistema para identificar el puesto de forma única.</span><span class="sxs-lookup"><span data-stu-id="26e17-122">A system-generated GUID value to uniquely identify the position.</span></span>  |
| <span data-ttu-id="26e17-123">**Campo primario**</span><span class="sxs-lookup"><span data-stu-id="26e17-123">**Primary field**</span></span><br><span data-ttu-id="26e17-124">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="26e17-124">mshr_primaryfield</span></span><br><span data-ttu-id="26e17-125">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="26e17-125">*String*</span></span> | <span data-ttu-id="26e17-126">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="26e17-126">Required</span></span><br><span data-ttu-id="26e17-127">Generado por el sistema</span><span class="sxs-lookup"><span data-stu-id="26e17-127">System generated</span></span> |  |
| <span data-ttu-id="26e17-128">**Valor de id. de trabajo de puesto**</span><span class="sxs-lookup"><span data-stu-id="26e17-128">**Position job ID value**</span></span><br><span data-ttu-id="26e17-129">_mshr_fk_positionjob_id_value</span><span class="sxs-lookup"><span data-stu-id="26e17-129">_mshr_fk_positionjob_id_value</span></span><br><span data-ttu-id="26e17-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="26e17-130">*GUID*</span></span> | <span data-ttu-id="26e17-131">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="26e17-131">Read-only</span></span><br><span data-ttu-id="26e17-132">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="26e17-132">Required</span></span><br><span data-ttu-id="26e17-133">Clave externa: mshr_PayrollPositionJobEntity de la mshr_payrollpositionjobentity</span><span class="sxs-lookup"><span data-stu-id="26e17-133">Foreign key:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity</span></span> |<span data-ttu-id="26e17-134">Id. del trabajo asociado al puesto.</span><span class="sxs-lookup"><span data-stu-id="26e17-134">The ID of the job associated with the position.</span></span>|
| <span data-ttu-id="26e17-135">**Valor de id. de plan de compensación fijo**</span><span class="sxs-lookup"><span data-stu-id="26e17-135">**Fixed compensation plan ID value**</span></span><br><span data-ttu-id="26e17-136">_mshr_fk_fixedcompplan_id_value</span><span class="sxs-lookup"><span data-stu-id="26e17-136">_mshr_fk_fixedcompplan_id_value</span></span><br><span data-ttu-id="26e17-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="26e17-137">*GUID*</span></span> | <span data-ttu-id="26e17-138">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="26e17-138">Read-only</span></span><br><span data-ttu-id="26e17-139">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="26e17-139">Required</span></span><br><span data-ttu-id="26e17-140">Clave externa: mshr_FixedCompPlan_id de mshr_payrollfixedcompensationplanentity</span><span class="sxs-lookup"><span data-stu-id="26e17-140">Foreign key: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity</span></span>  | <span data-ttu-id="26e17-141">Id. del plan de compensación fijo asociado al puesto.</span><span class="sxs-lookup"><span data-stu-id="26e17-141">The ID of the fixed compensation plan associated with the position.</span></span> |
| <span data-ttu-id="26e17-142">**Id. de ciclo de pago**</span><span class="sxs-lookup"><span data-stu-id="26e17-142">**Pay cycle ID**</span></span><br><span data-ttu-id="26e17-143">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="26e17-143">mshr_primaryfield</span></span><br><span data-ttu-id="26e17-144">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="26e17-144">*String*</span></span> | <span data-ttu-id="26e17-145">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="26e17-145">Read-only</span></span><br><span data-ttu-id="26e17-146">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="26e17-146">Required</span></span> | <span data-ttu-id="26e17-147">El ciclo de pago definido en la posición.</span><span class="sxs-lookup"><span data-stu-id="26e17-147">The pay cycle defined on the position.</span></span> |
| <span data-ttu-id="26e17-148">**Pagado por la entidad jurídica**</span><span class="sxs-lookup"><span data-stu-id="26e17-148">**Paid by legal entity**</span></span><br><span data-ttu-id="26e17-149">paidbylegalentity</span><span class="sxs-lookup"><span data-stu-id="26e17-149">paidbylegalentity</span></span><br><span data-ttu-id="26e17-150">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="26e17-150">*String*</span></span> | <span data-ttu-id="26e17-151">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="26e17-151">Read-only</span></span><br><span data-ttu-id="26e17-152">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="26e17-152">Required</span></span> | <span data-ttu-id="26e17-153">La entidad legal definida en el puesto responsable de emitir el pago.</span><span class="sxs-lookup"><span data-stu-id="26e17-153">The legal entity defined on the positoin responsible for issuing payment.</span></span> |
| <span data-ttu-id="26e17-154">**Id. de puesto**</span><span class="sxs-lookup"><span data-stu-id="26e17-154">**Position ID**</span></span><br><span data-ttu-id="26e17-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="26e17-155">mshr_positionid</span></span><br><span data-ttu-id="26e17-156">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="26e17-156">*String*</span></span> | <span data-ttu-id="26e17-157">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="26e17-157">Read-only</span></span><br><span data-ttu-id="26e17-158">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="26e17-158">Required</span></span> | <span data-ttu-id="26e17-159">El id. del puesto.</span><span class="sxs-lookup"><span data-stu-id="26e17-159">The ID of the position.</span></span> |
| <span data-ttu-id="26e17-160">**Válido hasta**</span><span class="sxs-lookup"><span data-stu-id="26e17-160">**Valid to**</span></span><br><span data-ttu-id="26e17-161">validto</span><span class="sxs-lookup"><span data-stu-id="26e17-161">validto</span></span><br><span data-ttu-id="26e17-162">*Desplazamineto de fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="26e17-162">*Date Time Offset*</span></span> | <span data-ttu-id="26e17-163">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="26e17-163">Read-only</span></span><br><span data-ttu-id="26e17-164">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="26e17-164">Required</span></span> |<span data-ttu-id="26e17-165">La fecha desde la que son válidos los detalles del puesto.</span><span class="sxs-lookup"><span data-stu-id="26e17-165">The date the position details are valid from.</span></span>  |
| <span data-ttu-id="26e17-166">**Válido desde**</span><span class="sxs-lookup"><span data-stu-id="26e17-166">**Valid from**</span></span><br><span data-ttu-id="26e17-167">validfrom</span><span class="sxs-lookup"><span data-stu-id="26e17-167">validfrom</span></span><br><span data-ttu-id="26e17-168">*Desplazamineto de fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="26e17-168">*Date Time Offset*</span></span> | <span data-ttu-id="26e17-169">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="26e17-169">Read-only</span></span><br><span data-ttu-id="26e17-170">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="26e17-170">Required</span></span> |<span data-ttu-id="26e17-171">La fecha hasta la que son válidos los detalles del puesto.</span><span class="sxs-lookup"><span data-stu-id="26e17-171">The date the position details are valid to.</span></span>  |

<span data-ttu-id="26e17-172">**Consulta**</span><span class="sxs-lookup"><span data-stu-id="26e17-172">**Query**</span></span>

<span data-ttu-id="26e17-173">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="26e17-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

<span data-ttu-id="26e17-174">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="26e17-174">**Response**</span></span>

```json
{
            "mshr_positionid": "000276",
            "mshr_paycycleid": "w",
            "mshr_annualregularhours": 3000,
            "mshr_paidbylegalentity": "USMF",
            "mshr_validfrom": "2021-03-14T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_primaryfield": "000276 | 3/14/2021",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
            "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```
