---
title: Plan de compensación fija con nómina
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad de plan de compensación fija de nóminas en Dynamics 365 Human Resources.
author: jcart
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
ms.openlocfilehash: 85cfce6f626090adab422ea6c60fc0778fd1ac67
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021305"
---
# <a name="payroll-fixed-compensation-plan"></a><span data-ttu-id="c7be7-103">Plan de compensación fija con nómina</span><span class="sxs-lookup"><span data-stu-id="c7be7-103">Payroll fixed compensation plan</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="c7be7-104">Este tema proporciona detalles y una consulta de ejemplo para la entidad de plan de compensación fija de nóminas en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c7be7-104">This topic provides details and an example query for the Payroll fixed compensation plan entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="c7be7-105">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c7be7-105">Properties</span></span>

| <span data-ttu-id="c7be7-106">Propiedad</span><span class="sxs-lookup"><span data-stu-id="c7be7-106">Property</span></span><br><span data-ttu-id="c7be7-107">**Nombre físico**</span><span class="sxs-lookup"><span data-stu-id="c7be7-107">**Physical name**</span></span><br><span data-ttu-id="c7be7-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="c7be7-108">**_Type_**</span></span> | <span data-ttu-id="c7be7-109">Utilizar</span><span class="sxs-lookup"><span data-stu-id="c7be7-109">Use</span></span> | <span data-ttu-id="c7be7-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7be7-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="c7be7-111">**Id. de empleado**</span><span class="sxs-lookup"><span data-stu-id="c7be7-111">**Employee ID**</span></span><br><span data-ttu-id="c7be7-112">mshr_fk_employee_id_value</span><span class="sxs-lookup"><span data-stu-id="c7be7-112">mshr_fk_employee_id_value</span></span><br><span data-ttu-id="c7be7-113">*GUID*</span><span class="sxs-lookup"><span data-stu-id="c7be7-113">*GUID*</span></span> | <span data-ttu-id="c7be7-114">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="c7be7-114">Read-only</span></span><br><span data-ttu-id="c7be7-115">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="c7be7-115">Required</span></span><br><span data-ttu-id="c7be7-116">Clave externa: mshr_Employee_id of mshr_payrollemployeeentity entity</span><span class="sxs-lookup"><span data-stu-id="c7be7-116">Foreign key:mshr_Employee_id of mshr_payrollemployeeentity entity</span></span>  | <span data-ttu-id="c7be7-117">Id. de empleado</span><span class="sxs-lookup"><span data-stu-id="c7be7-117">Employee ID</span></span> |
| <span data-ttu-id="c7be7-118">**Índice salarial**</span><span class="sxs-lookup"><span data-stu-id="c7be7-118">**Pay rate**</span></span><br><span data-ttu-id="c7be7-119">mshr_payrate</span><span class="sxs-lookup"><span data-stu-id="c7be7-119">mshr_payrate</span></span><br><span data-ttu-id="c7be7-120">*Decimal*</span><span class="sxs-lookup"><span data-stu-id="c7be7-120">*Decimal*</span></span> | <span data-ttu-id="c7be7-121">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="c7be7-121">Read-only</span></span><br><span data-ttu-id="c7be7-122">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="c7be7-122">Required</span></span> | <span data-ttu-id="c7be7-123">Tasa de pago definida en el plan de compensación fijo.</span><span class="sxs-lookup"><span data-stu-id="c7be7-123">Pay rate defined in fixed compensation plan.</span></span> |
| <span data-ttu-id="c7be7-124">**Id. de plan**</span><span class="sxs-lookup"><span data-stu-id="c7be7-124">**Plan ID**</span></span><br><span data-ttu-id="c7be7-125">mshr_planid</span><span class="sxs-lookup"><span data-stu-id="c7be7-125">mshr_planid</span></span><br><span data-ttu-id="c7be7-126">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="c7be7-126">*String*</span></span> | <span data-ttu-id="c7be7-127">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="c7be7-127">Read-only</span></span><br><span data-ttu-id="c7be7-128">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="c7be7-128">Required</span></span> |<span data-ttu-id="c7be7-129">Especifica el plan de compensación.</span><span class="sxs-lookup"><span data-stu-id="c7be7-129">Specifies the compensation plan.</span></span>  |
| <span data-ttu-id="c7be7-130">**Válido desde**</span><span class="sxs-lookup"><span data-stu-id="c7be7-130">**Valid from**</span></span><br><span data-ttu-id="c7be7-131">mshr_validfrom</span><span class="sxs-lookup"><span data-stu-id="c7be7-131">mshr_validfrom</span></span><br><span data-ttu-id="c7be7-132">*Desplazamineto de fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="c7be7-132">*Date Time Offset*</span></span> |  <span data-ttu-id="c7be7-133">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="c7be7-133">Read-only</span></span><br><span data-ttu-id="c7be7-134">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="c7be7-134">Required</span></span> |<span data-ttu-id="c7be7-135">Fecha de inicio de la validez de la compensación fija del empleado.</span><span class="sxs-lookup"><span data-stu-id="c7be7-135">Date the employee fixed compensation is valid from.</span></span>  |
| <span data-ttu-id="c7be7-136">**Entidad de plan de compensación fija con nómina**</span><span class="sxs-lookup"><span data-stu-id="c7be7-136">**Payroll Fixed Compensation Plan entity**</span></span><br><span data-ttu-id="c7be7-137">mshr_payrollfixedcompensationplanentityid</span><span class="sxs-lookup"><span data-stu-id="c7be7-137">mshr_payrollfixedcompensationplanentityid</span></span><br><span data-ttu-id="c7be7-138">*GUID*</span><span class="sxs-lookup"><span data-stu-id="c7be7-138">*GUID*</span></span> | <span data-ttu-id="c7be7-139">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="c7be7-139">Required</span></span><br><span data-ttu-id="c7be7-140">Generado por el sistema</span><span class="sxs-lookup"><span data-stu-id="c7be7-140">Sytem generated</span></span> | <span data-ttu-id="c7be7-141">Valor GUID generado por el sistema para identificar de forma única el plan de compensación.</span><span class="sxs-lookup"><span data-stu-id="c7be7-141">A system-generated GUID value to uniquely identify the compensation plan.</span></span> |
| <span data-ttu-id="c7be7-142">**Frecuencia de pago**</span><span class="sxs-lookup"><span data-stu-id="c7be7-142">**Pay frequency**</span></span><br><span data-ttu-id="c7be7-143">mshr_payfrequency</span><span class="sxs-lookup"><span data-stu-id="c7be7-143">mshr_payfrequency</span></span><br><span data-ttu-id="c7be7-144">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="c7be7-144">*String*</span></span> | <span data-ttu-id="c7be7-145">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="c7be7-145">Read-only</span></span><br><span data-ttu-id="c7be7-146">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="c7be7-146">Required</span></span> |<span data-ttu-id="c7be7-147">La frecuencia con la que se pagará al empleado.</span><span class="sxs-lookup"><span data-stu-id="c7be7-147">The frequency the employee will be paid.</span></span>  |
| <span data-ttu-id="c7be7-148">**Válido hasta**</span><span class="sxs-lookup"><span data-stu-id="c7be7-148">**Valid to**</span></span><br><span data-ttu-id="c7be7-149">mshr_validto</span><span class="sxs-lookup"><span data-stu-id="c7be7-149">mshr_validto</span></span><br><span data-ttu-id="c7be7-150">*Desplazamineto de fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="c7be7-150">*Date Time Offset*</span></span> | <span data-ttu-id="c7be7-151">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="c7be7-151">Read-only</span></span> <br><span data-ttu-id="c7be7-152">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="c7be7-152">Required</span></span> | <span data-ttu-id="c7be7-153">Fecha de finalización de la validez de la compensación fija del empleado.</span><span class="sxs-lookup"><span data-stu-id="c7be7-153">Date the employee fixed compensation is valid to.</span></span> |
| <span data-ttu-id="c7be7-154">**Id. de puesto**</span><span class="sxs-lookup"><span data-stu-id="c7be7-154">**Position ID**</span></span><br><span data-ttu-id="c7be7-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="c7be7-155">mshr_positionid</span></span><br><span data-ttu-id="c7be7-156">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="c7be7-156">*String*</span></span> | <span data-ttu-id="c7be7-157">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="c7be7-157">Read-only</span></span> <br><span data-ttu-id="c7be7-158">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="c7be7-158">Required</span></span> | <span data-ttu-id="c7be7-159">ID de puesto asociado con el empleado y la inscripción al plan de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="c7be7-159">Postion ID associated with the employee and fixed compensation plan enrollment.</span></span> |
| <span data-ttu-id="c7be7-160">**Divisa**</span><span class="sxs-lookup"><span data-stu-id="c7be7-160">**Currency**</span></span><br><span data-ttu-id="c7be7-161">mshr_currency</span><span class="sxs-lookup"><span data-stu-id="c7be7-161">mshr_currency</span></span><br><span data-ttu-id="c7be7-162">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="c7be7-162">*String*</span></span> | <span data-ttu-id="c7be7-163">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="c7be7-163">Read-only</span></span> <br><span data-ttu-id="c7be7-164">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="c7be7-164">Required</span></span> |<span data-ttu-id="c7be7-165">La moneda definida para el plan de compensación fijo</span><span class="sxs-lookup"><span data-stu-id="c7be7-165">The currency defined for the fixed compensation plan</span></span>   |
| <span data-ttu-id="c7be7-166">**Número de personal**</span><span class="sxs-lookup"><span data-stu-id="c7be7-166">**Personnel number**</span></span><br><span data-ttu-id="c7be7-167">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="c7be7-167">mshr_personnelnumber</span></span><br><span data-ttu-id="c7be7-168">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="c7be7-168">*String*</span></span> | <span data-ttu-id="c7be7-169">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="c7be7-169">Read-only</span></span><br><span data-ttu-id="c7be7-170">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="c7be7-170">Required</span></span> |<span data-ttu-id="c7be7-171">El número de personal exclusivo del empleado.</span><span class="sxs-lookup"><span data-stu-id="c7be7-171">The employee's unique personnel number.</span></span>  |

<span data-ttu-id="c7be7-172">**Consulta**</span><span class="sxs-lookup"><span data-stu-id="c7be7-172">**Query**</span></span>

<span data-ttu-id="c7be7-173">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="c7be7-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="c7be7-174">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="c7be7-174">**Response**</span></span>

```json
{
            "mshr_planid": "GradeC",
            "mshr_personnelnumber": "000041",
            "mshr_payrate": 75200,
            "mshr_positionid": "000276",
            "mshr_validfrom": "2011-04-05T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_payfrequency": "Annual",
            "mshr_currency": "USD",
            "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
            "_mshr_fk_payroll_id_value": null
}
```
