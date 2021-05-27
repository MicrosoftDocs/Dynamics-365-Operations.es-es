---
title: Dirección del trabajador de la nómina
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad de dirección de trabajador de nóminas en Dynamics 365 Human Resources.
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
ms.openlocfilehash: 964f04261ea95ee6fa2880b0905a669855f6c58a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020714"
---
# <a name="payroll-worker-address"></a><span data-ttu-id="25d05-103">Dirección del trabajador de la nómina</span><span class="sxs-lookup"><span data-stu-id="25d05-103">Payroll worker address</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="25d05-104">Este tema proporciona detalles y una consulta de ejemplo para la entidad de dirección de trabajador de nóminas en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="25d05-104">This topic provides details and an example query for the Payroll worker address entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="25d05-105">Propiedades</span><span class="sxs-lookup"><span data-stu-id="25d05-105">Properties</span></span>

| <span data-ttu-id="25d05-106">Propiedad</span><span class="sxs-lookup"><span data-stu-id="25d05-106">Property</span></span><br><span data-ttu-id="25d05-107">**Nombre físico**</span><span class="sxs-lookup"><span data-stu-id="25d05-107">**Physical name**</span></span><br><span data-ttu-id="25d05-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="25d05-108">**_Type_**</span></span> | <span data-ttu-id="25d05-109">Utilizar</span><span class="sxs-lookup"><span data-stu-id="25d05-109">Use</span></span> | <span data-ttu-id="25d05-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="25d05-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="25d05-111">**Ciudad**</span><span class="sxs-lookup"><span data-stu-id="25d05-111">**City**</span></span><br><span data-ttu-id="25d05-112">mshr_city</span><span class="sxs-lookup"><span data-stu-id="25d05-112">mshr_city</span></span><br><span data-ttu-id="25d05-113">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="25d05-113">*String*</span></span> | <span data-ttu-id="25d05-114">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="25d05-114">Read-only</span></span><br><span data-ttu-id="25d05-115">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="25d05-115">Required</span></span> | <span data-ttu-id="25d05-116">Ciudad deifnida para la dirección.</span><span class="sxs-lookup"><span data-stu-id="25d05-116">The city defined for the address.</span></span>   |
| <span data-ttu-id="25d05-117">**Número de personal**</span><span class="sxs-lookup"><span data-stu-id="25d05-117">**Personnel number**</span></span><br><span data-ttu-id="25d05-118">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="25d05-118">mshr_personnelnumber</span></span><br><span data-ttu-id="25d05-119">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="25d05-119">*String*</span></span> | <span data-ttu-id="25d05-120">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="25d05-120">Read-only</span></span><br><span data-ttu-id="25d05-121">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="25d05-121">Required</span></span> | <span data-ttu-id="25d05-122">El número de personal exclusivo del empleado.</span><span class="sxs-lookup"><span data-stu-id="25d05-122">The employee's unique personnel number.</span></span>  |
| <span data-ttu-id="25d05-123">**Región del país**</span><span class="sxs-lookup"><span data-stu-id="25d05-123">**Country region**</span></span><br><span data-ttu-id="25d05-124">mshr_countryregionid</span><span class="sxs-lookup"><span data-stu-id="25d05-124">mshr_countryregionid</span></span><br><span data-ttu-id="25d05-125">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="25d05-125">*String*</span></span> | <span data-ttu-id="25d05-126">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="25d05-126">Read-only</span></span><br><span data-ttu-id="25d05-127">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="25d05-127">Required</span></span> | <span data-ttu-id="25d05-128">Región del país para la dirección.</span><span class="sxs-lookup"><span data-stu-id="25d05-128">The country region defined for the address</span></span>  |
| <span data-ttu-id="25d05-129">**Válido desde**</span><span class="sxs-lookup"><span data-stu-id="25d05-129">**Valid from**</span></span><br><span data-ttu-id="25d05-130">mshr_postaladdressvalidfrom</span><span class="sxs-lookup"><span data-stu-id="25d05-130">mshr_postaladdressvalidfrom</span></span><br><span data-ttu-id="25d05-131">*Desplazamineto de fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="25d05-131">*Date Time Offset*</span></span> | <span data-ttu-id="25d05-132">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="25d05-132">Read-only</span></span> <br><span data-ttu-id="25d05-133">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="25d05-133">Required</span></span> | <span data-ttu-id="25d05-134">Fecha a partir de la cual es válida la dirección.</span><span class="sxs-lookup"><span data-stu-id="25d05-134">The date the address is valid from.</span></span> |
| <span data-ttu-id="25d05-135">**Trabajó en dirección**</span><span class="sxs-lookup"><span data-stu-id="25d05-135">**Worked in address**</span></span><br><span data-ttu-id="25d05-136">mshr_isworkedinaddressbr>*Int32*</span><span class="sxs-lookup"><span data-stu-id="25d05-136">mshr_isworkedinaddressbr>*Int32*</span></span> | <span data-ttu-id="25d05-137">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="25d05-137">Read-only</span></span><br><span data-ttu-id="25d05-138">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="25d05-138">Required</span></span> | <span data-ttu-id="25d05-139">Indica si la dirección es donde trabaja el empleado.</span><span class="sxs-lookup"><span data-stu-id="25d05-139">Denotes if the address is where the employee works.</span></span> |
| <span data-ttu-id="25d05-140">**Provincia**</span><span class="sxs-lookup"><span data-stu-id="25d05-140">**County**</span></span><br><span data-ttu-id="25d05-141">mshr_county</span><span class="sxs-lookup"><span data-stu-id="25d05-141">mshr_county</span></span><br><span data-ttu-id="25d05-142">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="25d05-142">*String*</span></span> | <span data-ttu-id="25d05-143">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="25d05-143">Read-only</span></span><br><span data-ttu-id="25d05-144">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="25d05-144">Required</span></span> | <span data-ttu-id="25d05-145">Condado deifnido para la dirección.</span><span class="sxs-lookup"><span data-stu-id="25d05-145">The county defined for the address.</span></span>  |
| <span data-ttu-id="25d05-146">**Id. de dirección del trabajador de la nómina**</span><span class="sxs-lookup"><span data-stu-id="25d05-146">**Payroll worker address ID**</span></span><br><span data-ttu-id="25d05-147">mshr_payrollworkeraddressentityid</span><span class="sxs-lookup"><span data-stu-id="25d05-147">mshr_payrollworkeraddressentityid</span></span><br><span data-ttu-id="25d05-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="25d05-148">*GUID*</span></span> | <span data-ttu-id="25d05-149">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="25d05-149">Required</span></span><br><span data-ttu-id="25d05-150">Generado por el sistema</span><span class="sxs-lookup"><span data-stu-id="25d05-150">System generated</span></span> | <span data-ttu-id="25d05-151">Valor GUID generado por el sistema para identificar de forma única la dirección.</span><span class="sxs-lookup"><span data-stu-id="25d05-151">A system-generated GUID value to uniquely identify the address.</span></span>  |
| <span data-ttu-id="25d05-152">**Campo primario**</span><span class="sxs-lookup"><span data-stu-id="25d05-152">**Primary field**</span></span><br><span data-ttu-id="25d05-153">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="25d05-153">mshr_primaryfield</span></span><br><span data-ttu-id="25d05-154">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="25d05-154">*String*</span></span> | <span data-ttu-id="25d05-155">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="25d05-155">Read-only</span></span><br><span data-ttu-id="25d05-156">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="25d05-156">Required</span></span> |  |
| <span data-ttu-id="25d05-157">**Calle**</span><span class="sxs-lookup"><span data-stu-id="25d05-157">**Street**</span></span><br><span data-ttu-id="25d05-158">mshr_street</span><span class="sxs-lookup"><span data-stu-id="25d05-158">mshr_street</span></span><br><span data-ttu-id="25d05-159">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="25d05-159">*String*</span></span> | <span data-ttu-id="25d05-160">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="25d05-160">Read-only</span></span><br><span data-ttu-id="25d05-161">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="25d05-161">Required</span></span> | <span data-ttu-id="25d05-162">Calle deifnida para la dirección.</span><span class="sxs-lookup"><span data-stu-id="25d05-162">The street defined for the address.</span></span> |
| <span data-ttu-id="25d05-163">**Válido hasta**</span><span class="sxs-lookup"><span data-stu-id="25d05-163">**Valid to**</span></span><br><span data-ttu-id="25d05-164">mshr_postaladdressvalidto</span><span class="sxs-lookup"><span data-stu-id="25d05-164">mshr_postaladdressvalidto</span></span><br><span data-ttu-id="25d05-165">*Desplazamineto de fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="25d05-165">*Date Time Offset*</span></span> | <span data-ttu-id="25d05-166">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="25d05-166">Read-only</span></span> <br><span data-ttu-id="25d05-167">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="25d05-167">Required</span></span> | <span data-ttu-id="25d05-168">Fecha hasta la cual es válida la dirección.</span><span class="sxs-lookup"><span data-stu-id="25d05-168">The date the address is valid to.</span></span>  |
| <span data-ttu-id="25d05-169">**Id. de ubicación**</span><span class="sxs-lookup"><span data-stu-id="25d05-169">**Location ID**</span></span><br><span data-ttu-id="25d05-170">mshr_locationidbr>*String*</span><span class="sxs-lookup"><span data-stu-id="25d05-170">mshr_locationidbr>*String*</span></span> | <span data-ttu-id="25d05-171">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="25d05-171">Read-only</span></span> <br><span data-ttu-id="25d05-172">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="25d05-172">Required</span></span> | <span data-ttu-id="25d05-173">El id. para la dirección.</span><span class="sxs-lookup"><span data-stu-id="25d05-173">The ID for the address.</span></span>  |
| <span data-ttu-id="25d05-174">**Código postal**</span><span class="sxs-lookup"><span data-stu-id="25d05-174">**Postal code**</span></span><br><span data-ttu-id="25d05-175">mshr_zipcode</span><span class="sxs-lookup"><span data-stu-id="25d05-175">mshr_zipcode</span></span><br><span data-ttu-id="25d05-176">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="25d05-176">*String*</span></span> | <span data-ttu-id="25d05-177">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="25d05-177">Read-only</span></span> <br><span data-ttu-id="25d05-178">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="25d05-178">Required</span></span> |<span data-ttu-id="25d05-179">El número de identificación definido para el empleado.</span><span class="sxs-lookup"><span data-stu-id="25d05-179">The identification number defined for the employee.</span></span>  |
| <span data-ttu-id="25d05-180">**Vivió en dirección**</span><span class="sxs-lookup"><span data-stu-id="25d05-180">**Lived in address**</span></span><br><span data-ttu-id="25d05-181">mshr_islivedinaddressbr>*String*</span><span class="sxs-lookup"><span data-stu-id="25d05-181">mshr_islivedinaddressbr>*String*</span></span> | <span data-ttu-id="25d05-182">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="25d05-182">Read-only</span></span><br><span data-ttu-id="25d05-183">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="25d05-183">Required</span></span> | <span data-ttu-id="25d05-184">Indica si la dirección es donde vive el empleado.</span><span class="sxs-lookup"><span data-stu-id="25d05-184">Denotes if the address is where the employee lives.</span></span> |
| <span data-ttu-id="25d05-185">**Estado o provincia**</span><span class="sxs-lookup"><span data-stu-id="25d05-185">**State**</span></span><br><span data-ttu-id="25d05-186">mshr_state</span><span class="sxs-lookup"><span data-stu-id="25d05-186">mshr_state</span></span><br><span data-ttu-id="25d05-187">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="25d05-187">*String*</span></span> | <span data-ttu-id="25d05-188">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="25d05-188">Read-only</span></span><br><span data-ttu-id="25d05-189">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="25d05-189">Required</span></span> | <span data-ttu-id="25d05-190">Estado deifnido para la dirección.</span><span class="sxs-lookup"><span data-stu-id="25d05-190">The state defined for the address.</span></span>  |

## <a name="example-query"></a><span data-ttu-id="25d05-191">Consulta de ejemplo</span><span class="sxs-lookup"><span data-stu-id="25d05-191">Example query</span></span>

<span data-ttu-id="25d05-192">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="25d05-192">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="25d05-193">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="25d05-193">**Response**</span></span>

```json
{
            "mshr_personnelnumber": "000041",
            "mshr_locationid": "000000538",
            "mshr_islivedinaddress": 200000001,
            "mshr_isworkedinaddress": 200000000,
            "mshr_countryregionid": "USA",
            "mshr_zipcode": "99025",
            "mshr_street": "6543 Cypress Ave",
            "mshr_city": "Tacoma",
            "mshr_state": "WA",
            "mshr_county": "KING",
            "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
            "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
            "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
            "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```
