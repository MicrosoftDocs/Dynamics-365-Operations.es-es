---
title: Dirección del trabajador de la nómina
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad de dirección de trabajador de nóminas en Dynamics 365 Human Resources.
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
ms.openlocfilehash: 6d93c38b21e953446142fc32cc2a0911616ac61d
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5882070"
---
# <a name="payroll-worker-address"></a><span data-ttu-id="1b785-103">Dirección del trabajador de la nómina</span><span class="sxs-lookup"><span data-stu-id="1b785-103">Payroll worker address</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1b785-104">Este tema proporciona detalles y una consulta de ejemplo para la entidad de dirección de trabajador de nóminas en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1b785-104">This topic provides details and an example query for the Payroll worker address entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="1b785-105">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1b785-105">Properties</span></span>

| <span data-ttu-id="1b785-106">Propiedad</span><span class="sxs-lookup"><span data-stu-id="1b785-106">Property</span></span><br><span data-ttu-id="1b785-107">**Nombre físico**</span><span class="sxs-lookup"><span data-stu-id="1b785-107">**Physical name**</span></span><br><span data-ttu-id="1b785-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="1b785-108">**_Type_**</span></span> | <span data-ttu-id="1b785-109">Utilizar</span><span class="sxs-lookup"><span data-stu-id="1b785-109">Use</span></span> | <span data-ttu-id="1b785-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b785-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="1b785-111">**Ciudad**</span><span class="sxs-lookup"><span data-stu-id="1b785-111">**City**</span></span><br><span data-ttu-id="1b785-112">mshr_city</span><span class="sxs-lookup"><span data-stu-id="1b785-112">mshr_city</span></span><br><span data-ttu-id="1b785-113">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="1b785-113">*String*</span></span> | <span data-ttu-id="1b785-114">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="1b785-114">Read-only</span></span><br><span data-ttu-id="1b785-115">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="1b785-115">Required</span></span> | <span data-ttu-id="1b785-116">Ciudad deifnida para la dirección.</span><span class="sxs-lookup"><span data-stu-id="1b785-116">The city defined for the address.</span></span>   |
| <span data-ttu-id="1b785-117">**Número de personal**</span><span class="sxs-lookup"><span data-stu-id="1b785-117">**Personnel number**</span></span><br><span data-ttu-id="1b785-118">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="1b785-118">mshr_personnelnumber</span></span><br><span data-ttu-id="1b785-119">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="1b785-119">*String*</span></span> | <span data-ttu-id="1b785-120">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="1b785-120">Read-only</span></span><br><span data-ttu-id="1b785-121">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="1b785-121">Required</span></span> | <span data-ttu-id="1b785-122">El número de personal exclusivo del empleado.</span><span class="sxs-lookup"><span data-stu-id="1b785-122">The employee's unique personnel number.</span></span>  |
| <span data-ttu-id="1b785-123">**Región del país**</span><span class="sxs-lookup"><span data-stu-id="1b785-123">**Country region**</span></span><br><span data-ttu-id="1b785-124">mshr_countryregionid</span><span class="sxs-lookup"><span data-stu-id="1b785-124">mshr_countryregionid</span></span><br><span data-ttu-id="1b785-125">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="1b785-125">*String*</span></span> | <span data-ttu-id="1b785-126">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="1b785-126">Read-only</span></span><br><span data-ttu-id="1b785-127">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="1b785-127">Required</span></span> | <span data-ttu-id="1b785-128">Región del país para la dirección.</span><span class="sxs-lookup"><span data-stu-id="1b785-128">The country region defined for the address</span></span>  |
| <span data-ttu-id="1b785-129">**Válido desde**</span><span class="sxs-lookup"><span data-stu-id="1b785-129">**Valid from**</span></span><br><span data-ttu-id="1b785-130">mshr_postaladdressvalidfrom</span><span class="sxs-lookup"><span data-stu-id="1b785-130">mshr_postaladdressvalidfrom</span></span><br><span data-ttu-id="1b785-131">*Desplazamineto de fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="1b785-131">*Date Time Offset*</span></span> | <span data-ttu-id="1b785-132">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="1b785-132">Read-only</span></span> <br><span data-ttu-id="1b785-133">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="1b785-133">Required</span></span> | <span data-ttu-id="1b785-134">Fecha a partir de la cual es válida la dirección.</span><span class="sxs-lookup"><span data-stu-id="1b785-134">The date the address is valid from.</span></span> |
| <span data-ttu-id="1b785-135">**Trabajó en dirección**</span><span class="sxs-lookup"><span data-stu-id="1b785-135">**Worked in address**</span></span><br><span data-ttu-id="1b785-136">mshr_isworkedinaddressbr>*Int32*</span><span class="sxs-lookup"><span data-stu-id="1b785-136">mshr_isworkedinaddressbr>*Int32*</span></span> | <span data-ttu-id="1b785-137">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="1b785-137">Read-only</span></span><br><span data-ttu-id="1b785-138">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="1b785-138">Required</span></span> | <span data-ttu-id="1b785-139">Indica si la dirección es donde trabaja el empleado.</span><span class="sxs-lookup"><span data-stu-id="1b785-139">Denotes if the address is where the employee works.</span></span> |
| <span data-ttu-id="1b785-140">**Provincia**</span><span class="sxs-lookup"><span data-stu-id="1b785-140">**County**</span></span><br><span data-ttu-id="1b785-141">mshr_county</span><span class="sxs-lookup"><span data-stu-id="1b785-141">mshr_county</span></span><br><span data-ttu-id="1b785-142">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="1b785-142">*String*</span></span> | <span data-ttu-id="1b785-143">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="1b785-143">Read-only</span></span><br><span data-ttu-id="1b785-144">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="1b785-144">Required</span></span> | <span data-ttu-id="1b785-145">Condado deifnido para la dirección.</span><span class="sxs-lookup"><span data-stu-id="1b785-145">The county defined for the address.</span></span>  |
| <span data-ttu-id="1b785-146">**Id. de dirección del trabajador de la nómina**</span><span class="sxs-lookup"><span data-stu-id="1b785-146">**Payroll worker address ID**</span></span><br><span data-ttu-id="1b785-147">mshr_payrollworkeraddressentityid</span><span class="sxs-lookup"><span data-stu-id="1b785-147">mshr_payrollworkeraddressentityid</span></span><br><span data-ttu-id="1b785-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="1b785-148">*GUID*</span></span> | <span data-ttu-id="1b785-149">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="1b785-149">Required</span></span><br><span data-ttu-id="1b785-150">Generado por el sistema</span><span class="sxs-lookup"><span data-stu-id="1b785-150">System generated</span></span> | <span data-ttu-id="1b785-151">Valor GUID generado por el sistema para identificar de forma única la dirección.</span><span class="sxs-lookup"><span data-stu-id="1b785-151">A system-generated GUID value to uniquely identify the address.</span></span>  |
| <span data-ttu-id="1b785-152">**Campo primario**</span><span class="sxs-lookup"><span data-stu-id="1b785-152">**Primary field**</span></span><br><span data-ttu-id="1b785-153">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="1b785-153">mshr_primaryfield</span></span><br><span data-ttu-id="1b785-154">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="1b785-154">*String*</span></span> | <span data-ttu-id="1b785-155">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="1b785-155">Read-only</span></span><br><span data-ttu-id="1b785-156">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="1b785-156">Required</span></span> |  |
| <span data-ttu-id="1b785-157">**Calle**</span><span class="sxs-lookup"><span data-stu-id="1b785-157">**Street**</span></span><br><span data-ttu-id="1b785-158">mshr_street</span><span class="sxs-lookup"><span data-stu-id="1b785-158">mshr_street</span></span><br><span data-ttu-id="1b785-159">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="1b785-159">*String*</span></span> | <span data-ttu-id="1b785-160">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="1b785-160">Read-only</span></span><br><span data-ttu-id="1b785-161">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="1b785-161">Required</span></span> | <span data-ttu-id="1b785-162">Calle deifnida para la dirección.</span><span class="sxs-lookup"><span data-stu-id="1b785-162">The street defined for the address.</span></span> |
| <span data-ttu-id="1b785-163">**Válido hasta**</span><span class="sxs-lookup"><span data-stu-id="1b785-163">**Valid to**</span></span><br><span data-ttu-id="1b785-164">mshr_postaladdressvalidto</span><span class="sxs-lookup"><span data-stu-id="1b785-164">mshr_postaladdressvalidto</span></span><br><span data-ttu-id="1b785-165">*Desplazamineto de fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="1b785-165">*Date Time Offset*</span></span> | <span data-ttu-id="1b785-166">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="1b785-166">Read-only</span></span> <br><span data-ttu-id="1b785-167">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="1b785-167">Required</span></span> | <span data-ttu-id="1b785-168">Fecha hasta la cual es válida la dirección.</span><span class="sxs-lookup"><span data-stu-id="1b785-168">The date the address is valid to.</span></span>  |
| <span data-ttu-id="1b785-169">**Id. de ubicación**</span><span class="sxs-lookup"><span data-stu-id="1b785-169">**Location ID**</span></span><br><span data-ttu-id="1b785-170">mshr_locationidbr>*String*</span><span class="sxs-lookup"><span data-stu-id="1b785-170">mshr_locationidbr>*String*</span></span> | <span data-ttu-id="1b785-171">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="1b785-171">Read-only</span></span> <br><span data-ttu-id="1b785-172">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="1b785-172">Required</span></span> | <span data-ttu-id="1b785-173">El id. para la dirección.</span><span class="sxs-lookup"><span data-stu-id="1b785-173">The ID for the address.</span></span>  |
| <span data-ttu-id="1b785-174">**Código postal**</span><span class="sxs-lookup"><span data-stu-id="1b785-174">**Postal code**</span></span><br><span data-ttu-id="1b785-175">mshr_zipcode</span><span class="sxs-lookup"><span data-stu-id="1b785-175">mshr_zipcode</span></span><br><span data-ttu-id="1b785-176">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="1b785-176">*String*</span></span> | <span data-ttu-id="1b785-177">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="1b785-177">Read-only</span></span> <br><span data-ttu-id="1b785-178">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="1b785-178">Required</span></span> |<span data-ttu-id="1b785-179">El número de identificación definido para el empleado.</span><span class="sxs-lookup"><span data-stu-id="1b785-179">The identification number defined for the employee.</span></span>  |
| <span data-ttu-id="1b785-180">**Vivió en dirección**</span><span class="sxs-lookup"><span data-stu-id="1b785-180">**Lived in address**</span></span><br><span data-ttu-id="1b785-181">mshr_islivedinaddressbr>*String*</span><span class="sxs-lookup"><span data-stu-id="1b785-181">mshr_islivedinaddressbr>*String*</span></span> | <span data-ttu-id="1b785-182">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="1b785-182">Read-only</span></span><br><span data-ttu-id="1b785-183">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="1b785-183">Required</span></span> | <span data-ttu-id="1b785-184">Indica si la dirección es donde vive el empleado.</span><span class="sxs-lookup"><span data-stu-id="1b785-184">Denotes if the address is where the employee lives.</span></span> |
| <span data-ttu-id="1b785-185">**Estado o provincia**</span><span class="sxs-lookup"><span data-stu-id="1b785-185">**State**</span></span><br><span data-ttu-id="1b785-186">mshr_state</span><span class="sxs-lookup"><span data-stu-id="1b785-186">mshr_state</span></span><br><span data-ttu-id="1b785-187">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="1b785-187">*String*</span></span> | <span data-ttu-id="1b785-188">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="1b785-188">Read-only</span></span><br><span data-ttu-id="1b785-189">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="1b785-189">Required</span></span> | <span data-ttu-id="1b785-190">Estado deifnido para la dirección.</span><span class="sxs-lookup"><span data-stu-id="1b785-190">The state defined for the address.</span></span>  |

## <a name="example-query"></a><span data-ttu-id="1b785-191">Consulta de ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b785-191">Example query</span></span>

<span data-ttu-id="1b785-192">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="1b785-192">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="1b785-193">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="1b785-193">**Response**</span></span>

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
